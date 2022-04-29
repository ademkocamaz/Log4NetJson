# Log4NetJson
Log4Net en basit hali ile çalışan Json formatında konsol uygulaması.
### Yapılacaklar
AssemblyInfo.cs içerisine 

    [assembly: log4net.Config.XmlConfigurator]

App.config içerisine

    <configSections>
        <section name="log4net" type="log4net.Config.Log4NetConfigurationSectionHandler, log4net" />
    </configSections>
    <appSettings>
        <add key="log4net.Config" value="log4.config"/>
        <add key="log4net.Config.Watch" value="True"/>
        <add key="log4net.Internal.Debug" value="False"/>
    </appSettings>
    <log4net>
        <appender name="JsonFileAppender" type="log4net.Appender.FileAppender">
			    <file value="log.json" />
			    <layout type="Log4NetJson.Jsonlayout" />
		    </appender>
		  <root>
			  <level value="ALL"/>
			  <appender-ref ref="JsonFileAppender"/>
		  </root>
	</log4net>


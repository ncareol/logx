# -*- python -*-

env = Environment(tools = Split('default doxygen log4cpp'))

sources = Split("""
 Logging.cc LogLayout.cc LogAppender.cc system_error.cc
""")
headers = Split("""
 CaptureStream.h EventSource.h Logging.h Checks.h
 system_error.h
""")

objects = env.SharedObject(sources)
liblogx = env.Library('logx', objects)
Default(liblogx)

env.InstallLibrary(liblogx)
env.InstallHeaders('logx', headers)

env['DOXYFILE_DICT'].update({ "PROJECT_NAME" : "logx library" })
env.Apidocs(sources + headers + ["private/LogLayout.h"])

SConscript("tests/SConscript")

# WiaTrcLib::InitTraceModule(ushort *)

- ea: `0x180075de8`
- end: `0x180075f34`
- name: `?InitTraceModule@WiaTrcLib@@YAJPEAG@Z`
- size: `332`
- prototype: `__int64 __fastcall(WiaTrcLib *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x1800767cc`

## callees

- `0x180075de8`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180075dfb`
- `KERNEL32!LoadLibraryExW` at `0x180075dfb`
- `KERNEL32!GetProcAddress` at `0x180075e1b`
- `KERNEL32!GetProcAddress` at `0x180075e36`
- `KERNEL32!GetProcAddress` at `0x180075e51`
- `KERNEL32!GetProcAddress` at `0x180075e6c`
- `KERNEL32!GetProcAddress` at `0x180075e87`
- `KERNEL32!GetProcAddress` at `0x180075ea2`
- `KERNEL32!GetProcAddress` at `0x180075ebd`
- `KERNEL32!GetProcAddress` at `0x180075ed8`
- `KERNEL32!GetProcAddress` at `0x180075e1b`
- `KERNEL32!GetProcAddress` at `0x180075e36`
- `KERNEL32!GetProcAddress` at `0x180075e51`
- `KERNEL32!GetProcAddress` at `0x180075e6c`
- `KERNEL32!GetProcAddress` at `0x180075e87`
- `KERNEL32!GetProcAddress` at `0x180075ea2`
- `KERNEL32!GetProcAddress` at `0x180075ebd`
- `KERNEL32!GetProcAddress` at `0x180075ed8`

## string_xrefs

- `0x180075dee`: `wiatrace.dll`

## pseudocode

```c
__int64 __fastcall WiaTrcLib::InitTraceModule(WiaTrcLib *this, unsigned __int16 *a2)
{
  HMODULE Library; // rax

  Library = LoadLibraryExW(L"wiatrace.dll", 0, 0x800u);
  WiaTrcLib::g_WiaTrc_hDllInstance = Library;
  if ( Library )
  {
    WiaTrcLib::g_WiaTrc_Init = (void (*)(struct HINSTANCE__ *, const char *))GetProcAddress(Library, "WIATRACE_Init");
    WiaTrcLib::g_WiaTrc_Term = (void (*)(void))GetProcAddress(WiaTrcLib::g_WiaTrc_hDllInstance, "WIATRACE_Term");
    WiaTrcLib::g_WiaTrc_OutputString = (void (*)(int, void *, void *, HINSTANCE, const char *, struct _SYSTEMTIME *, unsigned int, unsigned int, struct tagWiaTraceData_Type *))GetProcAddress(WiaTrcLib::g_WiaTrc_hDllInstance, "WIATRACE_OutputString");
    WiaTrcLib::g_WiaTrc_IncrementIndentLevel = (unsigned int (*)(void))GetProcAddress(
                                                                         WiaTrcLib::g_WiaTrc_hDllInstance,
                                                                         "WIATRACE_IncrementIndentLevel");
    WiaTrcLib::g_WiaTrc_DecrementIndentLevel = (unsigned int (*)(void))GetProcAddress(
                                                                         WiaTrcLib::g_WiaTrc_hDllInstance,
                                                                         "WIATRACE_DecrementIndentLevel");
    WiaTrcLib::g_WiaTrc_GetIndentLevel = (unsigned int (*)(void))GetProcAddress(
                                                                   WiaTrcLib::g_WiaTrc_hDllInstance,
                                                                   "WIATRACE_GetIndentLevel");
    WiaTrcLib::g_WiaTrc_SetTraceSettings = (void (*)(unsigned int, unsigned int, int))GetProcAddress(
                                                                                        WiaTrcLib::g_WiaTrc_hDllInstance,
                                                                                        "WIATRACE_SetTraceSettings");
    WiaTrcLib::g_WiaTrc_GetTraceSettings = (void (*)(unsigned int *, unsigned int *, int *))GetProcAddress(
                                                                                              WiaTrcLib::g_WiaTrc_hDllInstance,
                                                                                              "WIATRACE_GetTraceSettings");
  }
  if ( !WiaTrcLib::g_WiaTrc_Init || !WiaTrcLib::g_WiaTrc_Term || !WiaTrcLib::g_WiaTrc_OutputString )
  {
    WiaTrcLib::g_WiaTrc_Init = (void (*)(struct HINSTANCE__ *, const char *))wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
    WiaTrcLib::g_WiaTrc_Term = (void (*)(void))wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
    WiaTrcLib::g_WiaTrc_OutputString = (void (*)(int, void *, void *, HINSTANCE, const char *, struct _SYSTEMTIME *, unsigned int, unsigned int, struct tagWiaTraceData_Type *))wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
  }
  return 0;
}

```

## disassembly

```asm
0x180075de8  sub     rsp, 28h
0x180075dec  xor     edx, edx; hFile
0x180075dee  lea     rcx, aWiatraceDll; "wiatrace.dll"
0x180075df5  mov     r8d, 800h; dwFlags
0x180075dfb  call    cs:__imp_LoadLibraryExW
0x180075e01  mov     cs:?g_WiaTrc_hDllInstance@WiaTrcLib@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * WiaTrcLib::g_WiaTrc_hDllInstance
0x180075e08  test    rax, rax
0x180075e0b  jz      loc_180075EE5
0x180075e11  lea     rdx, aWiatraceInit; "WIATRACE_Init"
0x180075e18  mov     rcx, rax; hModule
0x180075e1b  call    cs:__imp_GetProcAddress
0x180075e21  mov     rcx, cs:?g_WiaTrc_hDllInstance@WiaTrcLib@@3PEAUHINSTANCE__@@EA; hModule
0x180075e28  lea     rdx, aWiatraceTerm; "WIATRACE_Term"
0x180075e2f  mov     cs:?g_WiaTrc_Init@WiaTrcLib@@3P6AXPEAUHINSTANCE__@@PEBD@ZEA, rax; void (*WiaTrcLib::g_WiaTrc_Init)(HINSTANCE__ *,char const *)
0x180075e36  call    cs:__imp_GetProcAddress
0x180075e3c  mov     rcx, cs:?g_WiaTrc_hDllInstance@WiaTrcLib@@3PEAUHINSTANCE__@@EA; hModule
0x180075e43  lea     rdx, aWiatraceOutput; "WIATRACE_OutputString"
0x180075e4a  mov     cs:?g_WiaTrc_Term@WiaTrcLib@@3P6AXXZEA, rax; void (*WiaTrcLib::g_WiaTrc_Term)(void)
0x180075e51  call    cs:__imp_GetProcAddress
0x180075e57  mov     rcx, cs:?g_WiaTrc_hDllInstance@WiaTrcLib@@3PEAUHINSTANCE__@@EA; hModule
0x180075e5e  lea     rdx, aWiatraceIncrem; "WIATRACE_IncrementIndentLevel"
0x180075e65  mov     cs:?g_WiaTrc_OutputString@WiaTrcLib@@3P6AXHPEAX0PEAUHINSTANCE__@@PEBDPEAU_SYSTEMTIME@@KKPEAUtagWiaTraceData_Type@@@ZEA, rax; void (*WiaTrcLib::g_WiaTrc_OutputString)(int,void *,void *,HINSTANCE__ *,char const *,_SYSTEMTIME *,ulong,ulong,tagWiaTraceData_Type *)
0x180075e6c  call    cs:__imp_GetProcAddress
0x180075e72  mov     rcx, cs:?g_WiaTrc_hDllInstance@WiaTrcLib@@3PEAUHINSTANCE__@@EA; hModule
0x180075e79  lea     rdx, aWiatraceDecrem; "WIATRACE_DecrementIndentLevel"
0x180075e80  mov     cs:?g_WiaTrc_IncrementIndentLevel@WiaTrcLib@@3P6AKXZEA, rax; ulong (*WiaTrcLib::g_WiaTrc_IncrementIndentLevel)(void)
0x180075e87  call    cs:__imp_GetProcAddress
0x180075e8d  mov     rcx, cs:?g_WiaTrc_hDllInstance@WiaTrcLib@@3PEAUHINSTANCE__@@EA; hModule
0x180075e94  lea     rdx, aWiatraceGetind; "WIATRACE_GetIndentLevel"
0x180075e9b  mov     cs:?g_WiaTrc_DecrementIndentLevel@WiaTrcLib@@3P6AKXZEA, rax; ulong (*WiaTrcLib::g_WiaTrc_DecrementIndentLevel)(void)
0x180075ea2  call    cs:__imp_GetProcAddress
0x180075ea8  mov     rcx, cs:?g_WiaTrc_hDllInstance@WiaTrcLib@@3PEAUHINSTANCE__@@EA; hModule
0x180075eaf  lea     rdx, aWiatraceSettra; "WIATRACE_SetTraceSettings"
0x180075eb6  mov     cs:?g_WiaTrc_GetIndentLevel@WiaTrcLib@@3P6AKXZEA, rax; ulong (*WiaTrcLib::g_WiaTrc_GetIndentLevel)(void)
0x180075ebd  call    cs:__imp_GetProcAddress
0x180075ec3  mov     rcx, cs:?g_WiaTrc_hDllInstance@WiaTrcLib@@3PEAUHINSTANCE__@@EA; hModule
0x180075eca  lea     rdx, aWiatraceGettra; "WIATRACE_GetTraceSettings"
0x180075ed1  mov     cs:?g_WiaTrc_SetTraceSettings@WiaTrcLib@@3P6AXKKH@ZEA, rax; void (*WiaTrcLib::g_WiaTrc_SetTraceSettings)(ulong,ulong,int)
0x180075ed8  call    cs:__imp_GetProcAddress
0x180075ede  mov     cs:?g_WiaTrc_GetTraceSettings@WiaTrcLib@@3P6AXPEAK0PEAH@ZEA, rax; void (*WiaTrcLib::g_WiaTrc_GetTraceSettings)(ulong *,ulong *,int *)
0x180075ee5  cmp     cs:?g_WiaTrc_Init@WiaTrcLib@@3P6AXPEAUHINSTANCE__@@PEBD@ZEA, 0; void (*WiaTrcLib::g_WiaTrc_Init)(HINSTANCE__ *,char const *)
0x180075eed  jz      short loc_180075F03
0x180075eef  cmp     cs:?g_WiaTrc_Term@WiaTrcLib@@3P6AXXZEA, 0; void (*WiaTrcLib::g_WiaTrc_Term)(void)
0x180075ef7  jz      short loc_180075F03
0x180075ef9  cmp     cs:?g_WiaTrc_OutputString@WiaTrcLib@@3P6AXHPEAX0PEAUHINSTANCE__@@PEBDPEAU_SYSTEMTIME@@KKPEAUtagWiaTraceData_Type@@@ZEA, 0; void (*WiaTrcLib::g_WiaTrc_OutputString)(int,void *,void *,HINSTANCE__ *,char const *,_SYSTEMTIME *,ulong,ulong,tagWiaTraceData_Type *)
0x180075f01  jnz     short loc_180075F2D
0x180075f03  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180075f0a  mov     cs:?g_WiaTrc_Init@WiaTrcLib@@3P6AXPEAUHINSTANCE__@@PEBD@ZEA, rax; void (*WiaTrcLib::g_WiaTrc_Init)(HINSTANCE__ *,char const *)
0x180075f11  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180075f18  mov     cs:?g_WiaTrc_Term@WiaTrcLib@@3P6AXXZEA, rax; void (*WiaTrcLib::g_WiaTrc_Term)(void)
0x180075f1f  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180075f26  mov     cs:?g_WiaTrc_OutputString@WiaTrcLib@@3P6AXHPEAX0PEAUHINSTANCE__@@PEBDPEAU_SYSTEMTIME@@KKPEAUtagWiaTraceData_Type@@@ZEA, rax; void (*WiaTrcLib::g_WiaTrc_OutputString)(int,void *,void *,HINSTANCE__ *,char const *,_SYSTEMTIME *,ulong,ulong,tagWiaTraceData_Type *)
0x180075f2d  xor     eax, eax
0x180075f2f  add     rsp, 28h
0x180075f33  retn
```

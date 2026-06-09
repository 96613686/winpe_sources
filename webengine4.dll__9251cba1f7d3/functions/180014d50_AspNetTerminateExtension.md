# AspNetTerminateExtension

- ea: `0x180014d50`
- end: `0x180014df0`
- name: `AspNetTerminateExtension`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a3e0`
- `0x180013ff0`
- `0x180014d50`
- `0x1800206a4`
- `0x18004bbe0`
- `0x1800504b4`
- `0x180056d88`
- `0x180065b60`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180014db2`
- `KERNEL32!FreeLibrary` at `0x180014db2`
- `KERNEL32!GetProcAddress` at `0x180014d95`
- `KERNEL32!GetProcAddress` at `0x180014d95`
- `KERNEL32!LoadLibraryW` at `0x180014dd7`
- `KERNEL32!LoadLibraryW` at `0x180014dd7`

## string_xrefs

- `0x180014d8e`: `MgdTerminateNativeConfig`

## pseudocode

```c
__int64 AspNetTerminateExtension()
{
  unsigned int v0; // edi
  HMODULE v1; // rcx
  void (*ProcAddress)(void); // rax
  int v3; // ebx

  v0 = 0;
  if ( !g_fUseXSPProcessModel )
  {
    HttpCompletion::DisposeAppDomains();
    ReleaseWmiEventManager();
  }
  v1 = g_hWebEngine;
  if ( g_hWebEngine )
  {
    if ( g_fNativeConfigInited )
    {
      MgdDeInitIsapiModeStatic();
      ProcAddress = (void (*)(void))GetProcAddress(g_hWebEngine, "MgdTerminateNativeConfig");
      if ( ProcAddress )
        ProcAddress();
      v1 = g_hWebEngine;
    }
    if ( v1 )
    {
      FreeLibrary(v1);
      g_hWebEngine = 0;
    }
  }
  ISAPIUninitProcessModel();
  v3 = EtwTraceAspNetUnregister();
  CloseCSP();
  LoadLibraryW(&Names::s_wszEngineFullPath);
  LOBYTE(v0) = v3 == 0;
  return v0;
}

```

## disassembly

```asm
0x180014d50  mov     [rsp+arg_0], rbx
0x180014d55  push    rdi
0x180014d56  sub     rsp, 20h
0x180014d5a  xor     edi, edi
0x180014d5c  cmp     cs:?g_fUseXSPProcessModel@@3HA, edi; int g_fUseXSPProcessModel
0x180014d62  jnz     short loc_180014D6E
0x180014d64  call    ?DisposeAppDomains@HttpCompletion@@SAJXZ; HttpCompletion::DisposeAppDomains(void)
0x180014d69  call    ReleaseWmiEventManager
0x180014d6e  mov     rcx, cs:?g_hWebEngine@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hWebEngine
0x180014d75  test    rcx, rcx
0x180014d78  jz      short loc_180014DBF
0x180014d7a  cmp     cs:?g_fNativeConfigInited@@3HA, edi; int g_fNativeConfigInited
0x180014d80  jz      short loc_180014DAD
0x180014d82  call    ?MgdDeInitIsapiModeStatic@@YAJXZ; MgdDeInitIsapiModeStatic(void)
0x180014d87  mov     rcx, cs:?g_hWebEngine@@3PEAUHINSTANCE__@@EA; hModule
0x180014d8e  lea     rdx, aMgdterminatena_0; "MgdTerminateNativeConfig"
0x180014d95  call    cs:__imp_GetProcAddress
0x180014d9b  test    rax, rax
0x180014d9e  jz      short loc_180014DA6
0x180014da0  call    cs:__guard_dispatch_icall_fptr
0x180014da6  mov     rcx, cs:?g_hWebEngine@@3PEAUHINSTANCE__@@EA; hLibModule
0x180014dad  test    rcx, rcx
0x180014db0  jz      short loc_180014DBF
0x180014db2  call    cs:__imp_FreeLibrary
0x180014db8  mov     cs:?g_hWebEngine@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hWebEngine
0x180014dbf  call    ?ISAPIUninitProcessModel@@YAJXZ; ISAPIUninitProcessModel(void)
0x180014dc4  call    ?EtwTraceAspNetUnregister@@YAJXZ; EtwTraceAspNetUnregister(void)
0x180014dc9  mov     ebx, eax
0x180014dcb  call    ?CloseCSP@@YAJXZ; CloseCSP(void)
0x180014dd0  lea     rcx, ?s_wszEngineFullPath@Names@@0PAGA; lpLibFileName
0x180014dd7  call    cs:__imp_LoadLibraryW
0x180014ddd  test    ebx, ebx
0x180014ddf  mov     rbx, [rsp+28h+arg_0]
0x180014de4  setz    dil
0x180014de8  mov     eax, edi
0x180014dea  add     rsp, 20h
0x180014dee  pop     rdi
0x180014def  retn
```

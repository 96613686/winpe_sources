# GetUsoSvcFunctions(ushort const *)

- ea: `0x180009998`
- end: `0x180009a75`
- name: `?GetUsoSvcFunctions@@YAXPEBG@Z`
- size: `221`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180009bf0`

## callees

- `0x180009998`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800099d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800099e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800099fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009a15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800099d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800099e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800099fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009a15`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180009a69`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180009a69`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800099a6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800099a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a5a`

## string_xrefs

- `0x1800099c6`: `SvchostPushServiceGlobals_Impl`
- `0x1800099d6`: `ServiceMain_Impl`
- `0x1800099ed`: `DllGetClassObject`
- `0x180009a04`: `DllCanUnloadNow`

## pseudocode

```c
void __fastcall GetUsoSvcFunctions(const unsigned __int16 *a1)
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  int (*ProcAddress)(void); // rax
  HMODULE v4; // rcx

  Library = LoadLibraryExW(a1, 0, 0x800u);
  v2 = Library;
  if ( !Library )
  {
    g_ExitCode = GetLastError();
    return;
  }
  g_ServiceHostPushGlobals = (void (*)(struct _SVCHOST_GLOBAL_DATA *))GetProcAddress(
                                                                        Library,
                                                                        "SvchostPushServiceGlobals_Impl");
  g_ServiceMain = (void (*)(unsigned int, unsigned __int16 **))GetProcAddress(v2, "ServiceMain_Impl");
  g_DllGetClassObject = (int (*)(const struct _GUID *, const struct _GUID *, void **))GetProcAddress(
                                                                                        v2,
                                                                                        "DllGetClassObject");
  ProcAddress = (int (*)(void))GetProcAddress(v2, "DllCanUnloadNow");
  g_DllCanUnloadNow = ProcAddress;
  if ( g_ServiceHostPushGlobals && g_ServiceMain && g_DllGetClassObject && ProcAddress )
  {
    v4 = g_UsoSvcImplModule;
    g_UsoSvcImplModule = v2;
    if ( !v4 )
      return;
  }
  else
  {
    g_ExitCode = GetLastError();
    v4 = v2;
  }
  FreeLibrary(v4);
}

```

## disassembly

```asm
0x180009998  push    rbx
0x18000999a  sub     rsp, 20h
0x18000999e  xor     edx, edx; hFile
0x1800099a0  mov     r8d, 800h; dwFlags
0x1800099a6  call    cs:__imp_LoadLibraryExW
0x1800099ac  mov     rbx, rax
0x1800099af  test    rax, rax
0x1800099b2  jnz     short loc_1800099C6
0x1800099b4  call    cs:__imp_GetLastError
0x1800099ba  mov     cs:?g_ExitCode@@3KA, eax; ulong g_ExitCode
0x1800099c0  add     rsp, 20h
0x1800099c4  pop     rbx
0x1800099c5  retn
0x1800099c6  lea     rdx, aSvchostpushser_0; "SvchostPushServiceGlobals_Impl"
0x1800099cd  mov     rcx, rbx; hModule
0x1800099d0  call    cs:__imp_GetProcAddress
0x1800099d6  lea     rdx, aServicemainImp; "ServiceMain_Impl"
0x1800099dd  mov     rcx, rbx; hModule
0x1800099e0  mov     cs:?g_ServiceHostPushGlobals@@3P6AXPEAU_SVCHOST_GLOBAL_DATA@@@ZEA, rax; void (*g_ServiceHostPushGlobals)(_SVCHOST_GLOBAL_DATA *)
0x1800099e7  call    cs:__imp_GetProcAddress
0x1800099ed  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x1800099f4  mov     rcx, rbx; hModule
0x1800099f7  mov     cs:?g_ServiceMain@@3P6AXKPEAPEAG@ZEA, rax; void (*g_ServiceMain)(ulong,ushort * *)
0x1800099fe  call    cs:__imp_GetProcAddress
0x180009a04  lea     rdx, aDllcanunloadno_0; "DllCanUnloadNow"
0x180009a0b  mov     rcx, rbx; hModule
0x180009a0e  mov     cs:?g_DllGetClassObject@@3P6AJAEBU_GUID@@0PEAPEAX@ZEA, rax; long (*g_DllGetClassObject)(_GUID const &,_GUID const &,void * *)
0x180009a15  call    cs:__imp_GetProcAddress
0x180009a1b  cmp     cs:?g_ServiceHostPushGlobals@@3P6AXPEAU_SVCHOST_GLOBAL_DATA@@@ZEA, 0; void (*g_ServiceHostPushGlobals)(_SVCHOST_GLOBAL_DATA *)
0x180009a23  mov     cs:?g_DllCanUnloadNow@@3P6AJXZEA, rax; long (*g_DllCanUnloadNow)(void)
0x180009a2a  jz      short loc_180009A5A
0x180009a2c  cmp     cs:?g_ServiceMain@@3P6AXKPEAPEAG@ZEA, 0; void (*g_ServiceMain)(ulong,ushort * *)
0x180009a34  jz      short loc_180009A5A
0x180009a36  cmp     cs:?g_DllGetClassObject@@3P6AJAEBU_GUID@@0PEAPEAX@ZEA, 0; long (*g_DllGetClassObject)(_GUID const &,_GUID const &,void * *)
0x180009a3e  jz      short loc_180009A5A
0x180009a40  test    rax, rax
0x180009a43  jz      short loc_180009A5A
0x180009a45  mov     rcx, cs:?g_UsoSvcImplModule@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> g_UsoSvcImplModule
0x180009a4c  mov     cs:?g_UsoSvcImplModule@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, rbx; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> g_UsoSvcImplModule
0x180009a53  test    rcx, rcx
0x180009a56  jz      short loc_180009A6F
0x180009a58  jmp     short loc_180009A69
0x180009a5a  call    cs:__imp_GetLastError
0x180009a60  mov     cs:?g_ExitCode@@3KA, eax; ulong g_ExitCode
0x180009a66  mov     rcx, rbx; hLibModule
0x180009a69  call    cs:__imp_FreeLibrary
0x180009a6f  add     rsp, 20h
0x180009a73  pop     rbx
0x180009a74  retn
```

# McGenEventTracingRegister

- ea: `0x180004620`
- end: `0x180004808`
- name: `McGenEventTracingRegister`
- size: `488`
- prototype: `__int64 __fastcall(LPCGUID ControlGuid, WMIDPREQUEST RequestAddress, PTRACEHANDLE RegistrationHandle)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800034b0`
- `0x1800040b8`
- `0x180004620`
- `0x180102010`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1800047e2`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1800047e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18000468e`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18000468e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800046c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800046de`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800046c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800046de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800046f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004712`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000472e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800046f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004712`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000472e`

## string_xrefs

- `0x1800046be`: `advapi32.dll`
- `0x1800046d7`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x1800046ec`: `EventWrite`

## pseudocode

```c
ULONG __fastcall McGenEventTracingRegister(
        LPCGUID ControlGuid,
        WMIDPREQUEST RequestAddress,
        PTRACEHANDLE RegistrationHandle,
        _QWORD *a4)
{
  ULONG result; // eax
  int v9; // edi
  HMODULE ModuleHandleW; // rbx
  ULONG (__stdcall *v11)(WMIDPREQUESTCODE, PVOID, ULONG *, PVOID); // rdx
  ULONG (__stdcall *v12)(WMIDPREQUESTCODE, PVOID, ULONG *, PVOID); // rcx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-178h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-168h] BYREF

  if ( !a4 )
    return 87;
  result = 0;
  if ( *a4 )
    return result;
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  if ( McGenTracingSupportInit )
    goto LABEL_19;
  VersionInformation.dwOSVersionInfoSize = 276;
  v9 = 0;
  if ( !GetVersionExW(&VersionInformation) )
    goto LABEL_10;
  McGenPreVista = VersionInformation.dwMajorVersion < 6;
  if ( VersionInformation.dwMajorVersion > 6
    || VersionInformation.dwMajorVersion == 6 && VersionInformation.dwMinorVersion > 1 )
  {
    v9 = 1;
  }
  if ( VersionInformation.dwMajorVersion >= 6 )
  {
LABEL_10:
    ModuleHandleW = GetModuleHandleW(L"advapi32.dll");
    if ( ModuleHandleW || v9 && (ModuleHandleW = GetModuleHandleW(L"api-ms-win-eventing-provider-l1-1-0.dll")) != 0 )
    {
      PfnEventWrite = (__int64)GetProcAddress(ModuleHandleW, "EventWrite");
      if ( PfnEventWrite )
      {
        PfnEventRegister = (__int64 (__fastcall *)(LPCGUID, WMIDPREQUEST, PTRACEHANDLE))GetProcAddress(
                                                                                          ModuleHandleW,
                                                                                          "EventRegister");
        if ( PfnEventRegister )
        {
          PfnEventUnregister = (__int64)GetProcAddress(ModuleHandleW, "EventUnregister");
          if ( PfnEventUnregister )
            goto LABEL_18;
        }
        PfnEventRegister = McGenEventTracingRegister;
      }
    }
    McGenPreVista = 1;
  }
LABEL_18:
  McGenTracingSupportInit = 1;
LABEL_19:
  if ( !McGenPreVista )
  {
    v11 = (ULONG (__stdcall *)(WMIDPREQUESTCODE, PVOID, ULONG *, PVOID))McGenControlCallbackV2;
    if ( RequestAddress )
      v11 = RequestAddress;
    return PfnEventRegister(ControlGuid, v11, RegistrationHandle);
  }
  if ( !RegistrationHandle )
    return 87;
  v12 = McGenControlCallback;
  if ( RequestAddress )
    v12 = RequestAddress;
  *a4 = RegistrationHandle;
  TraceGuidReg.Guid = ControlGuid;
  TraceGuidReg.RegHandle = 0;
  return RegisterTraceGuidsW(v12, RegistrationHandle, ControlGuid, 1u, &TraceGuidReg, 0, 0, RegistrationHandle);
}

```

## disassembly

```asm
0x180004620  push    rbx
0x180004622  push    rbp
0x180004623  push    rsi
0x180004624  push    rdi
0x180004625  push    r14
0x180004627  push    r15
0x180004629  sub     rsp, 188h
0x180004630  mov     rax, cs:__security_cookie
0x180004637  xor     rax, rsp
0x18000463a  mov     [rsp+1B8h+var_48], rax
0x180004642  mov     r14, r9
0x180004645  mov     rsi, r8
0x180004648  mov     rbp, rdx
0x18000464b  mov     r15, rcx
0x18000464e  test    r9, r9
0x180004651  jz      loc_18000478F
0x180004657  xor     eax, eax
0x180004659  cmp     [r9], rax
0x18000465c  jnz     loc_1800047E8
0x180004662  mov     ebx, 114h
0x180004667  lea     rcx, [rsp+1B8h+VersionInformation]; void *
0x18000466c  mov     r8d, ebx; Size
0x18000466f  xor     edx, edx; Val
0x180004671  call    memset_0
0x180004676  cmp     cs:McGenTracingSupportInit, 0
0x18000467d  jnz     loc_18000475C
0x180004683  lea     rcx, [rsp+1B8h+VersionInformation]; lpVersionInformation
0x180004688  mov     [rsp+1B8h+VersionInformation.dwOSVersionInfoSize], ebx
0x18000468c  xor     edi, edi
0x18000468e  call    cs:__imp_GetVersionExW
0x180004694  test    eax, eax
0x180004696  jz      short loc_1800046BE
0x180004698  cmp     [rsp+1B8h+VersionInformation.dwMajorVersion], 6
0x18000469d  setb    cl
0x1800046a0  mov     cs:McGenPreVista, cl
0x1800046a6  ja      short loc_1800046B1
0x1800046a8  jnz     short loc_1800046B6
0x1800046aa  cmp     [rsp+1B8h+VersionInformation.dwMinorVersion], 1
0x1800046af  jbe     short loc_1800046B6
0x1800046b1  mov     edi, 1
0x1800046b6  test    cl, cl
0x1800046b8  jnz     loc_180004755
0x1800046be  lea     rcx, LibFileName; "advapi32.dll"
0x1800046c5  call    cs:__imp_GetModuleHandleW
0x1800046cb  mov     rbx, rax
0x1800046ce  test    rax, rax
0x1800046d1  jnz     short loc_1800046EC
0x1800046d3  test    edi, edi
0x1800046d5  jz      short loc_18000474E
0x1800046d7  lea     rcx, aApiMsWinEventi_1; "api-ms-win-eventing-provider-l1-1-0.dll"
0x1800046de  call    cs:__imp_GetModuleHandleW
0x1800046e4  mov     rbx, rax
0x1800046e7  test    rax, rax
0x1800046ea  jz      short loc_18000474E
0x1800046ec  lea     rdx, ProcName; "EventWrite"
0x1800046f3  mov     rcx, rbx; hModule
0x1800046f6  call    cs:__imp_GetProcAddress
0x1800046fc  mov     cs:PfnEventWrite, rax
0x180004703  test    rax, rax
0x180004706  jz      short loc_18000474E
0x180004708  lea     rdx, aEventregister; "EventRegister"
0x18000470f  mov     rcx, rbx; hModule
0x180004712  call    cs:__imp_GetProcAddress
0x180004718  mov     cs:PfnEventRegister, rax
0x18000471f  test    rax, rax
0x180004722  jz      short loc_180004740
0x180004724  lea     rdx, aEventunregiste; "EventUnregister"
0x18000472b  mov     rcx, rbx; hModule
0x18000472e  call    cs:__imp_GetProcAddress
0x180004734  mov     cs:PfnEventUnregister, rax
0x18000473b  test    rax, rax
0x18000473e  jnz     short loc_180004755
0x180004740  lea     rax, McGenEventTracingRegister
0x180004747  mov     cs:PfnEventRegister, rax
0x18000474e  mov     cs:McGenPreVista, 1
0x180004755  mov     cs:McGenTracingSupportInit, 1
0x18000475c  cmp     cs:McGenPreVista, 0
0x180004763  jnz     short loc_18000478A
0x180004765  mov     rax, cs:PfnEventRegister
0x18000476c  lea     rdx, McGenControlCallbackV2
0x180004773  test    rbp, rbp
0x180004776  mov     r9, r14
0x180004779  mov     r8, rsi
0x18000477c  mov     rcx, r15
0x18000477f  cmovnz  rdx, rbp
0x180004783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004788  jmp     short loc_1800047E8
0x18000478a  test    rsi, rsi
0x18000478d  jnz     short loc_180004796
0x18000478f  mov     eax, 57h ; 'W'
0x180004794  jmp     short loc_1800047E8
0x180004796  mov     [rsp+1B8h+RegistrationHandle], rsi; RegistrationHandle
0x18000479b  lea     rax, [rsp+1B8h+var_178]
0x1800047a0  test    rbp, rbp
0x1800047a3  mov     [rsp+1B8h+MofResourceName], 0; MofResourceName
0x1800047ac  lea     rcx, McGenControlCallback
0x1800047b3  mov     [rsp+1B8h+MofImagePath], 0; MofImagePath
0x1800047bc  cmovnz  rcx, rbp; RequestAddress
0x1800047c0  mov     [r14], rsi
0x1800047c3  mov     r9d, 1; GuidCount
0x1800047c9  mov     [rsp+1B8h+var_178.Guid], r15
0x1800047ce  mov     r8, r15; ControlGuid
0x1800047d1  mov     [rsp+1B8h+var_178.RegHandle], 0
0x1800047da  mov     rdx, rsi; RequestContext
0x1800047dd  mov     [rsp+1B8h+TraceGuidReg], rax; TraceGuidReg
0x1800047e2  call    cs:__imp_RegisterTraceGuidsW
0x1800047e8  mov     rcx, [rsp+1B8h+var_48]
0x1800047f0  xor     rcx, rsp; StackCookie
0x1800047f3  call    __security_check_cookie
0x1800047f8  add     rsp, 188h
0x1800047ff  pop     r15
0x180004801  pop     r14
0x180004803  pop     rdi
0x180004804  pop     rsi
0x180004805  pop     rbp
0x180004806  pop     rbx
0x180004807  retn
```

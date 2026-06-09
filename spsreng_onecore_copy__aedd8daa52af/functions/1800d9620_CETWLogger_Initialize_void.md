# CETWLogger::Initialize(void)

- ea: `0x1800d9620`
- end: `0x1800d9867`
- name: `?Initialize@CETWLogger@@UEAAJXZ`
- size: `583`
- prototype: `__int64 __fastcall(CETWLogger *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800034b0`
- `0x1800040b8`
- `0x1800d9620`
- `0x1800d98a4`
- `0x180102010`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1800d982d`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1800d982d`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800d96e8`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800d96e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800d971f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800d9738`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800d971f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800d9738`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9750`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d976c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9788`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9750`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d976c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9788`

## string_xrefs

- `0x1800d9718`: `advapi32.dll`
- `0x1800d9731`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x1800d9746`: `EventWrite`

## pseudocode

```c
signed int __fastcall CETWLogger::Initialize(CETWLogger *this, bool a2)
{
  _QWORD *RegistrationHandle; // rdi
  struct _GUID *v3; // rbp
  signed int result; // eax
  int v5; // esi
  HMODULE ModuleHandleW; // rbx
  bool v7; // sf
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-168h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-158h] BYREF

  RegistrationHandle = (_QWORD *)((char *)this + 8);
  v3 = (struct _GUID *)((char *)this + 80);
  *((GUID *)this + 5) = GUID_NULL;
  *((_DWORD *)this + 28) = 0;
  *(_OWORD *)((char *)this + 8) = SYMBOL_PRIVATE_PROVIDER_Context;
  *((GUID *)this + 6) = SYMBOL_PRIVATE_PROVIDER;
  *(_OWORD *)((char *)this + 24) = xmmword_180108E50;
  *(_OWORD *)((char *)this + 40) = xmmword_180108E60;
  *(_OWORD *)((char *)this + 56) = *(_OWORD *)&off_180108E70;
  *((_QWORD *)this + 9) = Microsoft_Speech_SREngine_PrivateLevels;
  *((_QWORD *)this + 7) = (char *)this + 112;
  if ( this != (CETWLogger *)-8LL )
  {
    result = 0;
    if ( *RegistrationHandle )
      goto LABEL_23;
    memset_0(&VersionInformation, 0, sizeof(VersionInformation));
    if ( McGenTracingSupportInit )
    {
LABEL_20:
      if ( McGenPreVista )
      {
        *RegistrationHandle = RegistrationHandle;
        TraceGuidReg.Guid = &SYMBOL_PRIVATE_PROVIDER;
        TraceGuidReg.RegHandle = 0;
        result = RegisterTraceGuidsW(
                   McGenControlCallback,
                   RegistrationHandle,
                   &SYMBOL_PRIVATE_PROVIDER,
                   1u,
                   &TraceGuidReg,
                   0,
                   0,
                   RegistrationHandle);
      }
      else
      {
        result = ((__int64 (__fastcall *)(const GUID *, __int64 (__fastcall *)(int, int, int, int, __int64, int, __int64), _QWORD *, _QWORD *))PfnEventRegister)(
                   &SYMBOL_PRIVATE_PROVIDER,
                   McGenControlCallbackV2,
                   RegistrationHandle,
                   RegistrationHandle);
      }
LABEL_23:
      v7 = result < 0;
      if ( result <= 0 )
        goto LABEL_25;
      goto LABEL_24;
    }
    VersionInformation.dwOSVersionInfoSize = 276;
    v5 = 0;
    if ( !GetVersionExW(&VersionInformation) )
      goto LABEL_11;
    McGenPreVista = VersionInformation.dwMajorVersion < 6;
    if ( VersionInformation.dwMajorVersion > 6
      || VersionInformation.dwMajorVersion == 6 && VersionInformation.dwMinorVersion > 1 )
    {
      v5 = 1;
    }
    if ( VersionInformation.dwMajorVersion >= 6 )
    {
LABEL_11:
      ModuleHandleW = GetModuleHandleW(L"advapi32.dll");
      if ( ModuleHandleW || v5 && (ModuleHandleW = GetModuleHandleW(L"api-ms-win-eventing-provider-l1-1-0.dll")) != 0 )
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
              goto LABEL_19;
          }
          PfnEventRegister = McGenEventTracingRegister;
        }
      }
      McGenPreVista = 1;
    }
LABEL_19:
    McGenTracingSupportInit = 1;
    goto LABEL_20;
  }
  LOWORD(result) = 87;
LABEL_24:
  result = (unsigned __int16)result | 0x80070000;
  v7 = result < 0;
LABEL_25:
  if ( !v7 )
    return CETWLogger::SetCurrentThreadActivityID(this, a2, v3);
  return result;
}

```

## disassembly

```asm
0x1800d9620  push    rbx
0x1800d9622  push    rbp
0x1800d9623  push    rsi
0x1800d9624  push    rdi
0x1800d9625  sub     rsp, 188h
0x1800d962c  mov     rax, cs:__security_cookie
0x1800d9633  xor     rax, rsp
0x1800d9636  mov     [rsp+1A8h+var_38], rax
0x1800d963e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800d9645  lea     rdi, [rcx+8]
0x1800d9649  lea     rax, [rcx+70h]
0x1800d964d  lea     rbp, [rcx+50h]
0x1800d9651  movdqu  xmmword ptr [rbp+0], xmm0
0x1800d9656  movaps  xmm0, cs:SYMBOL_PRIVATE_PROVIDER_Context
0x1800d965d  movups  xmm1, xmmword ptr cs:SYMBOL_PRIVATE_PROVIDER.Data1
0x1800d9664  mov     dword ptr [rax], 0
0x1800d966a  movups  xmmword ptr [rdi], xmm0
0x1800d966d  movaps  xmm0, cs:xmmword_180108E60
0x1800d9674  movdqu  xmmword ptr [rcx+60h], xmm1
0x1800d9679  movaps  xmm1, cs:xmmword_180108E50
0x1800d9680  movups  xmmword ptr [rdi+10h], xmm1
0x1800d9684  movaps  xmm1, xmmword ptr cs:off_180108E70
0x1800d968b  movups  xmmword ptr [rdi+20h], xmm0
0x1800d968f  movsd   xmm0, cs:off_180108E80
0x1800d9697  movups  xmmword ptr [rdi+30h], xmm1
0x1800d969b  movsd   qword ptr [rdi+40h], xmm0
0x1800d96a0  mov     [rcx+38h], rax
0x1800d96a4  test    rdi, rdi
0x1800d96a7  jnz     short loc_1800D96B1
0x1800d96a9  lea     eax, [rdi+57h]
0x1800d96ac  jmp     loc_1800D9837
0x1800d96b1  xor     eax, eax
0x1800d96b3  cmp     [rdi], rax
0x1800d96b6  jnz     loc_1800D9833
0x1800d96bc  mov     ebx, 114h
0x1800d96c1  lea     rcx, [rsp+1A8h+VersionInformation]; void *
0x1800d96c6  mov     r8d, ebx; Size
0x1800d96c9  xor     edx, edx; Val
0x1800d96cb  call    memset_0
0x1800d96d0  cmp     cs:McGenTracingSupportInit, 0
0x1800d96d7  jnz     loc_1800D97B6
0x1800d96dd  lea     rcx, [rsp+1A8h+VersionInformation]; lpVersionInformation
0x1800d96e2  mov     [rsp+1A8h+VersionInformation.dwOSVersionInfoSize], ebx
0x1800d96e6  xor     esi, esi
0x1800d96e8  call    cs:__imp_GetVersionExW
0x1800d96ee  test    eax, eax
0x1800d96f0  jz      short loc_1800D9718
0x1800d96f2  cmp     [rsp+1A8h+VersionInformation.dwMajorVersion], 6
0x1800d96f7  setb    cl
0x1800d96fa  mov     cs:McGenPreVista, cl
0x1800d9700  ja      short loc_1800D970B
0x1800d9702  jnz     short loc_1800D9710
0x1800d9704  cmp     [rsp+1A8h+VersionInformation.dwMinorVersion], 1
0x1800d9709  jbe     short loc_1800D9710
0x1800d970b  mov     esi, 1
0x1800d9710  test    cl, cl
0x1800d9712  jnz     loc_1800D97AF
0x1800d9718  lea     rcx, LibFileName; "advapi32.dll"
0x1800d971f  call    cs:__imp_GetModuleHandleW
0x1800d9725  mov     rbx, rax
0x1800d9728  test    rax, rax
0x1800d972b  jnz     short loc_1800D9746
0x1800d972d  test    esi, esi
0x1800d972f  jz      short loc_1800D97A8
0x1800d9731  lea     rcx, aApiMsWinEventi_1; "api-ms-win-eventing-provider-l1-1-0.dll"
0x1800d9738  call    cs:__imp_GetModuleHandleW
0x1800d973e  mov     rbx, rax
0x1800d9741  test    rax, rax
0x1800d9744  jz      short loc_1800D97A8
0x1800d9746  lea     rdx, ProcName; "EventWrite"
0x1800d974d  mov     rcx, rbx; hModule
0x1800d9750  call    cs:__imp_GetProcAddress
0x1800d9756  mov     cs:PfnEventWrite, rax
0x1800d975d  test    rax, rax
0x1800d9760  jz      short loc_1800D97A8
0x1800d9762  lea     rdx, aEventregister; "EventRegister"
0x1800d9769  mov     rcx, rbx; hModule
0x1800d976c  call    cs:__imp_GetProcAddress
0x1800d9772  mov     cs:PfnEventRegister, rax
0x1800d9779  test    rax, rax
0x1800d977c  jz      short loc_1800D979A
0x1800d977e  lea     rdx, aEventunregiste; "EventUnregister"
0x1800d9785  mov     rcx, rbx; hModule
0x1800d9788  call    cs:__imp_GetProcAddress
0x1800d978e  mov     cs:PfnEventUnregister, rax
0x1800d9795  test    rax, rax
0x1800d9798  jnz     short loc_1800D97AF
0x1800d979a  lea     rax, McGenEventTracingRegister
0x1800d97a1  mov     cs:PfnEventRegister, rax
0x1800d97a8  mov     cs:McGenPreVista, 1
0x1800d97af  mov     cs:McGenTracingSupportInit, 1
0x1800d97b6  cmp     cs:McGenPreVista, 0
0x1800d97bd  jnz     short loc_1800D97E1
0x1800d97bf  mov     rax, cs:PfnEventRegister
0x1800d97c6  lea     rdx, McGenControlCallbackV2
0x1800d97cd  mov     r9, rdi
0x1800d97d0  lea     rcx, SYMBOL_PRIVATE_PROVIDER
0x1800d97d7  mov     r8, rdi
0x1800d97da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d97df  jmp     short loc_1800D9833
0x1800d97e1  mov     [rsp+1A8h+RegistrationHandle], rdi; RegistrationHandle
0x1800d97e6  lea     rax, SYMBOL_PRIVATE_PROVIDER
0x1800d97ed  mov     [rsp+1A8h+MofResourceName], 0; MofResourceName
0x1800d97f6  lea     rcx, [rsp+1A8h+var_168]
0x1800d97fb  mov     [rsp+1A8h+MofImagePath], 0; MofImagePath
0x1800d9804  mov     r9d, 1; GuidCount
0x1800d980a  mov     [rsp+1A8h+TraceGuidReg], rcx; TraceGuidReg
0x1800d980f  mov     r8, rax; ControlGuid
0x1800d9812  lea     rcx, McGenControlCallback; RequestAddress
0x1800d9819  mov     [rdi], rdi
0x1800d981c  mov     rdx, rdi; RequestContext
0x1800d981f  mov     [rsp+1A8h+var_168.Guid], rax
0x1800d9824  mov     [rsp+1A8h+var_168.RegHandle], 0
0x1800d982d  call    cs:__imp_RegisterTraceGuidsW
0x1800d9833  test    eax, eax
0x1800d9835  jle     short loc_1800D9841
0x1800d9837  movzx   eax, ax
0x1800d983a  or      eax, 80070000h
0x1800d983f  test    eax, eax
0x1800d9841  js      short loc_1800D984B
0x1800d9843  mov     r8, rbp; struct _GUID *
0x1800d9846  call    ?SetCurrentThreadActivityID@CETWLogger@@QEAAJ_NPEAU_GUID@@@Z; CETWLogger::SetCurrentThreadActivityID(bool,_GUID *)
0x1800d984b  mov     rcx, [rsp+1A8h+var_38]
0x1800d9853  xor     rcx, rsp; StackCookie
0x1800d9856  call    __security_check_cookie
0x1800d985b  add     rsp, 188h
0x1800d9862  pop     rdi
0x1800d9863  pop     rsi
0x1800d9864  pop     rbp
0x1800d9865  pop     rbx
0x1800d9866  retn
```

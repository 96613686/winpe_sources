# WinSrvExtDllInitialize

- ea: `0x180004c10`
- end: `0x180004dcd`
- name: `WinSrvExtDllInitialize`
- size: `445`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001138`
- `0x180004c10`
- `0x1800138f0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180004d61`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180004d61`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180004c82`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180004c82`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180004ca7`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180004ca7`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180004d8b`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180004d8b`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180004d31`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180004d31`

## pseudocode

```c
BOOL __stdcall WinSrvExtDllInitialize(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  ULONG64 *v3; // rdi
  const GUID **v4; // rsi
  const GUID *v5; // r8
  REGHANDLE v6; // rcx
  _QWORD *v7; // rdi
  TRACEHANDLE v8; // rcx
  GUID ProviderId; // [rsp+40h] [rbp-28h] BYREF

  if ( fdwReason == 1 )
  {
    _security_init_cookie();
    ProviderId = *(GUID *)&(*off_18001D0E0)[-16];
    if ( RegHandle )
      __fastfail(5u);
    xmmword_18001D100 = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_18001D0D8, &RegHandle) )
      EventSetInformation(RegHandle, 2, (char *)off_18001D0E0, *(unsigned __int16 *)off_18001D0E0);
    qword_180021C30 = 0;
    v3 = (ULONG64 *)&WPP_MAIN_CB;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_WinSrvExtTraceGuid;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    v4 = (const GUID **)&WPP_REGISTRATION_GUIDS;
    WPP_MAIN_CB = 0;
    qword_180021C38 = 1;
    do
    {
      v5 = *v4;
      *(_QWORD *)&ProviderId.Data1 = v5;
      ++v4;
      *(_QWORD *)ProviderId.Data4 = 0;
      v3[4] = (ULONG64)v5;
      RegisterTraceGuidsW(WppControlCallback, v3, v5, 1u, (PTRACE_GUID_REGISTRATION)&ProviderId, 0, 0, v3 + 1);
      v3 = (ULONG64 *)*v3;
    }
    while ( v3 );
  }
  else if ( !fdwReason )
  {
    v6 = RegHandle;
    dword_18001D0D8 = 0;
    RegHandle = 0;
    EventUnregister(v6);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      while ( v7 )
      {
        v8 = v7[1];
        if ( v8 )
        {
          UnregisterTraceGuids(v8);
          v7[1] = 0;
        }
        v7 = (_QWORD *)*v7;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180004c10  mov     [rsp+arg_0], rbx
0x180004c15  mov     [rsp+arg_8], rsi
0x180004c1a  push    rdi
0x180004c1b  sub     rsp, 60h
0x180004c1f  mov     rax, cs:__security_cookie
0x180004c26  xor     rax, rsp
0x180004c29  mov     [rsp+68h+var_18], rax
0x180004c2e  cmp     edx, 1
0x180004c31  jnz     loc_180004D47
0x180004c37  call    __security_init_cookie
0x180004c3c  mov     rax, cs:off_18001D0E0
0x180004c43  xor     ebx, ebx
0x180004c45  cmp     cs:RegHandle, rbx
0x180004c4c  movups  xmm0, xmmword ptr [rax-10h]
0x180004c50  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180004c56  jz      short loc_180004C5D
0x180004c58  lea     ecx, [rbx+5]
0x180004c5b  int     29h; Win8: RtlFailFast(ecx)
0x180004c5d  xorps   xmm0, xmm0
0x180004c60  lea     r9, RegHandle; RegHandle
0x180004c67  lea     r8, dword_18001D0D8; CallbackContext
0x180004c6e  lea     rdx, _tlgEnableCallback; EnableCallback
0x180004c75  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180004c7a  movdqu  cs:xmmword_18001D100, xmm0
0x180004c82  call    cs:__imp_EventRegister
0x180004c89  nop     dword ptr [rax+rax+00h]
0x180004c8e  test    eax, eax
0x180004c90  jnz     short loc_180004CB3
0x180004c92  mov     r8, cs:off_18001D0E0
0x180004c99  lea     edx, [rax+2]
0x180004c9c  mov     rcx, cs:RegHandle
0x180004ca3  movzx   r9d, word ptr [r8]
0x180004ca7  call    cs:__imp_EventSetInformation
0x180004cae  nop     dword ptr [rax+rax+00h]
0x180004cb3  lea     rax, WPP_ThisDir_CTLGUID_WinSrvExtTraceGuid
0x180004cba  mov     cs:qword_180021C30, rbx
0x180004cc1  lea     rdi, WPP_MAIN_CB
0x180004cc8  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180004ccf  mov     cs:WPP_GLOBAL_Control, rdi
0x180004cd6  lea     rsi, WPP_REGISTRATION_GUIDS
0x180004cdd  mov     cs:WPP_MAIN_CB, rbx
0x180004ce4  mov     cs:qword_180021C38, 1
0x180004cef  mov     r8, [rsi]; ControlGuid
0x180004cf2  lea     rax, [rdi+8]
0x180004cf6  mov     [rsp+68h+RegistrationHandle], rax; RegistrationHandle
0x180004cfb  lea     rcx, WppControlCallback; RequestAddress
0x180004d02  mov     [rsp+68h+MofResourceName], rbx; MofResourceName
0x180004d07  lea     rax, [rsp+68h+ProviderId]
0x180004d0c  mov     qword ptr [rsp+68h+ProviderId.Data1], r8
0x180004d11  lea     rsi, [rsi+8]
0x180004d15  mov     qword ptr [rsp+68h+ProviderId.Data4], rbx
0x180004d1a  mov     r9d, 1; GuidCount
0x180004d20  mov     [rsp+68h+MofImagePath], rbx; MofImagePath
0x180004d25  mov     rdx, rdi; RequestContext
0x180004d28  mov     [rsp+68h+TraceGuidReg], rax; TraceGuidReg
0x180004d2d  mov     [rdi+20h], r8
0x180004d31  call    cs:__imp_RegisterTraceGuidsW
0x180004d38  nop     dword ptr [rax+rax+00h]
0x180004d3d  mov     rdi, [rdi]
0x180004d40  test    rdi, rdi
0x180004d43  jnz     short loc_180004CEF
0x180004d45  jmp     short loc_180004DAA
0x180004d47  xor     ebx, ebx
0x180004d49  test    edx, edx
0x180004d4b  jnz     short loc_180004DAA
0x180004d4d  mov     rcx, cs:RegHandle; RegHandle
0x180004d54  mov     cs:dword_18001D0D8, ebx
0x180004d5a  mov     cs:RegHandle, rbx
0x180004d61  call    cs:__imp_EventUnregister
0x180004d68  nop     dword ptr [rax+rax+00h]
0x180004d6d  mov     rdi, cs:WPP_GLOBAL_Control
0x180004d74  lea     rsi, WPP_GLOBAL_Control
0x180004d7b  cmp     rdi, rsi
0x180004d7e  jz      short loc_180004DAA
0x180004d80  jmp     short loc_180004D9E
0x180004d82  mov     rcx, [rdi+8]; RegistrationHandle
0x180004d86  test    rcx, rcx
0x180004d89  jz      short loc_180004D9B
0x180004d8b  call    cs:__imp_UnregisterTraceGuids
0x180004d92  nop     dword ptr [rax+rax+00h]
0x180004d97  mov     [rdi+8], rbx
0x180004d9b  mov     rdi, [rdi]
0x180004d9e  test    rdi, rdi
0x180004da1  jnz     short loc_180004D82
0x180004da3  mov     cs:WPP_GLOBAL_Control, rsi
0x180004daa  mov     eax, 1
0x180004daf  mov     rcx, [rsp+68h+var_18]
0x180004db4  xor     rcx, rsp; StackCookie
0x180004db7  call    __security_check_cookie
0x180004dbc  mov     rbx, [rsp+68h+arg_0]
0x180004dc1  mov     rsi, [rsp+68h+arg_8]
0x180004dc6  add     rsp, 60h
0x180004dca  pop     rdi
0x180004dcb  retn
```

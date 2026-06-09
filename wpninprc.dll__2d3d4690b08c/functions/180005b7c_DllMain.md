# DllMain

- ea: `0x180005b7c`
- end: `0x180005d64`
- name: `DllMain`
- size: `488`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001384`

## callees

- `0x180001510`
- `0x18000593c`
- `0x180005b7c`
- `0x180005e78`
- `0x180005eb0`
- `0x180005ee0`
- `0x180005f3c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180005c11`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180005c11`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180005d01`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180005d01`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180005cc6`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180005cc6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005c1e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005c1e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005cdd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005cdd`

## string_xrefs

- `0x180005ba4`: `onecoreuap\base\diagnosis\platform\notifications\inproc\dll\dllmain.cpp`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  int v3; // edi
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  ULONG64 *v7; // rbx
  const GUID **v8; // rsi
  const GUID *v9; // r8
  TRACEHANDLE v10; // rcx
  int v11; // r8d
  int v12; // r9d
  _QWORD *v13; // rbx
  int TraceGuidReg; // [rsp+20h] [rbp-48h]
  struct _TRACE_GUID_REGISTRATION v16; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( hinstDLL )
  {
    v3 = 0;
    if ( fdwReason )
    {
      if ( fdwReason == 1 )
      {
        DisableThreadLibraryCalls(hinstDLL);
        InitializeCriticalSection(&g_CritSec);
        McGenEventRegister_EventRegister();
        if ( (Microsoft_Windows_PushNotifications_InProcEnableBits & 2) != 0 )
          McGenEventWrite_EventWriteTransfer(v4, (int)&WPNINPROC_EVENT_LOAD, v5, v6, (PEVENT_DATA_DESCRIPTOR)&v16);
        qword_18000B430 = 0;
        v7 = (ULONG64 *)&WPP_MAIN_CB;
        WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_Wpn;
        WPP_GLOBAL_Control = &WPP_MAIN_CB;
        v8 = (const GUID **)&WPP_REGISTRATION_GUIDS;
        WPP_MAIN_CB = 0;
        qword_18000B438 = 1;
        do
        {
          v9 = *v8;
          v16.Guid = v9;
          ++v8;
          v16.RegHandle = 0;
          v7[4] = (ULONG64)v9;
          RegisterTraceGuidsW(WppControlCallback, v7, v9, 1u, &v16, 0, 0, v7 + 1);
          v7 = (ULONG64 *)*v7;
        }
        while ( v7 );
      }
    }
    else
    {
      DeleteCriticalSection(&g_CritSec);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        while ( v13 )
        {
          v10 = v13[1];
          if ( v10 )
          {
            UnregisterTraceGuids(v10);
            v13[1] = 0;
          }
          v13 = (_QWORD *)*v13;
        }
        WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
      }
      if ( (Microsoft_Windows_PushNotifications_InProcEnableBits & 2) != 0 )
        McGenEventWrite_EventWriteTransfer(v10, (int)&WPNINPROC_EVENT_UNLOAD, v11, v12, (PEVENT_DATA_DESCRIPTOR)&v16);
      McGenEventUnregister_EventUnregister();
    }
  }
  else
  {
    v3 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\inproc\\dll\\dllmain.cpp",
      (const char *)0x80070057LL,
      TraceGuidReg);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3a96b840b9793ae967b06867319dff15_Traceguids, 2147942487LL);
  }
  return v3 >= 0;
}

```

## disassembly

```asm
0x180005b7c  mov     [rsp+arg_8], rbx
0x180005b81  mov     [rsp+arg_10], rsi
0x180005b86  push    rdi
0x180005b87  sub     rsp, 60h
0x180005b8b  mov     rax, cs:__security_cookie
0x180005b92  xor     rax, rsp
0x180005b95  mov     [rsp+68h+var_18], rax
0x180005b9a  test    rcx, rcx
0x180005b9d  jnz     short loc_180005BFE
0x180005b9f  mov     rcx, [rsp+68h]; this
0x180005ba4  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180005bab  mov     edi, 80070057h
0x180005bb0  mov     edx, 3Ch ; '<'; void *
0x180005bb5  mov     r9d, edi; char *
0x180005bb8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005bbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180005bc4  lea     rsi, WPP_GLOBAL_Control
0x180005bcb  cmp     rcx, rsi
0x180005bce  jz      loc_180005D3E
0x180005bd4  test    byte ptr [rcx+1Ch], 80h
0x180005bd8  jz      loc_180005D3E
0x180005bde  mov     rcx, [rcx+10h]
0x180005be2  lea     r8, WPP_3a96b840b9793ae967b06867319dff15_Traceguids
0x180005be9  mov     edx, 0Ah
0x180005bee  mov     r9d, 80070057h
0x180005bf4  call    WPP_SF_D
0x180005bf9  jmp     loc_180005D3E
0x180005bfe  xor     edi, edi
0x180005c00  test    edx, edx
0x180005c02  jz      loc_180005CD6
0x180005c08  cmp     edx, 1
0x180005c0b  jnz     loc_180005D3E
0x180005c11  call    cs:__imp_DisableThreadLibraryCalls
0x180005c17  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180005c1e  call    cs:__imp_InitializeCriticalSection
0x180005c24  call    McGenEventRegister_EventRegister
0x180005c29  test    cs:Microsoft_Windows_PushNotifications_InProcEnableBits, 2
0x180005c30  jz      short loc_180005C48
0x180005c32  lea     rax, [rsp+68h+var_28]
0x180005c37  lea     rdx, WPNINPROC_EVENT_LOAD; int
0x180005c3e  mov     [rsp+68h+TraceGuidReg], rax; PEVENT_DATA_DESCRIPTOR
0x180005c43  call    McGenEventWrite_EventWriteTransfer
0x180005c48  lea     rax, WPP_ThisDir_CTLGUID_Wpn
0x180005c4f  mov     cs:qword_18000B430, rdi
0x180005c56  lea     rbx, WPP_MAIN_CB
0x180005c5d  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180005c64  mov     cs:WPP_GLOBAL_Control, rbx
0x180005c6b  lea     rsi, WPP_REGISTRATION_GUIDS
0x180005c72  mov     cs:WPP_MAIN_CB, rdi
0x180005c79  mov     cs:qword_18000B438, 1
0x180005c84  mov     r8, [rsi]; ControlGuid
0x180005c87  lea     rax, [rbx+8]
0x180005c8b  mov     [rsp+68h+RegistrationHandle], rax; RegistrationHandle
0x180005c90  lea     rcx, WppControlCallback; RequestAddress
0x180005c97  mov     [rsp+68h+MofResourceName], rdi; MofResourceName
0x180005c9c  lea     rax, [rsp+68h+var_28]
0x180005ca1  mov     [rsp+68h+var_28.Guid], r8
0x180005ca6  lea     rsi, [rsi+8]
0x180005caa  mov     [rsp+68h+var_28.RegHandle], rdi
0x180005caf  mov     r9d, 1; GuidCount
0x180005cb5  mov     [rsp+68h+MofImagePath], rdi; MofImagePath
0x180005cba  mov     rdx, rbx; RequestContext
0x180005cbd  mov     [rsp+68h+TraceGuidReg], rax; TraceGuidReg
0x180005cc2  mov     [rbx+20h], r8
0x180005cc6  call    cs:__imp_RegisterTraceGuidsW
0x180005ccc  mov     rbx, [rbx]
0x180005ccf  test    rbx, rbx
0x180005cd2  jnz     short loc_180005C84
0x180005cd4  jmp     short loc_180005D3E
0x180005cd6  lea     rcx, ?g_CritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180005cdd  call    cs:__imp_DeleteCriticalSection
0x180005ce3  mov     rbx, cs:WPP_GLOBAL_Control
0x180005cea  lea     rsi, WPP_GLOBAL_Control
0x180005cf1  cmp     rbx, rsi
0x180005cf4  jz      short loc_180005D1A
0x180005cf6  jmp     short loc_180005D0E
0x180005cf8  mov     rcx, [rbx+8]; RegistrationHandle
0x180005cfc  test    rcx, rcx
0x180005cff  jz      short loc_180005D0B
0x180005d01  call    cs:__imp_UnregisterTraceGuids
0x180005d07  mov     [rbx+8], rdi
0x180005d0b  mov     rbx, [rbx]
0x180005d0e  test    rbx, rbx
0x180005d11  jnz     short loc_180005CF8
0x180005d13  mov     cs:WPP_GLOBAL_Control, rsi
0x180005d1a  test    cs:Microsoft_Windows_PushNotifications_InProcEnableBits, 2
0x180005d21  jz      short loc_180005D39
0x180005d23  lea     rax, [rsp+68h+var_28]
0x180005d28  lea     rdx, WPNINPROC_EVENT_UNLOAD; int
0x180005d2f  mov     [rsp+68h+TraceGuidReg], rax; PEVENT_DATA_DESCRIPTOR
0x180005d34  call    McGenEventWrite_EventWriteTransfer
0x180005d39  call    McGenEventUnregister_EventUnregister
0x180005d3e  not     edi
0x180005d40  shr     edi, 1Fh
0x180005d43  mov     eax, edi
0x180005d45  mov     rcx, [rsp+68h+var_18]
0x180005d4a  xor     rcx, rsp; StackCookie
0x180005d4d  call    __security_check_cookie
0x180005d52  lea     r11, [rsp+68h+var_8]
0x180005d57  mov     rbx, [r11+18h]
0x180005d5b  mov     rsi, [r11+20h]
0x180005d5f  mov     rsp, r11
0x180005d62  pop     rdi
0x180005d63  retn
```

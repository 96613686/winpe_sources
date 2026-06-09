# DllMain

- ea: `0x180031be8`
- end: `0x180031d32`
- name: `DllMain`
- size: `330`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003a3f4`

## callees

- `0x1800011e4`
- `0x180031be8`
- `0x180031d38`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180031bfa`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180031bfa`
- `ntdll!RtlDeleteCriticalSection` at `0x180031ca3`
- `ntdll!RtlDeleteCriticalSection` at `0x180031ca3`
- `ntdll!RtlNtStatusToDosError` at `0x180031c35`
- `ntdll!RtlNtStatusToDosError` at `0x180031cca`
- `ntdll!RtlNtStatusToDosError` at `0x180031c35`
- `ntdll!RtlNtStatusToDosError` at `0x180031cca`
- `ntdll!RtlInitializeCriticalSection` at `0x180031c0e`
- `ntdll!RtlInitializeCriticalSection` at `0x180031c0e`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  int v4; // edx
  ULONG v5; // eax
  int v7; // eax
  ULONG v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8

  if ( fdwReason != 1 )
  {
    if ( !fdwReason )
    {
      if ( byte_18005F5C4 )
      {
        v7 = RtlDeleteCriticalSection(&CriticalSection);
        *(_QWORD *)&fdwReason = (unsigned int)v7;
        if ( v7 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v8 = RtlNtStatusToDosError(v7);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_78b059fac4093813b2646cef9913e025_Traceguids, v8);
        }
        *(_OWORD *)&CriticalSection.DebugInfo = 0;
        CriticalSection.SpinCount = 0;
        *(_OWORD *)&CriticalSection.OwningThread = 0;
        byte_18005F5C4 = 0;
      }
      TraceLoggingUnregister_EventUnregister(&dword_18005F0C0, *(_QWORD *)&fdwReason, lpvReserved);
      TraceLoggingUnregister_EventUnregister(&dword_18005F088, v9, v10);
    }
    return 1;
  }
  DisableThreadLibraryCalls(hinstDLL);
  hInstance = hinstDLL;
  v4 = RtlInitializeCriticalSection(&CriticalSection);
  if ( v4 >= 0 )
  {
    byte_18005F5C4 = 1;
    byte_18005F5C5 = 0;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18005F0C0);
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18005F088);
    return 1;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v5 = RtlNtStatusToDosError(v4);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_78b059fac4093813b2646cef9913e025_Traceguids, v5);
  }
  return 0;
}

```

## disassembly

```asm
0x180031be8  push    rbx
0x180031bea  sub     rsp, 20h
0x180031bee  mov     rbx, rcx
0x180031bf1  cmp     edx, 1
0x180031bf4  jnz     loc_180031C8C
0x180031bfa  call    cs:__imp_DisableThreadLibraryCalls
0x180031c00  lea     rcx, CriticalSection; CriticalSection
0x180031c07  mov     cs:hInstance, rbx
0x180031c0e  call    cs:__imp_RtlInitializeCriticalSection
0x180031c14  mov     edx, eax
0x180031c16  test    eax, eax
0x180031c18  jns     short loc_180031C61
0x180031c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180031c21  lea     rax, WPP_GLOBAL_Control
0x180031c28  cmp     rcx, rax
0x180031c2b  jz      short loc_180031C5A
0x180031c2d  test    byte ptr [rcx+1Ch], 1
0x180031c31  jz      short loc_180031C5A
0x180031c33  mov     ecx, edx; Status
0x180031c35  call    cs:__imp_RtlNtStatusToDosError
0x180031c3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031c42  lea     r8, WPP_78b059fac4093813b2646cef9913e025_Traceguids
0x180031c49  mov     edx, 18h
0x180031c4e  mov     r9d, eax
0x180031c51  mov     rcx, [rcx+10h]
0x180031c55  call    WPP_SF_d
0x180031c5a  xor     eax, eax
0x180031c5c  jmp     loc_180031D2C
0x180031c61  lea     rcx, dword_18005F0C0; CallbackContext
0x180031c68  mov     cs:byte_18005F5C4, 1
0x180031c6f  mov     cs:byte_18005F5C5, 0
0x180031c76  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180031c7b  lea     rcx, dword_18005F088; CallbackContext
0x180031c82  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180031c87  jmp     loc_180031D27
0x180031c8c  test    edx, edx
0x180031c8e  jnz     loc_180031D27
0x180031c94  cmp     cs:byte_18005F5C4, dl
0x180031c9a  jz      short loc_180031D0F
0x180031c9c  lea     rcx, CriticalSection; CriticalSection
0x180031ca3  call    cs:__imp_RtlDeleteCriticalSection
0x180031ca9  mov     edx, eax
0x180031cab  test    eax, eax
0x180031cad  jns     short loc_180031CEF
0x180031caf  mov     rcx, cs:WPP_GLOBAL_Control
0x180031cb6  lea     rax, WPP_GLOBAL_Control
0x180031cbd  cmp     rcx, rax
0x180031cc0  jz      short loc_180031CEF
0x180031cc2  test    byte ptr [rcx+1Ch], 2
0x180031cc6  jz      short loc_180031CEF
0x180031cc8  mov     ecx, edx; Status
0x180031cca  call    cs:__imp_RtlNtStatusToDosError
0x180031cd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180031cd7  lea     r8, WPP_78b059fac4093813b2646cef9913e025_Traceguids
0x180031cde  mov     edx, 19h
0x180031ce3  mov     r9d, eax
0x180031ce6  mov     rcx, [rcx+10h]
0x180031cea  call    WPP_SF_d
0x180031cef  xorps   xmm0, xmm0
0x180031cf2  xor     ecx, ecx
0x180031cf4  movups  xmmword ptr cs:CriticalSection.DebugInfo, xmm0
0x180031cfb  mov     cs:CriticalSection.SpinCount, rcx
0x180031d02  movups  xmmword ptr cs:CriticalSection.OwningThread, xmm0
0x180031d09  mov     cs:byte_18005F5C4, cl
0x180031d0f  lea     rcx, dword_18005F0C0
0x180031d16  call    TraceLoggingUnregister_EventUnregister
0x180031d1b  lea     rcx, dword_18005F088
0x180031d22  call    TraceLoggingUnregister_EventUnregister
0x180031d27  mov     eax, 1
0x180031d2c  add     rsp, 20h
0x180031d30  pop     rbx
0x180031d31  retn
```

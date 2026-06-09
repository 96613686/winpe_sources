# ServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x18001ad90`
- end: `0x18001ae53`
- name: `?ServiceCtrlHandler@@YAKKKPEAX0@Z`
- size: `195`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x18001ad90`
- `0x1800271fc`
- `0x180029d70`
- `0x180029df0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ae42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ae42`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001adee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001adee`

## pseudocode

```c
__int64 __fastcall ServiceCtrlHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  DWORD v5; // ebx

  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids, dwControl);
  v5 = dwControl - 1;
  if ( !v5 || v5 == 4 )
  {
    EnterCriticalSection(&g_csSsdpRef);
    if ( g_lSsdpRef == -1 )
    {
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids);
    }
    else
    {
      g_lSsdpRef = -1;
      StartServiceShutdown();
    }
    LeaveCriticalSection(&g_csSsdpRef);
  }
  return 0;
}

```

## disassembly

```asm
0x18001ad90  mov     [rsp+arg_0], rbx
0x18001ad95  push    rdi
0x18001ad96  sub     rsp, 20h
0x18001ad9a  mov     ebx, ecx
0x18001ad9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ada3  lea     rdi, WPP_GLOBAL_Control
0x18001adaa  cmp     rcx, rdi
0x18001adad  jz      short loc_18001ADB5
0x18001adaf  test    byte ptr [rcx+1Ch], 8
0x18001adb3  jnz     short loc_18001ADCD
0x18001adb5  sub     ebx, 1
0x18001adb8  jz      short loc_18001ADE7
0x18001adba  cmp     ebx, 4
0x18001adbd  jz      short loc_18001ADE7
0x18001adbf  mov     rbx, [rsp+28h+arg_0]
0x18001adc4  xor     eax, eax
0x18001adc6  add     rsp, 20h
0x18001adca  pop     rdi
0x18001adcb  retn
0x18001adcd  mov     rcx, [rcx+10h]
0x18001add1  lea     r8, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids
0x18001add8  mov     edx, 0Dh
0x18001addd  mov     r9d, ebx
0x18001ade0  call    WPP_SF_d
0x18001ade5  jmp     short loc_18001ADB5
0x18001ade7  lea     rcx, ?g_csSsdpRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001adee  call    cs:__imp_EnterCriticalSection
0x18001adf5  nop     dword ptr [rax+rax+00h]
0x18001adfa  cmp     cs:?g_lSsdpRef@@3JA, 0FFFFFFFFh; long g_lSsdpRef
0x18001ae01  jnz     short loc_18001AE2C
0x18001ae03  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae0a  cmp     rcx, rdi
0x18001ae0d  jz      short loc_18001AE3B
0x18001ae0f  test    byte ptr [rcx+1Ch], 8
0x18001ae13  jz      short loc_18001AE3B
0x18001ae15  mov     rcx, [rcx+10h]
0x18001ae19  lea     r8, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids
0x18001ae20  mov     edx, 0Eh
0x18001ae25  call    WPP_SF_
0x18001ae2a  jmp     short loc_18001AE3B
0x18001ae2c  mov     cs:?g_lSsdpRef@@3JA, 0FFFFFFFFh; long g_lSsdpRef
0x18001ae36  call    ?StartServiceShutdown@@YAXXZ; StartServiceShutdown(void)
0x18001ae3b  lea     rcx, ?g_csSsdpRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ae42  call    cs:__imp_LeaveCriticalSection
0x18001ae49  nop     dword ptr [rax+rax+00h]
0x18001ae4e  jmp     loc_18001ADBF
```

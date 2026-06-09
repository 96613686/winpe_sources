# ServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x180019af0`
- end: `0x180019ba6`
- name: `?ServiceCtrlHandler@@YAKKKPEAX0@Z`
- size: `182`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180019af0`
- `0x1800255a8`
- `0x180027f90`
- `0x180028000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019b9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019b9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019b4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019b4d`

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
0x180019af0  mov     [rsp+arg_0], rbx
0x180019af5  push    rdi
0x180019af6  sub     rsp, 20h
0x180019afa  mov     ebx, ecx
0x180019afc  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b03  lea     rdi, WPP_GLOBAL_Control
0x180019b0a  cmp     rcx, rdi
0x180019b0d  jz      short loc_180019B15
0x180019b0f  test    byte ptr [rcx+1Ch], 8
0x180019b13  jnz     short loc_180019B2C
0x180019b15  sub     ebx, 1
0x180019b18  jz      short loc_180019B46
0x180019b1a  cmp     ebx, 4
0x180019b1d  jz      short loc_180019B46
0x180019b1f  mov     rbx, [rsp+28h+arg_0]
0x180019b24  xor     eax, eax
0x180019b26  add     rsp, 20h
0x180019b2a  pop     rdi
0x180019b2b  retn
0x180019b2c  mov     rcx, [rcx+10h]
0x180019b30  lea     r8, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids
0x180019b37  mov     edx, 0Dh
0x180019b3c  mov     r9d, ebx
0x180019b3f  call    WPP_SF_d
0x180019b44  jmp     short loc_180019B15
0x180019b46  lea     rcx, ?g_csSsdpRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019b4d  call    cs:__imp_EnterCriticalSection
0x180019b53  cmp     cs:?g_lSsdpRef@@3JA, 0FFFFFFFFh; long g_lSsdpRef
0x180019b5a  jnz     short loc_180019B85
0x180019b5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b63  cmp     rcx, rdi
0x180019b66  jz      short loc_180019B94
0x180019b68  test    byte ptr [rcx+1Ch], 8
0x180019b6c  jz      short loc_180019B94
0x180019b6e  mov     rcx, [rcx+10h]
0x180019b72  lea     r8, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids
0x180019b79  mov     edx, 0Eh
0x180019b7e  call    WPP_SF_
0x180019b83  jmp     short loc_180019B94
0x180019b85  mov     cs:?g_lSsdpRef@@3JA, 0FFFFFFFFh; long g_lSsdpRef
0x180019b8f  call    ?StartServiceShutdown@@YAXXZ; StartServiceShutdown(void)
0x180019b94  lea     rcx, ?g_csSsdpRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019b9b  call    cs:__imp_LeaveCriticalSection
0x180019ba1  jmp     loc_180019B1F
```

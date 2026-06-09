# _SSDPCloseRpc

- ea: `0x18002cd60`
- end: `0x18002cf00`
- name: `_SSDPCloseRpc`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002c830`

## callees

- `0x1800255a8`
- `0x180028000`
- `0x18002c8cc`
- `0x18002cd60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cee6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cee6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cdf6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cdf6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002ce9d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002ce9d`

## pseudocode

```c
__int64 __fastcall SSDPCloseRpc(_QWORD *a1)
{
  unsigned int v3; // edi
  int v4; // eax
  LPCSTR v5; // rcx
  __int64 v6; // rdx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( (int *)*a1 != &g_lSsdpRef )
    {
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids, *a1);
      v3 = 6;
      goto LABEL_25;
    }
    EnterCriticalSection(&g_csSsdpRef);
    v4 = g_lSsdpRef;
    if ( g_lSsdpRef == -1 )
    {
      v3 = 1062;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 8) == 0 )
        goto LABEL_24;
      v6 = 14;
    }
    else
    {
      v3 = 0;
      --g_lSsdpRef;
      if ( v4 != 1 )
        goto LABEL_24;
      if ( !g_fShutdownTimerSet )
      {
        pftDueTime.dwHighDateTime = -2;
        pftDueTime.dwLowDateTime = -1705032704;
        SetThreadpoolTimer(g_shutdownTimer, &pftDueTime, 0, 0);
        g_fShutdownTimerSet = 1;
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids, 10);
        goto LABEL_24;
      }
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 8) == 0 )
      {
LABEL_24:
        LeaveCriticalSection(&g_csSsdpRef);
LABEL_25:
        *a1 = 0;
        return v3;
      }
      v6 = 15;
    }
    WPP_SF_(*((_QWORD *)v5 + 2), v6, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids);
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids);
  return 87;
}

```

## disassembly

```asm
0x18002cd60  mov     [rsp+arg_8], rbx
0x18002cd65  push    rdi
0x18002cd66  sub     rsp, 20h
0x18002cd6a  mov     rbx, rcx
0x18002cd6d  test    rcx, rcx
0x18002cd70  jnz     short loc_18002CDA8
0x18002cd72  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd79  lea     rax, WPP_GLOBAL_Control
0x18002cd80  cmp     rcx, rax
0x18002cd83  jz      short loc_18002CD9E
0x18002cd85  test    byte ptr [rcx+1Ch], 1
0x18002cd89  jz      short loc_18002CD9E
0x18002cd8b  mov     rcx, [rcx+10h]
0x18002cd8f  lea     edx, [rbx+0Ch]
0x18002cd92  lea     r8, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids
0x18002cd99  call    WPP_SF_
0x18002cd9e  mov     eax, 57h ; 'W'
0x18002cda3  jmp     loc_18002CEF5
0x18002cda8  lea     rax, ?g_lSsdpRef@@3JA; long g_lSsdpRef
0x18002cdaf  cmp     [rcx], rax
0x18002cdb2  jz      short loc_18002CDEF
0x18002cdb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cdbb  lea     rax, WPP_GLOBAL_Control
0x18002cdc2  cmp     rcx, rax
0x18002cdc5  jz      short loc_18002CDE5
0x18002cdc7  test    byte ptr [rcx+1Ch], 1
0x18002cdcb  jz      short loc_18002CDE5
0x18002cdcd  mov     r9, [rbx]
0x18002cdd0  lea     r8, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids
0x18002cdd7  mov     rcx, [rcx+10h]
0x18002cddb  mov     edx, 0Dh
0x18002cde0  call    WPP_SF_q
0x18002cde5  mov     edi, 6
0x18002cdea  jmp     loc_18002CEEC
0x18002cdef  lea     rcx, ?g_csSsdpRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002cdf6  call    cs:__imp_EnterCriticalSection
0x18002cdfc  mov     eax, cs:?g_lSsdpRef@@3JA; long g_lSsdpRef
0x18002ce02  cmp     eax, 0FFFFFFFFh
0x18002ce05  jnz     short loc_18002CE34
0x18002ce07  mov     edi, 426h
0x18002ce0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce13  lea     rax, WPP_GLOBAL_Control
0x18002ce1a  cmp     rcx, rax
0x18002ce1d  jz      loc_18002CEDF
0x18002ce23  test    byte ptr [rcx+1Ch], 8
0x18002ce27  jz      loc_18002CEDF
0x18002ce2d  mov     edx, 0Eh
0x18002ce32  jmp     short loc_18002CE69
0x18002ce34  xor     edi, edi
0x18002ce36  sub     eax, 1
0x18002ce39  mov     cs:?g_lSsdpRef@@3JA, eax; long g_lSsdpRef
0x18002ce3f  jnz     loc_18002CEDF
0x18002ce45  cmp     cs:?g_fShutdownTimerSet@@3HA, edi; int g_fShutdownTimerSet
0x18002ce4b  jz      short loc_18002CE7B
0x18002ce4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce54  lea     rax, WPP_GLOBAL_Control
0x18002ce5b  cmp     rcx, rax
0x18002ce5e  jz      short loc_18002CEDF
0x18002ce60  test    byte ptr [rcx+1Ch], 8
0x18002ce64  jz      short loc_18002CEDF
0x18002ce66  lea     edx, [rdi+0Fh]
0x18002ce69  mov     rcx, [rcx+10h]
0x18002ce6d  lea     r8, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids
0x18002ce74  call    WPP_SF_
0x18002ce79  jmp     short loc_18002CEDF
0x18002ce7b  mov     rcx, cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA; pti
0x18002ce82  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18002ce87  xor     r9d, r9d; msWindowLength
0x18002ce8a  mov     [rsp+28h+pftDueTime.dwHighDateTime], 0FFFFFFFEh
0x18002ce92  xor     r8d, r8d; msPeriod
0x18002ce95  mov     [rsp+28h+pftDueTime.dwLowDateTime], 9A5F4400h
0x18002ce9d  call    cs:__imp_SetThreadpoolTimer
0x18002cea3  mov     cs:?g_fShutdownTimerSet@@3HA, 1; int g_fShutdownTimerSet
0x18002cead  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ceb4  lea     rax, WPP_GLOBAL_Control
0x18002cebb  cmp     rcx, rax
0x18002cebe  jz      short loc_18002CEDF
0x18002cec0  test    byte ptr [rcx+1Ch], 8
0x18002cec4  jz      short loc_18002CEDF
0x18002cec6  mov     rcx, [rcx+10h]
0x18002ceca  lea     r8, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids
0x18002ced1  mov     edx, 10h
0x18002ced6  lea     r9d, [rdx-6]
0x18002ceda  call    WPP_SF_d
0x18002cedf  lea     rcx, ?g_csSsdpRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002cee6  call    cs:__imp_LeaveCriticalSection
0x18002ceec  mov     qword ptr [rbx], 0
0x18002cef3  mov     eax, edi
0x18002cef5  mov     rbx, [rsp+28h+arg_8]
0x18002cefa  add     rsp, 20h
0x18002cefe  pop     rdi
0x18002ceff  retn
```

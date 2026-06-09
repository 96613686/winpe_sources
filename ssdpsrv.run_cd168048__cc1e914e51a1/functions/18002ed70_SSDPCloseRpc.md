# _SSDPCloseRpc

- ea: `0x18002ed70`
- end: `0x18002ef27`
- name: `_SSDPCloseRpc`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002e800`

## callees

- `0x1800271fc`
- `0x180029df0`
- `0x18002e8ac`
- `0x18002ed70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ef06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ef06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ee06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ee06`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002eeb7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002eeb7`

## pseudocode

```c
__int64 __fastcall SSDPCloseRpc(int **a1)
{
  unsigned int v3; // edi
  int v4; // eax
  LPCSTR v5; // rcx
  __int64 v6; // rdx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( *a1 != &g_lSsdpRef )
    {
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids);
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
0x18002ed70  mov     [rsp+arg_8], rbx
0x18002ed75  push    rdi
0x18002ed76  sub     rsp, 20h
0x18002ed7a  mov     rbx, rcx
0x18002ed7d  test    rcx, rcx
0x18002ed80  jnz     short loc_18002EDB8
0x18002ed82  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed89  lea     rax, WPP_GLOBAL_Control
0x18002ed90  cmp     rcx, rax
0x18002ed93  jz      short loc_18002EDAE
0x18002ed95  test    byte ptr [rcx+1Ch], 1
0x18002ed99  jz      short loc_18002EDAE
0x18002ed9b  mov     rcx, [rcx+10h]
0x18002ed9f  lea     edx, [rbx+0Ch]
0x18002eda2  lea     r8, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids
0x18002eda9  call    WPP_SF_
0x18002edae  mov     eax, 57h ; 'W'
0x18002edb3  jmp     loc_18002EF1B
0x18002edb8  lea     rax, ?g_lSsdpRef@@3JA; long g_lSsdpRef
0x18002edbf  cmp     [rcx], rax
0x18002edc2  jz      short loc_18002EDFF
0x18002edc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002edcb  lea     rax, WPP_GLOBAL_Control
0x18002edd2  cmp     rcx, rax
0x18002edd5  jz      short loc_18002EDF5
0x18002edd7  test    byte ptr [rcx+1Ch], 1
0x18002eddb  jz      short loc_18002EDF5
0x18002eddd  mov     r9, [rbx]
0x18002ede0  lea     r8, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids
0x18002ede7  mov     rcx, [rcx+10h]
0x18002edeb  mov     edx, 0Dh
0x18002edf0  call    WPP_SF_q
0x18002edf5  mov     edi, 6
0x18002edfa  jmp     loc_18002EF12
0x18002edff  lea     rcx, ?g_csSsdpRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002ee06  call    cs:__imp_EnterCriticalSection
0x18002ee0d  nop     dword ptr [rax+rax+00h]
0x18002ee12  mov     eax, cs:?g_lSsdpRef@@3JA; long g_lSsdpRef
0x18002ee18  cmp     eax, 0FFFFFFFFh
0x18002ee1b  jnz     short loc_18002EE4A
0x18002ee1d  mov     edi, 426h
0x18002ee22  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee29  lea     rax, WPP_GLOBAL_Control
0x18002ee30  cmp     rcx, rax
0x18002ee33  jz      loc_18002EEFF
0x18002ee39  test    byte ptr [rcx+1Ch], 8
0x18002ee3d  jz      loc_18002EEFF
0x18002ee43  mov     edx, 0Eh
0x18002ee48  jmp     short loc_18002EE83
0x18002ee4a  xor     edi, edi
0x18002ee4c  sub     eax, 1
0x18002ee4f  mov     cs:?g_lSsdpRef@@3JA, eax; long g_lSsdpRef
0x18002ee55  jnz     loc_18002EEFF
0x18002ee5b  cmp     cs:?g_fShutdownTimerSet@@3HA, edi; int g_fShutdownTimerSet
0x18002ee61  jz      short loc_18002EE95
0x18002ee63  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee6a  lea     rax, WPP_GLOBAL_Control
0x18002ee71  cmp     rcx, rax
0x18002ee74  jz      loc_18002EEFF
0x18002ee7a  test    byte ptr [rcx+1Ch], 8
0x18002ee7e  jz      short loc_18002EEFF
0x18002ee80  lea     edx, [rdi+0Fh]
0x18002ee83  mov     rcx, [rcx+10h]
0x18002ee87  lea     r8, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids
0x18002ee8e  call    WPP_SF_
0x18002ee93  jmp     short loc_18002EEFF
0x18002ee95  mov     rcx, cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA; pti
0x18002ee9c  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18002eea1  xor     r9d, r9d; msWindowLength
0x18002eea4  mov     [rsp+28h+pftDueTime.dwHighDateTime], 0FFFFFFFEh
0x18002eeac  xor     r8d, r8d; msPeriod
0x18002eeaf  mov     [rsp+28h+pftDueTime.dwLowDateTime], 9A5F4400h
0x18002eeb7  call    cs:__imp_SetThreadpoolTimer
0x18002eebe  nop     dword ptr [rax+rax+00h]
0x18002eec3  mov     cs:?g_fShutdownTimerSet@@3HA, 1; int g_fShutdownTimerSet
0x18002eecd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eed4  lea     rax, WPP_GLOBAL_Control
0x18002eedb  cmp     rcx, rax
0x18002eede  jz      short loc_18002EEFF
0x18002eee0  test    byte ptr [rcx+1Ch], 8
0x18002eee4  jz      short loc_18002EEFF
0x18002eee6  mov     rcx, [rcx+10h]
0x18002eeea  lea     r8, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids
0x18002eef1  mov     edx, 10h
0x18002eef6  lea     r9d, [rdx-6]
0x18002eefa  call    WPP_SF_d
0x18002eeff  lea     rcx, ?g_csSsdpRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002ef06  call    cs:__imp_LeaveCriticalSection
0x18002ef0d  nop     dword ptr [rax+rax+00h]
0x18002ef12  mov     qword ptr [rbx], 0
0x18002ef19  mov     eax, edi
0x18002ef1b  mov     rbx, [rsp+28h+arg_8]
0x18002ef20  add     rsp, 20h
0x18002ef24  pop     rdi
0x18002ef25  retn
```

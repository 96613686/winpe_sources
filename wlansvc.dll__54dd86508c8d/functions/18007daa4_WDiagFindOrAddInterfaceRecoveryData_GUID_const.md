# WDiagFindOrAddInterfaceRecoveryData(_GUID const *)

- ea: `0x18007daa4`
- end: `0x18007dd0b`
- name: `?WDiagFindOrAddInterfaceRecoveryData@@YAPEAU_WDIAG_RECOVERY_DATA@@PEBU_GUID@@@Z`
- size: `615`
- prototype: `struct _WDIAG_RECOVERY_DATA *__fastcall(const struct _GUID *)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18007d850`
- `0x1801caab4`
- `0x1801cad3c`

## callees

- `0x18000aa0c`
- `0x18002ae00`
- `0x18007daa4`
- `0x180107330`
- `0x1801c81ac`
- `0x1801c82e4`
- `0x1801ca730`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18007dc29`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18007dc29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007dcf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007dcf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dac4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dac4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007dad4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007dad4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007dab5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007dc87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007dab5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007dc87`

## pseudocode

```c
void **__fastcall WDiagFindOrAddInterfaceRecoveryData(const struct _GUID *a1)
{
  DWORD CurrentThreadId; // ebx
  PVOID *v3; // rcx
  void **v4; // rbx
  char *v5; // rax
  void **v6; // rax
  void ***v7; // rax
  char v8; // al
  int v10; // [rsp+28h] [rbp-70h]

  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection(&stru_1802A35F0);
  WaitForSingleObject(qword_1802A3640, 0xFFFFFFFF);
  if ( (dword_1802A3648 & 4) != 0 )
  {
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 225)
      || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) == 0 )
    {
      goto LABEL_7;
    }
    WPP_SF_qqdsddsd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (char)&qword_1802A35E8,
      dword_1802A3650[0],
      qword_1802A3658,
      dword_1802A3654[0],
      CurrentThreadId,
      (__int64)"WDiagFindOrAddInterfaceRecoveryData",
      189);
  }
  v3 = (PVOID *)WPP_GLOBAL_Control;
LABEL_7:
  dword_1802A3648 |= 4u;
  *(_DWORD *)dword_1802A3654 = 189;
  *(_DWORD *)dword_1802A3650 = CurrentThreadId;
  v4 = &qword_1802A3690;
  qword_1802A3658 = (__int64)"WDiagFindOrAddInterfaceRecoveryData";
  while ( 1 )
  {
    v4 = (void **)*v4;
    if ( v4 == &qword_1802A3690 )
      break;
    v5 = (char *)v4[7] - *(_QWORD *)&a1->Data1;
    if ( !v5 )
      v5 = (char *)v4[8] - *(_QWORD *)a1->Data4;
    if ( !v5 )
    {
      if ( v4 )
        goto LABEL_22;
      break;
    }
  }
  v6 = (void **)WDiagAllocMem(0xF0u);
  v4 = v6;
  if ( v6 )
  {
    memset_0(v6, 0, 0xF0u);
    *(struct _GUID *)(v4 + 7) = *a1;
    InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v4 + 2), 0xFA0u);
    InitializeRecoveryActionParams((struct _WDIAG_RECOVERY_DATA *)v4);
    v7 = (void ***)qword_1802A3698;
    if ( *(void ***)qword_1802A3698 != &qword_1802A3690 )
      __fastfail(3u);
    *v4 = &qword_1802A3690;
    v4[1] = v7;
    *v7 = v4;
    qword_1802A3698 = (__int64)v4;
    goto LABEL_21;
  }
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225)
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 15, WPP_6ba1dcf276c838076ffc51ecd6e1ba00_Traceguids, 240);
LABEL_21:
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_22:
  if ( (dword_1802A3648 & 4) == 0
    && v3 != &WPP_GLOBAL_Control
    && *((_BYTE *)v3 + 225)
    && (*((_BYTE *)v3 + 228) & 0x40) != 0 )
  {
    v8 = GetCurrentThreadId();
    WPP_SF_qqDsdDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (char)&qword_1802A35E8,
      v10,
      qword_1802A3668,
      dword_1802A3660[0],
      v8,
      (__int64)"WDiagFindOrAddInterfaceRecoveryData",
      227);
  }
  dword_1802A3648 &= ~4u;
  *(_DWORD *)dword_1802A3660 = 227;
  qword_1802A3668 = (__int64)"WDiagFindOrAddInterfaceRecoveryData";
  *(_DWORD *)dword_1802A3650 = 0;
  LeaveCriticalSection(&stru_1802A35F0);
  return v4;
}

```

## disassembly

```asm
0x18007daa4  push    rbx
0x18007daa6  push    rsi
0x18007daa7  push    rdi
0x18007daa8  push    r12
0x18007daaa  push    r13
0x18007daac  push    r14
0x18007daae  sub     rsp, 68h
0x18007dab2  mov     rdi, rcx
0x18007dab5  call    cs:__imp_GetCurrentThreadId
0x18007dabb  lea     rcx, stru_1802A35F0; lpCriticalSection
0x18007dac2  mov     ebx, eax
0x18007dac4  call    cs:__imp_EnterCriticalSection
0x18007daca  mov     rcx, cs:qword_1802A3640; hHandle
0x18007dad1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007dad4  call    cs:__imp_WaitForSingleObject
0x18007dada  test    byte ptr cs:dword_1802A3648, 4
0x18007dae1  lea     r14, aWdiagfindoradd; "WDiagFindOrAddInterfaceRecoveryData"
0x18007dae8  mov     esi, 0BDh
0x18007daed  lea     r13, qword_1802A35E8
0x18007daf4  lea     r12, WPP_GLOBAL_Control
0x18007dafb  jz      short loc_18007DB60
0x18007dafd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007db04  cmp     rcx, r12
0x18007db07  jz      short loc_18007DB67
0x18007db09  cmp     byte ptr [rcx+0E1h], 1
0x18007db10  jb      short loc_18007DB67
0x18007db12  test    byte ptr [rcx+0E4h], 40h
0x18007db19  jz      short loc_18007DB67
0x18007db1b  mov     eax, cs:dword_1802A3654
0x18007db21  lea     r9, ?g_WDiag@@3U_WDIAG_GLOBAL_CONTEXT@@A; _WDIAG_GLOBAL_CONTEXT g_WDiag
0x18007db28  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18007db2f  mov     dword ptr [rsp+98h+var_48], esi; char
0x18007db33  mov     [rsp+98h+var_50], r14; __int64
0x18007db38  mov     dword ptr [rsp+98h+var_58], ebx; char
0x18007db3c  mov     dword ptr [rsp+98h+var_60], eax; char
0x18007db40  mov     rax, cs:qword_1802A3658
0x18007db47  mov     [rsp+98h+var_68], rax; __int64
0x18007db4c  mov     eax, cs:dword_1802A3650
0x18007db52  mov     dword ptr [rsp+98h+var_70], eax; int
0x18007db56  mov     qword ptr [rsp+98h+var_78], r13; char
0x18007db5b  call    WPP_SF_qqdsddsd
0x18007db60  mov     rcx, cs:WPP_GLOBAL_Control
0x18007db67  or      cs:dword_1802A3648, 4
0x18007db6e  mov     cs:dword_1802A3654, esi
0x18007db74  lea     rsi, qword_1802A3690
0x18007db7b  mov     cs:dword_1802A3650, ebx
0x18007db81  mov     rbx, rsi
0x18007db84  mov     cs:qword_1802A3658, r14
0x18007db8b  mov     rbx, [rbx]
0x18007db8e  cmp     rbx, rsi
0x18007db91  jz      short loc_18007DBB2
0x18007db93  mov     rax, [rbx+38h]
0x18007db97  sub     rax, [rdi]
0x18007db9a  jnz     short loc_18007DBA4
0x18007db9c  mov     rax, [rbx+40h]
0x18007dba0  sub     rax, [rdi+8]
0x18007dba4  test    rax, rax
0x18007dba7  jnz     short loc_18007DB8B
0x18007dba9  test    rbx, rbx
0x18007dbac  jnz     loc_18007DC62
0x18007dbb2  mov     ecx, 0F0h; dwBytes
0x18007dbb7  call    ?WDiagAllocMem@@YAPEAXK@Z; WDiagAllocMem(ulong)
0x18007dbbc  mov     rbx, rax
0x18007dbbf  test    rax, rax
0x18007dbc2  jnz     short loc_18007DC08
0x18007dbc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dbcb  cmp     rcx, r12
0x18007dbce  jz      loc_18007DC62
0x18007dbd4  cmp     byte ptr [rcx+0E1h], 1
0x18007dbdb  jb      loc_18007DC62
0x18007dbe1  test    byte ptr [rcx+0E4h], 8
0x18007dbe8  jz      short loc_18007DC62
0x18007dbea  mov     rcx, [rcx+0D8h]
0x18007dbf1  lea     edx, [rax+0Fh]
0x18007dbf4  mov     r9d, 0F0h
0x18007dbfa  lea     r8, WPP_6ba1dcf276c838076ffc51ecd6e1ba00_Traceguids
0x18007dc01  call    WPP_SF_d
0x18007dc06  jmp     short loc_18007DC5B
0x18007dc08  xor     edx, edx; Val
0x18007dc0a  mov     r8d, 0F0h; Size
0x18007dc10  mov     rcx, rbx; void *
0x18007dc13  call    memset_0
0x18007dc18  movups  xmm0, xmmword ptr [rdi]
0x18007dc1b  lea     rcx, [rbx+10h]; lpCriticalSection
0x18007dc1f  mov     edx, 0FA0h; dwSpinCount
0x18007dc24  movdqu  xmmword ptr [rbx+38h], xmm0
0x18007dc29  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18007dc2f  mov     rcx, rbx; struct _WDIAG_RECOVERY_DATA *
0x18007dc32  call    ?InitializeRecoveryActionParams@@YAXPEAU_WDIAG_RECOVERY_DATA@@@Z; InitializeRecoveryActionParams(_WDIAG_RECOVERY_DATA *)
0x18007dc37  mov     rax, cs:qword_1802A3698
0x18007dc3e  cmp     [rax], rsi
0x18007dc41  jz      short loc_18007DC4A
0x18007dc43  mov     ecx, 3
0x18007dc48  int     29h; Win8: RtlFailFast(ecx)
0x18007dc4a  mov     [rbx], rsi
0x18007dc4d  mov     [rbx+8], rax
0x18007dc51  mov     [rax], rbx
0x18007dc54  mov     cs:qword_1802A3698, rbx
0x18007dc5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dc62  test    byte ptr cs:dword_1802A3648, 4
0x18007dc69  mov     edi, 0E3h
0x18007dc6e  jnz     short loc_18007DCCF
0x18007dc70  cmp     rcx, r12
0x18007dc73  jz      short loc_18007DCCF
0x18007dc75  cmp     byte ptr [rcx+0E1h], 1
0x18007dc7c  jb      short loc_18007DCCF
0x18007dc7e  test    byte ptr [rcx+0E4h], 40h
0x18007dc85  jz      short loc_18007DCCF
0x18007dc87  call    cs:__imp_GetCurrentThreadId
0x18007dc8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007dc94  lea     r9, ?g_WDiag@@3U_WDIAG_GLOBAL_CONTEXT@@A; _WDIAG_GLOBAL_CONTEXT g_WDiag
0x18007dc9b  mov     dword ptr [rsp+98h+var_48], edi; char
0x18007dc9f  mov     [rsp+98h+var_50], r14; __int64
0x18007dca4  mov     dword ptr [rsp+98h+var_58], eax; char
0x18007dca8  mov     eax, cs:dword_1802A3660
0x18007dcae  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18007dcb5  mov     dword ptr [rsp+98h+var_60], eax; char
0x18007dcb9  mov     rax, cs:qword_1802A3668
0x18007dcc0  mov     [rsp+98h+var_68], rax; __int64
0x18007dcc5  mov     qword ptr [rsp+98h+var_78], r13; char
0x18007dcca  call    WPP_SF_qqDsdDsd
0x18007dccf  and     cs:dword_1802A3648, 0FFFFFFFBh
0x18007dcd6  lea     rcx, stru_1802A35F0; lpCriticalSection
0x18007dcdd  mov     cs:dword_1802A3660, edi
0x18007dce3  mov     cs:qword_1802A3668, r14
0x18007dcea  mov     cs:dword_1802A3650, 0
0x18007dcf4  call    cs:__imp_LeaveCriticalSection
0x18007dcfa  mov     rax, rbx
0x18007dcfd  add     rsp, 68h
0x18007dd01  pop     r14
0x18007dd03  pop     r13
0x18007dd05  pop     r12
0x18007dd07  pop     rdi
0x18007dd08  pop     rsi
0x18007dd09  pop     rbx
0x18007dd0a  retn
```

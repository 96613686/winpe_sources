# UbpmpTriggerConsumerSaveRegistrationStats

- ea: `0x180014b30`
- end: `0x180014da9`
- name: `UbpmpTriggerConsumerSaveRegistrationStats`
- size: `633`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d5c0`

## callees

- `0x180014b30`
- `0x180015e10`
- `0x180034ec4`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180014b79`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180014b79`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180014c72`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180014c72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014b7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014b7f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180014be2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180014be2`

## pseudocode

```c
__int64 __fastcall UbpmpTriggerConsumerSaveRegistrationStats(
        __int64 a1,
        DWORD *a2,
        FILETIME *a3,
        __int64 *a4,
        FILETIME *a5)
{
  unsigned int v9; // eax
  unsigned int v10; // ebx
  FILETIME v11; // rcx
  char v12; // bl
  DWORD dwLowDateTime; // r8d
  FILETIME v14; // rdx
  __int64 v15; // rax
  _QWORD *v17; // rcx
  int v18; // edx
  __int64 v19; // rax
  FILETIME FileTime1[5]; // [rsp+30h] [rbp-38h] BYREF

  memset(FileTime1, 0, 36);
  RtlAcquireSRWLockExclusive(a1 + 208);
  *(_DWORD *)(a1 + 216) = GetCurrentThreadId();
  v9 = UbpmStatsOperation(a1, 0, FileTime1);
  v10 = v9;
  if ( !v9 )
    goto LABEL_2;
  if ( v9 == 2 )
  {
    dwLowDateTime = *a2;
    FileTime1[0].dwLowDateTime = 3;
    if ( dwLowDateTime || a3->dwLowDateTime || a3->dwHighDateTime )
    {
      v11 = *a3;
      v12 = 1;
      *(FILETIME *)&FileTime1[1].dwHighDateTime = *a3;
      FileTime1[3].dwLowDateTime = dwLowDateTime;
      goto LABEL_11;
    }
LABEL_2:
    v11 = *(FILETIME *)&FileTime1[1].dwHighDateTime;
    if ( (a3->dwLowDateTime || a3->dwHighDateTime) && !FileTime1[1].dwHighDateTime && !FileTime1[2].dwLowDateTime )
      goto LABEL_10;
    v12 = 0;
    if ( (a3->dwLowDateTime || a3->dwHighDateTime) && (FileTime1[1].dwHighDateTime || FileTime1[2].dwLowDateTime) )
    {
      if ( CompareFileTime((const FILETIME *)&FileTime1[1].dwHighDateTime, a3) < 0 )
      {
LABEL_10:
        v11 = *a3;
        v12 = 1;
        dwLowDateTime = *a2;
        *(FILETIME *)&FileTime1[1].dwHighDateTime = *a3;
        FileTime1[3].dwLowDateTime = dwLowDateTime;
        goto LABEL_11;
      }
      v11 = *(FILETIME *)&FileTime1[1].dwHighDateTime;
    }
    dwLowDateTime = FileTime1[3].dwLowDateTime;
LABEL_11:
    if ( (a5->dwLowDateTime || a5->dwHighDateTime) && *a5 != *(_QWORD *)&FileTime1[3].dwHighDateTime )
    {
      v14 = *a5;
      v12 = 1;
      *(FILETIME *)&FileTime1[3].dwHighDateTime = *a5;
    }
    else
    {
      v14 = *(FILETIME *)&FileTime1[3].dwHighDateTime;
    }
    if ( (*(_DWORD *)a4 || *((_DWORD *)a4 + 1))
      && (*(_DWORD *)a4 != FileTime1[0].dwHighDateTime || *((_DWORD *)a4 + 1) != FileTime1[1].dwLowDateTime) )
    {
      v19 = *a4;
      *a2 = dwLowDateTime;
      *a3 = v11;
      *a5 = v14;
      *a4 = v19;
      *(_QWORD *)&FileTime1[0].dwHighDateTime = v19;
    }
    else
    {
      v15 = *(_QWORD *)&FileTime1[0].dwHighDateTime;
      *a2 = dwLowDateTime;
      *a3 = v11;
      *a5 = v14;
      *a4 = v15;
      if ( !v12 )
      {
        v10 = 0;
        goto LABEL_20;
      }
    }
    v10 = UbpmStatsOperation(a1, 1, FileTime1);
    if ( v10 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v18 = 157;
        goto LABEL_43;
      }
    }
    goto LABEL_20;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v18 = 156;
LABEL_43:
    WPP_SF_SL(
      v17[2],
      v18,
      (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
      *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
      *a2);
  }
LABEL_20:
  *(_DWORD *)(a1 + 216) = 0;
  RtlReleaseSRWLockExclusive(a1 + 208);
  return v10;
}

```

## disassembly

```asm
0x180014b30  push    rbp
0x180014b32  push    rbx
0x180014b33  push    rsi
0x180014b34  push    rdi
0x180014b35  push    r12
0x180014b37  push    r13
0x180014b39  push    r14
0x180014b3b  push    r15
0x180014b3d  mov     rbp, rsp
0x180014b40  sub     rsp, 68h
0x180014b44  mov     rax, cs:__security_cookie
0x180014b4b  xor     rax, rsp
0x180014b4e  mov     [rbp+var_10], rax
0x180014b52  mov     r14, [rbp+arg_20]
0x180014b56  xorps   xmm0, xmm0
0x180014b59  mov     r13, rcx
0x180014b5c  xor     eax, eax
0x180014b5e  add     rcx, 0D0h
0x180014b65  mov     dword ptr [rbp+var_28+10h], eax
0x180014b68  movups  xmmword ptr [rbp+FileTime1.dwLowDateTime], xmm0
0x180014b6c  mov     r15, r9
0x180014b6f  mov     rsi, r8
0x180014b72  movups  xmmword ptr [rbp+var_28], xmm0
0x180014b76  mov     r12, rdx
0x180014b79  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180014b7f  call    cs:__imp_GetCurrentThreadId
0x180014b85  lea     r8, [rbp+FileTime1]
0x180014b89  xor     edx, edx
0x180014b8b  mov     rcx, r13
0x180014b8e  mov     [r13+0D8h], eax
0x180014b95  call    UbpmStatsOperation
0x180014b9a  mov     ebx, eax
0x180014b9c  test    eax, eax
0x180014b9e  jnz     loc_180014CA0
0x180014ba4  mov     edx, [rsi]
0x180014ba6  mov     rcx, qword ptr [rbp+FileTime1.dwHighDateTime+8]
0x180014baa  test    edx, edx
0x180014bac  jz      short loc_180014BC1
0x180014bae  cmp     [rbp+FileTime1.dwHighDateTime+8], 0
0x180014bb2  jnz     short loc_180014BC7
0x180014bb4  mov     rax, rcx
0x180014bb7  shr     rax, 20h
0x180014bbb  test    eax, eax
0x180014bbd  jnz     short loc_180014BC7
0x180014bbf  jmp     short loc_180014BF0
0x180014bc1  cmp     dword ptr [rsi+4], 0
0x180014bc5  jnz     short loc_180014BAE
0x180014bc7  xor     bl, bl
0x180014bc9  test    edx, edx
0x180014bcb  jz      loc_180014CF9
0x180014bd1  cmp     [rbp+FileTime1.dwHighDateTime+8], 0
0x180014bd5  jz      loc_180014D04
0x180014bdb  mov     rdx, rsi; lpFileTime2
0x180014bde  lea     rcx, [rbp+FileTime1.dwHighDateTime+8]; lpFileTime1
0x180014be2  call    cs:__imp_CompareFileTime
0x180014be8  test    eax, eax
0x180014bea  jns     loc_180014D14
0x180014bf0  mov     rcx, [rsi]
0x180014bf3  mov     bl, 1
0x180014bf5  mov     r8d, [r12]
0x180014bf9  mov     qword ptr [rbp+FileTime1.dwHighDateTime+8], rcx
0x180014bfd  mov     dword ptr [rbp+var_28+8], r8d
0x180014c01  mov     eax, [r14]
0x180014c04  test    eax, eax
0x180014c06  jnz     short loc_180014C0E
0x180014c08  cmp     [r14+4], eax
0x180014c0c  jz      short loc_180014C24
0x180014c0e  cmp     eax, dword ptr [rbp+var_28+0Ch]
0x180014c11  jnz     loc_180014D21
0x180014c17  mov     eax, dword ptr [rbp+var_28+10h]
0x180014c1a  cmp     [r14+4], eax
0x180014c1e  jnz     loc_180014D21
0x180014c24  mov     rdx, qword ptr [rbp+var_28+0Ch]
0x180014c28  mov     eax, [r15]
0x180014c2b  test    eax, eax
0x180014c2d  jz      short loc_180014C97
0x180014c2f  cmp     eax, [rbp+FileTime1.dwHighDateTime]
0x180014c32  jnz     loc_180014D2F
0x180014c38  mov     eax, [rbp+FileTime1.dwLowDateTime+8]
0x180014c3b  cmp     [r15+4], eax
0x180014c3f  jnz     loc_180014D2F
0x180014c45  mov     rax, qword ptr [rbp+FileTime1.dwHighDateTime]
0x180014c49  mov     [r12], r8d
0x180014c4d  mov     [rsi], rcx
0x180014c50  mov     [r14], rdx
0x180014c53  mov     [r15], rax
0x180014c56  test    bl, bl
0x180014c58  jnz     loc_180014D43
0x180014c5e  xor     ebx, ebx
0x180014c60  lea     rcx, [r13+0D0h]
0x180014c67  mov     dword ptr [r13+0D8h], 0
0x180014c72  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180014c78  mov     eax, ebx
0x180014c7a  mov     rcx, [rbp+var_10]
0x180014c7e  xor     rcx, rsp; StackCookie
0x180014c81  call    __security_check_cookie
0x180014c86  add     rsp, 68h
0x180014c8a  pop     r15
0x180014c8c  pop     r14
0x180014c8e  pop     r13
0x180014c90  pop     r12
0x180014c92  pop     rdi
0x180014c93  pop     rsi
0x180014c94  pop     rbx
0x180014c95  pop     rbp
0x180014c96  retn
0x180014c97  cmp     dword ptr [r15+4], 0
0x180014c9c  jz      short loc_180014C45
0x180014c9e  jmp     short loc_180014C2F
0x180014ca0  cmp     eax, 2
0x180014ca3  jz      short loc_180014CC8
0x180014ca5  mov     rcx, cs:WPP_GLOBAL_Control
0x180014cac  lea     rax, WPP_GLOBAL_Control
0x180014cb3  cmp     rcx, rax
0x180014cb6  jz      short loc_180014C60
0x180014cb8  test    byte ptr [rcx+1Ch], 1
0x180014cbc  jz      short loc_180014C60
0x180014cbe  mov     edx, 9Ch
0x180014cc3  jmp     loc_180014D84
0x180014cc8  mov     r8d, [r12]
0x180014ccc  mov     [rbp+FileTime1.dwLowDateTime], 3
0x180014cd3  test    r8d, r8d
0x180014cd6  jnz     short loc_180014CE7
0x180014cd8  cmp     [rsi], r8d
0x180014cdb  jnz     short loc_180014CE7
0x180014cdd  cmp     [rsi+4], r8d
0x180014ce1  jz      loc_180014BA4
0x180014ce7  mov     rcx, [rsi]
0x180014cea  mov     bl, 1
0x180014cec  mov     qword ptr [rbp+FileTime1.dwHighDateTime+8], rcx
0x180014cf0  mov     dword ptr [rbp+var_28+8], r8d
0x180014cf4  jmp     loc_180014C01
0x180014cf9  cmp     dword ptr [rsi+4], 0
0x180014cfd  jz      short loc_180014D18
0x180014cff  jmp     loc_180014BD1
0x180014d04  mov     rax, rcx
0x180014d07  shr     rax, 20h
0x180014d0b  test    eax, eax
0x180014d0d  jz      short loc_180014D18
0x180014d0f  jmp     loc_180014BDB
0x180014d14  mov     rcx, qword ptr [rbp+FileTime1.dwHighDateTime+8]
0x180014d18  mov     r8d, dword ptr [rbp+var_28+8]
0x180014d1c  jmp     loc_180014C01
0x180014d21  mov     rdx, [r14]
0x180014d24  mov     bl, 1
0x180014d26  mov     qword ptr [rbp+var_28+0Ch], rdx
0x180014d2a  jmp     loc_180014C28
0x180014d2f  mov     rax, [r15]
0x180014d32  mov     [r12], r8d
0x180014d36  mov     [rsi], rcx
0x180014d39  mov     [r14], rdx
0x180014d3c  mov     [r15], rax
0x180014d3f  mov     qword ptr [rbp+FileTime1.dwHighDateTime], rax
0x180014d43  lea     r8, [rbp+FileTime1]
0x180014d47  mov     edx, 1
0x180014d4c  mov     rcx, r13
0x180014d4f  call    UbpmStatsOperation
0x180014d54  mov     ebx, eax
0x180014d56  test    eax, eax
0x180014d58  jz      loc_180014C60
0x180014d5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d65  lea     rax, WPP_GLOBAL_Control
0x180014d6c  cmp     rcx, rax
0x180014d6f  jz      loc_180014C60
0x180014d75  test    byte ptr [rcx+1Ch], 1
0x180014d79  jz      loc_180014C60
0x180014d7f  mov     edx, 9Dh
0x180014d84  mov     r9, [r13+18h]
0x180014d88  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180014d8f  mov     eax, [r12]
0x180014d93  mov     rcx, [rcx+10h]
0x180014d97  mov     [rsp+68h+var_48], eax
0x180014d9b  mov     r9, [r9+8]
0x180014d9f  call    WPP_SF_SL
0x180014da4  jmp     loc_180014C60
```

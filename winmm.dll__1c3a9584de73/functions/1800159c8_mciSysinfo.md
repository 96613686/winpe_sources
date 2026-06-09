# mciSysinfo

- ea: `0x1800159c8`
- end: `0x180015d4a`
- name: `mciSysinfo`
- size: `898`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800102a8`

## callees

- `0x180003a2c`
- `0x18000c990`
- `0x1800153b8`
- `0x1800159c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015c3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015c3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015cca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015cdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015cca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015cdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015c03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015c03`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180015b28`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180015b28`

## pseudocode

```c
__int64 __fastcall mciSysinfo(unsigned int a1, __int16 a2, __int64 a3)
{
  __int64 v3; // rbp
  int v4; // r12d
  int v6; // ebx
  __int64 v9; // rax
  const unsigned __int16 *v10; // r8
  unsigned int v11; // ebx
  const unsigned __int16 *v12; // r13
  WCHAR *v13; // rsi
  int v14; // r14d
  int v15; // ebx
  int v17; // ebx
  _DWORD *v19; // rax
  __int64 v20; // rax
  DWORD CurrentThreadId; // eax
  __int64 v22; // rsi
  int v23; // ebx
  unsigned int i; // edx
  __int64 v25; // r8
  const unsigned __int16 *v26; // r8
  __int64 v27; // rax
  int v28; // eax
  int v29; // edx
  _WORD *v30; // rcx
  _DWORD *v31; // rax
  int v32; // [rsp+30h] [rbp-248h]
  WCHAR ReturnedString[256]; // [rsp+40h] [rbp-238h] BYREF

  v3 = a1;
  v4 = 0;
  v6 = a2 & 0x400;
  v32 = v6;
  if ( (a2 & 0x400) != 0 && !*(_DWORD *)(a3 + 20) )
    return 282;
  if ( !*(_QWORD *)(a3 + 8) || !*(_DWORD *)(a3 + 16) )
    return 268;
  if ( (a2 & 0x400) != 0 && (a2 & 0x100) != 0 )
    return 284;
  if ( (a2 & 0x800) != 0 )
  {
    if ( a1 == -1 )
      return 279;
    EnterCriticalSection(&mciCritSec);
    if ( (_DWORD)v3 && (unsigned int)v3 < MCI_wNextDeviceID && *((_QWORD *)MCI_lpDeviceList + v3) )
    {
      _mm_lfence();
      v9 = -1;
      v10 = *(const unsigned __int16 **)(*((_QWORD *)MCI_lpDeviceList + v3) + 8LL);
      do
        ++v9;
      while ( v10[v9] );
      if ( (unsigned int)v9 >= *(_DWORD *)(a3 + 16)
        || StringCchCopyW(*(unsigned __int16 **)(a3 + 8), *(unsigned int *)(a3 + 16), v10) < 0 )
      {
        goto LABEL_19;
      }
      v11 = 0;
    }
    else
    {
      v11 = 263;
    }
    goto LABEL_72;
  }
  if ( (a2 & 0x200) != 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    if ( (_DWORD)v3 != -1 && !*(_DWORD *)(a3 + 24) )
      return 287;
    if ( (a2 & 0x500) == 0 )
      return 273;
    v22 = CurrentThreadId;
    v23 = 0;
    EnterCriticalSection(&mciCritSec);
    for ( i = 1; i < MCI_wNextDeviceID; ++i )
    {
      v25 = *((_QWORD *)MCI_lpDeviceList + i);
      if ( v25 )
      {
        if ( (_DWORD)v3 == -1 && *(_QWORD *)(v25 + 88) == v22
          || *(_DWORD *)(v25 + 56) == *(_DWORD *)(a3 + 24) && *(_QWORD *)(v25 + 88) == v22 )
        {
          ++v23;
        }
        if ( (a2 & 0x400) != 0 && v23 == *(_DWORD *)(a3 + 20) )
        {
          v26 = *(const unsigned __int16 **)v25;
          v27 = -1;
          do
            ++v27;
          while ( v26[v27] );
          if ( (unsigned int)v27 < *(_DWORD *)(a3 + 16) )
          {
            v28 = StringCchCopyW(*(unsigned __int16 **)(a3 + 8), *(unsigned int *)(a3 + 16), v26);
            v29 = 0;
            if ( v28 < 0 )
              v29 = 268;
            v11 = v29;
            goto LABEL_72;
          }
LABEL_19:
          v11 = 268;
LABEL_72:
          LeaveCriticalSection(&mciCritSec);
          return v11;
        }
      }
    }
    LeaveCriticalSection(&mciCritSec);
    if ( !v32 )
    {
      if ( (a2 & 0x100) == 0 )
        return 268;
      v31 = *(_DWORD **)(a3 + 8);
      if ( !v31 || *(_DWORD *)(a3 + 16) < 4u )
        return 268;
      *v31 = v23;
      return 0x80000;
    }
    v30 = *(_WORD **)(a3 + 8);
    if ( v30 )
      *v30 = 0;
    return 282;
  }
  if ( a1 != -1 && !*(_DWORD *)(a3 + 24) )
    return 287;
  if ( (a2 & 0x500) == 0 )
    return 273;
  v12 = 0;
  v13 = ReturnedString;
  GetPrivateProfileStringW(L"MCI32", 0, &wszNull, ReturnedString, 0xFFu, L"system.ini");
  v14 = a2 & 0x100;
  do
  {
    while ( v14 )
    {
      if ( !*v13 )
      {
        v19 = *(_DWORD **)(a3 + 8);
        if ( v19 && *(_DWORD *)(a3 + 16) >= 4u )
        {
          *v19 = v4;
          return 0x80000;
        }
        return 268;
      }
      if ( (_DWORD)v3 == -1 || (v15 = *(_DWORD *)(a3 + 24), (unsigned int)mciLookUpType(v13) == v15) )
        ++v4;
      while ( *v13++ )
        ;
LABEL_40:
      v6 = v32;
    }
  }
  while ( !v6 );
  if ( v4 != *(_DWORD *)(a3 + 20) )
  {
    if ( !*v13 )
      return 282;
    v12 = v13;
    if ( (_DWORD)v3 == -1 || (v17 = *(_DWORD *)(a3 + 24), (unsigned int)mciLookUpType(v13) == v17) )
      ++v4;
    while ( *v13++ )
      ;
    goto LABEL_40;
  }
  v20 = -1;
  do
    ++v20;
  while ( v12[v20] );
  if ( (unsigned int)v20 < *(_DWORD *)(a3 + 16)
    && StringCchCopyW(*(unsigned __int16 **)(a3 + 8), *(unsigned int *)(a3 + 16), v12) >= 0 )
  {
    return 0;
  }
  return 268;
}

```

## disassembly

```asm
0x1800159c8  mov     [rsp+arg_8], rbx
0x1800159cd  mov     [rsp+arg_18], rbp
0x1800159d2  push    rsi
0x1800159d3  push    rdi
0x1800159d4  push    r12
0x1800159d6  push    r13
0x1800159d8  push    r14
0x1800159da  sub     rsp, 250h
0x1800159e1  mov     rax, cs:__security_cookie
0x1800159e8  xor     rax, rsp
0x1800159eb  mov     [rsp+278h+var_38], rax
0x1800159f3  mov     ebx, edx
0x1800159f5  mov     ebp, ecx
0x1800159f7  xor     r12d, r12d
0x1800159fa  mov     rdi, r8
0x1800159fd  and     ebx, 400h
0x180015a03  mov     r14d, edx
0x180015a06  mov     [rsp+278h+var_248], ebx
0x180015a0a  jz      short loc_180015A16
0x180015a0c  cmp     [r8+14h], r12d
0x180015a10  jz      loc_180015CF5
0x180015a16  cmp     [r8+8], r12
0x180015a1a  jz      loc_180015D19
0x180015a20  cmp     [r8+10h], r12d
0x180015a24  jz      loc_180015D19
0x180015a2a  test    ebx, ebx
0x180015a2c  jz      short loc_180015A3F
0x180015a2e  bt      r14d, 8
0x180015a33  jnb     short loc_180015A3F
0x180015a35  mov     eax, 11Ch
0x180015a3a  jmp     loc_180015D1E
0x180015a3f  bt      r14d, 0Bh
0x180015a44  jnb     loc_180015AD0
0x180015a4a  cmp     ebp, 0FFFFFFFFh
0x180015a4d  jnz     short loc_180015A59
0x180015a4f  mov     eax, 117h
0x180015a54  jmp     loc_180015D1E
0x180015a59  lea     rcx, mciCritSec; lpCriticalSection
0x180015a60  call    cs:__imp_EnterCriticalSection
0x180015a66  test    ebp, ebp
0x180015a68  jz      short loc_180015AC6
0x180015a6a  cmp     ebp, cs:MCI_wNextDeviceID
0x180015a70  jnb     short loc_180015AC6
0x180015a72  mov     rax, cs:MCI_lpDeviceList
0x180015a79  cmp     [rax+rbp*8], r12
0x180015a7d  jz      short loc_180015AC6
0x180015a7f  lfence
0x180015a82  mov     rax, cs:MCI_lpDeviceList
0x180015a89  mov     rcx, [rax+rbp*8]
0x180015a8d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015a91  mov     r8, [rcx+8]; unsigned __int16 *
0x180015a95  inc     rax
0x180015a98  cmp     [r8+rax*2], r12w
0x180015a9d  jnz     short loc_180015A95
0x180015a9f  cmp     eax, [rdi+10h]
0x180015aa2  jnb     short loc_180015ABC
0x180015aa4  mov     edx, [rdi+10h]; unsigned __int64
0x180015aa7  mov     rcx, [rdi+8]; unsigned __int16 *
0x180015aab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015ab0  test    eax, eax
0x180015ab2  js      short loc_180015ABC
0x180015ab4  mov     ebx, r12d
0x180015ab7  jmp     loc_180015CC3
0x180015abc  mov     ebx, 10Ch
0x180015ac1  jmp     loc_180015CC3
0x180015ac6  mov     ebx, 107h
0x180015acb  jmp     loc_180015CC3
0x180015ad0  bt      r14d, 9
0x180015ad5  jb      loc_180015C03
0x180015adb  cmp     ebp, 0FFFFFFFFh
0x180015ade  jz      short loc_180015AEA
0x180015ae0  cmp     [r8+18h], r12d
0x180015ae4  jz      loc_180015C14
0x180015aea  test    r14d, 500h
0x180015af1  jz      loc_180015C27
0x180015af7  lea     rax, FileName; "system.ini"
0x180015afe  xor     edx, edx; lpKeyName
0x180015b00  mov     [rsp+278h+lpFileName], rax; lpFileName
0x180015b05  lea     r9, [rsp+278h+ReturnedString]; lpReturnedString
0x180015b0a  lea     r8, wszNull; lpDefault
0x180015b11  mov     [rsp+278h+nSize], 0FFh; nSize
0x180015b19  lea     rcx, AppName; "MCI32"
0x180015b20  mov     r13, r12
0x180015b23  lea     rsi, [rsp+278h+ReturnedString]
0x180015b28  call    cs:__imp_GetPrivateProfileStringW
0x180015b2e  and     r14d, 100h
0x180015b35  xor     ecx, ecx
0x180015b37  test    r14d, r14d
0x180015b3a  jz      short loc_180015B68
0x180015b3c  cmp     [rsi], cx
0x180015b3f  jz      short loc_180015BA9
0x180015b41  cmp     ebp, 0FFFFFFFFh
0x180015b44  jz      short loc_180015B55
0x180015b46  mov     ebx, [rdi+18h]
0x180015b49  mov     rcx, rsi; unsigned __int16 *
0x180015b4c  call    mciLookUpType
0x180015b51  cmp     eax, ebx
0x180015b53  jnz     short loc_180015B58
0x180015b55  inc     r12d
0x180015b58  xor     ecx, ecx
0x180015b5a  movzx   eax, word ptr [rsi]
0x180015b5d  add     rsi, 2
0x180015b61  test    ax, ax
0x180015b64  jnz     short loc_180015B5A
0x180015b66  jmp     short loc_180015BA3
0x180015b68  test    ebx, ebx
0x180015b6a  jz      short loc_180015B37
0x180015b6c  cmp     r12d, [rdi+14h]
0x180015b70  jz      short loc_180015BCD
0x180015b72  cmp     [rsi], cx
0x180015b75  jz      loc_180015CF5
0x180015b7b  mov     r13, rsi
0x180015b7e  cmp     ebp, 0FFFFFFFFh
0x180015b81  jz      short loc_180015B92
0x180015b83  mov     ebx, [rdi+18h]
0x180015b86  mov     rcx, rsi; unsigned __int16 *
0x180015b89  call    mciLookUpType
0x180015b8e  cmp     eax, ebx
0x180015b90  jnz     short loc_180015B95
0x180015b92  inc     r12d
0x180015b95  xor     ecx, ecx
0x180015b97  movzx   eax, word ptr [rsi]
0x180015b9a  add     rsi, 2
0x180015b9e  test    ax, ax
0x180015ba1  jnz     short loc_180015B97
0x180015ba3  mov     ebx, [rsp+278h+var_248]
0x180015ba7  jmp     short loc_180015B37
0x180015ba9  mov     rax, [rdi+8]
0x180015bad  test    rax, rax
0x180015bb0  jz      loc_180015D19
0x180015bb6  cmp     dword ptr [rdi+10h], 4
0x180015bba  jb      loc_180015D19
0x180015bc0  mov     [rax], r12d
0x180015bc3  mov     eax, 80000h
0x180015bc8  jmp     loc_180015D1E
0x180015bcd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015bd1  inc     rax
0x180015bd4  cmp     [r13+rax*2+0], cx
0x180015bda  jnz     short loc_180015BD1
0x180015bdc  cmp     eax, [rdi+10h]
0x180015bdf  jnb     loc_180015D19
0x180015be5  mov     edx, [rdi+10h]; unsigned __int64
0x180015be8  mov     r8, r13; unsigned __int16 *
0x180015beb  mov     rcx, [rdi+8]; unsigned __int16 *
0x180015bef  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015bf4  test    eax, eax
0x180015bf6  js      loc_180015D19
0x180015bfc  xor     eax, eax
0x180015bfe  jmp     loc_180015D1E
0x180015c03  call    cs:__imp_GetCurrentThreadId
0x180015c09  cmp     ebp, 0FFFFFFFFh
0x180015c0c  jz      short loc_180015C1E
0x180015c0e  cmp     [rdi+18h], r12d
0x180015c12  jnz     short loc_180015C1E
0x180015c14  mov     eax, 11Fh
0x180015c19  jmp     loc_180015D1E
0x180015c1e  test    r14d, 500h
0x180015c25  jnz     short loc_180015C31
0x180015c27  mov     eax, 111h
0x180015c2c  jmp     loc_180015D1E
0x180015c31  lea     rcx, mciCritSec; lpCriticalSection
0x180015c38  mov     esi, eax
0x180015c3a  mov     ebx, r12d
0x180015c3d  call    cs:__imp_EnterCriticalSection
0x180015c43  mov     r9, cs:MCI_lpDeviceList
0x180015c4a  mov     edx, 1
0x180015c4f  cmp     edx, cs:MCI_wNextDeviceID
0x180015c55  jnb     short loc_180015CD4
0x180015c57  mov     eax, edx
0x180015c59  mov     r8, [r9+rax*8]
0x180015c5d  test    r8, r8
0x180015c60  jz      short loc_180015C8A
0x180015c62  cmp     ebp, 0FFFFFFFFh
0x180015c65  jnz     short loc_180015C6D
0x180015c67  cmp     [r8+58h], rsi
0x180015c6b  jz      short loc_180015C7C
0x180015c6d  mov     eax, [rdi+18h]
0x180015c70  cmp     [r8+38h], eax
0x180015c74  jnz     short loc_180015C7E
0x180015c76  cmp     [r8+58h], rsi
0x180015c7a  jnz     short loc_180015C7E
0x180015c7c  inc     ebx
0x180015c7e  bt      r14d, 0Ah
0x180015c83  jnb     short loc_180015C8A
0x180015c85  cmp     ebx, [rdi+14h]
0x180015c88  jz      short loc_180015C8E
0x180015c8a  inc     edx
0x180015c8c  jmp     short loc_180015C4F
0x180015c8e  mov     r8, [r8]; unsigned __int16 *
0x180015c91  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015c95  inc     rax
0x180015c98  cmp     [r8+rax*2], r12w
0x180015c9d  jnz     short loc_180015C95
0x180015c9f  cmp     eax, [rdi+10h]
0x180015ca2  jnb     loc_180015ABC
0x180015ca8  mov     edx, [rdi+10h]; unsigned __int64
0x180015cab  mov     rcx, [rdi+8]; unsigned __int16 *
0x180015caf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015cb4  mov     ebx, 10Ch
0x180015cb9  test    eax, eax
0x180015cbb  mov     edx, r12d
0x180015cbe  cmovs   edx, ebx
0x180015cc1  mov     ebx, edx
0x180015cc3  lea     rcx, mciCritSec; lpCriticalSection
0x180015cca  call    cs:__imp_LeaveCriticalSection
0x180015cd0  mov     eax, ebx
0x180015cd2  jmp     short loc_180015D1E
0x180015cd4  lea     rcx, mciCritSec; lpCriticalSection
0x180015cdb  call    cs:__imp_LeaveCriticalSection
0x180015ce1  cmp     [rsp+278h+var_248], r12d
0x180015ce6  jz      short loc_180015CFC
0x180015ce8  mov     rcx, [rdi+8]
0x180015cec  test    rcx, rcx
0x180015cef  jz      short loc_180015CF5
0x180015cf1  mov     [rcx], r12w
0x180015cf5  mov     eax, 11Ah
0x180015cfa  jmp     short loc_180015D1E
0x180015cfc  bt      r14d, 8
0x180015d01  jnb     short loc_180015D19
0x180015d03  mov     rax, [rdi+8]
0x180015d07  test    rax, rax
0x180015d0a  jz      short loc_180015D19
0x180015d0c  cmp     dword ptr [rdi+10h], 4
0x180015d10  jb      short loc_180015D19
0x180015d12  mov     [rax], ebx
0x180015d14  jmp     loc_180015BC3
0x180015d19  mov     eax, 10Ch
0x180015d1e  mov     rcx, [rsp+278h+var_38]
0x180015d26  xor     rcx, rsp; StackCookie
0x180015d29  call    __security_check_cookie
0x180015d2e  lea     r11, [rsp+278h+var_28]
0x180015d36  mov     rbx, [r11+38h]
0x180015d3a  mov     rbp, [r11+48h]
0x180015d3e  mov     rsp, r11
0x180015d41  pop     r14
0x180015d43  pop     r13
0x180015d45  pop     r12
0x180015d47  pop     rdi
0x180015d48  pop     rsi
0x180015d49  retn
```

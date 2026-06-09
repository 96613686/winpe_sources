# META_SCRIPT_MAP_ENTRY::Create(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,long,long,int,long)

- ea: `0x180018a84`
- end: `0x180018d21`
- name: `?Create@META_SCRIPT_MAP_ENTRY@@QEAAJPEBG00000JJHJ@Z`
- size: `669`
- prototype: `__int64 __fastcall(META_SCRIPT_MAP_ENTRY *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, LPCWSTR lpSrc, const unsigned __int16 *, int, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000806c`
- `0x180018e28`

## callees

- `0x180018a84`
- `0x1800224c2`
- `0x180022520`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180018b63`
- `msvcrt!_wcsupr` at `0x180018b63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c42`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180018be6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180018c38`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180018be6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180018c38`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018b38`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018b4f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018ba3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018bc0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018c98`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018b38`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018b4f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018ba3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018bc0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018c98`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018c5b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018d14`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018c5b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018d14`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180018af3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180018af3`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180018c8a`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180018c8a`
- `iisutil!?AppendW@MULTISZA@@QEAAHPEBGK@Z` at `0x180018d01`
- `iisutil!?AppendW@MULTISZA@@QEAAHPEBGK@Z` at `0x180018d01`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180018c1a`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180018c1a`

## pseudocode

```c
__int64 __fastcall META_SCRIPT_MAP_ENTRY::Create(
        META_SCRIPT_MAP_ENTRY *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        LPCWSTR lpSrc,
        const unsigned __int16 *a7,
        int a8,
        int a9,
        int a10,
        int a11)
{
  signed int v15; // ebx
  signed int v16; // eax
  DWORD v17; // edx
  signed int LastError; // eax
  unsigned __int16 *v20; // rdx
  unsigned int v21; // r8d
  unsigned __int16 v22; // ax
  unsigned __int16 *v23; // rcx
  _BYTE v24[32]; // [rsp+28h] [rbp-D0h] BYREF
  unsigned __int16 *v25; // [rsp+48h] [rbp-B0h]
  unsigned __int16 v26[32]; // [rsp+60h] [rbp-98h] BYREF

  memset_0(v26, 0, sizeof(v26));
  STRU::STRU((STRU *)v24, v26, 0x20u);
  *((_DWORD *)this + 93) = a10;
  *((_DWORD *)this + 94) = a11;
  *((_DWORD *)this + 90) = a8;
  *((_DWORD *)this + 91) = a9;
  v15 = STRU::Copy((META_SCRIPT_MAP_ENTRY *)((char *)this + 24), a2);
  if ( v15 < 0 )
    goto LABEL_21;
  v15 = STRU::Copy((META_SCRIPT_MAP_ENTRY *)((char *)this + 80), a3);
  if ( v15 < 0 )
    goto LABEL_21;
  _wcsupr(*((wchar_t **)this + 14));
  if ( *a3 == 42 && !a3[1] && *a4 == 42 && !a4[1] && a8 == 3 && !a9 )
    *((_DWORD *)this + 92) = 1;
  v16 = STRU::Copy((META_SCRIPT_MAP_ENTRY *)((char *)this + 304), a7);
  if ( v16 < 0 )
    goto LABEL_20;
  v16 = STRU::Copy((META_SCRIPT_MAP_ENTRY *)((char *)this + 192), a5);
  if ( v16 < 0 )
    goto LABEL_20;
  v17 = ExpandEnvironmentStringsW(lpSrc, *((LPWSTR *)this + 35), *((_DWORD *)this + 72) >> 1);
  if ( !v17 )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_21;
  }
  if ( v17 > *((_DWORD *)this + 72) >> 1 )
  {
    v16 = STRU::Resize((META_SCRIPT_MAP_ENTRY *)((char *)this + 248), 2 * v17);
    if ( v16 < 0 )
    {
LABEL_20:
      v15 = v16;
LABEL_21:
      STRU::~STRU((STRU *)v24);
      return (unsigned int)v15;
    }
    if ( !ExpandEnvironmentStringsW(lpSrc, *((LPWSTR *)this + 35), *((_DWORD *)this + 72) >> 1) )
    {
LABEL_18:
      v16 = GetLastError();
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      goto LABEL_20;
    }
  }
  STRU::SyncWithBuffer((META_SCRIPT_MAP_ENTRY *)((char *)this + 248));
  v16 = STRU::Copy((STRU *)v24, a4);
  if ( v16 < 0 )
    goto LABEL_20;
  v20 = v25;
  v21 = 1;
  v22 = *v25;
  if ( *v25 )
  {
    v23 = v25;
    do
    {
      if ( v22 == 44 || v22 == 32 )
      {
        while ( *v23 == 44 || *v23 == 32 )
          ++v23;
        v22 = 0;
      }
      else
      {
        ++v23;
      }
      *v20 = v22;
      ++v21;
      v22 = *v23;
      ++v20;
    }
    while ( *v23 );
    v20 = v25;
  }
  if ( !MULTISZA::AppendW((META_SCRIPT_MAP_ENTRY *)((char *)this + 136), v20, v21) )
    goto LABEL_18;
  STRU::~STRU((STRU *)v24);
  return 0;
}

```

## disassembly

```asm
0x180018a84  push    rbx
0x180018a86  push    rbp
0x180018a87  push    rsi
0x180018a88  push    rdi
0x180018a89  push    r12
0x180018a8b  push    r13
0x180018a8d  push    r14
0x180018a8f  push    r15
0x180018a91  sub     rsp, 0B8h
0x180018a98  mov     rax, cs:__security_cookie
0x180018a9f  xor     rax, rsp
0x180018aa2  mov     [rsp+0F8h+var_58], rax
0x180018aaa  mov     rax, [rsp+0F8h+arg_20]
0x180018ab2  mov     rbx, rdx
0x180018ab5  mov     r14, [rsp+0F8h+lpSrc]
0x180018abd  xor     edx, edx; Val
0x180018abf  mov     r13, [rsp+0F8h+arg_30]
0x180018ac7  mov     rsi, r8
0x180018aca  mov     rdi, rcx
0x180018acd  mov     [rsp+0F8h+var_D8], rax
0x180018ad2  lea     rcx, [rsp+0F8h+var_98]; void *
0x180018ad7  mov     rbp, r9
0x180018ada  lea     r8d, [rdx+40h]; Size
0x180018ade  call    memset_0
0x180018ae3  mov     r8d, 20h ; ' '
0x180018ae9  lea     rdx, [rsp+0F8h+var_98]
0x180018aee  lea     rcx, [rsp+0F8h+var_D0]
0x180018af3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180018af9  mov     eax, [rsp+0F8h+arg_48]
0x180018b00  lea     rcx, [rdi+18h]
0x180018b04  mov     r15d, [rsp+0F8h+arg_38]
0x180018b0c  mov     rdx, rbx
0x180018b0f  mov     r12d, [rsp+0F8h+arg_40]
0x180018b17  mov     [rdi+174h], eax
0x180018b1d  mov     eax, [rsp+0F8h+arg_50]
0x180018b24  mov     [rdi+178h], eax
0x180018b2a  mov     [rdi+168h], r15d
0x180018b31  mov     [rdi+16Ch], r12d
0x180018b38  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180018b3e  mov     ebx, eax
0x180018b40  test    eax, eax
0x180018b42  js      loc_180018C56
0x180018b48  lea     rcx, [rdi+50h]
0x180018b4c  mov     rdx, rsi
0x180018b4f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180018b55  mov     ebx, eax
0x180018b57  test    eax, eax
0x180018b59  js      loc_180018C56
0x180018b5f  mov     rcx, [rdi+70h]; String
0x180018b63  call    cs:__imp__wcsupr
0x180018b69  cmp     word ptr [rsi], 2Ah ; '*'
0x180018b6d  jnz     short loc_180018B99
0x180018b6f  xor     eax, eax
0x180018b71  cmp     [rsi+2], ax
0x180018b75  jnz     short loc_180018B99
0x180018b77  cmp     word ptr [rbp+0], 2Ah ; '*'
0x180018b7c  jnz     short loc_180018B99
0x180018b7e  cmp     [rbp+2], ax
0x180018b82  jnz     short loc_180018B99
0x180018b84  cmp     r15d, 3
0x180018b88  jnz     short loc_180018B99
0x180018b8a  test    r12d, r12d
0x180018b8d  jnz     short loc_180018B99
0x180018b8f  mov     dword ptr [rdi+170h], 1
0x180018b99  lea     rcx, [rdi+130h]
0x180018ba0  mov     rdx, r13
0x180018ba3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180018ba9  xor     r12d, r12d
0x180018bac  test    eax, eax
0x180018bae  js      loc_180018C54
0x180018bb4  mov     rdx, [rsp+0F8h+var_D8]
0x180018bb9  lea     rcx, [rdi+0C0h]
0x180018bc0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180018bc6  test    eax, eax
0x180018bc8  js      loc_180018C54
0x180018bce  mov     rdx, [rdi+118h]; lpDst
0x180018bd5  lea     rbx, [rdi+0F8h]
0x180018bdc  mov     r8d, [rbx+28h]
0x180018be0  mov     rcx, r14; lpSrc
0x180018be3  shr     r8d, 1; nSize
0x180018be6  call    cs:__imp_ExpandEnvironmentStringsW
0x180018bec  mov     edx, eax
0x180018bee  test    eax, eax
0x180018bf0  jnz     short loc_180018C09
0x180018bf2  call    cs:__imp_GetLastError
0x180018bf8  mov     ebx, eax
0x180018bfa  test    eax, eax
0x180018bfc  jle     short loc_180018C56
0x180018bfe  movzx   ebx, ax
0x180018c01  or      ebx, 80070000h
0x180018c07  jmp     short loc_180018C56
0x180018c09  mov     eax, [rdi+120h]
0x180018c0f  shr     eax, 1
0x180018c11  cmp     edx, eax
0x180018c13  jbe     short loc_180018C87
0x180018c15  add     edx, edx
0x180018c17  mov     rcx, rbx
0x180018c1a  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180018c20  test    eax, eax
0x180018c22  js      short loc_180018C54
0x180018c24  mov     r8d, [rdi+120h]
0x180018c2b  mov     rcx, r14; lpSrc
0x180018c2e  mov     rdx, [rdi+118h]; lpDst
0x180018c35  shr     r8d, 1; nSize
0x180018c38  call    cs:__imp_ExpandEnvironmentStringsW
0x180018c3e  test    eax, eax
0x180018c40  jnz     short loc_180018C87
0x180018c42  call    cs:__imp_GetLastError
0x180018c48  test    eax, eax
0x180018c4a  jle     short loc_180018C54
0x180018c4c  movzx   eax, ax
0x180018c4f  or      eax, 80070000h
0x180018c54  mov     ebx, eax
0x180018c56  lea     rcx, [rsp+0F8h+var_D0]
0x180018c5b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180018c61  mov     eax, ebx
0x180018c63  mov     rcx, [rsp+0F8h+var_58]
0x180018c6b  xor     rcx, rsp; StackCookie
0x180018c6e  call    __security_check_cookie
0x180018c73  add     rsp, 0B8h
0x180018c7a  pop     r15
0x180018c7c  pop     r14
0x180018c7e  pop     r13
0x180018c80  pop     r12
0x180018c82  pop     rdi
0x180018c83  pop     rsi
0x180018c84  pop     rbp
0x180018c85  pop     rbx
0x180018c86  retn
0x180018c87  mov     rcx, rbx
0x180018c8a  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180018c90  mov     rdx, rbp
0x180018c93  lea     rcx, [rsp+0F8h+var_D0]
0x180018c98  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180018c9e  test    eax, eax
0x180018ca0  js      short loc_180018C54
0x180018ca2  mov     rdx, [rsp+0F8h+var_B0]
0x180018ca7  mov     r8d, 1
0x180018cad  movzx   eax, word ptr [rdx]
0x180018cb0  test    ax, ax
0x180018cb3  jz      short loc_180018CFA
0x180018cb5  mov     rcx, rdx
0x180018cb8  lea     r9d, [r8+1Fh]
0x180018cbc  cmp     ax, 2Ch ; ','
0x180018cc0  jz      short loc_180018CCE
0x180018cc2  cmp     ax, r9w
0x180018cc6  jz      short loc_180018CCE
0x180018cc8  add     rcx, 2
0x180018ccc  jmp     short loc_180018CE3
0x180018cce  cmp     word ptr [rcx], 2Ch ; ','
0x180018cd2  jz      short loc_180018CDA
0x180018cd4  cmp     [rcx], r9w
0x180018cd8  jnz     short loc_180018CE0
0x180018cda  add     rcx, 2
0x180018cde  jmp     short loc_180018CCE
0x180018ce0  mov     eax, r12d
0x180018ce3  mov     [rdx], ax
0x180018ce6  inc     r8d
0x180018ce9  movzx   eax, word ptr [rcx]
0x180018cec  add     rdx, 2
0x180018cf0  test    ax, ax
0x180018cf3  jnz     short loc_180018CBC
0x180018cf5  mov     rdx, [rsp+0F8h+var_B0]
0x180018cfa  lea     rcx, [rdi+88h]
0x180018d01  call    cs:__imp_?AppendW@MULTISZA@@QEAAHPEBGK@Z; MULTISZA::AppendW(ushort const *,ulong)
0x180018d07  test    eax, eax
0x180018d09  jz      loc_180018C42
0x180018d0f  lea     rcx, [rsp+0F8h+var_D0]
0x180018d14  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180018d1a  xor     eax, eax
0x180018d1c  jmp     loc_180018C63
```

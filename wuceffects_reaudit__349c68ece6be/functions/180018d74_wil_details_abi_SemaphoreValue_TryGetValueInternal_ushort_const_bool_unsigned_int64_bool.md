# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180018d74`
- end: `0x180019001`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `653`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180018aac`
- `0x18001dc0c`

## callees

- `0x180018d74`
- `0x180019008`
- `0x180019034`
- `0x18001920c`
- `0x18001dc90`
- `0x18001f038`
- `0x180021060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180018e4e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180018f1d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180018e4e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180018f1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018faf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018faf`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wchar_t *v5; // rax
  __int64 v6; // r11
  __int64 v7; // r14
  __int64 v8; // rdx
  const unsigned __int16 *v9; // r8
  bool v10; // zf
  __int64 v11; // rax
  __int64 v12; // rcx
  wchar_t *v13; // rdx
  wchar_t *v14; // rcx
  wil::details *v15; // rax
  wil::details *v16; // rdi
  int ValueFromSemaphore; // eax
  unsigned int LastError; // esi
  void *v19; // rdx
  __int64 v20; // rdx
  wchar_t *v21; // rax
  __int64 v22; // r8
  wchar_t *v23; // rax
  const unsigned __int16 *v24; // rcx
  __int64 v25; // rbx
  wchar_t *v26; // rdx
  wil::details *v27; // rax
  const char *v28; // r9
  wil::details *v29; // rbx
  int v30; // eax
  void *v31; // rdx
  void *v32; // rdx
  void *v33; // rdx
  const char *v35; // r9
  size_t v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+30h] [rbp-D0h] BYREF
  int v39[3]; // [rsp+34h] [rbp-CCh] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v36);
  v5 = pszDest;
  v6 = 260;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  v7 = 2147483646;
  v8 = (260 - v6) & ((unsigned __int128)-(__int128)(unsigned __int64)v6 >> 64);
  if ( v6 )
  {
    v9 = L"_p0";
    v11 = 260 - v8;
    v10 = v8 == 260;
    v12 = 2147483646;
    v13 = &pszDest[v8];
    if ( !v10 )
    {
      do
      {
        if ( !v12 )
          break;
        if ( !*v9 )
          break;
        *v13++ = *v9++;
        --v12;
        --v11;
      }
      while ( v11 );
    }
    v14 = v13 - 1;
    if ( v11 )
      v14 = v13;
    *v14 = 0;
  }
  v15 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v16 = v15;
  if ( v15 )
  {
    v39[0] = 0;
    v38 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v15, v39);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v37);
LABEL_31:
      wil::details::CloseHandle(v16, v19);
      return LastError;
    }
    v20 = 260;
    v21 = pszDest;
    do
    {
      if ( !*v21 )
        break;
      ++v21;
      --v20;
    }
    while ( v20 );
    v22 = (260 - v20) & -(__int64)(v20 != 0);
    if ( v20 )
    {
      v23 = &pszDest[v22];
      v24 = L"h";
      v25 = 260 - v22;
      if ( 260 != v22 )
      {
        do
        {
          if ( !v7 )
            break;
          if ( !*v24 )
            break;
          *v23++ = *v24++;
          --v7;
          --v25;
        }
        while ( v25 );
      }
      v26 = v23 - 1;
      if ( v25 )
        v26 = v23;
      *v26 = 0;
    }
    v27 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v29 = v27;
    if ( !v27 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v28);
      goto LABEL_31;
    }
    v30 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v27, &v38);
    LastError = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v30,
        v37);
      wil::details::CloseHandle(v29, v32);
      goto LABEL_31;
    }
    wil::details::CloseHandle(v29, v31);
    *a3 = v39[0] | (unsigned __int64)((__int64)v38 << 31);
    wil::details::CloseHandle(v16, v33);
    return 0;
  }
  if ( GetLastError() == 2 )
    return 0;
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v35);
}

```

## disassembly

```asm
0x180018d74  mov     [rsp-8+arg_8], rbx
0x180018d79  mov     [rsp-8+arg_18], rsi
0x180018d7e  push    rbp
0x180018d7f  push    rdi
0x180018d80  push    r12
0x180018d82  push    r14
0x180018d84  push    r15
0x180018d86  lea     rbp, [rsp-160h]
0x180018d8e  sub     rsp, 260h
0x180018d95  mov     rax, cs:__security_cookie
0x180018d9c  xor     rax, rsp
0x180018d9f  mov     [rbp+180h+var_30], rax
0x180018da6  xor     r12d, r12d
0x180018da9  mov     r9, rcx; pszSrc
0x180018dac  mov     ebx, 104h
0x180018db1  mov     [r8], r12
0x180018db4  mov     edx, ebx; cchDest
0x180018db6  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180018dbb  mov     r15, r8
0x180018dbe  call    StringCopyWorkerW
0x180018dc3  lea     rax, [rsp+280h+pszDest]
0x180018dc8  mov     r11d, ebx
0x180018dcb  cmp     [rax], r12w
0x180018dcf  jz      short loc_180018DDB
0x180018dd1  add     rax, 2
0x180018dd5  sub     r11, 1
0x180018dd9  jnz     short loc_180018DCB
0x180018ddb  mov     rcx, rbx
0x180018dde  mov     rax, r11
0x180018de1  sub     rcx, r11
0x180018de4  mov     r14d, 7FFFFFFEh
0x180018dea  neg     rax
0x180018ded  sbb     rdx, rdx
0x180018df0  and     rdx, rcx
0x180018df3  test    r11, r11
0x180018df6  jz      short loc_180018E42
0x180018df8  mov     rax, rbx
0x180018dfb  lea     r8, aP0; "_p0"
0x180018e02  sub     rax, rdx
0x180018e05  mov     ecx, r14d
0x180018e08  lea     rdx, [rsp+rdx*2+280h+pszDest]
0x180018e0d  jz      short loc_180018E33
0x180018e0f  test    rcx, rcx
0x180018e12  jz      short loc_180018E33
0x180018e14  movzx   r9d, word ptr [r8]
0x180018e18  test    r9w, r9w
0x180018e1c  jz      short loc_180018E33
0x180018e1e  mov     [rdx], r9w
0x180018e22  add     r8, 2
0x180018e26  add     rdx, 2
0x180018e2a  dec     rcx
0x180018e2d  sub     rax, 1
0x180018e31  jnz     short loc_180018E0F
0x180018e33  test    rax, rax
0x180018e36  lea     rcx, [rdx-2]
0x180018e3a  cmovnz  rcx, rdx
0x180018e3e  mov     [rcx], r12w
0x180018e42  lea     r8, [rsp+280h+pszDest]; lpName
0x180018e47  xor     edx, edx; bInheritHandle
0x180018e49  mov     ecx, 1F0003h; dwDesiredAccess
0x180018e4e  call    cs:__imp_OpenSemaphoreW
0x180018e54  mov     rdi, rax
0x180018e57  test    rax, rax
0x180018e5a  jz      loc_180018FAF
0x180018e60  lea     rdx, [rsp+280h+var_24C]; int *
0x180018e65  mov     [rsp+280h+var_24C], r12d
0x180018e6a  mov     rcx, rax; hHandle
0x180018e6d  mov     [rsp+280h+var_250], r12d
0x180018e72  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180018e77  mov     esi, eax
0x180018e79  test    eax, eax
0x180018e7b  jns     short loc_180018E9D
0x180018e7d  mov     rcx, [rbp+188h]; this
0x180018e84  lea     r8, aWil; "wil"
0x180018e8b  mov     r9d, eax; char *
0x180018e8e  mov     edx, 0D6h; void *
0x180018e93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018e98  jmp     loc_180018FA3
0x180018e9d  mov     rdx, rbx
0x180018ea0  lea     rax, [rsp+280h+pszDest]
0x180018ea5  cmp     [rax], r12w
0x180018ea9  jz      short loc_180018EB5
0x180018eab  add     rax, 2
0x180018eaf  sub     rdx, 1
0x180018eb3  jnz     short loc_180018EA5
0x180018eb5  mov     rcx, rbx
0x180018eb8  mov     rax, rdx
0x180018ebb  sub     rcx, rdx
0x180018ebe  neg     rax
0x180018ec1  sbb     r8, r8
0x180018ec4  and     r8, rcx
0x180018ec7  test    rdx, rdx
0x180018eca  jz      short loc_180018F11
0x180018ecc  lea     rax, [rsp+280h+pszDest]
0x180018ed1  lea     rax, [rax+r8*2]
0x180018ed5  lea     rcx, asc_180034A10; "h"
0x180018edc  sub     rbx, r8
0x180018edf  jz      short loc_180018F02
0x180018ee1  test    r14, r14
0x180018ee4  jz      short loc_180018F02
0x180018ee6  movzx   edx, word ptr [rcx]
0x180018ee9  test    dx, dx
0x180018eec  jz      short loc_180018F02
0x180018eee  mov     [rax], dx
0x180018ef1  add     rcx, 2
0x180018ef5  add     rax, 2
0x180018ef9  dec     r14
0x180018efc  sub     rbx, 1
0x180018f00  jnz     short loc_180018EE1
0x180018f02  test    rbx, rbx
0x180018f05  lea     rdx, [rax-2]
0x180018f09  cmovnz  rdx, rax
0x180018f0d  mov     [rdx], r12w
0x180018f11  lea     r8, [rsp+280h+pszDest]; lpName
0x180018f16  xor     edx, edx; bInheritHandle
0x180018f18  mov     ecx, 1F0003h; dwDesiredAccess
0x180018f1d  call    cs:__imp_OpenSemaphoreW
0x180018f23  mov     rbx, rax
0x180018f26  test    rax, rax
0x180018f29  jz      short loc_180018F89
0x180018f2b  lea     rdx, [rsp+280h+var_250]; int *
0x180018f30  mov     rcx, rax; hHandle
0x180018f33  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180018f38  mov     esi, eax
0x180018f3a  test    eax, eax
0x180018f3c  jns     short loc_180018F63
0x180018f3e  mov     rcx, [rbp+188h]; this
0x180018f45  lea     r8, aWil; "wil"
0x180018f4c  mov     r9d, eax; char *
0x180018f4f  mov     edx, 0DEh; void *
0x180018f54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018f59  mov     rcx, rbx; this
0x180018f5c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180018f61  jmp     short loc_180018FA3
0x180018f63  mov     rcx, rbx; this
0x180018f66  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180018f6b  movsxd  rax, [rsp+280h+var_24C]
0x180018f70  movsxd  rcx, [rsp+280h+var_250]
0x180018f75  shl     rcx, 1Fh
0x180018f79  or      rcx, rax
0x180018f7c  mov     [r15], rcx
0x180018f7f  mov     rcx, rdi; this
0x180018f82  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180018f87  jmp     short loc_180018FBA
0x180018f89  mov     rcx, [rbp+188h]; this
0x180018f90  lea     r8, aWil; "wil"
0x180018f97  mov     edx, 0DCh; void *
0x180018f9c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018fa1  mov     esi, eax
0x180018fa3  mov     rcx, rdi; this
0x180018fa6  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180018fab  mov     eax, esi
0x180018fad  jmp     short loc_180018FD6
0x180018faf  call    cs:__imp_GetLastError
0x180018fb5  cmp     eax, 2
0x180018fb8  jnz     short loc_180018FBE
0x180018fba  xor     eax, eax
0x180018fbc  jmp     short loc_180018FD6
0x180018fbe  mov     rcx, [rbp+188h]; this
0x180018fc5  lea     r8, aWil; "wil"
0x180018fcc  mov     edx, 0D0h; void *
0x180018fd1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018fd6  mov     rcx, [rbp+180h+var_30]
0x180018fdd  xor     rcx, rsp; StackCookie
0x180018fe0  call    __security_check_cookie
0x180018fe5  lea     r11, [rsp+280h+var_20]
0x180018fed  mov     rbx, [r11+38h]
0x180018ff1  mov     rsi, [r11+48h]
0x180018ff5  mov     rsp, r11
0x180018ff8  pop     r15
0x180018ffa  pop     r14
0x180018ffc  pop     r12
0x180018ffe  pop     rdi
0x180018fff  pop     rbp
0x180019000  retn
```

# CommandLineBase::Parse(wchar_t const * *,unsigned __int64,wchar_t const * *,unsigned __int64)

- ea: `0x18000e86c`
- end: `0x18000ec84`
- name: `?Parse@CommandLineBase@@QEAAJPEAPEB_W_K01@Z`
- size: `1048`
- prototype: `__int64 __fastcall(CommandLineBase *__hidden this, const wchar_t **, unsigned __int64, const wchar_t **, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000ef98`

## callees

- `0x18000e86c`
- `0x18000ec8c`
- `0x18008fe00`
- `0x180095ed4`
- `0x180096170`
- `0x1800961f0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000ea3c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000ea3c`

## pseudocode

```c
__int64 __fastcall CommandLineBase::Parse(
        CommandLineBase *this,
        const wchar_t **a2,
        unsigned __int64 a3,
        const wchar_t **a4)
{
  const wchar_t **v6; // r14
  CommandLineBase *v7; // r13
  unsigned __int64 v8; // rcx
  __int64 result; // rax
  unsigned __int64 v10; // rsi
  __int64 v11; // rdi
  struct CommandLineArg *v12; // rcx
  unsigned __int64 v13; // rsi
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rax
  const wchar_t *v16; // r12
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // r15
  __int64 v19; // rdx
  const WCHAR *v20; // r14
  WCHAR v21; // ax
  const wchar_t **v22; // rdx
  __int64 cchCount2; // r13
  wchar_t *v24; // rax
  __int64 v25; // rdi
  struct CommandLineArg *v26; // rdx
  unsigned __int64 v27; // rdi
  unsigned __int64 v28; // rdx
  struct CommandLineArg *v29; // rcx
  __int64 v30; // r14
  int v31; // eax
  unsigned __int64 v32; // r15
  __int64 v33; // r8
  _DWORD *i; // r9
  int v35; // [rsp+50h] [rbp-51h]
  unsigned __int64 v37; // [rsp+60h] [rbp-41h] BYREF
  unsigned __int64 v38; // [rsp+68h] [rbp-39h]
  PCNZWCH lpString2; // [rsp+70h] [rbp-31h]
  PCNZWCH lpString1; // [rsp+78h] [rbp-29h]
  PCNZWCH *v41; // [rsp+80h] [rbp-21h]
  unsigned __int64 v42; // [rsp+88h] [rbp-19h]
  __int64 v43; // [rsp+90h] [rbp-11h]
  unsigned __int64 v44; // [rsp+98h] [rbp-9h]
  CommandLineBase *v45; // [rsp+A0h] [rbp-1h]
  struct CommandLineArg *v46; // [rsp+A8h] [rbp+7h] BYREF
  unsigned __int64 v47; // [rsp+B0h] [rbp+Fh] BYREF

  v38 = a3;
  v45 = this;
  v6 = a2;
  v7 = this;
  if ( a4 )
    *a4 = 0;
  v46 = 0;
  v47 = 0;
  (**(void (__fastcall ***)(CommandLineBase *, struct CommandLineArg **, unsigned __int64 *))this)(this, &v46, &v47);
  v8 = v47;
  if ( v47 > 0x40 )
    return 2147942456LL;
  v10 = 0;
  if ( v47 )
  {
    v11 = 0;
    do
    {
      v12 = v46;
      if ( (*(_DWORD *)((_BYTE *)v46 + v11 + 48) & 4) == 0 )
      {
        memset(
          (char *)v7 + *(_QWORD *)((char *)v46 + v11 + 8),
          0,
          *(_QWORD *)((char *)v46 + v11 + 16) * *(_QWORD *)((char *)v46 + v11 + 24));
        v12 = v46;
      }
      *(_QWORD *)((char *)v12 + v11 + 32) = 0;
      ++v10;
      v8 = v47;
      v11 += 56;
    }
    while ( v10 < v47 );
  }
  v37 = 0;
  v13 = 0;
  v14 = 0;
  if ( !a3 )
  {
    v26 = v46;
    goto LABEL_56;
  }
  v15 = 0;
  v44 = 0;
  do
  {
    v16 = v6[v15];
    if ( (*(unsigned __int8 (__fastcall **)(CommandLineBase *, _QWORD))(*(_QWORD *)v7 + 8LL))(v7, *v16) )
    {
      v17 = v47;
      v18 = 0;
      if ( v47 )
      {
        v19 = 0;
        v43 = 0;
        while ( 1 )
        {
          v20 = *(const WCHAR **)((char *)v46 + v19);
          if ( v20 )
          {
            v21 = *v20;
            if ( *v20 )
              break;
          }
LABEL_27:
          v19 += 56;
          ++v18;
          v43 = v19;
          if ( v18 >= v17 )
            goto LABEL_28;
        }
        v42 = v14 + 1;
        v35 = 1;
        lpString1 = v16 + 1;
        v22 = &a2[v44 + 1];
        while ( 1 )
        {
          LODWORD(cchCount2) = -1;
          v41 = v22;
          if ( v21 == 32 )
          {
            do
              ++v20;
            while ( *v20 == 32 );
          }
          lpString2 = v20;
          v24 = wcschr(v20, 0x20u);
          v20 = v24;
          if ( v24 && (cchCount2 = v24 - lpString2, (unsigned __int64)(cchCount2 + 0x80000000LL) > 0xFFFFFFFF)
            || CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, cchCount2) != 2 )
          {
LABEL_26:
            v17 = v47;
            v19 = v43;
            goto LABEL_27;
          }
          if ( (_DWORD)cchCount2 == -1 )
            break;
          if ( v42 >= v38 )
            goto LABEL_26;
          ++v35;
          v22 = v41 + 1;
          lpString1 = *v41;
          v21 = *v20;
          ++v42;
        }
        v25 = 56 * v18;
        if ( *((_QWORD *)v46 + 7 * v18 + 4) && (*((_BYTE *)v46 + v25 + 48) & 0x18) == 0 )
        {
          if ( a4 )
            *a4 = v16;
          return 2147942485LL;
        }
        v6 = a2;
        v7 = v45;
        result = CommandLineBase::ParseArg(v45, &v37, v35, a2, v38, v18, v46, v47, v16, a4);
        if ( (int)result < 0 )
          return result;
        v8 = v47;
        if ( v18 < v47 )
        {
          v26 = v46;
          if ( (*((_BYTE *)v46 + v25 + 48) & 0x20) == 0 )
          {
            v27 = v37;
            goto LABEL_50;
          }
          break;
        }
      }
LABEL_28:
      if ( a4 )
        *a4 = v16;
      return 2147942422LL;
    }
    v28 = v47;
    if ( v13 >= v47 )
      goto LABEL_28;
    v29 = v46;
    v30 = 56 * v13;
    while ( 1 )
    {
      v31 = *(_DWORD *)((char *)v29 + v30 + 48);
      if ( (v31 & 1) == 0 || *(_QWORD *)((char *)v29 + v30 + 32) && (v31 & 0x10) == 0 )
        goto LABEL_45;
      v32 = v14;
      result = CommandLineBase::ParseArg(
                 v7,
                 &v37,
                 0,
                 a2,
                 v38,
                 v13,
                 v29,
                 v28,
                 *(const wchar_t **)((char *)v29 + v30),
                 a4);
      if ( (int)result < 0 )
        return result;
      v14 = v37;
      if ( v37 > v32 )
        break;
      v29 = v46;
      v28 = v47;
LABEL_45:
      ++v13;
      v30 += 56;
      if ( v13 >= v28 )
        goto LABEL_28;
    }
    v8 = v47;
    v27 = v37 - 1;
    if ( v13 >= v47 )
      goto LABEL_28;
    v26 = v46;
    v6 = a2;
    if ( (*((_BYTE *)v46 + 56 * v13 + 48) & 0x10) == 0 )
      ++v13;
LABEL_50:
    v14 = v27 + 1;
    v15 = v14;
    v37 = v14;
    v44 = v14;
  }
  while ( v14 < v38 );
LABEL_56:
  v33 = 0;
  if ( !v8 )
    return 0;
  for ( i = (_DWORD *)((char *)v26 + 48); *((_QWORD *)i - 2) || (*i & 2) == 0; i += 14 )
  {
    if ( ++v33 >= v8 )
      return 0;
  }
  if ( a4 )
    *a4 = (const wchar_t *)*((_QWORD *)v26 + 7 * v33);
  return 2147942560LL;
}

```

## disassembly

```asm
0x18000e86c  mov     [rsp-8+arg_10], rbx
0x18000e871  push    rbp
0x18000e872  push    rsi
0x18000e873  push    rdi
0x18000e874  push    r12
0x18000e876  push    r13
0x18000e878  push    r14
0x18000e87a  push    r15
0x18000e87c  lea     rbp, [rsp-1Fh]
0x18000e881  sub     rsp, 0C0h
0x18000e888  mov     rax, cs:__security_cookie
0x18000e88f  xor     rax, rsp
0x18000e892  mov     [rbp+4Fh+var_38], rax
0x18000e896  xor     eax, eax
0x18000e898  mov     [rbp+4Fh+var_88], r8
0x18000e89c  mov     [rbp+4Fh+var_98], rdx
0x18000e8a0  mov     rbx, r9
0x18000e8a3  mov     [rbp+4Fh+var_50], rcx
0x18000e8a7  mov     r15, r8
0x18000e8aa  mov     r14, rdx
0x18000e8ad  mov     r13, rcx
0x18000e8b0  test    r9, r9
0x18000e8b3  jz      short loc_18000E8B8
0x18000e8b5  mov     [r9], rax
0x18000e8b8  mov     [rbp+4Fh+var_48], rax
0x18000e8bc  lea     r8, [rbp+4Fh+var_40]
0x18000e8c0  mov     [rbp+4Fh+var_40], rax
0x18000e8c4  lea     rdx, [rbp+4Fh+var_48]
0x18000e8c8  mov     rax, [rcx]
0x18000e8cb  mov     rax, [rax]
0x18000e8ce  call    _guard_dispatch_icall
0x18000e8d3  mov     rcx, [rbp+4Fh+var_40]
0x18000e8d7  cmp     rcx, 40h ; '@'
0x18000e8db  jbe     short loc_18000E8E7
0x18000e8dd  mov     eax, 80070038h
0x18000e8e2  jmp     loc_18000EC46
0x18000e8e7  xor     r10d, r10d
0x18000e8ea  mov     esi, r10d
0x18000e8ed  test    rcx, rcx
0x18000e8f0  jz      short loc_18000E937
0x18000e8f2  mov     edi, r10d
0x18000e8f5  mov     rcx, [rbp+4Fh+var_48]
0x18000e8f9  mov     eax, [rdi+rcx+30h]
0x18000e8fd  test    al, 4
0x18000e8ff  jnz     short loc_18000E922
0x18000e901  mov     r8, [rdi+rcx+18h]
0x18000e906  xor     edx, edx; Val
0x18000e908  imul    r8, [rdi+rcx+10h]; Size
0x18000e90e  mov     rcx, [rdi+rcx+8]
0x18000e913  add     rcx, r13; void *
0x18000e916  call    memset
0x18000e91b  mov     rcx, [rbp+4Fh+var_48]
0x18000e91f  xor     r10d, r10d
0x18000e922  mov     [rdi+rcx+20h], r10
0x18000e927  inc     rsi
0x18000e92a  mov     rcx, [rbp+4Fh+var_40]
0x18000e92e  add     rdi, 38h ; '8'
0x18000e932  cmp     rsi, rcx
0x18000e935  jb      short loc_18000E8F5
0x18000e937  mov     [rbp+4Fh+var_90], r10
0x18000e93b  mov     rsi, r10
0x18000e93e  mov     rdi, r10
0x18000e941  test    r15, r15
0x18000e944  jz      loc_18000EC1B
0x18000e94a  mov     rax, r10
0x18000e94d  mov     [rbp+4Fh+var_58], rax
0x18000e951  mov     r12, [r14+rax*8]
0x18000e955  mov     rcx, r13
0x18000e958  mov     rax, [r13+0]
0x18000e95c  movzx   edx, word ptr [r12]
0x18000e961  mov     rax, [rax+8]
0x18000e965  call    _guard_dispatch_icall
0x18000e96a  xor     r10d, r10d
0x18000e96d  test    al, al
0x18000e96f  jz      loc_18000EB3A
0x18000e975  mov     rcx, [rbp+4Fh+var_40]
0x18000e979  mov     r15d, r10d
0x18000e97c  test    rcx, rcx
0x18000e97f  jz      loc_18000EA98
0x18000e985  mov     edx, r10d
0x18000e988  mov     [rbp+4Fh+var_60], rdx
0x18000e98c  mov     rax, [rbp+4Fh+var_48]
0x18000e990  mov     r14, [rdx+rax]
0x18000e994  test    r14, r14
0x18000e997  jz      loc_18000EA84
0x18000e99d  movzx   eax, word ptr [r14]
0x18000e9a1  cmp     r10w, ax
0x18000e9a5  jz      loc_18000EA84
0x18000e9ab  mov     rdx, [rbp+4Fh+var_98]
0x18000e9af  lea     rcx, [rdi+1]
0x18000e9b3  mov     [rbp+4Fh+var_68], rcx
0x18000e9b7  lea     r8, [r12+2]
0x18000e9bc  mov     rcx, [rbp+4Fh+var_58]
0x18000e9c0  mov     [rbp+4Fh+var_A0], 1
0x18000e9c7  mov     [rbp+4Fh+lpString1], r8
0x18000e9cb  lea     rdx, [rdx+rcx*8]
0x18000e9cf  add     rdx, 8
0x18000e9d3  or      r13d, 0FFFFFFFFh
0x18000e9d7  mov     [rbp+4Fh+var_70], rdx
0x18000e9db  lea     ecx, [r13+21h]
0x18000e9df  cmp     cx, ax
0x18000e9e2  jnz     short loc_18000E9EE
0x18000e9e4  add     r14, 2
0x18000e9e8  cmp     cx, [r14]
0x18000e9ec  jz      short loc_18000E9E4
0x18000e9ee  mov     edx, ecx; Ch
0x18000e9f0  mov     [rbp+4Fh+var_80], r14
0x18000e9f4  mov     rcx, r14; Str
0x18000e9f7  call    wcschr
0x18000e9fc  mov     rcx, [rbp+4Fh+var_80]
0x18000ea00  mov     r14, rax
0x18000ea03  test    rax, rax
0x18000ea06  jz      short loc_18000EA23
0x18000ea08  mov     r13, rax
0x18000ea0b  mov     edx, 0FFFFFFFFh
0x18000ea10  sub     r13, rcx
0x18000ea13  mov     eax, 80000000h
0x18000ea18  sar     r13, 1
0x18000ea1b  add     rax, r13
0x18000ea1e  cmp     rax, rdx
0x18000ea21  ja      short loc_18000EA79
0x18000ea23  mov     r8, [rbp+4Fh+lpString1]; lpString1
0x18000ea27  or      r9d, 0FFFFFFFFh; cchCount1
0x18000ea2b  mov     [rsp+0F0h+cchCount2], r13d; cchCount2
0x18000ea30  mov     [rsp+0F0h+lpString2], rcx; lpString2
0x18000ea35  lea     edx, [r9+2]; dwCmpFlags
0x18000ea39  lea     ecx, [rdx+7Eh]; Locale
0x18000ea3c  call    cs:__imp_CompareStringW
0x18000ea42  cmp     eax, 2
0x18000ea45  jnz     short loc_18000EA79
0x18000ea47  cmp     r13d, 0FFFFFFFFh
0x18000ea4b  jz      short loc_18000EAAA
0x18000ea4d  mov     rcx, [rbp+4Fh+var_68]
0x18000ea51  cmp     rcx, [rbp+4Fh+var_88]
0x18000ea55  jnb     short loc_18000EA79
0x18000ea57  mov     rdx, [rbp+4Fh+var_70]
0x18000ea5b  inc     [rbp+4Fh+var_A0]
0x18000ea5e  mov     rax, [rdx]
0x18000ea61  add     rdx, 8
0x18000ea65  inc     rcx
0x18000ea68  mov     [rbp+4Fh+lpString1], rax
0x18000ea6c  movzx   eax, word ptr [r14]
0x18000ea70  mov     [rbp+4Fh+var_68], rcx
0x18000ea74  jmp     loc_18000E9D3
0x18000ea79  mov     rcx, [rbp+4Fh+var_40]
0x18000ea7d  xor     r10d, r10d
0x18000ea80  mov     rdx, [rbp+4Fh+var_60]
0x18000ea84  add     rdx, 38h ; '8'
0x18000ea88  inc     r15
0x18000ea8b  mov     [rbp+4Fh+var_60], rdx
0x18000ea8f  cmp     r15, rcx
0x18000ea92  jb      loc_18000E98C
0x18000ea98  test    rbx, rbx
0x18000ea9b  jz      short loc_18000EAA0
0x18000ea9d  mov     [rbx], r12
0x18000eaa0  mov     eax, 80070016h
0x18000eaa5  jmp     loc_18000EC46
0x18000eaaa  mov     rcx, [rbp+4Fh+var_48]
0x18000eaae  imul    rdi, r15, 38h ; '8'
0x18000eab2  cmp     qword ptr [rdi+rcx+20h], 0
0x18000eab8  jbe     short loc_18000EAC5
0x18000eaba  test    byte ptr [rdi+rcx+30h], 18h
0x18000eabf  jz      loc_18000EC0C
0x18000eac5  mov     rax, [rbp+4Fh+var_40]
0x18000eac9  lea     rdx, [rbp+4Fh+var_90]; unsigned __int64 *
0x18000eacd  mov     r14, [rbp+4Fh+var_98]
0x18000ead1  mov     r13, [rbp+4Fh+var_50]
0x18000ead5  mov     r9, r14; wchar_t **
0x18000ead8  movsxd  r8, [rbp+4Fh+var_A0]; unsigned __int64
0x18000eadc  mov     [rsp+0F0h+var_A8], rbx; wchar_t **
0x18000eae1  mov     [rsp+0F0h+var_B0], r12; wchar_t *
0x18000eae6  mov     [rsp+0F0h+var_B8], rax; unsigned __int64
0x18000eaeb  mov     rax, [rbp+4Fh+var_88]
0x18000eaef  mov     [rsp+0F0h+var_C0], rcx; struct CommandLineArg *
0x18000eaf4  mov     rcx, r13; this
0x18000eaf7  mov     qword ptr [rsp+0F0h+cchCount2], r15; unsigned __int64
0x18000eafc  mov     [rsp+0F0h+lpString2], rax; unsigned __int64
0x18000eb01  call    ?ParseArg@CommandLineBase@@AEAAJPEA_K_KPEAPEB_W11PEAUCommandLineArg@@1PEB_W2@Z; CommandLineBase::ParseArg(unsigned __int64 *,unsigned __int64,wchar_t const * *,unsigned __int64,unsigned __int64,CommandLineArg *,unsigned __int64,wchar_t const *,wchar_t const * *)
0x18000eb06  xor     r10d, r10d
0x18000eb09  test    eax, eax
0x18000eb0b  js      loc_18000EC46
0x18000eb11  mov     rcx, [rbp+4Fh+var_40]
0x18000eb15  cmp     r15, rcx
0x18000eb18  jnb     loc_18000EA98
0x18000eb1e  mov     rdx, [rbp+4Fh+var_48]
0x18000eb22  lea     r8d, [r10+20h]
0x18000eb26  test    [rdi+rdx+30h], r8b
0x18000eb2b  jnz     loc_18000EC1F
0x18000eb31  mov     rdi, [rbp+4Fh+var_90]
0x18000eb35  jmp     loc_18000EBF2
0x18000eb3a  mov     rdx, [rbp+4Fh+var_40]
0x18000eb3e  cmp     rsi, rdx
0x18000eb41  jnb     loc_18000EA98
0x18000eb47  mov     rcx, [rbp+4Fh+var_48]
0x18000eb4b  imul    r14, rsi, 38h ; '8'
0x18000eb4f  mov     eax, [r14+rcx+30h]
0x18000eb54  test    al, 1
0x18000eb56  jz      short loc_18000EBBB
0x18000eb58  cmp     [r14+rcx+20h], r10
0x18000eb5d  jbe     short loc_18000EB63
0x18000eb5f  test    al, 10h
0x18000eb61  jz      short loc_18000EBBB
0x18000eb63  mov     rax, [r14+rcx]
0x18000eb67  xor     r8d, r8d; unsigned __int64
0x18000eb6a  mov     r9, [rbp+4Fh+var_98]; wchar_t **
0x18000eb6e  mov     r15, rdi
0x18000eb71  mov     [rsp+0F0h+var_A8], rbx; wchar_t **
0x18000eb76  mov     [rsp+0F0h+var_B0], rax; wchar_t *
0x18000eb7b  mov     rax, [rbp+4Fh+var_88]
0x18000eb7f  mov     [rsp+0F0h+var_B8], rdx; unsigned __int64
0x18000eb84  lea     rdx, [rbp+4Fh+var_90]; unsigned __int64 *
0x18000eb88  mov     [rsp+0F0h+var_C0], rcx; struct CommandLineArg *
0x18000eb8d  mov     rcx, r13; this
0x18000eb90  mov     qword ptr [rsp+0F0h+cchCount2], rsi; unsigned __int64
0x18000eb95  mov     [rsp+0F0h+lpString2], rax; unsigned __int64
0x18000eb9a  call    ?ParseArg@CommandLineBase@@AEAAJPEA_K_KPEAPEB_W11PEAUCommandLineArg@@1PEB_W2@Z; CommandLineBase::ParseArg(unsigned __int64 *,unsigned __int64,wchar_t const * *,unsigned __int64,unsigned __int64,CommandLineArg *,unsigned __int64,wchar_t const *,wchar_t const * *)
0x18000eb9f  xor     r10d, r10d
0x18000eba2  test    eax, eax
0x18000eba4  js      loc_18000EC46
0x18000ebaa  mov     rdi, [rbp+4Fh+var_90]
0x18000ebae  cmp     rdi, r15
0x18000ebb1  ja      short loc_18000EBCC
0x18000ebb3  mov     rcx, [rbp+4Fh+var_48]
0x18000ebb7  mov     rdx, [rbp+4Fh+var_40]
0x18000ebbb  inc     rsi
0x18000ebbe  add     r14, 38h ; '8'
0x18000ebc2  cmp     rsi, rdx
0x18000ebc5  jb      short loc_18000EB4F
0x18000ebc7  jmp     loc_18000EA98
0x18000ebcc  mov     rcx, [rbp+4Fh+var_40]
0x18000ebd0  dec     rdi
0x18000ebd3  cmp     rsi, rcx
0x18000ebd6  jnb     loc_18000EA98
0x18000ebdc  mov     rdx, [rbp+4Fh+var_48]
0x18000ebe0  mov     r14, [rbp+4Fh+var_98]
0x18000ebe4  imul    rax, rsi, 38h ; '8'
0x18000ebe8  test    byte ptr [rax+rdx+30h], 10h
0x18000ebed  jnz     short loc_18000EBF2
0x18000ebef  inc     rsi
0x18000ebf2  inc     rdi
0x18000ebf5  mov     rax, rdi
0x18000ebf8  mov     [rbp+4Fh+var_90], rdi
0x18000ebfc  mov     [rbp+4Fh+var_58], rax
0x18000ec00  cmp     rdi, [rbp+4Fh+var_88]
0x18000ec04  jb      loc_18000E951
0x18000ec0a  jmp     short loc_18000EC1F
0x18000ec0c  test    rbx, rbx
0x18000ec0f  jz      short loc_18000EC14
0x18000ec11  mov     [rbx], r12
0x18000ec14  mov     eax, 80070055h
0x18000ec19  jmp     short loc_18000EC46
0x18000ec1b  mov     rdx, [rbp+4Fh+var_48]
0x18000ec1f  mov     r8, r10
0x18000ec22  test    rcx, rcx
0x18000ec25  jz      short loc_18000EC44
0x18000ec27  lea     r9, [rdx+30h]
0x18000ec2b  cmp     [r9-10h], r10
0x18000ec2f  ja      short loc_18000EC38
0x18000ec31  mov     eax, [r9]
0x18000ec34  test    al, 2
0x18000ec36  jnz     short loc_18000EC6D
0x18000ec38  inc     r8
0x18000ec3b  add     r9, 38h ; '8'
0x18000ec3f  cmp     r8, rcx
0x18000ec42  jb      short loc_18000EC2B
0x18000ec44  xor     eax, eax
0x18000ec46  mov     rcx, [rbp+4Fh+var_38]
0x18000ec4a  xor     rcx, rsp; StackCookie
0x18000ec4d  call    __security_check_cookie
0x18000ec52  mov     rbx, [rsp+0F0h+arg_10]
0x18000ec5a  add     rsp, 0C0h
0x18000ec61  pop     r15
0x18000ec63  pop     r14
0x18000ec65  pop     r13
0x18000ec67  pop     r12
0x18000ec69  pop     rdi
0x18000ec6a  pop     rsi
0x18000ec6b  pop     rbp
0x18000ec6c  retn
0x18000ec6d  test    rbx, rbx
0x18000ec70  jz      short loc_18000EC7D
0x18000ec72  imul    rax, r8, 38h ; '8'
0x18000ec76  mov     rcx, [rax+rdx]
0x18000ec7a  mov     [rbx], rcx
0x18000ec7d  mov     eax, 800700A0h
0x18000ec82  jmp     short loc_18000EC46
```

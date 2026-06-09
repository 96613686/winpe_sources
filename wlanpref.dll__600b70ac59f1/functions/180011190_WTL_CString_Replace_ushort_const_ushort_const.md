# WTL::CString::Replace(ushort const *,ushort const *)

- ea: `0x180011190`
- end: `0x180011412`
- name: `?Replace@CString@WTL@@QEAAHPEBG0@Z`
- size: `642`
- prototype: `__int64 __fastcall(WTL::CString *__hidden this, wchar_t *SubStr, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000fb60`

## callees

- `0x1800048d4`
- `0x180004c00`
- `0x180005840`
- `0x18000b85c`
- `0x180011190`

## import_xrefs

- `msvcrt!wcsstr` at `0x180011208`
- `msvcrt!wcsstr` at `0x180011226`
- `msvcrt!wcsstr` at `0x1800112eb`
- `msvcrt!wcsstr` at `0x1800113a3`
- `msvcrt!wcsstr` at `0x180011208`
- `msvcrt!wcsstr` at `0x180011226`
- `msvcrt!wcsstr` at `0x1800112eb`
- `msvcrt!wcsstr` at `0x1800113a3`
- `msvcrt!memmove_s` at `0x180011354`
- `msvcrt!memmove_s` at `0x180011354`
- `msvcrt!memcpy_s` at `0x1800112b6`
- `msvcrt!memcpy_s` at `0x180011379`
- `msvcrt!memcpy_s` at `0x1800112b6`
- `msvcrt!memcpy_s` at `0x180011379`
- `KERNEL32!lstrlenW` at `0x1800111bb`
- `KERNEL32!lstrlenW` at `0x1800111d3`
- `KERNEL32!lstrlenW` at `0x18001123c`
- `KERNEL32!lstrlenW` at `0x1800113c5`
- `KERNEL32!lstrlenW` at `0x1800111bb`
- `KERNEL32!lstrlenW` at `0x1800111d3`
- `KERNEL32!lstrlenW` at `0x18001123c`
- `KERNEL32!lstrlenW` at `0x1800113c5`

## pseudocode

```c
__int64 __fastcall WTL::CString::Replace(const wchar_t **this, wchar_t *SubStr, const unsigned __int16 *a3)
{
  int v5; // eax
  __int64 v6; // r12
  int v7; // eax
  const wchar_t *v8; // rbx
  int v9; // r15d
  int v10; // r13d
  unsigned __int64 v11; // rsi
  wchar_t *v12; // rax
  __int64 v13; // rdi
  const wchar_t *v14; // rdi
  int v15; // r13d
  errno_t v17; // eax
  const wchar_t *v18; // rsi
  wchar_t *v19; // rdx
  int v20; // r9d
  rsize_t v21; // r13
  __int64 v22; // rcx
  int v23; // ebx
  rsize_t v24; // rdi
  errno_t v25; // eax
  errno_t v26; // eax
  wchar_t *v27; // rax
  int v28; // [rsp+20h] [rbp-58h]
  wchar_t *Destination; // [rsp+28h] [rbp-50h]
  unsigned __int64 v30; // [rsp+30h] [rbp-48h]
  int v31; // [rsp+88h] [rbp+10h]
  int v32; // [rsp+90h] [rbp+18h]
  int v33; // [rsp+98h] [rbp+20h]

  if ( !SubStr )
    return 0;
  v5 = lstrlenW(SubStr);
  v6 = v5;
  if ( !v5 )
    return 0;
  v7 = lstrlenW(&word_180034F94);
  v8 = *this;
  v9 = 0;
  v10 = v7;
  v31 = v7;
  v33 = 0;
  v11 = (unsigned __int64)&(*this)[*((int *)*this - 2)];
  if ( (unsigned __int64)*this < v11 )
  {
    do
    {
      v12 = wcsstr(v8, SubStr);
      if ( v12 )
      {
        v13 = v6;
        do
        {
          v8 = &v12[v13];
          ++v9;
          v12 = wcsstr(&v12[v13], SubStr);
        }
        while ( v12 );
        v33 = v9;
      }
      v8 += lstrlenW(v8) + 1;
    }
    while ( (unsigned __int64)v8 < v11 );
    if ( v9 > 0 )
    {
      WTL::CString::CopyBeforeWrite((WTL::CString *)this);
      v14 = *this;
      v32 = *((_DWORD *)*this - 2);
      v15 = v32 + v9 * (v10 - v6);
      v28 = v15;
      if ( *((_DWORD *)*this - 1) < v15 || *((int *)v14 - 3) > 1 )
      {
        if ( !(unsigned int)WTL::CString::AllocBuffer((WTL::CString *)this, v15) )
          return 0xFFFFFFFFLL;
        v17 = memcpy_s((void *const)*this, 2LL * (v15 + 1), v14, 2LL * *((int *)v14 - 2));
        ATL::AtlCrtErrorCheck(v17);
        WTL::CString::Release((struct WTL::CStringData *)(v14 - 6));
      }
      v18 = *this;
      v30 = (unsigned __int64)&(*this)[*((int *)*this - 2)];
      if ( (unsigned __int64)*this < v30 )
      {
        do
        {
          Destination = wcsstr(v18, SubStr);
          v19 = Destination;
          if ( Destination )
          {
            v20 = v31;
            v21 = v31;
            do
            {
              v18 = &v19[v21];
              v22 = v19 - *this;
              v23 = *((_DWORD *)*this - 1) - v22;
              v24 = v32 - (int)v22 - (int)v6;
              v25 = memmove_s(&v19[v21], 2LL * (v23 - v20 + 1), &v19[v6], v24 * 2);
              ATL::AtlCrtErrorCheck(v25);
              v26 = memcpy_s(Destination, 2LL * (v23 + 1), &word_180034F94, v21 * 2);
              ATL::AtlCrtErrorCheck(v26);
              v18[v24] = 0;
              v32 += v31 - v6;
              v27 = wcsstr(v18, SubStr);
              v20 = v31;
              v19 = v27;
              Destination = v27;
            }
            while ( v27 );
          }
          v18 += lstrlenW(v18) + 1;
        }
        while ( (unsigned __int64)v18 < v30 );
        v9 = v33;
        v15 = v28;
      }
      *((_DWORD *)*this - 2) = v15;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180011190  mov     [rsp+arg_0], rbx
0x180011195  mov     [rsp+arg_10], r8
0x18001119a  push    rbp
0x18001119b  push    rsi
0x18001119c  push    rdi
0x18001119d  push    r12
0x18001119f  push    r13
0x1800111a1  push    r14
0x1800111a3  push    r15
0x1800111a5  sub     rsp, 40h
0x1800111a9  mov     rbp, rdx
0x1800111ac  mov     r14, rcx
0x1800111af  test    rdx, rdx
0x1800111b2  jz      loc_1800113F8
0x1800111b8  mov     rcx, rdx; lpString
0x1800111bb  call    cs:__imp_lstrlenW
0x1800111c1  movsxd  r12, eax
0x1800111c4  test    eax, eax
0x1800111c6  jz      loc_1800113F8
0x1800111cc  lea     rcx, word_180034F94; lpString
0x1800111d3  call    cs:__imp_lstrlenW
0x1800111d9  mov     rbx, [r14]
0x1800111dc  xor     r15d, r15d
0x1800111df  mov     r13d, eax
0x1800111e2  mov     [rsp+78h+arg_8], eax
0x1800111e9  mov     [rsp+78h+arg_18], r15d
0x1800111f1  movsxd  rax, dword ptr [rbx-8]
0x1800111f5  lea     rsi, [rbx+rax*2]
0x1800111f9  cmp     rbx, rsi
0x1800111fc  jnb     loc_1800113F3
0x180011202  mov     rdx, rbp; SubStr
0x180011205  mov     rcx, rbx; Str
0x180011208  call    cs:__imp_wcsstr
0x18001120e  test    rax, rax
0x180011211  jz      short loc_180011239
0x180011213  mov     rdi, r12
0x180011216  add     rdi, rdi
0x180011219  lea     rbx, [rdi+rax]
0x18001121d  mov     rdx, rbp; SubStr
0x180011220  mov     rcx, rbx; Str
0x180011223  inc     r15d
0x180011226  call    cs:__imp_wcsstr
0x18001122c  test    rax, rax
0x18001122f  jnz     short loc_180011219
0x180011231  mov     [rsp+78h+arg_18], r15d
0x180011239  mov     rcx, rbx; lpString
0x18001123c  call    cs:__imp_lstrlenW
0x180011242  inc     eax
0x180011244  cdqe
0x180011246  lea     rbx, [rbx+rax*2]
0x18001124a  cmp     rbx, rsi
0x18001124d  jb      short loc_180011202
0x18001124f  test    r15d, r15d
0x180011252  jle     loc_1800113F3
0x180011258  mov     rcx, r14; this
0x18001125b  call    ?CopyBeforeWrite@CString@WTL@@IEAAXXZ; WTL::CString::CopyBeforeWrite(void)
0x180011260  mov     rdi, [r14]
0x180011263  sub     r13d, r12d
0x180011266  imul    r13d, r15d
0x18001126a  mov     ecx, [rdi-8]
0x18001126d  mov     dword ptr [rsp+78h+arg_10], ecx
0x180011274  add     r13d, ecx
0x180011277  mov     [rsp+78h+var_58], r13d
0x18001127c  cmp     [rdi-4], r13d
0x180011280  jl      short loc_180011288
0x180011282  cmp     dword ptr [rdi-0Ch], 1
0x180011286  jle     short loc_1800112CC
0x180011288  mov     edx, r13d; int
0x18001128b  mov     rcx, r14; this
0x18001128e  call    ?AllocBuffer@CString@WTL@@IEAAHH@Z; WTL::CString::AllocBuffer(int)
0x180011293  test    eax, eax
0x180011295  jnz     short loc_18001129F
0x180011297  or      eax, 0FFFFFFFFh
0x18001129a  jmp     loc_1800113FA
0x18001129f  movsxd  r9, dword ptr [rdi-8]
0x1800112a3  lea     eax, [r13+1]
0x1800112a7  mov     rcx, [r14]; Destination
0x1800112aa  add     r9, r9; SourceSize
0x1800112ad  movsxd  rdx, eax
0x1800112b0  mov     r8, rdi; Source
0x1800112b3  add     rdx, rdx; DestinationSize
0x1800112b6  call    cs:__imp_memcpy_s
0x1800112bc  mov     ecx, eax; int
0x1800112be  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800112c3  lea     rcx, [rdi-0Ch]; struct WTL::CStringData *
0x1800112c7  call    ?Release@CString@WTL@@KAXPEAUCStringData@2@@Z; WTL::CString::Release(WTL::CStringData *)
0x1800112cc  mov     rsi, [r14]
0x1800112cf  movsxd  rax, dword ptr [rsi-8]
0x1800112d3  lea     rax, [rsi+rax*2]
0x1800112d7  mov     [rsp+78h+var_48], rax
0x1800112dc  cmp     rsi, rax
0x1800112df  jnb     loc_1800113EC
0x1800112e5  mov     rdx, rbp; SubStr
0x1800112e8  mov     rcx, rsi; Str
0x1800112eb  call    cs:__imp_wcsstr
0x1800112f1  mov     [rsp+78h+Destination], rax
0x1800112f6  mov     rdx, rax
0x1800112f9  test    rax, rax
0x1800112fc  jz      loc_1800113C2
0x180011302  movsxd  r9, [rsp+78h+arg_8]
0x18001130a  mov     r15, r12
0x18001130d  add     r15, r15
0x180011310  mov     r13, r9
0x180011313  add     r13, r13
0x180011316  mov     rax, [r14]
0x180011319  lea     rsi, [rdx+r13]
0x18001131d  mov     rcx, rdx
0x180011320  lea     r8, [r15+rdx]; Source
0x180011324  sub     rcx, rax
0x180011327  sar     rcx, 1
0x18001132a  mov     ebx, [rax-4]
0x18001132d  mov     eax, dword ptr [rsp+78h+arg_10]
0x180011334  sub     ebx, ecx
0x180011336  sub     eax, ecx
0x180011338  mov     rcx, rsi; Destination
0x18001133b  sub     eax, r12d
0x18001133e  cdqe
0x180011340  lea     rdi, [rax+rax]
0x180011344  mov     eax, ebx
0x180011346  sub     eax, r9d
0x180011349  mov     r9, rdi; SourceSize
0x18001134c  inc     eax
0x18001134e  movsxd  rdx, eax
0x180011351  add     rdx, rdx; DestinationSize
0x180011354  call    cs:__imp_memmove_s
0x18001135a  mov     ecx, eax; int
0x18001135c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180011361  mov     rcx, [rsp+78h+Destination]; Destination
0x180011366  lea     eax, [rbx+1]
0x180011369  movsxd  rdx, eax
0x18001136c  lea     r8, word_180034F94; Source
0x180011373  add     rdx, rdx; DestinationSize
0x180011376  mov     r9, r13; SourceSize
0x180011379  call    cs:__imp_memcpy_s
0x18001137f  mov     ecx, eax; int
0x180011381  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180011386  xor     eax, eax
0x180011388  mov     rdx, rbp; SubStr
0x18001138b  mov     [rsi+rdi], ax
0x18001138f  mov     rcx, rsi; Str
0x180011392  mov     eax, [rsp+78h+arg_8]
0x180011399  sub     eax, r12d
0x18001139c  add     dword ptr [rsp+78h+arg_10], eax
0x1800113a3  call    cs:__imp_wcsstr
0x1800113a9  mov     r9d, [rsp+78h+arg_8]
0x1800113b1  mov     rdx, rax
0x1800113b4  mov     [rsp+78h+Destination], rax
0x1800113b9  test    rax, rax
0x1800113bc  jnz     loc_180011316
0x1800113c2  mov     rcx, rsi; lpString
0x1800113c5  call    cs:__imp_lstrlenW
0x1800113cb  inc     eax
0x1800113cd  movsxd  rcx, eax
0x1800113d0  lea     rsi, [rsi+rcx*2]
0x1800113d4  cmp     rsi, [rsp+78h+var_48]
0x1800113d9  jb      loc_1800112E5
0x1800113df  mov     r15d, [rsp+78h+arg_18]
0x1800113e7  mov     r13d, [rsp+78h+var_58]
0x1800113ec  mov     rcx, [r14]
0x1800113ef  mov     [rcx-8], r13d
0x1800113f3  mov     eax, r15d
0x1800113f6  jmp     short loc_1800113FA
0x1800113f8  xor     eax, eax
0x1800113fa  mov     rbx, [rsp+78h+arg_0]
0x180011402  add     rsp, 40h
0x180011406  pop     r15
0x180011408  pop     r14
0x18001140a  pop     r13
0x18001140c  pop     r12
0x18001140e  pop     rdi
0x18001140f  pop     rsi
0x180011410  pop     rbp
0x180011411  retn
```

# ResolveAccountSid(void *,ushort * *,ushort * *,ushort * *)

- ea: `0x1800137b0`
- end: `0x180013a02`
- name: `?ResolveAccountSid@@YAKPEAXPEAPEAG11@Z`
- size: `594`
- prototype: `unsigned int __fastcall(PSID Sid, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180012d70`

## callees

- `0x18000214c`
- `0x180006310`
- `0x1800137b0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001396d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800139b1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800139c5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001396d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800139b1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800139c5`
- `KERNEL32!GetLastError` at `0x180013832`
- `KERNEL32!GetLastError` at `0x1800138dd`
- `KERNEL32!GetLastError` at `0x1800139d3`
- `KERNEL32!GetLastError` at `0x180013832`
- `KERNEL32!GetLastError` at `0x1800138dd`
- `KERNEL32!GetLastError` at `0x1800139d3`
- `ADVAPI32!LookupAccountSidW` at `0x18001380a`
- `ADVAPI32!LookupAccountSidW` at `0x1800138cd`
- `ADVAPI32!LookupAccountSidW` at `0x18001380a`
- `ADVAPI32!LookupAccountSidW` at `0x1800138cd`

## pseudocode

```c
__int64 __fastcall ResolveAccountSid(PSID Sid, unsigned __int16 **a2, unsigned __int16 **a3, unsigned __int16 **a4)
{
  unsigned __int64 v8; // rax
  WCHAR *v9; // rsi
  signed int LastError; // ebx
  unsigned __int64 v11; // rax
  WCHAR *ReferencedDomainName; // rdi
  __int64 v13; // r8
  __int64 v14; // rcx
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rax
  unsigned __int16 *v17; // rax
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-20h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-1Ch] BYREF
  enum _SID_NAME_USE peUse[6]; // [rsp+48h] [rbp-18h] BYREF

  cchName = 0;
  cchReferencedDomainName = 0;
  peUse[0] = 0;
  if ( LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, peUse)
    || !cchName
    || !cchReferencedDomainName
    || GetLastError() == 1332 )
  {
    return GetLastError();
  }
  v8 = 2LL * cchName;
  if ( !is_mul_ok(cchName, 2u) )
    v8 = -1;
  v9 = (WCHAR *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v9 )
    return 8;
  v11 = 2LL * cchReferencedDomainName;
  if ( !is_mul_ok(cchReferencedDomainName, 2u) )
    v11 = -1;
  ReferencedDomainName = (WCHAR *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
  if ( !ReferencedDomainName )
    goto LABEL_12;
  if ( !LookupAccountSidW(0, Sid, v9, &cchName, ReferencedDomainName, &cchReferencedDomainName, peUse) )
  {
    LastError = GetLastError();
    goto LABEL_33;
  }
  if ( !a4 )
  {
LABEL_28:
    if ( a2 )
    {
      *a2 = v9;
      v9 = 0;
    }
    if ( a3 )
    {
      *a3 = ReferencedDomainName;
      ReferencedDomainName = 0;
    }
    LastError = 0;
    if ( !v9 )
      goto LABEL_34;
    goto LABEL_33;
  }
  v13 = -1;
  do
    ++v13;
  while ( ReferencedDomainName[v13] );
  v14 = -1;
  do
    ++v14;
  while ( v9[v14] );
  v15 = v13 + v14 + 2;
  v16 = 2 * v15;
  if ( !is_mul_ok(v15, 2u) )
    v16 = -1;
  v17 = (unsigned __int16 *)operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
  *a4 = v17;
  if ( v17 )
  {
    LastError = StringCchPrintfW(v17, v15, L"%s\\%s", ReferencedDomainName, v9);
    if ( LastError < 0 )
    {
      if ( *a4 )
      {
        operator delete(*a4);
        *a4 = 0;
      }
      if ( (LastError & 0x1FFF0000) == 0x70000 )
        LastError = (unsigned __int16)LastError;
      goto LABEL_33;
    }
    goto LABEL_28;
  }
LABEL_12:
  LastError = 8;
LABEL_33:
  operator delete(v9);
LABEL_34:
  if ( ReferencedDomainName )
    operator delete(ReferencedDomainName);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800137b0  mov     r11, rsp
0x1800137b3  mov     [r11+8], rbx
0x1800137b7  mov     [r11+10h], rsi
0x1800137bb  mov     [r11+18h], rdi
0x1800137bf  push    rbp
0x1800137c0  push    r12
0x1800137c2  push    r13
0x1800137c4  push    r14
0x1800137c6  push    r15
0x1800137c8  mov     rbp, rsp
0x1800137cb  sub     rsp, 60h
0x1800137cf  xor     r13d, r13d
0x1800137d2  lea     rax, [rbp+var_18]
0x1800137d6  mov     [r11-58h], rax
0x1800137da  mov     r15, rdx
0x1800137dd  lea     rax, [rbp+var_20]
0x1800137e1  mov     [rbp+cchName], r13d
0x1800137e5  mov     r14, r9
0x1800137e8  mov     [r11-60h], rax
0x1800137ec  mov     r12, r8
0x1800137ef  mov     [r11-68h], r13
0x1800137f3  mov     rbx, rcx
0x1800137f6  mov     [rbp+var_20], r13d
0x1800137fa  mov     rdx, rcx; Sid
0x1800137fd  mov     [rbp+var_18], r13d
0x180013801  lea     r9, [rbp+cchName]; cchName
0x180013805  xor     r8d, r8d; Name
0x180013808  xor     ecx, ecx; lpSystemName
0x18001380a  call    cs:__imp_LookupAccountSidW
0x180013811  nop     dword ptr [rax+rax+00h]
0x180013816  test    eax, eax
0x180013818  jnz     loc_1800139D3
0x18001381e  cmp     [rbp+cchName], r13d
0x180013822  jz      loc_1800139D3
0x180013828  cmp     [rbp+var_20], r13d
0x18001382c  jz      loc_1800139D3
0x180013832  call    cs:__imp_GetLastError
0x180013839  nop     dword ptr [rax+rax+00h]
0x18001383e  cmp     eax, 534h
0x180013843  jz      loc_1800139D3
0x180013849  mov     ecx, [rbp+cchName]
0x18001384c  lea     eax, [r13+2]
0x180013850  mul     rcx
0x180013853  lea     rdi, [r13-1]
0x180013857  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001385e  cmovo   rax, rdi
0x180013862  mov     rcx, rax; unsigned __int64
0x180013865  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001386a  mov     rsi, rax
0x18001386d  test    rax, rax
0x180013870  jnz     short loc_18001387A
0x180013872  lea     ebx, [rdi+9]
0x180013875  jmp     loc_1800139E1
0x18001387a  mov     ecx, [rbp+var_20]
0x18001387d  mov     eax, 2
0x180013882  mul     rcx
0x180013885  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001388c  cmovo   rax, rdi
0x180013890  mov     rcx, rax; unsigned __int64
0x180013893  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180013898  mov     rdi, rax
0x18001389b  test    rax, rax
0x18001389e  jnz     short loc_1800138AA
0x1800138a0  mov     ebx, 8
0x1800138a5  jmp     loc_1800139AE
0x1800138aa  lea     rax, [rbp+var_18]
0x1800138ae  mov     r8, rsi; Name
0x1800138b1  mov     [rsp+60h+peUse], rax; peUse
0x1800138b6  lea     r9, [rbp+cchName]; cchName
0x1800138ba  lea     rax, [rbp+var_20]
0x1800138be  mov     rdx, rbx; Sid
0x1800138c1  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800138c6  xor     ecx, ecx; lpSystemName
0x1800138c8  mov     [rsp+60h+ReferencedDomainName], rdi; ReferencedDomainName
0x1800138cd  call    cs:__imp_LookupAccountSidW
0x1800138d4  nop     dword ptr [rax+rax+00h]
0x1800138d9  test    eax, eax
0x1800138db  jnz     short loc_1800138F0
0x1800138dd  call    cs:__imp_GetLastError
0x1800138e4  nop     dword ptr [rax+rax+00h]
0x1800138e9  mov     ebx, eax
0x1800138eb  jmp     loc_1800139AE
0x1800138f0  test    r14, r14
0x1800138f3  jz      loc_18001398F
0x1800138f9  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800138fd  mov     r8, r9
0x180013900  inc     r8
0x180013903  cmp     [rdi+r8*2], r13w
0x180013908  jnz     short loc_180013900
0x18001390a  mov     rcx, r9
0x18001390d  inc     rcx
0x180013910  cmp     [rsi+rcx*2], r13w
0x180013915  jnz     short loc_18001390D
0x180013917  lea     rbx, [rcx+2]
0x18001391b  mov     eax, 2
0x180013920  add     rbx, r8
0x180013923  mul     rbx
0x180013926  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001392d  cmovo   rax, r9
0x180013931  mov     rcx, rax; unsigned __int64
0x180013934  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180013939  mov     [r14], rax
0x18001393c  test    rax, rax
0x18001393f  jz      loc_1800138A0
0x180013945  mov     r9, rdi
0x180013948  mov     [rsp+60h+ReferencedDomainName], rsi
0x18001394d  lea     r8, aSS; "%s\\%s"
0x180013954  mov     rdx, rbx; unsigned __int64
0x180013957  mov     rcx, rax; unsigned __int16 *
0x18001395a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001395f  mov     ebx, eax
0x180013961  test    eax, eax
0x180013963  jns     short loc_18001398F
0x180013965  mov     rcx, [r14]
0x180013968  test    rcx, rcx
0x18001396b  jz      short loc_18001397C
0x18001396d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013974  nop     dword ptr [rax+rax+00h]
0x180013979  mov     [r14], r13
0x18001397c  mov     eax, ebx
0x18001397e  and     eax, 1FFF0000h
0x180013983  cmp     eax, 70000h
0x180013988  jnz     short loc_1800139AE
0x18001398a  movzx   ebx, bx
0x18001398d  jmp     short loc_1800139AE
0x18001398f  test    r15, r15
0x180013992  jz      short loc_18001399A
0x180013994  mov     [r15], rsi
0x180013997  mov     rsi, r13
0x18001399a  test    r12, r12
0x18001399d  jz      short loc_1800139A6
0x18001399f  mov     [r12], rdi
0x1800139a3  mov     rdi, r13
0x1800139a6  mov     ebx, r13d
0x1800139a9  test    rsi, rsi
0x1800139ac  jz      short loc_1800139BD
0x1800139ae  mov     rcx, rsi
0x1800139b1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800139b8  nop     dword ptr [rax+rax+00h]
0x1800139bd  test    rdi, rdi
0x1800139c0  jz      short loc_1800139E1
0x1800139c2  mov     rcx, rdi
0x1800139c5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800139cc  nop     dword ptr [rax+rax+00h]
0x1800139d1  jmp     short loc_1800139E1
0x1800139d3  call    cs:__imp_GetLastError
0x1800139da  nop     dword ptr [rax+rax+00h]
0x1800139df  mov     ebx, eax
0x1800139e1  lea     r11, [rsp+60h+var_s0]
0x1800139e6  mov     eax, ebx
0x1800139e8  mov     rbx, [r11+30h]
0x1800139ec  mov     rsi, [r11+38h]
0x1800139f0  mov     rdi, [r11+40h]
0x1800139f4  mov     rsp, r11
0x1800139f7  pop     r15
0x1800139f9  pop     r14
0x1800139fb  pop     r13
0x1800139fd  pop     r12
0x1800139ff  pop     rbp
0x180013a00  retn
```

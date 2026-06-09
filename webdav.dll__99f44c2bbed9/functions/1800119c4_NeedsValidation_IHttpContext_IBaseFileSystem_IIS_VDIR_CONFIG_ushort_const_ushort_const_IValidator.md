# NeedsValidation(IHttpContext *,IBaseFileSystem *,IIS_VDIR_CONFIG *,ushort const *,ushort const *,IValidator * *)

- ea: `0x1800119c4`
- end: `0x180011aca`
- name: `?NeedsValidation@@YAJPEAVIHttpContext@@PEAVIBaseFileSystem@@PEAVIIS_VDIR_CONFIG@@PEBG3PEAPEAVIValidator@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct IBaseFileSystem *, struct IIS_VDIR_CONFIG *, const unsigned __int16 *, const unsigned __int16 *, struct IValidator **)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002fbc`
- `0x18000dfb4`
- `0x18000f640`

## callees

- `0x1800011d4`
- `0x180011514`
- `0x1800119c4`
- `0x180023010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180011a1e`
- `msvcrt!_wcsicmp` at `0x180011a1e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011a50`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011a5a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011a67`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011a50`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011a5a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011a67`

## string_xrefs

- `0x180011a13`: `\web.config`

## pseudocode

```c
__int64 __fastcall NeedsValidation(
        struct IHttpContext *a1,
        struct IBaseFileSystem *a2,
        struct IIS_VDIR_CONFIG *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        struct IValidator **a6)
{
  unsigned __int64 v10; // rax
  _QWORD *v11; // rbx
  int v12; // edi

  v10 = -1;
  *a6 = 0;
  do
    ++v10;
  while ( a5[v10] );
  if ( v10 < 0xB || _wcsicmp(&a5[v10 - 11], L"\\web.config") )
    return 0;
  v11 = operator new(0xE0u);
  if ( v11 )
  {
    *v11 = &DAV_WEB_CONFIG_VALIDATOR::`vftable';
    STRU::STRU((STRU *)(v11 + 6));
    STRU::STRU((STRU *)(v11 + 13));
    STRU::STRU((STRU *)(v11 + 20));
    v11[1] = a1;
    v11[2] = a2;
    v11[3] = a3;
    v11[4] = a4;
    v11[5] = a5;
    *((_DWORD *)v11 + 54) = 0;
    v12 = DAV_WEB_CONFIG_VALIDATOR::Initialize((DAV_WEB_CONFIG_VALIDATOR *)v11);
    if ( v12 < 0 )
    {
      (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
      return (unsigned int)v12;
    }
    *a6 = (struct IValidator *)v11;
    return 0;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x1800119c4  push    rbx
0x1800119c6  push    rbp
0x1800119c7  push    rsi
0x1800119c8  push    rdi
0x1800119c9  push    r12
0x1800119cb  push    r13
0x1800119cd  push    r14
0x1800119cf  push    r15
0x1800119d1  sub     rsp, 28h
0x1800119d5  mov     rsi, [rsp+68h+arg_28]
0x1800119dd  xor     r13d, r13d
0x1800119e0  mov     rdi, [rsp+68h+arg_20]
0x1800119e8  mov     rbp, r9
0x1800119eb  mov     r14, r8
0x1800119ee  mov     r15, rdx
0x1800119f1  mov     r12, rcx
0x1800119f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800119f8  mov     [rsi], r13
0x1800119fb  inc     rax
0x1800119fe  cmp     [rdi+rax*2], r13w
0x180011a03  jnz     short loc_1800119FB
0x180011a05  cmp     rax, 0Bh
0x180011a09  jb      loc_180011AB0
0x180011a0f  add     rax, 0FFFFFFFFFFFFFFF5h
0x180011a13  lea     rdx, aWebConfig; "\\web.config"
0x180011a1a  lea     rcx, [rdi+rax*2]; String1
0x180011a1e  call    cs:__imp__wcsicmp
0x180011a24  test    eax, eax
0x180011a26  jnz     loc_180011AB0
0x180011a2c  mov     ecx, 0E0h; Size
0x180011a31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011a36  mov     rbx, rax
0x180011a39  test    rax, rax
0x180011a3c  jz      loc_180011AC3
0x180011a42  lea     rax, ??_7DAV_WEB_CONFIG_VALIDATOR@@6B@; const DAV_WEB_CONFIG_VALIDATOR::`vftable'
0x180011a49  lea     rcx, [rbx+30h]
0x180011a4d  mov     [rbx], rax
0x180011a50  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180011a56  lea     rcx, [rbx+68h]
0x180011a5a  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180011a60  lea     rcx, [rbx+0A0h]
0x180011a67  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180011a6d  mov     rcx, rbx; this
0x180011a70  mov     [rbx+8], r12
0x180011a74  mov     [rbx+10h], r15
0x180011a78  mov     [rbx+18h], r14
0x180011a7c  mov     [rbx+20h], rbp
0x180011a80  mov     [rbx+28h], rdi
0x180011a84  mov     [rbx+0D8h], r13d
0x180011a8b  call    ?Initialize@DAV_WEB_CONFIG_VALIDATOR@@QEAAJXZ; DAV_WEB_CONFIG_VALIDATOR::Initialize(void)
0x180011a90  mov     edi, eax
0x180011a92  test    eax, eax
0x180011a94  jns     short loc_180011AAD
0x180011a96  mov     rcx, [rbx]
0x180011a99  mov     edx, 1
0x180011a9e  mov     rax, [rcx]
0x180011aa1  mov     rcx, rbx
0x180011aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011aa9  mov     eax, edi
0x180011aab  jmp     short loc_180011AB2
0x180011aad  mov     [rsi], rbx
0x180011ab0  xor     eax, eax
0x180011ab2  add     rsp, 28h
0x180011ab6  pop     r15
0x180011ab8  pop     r14
0x180011aba  pop     r13
0x180011abc  pop     r12
0x180011abe  pop     rdi
0x180011abf  pop     rsi
0x180011ac0  pop     rbp
0x180011ac1  pop     rbx
0x180011ac2  retn
0x180011ac3  mov     eax, 80070008h
0x180011ac8  jmp     short loc_180011AB2
```

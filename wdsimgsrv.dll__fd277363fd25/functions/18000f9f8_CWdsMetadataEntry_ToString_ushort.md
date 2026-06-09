# CWdsMetadataEntry::ToString(ushort * *)

- ea: `0x18000f9f8`
- end: `0x18000fb37`
- name: `?ToString@CWdsMetadataEntry@@QEBAKPEAPEAG@Z`
- size: `319`
- prototype: `unsigned int __fastcall(CWdsMetadataEntry *__hidden this, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800096e8`
- `0x18000d2ac`
- `0x1800139a8`
- `0x180014f60`

## callees

- `0x1800016b8`
- `0x18000ab00`
- `0x18000f9f8`
- `0x18000fc04`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000fb08`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000fb08`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000faf7`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000faf7`

## pseudocode

```c
__int64 __fastcall CWdsMetadataEntry::ToString(CWdsMetadataEntry *this, unsigned __int16 **a2)
{
  unsigned int v2; // ebx
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  unsigned __int64 v10; // rbp
  unsigned __int64 v11; // rax
  unsigned __int16 *v12; // rsi
  __int64 v13; // r9
  const unsigned __int16 *v14; // r8
  const WCHAR *v15; // rcx
  const wchar_t *v16; // rax
  __int64 v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // r8

  v2 = 0;
  v4 = *(_QWORD *)this;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(v4 + 2 * v5) );
  v7 = *((_QWORD *)this + 2);
  if ( v7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v7 + 2 * v8) );
    v5 += v8 + 2;
  }
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(*((_QWORD *)this + 1) + 2 * v9) );
  v10 = v5 + v9 + 2;
  v11 = 2 * v10;
  if ( !is_mul_ok(v10, 2u) )
    v11 = -1;
  v12 = (unsigned __int16 *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
  if ( v12 )
  {
    v13 = *((_QWORD *)this + 2);
    v14 = L"]";
    v15 = &pszSrch;
    v16 = L"[";
    if ( v13 )
      v15 = (const WCHAR *)*((_QWORD *)this + 2);
    else
      v14 = &pszSrch;
    if ( !v13 )
      v16 = &pszSrch;
    v17 = (unsigned int)StringCchPrintfW(
                          v12,
                          v10,
                          L"%s%s%s%s=%s",
                          *(_QWORD *)this,
                          v16,
                          v15,
                          v14,
                          *((_QWORD *)this + 1));
    if ( (int)ElValidateHr_2(v17, v18, v19, 2545) >= 0 )
    {
      *a2 = v12;
    }
    else
    {
      v2 = WIN32_FROM_HRESULT(v17);
      operator delete(v12);
    }
  }
  else
  {
    return 8;
  }
  return v2;
}

```

## disassembly

```asm
0x18000f9f8  mov     rax, rsp
0x18000f9fb  mov     [rax+8], rbx
0x18000f9ff  mov     [rax+10h], rbp
0x18000fa03  mov     [rax+18h], rsi
0x18000fa07  mov     [rax+20h], rdi
0x18000fa0b  push    r14
0x18000fa0d  sub     rsp, 40h
0x18000fa11  xor     ebx, ebx
0x18000fa13  mov     rdi, rcx
0x18000fa16  mov     rcx, [rcx]
0x18000fa19  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000fa1d  mov     rax, r8
0x18000fa20  mov     r14, rdx
0x18000fa23  inc     rax
0x18000fa26  cmp     [rcx+rax*2], bx
0x18000fa2a  jnz     short loc_18000FA23
0x18000fa2c  mov     rdx, [rdi+10h]
0x18000fa30  test    rdx, rdx
0x18000fa33  jz      short loc_18000FA48
0x18000fa35  mov     rcx, r8
0x18000fa38  inc     rcx
0x18000fa3b  cmp     [rdx+rcx*2], bx
0x18000fa3f  jnz     short loc_18000FA38
0x18000fa41  add     rax, 2
0x18000fa45  add     rax, rcx
0x18000fa48  mov     rdx, [rdi+8]
0x18000fa4c  mov     rcx, r8
0x18000fa4f  inc     rcx
0x18000fa52  cmp     [rdx+rcx*2], bx
0x18000fa56  jnz     short loc_18000FA4F
0x18000fa58  lea     rbp, [rcx+2]
0x18000fa5c  add     rbp, rax
0x18000fa5f  mov     eax, 2
0x18000fa64  mul     rbp
0x18000fa67  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fa6e  cmovo   rax, r8
0x18000fa72  mov     rcx, rax; unsigned __int64
0x18000fa75  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000fa7a  mov     rsi, rax
0x18000fa7d  test    rax, rax
0x18000fa80  jnz     short loc_18000FA8A
0x18000fa82  lea     ebx, [rax+8]
0x18000fa85  jmp     loc_18000FB19
0x18000fa8a  mov     r9, [rdi+10h]
0x18000fa8e  lea     rdx, pszSrch
0x18000fa95  mov     r10, [rdi+8]
0x18000fa99  lea     r8, asc_18001D614; "]"
0x18000faa0  test    r9, r9
0x18000faa3  mov     [rsp+48h+var_10], r10
0x18000faa8  mov     rcx, rdx
0x18000faab  lea     rax, asc_18001D618; "["
0x18000fab2  cmovz   r8, rdx
0x18000fab6  cmovnz  rcx, r9
0x18000faba  mov     r9, [rdi]
0x18000fabd  cmovz   rax, rdx
0x18000fac1  mov     [rsp+48h+var_18], r8
0x18000fac6  mov     rdx, rbp; unsigned __int64
0x18000fac9  mov     [rsp+48h+var_20], rcx
0x18000face  lea     r8, aSSSSS; "%s%s%s%s=%s"
0x18000fad5  mov     rcx, rsi; unsigned __int16 *
0x18000fad8  mov     [rsp+48h+var_28], rax
0x18000fadd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fae2  mov     r9d, 9F1h
0x18000fae8  mov     ecx, eax
0x18000faea  mov     edi, eax
0x18000faec  call    ElValidateHr_2
0x18000faf1  test    eax, eax
0x18000faf3  jns     short loc_18000FB16
0x18000faf5  mov     ecx, edi
0x18000faf7  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000fafe  nop     dword ptr [rax+rax+00h]
0x18000fb03  mov     rcx, rsi
0x18000fb06  mov     ebx, eax
0x18000fb08  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000fb0f  nop     dword ptr [rax+rax+00h]
0x18000fb14  jmp     short loc_18000FB19
0x18000fb16  mov     [r14], rsi
0x18000fb19  mov     rbp, [rsp+48h+arg_8]
0x18000fb1e  mov     eax, ebx
0x18000fb20  mov     rbx, [rsp+48h+arg_0]
0x18000fb25  mov     rsi, [rsp+48h+arg_10]
0x18000fb2a  mov     rdi, [rsp+48h+arg_18]
0x18000fb2f  add     rsp, 40h
0x18000fb33  pop     r14
0x18000fb35  retn
```

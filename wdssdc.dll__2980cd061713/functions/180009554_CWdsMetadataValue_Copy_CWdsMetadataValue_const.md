# CWdsMetadataValue::Copy(CWdsMetadataValue const *)

- ea: `0x180009554`
- end: `0x18000963a`
- name: `?Copy@CWdsMetadataValue@@QEAAKPEBV1@@Z`
- size: `230`
- prototype: `unsigned int __fastcall(CWdsMetadataValue *__hidden this, const struct CWdsMetadataValue *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b6d4`

## callees

- `0x1800015d4`
- `0x180001934`
- `0x180009554`
- `0x18000bec0`
- `0x18000c274`
- `0x18000cc10`

## import_xrefs

- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180009592`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180009592`

## pseudocode

```c
__int64 __fastcall CWdsMetadataValue::Copy(CWdsMetadataValue *this, const struct CWdsMetadataValue *a2)
{
  unsigned int v2; // esi
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  void *v8; // rax
  void *v9; // rbp
  void *Block; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  Block = 0;
  if ( this != a2 )
  {
    CWdsMetadataValue::Shutdown(this);
    v5 = *(_DWORD *)a2;
    if ( *(_DWORD *)a2 == 1 )
    {
      v2 = DuplicateStringW(*((const unsigned __int16 **)a2 + 1), (unsigned __int16 **)&Block);
      if ( !(unsigned int)ElValidateWin32_1(v2, v6, v7, 1461) )
      {
        *((_QWORD *)this + 1) = Block;
        *(_DWORD *)this = 1;
        return v2;
      }
    }
    else if ( v5 == 7 )
    {
      v8 = operator new[](*((_QWORD *)a2 + 2), (const struct std::nothrow_t *)&std::nothrow);
      v9 = v8;
      if ( v8 )
      {
        memcpy_0(v8, *((const void **)a2 + 1), *((_QWORD *)a2 + 2));
        *(_DWORD *)this = 7;
        *((_QWORD *)this + 1) = v9;
        *((_QWORD *)this + 2) = *((_QWORD *)a2 + 2);
      }
      else
      {
        v2 = 8;
      }
    }
    else
    {
      *(_DWORD *)this = v5;
      *(_OWORD *)((char *)this + 8) = *(_OWORD *)((char *)a2 + 8);
    }
    if ( Block )
      operator delete(Block);
  }
  return v2;
}

```

## disassembly

```asm
0x180009554  mov     rax, rsp
0x180009557  mov     [rax+10h], rbx
0x18000955b  mov     [rax+18h], rbp
0x18000955f  mov     [rax+20h], rsi
0x180009563  push    rdi
0x180009564  sub     rsp, 20h
0x180009568  xor     esi, esi
0x18000956a  mov     rdi, rdx
0x18000956d  mov     [rax+8], rsi
0x180009571  mov     rbx, rcx
0x180009574  cmp     rcx, rdx
0x180009577  jz      loc_180009622
0x18000957d  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x180009582  mov     eax, [rdi]
0x180009584  cmp     eax, 1
0x180009587  jnz     short loc_1800095C2
0x180009589  mov     rcx, [rdi+8]
0x18000958d  lea     rdx, [rsp+28h+Block]
0x180009592  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180009599  nop     dword ptr [rax+rax+00h]
0x18000959e  mov     ecx, eax
0x1800095a0  mov     r9d, 5B5h
0x1800095a6  mov     esi, eax
0x1800095a8  call    ElValidateWin32_1
0x1800095ad  test    eax, eax
0x1800095af  jnz     short loc_180009613
0x1800095b1  mov     rcx, [rsp+28h+Block]
0x1800095b6  mov     [rbx+8], rcx
0x1800095ba  mov     dword ptr [rbx], 1
0x1800095c0  jmp     short loc_180009622
0x1800095c2  cmp     eax, 7
0x1800095c5  jnz     short loc_180009608
0x1800095c7  mov     rcx, [rdi+10h]; unsigned __int64
0x1800095cb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800095d2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800095d7  mov     rbp, rax
0x1800095da  test    rax, rax
0x1800095dd  jnz     short loc_1800095E4
0x1800095df  lea     esi, [rax+8]
0x1800095e2  jmp     short loc_180009613
0x1800095e4  mov     r8, [rdi+10h]; Size
0x1800095e8  mov     rcx, rbp; void *
0x1800095eb  mov     rdx, [rdi+8]; Src
0x1800095ef  call    memcpy_0
0x1800095f4  mov     dword ptr [rbx], 7
0x1800095fa  mov     [rbx+8], rbp
0x1800095fe  mov     rax, [rdi+10h]
0x180009602  mov     [rbx+10h], rax
0x180009606  jmp     short loc_180009613
0x180009608  mov     [rbx], eax
0x18000960a  movups  xmm0, xmmword ptr [rdi+8]
0x18000960e  movdqu  xmmword ptr [rbx+8], xmm0
0x180009613  mov     rcx, [rsp+28h+Block]; Block
0x180009618  test    rcx, rcx
0x18000961b  jz      short loc_180009622
0x18000961d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009622  mov     rbx, [rsp+28h+arg_8]
0x180009627  mov     eax, esi
0x180009629  mov     rsi, [rsp+28h+arg_18]
0x18000962e  mov     rbp, [rsp+28h+arg_10]
0x180009633  add     rsp, 20h
0x180009637  pop     rdi
0x180009638  retn
```

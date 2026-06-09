# NCoreLibrary::TMultiString::Update(ushort const *)

- ea: `0x180016800`
- end: `0x1800168a0`
- name: `?Update@TMultiString@NCoreLibrary@@QEAAJPEBG@Z`
- size: `160`
- prototype: `int(NCoreLibrary::TMultiString *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180015aa4`

## callees

- `0x1800065c0`
- `0x1800167c4`
- `0x180016800`
- `0x1800168a8`
- `0x180016a3c`

## pseudocode

```c
__int64 __fastcall NCoreLibrary::TMultiString::Update(void **this, NCoreLibrary *a2)
{
  unsigned __int64 v4; // r14
  unsigned __int64 v5; // rax
  void *v6; // rax
  NCoreLibrary::TMultiString *v7; // rcx
  void *v8; // rbp
  unsigned int v9; // edi
  NCoreLibrary::TMultiString *v10; // rcx

  if ( a2 )
  {
    v4 = NCoreLibrary::MultiSzSize(a2, (const unsigned __int16 *)a2);
    v5 = 2 * v4;
    if ( !is_mul_ok(v4, 2u) )
      v5 = -1;
    v6 = operator new[](v5, (const struct std::nothrow_t *)NCoreLibrary::nothrow);
    v8 = v6;
    if ( v6 )
    {
      v9 = 0;
      memcpy_0(v6, a2, 2 * v4);
      NCoreLibrary::TMultiString::vFree(v10, this[1]);
      this[1] = v8;
    }
    else
    {
      v9 = -2147024882;
    }
    NCoreLibrary::TMultiString::vFree(v7, 0);
  }
  else
  {
    v9 = 0;
    NCoreLibrary::TMultiString::vFree((NCoreLibrary::TMultiString *)this, this[1]);
    *((_DWORD *)this + 4) = 0;
    this[1] = &NCoreLibrary::TMultiString::gszzEmpty;
  }
  return v9;
}

```

## disassembly

```asm
0x180016800  push    rbx
0x180016802  push    rbp
0x180016803  push    rsi
0x180016804  push    rdi
0x180016805  push    r14
0x180016807  sub     rsp, 20h
0x18001680b  mov     rsi, rdx
0x18001680e  mov     rbx, rcx
0x180016811  test    rdx, rdx
0x180016814  jz      short loc_180016879
0x180016816  mov     rcx, rdx; this
0x180016819  call    ?MultiSzSize@NCoreLibrary@@YAIPEBG@Z; NCoreLibrary::MultiSzSize(ushort const *)
0x18001681e  mov     r14d, eax
0x180016821  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180016828  mov     eax, 2
0x18001682d  mul     r14
0x180016830  lea     rdx, ?nothrow@NCoreLibrary@@3Unothrow_t@std@@B; struct std::nothrow_t *
0x180016837  cmovb   rax, rcx
0x18001683b  mov     rcx, rax; unsigned __int64
0x18001683e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180016843  mov     rbp, rax
0x180016846  test    rax, rax
0x180016849  jz      short loc_18001686B
0x18001684b  lea     r8, [r14+r14]; Size
0x18001684f  mov     rdx, rsi; Src
0x180016852  mov     rcx, rax; void *
0x180016855  xor     edi, edi
0x180016857  call    memcpy_0
0x18001685c  mov     rdx, [rbx+8]; void *
0x180016860  call    ?vFree@TMultiString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TMultiString::vFree(void *)
0x180016865  mov     [rbx+8], rbp
0x180016869  jmp     short loc_180016870
0x18001686b  mov     edi, 8007000Eh
0x180016870  xor     edx, edx; void *
0x180016872  call    ?vFree@TMultiString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TMultiString::vFree(void *)
0x180016877  jmp     short loc_180016892
0x180016879  mov     rdx, [rcx+8]; void *
0x18001687d  xor     edi, edi
0x18001687f  call    ?vFree@TMultiString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TMultiString::vFree(void *)
0x180016884  lea     rax, ?gszzEmpty@TMultiString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TMultiString::gszzEmpty
0x18001688b  mov     [rbx+10h], edi
0x18001688e  mov     [rbx+8], rax
0x180016892  mov     eax, edi
0x180016894  add     rsp, 20h
0x180016898  pop     r14
0x18001689a  pop     rdi
0x18001689b  pop     rsi
0x18001689c  pop     rbp
0x18001689d  pop     rbx
0x18001689e  retn
```

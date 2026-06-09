# NCoreLibrary::TMultiString::Update(ushort const *)

- ea: `0x180014df8`
- end: `0x180014e97`
- name: `?Update@TMultiString@NCoreLibrary@@QEAAJPEBG@Z`
- size: `159`
- prototype: `int(NCoreLibrary::TMultiString *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800141a4`

## callees

- `0x180006250`
- `0x180014dbc`
- `0x180014df8`
- `0x180014ea0`
- `0x18001503c`

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
0x180014df8  push    rbx
0x180014dfa  push    rbp
0x180014dfb  push    rsi
0x180014dfc  push    rdi
0x180014dfd  push    r14
0x180014dff  sub     rsp, 20h
0x180014e03  mov     rsi, rdx
0x180014e06  mov     rbx, rcx
0x180014e09  test    rdx, rdx
0x180014e0c  jz      short loc_180014E71
0x180014e0e  mov     rcx, rdx; this
0x180014e11  call    ?MultiSzSize@NCoreLibrary@@YAIPEBG@Z; NCoreLibrary::MultiSzSize(ushort const *)
0x180014e16  mov     r14d, eax
0x180014e19  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180014e20  mov     eax, 2
0x180014e25  mul     r14
0x180014e28  lea     rdx, ?nothrow@NCoreLibrary@@3Unothrow_t@std@@B; struct std::nothrow_t *
0x180014e2f  cmovb   rax, rcx
0x180014e33  mov     rcx, rax; unsigned __int64
0x180014e36  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180014e3b  mov     rbp, rax
0x180014e3e  test    rax, rax
0x180014e41  jz      short loc_180014E63
0x180014e43  lea     r8, [r14+r14]; Size
0x180014e47  mov     rdx, rsi; Src
0x180014e4a  mov     rcx, rax; void *
0x180014e4d  xor     edi, edi
0x180014e4f  call    memcpy_0
0x180014e54  mov     rdx, [rbx+8]; void *
0x180014e58  call    ?vFree@TMultiString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TMultiString::vFree(void *)
0x180014e5d  mov     [rbx+8], rbp
0x180014e61  jmp     short loc_180014E68
0x180014e63  mov     edi, 8007000Eh
0x180014e68  xor     edx, edx; void *
0x180014e6a  call    ?vFree@TMultiString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TMultiString::vFree(void *)
0x180014e6f  jmp     short loc_180014E8A
0x180014e71  mov     rdx, [rcx+8]; void *
0x180014e75  xor     edi, edi
0x180014e77  call    ?vFree@TMultiString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TMultiString::vFree(void *)
0x180014e7c  lea     rax, ?gszzEmpty@TMultiString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TMultiString::gszzEmpty
0x180014e83  mov     [rbx+10h], edi
0x180014e86  mov     [rbx+8], rax
0x180014e8a  mov     eax, edi
0x180014e8c  add     rsp, 20h
0x180014e90  pop     r14
0x180014e92  pop     rdi
0x180014e93  pop     rsi
0x180014e94  pop     rbp
0x180014e95  pop     rbx
0x180014e96  retn
```

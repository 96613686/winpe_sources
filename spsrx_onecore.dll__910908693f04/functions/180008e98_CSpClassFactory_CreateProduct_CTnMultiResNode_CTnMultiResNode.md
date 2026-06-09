# CSpClassFactory::CreateProduct<CTnMultiResNode>(CTnMultiResNode * *)

- ea: `0x180008e98`
- end: `0x180008f26`
- name: `??$CreateProduct@VCTnMultiResNode@@@CSpClassFactory@@QEAAJPEAPEAVCTnMultiResNode@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(CSpClassFactory *this)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180009930`
- `0x18000a14c`
- `0x18000a298`
- `0x18000a4c8`
- `0x18000afe0`
- `0x18000d1c0`

## callees

- `0x180002ecc`
- `0x180008e98`
- `0x18000906c`
- `0x180009e70`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CSpClassFactory::CreateProduct<CTnMultiResNode>(
        CSpClassFactory *this,
        struct CSpClassFactoryProduct **a2)
{
  CTnMultiResNode *v5; // rax
  struct CSpClassFactoryProduct *v6; // rax
  struct CSpClassFactoryProduct *v7; // rbx
  int v8; // edi

  if ( !a2 )
    return 2147942487LL;
  v5 = (CTnMultiResNode *)operator new[](0x100u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v5 || (v6 = CTnMultiResNode::CTnMultiResNode(v5), *a2 = v6, (v7 = v6) == 0) )
  {
    v8 = -2147024882;
    goto LABEL_8;
  }
  v8 = CSpClassFactory::AttachProduct(this, v6);
  if ( v8 < 0 )
  {
    (**(void (__fastcall ***)(struct CSpClassFactoryProduct *, __int64))v7)(v7, 1);
LABEL_8:
    *a2 = 0;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180008e98  mov     [rsp+arg_0], rbx
0x180008e9d  mov     [rsp+arg_8], rsi
0x180008ea2  push    rdi
0x180008ea3  sub     rsp, 20h
0x180008ea7  mov     rsi, rdx
0x180008eaa  mov     rdi, rcx
0x180008ead  test    rdx, rdx
0x180008eb0  jnz     short loc_180008EB9
0x180008eb2  mov     eax, 80070057h
0x180008eb7  jmp     short loc_180008F16
0x180008eb9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008ec0  mov     ecx, 100h; unsigned __int64
0x180008ec5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008eca  test    rax, rax
0x180008ecd  jz      short loc_180008F08
0x180008ecf  mov     rcx, rax; this
0x180008ed2  call    ??0CTnMultiResNode@@QEAA@XZ; CTnMultiResNode::CTnMultiResNode(void)
0x180008ed7  mov     [rsi], rax
0x180008eda  mov     rbx, rax
0x180008edd  test    rax, rax
0x180008ee0  jz      short loc_180008F08
0x180008ee2  mov     rdx, rax; struct CSpClassFactoryProduct *
0x180008ee5  mov     rcx, rdi; this
0x180008ee8  call    ?AttachProduct@CSpClassFactory@@IEAAJPEAVCSpClassFactoryProduct@@@Z; CSpClassFactory::AttachProduct(CSpClassFactoryProduct *)
0x180008eed  mov     edi, eax
0x180008eef  test    eax, eax
0x180008ef1  jns     short loc_180008F14
0x180008ef3  mov     rcx, [rbx]
0x180008ef6  mov     edx, 1
0x180008efb  mov     rax, [rcx]
0x180008efe  mov     rcx, rbx
0x180008f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f06  jmp     short loc_180008F0D
0x180008f08  mov     edi, 8007000Eh
0x180008f0d  mov     qword ptr [rsi], 0
0x180008f14  mov     eax, edi
0x180008f16  mov     rbx, [rsp+28h+arg_0]
0x180008f1b  mov     rsi, [rsp+28h+arg_8]
0x180008f20  add     rsp, 20h
0x180008f24  pop     rdi
0x180008f25  retn
```

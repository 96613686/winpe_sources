# CSpClassFactory::CreateProduct<CTnMultiResCursor>(CTnMultiResCursor * *)

- ea: `0x180008da8`
- end: `0x180008e8f`
- name: `??$CreateProduct@VCTnMultiResCursor@@@CSpClassFactory@@QEAAJPEAPEAVCTnMultiResCursor@@@Z`
- size: `231`
- prototype: `__int64 __fastcall(CSpClassFactory *this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a614`
- `0x18000acb0`

## callees

- `0x180002ecc`
- `0x180008da8`
- `0x180009e70`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CSpClassFactory::CreateProduct<CTnMultiResCursor>(CSpClassFactory *this, _QWORD *a2)
{
  void (__fastcall ***v5)(_QWORD, __int64); // rax
  void (__fastcall ***v6)(_QWORD, __int64); // rbx
  int v7; // esi

  if ( !a2 )
    return 2147942487LL;
  v5 = (void (__fastcall ***)(_QWORD, __int64))operator new[](0x60u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( !v5 )
  {
    v7 = -2147024882;
    goto LABEL_7;
  }
  v5[1] = 0;
  v5[2] = 0;
  v5[3] = 0;
  *v5 = (void (__fastcall **)(_QWORD, __int64))&CTnMultiResCursor::`vftable';
  v5[4] = 0;
  *((_DWORD *)v5 + 10) = 0;
  *((_DWORD *)v5 + 16) = 0;
  v5[9] = 0;
  v5[7] = 0;
  v5[6] = 0;
  v5[10] = 0;
  *((_DWORD *)v5 + 22) = 10;
  *a2 = v5;
  v7 = CSpClassFactory::AttachProduct(this, (struct CSpClassFactoryProduct *)v5);
  if ( v7 < 0 )
  {
    (**v6)(v6, 1);
LABEL_7:
    *a2 = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008da8  mov     [rsp+arg_0], rbx
0x180008dad  mov     [rsp+arg_8], rsi
0x180008db2  push    rdi
0x180008db3  sub     rsp, 20h
0x180008db7  mov     rdi, rdx
0x180008dba  mov     rsi, rcx
0x180008dbd  test    rdx, rdx
0x180008dc0  jnz     short loc_180008DCC
0x180008dc2  mov     eax, 80070057h
0x180008dc7  jmp     loc_180008E7F
0x180008dcc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008dd3  mov     ecx, 60h ; '`'; unsigned __int64
0x180008dd8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008ddd  mov     rbx, rax
0x180008de0  test    rax, rax
0x180008de3  jz      loc_180008E71
0x180008de9  mov     qword ptr [rax+8], 0
0x180008df1  mov     rdx, rbx; struct CSpClassFactoryProduct *
0x180008df4  mov     qword ptr [rax+10h], 0
0x180008dfc  mov     rcx, rsi; this
0x180008dff  lea     rax, ??_7CTnMultiResCursor@@6B@; const CTnMultiResCursor::`vftable'
0x180008e06  mov     qword ptr [rbx+18h], 0
0x180008e0e  mov     [rbx], rax
0x180008e11  mov     qword ptr [rbx+20h], 0
0x180008e19  mov     dword ptr [rbx+28h], 0
0x180008e20  mov     dword ptr [rbx+40h], 0
0x180008e27  mov     qword ptr [rbx+48h], 0
0x180008e2f  mov     qword ptr [rbx+38h], 0
0x180008e37  mov     qword ptr [rbx+30h], 0
0x180008e3f  mov     qword ptr [rbx+50h], 0
0x180008e47  mov     dword ptr [rbx+58h], 0Ah
0x180008e4e  mov     [rdi], rbx
0x180008e51  call    ?AttachProduct@CSpClassFactory@@IEAAJPEAVCSpClassFactoryProduct@@@Z; CSpClassFactory::AttachProduct(CSpClassFactoryProduct *)
0x180008e56  mov     esi, eax
0x180008e58  test    eax, eax
0x180008e5a  jns     short loc_180008E7D
0x180008e5c  mov     rcx, [rbx]
0x180008e5f  mov     edx, 1
0x180008e64  mov     rax, [rcx]
0x180008e67  mov     rcx, rbx
0x180008e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e6f  jmp     short loc_180008E76
0x180008e71  mov     esi, 8007000Eh
0x180008e76  mov     qword ptr [rdi], 0
0x180008e7d  mov     eax, esi
0x180008e7f  mov     rbx, [rsp+28h+arg_0]
0x180008e84  mov     rsi, [rsp+28h+arg_8]
0x180008e89  add     rsp, 20h
0x180008e8d  pop     rdi
0x180008e8e  retn
```

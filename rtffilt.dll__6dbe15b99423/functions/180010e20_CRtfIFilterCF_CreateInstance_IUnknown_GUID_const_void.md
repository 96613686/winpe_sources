# CRtfIFilterCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180010e20`
- end: `0x180010f20`
- name: `?CreateInstance@CRtfIFilterCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `256`
- prototype: `__int64 __fastcall(CRtfIFilterCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001ed4`
- `0x180010e20`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall CRtfIFilterCF::CreateInstance(
        CRtfIFilterCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  unsigned int v8; // edi

  *a4 = 0;
  v6 = operator new(0xE0u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    *v6 = &CRtfIFilter::`vftable'{for `IPixelFilter'};
    v6[1] = &CRtfIFilter::`vftable'{for `IPersistFile'};
    v6[2] = &CRtfIFilter::`vftable'{for `IPersistStream'};
    v6[3] = 0;
    *((_DWORD *)v6 + 11) = 1;
    *((_DWORD *)v6 + 12) = 1;
    v6[7] = 0;
    *((_DWORD *)v6 + 16) = 1;
    v6[9] = 0;
    v6[10] = 0;
    v6[11] = 0;
    v6[12] = 0;
    *((_DWORD *)v6 + 26) = 1;
    v6[14] = 0;
    v6[15] = 0;
    v6[19] = 0;
    v6[20] = 0;
    v6[21] = 0;
    v6[22] = 0;
    v6[24] = 0;
    v6[25] = 0;
    v6[26] = 0;
    v6[27] = 0;
    _InterlockedAdd(&g_cInstances, 1u);
    v8 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v6)(v6, a3, a4);
    (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v8;
}

```

## disassembly

```asm
0x180010e20  push    rbx
0x180010e22  push    rbp
0x180010e23  push    rsi
0x180010e24  push    rdi
0x180010e25  sub     rsp, 28h
0x180010e29  xor     ebp, ebp
0x180010e2b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010e32  mov     ecx, 0E0h; unsigned __int64
0x180010e37  mov     [r9], rbp
0x180010e3a  mov     rdi, r9
0x180010e3d  mov     rsi, r8
0x180010e40  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010e45  mov     [rsp+48h+arg_18], rax
0x180010e4a  mov     rbx, rax
0x180010e4d  test    rax, rax
0x180010e50  jz      loc_180010F10
0x180010e56  lea     rax, ??_7CRtfIFilter@@6BIPixelFilter@@@; const CRtfIFilter::`vftable'{for `IPixelFilter'}
0x180010e5d  mov     [rbx], rax
0x180010e60  lea     rax, ??_7CRtfIFilter@@6BIPersistFile@@@; const CRtfIFilter::`vftable'{for `IPersistFile'}
0x180010e67  mov     [rbx+8], rax
0x180010e6b  lea     rax, ??_7CRtfIFilter@@6BIPersistStream@@@; const CRtfIFilter::`vftable'{for `IPersistStream'}
0x180010e72  mov     [rbx+10h], rax
0x180010e76  lea     eax, [rbp+1]
0x180010e79  mov     [rbx+18h], rbp
0x180010e7d  mov     [rbx+2Ch], eax
0x180010e80  mov     [rbx+30h], eax
0x180010e83  mov     [rbx+38h], rbp
0x180010e87  mov     [rbx+40h], eax
0x180010e8a  mov     [rbx+48h], rbp
0x180010e8e  mov     [rbx+50h], rbp
0x180010e92  mov     [rbx+58h], rbp
0x180010e96  mov     [rbx+60h], rbp
0x180010e9a  mov     [rbx+68h], eax
0x180010e9d  mov     [rbx+70h], rbp
0x180010ea1  mov     [rbx+78h], rbp
0x180010ea5  mov     [rbx+98h], rbp
0x180010eac  mov     [rbx+0A0h], rbp
0x180010eb3  mov     [rbx+0A8h], rbp
0x180010eba  mov     [rbx+0B0h], rbp
0x180010ec1  mov     [rbx+0C0h], rbp
0x180010ec8  mov     [rbx+0C8h], rbp
0x180010ecf  mov     [rbx+0D0h], rbp
0x180010ed6  mov     [rbx+0D8h], rbp
0x180010edd  lock add cs:?g_cInstances@@3JA, eax; long g_cInstances
0x180010ee4  test    rbx, rbx
0x180010ee7  jz      short loc_180010F10
0x180010ee9  mov     rax, [rbx]
0x180010eec  mov     r8, rdi
0x180010eef  mov     rdx, rsi
0x180010ef2  mov     rcx, rbx
0x180010ef5  mov     rax, [rax]
0x180010ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010efd  mov     rdx, [rbx]
0x180010f00  mov     edi, eax
0x180010f02  mov     rcx, rbx
0x180010f05  mov     rax, [rdx+10h]
0x180010f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f0e  jmp     short loc_180010F15
0x180010f10  mov     edi, 8007000Eh
0x180010f15  mov     eax, edi
0x180010f17  add     rsp, 28h
0x180010f1b  pop     rdi
0x180010f1c  pop     rsi
0x180010f1d  pop     rbp
0x180010f1e  pop     rbx
0x180010f1f  retn
```

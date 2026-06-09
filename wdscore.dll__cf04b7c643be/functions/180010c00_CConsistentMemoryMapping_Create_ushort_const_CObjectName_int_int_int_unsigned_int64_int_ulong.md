# CConsistentMemoryMapping::Create(ushort const *,CObjectName &,int,int,int,unsigned __int64,int *,ulong)

- ea: `0x180010c00`
- end: `0x180010c9d`
- name: `?Create@CConsistentMemoryMapping@@UEAAHPEBGAEAVCObjectName@@HHH_KPEAHK@Z`
- size: `157`
- prototype: `__int64 __fastcall(CConsistentMemoryMapping *__hidden this, const unsigned __int16 *, struct CObjectName *, int, int, int, unsigned __int64, int *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path`

## callees

- `0x180010c00`
- `0x1800274de`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall CConsistentMemoryMapping::Create(
        CConsistentMemoryMapping *this,
        const unsigned __int16 *a2,
        struct CObjectName *a3,
        __int64 a4,
        int a5,
        int a6,
        unsigned __int64 a7,
        int *a8)
{
  unsigned __int64 v9; // rsi
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  unsigned __int64 *v13; // rax
  __int64 result; // rax

  if ( a7 > 0xFFFFFFFF )
    return 0;
  v9 = a7 << 8;
  v10 = *(_QWORD *)g_Kernel32;
  v11 = (*(__int64 (__fastcall **)(struct IKernel32Interface *, const unsigned __int16 *, struct CObjectName *))(*(_QWORD *)g_Kernel32 + 56LL))(
          g_Kernel32,
          a2,
          a3);
  v12 = (*(__int64 (__fastcall **)(struct IKernel32Interface *, __int64, __int64, unsigned __int64))(v10 + 80))(
          g_Kernel32,
          v11,
          8,
          a7 << 8);
  *((_QWORD *)this + 2) = v12;
  if ( !v12 )
    return 0;
  v13 = (unsigned __int64 *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 3) = v9;
  *v13 = v9;
  memset_0(*((void **)this + 2), 0, *((_QWORD *)this + 3));
  result = 1;
  if ( a8 )
    *a8 = 1;
  return result;
}

```

## disassembly

```asm
0x180010c00  mov     [rsp+arg_0], rbx
0x180010c05  mov     [rsp+arg_8], rsi
0x180010c0a  push    rdi
0x180010c0b  sub     rsp, 30h
0x180010c0f  mov     rsi, [rsp+38h+arg_30]
0x180010c14  mov     eax, 0FFFFFFFFh
0x180010c19  mov     rdi, rcx
0x180010c1c  cmp     rsi, rax
0x180010c1f  ja      short loc_180010C8A
0x180010c21  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180010c28  shl     rsi, 8
0x180010c2c  mov     rbx, [rcx]
0x180010c2f  mov     rax, [rbx+38h]
0x180010c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c38  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180010c3f  mov     rdx, rax
0x180010c42  mov     rax, [rbx+50h]
0x180010c46  mov     r9, rsi
0x180010c49  mov     r8d, 8
0x180010c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c54  mov     [rdi+10h], rax
0x180010c58  test    rax, rax
0x180010c5b  jz      short loc_180010C8A
0x180010c5d  mov     rax, [rdi+8]
0x180010c61  xor     edx, edx; Val
0x180010c63  mov     [rdi+18h], rsi
0x180010c67  mov     [rax], rsi
0x180010c6a  mov     r8, [rdi+18h]; Size
0x180010c6e  mov     rcx, [rdi+10h]; void *
0x180010c72  call    memset_0
0x180010c77  mov     rcx, [rsp+38h+arg_38]
0x180010c7c  mov     eax, 1
0x180010c81  test    rcx, rcx
0x180010c84  jz      short loc_180010C8C
0x180010c86  mov     [rcx], eax
0x180010c88  jmp     short loc_180010C8C
0x180010c8a  xor     eax, eax
0x180010c8c  mov     rbx, [rsp+38h+arg_0]
0x180010c91  mov     rsi, [rsp+38h+arg_8]
0x180010c96  add     rsp, 30h
0x180010c9a  pop     rdi
0x180010c9b  retn
```

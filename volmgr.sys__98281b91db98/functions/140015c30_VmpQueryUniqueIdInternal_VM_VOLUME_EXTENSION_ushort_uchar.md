# VmpQueryUniqueIdInternal(VM_VOLUME_EXTENSION *,ushort *,uchar *)

- ea: `0x140015c30`
- end: `0x140015cff`
- name: `?VmpQueryUniqueIdInternal@@YAJPEAVVM_VOLUME_EXTENSION@@PEAGPEAE@Z`
- size: `207`
- prototype: `int(struct VM_VOLUME_EXTENSION *, unsigned __int16 *, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000eba0`
- `0x14000fb80`
- `0x140010ad8`
- `0x140015bb0`
- `0x140015da0`

## callees

- `0x140005090`
- `0x140005240`
- `0x140015c30`

## pseudocode

```c
__int64 __fastcall VmpQueryUniqueIdInternal(struct VM_VOLUME_EXTENSION *a1, unsigned __int16 *a2, unsigned __int8 *a3)
{
  char v5; // cl
  __int64 v7; // rdx
  unsigned __int16 v8; // bx
  __int64 result; // rax
  _OWORD *v10; // rdi

  v5 = *((_BYTE *)a1 + 426);
  if ( v5 )
  {
    v7 = 0;
    v8 = 24;
  }
  else
  {
    v7 = *(_QWORD *)(*((_QWORD *)a1 + 43) + 64LL);
    v8 = **(_WORD **)(v7 + 80);
  }
  if ( v8 <= *a2 )
  {
    if ( v5 )
    {
      v10 = (_OWORD *)((char *)a1 + 408);
      (*(void (__fastcall **)(_QWORD, char *))(*((_QWORD *)VmRootExtension + 49) + 120LL))(
        *((_QWORD *)a1 + 54),
        (char *)a1 + 408);
      *(_QWORD *)a3 = 0x3A44493A4F494D44LL;
      *(_OWORD *)(a3 + 8) = *v10;
    }
    else
    {
      memmove(a3, (const void *)(*(_QWORD *)(v7 + 80) + 2LL), v8);
    }
    result = 0;
  }
  else
  {
    result = 2147483653LL;
  }
  *a2 = v8;
  return result;
}

```

## disassembly

```asm
0x140015c30  mov     [rsp+arg_10], rbx
0x140015c35  mov     [rsp+arg_18], rsi
0x140015c3a  push    r14
0x140015c3c  sub     rsp, 20h
0x140015c40  mov     r9, rcx
0x140015c43  mov     r14, r8
0x140015c46  movzx   ecx, byte ptr [rcx+1AAh]
0x140015c4d  mov     rsi, rdx
0x140015c50  test    cl, cl
0x140015c52  jnz     short loc_140015CAD
0x140015c54  mov     rax, [r9+158h]
0x140015c5b  mov     rdx, [rax+40h]
0x140015c5f  mov     rbx, [rdx+50h]
0x140015c63  movzx   ebx, word ptr [rbx]
0x140015c66  cmp     bx, [rsi]
0x140015c69  jbe     short loc_140015C85
0x140015c6b  mov     eax, 80000005h
0x140015c70  mov     [rsi], bx
0x140015c73  mov     rbx, [rsp+28h+arg_10]
0x140015c78  mov     rsi, [rsp+28h+arg_18]
0x140015c7d  add     rsp, 20h
0x140015c81  pop     r14
0x140015c83  retn
0x140015c85  mov     [rsp+28h+arg_0], rbp
0x140015c8a  xor     ebp, ebp
0x140015c8c  test    cl, cl
0x140015c8e  jnz     short loc_140015CB6
0x140015c90  mov     rdx, [rdx+50h]
0x140015c94  mov     rcx, r14; void *
0x140015c97  add     rdx, 2; Src
0x140015c9b  movzx   r8d, bx; Size
0x140015c9f  call    memmove
0x140015ca4  mov     eax, ebp
0x140015ca6  mov     rbp, [rsp+28h+arg_0]
0x140015cab  jmp     short loc_140015C70
0x140015cad  xor     edx, edx
0x140015caf  mov     ebx, 18h
0x140015cb4  jmp     short loc_140015C66
0x140015cb6  mov     rax, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140015cbd  mov     [rsp+28h+arg_8], rdi
0x140015cc2  lea     rdi, [r9+198h]
0x140015cc9  mov     rdx, rdi
0x140015ccc  mov     rcx, [rax+188h]
0x140015cd3  mov     rax, [rcx+78h]
0x140015cd7  mov     rcx, [r9+1B0h]
0x140015cde  call    _guard_dispatch_icall
0x140015ce3  mov     rax, 3A44493A4F494D44h
0x140015ced  mov     [r14], rax
0x140015cf0  movups  xmm0, xmmword ptr [rdi]
0x140015cf3  mov     rdi, [rsp+28h+arg_8]
0x140015cf8  movups  xmmword ptr [r14+8], xmm0
0x140015cfd  jmp     short loc_140015CA4
```

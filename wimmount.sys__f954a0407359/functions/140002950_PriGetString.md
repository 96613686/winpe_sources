# PriGetString

- ea: `0x140002950`
- end: `0x1400029e0`
- name: `PriGetString`
- size: `144`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000223c`

## callees

- `0x140002950`
- `0x1400029e8`
- `0x140002c90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400029c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400029c2`

## pseudocode

```c
__int64 __fastcall PriGetString(__int64 a1, __int64 (__fastcall *a2)(__int64, __int64, unsigned int *), __int64 a3)
{
  int v6; // edi
  __int64 v7; // rdx
  void *v8; // rcx
  unsigned int v10; // [rsp+58h] [rbp+10h] BYREF

  v10 = 0;
  do
  {
    v6 = a2(a1, a3, &v10);
    if ( v6 != -1073741789 )
      break;
    v7 = v10;
    if ( v10 <= *(unsigned __int16 *)(a3 + 2) || v10 > 0xFFFF )
      goto LABEL_7;
    *(_WORD *)a3 = 0;
  }
  while ( (int)PriStringEnsureCapacity(a3, v7) >= 0 );
  if ( v6 >= 0 )
    return (unsigned int)v6;
LABEL_7:
  if ( a3 )
  {
    v8 = *(void **)(a3 + 8);
    if ( v8 )
      ExFreePoolWithTag(v8, 0x574D6365u);
    *(_OWORD *)a3 = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140002950  push    rbx
0x140002952  push    rbp
0x140002953  push    rsi
0x140002954  push    rdi
0x140002955  sub     rsp, 28h
0x140002959  mov     rbx, r8
0x14000295c  mov     [rsp+48h+arg_8], 0
0x140002964  mov     rsi, rdx
0x140002967  mov     rbp, rcx
0x14000296a  lea     r8, [rsp+48h+arg_8]
0x14000296f  mov     rdx, rbx
0x140002972  mov     rcx, rbp
0x140002975  mov     rax, rsi
0x140002978  call    _guard_dispatch_icall
0x14000297d  mov     edi, eax
0x14000297f  cmp     eax, 0C0000023h
0x140002984  jnz     short loc_1400029AB
0x140002986  movzx   ecx, word ptr [rbx+2]
0x14000298a  mov     edx, [rsp+48h+arg_8]
0x14000298e  cmp     edx, ecx
0x140002990  jbe     short loc_1400029AF
0x140002992  cmp     edx, 0FFFFh
0x140002998  ja      short loc_1400029AF
0x14000299a  xor     ecx, ecx
0x14000299c  mov     [rbx], cx
0x14000299f  mov     rcx, rbx
0x1400029a2  call    PriStringEnsureCapacity
0x1400029a7  test    eax, eax
0x1400029a9  jns     short loc_14000296A
0x1400029ab  test    edi, edi
0x1400029ad  jns     short loc_1400029D4
0x1400029af  test    rbx, rbx
0x1400029b2  jz      short loc_1400029D4
0x1400029b4  mov     rcx, [rbx+8]; P
0x1400029b8  test    rcx, rcx
0x1400029bb  jz      short loc_1400029CE
0x1400029bd  mov     edx, 574D6365h; Tag
0x1400029c2  call    cs:__imp_ExFreePoolWithTag
0x1400029c9  nop     dword ptr [rax+rax+00h]
0x1400029ce  xorps   xmm0, xmm0
0x1400029d1  movups  xmmword ptr [rbx], xmm0
0x1400029d4  mov     eax, edi
0x1400029d6  add     rsp, 28h
0x1400029da  pop     rdi
0x1400029db  pop     rsi
0x1400029dc  pop     rbp
0x1400029dd  pop     rbx
0x1400029de  retn
```

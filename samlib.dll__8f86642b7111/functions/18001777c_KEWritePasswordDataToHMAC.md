# KEWritePasswordDataToHMAC

- ea: `0x18001777c`
- end: `0x180017819`
- name: `KEWritePasswordDataToHMAC`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009b38`

## callees

- `0x18001777c`
- `0x180017929`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800177bc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800177bc`

## pseudocode

```c
__int64 __fastcall KEWritePasswordDataToHMAC(
        _OWORD *a1,
        __int64 a2,
        const void *a3,
        unsigned int a4,
        _QWORD *a5,
        unsigned int *a6)
{
  size_t v7; // rbp
  unsigned int v9; // esi
  char *v10; // rax
  char *v11; // rdi
  __int64 result; // rax

  v7 = a4;
  *a5 = 0;
  *a6 = 0;
  v9 = a4 + 18;
  v10 = (char *)LocalAlloc(0x40u, a4 + 18);
  *a5 = v10;
  v11 = v10;
  if ( !v10 )
    return 3221225626LL;
  *v10 = 1;
  *(_OWORD *)(v10 + 1) = *a1;
  memcpy_0(v10 + 17, a3, v7);
  v11[(unsigned int)(v7 + 17)] = 1;
  if ( (_DWORD)v7 + 18 != v9 )
    return 3221225485LL;
  result = 0;
  *a6 = v9;
  return result;
}

```

## disassembly

```asm
0x18001777c  push    rbx
0x18001777e  push    rbp
0x18001777f  push    rsi
0x180017780  push    rdi
0x180017781  push    r12
0x180017783  push    r14
0x180017785  push    r15
0x180017787  sub     rsp, 20h
0x18001778b  mov     rbx, [rsp+58h+arg_20]
0x180017793  mov     r12, rcx
0x180017796  mov     r14, [rsp+58h+arg_28]
0x18001779e  mov     ecx, 40h ; '@'; uFlags
0x1800177a3  mov     ebp, r9d
0x1800177a6  mov     r15, r8
0x1800177a9  mov     qword ptr [rbx], 0
0x1800177b0  mov     dword ptr [r14], 0
0x1800177b7  lea     esi, [rbp+12h]
0x1800177ba  mov     edx, esi; uBytes
0x1800177bc  call    cs:__imp_LocalAlloc
0x1800177c2  mov     [rbx], rax
0x1800177c5  mov     rdi, rax
0x1800177c8  test    rax, rax
0x1800177cb  jnz     short loc_1800177D4
0x1800177cd  mov     eax, 0C000009Ah
0x1800177d2  jmp     short loc_18001780A
0x1800177d4  mov     byte ptr [rax], 1
0x1800177d7  lea     rcx, [rax+11h]; void *
0x1800177db  movups  xmm0, xmmword ptr [r12]
0x1800177e0  mov     r8, rbp; Size
0x1800177e3  mov     rdx, r15; Src
0x1800177e6  movdqu  xmmword ptr [rax+1], xmm0
0x1800177eb  call    memcpy_0
0x1800177f0  lea     ecx, [rbp+11h]
0x1800177f3  lea     eax, [rcx+1]
0x1800177f6  mov     byte ptr [rcx+rdi], 1
0x1800177fa  cmp     eax, esi
0x1800177fc  jz      short loc_180017805
0x1800177fe  mov     eax, 0C000000Dh
0x180017803  jmp     short loc_18001780A
0x180017805  xor     eax, eax
0x180017807  mov     [r14], esi
0x18001780a  add     rsp, 20h
0x18001780e  pop     r15
0x180017810  pop     r14
0x180017812  pop     r12
0x180017814  pop     rdi
0x180017815  pop     rsi
0x180017816  pop     rbp
0x180017817  pop     rbx
0x180017818  retn
```

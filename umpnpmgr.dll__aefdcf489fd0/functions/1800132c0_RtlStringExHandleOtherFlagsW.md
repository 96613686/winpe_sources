# RtlStringExHandleOtherFlagsW

- ea: `0x1800132c0`
- end: `0x18001336a`
- name: `RtlStringExHandleOtherFlagsW`
- size: `170`
- prototype: `__int64 __fastcall(_WORD *, size_t, __int64, _QWORD *, size_t *, __int16)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ec0`
- `0x1800027a0`
- `0x180004180`
- `0x1800056d0`

## callees

- `0x1800132c0`
- `0x18001893e`

## pseudocode

```c
__int64 __fastcall RtlStringExHandleOtherFlagsW(_WORD *a1, size_t a2, __int64 a3, _QWORD *a4, size_t *a5, __int16 a6)
{
  size_t v6; // rdi
  _WORD *v10; // rdx
  _WORD *v12; // rcx

  v6 = a2 >> 1;
  if ( a2 >> 1 && (a6 & 0x1000) != 0 )
  {
    v10 = &a1[a3];
    *a4 = v10;
    *a5 = v6 - a3;
    *v10 = 0;
  }
  if ( (a6 & 0x400) == 0 )
  {
LABEL_7:
    if ( !v6 )
      return 0;
    goto LABEL_8;
  }
  memset_0(a1, (unsigned __int8)a6, a2);
  if ( !(_BYTE)a6 )
  {
    *a4 = a1;
    *a5 = v6;
    goto LABEL_7;
  }
  if ( !v6 )
    return 0;
  *a5 = 1;
  v12 = &a1[v6 - 1];
  *a4 = v12;
  *v12 = 0;
LABEL_8:
  if ( (a6 & 0x800) != 0 )
  {
    *a4 = a1;
    *a1 = 0;
    *a5 = v6;
  }
  return 0;
}

```

## disassembly

```asm
0x1800132c0  push    rbx
0x1800132c2  push    rsi
0x1800132c3  push    rdi
0x1800132c4  push    r14
0x1800132c6  push    r15
0x1800132c8  sub     rsp, 20h
0x1800132cc  mov     r15, [rsp+48h+arg_20]
0x1800132d1  mov     rdi, rdx
0x1800132d4  shr     rdi, 1
0x1800132d7  mov     r14, r9
0x1800132da  mov     r9, rdx
0x1800132dd  mov     rsi, rcx
0x1800132e0  jz      short loc_180013301
0x1800132e2  test    [rsp+48h+arg_28], 1000h
0x1800132ea  jz      short loc_180013301
0x1800132ec  lea     rdx, [rcx+r8*2]
0x1800132f0  mov     rax, rdi
0x1800132f3  sub     rax, r8
0x1800132f6  mov     [r14], rdx
0x1800132f9  mov     [r15], rax
0x1800132fc  xor     eax, eax
0x1800132fe  mov     [rdx], ax
0x180013301  test    [rsp+48h+arg_28], 400h
0x180013309  jz      short loc_180013324
0x18001330b  movzx   ebx, byte ptr [rsp+48h+arg_28]
0x180013310  mov     r8, r9; Size
0x180013313  mov     edx, ebx; Val
0x180013315  call    memset_0
0x18001331a  test    ebx, ebx
0x18001331c  jnz     short loc_18001334C
0x18001331e  mov     [r14], rsi
0x180013321  mov     [r15], rdi
0x180013324  test    rdi, rdi
0x180013327  jz      short loc_18001333E
0x180013329  test    [rsp+48h+arg_28], 800h
0x180013331  jz      short loc_18001333E
0x180013333  xor     eax, eax
0x180013335  mov     [r14], rsi
0x180013338  mov     [rsi], ax
0x18001333b  mov     [r15], rdi
0x18001333e  xor     eax, eax
0x180013340  add     rsp, 20h
0x180013344  pop     r15
0x180013346  pop     r14
0x180013348  pop     rdi
0x180013349  pop     rsi
0x18001334a  pop     rbx
0x18001334b  retn
0x18001334c  test    rdi, rdi
0x18001334f  jz      short loc_18001333E
0x180013351  lea     rcx, [rsi-2]
0x180013355  mov     qword ptr [r15], 1
0x18001335c  lea     rcx, [rcx+rdi*2]
0x180013360  xor     eax, eax
0x180013362  mov     [r14], rcx
0x180013365  mov     [rcx], ax
0x180013368  jmp     short loc_180013329
```

# VsmmBitmapClone

- ea: `0x1400d6dc0`
- end: `0x1400d6f16`
- name: `VsmmBitmapClone`
- size: `342`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1400b16c0`
- `0x1400f6810`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x1400d6dc0`
- `0x1400f4f24`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400d6e0b`
- `ntoskrnl!ExAllocatePool2` at `0x1400d6e0b`
- `ntoskrnl!RtlCopyBitMapEx` at `0x1400d6ee6`
- `ntoskrnl!RtlCopyBitMapEx` at `0x1400d6ee6`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x1400d6ed1`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x1400d6ed1`

## pseudocode

```c
__int64 __fastcall VsmmBitmapClone(_OWORD *a1, _QWORD *a2)
{
  unsigned __int64 v4; // rsi
  __int64 Pool2; // rax
  unsigned int v6; // ebx
  int v8; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int64 v9; // [rsp+38h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+40h] [rbp-29h] BYREF
  char v11[16]; // [rsp+60h] [rbp-9h] BYREF
  char v12[16]; // [rsp+70h] [rbp+7h] BYREF
  int *v13; // [rsp+80h] [rbp+17h]
  __int64 v14; // [rsp+88h] [rbp+1Fh]
  unsigned __int64 *v15; // [rsp+90h] [rbp+27h]
  __int64 v16; // [rsp+98h] [rbp+2Fh]

  *a1 = 0;
  v4 = 8 * ((unsigned __int64)(*a2 + 63LL) >> 6);
  Pool2 = ExAllocatePool2(66, v4, 1833788502);
  if ( Pool2 )
  {
    RtlInitializeBitMapEx(a1, Pool2, *a2);
    RtlCopyBitMapEx(a2, a1, 0);
    return 0;
  }
  else
  {
    v6 = -1073741670;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v11, "VsmmBitmapClone");
      tlgCreate1Sz_char(v12, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
      v8 = 8382;
      v13 = &v8;
      v14 = 4;
      v15 = &v9;
      v9 = v4;
      v16 = 8;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, (unsigned __int8 *)byte_14005552B, 0, 0, 6u, &v10);
    }
    VsmmBitmapTeardown(a1);
  }
  return v6;
}

```

## disassembly

```asm
0x1400d6dc0  mov     [rsp-8+arg_10], rbx
0x1400d6dc5  push    rbp
0x1400d6dc6  push    rsi
0x1400d6dc7  push    rdi
0x1400d6dc8  lea     rbp, [rsp-47h]
0x1400d6dcd  sub     rsp, 0B0h
0x1400d6dd4  mov     rax, cs:__security_cookie
0x1400d6ddb  xor     rax, rsp
0x1400d6dde  mov     [rbp+57h+var_20], rax
0x1400d6de2  xorps   xmm0, xmm0
0x1400d6de5  mov     rbx, rdx
0x1400d6de8  movups  xmmword ptr [rcx], xmm0
0x1400d6deb  mov     rsi, [rdx]
0x1400d6dee  mov     rdi, rcx
0x1400d6df1  add     rsi, 3Fh ; '?'
0x1400d6df5  mov     r8d, 6D4D6456h
0x1400d6dfb  shr     rsi, 6
0x1400d6dff  mov     ecx, 42h ; 'B'
0x1400d6e04  shl     rsi, 3
0x1400d6e08  mov     rdx, rsi
0x1400d6e0b  call    cs:__imp_ExAllocatePool2
0x1400d6e12  nop     dword ptr [rax+rax+00h]
0x1400d6e17  test    rax, rax
0x1400d6e1a  jnz     loc_1400D6EC8
0x1400d6e20  mov     eax, cs:dword_140065110
0x1400d6e26  mov     ebx, 0C000009Ah
0x1400d6e2b  cmp     eax, 2
0x1400d6e2e  jbe     loc_1400D6EBE
0x1400d6e34  mov     edx, 100h
0x1400d6e39  lea     rcx, dword_140065110
0x1400d6e40  call    _tlgKeywordOn
0x1400d6e45  test    al, al
0x1400d6e47  jz      short loc_1400D6EBE
0x1400d6e49  lea     rdx, aVsmmbitmapclon; "VsmmBitmapClone"
0x1400d6e50  lea     rcx, [rbp+57h+var_60]
0x1400d6e54  call    _tlgCreate1Sz_char
0x1400d6e59  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x1400d6e60  lea     rcx, [rbp+57h+var_50]
0x1400d6e64  call    _tlgCreate1Sz_char
0x1400d6e69  lea     rax, [rbp+57h+var_90]
0x1400d6e6d  mov     [rbp+57h+var_90], 20BEh
0x1400d6e74  mov     [rbp+57h+var_40], rax
0x1400d6e78  lea     rdx, byte_14005552B
0x1400d6e7f  lea     rax, [rbp+57h+var_88]
0x1400d6e83  mov     [rbp+57h+var_38], 4
0x1400d6e8b  mov     [rbp+57h+var_30], rax
0x1400d6e8f  lea     rcx, dword_140065110
0x1400d6e96  lea     rax, [rbp+57h+var_80]
0x1400d6e9a  mov     [rbp+57h+var_88], rsi
0x1400d6e9e  mov     [rsp+0C0h+var_98], rax
0x1400d6ea3  xor     r9d, r9d
0x1400d6ea6  xor     r8d, r8d
0x1400d6ea9  mov     [rsp+0C0h+var_A0], 6
0x1400d6eb1  mov     [rbp+57h+var_28], 8
0x1400d6eb9  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400d6ebe  mov     rcx, rdi
0x1400d6ec1  call    VsmmBitmapTeardown
0x1400d6ec6  jmp     short loc_1400D6EF4
0x1400d6ec8  mov     r8, [rbx]
0x1400d6ecb  mov     rdx, rax
0x1400d6ece  mov     rcx, rdi
0x1400d6ed1  call    cs:__imp_RtlInitializeBitMapEx
0x1400d6ed8  nop     dword ptr [rax+rax+00h]
0x1400d6edd  xor     r8d, r8d
0x1400d6ee0  mov     rdx, rdi
0x1400d6ee3  mov     rcx, rbx
0x1400d6ee6  call    cs:__imp_RtlCopyBitMapEx
0x1400d6eed  nop     dword ptr [rax+rax+00h]
0x1400d6ef2  xor     ebx, ebx
0x1400d6ef4  mov     eax, ebx
0x1400d6ef6  mov     rcx, [rbp+57h+var_20]
0x1400d6efa  xor     rcx, rsp; StackCookie
0x1400d6efd  call    __security_check_cookie
0x1400d6f02  mov     rbx, [rsp+0C0h+arg_10]
0x1400d6f0a  add     rsp, 0B0h
0x1400d6f11  pop     rdi
0x1400d6f12  pop     rsi
0x1400d6f13  pop     rbp
0x1400d6f14  retn
```

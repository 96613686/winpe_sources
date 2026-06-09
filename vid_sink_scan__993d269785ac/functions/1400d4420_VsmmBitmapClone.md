# VsmmBitmapClone

- ea: `0x1400d4420`
- end: `0x1400d4576`
- name: `VsmmBitmapClone`
- size: `342`
- prototype: `__int64 __fastcall(_OWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1400af880`
- `0x1400f3d30`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x1400d4420`
- `0x1400f2cbc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400d446b`
- `ntoskrnl!ExAllocatePool2` at `0x1400d446b`
- `ntoskrnl!RtlCopyBitMapEx` at `0x1400d4546`
- `ntoskrnl!RtlCopyBitMapEx` at `0x1400d4546`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x1400d4531`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x1400d4531`

## pseudocode

```c
__int64 __fastcall VsmmBitmapClone(_OWORD *a1, _QWORD *a2)
{
  unsigned __int64 v4; // rsi
  __int64 Pool2; // rax
  unsigned int v6; // ebx
  int v8; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int64 v9; // [rsp+38h] [rbp-31h] BYREF
  char v10[32]; // [rsp+40h] [rbp-29h] BYREF
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
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v11, "VsmmBitmapClone");
      tlgCreate1Sz_char(v12, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
      v8 = 8384;
      v13 = &v8;
      v14 = 4;
      v15 = &v9;
      v9 = v4;
      v16 = 8;
      tlgWriteTransfer_EtwWriteTransfer(
        (__int64)&dword_140064110,
        (unsigned __int8 *)byte_140054E89,
        0,
        0,
        6u,
        (PEVENT_DATA_DESCRIPTOR)v10);
    }
    VsmmBitmapTeardown(a1);
  }
  return v6;
}

```

## disassembly

```asm
0x1400d4420  mov     [rsp-8+arg_10], rbx
0x1400d4425  push    rbp
0x1400d4426  push    rsi
0x1400d4427  push    rdi
0x1400d4428  lea     rbp, [rsp-47h]
0x1400d442d  sub     rsp, 0B0h
0x1400d4434  mov     rax, cs:__security_cookie
0x1400d443b  xor     rax, rsp
0x1400d443e  mov     [rbp+57h+var_20], rax
0x1400d4442  xorps   xmm0, xmm0
0x1400d4445  mov     rbx, rdx
0x1400d4448  movups  xmmword ptr [rcx], xmm0
0x1400d444b  mov     rsi, [rdx]
0x1400d444e  mov     rdi, rcx
0x1400d4451  add     rsi, 3Fh ; '?'
0x1400d4455  mov     r8d, 6D4D6456h
0x1400d445b  shr     rsi, 6
0x1400d445f  mov     ecx, 42h ; 'B'
0x1400d4464  shl     rsi, 3
0x1400d4468  mov     rdx, rsi
0x1400d446b  call    cs:__imp_ExAllocatePool2
0x1400d4472  nop     dword ptr [rax+rax+00h]
0x1400d4477  test    rax, rax
0x1400d447a  jnz     loc_1400D4528
0x1400d4480  mov     eax, cs:dword_140064110
0x1400d4486  mov     ebx, 0C000009Ah
0x1400d448b  cmp     eax, 2
0x1400d448e  jbe     loc_1400D451E
0x1400d4494  mov     edx, 100h
0x1400d4499  lea     rcx, dword_140064110
0x1400d44a0  call    _tlgKeywordOn
0x1400d44a5  test    al, al
0x1400d44a7  jz      short loc_1400D451E
0x1400d44a9  lea     rdx, aVsmmbitmapclon; "VsmmBitmapClone"
0x1400d44b0  lea     rcx, [rbp+57h+var_60]
0x1400d44b4  call    _tlgCreate1Sz_char
0x1400d44b9  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x1400d44c0  lea     rcx, [rbp+57h+var_50]
0x1400d44c4  call    _tlgCreate1Sz_char
0x1400d44c9  lea     rax, [rbp+57h+var_90]
0x1400d44cd  mov     [rbp+57h+var_90], 20C0h
0x1400d44d4  mov     [rbp+57h+var_40], rax
0x1400d44d8  lea     rdx, byte_140054E89
0x1400d44df  lea     rax, [rbp+57h+var_88]
0x1400d44e3  mov     [rbp+57h+var_38], 4
0x1400d44eb  mov     [rbp+57h+var_30], rax
0x1400d44ef  lea     rcx, dword_140064110
0x1400d44f6  lea     rax, [rbp+57h+var_80]
0x1400d44fa  mov     [rbp+57h+var_88], rsi
0x1400d44fe  mov     [rsp+0C0h+var_98], rax
0x1400d4503  xor     r9d, r9d
0x1400d4506  xor     r8d, r8d
0x1400d4509  mov     [rsp+0C0h+var_A0], 6
0x1400d4511  mov     [rbp+57h+var_28], 8
0x1400d4519  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400d451e  mov     rcx, rdi
0x1400d4521  call    VsmmBitmapTeardown
0x1400d4526  jmp     short loc_1400D4554
0x1400d4528  mov     r8, [rbx]
0x1400d452b  mov     rdx, rax
0x1400d452e  mov     rcx, rdi
0x1400d4531  call    cs:__imp_RtlInitializeBitMapEx
0x1400d4538  nop     dword ptr [rax+rax+00h]
0x1400d453d  xor     r8d, r8d
0x1400d4540  mov     rdx, rdi
0x1400d4543  mov     rcx, rbx
0x1400d4546  call    cs:__imp_RtlCopyBitMapEx
0x1400d454d  nop     dword ptr [rax+rax+00h]
0x1400d4552  xor     ebx, ebx
0x1400d4554  mov     eax, ebx
0x1400d4556  mov     rcx, [rbp+57h+var_20]
0x1400d455a  xor     rcx, rsp; StackCookie
0x1400d455d  call    __security_check_cookie
0x1400d4562  mov     rbx, [rsp+0C0h+arg_10]
0x1400d456a  add     rsp, 0B0h
0x1400d4571  pop     rdi
0x1400d4572  pop     rsi
0x1400d4573  pop     rbp
0x1400d4574  retn
```

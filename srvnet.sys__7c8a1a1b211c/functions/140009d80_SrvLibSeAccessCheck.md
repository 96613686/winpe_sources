# SrvLibSeAccessCheck

- ea: `0x140009d80`
- end: `0x140009ee4`
- name: `SrvLibSeAccessCheck`
- size: `356`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, __int64, char, __int64, void *, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140028ea0`
- `0x14004fac0`
- `0x140056ae8`

## callees

- `0x14002a3e0`
- `0x14002a840`

## import_xrefs

- `ntoskrnl!SeAccessCheckEx` at `0x140009eb4`
- `ntoskrnl!SeAccessCheckEx` at `0x140009eb4`

## pseudocode

```c
__int64 __fastcall SrvLibSeAccessCheck(
        __int64 a1,
        __int64 a2,
        unsigned __int8 a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        char a8,
        __int64 a9,
        _BYTE *a10,
        __int64 a11)
{
  _BYTE *v12; // rdi
  _QWORD v18[2]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v19[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h]
  __int64 v21; // [rsp+60h] [rbp-A0h]
  _BYTE *v22; // [rsp+68h] [rbp-98h]
  __int64 v23; // [rsp+70h] [rbp-90h]
  _QWORD v24[2]; // [rsp+78h] [rbp-88h] BYREF
  int v25; // [rsp+88h] [rbp-78h]
  int v26; // [rsp+8Ch] [rbp-74h]
  __int64 v27; // [rsp+90h] [rbp-70h]
  __int64 v28; // [rsp+98h] [rbp-68h]
  __int128 v29; // [rsp+A0h] [rbp-60h]
  _DWORD v30[24]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v31[128]; // [rsp+110h] [rbp+10h] BYREF

  memset(v31, 0, sizeof(v31));
  v12 = v31;
  if ( a10 )
    v12 = a10;
  memset(v12, 0, 0x80u);
  v18[0] = 16;
  v27 = 0;
  v25 = a4;
  v26 = a5;
  v24[1] = v18;
  v18[1] = a1;
  v24[0] = 56;
  v29 = 0;
  v28 = a7;
  v19[0] = 40;
  v19[1] = 1;
  v20 = a9;
  v21 = a11;
  v22 = v12;
  v23 = a6;
  memset(&v30[1], 0, 0x5Cu);
  v30[0] = 96;
  return SeAccessCheckEx(a2, a3, v24, v19, v30, a8);
}

```

## disassembly

```asm
0x140009d80  push    rbp
0x140009d82  push    rbx
0x140009d83  push    rsi
0x140009d84  push    rdi
0x140009d85  push    r12
0x140009d87  push    r13
0x140009d89  push    r14
0x140009d8b  push    r15
0x140009d8d  lea     rbp, [rsp-0A8h]
0x140009d95  sub     rsp, 1A8h
0x140009d9c  mov     rax, cs:__security_cookie
0x140009da3  xor     rax, rsp
0x140009da6  mov     [rbp+0E0h+var_50], rax
0x140009dad  mov     rbx, [rbp+0E0h+arg_48]
0x140009db4  mov     r14, rcx
0x140009db7  mov     r13, [rbp+0E0h+arg_28]
0x140009dbe  lea     rcx, [rbp+0E0h+var_D0]; void *
0x140009dc2  mov     rsi, [rbp+0E0h+arg_30]
0x140009dc9  mov     r12, [rbp+0E0h+arg_40]
0x140009dd0  mov     r15, [rbp+0E0h+arg_50]
0x140009dd7  mov     [rsp+1E0h+var_1B0], r8b
0x140009ddc  mov     r8d, 80h; Size
0x140009de2  mov     [rsp+1E0h+var_1A8], rdx
0x140009de7  xor     edx, edx; Val
0x140009de9  mov     [rsp+1E0h+var_1AC], r9d
0x140009dee  call    memset
0x140009df3  test    rbx, rbx
0x140009df6  lea     rdi, [rbp+0E0h+var_D0]
0x140009dfa  mov     r8d, 80h; Size
0x140009e00  cmovnz  rdi, rbx
0x140009e04  xor     edx, edx; Val
0x140009e06  mov     rcx, rdi; void *
0x140009e09  call    memset
0x140009e0e  xor     eax, eax
0x140009e10  mov     [rsp+1E0h+var_1A0], 10h
0x140009e19  mov     [rbp+0E0h+var_150], rax
0x140009e1d  lea     rcx, [rbp+0E0h+var_12C]; void *
0x140009e21  mov     eax, [rsp+1E0h+var_1AC]
0x140009e25  xorps   xmm0, xmm0
0x140009e28  mov     [rbp+0E0h+var_158], eax
0x140009e2b  xor     edx, edx; Val
0x140009e2d  mov     eax, [rbp+0E0h+arg_20]
0x140009e33  mov     r8d, 5Ch ; '\'; Size
0x140009e39  mov     [rbp+0E0h+var_154], eax
0x140009e3c  lea     rax, [rsp+1E0h+var_1A0]
0x140009e41  mov     [rbp+0E0h+var_160], rax
0x140009e45  mov     [rsp+1E0h+var_198], r14
0x140009e4a  mov     [rsp+1E0h+var_168], 38h ; '8'
0x140009e53  movdqu  [rbp+0E0h+var_140], xmm0
0x140009e58  mov     [rbp+0E0h+var_148], rsi
0x140009e5c  mov     [rsp+1E0h+var_190], 28h ; '('
0x140009e64  mov     [rsp+1E0h+var_18C], 1
0x140009e6c  mov     [rsp+1E0h+var_188], r12
0x140009e71  mov     [rsp+1E0h+var_180], r15
0x140009e76  mov     [rsp+1E0h+var_178], rdi
0x140009e7b  mov     [rsp+1E0h+var_170], r13
0x140009e80  call    memset
0x140009e85  movzx   eax, [rbp+0E0h+arg_38]
0x140009e8c  lea     r9, [rsp+1E0h+var_190]
0x140009e91  movzx   edx, [rsp+1E0h+var_1B0]
0x140009e96  lea     r8, [rsp+1E0h+var_168]
0x140009e9b  mov     rcx, [rsp+1E0h+var_1A8]
0x140009ea0  mov     [rsp+1E0h+var_1B8], al
0x140009ea4  lea     rax, [rbp+0E0h+var_130]
0x140009ea8  mov     [rsp+1E0h+var_1C0], rax
0x140009ead  mov     [rbp+0E0h+var_130], 60h ; '`'
0x140009eb4  call    cs:__imp_SeAccessCheckEx
0x140009ebb  nop     dword ptr [rax+rax+00h]
0x140009ec0  mov     rcx, [rbp+0E0h+var_50]
0x140009ec7  xor     rcx, rsp; StackCookie
0x140009eca  call    __security_check_cookie
0x140009ecf  add     rsp, 1A8h
0x140009ed6  pop     r15
0x140009ed8  pop     r14
0x140009eda  pop     r13
0x140009edc  pop     r12
0x140009ede  pop     rdi
0x140009edf  pop     rsi
0x140009ee0  pop     rbx
0x140009ee1  pop     rbp
0x140009ee2  retn
```

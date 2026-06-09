# WinHvpRangeRepHypercall

- ea: `0x140001a38`
- end: `0x140001ced`
- name: `WinHvpRangeRepHypercall`
- size: `693`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140001620`
- `0x140004b90`
- `0x140005470`
- `0x140025f30`

## callees

- `0x140001a38`
- `0x140002240`
- `0x140009c90`
- `0x140009d40`
- `0x14000a040`
- `0x14001b350`

## import_xrefs

- `ntoskrnl!HvlInvokeHypercall` at `0x140001b4b`
- `ntoskrnl!HvlInvokeHypercall` at `0x140001b4b`

## pseudocode

```c
__int64 __fastcall WinHvpRangeRepHypercall(
        int a1,
        unsigned __int64 a2,
        void *a3,
        int a4,
        _QWORD *a5,
        __int64 a6,
        _QWORD *a7,
        _QWORD *a8)
{
  void *v9; // rbp
  _QWORD *v10; // r15
  _QWORD *v11; // rdi
  _QWORD *v12; // r14
  unsigned int v13; // r13d
  signed int v14; // ebx
  _QWORD *v15; // rsi
  size_t v16; // r15
  int v17; // ecx
  _QWORD *v18; // rax
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 (__fastcall *v23)(); // rax
  signed int v25; // eax
  void *v26; // rbp
  _BYTE *v27; // rdi
  void *v28; // [rsp+30h] [rbp-98h] BYREF
  __int64 v29; // [rsp+38h] [rbp-90h]
  _BYTE v30[136]; // [rsp+40h] [rbp-88h] BYREF
  unsigned int v32; // [rsp+D8h] [rbp+10h] BYREF
  void *Src; // [rsp+E0h] [rbp+18h]
  size_t Size; // [rsp+E8h] [rbp+20h]

  LODWORD(Size) = a4;
  Src = a3;
  v9 = a3;
  memset(v30, 0, 0x40u);
  v10 = a7;
  v11 = 0;
  v12 = a5;
  v13 = 0;
  v28 = 0;
  v14 = 0;
  *a8 = 0;
  v32 = 0;
  if ( v10 )
  {
    v15 = v10;
    if ( *v10 )
    {
      v26 = (void *)v10[1];
      v28 = v26;
      memmove(v26, Src, (unsigned int)Size);
      if ( v12 )
      {
        v27 = v26;
        v9 = Src;
        v11 = (_QWORD *)((char *)v12 + v27 - (_BYTE *)Src);
      }
      else
      {
        v9 = Src;
      }
    }
  }
  else
  {
    v15 = v30;
  }
  v16 = (unsigned int)Size;
  do
  {
    if ( !a2 )
      break;
    if ( !*v15 )
    {
      WinHvpSetupHypercall((__int64 **)&v28, 0, (__int64)v15);
      memmove(v28, v9, v16);
      if ( v12 )
        v11 = (_QWORD *)((char *)v12 + (_BYTE *)v28 - (_BYTE *)v9);
    }
    v17 = a2;
    if ( a2 >= 0xFFF )
      v17 = 4095;
    v18 = (_QWORD *)*v15;
    if ( *(_BYTE *)(*v15 + 24LL) )
    {
      v25 = WinHvpSlowHypercallRemote(a1, v17, v18[1], v18[2], (__int64)&v32);
      v13 = v32;
      v14 = v25;
    }
    else
    {
      if ( v18[2] )
        v19 = *(_QWORD *)(v18[5] + 40LL);
      else
        v19 = 0;
      if ( v18[1] )
        v20 = *(_QWORD *)(v18[5] + 24LL);
      else
        v20 = 0;
      HIDWORD(v29) = v17 & 0xFFF;
      LODWORD(v29) = (WinHvpNested != 0 ? 0x80000000 : 0) | (unsigned __int16)a1;
      if ( WinHvpConnected )
      {
        v21 = HvlInvokeHypercall(v29, v20, v19);
        v13 = WORD2(v21) & 0xFFF;
        v32 = v13;
        if ( (_WORD)v21 )
          v14 = (unsigned __int16)v21 | 0xC0350000;
        else
          v14 = 0;
      }
      else
      {
        v14 = -1070264320;
      }
    }
    a2 -= v13;
    *a8 += v13;
    if ( v12 )
    {
      v22 = a6 * v13;
      *v12 += v22;
      *v11 += v22;
    }
    v23 = (__int64 (__fastcall *)())v15[7];
    if ( v23 == WinHvpReleaseFallbackBuffers )
    {
      ((void (__fastcall *)(_QWORD))v23)(*v15);
      *v15 = 0;
    }
  }
  while ( v14 >= 0 );
  if ( !a7 && *v15 )
    ((void (*)(void))v15[7])();
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140001a38  mov     dword ptr [rsp+Size], r9d
0x140001a3d  mov     [rsp+Src], r8
0x140001a42  mov     [rsp+arg_0], ecx
0x140001a46  push    rbx
0x140001a47  push    rbp
0x140001a48  push    rsi
0x140001a49  push    rdi
0x140001a4a  push    r12
0x140001a4c  push    r13
0x140001a4e  push    r14
0x140001a50  push    r15
0x140001a52  sub     rsp, 88h
0x140001a59  mov     r12, rdx
0x140001a5c  lea     rcx, [rsp+0C8h+var_88]; void *
0x140001a61  xor     edx, edx; Val
0x140001a63  mov     rbp, r8
0x140001a66  lea     r8d, [rdx+40h]; Size
0x140001a6a  call    memset
0x140001a6f  mov     rax, [rsp+0C8h+arg_38]
0x140001a77  xor     r10d, r10d
0x140001a7a  mov     r15, [rsp+0C8h+arg_30]
0x140001a82  mov     edi, r10d
0x140001a85  mov     r14, [rsp+0C8h+arg_20]
0x140001a8d  mov     r13d, r10d
0x140001a90  mov     [rsp+0C8h+var_98], r10
0x140001a95  mov     ebx, r10d
0x140001a98  mov     [rax], r10
0x140001a9b  mov     [rsp+0C8h+arg_8], r10d
0x140001aa3  test    r15, r15
0x140001aa6  jz      loc_140001C2F
0x140001aac  mov     rsi, r15
0x140001aaf  cmp     [r15], r10
0x140001ab2  jnz     loc_140001C84
0x140001ab8  mov     r15d, dword ptr [rsp+0C8h+Size]
0x140001ac0  test    r12, r12
0x140001ac3  jz      loc_140001BB9
0x140001ac9  cmp     [rsi], r10
0x140001acc  jz      loc_140001BEC
0x140001ad2  mov     ebx, 0FFFh
0x140001ad7  mov     ecx, r12d
0x140001ada  cmp     r12, rbx
0x140001add  jb      short loc_140001AE1
0x140001adf  mov     ecx, ebx
0x140001ae1  mov     rax, [rsi]
0x140001ae4  cmp     [rax+18h], r10b
0x140001ae8  jnz     loc_140001C47
0x140001aee  cmp     [rax+10h], r10
0x140001af2  jz      loc_140001C27
0x140001af8  mov     r8, [rax+28h]
0x140001afc  mov     r8, [r8+28h]
0x140001b00  cmp     [rax+8], r10
0x140001b04  jz      loc_140001C7C
0x140001b0a  mov     rdx, [rax+28h]
0x140001b0e  mov     rdx, [rdx+18h]
0x140001b12  mov     al, cs:WinHvpNested
0x140001b18  and     ecx, ebx
0x140001b1a  movzx   r9d, word ptr [rsp+0C8h+arg_0]
0x140001b23  neg     al
0x140001b25  mov     dword ptr [rsp+0C8h+var_90+4], ecx
0x140001b29  sbb     ecx, ecx
0x140001b2b  and     ecx, 80000000h
0x140001b31  or      r9d, ecx
0x140001b34  cmp     cs:WinHvpConnected, r10b
0x140001b3b  mov     dword ptr [rsp+0C8h+var_90], r9d
0x140001b40  jz      loc_140001CD0
0x140001b46  mov     rcx, [rsp+0C8h+var_90]
0x140001b4b  call    cs:__imp_HvlInvokeHypercall
0x140001b52  nop     dword ptr [rax+rax+00h]
0x140001b57  mov     r13, rax
0x140001b5a  xor     r10d, r10d
0x140001b5d  shr     r13, 20h
0x140001b61  and     r13d, ebx
0x140001b64  mov     [rsp+0C8h+arg_8], r13d
0x140001b6c  test    ax, ax
0x140001b6f  jnz     loc_140001C39
0x140001b75  mov     ebx, r10d
0x140001b78  mov     rcx, [rsp+0C8h+arg_38]
0x140001b80  mov     eax, r13d
0x140001b83  sub     r12, rax
0x140001b86  add     [rcx], rax
0x140001b89  test    r14, r14
0x140001b8c  jz      short loc_140001B9D
0x140001b8e  imul    rax, [rsp+0C8h+arg_28]
0x140001b97  add     [r14], rax
0x140001b9a  add     [rdi], rax
0x140001b9d  mov     rax, [rsi+38h]
0x140001ba1  lea     rcx, WinHvpReleaseFallbackBuffers
0x140001ba8  cmp     rax, rcx
0x140001bab  jz      loc_140001CDA
0x140001bb1  test    ebx, ebx
0x140001bb3  jns     loc_140001AC0
0x140001bb9  cmp     [rsp+0C8h+arg_30], 0
0x140001bc2  jnz     short loc_140001BD5
0x140001bc4  mov     rcx, [rsi]
0x140001bc7  test    rcx, rcx
0x140001bca  jz      short loc_140001BD5
0x140001bcc  mov     rax, [rsi+38h]
0x140001bd0  call    _guard_dispatch_icall
0x140001bd5  mov     eax, ebx
0x140001bd7  add     rsp, 88h
0x140001bde  pop     r15
0x140001be0  pop     r14
0x140001be2  pop     r13
0x140001be4  pop     r12
0x140001be6  pop     rdi
0x140001be7  pop     rsi
0x140001be8  pop     rbp
0x140001be9  pop     rbx
0x140001bea  retn
0x140001bec  mov     r8, rsi
0x140001bef  lea     rcx, [rsp+0C8h+var_98]
0x140001bf4  xor     edx, edx
0x140001bf6  call    WinHvpSetupHypercall
0x140001bfb  mov     rcx, [rsp+0C8h+var_98]; void *
0x140001c00  mov     r8, r15; Size
0x140001c03  mov     rdx, rbp; Src
0x140001c06  call    memmove
0x140001c0b  xor     r10d, r10d
0x140001c0e  test    r14, r14
0x140001c11  jz      loc_140001AD2
0x140001c17  mov     rdi, [rsp+0C8h+var_98]
0x140001c1c  sub     rdi, rbp
0x140001c1f  add     rdi, r14
0x140001c22  jmp     loc_140001AD2
0x140001c27  mov     r8, r10
0x140001c2a  jmp     loc_140001B00
0x140001c2f  lea     rsi, [rsp+0C8h+var_88]
0x140001c34  jmp     loc_140001AB8
0x140001c39  movzx   ebx, ax
0x140001c3c  or      ebx, 0C0350000h
0x140001c42  jmp     loc_140001B78
0x140001c47  mov     r9, [rax+10h]
0x140001c4b  lea     rdx, [rsp+0C8h+arg_8]
0x140001c53  mov     r8, [rax+8]
0x140001c57  mov     [rsp+0C8h+var_A8], rdx
0x140001c5c  mov     edx, ecx
0x140001c5e  mov     ecx, [rsp+0C8h+arg_0]
0x140001c65  call    WinHvpSlowHypercallRemote
0x140001c6a  mov     r13d, [rsp+0C8h+arg_8]
0x140001c72  mov     ebx, eax
0x140001c74  xor     r10d, r10d
0x140001c77  jmp     loc_140001B78
0x140001c7c  mov     rdx, r10
0x140001c7f  jmp     loc_140001B12
0x140001c84  mov     rbp, [r15+8]
0x140001c88  mov     r8d, dword ptr [rsp+0C8h+Size]; Size
0x140001c90  mov     rcx, rbp; void *
0x140001c93  mov     rdx, [rsp+0C8h+Src]; Src
0x140001c9b  mov     [rsp+0C8h+var_98], rbp
0x140001ca0  call    memmove
0x140001ca5  xor     r10d, r10d
0x140001ca8  test    r14, r14
0x140001cab  jz      short loc_140001CC3
0x140001cad  mov     rdi, rbp
0x140001cb0  mov     rbp, [rsp+0C8h+Src]
0x140001cb8  sub     rdi, rbp
0x140001cbb  add     rdi, r14
0x140001cbe  jmp     loc_140001AB8
0x140001cc3  mov     rbp, [rsp+0C8h+Src]
0x140001ccb  jmp     loc_140001AB8
0x140001cd0  mov     ebx, 0C0351000h
0x140001cd5  jmp     loc_140001B78
0x140001cda  mov     rcx, [rsi]
0x140001cdd  call    _guard_dispatch_icall
0x140001ce2  xor     r10d, r10d
0x140001ce5  mov     [rsi], r10
0x140001ce8  jmp     loc_140001BB1
```

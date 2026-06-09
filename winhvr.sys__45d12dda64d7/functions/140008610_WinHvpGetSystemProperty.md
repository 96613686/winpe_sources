# WinHvpGetSystemProperty

- ea: `0x140008610`
- end: `0x1400086bf`
- name: `WinHvpGetSystemProperty`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x140002240`
- `0x140003610`
- `0x140008610`
- `0x140009c90`
- `0x140009d40`
- `0x14000a040`

## pseudocode

```c
__int64 __fastcall WinHvpGetSystemProperty(int a1, const void *a2, unsigned int a3, void *a4, unsigned int Size)
{
  __int64 *v9; // rcx
  int v10; // ebx
  __int64 *v12; // [rsp+20h] [rbp-78h] BYREF
  void *Src; // [rsp+28h] [rbp-70h] BYREF
  _QWORD v14[13]; // [rsp+30h] [rbp-68h] BYREF

  memset(v14, 0, 0x40u);
  v12 = 0;
  Src = 0;
  WinHvpSetupHypercall(&v12, (__int64 *)&Src, (__int64)v14);
  v9 = v12;
  *(_OWORD *)v12 = 0;
  *(_DWORD *)v9 = a1;
  if ( a3 )
    memmove(v9 + 1, a2, a3);
  v10 = WinHvpSimplePoolHypercall_CallViaMacro(v14[0], 123);
  if ( v10 >= 0 )
    memmove(a4, Src, Size);
  ((void (__fastcall *)(_QWORD))v14[7])(v14[0]);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140008610  push    rbx
0x140008612  push    rbp
0x140008613  push    rsi
0x140008614  push    rdi
0x140008615  sub     rsp, 78h
0x140008619  mov     rbp, rdx
0x14000861c  mov     edi, r8d
0x14000861f  xor     edx, edx; Val
0x140008621  mov     ebx, ecx
0x140008623  lea     rcx, [rsp+98h+var_68]; void *
0x140008628  mov     rsi, r9
0x14000862b  lea     r8d, [rdx+40h]; Size
0x14000862f  call    memset
0x140008634  lea     r8, [rsp+98h+var_68]
0x140008639  mov     [rsp+98h+var_78], 0
0x140008642  lea     rdx, [rsp+98h+Src]
0x140008647  mov     [rsp+98h+Src], 0
0x140008650  lea     rcx, [rsp+98h+var_78]
0x140008655  call    WinHvpSetupHypercall
0x14000865a  mov     rcx, [rsp+98h+var_78]
0x14000865f  xorps   xmm0, xmm0
0x140008662  movups  xmmword ptr [rcx], xmm0
0x140008665  mov     [rcx], ebx
0x140008667  test    edi, edi
0x140008669  jz      short loc_14000867A
0x14000866b  mov     r8d, edi; Size
0x14000866e  add     rcx, 8; void *
0x140008672  mov     rdx, rbp; Src
0x140008675  call    memmove
0x14000867a  mov     rcx, [rsp+98h+var_68]
0x14000867f  mov     edx, 7Bh ; '{'
0x140008684  call    WinHvpSimplePoolHypercall_CallViaMacro
0x140008689  mov     ebx, eax
0x14000868b  test    eax, eax
0x14000868d  js      short loc_1400086A4
0x14000868f  mov     r8d, dword ptr [rsp+98h+Size]; Size
0x140008697  mov     rcx, rsi; void *
0x14000869a  mov     rdx, [rsp+98h+Src]; Src
0x14000869f  call    memmove
0x1400086a4  mov     rcx, [rsp+98h+var_68]
0x1400086a9  mov     rax, [rsp+98h+var_30]
0x1400086ae  call    _guard_dispatch_icall
0x1400086b3  mov     eax, ebx
0x1400086b5  add     rsp, 78h
0x1400086b9  pop     rdi
0x1400086ba  pop     rsi
0x1400086bb  pop     rbp
0x1400086bc  pop     rbx
0x1400086bd  retn
```

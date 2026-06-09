# WinHvpSetSystemProperty

- ea: `0x140008750`
- end: `0x1400087e4`
- name: `WinHvpSetSystemProperty`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x140002240`
- `0x140003610`
- `0x140009c90`
- `0x140009d40`
- `0x14000a040`

## pseudocode

```c
__int64 __fastcall WinHvpSetSystemProperty(int a1, const void *a2, unsigned int a3)
{
  _DWORD *v6; // rbx
  _QWORD v8[13]; // [rsp+20h] [rbp-68h] BYREF
  void *v9; // [rsp+A8h] [rbp+20h] BYREF

  memset(v8, 0, 0x40u);
  v9 = 0;
  WinHvpSetupHypercall((__int64 **)&v9, 0, (__int64)v8);
  v6 = v9;
  memset(v9, 0, 0x48u);
  *v6 = a1;
  memmove(v6 + 2, a2, a3);
  LODWORD(v6) = WinHvpSimplePoolHypercall_CallViaMacro(v8[0], 111);
  ((void (__fastcall *)(_QWORD))v8[7])(v8[0]);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140008750  push    rbx
0x140008752  push    rbp
0x140008753  push    rsi
0x140008754  push    rdi
0x140008755  sub     rsp, 68h
0x140008759  mov     rbp, rdx
0x14000875c  mov     esi, r8d
0x14000875f  xor     edx, edx; Val
0x140008761  mov     edi, ecx
0x140008763  lea     rcx, [rsp+88h+var_68]; void *
0x140008768  lea     r8d, [rdx+40h]; Size
0x14000876c  call    memset
0x140008771  lea     r8, [rsp+88h+var_68]
0x140008776  mov     [rsp+88h+arg_18], 0
0x140008782  xor     edx, edx
0x140008784  lea     rcx, [rsp+88h+arg_18]
0x14000878c  call    WinHvpSetupHypercall
0x140008791  mov     rbx, [rsp+88h+arg_18]
0x140008799  xor     edx, edx; Val
0x14000879b  mov     rcx, rbx; void *
0x14000879e  lea     r8d, [rdx+48h]; Size
0x1400087a2  call    memset
0x1400087a7  mov     r8d, esi; Size
0x1400087aa  mov     [rbx], edi
0x1400087ac  lea     rcx, [rbx+8]; void *
0x1400087b0  mov     rdx, rbp; Src
0x1400087b3  call    memmove
0x1400087b8  mov     rcx, [rsp+88h+var_68]
0x1400087bd  mov     edx, 6Fh ; 'o'
0x1400087c2  call    WinHvpSimplePoolHypercall_CallViaMacro
0x1400087c7  mov     rcx, [rsp+88h+var_68]
0x1400087cc  mov     ebx, eax
0x1400087ce  mov     rax, [rsp+88h+var_30]
0x1400087d3  call    _guard_dispatch_icall
0x1400087d8  mov     eax, ebx
0x1400087da  add     rsp, 68h
0x1400087de  pop     rdi
0x1400087df  pop     rsi
0x1400087e0  pop     rbp
0x1400087e1  pop     rbx
0x1400087e2  retn
```

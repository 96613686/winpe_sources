# WinHvReadGpa

- ea: `0x140005140`
- end: `0x14000520b`
- name: `WinHvReadGpa`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x140002240`
- `0x140003610`
- `0x140005140`
- `0x140009c90`
- `0x140009d40`
- `0x14000a040`

## pseudocode

```c
__int64 __fastcall WinHvReadGpa(__int64 a1, int a2, __int64 a3, unsigned int a4, __int64 a5, _QWORD *a6, void *a7)
{
  size_t v8; // rbx
  __int64 *v12; // rcx
  int v13; // edi
  _QWORD *v14; // r9
  __int64 *v15; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v16; // [rsp+28h] [rbp-70h] BYREF
  _QWORD v17[13]; // [rsp+30h] [rbp-68h] BYREF

  v8 = a4;
  v15 = 0;
  v16 = 0;
  memset(v17, 0, 0x40u);
  if ( (unsigned int)v8 > 0x10 )
    return 3221225485LL;
  WinHvpSetupHypercall(&v15, (__int64 *)&v16, (__int64)v17);
  v12 = v15;
  *v15 = a1;
  *((_DWORD *)v12 + 2) = a2;
  *((_DWORD *)v12 + 3) = v8;
  v12[2] = a3;
  v12[3] = a5;
  v13 = WinHvpSimplePoolHypercall_CallViaMacro(v17[0], 83);
  if ( v13 >= 0 )
  {
    v14 = v16;
    *a6 = *v16;
    memmove(a7, v14 + 1, v8);
  }
  ((void (__fastcall *)(_QWORD))v17[7])(v17[0]);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140005140  push    rbx
0x140005142  push    rbp
0x140005143  push    rsi
0x140005144  push    rdi
0x140005145  sub     rsp, 78h
0x140005149  mov     esi, edx
0x14000514b  mov     ebx, r9d
0x14000514e  xor     edx, edx; Val
0x140005150  mov     [rsp+98h+var_78], 0
0x140005159  mov     rdi, r8
0x14000515c  mov     [rsp+98h+var_70], 0
0x140005165  mov     rbp, rcx
0x140005168  lea     rcx, [rsp+98h+var_68]; void *
0x14000516d  lea     r8d, [rdx+40h]; Size
0x140005171  call    memset
0x140005176  cmp     ebx, 10h
0x140005179  jbe     short loc_140005182
0x14000517b  mov     eax, 0C000000Dh
0x140005180  jmp     short loc_140005201
0x140005182  lea     r8, [rsp+98h+var_68]
0x140005187  lea     rdx, [rsp+98h+var_70]
0x14000518c  lea     rcx, [rsp+98h+var_78]
0x140005191  call    WinHvpSetupHypercall
0x140005196  mov     rcx, [rsp+98h+var_78]
0x14000519b  mov     edx, 53h ; 'S'
0x1400051a0  mov     rax, [rsp+98h+arg_20]
0x1400051a8  mov     [rcx], rbp
0x1400051ab  mov     [rcx+8], esi
0x1400051ae  mov     [rcx+0Ch], ebx
0x1400051b1  mov     [rcx+10h], rdi
0x1400051b5  mov     [rcx+18h], rax
0x1400051b9  mov     rcx, [rsp+98h+var_68]
0x1400051be  call    WinHvpSimplePoolHypercall_CallViaMacro
0x1400051c3  mov     edi, eax
0x1400051c5  test    eax, eax
0x1400051c7  js      short loc_1400051F0
0x1400051c9  mov     r9, [rsp+98h+var_70]
0x1400051ce  mov     r8, rbx; Size
0x1400051d1  mov     rcx, [rsp+98h+arg_28]
0x1400051d9  mov     rdx, [r9]
0x1400051dc  mov     [rcx], rdx
0x1400051df  lea     rdx, [r9+8]; Src
0x1400051e3  mov     rcx, [rsp+98h+arg_30]; void *
0x1400051eb  call    memmove
0x1400051f0  mov     rcx, [rsp+98h+var_68]
0x1400051f5  mov     rax, [rsp+98h+var_30]
0x1400051fa  call    _guard_dispatch_icall
0x1400051ff  mov     eax, edi
0x140005201  add     rsp, 78h
0x140005205  pop     rdi
0x140005206  pop     rsi
0x140005207  pop     rbp
0x140005208  pop     rbx
0x140005209  retn
```

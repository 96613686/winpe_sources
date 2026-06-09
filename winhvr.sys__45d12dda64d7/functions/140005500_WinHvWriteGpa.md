# WinHvWriteGpa

- ea: `0x140005500`
- end: `0x1400055cb`
- name: `WinHvWriteGpa`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x140002240`
- `0x140003610`
- `0x140005500`
- `0x140009c90`
- `0x140009d40`
- `0x14000a040`

## pseudocode

```c
__int64 __fastcall WinHvWriteGpa(__int64 a1, int a2, __int64 a3, unsigned int a4, __int64 a5, void *Src, _QWORD *a7)
{
  size_t v8; // rbx
  __int64 *v12; // rcx
  int v13; // ebx
  __int64 *v14; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v15; // [rsp+28h] [rbp-70h] BYREF
  _QWORD v16[13]; // [rsp+30h] [rbp-68h] BYREF

  v8 = a4;
  v14 = 0;
  v15 = 0;
  memset(v16, 0, 0x40u);
  if ( (unsigned int)v8 > 0x10 )
    return 3221225485LL;
  WinHvpSetupHypercall(&v14, (__int64 *)&v15, (__int64)v16);
  v12 = v14;
  *v14 = a1;
  *((_DWORD *)v12 + 2) = a2;
  *((_DWORD *)v12 + 3) = v8;
  v12[2] = a3;
  v12[3] = a5;
  memmove(v12 + 4, Src, v8);
  v13 = WinHvpSimplePoolHypercall_CallViaMacro(v16[0], 84);
  if ( v13 >= 0 )
    *a7 = *v15;
  ((void (__fastcall *)(_QWORD))v16[7])(v16[0]);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140005500  push    rbx
0x140005502  push    rbp
0x140005503  push    rsi
0x140005504  push    rdi
0x140005505  sub     rsp, 78h
0x140005509  mov     esi, edx
0x14000550b  mov     ebx, r9d
0x14000550e  xor     edx, edx; Val
0x140005510  mov     [rsp+98h+var_78], 0
0x140005519  mov     rdi, r8
0x14000551c  mov     [rsp+98h+var_70], 0
0x140005525  mov     rbp, rcx
0x140005528  lea     rcx, [rsp+98h+var_68]; void *
0x14000552d  lea     r8d, [rdx+40h]; Size
0x140005531  call    memset
0x140005536  cmp     ebx, 10h
0x140005539  jbe     short loc_140005542
0x14000553b  mov     eax, 0C000000Dh
0x140005540  jmp     short loc_1400055C1
0x140005542  lea     r8, [rsp+98h+var_68]
0x140005547  lea     rdx, [rsp+98h+var_70]
0x14000554c  lea     rcx, [rsp+98h+var_78]
0x140005551  call    WinHvpSetupHypercall
0x140005556  mov     rcx, [rsp+98h+var_78]
0x14000555b  mov     r8, rbx; Size
0x14000555e  mov     rax, [rsp+98h+arg_20]
0x140005566  mov     rdx, [rsp+98h+Src]; Src
0x14000556e  mov     [rcx], rbp
0x140005571  mov     [rcx+8], esi
0x140005574  mov     [rcx+0Ch], ebx
0x140005577  mov     [rcx+10h], rdi
0x14000557b  mov     [rcx+18h], rax
0x14000557f  add     rcx, 20h ; ' '; void *
0x140005583  call    memmove
0x140005588  mov     rcx, [rsp+98h+var_68]
0x14000558d  mov     edx, 54h ; 'T'
0x140005592  call    WinHvpSimplePoolHypercall_CallViaMacro
0x140005597  mov     ebx, eax
0x140005599  test    eax, eax
0x14000559b  js      short loc_1400055B0
0x14000559d  mov     rcx, [rsp+98h+var_70]
0x1400055a2  mov     rdx, [rcx]
0x1400055a5  mov     rcx, [rsp+98h+arg_30]
0x1400055ad  mov     [rcx], rdx
0x1400055b0  mov     rcx, [rsp+98h+var_68]
0x1400055b5  mov     rax, [rsp+98h+var_30]
0x1400055ba  call    _guard_dispatch_icall
0x1400055bf  mov     eax, ebx
0x1400055c1  add     rsp, 78h
0x1400055c5  pop     rdi
0x1400055c6  pop     rsi
0x1400055c7  pop     rbp
0x1400055c8  pop     rbx
0x1400055c9  retn
```

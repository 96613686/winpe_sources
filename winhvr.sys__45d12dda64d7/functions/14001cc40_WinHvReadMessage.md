# WinHvReadMessage

- ea: `0x14001cc40`
- end: `0x14001ccfc`
- name: `WinHvReadMessage`
- size: `188`
- prototype: `__int64 __fastcall(int, int, int, int, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x140002240`
- `0x140003610`
- `0x140009c90`
- `0x140009d40`
- `0x14000a040`
- `0x14001cc40`

## pseudocode

```c
__int64 __fastcall WinHvReadMessage(int a1, _DWORD *a2, _DWORD *a3, _DWORD *a4, void *a5)
{
  int v9; // ebx
  _DWORD *v10; // rdx
  __int64 *v12; // [rsp+20h] [rbp-78h] BYREF
  _DWORD *v13; // [rsp+28h] [rbp-70h] BYREF
  _QWORD v14[13]; // [rsp+30h] [rbp-68h] BYREF

  v12 = 0;
  v13 = 0;
  memset(v14, 0, 0x40u);
  WinHvpSetupHypercall(&v12, (__int64 *)&v13, (__int64)v14);
  *(_DWORD *)v12 = a1;
  v9 = WinHvpSimplePoolHypercall_CallViaMacro(v14[0], 304);
  if ( v9 >= 0 )
  {
    v10 = v13;
    if ( v13[2] > 0xF0u )
      __fastfail(0x3Au);
    *a2 = *v13;
    *a3 = v10[1];
    *a4 = v10[2];
    memmove(a5, v10 + 4, (unsigned int)v10[2]);
  }
  ((void (__fastcall *)(_QWORD))v14[7])(v14[0]);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14001cc40  push    rbx
0x14001cc42  push    rsi
0x14001cc43  push    rdi
0x14001cc44  push    r14
0x14001cc46  sub     rsp, 78h
0x14001cc4a  mov     r14, rdx
0x14001cc4d  mov     [rsp+98h+var_78], 0
0x14001cc56  xor     edx, edx; Val
0x14001cc58  mov     [rsp+98h+var_70], 0
0x14001cc61  mov     rsi, r8
0x14001cc64  mov     ebx, ecx
0x14001cc66  lea     rcx, [rsp+98h+var_68]; void *
0x14001cc6b  mov     rdi, r9
0x14001cc6e  lea     r8d, [rdx+40h]; Size
0x14001cc72  call    memset
0x14001cc77  lea     r8, [rsp+98h+var_68]
0x14001cc7c  lea     rdx, [rsp+98h+var_70]
0x14001cc81  lea     rcx, [rsp+98h+var_78]
0x14001cc86  call    WinHvpSetupHypercall
0x14001cc8b  mov     rax, [rsp+98h+var_78]
0x14001cc90  mov     edx, 130h
0x14001cc95  mov     [rax], ebx
0x14001cc97  mov     rcx, [rsp+98h+var_68]
0x14001cc9c  call    WinHvpSimplePoolHypercall_CallViaMacro
0x14001cca1  mov     ebx, eax
0x14001cca3  test    eax, eax
0x14001cca5  js      short loc_14001CCE0
0x14001cca7  mov     rdx, [rsp+98h+var_70]
0x14001ccac  cmp     dword ptr [rdx+8], 0F0h
0x14001ccb3  jbe     short loc_14001CCBC
0x14001ccb5  mov     ecx, 3Ah ; ':'
0x14001ccba  int     29h; Win8: RtlFailFast(ecx)
0x14001ccbc  mov     eax, [rdx]
0x14001ccbe  mov     rcx, [rsp+98h+arg_20]; void *
0x14001ccc6  mov     [r14], eax
0x14001ccc9  mov     eax, [rdx+4]
0x14001cccc  mov     [rsi], eax
0x14001ccce  mov     eax, [rdx+8]
0x14001ccd1  mov     [rdi], eax
0x14001ccd3  mov     r8d, [rdx+8]; Size
0x14001ccd7  add     rdx, 10h; Src
0x14001ccdb  call    memmove
0x14001cce0  mov     rcx, [rsp+98h+var_68]
0x14001cce5  mov     rax, [rsp+98h+var_30]
0x14001ccea  call    _guard_dispatch_icall
0x14001ccef  mov     eax, ebx
0x14001ccf1  add     rsp, 78h
0x14001ccf5  pop     r14
0x14001ccf7  pop     rdi
0x14001ccf8  pop     rsi
0x14001ccf9  pop     rbx
0x14001ccfa  retn
```

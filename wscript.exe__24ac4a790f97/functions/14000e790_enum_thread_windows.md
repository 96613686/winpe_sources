# enum_thread_windows

- ea: `0x14000e790`
- end: `0x14000e865`
- name: `enum_thread_windows`
- size: `213`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000e790`
- `0x1400175a0`

## import_xrefs

- `USER32!GetClassNameA` at `0x14000e7d8`
- `USER32!GetClassNameA` at `0x14000e7d8`
- `USER32!PostMessageA` at `0x14000e826`
- `USER32!PostMessageA` at `0x14000e83b`
- `USER32!PostMessageA` at `0x14000e826`
- `USER32!PostMessageA` at `0x14000e83b`
- `USER32!IsWindowVisible` at `0x14000e7b4`
- `USER32!IsWindowVisible` at `0x14000e7b4`
- `USER32!GetParent` at `0x14000e80b`
- `USER32!GetParent` at `0x14000e80b`

## pseudocode

```c
__int64 __fastcall enum_thread_windows(HWND a1, _DWORD *a2)
{
  HWND Parent; // rdi
  CHAR ClassName[8]; // [rsp+20h] [rbp-18h] BYREF

  if ( IsWindowVisible(a1) )
  {
    Parent = a1;
    if ( a1 )
    {
      while ( GetClassNameA(Parent, ClassName, 5) != 3
           || ClassName[3]
           || ((ClassName[0] - 73) & 0xDF) != 0
           || ((ClassName[1] - 77) & 0xDF) != 0
           || ((ClassName[2] - 69) & 0xDF) != 0 )
      {
        Parent = GetParent(Parent);
        if ( !Parent )
          goto LABEL_9;
      }
    }
    else
    {
LABEL_9:
      PostMessageA(a1, 0x10u, 0, 0);
      PostMessageA(a1, 0x100u, 0xDu, 0);
      ++*a2;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14000e790  mov     [rsp+arg_10], rbx
0x14000e795  mov     [rsp+arg_18], rsi
0x14000e79a  push    rdi
0x14000e79b  sub     rsp, 30h
0x14000e79f  mov     rax, cs:__security_cookie
0x14000e7a6  xor     rax, rsp
0x14000e7a9  mov     [rsp+38h+var_10], rax
0x14000e7ae  mov     rsi, rdx
0x14000e7b1  mov     rbx, rcx
0x14000e7b4  call    cs:__imp_IsWindowVisible
0x14000e7ba  test    eax, eax
0x14000e7bc  jz      loc_14000E843
0x14000e7c2  mov     rdi, rbx
0x14000e7c5  test    rbx, rbx
0x14000e7c8  jz      short loc_14000E819
0x14000e7ca  mov     r8d, 5; nMaxCount
0x14000e7d0  lea     rdx, [rsp+38h+ClassName]; lpClassName
0x14000e7d5  mov     rcx, rdi; hWnd
0x14000e7d8  call    cs:__imp_GetClassNameA
0x14000e7de  cmp     eax, 3
0x14000e7e1  jnz     short loc_14000E808
0x14000e7e3  cmp     [rsp+38h+var_15], 0
0x14000e7e8  jnz     short loc_14000E808
0x14000e7ea  mov     al, [rsp+38h+ClassName]
0x14000e7ee  sub     al, 49h ; 'I'
0x14000e7f0  test    al, 0DFh
0x14000e7f2  jnz     short loc_14000E808
0x14000e7f4  mov     al, [rsp+38h+var_17]
0x14000e7f8  sub     al, 4Dh ; 'M'
0x14000e7fa  test    al, 0DFh
0x14000e7fc  jnz     short loc_14000E808
0x14000e7fe  mov     al, [rsp+38h+var_16]
0x14000e802  sub     al, 45h ; 'E'
0x14000e804  test    al, 0DFh
0x14000e806  jz      short loc_14000E843
0x14000e808  mov     rcx, rdi; hWnd
0x14000e80b  call    cs:__imp_GetParent
0x14000e811  mov     rdi, rax
0x14000e814  test    rax, rax
0x14000e817  jnz     short loc_14000E7CA
0x14000e819  xor     r9d, r9d; lParam
0x14000e81c  xor     r8d, r8d; wParam
0x14000e81f  mov     rcx, rbx; hWnd
0x14000e822  lea     edx, [r9+10h]; Msg
0x14000e826  call    cs:__imp_PostMessageA
0x14000e82c  xor     r9d, r9d; lParam
0x14000e82f  mov     edx, 100h; Msg
0x14000e834  mov     rcx, rbx; hWnd
0x14000e837  lea     r8d, [r9+0Dh]; wParam
0x14000e83b  call    cs:__imp_PostMessageA
0x14000e841  inc     dword ptr [rsi]
0x14000e843  mov     eax, 1
0x14000e848  mov     rcx, [rsp+38h+var_10]
0x14000e84d  xor     rcx, rsp; StackCookie
0x14000e850  call    __security_check_cookie
0x14000e855  mov     rbx, [rsp+38h+arg_10]
0x14000e85a  mov     rsi, [rsp+38h+arg_18]
0x14000e85f  add     rsp, 30h
0x14000e863  pop     rdi
0x14000e864  retn
```

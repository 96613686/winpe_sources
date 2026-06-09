# DllGetClassObject

- ea: `0x1800c6d70`
- end: `0x1800c6e64`
- name: `DllGetClassObject`
- size: `244`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180096dec`
- `0x18009904c`
- `0x1800c6d70`
- `0x18020ca70`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v6; // rax
  __int64 v7; // rax
  int i; // ecx
  char *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rax
  void *v12; // rax

  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = *(_QWORD *)&riid->Data1;
  if ( !*(_QWORD *)&riid->Data1 )
    v6 = *(_QWORD *)riid->Data4 - 0x46000000000000C0LL;
  if ( !v6 )
    goto LABEL_10;
  v7 = *(_QWORD *)&riid->Data1 - 1LL;
  if ( *(_QWORD *)&riid->Data1 == 1 )
    v7 = *(_QWORD *)riid->Data4 - 0x46000000000000C0LL;
  if ( v7 )
    return -2147467262;
LABEL_10:
  for ( i = 0; ; ++i )
  {
    if ( i >= 1 )
      return -2147221231;
    v9 = (char *)&off_180282000 + 16 * i;
    v10 = **(_QWORD **)v9 - *(_QWORD *)&rclsid->Data1;
    if ( !v10 )
      v10 = *(_QWORD *)(*(_QWORD *)v9 + 8LL) - *(_QWORD *)rclsid->Data4;
    if ( !v10 )
      break;
  }
  v11 = sub_18009904C(24);
  if ( v11 )
  {
    v12 = (void *)sub_180096DEC(v11, v9);
    *ppv = v12;
    if ( v12 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 8LL))(v12);
      return 0;
    }
  }
  else
  {
    *ppv = 0;
  }
  return -2147024882;
}

```

## disassembly

```asm
0x1800c6d70  mov     [rsp+arg_0], rbx
0x1800c6d75  push    rdi
0x1800c6d76  sub     rsp, 20h
0x1800c6d7a  mov     rbx, r8
0x1800c6d7d  mov     r8, rcx
0x1800c6d80  test    rbx, rbx
0x1800c6d83  jnz     short loc_1800C6D8F
0x1800c6d85  mov     eax, 80004003h
0x1800c6d8a  jmp     loc_1800C6E58
0x1800c6d8f  mov     qword ptr [rbx], 0
0x1800c6d96  mov     rax, [rdx]
0x1800c6d99  sub     rax, cs:qword_180219FD0
0x1800c6da0  jnz     short loc_1800C6DAD
0x1800c6da2  mov     rax, [rdx+8]
0x1800c6da6  sub     rax, cs:qword_180219FD8
0x1800c6dad  test    rax, rax
0x1800c6db0  jz      short loc_1800C6DD8
0x1800c6db2  mov     rax, [rdx]
0x1800c6db5  sub     rax, cs:qword_180219FE0
0x1800c6dbc  jnz     short loc_1800C6DC9
0x1800c6dbe  mov     rax, [rdx+8]
0x1800c6dc2  sub     rax, cs:qword_180219FE8
0x1800c6dc9  test    rax, rax
0x1800c6dcc  jz      short loc_1800C6DD8
0x1800c6dce  mov     eax, 80004002h
0x1800c6dd3  jmp     loc_1800C6E58
0x1800c6dd8  xor     ecx, ecx
0x1800c6dda  cmp     ecx, 1
0x1800c6ddd  jge     short loc_1800C6E53
0x1800c6ddf  lea     rdx, off_180282000
0x1800c6de6  movsxd  rdi, ecx
0x1800c6de9  shl     rdi, 4
0x1800c6ded  add     rdi, rdx
0x1800c6df0  mov     rdx, [rdi]
0x1800c6df3  mov     rax, [rdx]
0x1800c6df6  sub     rax, [r8]
0x1800c6df9  jnz     short loc_1800C6E03
0x1800c6dfb  mov     rax, [rdx+8]
0x1800c6dff  sub     rax, [r8+8]
0x1800c6e03  test    rax, rax
0x1800c6e06  jz      short loc_1800C6E0C
0x1800c6e08  inc     ecx
0x1800c6e0a  jmp     short loc_1800C6DDA
0x1800c6e0c  mov     ecx, 18h
0x1800c6e11  call    sub_18009904C
0x1800c6e16  test    rax, rax
0x1800c6e19  jz      short loc_1800C6E45
0x1800c6e1b  mov     rdx, rdi
0x1800c6e1e  mov     rcx, rax
0x1800c6e21  call    sub_180096DEC
0x1800c6e26  mov     [rbx], rax
0x1800c6e29  mov     rdx, rax
0x1800c6e2c  test    rax, rax
0x1800c6e2f  jz      short loc_1800C6E4C
0x1800c6e31  mov     rcx, [rax]
0x1800c6e34  mov     rax, [rcx+8]
0x1800c6e38  mov     rcx, rdx
0x1800c6e3b  call    cs:__guard_dispatch_icall_fptr
0x1800c6e41  xor     eax, eax
0x1800c6e43  jmp     short loc_1800C6E58
0x1800c6e45  mov     qword ptr [rbx], 0
0x1800c6e4c  mov     eax, 8007000Eh
0x1800c6e51  jmp     short loc_1800C6E58
0x1800c6e53  mov     eax, 80040111h
0x1800c6e58  mov     rbx, [rsp+28h+arg_0]
0x1800c6e5d  add     rsp, 20h
0x1800c6e61  pop     rdi
0x1800c6e62  retn
```

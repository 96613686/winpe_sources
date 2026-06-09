# DllGetClassObject

- ea: `0x180038ce0`
- end: `0x180038dd4`
- name: `DllGetClassObject`
- size: `244`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180010bec`
- `0x1800386fc`
- `0x180038ce0`
- `0x1800932f0`

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
    if ( i >= 2 )
      return -2147221231;
    v9 = (char *)&off_1800E0000 + 16 * i;
    v10 = **(_QWORD **)v9 - *(_QWORD *)&rclsid->Data1;
    if ( !v10 )
      v10 = *(_QWORD *)(*(_QWORD *)v9 + 8LL) - *(_QWORD *)rclsid->Data4;
    if ( !v10 )
      break;
  }
  v11 = sub_180010BEC(24);
  if ( v11 )
  {
    v12 = (void *)sub_1800386FC(v11, v9);
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
0x180038ce0  mov     [rsp+arg_0], rbx
0x180038ce5  push    rdi
0x180038ce6  sub     rsp, 20h
0x180038cea  mov     rbx, r8
0x180038ced  mov     r8, rcx
0x180038cf0  test    rbx, rbx
0x180038cf3  jnz     short loc_180038CFF
0x180038cf5  mov     eax, 80004003h
0x180038cfa  jmp     loc_180038DC8
0x180038cff  mov     qword ptr [rbx], 0
0x180038d06  mov     rax, [rdx]
0x180038d09  sub     rax, cs:qword_18009F1D0
0x180038d10  jnz     short loc_180038D1D
0x180038d12  mov     rax, [rdx+8]
0x180038d16  sub     rax, cs:qword_18009F1D8
0x180038d1d  test    rax, rax
0x180038d20  jz      short loc_180038D48
0x180038d22  mov     rax, [rdx]
0x180038d25  sub     rax, cs:qword_18009F1E0
0x180038d2c  jnz     short loc_180038D39
0x180038d2e  mov     rax, [rdx+8]
0x180038d32  sub     rax, cs:qword_18009F1E8
0x180038d39  test    rax, rax
0x180038d3c  jz      short loc_180038D48
0x180038d3e  mov     eax, 80004002h
0x180038d43  jmp     loc_180038DC8
0x180038d48  xor     ecx, ecx
0x180038d4a  cmp     ecx, 2
0x180038d4d  jge     short loc_180038DC3
0x180038d4f  lea     rdx, off_1800E0000
0x180038d56  movsxd  rdi, ecx
0x180038d59  shl     rdi, 4
0x180038d5d  add     rdi, rdx
0x180038d60  mov     rdx, [rdi]
0x180038d63  mov     rax, [rdx]
0x180038d66  sub     rax, [r8]
0x180038d69  jnz     short loc_180038D73
0x180038d6b  mov     rax, [rdx+8]
0x180038d6f  sub     rax, [r8+8]
0x180038d73  test    rax, rax
0x180038d76  jz      short loc_180038D7C
0x180038d78  inc     ecx
0x180038d7a  jmp     short loc_180038D4A
0x180038d7c  mov     ecx, 18h
0x180038d81  call    sub_180010BEC
0x180038d86  test    rax, rax
0x180038d89  jz      short loc_180038DB5
0x180038d8b  mov     rdx, rdi
0x180038d8e  mov     rcx, rax
0x180038d91  call    sub_1800386FC
0x180038d96  mov     [rbx], rax
0x180038d99  mov     rdx, rax
0x180038d9c  test    rax, rax
0x180038d9f  jz      short loc_180038DBC
0x180038da1  mov     rcx, [rax]
0x180038da4  mov     rax, [rcx+8]
0x180038da8  mov     rcx, rdx
0x180038dab  call    cs:__guard_dispatch_icall_fptr
0x180038db1  xor     eax, eax
0x180038db3  jmp     short loc_180038DC8
0x180038db5  mov     qword ptr [rbx], 0
0x180038dbc  mov     eax, 8007000Eh
0x180038dc1  jmp     short loc_180038DC8
0x180038dc3  mov     eax, 80040111h
0x180038dc8  mov     rbx, [rsp+28h+arg_0]
0x180038dcd  add     rsp, 20h
0x180038dd1  pop     rdi
0x180038dd2  retn
```

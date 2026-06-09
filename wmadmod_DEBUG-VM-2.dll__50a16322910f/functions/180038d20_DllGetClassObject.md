# DllGetClassObject

- ea: `0x180038d20`
- end: `0x180038e14`
- name: `DllGetClassObject`
- size: `244`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180010bec`
- `0x18003873c`
- `0x180038d20`
- `0x180093330`

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
    v12 = (void *)sub_18003873C(v11, v9);
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
0x180038d20  mov     [rsp+arg_0], rbx
0x180038d25  push    rdi
0x180038d26  sub     rsp, 20h
0x180038d2a  mov     rbx, r8
0x180038d2d  mov     r8, rcx
0x180038d30  test    rbx, rbx
0x180038d33  jnz     short loc_180038D3F
0x180038d35  mov     eax, 80004003h
0x180038d3a  jmp     loc_180038E08
0x180038d3f  mov     qword ptr [rbx], 0
0x180038d46  mov     rax, [rdx]
0x180038d49  sub     rax, cs:qword_18009F1D0
0x180038d50  jnz     short loc_180038D5D
0x180038d52  mov     rax, [rdx+8]
0x180038d56  sub     rax, cs:qword_18009F1D8
0x180038d5d  test    rax, rax
0x180038d60  jz      short loc_180038D88
0x180038d62  mov     rax, [rdx]
0x180038d65  sub     rax, cs:qword_18009F1E0
0x180038d6c  jnz     short loc_180038D79
0x180038d6e  mov     rax, [rdx+8]
0x180038d72  sub     rax, cs:qword_18009F1E8
0x180038d79  test    rax, rax
0x180038d7c  jz      short loc_180038D88
0x180038d7e  mov     eax, 80004002h
0x180038d83  jmp     loc_180038E08
0x180038d88  xor     ecx, ecx
0x180038d8a  cmp     ecx, 2
0x180038d8d  jge     short loc_180038E03
0x180038d8f  lea     rdx, off_1800E0000
0x180038d96  movsxd  rdi, ecx
0x180038d99  shl     rdi, 4
0x180038d9d  add     rdi, rdx
0x180038da0  mov     rdx, [rdi]
0x180038da3  mov     rax, [rdx]
0x180038da6  sub     rax, [r8]
0x180038da9  jnz     short loc_180038DB3
0x180038dab  mov     rax, [rdx+8]
0x180038daf  sub     rax, [r8+8]
0x180038db3  test    rax, rax
0x180038db6  jz      short loc_180038DBC
0x180038db8  inc     ecx
0x180038dba  jmp     short loc_180038D8A
0x180038dbc  mov     ecx, 18h
0x180038dc1  call    sub_180010BEC
0x180038dc6  test    rax, rax
0x180038dc9  jz      short loc_180038DF5
0x180038dcb  mov     rdx, rdi
0x180038dce  mov     rcx, rax
0x180038dd1  call    sub_18003873C
0x180038dd6  mov     [rbx], rax
0x180038dd9  mov     rdx, rax
0x180038ddc  test    rax, rax
0x180038ddf  jz      short loc_180038DFC
0x180038de1  mov     rcx, [rax]
0x180038de4  mov     rax, [rcx+8]
0x180038de8  mov     rcx, rdx
0x180038deb  call    cs:__guard_dispatch_icall_fptr
0x180038df1  xor     eax, eax
0x180038df3  jmp     short loc_180038E08
0x180038df5  mov     qword ptr [rbx], 0
0x180038dfc  mov     eax, 8007000Eh
0x180038e01  jmp     short loc_180038E08
0x180038e03  mov     eax, 80040111h
0x180038e08  mov     rbx, [rsp+28h+arg_0]
0x180038e0d  add     rsp, 20h
0x180038e11  pop     rdi
0x180038e12  retn
```

# common_exit

- ea: `0x10042a1e8`
- end: `0x10042a2ad`
- name: `common_exit`
- size: `197`
- prototype: `__int64 __fastcall(UINT uExitCode)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10042a39c`
- `0x10042a3b0`

## callees

- `0x10042a0d4`
- `0x10042a1e8`
- `0x10042a2b4`
- `0x10042a314`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x10042a20f`
- `KERNEL32!GetModuleHandleW` at `0x10042a20f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall common_exit(UINT uExitCode, int a2, int a3)
{
  HMODULE ModuleHandleW; // rax
  char *v5; // rcx
  __int64 result; // rax
  _BYTE v7[4]; // [rsp+20h] [rbp-30h] BYREF
  int v8; // [rsp+24h] [rbp-2Ch] BYREF
  int v9; // [rsp+28h] [rbp-28h] BYREF
  __int64 v10; // [rsp+30h] [rbp-20h]
  _QWORD v11[3]; // [rsp+38h] [rbp-18h] BYREF
  int v12; // [rsp+68h] [rbp+18h] BYREF
  int v13; // [rsp+70h] [rbp+20h] BYREF
  char v14; // [rsp+78h] [rbp+28h] BYREF

  v13 = a3;
  v12 = a2;
  v10 = -2;
  if ( !a3 )
  {
    ModuleHandleW = GetModuleHandleW(0);
    if ( ModuleHandleW )
    {
      if ( *(_WORD *)ModuleHandleW == 23117 )
      {
        v5 = (char *)ModuleHandleW + *((int *)ModuleHandleW + 15);
        if ( *(_DWORD *)v5 == 17744 && *((_WORD *)v5 + 12) == 523 && *((_DWORD *)v5 + 33) > 0xEu && *((_DWORD *)v5 + 62) )
          try_cor_exit_process(uExitCode);
      }
    }
  }
  v14 = 0;
  v11[0] = &v12;
  v11[1] = &v13;
  v11[2] = &v14;
  v8 = 2;
  v9 = 2;
  result = _crt_seh_guarded_call_void_::operator()__lambda_d80eeec6fff315bfe5c115232f3240e3___lambda_6e4b09c48022b2350581041d5f6b0c4c_____lambda_2358e3775559c9db80273638284d5e45___(
             v7,
             &v9,
             v11,
             &v8);
  if ( !v13 )
    exit_or_terminate_process(uExitCode);
  return result;
}

```

## disassembly

```asm
0x10042a1e8  mov     [rsp-8+arg_10], r8d
0x10042a1ed  mov     [rsp-8+arg_8], edx
0x10042a1f1  push    rbp
0x10042a1f2  mov     rbp, rsp
0x10042a1f5  sub     rsp, 50h
0x10042a1f9  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x10042a201  mov     [rsp+50h+arg_0], rbx
0x10042a206  mov     ebx, ecx
0x10042a208  test    r8d, r8d
0x10042a20b  jnz     short loc_10042A257
0x10042a20d  xor     ecx, ecx; lpModuleName
0x10042a20f  call    cs:__imp_GetModuleHandleW
0x10042a215  test    rax, rax
0x10042a218  jz      short loc_10042A257
0x10042a21a  mov     ecx, 5A4Dh
0x10042a21f  cmp     [rax], cx
0x10042a222  jnz     short loc_10042A257
0x10042a224  movsxd  rcx, dword ptr [rax+3Ch]
0x10042a228  add     rcx, rax
0x10042a22b  cmp     dword ptr [rcx], 4550h
0x10042a231  jnz     short loc_10042A257
0x10042a233  mov     eax, 20Bh
0x10042a238  cmp     [rcx+18h], ax
0x10042a23c  jnz     short loc_10042A257
0x10042a23e  cmp     dword ptr [rcx+84h], 0Eh
0x10042a245  jbe     short loc_10042A257
0x10042a247  cmp     dword ptr [rcx+0F8h], 0
0x10042a24e  jz      short loc_10042A257
0x10042a250  mov     ecx, ebx
0x10042a252  call    try_cor_exit_process
0x10042a257  mov     [rbp+arg_18], 0
0x10042a25b  lea     rax, [rbp+arg_8]
0x10042a25f  mov     [rbp+var_18], rax
0x10042a263  lea     rax, [rbp+arg_10]
0x10042a267  mov     [rbp+var_10], rax
0x10042a26b  lea     rax, [rbp+arg_18]
0x10042a26f  mov     [rbp+var_8], rax
0x10042a273  mov     eax, 2
0x10042a278  mov     [rbp+var_2C], eax
0x10042a27b  mov     [rbp+var_28], eax
0x10042a27e  lea     r9, [rbp+var_2C]
0x10042a282  lea     r8, [rbp+var_18]
0x10042a286  lea     rdx, [rbp+var_28]
0x10042a28a  lea     rcx, [rbp+var_30]
0x10042a28e  call    __crt_seh_guarded_call_void___operator____lambda_d80eeec6fff315bfe5c115232f3240e3___lambda_6e4b09c48022b2350581041d5f6b0c4c_____lambda_2358e3775559c9db80273638284d5e45___
0x10042a293  nop
0x10042a294  cmp     [rbp+arg_10], 0
0x10042a298  jz      short loc_10042A2A5
0x10042a29a  mov     rbx, [rsp+50h+arg_0]
0x10042a29f  add     rsp, 50h
0x10042a2a3  pop     rbp
0x10042a2a4  retn
0x10042a2a5  mov     ecx, ebx; uExitCode
0x10042a2a7  call    exit_or_terminate_process
```

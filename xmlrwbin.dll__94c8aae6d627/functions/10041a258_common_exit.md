# common_exit

- ea: `0x10041a258`
- end: `0x10041a31d`
- name: `common_exit`
- size: `197`
- prototype: `__int64 __fastcall(UINT uExitCode)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10041a40c`
- `0x10041a420`

## callees

- `0x10041a144`
- `0x10041a258`
- `0x10041a324`
- `0x10041a384`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x10041a27f`
- `KERNEL32!GetModuleHandleW` at `0x10041a27f`

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
0x10041a258  mov     [rsp-8+arg_10], r8d
0x10041a25d  mov     [rsp-8+arg_8], edx
0x10041a261  push    rbp
0x10041a262  mov     rbp, rsp
0x10041a265  sub     rsp, 50h
0x10041a269  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x10041a271  mov     [rsp+50h+arg_0], rbx
0x10041a276  mov     ebx, ecx
0x10041a278  test    r8d, r8d
0x10041a27b  jnz     short loc_10041A2C7
0x10041a27d  xor     ecx, ecx; lpModuleName
0x10041a27f  call    cs:__imp_GetModuleHandleW
0x10041a285  test    rax, rax
0x10041a288  jz      short loc_10041A2C7
0x10041a28a  mov     ecx, 5A4Dh
0x10041a28f  cmp     [rax], cx
0x10041a292  jnz     short loc_10041A2C7
0x10041a294  movsxd  rcx, dword ptr [rax+3Ch]
0x10041a298  add     rcx, rax
0x10041a29b  cmp     dword ptr [rcx], 4550h
0x10041a2a1  jnz     short loc_10041A2C7
0x10041a2a3  mov     eax, 20Bh
0x10041a2a8  cmp     [rcx+18h], ax
0x10041a2ac  jnz     short loc_10041A2C7
0x10041a2ae  cmp     dword ptr [rcx+84h], 0Eh
0x10041a2b5  jbe     short loc_10041A2C7
0x10041a2b7  cmp     dword ptr [rcx+0F8h], 0
0x10041a2be  jz      short loc_10041A2C7
0x10041a2c0  mov     ecx, ebx
0x10041a2c2  call    try_cor_exit_process
0x10041a2c7  mov     [rbp+arg_18], 0
0x10041a2cb  lea     rax, [rbp+arg_8]
0x10041a2cf  mov     [rbp+var_18], rax
0x10041a2d3  lea     rax, [rbp+arg_10]
0x10041a2d7  mov     [rbp+var_10], rax
0x10041a2db  lea     rax, [rbp+arg_18]
0x10041a2df  mov     [rbp+var_8], rax
0x10041a2e3  mov     eax, 2
0x10041a2e8  mov     [rbp+var_2C], eax
0x10041a2eb  mov     [rbp+var_28], eax
0x10041a2ee  lea     r9, [rbp+var_2C]
0x10041a2f2  lea     r8, [rbp+var_18]
0x10041a2f6  lea     rdx, [rbp+var_28]
0x10041a2fa  lea     rcx, [rbp+var_30]
0x10041a2fe  call    __crt_seh_guarded_call_void___operator____lambda_d80eeec6fff315bfe5c115232f3240e3___lambda_6e4b09c48022b2350581041d5f6b0c4c_____lambda_2358e3775559c9db80273638284d5e45___
0x10041a303  nop
0x10041a304  cmp     [rbp+arg_10], 0
0x10041a308  jz      short loc_10041A315
0x10041a30a  mov     rbx, [rsp+50h+arg_0]
0x10041a30f  add     rsp, 50h
0x10041a313  pop     rbp
0x10041a314  retn
0x10041a315  mov     ecx, ebx; uExitCode
0x10041a317  call    exit_or_terminate_process
```

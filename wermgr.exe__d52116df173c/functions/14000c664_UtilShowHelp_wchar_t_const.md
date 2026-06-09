# UtilShowHelp(wchar_t const *)

- ea: `0x14000c664`
- end: `0x14000c792`
- name: `?UtilShowHelp@@YAJPEB_W@Z`
- size: `302`
- prototype: `__int64 __fastcall(const wchar_t *psz)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a1ac`

## callees

- `0x14000c664`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000c688`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000c688`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000c6e0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000c6e0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c77f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c77f`
- `OLEAUT32!__imp_SysAllocString` at `0x14000c71c`
- `OLEAUT32!__imp_SysAllocString` at `0x14000c71c`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c75e`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c75e`

## pseudocode

```c
__int64 __fastcall UtilShowHelp(const wchar_t *psz)
{
  HRESULT v3; // ebx
  HRESULT v4; // esi
  LPVOID v5; // rcx
  OLECHAR *v6; // rdi
  BSTR v7; // rax
  LPVOID ppv; // [rsp+30h] [rbp-20h] BYREF
  LPVOID *v9; // [rsp+38h] [rbp-18h]
  __int64 v10; // [rsp+88h] [rbp+38h] BYREF
  BSTR v11; // [rsp+90h] [rbp+40h]

  if ( !psz )
    return 2147942487LL;
  v3 = CoInitializeEx(0, 0);
  v10 = 0;
  v11 = 0;
  if ( v3 < 0 )
  {
    v4 = v3;
    v6 = 0;
  }
  else
  {
    ppv = 0;
    v9 = (LPVOID *)&v10;
    v10 = 0;
    v4 = CoCreateInstance(
           &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
           0,
           1u,
           &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
           &ppv);
    if ( ppv )
    {
      v5 = *v9;
      *v9 = ppv;
      if ( v5 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
    }
    v6 = 0;
    if ( v4 >= 0 && v10 )
    {
      v7 = SysAllocString(psz);
      v6 = v7;
      v11 = v7;
      if ( v7 )
      {
        v4 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v10 + 24LL))(v10, v7);
        if ( v4 >= 0 )
          v4 = 0;
      }
      else
      {
        v4 = -2147024882;
      }
    }
  }
  if ( v6 )
    SysFreeString(v6);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v3 >= 0 )
    CoUninitialize();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000c664  push    rbp
0x14000c666  push    rbx
0x14000c667  push    rsi
0x14000c668  push    rdi
0x14000c669  push    r14
0x14000c66b  mov     rbp, rsp
0x14000c66e  sub     rsp, 50h
0x14000c672  mov     r14, rcx
0x14000c675  test    rcx, rcx
0x14000c678  jnz     short loc_14000C684
0x14000c67a  mov     eax, 80070057h
0x14000c67f  jmp     loc_14000C787
0x14000c684  xor     edx, edx; dwCoInit
0x14000c686  xor     ecx, ecx; pvReserved
0x14000c688  call    cs:__imp_CoInitializeEx
0x14000c68e  mov     ebx, eax
0x14000c690  mov     [rbp+arg_0], eax
0x14000c693  mov     [rbp+arg_8], 0
0x14000c69b  mov     [rbp+arg_10], 0
0x14000c6a3  test    eax, eax
0x14000c6a5  js      loc_14000C752
0x14000c6ab  mov     [rbp+var_20], 0
0x14000c6b3  lea     rax, [rbp+arg_8]
0x14000c6b7  mov     [rbp+var_18], rax
0x14000c6bb  mov     [rbp+arg_8], 0
0x14000c6c3  lea     rax, [rbp+var_20]
0x14000c6c7  mov     [rsp+50h+ppv], rax; ppv
0x14000c6cc  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x14000c6d3  xor     edx, edx; pUnkOuter
0x14000c6d5  lea     r8d, [rdx+1]; dwClsContext
0x14000c6d9  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x14000c6e0  call    cs:__imp_CoCreateInstance
0x14000c6e6  mov     esi, eax
0x14000c6e8  mov     rdx, [rbp+var_20]
0x14000c6ec  test    rdx, rdx
0x14000c6ef  jz      short loc_14000C70D
0x14000c6f1  mov     rax, [rbp+var_18]
0x14000c6f5  mov     rcx, [rax]
0x14000c6f8  mov     [rax], rdx
0x14000c6fb  test    rcx, rcx
0x14000c6fe  jz      short loc_14000C70D
0x14000c700  mov     rax, [rcx]
0x14000c703  mov     rax, [rax+10h]
0x14000c707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c70c  nop
0x14000c70d  xor     edi, edi
0x14000c70f  test    esi, esi
0x14000c711  js      short loc_14000C756
0x14000c713  cmp     [rbp+arg_8], rdi
0x14000c717  jz      short loc_14000C756
0x14000c719  mov     rcx, r14; psz
0x14000c71c  call    cs:__imp_SysAllocString
0x14000c722  mov     rdi, rax
0x14000c725  mov     [rbp+arg_10], rax
0x14000c729  test    rax, rax
0x14000c72c  jnz     short loc_14000C735
0x14000c72e  mov     esi, 8007000Eh
0x14000c733  jmp     short loc_14000C756
0x14000c735  mov     rcx, [rbp+arg_8]
0x14000c739  mov     rax, [rcx]
0x14000c73c  mov     rdx, rdi
0x14000c73f  mov     rax, [rax+18h]
0x14000c743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c748  mov     esi, eax
0x14000c74a  test    eax, eax
0x14000c74c  js      short loc_14000C756
0x14000c74e  xor     esi, esi
0x14000c750  jmp     short loc_14000C756
0x14000c752  mov     esi, ebx
0x14000c754  xor     edi, edi
0x14000c756  test    rdi, rdi
0x14000c759  jz      short loc_14000C765
0x14000c75b  mov     rcx, rdi; bstrString
0x14000c75e  call    cs:__imp_SysFreeString
0x14000c764  nop
0x14000c765  mov     rcx, [rbp+arg_8]
0x14000c769  test    rcx, rcx
0x14000c76c  jz      short loc_14000C77B
0x14000c76e  mov     rax, [rcx]
0x14000c771  mov     rax, [rax+10h]
0x14000c775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c77a  nop
0x14000c77b  test    ebx, ebx
0x14000c77d  js      short loc_14000C785
0x14000c77f  call    cs:__imp_CoUninitialize
0x14000c785  mov     eax, esi
0x14000c787  add     rsp, 50h
0x14000c78b  pop     r14
0x14000c78d  pop     rdi
0x14000c78e  pop     rsi
0x14000c78f  pop     rbx
0x14000c790  pop     rbp
0x14000c791  retn
```

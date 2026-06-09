# _CreatePropSheet

- ea: `0x18001d338`
- end: `0x18001d417`
- name: `_CreatePropSheet`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f2c0`

## callees

- `0x1800188d0`
- `0x18001d338`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18001d384`
- `ole32!CoCreateInstance` at `0x18001d384`
- `ole32!CoUninitialize` at `0x18001d38c`
- `ole32!CoUninitialize` at `0x18001d38c`
- `ole32!CoInitialize` at `0x18001d358`
- `ole32!CoInitialize` at `0x18001d358`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d3ff`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d3ff`

## pseudocode

```c
HRESULT __fastcall CreatePropSheet(__int64 a1, __int64 a2)
{
  HRESULT result; // eax
  HRESULT v5; // ebx
  int v6; // eax
  OLECHAR *v7; // rbx
  int v8; // edi
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp+20h] BYREF

  ppv = 0;
  result = CoInitialize(0);
  if ( result >= 0 )
  {
    v5 = CoCreateInstance(&CLSID_SubscriptionMgr, 0, 1u, &IID_ISubscriptionMgr, &ppv);
    CoUninitialize();
    if ( v5 >= 0 )
    {
      bstrString = 0;
      v6 = CreateBSTRFromTSTR(&bstrString, a2 + 556);
      v7 = bstrString;
      v8 = v6;
      if ( !v6 )
        v8 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64))(*(_QWORD *)ppv + 72LL))(ppv, bstrString, a1);
      if ( ppv )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        ppv = 0;
      }
      if ( v7 )
        SysFreeString(v7);
      return v8;
    }
    else
    {
      return v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001d338  mov     [rsp+arg_0], rbx
0x18001d33d  mov     [rsp+arg_8], rsi
0x18001d342  push    rdi
0x18001d343  sub     rsp, 30h
0x18001d347  mov     rsi, rcx
0x18001d34a  mov     [rsp+38h+arg_10], 0
0x18001d353  xor     ecx, ecx; pvReserved
0x18001d355  mov     rdi, rdx
0x18001d358  call    cs:__imp_CoInitialize
0x18001d35e  test    eax, eax
0x18001d360  js      loc_18001D407
0x18001d366  xor     edx, edx; pUnkOuter
0x18001d368  lea     rax, [rsp+38h+arg_10]
0x18001d36d  lea     r9, IID_ISubscriptionMgr; riid
0x18001d374  mov     [rsp+38h+ppv], rax; ppv
0x18001d379  lea     rcx, CLSID_SubscriptionMgr; rclsid
0x18001d380  lea     r8d, [rdx+1]; dwClsContext
0x18001d384  call    cs:__imp_CoCreateInstance
0x18001d38a  mov     ebx, eax
0x18001d38c  call    cs:__imp_CoUninitialize
0x18001d392  test    ebx, ebx
0x18001d394  jns     short loc_18001D39A
0x18001d396  mov     eax, ebx
0x18001d398  jmp     short loc_18001D407
0x18001d39a  lea     rdx, [rdi+22Ch]
0x18001d3a1  mov     [rsp+38h+bstrString], 0
0x18001d3aa  lea     rcx, [rsp+38h+bstrString]
0x18001d3af  call    CreateBSTRFromTSTR
0x18001d3b4  mov     rbx, [rsp+38h+bstrString]
0x18001d3b9  mov     edi, eax
0x18001d3bb  test    eax, eax
0x18001d3bd  jnz     short loc_18001D3D8
0x18001d3bf  mov     rcx, [rsp+38h+arg_10]
0x18001d3c4  mov     r8, rsi
0x18001d3c7  mov     rdx, rbx
0x18001d3ca  mov     rax, [rcx]
0x18001d3cd  mov     rax, [rax+48h]
0x18001d3d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3d6  mov     edi, eax
0x18001d3d8  mov     rcx, [rsp+38h+arg_10]
0x18001d3dd  test    rcx, rcx
0x18001d3e0  jz      short loc_18001D3F7
0x18001d3e2  mov     rax, [rcx]
0x18001d3e5  mov     rax, [rax+10h]
0x18001d3e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3ee  mov     [rsp+38h+arg_10], 0
0x18001d3f7  test    rbx, rbx
0x18001d3fa  jz      short loc_18001D405
0x18001d3fc  mov     rcx, rbx; bstrString
0x18001d3ff  call    cs:__imp_SysFreeString
0x18001d405  mov     eax, edi
0x18001d407  mov     rbx, [rsp+38h+arg_0]
0x18001d40c  mov     rsi, [rsp+38h+arg_8]
0x18001d411  add     rsp, 30h
0x18001d415  pop     rdi
0x18001d416  retn
```

# CWbemPathCracker::GetTypeFromText(ATL::CComBSTR const &)

- ea: `0x180004d28`
- end: `0x180004dae`
- name: `?GetTypeFromText@CWbemPathCracker@@CA?AW4WbemPathType@1@AEBVCComBSTR@ATL@@@Z`
- size: `134`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004140`
- `0x1800044a4`
- `0x1800045c0`
- `0x18000e9a0`

## callees

- `0x180004d28`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004d5f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004d5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall CWbemPathCracker::GetTypeFromText(_QWORD *a1)
{
  BOOL v2; // ebx
  LPVOID v4; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v4 = 0;
  if ( CoCreateInstance(&CLSID_WbemDefPath, 0, 1u, &IID_IWbemPath, &v4) >= 0 )
    v2 = (*(int (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v4 + 24LL))(v4, 4, *a1) >= 0;
  if ( v4 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
  return v2;
}

```

## disassembly

```asm
0x180004d28  mov     r11, rsp
0x180004d2b  mov     [r11+8], rbx
0x180004d2f  mov     [r11+18h], rsi
0x180004d33  push    rdi
0x180004d34  sub     rsp, 30h
0x180004d38  mov     rdi, rcx
0x180004d3b  xor     ebx, ebx
0x180004d3d  mov     [r11+10h], rbx
0x180004d41  lea     rax, [r11+10h]
0x180004d45  mov     [r11-18h], rax
0x180004d49  lea     r9, IID_IWbemPath; riid
0x180004d50  lea     esi, [rbx+1]
0x180004d53  mov     r8d, esi; dwClsContext
0x180004d56  xor     edx, edx; pUnkOuter
0x180004d58  lea     rcx, CLSID_WbemDefPath; rclsid
0x180004d5f  call    cs:__imp_CoCreateInstance
0x180004d65  test    eax, eax
0x180004d67  js      short loc_180004D85
0x180004d69  mov     rcx, [rsp+38h+arg_8]
0x180004d6e  mov     rax, [rcx]
0x180004d71  mov     r8, [rdi]
0x180004d74  lea     edx, [rbx+4]
0x180004d77  mov     rax, [rax+18h]
0x180004d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d80  test    eax, eax
0x180004d82  cmovns  ebx, esi
0x180004d85  mov     rcx, [rsp+38h+arg_8]
0x180004d8a  test    rcx, rcx
0x180004d8d  jz      short loc_180004D9C
0x180004d8f  mov     rdx, [rcx]
0x180004d92  mov     rax, [rdx+10h]
0x180004d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d9b  nop
0x180004d9c  mov     eax, ebx
0x180004d9e  mov     rbx, [rsp+38h+arg_0]
0x180004da3  mov     rsi, [rsp+38h+arg_10]
0x180004da8  add     rsp, 30h
0x180004dac  pop     rdi
0x180004dad  retn
```

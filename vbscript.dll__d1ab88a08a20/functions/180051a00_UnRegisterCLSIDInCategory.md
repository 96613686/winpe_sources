# UnRegisterCLSIDInCategory

- ea: `0x180051a00`
- end: `0x180051ac6`
- name: `UnRegisterCLSIDInCategory`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800455dc`

## callees

- `0x1800517a4`
- `0x180051a00`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `OLE32!CoCreateInstance` at `0x180051a54`
- `OLE32!CoCreateInstance` at `0x180051a54`

## pseudocode

```c
__int64 __fastcall UnRegisterCLSIDInCategory(const struct _GUID *a1, __int128 *a2, unsigned int a3)
{
  __int64 result; // rax
  HRESULT v6; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-28h] BYREF
  __int128 v8; // [rsp+38h] [rbp-20h] BYREF

  ppv = 0;
  result = FExistsCLSID(a1, (__int64)a2, a3);
  if ( (_DWORD)result )
  {
    v6 = CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &IID_ICatRegister, &ppv);
    if ( v6 >= 0 )
    {
      v8 = *a2;
      v6 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, __int64, __int128 *))(*(_QWORD *)ppv + 48LL))(
             ppv,
             a1,
             1,
             &v8);
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x180051a00  mov     [rsp+arg_8], rbx
0x180051a05  mov     [rsp+arg_10], rsi
0x180051a0a  push    rdi
0x180051a0b  sub     rsp, 50h
0x180051a0f  mov     rax, cs:__security_cookie
0x180051a16  xor     rax, rsp
0x180051a19  mov     [rsp+58h+var_10], rax
0x180051a1e  mov     rsi, rdx
0x180051a21  mov     [rsp+58h+var_28], 0
0x180051a2a  mov     rdi, rcx
0x180051a2d  call    FExistsCLSID
0x180051a32  test    eax, eax
0x180051a34  jz      short loc_180051AA8
0x180051a36  xor     edx, edx; pUnkOuter
0x180051a38  lea     rax, [rsp+58h+var_28]
0x180051a3d  lea     r9, IID_ICatRegister; riid
0x180051a44  mov     [rsp+58h+ppv], rax; ppv
0x180051a49  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180051a50  lea     r8d, [rdx+1]; dwClsContext
0x180051a54  call    cs:__imp_CoCreateInstance
0x180051a5b  nop     dword ptr [rax+rax+00h]
0x180051a60  mov     ebx, eax
0x180051a62  test    eax, eax
0x180051a64  js      short loc_180051A90
0x180051a66  mov     rcx, [rsp+58h+var_28]
0x180051a6b  lea     r9, [rsp+58h+var_20]
0x180051a70  movaps  xmm0, xmmword ptr [rsi]
0x180051a73  mov     r8d, 1
0x180051a79  movdqu  [rsp+58h+var_20], xmm0
0x180051a7f  mov     rdx, rdi
0x180051a82  mov     rax, [rcx]
0x180051a85  mov     rax, [rax+30h]
0x180051a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a8e  mov     ebx, eax
0x180051a90  mov     rcx, [rsp+58h+var_28]
0x180051a95  test    rcx, rcx
0x180051a98  jz      short loc_180051AA6
0x180051a9a  mov     rax, [rcx]
0x180051a9d  mov     rax, [rax+10h]
0x180051aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051aa6  mov     eax, ebx
0x180051aa8  mov     rcx, [rsp+58h+var_10]
0x180051aad  xor     rcx, rsp; StackCookie
0x180051ab0  call    __security_check_cookie
0x180051ab5  mov     rbx, [rsp+58h+arg_8]
0x180051aba  mov     rsi, [rsp+58h+arg_10]
0x180051abf  add     rsp, 50h
0x180051ac3  pop     rdi
0x180051ac4  retn
```

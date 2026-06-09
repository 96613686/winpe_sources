# UnRegisterCLSIDInCategory

- ea: `0x180050244`
- end: `0x180050303`
- name: `UnRegisterCLSIDInCategory`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180044378`

## callees

- `0x180050000`
- `0x180050244`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `OLE32!CoCreateInstance` at `0x180050298`
- `OLE32!CoCreateInstance` at `0x180050298`

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
0x180050244  mov     [rsp+arg_8], rbx
0x180050249  mov     [rsp+arg_10], rsi
0x18005024e  push    rdi
0x18005024f  sub     rsp, 50h
0x180050253  mov     rax, cs:__security_cookie
0x18005025a  xor     rax, rsp
0x18005025d  mov     [rsp+58h+var_10], rax
0x180050262  mov     rsi, rdx
0x180050265  mov     [rsp+58h+var_28], 0
0x18005026e  mov     rdi, rcx
0x180050271  call    FExistsCLSID
0x180050276  test    eax, eax
0x180050278  jz      short loc_1800502E6
0x18005027a  xor     edx, edx; pUnkOuter
0x18005027c  lea     rax, [rsp+58h+var_28]
0x180050281  lea     r9, IID_ICatRegister; riid
0x180050288  mov     [rsp+58h+ppv], rax; ppv
0x18005028d  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180050294  lea     r8d, [rdx+1]; dwClsContext
0x180050298  call    cs:__imp_CoCreateInstance
0x18005029e  mov     ebx, eax
0x1800502a0  test    eax, eax
0x1800502a2  js      short loc_1800502CE
0x1800502a4  mov     rcx, [rsp+58h+var_28]
0x1800502a9  lea     r9, [rsp+58h+var_20]
0x1800502ae  movaps  xmm0, xmmword ptr [rsi]
0x1800502b1  mov     r8d, 1
0x1800502b7  movdqu  [rsp+58h+var_20], xmm0
0x1800502bd  mov     rdx, rdi
0x1800502c0  mov     rax, [rcx]
0x1800502c3  mov     rax, [rax+30h]
0x1800502c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502cc  mov     ebx, eax
0x1800502ce  mov     rcx, [rsp+58h+var_28]
0x1800502d3  test    rcx, rcx
0x1800502d6  jz      short loc_1800502E4
0x1800502d8  mov     rax, [rcx]
0x1800502db  mov     rax, [rax+10h]
0x1800502df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502e4  mov     eax, ebx
0x1800502e6  mov     rcx, [rsp+58h+var_10]
0x1800502eb  xor     rcx, rsp; StackCookie
0x1800502ee  call    __security_check_cookie
0x1800502f3  mov     rbx, [rsp+58h+arg_8]
0x1800502f8  mov     rsi, [rsp+58h+arg_10]
0x1800502fd  add     rsp, 50h
0x180050301  pop     rdi
0x180050302  retn
```

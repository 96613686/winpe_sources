# COleScript::GetINETSecurityManagerNoRef(IInternetSecurityManager * *)

- ea: `0x180053c70`
- end: `0x180053d56`
- name: `?GetINETSecurityManagerNoRef@COleScript@@IEAAJPEAPEAUIInternetSecurityManager@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(COleScript *__hidden this, struct IInternetSecurityManager **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180054128`

## callees

- `0x180053c70`
- `0x180077010`

## import_xrefs

- `OLE32!CoCreateInstance` at `0x180053d32`
- `OLE32!CoCreateInstance` at `0x180053d32`

## pseudocode

```c
HRESULT __fastcall COleScript::GetINETSecurityManagerNoRef(COleScript *this, struct IInternetSecurityManager **a2)
{
  bool v2; // zf
  HRESULT result; // eax
  LPVOID *ppv; // r14
  struct IInternetSecurityManager *v7; // rax
  int v8; // ebx
  __int64 v9; // [rsp+60h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 174) == 0;
  *a2 = 0;
  v9 = 0;
  if ( !v2 )
    return -2147467259;
  ppv = (LPVOID *)((char *)this + 712);
  v7 = (struct IInternetSecurityManager *)*((_QWORD *)this + 89);
  if ( v7 )
  {
    *a2 = v7;
  }
  else
  {
    if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 20))(
           *((_QWORD *)this + 20),
           &IID_IServiceProvider,
           &v9) < 0
      || (v8 = (*(__int64 (__fastcall **)(__int64, GUID *, GUID *, LPVOID *))(*(_QWORD *)v9 + 24LL))(
                 v9,
                 &IID_IInternetSecurityManager,
                 &IID_IInternetSecurityManager,
                 ppv),
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9),
          v8 < 0) )
    {
      result = CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &IID_IInternetSecurityManager, ppv);
      if ( result < 0 )
      {
        *((_DWORD *)this + 174) = 1;
        return result;
      }
    }
    *a2 = (struct IInternetSecurityManager *)*ppv;
  }
  return 0;
}

```

## disassembly

```asm
0x180053c70  push    rbx
0x180053c72  push    rsi
0x180053c73  push    rdi
0x180053c74  push    r14
0x180053c76  sub     rsp, 38h
0x180053c7a  cmp     dword ptr [rcx+2B8h], 0
0x180053c81  mov     rsi, rdx
0x180053c84  mov     rdi, rcx
0x180053c87  mov     qword ptr [rdx], 0
0x180053c8e  mov     [rsp+58h+arg_0], 0
0x180053c97  jz      short loc_180053CA3
0x180053c99  mov     eax, 80004005h
0x180053c9e  jmp     loc_180053D4C
0x180053ca3  lea     r14, [rcx+2C8h]
0x180053caa  mov     rax, [r14]
0x180053cad  test    rax, rax
0x180053cb0  jz      short loc_180053CBA
0x180053cb2  mov     [rdx], rax
0x180053cb5  jmp     loc_180053D4A
0x180053cba  mov     rcx, [rcx+0A0h]
0x180053cc1  lea     r8, [rsp+58h+arg_0]
0x180053cc6  lea     rdx, IID_IServiceProvider
0x180053ccd  mov     rax, [rcx]
0x180053cd0  mov     rax, [rax]
0x180053cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053cd8  test    eax, eax
0x180053cda  js      short loc_180053D15
0x180053cdc  mov     rcx, [rsp+58h+arg_0]
0x180053ce1  lea     r8, IID_IInternetSecurityManager
0x180053ce8  mov     r9, r14
0x180053ceb  lea     rdx, IID_IInternetSecurityManager
0x180053cf2  mov     rax, [rcx]
0x180053cf5  mov     rax, [rax+18h]
0x180053cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053cfe  mov     rcx, [rsp+58h+arg_0]
0x180053d03  mov     ebx, eax
0x180053d05  mov     rdx, [rcx]
0x180053d08  mov     rax, [rdx+10h]
0x180053d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d11  test    ebx, ebx
0x180053d13  jns     short loc_180053D44
0x180053d15  mov     ebx, 1
0x180053d1a  mov     [rsp+58h+ppv], r14; ppv
0x180053d1f  mov     r8d, ebx; dwClsContext
0x180053d22  lea     r9, IID_IInternetSecurityManager; riid
0x180053d29  xor     edx, edx; pUnkOuter
0x180053d2b  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x180053d32  call    cs:__imp_CoCreateInstance
0x180053d38  test    eax, eax
0x180053d3a  jns     short loc_180053D44
0x180053d3c  mov     [rdi+2B8h], ebx
0x180053d42  jmp     short loc_180053D4C
0x180053d44  mov     rax, [r14]
0x180053d47  mov     [rsi], rax
0x180053d4a  xor     eax, eax
0x180053d4c  add     rsp, 38h
0x180053d50  pop     r14
0x180053d52  pop     rdi
0x180053d53  pop     rsi
0x180053d54  pop     rbx
0x180053d55  retn
```

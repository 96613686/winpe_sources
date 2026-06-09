# COleScript::GetINETSecurityManagerNoRef(IInternetSecurityManager * *)

- ea: `0x180055530`
- end: `0x18005561d`
- name: `?GetINETSecurityManagerNoRef@COleScript@@IEAAJPEAPEAUIInternetSecurityManager@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(COleScript *__hidden this, struct IInternetSecurityManager **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180055a00`

## callees

- `0x180055530`
- `0x18007a010`

## import_xrefs

- `OLE32!CoCreateInstance` at `0x1800555f2`
- `OLE32!CoCreateInstance` at `0x1800555f2`

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
0x180055530  push    rbx
0x180055532  push    rsi
0x180055533  push    rdi
0x180055534  push    r14
0x180055536  sub     rsp, 38h
0x18005553a  cmp     dword ptr [rcx+2B8h], 0
0x180055541  mov     rsi, rdx
0x180055544  mov     rdi, rcx
0x180055547  mov     qword ptr [rdx], 0
0x18005554e  mov     [rsp+58h+arg_0], 0
0x180055557  jz      short loc_180055563
0x180055559  mov     eax, 80004005h
0x18005555e  jmp     loc_180055612
0x180055563  lea     r14, [rcx+2C8h]
0x18005556a  mov     rax, [r14]
0x18005556d  test    rax, rax
0x180055570  jz      short loc_18005557A
0x180055572  mov     [rdx], rax
0x180055575  jmp     loc_180055610
0x18005557a  mov     rcx, [rcx+0A0h]
0x180055581  lea     r8, [rsp+58h+arg_0]
0x180055586  lea     rdx, IID_IServiceProvider
0x18005558d  mov     rax, [rcx]
0x180055590  mov     rax, [rax]
0x180055593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055598  test    eax, eax
0x18005559a  js      short loc_1800555D5
0x18005559c  mov     rcx, [rsp+58h+arg_0]
0x1800555a1  lea     r8, IID_IInternetSecurityManager
0x1800555a8  mov     r9, r14
0x1800555ab  lea     rdx, IID_IInternetSecurityManager
0x1800555b2  mov     rax, [rcx]
0x1800555b5  mov     rax, [rax+18h]
0x1800555b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800555be  mov     rcx, [rsp+58h+arg_0]
0x1800555c3  mov     ebx, eax
0x1800555c5  mov     rdx, [rcx]
0x1800555c8  mov     rax, [rdx+10h]
0x1800555cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800555d1  test    ebx, ebx
0x1800555d3  jns     short loc_18005560A
0x1800555d5  mov     ebx, 1
0x1800555da  mov     [rsp+58h+ppv], r14; ppv
0x1800555df  mov     r8d, ebx; dwClsContext
0x1800555e2  lea     r9, IID_IInternetSecurityManager; riid
0x1800555e9  xor     edx, edx; pUnkOuter
0x1800555eb  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x1800555f2  call    cs:__imp_CoCreateInstance
0x1800555f9  nop     dword ptr [rax+rax+00h]
0x1800555fe  test    eax, eax
0x180055600  jns     short loc_18005560A
0x180055602  mov     [rdi+2B8h], ebx
0x180055608  jmp     short loc_180055612
0x18005560a  mov     rax, [r14]
0x18005560d  mov     [rsi], rax
0x180055610  xor     eax, eax
0x180055612  add     rsp, 38h
0x180055616  pop     r14
0x180055618  pop     rdi
0x180055619  pop     rsi
0x18005561a  pop     rbx
0x18005561b  retn
```

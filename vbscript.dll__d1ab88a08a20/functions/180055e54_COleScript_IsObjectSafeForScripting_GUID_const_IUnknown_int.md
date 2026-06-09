# COleScript::IsObjectSafeForScripting(_GUID const &,IUnknown *,int)

- ea: `0x180055e54`
- end: `0x180055fdd`
- name: `?IsObjectSafeForScripting@COleScript@@IEAAHAEBU_GUID@@PEAUIUnknown@@H@Z`
- size: `393`
- prototype: `__int64 __fastcall(COleScript *__hidden this, const struct _GUID *, struct IUnknown *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180026380`

## callees

- `0x180055e54`
- `0x18005762c`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `OLE32!CoCreateInstance` at `0x180055f16`
- `OLE32!CoCreateInstance` at `0x180055f16`

## pseudocode

```c
_BOOL8 __fastcall COleScript::IsObjectSafeForScripting(
        COleScript *this,
        const struct _GUID *a2,
        struct IUnknown *a3,
        int a4)
{
  struct IUnknownVtbl *lpVtbl; // rax
  COleScript *v7; // rcx
  BOOL v8; // ebx
  unsigned int v9; // edi
  COleScript *v10; // rcx
  void (*Release)(void); // rax
  struct IObjectSafety *v13; // [rsp+40h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-28h] BYREF
  GUID v15; // [rsp+50h] [rbp-20h] BYREF

  lpVtbl = a3->lpVtbl;
  v13 = 0;
  v8 = 1;
  if ( ((int (__fastcall *)(struct IUnknown *, GUID *, struct IObjectSafety **))lpVtbl->QueryInterface)(
         a3,
         &IID_IObjectSafety,
         &v13) < 0 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &IID_ICatInformation, &ppv) < 0 )
      return 0;
    v15 = CATID_SafeForScripting;
    if ( (*(unsigned int (__fastcall **)(LPVOID, const struct _GUID *, __int64, GUID *, _DWORD, _QWORD))(*(_QWORD *)ppv + 48LL))(
           ppv,
           a2,
           1,
           &v15,
           0,
           0) )
    {
      v8 = 0;
    }
    else if ( a4 )
    {
      v15 = CATID_SafeForInitializing;
      v8 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, __int64, GUID *, _DWORD, _QWORD))(*(_QWORD *)ppv + 48LL))(
             ppv,
             a2,
             1,
             &v15,
             0,
             0) == 0;
    }
    Release = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
  }
  else
  {
    v9 = a4 != 0 ? 3 : 1;
    if ( (int)COleScript::SetObjectSafety(v7, v13, &GUID_NULL, v9, v9) < 0 )
      v8 = (int)COleScript::SetObjectSafety(v10, v13, &IID_IDispatch, v9, v9) >= 0;
    Release = (void (*)(void))v13->lpVtbl->Release;
  }
  Release();
  return v8;
}

```

## disassembly

```asm
0x180055e54  mov     [rsp-18h+arg_0], rbx
0x180055e59  push    rbp
0x180055e5a  push    rsi
0x180055e5b  push    rdi
0x180055e5c  mov     rbp, rsp
0x180055e5f  sub     rsp, 70h
0x180055e63  mov     rax, cs:__security_cookie
0x180055e6a  xor     rax, rsp
0x180055e6d  mov     [rbp+var_10], rax
0x180055e71  mov     rax, [r8]
0x180055e74  mov     rcx, r8
0x180055e77  mov     rsi, rdx
0x180055e7a  mov     [rbp+var_30], 0
0x180055e82  lea     r8, [rbp+var_30]
0x180055e86  mov     edi, r9d
0x180055e89  lea     rdx, IID_IObjectSafety
0x180055e90  mov     rax, [rax]
0x180055e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055e98  mov     ebx, 1
0x180055e9d  test    eax, eax
0x180055e9f  js      short loc_180055EF2
0x180055ea1  mov     rdx, [rbp+var_30]; struct IObjectSafety *
0x180055ea5  lea     r8, GUID_NULL; struct _GUID *
0x180055eac  neg     edi
0x180055eae  sbb     edi, edi
0x180055eb0  and     edi, 2
0x180055eb3  add     edi, ebx
0x180055eb5  mov     r9d, edi; unsigned int
0x180055eb8  mov     dword ptr [rsp+70h+ppv], edi; unsigned int
0x180055ebc  call    ?SetObjectSafety@COleScript@@IEAAJPEAUIObjectSafety@@AEBU_GUID@@KK@Z; COleScript::SetObjectSafety(IObjectSafety *,_GUID const &,ulong,ulong)
0x180055ec1  test    eax, eax
0x180055ec3  jns     short loc_180055EE2
0x180055ec5  mov     rdx, [rbp+var_30]; struct IObjectSafety *
0x180055ec9  lea     r8, IID_IDispatch; struct _GUID *
0x180055ed0  mov     r9d, edi; unsigned int
0x180055ed3  mov     dword ptr [rsp+70h+ppv], edi; unsigned int
0x180055ed7  call    ?SetObjectSafety@COleScript@@IEAAJPEAUIObjectSafety@@AEBU_GUID@@KK@Z; COleScript::SetObjectSafety(IObjectSafety *,_GUID const &,ulong,ulong)
0x180055edc  test    eax, eax
0x180055ede  jns     short loc_180055EE2
0x180055ee0  xor     ebx, ebx
0x180055ee2  mov     rcx, [rbp+var_30]
0x180055ee6  mov     rax, [rcx]
0x180055ee9  mov     rax, [rax+10h]
0x180055eed  jmp     loc_180055FB9
0x180055ef2  lea     rax, [rbp+var_28]
0x180055ef6  mov     [rbp+var_28], 0
0x180055efe  lea     r9, IID_ICatInformation; riid
0x180055f05  mov     [rsp+70h+ppv], rax; ppv
0x180055f0a  mov     r8d, ebx; dwClsContext
0x180055f0d  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180055f14  xor     edx, edx; pUnkOuter
0x180055f16  call    cs:__imp_CoCreateInstance
0x180055f1d  nop     dword ptr [rax+rax+00h]
0x180055f22  test    eax, eax
0x180055f24  jns     short loc_180055F2D
0x180055f26  xor     eax, eax
0x180055f28  jmp     loc_180055FC0
0x180055f2d  movups  xmm0, xmmword ptr cs:CATID_SafeForScripting.Data1
0x180055f34  mov     rcx, [rbp+var_28]
0x180055f38  lea     r9, [rbp+var_20]
0x180055f3c  mov     [rsp+70h+var_48], 0
0x180055f45  mov     r8d, ebx
0x180055f48  movdqu  [rbp+var_20], xmm0
0x180055f4d  mov     rdx, rsi
0x180055f50  mov     dword ptr [rsp+70h+ppv], 0
0x180055f58  mov     rax, [rcx]
0x180055f5b  mov     rax, [rax+30h]
0x180055f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f64  test    eax, eax
0x180055f66  jnz     short loc_180055FAC
0x180055f68  test    edi, edi
0x180055f6a  jz      short loc_180055FAE
0x180055f6c  movups  xmm0, xmmword ptr cs:CATID_SafeForInitializing.Data1
0x180055f73  mov     rcx, [rbp+var_28]
0x180055f77  lea     r9, [rbp+var_20]
0x180055f7b  mov     [rsp+70h+var_48], 0
0x180055f84  mov     r8d, ebx
0x180055f87  movdqu  [rbp+var_20], xmm0
0x180055f8c  mov     rdx, rsi
0x180055f8f  mov     dword ptr [rsp+70h+ppv], 0
0x180055f97  mov     rax, [rcx]
0x180055f9a  mov     rax, [rax+30h]
0x180055f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fa3  xor     ebx, ebx
0x180055fa5  test    eax, eax
0x180055fa7  setz    bl
0x180055faa  jmp     short loc_180055FAE
0x180055fac  xor     ebx, ebx
0x180055fae  mov     rcx, [rbp+var_28]
0x180055fb2  mov     rdx, [rcx]
0x180055fb5  mov     rax, [rdx+10h]
0x180055fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fbe  mov     eax, ebx
0x180055fc0  mov     rcx, [rbp+var_10]
0x180055fc4  xor     rcx, rsp; StackCookie
0x180055fc7  call    __security_check_cookie
0x180055fcc  mov     rbx, [rsp+70h+arg_0]
0x180055fd4  add     rsp, 70h
0x180055fd8  pop     rdi
0x180055fd9  pop     rsi
0x180055fda  pop     rbp
0x180055fdb  retn
```

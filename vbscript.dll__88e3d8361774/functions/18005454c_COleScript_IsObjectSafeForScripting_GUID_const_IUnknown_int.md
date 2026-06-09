# COleScript::IsObjectSafeForScripting(_GUID const &,IUnknown *,int)

- ea: `0x18005454c`
- end: `0x1800546ce`
- name: `?IsObjectSafeForScripting@COleScript@@IEAAHAEBU_GUID@@PEAUIUnknown@@H@Z`
- size: `386`
- prototype: `__int64 __fastcall(COleScript *__hidden this, const struct _GUID *, struct IUnknown *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180039480`

## callees

- `0x18005454c`
- `0x180055cbc`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `OLE32!CoCreateInstance` at `0x18005460e`
- `OLE32!CoCreateInstance` at `0x18005460e`

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
0x18005454c  mov     [rsp-18h+arg_0], rbx
0x180054551  push    rbp
0x180054552  push    rsi
0x180054553  push    rdi
0x180054554  mov     rbp, rsp
0x180054557  sub     rsp, 70h
0x18005455b  mov     rax, cs:__security_cookie
0x180054562  xor     rax, rsp
0x180054565  mov     [rbp+var_10], rax
0x180054569  mov     rax, [r8]
0x18005456c  mov     rcx, r8
0x18005456f  mov     rsi, rdx
0x180054572  mov     [rbp+var_30], 0
0x18005457a  lea     r8, [rbp+var_30]
0x18005457e  mov     edi, r9d
0x180054581  lea     rdx, IID_IObjectSafety
0x180054588  mov     rax, [rax]
0x18005458b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054590  mov     ebx, 1
0x180054595  test    eax, eax
0x180054597  js      short loc_1800545EA
0x180054599  mov     rdx, [rbp+var_30]; struct IObjectSafety *
0x18005459d  lea     r8, GUID_NULL; struct _GUID *
0x1800545a4  neg     edi
0x1800545a6  sbb     edi, edi
0x1800545a8  and     edi, 2
0x1800545ab  add     edi, ebx
0x1800545ad  mov     r9d, edi; unsigned int
0x1800545b0  mov     dword ptr [rsp+70h+ppv], edi; unsigned int
0x1800545b4  call    ?SetObjectSafety@COleScript@@IEAAJPEAUIObjectSafety@@AEBU_GUID@@KK@Z; COleScript::SetObjectSafety(IObjectSafety *,_GUID const &,ulong,ulong)
0x1800545b9  test    eax, eax
0x1800545bb  jns     short loc_1800545DA
0x1800545bd  mov     rdx, [rbp+var_30]; struct IObjectSafety *
0x1800545c1  lea     r8, IID_IDispatch; struct _GUID *
0x1800545c8  mov     r9d, edi; unsigned int
0x1800545cb  mov     dword ptr [rsp+70h+ppv], edi; unsigned int
0x1800545cf  call    ?SetObjectSafety@COleScript@@IEAAJPEAUIObjectSafety@@AEBU_GUID@@KK@Z; COleScript::SetObjectSafety(IObjectSafety *,_GUID const &,ulong,ulong)
0x1800545d4  test    eax, eax
0x1800545d6  jns     short loc_1800545DA
0x1800545d8  xor     ebx, ebx
0x1800545da  mov     rcx, [rbp+var_30]
0x1800545de  mov     rax, [rcx]
0x1800545e1  mov     rax, [rax+10h]
0x1800545e5  jmp     loc_1800546AB
0x1800545ea  lea     rax, [rbp+var_28]
0x1800545ee  mov     [rbp+var_28], 0
0x1800545f6  lea     r9, IID_ICatInformation; riid
0x1800545fd  mov     [rsp+70h+ppv], rax; ppv
0x180054602  mov     r8d, ebx; dwClsContext
0x180054605  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18005460c  xor     edx, edx; pUnkOuter
0x18005460e  call    cs:__imp_CoCreateInstance
0x180054614  test    eax, eax
0x180054616  jns     short loc_18005461F
0x180054618  xor     eax, eax
0x18005461a  jmp     loc_1800546B2
0x18005461f  movups  xmm0, xmmword ptr cs:CATID_SafeForScripting.Data1
0x180054626  mov     rcx, [rbp+var_28]
0x18005462a  lea     r9, [rbp+var_20]
0x18005462e  mov     [rsp+70h+var_48], 0
0x180054637  mov     r8d, ebx
0x18005463a  movdqu  [rbp+var_20], xmm0
0x18005463f  mov     rdx, rsi
0x180054642  mov     dword ptr [rsp+70h+ppv], 0
0x18005464a  mov     rax, [rcx]
0x18005464d  mov     rax, [rax+30h]
0x180054651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054656  test    eax, eax
0x180054658  jnz     short loc_18005469E
0x18005465a  test    edi, edi
0x18005465c  jz      short loc_1800546A0
0x18005465e  movups  xmm0, xmmword ptr cs:CATID_SafeForInitializing.Data1
0x180054665  mov     rcx, [rbp+var_28]
0x180054669  lea     r9, [rbp+var_20]
0x18005466d  mov     [rsp+70h+var_48], 0
0x180054676  mov     r8d, ebx
0x180054679  movdqu  [rbp+var_20], xmm0
0x18005467e  mov     rdx, rsi
0x180054681  mov     dword ptr [rsp+70h+ppv], 0
0x180054689  mov     rax, [rcx]
0x18005468c  mov     rax, [rax+30h]
0x180054690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054695  xor     ebx, ebx
0x180054697  test    eax, eax
0x180054699  setz    bl
0x18005469c  jmp     short loc_1800546A0
0x18005469e  xor     ebx, ebx
0x1800546a0  mov     rcx, [rbp+var_28]
0x1800546a4  mov     rdx, [rcx]
0x1800546a7  mov     rax, [rdx+10h]
0x1800546ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800546b0  mov     eax, ebx
0x1800546b2  mov     rcx, [rbp+var_10]
0x1800546b6  xor     rcx, rsp; StackCookie
0x1800546b9  call    __security_check_cookie
0x1800546be  mov     rbx, [rsp+70h+arg_0]
0x1800546c6  add     rsp, 70h
0x1800546ca  pop     rdi
0x1800546cb  pop     rsi
0x1800546cc  pop     rbp
0x1800546cd  retn
```

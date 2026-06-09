# CSWbemNamedValueSet::CSWbemNamedValueSet(CWbemPathCracker *,bool)

- ea: `0x180022d70`
- end: `0x180022eae`
- name: `??0CSWbemNamedValueSet@@QEAA@PEAVCWbemPathCracker@@_N@Z`
- size: `318`
- prototype: `CSWbemNamedValueSet *__fastcall(CSWbemNamedValueSet *__hidden this, struct CWbemPathCracker *, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180020020`
- `0x1800336b0`

## callees

- `0x1800126c0`
- `0x180022d70`
- `0x180023320`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022e67`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022e67`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CSWbemNamedValueSet *__fastcall CSWbemNamedValueSet::CSWbemNamedValueSet(
        CSWbemNamedValueSet *this,
        struct CWbemPathCracker *a2,
        char a3)
{
  LPVOID *ppv; // rbx
  char *v5; // rcx
  __int64 v6; // rcx
  GUID v8; // [rsp+30h] [rbp-28h] BYREF
  GUID v9; // [rsp+40h] [rbp-18h] BYREF

  *(_QWORD *)this = &CSWbemNamedValueSet::`vftable'{for `ISWbemNamedValueSet'};
  *((_QWORD *)this + 1) = &CSWbemNamedValueSet::`vftable'{for `ISWbemInternalContext'};
  *((_QWORD *)this + 2) = &CSWbemNamedValueSet::`vftable'{for `IObjectSafety'};
  *((_QWORD *)this + 3) = &CSWbemNamedValueSet::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 4) = &CSWbemNamedValueSet::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 5) = 0;
  ppv = (LPVOID *)((char *)this + 48);
  *((_QWORD *)this + 6) = 0;
  v5 = (char *)this + 56;
  *((_QWORD *)v5 + 3) = 0;
  *((_QWORD *)v5 + 4) = 0;
  *((_QWORD *)v5 + 5) = 0;
  *((_QWORD *)v5 + 1) = 0;
  *((_DWORD *)v5 + 4) = 0;
  *(_QWORD *)v5 = &CSWbemNamedValueSet::CContextDispatchHelp::`vftable';
  *((_QWORD *)this + 17) = a2;
  *((_BYTE *)this + 144) = a3;
  *((_DWORD *)this + 37) = 0;
  v8 = CLSID_SWbemNamedValueSet;
  v9 = IID_ISWbemNamedValueSet;
  CDispatchHelp::SetObj((CDispatchHelp *)v5, (struct IDispatch *)this, &v9, &v8, L"SWbemNamedValueSet");
  CoCreateInstance(&CLSID_WbemContext, 0, 1u, &IID_IWbemContext, ppv);
  v6 = *((_QWORD *)this + 17);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    ++*((_DWORD *)this + 37);
    CSWbemNamedValueSet::BuildContextFromKeyList(this);
    --*((_DWORD *)this + 37);
  }
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x180022d70  mov     r11, rsp
0x180022d73  mov     [r11+10h], rbx
0x180022d77  mov     [r11+8], rcx
0x180022d7b  push    rdi
0x180022d7c  sub     rsp, 50h
0x180022d80  mov     rdi, rcx
0x180022d83  lea     rax, ??_7CSWbemNamedValueSet@@6BISWbemNamedValueSet@@@; const CSWbemNamedValueSet::`vftable'{for `ISWbemNamedValueSet'}
0x180022d8a  mov     [rcx], rax
0x180022d8d  lea     rax, ??_7CSWbemNamedValueSet@@6BISWbemInternalContext@@@; const CSWbemNamedValueSet::`vftable'{for `ISWbemInternalContext'}
0x180022d94  mov     [rcx+8], rax
0x180022d98  lea     rax, ??_7CSWbemNamedValueSet@@6BIObjectSafety@@@; const CSWbemNamedValueSet::`vftable'{for `IObjectSafety'}
0x180022d9f  mov     [rcx+10h], rax
0x180022da3  lea     rax, ??_7CSWbemNamedValueSet@@6BISupportErrorInfo@@@; const CSWbemNamedValueSet::`vftable'{for `ISupportErrorInfo'}
0x180022daa  mov     [rcx+18h], rax
0x180022dae  lea     rax, ??_7CSWbemNamedValueSet@@6BIProvideClassInfo@@@; const CSWbemNamedValueSet::`vftable'{for `IProvideClassInfo'}
0x180022db5  mov     [rcx+20h], rax
0x180022db9  mov     qword ptr [rcx+28h], 0
0x180022dc1  lea     rbx, [rcx+30h]
0x180022dc5  mov     qword ptr [rbx], 0
0x180022dcc  add     rcx, 38h ; '8'; this
0x180022dd0  mov     qword ptr [rcx+18h], 0
0x180022dd8  mov     qword ptr [rcx+20h], 0
0x180022de0  mov     qword ptr [rcx+28h], 0
0x180022de8  mov     qword ptr [rcx+8], 0
0x180022df0  mov     dword ptr [rcx+10h], 0
0x180022df7  lea     rax, ??_7CContextDispatchHelp@CSWbemNamedValueSet@@6B@; const CSWbemNamedValueSet::CContextDispatchHelp::`vftable'
0x180022dfe  mov     [rcx], rax
0x180022e01  mov     [rdi+88h], rdx
0x180022e08  mov     [rdi+90h], r8b
0x180022e0f  mov     dword ptr [rdi+94h], 0
0x180022e19  movups  xmm0, xmmword ptr cs:CLSID_SWbemNamedValueSet.Data1
0x180022e20  movdqu  [rsp+58h+var_28], xmm0
0x180022e26  movups  xmm1, xmmword ptr cs:IID_ISWbemNamedValueSet.Data1
0x180022e2d  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm1
0x180022e33  lea     rax, aSwbemnamedvalu; "SWbemNamedValueSet"
0x180022e3a  mov     [r11-38h], rax
0x180022e3e  lea     r9, [r11-28h]; struct _GUID *
0x180022e42  lea     r8, [r11-18h]; struct _GUID *
0x180022e46  mov     rdx, rdi; struct IDispatch *
0x180022e49  call    ?SetObj@CDispatchHelp@@QEAAXPEAUIDispatch@@U_GUID@@1PEAG@Z; CDispatchHelp::SetObj(IDispatch *,_GUID,_GUID,ushort *)
0x180022e4e  mov     [rsp+58h+ppv], rbx; ppv
0x180022e53  lea     r9, IID_IWbemContext; riid
0x180022e5a  xor     edx, edx; pUnkOuter
0x180022e5c  lea     r8d, [rdx+1]; dwClsContext
0x180022e60  lea     rcx, CLSID_WbemContext; rclsid
0x180022e67  call    cs:__imp_CoCreateInstance
0x180022e6d  mov     rcx, [rdi+88h]
0x180022e74  test    rcx, rcx
0x180022e77  jz      short loc_180022E99
0x180022e79  mov     rax, [rcx]
0x180022e7c  mov     rax, [rax+8]
0x180022e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e85  inc     dword ptr [rdi+94h]
0x180022e8b  mov     rcx, rdi; this
0x180022e8e  call    ?BuildContextFromKeyList@CSWbemNamedValueSet@@AEAAXXZ; CSWbemNamedValueSet::BuildContextFromKeyList(void)
0x180022e93  dec     dword ptr [rdi+94h]
0x180022e99  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180022ea0  mov     rax, rdi
0x180022ea3  mov     rbx, [rsp+58h+arg_8]
0x180022ea8  add     rsp, 50h
0x180022eac  pop     rdi
0x180022ead  retn
```

# CSWbemPrivilegeSet::CSWbemPrivilegeSet(ISWbemPrivilegeSet *)

- ea: `0x18001c274`
- end: `0x18001c4bc`
- name: `??0CSWbemPrivilegeSet@@QEAA@PEAUISWbemPrivilegeSet@@@Z`
- size: `584`
- prototype: `CSWbemPrivilegeSet *__fastcall(CSWbemPrivilegeSet *__hidden this, struct ISWbemPrivilegeSet *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001e5dc`

## callees

- `0x180010a9c`
- `0x1800126c0`
- `0x18001a020`
- `0x18001c274`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001c398`
- `OLEAUT32!__imp_VariantInit` at `0x18001c398`
- `OLEAUT32!__imp_VariantClear` at `0x18001c471`
- `OLEAUT32!__imp_VariantClear` at `0x18001c480`
- `OLEAUT32!__imp_VariantClear` at `0x18001c471`
- `OLEAUT32!__imp_VariantClear` at `0x18001c480`

## string_xrefs

- `0x18001c303`: `SWbemPrivilegeSet`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CSWbemPrivilegeSet *__fastcall CSWbemPrivilegeSet::CSWbemPrivilegeSet(
        CSWbemPrivilegeSet *this,
        struct ISWbemPrivilegeSet *a2)
{
  __int64 v5; // [rsp+30h] [rbp-19h] BYREF
  __int64 v6; // [rsp+38h] [rbp-11h] BYREF
  struct _GUID v7; // [rsp+40h] [rbp-9h] BYREF
  struct _GUID v8; // [rsp+50h] [rbp+7h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp+17h] BYREF
  unsigned __int16 v10; // [rsp+B8h] [rbp+6Fh] BYREF
  WbemPrivilegeEnum v11; // [rsp+C0h] [rbp+77h] BYREF
  int v12; // [rsp+C8h] [rbp+7Fh] BYREF

  *(_QWORD *)this = &CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'};
  *((_QWORD *)this + 1) = &CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 2) = &CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 4) = &CDispatchHelp::`vftable';
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  std::map<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>>::map<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>>((char *)this + 112);
  v8 = CLSID_SWbemPrivilegeSet;
  v7 = IID_ISWbemPrivilegeSet;
  CDispatchHelp::SetObj(
    (CSWbemPrivilegeSet *)((char *)this + 32),
    (struct IDispatch *)this,
    &v7,
    &v8,
    (OLECHAR *)L"SWbemPrivilegeSet");
  *((_DWORD *)this + 32) = 1;
  *((_BYTE *)this + 24) = 1;
  if ( a2 )
  {
    *(_QWORD *)&v7.Data1 = 0;
    if ( ((int (__fastcall *)(struct ISWbemPrivilegeSet *, struct _GUID *))a2->lpVtbl->get__NewEnum)(a2, &v7) >= 0 )
    {
      v6 = 0;
      if ( (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v7.Data1)(
             *(_QWORD *)&v7.Data1,
             &IID_IEnumVARIANT,
             &v6) >= 0 )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        v12 = 0;
        while ( !(*(unsigned int (__fastcall **)(__int64, __int64, VARIANTARG *, int *))(*(_QWORD *)v6 + 24LL))(
                   v6,
                   1,
                   &pvarg,
                   &v12) )
        {
          if ( pvarg.vt == 9 )
          {
            v5 = 0;
            if ( (**(int (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(
                   pvarg.llVal,
                   &IID_ISWbemPrivilege,
                   &v5) >= 0 )
            {
              v11 = 0;
              v10 = 0;
              *(_QWORD *)&v8.Data1 = 0;
              (*(void (__fastcall **)(__int64, WbemPrivilegeEnum *))(*(_QWORD *)v5 + 88LL))(v5, &v11);
              (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v5 + 56LL))(v5, &v10);
              if ( (int)CSWbemPrivilegeSet::Add(this, v11, v10, (struct ISWbemPrivilege **)&v8) >= 0 )
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v8.Data1 + 16LL))(*(_QWORD *)&v8.Data1);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
            }
          }
          VariantClear(&pvarg);
        }
        VariantClear(&pvarg);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v7.Data1 + 16LL))(*(_QWORD *)&v7.Data1);
    }
  }
  _InterlockedAdd(&g_cObj, 1u);
  return this;
}

```

## disassembly

```asm
0x18001c274  mov     [rsp-8+arg_0], rcx
0x18001c279  push    rbp
0x18001c27a  push    rbx
0x18001c27b  push    rsi
0x18001c27c  push    rdi
0x18001c27d  lea     rbp, [rsp-3Fh]
0x18001c282  sub     rsp, 88h
0x18001c289  mov     rsi, rdx
0x18001c28c  mov     rdi, rcx
0x18001c28f  lea     rax, ??_7CSWbemPrivilegeSet@@6BISWbemPrivilegeSet@@@; const CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'}
0x18001c296  mov     [rcx], rax
0x18001c299  lea     rax, ??_7CSWbemPrivilegeSet@@6BISupportErrorInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'}
0x18001c2a0  mov     [rcx+8], rax
0x18001c2a4  lea     rax, ??_7CSWbemPrivilegeSet@@6BIProvideClassInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'}
0x18001c2ab  mov     [rcx+10h], rax
0x18001c2af  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x18001c2b6  mov     [rcx+20h], rax
0x18001c2ba  mov     qword ptr [rcx+38h], 0
0x18001c2c2  mov     qword ptr [rcx+40h], 0
0x18001c2ca  mov     qword ptr [rcx+48h], 0
0x18001c2d2  mov     qword ptr [rcx+28h], 0
0x18001c2da  mov     dword ptr [rcx+30h], 0
0x18001c2e1  add     rcx, 70h ; 'p'
0x18001c2e5  call    ??0?$map@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@@std@@QEAA@XZ; std::map<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>>::map<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>>(void)
0x18001c2ea  nop
0x18001c2eb  movups  xmm0, xmmword ptr cs:CLSID_SWbemPrivilegeSet.Data1
0x18001c2f2  movdqu  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x18001c2f7  movups  xmm1, xmmword ptr cs:IID_ISWbemPrivilegeSet.Data1
0x18001c2fe  movdqu  xmmword ptr [rbp+57h+var_60.Data1], xmm1
0x18001c303  lea     rax, aSwbemprivilege_0; "SWbemPrivilegeSet"
0x18001c30a  mov     [rsp+0A0h+psz], rax; psz
0x18001c30f  lea     r9, [rbp+57h+var_50]; struct _GUID *
0x18001c313  lea     r8, [rbp+57h+var_60]; struct _GUID *
0x18001c317  mov     rdx, rdi; struct IDispatch *
0x18001c31a  lea     rcx, [rdi+20h]; this
0x18001c31e  call    ?SetObj@CDispatchHelp@@QEAAXPEAUIDispatch@@U_GUID@@1PEAG@Z; CDispatchHelp::SetObj(IDispatch *,_GUID,_GUID,ushort *)
0x18001c323  mov     ebx, 1
0x18001c328  mov     [rdi+80h], ebx
0x18001c32e  mov     [rdi+18h], bl
0x18001c331  test    rsi, rsi
0x18001c334  jz      loc_18001C4A6
0x18001c33a  mov     qword ptr [rbp+57h+var_60.Data1], 0
0x18001c342  mov     rax, [rsi]
0x18001c345  lea     rdx, [rbp+57h+var_60]
0x18001c349  mov     rcx, rsi
0x18001c34c  mov     rax, [rax+38h]
0x18001c350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c355  test    eax, eax
0x18001c357  js      loc_18001C4A6
0x18001c35d  mov     [rbp+57h+var_68], 0
0x18001c365  mov     rcx, qword ptr [rbp+57h+var_60.Data1]
0x18001c369  mov     rax, [rcx]
0x18001c36c  lea     r8, [rbp+57h+var_68]
0x18001c370  lea     rdx, IID_IEnumVARIANT
0x18001c377  mov     rax, [rax]
0x18001c37a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c37f  test    eax, eax
0x18001c381  js      loc_18001C496
0x18001c387  xorps   xmm0, xmm0
0x18001c38a  xor     eax, eax
0x18001c38c  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001c390  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001c394  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001c398  call    cs:__imp_VariantInit
0x18001c39e  mov     [rbp+57h+arg_18], 0
0x18001c3a5  mov     rcx, [rbp+57h+var_68]
0x18001c3a9  mov     rax, [rcx]
0x18001c3ac  lea     r9, [rbp+57h+arg_18]
0x18001c3b0  lea     r8, [rbp+57h+pvarg]
0x18001c3b4  mov     edx, ebx
0x18001c3b6  mov     rax, [rax+18h]
0x18001c3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3bf  test    eax, eax
0x18001c3c1  jnz     loc_18001C47C
0x18001c3c7  mov     eax, 9
0x18001c3cc  cmp     ax, word ptr [rbp+57h+pvarg]
0x18001c3d0  jnz     loc_18001C46D
0x18001c3d6  mov     [rbp+57h+var_70], 0
0x18001c3de  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x18001c3e2  mov     rax, [rcx]
0x18001c3e5  lea     r8, [rbp+57h+var_70]
0x18001c3e9  lea     rdx, IID_ISWbemPrivilege
0x18001c3f0  mov     rax, [rax]
0x18001c3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3f8  test    eax, eax
0x18001c3fa  js      short loc_18001C46D
0x18001c3fc  mov     [rbp+57h+arg_10], 0
0x18001c403  xor     eax, eax
0x18001c405  mov     [rbp+57h+arg_8], ax
0x18001c409  mov     qword ptr [rbp+57h+var_50.Data1], rax
0x18001c40d  mov     rcx, [rbp+57h+var_70]
0x18001c411  mov     rax, [rcx]
0x18001c414  lea     rdx, [rbp+57h+arg_10]
0x18001c418  mov     rax, [rax+58h]
0x18001c41c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c421  mov     rcx, [rbp+57h+var_70]
0x18001c425  mov     rax, [rcx]
0x18001c428  lea     rdx, [rbp+57h+arg_8]
0x18001c42c  mov     rax, [rax+38h]
0x18001c430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c435  lea     r9, [rbp+57h+var_50]; struct ISWbemPrivilege **
0x18001c439  movzx   r8d, [rbp+57h+arg_8]; __int16
0x18001c43e  mov     edx, [rbp+57h+arg_10]; enum WbemPrivilegeEnum
0x18001c441  mov     rcx, rdi; this
0x18001c444  call    ?Add@CSWbemPrivilegeSet@@UEAAJW4WbemPrivilegeEnum@@FPEAPEAUISWbemPrivilege@@@Z; CSWbemPrivilegeSet::Add(WbemPrivilegeEnum,short,ISWbemPrivilege * *)
0x18001c449  test    eax, eax
0x18001c44b  js      short loc_18001C45D
0x18001c44d  mov     rcx, qword ptr [rbp+57h+var_50.Data1]
0x18001c451  mov     rax, [rcx]
0x18001c454  mov     rax, [rax+10h]
0x18001c458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c45d  mov     rcx, [rbp+57h+var_70]
0x18001c461  mov     rax, [rcx]
0x18001c464  mov     rax, [rax+10h]
0x18001c468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c46d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001c471  call    cs:__imp_VariantClear
0x18001c477  jmp     loc_18001C3A5
0x18001c47c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001c480  call    cs:__imp_VariantClear
0x18001c486  mov     rcx, [rbp+57h+var_68]
0x18001c48a  mov     rax, [rcx]
0x18001c48d  mov     rax, [rax+10h]
0x18001c491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c496  mov     rcx, qword ptr [rbp+57h+var_60.Data1]
0x18001c49a  mov     rax, [rcx]
0x18001c49d  mov     rax, [rax+10h]
0x18001c4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4a6  lock add cs:?g_cObj@@3JA, ebx; long g_cObj
0x18001c4ad  mov     rax, rdi
0x18001c4b0  add     rsp, 88h
0x18001c4b7  pop     rdi
0x18001c4b8  pop     rsi
0x18001c4b9  pop     rbx
0x18001c4ba  pop     rbp
0x18001c4bb  retn
```

# CWbemDispatchMgr::InvokeWbemMethod(long,tagDISPPARAMS *,tagVARIANT *)

- ea: `0x1800028b0`
- end: `0x180002bb1`
- name: `?InvokeWbemMethod@CWbemDispatchMgr@@AEAAJJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `769`
- prototype: `__int64 __fastcall(CWbemDispatchMgr *__hidden this, int, struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800055c0`

## callees

- `0x1800028b0`
- `0x180002bc0`
- `0x18000311c`
- `0x180003140`
- `0x180003170`
- `0x1800036e0`
- `0x180003a10`
- `0x1800077d0`
- `0x180013750`
- `0x1800184d4`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002b50`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b50`
- `OLEAUT32!__imp_VariantInit` at `0x1800029db`
- `OLEAUT32!__imp_VariantInit` at `0x1800029db`
- `OLEAUT32!__imp_VariantClear` at `0x180002aef`
- `OLEAUT32!__imp_VariantClear` at `0x180002aef`

## string_xrefs

- `0x1800029fd`: `__RELPATH`

## pseudocode

```c
__int64 __fastcall CWbemDispatchMgr::InvokeWbemMethod(
        CWbemDispatchMgr *this,
        int a2,
        struct tagDISPPARAMS *a3,
        struct tagVARIANT *a4)
{
  int v6; // r10d
  int v8; // edi
  __int64 v9; // r8
  OLECHAR *v10; // rbx
  __int64 *v11; // r8
  __int64 v12; // rax
  struct IWbemServices *IWbemServices; // r14
  CSWbemSecurity *SecurityInfo; // rax
  CSWbemSecurity *v15; // r15
  CSWbemSecurity *v16; // rcx
  __int64 i; // rcx
  struct IWbemClassObject *v19; // [rsp+50h] [rbp-39h] BYREF
  struct IWbemClassObject *v20; // [rsp+58h] [rbp-31h] BYREF
  struct IWbemClassObject *v21; // [rsp+60h] [rbp-29h] BYREF
  struct IWbemClassObject *v22; // [rsp+68h] [rbp-21h] BYREF
  void *v23; // [rsp+70h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-11h] BYREF
  OLECHAR *v25; // [rsp+90h] [rbp+7h]
  struct IWbemServices *v26; // [rsp+98h] [rbp+Fh]
  bool v27; // [rsp+F0h] [rbp+67h] BYREF

  v6 = a2;
  v8 = -2147467259;
  if ( !*((_QWORD *)this + 4) )
    return (unsigned int)v8;
  v9 = *((_QWORD *)this + 8);
  if ( !v9 )
    return (unsigned int)v8;
  if ( !a3->cNamedArgs )
  {
    v10 = 0;
    v25 = 0;
    v11 = *(__int64 **)(v9 + 16);
    v12 = *v11;
    while ( (__int64 *)v12 != v11 )
    {
      if ( v6 == *(_DWORD *)(v12 + 48) )
      {
        if ( *(_QWORD *)(v12 + 32) )
        {
          v10 = ATL::CComBSTR::Copy((ATL::CComBSTR *)(v12 + 32));
          v25 = v10;
        }
        v22 = 0;
        v21 = 0;
        v8 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, struct IWbemClassObject **, struct IWbemClassObject **))(**((_QWORD **)this + 5) + 152LL))(
               *((_QWORD *)this + 5),
               v10,
               0,
               &v22,
               &v21);
        if ( v8 >= 0 )
        {
          v20 = 0;
          if ( !v22 || (v8 = CWbemDispatchMgr::MapInParameters(this, a3, v22, &v20), v8 >= 0) )
          {
            v26 = 0;
            IWbemServices = CSWbemServices::GetIWbemServices(*((CSWbemServices **)this + 4));
            v26 = IWbemServices;
            if ( IWbemServices )
            {
              memset(&pvarg, 0, sizeof(pvarg));
              VariantInit(&pvarg);
              v8 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 32LL))(
                     *((_QWORD *)this + 2),
                     L"__RELPATH",
                     0,
                     &pvarg,
                     0,
                     0);
              if ( v8 >= 0 )
              {
                if ( pvarg.vt == 8 )
                {
                  v19 = 0;
                  v27 = 0;
                  v23 = 0;
                  SecurityInfo = CSWbemServices::GetSecurityInfo(*((CSWbemServices **)this + 4));
                  v15 = SecurityInfo;
                  if ( SecurityInfo )
                  {
                    if ( (unsigned int)CSWbemSecurity::SetSecurity(SecurityInfo, &v27, &v23) )
                    {
                      v8 = ((__int64 (__fastcall *)(struct IWbemServices *, LONGLONG, OLECHAR *, _QWORD, _QWORD, struct IWbemClassObject *, struct IWbemClassObject **, _QWORD))IWbemServices->lpVtbl->ExecMethod)(
                             IWbemServices,
                             pvarg.llVal,
                             v10,
                             0,
                             0,
                             v20,
                             &v19,
                             0);
                      if ( v8 >= 0 )
                        v8 = CWbemDispatchMgr::MapOutParameters(this, a3, v21, v19, a4);
                      SetWbemError(*((struct CSWbemServices **)this + 4));
                    }
                    if ( v27 )
                      CSWbemSecurity::ResetSecurity(v16, v23);
                    (*(void (__fastcall **)(CSWbemSecurity *))(*(_QWORD *)v15 + 16LL))(v15);
                  }
                  if ( v19 )
                    ((void (__fastcall *)(struct IWbemClassObject *))v19->lpVtbl->Release)(v19);
                }
                else
                {
                  v8 = -2147217407;
                }
              }
              VariantClear(&pvarg);
            }
            if ( IWbemServices )
              ((void (__fastcall *)(struct IWbemServices *))IWbemServices->lpVtbl->Release)(IWbemServices);
          }
          if ( v20 )
            ((void (__fastcall *)(struct IWbemClassObject *))v20->lpVtbl->Release)(v20);
        }
        if ( v21 )
          ((void (__fastcall *)(struct IWbemClassObject *))v21->lpVtbl->Release)(v21);
        if ( v22 )
          ((void (__fastcall *)(struct IWbemClassObject *))v22->lpVtbl->Release)(v22);
        break;
      }
      if ( !*(_BYTE *)(v12 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)(v12 + 16) + 25LL) )
        {
          for ( i = *(_QWORD *)(v12 + 8); !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
          {
            if ( v12 != *(_QWORD *)(i + 16) )
              break;
            v12 = i;
          }
          v12 = i;
        }
        else
        {
          v12 = std::_Tree_val<std::_Tree_simple_types<std::pair<long const,CSWbemRefreshableItem *>>>::_Min();
        }
      }
    }
    SysFreeString(v10);
    return (unsigned int)v8;
  }
  return 2147614727LL;
}

```

## disassembly

```asm
0x1800028b0  push    rbp
0x1800028b2  push    rbx
0x1800028b3  push    rsi
0x1800028b4  push    rdi
0x1800028b5  push    r12
0x1800028b7  push    r13
0x1800028b9  push    r14
0x1800028bb  push    r15
0x1800028bd  lea     rbp, [rsp-1Fh]
0x1800028c2  sub     rsp, 0A8h
0x1800028c9  mov     r13, r9
0x1800028cc  mov     r12, r8
0x1800028cf  mov     r10d, edx
0x1800028d2  mov     rsi, rcx
0x1800028d5  mov     edi, 80004005h
0x1800028da  cmp     qword ptr [rcx+20h], 0
0x1800028df  jz      loc_180002B56
0x1800028e5  mov     r8, [rcx+40h]
0x1800028e9  test    r8, r8
0x1800028ec  jz      loc_180002B56
0x1800028f2  cmp     dword ptr [r12+14h], 0
0x1800028f8  ja      loc_180002B6C
0x1800028fe  xor     r15d, r15d
0x180002901  mov     ebx, r15d
0x180002904  mov     [rbp+57h+var_50], rbx
0x180002908  mov     r8, [r8+10h]
0x18000290c  mov     rax, [r8]
0x18000290f  cmp     rax, r8
0x180002912  jz      loc_180002B4D
0x180002918  cmp     r10d, [rax+30h]
0x18000291c  jz      short loc_180002939
0x18000291e  cmp     byte ptr [rax+19h], 0
0x180002922  jnz     short loc_18000290F
0x180002924  mov     rcx, [rax+10h]
0x180002928  cmp     byte ptr [rcx+19h], 0
0x18000292c  jnz     loc_180002B73
0x180002932  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBJPEAVCSWbemRefreshableItem@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBJPEAVCSWbemRefreshableItem@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<long const,CSWbemRefreshableItem *>>>::_Min(std::_Tree_node<std::pair<long const,CSWbemRefreshableItem *>,void *> *)
0x180002937  jmp     short loc_18000290F
0x180002939  lea     rcx, [rax+20h]; this
0x18000293d  cmp     qword ptr [rcx], 0
0x180002941  jz      short loc_18000294F
0x180002943  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x180002948  mov     rbx, rax
0x18000294b  mov     [rbp+57h+var_50], rax
0x18000294f  mov     [rbp+57h+var_78], r15
0x180002953  mov     [rbp+57h+var_80], r15
0x180002957  mov     rcx, [rsi+28h]
0x18000295b  mov     rax, [rcx]
0x18000295e  lea     rdx, [rbp+57h+var_80]
0x180002962  mov     [rsp+0E0h+var_C0], rdx
0x180002967  lea     r9, [rbp+57h+var_78]
0x18000296b  xor     r8d, r8d
0x18000296e  mov     rdx, rbx
0x180002971  mov     rax, [rax+98h]
0x180002978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000297d  mov     edi, eax
0x18000297f  test    eax, eax
0x180002981  js      loc_180002B21
0x180002987  mov     [rbp+57h+var_88], r15
0x18000298b  mov     r8, [rbp+57h+var_78]; struct IWbemClassObject *
0x18000298f  test    r8, r8
0x180002992  jz      short loc_1800029AD
0x180002994  lea     r9, [rbp+57h+var_88]; struct IWbemClassObject **
0x180002998  mov     rdx, r12; struct tagDISPPARAMS *
0x18000299b  mov     rcx, rsi; this
0x18000299e  call    ?MapInParameters@CWbemDispatchMgr@@AEAAJPEAUtagDISPPARAMS@@PEAUIWbemClassObject@@PEAPEAU3@@Z; CWbemDispatchMgr::MapInParameters(tagDISPPARAMS *,IWbemClassObject *,IWbemClassObject * *)
0x1800029a3  mov     edi, eax
0x1800029a5  test    eax, eax
0x1800029a7  js      loc_180002B0B
0x1800029ad  mov     [rbp+57h+var_48], r15
0x1800029b1  mov     rcx, [rsi+20h]; this
0x1800029b5  call    ?GetIWbemServices@CSWbemServices@@QEAAPEAUIWbemServices@@XZ; CSWbemServices::GetIWbemServices(void)
0x1800029ba  mov     r14, rax
0x1800029bd  mov     [rbp+57h+var_48], rax
0x1800029c1  test    rax, rax
0x1800029c4  jz      loc_180002AF6
0x1800029ca  xorps   xmm0, xmm0
0x1800029cd  xor     eax, eax
0x1800029cf  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800029d3  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800029d7  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800029db  call    cs:__imp_VariantInit
0x1800029e1  mov     rcx, [rsi+10h]
0x1800029e5  mov     rdx, [rcx]
0x1800029e8  mov     rax, [rdx+20h]
0x1800029ec  mov     [rsp+0E0h+var_B8], r15
0x1800029f1  mov     [rsp+0E0h+var_C0], r15
0x1800029f6  lea     r9, [rbp+57h+pvarg]
0x1800029fa  xor     r8d, r8d
0x1800029fd  lea     rdx, aRelpath; "__RELPATH"
0x180002a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a09  mov     edi, eax
0x180002a0b  test    eax, eax
0x180002a0d  js      loc_180002AEB
0x180002a13  mov     eax, 8
0x180002a18  cmp     ax, word ptr [rbp+57h+pvarg]
0x180002a1c  jnz     loc_180002BA6
0x180002a22  mov     [rbp+57h+var_90], r15
0x180002a26  mov     [rbp+57h+arg_0], 0
0x180002a2a  mov     [rbp+57h+var_70], r15
0x180002a2e  mov     rcx, [rsi+20h]; this
0x180002a32  call    ?GetSecurityInfo@CSWbemServices@@QEAAPEAVCSWbemSecurity@@XZ; CSWbemServices::GetSecurityInfo(void)
0x180002a37  mov     r15, rax
0x180002a3a  test    rax, rax
0x180002a3d  jz      loc_180002AD5
0x180002a43  lea     r8, [rbp+57h+var_70]; void **
0x180002a47  lea     rdx, [rbp+57h+arg_0]; bool *
0x180002a4b  mov     rcx, rax; this
0x180002a4e  call    ?SetSecurity@CSWbemSecurity@@QEAAHAEA_NAEAPEAX@Z; CSWbemSecurity::SetSecurity(bool &,void * &)
0x180002a53  test    eax, eax
0x180002a55  jz      short loc_180002ABB
0x180002a57  mov     rdx, [rbp+57h+var_88]
0x180002a5b  mov     rcx, [r14]
0x180002a5e  mov     rax, [rcx+0C0h]
0x180002a65  xor     r8d, r8d
0x180002a68  mov     [rsp+0E0h+var_A8], r8
0x180002a6d  lea     rcx, [rbp+57h+var_90]
0x180002a71  mov     [rsp+0E0h+var_B0], rcx
0x180002a76  mov     [rsp+0E0h+var_B8], rdx
0x180002a7b  mov     [rsp+0E0h+var_C0], r8
0x180002a80  xor     r9d, r9d
0x180002a83  mov     r8, rbx
0x180002a86  mov     rdx, qword ptr [rbp+57h+pvarg+8]
0x180002a8a  mov     rcx, r14
0x180002a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a92  mov     edi, eax
0x180002a94  test    eax, eax
0x180002a96  js      short loc_180002AB2
0x180002a98  mov     [rsp+0E0h+var_C0], r13; struct tagVARIANT *
0x180002a9d  mov     r9, [rbp+57h+var_90]; struct IWbemClassObject *
0x180002aa1  mov     r8, [rbp+57h+var_80]; struct IWbemClassObject *
0x180002aa5  mov     rdx, r12; struct tagDISPPARAMS *
0x180002aa8  mov     rcx, rsi; this
0x180002aab  call    ?MapOutParameters@CWbemDispatchMgr@@AEAAJPEAUtagDISPPARAMS@@PEAUIWbemClassObject@@1PEAUtagVARIANT@@@Z; CWbemDispatchMgr::MapOutParameters(tagDISPPARAMS *,IWbemClassObject *,IWbemClassObject *,tagVARIANT *)
0x180002ab0  mov     edi, eax
0x180002ab2  mov     rcx, [rsi+20h]; this
0x180002ab6  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x180002abb  cmp     [rbp+57h+arg_0], 0
0x180002abf  jnz     loc_180002B98
0x180002ac5  mov     rax, [r15]
0x180002ac8  mov     rcx, r15
0x180002acb  mov     rax, [rax+10h]
0x180002acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ad4  nop
0x180002ad5  mov     rcx, [rbp+57h+var_90]
0x180002ad9  test    rcx, rcx
0x180002adc  jz      short loc_180002AEB
0x180002ade  mov     rax, [rcx]
0x180002ae1  mov     rax, [rax+10h]
0x180002ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aea  nop
0x180002aeb  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180002aef  call    cs:__imp_VariantClear
0x180002af5  nop
0x180002af6  test    r14, r14
0x180002af9  jz      short loc_180002B0B
0x180002afb  mov     rax, [r14]
0x180002afe  mov     rcx, r14
0x180002b01  mov     rax, [rax+10h]
0x180002b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b0a  nop
0x180002b0b  mov     rcx, [rbp+57h+var_88]
0x180002b0f  test    rcx, rcx
0x180002b12  jz      short loc_180002B21
0x180002b14  mov     rax, [rcx]
0x180002b17  mov     rax, [rax+10h]
0x180002b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b20  nop
0x180002b21  mov     rcx, [rbp+57h+var_80]
0x180002b25  test    rcx, rcx
0x180002b28  jz      short loc_180002B37
0x180002b2a  mov     rax, [rcx]
0x180002b2d  mov     rax, [rax+10h]
0x180002b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b36  nop
0x180002b37  mov     rcx, [rbp+57h+var_78]
0x180002b3b  test    rcx, rcx
0x180002b3e  jz      short loc_180002B4D
0x180002b40  mov     rax, [rcx]
0x180002b43  mov     rax, [rax+10h]
0x180002b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b4c  nop
0x180002b4d  mov     rcx, rbx; bstrString
0x180002b50  call    cs:__imp_SysFreeString
0x180002b56  mov     eax, edi
0x180002b58  add     rsp, 0A8h
0x180002b5f  pop     r15
0x180002b61  pop     r14
0x180002b63  pop     r13
0x180002b65  pop     r12
0x180002b67  pop     rdi
0x180002b68  pop     rsi
0x180002b69  pop     rbx
0x180002b6a  pop     rbp
0x180002b6b  retn
0x180002b6c  mov     eax, 80020007h
0x180002b71  jmp     short loc_180002B58
0x180002b73  mov     rcx, [rax+8]
0x180002b77  cmp     byte ptr [rcx+19h], 0
0x180002b7b  jnz     short loc_180002B90
0x180002b7d  cmp     rax, [rcx+10h]
0x180002b81  jnz     short loc_180002B90
0x180002b83  mov     rax, rcx
0x180002b86  mov     rcx, [rcx+8]
0x180002b8a  cmp     byte ptr [rcx+19h], 0
0x180002b8e  jz      short loc_180002B7D
0x180002b90  mov     rax, rcx
0x180002b93  jmp     loc_18000290F
0x180002b98  mov     rdx, [rbp+57h+var_70]; void *
0x180002b9c  call    ?ResetSecurity@CSWbemSecurity@@QEAAXPEAX@Z; CSWbemSecurity::ResetSecurity(void *)
0x180002ba1  jmp     loc_180002AC5
0x180002ba6  mov     edi, 80041001h
0x180002bab  jmp     loc_180002AEB
```

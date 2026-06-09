# CWcnUpnpTransport::Init(void)

- ea: `0x18003f2c0`
- end: `0x18003f6b8`
- name: `?Init@CWcnUpnpTransport@@UEAAJXZ`
- size: `1016`
- prototype: `__int64 __fastcall(CWcnUpnpTransport *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18003ebe0`
- `0x18003f2c0`
- `0x18003fec8`
- `0x1800402e4`
- `0x180042290`
- `0x180043338`
- `0x180053004`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f540`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f540`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003f64c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003f64c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003f326`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003f326`

## pseudocode

```c
__int64 __fastcall CWcnUpnpTransport::Init(CWcnUpnpTransport *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  HRESULT v4; // eax
  int v5; // ebx
  _BYTE *v6; // r10
  HRESULT Instance; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  _QWORD *v10; // r10
  const char *v11; // rax
  __int64 v12; // r10
  struct IUnknown **v13; // r14
  int v14; // eax
  CWcnUpnpGit *v15; // rcx
  RTL_SRWLOCK *v16; // rcx
  unsigned int v17; // eax
  __int64 v18; // r10
  __int64 v19; // r9
  __int64 v20; // rcx
  unsigned int v21; // eax
  __int64 v22; // r10
  __int64 v24; // [rsp+58h] [rbp+10h] BYREF
  RTL_SRWLOCK *v25; // [rsp+60h] [rbp+18h] BYREF

  v24 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 10, WPP_1038bd85cc6033fecb4c6bfd5194080f_Traceguids, Indent);
  }
  v4 = CoInitializeEx(0, 4u);
  v5 = v4;
  if ( v4 >= 0 )
  {
    Instance = WcnUpnpReferenceGit();
    v5 = Instance;
    if ( Instance < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_60;
      v9 = 12;
      goto LABEL_58;
    }
    *((_BYTE *)this + 18) = 1;
    v25 = 0;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v11 = GetIndent(1);
      WPP_SF_s(*(_QWORD *)(v12 + 16), 10, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids, v11);
      v10 = WPP_GLOBAL_Control;
    }
    v13 = (struct IUnknown **)((char *)this + 32);
    if ( this == (CWcnUpnpTransport *)-32LL )
    {
      if ( v10 != &WPP_GLOBAL_Control && *((_BYTE *)v10 + 25) >= 2u )
      {
        WPP_SF_s(v10[2], 12, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids, "ppCallback");
        v10 = WPP_GLOBAL_Control;
      }
      v5 = -2147467261;
      goto LABEL_31;
    }
    *v13 = 0;
    v14 = ATL::CComObject<CWcnUpnpDiscoveryListener>::CreateInstance(&v25);
    v5 = v14;
    if ( v14 >= 0 )
    {
      v16 = v25;
      v25[8].Ptr = this;
      *v13 = (struct IUnknown *)v16;
      (*((void (__fastcall **)(RTL_SRWLOCK *))v16->Ptr + 1))(v16);
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_30;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_26:
        if ( v10 != &WPP_GLOBAL_Control && (v5 < 0 || *((_BYTE *)v10 + 25) >= 6u) )
        {
          v17 = (unsigned int)GetIndent(-1);
          WPP_SF_sd(*(_QWORD *)(v18 + 16), 14, (unsigned int)WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids, v17, v5);
          v10 = WPP_GLOBAL_Control;
        }
LABEL_30:
        if ( v5 >= 0 )
        {
          Instance = CWcnUpnpGit::PutItem(
                       v15,
                       &GUID_415a984a_88b3_49f3_92af_0508bedf0d6c,
                       *v13,
                       (unsigned int *)this + 10);
          v5 = Instance;
          if ( Instance >= 0 )
          {
            Instance = CoCreateInstance(
                         &CLSID_UPnPDeviceFinder,
                         0,
                         1u,
                         &GUID_adda3d55_6f72_4319_bff9_18600a539b10,
                         (LPVOID *)this + 3);
            v5 = Instance;
            if ( Instance >= 0 )
            {
              Instance = WcnUpnpInitializeCallbackContext();
              v5 = Instance;
              if ( Instance >= 0 )
              {
                *((_BYTE *)this + 19) = 1;
                Instance = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
                             *((_QWORD *)this + 3),
                             &GUID_e3bf6178_694e_459f_a5a6_191ea0ffa1c7,
                             &v24);
                v5 = Instance;
                if ( Instance >= 0 )
                {
                  Instance = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 24LL))(v24, 3);
                  v5 = Instance;
                  if ( Instance >= 0 )
                  {
                    Instance = WcnUpnpPerformCallInContext<CWcnUpnpTransport>(
                                 this,
                                 CWcnUpnpTransport::CreateAsyncFindInner);
                    v5 = Instance;
                    if ( Instance >= 0 )
                      goto LABEL_60;
                    v8 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      goto LABEL_60;
                    }
                    v9 = 19;
                  }
                  else
                  {
                    v8 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      goto LABEL_60;
                    }
                    v9 = 18;
                  }
                }
                else
                {
                  v8 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    goto LABEL_60;
                  v9 = 17;
                }
              }
              else
              {
                v8 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  goto LABEL_60;
                v9 = 16;
              }
            }
            else
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                goto LABEL_60;
              v9 = 15;
            }
          }
          else
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_60;
            v9 = 14;
          }
LABEL_58:
          v20 = v8[2];
          v19 = (unsigned int)Instance;
LABEL_59:
          WPP_SF_d(v20, v9, WPP_1038bd85cc6033fecb4c6bfd5194080f_Traceguids, v19);
LABEL_60:
          CoUninitialize();
          goto LABEL_61;
        }
LABEL_31:
        if ( v10 == &WPP_GLOBAL_Control || *((_BYTE *)v10 + 25) < 2u )
          goto LABEL_60;
        v9 = 13;
        v19 = (unsigned int)v5;
        v20 = v10[2];
        goto LABEL_59;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids,
        (unsigned int)v14);
    }
    v10 = WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_66;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_1038bd85cc6033fecb4c6bfd5194080f_Traceguids, (unsigned int)v4);
LABEL_61:
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (_BYTE *)&WPP_GLOBAL_Control && (v5 < 0 || v6[25] >= 6u) )
  {
    v21 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v22 + 16), 20, (unsigned int)WPP_1038bd85cc6033fecb4c6bfd5194080f_Traceguids, v21, v5);
  }
LABEL_66:
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003f2c0  mov     [rsp+arg_0], rbx
0x18003f2c5  mov     [rsp+arg_18], rsi
0x18003f2ca  push    r12
0x18003f2cc  push    r14
0x18003f2ce  push    r15
0x18003f2d0  sub     rsp, 30h
0x18003f2d4  mov     rsi, rcx
0x18003f2d7  mov     [rsp+48h+arg_8], 0
0x18003f2e0  lea     r15, WPP_GLOBAL_Control
0x18003f2e7  lea     r12, WPP_1038bd85cc6033fecb4c6bfd5194080f_Traceguids
0x18003f2ee  mov     r10, cs:WPP_GLOBAL_Control
0x18003f2f5  cmp     r10, r15
0x18003f2f8  jz      short loc_18003F31F
0x18003f2fa  cmp     byte ptr [r10+19h], 6
0x18003f2ff  jb      short loc_18003F31F
0x18003f301  mov     ecx, 1; int
0x18003f306  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003f30b  mov     edx, 0Ah
0x18003f310  mov     r9, rax
0x18003f313  mov     r8, r12
0x18003f316  mov     rcx, [r10+10h]
0x18003f31a  call    WPP_SF_s
0x18003f31f  mov     edx, 4; dwCoInit
0x18003f324  xor     ecx, ecx; pvReserved
0x18003f326  call    cs:__imp_CoInitializeEx
0x18003f32c  mov     ebx, eax
0x18003f32e  test    eax, eax
0x18003f330  jns     short loc_18003F366
0x18003f332  mov     r10, cs:WPP_GLOBAL_Control
0x18003f339  cmp     r10, r15
0x18003f33c  jz      loc_18003F68A
0x18003f342  cmp     byte ptr [r10+19h], 2
0x18003f347  jb      loc_18003F659
0x18003f34d  mov     edx, 0Bh
0x18003f352  mov     r9d, eax
0x18003f355  mov     r8, r12
0x18003f358  mov     rcx, [r10+10h]
0x18003f35c  call    WPP_SF_d
0x18003f361  jmp     loc_18003F652
0x18003f366  call    ?WcnUpnpReferenceGit@@YAJXZ; WcnUpnpReferenceGit(void)
0x18003f36b  mov     ebx, eax
0x18003f36d  test    eax, eax
0x18003f36f  jns     short loc_18003F395
0x18003f371  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f378  cmp     rcx, r15
0x18003f37b  jz      loc_18003F64C
0x18003f381  cmp     byte ptr [rcx+19h], 2
0x18003f385  jb      loc_18003F64C
0x18003f38b  mov     edx, 0Ch
0x18003f390  jmp     loc_18003F63D
0x18003f395  mov     byte ptr [rsi+12h], 1
0x18003f399  mov     [rsp+48h+arg_10], 0
0x18003f3a2  mov     r10, cs:WPP_GLOBAL_Control
0x18003f3a9  cmp     r10, r15
0x18003f3ac  jz      short loc_18003F3DE
0x18003f3ae  cmp     byte ptr [r10+19h], 6
0x18003f3b3  jb      short loc_18003F3DE
0x18003f3b5  mov     ecx, 1; int
0x18003f3ba  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003f3bf  mov     edx, 0Ah
0x18003f3c4  mov     r9, rax
0x18003f3c7  lea     r8, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids
0x18003f3ce  mov     rcx, [r10+10h]
0x18003f3d2  call    WPP_SF_s
0x18003f3d7  mov     r10, cs:WPP_GLOBAL_Control
0x18003f3de  lea     r14, [rsi+20h]
0x18003f3e2  test    r14, r14
0x18003f3e5  jnz     short loc_18003F41F
0x18003f3e7  cmp     r10, r15
0x18003f3ea  jz      short loc_18003F415
0x18003f3ec  cmp     byte ptr [r10+19h], 2
0x18003f3f1  jb      short loc_18003F415
0x18003f3f3  lea     edx, [r14+0Ch]
0x18003f3f7  lea     r9, aPpcallback; "ppCallback"
0x18003f3fe  lea     r8, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids
0x18003f405  mov     rcx, [r10+10h]
0x18003f409  call    WPP_SF_s
0x18003f40e  mov     r10, cs:WPP_GLOBAL_Control
0x18003f415  mov     ebx, 80004003h
0x18003f41a  jmp     loc_18003F4C1
0x18003f41f  mov     qword ptr [r14], 0
0x18003f426  lea     rcx, [rsp+48h+arg_10]
0x18003f42b  call    ?CreateInstance@?$CComObject@VCWcnUpnpDiscoveryListener@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWcnUpnpDiscoveryListener>::CreateInstance(ATL::CComObject<CWcnUpnpDiscoveryListener> * *)
0x18003f430  mov     ebx, eax
0x18003f432  test    eax, eax
0x18003f434  jns     short loc_18003F463
0x18003f436  mov     r10, cs:WPP_GLOBAL_Control
0x18003f43d  cmp     r10, r15
0x18003f440  jz      short loc_18003F4BD
0x18003f442  cmp     byte ptr [r10+19h], 2
0x18003f447  jb      short loc_18003F482
0x18003f449  mov     edx, 0Dh
0x18003f44e  mov     r9d, eax
0x18003f451  lea     r8, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids
0x18003f458  mov     rcx, [r10+10h]
0x18003f45c  call    WPP_SF_d
0x18003f461  jmp     short loc_18003F47B
0x18003f463  mov     rcx, [rsp+48h+arg_10]
0x18003f468  mov     [rcx+40h], rsi
0x18003f46c  mov     [r14], rcx
0x18003f46f  mov     rax, [rcx]
0x18003f472  mov     rax, [rax+8]
0x18003f476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f47b  mov     r10, cs:WPP_GLOBAL_Control
0x18003f482  cmp     r10, r15
0x18003f485  jz      short loc_18003F4BD
0x18003f487  test    ebx, ebx
0x18003f489  js      short loc_18003F492
0x18003f48b  cmp     byte ptr [r10+19h], 6
0x18003f490  jb      short loc_18003F4BD
0x18003f492  or      ecx, 0FFFFFFFFh; int
0x18003f495  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003f49a  mov     edx, 0Eh
0x18003f49f  mov     dword ptr [rsp+48h+ppv], ebx
0x18003f4a3  mov     r9, rax
0x18003f4a6  lea     r8, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids
0x18003f4ad  mov     rcx, [r10+10h]
0x18003f4b1  call    WPP_SF_sd
0x18003f4b6  mov     r10, cs:WPP_GLOBAL_Control
0x18003f4bd  test    ebx, ebx
0x18003f4bf  jns     short loc_18003F4E6
0x18003f4c1  cmp     r10, r15
0x18003f4c4  jz      loc_18003F64C
0x18003f4ca  cmp     byte ptr [r10+19h], 2
0x18003f4cf  jb      loc_18003F64C
0x18003f4d5  mov     edx, 0Dh
0x18003f4da  mov     r9d, ebx
0x18003f4dd  mov     rcx, [r10+10h]
0x18003f4e1  jmp     loc_18003F644
0x18003f4e6  lea     r9, [rsi+28h]; unsigned int *
0x18003f4ea  mov     r8, [r14]; struct IUnknown *
0x18003f4ed  lea     rdx, _GUID_415a984a_88b3_49f3_92af_0508bedf0d6c; struct _GUID *
0x18003f4f4  call    ?PutItem@CWcnUpnpGit@@QEAAJAEBU_GUID@@PEAUIUnknown@@PEAK@Z; CWcnUpnpGit::PutItem(_GUID const &,IUnknown *,ulong *)
0x18003f4f9  mov     ebx, eax
0x18003f4fb  test    eax, eax
0x18003f4fd  jns     short loc_18003F523
0x18003f4ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f506  cmp     rcx, r15
0x18003f509  jz      loc_18003F64C
0x18003f50f  cmp     byte ptr [rcx+19h], 2
0x18003f513  jb      loc_18003F64C
0x18003f519  mov     edx, 0Eh
0x18003f51e  jmp     loc_18003F63D
0x18003f523  lea     r14, [rsi+18h]
0x18003f527  mov     [rsp+48h+ppv], r14; ppv
0x18003f52c  lea     r9, _GUID_adda3d55_6f72_4319_bff9_18600a539b10; riid
0x18003f533  xor     edx, edx; pUnkOuter
0x18003f535  lea     r8d, [rdx+1]; dwClsContext
0x18003f539  lea     rcx, CLSID_UPnPDeviceFinder; rclsid
0x18003f540  call    cs:__imp_CoCreateInstance
0x18003f546  mov     ebx, eax
0x18003f548  test    eax, eax
0x18003f54a  jns     short loc_18003F570
0x18003f54c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f553  cmp     rcx, r15
0x18003f556  jz      loc_18003F64C
0x18003f55c  cmp     byte ptr [rcx+19h], 2
0x18003f560  jb      loc_18003F64C
0x18003f566  mov     edx, 0Fh
0x18003f56b  jmp     loc_18003F63D
0x18003f570  call    ?WcnUpnpInitializeCallbackContext@@YAJXZ; WcnUpnpInitializeCallbackContext(void)
0x18003f575  mov     ebx, eax
0x18003f577  test    eax, eax
0x18003f579  jns     short loc_18003F59F
0x18003f57b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f582  cmp     rcx, r15
0x18003f585  jz      loc_18003F64C
0x18003f58b  cmp     byte ptr [rcx+19h], 2
0x18003f58f  jb      loc_18003F64C
0x18003f595  mov     edx, 10h
0x18003f59a  jmp     loc_18003F63D
0x18003f59f  mov     byte ptr [rsi+13h], 1
0x18003f5a3  mov     rcx, [r14]
0x18003f5a6  mov     rax, [rcx]
0x18003f5a9  lea     r8, [rsp+48h+arg_8]
0x18003f5ae  lea     rdx, _GUID_e3bf6178_694e_459f_a5a6_191ea0ffa1c7
0x18003f5b5  mov     rax, [rax]
0x18003f5b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f5bd  mov     ebx, eax
0x18003f5bf  test    eax, eax
0x18003f5c1  jns     short loc_18003F5DC
0x18003f5c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f5ca  cmp     rcx, r15
0x18003f5cd  jz      short loc_18003F64C
0x18003f5cf  cmp     byte ptr [rcx+19h], 2
0x18003f5d3  jb      short loc_18003F64C
0x18003f5d5  mov     edx, 11h
0x18003f5da  jmp     short loc_18003F63D
0x18003f5dc  mov     rcx, [rsp+48h+arg_8]
0x18003f5e1  mov     rax, [rcx]
0x18003f5e4  mov     edx, 3
0x18003f5e9  mov     rax, [rax+18h]
0x18003f5ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f5f2  mov     ebx, eax
0x18003f5f4  test    eax, eax
0x18003f5f6  jns     short loc_18003F611
0x18003f5f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f5ff  cmp     rcx, r15
0x18003f602  jz      short loc_18003F64C
0x18003f604  cmp     byte ptr [rcx+19h], 2
0x18003f608  jb      short loc_18003F64C
0x18003f60a  mov     edx, 12h
0x18003f60f  jmp     short loc_18003F63D
0x18003f611  lea     rdx, ?CreateAsyncFindInner@CWcnUpnpTransport@@AEAAJXZ; CWcnUpnpTransport::CreateAsyncFindInner(void)
0x18003f618  mov     rcx, rsi
0x18003f61b  call    ??$WcnUpnpPerformCallInContext@VCWcnUpnpTransport@@@@YAJPEAVCWcnUpnpTransport@@P80@EAAJXZ@Z; WcnUpnpPerformCallInContext<CWcnUpnpTransport>(CWcnUpnpTransport *,long (CWcnUpnpTransport::*)(void))
0x18003f620  mov     ebx, eax
0x18003f622  test    eax, eax
0x18003f624  jns     short loc_18003F64C
0x18003f626  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f62d  cmp     rcx, r15
0x18003f630  jz      short loc_18003F64C
0x18003f632  cmp     byte ptr [rcx+19h], 2
0x18003f636  jb      short loc_18003F64C
0x18003f638  mov     edx, 13h
0x18003f63d  mov     rcx, [rcx+10h]
0x18003f641  mov     r9d, eax
0x18003f644  mov     r8, r12
0x18003f647  call    WPP_SF_d
0x18003f64c  call    cs:__imp_CoUninitialize
0x18003f652  mov     r10, cs:WPP_GLOBAL_Control
0x18003f659  cmp     r10, r15
0x18003f65c  jz      short loc_18003F68A
0x18003f65e  test    ebx, ebx
0x18003f660  js      short loc_18003F669
0x18003f662  cmp     byte ptr [r10+19h], 6
0x18003f667  jb      short loc_18003F68A
0x18003f669  or      ecx, 0FFFFFFFFh; int
0x18003f66c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003f671  mov     edx, 14h
0x18003f676  mov     dword ptr [rsp+48h+ppv], ebx
0x18003f67a  mov     r9, rax
0x18003f67d  mov     r8, r12
0x18003f680  mov     rcx, [r10+10h]
0x18003f684  call    WPP_SF_sd
0x18003f689  nop
0x18003f68a  mov     rcx, [rsp+48h+arg_8]
0x18003f68f  test    rcx, rcx
0x18003f692  jz      short loc_18003F6A1
0x18003f694  mov     rax, [rcx]
0x18003f697  mov     rax, [rax+10h]
0x18003f69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6a0  nop
0x18003f6a1  mov     eax, ebx
0x18003f6a3  mov     rbx, [rsp+48h+arg_0]
0x18003f6a8  mov     rsi, [rsp+48h+arg_18]
0x18003f6ad  add     rsp, 30h
0x18003f6b1  pop     r15
0x18003f6b3  pop     r14
0x18003f6b5  pop     r12
0x18003f6b7  retn
```

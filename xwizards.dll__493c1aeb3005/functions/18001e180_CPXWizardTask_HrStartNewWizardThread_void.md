# CPXWizardTask::HrStartNewWizardThread(void *)

- ea: `0x18001e180`
- end: `0x18001e75d`
- name: `?HrStartNewWizardThread@CPXWizardTask@@CAKPEAX@Z`
- size: `1501`
- prototype: `unsigned int __fastcall(void *lpTlsValue)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x180001200`
- `0x180004370`
- `0x18000ae04`
- `0x18000ae44`
- `0x18000ae90`
- `0x18000e03c`
- `0x18001d854`
- `0x18001e0b8`
- `0x18001e180`
- `0x18001f6f8`
- `0x18001fe78`
- `0x180024074`
- `0x180032a02`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001e732`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e732`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e371`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e371`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001e234`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001e234`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001e752`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001e752`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001e1c9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001e297`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001e1c9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001e297`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPXWizardTask::HrStartNewWizardThread(struct tag_WIZARD_TASK_DATA *lpTlsValue)
{
  struct tag_WIZARD_TASK_DATA *v1; // rdi
  unsigned int LastErrorHRESULT; // eax
  unsigned int v3; // ebx
  _DWORD *v5; // r13
  HRESULT v6; // eax
  BOOL v7; // r12d
  int v8; // esi
  PVOID *v9; // rcx
  CPXWizardTask *v10; // r14
  HRESULT v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  unsigned int v14; // ecx
  __int64 v15; // r9
  void *v16; // rax
  void *v17; // r15
  __int64 v18; // rcx
  IID *v19; // rdx
  int v20; // eax
  int v21; // eax
  unsigned int v22; // [rsp+40h] [rbp-108h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-100h] BYREF
  BOOL v24; // [rsp+50h] [rbp-F8h]
  __int64 v25; // [rsp+58h] [rbp-F0h] BYREF
  struct tag_WIZARD_TASK_DATA *v26; // [rsp+60h] [rbp-E8h]
  _DWORD *v27; // [rsp+68h] [rbp-E0h]
  struct tag_WIZARD_TASK_DATA *v28; // [rsp+70h] [rbp-D8h] BYREF
  IID rclsid; // [rsp+78h] [rbp-D0h] BYREF
  int v30; // [rsp+90h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+94h] [rbp-B4h] BYREF
  int v32; // [rsp+9Ch] [rbp-ACh]
  unsigned __int16 v33[56]; // [rsp+A0h] [rbp-A8h] BYREF

  v1 = lpTlsValue;
  v26 = lpTlsValue;
  v28 = lpTlsValue;
  v25 = 0;
  if ( !TlsSetValue(g_dwTLSThreadInstanceIndex, lpTlsValue) )
  {
    LastErrorHRESULT = GetLastErrorHRESULT();
    v3 = LastErrorHRESULT;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids,
        g_dwTLSThreadInstanceIndex,
        LastErrorHRESULT);
    return v3;
  }
  v5 = (_DWORD *)((char *)v1 + 68);
  v27 = (_DWORD *)((char *)v1 + 68);
  if ( *((_DWORD *)v1 + 17) )
  {
    v6 = CoInitializeEx(0, 6u);
    v7 = v6 != -2147417850;
    v8 = 0;
    if ( v6 != -2147417850 )
      v8 = v6;
    *((_QWORD *)v1 + 11) = &v25;
    if ( v8 < 0 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_11;
    }
  }
  else
  {
    v7 = 1;
  }
  v24 = v7;
  v10 = (CPXWizardTask *)*((_QWORD *)v1 + 9);
  ppv = 0;
  v11 = CPXWizardTask::HrEnsureRegistryInfoModuleLoaded(v10);
  v8 = v11;
  if ( v11 < 0 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v13 = 26;
      goto LABEL_44;
    }
  }
  else
  {
    rclsid = 0;
    v12 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, IID *, _QWORD))(**((_QWORD **)v10 + 12) + 88LL))(
            *((_QWORD **)v10 + 12),
            *((unsigned int *)v1 + 10),
            &rclsid,
            0);
    v8 = v12;
    if ( v12 < 0 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids,
          *((unsigned int *)v1 + 10),
          v12);
LABEL_46:
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    else
    {
      v11 = CoCreateInstance(&rclsid, 0, 0x401u, &IID_IPXWizardTypeEvent, &ppv);
      v8 = v11;
      if ( v11 >= 0 )
      {
        v22 = 0;
        v11 = (*(__int64 (__fastcall **)(CPXWizardTask *, __int64, unsigned int *))(*(_QWORD *)v10 + 64LL))(
                v10,
                (__int64)v1 + 24,
                &v22);
        v8 = v11;
        if ( v11 < 0 )
        {
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v13 = 28;
            goto LABEL_44;
          }
        }
        else
        {
          if ( (*((_BYTE *)v1 + 64) & 0x10) != 0 )
          {
            rclsid.Data1 = *((_DWORD *)v1 + 10);
            do
            {
              (*(void (__fastcall **)(LPVOID, IID *, _QWORD))(*(_QWORD *)ppv + 152LL))(ppv, &rclsid, 0);
              v14 = rclsid.Data1 | v22;
              v22 |= rclsid.Data1;
            }
            while ( rclsid.Data1 != *((_DWORD *)v1 + 10) );
            v8 = 0;
          }
          else
          {
            v14 = v22;
          }
          if ( (v14 & *((_DWORD *)v1 + 10)) != 0 )
            goto LABEL_46;
          v8 = -2147467263;
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v13 = 27;
            v15 = 2147500033LL;
LABEL_45:
            WPP_SF_d(v9[2], v13, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids, v15);
            goto LABEL_46;
          }
        }
      }
      else
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v13 = 24;
LABEL_44:
          v15 = (unsigned int)v11;
          goto LABEL_45;
        }
      }
    }
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 >= 0 )
  {
    ppv = 0;
    try
    {
      v16 = operator new(0x428u);
      *(_QWORD *)&rclsid.Data1 = v16;
      if ( v16 )
        v17 = (void *)CTask::CTask(
                        (__int64)v16,
                        *(unsigned __int16 **)v1,
                        (const struct _GUID *)((char *)v1 + 24),
                        *((_DWORD *)v1 + 10),
                        *((_QWORD *)v1 + 10),
                        *((struct CUnknown **)v1 + 11));
      else
        v17 = 0;
      ppv = v17;
    }
    catch ( ... )
    {
      v7 = v24;
      v17 = ppv;
      v1 = v26;
      v5 = v27;
    }
    if ( v17 )
    {
      v18 = *((_QWORD *)v1 + 1) - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v18 )
        v18 = *((_QWORD *)v1 + 2) - *(_QWORD *)GUID_NULL.Data4;
      v19 = 0;
      if ( v18 )
        v19 = (IID *)((char *)v1 + 8);
      v8 = CTask::RunWizard(
             (CTask *)v17,
             v19,
             *((_DWORD *)v1 + 11),
             *((unsigned __int16 *const *)v1 + 6),
             *((void *const *)v1 + 7),
             (const unsigned int *)v1 + 16);
      if ( *((_QWORD *)v1 + 10) )
      {
        memset_0(&v31, 0, 0x74u);
        v30 = *((_DWORD *)v1 + 6);
        v31 = *(_QWORD *)((char *)v1 + 28);
        v32 = *((_DWORD *)v1 + 9);
        v33[0] = 0;
        StringCchCopyNW(v33, 0x33u, L"_user_context_handle", 0x15u);
        v20 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, _QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)v1 + 10)
                                                                                                + 56LL))(
                *((_QWORD *)v1 + 10),
                (__int64)v1 + 24,
                &v30,
                0,
                0,
                0,
                0);
        if ( v20 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            (unsigned int)&WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids,
            (unsigned int)L"_user_context_handle",
            v20);
        v33[0] = 0;
        StringCchCopyNW(v33, 0x33u, L"xwizard.UserContextHandle", 0x1Au);
        v21 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, _QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)v1 + 10)
                                                                                                + 56LL))(
                *((_QWORD *)v1 + 10),
                (__int64)v1 + 24,
                &v30,
                0,
                0,
                0,
                0);
        if ( v21 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            30,
            (unsigned int)&WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids,
            (unsigned int)L"xwizard.UserContextHandle",
            v21);
      }
      CTask::~CTask((CTask *)v17);
      operator delete(v17);
    }
    else
    {
      v8 = -2147024882;
    }
    if ( *v5 && v7 )
      CoUninitialize();
    goto LABEL_14;
  }
LABEL_11:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
    WPP_SF_d(v9[2], 31, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids, (unsigned int)v8);
LABEL_14:
  TlsSetValue(g_dwTLSThreadInstanceIndex, 0);
  CPXWizardTask::FreeTaskDataElement((LPVOID *)&v28);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids,
      (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001e180  mov     [rsp+arg_8], rbx
0x18001e185  mov     [rsp+arg_10], rsi
0x18001e18a  push    rdi
0x18001e18b  push    r12
0x18001e18d  push    r13
0x18001e18f  push    r14
0x18001e191  push    r15
0x18001e193  sub     rsp, 120h
0x18001e19a  mov     rax, cs:__security_cookie
0x18001e1a1  xor     rax, rsp
0x18001e1a4  mov     [rsp+148h+var_38], rax
0x18001e1ac  mov     rdi, rcx
0x18001e1af  mov     [rsp+148h+var_E8], rcx
0x18001e1b4  mov     [rsp+148h+var_D8], rcx
0x18001e1b9  xor     ebx, ebx
0x18001e1bb  mov     [rsp+148h+var_F0], rbx
0x18001e1c0  mov     rdx, rcx; lpTlsValue
0x18001e1c3  mov     ecx, cs:?g_dwTLSThreadInstanceIndex@@3KA; dwTlsIndex
0x18001e1c9  call    cs:__imp_TlsSetValue
0x18001e1cf  test    eax, eax
0x18001e1d1  jnz     short loc_18001E21A
0x18001e1d3  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18001e1d8  mov     ebx, eax
0x18001e1da  lea     r14, WPP_GLOBAL_Control
0x18001e1e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e1e8  cmp     rcx, r14
0x18001e1eb  jz      short loc_18001E213
0x18001e1ed  test    byte ptr [rcx+1Ch], 4
0x18001e1f1  jz      short loc_18001E213
0x18001e1f3  mov     edx, 17h
0x18001e1f8  mov     dword ptr [rsp+148h+ppv], eax
0x18001e1fc  mov     r9d, cs:?g_dwTLSThreadInstanceIndex@@3KA; ulong g_dwTLSThreadInstanceIndex
0x18001e203  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001e20a  mov     rcx, [rcx+10h]
0x18001e20e  call    WPP_SF_DD
0x18001e213  mov     eax, ebx
0x18001e215  jmp     loc_18001E2D3
0x18001e21a  lea     r13, [rdi+44h]
0x18001e21e  mov     [rsp+148h+var_E0], r13
0x18001e223  cmp     [r13+0], ebx
0x18001e227  jz      loc_18001E300
0x18001e22d  mov     edx, 6; dwCoInit
0x18001e232  xor     ecx, ecx; pvReserved
0x18001e234  call    cs:__imp_CoInitializeEx
0x18001e23a  mov     r12d, ebx
0x18001e23d  mov     ecx, 80010106h
0x18001e242  cmp     eax, ecx
0x18001e244  setnz   r12b
0x18001e248  mov     esi, ebx
0x18001e24a  cmovnz  esi, eax
0x18001e24d  lea     rax, [rsp+148h+var_F0]
0x18001e252  mov     [rdi+58h], rax
0x18001e256  test    esi, esi
0x18001e258  jns     loc_18001E306
0x18001e25e  lea     r14, WPP_GLOBAL_Control
0x18001e265  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e26c  cmp     rcx, r14
0x18001e26f  jz      short loc_18001E28F
0x18001e271  test    byte ptr [rcx+1Ch], 4
0x18001e275  jz      short loc_18001E28F
0x18001e277  mov     edx, 1Fh
0x18001e27c  mov     r9d, esi
0x18001e27f  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001e286  mov     rcx, [rcx+10h]
0x18001e28a  call    WPP_SF_d
0x18001e28f  xor     edx, edx; lpTlsValue
0x18001e291  mov     ecx, cs:?g_dwTLSThreadInstanceIndex@@3KA; dwTlsIndex
0x18001e297  call    cs:__imp_TlsSetValue
0x18001e29d  lea     rcx, [rsp+148h+var_D8]; struct tag_WIZARD_TASK_DATA **
0x18001e2a2  call    ?FreeTaskDataElement@CPXWizardTask@@CAXPEAPEAUtag_WIZARD_TASK_DATA@@@Z; CPXWizardTask::FreeTaskDataElement(tag_WIZARD_TASK_DATA * *)
0x18001e2a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e2ae  cmp     rcx, r14
0x18001e2b1  jz      short loc_18001E2D1
0x18001e2b3  test    byte ptr [rcx+1Ch], 10h
0x18001e2b7  jz      short loc_18001E2D1
0x18001e2b9  mov     edx, 20h ; ' '
0x18001e2be  mov     r9d, esi
0x18001e2c1  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001e2c8  mov     rcx, [rcx+10h]
0x18001e2cc  call    WPP_SF_d
0x18001e2d1  mov     eax, esi
0x18001e2d3  mov     rcx, [rsp+148h+var_38]
0x18001e2db  xor     rcx, rsp; StackCookie
0x18001e2de  call    __security_check_cookie
0x18001e2e3  lea     r11, [rsp+148h+var_28]
0x18001e2eb  mov     rbx, [r11+38h]
0x18001e2ef  mov     rsi, [r11+40h]
0x18001e2f3  mov     rsp, r11
0x18001e2f6  pop     r15
0x18001e2f8  pop     r14
0x18001e2fa  pop     r13
0x18001e2fc  pop     r12
0x18001e2fe  pop     rdi
0x18001e2ff  retn
0x18001e300  mov     r12d, 1
0x18001e306  mov     [rsp+148h+var_F8], r12d
0x18001e30b  mov     r14, [rdi+48h]
0x18001e30f  mov     [rsp+148h+var_100], rbx
0x18001e314  mov     rcx, r14; this
0x18001e317  call    ?HrEnsureRegistryInfoModuleLoaded@CPXWizardTask@@AEAAJXZ; CPXWizardTask::HrEnsureRegistryInfoModuleLoaded(void)
0x18001e31c  mov     esi, eax
0x18001e31e  test    eax, eax
0x18001e320  js      loc_18001E4B1
0x18001e326  xorps   xmm0, xmm0
0x18001e329  movups  xmmword ptr [rsp+148h+rclsid.Data1], xmm0
0x18001e32e  mov     rcx, [r14+60h]
0x18001e332  mov     rax, [rcx]
0x18001e335  xor     r9d, r9d
0x18001e338  lea     r8, [rsp+148h+rclsid]
0x18001e33d  mov     edx, [rdi+28h]
0x18001e340  mov     rax, [rax+58h]
0x18001e344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e349  mov     esi, eax
0x18001e34b  test    eax, eax
0x18001e34d  js      loc_18001E479
0x18001e353  lea     rax, [rsp+148h+var_100]
0x18001e358  mov     [rsp+148h+ppv], rax; ppv
0x18001e35d  lea     r9, IID_IPXWizardTypeEvent; riid
0x18001e364  xor     edx, edx; pUnkOuter
0x18001e366  mov     r8d, 401h; dwClsContext
0x18001e36c  lea     rcx, [rsp+148h+rclsid]; rclsid
0x18001e371  call    cs:__imp_CoCreateInstance
0x18001e377  mov     esi, eax
0x18001e379  test    eax, eax
0x18001e37b  jns     short loc_18001E3A8
0x18001e37d  lea     r14, WPP_GLOBAL_Control
0x18001e384  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e38b  cmp     rcx, r14
0x18001e38e  jz      loc_18001E4E9
0x18001e394  test    byte ptr [rcx+1Ch], 4
0x18001e398  jz      loc_18001E4E9
0x18001e39e  mov     edx, 18h
0x18001e3a3  jmp     loc_18001E4CF
0x18001e3a8  mov     [rsp+148h+var_108], ebx
0x18001e3ac  mov     rax, [r14]
0x18001e3af  lea     rdx, [rdi+18h]
0x18001e3b3  lea     r8, [rsp+148h+var_108]
0x18001e3b8  mov     rcx, r14
0x18001e3bb  mov     rax, [rax+40h]
0x18001e3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3c4  mov     esi, eax
0x18001e3c6  test    eax, eax
0x18001e3c8  js      loc_18001E459
0x18001e3ce  test    byte ptr [rdi+40h], 10h
0x18001e3d2  jz      short loc_18001E40E
0x18001e3d4  mov     eax, [rdi+28h]
0x18001e3d7  mov     [rsp+148h+rclsid.Data1], eax
0x18001e3db  mov     rcx, [rsp+148h+var_100]
0x18001e3e0  mov     rax, [rcx]
0x18001e3e3  xor     r8d, r8d
0x18001e3e6  lea     rdx, [rsp+148h+rclsid]
0x18001e3eb  mov     rax, [rax+98h]
0x18001e3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3f7  mov     ecx, [rsp+148h+var_108]
0x18001e3fb  mov     eax, [rsp+148h+rclsid.Data1]
0x18001e3ff  or      ecx, eax
0x18001e401  mov     [rsp+148h+var_108], ecx
0x18001e405  cmp     eax, [rdi+28h]
0x18001e408  jnz     short loc_18001E3DB
0x18001e40a  mov     esi, ebx
0x18001e40c  jmp     short loc_18001E412
0x18001e40e  mov     ecx, [rsp+148h+var_108]
0x18001e412  test    [rdi+28h], ecx
0x18001e415  jnz     short loc_18001E44D
0x18001e417  mov     esi, 80004001h
0x18001e41c  lea     r14, WPP_GLOBAL_Control
0x18001e423  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e42a  cmp     rcx, r14
0x18001e42d  jz      loc_18001E4E9
0x18001e433  test    byte ptr [rcx+1Ch], 8
0x18001e437  jz      loc_18001E4E9
0x18001e43d  mov     edx, 1Bh
0x18001e442  mov     r9d, 80004001h
0x18001e448  jmp     loc_18001E4D2
0x18001e44d  lea     r14, WPP_GLOBAL_Control
0x18001e454  jmp     loc_18001E4E2
0x18001e459  lea     r14, WPP_GLOBAL_Control
0x18001e460  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e467  cmp     rcx, r14
0x18001e46a  jz      short loc_18001E4E9
0x18001e46c  test    byte ptr [rcx+1Ch], 4
0x18001e470  jz      short loc_18001E4E9
0x18001e472  mov     edx, 1Ch
0x18001e477  jmp     short loc_18001E4CF
0x18001e479  lea     r14, WPP_GLOBAL_Control
0x18001e480  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e487  cmp     rcx, r14
0x18001e48a  jz      short loc_18001E4E9
0x18001e48c  test    byte ptr [rcx+1Ch], 4
0x18001e490  jz      short loc_18001E4E9
0x18001e492  mov     edx, 19h
0x18001e497  mov     dword ptr [rsp+148h+ppv], eax
0x18001e49b  mov     r9d, [rdi+28h]
0x18001e49f  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001e4a6  mov     rcx, [rcx+10h]
0x18001e4aa  call    WPP_SF_DD
0x18001e4af  jmp     short loc_18001E4E2
0x18001e4b1  lea     r14, WPP_GLOBAL_Control
0x18001e4b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e4bf  cmp     rcx, r14
0x18001e4c2  jz      short loc_18001E4E9
0x18001e4c4  test    byte ptr [rcx+1Ch], 4
0x18001e4c8  jz      short loc_18001E4E9
0x18001e4ca  mov     edx, 1Ah
0x18001e4cf  mov     r9d, eax
0x18001e4d2  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001e4d9  mov     rcx, [rcx+10h]
0x18001e4dd  call    WPP_SF_d
0x18001e4e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e4e9  mov     rdx, [rsp+148h+var_100]
0x18001e4ee  test    rdx, rdx
0x18001e4f1  jz      short loc_18001E509
0x18001e4f3  mov     rax, [rdx]
0x18001e4f6  mov     rcx, rdx
0x18001e4f9  mov     rax, [rax+10h]
0x18001e4fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e502  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e509  test    esi, esi
0x18001e50b  js      loc_18001E26C
0x18001e511  mov     [rsp+148h+var_100], rbx
0x18001e516  mov     ecx, 428h; Size
0x18001e51b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e520  mov     qword ptr [rsp+148h+rclsid.Data1], rax
0x18001e525  test    rax, rax
0x18001e528  jz      short loc_18001E554
0x18001e52a  lea     r8, [rdi+18h]
0x18001e52e  mov     rcx, [rdi+58h]
0x18001e532  mov     [rsp+148h+var_120], rcx
0x18001e537  mov     rcx, [rdi+50h]
0x18001e53b  mov     [rsp+148h+ppv], rcx
0x18001e540  mov     r9d, [rdi+28h]
0x18001e544  mov     rdx, [rdi]
0x18001e547  mov     rcx, rax
0x18001e54a  call    ??0CTask@@QEAA@QEAUHWND__@@PEBU_GUID@@W4tagXW_WIZARD_TYPE@@PEAUIPXWizardPropertyBag@@PEAPEAUIMultiObjectElevationFactory@@@Z; CTask::CTask(HWND__ * const,_GUID const *,tagXW_WIZARD_TYPE,IPXWizardPropertyBag *,IMultiObjectElevationFactory * *)
0x18001e54f  mov     r15, rax
0x18001e552  jmp     short loc_18001E557
0x18001e554  mov     r15, rbx
0x18001e557  mov     [rsp+148h+var_100], r15
0x18001e55c  jmp     short loc_18001E57B
0x18001e55e  xor     ebx, ebx
0x18001e560  lea     r14, WPP_GLOBAL_Control
0x18001e567  mov     r12d, [rsp+148h+var_F8]
0x18001e56c  mov     r15, [rsp+148h+var_100]
0x18001e571  mov     rdi, [rsp+148h+var_E8]
0x18001e576  mov     r13, [rsp+148h+var_E0]
0x18001e57b  test    r15, r15
0x18001e57e  jz      loc_18001E73A
0x18001e584  lea     r10, [rdi+40h]
0x18001e588  mov     r11, [rdi+38h]
0x18001e58c  lea     r9, [rdi+8]
0x18001e590  mov     rcx, [r9]
0x18001e593  sub     rcx, qword ptr cs:GUID_NULL.Data1
0x18001e59a  jnz     short loc_18001E5A7
0x18001e59c  mov     rcx, [r9+8]
0x18001e5a0  sub     rcx, qword ptr cs:GUID_NULL.Data4
0x18001e5a7  mov     eax, ebx
0x18001e5a9  test    rcx, rcx
0x18001e5ac  setz    al
0x18001e5af  mov     rdx, rbx
0x18001e5b2  test    eax, eax
0x18001e5b4  cmovz   rdx, r9; rclsid
0x18001e5b8  mov     [rsp+148h+var_120], r10; unsigned int *
0x18001e5bd  mov     [rsp+148h+ppv], r11; void *
0x18001e5c2  mov     r9, [rdi+30h]; unsigned __int16 *
0x18001e5c6  mov     r8d, [rdi+2Ch]; unsigned int
0x18001e5ca  mov     rcx, r15; this
0x18001e5cd  call    ?RunWizard@CTask@@QEAAJPEBU_GUID@@KQEAGQEAXPEBK@Z; CTask::RunWizard(_GUID const *,ulong,ushort * const,void * const,ulong const *)
0x18001e5d2  mov     esi, eax
0x18001e5d4  cmp     [rdi+50h], rbx
0x18001e5d8  jz      loc_18001E727
0x18001e5de  xor     edx, edx; Val
0x18001e5e0  lea     r8d, [rdx+74h]; Size
0x18001e5e4  lea     rcx, [rsp+148h+var_B4]; void *
0x18001e5ec  call    memset_0
0x18001e5f1  mov     eax, [rdi+18h]
0x18001e5f4  mov     [rsp+148h+var_B8], eax
0x18001e5fb  movsd   xmm0, qword ptr [rdi+1Ch]
0x18001e600  movsd   [rsp+148h+var_B4], xmm0
0x18001e609  mov     eax, [rdi+24h]
0x18001e60c  mov     [rsp+148h+var_AC], eax
0x18001e613  mov     [rsp+148h+var_A8], bx
0x18001e61b  mov     r9d, 15h; unsigned __int64
0x18001e621  lea     r8, aUserContextHan_0; "_user_context_handle"
0x18001e628  lea     edx, [r9+1Eh]; unsigned __int64
0x18001e62c  lea     rcx, [rsp+148h+var_A8]; unsigned __int16 *
0x18001e634  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001e639  mov     rcx, [rdi+50h]
0x18001e63d  mov     rax, [rcx]
0x18001e640  mov     [rsp+148h+var_118], rbx
0x18001e645  mov     [rsp+148h+var_120], rbx
0x18001e64a  mov     [rsp+148h+ppv], rbx
0x18001e64f  xor     r9d, r9d
0x18001e652  lea     r8, [rsp+148h+var_B8]
0x18001e65a  lea     rdx, [rdi+18h]
0x18001e65e  mov     rax, [rax+38h]
0x18001e662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e667  test    eax, eax
0x18001e669  jns     short loc_18001E69D
0x18001e66b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e672  cmp     rcx, r14
  ... truncated ...
```

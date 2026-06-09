# CWTPage::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x18002bae0`
- end: `0x18002c03c`
- name: `?CanRunPage@CWTPage@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `1372`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x18000e150`
- `0x18002bae0`
- `0x18002c854`
- `0x18002f9c8`
- `0x1800329db`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002bb99`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002bdc9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002bb99`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002bdc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bcc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bcc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfeb`

## pseudocode

```c
__int64 __fastcall CWTPage::CanRunPage(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        int a7,
        __int64 a8,
        LPVOID ppv)
{
  LPVOID *v9; // rsi
  __int64 v10; // r15
  __int64 v12; // r14
  __int64 v14; // rax
  HRESULT v15; // ebx
  int Instance; // eax
  LPVOID *v17; // r8
  HRESULT v18; // eax
  __int64 v19; // rax
  int v20; // r14d
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // edx
  int v24; // r8d
  __int64 v25; // r8
  __int64 v26; // r8
  __int64 v28; // [rsp+50h] [rbp-10h] BYREF
  __int64 v29; // [rsp+58h] [rbp-8h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v31; // [rsp+A8h] [rbp+48h]
  __int64 v32; // [rsp+B0h] [rbp+50h]

  v32 = a3;
  v31 = a2;
  v9 = (LPVOID *)ppv;
  v10 = a8;
  pv = 0;
  v12 = a2;
  v28 = 0;
  *(_QWORD *)ppv = 0;
  v29 = 0;
  v14 = _RTDynamicCast_0(
          v10,
          0,
          &IXWizardSource `RTTI Type Descriptor',
          &IPXWizardInternalSource `RTTI Type Descriptor',
          0);
  v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 40LL))(v14, a1 + 72);
  if ( v15 < 0 )
    goto LABEL_26;
  if ( *(_QWORD *)(a1 + 144) )
    goto LABEL_14;
  if ( *(_DWORD *)(a1 + 88) )
  {
    v17 = *(LPVOID **)(a1 + 160);
  }
  else
  {
    if ( !*(_DWORD *)(a1 + 92) )
    {
      Instance = CoCreateInstance((const IID *const)(a1 + 72), 0, 0x401u, &IID_IXWizardTaskEvent, (LPVOID *)(a1 + 144));
      goto LABEL_10;
    }
    v17 = 0;
  }
  Instance = CPXWizardTaskProxy::HrCreateInstance(
               *(HWND *)(a1 + 64),
               (struct _GUID *)(a1 + 72),
               v17,
               *(struct IPXWizardTypeEvent **)(a1 + 176),
               (struct IXWizardTaskEvent **)(a1 + 144));
LABEL_10:
  v15 = Instance;
  if ( Instance >= 0 )
  {
LABEL_14:
    v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, int, __int64, int, __int64, LPVOID *))(**(_QWORD **)(a1 + 144) + 56LL))(
            *(_QWORD *)(a1 + 144),
            *(_QWORD *)(a1 + 64),
            v31,
            a4,
            a5,
            a6,
            a7,
            v10,
            v9);
    v15 = v18;
    if ( *(_DWORD *)(a1 + 96) && !v18 && *v9 )
    {
      (*(void (__fastcall **)(_QWORD, __int64, LPVOID, LPVOID *))(**(_QWORD **)(a1 + 176) + 160LL))(
        *(_QWORD *)(a1 + 176),
        3001,
        *v9,
        &pv);
      (*(void (__fastcall **)(_QWORD, __int64, LPVOID, __int64 *))(**(_QWORD **)(a1 + 176) + 160LL))(
        *(_QWORD *)(a1 + 176),
        3002,
        *v9,
        &v28);
      (*(void (__fastcall **)(_QWORD, __int64, LPVOID, __int64 *))(**(_QWORD **)(a1 + 176) + 160LL))(
        *(_QWORD *)(a1 + 176),
        3003,
        *v9,
        &v29);
    }
    CoTaskMemFree(*v9);
    *v9 = 0;
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_f8455e9d40b9396bc9f6cea9ffa6b464_Traceguids,
      (unsigned int)Instance);
LABEL_19:
  v19 = _RTDynamicCast_0(
          v10,
          0,
          &IXWizardSource `RTTI Type Descriptor',
          &IPXWizardInternalSource `RTTI Type Descriptor',
          0);
  v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 48LL))(v19);
  if ( v20 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_f8455e9d40b9396bc9f6cea9ffa6b464_Traceguids,
        (unsigned int)v20);
    if ( !v15 )
      v15 = v20;
    goto LABEL_44;
  }
  v12 = v31;
LABEL_26:
  if ( !v15 )
  {
    v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, int, __int64, int, __int64, LPVOID *))(**(_QWORD **)(a1 + 152) + 56LL))(
            *(_QWORD *)(a1 + 152),
            v12,
            v32,
            a4,
            a5,
            a6,
            a7,
            v10,
            v9);
    if ( !v15 )
    {
      ppv = 0;
      v15 = CoCreateInstance(&CLSID_CXWizard, 0, 0x401u, &IID_IXWizard, &ppv);
      if ( v15 < 0 )
        goto LABEL_43;
      (*(void (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)ppv + 216LL))(ppv, 1, *(_QWORD *)(a1 + 64));
      v21 = *(_QWORD *)(a1 + 136);
      if ( v21 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        *(_QWORD *)(a1 + 136) = 0;
        *(_DWORD *)(a1 + 128) = 0;
      }
      v15 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, __int64))(*(_QWORD *)ppv + 128LL))(
              ppv,
              a1 + 72,
              0,
              a1 + 136);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( v15 < 0 )
      {
LABEL_43:
        CoTaskMemFree(*v9);
        *v9 = 0;
      }
      else
      {
        if ( *(_DWORD *)(a1 + 96) )
        {
          CoTaskMemFree(*(LPVOID *)(a1 + 104));
          v22 = *(_QWORD *)(a1 + 176);
          *(_QWORD *)(a1 + 104) = 0;
          *(_QWORD *)(a1 + 112) = 0;
          *(_QWORD *)(a1 + 120) = 0;
          (*(void (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v22 + 160LL))(v22, 3001, 0, a1 + 104);
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, LPVOID))(**(_QWORD **)(a1 + 176) + 168LL))(
            *(_QWORD *)(a1 + 176),
            3001,
            0,
            pv);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, v24, *(_QWORD *)(a1 + 104), (__int64)pv);
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(a1 + 176) + 160LL))(
            *(_QWORD *)(a1 + 176),
            3002,
            0,
            a1 + 112);
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(a1 + 176) + 168LL))(
            *(_QWORD *)(a1 + 176),
            3002,
            0,
            v28);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v25, *(_QWORD *)(a1 + 112), v28);
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(a1 + 176) + 160LL))(
            *(_QWORD *)(a1 + 176),
            3003,
            0,
            a1 + 120);
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(a1 + 176) + 168LL))(
            *(_QWORD *)(a1 + 176),
            3003,
            0,
            v29);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v26, *(_QWORD *)(a1 + 120), v29);
        }
        v15 = 0;
      }
    }
  }
LABEL_44:
  CoTaskMemFree(pv);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_f8455e9d40b9396bc9f6cea9ffa6b464_Traceguids,
      (unsigned int)v15);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18002bae0  mov     [rsp-38h+arg_18], rbx
0x18002bae5  mov     [rsp-38h+arg_10], r8
0x18002baea  mov     [rsp-38h+arg_8], rdx
0x18002baef  push    rbp
0x18002baf0  push    rsi
0x18002baf1  push    rdi
0x18002baf2  push    r12
0x18002baf4  push    r13
0x18002baf6  push    r14
0x18002baf8  push    r15
0x18002bafa  mov     rbp, rsp
0x18002bafd  sub     rsp, 60h
0x18002bb01  mov     rsi, [rbp+arg_40]
0x18002bb08  lea     r8, ??_R0?AUIXWizardSource@@@8; IXWizardSource `RTTI Type Descriptor'
0x18002bb0f  mov     r15, [rbp+arg_38]
0x18002bb13  xor     eax, eax
0x18002bb15  mov     r13d, r9d
0x18002bb18  mov     [rbp+pv], rax
0x18002bb1c  mov     r14, rdx
0x18002bb1f  mov     [rbp+var_10], rax
0x18002bb23  mov     rdi, rcx
0x18002bb26  mov     [rsi], rax
0x18002bb29  lea     r9, ??_R0?AUIPXWizardInternalSource@@@8; IPXWizardInternalSource `RTTI Type Descriptor'
0x18002bb30  mov     [rbp+var_8], rax
0x18002bb34  xor     edx, edx
0x18002bb36  mov     dword ptr [rsp+60h+ppv], eax
0x18002bb3a  mov     rcx, r15
0x18002bb3d  call    __RTDynamicCast_0
0x18002bb42  mov     r8, rax
0x18002bb45  lea     r12, [rdi+48h]
0x18002bb49  mov     rdx, r12
0x18002bb4c  mov     rcx, [rax]
0x18002bb4f  mov     rax, [rcx+28h]
0x18002bb53  mov     rcx, r8
0x18002bb56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb5b  mov     ebx, eax
0x18002bb5d  test    eax, eax
0x18002bb5f  js      loc_18002BD4D
0x18002bb65  lea     r14, [rdi+90h]
0x18002bb6c  cmp     qword ptr [r14], 0
0x18002bb70  jnz     loc_18002BC0D
0x18002bb76  mov     eax, [rdi+58h]
0x18002bb79  test    eax, eax
0x18002bb7b  jnz     short loc_18002BBA5
0x18002bb7d  cmp     [rdi+5Ch], eax
0x18002bb80  jnz     short loc_18002BBA1
0x18002bb82  lea     r9, IID_IXWizardTaskEvent; riid
0x18002bb89  mov     [rsp+60h+ppv], r14; ppv
0x18002bb8e  xor     edx, edx; pUnkOuter
0x18002bb90  mov     r8d, 401h; dwClsContext
0x18002bb96  mov     rcx, r12; rclsid
0x18002bb99  call    cs:__imp_CoCreateInstance
0x18002bb9f  jmp     short loc_18002BBC9
0x18002bba1  test    eax, eax
0x18002bba3  jz      short loc_18002BBAE
0x18002bba5  mov     r8, [rdi+0A0h]
0x18002bbac  jmp     short loc_18002BBB1
0x18002bbae  xor     r8d, r8d; struct IMultiObjectElevationFactory **
0x18002bbb1  mov     r9, [rdi+0B0h]; struct IPXWizardTypeEvent *
0x18002bbb8  mov     rdx, r12; struct _GUID *
0x18002bbbb  mov     rcx, [rdi+40h]; HWND
0x18002bbbf  mov     [rsp+60h+ppv], r14; struct IXWizardTaskEvent **
0x18002bbc4  call    ?HrCreateInstance@CPXWizardTaskProxy@@SAJPEAUHWND__@@PEAU_GUID@@PEAPEAUIMultiObjectElevationFactory@@PEAUIPXWizardTypeEvent@@PEAPEAUIXWizardTaskEvent@@@Z; CPXWizardTaskProxy::HrCreateInstance(HWND__ *,_GUID *,IMultiObjectElevationFactory * *,IPXWizardTypeEvent *,IXWizardTaskEvent * *)
0x18002bbc9  mov     ebx, eax
0x18002bbcb  test    eax, eax
0x18002bbcd  jns     short loc_18002BC0D
0x18002bbcf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bbd6  lea     rax, WPP_GLOBAL_Control
0x18002bbdd  cmp     rcx, rax
0x18002bbe0  jz      loc_18002BCCF
0x18002bbe6  test    byte ptr [rcx+1Ch], 8
0x18002bbea  jz      loc_18002BCCF
0x18002bbf0  mov     rcx, [rcx+10h]
0x18002bbf4  lea     r8, WPP_f8455e9d40b9396bc9f6cea9ffa6b464_Traceguids
0x18002bbfb  mov     edx, 0Ah
0x18002bc00  mov     r9d, ebx
0x18002bc03  call    WPP_SF_d
0x18002bc08  jmp     loc_18002BCCF
0x18002bc0d  mov     rcx, [r14]
0x18002bc10  mov     r9d, r13d
0x18002bc13  mov     edx, [rbp+arg_30]
0x18002bc16  mov     r8, [rbp+arg_8]
0x18002bc1a  mov     [rsp+60h+var_20], rsi
0x18002bc1f  mov     rax, [rcx]
0x18002bc22  mov     [rsp+60h+var_28], r15
0x18002bc27  mov     [rsp+60h+var_30], edx
0x18002bc2b  mov     rdx, [rbp+arg_28]
0x18002bc2f  mov     rax, [rax+38h]
0x18002bc33  mov     [rsp+60h+var_38], rdx
0x18002bc38  mov     edx, [rbp+arg_20]
0x18002bc3b  mov     dword ptr [rsp+60h+ppv], edx
0x18002bc3f  mov     rdx, [rdi+40h]
0x18002bc43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc48  cmp     dword ptr [rdi+60h], 0
0x18002bc4c  mov     ebx, eax
0x18002bc4e  jz      short loc_18002BCBF
0x18002bc50  test    eax, eax
0x18002bc52  jnz     short loc_18002BCBF
0x18002bc54  mov     r8, [rsi]
0x18002bc57  test    r8, r8
0x18002bc5a  jz      short loc_18002BCBF
0x18002bc5c  mov     rcx, [rdi+0B0h]
0x18002bc63  lea     r9, [rbp+pv]
0x18002bc67  mov     edx, 0BB9h
0x18002bc6c  mov     rax, [rcx]
0x18002bc6f  mov     rax, [rax+0A0h]
0x18002bc76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc7b  mov     rcx, [rdi+0B0h]
0x18002bc82  lea     r9, [rbp+var_10]
0x18002bc86  mov     r8, [rsi]
0x18002bc89  mov     edx, 0BBAh
0x18002bc8e  mov     rax, [rcx]
0x18002bc91  mov     rax, [rax+0A0h]
0x18002bc98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc9d  mov     rcx, [rdi+0B0h]
0x18002bca4  lea     r9, [rbp+var_8]
0x18002bca8  mov     r8, [rsi]
0x18002bcab  mov     edx, 0BBBh
0x18002bcb0  mov     rax, [rcx]
0x18002bcb3  mov     rax, [rax+0A0h]
0x18002bcba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcbf  mov     rcx, [rsi]; pv
0x18002bcc2  call    cs:__imp_CoTaskMemFree
0x18002bcc8  mov     qword ptr [rsi], 0
0x18002bccf  lea     r9, ??_R0?AUIPXWizardInternalSource@@@8; IPXWizardInternalSource `RTTI Type Descriptor'
0x18002bcd6  mov     dword ptr [rsp+60h+ppv], 0
0x18002bcde  lea     r8, ??_R0?AUIXWizardSource@@@8; IXWizardSource `RTTI Type Descriptor'
0x18002bce5  xor     edx, edx
0x18002bce7  mov     rcx, r15
0x18002bcea  call    __RTDynamicCast_0
0x18002bcef  mov     rdx, rax
0x18002bcf2  mov     rcx, [rax]
0x18002bcf5  mov     rax, [rcx+30h]
0x18002bcf9  mov     rcx, rdx
0x18002bcfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd01  mov     r14d, eax
0x18002bd04  test    eax, eax
0x18002bd06  jns     short loc_18002BD49
0x18002bd08  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bd0f  lea     rax, WPP_GLOBAL_Control
0x18002bd16  cmp     rcx, rax
0x18002bd19  jz      short loc_18002BD39
0x18002bd1b  test    byte ptr [rcx+1Ch], 4
0x18002bd1f  jz      short loc_18002BD39
0x18002bd21  mov     rcx, [rcx+10h]
0x18002bd25  lea     r8, WPP_f8455e9d40b9396bc9f6cea9ffa6b464_Traceguids
0x18002bd2c  mov     edx, 0Bh
0x18002bd31  mov     r9d, r14d
0x18002bd34  call    WPP_SF_d
0x18002bd39  test    ebx, ebx
0x18002bd3b  jnz     loc_18002BFE7
0x18002bd41  mov     ebx, r14d
0x18002bd44  jmp     loc_18002BFE7
0x18002bd49  mov     r14, [rbp+arg_8]
0x18002bd4d  test    ebx, ebx
0x18002bd4f  jnz     loc_18002BFE7
0x18002bd55  mov     rcx, [rdi+98h]
0x18002bd5c  mov     r9d, r13d
0x18002bd5f  mov     edx, [rbp+arg_30]
0x18002bd62  mov     r8, [rbp+arg_10]
0x18002bd66  mov     [rsp+60h+var_20], rsi
0x18002bd6b  mov     rax, [rcx]
0x18002bd6e  mov     [rsp+60h+var_28], r15
0x18002bd73  mov     [rsp+60h+var_30], edx
0x18002bd77  mov     rdx, [rbp+arg_28]
0x18002bd7b  mov     rax, [rax+38h]
0x18002bd7f  mov     [rsp+60h+var_38], rdx
0x18002bd84  mov     edx, [rbp+arg_20]
0x18002bd87  mov     dword ptr [rsp+60h+ppv], edx
0x18002bd8b  mov     rdx, r14
0x18002bd8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd93  xor     r15d, r15d
0x18002bd96  mov     ebx, eax
0x18002bd98  test    eax, eax
0x18002bd9a  jnz     loc_18002BFE7
0x18002bda0  lea     rax, [rbp+arg_40]
0x18002bda7  mov     [rbp+arg_40], r15
0x18002bdae  lea     r9, IID_IXWizard; riid
0x18002bdb5  mov     [rsp+60h+ppv], rax; ppv
0x18002bdba  xor     edx, edx; pUnkOuter
0x18002bdbc  lea     rcx, CLSID_CXWizard; rclsid
0x18002bdc3  mov     r8d, 401h; dwClsContext
0x18002bdc9  call    cs:__imp_CoCreateInstance
0x18002bdcf  mov     ebx, eax
0x18002bdd1  test    eax, eax
0x18002bdd3  js      loc_18002BFDB
0x18002bdd9  mov     rcx, [rbp+arg_40]
0x18002bde0  lea     edx, [r15+1]
0x18002bde4  mov     r8, [rdi+40h]
0x18002bde8  mov     rax, [rcx]
0x18002bdeb  mov     rax, [rax+0D8h]
0x18002bdf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdf7  lea     rbx, [rdi+88h]
0x18002bdfe  mov     rcx, [rbx]
0x18002be01  test    rcx, rcx
0x18002be04  jz      short loc_18002BE1C
0x18002be06  mov     rax, [rcx]
0x18002be09  mov     rax, [rax+10h]
0x18002be0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be12  mov     [rbx], r15
0x18002be15  mov     [rdi+80h], r15d
0x18002be1c  mov     rcx, [rbp+arg_40]
0x18002be23  mov     r9, rbx
0x18002be26  xor     r8d, r8d
0x18002be29  mov     rdx, r12
0x18002be2c  mov     rax, [rcx]
0x18002be2f  mov     rax, [rax+80h]
0x18002be36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be3b  mov     rcx, [rbp+arg_40]
0x18002be42  mov     ebx, eax
0x18002be44  mov     rax, [rcx]
0x18002be47  mov     rax, [rax+10h]
0x18002be4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be50  test    ebx, ebx
0x18002be52  js      loc_18002BFDB
0x18002be58  cmp     [rdi+60h], r15d
0x18002be5c  jz      loc_18002BFD6
0x18002be62  lea     rbx, [rdi+68h]
0x18002be66  mov     rcx, [rbx]; pv
0x18002be69  call    cs:__imp_CoTaskMemFree
0x18002be6f  mov     rcx, [rdi+0B0h]
0x18002be76  lea     rsi, [rdi+70h]
0x18002be7a  mov     [rbx], r15
0x18002be7d  lea     r14, [rdi+78h]
0x18002be81  mov     [rsi], r15
0x18002be84  mov     r12d, 0BB9h
0x18002be8a  mov     [r14], r15
0x18002be8d  mov     r9, rbx
0x18002be90  mov     rax, [rcx]
0x18002be93  xor     r8d, r8d
0x18002be96  mov     edx, r12d
0x18002be99  mov     rax, [rax+0A0h]
0x18002bea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bea5  mov     rcx, [rdi+0B0h]
0x18002beac  xor     r8d, r8d
0x18002beaf  mov     r9, [rbp+pv]
0x18002beb3  mov     edx, r12d
0x18002beb6  mov     rax, [rcx]
0x18002beb9  mov     rax, [rax+0A8h]
0x18002bec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bec5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002becc  lea     rax, WPP_GLOBAL_Control
0x18002bed3  cmp     rcx, rax
0x18002bed6  jz      short loc_18002BEF3
0x18002bed8  test    byte ptr [rcx+1Ch], 8
0x18002bedc  jz      short loc_18002BEF3
0x18002bede  mov     rax, [rbp+pv]
0x18002bee2  mov     r9, [rbx]
0x18002bee5  mov     rcx, [rcx+10h]
0x18002bee9  mov     [rsp+60h+ppv], rax
0x18002beee  call    WPP_SF_SS
0x18002bef3  mov     rcx, [rdi+0B0h]
0x18002befa  mov     ebx, 0BBAh
0x18002beff  mov     r9, rsi
0x18002bf02  xor     r8d, r8d
0x18002bf05  mov     edx, ebx
0x18002bf07  mov     rax, [rcx]
0x18002bf0a  mov     rax, [rax+0A0h]
0x18002bf11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf16  mov     rcx, [rdi+0B0h]
0x18002bf1d  xor     r8d, r8d
0x18002bf20  mov     r9, [rbp+var_10]
0x18002bf24  mov     edx, ebx
0x18002bf26  mov     rax, [rcx]
0x18002bf29  mov     rax, [rax+0A8h]
0x18002bf30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf35  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf3c  lea     rbx, WPP_GLOBAL_Control
0x18002bf43  cmp     rcx, rbx
0x18002bf46  jz      short loc_18002BF68
0x18002bf48  test    byte ptr [rcx+1Ch], 8
0x18002bf4c  jz      short loc_18002BF68
0x18002bf4e  mov     rax, [rbp+var_10]
0x18002bf52  mov     edx, 0Dh
0x18002bf57  mov     r9, [rsi]
0x18002bf5a  mov     rcx, [rcx+10h]
0x18002bf5e  mov     [rsp+60h+ppv], rax
0x18002bf63  call    WPP_SF_qq
0x18002bf68  mov     rcx, [rdi+0B0h]
0x18002bf6f  mov     esi, 0BBBh
0x18002bf74  mov     r9, r14
0x18002bf77  xor     r8d, r8d
0x18002bf7a  mov     edx, esi
0x18002bf7c  mov     rax, [rcx]
0x18002bf7f  mov     rax, [rax+0A0h]
0x18002bf86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf8b  mov     rcx, [rdi+0B0h]
0x18002bf92  xor     r8d, r8d
0x18002bf95  mov     r9, [rbp+var_8]
0x18002bf99  mov     edx, esi
0x18002bf9b  mov     rax, [rcx]
0x18002bf9e  mov     rax, [rax+0A8h]
0x18002bfa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bfb1  cmp     rcx, rbx
0x18002bfb4  jz      short loc_18002BFD6
0x18002bfb6  test    byte ptr [rcx+1Ch], 8
0x18002bfba  jz      short loc_18002BFD6
0x18002bfbc  mov     rax, [rbp+var_8]
0x18002bfc0  mov     edx, 0Eh
  ... truncated ...
```

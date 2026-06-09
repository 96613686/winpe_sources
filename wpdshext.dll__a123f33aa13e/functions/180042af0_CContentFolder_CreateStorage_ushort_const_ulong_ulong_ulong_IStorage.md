# CContentFolder::CreateStorage(ushort const *,ulong,ulong,ulong,IStorage * *)

- ea: `0x180042af0`
- end: `0x18004309d`
- name: `?CreateStorage@CContentFolder@@UEAAJPEBGKKKPEAPEAUIStorage@@@Z`
- size: `1453`
- prototype: `int(CContentFolder *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, struct IStorage **)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000ef50`
- `0x180012408`
- `0x1800285c8`
- `0x1800287d0`
- `0x18002ff5c`
- `0x180035590`
- `0x180039c8c`
- `0x180039e80`
- `0x180042af0`
- `0x180045e64`
- `0x180047f0c`
- `0x18006b954`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18004305f`
- `ole32!CoTaskMemFree` at `0x18004306b`
- `ole32!CoTaskMemFree` at `0x18004305f`
- `ole32!CoTaskMemFree` at `0x18004306b`
- `ole32!CoCreateInstance` at `0x180042d69`
- `ole32!CoCreateInstance` at `0x180042d69`
- `SHELL32!__imp_ILFree` at `0x180042ff1`
- `SHELL32!__imp_ILFree` at `0x180043006`
- `SHELL32!__imp_ILFree` at `0x180042ff1`
- `SHELL32!__imp_ILFree` at `0x180043006`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CContentFolder::CreateStorage(
        CContentFolder *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        struct IStorage **a6)
{
  const unsigned __int16 *v7; // r12
  ITEMIDLIST *v9; // r15
  ITEMIDLIST *v10; // r13
  void *v11; // rbx
  CContentFolder *v12; // rsi
  int v13; // edi
  int v14; // eax
  PVOID *v15; // rcx
  HRESULT MyObjectID; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  unsigned int v19; // r8d
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  struct _ITEMIDLIST *v26; // [rsp+38h] [rbp-C8h] BYREF
  LPCVOID dwItem1; // [rsp+40h] [rbp-C0h] BYREF
  struct IPortableDeviceValues *ppv; // [rsp+48h] [rbp-B8h] BYREF
  struct IPortableDevice *v29; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v30; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+68h] [rbp-98h] BYREF
  struct IStorage **v33; // [rsp+70h] [rbp-90h]
  GUID v34; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v35[264]; // [rsp+90h] [rbp-70h] BYREF

  v7 = a2;
  v33 = a6;
  v9 = 0;
  v26 = 0;
  v10 = 0;
  dwItem1 = 0;
  v30 = 0;
  v11 = 0;
  pv = 0;
  v29 = 0;
  v31 = 0;
  ppv = 0;
  *a6 = 0;
  v12 = (CContentFolder *)((char *)this - 128);
  if ( !CBaseFolder::_IsValidItemName((CContentFolder *)((char *)this - 128), a2) )
  {
    v13 = -2147286788;
    goto LABEL_65;
  }
  if ( (a3 & 0xFFFFEFFC) != 0 )
  {
    v13 = -2147287039;
LABEL_65:
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_66;
  }
  if ( !(*(unsigned int (__fastcall **)(CContentFolder *, _QWORD, const GUID *))(*(_QWORD *)v12 + 56LL))(
          v12,
          *((_QWORD *)this - 8),
          &WPD_CONTENT_TYPE_FOLDER)
    || (v34 = WPD_CONTENT_TYPE_FOLDER,
        !(*(unsigned int (__fastcall **)(CContentFolder *, _QWORD, GUID *, _QWORD))(*(_QWORD *)v12 + 64LL))(
           v12,
           *((_QWORD *)this - 8),
           &v34,
           0))
    || !(*(unsigned int (__fastcall **)(CContentFolder *, _QWORD, const PROPERTYKEY *))(*(_QWORD *)v12 + 72LL))(
          v12,
          *((_QWORD *)this - 8),
          &WPD_COMMAND_OBJECT_MANAGEMENT_CREATE_OBJECT_WITH_PROPERTIES_ONLY) )
  {
    v13 = -2147287035;
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_66;
    v17 = 140;
    goto LABEL_63;
  }
  v14 = CContentFolder::_CheckForStgItemCollision(v12, v7, (a3 >> 12) & 1, (unsigned __int16 **)&pv);
  v13 = v14;
  if ( v14 < 0 )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
      v11 = pv;
      goto LABEL_66;
    }
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      141,
      (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
      (_DWORD)v7,
      v14);
    v11 = pv;
    goto LABEL_65;
  }
  v11 = pv;
  if ( pv )
    v7 = (const unsigned __int16 *)pv;
  MyObjectID = (*(__int64 (__fastcall **)(CContentFolder *, _QWORD, struct IPortableDevice **))(*(_QWORD *)v12 + 136LL))(
                 v12,
                 *((_QWORD *)this - 8),
                 &v29);
  v13 = MyObjectID;
  if ( MyObjectID < 0 )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v17 = 142;
LABEL_20:
      v18 = (unsigned int)MyObjectID;
LABEL_64:
      WPP_SF_d(v15[2], v17, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v18);
      goto LABEL_65;
    }
    goto LABEL_66;
  }
  MyObjectID = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))v29->lpVtbl->Content)(v29, &v31);
  v13 = MyObjectID;
  if ( MyObjectID >= 0 )
  {
    MyObjectID = CContentFolder::_GetMyObjectID(v12, v35, v19);
    v13 = MyObjectID;
    if ( MyObjectID < 0 )
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v17 = 144;
        goto LABEL_20;
      }
      goto LABEL_66;
    }
    MyObjectID = CoCreateInstance(
                   &CLSID_PortableDeviceValues,
                   0,
                   1u,
                   &GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143,
                   (LPVOID *)&ppv);
    v13 = MyObjectID;
    if ( MyObjectID < 0 )
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v17 = 145;
        goto LABEL_20;
      }
      goto LABEL_66;
    }
    MyObjectID = GetFolderProperties(ppv, 0, v35, v7, 0);
    v13 = MyObjectID;
    if ( MyObjectID < 0 )
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v17 = 146;
        goto LABEL_20;
      }
      goto LABEL_66;
    }
    v20 = (*(__int64 (__fastcall **)(__int64, struct IPortableDeviceValues *, unsigned __int16 **))(*(_QWORD *)v31 + 48LL))(
            v31,
            ppv,
            &v30);
    v13 = 0;
    if ( v20 != -2147023893 )
      v13 = v20;
    if ( v13 >= 0 )
    {
      if ( !v30 )
      {
        v13 = -2147418113;
        goto LABEL_65;
      }
      v21 = CContentFolder::_CreateIDList(v12, v29, v30, 0, &v26, &v32);
      v13 = v21;
      if ( v21 < 0 )
      {
        v15 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
          v9 = v26;
          goto LABEL_66;
        }
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          148,
          WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
          (unsigned int)v21);
        v9 = v26;
        goto LABEL_65;
      }
      v9 = v26;
      v22 = (*(__int64 (__fastcall **)(char *, struct _ITEMIDLIST *, _QWORD, GUID *, struct IStorage **))(*((_QWORD *)this - 14) + 40LL))(
              (char *)this - 112,
              v26,
              0,
              &GUID_0000000b_0000_0000_c000_000000000046,
              v33);
      v13 = v22;
      if ( v22 >= 0 )
      {
        v23 = SHILCombine(*((_QWORD *)this - 8), v9, &dwItem1);
        if ( v23 >= 0 )
        {
          v10 = (ITEMIDLIST *)dwItem1;
          ChangeNotify(8, 0x1000u, dwItem1, 0);
        }
        else
        {
          v15 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          {
            v10 = (ITEMIDLIST *)dwItem1;
            goto LABEL_66;
          }
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            150,
            WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
            (unsigned int)v23);
          v10 = (ITEMIDLIST *)dwItem1;
        }
        goto LABEL_65;
      }
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          149,
          (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
          (_DWORD)v30,
          v22);
        goto LABEL_65;
      }
      goto LABEL_66;
    }
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_66;
    v17 = 147;
LABEL_63:
    v18 = (unsigned int)v13;
    goto LABEL_64;
  }
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v17 = 143;
    goto LABEL_20;
  }
LABEL_66:
  if ( v9 )
  {
    ILFree(v9);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 )
  {
    ILFree(v10);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 < 0 && v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 )
    WPP_SF_d(v15[2], 151, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v13);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  CoTaskMemFree(v11);
  CoTaskMemFree(v30);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180042af0  mov     [rsp-8+arg_10], rbx
0x180042af5  push    rbp
0x180042af6  push    rsi
0x180042af7  push    rdi
0x180042af8  push    r12
0x180042afa  push    r13
0x180042afc  push    r14
0x180042afe  push    r15
0x180042b00  lea     rbp, [rsp-1B0h]
0x180042b08  sub     rsp, 2B0h
0x180042b0f  mov     rax, cs:__security_cookie
0x180042b16  xor     rax, rsp
0x180042b19  mov     [rbp+1E0h+var_40], rax
0x180042b20  mov     edi, r8d
0x180042b23  mov     r12, rdx
0x180042b26  mov     r14, rcx
0x180042b29  mov     rax, [rbp+1E0h+arg_28]
0x180042b30  mov     [rsp+2E0h+var_270], rax
0x180042b35  xor     ecx, ecx
0x180042b37  mov     r15d, ecx
0x180042b3a  mov     [rsp+2E0h+var_2A8], rcx
0x180042b3f  mov     r13d, ecx
0x180042b42  mov     [rsp+2E0h+dwItem1], rcx
0x180042b47  mov     [rsp+2E0h+var_288], rcx
0x180042b4c  mov     ebx, ecx
0x180042b4e  mov     [rsp+2E0h+pv], rcx
0x180042b53  mov     [rsp+2E0h+var_290], rcx
0x180042b58  mov     [rsp+2E0h+var_280], rcx
0x180042b5d  mov     [rsp+2E0h+var_298], rcx
0x180042b62  mov     [rax], rcx
0x180042b65  lea     rsi, [r14-80h]
0x180042b69  mov     rcx, rsi; this
0x180042b6c  call    ?_IsValidItemName@CBaseFolder@@IEAAHPEBG@Z; CBaseFolder::_IsValidItemName(ushort const *)
0x180042b71  test    eax, eax
0x180042b73  jnz     short loc_180042B86
0x180042b75  mov     edi, 800300FCh
0x180042b7a  lea     rsi, WPP_GLOBAL_Control
0x180042b81  jmp     loc_180042FE2
0x180042b86  test    edi, 0FFFFEFFCh
0x180042b8c  jz      short loc_180042B95
0x180042b8e  mov     edi, 80030001h
0x180042b93  jmp     short loc_180042B7A
0x180042b95  mov     rax, [rsi]
0x180042b98  lea     r8, WPD_CONTENT_TYPE_FOLDER
0x180042b9f  mov     rdx, [r14-40h]
0x180042ba3  mov     rcx, rsi
0x180042ba6  mov     rax, [rax+38h]
0x180042baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042baf  test    eax, eax
0x180042bb1  jz      loc_180042FAC
0x180042bb7  movups  xmm0, xmmword ptr cs:WPD_CONTENT_TYPE_FOLDER.Data1
0x180042bbe  movdqu  [rbp+1E0h+var_260], xmm0
0x180042bc3  mov     rax, [rsi]
0x180042bc6  xor     r9d, r9d
0x180042bc9  lea     r8, [rbp+1E0h+var_260]
0x180042bcd  mov     rdx, [r14-40h]
0x180042bd1  mov     rcx, rsi
0x180042bd4  mov     rax, [rax+40h]
0x180042bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042bdd  test    eax, eax
0x180042bdf  jz      loc_180042FAC
0x180042be5  mov     rax, [rsi]
0x180042be8  lea     r8, WPD_COMMAND_OBJECT_MANAGEMENT_CREATE_OBJECT_WITH_PROPERTIES_ONLY
0x180042bef  mov     rdx, [r14-40h]
0x180042bf3  mov     rcx, rsi
0x180042bf6  mov     rax, [rax+48h]
0x180042bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042bff  test    eax, eax
0x180042c01  jz      loc_180042FAC
0x180042c07  shr     edi, 0Ch
0x180042c0a  and     edi, 1
0x180042c0d  lea     r9, [rsp+2E0h+pv]; unsigned __int16 **
0x180042c12  mov     r8d, edi; int
0x180042c15  mov     rdx, r12; unsigned __int16 *
0x180042c18  mov     rcx, rsi; this
0x180042c1b  call    ?_CheckForStgItemCollision@CContentFolder@@AEAAJPEBGHPEAPEAG@Z; CContentFolder::_CheckForStgItemCollision(ushort const *,int,ushort * *)
0x180042c20  mov     edi, eax
0x180042c22  test    eax, eax
0x180042c24  jns     short loc_180042C6F
0x180042c26  mov     rcx, cs:WPP_GLOBAL_Control
0x180042c2d  lea     rsi, WPP_GLOBAL_Control
0x180042c34  cmp     rcx, rsi
0x180042c37  jz      short loc_180042C65
0x180042c39  test    byte ptr [rcx+1Ch], 2
0x180042c3d  jz      short loc_180042C65
0x180042c3f  mov     edx, 8Dh
0x180042c44  mov     dword ptr [rsp+2E0h+ppv], eax
0x180042c48  mov     r9, r12
0x180042c4b  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180042c52  mov     rcx, [rcx+10h]
0x180042c56  call    WPP_SF_Sd
0x180042c5b  mov     rbx, [rsp+2E0h+pv]
0x180042c60  jmp     loc_180042FE2
0x180042c65  mov     rbx, [rsp+2E0h+pv]
0x180042c6a  jmp     loc_180042FE9
0x180042c6f  mov     rbx, [rsp+2E0h+pv]
0x180042c74  test    rbx, rbx
0x180042c77  cmovnz  r12, rbx
0x180042c7b  mov     rax, [rsi]
0x180042c7e  lea     r8, [rsp+2E0h+var_290]
0x180042c83  mov     rdx, [r14-40h]
0x180042c87  mov     rcx, rsi
0x180042c8a  mov     rax, [rax+88h]
0x180042c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c96  mov     edi, eax
0x180042c98  test    eax, eax
0x180042c9a  jns     short loc_180042CCA
0x180042c9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180042ca3  lea     rsi, WPP_GLOBAL_Control
0x180042caa  cmp     rcx, rsi
0x180042cad  jz      loc_180042FE9
0x180042cb3  test    byte ptr [rcx+1Ch], 2
0x180042cb7  jz      loc_180042FE9
0x180042cbd  mov     edx, 8Eh
0x180042cc2  mov     r9d, eax
0x180042cc5  jmp     loc_180042FD2
0x180042cca  mov     rcx, [rsp+2E0h+var_290]
0x180042ccf  mov     rax, [rcx]
0x180042cd2  lea     rdx, [rsp+2E0h+var_280]
0x180042cd7  mov     rax, [rax+28h]
0x180042cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ce0  mov     edi, eax
0x180042ce2  test    eax, eax
0x180042ce4  jns     short loc_180042D0E
0x180042ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x180042ced  lea     rsi, WPP_GLOBAL_Control
0x180042cf4  cmp     rcx, rsi
0x180042cf7  jz      loc_180042FE9
0x180042cfd  test    byte ptr [rcx+1Ch], 2
0x180042d01  jz      loc_180042FE9
0x180042d07  mov     edx, 8Fh
0x180042d0c  jmp     short loc_180042CC2
0x180042d0e  lea     rdx, [rbp+1E0h+var_250]; unsigned __int16 *
0x180042d12  mov     rcx, rsi; this
0x180042d15  call    ?_GetMyObjectID@CContentFolder@@AEAAJPEAGI@Z; CContentFolder::_GetMyObjectID(ushort *,uint)
0x180042d1a  mov     edi, eax
0x180042d1c  test    eax, eax
0x180042d1e  jns     short loc_180042D4B
0x180042d20  mov     rcx, cs:WPP_GLOBAL_Control
0x180042d27  lea     rsi, WPP_GLOBAL_Control
0x180042d2e  cmp     rcx, rsi
0x180042d31  jz      loc_180042FE9
0x180042d37  test    byte ptr [rcx+1Ch], 2
0x180042d3b  jz      loc_180042FE9
0x180042d41  mov     edx, 90h
0x180042d46  jmp     loc_180042CC2
0x180042d4b  lea     rax, [rsp+2E0h+var_298]
0x180042d50  mov     [rsp+2E0h+ppv], rax; ppv
0x180042d55  lea     r9, _GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143; riid
0x180042d5c  xor     edx, edx; pUnkOuter
0x180042d5e  lea     r8d, [rdx+1]; dwClsContext
0x180042d62  lea     rcx, CLSID_PortableDeviceValues; rclsid
0x180042d69  call    cs:__imp_CoCreateInstance
0x180042d6f  mov     edi, eax
0x180042d71  test    eax, eax
0x180042d73  jns     short loc_180042DA0
0x180042d75  mov     rcx, cs:WPP_GLOBAL_Control
0x180042d7c  lea     rsi, WPP_GLOBAL_Control
0x180042d83  cmp     rcx, rsi
0x180042d86  jz      loc_180042FE9
0x180042d8c  test    byte ptr [rcx+1Ch], 2
0x180042d90  jz      loc_180042FE9
0x180042d96  mov     edx, 91h
0x180042d9b  jmp     loc_180042CC2
0x180042da0  mov     [rsp+2E0h+ppv], 0; unsigned __int16 *
0x180042da9  mov     r9, r12; unsigned __int16 *
0x180042dac  lea     r8, [rbp+1E0h+var_250]; unsigned __int16 *
0x180042db0  xor     edx, edx; struct _ITEMIDLIST *
0x180042db2  mov     rcx, [rsp+2E0h+var_298]; struct IPortableDeviceValues *
0x180042db7  call    ?GetFolderProperties@@YAJPEAUIPortableDeviceValues@@PEFBU_ITEMIDLIST@@PEBG22@Z; GetFolderProperties(IPortableDeviceValues *,_ITEMIDLIST const *,ushort const *,ushort const *,ushort const *)
0x180042dbc  mov     edi, eax
0x180042dbe  test    eax, eax
0x180042dc0  jns     short loc_180042DED
0x180042dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180042dc9  lea     rsi, WPP_GLOBAL_Control
0x180042dd0  cmp     rcx, rsi
0x180042dd3  jz      loc_180042FE9
0x180042dd9  test    byte ptr [rcx+1Ch], 2
0x180042ddd  jz      loc_180042FE9
0x180042de3  mov     edx, 92h
0x180042de8  jmp     loc_180042CC2
0x180042ded  mov     rcx, [rsp+2E0h+var_280]
0x180042df2  mov     rax, [rcx]
0x180042df5  lea     r8, [rsp+2E0h+var_288]
0x180042dfa  mov     rdx, [rsp+2E0h+var_298]
0x180042dff  mov     rax, [rax+30h]
0x180042e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e08  xor     edi, edi
0x180042e0a  cmp     eax, 800703EBh
0x180042e0f  cmovnz  edi, eax
0x180042e12  test    edi, edi
0x180042e14  jns     short loc_180042E41
0x180042e16  mov     rcx, cs:WPP_GLOBAL_Control
0x180042e1d  lea     rsi, WPP_GLOBAL_Control
0x180042e24  cmp     rcx, rsi
0x180042e27  jz      loc_180042FE9
0x180042e2d  test    byte ptr [rcx+1Ch], 2
0x180042e31  jz      loc_180042FE9
0x180042e37  mov     edx, 93h
0x180042e3c  jmp     loc_180042FCF
0x180042e41  mov     r8, [rsp+2E0h+var_288]; unsigned __int16 *
0x180042e46  test    r8, r8
0x180042e49  jnz     short loc_180042E55
0x180042e4b  mov     edi, 8000FFFFh
0x180042e50  jmp     loc_180042B7A
0x180042e55  lea     rax, [rsp+2E0h+var_278]
0x180042e5a  mov     [rsp+2E0h+var_2B8], rax; int *
0x180042e5f  lea     rax, [rsp+2E0h+var_2A8]
0x180042e64  mov     [rsp+2E0h+ppv], rax; struct _ITEMIDLIST **
0x180042e69  xor     r9d, r9d; int
0x180042e6c  mov     rdx, [rsp+2E0h+var_290]; struct IPortableDevice *
0x180042e71  mov     rcx, rsi; this
0x180042e74  call    ?_CreateIDList@CContentFolder@@QEAAJPEAUIPortableDevice@@PEBGHPEAPEFAU_ITEMIDLIST@@PEAH@Z; CContentFolder::_CreateIDList(IPortableDevice *,ushort const *,int,_ITEMIDLIST * *,int *)
0x180042e79  mov     edi, eax
0x180042e7b  test    eax, eax
0x180042e7d  jns     short loc_180042EC4
0x180042e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180042e86  lea     rsi, WPP_GLOBAL_Control
0x180042e8d  cmp     rcx, rsi
0x180042e90  jz      short loc_180042EBA
0x180042e92  test    byte ptr [rcx+1Ch], 2
0x180042e96  jz      short loc_180042EBA
0x180042e98  mov     edx, 94h
0x180042e9d  mov     r9d, eax
0x180042ea0  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180042ea7  mov     rcx, [rcx+10h]
0x180042eab  call    WPP_SF_d
0x180042eb0  mov     r15, [rsp+2E0h+var_2A8]
0x180042eb5  jmp     loc_180042FE2
0x180042eba  mov     r15, [rsp+2E0h+var_2A8]
0x180042ebf  jmp     loc_180042FE9
0x180042ec4  lea     rcx, [r14-70h]
0x180042ec8  mov     rax, [rcx]
0x180042ecb  mov     rdx, [rsp+2E0h+var_270]
0x180042ed0  mov     [rsp+2E0h+ppv], rdx
0x180042ed5  lea     r9, _GUID_0000000b_0000_0000_c000_000000000046
0x180042edc  xor     r8d, r8d
0x180042edf  mov     r15, [rsp+2E0h+var_2A8]
0x180042ee4  mov     rdx, r15
0x180042ee7  mov     rax, [rax+28h]
0x180042eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ef0  mov     edi, eax
0x180042ef2  test    eax, eax
0x180042ef4  jns     short loc_180042F3A
0x180042ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x180042efd  lea     rsi, WPP_GLOBAL_Control
0x180042f04  cmp     rcx, rsi
0x180042f07  jz      loc_180042FE9
0x180042f0d  test    byte ptr [rcx+1Ch], 2
0x180042f11  jz      loc_180042FE9
0x180042f17  mov     edx, 95h
0x180042f1c  mov     dword ptr [rsp+2E0h+ppv], eax
0x180042f20  mov     r9, [rsp+2E0h+var_288]
0x180042f25  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180042f2c  mov     rcx, [rcx+10h]
0x180042f30  call    WPP_SF_Sd
0x180042f35  jmp     loc_180042FE2
0x180042f3a  lea     r8, [rsp+2E0h+dwItem1]
0x180042f3f  mov     rdx, r15
0x180042f42  mov     rcx, [r14-40h]
0x180042f46  call    SHILCombine
0x180042f4b  test    eax, eax
0x180042f4d  jns     short loc_180042F8E
0x180042f4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180042f56  lea     rsi, WPP_GLOBAL_Control
0x180042f5d  cmp     rcx, rsi
0x180042f60  jz      short loc_180042F87
0x180042f62  test    byte ptr [rcx+1Ch], 2
0x180042f66  jz      short loc_180042F87
0x180042f68  mov     edx, 96h
0x180042f6d  mov     r9d, eax
0x180042f70  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180042f77  mov     rcx, [rcx+10h]
0x180042f7b  call    WPP_SF_d
0x180042f80  mov     r13, [rsp+2E0h+dwItem1]
0x180042f85  jmp     short loc_180042FE2
0x180042f87  mov     r13, [rsp+2E0h+dwItem1]
0x180042f8c  jmp     short loc_180042FE9
0x180042f8e  xor     r9d, r9d; dwItem2
0x180042f91  mov     r13, [rsp+2E0h+dwItem1]
0x180042f96  mov     r8, r13; dwItem1
0x180042f99  mov     edx, 1000h; uFlags
0x180042f9e  lea     ecx, [r9+8]; wEventId
0x180042fa2  call    ?ChangeNotify@@YAXJIPEFBU_ITEMIDLIST@@0@Z; ChangeNotify(long,uint,_ITEMIDLIST const *,_ITEMIDLIST const *)
0x180042fa7  jmp     loc_180042B7A
0x180042fac  mov     edi, 80030005h
0x180042fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180042fb8  lea     rsi, WPP_GLOBAL_Control
0x180042fbf  cmp     rcx, rsi
0x180042fc2  jz      short loc_180042FE9
0x180042fc4  test    byte ptr [rcx+1Ch], 2
0x180042fc8  jz      short loc_180042FE9
0x180042fca  mov     edx, 8Ch
0x180042fcf  mov     r9d, edi
0x180042fd2  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180042fd9  mov     rcx, [rcx+10h]
0x180042fdd  call    WPP_SF_d
0x180042fe2  mov     rcx, cs:WPP_GLOBAL_Control
0x180042fe9  test    r15, r15
0x180042fec  jz      short loc_180042FFE
  ... truncated ...
```

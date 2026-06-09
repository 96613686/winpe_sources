# CContentFolder::_RenameElement(_ITEMIDLIST const *,ushort const *)

- ea: `0x180048924`
- end: `0x180048d08`
- name: `?_RenameElement@CContentFolder@@AEAAJPEFBU_ITEMIDLIST@@PEBG@Z`
- size: `996`
- prototype: `__int64 __fastcall(CContentFolder *__hidden this, const struct _ITEMIDLIST *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800446b0`
- `0x180044b20`

## callees

- `0x180004110`
- `0x1800050d0`
- `0x1800082e0`
- `0x180016260`
- `0x1800285c8`
- `0x18002ff5c`
- `0x180035590`
- `0x180039e80`
- `0x180045e64`
- `0x180048924`
- `0x180078010`

## import_xrefs

- `SHLWAPI!PathRemoveExtensionW` at `0x180048aa1`
- `SHLWAPI!PathRemoveExtensionW` at `0x180048aa1`
- `ole32!CoCreateInstance` at `0x1800489fc`
- `ole32!CoCreateInstance` at `0x1800489fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CContentFolder::_RenameElement(
        CContentFolder *this,
        const struct _ITEMIDLIST *a2,
        const unsigned __int16 *a3)
{
  const struct CONTENTITEM *v5; // r14
  int ObjectID; // eax
  unsigned int v7; // edi
  PVOID *v8; // rcx
  int v9; // edx
  unsigned __int16 *v10; // r9
  HRESULT PortableDeviceProperties; // eax
  __int64 v12; // rdx
  unsigned int v13; // r10d
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  struct IPortableDeviceProperties *v16; // [rsp+38h] [rbp-C8h] BYREF
  struct IPortableDevice *v17; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v20[264]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v21[264]; // [rsp+470h] [rbp+370h] BYREF

  v17 = 0;
  v16 = 0;
  ppv = 0;
  v18 = 0;
  v5 = CContentFolder::_IsValid(this, a2);
  ObjectID = CContentFolder::_CheckForStgItemCollision(this, a3, 0, 0);
  v7 = ObjectID;
  if ( ObjectID < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_46;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v9 = 166;
    LODWORD(v10) = (_DWORD)a3;
LABEL_5:
    WPP_SF_Sd(
      (unsigned int)v8[2],
      v9,
      (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
      (_DWORD)v10,
      ObjectID);
LABEL_42:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_43;
  }
  PortableDeviceProperties = CoCreateInstance(
                               &CLSID_PortableDeviceValues,
                               0,
                               1u,
                               &GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143,
                               &ppv);
  v7 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_46;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v12 = 167;
    goto LABEL_41;
  }
  PortableDeviceProperties = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, const unsigned __int16 *))(*(_QWORD *)ppv + 56LL))(
                               ppv,
                               &WPD_OBJECT_ORIGINAL_FILE_NAME,
                               a3);
  v7 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_46;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v12 = 168;
    goto LABEL_41;
  }
  if ( *(_DWORD *)((char *)v5 + 66) <= 1u )
  {
    PortableDeviceProperties = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, const unsigned __int16 *))(*(_QWORD *)ppv + 56LL))(
                                 ppv,
                                 &WPD_OBJECT_NAME,
                                 a3);
    v7 = PortableDeviceProperties;
    if ( PortableDeviceProperties < 0 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_46;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_43;
      v12 = 170;
      goto LABEL_41;
    }
  }
  else
  {
    if ( (int)StringCchCopyW(pszPath, 0x104u, a3) >= 0 )
      PathRemoveExtensionW(pszPath);
    PortableDeviceProperties = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, WCHAR *))(*(_QWORD *)ppv + 56LL))(
                                 ppv,
                                 &WPD_OBJECT_NAME,
                                 pszPath);
    v7 = PortableDeviceProperties;
    if ( PortableDeviceProperties < 0 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_46;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_43;
      v12 = 169;
      goto LABEL_41;
    }
  }
  StringCchCopyW(
    v20,
    0x104u,
    (const unsigned __int16 *)v5 + *(unsigned int *)((char *)v5 + 66) + *(unsigned int *)((char *)v5 + 62) + 37);
  ObjectID = CBaseFolder::_GetObjectID(this, v20, v21, v13);
  v7 = ObjectID;
  if ( ObjectID < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_46;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v9 = 171;
    v10 = v20;
    goto LABEL_5;
  }
  PortableDeviceProperties = (*(__int64 (__fastcall **)(CContentFolder *, _QWORD, struct IPortableDevice **))(*(_QWORD *)this + 136LL))(
                               this,
                               *((_QWORD *)this + 8),
                               &v17);
  v7 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_46;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v12 = 172;
    goto LABEL_41;
  }
  PortableDeviceProperties = GetPortableDeviceProperties(v17, &v16);
  v7 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_46;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v12 = 173;
    goto LABEL_41;
  }
  PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDeviceProperties *, unsigned __int16 *, LPVOID, __int64 *))v16->lpVtbl->SetValues)(
                               v16,
                               v21,
                               ppv,
                               &v18);
  v7 = PortableDeviceProperties;
  if ( PortableDeviceProperties >= 0 )
    goto LABEL_46;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_46;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v12 = 174;
LABEL_41:
    WPP_SF_d(v8[2], v12, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)PortableDeviceProperties);
    goto LABEL_42;
  }
LABEL_43:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 )
    WPP_SF_d(v8[2], 175, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v7);
LABEL_46:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  return v7;
}

```

## disassembly

```asm
0x180048924  mov     [rsp-8+arg_18], rbx
0x180048929  push    rbp
0x18004892a  push    rsi
0x18004892b  push    rdi
0x18004892c  push    r12
0x18004892e  push    r14
0x180048930  lea     rbp, [rsp-590h]
0x180048938  sub     rsp, 690h
0x18004893f  mov     rax, cs:__security_cookie
0x180048946  xor     rax, rsp
0x180048949  mov     [rbp+5B0h+var_30], rax
0x180048950  mov     rsi, r8
0x180048953  mov     rbx, rcx
0x180048956  mov     [rsp+6B0h+var_670], 0
0x18004895f  mov     [rsp+6B0h+var_678], 0
0x180048968  mov     [rsp+6B0h+var_680], 0
0x180048971  mov     [rsp+6B0h+var_668], 0
0x18004897a  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x18004897f  mov     r14, rax
0x180048982  xor     r9d, r9d; unsigned __int16 **
0x180048985  xor     r8d, r8d; int
0x180048988  mov     rdx, rsi; unsigned __int16 *
0x18004898b  mov     rcx, rbx; this
0x18004898e  call    ?_CheckForStgItemCollision@CContentFolder@@AEAAJPEBGHPEAPEAG@Z; CContentFolder::_CheckForStgItemCollision(ushort const *,int,ushort * *)
0x180048993  mov     edi, eax
0x180048995  lea     r12, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x18004899c  test    eax, eax
0x18004899e  jns     short loc_1800489DE
0x1800489a0  lea     rbx, WPP_GLOBAL_Control
0x1800489a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800489ae  cmp     rcx, rbx
0x1800489b1  jz      loc_180048CB5
0x1800489b7  test    byte ptr [rcx+1Ch], 2
0x1800489bb  jz      loc_180048C95
0x1800489c1  mov     edx, 0A6h
0x1800489c6  mov     r9, rsi
0x1800489c9  mov     dword ptr [rsp+6B0h+ppv], eax
0x1800489cd  mov     r8, r12
0x1800489d0  mov     rcx, [rcx+10h]
0x1800489d4  call    WPP_SF_Sd
0x1800489d9  jmp     loc_180048C8E
0x1800489de  lea     rax, [rsp+6B0h+var_680]
0x1800489e3  mov     [rsp+6B0h+ppv], rax; ppv
0x1800489e8  lea     r9, _GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143; riid
0x1800489ef  xor     edx, edx; pUnkOuter
0x1800489f1  lea     r8d, [rdx+1]; dwClsContext
0x1800489f5  lea     rcx, CLSID_PortableDeviceValues; rclsid
0x1800489fc  call    cs:__imp_CoCreateInstance
0x180048a02  mov     edi, eax
0x180048a04  test    eax, eax
0x180048a06  jns     short loc_180048A33
0x180048a08  lea     rbx, WPP_GLOBAL_Control
0x180048a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180048a16  cmp     rcx, rbx
0x180048a19  jz      loc_180048CB5
0x180048a1f  test    byte ptr [rcx+1Ch], 2
0x180048a23  jz      loc_180048C95
0x180048a29  mov     edx, 0A7h
0x180048a2e  jmp     loc_180048C7F
0x180048a33  mov     rcx, [rsp+6B0h+var_680]
0x180048a38  mov     rax, [rcx]
0x180048a3b  mov     r8, rsi
0x180048a3e  lea     rdx, WPD_OBJECT_ORIGINAL_FILE_NAME
0x180048a45  mov     rax, [rax+38h]
0x180048a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a4e  mov     edi, eax
0x180048a50  test    eax, eax
0x180048a52  jns     short loc_180048A7F
0x180048a54  lea     rbx, WPP_GLOBAL_Control
0x180048a5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180048a62  cmp     rcx, rbx
0x180048a65  jz      loc_180048CB5
0x180048a6b  test    byte ptr [rcx+1Ch], 2
0x180048a6f  jz      loc_180048C95
0x180048a75  mov     edx, 0A8h
0x180048a7a  jmp     loc_180048C7F
0x180048a7f  mov     r8, rsi; unsigned __int16 *
0x180048a82  cmp     dword ptr [r14+42h], 1
0x180048a87  jbe     short loc_180048AF5
0x180048a89  mov     edx, 104h; unsigned __int64
0x180048a8e  lea     rcx, [rsp+6B0h+pszPath]; unsigned __int16 *
0x180048a93  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180048a98  test    eax, eax
0x180048a9a  js      short loc_180048AA7
0x180048a9c  lea     rcx, [rsp+6B0h+pszPath]; pszPath
0x180048aa1  call    cs:__imp_PathRemoveExtensionW
0x180048aa7  mov     rcx, [rsp+6B0h+var_680]
0x180048aac  mov     rax, [rcx]
0x180048aaf  lea     r8, [rsp+6B0h+pszPath]
0x180048ab4  lea     rdx, WPD_OBJECT_NAME
0x180048abb  mov     rax, [rax+38h]
0x180048abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ac4  mov     edi, eax
0x180048ac6  test    eax, eax
0x180048ac8  jns     short loc_180048B3E
0x180048aca  lea     rbx, WPP_GLOBAL_Control
0x180048ad1  mov     rcx, cs:WPP_GLOBAL_Control
0x180048ad8  cmp     rcx, rbx
0x180048adb  jz      loc_180048CB5
0x180048ae1  test    byte ptr [rcx+1Ch], 2
0x180048ae5  jz      loc_180048C95
0x180048aeb  mov     edx, 0A9h
0x180048af0  jmp     loc_180048C7F
0x180048af5  mov     rcx, [rsp+6B0h+var_680]
0x180048afa  mov     rax, [rcx]
0x180048afd  lea     rdx, WPD_OBJECT_NAME
0x180048b04  mov     rax, [rax+38h]
0x180048b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b0d  mov     edi, eax
0x180048b0f  test    eax, eax
0x180048b11  jns     short loc_180048B3E
0x180048b13  lea     rbx, WPP_GLOBAL_Control
0x180048b1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180048b21  cmp     rcx, rbx
0x180048b24  jz      loc_180048CB5
0x180048b2a  test    byte ptr [rcx+1Ch], 2
0x180048b2e  jz      loc_180048C95
0x180048b34  mov     edx, 0AAh
0x180048b39  jmp     loc_180048C7F
0x180048b3e  mov     ecx, [r14+3Eh]
0x180048b42  mov     eax, [r14+42h]
0x180048b46  add     rax, 25h ; '%'
0x180048b4a  add     rcx, rax
0x180048b4d  lea     r8, [r14+rcx*2]; unsigned __int16 *
0x180048b51  mov     r10d, 104h
0x180048b57  mov     edx, r10d; unsigned __int64
0x180048b5a  lea     rcx, [rbp+5B0h+var_450]; unsigned __int16 *
0x180048b61  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180048b66  mov     r9d, r10d; unsigned int
0x180048b69  lea     r8, [rbp+5B0h+var_240]; unsigned __int16 *
0x180048b70  lea     rdx, [rbp+5B0h+var_450]; unsigned __int16 *
0x180048b77  mov     rcx, rbx; this
0x180048b7a  call    ?_GetObjectID@CBaseFolder@@QEAAJPEBGPEAGI@Z; CBaseFolder::_GetObjectID(ushort const *,ushort *,uint)
0x180048b7f  mov     edi, eax
0x180048b81  test    eax, eax
0x180048b83  jns     short loc_180048BB7
0x180048b85  lea     rbx, WPP_GLOBAL_Control
0x180048b8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048b93  cmp     rcx, rbx
0x180048b96  jz      loc_180048CB5
0x180048b9c  test    byte ptr [rcx+1Ch], 2
0x180048ba0  jz      loc_180048C95
0x180048ba6  mov     edx, 0ABh
0x180048bab  lea     r9, [rbp+5B0h+var_450]
0x180048bb2  jmp     loc_1800489C9
0x180048bb7  mov     rax, [rbx]
0x180048bba  lea     r8, [rsp+6B0h+var_670]
0x180048bbf  mov     rdx, [rbx+40h]
0x180048bc3  mov     rcx, rbx
0x180048bc6  mov     rax, [rax+88h]
0x180048bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048bd2  mov     edi, eax
0x180048bd4  test    eax, eax
0x180048bd6  jns     short loc_180048C00
0x180048bd8  lea     rbx, WPP_GLOBAL_Control
0x180048bdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180048be6  cmp     rcx, rbx
0x180048be9  jz      loc_180048CB5
0x180048bef  test    byte ptr [rcx+1Ch], 2
0x180048bf3  jz      loc_180048C95
0x180048bf9  mov     edx, 0ACh
0x180048bfe  jmp     short loc_180048C7F
0x180048c00  lea     rdx, [rsp+6B0h+var_678]; struct IPortableDeviceProperties **
0x180048c05  mov     rcx, [rsp+6B0h+var_670]; struct IPortableDevice *
0x180048c0a  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x180048c0f  mov     edi, eax
0x180048c11  test    eax, eax
0x180048c13  jns     short loc_180048C39
0x180048c15  lea     rbx, WPP_GLOBAL_Control
0x180048c1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048c23  cmp     rcx, rbx
0x180048c26  jz      loc_180048CB5
0x180048c2c  test    byte ptr [rcx+1Ch], 2
0x180048c30  jz      short loc_180048C95
0x180048c32  mov     edx, 0ADh
0x180048c37  jmp     short loc_180048C7F
0x180048c39  mov     rcx, [rsp+6B0h+var_678]
0x180048c3e  mov     rax, [rcx]
0x180048c41  lea     r9, [rsp+6B0h+var_668]
0x180048c46  mov     r8, [rsp+6B0h+var_680]
0x180048c4b  lea     rdx, [rbp+5B0h+var_240]
0x180048c52  mov     rax, [rax+30h]
0x180048c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c5b  mov     edi, eax
0x180048c5d  test    eax, eax
0x180048c5f  jns     short loc_180048CB5
0x180048c61  lea     rbx, WPP_GLOBAL_Control
0x180048c68  mov     rcx, cs:WPP_GLOBAL_Control
0x180048c6f  cmp     rcx, rbx
0x180048c72  jz      short loc_180048CB5
0x180048c74  test    byte ptr [rcx+1Ch], 2
0x180048c78  jz      short loc_180048C95
0x180048c7a  mov     edx, 0AEh
0x180048c7f  mov     r9d, eax
0x180048c82  mov     r8, r12
0x180048c85  mov     rcx, [rcx+10h]
0x180048c89  call    WPP_SF_d
0x180048c8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180048c95  cmp     rcx, rbx
0x180048c98  jz      short loc_180048CB5
0x180048c9a  test    byte ptr [rcx+1Ch], 2
0x180048c9e  jz      short loc_180048CB5
0x180048ca0  mov     edx, 0AFh
0x180048ca5  mov     r9d, edi
0x180048ca8  mov     r8, r12
0x180048cab  mov     rcx, [rcx+10h]
0x180048caf  call    WPP_SF_d
0x180048cb4  nop
0x180048cb5  lea     rcx, [rsp+6B0h+var_668]
0x180048cba  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048cbf  nop
0x180048cc0  lea     rcx, [rsp+6B0h+var_680]
0x180048cc5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048cca  nop
0x180048ccb  lea     rcx, [rsp+6B0h+var_678]
0x180048cd0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048cd5  nop
0x180048cd6  lea     rcx, [rsp+6B0h+var_670]
0x180048cdb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048ce0  mov     eax, edi
0x180048ce2  mov     rcx, [rbp+5B0h+var_30]
0x180048ce9  xor     rcx, rsp; StackCookie
0x180048cec  call    __security_check_cookie
0x180048cf1  mov     rbx, [rsp+6B0h+arg_18]
0x180048cf9  add     rsp, 690h
0x180048d00  pop     r14
0x180048d02  pop     r12
0x180048d04  pop     rdi
0x180048d05  pop     rsi
0x180048d06  pop     rbp
0x180048d07  retn
```

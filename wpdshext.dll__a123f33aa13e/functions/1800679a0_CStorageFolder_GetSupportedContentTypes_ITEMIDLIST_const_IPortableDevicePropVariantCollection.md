# CStorageFolder::_GetSupportedContentTypes(_ITEMIDLIST const *,IPortableDevicePropVariantCollection * *)

- ea: `0x1800679a0`
- end: `0x180067b9a`
- name: `?_GetSupportedContentTypes@CStorageFolder@@UEAAJPEFBU_ITEMIDLIST@@PEAPEAUIPortableDevicePropVariantCollection@@@Z`
- size: `506`
- prototype: `int(CStorageFolder *__hidden this, const struct _ITEMIDLIST *, struct IPortableDevicePropVariantCollection **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009890`
- `0x1800285c8`
- `0x18002ff5c`
- `0x180035590`
- `0x1800679a0`
- `0x180078010`

## import_xrefs

- `ole32!CLSIDFromString` at `0x180067a9a`
- `ole32!CLSIDFromString` at `0x180067a9a`
- `ole32!PropVariantClear` at `0x180067b3a`
- `ole32!PropVariantClear` at `0x180067b3a`
- `ole32!CoCreateInstance` at `0x1800679fc`
- `ole32!CoCreateInstance` at `0x1800679fc`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180067aac`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180067aac`
- `SHELL32!__imp_ILFindLastID` at `0x180067a49`
- `SHELL32!__imp_ILFindLastID` at `0x180067a49`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStorageFolder::_GetSupportedContentTypes(
        CStorageFolder *this,
        const struct _ITEMIDLIST *a2,
        struct IPortableDevicePropVariantCollection **a3)
{
  HRESULT inited; // eax
  int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  const struct _ITEMIDLIST *ID; // rax
  CStorageFolder *v10; // rcx
  const struct STORAGEITEM *v11; // rax
  const struct STORAGEITEM *v12; // rdi
  const OLECHAR *v13; // r14
  unsigned int i; // esi
  struct IPortableDevicePropVariantCollection *v15; // rax
  LPVOID ppv; // [rsp+30h] [rbp-40h] BYREF
  PROPVARIANT ppropvar; // [rsp+38h] [rbp-38h] BYREF
  CLSID pclsid; // [rsp+50h] [rbp-20h] BYREF

  ppv = 0;
  memset(&ppropvar, 0, sizeof(ppropvar));
  *a3 = 0;
  inited = CoCreateInstance(
             &CLSID_PortableDevicePropVariantCollection,
             0,
             1u,
             &GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3,
             &ppv);
  v6 = inited;
  if ( inited < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 171;
LABEL_5:
      WPP_SF_d(v7[2], v8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, (unsigned int)inited);
    }
    goto LABEL_21;
  }
  ID = ILFindLastID(a2);
  v11 = CStorageFolder::_IsValid(v10, ID);
  v12 = v11;
  if ( !v11 )
  {
    v6 = -2147024809;
    goto LABEL_21;
  }
  v13 = (const OLECHAR *)((char *)v11
                        + 2 * *(unsigned int *)((char *)v11 + 38)
                        + 2 * *(unsigned int *)((char *)v11 + 42)
                        + 2 * (unsigned __int64)*(unsigned int *)((char *)v11 + 46)
                        + 54);
  for ( i = 0; ; ++i )
  {
    if ( i >= *(_DWORD *)((char *)v12 + 50) )
    {
      v15 = (struct IPortableDevicePropVariantCollection *)ppv;
      ppv = 0;
      *a3 = v15;
      goto LABEL_21;
    }
    pclsid = 0;
    if ( CLSIDFromString(v13, &pclsid) < 0 )
      goto LABEL_13;
    inited = InitPropVariantFromCLSID(&pclsid, &ppropvar);
    v6 = inited;
    if ( inited < 0 )
      break;
    inited = (*(__int64 (__fastcall **)(LPVOID, PROPVARIANT *))(*(_QWORD *)ppv + 40LL))(ppv, &ppropvar);
    v6 = inited;
    if ( inited < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v8 = 173;
        goto LABEL_5;
      }
      goto LABEL_21;
    }
LABEL_13:
    v13 += 39;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v8 = 172;
    goto LABEL_5;
  }
LABEL_21:
  PropVariantClear(&ppropvar);
  if ( v6 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      174,
      WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
      (unsigned int)v6);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800679a0  mov     [rsp-28h+arg_0], rbx
0x1800679a5  push    rbp
0x1800679a6  push    rsi
0x1800679a7  push    rdi
0x1800679a8  push    r14
0x1800679aa  push    r15
0x1800679ac  mov     rbp, rsp
0x1800679af  sub     rsp, 70h
0x1800679b3  mov     rax, cs:__security_cookie
0x1800679ba  xor     rax, rsp
0x1800679bd  mov     [rbp+var_10], rax
0x1800679c1  mov     r15, r8
0x1800679c4  mov     rdi, rdx
0x1800679c7  mov     [rbp+var_40], 0
0x1800679cf  xorps   xmm0, xmm0
0x1800679d2  xor     eax, eax
0x1800679d4  movups  xmmword ptr [rbp+ppropvar], xmm0
0x1800679d8  mov     qword ptr [rbp+ppropvar+10h], rax
0x1800679dc  mov     [r8], rax
0x1800679df  lea     rax, [rbp+var_40]
0x1800679e3  mov     [rsp+70h+ppv], rax; ppv
0x1800679e8  lea     r9, _GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3; riid
0x1800679ef  xor     edx, edx; pUnkOuter
0x1800679f1  lea     r8d, [rdx+1]; dwClsContext
0x1800679f5  lea     rcx, CLSID_PortableDevicePropVariantCollection; rclsid
0x1800679fc  call    cs:__imp_CoCreateInstance
0x180067a02  mov     ebx, eax
0x180067a04  lea     rsi, WPP_GLOBAL_Control
0x180067a0b  test    eax, eax
0x180067a0d  jns     short loc_180067A46
0x180067a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180067a16  cmp     rcx, rsi
0x180067a19  jz      loc_180067B36
0x180067a1f  test    byte ptr [rcx+1Ch], 2
0x180067a23  jz      loc_180067B36
0x180067a29  mov     edx, 0ABh
0x180067a2e  mov     r9d, eax
0x180067a31  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180067a38  mov     rcx, [rcx+10h]
0x180067a3c  call    WPP_SF_d
0x180067a41  jmp     loc_180067B36
0x180067a46  mov     rcx, rdi; pidl
0x180067a49  call    cs:__imp_ILFindLastID
0x180067a4f  mov     rdx, rax; struct _ITEMIDLIST *
0x180067a52  call    ?_IsValid@CStorageFolder@@AEAAPEFBUSTORAGEITEM@@PEFBU_ITEMIDLIST@@@Z; CStorageFolder::_IsValid(_ITEMIDLIST const *)
0x180067a57  mov     rdi, rax
0x180067a5a  test    rax, rax
0x180067a5d  jnz     short loc_180067A69
0x180067a5f  mov     ebx, 80070057h
0x180067a64  jmp     loc_180067B36
0x180067a69  mov     r14d, [rax+2Eh]
0x180067a6d  mov     eax, [rax+2Ah]
0x180067a70  add     r14, rax
0x180067a73  mov     eax, [rdi+26h]
0x180067a76  add     r14, 1Bh
0x180067a7a  add     r14, rax
0x180067a7d  lea     r14, [rdi+r14*2]
0x180067a81  xor     esi, esi
0x180067a83  cmp     esi, [rdi+32h]
0x180067a86  jnb     loc_180067B20
0x180067a8c  xorps   xmm0, xmm0
0x180067a8f  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x180067a93  lea     rdx, [rbp+pclsid]; pclsid
0x180067a97  mov     rcx, r14; lpsz
0x180067a9a  call    cs:__imp_CLSIDFromString
0x180067aa0  test    eax, eax
0x180067aa2  js      short loc_180067AD2
0x180067aa4  lea     rdx, [rbp+ppropvar]; ppropvar
0x180067aa8  lea     rcx, [rbp+pclsid]; clsid
0x180067aac  call    cs:__imp_InitPropVariantFromCLSID
0x180067ab2  mov     ebx, eax
0x180067ab4  test    eax, eax
0x180067ab6  js      short loc_180067AFD
0x180067ab8  mov     rcx, [rbp+var_40]
0x180067abc  mov     rax, [rcx]
0x180067abf  lea     rdx, [rbp+ppropvar]
0x180067ac3  mov     rax, [rax+28h]
0x180067ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067acc  mov     ebx, eax
0x180067ace  test    eax, eax
0x180067ad0  js      short loc_180067ADA
0x180067ad2  add     r14, 4Eh ; 'N'
0x180067ad6  inc     esi
0x180067ad8  jmp     short loc_180067A83
0x180067ada  mov     rcx, cs:WPP_GLOBAL_Control
0x180067ae1  lea     rsi, WPP_GLOBAL_Control
0x180067ae8  cmp     rcx, rsi
0x180067aeb  jz      short loc_180067B36
0x180067aed  test    byte ptr [rcx+1Ch], 2
0x180067af1  jz      short loc_180067B36
0x180067af3  mov     edx, 0ADh
0x180067af8  jmp     loc_180067A2E
0x180067afd  mov     rcx, cs:WPP_GLOBAL_Control
0x180067b04  lea     rsi, WPP_GLOBAL_Control
0x180067b0b  cmp     rcx, rsi
0x180067b0e  jz      short loc_180067B36
0x180067b10  test    byte ptr [rcx+1Ch], 2
0x180067b14  jz      short loc_180067B36
0x180067b16  mov     edx, 0ACh
0x180067b1b  jmp     loc_180067A2E
0x180067b20  mov     rax, [rbp+var_40]
0x180067b24  mov     [rbp+var_40], 0
0x180067b2c  mov     [r15], rax
0x180067b2f  lea     rsi, WPP_GLOBAL_Control
0x180067b36  lea     rcx, [rbp+ppropvar]; pvar
0x180067b3a  call    cs:__imp_PropVariantClear
0x180067b40  test    ebx, ebx
0x180067b42  jns     short loc_180067B6F
0x180067b44  mov     rcx, cs:WPP_GLOBAL_Control
0x180067b4b  cmp     rcx, rsi
0x180067b4e  jz      short loc_180067B6F
0x180067b50  test    byte ptr [rcx+1Ch], 2
0x180067b54  jz      short loc_180067B6F
0x180067b56  mov     edx, 0AEh
0x180067b5b  mov     r9d, ebx
0x180067b5e  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180067b65  mov     rcx, [rcx+10h]
0x180067b69  call    WPP_SF_d
0x180067b6e  nop
0x180067b6f  lea     rcx, [rbp+var_40]
0x180067b73  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180067b78  mov     eax, ebx
0x180067b7a  mov     rcx, [rbp+var_10]
0x180067b7e  xor     rcx, rsp; StackCookie
0x180067b81  call    __security_check_cookie
0x180067b86  mov     rbx, [rsp+70h+arg_0]
0x180067b8e  add     rsp, 70h
0x180067b92  pop     r15
0x180067b94  pop     r14
0x180067b96  pop     rdi
0x180067b97  pop     rsi
0x180067b98  pop     rbp
0x180067b99  retn
```

# SearchForMetaData(_ITEMIDLIST const *,IPortableDeviceValues *)

- ea: `0x180052c80`
- end: `0x1800531a5`
- name: `?SearchForMetaData@@YAJPEFBU_ITEMIDLIST@@PEAUIPortableDeviceValues@@@Z`
- size: `1317`
- prototype: `int(const struct _ITEMIDLIST *, struct IPortableDeviceValues *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012408`
- `0x180025048`

## callees

- `0x1800285c8`
- `0x18002ff5c`
- `0x180035590`
- `0x180051dc8`
- `0x180052c80`
- `0x180053490`
- `0x18007559c`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180053130`
- `ole32!CoTaskMemFree` at `0x180053145`
- `ole32!CoTaskMemFree` at `0x180053130`
- `ole32!CoTaskMemFree` at `0x180053145`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SearchForMetaData(const struct _ITEMIDLIST *a1, struct IPortableDeviceValues *a2)
{
  int PropertyStoreFromPIDL; // eax
  int v4; // ebx
  PVOID *v5; // rcx
  __int64 v6; // rdx
  void *v7; // r15
  void *v8; // r14
  int v9; // eax
  __int64 v10; // rdx
  struct IPropertyStore *v12; // [rsp+20h] [rbp-30h] BYREF
  void *v13; // [rsp+28h] [rbp-28h] BYREF
  int v14; // [rsp+30h] [rbp-20h] BYREF
  __int128 Buf2; // [rsp+38h] [rbp-18h] BYREF

  v14 = 0;
  Buf2 = 0;
  v13 = 0;
  v12 = 0;
  PropertyStoreFromPIDL = GetPropertyStoreFromPIDL(a1, &v12);
  v4 = PropertyStoreFromPIDL;
  if ( PropertyStoreFromPIDL >= 0 )
  {
    PropertyStoreFromPIDL = _AddMetaData(a2, v12, (const struct METADATA_MAPPING *)qword_180095690, 1u);
    v4 = PropertyStoreFromPIDL;
    if ( PropertyStoreFromPIDL < 0 )
    {
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_69;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_66;
      v6 = 42;
      goto LABEL_5;
    }
    if ( ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, int *))a2->lpVtbl->GetBoolValue)(
           a2,
           &WPD_OBJECT_IS_DRM_PROTECTED,
           &v14) < 0 )
      ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, _QWORD))a2->lpVtbl->SetBoolValue)(
        a2,
        &WPD_OBJECT_IS_DRM_PROTECTED,
        0);
    PropertyStoreFromPIDL = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, __int128 *))a2->lpVtbl->GetGuidValue)(
                              a2,
                              &WPD_OBJECT_CONTENT_TYPE,
                              &Buf2);
    v4 = PropertyStoreFromPIDL;
    if ( PropertyStoreFromPIDL < 0 )
    {
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_69;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_66;
      v6 = 43;
      goto LABEL_5;
    }
    if ( !memcmp_0(&WPD_CONTENT_TYPE_UNSPECIFIED, &Buf2, 0x10u)
      || !memcmp_0(&WPD_CONTENT_TYPE_GENERIC_FILE, &Buf2, 0x10u) )
    {
      goto LABEL_17;
    }
    if ( !memcmp_0(&WPD_CONTENT_TYPE_CONTACT, &Buf2, 0x10u) )
    {
      PropertyStoreFromPIDL = _AddMetaData(a2, v12, (const struct METADATA_MAPPING *)qword_180091200, 0x1Cu);
      v4 = PropertyStoreFromPIDL;
      if ( PropertyStoreFromPIDL < 0 )
      {
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_69;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_66;
        v6 = 44;
        goto LABEL_5;
      }
    }
    if ( memcmp_0(&WPD_CONTENT_TYPE_VIDEO, &Buf2, 0x10u)
      && memcmp_0(&WPD_CONTENT_TYPE_IMAGE, &Buf2, 0x10u)
      && memcmp_0(&WPD_CONTENT_TYPE_AUDIO, &Buf2, 0x10u) )
    {
LABEL_17:
      v4 = 1;
      goto LABEL_69;
    }
    if ( v4 == 1 )
      goto LABEL_64;
    PropertyStoreFromPIDL = _AddMetaData(a2, v12, (const struct METADATA_MAPPING *)qword_180091740, 0xFu);
    v4 = PropertyStoreFromPIDL;
    if ( PropertyStoreFromPIDL < 0 )
    {
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_69;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_66;
      v6 = 45;
      goto LABEL_5;
    }
    v7 = 0;
    v8 = 0;
    if ( ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, void **))a2->lpVtbl->GetStringValue)(
           a2,
           &WPD_MEDIA_TITLE,
           &v13) >= 0 )
    {
      v8 = v13;
      if ( ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, void **))a2->lpVtbl->GetStringValue)(
             a2,
             &WPD_OBJECT_ORIGINAL_FILE_NAME,
             &v13) >= 0 )
      {
        v7 = v13;
        ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, void *))a2->lpVtbl->SetStringValue)(
          a2,
          &WPD_OBJECT_NAME,
          v8);
      }
    }
    if ( !memcmp_0(&WPD_CONTENT_TYPE_AUDIO, &Buf2, 0x10u) )
    {
      v9 = _AddMetaData(a2, v12, (const struct METADATA_MAPPING *)qword_180091A10, 5u);
      v4 = v9;
      if ( v9 < 0 )
      {
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_60;
        v10 = 46;
        goto LABEL_58;
      }
      v9 = _AddMetaData(a2, v12, (const struct METADATA_MAPPING *)qword_180091B00, 7u);
      v4 = v9;
      if ( v9 < 0 )
      {
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_60;
        v10 = 47;
        goto LABEL_58;
      }
LABEL_59:
      v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_60:
      if ( v7 )
      {
        CoTaskMemFree(v7);
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !v8 )
      {
LABEL_65:
        if ( v4 >= 0 )
          goto LABEL_69;
        goto LABEL_66;
      }
      CoTaskMemFree(v8);
LABEL_64:
      v5 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_65;
    }
    if ( !memcmp_0(&WPD_CONTENT_TYPE_IMAGE, &Buf2, 0x10u) )
    {
      v9 = _AddMetaData(a2, v12, (const struct METADATA_MAPPING *)qword_180091C50, 0xFu);
      v4 = v9;
      if ( v9 >= 0 )
        goto LABEL_59;
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_60;
      v10 = 48;
    }
    else
    {
      if ( memcmp_0(&WPD_CONTENT_TYPE_VIDEO, &Buf2, 0x10u) )
        goto LABEL_59;
      v9 = _AddMetaData(a2, v12, (const struct METADATA_MAPPING *)qword_180091A10, 5u);
      v4 = v9;
      if ( v9 >= 0 )
      {
        v9 = _AddMetaData(a2, v12, (const struct METADATA_MAPPING *)qword_180091F20, 0xDu);
        v4 = v9;
        if ( v9 >= 0 )
          goto LABEL_59;
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_60;
        v10 = 50;
      }
      else
      {
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_60;
        v10 = 49;
      }
    }
LABEL_58:
    WPP_SF_d(v5[2], v10, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, (unsigned int)v9);
    goto LABEL_59;
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_69;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v6 = 41;
LABEL_5:
    WPP_SF_d(v5[2], v6, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, (unsigned int)PropertyStoreFromPIDL);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_66:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 )
    WPP_SF_d(v5[2], 51, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, (unsigned int)v4);
LABEL_69:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180052c80  mov     [rsp-28h+arg_10], rbx
0x180052c85  push    rbp
0x180052c86  push    rsi
0x180052c87  push    rdi
0x180052c88  push    r14
0x180052c8a  push    r15
0x180052c8c  mov     rbp, rsp
0x180052c8f  sub     rsp, 50h
0x180052c93  mov     rax, cs:__security_cookie
0x180052c9a  xor     rax, rsp
0x180052c9d  mov     [rbp+var_8], rax
0x180052ca1  mov     rsi, rdx
0x180052ca4  mov     [rbp+var_20], 0
0x180052cab  xorps   xmm0, xmm0
0x180052cae  movups  [rbp+Buf2], xmm0
0x180052cb2  mov     [rbp+var_28], 0
0x180052cba  mov     [rbp+var_30], 0
0x180052cc2  lea     rdx, [rbp+var_30]; struct IPropertyStore **
0x180052cc6  call    ?GetPropertyStoreFromPIDL@@YAJPEFBU_ITEMIDLIST@@PEAPEAUIPropertyStore@@@Z; GetPropertyStoreFromPIDL(_ITEMIDLIST const *,IPropertyStore * *)
0x180052ccb  mov     ebx, eax
0x180052ccd  test    eax, eax
0x180052ccf  jns     short loc_180052D16
0x180052cd1  lea     rdi, WPP_GLOBAL_Control
0x180052cd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180052cdf  cmp     rcx, rdi
0x180052ce2  jz      loc_18005317A
0x180052ce8  test    byte ptr [rcx+1Ch], 2
0x180052cec  jz      loc_180053156
0x180052cf2  mov     edx, 29h ; ')'
0x180052cf7  mov     r9d, eax
0x180052cfa  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180052d01  mov     rcx, [rcx+10h]
0x180052d05  call    WPP_SF_d
0x180052d0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180052d11  jmp     loc_180053156
0x180052d16  mov     r14d, 1
0x180052d1c  mov     r9d, r14d; unsigned int
0x180052d1f  lea     r8, qword_180095690; struct METADATA_MAPPING *
0x180052d26  mov     rdx, [rbp+var_30]; struct IPropertyStore *
0x180052d2a  mov     rcx, rsi; struct IPortableDeviceValues *
0x180052d2d  call    ?_AddMetaData@@YAJPEAUIPortableDeviceValues@@PEAUIPropertyStore@@PEBUMETADATA_MAPPING@@I@Z; _AddMetaData(IPortableDeviceValues *,IPropertyStore *,METADATA_MAPPING const *,uint)
0x180052d32  mov     ebx, eax
0x180052d34  test    eax, eax
0x180052d36  jns     short loc_180052D5F
0x180052d38  lea     rdi, WPP_GLOBAL_Control
0x180052d3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180052d46  cmp     rcx, rdi
0x180052d49  jz      loc_18005317A
0x180052d4f  test    byte ptr [rcx+1Ch], 2
0x180052d53  jz      loc_180053156
0x180052d59  lea     edx, [r14+29h]
0x180052d5d  jmp     short loc_180052CF7
0x180052d5f  mov     rax, [rsi]
0x180052d62  lea     r8, [rbp+var_20]
0x180052d66  lea     rdx, WPD_OBJECT_IS_DRM_PROTECTED
0x180052d6d  mov     rcx, rsi
0x180052d70  mov     rax, [rax+0C0h]
0x180052d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d7c  test    eax, eax
0x180052d7e  jns     short loc_180052D9C
0x180052d80  mov     rax, [rsi]
0x180052d83  xor     r8d, r8d
0x180052d86  lea     rdx, WPD_OBJECT_IS_DRM_PROTECTED
0x180052d8d  mov     rcx, rsi
0x180052d90  mov     rax, [rax+0B8h]
0x180052d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d9c  mov     rax, [rsi]
0x180052d9f  lea     r8, [rbp+Buf2]
0x180052da3  lea     rdx, WPD_OBJECT_CONTENT_TYPE
0x180052daa  mov     rcx, rsi
0x180052dad  mov     rax, [rax+0E0h]
0x180052db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052db9  mov     ebx, eax
0x180052dbb  test    eax, eax
0x180052dbd  jns     short loc_180052DEA
0x180052dbf  lea     rdi, WPP_GLOBAL_Control
0x180052dc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180052dcd  cmp     rcx, rdi
0x180052dd0  jz      loc_18005317A
0x180052dd6  test    byte ptr [rcx+1Ch], 2
0x180052dda  jz      loc_180053156
0x180052de0  mov     edx, 2Bh ; '+'
0x180052de5  jmp     loc_180052CF7
0x180052dea  mov     edi, 10h
0x180052def  mov     r8d, edi; Size
0x180052df2  lea     rdx, [rbp+Buf2]; Buf2
0x180052df6  lea     rcx, WPD_CONTENT_TYPE_UNSPECIFIED; Buf1
0x180052dfd  call    memcmp_0
0x180052e02  test    eax, eax
0x180052e04  jnz     short loc_180052E0E
0x180052e06  mov     ebx, r14d
0x180052e09  jmp     loc_18005317A
0x180052e0e  mov     r8, rdi; Size
0x180052e11  lea     rdx, [rbp+Buf2]; Buf2
0x180052e15  lea     rcx, WPD_CONTENT_TYPE_GENERIC_FILE; Buf1
0x180052e1c  call    memcmp_0
0x180052e21  test    eax, eax
0x180052e23  jz      short loc_180052E06
0x180052e25  mov     r8, rdi; Size
0x180052e28  lea     rdx, [rbp+Buf2]; Buf2
0x180052e2c  lea     rcx, WPD_CONTENT_TYPE_CONTACT; Buf1
0x180052e33  call    memcmp_0
0x180052e38  test    eax, eax
0x180052e3a  jnz     short loc_180052E84
0x180052e3c  lea     r9d, [rax+1Ch]; unsigned int
0x180052e40  lea     r8, qword_180091200; struct METADATA_MAPPING *
0x180052e47  mov     rdx, [rbp+var_30]; struct IPropertyStore *
0x180052e4b  mov     rcx, rsi; struct IPortableDeviceValues *
0x180052e4e  call    ?_AddMetaData@@YAJPEAUIPortableDeviceValues@@PEAUIPropertyStore@@PEBUMETADATA_MAPPING@@I@Z; _AddMetaData(IPortableDeviceValues *,IPropertyStore *,METADATA_MAPPING const *,uint)
0x180052e53  mov     ebx, eax
0x180052e55  test    eax, eax
0x180052e57  jns     short loc_180052E84
0x180052e59  lea     rdi, WPP_GLOBAL_Control
0x180052e60  mov     rcx, cs:WPP_GLOBAL_Control
0x180052e67  cmp     rcx, rdi
0x180052e6a  jz      loc_18005317A
0x180052e70  test    byte ptr [rcx+1Ch], 2
0x180052e74  jz      loc_180053156
0x180052e7a  mov     edx, 2Ch ; ','
0x180052e7f  jmp     loc_180052CF7
0x180052e84  mov     r8, rdi; Size
0x180052e87  lea     rdx, [rbp+Buf2]; Buf2
0x180052e8b  lea     rcx, WPD_CONTENT_TYPE_VIDEO; Buf1
0x180052e92  call    memcmp_0
0x180052e97  test    eax, eax
0x180052e99  jz      short loc_180052ECD
0x180052e9b  mov     r8, rdi; Size
0x180052e9e  lea     rdx, [rbp+Buf2]; Buf2
0x180052ea2  lea     rcx, WPD_CONTENT_TYPE_IMAGE; Buf1
0x180052ea9  call    memcmp_0
0x180052eae  test    eax, eax
0x180052eb0  jz      short loc_180052ECD
0x180052eb2  mov     r8, rdi; Size
0x180052eb5  lea     rdx, [rbp+Buf2]; Buf2
0x180052eb9  lea     rcx, WPD_CONTENT_TYPE_AUDIO; Buf1
0x180052ec0  call    memcmp_0
0x180052ec5  test    eax, eax
0x180052ec7  jnz     loc_180052E06
0x180052ecd  lea     rdi, WPP_GLOBAL_Control
0x180052ed4  cmp     ebx, r14d
0x180052ed7  jz      loc_18005314B
0x180052edd  mov     r9d, 0Fh; unsigned int
0x180052ee3  lea     r8, qword_180091740; struct METADATA_MAPPING *
0x180052eea  mov     rdx, [rbp+var_30]; struct IPropertyStore *
0x180052eee  mov     rcx, rsi; struct IPortableDeviceValues *
0x180052ef1  call    ?_AddMetaData@@YAJPEAUIPortableDeviceValues@@PEAUIPropertyStore@@PEBUMETADATA_MAPPING@@I@Z; _AddMetaData(IPortableDeviceValues *,IPropertyStore *,METADATA_MAPPING const *,uint)
0x180052ef6  mov     ebx, eax
0x180052ef8  test    eax, eax
0x180052efa  jns     short loc_180052F20
0x180052efc  mov     rcx, cs:WPP_GLOBAL_Control
0x180052f03  cmp     rcx, rdi
0x180052f06  jz      loc_18005317A
0x180052f0c  test    byte ptr [rcx+1Ch], 2
0x180052f10  jz      loc_180053156
0x180052f16  mov     edx, 2Dh ; '-'
0x180052f1b  jmp     loc_180052CF7
0x180052f20  xor     r15d, r15d
0x180052f23  xor     r14d, r14d
0x180052f26  mov     rax, [rsi]
0x180052f29  lea     r8, [rbp+var_28]
0x180052f2d  lea     rdx, WPD_MEDIA_TITLE
0x180052f34  mov     rcx, rsi
0x180052f37  mov     rax, [rax+40h]
0x180052f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f40  test    eax, eax
0x180052f42  js      short loc_180052F83
0x180052f44  mov     r14, [rbp+var_28]
0x180052f48  mov     rax, [rsi]
0x180052f4b  lea     r8, [rbp+var_28]
0x180052f4f  lea     rdx, WPD_OBJECT_ORIGINAL_FILE_NAME
0x180052f56  mov     rcx, rsi
0x180052f59  mov     rax, [rax+40h]
0x180052f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f62  test    eax, eax
0x180052f64  js      short loc_180052F83
0x180052f66  mov     r15, [rbp+var_28]
0x180052f6a  mov     rax, [rsi]
0x180052f6d  mov     r8, r14
0x180052f70  lea     rdx, WPD_OBJECT_NAME
0x180052f77  mov     rcx, rsi
0x180052f7a  mov     rax, [rax+38h]
0x180052f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f83  mov     r8d, 10h; Size
0x180052f89  lea     rdx, [rbp+Buf2]; Buf2
0x180052f8d  lea     rcx, WPD_CONTENT_TYPE_AUDIO; Buf1
0x180052f94  call    memcmp_0
0x180052f99  test    eax, eax
0x180052f9b  jnz     loc_180053029
0x180052fa1  lea     r9d, [rax+5]; unsigned int
0x180052fa5  lea     r8, qword_180091A10; struct METADATA_MAPPING *
0x180052fac  mov     rdx, [rbp+var_30]; struct IPropertyStore *
0x180052fb0  mov     rcx, rsi; struct IPortableDeviceValues *
0x180052fb3  call    ?_AddMetaData@@YAJPEAUIPortableDeviceValues@@PEAUIPropertyStore@@PEBUMETADATA_MAPPING@@I@Z; _AddMetaData(IPortableDeviceValues *,IPropertyStore *,METADATA_MAPPING const *,uint)
0x180052fb8  mov     ebx, eax
0x180052fba  test    eax, eax
0x180052fbc  jns     short loc_180052FE2
0x180052fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180052fc5  cmp     rcx, rdi
0x180052fc8  jz      loc_180053128
0x180052fce  test    byte ptr [rcx+1Ch], 2
0x180052fd2  jz      loc_180053128
0x180052fd8  mov     edx, 2Eh ; '.'
0x180052fdd  jmp     loc_18005310E
0x180052fe2  mov     r9d, 7; unsigned int
0x180052fe8  lea     r8, qword_180091B00; struct METADATA_MAPPING *
0x180052fef  mov     rdx, [rbp+var_30]; struct IPropertyStore *
0x180052ff3  mov     rcx, rsi; struct IPortableDeviceValues *
0x180052ff6  call    ?_AddMetaData@@YAJPEAUIPortableDeviceValues@@PEAUIPropertyStore@@PEBUMETADATA_MAPPING@@I@Z; _AddMetaData(IPortableDeviceValues *,IPropertyStore *,METADATA_MAPPING const *,uint)
0x180052ffb  mov     ebx, eax
0x180052ffd  test    eax, eax
0x180052fff  jns     loc_180053121
0x180053005  mov     rcx, cs:WPP_GLOBAL_Control
0x18005300c  cmp     rcx, rdi
0x18005300f  jz      loc_180053128
0x180053015  test    byte ptr [rcx+1Ch], 2
0x180053019  jz      loc_180053128
0x18005301f  mov     edx, 2Fh ; '/'
0x180053024  jmp     loc_18005310E
0x180053029  mov     r8d, 10h; Size
0x18005302f  lea     rdx, [rbp+Buf2]; Buf2
0x180053033  lea     rcx, WPD_CONTENT_TYPE_IMAGE; Buf1
0x18005303a  call    memcmp_0
0x18005303f  test    eax, eax
0x180053041  jnz     short loc_180053088
0x180053043  lea     r9d, [rax+0Fh]; unsigned int
0x180053047  lea     r8, qword_180091C50; struct METADATA_MAPPING *
0x18005304e  mov     rdx, [rbp+var_30]; struct IPropertyStore *
0x180053052  mov     rcx, rsi; struct IPortableDeviceValues *
0x180053055  call    ?_AddMetaData@@YAJPEAUIPortableDeviceValues@@PEAUIPropertyStore@@PEBUMETADATA_MAPPING@@I@Z; _AddMetaData(IPortableDeviceValues *,IPropertyStore *,METADATA_MAPPING const *,uint)
0x18005305a  mov     ebx, eax
0x18005305c  test    eax, eax
0x18005305e  jns     loc_180053121
0x180053064  mov     rcx, cs:WPP_GLOBAL_Control
0x18005306b  cmp     rcx, rdi
0x18005306e  jz      loc_180053128
0x180053074  test    byte ptr [rcx+1Ch], 2
0x180053078  jz      loc_180053128
0x18005307e  mov     edx, 30h ; '0'
0x180053083  jmp     loc_18005310E
0x180053088  mov     r8d, 10h; Size
0x18005308e  lea     rdx, [rbp+Buf2]; Buf2
0x180053092  lea     rcx, WPD_CONTENT_TYPE_VIDEO; Buf1
0x180053099  call    memcmp_0
0x18005309e  test    eax, eax
0x1800530a0  jnz     short loc_180053121
0x1800530a2  lea     r9d, [rax+5]; unsigned int
0x1800530a6  lea     r8, qword_180091A10; struct METADATA_MAPPING *
0x1800530ad  mov     rdx, [rbp+var_30]; struct IPropertyStore *
0x1800530b1  mov     rcx, rsi; struct IPortableDeviceValues *
0x1800530b4  call    ?_AddMetaData@@YAJPEAUIPortableDeviceValues@@PEAUIPropertyStore@@PEBUMETADATA_MAPPING@@I@Z; _AddMetaData(IPortableDeviceValues *,IPropertyStore *,METADATA_MAPPING const *,uint)
0x1800530b9  mov     ebx, eax
0x1800530bb  test    eax, eax
0x1800530bd  jns     short loc_1800530D8
0x1800530bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800530c6  cmp     rcx, rdi
0x1800530c9  jz      short loc_180053128
0x1800530cb  test    byte ptr [rcx+1Ch], 2
0x1800530cf  jz      short loc_180053128
0x1800530d1  mov     edx, 31h ; '1'
0x1800530d6  jmp     short loc_18005310E
0x1800530d8  mov     r9d, 0Dh; unsigned int
0x1800530de  lea     r8, qword_180091F20; struct METADATA_MAPPING *
0x1800530e5  mov     rdx, [rbp+var_30]; struct IPropertyStore *
0x1800530e9  mov     rcx, rsi; struct IPortableDeviceValues *
0x1800530ec  call    ?_AddMetaData@@YAJPEAUIPortableDeviceValues@@PEAUIPropertyStore@@PEBUMETADATA_MAPPING@@I@Z; _AddMetaData(IPortableDeviceValues *,IPropertyStore *,METADATA_MAPPING const *,uint)
0x1800530f1  mov     ebx, eax
0x1800530f3  test    eax, eax
0x1800530f5  jns     short loc_180053121
0x1800530f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800530fe  cmp     rcx, rdi
0x180053101  jz      short loc_180053128
0x180053103  test    byte ptr [rcx+1Ch], 2
0x180053107  jz      short loc_180053128
0x180053109  mov     edx, 32h ; '2'
0x18005310e  mov     r9d, eax
0x180053111  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180053118  mov     rcx, [rcx+10h]
0x18005311c  call    WPP_SF_d
0x180053121  mov     rcx, cs:WPP_GLOBAL_Control
0x180053128  test    r15, r15
0x18005312b  jz      short loc_18005313D
0x18005312d  mov     rcx, r15; pv
0x180053130  call    cs:__imp_CoTaskMemFree
0x180053136  mov     rcx, cs:WPP_GLOBAL_Control
0x18005313d  test    r14, r14
0x180053140  jz      short loc_180053152
0x180053142  mov     rcx, r14; pv
0x180053145  call    cs:__imp_CoTaskMemFree
0x18005314b  mov     rcx, cs:WPP_GLOBAL_Control
0x180053152  test    ebx, ebx
0x180053154  jns     short loc_18005317A
0x180053156  cmp     rcx, rdi
0x180053159  jz      short loc_18005317A
0x18005315b  test    byte ptr [rcx+1Ch], 2
0x18005315f  jz      short loc_18005317A
0x180053161  mov     edx, 33h ; '3'
0x180053166  mov     r9d, ebx
0x180053169  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180053170  mov     rcx, [rcx+10h]
0x180053174  call    WPP_SF_d
  ... truncated ...
```

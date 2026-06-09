# FilterContentItem(_ITEMIDLIST *,IPortableDevice *,CContentEnum *,CDPA<_ITEMIDLIST> *)

- ea: `0x18000fbd8`
- end: `0x18000ff35`
- name: `?FilterContentItem@@YAHPEFAU_ITEMIDLIST@@PEAUIPortableDevice@@PEAVCContentEnum@@PEAV?$CDPA@$$CFAU_ITEMIDLIST@@@@@Z`
- size: `861`
- prototype: `__int64 __fastcall(struct _ITEMIDLIST *, struct IPortableDevice *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e840`

## callees

- `0x180004110`
- `0x1800050d0`
- `0x1800082e0`
- `0x18000bde4`
- `0x18000e760`
- `0x18000fbd8`
- `0x180016260`
- `0x18001d860`
- `0x1800285c8`
- `0x180035590`
- `0x180041ab0`
- `0x180078010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000fd57`
- `ole32!CoCreateInstance` at `0x18000fd57`
- `SHELL32!__imp_ILFree` at `0x18000fe4a`
- `SHELL32!__imp_ILFree` at `0x18000fe4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall FilterContentItem(struct _ITEMIDLIST *a1, struct IPortableDevice *a2, __int64 a3, _QWORD *a4)
{
  struct IPortableDeviceProperties *v8; // rbx
  CBaseFolder *v9; // r13
  const struct CONTENTITEM *v10; // rax
  const struct CONTENTITEM *v11; // rdi
  unsigned int v13; // r10d
  __int64 v14; // rdx
  ITEMIDLIST *v15; // rdi
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  struct IPortableDeviceProperties *v20; // [rsp+50h] [rbp-B0h] BYREF
  LPITEMIDLIST pidl; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v22[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v23[264]; // [rsp+270h] [rbp+170h] BYREF

  v16 = 0;
  v8 = 0;
  v20 = 0;
  ppv = 0;
  v19 = 0;
  v18 = 0;
  v9 = *(CBaseFolder **)(a3 + 64);
  v10 = CContentFolder::_IsValid((CContentFolder *)a1, a1);
  v11 = v10;
  if ( v10 )
  {
    if ( (*(_DWORD *)((_BYTE *)v10 + 10) & 0x400) != 0 && !*(_DWORD *)(a3 + 32) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_dfacde6f4b3f3ae519c2a03af24374aa_Traceguids);
      return 1;
    }
    if ( (*(_DWORD *)((_BYTE *)v10 + 14) & 0x300) != 0 )
    {
      if ( (int)GetPortableDeviceProperties(a2, &v20) < 0
        || (StringCchCopyW(
              v22,
              0x104u,
              (const unsigned __int16 *)v11
            + *(unsigned int *)((char *)v11 + 62)
            + *(unsigned int *)((char *)v11 + 66)
            + 37),
            (int)CBaseFolder::_GetObjectID(v9, v22, v23, v13) < 0)
        || CoCreateInstance(&CLSID_PortableDeviceKeyCollection, 0, 1u, &GUID_dada2357_e0ad_492e_98db_dd61c53ba353, &ppv) < 0 )
      {
        v8 = v20;
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_REFERENCES);
        v8 = v20;
        if ( ((int (__fastcall *)(struct IPortableDeviceProperties *, unsigned __int16 *, LPVOID, __int64 *))v20->lpVtbl->GetValues)(
               v20,
               v23,
               ppv,
               &v19) >= 0 )
        {
          v16 = 0;
          if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, __int64 *))(*(_QWORD *)v19 + 272LL))(
                 v19,
                 &WPD_OBJECT_REFERENCES,
                 &v18) >= 0 )
            (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 24LL))(v18, &v16);
          if ( !v16 )
          {
            if ( *a4 || (CDPA_Base<PROPERTY_ITEM>::Create(a4), *a4) )
            {
              pidl = 0;
              if ( (int)SHILCloneFirst(a1, &pidl) >= 0 )
              {
                v15 = pidl;
                if ( (unsigned int)IsolationAwareDPA_InsertPtr(*a4, v14, pidl) != -1 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_dfacde6f4b3f3ae519c2a03af24374aa_Traceguids);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
                  return 1;
                }
                if ( v15 )
                  ILFree(v15);
              }
            }
          }
        }
      }
    }
  }
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v8 )
    ((void (__fastcall *)(struct IPortableDeviceProperties *))v8->lpVtbl->Release)(v8);
  return 0;
}

```

## disassembly

```asm
0x18000fbd8  push    rbp
0x18000fbda  push    rbx
0x18000fbdb  push    rsi
0x18000fbdc  push    rdi
0x18000fbdd  push    r12
0x18000fbdf  push    r13
0x18000fbe1  push    r14
0x18000fbe3  push    r15
0x18000fbe5  lea     rbp, [rsp-398h]
0x18000fbed  sub     rsp, 498h
0x18000fbf4  mov     rax, cs:__security_cookie
0x18000fbfb  xor     rax, rsp
0x18000fbfe  mov     [rbp+3D0h+var_50], rax
0x18000fc05  mov     rsi, r9
0x18000fc08  mov     r14, r8
0x18000fc0b  mov     r15, rdx
0x18000fc0e  mov     r12, rcx
0x18000fc11  xor     eax, eax
0x18000fc13  mov     [rsp+4D0h+var_4A0], eax
0x18000fc17  mov     ebx, eax
0x18000fc19  mov     [rsp+4D0h+var_480], rax
0x18000fc1e  mov     [rsp+4D0h+var_498], rax
0x18000fc23  mov     [rsp+4D0h+var_488], rax
0x18000fc28  mov     [rsp+4D0h+var_490], rax
0x18000fc2d  mov     r13, [r8+40h]
0x18000fc31  mov     rdx, rcx; struct _ITEMIDLIST *
0x18000fc34  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x18000fc39  mov     rdi, rax
0x18000fc3c  test    rax, rax
0x18000fc3f  jz      loc_18000FEB6
0x18000fc45  test    dword ptr [rax+0Ah], 400h
0x18000fc4c  jz      loc_18000FCD4
0x18000fc52  cmp     [r14+20h], ebx
0x18000fc56  jnz     short loc_18000FCD4
0x18000fc58  lea     rax, WPP_GLOBAL_Control
0x18000fc5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc66  cmp     rcx, rax
0x18000fc69  jz      short loc_18000FC85
0x18000fc6b  test    byte ptr [rcx+1Ch], 40h
0x18000fc6f  jz      short loc_18000FC85
0x18000fc71  lea     edx, [rbx+14h]
0x18000fc74  lea     r8, WPP_dfacde6f4b3f3ae519c2a03af24374aa_Traceguids
0x18000fc7b  mov     rcx, [rcx+10h]
0x18000fc7f  call    WPP_SF_
0x18000fc84  nop
0x18000fc85  mov     rcx, [rsp+4D0h+var_490]
0x18000fc8a  test    rcx, rcx
0x18000fc8d  jz      short loc_18000FC9C
0x18000fc8f  mov     rax, [rcx]
0x18000fc92  mov     rax, [rax+10h]
0x18000fc96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc9b  nop
0x18000fc9c  mov     rcx, [rsp+4D0h+var_488]
0x18000fca1  test    rcx, rcx
0x18000fca4  jz      short loc_18000FCB3
0x18000fca6  mov     rax, [rcx]
0x18000fca9  mov     rax, [rax+10h]
0x18000fcad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcb2  nop
0x18000fcb3  mov     rcx, [rsp+4D0h+var_498]
0x18000fcb8  test    rcx, rcx
0x18000fcbb  jz      short loc_18000FCCA
0x18000fcbd  mov     rax, [rcx]
0x18000fcc0  mov     rax, [rax+10h]
0x18000fcc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcc9  nop
0x18000fcca  mov     eax, 1
0x18000fccf  jmp     loc_18000FF12
0x18000fcd4  test    dword ptr [rax+0Eh], 300h
0x18000fcdb  jz      loc_18000FEB6
0x18000fce1  lea     rdx, [rsp+4D0h+var_480]; struct IPortableDeviceProperties **
0x18000fce6  mov     rcx, r15; struct IPortableDevice *
0x18000fce9  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x18000fcee  test    eax, eax
0x18000fcf0  js      loc_18000FEB1
0x18000fcf6  mov     ecx, [rdi+42h]
0x18000fcf9  mov     eax, [rdi+3Eh]
0x18000fcfc  add     rax, 25h ; '%'
0x18000fd00  add     rcx, rax
0x18000fd03  lea     r8, [rdi+rcx*2]; unsigned __int16 *
0x18000fd07  mov     r10d, 104h
0x18000fd0d  mov     edx, r10d; unsigned __int64
0x18000fd10  lea     rcx, [rsp+4D0h+var_470]; unsigned __int16 *
0x18000fd15  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fd1a  mov     r9d, r10d; unsigned int
0x18000fd1d  lea     r8, [rbp+3D0h+var_260]; unsigned __int16 *
0x18000fd24  lea     rdx, [rsp+4D0h+var_470]; unsigned __int16 *
0x18000fd29  mov     rcx, r13; this
0x18000fd2c  call    ?_GetObjectID@CBaseFolder@@QEAAJPEBGPEAGI@Z; CBaseFolder::_GetObjectID(ushort const *,ushort *,uint)
0x18000fd31  test    eax, eax
0x18000fd33  js      loc_18000FEB1
0x18000fd39  lea     rax, [rsp+4D0h+var_498]
0x18000fd3e  mov     [rsp+4D0h+ppv], rax; ppv
0x18000fd43  lea     r9, _GUID_dada2357_e0ad_492e_98db_dd61c53ba353; riid
0x18000fd4a  xor     edx, edx; pUnkOuter
0x18000fd4c  lea     r8d, [rdx+1]; dwClsContext
0x18000fd50  lea     rcx, CLSID_PortableDeviceKeyCollection; rclsid
0x18000fd57  call    cs:__imp_CoCreateInstance
0x18000fd5d  test    eax, eax
0x18000fd5f  js      loc_18000FEB1
0x18000fd65  mov     rcx, [rsp+4D0h+var_498]
0x18000fd6a  mov     rax, [rcx]
0x18000fd6d  lea     rdx, WPD_OBJECT_REFERENCES
0x18000fd74  mov     rax, [rax+28h]
0x18000fd78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd7d  mov     rbx, [rsp+4D0h+var_480]
0x18000fd82  mov     rax, [rbx]
0x18000fd85  lea     r9, [rsp+4D0h+var_488]
0x18000fd8a  mov     r8, [rsp+4D0h+var_498]
0x18000fd8f  lea     rdx, [rbp+3D0h+var_260]
0x18000fd96  mov     rcx, rbx
0x18000fd99  mov     rax, [rax+28h]
0x18000fd9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fda2  test    eax, eax
0x18000fda4  js      loc_18000FEB6
0x18000fdaa  mov     [rsp+4D0h+var_4A0], 0
0x18000fdb2  mov     rcx, [rsp+4D0h+var_488]
0x18000fdb7  mov     rax, [rcx]
0x18000fdba  lea     r8, [rsp+4D0h+var_490]
0x18000fdbf  lea     rdx, WPD_OBJECT_REFERENCES
0x18000fdc6  mov     rax, [rax+110h]
0x18000fdcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdd2  test    eax, eax
0x18000fdd4  js      short loc_18000FDEC
0x18000fdd6  mov     rcx, [rsp+4D0h+var_490]
0x18000fddb  mov     rax, [rcx]
0x18000fdde  lea     rdx, [rsp+4D0h+var_4A0]
0x18000fde3  mov     rax, [rax+18h]
0x18000fde7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdec  cmp     [rsp+4D0h+var_4A0], 0
0x18000fdf1  jnz     loc_18000FEB6
0x18000fdf7  cmp     qword ptr [rsi], 0
0x18000fdfb  jnz     short loc_18000FE0F
0x18000fdfd  mov     rcx, rsi
0x18000fe00  call    ?Create@?$CDPA_Base@UPROPERTY_ITEM@@@@QEAAHH@Z; CDPA_Base<PROPERTY_ITEM>::Create(int)
0x18000fe05  cmp     qword ptr [rsi], 0
0x18000fe09  jz      loc_18000FEB6
0x18000fe0f  mov     [rsp+4D0h+pidl], 0
0x18000fe18  lea     rdx, [rsp+4D0h+pidl]
0x18000fe1d  mov     rcx, r12
0x18000fe20  call    SHILCloneFirst
0x18000fe25  test    eax, eax
0x18000fe27  js      loc_18000FEB6
0x18000fe2d  mov     rdi, [rsp+4D0h+pidl]
0x18000fe32  mov     r8, rdi
0x18000fe35  mov     rcx, [rsi]
0x18000fe38  call    IsolationAwareDPA_InsertPtr
0x18000fe3d  cmp     eax, 0FFFFFFFFh
0x18000fe40  jnz     short loc_18000FE52
0x18000fe42  test    rdi, rdi
0x18000fe45  jz      short loc_18000FEB6
0x18000fe47  mov     rcx, rdi; pidl
0x18000fe4a  call    cs:__imp_ILFree
0x18000fe50  jmp     short loc_18000FEB6
0x18000fe52  lea     rax, WPP_GLOBAL_Control
0x18000fe59  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe60  cmp     rcx, rax
0x18000fe63  jz      short loc_18000FE81
0x18000fe65  test    byte ptr [rcx+1Ch], 40h
0x18000fe69  jz      short loc_18000FE81
0x18000fe6b  mov     edx, 15h
0x18000fe70  lea     r8, WPP_dfacde6f4b3f3ae519c2a03af24374aa_Traceguids
0x18000fe77  mov     rcx, [rcx+10h]
0x18000fe7b  call    WPP_SF_
0x18000fe80  nop
0x18000fe81  lea     rcx, [rsp+4D0h+var_490]
0x18000fe86  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000fe8b  nop
0x18000fe8c  lea     rcx, [rsp+4D0h+var_488]
0x18000fe91  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000fe96  nop
0x18000fe97  lea     rcx, [rsp+4D0h+var_498]
0x18000fe9c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000fea1  nop
0x18000fea2  lea     rcx, [rsp+4D0h+var_480]
0x18000fea7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000feac  jmp     loc_18000FCCA
0x18000feb1  mov     rbx, [rsp+4D0h+var_480]
0x18000feb6  mov     rcx, [rsp+4D0h+var_490]
0x18000febb  test    rcx, rcx
0x18000febe  jz      short loc_18000FECD
0x18000fec0  mov     rax, [rcx]
0x18000fec3  mov     rax, [rax+10h]
0x18000fec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fecc  nop
0x18000fecd  mov     rcx, [rsp+4D0h+var_488]
0x18000fed2  test    rcx, rcx
0x18000fed5  jz      short loc_18000FEE4
0x18000fed7  mov     rax, [rcx]
0x18000feda  mov     rax, [rax+10h]
0x18000fede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fee3  nop
0x18000fee4  mov     rcx, [rsp+4D0h+var_498]
0x18000fee9  test    rcx, rcx
0x18000feec  jz      short loc_18000FEFB
0x18000feee  mov     rax, [rcx]
0x18000fef1  mov     rax, [rax+10h]
0x18000fef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fefa  nop
0x18000fefb  test    rbx, rbx
0x18000fefe  jz      short loc_18000FF10
0x18000ff00  mov     rax, [rbx]
0x18000ff03  mov     rcx, rbx
0x18000ff06  mov     rax, [rax+10h]
0x18000ff0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff0f  nop
0x18000ff10  xor     eax, eax
0x18000ff12  mov     rcx, [rbp+3D0h+var_50]
0x18000ff19  xor     rcx, rsp; StackCookie
0x18000ff1c  call    __security_check_cookie
0x18000ff21  add     rsp, 498h
0x18000ff28  pop     r15
0x18000ff2a  pop     r14
0x18000ff2c  pop     r13
0x18000ff2e  pop     r12
0x18000ff30  pop     rdi
0x18000ff31  pop     rsi
0x18000ff32  pop     rbx
0x18000ff33  pop     rbp
0x18000ff34  retn
```

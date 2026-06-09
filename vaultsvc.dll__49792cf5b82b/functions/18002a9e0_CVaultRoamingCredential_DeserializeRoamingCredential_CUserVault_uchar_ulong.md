# CVaultRoamingCredential::DeserializeRoamingCredential(CUserVault *,uchar *,ulong)

- ea: `0x18002a9e0`
- end: `0x18002b310`
- name: `?DeserializeRoamingCredential@CVaultRoamingCredential@@AEAAKPEAVCUserVault@@PEAEK@Z`
- size: `2352`
- prototype: `unsigned int __fastcall(CVaultRoamingCredential *__hidden this, struct CUserVault *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config`

## callers

- `0x180022290`

## callees

- `0x180002d10`
- `0x180003140`
- `0x180005d68`
- `0x180005df0`
- `0x180006610`
- `0x180007af0`
- `0x180009a20`
- `0x18000ae60`
- `0x18001a924`
- `0x180027340`
- `0x18002a9e0`
- `0x18002e5d0`
- `0x1800311e0`
- `0x18003a580`
- `0x18003b7d8`
- `0x18003be38`
- `0x18004976c`
- `0x18004b430`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aee0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002afb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b0d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b170`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b240`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aee0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002afb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b0d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b170`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b240`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002aebe`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002af8e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002b0ae`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002b14e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002b21e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002aebe`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002af8e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002b0ae`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002b14e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002b21e`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CVaultRoamingCredential::DeserializeRoamingCredential(
        CVaultRoamingCredential *this,
        struct CUserVault *a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  __int128 v6; // xmm6
  unsigned __int8 *v7; // r14
  unsigned int v8; // r15d
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rbx
  int v13; // eax
  int v14; // ebx
  void (__fastcall ***v15)(_QWORD); // rcx
  __int64 v16; // r15
  unsigned int VaultStore; // edi
  unsigned int Schema; // ebx
  unsigned int v20; // eax
  __int64 v21; // r9
  unsigned int v22; // edi
  _BYTE *v23; // rbx
  __int64 v24; // rax
  SIZE_T v25; // rax
  _BYTE *v26; // rcx
  unsigned int v27; // edi
  _BYTE *v28; // rbx
  __int64 v29; // rax
  SIZE_T v30; // rax
  _BYTE *v31; // rcx
  unsigned int v32; // edi
  _BYTE *v33; // rbx
  __int64 v34; // rax
  SIZE_T v35; // rax
  _BYTE *v36; // rcx
  unsigned int v37; // edi
  _BYTE *v38; // rbx
  __int64 v39; // rax
  SIZE_T v40; // rax
  _BYTE *v41; // rcx
  _BYTE *v42; // rbx
  __int64 v43; // rax
  SIZE_T v44; // rax
  _BYTE *v45; // rcx
  unsigned int v46; // [rsp+30h] [rbp-D0h] BYREF
  void (__fastcall *v47)(_BYTE *); // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v49; // [rsp+48h] [rbp-B8h]
  unsigned __int8 *v50; // [rsp+50h] [rbp-B0h] BYREF
  __int128 Buf1; // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall *v52)(_QWORD); // [rsp+68h] [rbp-98h] BYREF
  struct IVaultStore *v53; // [rsp+70h] [rbp-90h] BYREF
  int v54; // [rsp+78h] [rbp-88h]
  __int64 (__fastcall *v55)(_QWORD); // [rsp+80h] [rbp-80h] BYREF
  __int64 v56; // [rsp+88h] [rbp-78h]
  int v57; // [rsp+90h] [rbp-70h]
  void (__fastcall *v58)(struct IVaultAllocator *, struct _VAULT_ITEM_SCHEMA *); // [rsp+98h] [rbp-68h]
  void **v59; // [rsp+A0h] [rbp-60h]
  int *v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v62; // [rsp+B4h] [rbp-4Ch]
  __int128 v63; // [rsp+C4h] [rbp-3Ch]
  _BYTE v64[28]; // [rsp+D4h] [rbp-2Ch] BYREF

  v47 = (void (__fastcall *)(_BYTE *))AutoDereference<IVaultKeyManager>;
  hMem = 0;
  v49 = 0;
  if ( a4 < 0x10 )
  {
    v9 = 122;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_134;
    v11 = 30;
LABEL_133:
    WPP_SF_d(v10[2], v11, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids, v9);
    goto LABEL_134;
  }
  v6 = *(_OWORD *)a3;
  Buf1 = *(_OWORD *)a3;
  v7 = a3 + 16;
  v8 = a4 - 16;
  v46 = a4 - 16;
  if ( memcmp_0(&Buf1, &Vault_Schema_WebPassword, 0x10u) )
  {
    v9 = 87;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_134;
    v11 = 31;
    goto LABEL_133;
  }
  *((_OWORD *)this + 2) = v6;
  v55 = AutoDereference<IVaultKeyManager>;
  v56 = 0;
  v57 = 0;
  v52 = AutoDereference<IVaultKeyManager>;
  v53 = 0;
  v54 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  memset(v64, 0, sizeof(v64));
  v58 = VaultFreeVaultSchema;
  v59 = VaultGlobals::g_HeapAlloc;
  v60 = &v61;
  v12 = *((_QWORD *)a2 + 1);
  *(_QWORD *)&Buf1 = v12;
  if ( v12 )
  {
    (**(void (__fastcall ***)(__int64))v12)(v12);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 200LL))(v12, 0);
  }
  BYTE8(Buf1) = 1;
  v13 = *((_DWORD *)a2 + 27);
  if ( v13 == 2 )
  {
    if ( v12 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 208LL))(v12);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    }
    v14 = 55;
    goto LABEL_29;
  }
  if ( !v13 )
  {
    CVaultStoreLock::~CVaultStoreLock((CVaultStoreLock *)&Buf1);
    v14 = 212;
LABEL_29:
    VaultFreeVaultSchema((struct IVaultAllocator *)VaultGlobals::g_HeapAlloc, (struct _VAULT_ITEM_SCHEMA *)&v61);
    VaultStore = v14;
    goto LABEL_30;
  }
  v15 = (void (__fastcall ***)(_QWORD))*((_QWORD *)a2 + 1);
  if ( !v15 )
  {
    CVaultStoreLock::~CVaultStoreLock((CVaultStoreLock *)&Buf1);
    v14 = 1168;
    goto LABEL_29;
  }
  (**v15)(v15);
  v16 = *((_QWORD *)a2 + 1);
  v56 = v16;
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 208LL))(v12);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  }
  VaultStore = (*(__int64 (__fastcall **)(__int64, char *, HLOCAL *))(*(_QWORD *)v16 + 80LL))(
                 v16,
                 (char *)this + 32,
                 &hMem);
  if ( VaultStore == 1168 )
  {
    VaultStore = CUserVault::GetVaultStore(VaultGlobals::g_GlobalSchemaMgr, &v53, 0);
    if ( VaultStore )
    {
LABEL_22:
      VaultFreeVaultSchema((struct IVaultAllocator *)VaultGlobals::g_HeapAlloc, (struct _VAULT_ITEM_SCHEMA *)&v61);
      CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v52);
      CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v55);
      goto LABEL_31;
    }
    VaultStore = (*(__int64 (__fastcall **)(struct IVaultStore *, char *, HLOCAL *))(*(_QWORD *)v53 + 80LL))(
                   v53,
                   (char *)this + 32,
                   &hMem);
    if ( !VaultStore )
    {
      VaultStore = VaultConvertSchema(
                     (struct IVaultAllocator *)VaultGlobals::g_HeapAlloc,
                     (struct IVaultSchema *)hMem,
                     (struct _VAULT_ITEM_SCHEMA *)&v61);
      if ( VaultStore )
        goto LABEL_22;
      Schema = VaultCreateSchema(a2, (struct _VAULT_ITEM_SCHEMA *)&v61, 0, 1);
      VaultFreeVaultSchema((struct IVaultAllocator *)VaultGlobals::g_HeapAlloc, (struct _VAULT_ITEM_SCHEMA *)&v61);
      VaultStore = 0;
      if ( Schema != 183 )
        VaultStore = Schema;
    }
    VaultFreeVaultSchema((struct IVaultAllocator *)VaultGlobals::g_HeapAlloc, (struct _VAULT_ITEM_SCHEMA *)&v61);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v52);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v55);
    v8 = v46;
    goto LABEL_30;
  }
  VaultFreeVaultSchema((struct IVaultAllocator *)VaultGlobals::g_HeapAlloc, (struct _VAULT_ITEM_SCHEMA *)&v61);
  if ( v16 )
    AutoDereference<IVaultKeyManager>(v16);
  v8 = v46;
LABEL_30:
  if ( VaultStore )
  {
LABEL_31:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids, VaultStore);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v47);
    return VaultStore;
  }
  v20 = (*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)hMem + 96LL))(hMem);
  if ( v8 < 4 )
  {
    v9 = 122;
LABEL_134:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v47);
    return v9;
  }
  if ( *(_DWORD *)v7 > v20 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids, v20);
    v9 = 87;
    goto LABEL_134;
  }
  *((_DWORD *)this + 15) = *(_DWORD *)v7;
  if ( v8 - 4 < 4 )
  {
    v9 = 122;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids, 122);
    goto LABEL_134;
  }
  v21 = *((unsigned int *)v7 + 1);
  v50 = v7 + 8;
  v46 = v8 - 8;
  if ( (_DWORD)v21 != 256 )
  {
    v9 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids, v21, 87);
    goto LABEL_134;
  }
  *((_DWORD *)this + 14) = 256;
  *(_QWORD *)&Buf1 = 0;
  v22 = VaultDeserialize(&v50, &v46, (unsigned __int16 **)&Buf1);
  if ( v22 )
  {
    v23 = hMem;
    if ( hMem )
    {
      if ( v49 )
      {
        v24 = v49;
        do
        {
          *v23++ = 0;
          --v24;
        }
        while ( v24 );
        v23 = hMem;
      }
      if ( v47 )
      {
        v47(v23);
      }
      else if ( v23 )
      {
        v25 = LocalSize(v23);
        if ( v25 )
        {
          v26 = v23;
          do
          {
            *v26++ = 0;
            --v25;
          }
          while ( v25 );
        }
        LocalFree(v23);
      }
    }
    return v22;
  }
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((char *)this + 168);
  *((_QWORD *)this + 22) = Buf1;
  if ( ((*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)hMem + 32LL))(hMem) & 1) == 0 )
  {
    v27 = CVaultRoamingCredential::DeserializeCredElement(
            &v50,
            &v46,
            (struct IVaultSchema *)hMem,
            (struct CVaultCredElement **)this + 9);
    if ( v27 )
    {
      v28 = hMem;
      if ( hMem )
      {
        if ( v49 )
        {
          v29 = v49;
          do
          {
            *v28++ = 0;
            --v29;
          }
          while ( v29 );
          v28 = hMem;
        }
        if ( v47 )
        {
          v47(v28);
        }
        else if ( v28 )
        {
          v30 = LocalSize(v28);
          if ( v30 )
          {
            v31 = v28;
            do
            {
              *v31++ = 0;
              --v30;
            }
            while ( v30 );
          }
          LocalFree(v28);
        }
      }
      return v27;
    }
  }
  v9 = CVaultRoamingCredential::DeserializeCredElement(
         &v50,
         &v46,
         (struct IVaultSchema *)hMem,
         (struct CVaultCredElement **)this + 12);
  if ( v9
    || (v9 = CVaultRoamingCredential::DeserializeCredElement(
               &v50,
               &v46,
               (struct IVaultSchema *)hMem,
               (struct CVaultCredElement **)this + 15)) != 0
    || (v9 = CVaultRoamingCredential::DeserializeCredProperties(this, &v50, &v46, (struct IVaultSchema *)hMem)) != 0 )
  {
LABEL_79:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v47);
    return v9;
  }
  v32 = CVaultCredential::InitializeInternalProperties((char *)this + 192);
  if ( v32 )
  {
    v33 = hMem;
    if ( hMem )
    {
      if ( v49 )
      {
        v34 = v49;
        do
        {
          *v33++ = 0;
          --v34;
        }
        while ( v34 );
        v33 = hMem;
      }
      if ( v47 )
      {
        v47(v33);
      }
      else if ( v33 )
      {
        v35 = LocalSize(v33);
        if ( v35 )
        {
          v36 = v33;
          do
          {
            *v36++ = 0;
            --v35;
          }
          while ( v35 );
        }
        LocalFree(v33);
      }
    }
    return v32;
  }
  else
  {
    v37 = CVaultGenericPropertyCollection<enum ECredPropertyId,5>::DeserializeCollection(
            *((_QWORD *)this + 24),
            (_DWORD **)&v50,
            (int *)&v46);
    if ( v37 )
    {
      v38 = hMem;
      if ( hMem )
      {
        if ( v49 )
        {
          v39 = v49;
          do
          {
            *v38++ = 0;
            --v39;
          }
          while ( v39 );
          v38 = hMem;
        }
        if ( v47 )
        {
          v47(v38);
        }
        else if ( v38 )
        {
          v40 = LocalSize(v38);
          if ( v40 )
          {
            v41 = v38;
            do
            {
              *v41++ = 0;
              --v40;
            }
            while ( v40 );
          }
          LocalFree(v38);
        }
      }
      return v37;
    }
    else
    {
      if ( v46 )
      {
        v9 = 87;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids, v46, 87);
        goto LABEL_79;
      }
      v42 = hMem;
      if ( hMem )
      {
        v43 = v49;
        if ( v49 )
        {
          do
          {
            *v42++ = 0;
            --v43;
          }
          while ( v43 );
          v42 = hMem;
        }
        if ( v47 )
        {
          v47(v42);
        }
        else if ( v42 )
        {
          v44 = LocalSize(v42);
          if ( v44 )
          {
            v45 = v42;
            do
            {
              *v45++ = 0;
              --v44;
            }
            while ( v44 );
          }
          LocalFree(v42);
        }
      }
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18002a9e0  push    rbp
0x18002a9e2  push    rbx
0x18002a9e3  push    rsi
0x18002a9e4  push    rdi
0x18002a9e5  push    r12
0x18002a9e7  push    r13
0x18002a9e9  push    r14
0x18002a9eb  push    r15
0x18002a9ed  lea     rbp, [rsp-18h]
0x18002a9f2  sub     rsp, 118h
0x18002a9f9  movaps  [rsp+150h+var_50], xmm6
0x18002aa01  mov     rax, cs:__security_cookie
0x18002aa08  xor     rax, rsp
0x18002aa0b  mov     [rbp+50h+var_60], rax
0x18002aa0f  mov     r13, rdx
0x18002aa12  mov     rsi, rcx
0x18002aa15  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18002aa1c  mov     [rsp+150h+var_118], rax
0x18002aa21  xor     ebx, ebx
0x18002aa23  mov     [rsp+150h+hMem], rbx
0x18002aa28  mov     [rsp+150h+var_108], ebx
0x18002aa2c  cmp     r9d, 10h
0x18002aa30  jb      loc_18002B2A4
0x18002aa36  movups  xmm6, xmmword ptr [r8]
0x18002aa3a  movups  [rsp+150h+Buf1], xmm6
0x18002aa3f  lea     r14, [r8+10h]
0x18002aa43  lea     r15d, [r9-10h]
0x18002aa47  mov     [rsp+150h+var_120], r15d
0x18002aa4c  mov     r8d, 10h; Size
0x18002aa52  lea     rdx, Vault_Schema_WebPassword; Buf2
0x18002aa59  lea     rcx, [rsp+150h+Buf1]; Buf1
0x18002aa5e  call    memcmp_0
0x18002aa63  test    eax, eax
0x18002aa65  jz      short loc_18002AA97
0x18002aa67  lea     rax, WPP_GLOBAL_Control
0x18002aa6e  mov     ebx, 57h ; 'W'
0x18002aa73  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa7a  cmp     rcx, rax
0x18002aa7d  jz      loc_18002B2DB
0x18002aa83  test    byte ptr [rcx+1Ch], 2
0x18002aa87  jz      loc_18002B2DB
0x18002aa8d  mov     edx, 1Fh
0x18002aa92  jmp     loc_18002B2C7
0x18002aa97  movups  xmmword ptr [rsi+20h], xmm6
0x18002aa9b  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18002aaa2  mov     [rbp+50h+var_D0], rax
0x18002aaa6  mov     [rbp+50h+var_C8], rbx
0x18002aaaa  mov     [rbp+50h+var_C0], ebx
0x18002aaad  mov     [rsp+150h+var_E8], rax
0x18002aab2  mov     [rsp+150h+var_E0], rbx
0x18002aab7  mov     [rsp+150h+var_D8], ebx
0x18002aabb  mov     [rbp+50h+var_A0], ebx
0x18002aabe  xorps   xmm0, xmm0
0x18002aac1  movups  [rbp+50h+var_9C], xmm0
0x18002aac5  movups  [rbp+50h+var_8C], xmm0
0x18002aac9  movups  xmmword ptr [rbp+50h+var_7C], xmm0
0x18002aacd  movups  xmmword ptr [rbp+50h+var_7C+0Ch], xmm0
0x18002aad1  lea     rax, ?VaultFreeVaultSchema@@YAXPEAUIVaultAllocator@@PEAU_VAULT_ITEM_SCHEMA@@@Z; VaultFreeVaultSchema(IVaultAllocator *,_VAULT_ITEM_SCHEMA *)
0x18002aad8  mov     [rbp+50h+var_B8], rax
0x18002aadc  lea     rdi, ?g_HeapAlloc@VaultGlobals@@3VCVaultHeapAllocator@@A; CVaultHeapAllocator VaultGlobals::g_HeapAlloc
0x18002aae3  mov     [rbp+50h+var_B0], rdi
0x18002aae7  lea     rax, [rbp+50h+var_A0]
0x18002aaeb  mov     [rbp+50h+var_A8], rax
0x18002aaef  mov     rbx, [r13+8]
0x18002aaf3  mov     qword ptr [rsp+150h+Buf1], rbx
0x18002aaf8  test    rbx, rbx
0x18002aafb  jz      short loc_18002AB1F
0x18002aafd  mov     rax, [rbx]
0x18002ab00  mov     rcx, rbx
0x18002ab03  mov     rax, [rax]
0x18002ab06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab0b  mov     rax, [rbx]
0x18002ab0e  xor     edx, edx
0x18002ab10  mov     rcx, rbx
0x18002ab13  mov     rax, [rax+0C8h]
0x18002ab1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab1f  mov     byte ptr [rsp+150h+Buf1+8], 1
0x18002ab24  mov     eax, [r13+6Ch]
0x18002ab28  cmp     eax, 2
0x18002ab2b  jnz     short loc_18002AB5E
0x18002ab2d  test    rbx, rbx
0x18002ab30  jz      short loc_18002AB54
0x18002ab32  mov     rax, [rbx]
0x18002ab35  mov     rcx, rbx
0x18002ab38  mov     rax, [rax+0D0h]
0x18002ab3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab44  mov     rax, [rbx]
0x18002ab47  mov     rcx, rbx
0x18002ab4a  mov     rax, [rax+8]
0x18002ab4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab53  nop
0x18002ab54  mov     ebx, 37h ; '7'
0x18002ab59  jmp     loc_18002AD1C
0x18002ab5e  test    eax, eax
0x18002ab60  jnz     short loc_18002AB76
0x18002ab62  lea     rcx, [rsp+150h+Buf1]; this
0x18002ab67  call    ??1CVaultStoreLock@@QEAA@XZ; CVaultStoreLock::~CVaultStoreLock(void)
0x18002ab6c  mov     ebx, 0D4h
0x18002ab71  jmp     loc_18002AD1C
0x18002ab76  mov     rcx, [r13+8]
0x18002ab7a  test    rcx, rcx
0x18002ab7d  jz      loc_18002AD0D
0x18002ab83  mov     rax, [rcx]
0x18002ab86  mov     rax, [rax]
0x18002ab89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab8e  mov     r15, [r13+8]
0x18002ab92  mov     [rbp+50h+var_C8], r15
0x18002ab96  test    rbx, rbx
0x18002ab99  jz      short loc_18002ABBD
0x18002ab9b  mov     rax, [rbx]
0x18002ab9e  mov     rcx, rbx
0x18002aba1  mov     rax, [rax+0D0h]
0x18002aba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abad  mov     rax, [rbx]
0x18002abb0  mov     rcx, rbx
0x18002abb3  mov     rax, [rax+8]
0x18002abb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abbc  nop
0x18002abbd  mov     rax, [r15]
0x18002abc0  lea     r8, [rsp+150h+hMem]
0x18002abc5  lea     rdx, [rsi+20h]
0x18002abc9  mov     rcx, r15
0x18002abcc  mov     rax, [rax+50h]
0x18002abd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abd5  mov     edi, eax
0x18002abd7  mov     ebx, 490h
0x18002abdc  cmp     eax, ebx
0x18002abde  jz      short loc_18002AC09
0x18002abe0  lea     rdx, [rbp+50h+var_A0]; struct _VAULT_ITEM_SCHEMA *
0x18002abe4  lea     rcx, ?g_HeapAlloc@VaultGlobals@@3VCVaultHeapAllocator@@A; struct IVaultAllocator *
0x18002abeb  call    ?VaultFreeVaultSchema@@YAXPEAUIVaultAllocator@@PEAU_VAULT_ITEM_SCHEMA@@@Z; VaultFreeVaultSchema(IVaultAllocator *,_VAULT_ITEM_SCHEMA *)
0x18002abf0  nop
0x18002abf1  test    r15, r15
0x18002abf4  jz      short loc_18002ABFF
0x18002abf6  mov     rcx, r15
0x18002abf9  call    ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18002abfe  nop
0x18002abff  mov     r15d, [rsp+150h+var_120]
0x18002ac04  jmp     loc_18002AD2B
0x18002ac09  xor     r8d, r8d; unsigned __int8
0x18002ac0c  lea     rdx, [rsp+150h+var_E0]; struct IVaultStore **
0x18002ac11  mov     rcx, cs:?g_GlobalSchemaMgr@VaultGlobals@@3VCVaultGlobalSchemaMgr@@A; this
0x18002ac18  call    ?GetVaultStore@CUserVault@@QEAAKPEAPEAUIVaultStore@@E@Z; CUserVault::GetVaultStore(IVaultStore * *,uchar)
0x18002ac1d  mov     edi, eax
0x18002ac1f  test    eax, eax
0x18002ac21  jz      short loc_18002AC4E
0x18002ac23  lea     rdx, [rbp+50h+var_A0]; struct _VAULT_ITEM_SCHEMA *
0x18002ac27  lea     rcx, ?g_HeapAlloc@VaultGlobals@@3VCVaultHeapAllocator@@A; struct IVaultAllocator *
0x18002ac2e  call    ?VaultFreeVaultSchema@@YAXPEAUIVaultAllocator@@PEAU_VAULT_ITEM_SCHEMA@@@Z; VaultFreeVaultSchema(IVaultAllocator *,_VAULT_ITEM_SCHEMA *)
0x18002ac33  nop
0x18002ac34  lea     rcx, [rsp+150h+var_E8]
0x18002ac39  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x18002ac3e  nop
0x18002ac3f  lea     rcx, [rbp+50h+var_D0]
0x18002ac43  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x18002ac48  nop
0x18002ac49  jmp     loc_18002AD2F
0x18002ac4e  mov     rcx, [rsp+150h+var_E0]
0x18002ac53  mov     rax, [rcx]
0x18002ac56  lea     r8, [rsp+150h+hMem]
0x18002ac5b  lea     rdx, [rsi+20h]
0x18002ac5f  mov     rax, [rax+50h]
0x18002ac63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac68  mov     edi, eax
0x18002ac6a  test    eax, eax
0x18002ac6c  jnz     short loc_18002ACE0
0x18002ac6e  lea     r8, [rbp+50h+var_A0]; struct _VAULT_ITEM_SCHEMA *
0x18002ac72  mov     rdx, [rsp+150h+hMem]; struct IVaultSchema *
0x18002ac77  lea     rcx, ?g_HeapAlloc@VaultGlobals@@3VCVaultHeapAllocator@@A; struct IVaultAllocator *
0x18002ac7e  call    ?VaultConvertSchema@@YAKPEAUIVaultAllocator@@PEAUIVaultSchema@@PEAU_VAULT_ITEM_SCHEMA@@@Z; VaultConvertSchema(IVaultAllocator *,IVaultSchema *,_VAULT_ITEM_SCHEMA *)
0x18002ac83  mov     edi, eax
0x18002ac85  test    eax, eax
0x18002ac87  jz      short loc_18002ACB1
0x18002ac89  lea     rdx, [rbp+50h+var_A0]; struct _VAULT_ITEM_SCHEMA *
0x18002ac8d  lea     rcx, ?g_HeapAlloc@VaultGlobals@@3VCVaultHeapAllocator@@A; struct IVaultAllocator *
0x18002ac94  call    ?VaultFreeVaultSchema@@YAXPEAUIVaultAllocator@@PEAU_VAULT_ITEM_SCHEMA@@@Z; VaultFreeVaultSchema(IVaultAllocator *,_VAULT_ITEM_SCHEMA *)
0x18002ac99  nop
0x18002ac9a  lea     rcx, [rsp+150h+var_E8]
0x18002ac9f  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x18002aca4  nop
0x18002aca5  lea     rcx, [rbp+50h+var_D0]
0x18002aca9  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x18002acae  nop
0x18002acaf  jmp     short loc_18002AD2F
0x18002acb1  mov     r9b, 1; unsigned __int8
0x18002acb4  xor     r8d, r8d; unsigned int
0x18002acb7  lea     rdx, [rbp+50h+var_A0]; struct _VAULT_ITEM_SCHEMA *
0x18002acbb  mov     rcx, r13; this
0x18002acbe  call    ?VaultCreateSchema@@YAKPEAVCUserVault@@PEAU_VAULT_ITEM_SCHEMA@@KE@Z; VaultCreateSchema(CUserVault *,_VAULT_ITEM_SCHEMA *,ulong,uchar)
0x18002acc3  mov     ebx, eax
0x18002acc5  lea     rdx, [rbp+50h+var_A0]; struct _VAULT_ITEM_SCHEMA *
0x18002acc9  lea     rcx, ?g_HeapAlloc@VaultGlobals@@3VCVaultHeapAllocator@@A; struct IVaultAllocator *
0x18002acd0  call    ?VaultFreeVaultSchema@@YAXPEAUIVaultAllocator@@PEAU_VAULT_ITEM_SCHEMA@@@Z; VaultFreeVaultSchema(IVaultAllocator *,_VAULT_ITEM_SCHEMA *)
0x18002acd5  xor     edi, edi
0x18002acd7  cmp     ebx, 0B7h
0x18002acdd  cmovnz  edi, ebx
0x18002ace0  lea     rdx, [rbp+50h+var_A0]; struct _VAULT_ITEM_SCHEMA *
0x18002ace4  lea     rcx, ?g_HeapAlloc@VaultGlobals@@3VCVaultHeapAllocator@@A; struct IVaultAllocator *
0x18002aceb  call    ?VaultFreeVaultSchema@@YAXPEAUIVaultAllocator@@PEAU_VAULT_ITEM_SCHEMA@@@Z; VaultFreeVaultSchema(IVaultAllocator *,_VAULT_ITEM_SCHEMA *)
0x18002acf0  nop
0x18002acf1  lea     rcx, [rsp+150h+var_E8]
0x18002acf6  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x18002acfb  nop
0x18002acfc  lea     rcx, [rbp+50h+var_D0]
0x18002ad00  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x18002ad05  nop
0x18002ad06  mov     r15d, [rsp+150h+var_120]
0x18002ad0b  jmp     short loc_18002AD2B
0x18002ad0d  lea     rcx, [rsp+150h+Buf1]; this
0x18002ad12  call    ??1CVaultStoreLock@@QEAA@XZ; CVaultStoreLock::~CVaultStoreLock(void)
0x18002ad17  mov     ebx, 490h
0x18002ad1c  lea     rdx, [rbp+50h+var_A0]; struct _VAULT_ITEM_SCHEMA *
0x18002ad20  mov     rcx, rdi; struct IVaultAllocator *
0x18002ad23  call    ?VaultFreeVaultSchema@@YAXPEAUIVaultAllocator@@PEAU_VAULT_ITEM_SCHEMA@@@Z; VaultFreeVaultSchema(IVaultAllocator *,_VAULT_ITEM_SCHEMA *)
0x18002ad28  nop
0x18002ad29  mov     edi, ebx
0x18002ad2b  test    edi, edi
0x18002ad2d  jz      short loc_18002AD73
0x18002ad2f  lea     rax, WPP_GLOBAL_Control
0x18002ad36  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad3d  cmp     rcx, rax
0x18002ad40  jz      short loc_18002AD61
0x18002ad42  test    byte ptr [rcx+1Ch], 2
0x18002ad46  jz      short loc_18002AD61
0x18002ad48  mov     edx, 2Bh ; '+'
0x18002ad4d  mov     r9d, edi
0x18002ad50  lea     r8, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids
0x18002ad57  mov     rcx, [rcx+10h]
0x18002ad5b  call    WPP_SF_d
0x18002ad60  nop
0x18002ad61  lea     rcx, [rsp+150h+var_118]
0x18002ad66  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002ad6b  nop
0x18002ad6c  mov     eax, edi
0x18002ad6e  jmp     loc_18002B2E8
0x18002ad73  mov     rcx, [rsp+150h+hMem]
0x18002ad78  mov     rax, [rcx]
0x18002ad7b  mov     rax, [rax+60h]
0x18002ad7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad84  mov     r9d, eax
0x18002ad87  cmp     r15d, 4
0x18002ad8b  jb      loc_18002B292
0x18002ad91  mov     ecx, [r14]
0x18002ad94  cmp     ecx, eax
0x18002ad96  jbe     short loc_18002ADD0
0x18002ad98  lea     rax, WPP_GLOBAL_Control
0x18002ad9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ada6  cmp     rcx, rax
0x18002ada9  jz      short loc_18002ADC6
0x18002adab  test    byte ptr [rcx+1Ch], 2
0x18002adaf  jz      short loc_18002ADC6
0x18002adb1  mov     edx, 20h ; ' '
0x18002adb6  lea     r8, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids
0x18002adbd  mov     rcx, [rcx+10h]
0x18002adc1  call    WPP_SF_d
0x18002adc6  mov     ebx, 57h ; 'W'
0x18002adcb  jmp     loc_18002B297
0x18002add0  lea     edx, [r15-4]
0x18002add4  mov     [rsi+3Ch], ecx
0x18002add7  cmp     edx, 4
0x18002adda  jb      loc_18002B24E
0x18002ade0  mov     r9d, [r14+4]
0x18002ade4  lea     rax, [r14+8]
0x18002ade8  mov     [rsp+150h+var_100], rax
0x18002aded  lea     eax, [rdx-4]
0x18002adf0  mov     [rsp+150h+var_120], eax
0x18002adf4  cmp     r9d, 100h
0x18002adfb  jz      short loc_18002AE41
0x18002adfd  lea     rax, WPP_GLOBAL_Control
0x18002ae04  mov     ebx, 57h ; 'W'
0x18002ae09  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae10  cmp     rcx, rax
0x18002ae13  jz      loc_18002B285
0x18002ae19  test    byte ptr [rcx+1Ch], 2
0x18002ae1d  jz      loc_18002B285
0x18002ae23  mov     edx, 22h ; '"'
0x18002ae28  mov     [rsp+150h+var_130], ebx
0x18002ae2c  lea     r8, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids
0x18002ae33  mov     rcx, [rcx+10h]
0x18002ae37  call    WPP_SF_dd
0x18002ae3c  jmp     loc_18002B285
0x18002ae41  mov     dword ptr [rsi+38h], 100h
0x18002ae48  mov     qword ptr [rsp+150h+Buf1], 0
0x18002ae51  lea     r8, [rsp+150h+Buf1]; unsigned __int16 **
0x18002ae56  lea     rdx, [rsp+150h+var_120]; unsigned int *
0x18002ae5b  lea     rcx, [rsp+150h+var_100]; unsigned __int8 **
0x18002ae60  call    ?VaultDeserialize@@YAKAEAPEAEAEAKAEAPEAG@Z; VaultDeserialize(uchar * &,ulong &,ushort * &)
0x18002ae65  mov     edi, eax
0x18002ae67  test    eax, eax
0x18002ae69  jz      loc_18002AEEE
0x18002ae6f  mov     rbx, [rsp+150h+hMem]
0x18002ae74  test    rbx, rbx
0x18002ae77  jz      short loc_18002AEE7
0x18002ae79  mov     ecx, [rsp+150h+var_108]
0x18002ae7d  test    ecx, ecx
0x18002ae7f  jz      short loc_18002AEA2
0x18002ae81  test    rbx, rbx
0x18002ae84  jz      short loc_18002AEA2
0x18002ae86  mov     eax, ecx
0x18002ae88  test    ecx, ecx
  ... truncated ...
```

# CBlbBackupAsync::PopulateVolumeMap(ulong,_BLBCAT_VOLUME_INFO *,_BLBSRV_VOLUME_MAP * *,ulong *)

- ea: `0x14002f4cc`
- end: `0x14002f85c`
- name: `?PopulateVolumeMap@CBlbBackupAsync@@AEAAJKPEAU_BLBCAT_VOLUME_INFO@@PEAPEAU_BLBSRV_VOLUME_MAP@@PEAK@Z`
- size: `912`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this, unsigned int, struct _BLBCAT_VOLUME_INFO *, struct _BLBSRV_VOLUME_MAP **, BSTR bstrString)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x140019fd0`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000be04`
- `0x140014200`
- `0x14002f4cc`
- `0x140088d0c`
- `0x14008ba2c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14002f66f`
- `msvcrt!_wcsicmp` at `0x14002f66f`
- `ole32!CoTaskMemAlloc` at `0x14002f5b4`
- `ole32!CoTaskMemAlloc` at `0x14002f5b4`
- `ole32!CoTaskMemFree` at `0x14002f62b`
- `ole32!CoTaskMemFree` at `0x14002f77f`
- `ole32!CoTaskMemFree` at `0x14002f797`
- `ole32!CoTaskMemFree` at `0x14002f7b0`
- `ole32!CoTaskMemFree` at `0x14002f7cd`
- `ole32!CoTaskMemFree` at `0x14002f80f`
- `ole32!CoTaskMemFree` at `0x14002f62b`
- `ole32!CoTaskMemFree` at `0x14002f77f`
- `ole32!CoTaskMemFree` at `0x14002f797`
- `ole32!CoTaskMemFree` at `0x14002f7b0`
- `ole32!CoTaskMemFree` at `0x14002f7cd`
- `ole32!CoTaskMemFree` at `0x14002f80f`
- `OLEAUT32!__imp_SysFreeString` at `0x14002f75f`
- `OLEAUT32!__imp_SysFreeString` at `0x14002f75f`

## string_xrefs

- `0x14002f54f`: `base\stor\blb\engine\service\backup.cpp`
- `0x14002f59b`: `base\stor\blb\engine\service\backup.cpp`
- `0x14002f7e6`: `base\stor\blb\engine\service\backup.cpp`

## pseudocode

```c
__int64 __fastcall CBlbBackupAsync::PopulateVolumeMap(
        CBlbBackupAsync *this,
        unsigned int a2,
        struct _BLBCAT_VOLUME_INFO *a3,
        struct _BLBSRV_VOLUME_MAP **a4,
        BSTR bstrString)
{
  unsigned int v5; // r12d
  unsigned int v8; // r15d
  unsigned int v9; // ebp
  wchar_t *v10; // r13
  unsigned int v11; // edx
  struct _BLBSRV_VOLUME_MAP *v12; // rax
  struct _BLBSRV_VOLUME_MAP *v13; // r14
  int v14; // esi
  __int64 i; // rax
  struct _GUID *v16; // r15
  __int64 v17; // rdi
  unsigned int j; // ebx
  __int64 v19; // rax
  int v20; // eax
  unsigned __int16 **v21; // rbx
  unsigned __int16 *v22; // rcx
  ATL::CComBSTR *v23; // rax
  char v24; // al
  unsigned int v25; // r12d
  __int64 v26; // r15
  void *v27; // rcx
  void *v28; // rcx
  void *v29; // rcx
  int v31; // [rsp+24h] [rbp-64h]
  wchar_t *String2; // [rsp+28h] [rbp-60h] BYREF
  __int64 v33; // [rsp+30h] [rbp-58h]

  v5 = 0;
  v8 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 423, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  String2 = 0;
  v9 = 0;
  v10 = 0;
  if ( !a4 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x25CEu, "ppVolumeMap");
  *a4 = 0;
  v11 = 0;
  *(_DWORD *)bstrString = 0;
  if ( !v8 )
    goto LABEL_12;
  do
  {
    if ( (*((_BYTE *)a3 + 120 * v11 + 16) & 1) == 0 )
      ++v9;
    ++v11;
  }
  while ( v11 < v8 );
  if ( !v9 )
LABEL_12:
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x25DCu, "cVolumeMap > 0");
  v12 = (struct _BLBSRV_VOLUME_MAP *)CoTaskMemAlloc(24LL * v9);
  v13 = v12;
  if ( v12 )
  {
    v14 = 0;
    memset_0(v12, 0, 24LL * v9);
    for ( i = 0; ; i = (unsigned int)(v31 + 1) )
    {
      v31 = i;
      if ( (unsigned int)i >= v8 )
      {
        if ( v5 != v9 )
          BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x2628u, "iVolumeMap == cVolumeMap");
        *(_DWORD *)bstrString = v9;
        *a4 = v13;
        goto LABEL_54;
      }
      v16 = (struct _GUID *)((char *)a3 + 120 * i);
      if ( (v16[1].Data1 & 1) == 0 )
        break;
LABEL_33:
      v8 = a2;
    }
    v17 = 0;
    for ( j = 0; ; ++j )
    {
      v19 = *((_QWORD *)this + 54);
      if ( j >= *(_DWORD *)(v19 + 80) )
        break;
      v33 = *(_QWORD *)(v19 + 88);
      if ( v10 )
      {
        CoTaskMemFree(v10);
        String2 = 0;
      }
      v20 = BlbutilQueryVolumeName(v16, v16[1].Data1, &String2, 0);
      v10 = String2;
      v14 = v20;
      if ( v20 < 0 )
        goto LABEL_41;
      v17 = v33 + 56LL * j;
      if ( !_wcsicmp(*(const wchar_t **)(v17 + 16), String2) )
        break;
    }
    if ( j == *(_DWORD *)(*((_QWORD *)this + 54) + 80LL) || (v21 = (unsigned __int16 **)(v17 + 24), v17) && !*v21 )
    {
      v14 = -2139619296;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        v24 = 0;
      }
      else
      {
        v23 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v16);
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          424,
          &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          *(_QWORD *)v23);
        v24 = 1;
      }
      if ( (v24 & 1) != 0 )
        SysFreeString(bstrString);
    }
    else
    {
      v22 = *(unsigned __int16 **)v16[1].Data4;
      if ( !v22 )
        v22 = v10;
      v14 = BlbutilSlashTerminatePath(v22, (LPVOID *)v13 + 3 * v5);
      if ( v14 >= 0 )
      {
        v14 = BlbutilSlashTerminatePath(*v21, (LPVOID *)v13 + 3 * v5 + 2);
        if ( v14 >= 0 )
        {
          ++v5;
          goto LABEL_33;
        }
      }
    }
LABEL_41:
    v25 = 0;
    if ( v9 )
    {
      v26 = 0;
      do
      {
        v27 = (void *)*((_QWORD *)v13 + 3 * v26);
        if ( v27 )
        {
          CoTaskMemFree(v27);
          *((_QWORD *)v13 + 3 * v26) = 0;
        }
        v28 = (void *)*((_QWORD *)v13 + 3 * v26 + 2);
        if ( v28 )
        {
          CoTaskMemFree(v28);
          *((_QWORD *)v13 + 3 * v26 + 2) = 0;
        }
        v29 = (void *)*((_QWORD *)v13 + 3 * v26 + 1);
        if ( v29 )
        {
          CoTaskMemFree(v29);
          *((_QWORD *)v13 + 3 * v26 + 1) = 0;
        }
        ++v25;
        ++v26;
      }
      while ( v25 < v9 );
    }
    CoTaskMemFree(v13);
LABEL_54:
    if ( v10 )
      CoTaskMemFree(v10);
  }
  else
  {
    v14 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 425, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14002f4cc  mov     rax, rsp
0x14002f4cf  mov     [rax+20h], r9
0x14002f4d3  mov     [rax+18h], r8
0x14002f4d7  mov     [rax+10h], edx
0x14002f4da  mov     [rax+8], rcx
0x14002f4de  push    rbx
0x14002f4df  push    rbp
0x14002f4e0  push    rsi
0x14002f4e1  push    rdi
0x14002f4e2  push    r12
0x14002f4e4  push    r13
0x14002f4e6  push    r14
0x14002f4e8  push    r15
0x14002f4ea  sub     rsp, 48h
0x14002f4ee  xor     r12d, r12d
0x14002f4f1  mov     rdi, r9
0x14002f4f4  mov     [rsp+88h+var_68], r12d
0x14002f4f9  mov     rbx, r8
0x14002f4fc  mov     r15d, edx
0x14002f4ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f506  lea     rax, WPP_GLOBAL_Control
0x14002f50d  cmp     rcx, rax
0x14002f510  jz      short loc_14002F533
0x14002f512  test    byte ptr [rcx+1Ch], 1
0x14002f516  jz      short loc_14002F533
0x14002f518  cmp     byte ptr [rcx+19h], 4
0x14002f51c  jb      short loc_14002F533
0x14002f51e  mov     rcx, [rcx+10h]
0x14002f522  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002f529  mov     edx, 1A7h
0x14002f52e  call    WPP_SF_
0x14002f533  mov     [rsp+88h+String2], r12
0x14002f538  mov     ebp, r12d
0x14002f53b  mov     r13, r12
0x14002f53e  test    rdi, rdi
0x14002f541  jnz     short loc_14002F55B
0x14002f543  lea     r8, aPpvolumemap; "ppVolumeMap"
0x14002f54a  mov     edx, 25CEh; unsigned int
0x14002f54f  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14002f556  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14002f55b  mov     [rdi], r12
0x14002f55e  mov     edx, r12d
0x14002f561  mov     rdi, [rsp+88h+bstrString]
0x14002f569  mov     [rdi], r12d
0x14002f56c  test    r15d, r15d
0x14002f56f  jz      short loc_14002F58F
0x14002f571  mov     eax, edx
0x14002f573  imul    rcx, rax, 78h ; 'x'
0x14002f577  lea     eax, [rbp+1]
0x14002f57a  test    byte ptr [rcx+rbx+10h], 1
0x14002f57f  cmovz   ebp, eax
0x14002f582  inc     edx
0x14002f584  mov     eax, ebp
0x14002f586  cmp     edx, r15d
0x14002f589  jb      short loc_14002F571
0x14002f58b  test    eax, eax
0x14002f58d  jnz     short loc_14002F5A7
0x14002f58f  lea     r8, aCvolumemap0; "cVolumeMap > 0"
0x14002f596  mov     edx, 25DCh; unsigned int
0x14002f59b  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14002f5a2  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14002f5a7  mov     eax, ebp
0x14002f5a9  lea     rbx, [rax+rax*2]
0x14002f5ad  shl     rbx, 3
0x14002f5b1  mov     rcx, rbx; cb
0x14002f5b4  call    cs:__imp_CoTaskMemAlloc
0x14002f5ba  mov     r14, rax
0x14002f5bd  test    rax, rax
0x14002f5c0  jnz     short loc_14002F5CC
0x14002f5c2  mov     esi, 8007000Eh
0x14002f5c7  jmp     loc_14002F815
0x14002f5cc  mov     r8, rbx; Size
0x14002f5cf  xor     edx, edx; Val
0x14002f5d1  mov     rcx, r14; void *
0x14002f5d4  mov     esi, r12d
0x14002f5d7  call    memset_0
0x14002f5dc  xor     eax, eax
0x14002f5de  mov     [rsp+88h+var_64], eax
0x14002f5e2  cmp     eax, r15d
0x14002f5e5  jnb     loc_14002F7D5
0x14002f5eb  imul    r15, rax, 78h ; 'x'
0x14002f5ef  add     r15, [rsp+88h+arg_10]
0x14002f5f7  test    byte ptr [r15+10h], 1
0x14002f5fc  jnz     loc_14002F6E2
0x14002f602  xor     edi, edi
0x14002f604  xor     ebx, ebx
0x14002f606  mov     rax, [rsp+88h+arg_0]
0x14002f60e  mov     rax, [rax+1B0h]
0x14002f615  cmp     ebx, [rax+50h]
0x14002f618  jnb     short loc_14002F67D
0x14002f61a  mov     rax, [rax+58h]
0x14002f61e  mov     [rsp+88h+var_58], rax
0x14002f623  test    r13, r13
0x14002f626  jz      short loc_14002F63A
0x14002f628  mov     rcx, r13; pv
0x14002f62b  call    cs:__imp_CoTaskMemFree
0x14002f631  mov     [rsp+88h+String2], 0
0x14002f63a  mov     edx, [r15+10h]; unsigned int
0x14002f63e  lea     r8, [rsp+88h+String2]; unsigned __int16 **
0x14002f643  xor     r9d, r9d; unsigned __int8
0x14002f646  mov     rcx, r15; struct _GUID *
0x14002f649  call    ?BlbutilQueryVolumeName@@YAJPEAU_GUID@@KPEAPEAGE@Z; BlbutilQueryVolumeName(_GUID *,ulong,ushort * *,uchar)
0x14002f64e  mov     r13, [rsp+88h+String2]
0x14002f653  mov     esi, eax
0x14002f655  test    eax, eax
0x14002f657  js      loc_14002F765
0x14002f65d  mov     eax, ebx
0x14002f65f  mov     rdx, r13; String2
0x14002f662  imul    rdi, rax, 38h ; '8'
0x14002f666  add     rdi, [rsp+88h+var_58]
0x14002f66b  mov     rcx, [rdi+10h]; String1
0x14002f66f  call    cs:__imp__wcsicmp
0x14002f675  test    eax, eax
0x14002f677  jz      short loc_14002F67D
0x14002f679  inc     ebx
0x14002f67b  jmp     short loc_14002F606
0x14002f67d  mov     rax, [rsp+88h+arg_0]
0x14002f685  mov     rax, [rax+1B0h]
0x14002f68c  cmp     ebx, [rax+50h]
0x14002f68f  jz      short loc_14002F6F5
0x14002f691  lea     rbx, [rdi+18h]
0x14002f695  test    rdi, rdi
0x14002f698  jz      short loc_14002F6A0
0x14002f69a  cmp     qword ptr [rbx], 0
0x14002f69e  jz      short loc_14002F6F5
0x14002f6a0  mov     rcx, [r15+18h]
0x14002f6a4  mov     eax, r12d
0x14002f6a7  lea     rdx, [rax+rax*2]
0x14002f6ab  lea     rdi, [r14+rdx*8]
0x14002f6af  mov     rdx, rdi; unsigned __int16 **
0x14002f6b2  test    rcx, rcx
0x14002f6b5  jnz     short loc_14002F6BA
0x14002f6b7  mov     rcx, r13; unsigned __int16 *
0x14002f6ba  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x14002f6bf  mov     esi, eax
0x14002f6c1  test    eax, eax
0x14002f6c3  js      loc_14002F765
0x14002f6c9  mov     rcx, [rbx]; unsigned __int16 *
0x14002f6cc  lea     rdx, [rdi+10h]; unsigned __int16 **
0x14002f6d0  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x14002f6d5  mov     esi, eax
0x14002f6d7  test    eax, eax
0x14002f6d9  js      loc_14002F765
0x14002f6df  inc     r12d
0x14002f6e2  mov     eax, [rsp+88h+var_64]
0x14002f6e6  mov     r15d, [rsp+88h+arg_8]
0x14002f6ee  inc     eax
0x14002f6f0  jmp     loc_14002F5DE
0x14002f6f5  mov     esi, 80780020h
0x14002f6fa  mov     rax, cs:WPP_GLOBAL_Control
0x14002f701  lea     rcx, WPP_GLOBAL_Control
0x14002f708  cmp     rax, rcx
0x14002f70b  jz      short loc_14002F74F
0x14002f70d  test    byte ptr [rax+1Ch], 1
0x14002f711  jz      short loc_14002F74F
0x14002f713  cmp     byte ptr [rax+19h], 2
0x14002f717  jb      short loc_14002F74F
0x14002f719  mov     rdx, r15; struct _GUID *
0x14002f71c  lea     rcx, [rsp+88h+bstrString]; this
0x14002f724  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x14002f729  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f730  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002f737  mov     edx, 1A8h
0x14002f73c  mov     r9, [rax]
0x14002f73f  mov     rcx, [rcx+10h]
0x14002f743  call    WPP_SF_S
0x14002f748  mov     eax, 1
0x14002f74d  jmp     short loc_14002F753
0x14002f74f  mov     eax, [rsp+88h+var_68]
0x14002f753  test    al, 1
0x14002f755  jz      short loc_14002F765
0x14002f757  mov     rcx, [rsp+88h+bstrString]; bstrString
0x14002f75f  call    cs:__imp_SysFreeString
0x14002f765  xor     r12d, r12d
0x14002f768  mov     rbx, r14
0x14002f76b  test    ebp, ebp
0x14002f76d  jz      short loc_14002F7CA
0x14002f76f  xor     r15d, r15d
0x14002f772  lea     rdi, [r15+r15*2]
0x14002f776  mov     rcx, [rbx+rdi*8]; pv
0x14002f77a  test    rcx, rcx
0x14002f77d  jz      short loc_14002F78D
0x14002f77f  call    cs:__imp_CoTaskMemFree
0x14002f785  mov     qword ptr [rbx+rdi*8], 0
0x14002f78d  mov     rcx, [rbx+rdi*8+10h]; pv
0x14002f792  test    rcx, rcx
0x14002f795  jz      short loc_14002F7A6
0x14002f797  call    cs:__imp_CoTaskMemFree
0x14002f79d  mov     qword ptr [rbx+rdi*8+10h], 0
0x14002f7a6  mov     rcx, [rbx+rdi*8+8]; pv
0x14002f7ab  test    rcx, rcx
0x14002f7ae  jz      short loc_14002F7BF
0x14002f7b0  call    cs:__imp_CoTaskMemFree
0x14002f7b6  mov     qword ptr [rbx+rdi*8+8], 0
0x14002f7bf  inc     r12d
0x14002f7c2  inc     r15
0x14002f7c5  cmp     r12d, ebp
0x14002f7c8  jb      short loc_14002F772
0x14002f7ca  mov     rcx, r14; pv
0x14002f7cd  call    cs:__imp_CoTaskMemFree
0x14002f7d3  jmp     short loc_14002F807
0x14002f7d5  cmp     r12d, ebp
0x14002f7d8  jz      short loc_14002F7F2
0x14002f7da  lea     r8, aIvolumemapCvol; "iVolumeMap == cVolumeMap"
0x14002f7e1  mov     edx, 2628h; unsigned int
0x14002f7e6  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14002f7ed  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14002f7f2  mov     rax, [rsp+88h+bstrString]
0x14002f7fa  mov     [rax], ebp
0x14002f7fc  mov     rax, [rsp+88h+arg_18]
0x14002f804  mov     [rax], r14
0x14002f807  test    r13, r13
0x14002f80a  jz      short loc_14002F815
0x14002f80c  mov     rcx, r13; pv
0x14002f80f  call    cs:__imp_CoTaskMemFree
0x14002f815  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f81c  lea     rax, WPP_GLOBAL_Control
0x14002f823  cmp     rcx, rax
0x14002f826  jz      short loc_14002F849
0x14002f828  test    byte ptr [rcx+1Ch], 1
0x14002f82c  jz      short loc_14002F849
0x14002f82e  cmp     byte ptr [rcx+19h], 4
0x14002f832  jb      short loc_14002F849
0x14002f834  mov     rcx, [rcx+10h]
0x14002f838  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002f83f  mov     edx, 1A9h
0x14002f844  call    WPP_SF_
0x14002f849  mov     eax, esi
0x14002f84b  add     rsp, 48h
0x14002f84f  pop     r15
0x14002f851  pop     r14
0x14002f853  pop     r13
0x14002f855  pop     r12
0x14002f857  pop     rdi
0x14002f858  pop     rsi
0x14002f859  pop     rbp
0x14002f85a  pop     rbx
0x14002f85b  retn
```

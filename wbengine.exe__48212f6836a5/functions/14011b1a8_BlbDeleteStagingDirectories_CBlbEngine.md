# BlbDeleteStagingDirectories(CBlbEngine *)

- ea: `0x14011b1a8`
- end: `0x14011b5c1`
- name: `?BlbDeleteStagingDirectories@@YAJPEAVCBlbEngine@@@Z`
- size: `1049`
- prototype: `__int64 __fastcall(struct CBlbEngine *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x140075000`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000be04`
- `0x140014200`
- `0x140014260`
- `0x14008863c`
- `0x140088d0c`
- `0x14008ba2c`
- `0x14008c7ec`
- `0x14008db7c`
- `0x14011b1a8`
- `0x14012e834`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14011b302`
- `ole32!CoTaskMemFree` at `0x14011b31d`
- `ole32!CoTaskMemFree` at `0x14011b338`
- `ole32!CoTaskMemFree` at `0x14011b552`
- `ole32!CoTaskMemFree` at `0x14011b560`
- `ole32!CoTaskMemFree` at `0x14011b56e`
- `ole32!CoTaskMemFree` at `0x14011b302`
- `ole32!CoTaskMemFree` at `0x14011b31d`
- `ole32!CoTaskMemFree` at `0x14011b338`
- `ole32!CoTaskMemFree` at `0x14011b552`
- `ole32!CoTaskMemFree` at `0x14011b560`
- `ole32!CoTaskMemFree` at `0x14011b56e`
- `OLEAUT32!__imp_SysFreeString` at `0x14011b3d2`
- `OLEAUT32!__imp_SysFreeString` at `0x14011b3d2`

## pseudocode

```c
__int64 __fastcall BlbDeleteStagingDirectories(struct CBlbEngine *a1)
{
  unsigned __int16 *v2; // rsi
  unsigned __int16 *v3; // r14
  unsigned __int16 *v4; // rdi
  int v5; // ebx
  PVOID *v6; // rcx
  unsigned int i; // r13d
  unsigned __int64 v8; // r15
  unsigned int v9; // r12d
  ATL::CComBSTR *v10; // rax
  int v11; // r15d
  __int64 v12; // r9
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  int appended; // eax
  int IsDirectory; // eax
  unsigned int v18; // edx
  unsigned __int8 *v19; // r8
  struct IBlbutilDeleteCallback *v20; // r9
  int v21; // eax
  unsigned __int16 *v23; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 *v24; // [rsp+38h] [rbp-30h] BYREF
  struct _BLB_VOLUME_INFO *v25; // [rsp+40h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-20h] BYREF
  struct _GUID v27; // [rsp+50h] [rbp-18h] BYREF
  unsigned __int8 v28; // [rsp+B0h] [rbp+48h] BYREF
  unsigned int v29; // [rsp+B8h] [rbp+50h]
  unsigned int v30; // [rsp+C0h] [rbp+58h] BYREF
  unsigned __int16 *v31; // [rsp+C8h] [rbp+60h] BYREF

  v29 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_fb2577b883a235482d9189780eae0983_Traceguids);
  }
  v2 = 0;
  v25 = 0;
  v3 = 0;
  v30 = 0;
  v4 = 0;
  v24 = 0;
  v23 = 0;
  v31 = 0;
  if ( !a1 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbsystemstateutils.cpp", 0x14Bu, "pEngine != NULL");
  v5 = (*(__int64 (__fastcall **)(struct CBlbEngine *, unsigned int *, struct _BLB_VOLUME_INFO **))(*(_QWORD *)a1 + 64LL))(
         a1,
         &v30,
         &v25);
  if ( v5 >= 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_fb2577b883a235482d9189780eae0983_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    for ( i = 0; i < v30; ++i )
    {
      v8 = (unsigned __int64)i << 7;
      v28 = 0;
      v9 = *(_DWORD *)((char *)v25 + v8 + 88);
      v27 = *(struct _GUID *)((char *)v25 + v8);
      if ( v4 )
      {
        CoTaskMemFree(v4);
        v6 = (PVOID *)WPP_GLOBAL_Control;
        v4 = 0;
        v31 = 0;
      }
      if ( v2 )
      {
        CoTaskMemFree(v2);
        v6 = (PVOID *)WPP_GLOBAL_Control;
        v2 = 0;
        v24 = 0;
      }
      if ( v3 )
      {
        CoTaskMemFree(v3);
        v6 = (PVOID *)WPP_GLOBAL_Control;
        v3 = 0;
        v23 = 0;
      }
      if ( (v9 & 1) == 0 )
      {
        if ( *((_BYTE *)v25 + v8 + 85) )
        {
          v14 = BlbutilQueryVolumeName(&v27, v9, &v24, 0);
          v2 = v24;
          v5 = v14;
          if ( v14 < 0 )
            break;
          v15 = BlbutilSlashTerminatePath(v24, (LPVOID *)&v23);
          v3 = v23;
          v5 = v15;
          if ( v15 < 0 )
            break;
          appended = BlbutilAppendString(v23, L"System Volume Information\\SystemStateRestore", &v31);
          v4 = v31;
          v5 = appended;
          if ( appended < 0 )
            break;
          IsDirectory = BlbutilIsDirectory(v31, &v28);
          v5 = IsDirectory;
          if ( IsDirectory >= 0 )
          {
            if ( v28 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_fb2577b883a235482d9189780eae0983_Traceguids, v4);
              }
              v21 = BlbutilDeleteDirectory(v4, v18, v19, v20);
              v5 = v21;
              if ( v21 < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    28,
                    (unsigned int)&WPP_fb2577b883a235482d9189780eae0983_Traceguids,
                    (_DWORD)v4,
                    v21);
                }
                break;
              }
            }
            v6 = (PVOID *)WPP_GLOBAL_Control;
          }
          else
          {
            if ( (unsigned int)(IsDirectory + 2147024894) > 1 )
              break;
            v6 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_fb2577b883a235482d9189780eae0983_Traceguids, v4);
              v6 = (PVOID *)WPP_GLOBAL_Control;
            }
            v5 = 0;
          }
        }
        else
        {
          if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 1) == 0 || *((_BYTE *)v6 + 25) < 4u )
          {
            v11 = v29;
          }
          else
          {
            v10 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, (const struct _GUID *)((char *)v25 + v8));
            v11 = v29 | 1;
            v12 = *(_QWORD *)v10;
            v13 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            v29 |= 1u;
            WPP_SF_S(v13, 25, &WPP_fb2577b883a235482d9189780eae0983_Traceguids, v12);
            v6 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( (v11 & 1) != 0 )
          {
            v29 = v11 & 0xFFFFFFFE;
            SysFreeString(bstrString);
            v6 = (PVOID *)WPP_GLOBAL_Control;
          }
        }
      }
    }
    if ( v4 )
      CoTaskMemFree(v4);
    if ( v2 )
      CoTaskMemFree(v2);
    if ( v3 )
      CoTaskMemFree(v3);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_fb2577b883a235482d9189780eae0983_Traceguids);
  }
  FreeVolumes(&v25, &v30);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_fb2577b883a235482d9189780eae0983_Traceguids);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14011b1a8  push    rbp
0x14011b1aa  push    rbx
0x14011b1ab  push    rsi
0x14011b1ac  push    rdi
0x14011b1ad  push    r12
0x14011b1af  push    r13
0x14011b1b1  push    r14
0x14011b1b3  push    r15
0x14011b1b5  mov     rbp, rsp
0x14011b1b8  sub     rsp, 68h
0x14011b1bc  xor     r15d, r15d
0x14011b1bf  mov     rbx, rcx
0x14011b1c2  mov     [rbp+arg_8], r15d
0x14011b1c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14011b1cd  lea     r15, WPP_GLOBAL_Control
0x14011b1d4  cmp     rcx, r15
0x14011b1d7  jz      short loc_14011B1FA
0x14011b1d9  test    byte ptr [rcx+1Ch], 1
0x14011b1dd  jz      short loc_14011B1FA
0x14011b1df  cmp     byte ptr [rcx+19h], 4
0x14011b1e3  jb      short loc_14011B1FA
0x14011b1e5  mov     rcx, [rcx+10h]
0x14011b1e9  lea     r8, WPP_fb2577b883a235482d9189780eae0983_Traceguids
0x14011b1f0  mov     edx, 16h
0x14011b1f5  call    WPP_SF_
0x14011b1fa  xor     esi, esi
0x14011b1fc  mov     [rbp+var_28], 0
0x14011b204  xor     r14d, r14d
0x14011b207  mov     [rbp+arg_10], 0
0x14011b20e  xor     edi, edi
0x14011b210  mov     [rbp+var_30], rsi
0x14011b214  mov     [rbp+var_38], r14
0x14011b218  mov     [rbp+arg_18], rdi
0x14011b21c  test    rbx, rbx
0x14011b21f  jnz     short loc_14011B239
0x14011b221  lea     r8, aPengineNull; "pEngine != NULL"
0x14011b228  mov     edx, 14Bh; unsigned int
0x14011b22d  lea     rcx, aBaseStorBlbEng_3; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x14011b234  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14011b239  mov     rax, [rbx]
0x14011b23c  lea     r8, [rbp+var_28]
0x14011b240  lea     rdx, [rbp+arg_10]
0x14011b244  mov     rcx, rbx
0x14011b247  mov     rax, [rax+40h]
0x14011b24b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011b250  mov     ebx, eax
0x14011b252  test    eax, eax
0x14011b254  jns     short loc_14011B297
0x14011b256  mov     rcx, cs:WPP_GLOBAL_Control
0x14011b25d  cmp     rcx, r15
0x14011b260  jz      loc_14011B574
0x14011b266  test    byte ptr [rcx+1Ch], 1
0x14011b26a  jz      loc_14011B574
0x14011b270  cmp     byte ptr [rcx+19h], 2
0x14011b274  jb      loc_14011B574
0x14011b27a  mov     rcx, [rcx+10h]
0x14011b27e  lea     r8, WPP_fb2577b883a235482d9189780eae0983_Traceguids
0x14011b285  mov     edx, 17h
0x14011b28a  mov     r9d, eax
0x14011b28d  call    WPP_SF_d
0x14011b292  jmp     loc_14011B574
0x14011b297  mov     rcx, cs:WPP_GLOBAL_Control
0x14011b29e  cmp     rcx, r15
0x14011b2a1  jz      short loc_14011B2CF
0x14011b2a3  test    byte ptr [rcx+1Ch], 1
0x14011b2a7  jz      short loc_14011B2CF
0x14011b2a9  cmp     byte ptr [rcx+19h], 4
0x14011b2ad  jb      short loc_14011B2CF
0x14011b2af  mov     r9d, [rbp+arg_10]
0x14011b2b3  lea     r8, WPP_fb2577b883a235482d9189780eae0983_Traceguids
0x14011b2ba  mov     rcx, [rcx+10h]
0x14011b2be  mov     edx, 18h
0x14011b2c3  call    WPP_SF_d
0x14011b2c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14011b2cf  xor     r13d, r13d
0x14011b2d2  cmp     r13d, [rbp+arg_10]
0x14011b2d6  jnb     loc_14011B54A
0x14011b2dc  mov     rax, [rbp+var_28]
0x14011b2e0  mov     r15d, r13d
0x14011b2e3  shl     r15, 7
0x14011b2e7  mov     [rbp+arg_0], 0
0x14011b2eb  mov     r12d, [r15+rax+58h]
0x14011b2f0  movups  xmm0, xmmword ptr [r15+rax]
0x14011b2f5  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x14011b2fa  test    rdi, rdi
0x14011b2fd  jz      short loc_14011B315
0x14011b2ff  mov     rcx, rdi; pv
0x14011b302  call    cs:__imp_CoTaskMemFree
0x14011b308  mov     rcx, cs:WPP_GLOBAL_Control
0x14011b30f  xor     edi, edi
0x14011b311  mov     [rbp+arg_18], rdi
0x14011b315  test    rsi, rsi
0x14011b318  jz      short loc_14011B330
0x14011b31a  mov     rcx, rsi; pv
0x14011b31d  call    cs:__imp_CoTaskMemFree
0x14011b323  mov     rcx, cs:WPP_GLOBAL_Control
0x14011b32a  xor     esi, esi
0x14011b32c  mov     [rbp+var_30], rsi
0x14011b330  test    r14, r14
0x14011b333  jz      short loc_14011B34C
0x14011b335  mov     rcx, r14; pv
0x14011b338  call    cs:__imp_CoTaskMemFree
0x14011b33e  mov     rcx, cs:WPP_GLOBAL_Control
0x14011b345  xor     r14d, r14d
0x14011b348  mov     [rbp+var_38], r14
0x14011b34c  test    r12b, 1
0x14011b350  jnz     loc_14011B3DF
0x14011b356  mov     rdx, [rbp+var_28]
0x14011b35a  add     rdx, r15; struct _GUID *
0x14011b35d  cmp     byte ptr [rdx+55h], 0
0x14011b361  jnz     loc_14011B3EE
0x14011b367  lea     rax, WPP_GLOBAL_Control
0x14011b36e  cmp     rcx, rax
0x14011b371  jz      short loc_14011B3BC
0x14011b373  test    byte ptr [rcx+1Ch], 1
0x14011b377  jz      short loc_14011B3BC
0x14011b379  cmp     byte ptr [rcx+19h], 4
0x14011b37d  jb      short loc_14011B3BC
0x14011b37f  lea     rcx, [rbp+bstrString]; this
0x14011b383  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x14011b388  mov     rcx, cs:WPP_GLOBAL_Control
0x14011b38f  lea     r8, WPP_fb2577b883a235482d9189780eae0983_Traceguids
0x14011b396  mov     r15d, [rbp+arg_8]
0x14011b39a  mov     edx, 19h
0x14011b39f  or      r15d, 1
0x14011b3a3  mov     r9, [rax]
0x14011b3a6  mov     rcx, [rcx+10h]
0x14011b3aa  mov     [rbp+arg_8], r15d
0x14011b3ae  call    WPP_SF_S
0x14011b3b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14011b3ba  jmp     short loc_14011B3C0
0x14011b3bc  mov     r15d, [rbp+arg_8]
0x14011b3c0  test    r15b, 1
0x14011b3c4  jz      short loc_14011B3DF
0x14011b3c6  mov     rcx, [rbp+bstrString]; bstrString
0x14011b3ca  and     r15d, 0FFFFFFFEh
0x14011b3ce  mov     [rbp+arg_8], r15d
0x14011b3d2  call    cs:__imp_SysFreeString
0x14011b3d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14011b3df  lea     r15, WPP_GLOBAL_Control
0x14011b3e6  inc     r13d
0x14011b3e9  jmp     loc_14011B2D2
0x14011b3ee  xor     r9d, r9d; unsigned __int8
0x14011b3f1  lea     r8, [rbp+var_30]; unsigned __int16 **
0x14011b3f5  mov     edx, r12d; unsigned int
0x14011b3f8  lea     rcx, [rbp+var_18]; struct _GUID *
0x14011b3fc  call    ?BlbutilQueryVolumeName@@YAJPEAU_GUID@@KPEAPEAGE@Z; BlbutilQueryVolumeName(_GUID *,ulong,ushort * *,uchar)
0x14011b401  mov     rsi, [rbp+var_30]
0x14011b405  mov     ebx, eax
0x14011b407  test    eax, eax
0x14011b409  js      loc_14011B543
0x14011b40f  lea     rdx, [rbp+var_38]; unsigned __int16 **
0x14011b413  mov     rcx, rsi; unsigned __int16 *
0x14011b416  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x14011b41b  mov     r14, [rbp+var_38]
0x14011b41f  mov     ebx, eax
0x14011b421  test    eax, eax
0x14011b423  js      loc_14011B543
0x14011b429  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x14011b42d  mov     rcx, r14; unsigned __int16 *
0x14011b430  lea     rdx, aSystemVolumeIn_2; "System Volume Information\\SystemStateR"...
0x14011b437  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x14011b43c  mov     rdi, [rbp+arg_18]
0x14011b440  mov     ebx, eax
0x14011b442  test    eax, eax
0x14011b444  js      loc_14011B543
0x14011b44a  lea     rdx, [rbp+arg_0]; unsigned __int8 *
0x14011b44e  mov     rcx, rdi; unsigned __int16 *
0x14011b451  call    ?BlbutilIsDirectory@@YAJPEAGPEAE@Z; BlbutilIsDirectory(ushort *,uchar *)
0x14011b456  mov     ebx, eax
0x14011b458  test    eax, eax
0x14011b45a  jns     short loc_14011B4AF
0x14011b45c  add     eax, 7FF8FFFEh
0x14011b461  cmp     eax, 1
0x14011b464  ja      loc_14011B543
0x14011b46a  mov     rcx, cs:WPP_GLOBAL_Control
0x14011b471  lea     r15, WPP_GLOBAL_Control
0x14011b478  cmp     rcx, r15
0x14011b47b  jz      short loc_14011B4A8
0x14011b47d  test    byte ptr [rcx+1Ch], 1
0x14011b481  jz      short loc_14011B4A8
0x14011b483  cmp     byte ptr [rcx+19h], 4
0x14011b487  jb      short loc_14011B4A8
0x14011b489  mov     rcx, [rcx+10h]
0x14011b48d  lea     r8, WPP_fb2577b883a235482d9189780eae0983_Traceguids
0x14011b494  mov     edx, 1Ah
0x14011b499  mov     r9, rdi
0x14011b49c  call    WPP_SF_S
0x14011b4a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14011b4a8  xor     ebx, ebx
0x14011b4aa  jmp     loc_14011B3E6
0x14011b4af  cmp     [rbp+arg_0], 0
0x14011b4b3  jz      short loc_14011B530
0x14011b4b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14011b4bc  lea     r15, WPP_GLOBAL_Control
0x14011b4c3  cmp     rcx, r15
0x14011b4c6  jz      short loc_14011B4EC
0x14011b4c8  test    byte ptr [rcx+1Ch], 1
0x14011b4cc  jz      short loc_14011B4EC
0x14011b4ce  cmp     byte ptr [rcx+19h], 4
0x14011b4d2  jb      short loc_14011B4EC
0x14011b4d4  mov     rcx, [rcx+10h]
0x14011b4d8  lea     r8, WPP_fb2577b883a235482d9189780eae0983_Traceguids
0x14011b4df  mov     edx, 1Bh
0x14011b4e4  mov     r9, rdi
0x14011b4e7  call    WPP_SF_S
0x14011b4ec  mov     rcx, rdi; unsigned __int16 *
0x14011b4ef  call    ?BlbutilDeleteDirectory@@YAJPEAGKPEAEPEAUIBlbutilDeleteCallback@@@Z; BlbutilDeleteDirectory(ushort *,ulong,uchar *,IBlbutilDeleteCallback *)
0x14011b4f4  mov     ebx, eax
0x14011b4f6  test    eax, eax
0x14011b4f8  jns     short loc_14011B537
0x14011b4fa  mov     rcx, cs:WPP_GLOBAL_Control
0x14011b501  cmp     rcx, r15
0x14011b504  jz      short loc_14011B54A
0x14011b506  test    byte ptr [rcx+1Ch], 1
0x14011b50a  jz      short loc_14011B54A
0x14011b50c  cmp     byte ptr [rcx+19h], 2
0x14011b510  jb      short loc_14011B54A
0x14011b512  mov     rcx, [rcx+10h]
0x14011b516  lea     r8, WPP_fb2577b883a235482d9189780eae0983_Traceguids
0x14011b51d  mov     edx, 1Ch
0x14011b522  mov     [rsp+68h+var_48], eax
0x14011b526  mov     r9, rdi
0x14011b529  call    WPP_SF_Sd
0x14011b52e  jmp     short loc_14011B54A
0x14011b530  lea     r15, WPP_GLOBAL_Control
0x14011b537  mov     rcx, cs:WPP_GLOBAL_Control
0x14011b53e  jmp     loc_14011B3E6
0x14011b543  lea     r15, WPP_GLOBAL_Control
0x14011b54a  test    rdi, rdi
0x14011b54d  jz      short loc_14011B558
0x14011b54f  mov     rcx, rdi; pv
0x14011b552  call    cs:__imp_CoTaskMemFree
0x14011b558  test    rsi, rsi
0x14011b55b  jz      short loc_14011B566
0x14011b55d  mov     rcx, rsi; pv
0x14011b560  call    cs:__imp_CoTaskMemFree
0x14011b566  test    r14, r14
0x14011b569  jz      short loc_14011B574
0x14011b56b  mov     rcx, r14; pv
0x14011b56e  call    cs:__imp_CoTaskMemFree
0x14011b574  lea     rdx, [rbp+arg_10]; unsigned int *
0x14011b578  lea     rcx, [rbp+var_28]; struct _BLB_VOLUME_INFO **
0x14011b57c  call    ?FreeVolumes@@YAXAEAPEAU_BLB_VOLUME_INFO@@AEAK@Z; FreeVolumes(_BLB_VOLUME_INFO * &,ulong &)
0x14011b581  mov     rcx, cs:WPP_GLOBAL_Control
0x14011b588  cmp     rcx, r15
0x14011b58b  jz      short loc_14011B5AE
0x14011b58d  test    byte ptr [rcx+1Ch], 1
0x14011b591  jz      short loc_14011B5AE
0x14011b593  cmp     byte ptr [rcx+19h], 4
0x14011b597  jb      short loc_14011B5AE
0x14011b599  mov     rcx, [rcx+10h]
0x14011b59d  lea     r8, WPP_fb2577b883a235482d9189780eae0983_Traceguids
0x14011b5a4  mov     edx, 1Dh
0x14011b5a9  call    WPP_SF_
0x14011b5ae  mov     eax, ebx
0x14011b5b0  add     rsp, 68h
0x14011b5b4  pop     r15
0x14011b5b6  pop     r14
0x14011b5b8  pop     r13
0x14011b5ba  pop     r12
0x14011b5bc  pop     rdi
0x14011b5bd  pop     rsi
0x14011b5be  pop     rbx
0x14011b5bf  pop     rbp
0x14011b5c0  retn
```

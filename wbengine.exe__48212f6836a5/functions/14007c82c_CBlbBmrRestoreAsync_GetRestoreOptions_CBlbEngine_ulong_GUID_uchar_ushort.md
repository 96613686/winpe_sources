# CBlbBmrRestoreAsync::GetRestoreOptions(CBlbEngine *,ulong,_GUID *,uchar,ushort * *)

- ea: `0x14007c82c`
- end: `0x14007ce4f`
- name: `?GetRestoreOptions@CBlbBmrRestoreAsync@@AEAAJPEAVCBlbEngine@@KPEAU_GUID@@EPEAPEAG@Z`
- size: `1571`
- prototype: `int(CBlbBmrRestoreAsync *__hidden this, struct CBlbEngine *, unsigned int, struct _GUID *, unsigned __int8, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task`

## callers

- `0x14007df90`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x1400142d8`
- `0x14007bf00`
- `0x14007c430`
- `0x14007c6b8`
- `0x14007c82c`
- `0x14008863c`
- `0x1400889f0`
- `0x14008adb8`
- `0x140092d9c`
- `0x14012dbcc`
- `0x14012e138`
- `0x14012e680`
- `0x140137010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14007cad0`
- `msvcrt!_wcsicmp` at `0x14007cad0`
- `ole32!CoTaskMemFree` at `0x14007ca7c`
- `ole32!CoTaskMemFree` at `0x14007cbaa`
- `ole32!CoTaskMemFree` at `0x14007cbb3`
- `ole32!CoTaskMemFree` at `0x14007cbc4`
- `ole32!CoTaskMemFree` at `0x14007cd6a`
- `ole32!CoTaskMemFree` at `0x14007cd7c`
- `ole32!CoTaskMemFree` at `0x14007cd8a`
- `ole32!CoTaskMemFree` at `0x14007cd98`
- `ole32!CoTaskMemFree` at `0x14007cdaa`
- `ole32!CoTaskMemFree` at `0x14007cdb8`
- `ole32!CoTaskMemFree` at `0x14007cdca`
- `ole32!CoTaskMemFree` at `0x14007ca7c`
- `ole32!CoTaskMemFree` at `0x14007cbaa`
- `ole32!CoTaskMemFree` at `0x14007cbb3`
- `ole32!CoTaskMemFree` at `0x14007cbc4`
- `ole32!CoTaskMemFree` at `0x14007cd6a`
- `ole32!CoTaskMemFree` at `0x14007cd7c`
- `ole32!CoTaskMemFree` at `0x14007cd8a`
- `ole32!CoTaskMemFree` at `0x14007cd98`
- `ole32!CoTaskMemFree` at `0x14007cdaa`
- `ole32!CoTaskMemFree` at `0x14007cdb8`
- `ole32!CoTaskMemFree` at `0x14007cdca`

## string_xrefs

- `0x14007ca03`: `base\stor\blb\engine\service\bmr.cpp`
- `0x14007ca56`: `base\stor\blb\engine\service\bmr.cpp`

## pseudocode

```c
__int64 __fastcall CBlbBmrRestoreAsync::GetRestoreOptions(
        const unsigned __int16 **this,
        struct CBlbEngine *a2,
        unsigned int a3,
        struct _GUID *a4,
        unsigned __int8 a5,
        unsigned __int16 **a6)
{
  __int64 v9; // rax
  unsigned __int16 *v10; // r12
  unsigned __int16 *v11; // r14
  __int64 (__fastcall *v12)(struct CBlbEngine *, unsigned int *, struct _BLB_DISK_INFO **); // rax
  int ExcludeDisksInfo; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  unsigned __int16 **v16; // rdi
  __int64 i; // r13
  char *v18; // rsi
  __int64 v19; // rdi
  __int64 j; // r15
  struct _BLB_TARGET_INFO *v21; // rdi
  __int64 v22; // rbx
  unsigned __int16 *v23; // rdi
  unsigned __int16 *v24; // r12
  int BootVolume; // eax
  unsigned __int16 *v26; // rsi
  unsigned int v28; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v29; // [rsp+34h] [rbp-45h] BYREF
  unsigned __int16 *v30; // [rsp+38h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int16 *v32; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v33; // [rsp+50h] [rbp-29h] BYREF
  struct _BLB_DISK_INFO *v34; // [rsp+58h] [rbp-21h] BYREF
  struct _BLB_BACKUP_SET_INFO *v35; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int8 *v36; // [rsp+68h] [rbp-11h] BYREF
  struct _BLB_TARGET_INFO *v37; // [rsp+70h] [rbp-9h] BYREF
  unsigned __int16 *v38; // [rsp+78h] [rbp-1h] BYREF
  struct _GUID v39; // [rsp+80h] [rbp+7h] BYREF
  unsigned int v41; // [rsp+D8h] [rbp+5Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
  }
  v9 = *(_QWORD *)a2;
  v10 = 0;
  v36 = 0;
  v11 = 0;
  v41 = 0;
  v12 = *(__int64 (__fastcall **)(struct CBlbEngine *, unsigned int *, struct _BLB_DISK_INFO **))(v9 + 96);
  v29 = 0;
  v34 = 0;
  v37 = 0;
  v35 = 0;
  v38 = 0;
  v39 = GUID_NULL;
  pv = 0;
  v32 = 0;
  v30 = 0;
  v33 = 0;
  ExcludeDisksInfo = v12(a2, &v41, &v34);
  if ( ExcludeDisksInfo >= 0 )
  {
    ExcludeDisksInfo = (*(__int64 (__fastcall **)(struct CBlbEngine *, unsigned int *, struct _BLB_TARGET_INFO **))(*(_QWORD *)a2 + 72LL))(
                         a2,
                         &v29,
                         &v37);
    if ( ExcludeDisksInfo >= 0 )
    {
      ExcludeDisksInfo = GetExcludeDisksInfo(a3, a4, v41, v34, &v36);
      if ( ExcludeDisksInfo >= 0 )
      {
        v16 = a6;
        if ( !a6 )
          BlbAssert("base\\stor\\blb\\engine\\service\\bmr.cpp", 0x534u, "pwszRestoreOptions");
        *v16 = 0;
        for ( i = 0; (unsigned int)i < v41; i = (unsigned int)(i + 1) )
        {
          v18 = (char *)v34 + 112 * (unsigned int)i;
          if ( *((_DWORD *)v18 + 17) && v36[i] == 1 )
          {
            if ( v18[64] )
              BlbAssert(
                "base\\stor\\blb\\engine\\service\\bmr.cpp",
                0x53Cu,
                "pDisk->m_bVolumeInformationUnavailable == FALSE");
            v19 = 0;
LABEL_30:
            v28 = v19;
            if ( (unsigned int)v19 < *((_DWORD *)v18 + 17) )
            {
              if ( pv )
              {
                CoTaskMemFree(pv);
                pv = 0;
              }
              ExcludeDisksInfo = BlbutilGetVolumeTargetNameFromAccessPath(
                                   (struct _GUID *)(*((_QWORD *)v18 + 9) + 16LL * (unsigned int)v19),
                                   *(_DWORD *)(*((_QWORD *)v18 + 10) + 4 * v19),
                                   (unsigned __int16 **)&pv);
              if ( ExcludeDisksInfo < 0 )
              {
LABEL_47:
                v23 = 0;
                goto LABEL_81;
              }
              for ( j = 0; ; j = (unsigned int)(j + 1) )
              {
                if ( (unsigned int)j >= v29 )
                {
                  v19 = v28 + 1;
                  goto LABEL_30;
                }
                v21 = v37;
                v22 = 96 * j;
                if ( !_wcsicmp(*((const wchar_t **)v37 + 12 * j + 2), (const wchar_t *)pv) )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                  {
                    WPP_SF_SS(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      83,
                      (unsigned int)&WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids,
                      *(_QWORD *)((char *)v21 + v22 + 24),
                      *(_QWORD *)((char *)v21 + v22 + 16));
                  }
                  ExcludeDisksInfo = BlbutilGetRestoreOptions(*(unsigned __int16 **)((char *)v21 + v22 + 16), &v32);
                  if ( ExcludeDisksInfo < 0 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        84,
                        &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
                    }
                    v11 = v32;
                    v23 = 0;
                    goto LABEL_81;
                  }
                  v11 = v32;
                }
                if ( v11 )
                {
                  if ( v10 )
                  {
                    v23 = v10;
                    ExcludeDisksInfo = BlbutilAppendString(v10, L",", &v33);
                    if ( ExcludeDisksInfo < 0 )
                      goto LABEL_81;
                    v24 = v33;
                    ExcludeDisksInfo = BlbutilAppendString(v33, v11, &v30);
                    if ( ExcludeDisksInfo < 0 )
                    {
                      v10 = v30;
                      goto LABEL_81;
                    }
                    CoTaskMemFree(v23);
                    CoTaskMemFree(v24);
                    v33 = 0;
                  }
                  else
                  {
                    ExcludeDisksInfo = BlbutilDuplicateString(v11, &v30, 0);
                    if ( ExcludeDisksInfo < 0 )
                    {
                      v10 = v30;
                      goto LABEL_47;
                    }
                  }
                  CoTaskMemFree(v11);
                  v10 = v30;
                  v11 = 0;
                  v32 = 0;
                }
              }
            }
          }
        }
        ExcludeDisksInfo = (*((__int64 (__fastcall **)(const unsigned __int16 **, struct _BLB_BACKUP_SET_INFO **))*this
                            + 7))(
                             this,
                             &v35);
        if ( ExcludeDisksInfo >= 0 )
        {
          BootVolume = CBlbBmrRestoreAsync::GetBootVolume((CBlbBmrRestoreAsync *)this, v35, &v39, &v38);
          v26 = v38;
          ExcludeDisksInfo = BootVolume;
          if ( BootVolume >= 0 )
          {
            v23 = 0;
            ExcludeDisksInfo = AddASRRestoreOptions(v10, a5, *((_BYTE *)this + 464) == 0, v38, this[57], a6);
            if ( ExcludeDisksInfo < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
            }
            v23 = 0;
          }
          if ( v26 )
            CoTaskMemFree(v26);
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
          }
          v23 = 0;
        }
LABEL_81:
        if ( pv )
          CoTaskMemFree(pv);
        if ( v10 )
          CoTaskMemFree(v10);
        if ( v23 )
          CoTaskMemFree(v23);
        if ( v33 )
          CoTaskMemFree(v33);
        if ( v11 )
          CoTaskMemFree(v11);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
      }
      if ( v36 )
        CoTaskMemFree(v36);
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = 81;
        goto LABEL_10;
      }
    }
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 80;
LABEL_10:
      WPP_SF_d(v14[2], v15, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
    }
  }
  FreeTargets(&v37, &v29);
  FreeDisks(&v34, &v41);
  if ( v35 )
  {
    v28 = 1;
    FreeBackupSets(&v35, &v28);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
  }
  return (unsigned int)ExcludeDisksInfo;
}

```

## disassembly

```asm
0x14007c82c  mov     [rsp-8+arg_10], rbx
0x14007c831  mov     [rsp-8+arg_0], rcx
0x14007c836  push    rbp
0x14007c837  push    rsi
0x14007c838  push    rdi
0x14007c839  push    r12
0x14007c83b  push    r13
0x14007c83d  push    r14
0x14007c83f  push    r15
0x14007c841  lea     rbp, [rsp-17h]
0x14007c846  sub     rsp, 90h
0x14007c84d  mov     rsi, r9
0x14007c850  mov     r15d, r8d
0x14007c853  mov     rdi, rdx
0x14007c856  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c85d  lea     r13, WPP_GLOBAL_Control
0x14007c864  cmp     rcx, r13
0x14007c867  jz      short loc_14007C88A
0x14007c869  test    byte ptr [rcx+1Ch], 1
0x14007c86d  jz      short loc_14007C88A
0x14007c86f  cmp     byte ptr [rcx+19h], 4
0x14007c873  jb      short loc_14007C88A
0x14007c875  mov     rcx, [rcx+10h]
0x14007c879  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007c880  mov     edx, 4Fh ; 'O'
0x14007c885  call    WPP_SF_
0x14007c88a  mov     rax, [rdi]
0x14007c88d  lea     r8, [rbp+47h+var_68]
0x14007c891  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14007c898  xor     r12d, r12d
0x14007c89b  mov     [rbp+47h+var_58], 0
0x14007c8a3  xor     r14d, r14d
0x14007c8a6  mov     [rbp+47h+arg_8], 0
0x14007c8ad  mov     rax, [rax+60h]
0x14007c8b1  lea     rdx, [rbp+47h+arg_8]
0x14007c8b5  mov     rcx, rdi
0x14007c8b8  mov     [rbp+47h+var_8C], 0
0x14007c8bf  mov     [rbp+47h+var_68], 0
0x14007c8c7  mov     [rbp+47h+var_50], 0
0x14007c8cf  mov     [rbp+47h+var_60], 0
0x14007c8d7  mov     [rbp+47h+var_48], 0
0x14007c8df  movdqu  xmmword ptr [rbp+47h+var_40.Data1], xmm0
0x14007c8e4  mov     [rbp+47h+pv], 0
0x14007c8ec  mov     [rbp+47h+var_78], r14
0x14007c8f0  mov     [rbp+47h+var_88], r12
0x14007c8f4  mov     [rbp+47h+var_70], r12
0x14007c8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c8fd  mov     ebx, eax
0x14007c8ff  test    eax, eax
0x14007c901  jns     short loc_14007C943
0x14007c903  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c90a  cmp     rcx, r13
0x14007c90d  jz      loc_14007CDD0
0x14007c913  test    byte ptr [rcx+1Ch], 1
0x14007c917  jz      loc_14007CDD0
0x14007c91d  cmp     byte ptr [rcx+19h], 2
0x14007c921  jb      loc_14007CDD0
0x14007c927  lea     edx, [r14+50h]
0x14007c92b  mov     rcx, [rcx+10h]
0x14007c92f  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007c936  mov     r9d, eax
0x14007c939  call    WPP_SF_d
0x14007c93e  jmp     loc_14007CDD0
0x14007c943  mov     rax, [rdi]
0x14007c946  lea     r8, [rbp+47h+var_50]
0x14007c94a  lea     rdx, [rbp+47h+var_8C]
0x14007c94e  mov     rcx, rdi
0x14007c951  mov     rax, [rax+48h]
0x14007c955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c95a  mov     ebx, eax
0x14007c95c  test    eax, eax
0x14007c95e  jns     short loc_14007C98B
0x14007c960  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c967  cmp     rcx, r13
0x14007c96a  jz      loc_14007CDD0
0x14007c970  test    byte ptr [rcx+1Ch], 1
0x14007c974  jz      loc_14007CDD0
0x14007c97a  cmp     byte ptr [rcx+19h], 2
0x14007c97e  jb      loc_14007CDD0
0x14007c984  mov     edx, 51h ; 'Q'
0x14007c989  jmp     short loc_14007C92B
0x14007c98b  mov     r9, [rbp+47h+var_68]; struct _BLB_DISK_INFO *
0x14007c98f  lea     rax, [rbp+47h+var_58]
0x14007c993  mov     r8d, [rbp+47h+arg_8]; unsigned int
0x14007c997  mov     rdx, rsi; struct _GUID *
0x14007c99a  mov     ecx, r15d; unsigned int
0x14007c99d  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 **
0x14007c9a2  call    ?GetExcludeDisksInfo@@YAJKPEAU_GUID@@KPEAU_BLB_DISK_INFO@@PEAPEAE@Z; GetExcludeDisksInfo(ulong,_GUID *,ulong,_BLB_DISK_INFO *,uchar * *)
0x14007c9a7  mov     ebx, eax
0x14007c9a9  test    eax, eax
0x14007c9ab  jns     short loc_14007C9EE
0x14007c9ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c9b4  cmp     rcx, r13
0x14007c9b7  jz      loc_14007CDBE
0x14007c9bd  test    byte ptr [rcx+1Ch], 1
0x14007c9c1  jz      loc_14007CDBE
0x14007c9c7  cmp     byte ptr [rcx+19h], 2
0x14007c9cb  jb      loc_14007CDBE
0x14007c9d1  mov     rcx, [rcx+10h]
0x14007c9d5  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007c9dc  mov     edx, 52h ; 'R'
0x14007c9e1  mov     r9d, eax
0x14007c9e4  call    WPP_SF_d
0x14007c9e9  jmp     loc_14007CDBE
0x14007c9ee  mov     rdi, [rbp+47h+arg_28]
0x14007c9f2  test    rdi, rdi
0x14007c9f5  jnz     short loc_14007CA0F
0x14007c9f7  lea     r8, aPwszrestoreopt; "pwszRestoreOptions"
0x14007c9fe  mov     edx, 534h; unsigned int
0x14007ca03  lea     rcx, aBaseStorBlbEng_10; "base\\stor\\blb\\engine\\service\\bmr.c"...
0x14007ca0a  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14007ca0f  mov     [rdi], r12
0x14007ca12  xor     r13d, r13d
0x14007ca15  cmp     r13d, [rbp+47h+arg_8]
0x14007ca19  jnb     loc_14007CC3A
0x14007ca1f  mov     eax, r13d
0x14007ca22  imul    rsi, rax, 70h ; 'p'
0x14007ca26  add     rsi, [rbp+47h+var_68]
0x14007ca2a  cmp     dword ptr [rsi+44h], 0
0x14007ca2e  jz      loc_14007CBE7
0x14007ca34  mov     rcx, [rbp+47h+var_58]
0x14007ca38  cmp     byte ptr [r13+rcx+0], 1
0x14007ca3e  jnz     loc_14007CBE7
0x14007ca44  cmp     byte ptr [rsi+40h], 0
0x14007ca48  jz      short loc_14007CA62
0x14007ca4a  lea     r8, aPdiskMBvolumei; "pDisk->m_bVolumeInformationUnavailable "...
0x14007ca51  mov     edx, 53Ch; unsigned int
0x14007ca56  lea     rcx, aBaseStorBlbEng_10; "base\\stor\\blb\\engine\\service\\bmr.c"...
0x14007ca5d  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14007ca62  xor     edi, edi
0x14007ca64  mov     [rbp+47h+var_90], edi
0x14007ca67  cmp     edi, [rsi+44h]
0x14007ca6a  jnb     loc_14007CBE7
0x14007ca70  mov     rax, [rbp+47h+pv]
0x14007ca74  test    rax, rax
0x14007ca77  jz      short loc_14007CA8A
0x14007ca79  mov     rcx, rax; pv
0x14007ca7c  call    cs:__imp_CoTaskMemFree
0x14007ca82  mov     [rbp+47h+pv], 0
0x14007ca8a  mov     rdx, [rsi+50h]
0x14007ca8e  lea     r8, [rbp+47h+pv]; unsigned __int16 **
0x14007ca92  mov     ecx, edi
0x14007ca94  shl     rcx, 4
0x14007ca98  add     rcx, [rsi+48h]; struct _GUID *
0x14007ca9c  mov     edx, [rdx+rdi*4]; unsigned int
0x14007ca9f  call    ?BlbutilGetVolumeTargetNameFromAccessPath@@YAJPEAU_GUID@@KPEAPEAG@Z; BlbutilGetVolumeTargetNameFromAccessPath(_GUID *,ulong,ushort * *)
0x14007caa4  mov     ebx, eax
0x14007caa6  test    eax, eax
0x14007caa8  js      loc_14007CB60
0x14007caae  xor     r15d, r15d
0x14007cab1  cmp     r15d, [rbp+47h+var_8C]
0x14007cab5  jnb     loc_14007CBDD
0x14007cabb  mov     rdi, [rbp+47h+var_50]
0x14007cabf  lea     rbx, [r15+r15*2]
0x14007cac3  mov     rdx, [rbp+47h+pv]; String2
0x14007cac7  shl     rbx, 5
0x14007cacb  mov     rcx, [rbx+rdi+10h]; String1
0x14007cad0  call    cs:__imp__wcsicmp
0x14007cad6  test    eax, eax
0x14007cad8  jnz     short loc_14007CB39
0x14007cada  mov     rcx, cs:WPP_GLOBAL_Control
0x14007cae1  lea     rax, WPP_GLOBAL_Control
0x14007cae8  cmp     rcx, rax
0x14007caeb  jz      short loc_14007CB1D
0x14007caed  test    byte ptr [rcx+1Ch], 1
0x14007caf1  jz      short loc_14007CB1D
0x14007caf3  cmp     byte ptr [rcx+19h], 5
0x14007caf7  jb      short loc_14007CB1D
0x14007caf9  mov     rax, [rbx+rdi+10h]
0x14007cafe  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007cb05  mov     r9, [rbx+rdi+18h]
0x14007cb0a  mov     edx, 53h ; 'S'
0x14007cb0f  mov     rcx, [rcx+10h]
0x14007cb13  mov     [rsp+0C0h+var_A0], rax
0x14007cb18  call    WPP_SF_SS
0x14007cb1d  mov     rcx, [rbx+rdi+10h]; unsigned __int16 *
0x14007cb22  lea     rdx, [rbp+47h+var_78]; unsigned __int16 **
0x14007cb26  call    ?BlbutilGetRestoreOptions@@YAJPEAGPEAPEAG@Z; BlbutilGetRestoreOptions(ushort *,ushort * *)
0x14007cb2b  mov     ebx, eax
0x14007cb2d  test    eax, eax
0x14007cb2f  js      loc_14007CBEF
0x14007cb35  mov     r14, [rbp+47h+var_78]
0x14007cb39  test    r14, r14
0x14007cb3c  jz      loc_14007CBD5
0x14007cb42  test    r12, r12
0x14007cb45  jnz     short loc_14007CB6E
0x14007cb47  xor     r8d, r8d; unsigned __int64
0x14007cb4a  lea     rdx, [rbp+47h+var_88]; unsigned __int16 **
0x14007cb4e  mov     rcx, r14; unsigned __int16 *
0x14007cb51  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14007cb56  mov     ebx, eax
0x14007cb58  test    eax, eax
0x14007cb5a  jns     short loc_14007CBC1
0x14007cb5c  mov     r12, [rbp+47h+var_88]
0x14007cb60  xor     edi, edi
0x14007cb62  lea     r13, WPP_GLOBAL_Control
0x14007cb69  jmp     loc_14007CD70
0x14007cb6e  lea     r8, [rbp+47h+var_70]; unsigned __int16 **
0x14007cb72  mov     rcx, r12; unsigned __int16 *
0x14007cb75  lea     rdx, asc_140141918; ","
0x14007cb7c  mov     rdi, r12
0x14007cb7f  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x14007cb84  mov     ebx, eax
0x14007cb86  test    eax, eax
0x14007cb88  js      short loc_14007CB62
0x14007cb8a  mov     r12, [rbp+47h+var_70]
0x14007cb8e  lea     r8, [rbp+47h+var_88]; unsigned __int16 **
0x14007cb92  mov     rcx, r12; unsigned __int16 *
0x14007cb95  mov     rdx, r14; unsigned __int16 *
0x14007cb98  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x14007cb9d  mov     ebx, eax
0x14007cb9f  test    eax, eax
0x14007cba1  js      loc_14007CC31
0x14007cba7  mov     rcx, rdi; pv
0x14007cbaa  call    cs:__imp_CoTaskMemFree
0x14007cbb0  mov     rcx, r12; pv
0x14007cbb3  call    cs:__imp_CoTaskMemFree
0x14007cbb9  mov     [rbp+47h+var_70], 0
0x14007cbc1  mov     rcx, r14; pv
0x14007cbc4  call    cs:__imp_CoTaskMemFree
0x14007cbca  mov     r12, [rbp+47h+var_88]
0x14007cbce  xor     r14d, r14d
0x14007cbd1  mov     [rbp+47h+var_78], r14
0x14007cbd5  inc     r15d
0x14007cbd8  jmp     loc_14007CAB1
0x14007cbdd  mov     edi, [rbp+47h+var_90]
0x14007cbe0  inc     edi
0x14007cbe2  jmp     loc_14007CA64
0x14007cbe7  inc     r13d
0x14007cbea  jmp     loc_14007CA15
0x14007cbef  mov     rcx, cs:WPP_GLOBAL_Control
0x14007cbf6  lea     r13, WPP_GLOBAL_Control
0x14007cbfd  cmp     rcx, r13
0x14007cc00  jz      short loc_14007CC26
0x14007cc02  test    byte ptr [rcx+1Ch], 1
0x14007cc06  jz      short loc_14007CC26
0x14007cc08  cmp     byte ptr [rcx+19h], 2
0x14007cc0c  jb      short loc_14007CC26
0x14007cc0e  mov     rcx, [rcx+10h]
0x14007cc12  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007cc19  mov     edx, 54h ; 'T'
0x14007cc1e  mov     r9d, eax
0x14007cc21  call    WPP_SF_d
0x14007cc26  mov     r14, [rbp+47h+var_78]
0x14007cc2a  xor     edi, edi
0x14007cc2c  jmp     loc_14007CD70
0x14007cc31  mov     r12, [rbp+47h+var_88]
0x14007cc35  jmp     loc_14007CB62
0x14007cc3a  mov     rdi, [rbp+47h+arg_0]
0x14007cc3e  lea     rdx, [rbp+47h+var_60]
0x14007cc42  mov     rcx, rdi
0x14007cc45  mov     rax, [rdi]
0x14007cc48  mov     rax, [rax+38h]
0x14007cc4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007cc51  mov     ebx, eax
0x14007cc53  test    eax, eax
0x14007cc55  jns     short loc_14007CC95
0x14007cc57  mov     rcx, cs:WPP_GLOBAL_Control
0x14007cc5e  lea     r13, WPP_GLOBAL_Control
0x14007cc65  cmp     rcx, r13
0x14007cc68  jz      short loc_14007CC8E
0x14007cc6a  test    byte ptr [rcx+1Ch], 1
0x14007cc6e  jz      short loc_14007CC8E
0x14007cc70  cmp     byte ptr [rcx+19h], 2
0x14007cc74  jb      short loc_14007CC8E
0x14007cc76  mov     rcx, [rcx+10h]
0x14007cc7a  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007cc81  mov     edx, 55h ; 'U'
0x14007cc86  mov     r9d, eax
0x14007cc89  call    WPP_SF_d
0x14007cc8e  xor     edi, edi
0x14007cc90  jmp     loc_14007CD70
0x14007cc95  mov     rdx, [rbp+47h+var_60]; struct _BLB_BACKUP_SET_INFO *
0x14007cc99  lea     r9, [rbp+47h+var_48]; unsigned __int16 **
0x14007cc9d  lea     r8, [rbp+47h+var_40]; struct _GUID *
0x14007cca1  mov     rcx, rdi; this
0x14007cca4  call    ?GetBootVolume@CBlbBmrRestoreAsync@@AEAAJPEAU_BLB_BACKUP_SET_INFO@@PEAU_GUID@@PEAPEAG@Z; CBlbBmrRestoreAsync::GetBootVolume(_BLB_BACKUP_SET_INFO *,_GUID *,ushort * *)
0x14007cca9  mov     rsi, [rbp+47h+var_48]
0x14007ccad  mov     ebx, eax
0x14007ccaf  test    eax, eax
0x14007ccb1  jns     short loc_14007CCEE
0x14007ccb3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ccba  lea     r13, WPP_GLOBAL_Control
0x14007ccc1  cmp     rcx, r13
0x14007ccc4  jz      short loc_14007CCEA
0x14007ccc6  test    byte ptr [rcx+1Ch], 1
0x14007ccca  jz      short loc_14007CCEA
0x14007cccc  cmp     byte ptr [rcx+19h], 2
0x14007ccd0  jb      short loc_14007CCEA
0x14007ccd2  mov     rcx, [rcx+10h]
0x14007ccd6  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007ccdd  mov     edx, 56h ; 'V'
0x14007cce2  mov     r9d, eax
0x14007cce5  call    WPP_SF_d
0x14007ccea  xor     edi, edi
0x14007ccec  jmp     short loc_14007CD62
0x14007ccee  mov     rax, [rbp+47h+arg_28]
0x14007ccf2  mov     r9, rsi; unsigned __int16 *
0x14007ccf5  cmp     byte ptr [rdi+1D0h], 0
0x14007ccfc  mov     rcx, r12; unsigned __int16 *
  ... truncated ...
```

# CBlbBackupAsync::DoTargetSnapshot(IVssBackupComponents *,ushort * *,ulong,long *)

- ea: `0x1400230c4`
- end: `0x1400237d4`
- name: `?DoTargetSnapshot@CBlbBackupAsync@@AEAAJPEAVIVssBackupComponents@@PEAPEAGKPEAJ@Z`
- size: `1808`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this, struct IVssBackupComponents *, unsigned __int16 **, unsigned int, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140019fd0`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x1400142d8`
- `0x1400230c4`
- `0x14003c9cc`
- `0x14008863c`
- `0x14008fed0`
- `0x1400ec64c`
- `0x14011879c`
- `0x140137010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x14002331d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14002336e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14002331d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14002336e`
- `msvcrt!_wcsicmp` at `0x1400235c5`
- `msvcrt!_wcsicmp` at `0x1400235f9`
- `msvcrt!_wcsicmp` at `0x1400235c5`
- `msvcrt!_wcsicmp` at `0x1400235f9`
- `ole32!CoTaskMemFree` at `0x14002364e`
- `ole32!CoTaskMemFree` at `0x140023658`
- `ole32!CoTaskMemFree` at `0x1400236c7`
- `ole32!CoTaskMemFree` at `0x14002364e`
- `ole32!CoTaskMemFree` at `0x140023658`
- `ole32!CoTaskMemFree` at `0x1400236c7`
- `ole32!CoCreateInstance` at `0x140023469`
- `ole32!CoCreateInstance` at `0x140023469`

## string_xrefs

- `0x140023203`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400235b2`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400235db`: `base\stor\blb\engine\service\backup.cpp`
- `0x140023675`: `base\stor\blb\engine\service\backup.cpp`

## pseudocode

```c
__int64 __fastcall CBlbBackupAsync::DoTargetSnapshot(
        const unsigned __int16 **this,
        struct IVssBackupComponents *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        int *a5)
{
  int appended; // eax
  char *v10; // r14
  HRESULT IsClientSKU; // ebx
  PVOID *v12; // rcx
  __int64 v13; // rdx
  int DiffAreaSpace; // eax
  __int64 v15; // rax
  int v16; // eax
  int v17; // edx
  char v18; // di
  unsigned int i; // ebx
  int v21; // [rsp+30h] [rbp-71h] BYREF
  int v22; // [rsp+34h] [rbp-6Dh] BYREF
  __int64 v23; // [rsp+38h] [rbp-69h] BYREF
  __int64 v24; // [rsp+40h] [rbp-61h] BYREF
  __int64 v25; // [rsp+48h] [rbp-59h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-51h] BYREF
  wchar_t *String2; // [rsp+58h] [rbp-49h] BYREF
  struct _FILETIME v28; // [rsp+60h] [rbp-41h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-39h] BYREF
  __int64 v30[2]; // [rsp+70h] [rbp-31h] BYREF
  wchar_t *String1[2]; // [rsp+80h] [rbp-21h] BYREF
  wchar_t *v32[2]; // [rsp+90h] [rbp-11h]
  __int128 v33; // [rsp+A0h] [rbp-1h]
  unsigned __int8 v34; // [rsp+100h] [rbp+5Fh] BYREF

  v23 = 0;
  v22 = 0;
  String2 = 0;
  v30[0] = 0;
  SystemTimeAsFileTime = 0;
  v28 = 0;
  v34 = 0;
  ppv = 0;
  v25 = 0;
  v24 = 0;
  *(_OWORD *)String1 = 0;
  v21 = 0;
  *(_OWORD *)v32 = 0;
  v33 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 585, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  appended = BlbutilAppendString(this[43], L"\\", &String2);
  v10 = (char *)String2;
  IsClientSKU = appended;
  if ( appended < 0 )
    goto LABEL_93;
  IsClientSKU = BlbutilIsClientSKU(&v34);
  if ( IsClientSKU >= 0 )
  {
    if ( v34 && !*((_BYTE *)this + 1064) )
    {
      if ( *((_BYTE *)this + 592) )
        BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x3658u, "m_bResetTargetDiffArea == FALSE");
      DiffAreaSpace = BlbGetDiffAreaSpace(v10, 0, 0, v30, 1);
      if ( DiffAreaSpace >= 0 )
      {
        if ( !v30[0] )
          *((_BYTE *)this + 592) = 1;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            587,
            (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
            (_DWORD)v10,
            DiffAreaSpace);
        }
        *((_BYTE *)this + 592) = 0;
      }
    }
    IsClientSKU = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, __int64 *))(*(_QWORD *)a2 + 304LL))(
                    a2,
                    &v23);
    if ( IsClientSKU >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 589, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, this[43]);
      }
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      IsClientSKU = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 32LL))(v23, 0xFFFFFFFFLL);
      if ( IsClientSKU >= 0 )
      {
        GetSystemTimeAsFileTime(&v28);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Sq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            591,
            (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
            (unsigned int)this[43],
            (*(_QWORD *)&v28 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL);
        }
        IsClientSKU = (*(__int64 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v23 + 40LL))(v23, &v22, 0);
        if ( IsClientSKU >= 0 )
        {
          IsClientSKU = v22;
          if ( v22 >= 0 )
          {
            IsClientSKU = CoCreateInstance(&CLSID_VssSnapshotMgmt, 0, 4u, &IID_IVssSnapshotMgmt, &ppv);
            if ( IsClientSKU >= 0 )
            {
              v15 = *(_QWORD *)ppv;
              *(_OWORD *)v30 = xmmword_14013EA80;
              IsClientSKU = (*(__int64 (__fastcall **)(LPVOID, __int64 *, GUID *, __int64 *))(v15 + 24))(
                              ppv,
                              v30,
                              &IID_IVssDifferentialSoftwareSnapshotMgmt,
                              &v25);
              if ( IsClientSKU >= 0 )
              {
                v16 = (*(__int64 (__fastcall **)(__int64, char *, __int64 *))(*(_QWORD *)v25 + 48LL))(v25, v10, &v24);
                IsClientSKU = v16;
                if ( v16 >= 0 )
                {
                  v18 = 0;
                  while ( 1 )
                  {
                    if ( v18 )
                    {
                      IsClientSKU = -2139619272;
                      goto LABEL_93;
                    }
                    v16 = (*(__int64 (__fastcall **)(__int64, __int64, wchar_t **, int *))(*(_QWORD *)v24 + 24LL))(
                            v24,
                            1,
                            String1,
                            &v21);
                    IsClientSKU = v16;
                    if ( v16 < 0 )
                      break;
                    if ( v16 == 1 )
                    {
                      if ( v21 )
                        BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x36CCu, "ulFetched == 0");
                      goto LABEL_93;
                    }
                    if ( v21 != 1 )
                      BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x36D0u, "ulFetched == 1");
                    if ( _wcsicmp(String1[1], (const wchar_t *)v10) )
                      BlbAssert(
                        "base\\stor\\blb\\engine\\service\\backup.cpp",
                        0x36D4u,
                        "_wcsicmp(pDiffArea->m_pwszVolumeName, wszTargetVolumeName) == 0");
                    for ( i = 0; i < a4; ++i )
                    {
                      if ( !_wcsicmp(v32[0], a3[i]) )
                      {
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                        {
                          WPP_SF_SS(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            598,
                            (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
                            (_DWORD)v10,
                            (__int64)a3[i]);
                        }
                        v18 = 1;
                        break;
                      }
                    }
                    CoTaskMemFree(String1[1]);
                    CoTaskMemFree(v32[0]);
                  }
                  v12 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v17 = 597;
                    goto LABEL_67;
                  }
                }
                else
                {
                  v12 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v17 = 596;
LABEL_67:
                    WPP_SF_Sd(
                      (unsigned int)v12[2],
                      v17,
                      (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
                      (_DWORD)v10,
                      v16);
                    goto LABEL_93;
                  }
                }
              }
              else
              {
                v12 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v13 = 595;
                  goto LABEL_11;
                }
              }
            }
            else
            {
              v12 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v13 = 594;
                goto LABEL_11;
              }
            }
          }
          else
          {
            v12 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v13 = 593;
              goto LABEL_11;
            }
          }
        }
        else
        {
          v12 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v13 = 592;
            goto LABEL_11;
          }
        }
      }
      else
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = 590;
          goto LABEL_11;
        }
      }
    }
    else
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 588;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 586;
LABEL_11:
      WPP_SF_d(v12[2], v13, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
LABEL_93:
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v10 )
  {
    CoTaskMemFree(v10);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( IsClientSKU < 0 )
  {
    IsClientSKU = BlbTranslateVssError(IsClientSKU, a5);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return (unsigned int)IsClientSKU;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 600, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 4u )
    WPP_SF_(v12[2], 601, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  return (unsigned int)IsClientSKU;
}

```

## disassembly

```asm
0x1400230c4  push    rbp
0x1400230c6  push    rbx
0x1400230c7  push    rsi
0x1400230c8  push    rdi
0x1400230c9  push    r12
0x1400230cb  push    r13
0x1400230cd  push    r14
0x1400230cf  push    r15
0x1400230d1  lea     rbp, [rsp-17h]
0x1400230d6  sub     rsp, 0B8h
0x1400230dd  xor     r13d, r13d
0x1400230e0  xorps   xmm0, xmm0
0x1400230e3  mov     [rbp+4Fh+var_B8], r13
0x1400230e7  mov     r12d, r9d
0x1400230ea  mov     [rbp+4Fh+var_BC], r13d
0x1400230ee  mov     r15, r8
0x1400230f1  mov     [rbp+4Fh+String2], r13
0x1400230f5  mov     rsi, rdx
0x1400230f8  mov     [rbp+4Fh+var_80], r13
0x1400230fc  mov     rdi, rcx
0x1400230ff  mov     qword ptr [rbp+4Fh+SystemTimeAsFileTime.dwLowDateTime], r13
0x140023103  mov     qword ptr [rbp+4Fh+var_90.dwLowDateTime], r13
0x140023107  mov     [rbp+4Fh+arg_0], r13b
0x14002310b  mov     [rbp+4Fh+var_A0], r13
0x14002310f  mov     [rbp+4Fh+var_A8], r13
0x140023113  mov     [rbp+4Fh+var_B0], r13
0x140023117  movups  xmmword ptr [rbp+4Fh+String1], xmm0
0x14002311b  mov     [rbp+4Fh+var_C0], r13d
0x14002311f  movups  xmmword ptr [rbp+4Fh+var_60], xmm0
0x140023123  movups  [rbp+4Fh+var_50], xmm0
0x140023127  mov     rcx, cs:WPP_GLOBAL_Control
0x14002312e  lea     rax, WPP_GLOBAL_Control
0x140023135  cmp     rcx, rax
0x140023138  jz      short loc_14002315B
0x14002313a  test    byte ptr [rcx+1Ch], 1
0x14002313e  jz      short loc_14002315B
0x140023140  cmp     byte ptr [rcx+19h], 4
0x140023144  jb      short loc_14002315B
0x140023146  mov     rcx, [rcx+10h]
0x14002314a  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140023151  mov     edx, 249h
0x140023156  call    WPP_SF_
0x14002315b  mov     rcx, [rdi+158h]; unsigned __int16 *
0x140023162  lea     r8, [rbp+4Fh+String2]; unsigned __int16 **
0x140023166  lea     rdx, asc_14013C090; "\\"
0x14002316d  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x140023172  mov     r14, [rbp+4Fh+String2]
0x140023176  mov     ebx, eax
0x140023178  test    eax, eax
0x14002317a  js      loc_1400236B1
0x140023180  lea     rcx, [rbp+4Fh+arg_0]; unsigned __int8 *
0x140023184  call    ?BlbutilIsClientSKU@@YAJPEAE@Z; BlbutilIsClientSKU(uchar *)
0x140023189  mov     ebx, eax
0x14002318b  test    eax, eax
0x14002318d  jns     short loc_1400231D7
0x14002318f  mov     rcx, cs:WPP_GLOBAL_Control
0x140023196  lea     rsi, WPP_GLOBAL_Control
0x14002319d  cmp     rcx, rsi
0x1400231a0  jz      loc_1400236BF
0x1400231a6  test    byte ptr [rcx+1Ch], 1
0x1400231aa  jz      loc_1400236BF
0x1400231b0  cmp     byte ptr [rcx+19h], 2
0x1400231b4  jb      loc_1400236BF
0x1400231ba  mov     edx, 24Ah
0x1400231bf  mov     rcx, [rcx+10h]
0x1400231c3  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x1400231ca  mov     r9d, eax
0x1400231cd  call    WPP_SF_d
0x1400231d2  jmp     loc_1400236B8
0x1400231d7  cmp     [rbp+4Fh+arg_0], r13b
0x1400231db  jz      loc_14002327A
0x1400231e1  cmp     [rdi+428h], r13b
0x1400231e8  jnz     loc_14002327A
0x1400231ee  cmp     [rdi+250h], r13b
0x1400231f5  jz      short loc_14002320F
0x1400231f7  lea     r8, aMBresettargetd; "m_bResetTargetDiffArea == FALSE"
0x1400231fe  mov     edx, 3658h; unsigned int
0x140023203  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14002320a  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14002320f  lea     r9, [rbp+4Fh+var_80]; __int64 *
0x140023213  mov     byte ptr [rsp+0F0h+ppv], 1; char
0x140023218  xor     r8d, r8d; unsigned __int64 *
0x14002321b  xor     edx, edx; unsigned __int64 *
0x14002321d  mov     rcx, r14; unsigned __int16 *
0x140023220  call    ?BlbGetDiffAreaSpace@@YAJPEAGPEA_K1PEA_JE@Z; BlbGetDiffAreaSpace(ushort *,unsigned __int64 *,unsigned __int64 *,__int64 *,uchar)
0x140023225  test    eax, eax
0x140023227  jns     short loc_14002326D
0x140023229  mov     rcx, cs:WPP_GLOBAL_Control
0x140023230  lea     rdx, WPP_GLOBAL_Control
0x140023237  cmp     rcx, rdx
0x14002323a  jz      short loc_140023264
0x14002323c  test    byte ptr [rcx+1Ch], 1
0x140023240  jz      short loc_140023264
0x140023242  cmp     byte ptr [rcx+19h], 2
0x140023246  jb      short loc_140023264
0x140023248  mov     rcx, [rcx+10h]
0x14002324c  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140023253  mov     edx, 24Bh
0x140023258  mov     dword ptr [rsp+0F0h+ppv], eax
0x14002325c  mov     r9, r14
0x14002325f  call    WPP_SF_Sd
0x140023264  mov     [rdi+250h], r13b
0x14002326b  jmp     short loc_14002327A
0x14002326d  cmp     [rbp+4Fh+var_80], r13
0x140023271  jnz     short loc_14002327A
0x140023273  mov     byte ptr [rdi+250h], 1
0x14002327a  mov     rax, [rsi]
0x14002327d  lea     rdx, [rbp+4Fh+var_B8]
0x140023281  mov     rcx, rsi
0x140023284  mov     rax, [rax+130h]
0x14002328b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023290  mov     ebx, eax
0x140023292  test    eax, eax
0x140023294  jns     short loc_1400232DE
0x140023296  mov     rcx, cs:WPP_GLOBAL_Control
0x14002329d  lea     rsi, WPP_GLOBAL_Control
0x1400232a4  cmp     rcx, rsi
0x1400232a7  jz      loc_1400236BF
0x1400232ad  test    byte ptr [rcx+1Ch], 1
0x1400232b1  jz      loc_1400236BF
0x1400232b7  cmp     byte ptr [rcx+19h], 2
0x1400232bb  jb      loc_1400236BF
0x1400232c1  mov     edx, 24Ch
0x1400232c6  mov     r9d, eax
0x1400232c9  mov     rcx, [rcx+10h]
0x1400232cd  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x1400232d4  call    WPP_SF_d
0x1400232d9  jmp     loc_1400236B8
0x1400232de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400232e5  lea     rsi, WPP_GLOBAL_Control
0x1400232ec  cmp     rcx, rsi
0x1400232ef  jz      short loc_140023319
0x1400232f1  test    byte ptr [rcx+1Ch], 1
0x1400232f5  jz      short loc_140023319
0x1400232f7  cmp     byte ptr [rcx+19h], 4
0x1400232fb  jb      short loc_140023319
0x1400232fd  mov     r9, [rdi+158h]
0x140023304  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002330b  mov     rcx, [rcx+10h]
0x14002330f  mov     edx, 24Dh
0x140023314  call    WPP_SF_S
0x140023319  lea     rcx, [rbp+4Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14002331d  call    cs:__imp_GetSystemTimeAsFileTime
0x140023323  mov     rcx, [rbp+4Fh+var_B8]
0x140023327  or      edx, 0FFFFFFFFh
0x14002332a  mov     rax, [rcx]
0x14002332d  mov     rax, [rax+20h]
0x140023331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023336  mov     ebx, eax
0x140023338  test    eax, eax
0x14002333a  jns     short loc_14002336A
0x14002333c  mov     rcx, cs:WPP_GLOBAL_Control
0x140023343  cmp     rcx, rsi
0x140023346  jz      loc_1400236BF
0x14002334c  test    byte ptr [rcx+1Ch], 1
0x140023350  jz      loc_1400236BF
0x140023356  cmp     byte ptr [rcx+19h], 2
0x14002335a  jb      loc_1400236BF
0x140023360  mov     edx, 24Eh
0x140023365  jmp     loc_1400232C6
0x14002336a  lea     rcx, [rbp+4Fh+var_90]; lpSystemTimeAsFileTime
0x14002336e  call    cs:__imp_GetSystemTimeAsFileTime
0x140023374  mov     rcx, cs:WPP_GLOBAL_Control
0x14002337b  cmp     rcx, rsi
0x14002337e  jz      short loc_1400233C9
0x140023380  test    byte ptr [rcx+1Ch], 1
0x140023384  jz      short loc_1400233C9
0x140023386  cmp     byte ptr [rcx+19h], 4
0x14002338a  jb      short loc_1400233C9
0x14002338c  mov     rdx, qword ptr [rbp+4Fh+var_90.dwLowDateTime]
0x140023390  mov     rax, 346DC5D63886594Bh
0x14002339a  sub     rdx, qword ptr [rbp+4Fh+SystemTimeAsFileTime.dwLowDateTime]
0x14002339e  mov     r9, [rdi+158h]
0x1400233a5  mov     rcx, [rcx+10h]
0x1400233a9  mul     rdx
0x1400233ac  mov     r8, rdx
0x1400233af  mov     edx, 24Fh
0x1400233b4  shr     r8, 0Bh
0x1400233b8  mov     [rsp+0F0h+ppv], r8
0x1400233bd  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x1400233c4  call    WPP_SF_Sq
0x1400233c9  mov     rcx, [rbp+4Fh+var_B8]
0x1400233cd  lea     rdx, [rbp+4Fh+var_BC]
0x1400233d1  xor     r8d, r8d
0x1400233d4  mov     rax, [rcx]
0x1400233d7  mov     rax, [rax+28h]
0x1400233db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400233e0  mov     ebx, eax
0x1400233e2  test    eax, eax
0x1400233e4  jns     short loc_140023414
0x1400233e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400233ed  cmp     rcx, rsi
0x1400233f0  jz      loc_1400236BF
0x1400233f6  test    byte ptr [rcx+1Ch], 1
0x1400233fa  jz      loc_1400236BF
0x140023400  cmp     byte ptr [rcx+19h], 2
0x140023404  jb      loc_1400236BF
0x14002340a  mov     edx, 250h
0x14002340f  jmp     loc_1400232C6
0x140023414  mov     ebx, [rbp+4Fh+var_BC]
0x140023417  test    ebx, ebx
0x140023419  jns     short loc_14002344C
0x14002341b  mov     rcx, cs:WPP_GLOBAL_Control
0x140023422  cmp     rcx, rsi
0x140023425  jz      loc_1400236BF
0x14002342b  test    byte ptr [rcx+1Ch], 1
0x14002342f  jz      loc_1400236BF
0x140023435  cmp     byte ptr [rcx+19h], 2
0x140023439  jb      loc_1400236BF
0x14002343f  mov     edx, 251h
0x140023444  mov     r9d, ebx
0x140023447  jmp     loc_1400232C9
0x14002344c  xor     edx, edx; pUnkOuter
0x14002344e  lea     rax, [rbp+4Fh+var_A0]
0x140023452  lea     r9, IID_IVssSnapshotMgmt; riid
0x140023459  mov     [rsp+0F0h+ppv], rax; ppv
0x14002345e  lea     rcx, CLSID_VssSnapshotMgmt; rclsid
0x140023465  lea     r8d, [rdx+4]; dwClsContext
0x140023469  call    cs:__imp_CoCreateInstance
0x14002346f  mov     ebx, eax
0x140023471  test    eax, eax
0x140023473  jns     short loc_1400234A3
0x140023475  mov     rcx, cs:WPP_GLOBAL_Control
0x14002347c  cmp     rcx, rsi
0x14002347f  jz      loc_1400236BF
0x140023485  test    byte ptr [rcx+1Ch], 1
0x140023489  jz      loc_1400236BF
0x14002348f  cmp     byte ptr [rcx+19h], 2
0x140023493  jb      loc_1400236BF
0x140023499  mov     edx, 252h
0x14002349e  jmp     loc_1400231BF
0x1400234a3  mov     rcx, [rbp+4Fh+var_A0]
0x1400234a7  lea     r9, [rbp+4Fh+var_A8]
0x1400234ab  movups  xmm0, cs:xmmword_14013EA80
0x1400234b2  lea     r8, IID_IVssDifferentialSoftwareSnapshotMgmt
0x1400234b9  lea     rdx, [rbp+4Fh+var_80]
0x1400234bd  mov     rax, [rcx]
0x1400234c0  movdqu  xmmword ptr [rbp+4Fh+var_80], xmm0
0x1400234c5  mov     rax, [rax+18h]
0x1400234c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400234ce  mov     ebx, eax
0x1400234d0  test    eax, eax
0x1400234d2  jns     short loc_140023502
0x1400234d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400234db  cmp     rcx, rsi
0x1400234de  jz      loc_1400236BF
0x1400234e4  test    byte ptr [rcx+1Ch], 1
0x1400234e8  jz      loc_1400236BF
0x1400234ee  cmp     byte ptr [rcx+19h], 2
0x1400234f2  jb      loc_1400236BF
0x1400234f8  mov     edx, 253h
0x1400234fd  jmp     loc_1400231BF
0x140023502  mov     rcx, [rbp+4Fh+var_A8]
0x140023506  lea     r8, [rbp+4Fh+var_B0]
0x14002350a  mov     rdx, r14
0x14002350d  mov     rax, [rcx]
0x140023510  mov     rax, [rax+30h]
0x140023514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023519  mov     ebx, eax
0x14002351b  test    eax, eax
0x14002351d  jns     short loc_140023564
0x14002351f  mov     rcx, cs:WPP_GLOBAL_Control
0x140023526  cmp     rcx, rsi
0x140023529  jz      loc_1400236BF
0x14002352f  test    byte ptr [rcx+1Ch], 1
0x140023533  jz      loc_1400236BF
0x140023539  cmp     byte ptr [rcx+19h], 2
0x14002353d  jb      loc_1400236BF
0x140023543  mov     edx, 254h
0x140023548  mov     rcx, [rcx+10h]
0x14002354c  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140023553  mov     r9, r14
0x140023556  mov     dword ptr [rsp+0F0h+ppv], eax
0x14002355a  call    WPP_SF_Sd
0x14002355f  jmp     loc_1400236B8
0x140023564  mov     dil, r13b
0x140023567  test    dil, dil
0x14002356a  jnz     loc_1400236AC
0x140023570  mov     rcx, [rbp+4Fh+var_B0]
0x140023574  lea     r9, [rbp+4Fh+var_C0]
0x140023578  lea     r8, [rbp+4Fh+String1]
0x14002357c  mov     edx, 1
0x140023581  mov     rax, [rcx]
0x140023584  mov     rax, [rax+18h]
0x140023588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002358d  mov     ebx, eax
0x14002358f  test    eax, eax
0x140023591  js      loc_140023683
0x140023597  cmp     eax, 1
0x14002359a  jz      loc_140023663
0x1400235a0  cmp     [rbp+4Fh+var_C0], 1
0x1400235a4  jz      short loc_1400235BE
0x1400235a6  lea     r8, aUlfetched1; "ulFetched == 1"
0x1400235ad  mov     edx, 36D0h; unsigned int
0x1400235b2  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x1400235b9  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400235be  mov     rcx, [rbp+4Fh+String1+8]; String1
0x1400235c2  mov     rdx, r14; String2
0x1400235c5  call    cs:__imp__wcsicmp
0x1400235cb  test    eax, eax
  ... truncated ...
```

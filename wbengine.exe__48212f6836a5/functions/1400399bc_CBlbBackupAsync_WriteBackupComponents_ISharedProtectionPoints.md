# CBlbBackupAsync::WriteBackupComponents(ISharedProtectionPoints *)

- ea: `0x1400399bc`
- end: `0x140039eb8`
- name: `?WriteBackupComponents@CBlbBackupAsync@@AEAAJPEAUISharedProtectionPoints@@@Z`
- size: `1276`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this, struct ISharedProtectionPoints *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140019fd0`

## callees

- `0x140006ca8`
- `0x140006d94`
- `0x140008ac8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000fe94`
- `0x140014260`
- `0x140014384`
- `0x140014798`
- `0x140028eb8`
- `0x140035350`
- `0x1400399bc`
- `0x1400889f0`
- `0x14008fed0`
- `0x1400f007c`
- `0x1400f07dc`
- `0x1400f25c0`
- `0x1400f3bbc`
- `0x140101d48`
- `0x140137010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x140039bb0`
- `KERNEL32!DeleteFileW` at `0x140039bb0`
- `KERNEL32!GetLastError` at `0x140039bba`
- `KERNEL32!GetLastError` at `0x140039bba`
- `ole32!CoTaskMemFree` at `0x140039dfa`
- `ole32!CoTaskMemFree` at `0x140039e0d`
- `ole32!CoTaskMemFree` at `0x140039e1b`
- `ole32!CoTaskMemFree` at `0x140039e29`
- `ole32!CoTaskMemFree` at `0x140039e37`
- `ole32!CoTaskMemFree` at `0x140039dfa`
- `ole32!CoTaskMemFree` at `0x140039e0d`
- `ole32!CoTaskMemFree` at `0x140039e1b`
- `ole32!CoTaskMemFree` at `0x140039e29`
- `ole32!CoTaskMemFree` at `0x140039e37`

## string_xrefs

- `0x140039a45`: `base\stor\blb\engine\service\backup.cpp`
- `0x140039c91`: `base\stor\blb\engine\service\backup.cpp`
- `0x140039a39`: `m_wszBackupSetDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBlbBackupAsync::WriteBackupComponents(CBlbBackupAsync *this, struct ISharedProtectionPoints *a2)
{
  unsigned __int16 *v4; // r13
  WCHAR *v5; // r15
  unsigned __int16 *v6; // r12
  int IsClientSKU; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  int File; // eax
  DWORD LastError; // eax
  int v12; // eax
  LPVOID v13; // r9
  CBlbFileVerifier *v14; // rax
  CBlbFileVerifier *v15; // r14
  void *v16; // rdx
  _WORD *v17; // rcx
  __int64 v18; // rax
  _QWORD *v19; // rdi
  unsigned __int64 v20; // rsi
  PVOID *v21; // rcx
  unsigned __int16 *v23; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v24; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 *v25; // [rsp+40h] [rbp-10h] BYREF
  CBlbImpersonationHelper *v26; // [rsp+48h] [rbp-8h]
  CBlbFileVerifier *v27; // [rsp+90h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp+50h] BYREF
  LPCWSTR lpFileName; // [rsp+A8h] [rbp+58h] BYREF

  v4 = 0;
  v24 = 0;
  v5 = 0;
  lpFileName = 0;
  v6 = 0;
  v25 = 0;
  v23 = 0;
  pv = 0;
  LOBYTE(v27) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 351, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  if ( !*((_QWORD *)this + 59) )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x1C4Du, "m_wszBackupSetDirectory");
  v26 = (CBlbBackupAsync *)((char *)this + 40);
  IsClientSKU = CBlbImpersonationHelper::ImpersonateCaller((CBlbBackupAsync *)((char *)this + 40), 0);
  if ( IsClientSKU >= 0 )
  {
    IsClientSKU = BlbutilIsClientSKU((unsigned __int8 *)&v27);
    if ( IsClientSKU >= 0 )
    {
      if ( !*((_QWORD *)this + 58) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 353, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
        }
        goto LABEL_68;
      }
      if ( (*((_BYTE *)this + 340) & 4) == 0 )
        goto LABEL_35;
      IsClientSKU = BlbAppendBackupComponentsFile(*((unsigned __int16 **)this + 59), 0, 0, &v24);
      v4 = v24;
      if ( IsClientSKU < 0 )
        goto LABEL_68;
      File = BlbFindFile(v24, (unsigned __int16 **)&lpFileName);
      IsClientSKU = File;
      if ( File < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            354,
            (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
            (_DWORD)v4,
            *((_QWORD *)this + 59),
            File);
        }
        v5 = (WCHAR *)lpFileName;
        goto LABEL_68;
      }
      v5 = (WCHAR *)lpFileName;
      if ( lpFileName && !DeleteFileW(lpFileName) )
      {
        LastError = GetLastError();
        IsClientSKU = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            355,
            (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
            (_DWORD)v5,
            LastError);
        }
        if ( IsClientSKU > 0 )
          IsClientSKU = (unsigned __int16)IsClientSKU | 0x80070000;
      }
      else
      {
LABEL_35:
        IsClientSKU = BlbAppendBackupComponentsFile(
                        *((unsigned __int16 **)this + 59),
                        (UUID *)((char *)this + 296),
                        0,
                        &v25);
        v6 = v25;
        if ( IsClientSKU >= 0 )
        {
          v12 = (*((_BYTE *)this + 340) & 1) != 0
              ? BlbutilDuplicateString(v25, &v23, 0)
              : BlbAppendBackupComponentsFile(*((unsigned __int16 **)this + 59), (UUID *)((char *)this + 296), 1u, &v23);
          IsClientSKU = v12;
          if ( v12 >= 0 )
          {
            if ( (_BYTE)v27 )
              goto LABEL_48;
            if ( !a2 )
              BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x1CAAu, "pSPP");
            IsClientSKU = (*(__int64 (__fastcall **)(struct ISharedProtectionPoints *, LPVOID *))(*(_QWORD *)a2 + 112LL))(
                            a2,
                            &pv);
            if ( IsClientSKU >= 0 )
            {
LABEL_48:
              v13 = pv;
              if ( !pv )
                v13 = (LPVOID)*((_QWORD *)this + 58);
              IsClientSKU = BlbSafeDumpFile(v6, v23, *((unsigned int *)this + 84), v13);
              if ( IsClientSKU >= 0 && *((char *)this + 340) < 0 && *((_BYTE *)this + 276) )
              {
                v14 = (CBlbFileVerifier *)operator new(0x40u);
                v27 = v14;
                v15 = v14 ? CBlbFileVerifier::CBlbFileVerifier(v14) : 0LL;
                IsClientSKU = CBlbFileVerifier::Init(v15, v6);
                if ( IsClientSKU >= 0 )
                {
                  v16 = pv;
                  v17 = pv;
                  if ( !pv )
                    v17 = (_WORD *)*((_QWORD *)this + 58);
                  v18 = -1;
                  do
                    ++v18;
                  while ( v17[v18] );
                  if ( !pv )
                    v16 = (void *)*((_QWORD *)this + 58);
                  IsClientSKU = CBlbFileVerifier::SetChecksumForData(v15, v16, 2 * v18 + 2);
                  if ( IsClientSKU >= 0 )
                  {
                    v19 = (_QWORD *)((char *)this + 776);
                    v20 = v19[1];
                    if ( v20 >= v19[2]
                      && !(unsigned __int8)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
                                             v19,
                                             v20 + 1) )
                    {
                      ATL::AtlThrowImpl(-2147024882);
                    }
                    *(_QWORD *)(*v19 + 8 * v20) = v15;
                    ++v19[1];
                  }
                }
              }
            }
            else
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v9 = 356;
                goto LABEL_13;
              }
            }
          }
        }
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 352;
LABEL_13:
        WPP_SF_d(v8[2], v9, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      }
    }
  }
LABEL_68:
  CBlbImpersonationHelper::Revert(v26);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v23 )
    CoTaskMemFree(v23);
  if ( v5 )
    CoTaskMemFree(v5);
  if ( v4 )
    CoTaskMemFree(v4);
  if ( v6 )
    CoTaskMemFree(v6);
  if ( IsClientSKU >= 0 )
    goto LABEL_83;
  v21 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)IsClientSKU;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 357, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
LABEL_83:
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 1) != 0 && *((_BYTE *)v21 + 25) >= 4u )
    WPP_SF_(v21[2], 358, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  return (unsigned int)IsClientSKU;
}

```

## disassembly

```asm
0x1400399bc  mov     [rsp-38h+arg_8], rbx
0x1400399c1  push    rbp
0x1400399c2  push    rsi
0x1400399c3  push    rdi
0x1400399c4  push    r12
0x1400399c6  push    r13
0x1400399c8  push    r14
0x1400399ca  push    r15
0x1400399cc  mov     rbp, rsp
0x1400399cf  sub     rsp, 50h
0x1400399d3  mov     r14, rdx
0x1400399d6  mov     rdi, rcx
0x1400399d9  xor     esi, esi
0x1400399db  mov     r13d, esi
0x1400399de  mov     [rbp+var_18], rsi
0x1400399e2  mov     r15d, esi
0x1400399e5  mov     [rbp+lpFileName], rsi
0x1400399e9  mov     r12d, esi
0x1400399ec  mov     [rbp+var_10], rsi
0x1400399f0  mov     [rbp+var_20], rsi
0x1400399f4  mov     [rbp+pv], rsi
0x1400399f8  mov     byte ptr [rbp+arg_0], sil
0x1400399fc  lea     rax, WPP_GLOBAL_Control
0x140039a03  mov     rcx, cs:WPP_GLOBAL_Control
0x140039a0a  cmp     rcx, rax
0x140039a0d  jz      short loc_140039A30
0x140039a0f  test    byte ptr [rcx+1Ch], 1
0x140039a13  jz      short loc_140039A30
0x140039a15  cmp     byte ptr [rcx+19h], 4
0x140039a19  jb      short loc_140039A30
0x140039a1b  mov     edx, 15Fh
0x140039a20  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140039a27  mov     rcx, [rcx+10h]
0x140039a2b  call    WPP_SF_
0x140039a30  cmp     [rdi+1D8h], rsi
0x140039a37  jnz     short loc_140039A51
0x140039a39  lea     r8, aMWszbackupsetd; "m_wszBackupSetDirectory"
0x140039a40  mov     edx, 1C4Dh; unsigned int
0x140039a45  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x140039a4c  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140039a51  lea     rax, [rdi+28h]
0x140039a55  mov     [rbp+var_8], rax
0x140039a59  xor     edx, edx; unsigned __int8
0x140039a5b  mov     rcx, rax; this
0x140039a5e  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x140039a63  mov     ebx, eax
0x140039a65  test    eax, eax
0x140039a67  js      loc_140039DE1
0x140039a6d  lea     rcx, [rbp+arg_0]; unsigned __int8 *
0x140039a71  call    ?BlbutilIsClientSKU@@YAJPEAE@Z; BlbutilIsClientSKU(uchar *)
0x140039a76  mov     ebx, eax
0x140039a78  test    eax, eax
0x140039a7a  jns     short loc_140039AC4
0x140039a7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140039a83  lea     r14, WPP_GLOBAL_Control
0x140039a8a  cmp     rcx, r14
0x140039a8d  jz      loc_140039DE8
0x140039a93  test    byte ptr [rcx+1Ch], 1
0x140039a97  jz      loc_140039DE8
0x140039a9d  cmp     byte ptr [rcx+19h], 2
0x140039aa1  jb      loc_140039DE8
0x140039aa7  mov     edx, 160h
0x140039aac  mov     r9d, eax
0x140039aaf  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140039ab6  mov     rcx, [rcx+10h]
0x140039aba  call    WPP_SF_d
0x140039abf  jmp     loc_140039DE8
0x140039ac4  cmp     [rdi+1D0h], rsi
0x140039acb  jnz     short loc_140039B12
0x140039acd  mov     rcx, cs:WPP_GLOBAL_Control
0x140039ad4  lea     r14, WPP_GLOBAL_Control
0x140039adb  cmp     rcx, r14
0x140039ade  jz      loc_140039DE8
0x140039ae4  test    byte ptr [rcx+1Ch], 1
0x140039ae8  jz      loc_140039DE8
0x140039aee  cmp     byte ptr [rcx+19h], 4
0x140039af2  jb      loc_140039DE8
0x140039af8  mov     edx, 161h
0x140039afd  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140039b04  mov     rcx, [rcx+10h]
0x140039b08  call    WPP_SF_
0x140039b0d  jmp     loc_140039DE8
0x140039b12  test    byte ptr [rdi+154h], 4
0x140039b19  jz      loc_140039C13
0x140039b1f  lea     r9, [rbp+var_18]; unsigned __int16 **
0x140039b23  xor     r8d, r8d; unsigned __int8
0x140039b26  xor     edx, edx; Uuid
0x140039b28  mov     rcx, [rdi+1D8h]; unsigned __int16 *
0x140039b2f  call    ?BlbAppendBackupComponentsFile@@YAJPEAGPEAU_GUID@@EPEAPEAG@Z; BlbAppendBackupComponentsFile(ushort *,_GUID *,uchar,ushort * *)
0x140039b34  mov     ebx, eax
0x140039b36  mov     r13, [rbp+var_18]
0x140039b3a  test    eax, eax
0x140039b3c  js      loc_140039DE1
0x140039b42  lea     rdx, [rbp+lpFileName]; unsigned __int16 **
0x140039b46  mov     rcx, r13; unsigned __int16 *
0x140039b49  call    ?BlbFindFile@@YAJPEAGPEAPEAG@Z; BlbFindFile(ushort *,ushort * *)
0x140039b4e  mov     ebx, eax
0x140039b50  test    eax, eax
0x140039b52  jns     short loc_140039BA4
0x140039b54  mov     rcx, cs:WPP_GLOBAL_Control
0x140039b5b  lea     r14, WPP_GLOBAL_Control
0x140039b62  cmp     rcx, r14
0x140039b65  jz      short loc_140039B9B
0x140039b67  test    byte ptr [rcx+1Ch], 1
0x140039b6b  jz      short loc_140039B9B
0x140039b6d  cmp     byte ptr [rcx+19h], 2
0x140039b71  jb      short loc_140039B9B
0x140039b73  mov     edx, 162h
0x140039b78  mov     [rsp+50h+var_28], eax
0x140039b7c  mov     rax, [rdi+1D8h]
0x140039b83  mov     [rsp+50h+var_30], rax
0x140039b88  mov     r9, r13
0x140039b8b  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140039b92  mov     rcx, [rcx+10h]
0x140039b96  call    WPP_SF_SSD
0x140039b9b  mov     r15, [rbp+lpFileName]
0x140039b9f  jmp     loc_140039DE8
0x140039ba4  mov     r15, [rbp+lpFileName]
0x140039ba8  test    r15, r15
0x140039bab  jz      short loc_140039C13
0x140039bad  mov     rcx, r15; lpFileName
0x140039bb0  call    cs:__imp_DeleteFileW
0x140039bb6  test    eax, eax
0x140039bb8  jnz     short loc_140039C13
0x140039bba  call    cs:__imp_GetLastError
0x140039bc0  mov     ebx, eax
0x140039bc2  mov     rcx, cs:WPP_GLOBAL_Control
0x140039bc9  lea     r14, WPP_GLOBAL_Control
0x140039bd0  cmp     rcx, r14
0x140039bd3  jz      short loc_140039BFD
0x140039bd5  test    byte ptr [rcx+1Ch], 1
0x140039bd9  jz      short loc_140039BFD
0x140039bdb  cmp     byte ptr [rcx+19h], 2
0x140039bdf  jb      short loc_140039BFD
0x140039be1  mov     edx, 163h
0x140039be6  mov     dword ptr [rsp+50h+var_30], eax
0x140039bea  mov     r9, r15
0x140039bed  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140039bf4  mov     rcx, [rcx+10h]
0x140039bf8  call    WPP_SF_Sd
0x140039bfd  test    ebx, ebx
0x140039bff  jle     loc_140039DE8
0x140039c05  movzx   ebx, bx
0x140039c08  or      ebx, 80070000h
0x140039c0e  jmp     loc_140039DE8
0x140039c13  lea     rsi, [rdi+128h]
0x140039c1a  lea     r9, [rbp+var_10]; unsigned __int16 **
0x140039c1e  xor     r8d, r8d; unsigned __int8
0x140039c21  mov     rdx, rsi; Uuid
0x140039c24  mov     rcx, [rdi+1D8h]; unsigned __int16 *
0x140039c2b  call    ?BlbAppendBackupComponentsFile@@YAJPEAGPEAU_GUID@@EPEAPEAG@Z; BlbAppendBackupComponentsFile(ushort *,_GUID *,uchar,ushort * *)
0x140039c30  mov     ebx, eax
0x140039c32  mov     r12, [rbp+var_10]
0x140039c36  test    eax, eax
0x140039c38  js      loc_140039DDF
0x140039c3e  test    byte ptr [rdi+154h], 1
0x140039c45  jz      short loc_140039C58
0x140039c47  xor     r8d, r8d; unsigned __int64
0x140039c4a  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x140039c4e  mov     rcx, r12; unsigned __int16 *
0x140039c51  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140039c56  jmp     short loc_140039C6E
0x140039c58  lea     r9, [rbp+var_20]; unsigned __int16 **
0x140039c5c  mov     r8b, 1; unsigned __int8
0x140039c5f  mov     rdx, rsi; Uuid
0x140039c62  mov     rcx, [rdi+1D8h]; unsigned __int16 *
0x140039c69  call    ?BlbAppendBackupComponentsFile@@YAJPEAGPEAU_GUID@@EPEAPEAG@Z; BlbAppendBackupComponentsFile(ushort *,_GUID *,uchar,ushort * *)
0x140039c6e  xor     esi, esi
0x140039c70  test    eax, eax
0x140039c72  mov     ebx, eax
0x140039c74  js      loc_140039DE1
0x140039c7a  cmp     byte ptr [rbp+arg_0], sil
0x140039c7e  jnz     short loc_140039CEB
0x140039c80  test    r14, r14
0x140039c83  jnz     short loc_140039C9D
0x140039c85  lea     r8, aPspp; "pSPP"
0x140039c8c  mov     edx, 1CAAh; unsigned int
0x140039c91  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x140039c98  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140039c9d  mov     rax, [r14]
0x140039ca0  lea     rdx, [rbp+pv]
0x140039ca4  mov     rcx, r14
0x140039ca7  mov     rax, [rax+70h]
0x140039cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039cb0  mov     ebx, eax
0x140039cb2  test    eax, eax
0x140039cb4  jns     short loc_140039CEB
0x140039cb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140039cbd  lea     r14, WPP_GLOBAL_Control
0x140039cc4  cmp     rcx, r14
0x140039cc7  jz      loc_140039DE8
0x140039ccd  test    byte ptr [rcx+1Ch], 1
0x140039cd1  jz      loc_140039DE8
0x140039cd7  cmp     byte ptr [rcx+19h], 2
0x140039cdb  jb      loc_140039DE8
0x140039ce1  mov     edx, 164h
0x140039ce6  jmp     loc_140039AAC
0x140039ceb  mov     r9, [rbp+pv]
0x140039cef  test    r9, r9
0x140039cf2  jnz     short loc_140039CFB
0x140039cf4  mov     r9, [rdi+1D0h]
0x140039cfb  mov     r8d, [rdi+150h]
0x140039d02  mov     rdx, [rbp+var_20]
0x140039d06  mov     rcx, r12
0x140039d09  call    ?BlbSafeDumpFile@@YAJPEBG0W4_BLB_MEDIA_TYPE@@0@Z; BlbSafeDumpFile(ushort const *,ushort const *,_BLB_MEDIA_TYPE,ushort const *)
0x140039d0e  mov     ebx, eax
0x140039d10  test    eax, eax
0x140039d12  js      loc_140039DE1
0x140039d18  test    byte ptr [rdi+154h], 80h
0x140039d1f  jz      loc_140039DE1
0x140039d25  cmp     [rdi+114h], sil
0x140039d2c  jz      loc_140039DE1
0x140039d32  mov     ecx, 40h ; '@'; Size
0x140039d37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140039d3c  mov     [rbp+arg_0], rax
0x140039d40  test    rax, rax
0x140039d43  jz      short loc_140039D52
0x140039d45  mov     rcx, rax; this
0x140039d48  call    ??0CBlbFileVerifier@@QEAA@XZ; CBlbFileVerifier::CBlbFileVerifier(void)
0x140039d4d  mov     r14, rax
0x140039d50  jmp     short loc_140039D55
0x140039d52  mov     r14, rsi
0x140039d55  mov     rdx, r12; unsigned __int16 *
0x140039d58  mov     rcx, r14; this
0x140039d5b  call    ?Init@CBlbFileVerifier@@QEAAJPEAG@Z; CBlbFileVerifier::Init(ushort *)
0x140039d60  mov     ebx, eax
0x140039d62  test    eax, eax
0x140039d64  js      short loc_140039DE1
0x140039d66  mov     rdx, [rbp+pv]
0x140039d6a  test    rdx, rdx
0x140039d6d  mov     rcx, rdx
0x140039d70  jnz     short loc_140039D79
0x140039d72  mov     rcx, [rdi+1D0h]
0x140039d79  or      rax, 0FFFFFFFFFFFFFFFFh
0x140039d7d  inc     rax
0x140039d80  cmp     [rcx+rax*2], si
0x140039d84  jnz     short loc_140039D7D
0x140039d86  lea     r8, ds:2[rax*2]; unsigned __int64
0x140039d8e  test    rdx, rdx
0x140039d91  jnz     short loc_140039D9A
0x140039d93  mov     rdx, [rdi+1D0h]; void *
0x140039d9a  mov     rcx, r14; this
0x140039d9d  call    ?SetChecksumForData@CBlbFileVerifier@@QEAAJPEAX_K@Z; CBlbFileVerifier::SetChecksumForData(void *,unsigned __int64)
0x140039da2  mov     ebx, eax
0x140039da4  test    eax, eax
0x140039da6  js      short loc_140039DE1
0x140039da8  add     rdi, 308h
0x140039daf  mov     rsi, [rdi+8]
0x140039db3  cmp     rsi, [rdi+10h]
0x140039db7  jb      short loc_140039DD4
0x140039db9  lea     rdx, [rsi+1]
0x140039dbd  mov     rcx, rdi
0x140039dc0  call    ?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(unsigned __int64)
0x140039dc5  test    al, al
0x140039dc7  jnz     short loc_140039DD4
0x140039dc9  mov     ecx, 8007000Eh; int
0x140039dce  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140039dd4  mov     rax, [rdi]
0x140039dd7  mov     [rax+rsi*8], r14
0x140039ddb  inc     qword ptr [rdi+8]
0x140039ddf  xor     esi, esi
0x140039de1  lea     r14, WPP_GLOBAL_Control
0x140039de8  mov     rcx, [rbp+var_8]; this
0x140039dec  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x140039df1  mov     rcx, [rbp+pv]; pv
0x140039df5  test    rcx, rcx
0x140039df8  jz      short loc_140039E04
0x140039dfa  call    cs:__imp_CoTaskMemFree
0x140039e00  mov     [rbp+pv], rsi
0x140039e04  mov     rcx, [rbp+var_20]; pv
0x140039e08  test    rcx, rcx
0x140039e0b  jz      short loc_140039E13
0x140039e0d  call    cs:__imp_CoTaskMemFree
0x140039e13  test    r15, r15
0x140039e16  jz      short loc_140039E21
0x140039e18  mov     rcx, r15; pv
0x140039e1b  call    cs:__imp_CoTaskMemFree
0x140039e21  test    r13, r13
0x140039e24  jz      short loc_140039E2F
0x140039e26  mov     rcx, r13; pv
0x140039e29  call    cs:__imp_CoTaskMemFree
0x140039e2f  test    r12, r12
0x140039e32  jz      short loc_140039E3D
0x140039e34  mov     rcx, r12; pv
0x140039e37  call    cs:__imp_CoTaskMemFree
0x140039e3d  test    ebx, ebx
0x140039e3f  jns     short loc_140039E71
0x140039e41  mov     rcx, cs:WPP_GLOBAL_Control
0x140039e48  cmp     rcx, r14
0x140039e4b  jz      short loc_140039E9E
0x140039e4d  test    byte ptr [rcx+1Ch], 1
0x140039e51  jz      short loc_140039E78
0x140039e53  cmp     byte ptr [rcx+19h], 2
0x140039e57  jb      short loc_140039E78
0x140039e59  mov     edx, 165h
0x140039e5e  mov     r9d, ebx
0x140039e61  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140039e68  mov     rcx, [rcx+10h]
0x140039e6c  call    WPP_SF_d
0x140039e71  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```

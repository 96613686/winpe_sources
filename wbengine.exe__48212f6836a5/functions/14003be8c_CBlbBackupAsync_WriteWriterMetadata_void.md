# CBlbBackupAsync::WriteWriterMetadata(void)

- ea: `0x14003be8c`
- end: `0x14003c2f0`
- name: `?WriteWriterMetadata@CBlbBackupAsync@@AEAAJXZ`
- size: `1124`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x140039ec0`

## callees

- `0x140006ca8`
- `0x140006d94`
- `0x140008ac8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000fe94`
- `0x140014260`
- `0x140014798`
- `0x140028eb8`
- `0x140035350`
- `0x14003be8c`
- `0x1400889f0`
- `0x1400f25c0`
- `0x1400f3bbc`
- `0x140102560`
- `0x14011a224`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x14003c0b9`
- `KERNEL32!DeleteFileW` at `0x14003c0b9`
- `KERNEL32!GetLastError` at `0x14003c0c3`
- `KERNEL32!GetLastError` at `0x14003c0c3`
- `ole32!CoTaskMemFree` at `0x14003bf3b`
- `ole32!CoTaskMemFree` at `0x14003bf49`
- `ole32!CoTaskMemFree` at `0x14003bf57`
- `ole32!CoTaskMemFree` at `0x14003bf65`
- `ole32!CoTaskMemFree` at `0x14003bf73`
- `ole32!CoTaskMemFree` at `0x14003bfec`
- `ole32!CoTaskMemFree` at `0x14003c04f`
- `ole32!CoTaskMemFree` at `0x14003c089`
- `ole32!CoTaskMemFree` at `0x14003c12c`
- `ole32!CoTaskMemFree` at `0x14003c172`
- `ole32!CoTaskMemFree` at `0x14003bf3b`
- `ole32!CoTaskMemFree` at `0x14003bf49`
- `ole32!CoTaskMemFree` at `0x14003bf57`
- `ole32!CoTaskMemFree` at `0x14003bf65`
- `ole32!CoTaskMemFree` at `0x14003bf73`
- `ole32!CoTaskMemFree` at `0x14003bfec`
- `ole32!CoTaskMemFree` at `0x14003c04f`
- `ole32!CoTaskMemFree` at `0x14003c089`
- `ole32!CoTaskMemFree` at `0x14003c12c`
- `ole32!CoTaskMemFree` at `0x14003c172`

## string_xrefs

- `0x14003c02e`: `base\stor\blb\engine\service\backup.cpp`
- `0x14003c022`: `m_wszBackupSetDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBlbBackupAsync::WriteWriterMetadata(CBlbBackupAsync *this)
{
  unsigned int v2; // r12d
  signed int WriterInfo; // ebx
  unsigned __int16 *v4; // r14
  WCHAR *v5; // r15
  unsigned __int16 *v6; // r13
  unsigned __int16 *v7; // rdi
  unsigned __int16 *v8; // r12
  void *v9; // r14
  DWORD LastError; // eax
  int appended; // eax
  CBlbFileVerifier *v13; // r14
  CBlbFileVerifier *v14; // rax
  __int64 v15; // r8
  unsigned __int64 v16; // rax
  LPVOID pv; // [rsp+30h] [rbp-49h] BYREF
  unsigned __int16 *v18; // [rsp+38h] [rbp-41h] BYREF
  unsigned __int16 *v19; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v20; // [rsp+48h] [rbp-31h]
  LPCWSTR lpFileName; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int16 *v22; // [rsp+58h] [rbp-21h] BYREF
  unsigned __int64 v23; // [rsp+60h] [rbp-19h]
  CBlbFileVerifier *v24; // [rsp+68h] [rbp-11h]
  UUID v25; // [rsp+70h] [rbp-9h] BYREF

  v2 = 0;
  WriterInfo = 0;
  v25 = 0;
  v4 = 0;
  v18 = 0;
  v5 = 0;
  lpFileName = 0;
  v6 = 0;
  v22 = 0;
  pv = 0;
  v7 = 0;
  v19 = 0;
  if ( *((_QWORD *)this + 57) )
  {
    while ( 1 )
    {
      v20 = v2;
      if ( v2 >= *(_DWORD *)(*((_QWORD *)this + 57) + 8LL) )
        break;
      if ( v7 )
      {
        CoTaskMemFree(v7);
        v7 = 0;
        v19 = 0;
      }
      WriterInfo = BlbGetWriterInfo(*((struct _SPP_METADATA_PROP **)this + 57), v2, &v25, &v19);
      if ( WriterInfo < 0 )
      {
LABEL_69:
        v7 = v19;
        break;
      }
      if ( *((unsigned __int16 **)this + 59) == v7 )
        BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x1D29u, "m_wszBackupSetDirectory");
      if ( (*((_BYTE *)this + 340) & 4) != 0 )
      {
        if ( v4 )
        {
          CoTaskMemFree(v4);
          v18 = v7;
        }
        WriterInfo = BlbAppendWriterMetadataFile(*((unsigned __int16 **)this + 59), 0, &v25, 0, &v18);
        if ( WriterInfo < 0 )
          goto LABEL_69;
        if ( v5 )
        {
          CoTaskMemFree(v5);
          lpFileName = v7;
        }
        v8 = v18;
        WriterInfo = BlbFindFile(v18, (unsigned __int16 **)&lpFileName);
        v5 = (WCHAR *)lpFileName;
        if ( WriterInfo < 0 )
          goto LABEL_74;
        if ( lpFileName && !DeleteFileW(lpFileName) )
        {
          LastError = GetLastError();
          WriterInfo = LastError;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              360,
              (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
              (_DWORD)v5,
              LastError);
          }
          if ( WriterInfo > 0 )
            WriterInfo = (unsigned __int16)WriterInfo | 0x80070000;
          v7 = v19;
          v9 = pv;
          goto LABEL_8;
        }
      }
      else
      {
        v8 = v18;
      }
      if ( v6 )
      {
        CoTaskMemFree(v6);
        v22 = v7;
      }
      WriterInfo = BlbAppendWriterMetadataFile(
                     *((unsigned __int16 **)this + 59),
                     (UUID *)((char *)this + 296),
                     &v25,
                     0,
                     &v22);
      if ( WriterInfo < 0 )
      {
        v6 = v22;
LABEL_74:
        v7 = v19;
        goto LABEL_7;
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v6 = v22;
      if ( (*((_BYTE *)this + 340) & 1) != 0 )
        appended = BlbutilDuplicateString(v22, (unsigned __int16 **)&pv, 0);
      else
        appended = BlbAppendWriterMetadataFile(
                     *((unsigned __int16 **)this + 59),
                     (UUID *)((char *)this + 296),
                     &v25,
                     1u,
                     (unsigned __int16 **)&pv);
      WriterInfo = appended;
      v7 = v19;
      v9 = pv;
      if ( appended < 0 )
        goto LABEL_8;
      WriterInfo = BlbSafeDumpFile(v6, pv, *((unsigned int *)this + 84), v19);
      if ( WriterInfo < 0 )
        goto LABEL_8;
      if ( *((char *)this + 340) < 0 )
      {
        v13 = 0;
        if ( *((_BYTE *)this + 276) )
        {
          v14 = (CBlbFileVerifier *)operator new(0x40u);
          v24 = v14;
          if ( v14 )
            v13 = CBlbFileVerifier::CBlbFileVerifier(v14);
          WriterInfo = CBlbFileVerifier::Init(v13, v6);
          if ( WriterInfo < 0 )
            goto LABEL_71;
          v15 = -1;
          do
            ++v15;
          while ( v7[v15] );
          WriterInfo = CBlbFileVerifier::SetChecksumForData(v13, v7, 2 * v15 + 2);
          if ( WriterInfo < 0 )
          {
LABEL_71:
            if ( v13 )
              (**(void (__fastcall ***)(CBlbFileVerifier *, __int64))v13)(v13, 1);
            goto LABEL_7;
          }
          v16 = *((_QWORD *)this + 98);
          v23 = v16;
          if ( v16 >= *((_QWORD *)this + 99)
            && !(unsigned __int8)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
                                   (char *)this + 776,
                                   v16 + 1) )
          {
            ATL::AtlThrowImpl(-2147024882);
          }
          *(_QWORD *)(*((_QWORD *)this + 97) + 8 * v23) = v13;
          ++*((_QWORD *)this + 98);
        }
      }
      v2 = v20 + 1;
      v4 = v18;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 359, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  v8 = v18;
LABEL_7:
  v9 = pv;
LABEL_8:
  if ( v7 )
    CoTaskMemFree(v7);
  if ( v9 )
    CoTaskMemFree(v9);
  if ( v5 )
    CoTaskMemFree(v5);
  if ( v8 )
    CoTaskMemFree(v8);
  if ( v6 )
    CoTaskMemFree(v6);
  if ( WriterInfo < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 361, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  return (unsigned int)WriterInfo;
}

```

## disassembly

```asm
0x14003be8c  push    rbp
0x14003be8e  push    rbx
0x14003be8f  push    rsi
0x14003be90  push    rdi
0x14003be91  push    r12
0x14003be93  push    r13
0x14003be95  push    r14
0x14003be97  push    r15
0x14003be99  lea     rbp, [rsp-1Fh]
0x14003be9e  sub     rsp, 98h
0x14003bea5  mov     rax, cs:__security_cookie
0x14003beac  xor     rax, rsp
0x14003beaf  mov     [rbp+57h+var_50], rax
0x14003beb3  mov     rsi, rcx
0x14003beb6  xor     r12d, r12d
0x14003beb9  mov     ebx, r12d
0x14003bebc  xorps   xmm0, xmm0
0x14003bebf  movups  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x14003bec3  mov     r14d, r12d
0x14003bec6  mov     [rbp+57h+var_98], r12
0x14003beca  mov     r15d, r12d
0x14003becd  mov     [rbp+57h+lpFileName], r12
0x14003bed1  mov     r13d, r12d
0x14003bed4  mov     [rbp+57h+var_78], r12
0x14003bed8  mov     [rbp+57h+pv], r12
0x14003bedc  mov     edi, r12d
0x14003bedf  mov     [rbp+57h+var_90], r12
0x14003bee3  lea     rax, WPP_GLOBAL_Control
0x14003beea  cmp     [rcx+1C8h], r12
0x14003bef1  jnz     loc_14003BFCF
0x14003bef7  mov     rcx, cs:WPP_GLOBAL_Control
0x14003befe  cmp     rcx, rax
0x14003bf01  jz      short loc_14003BF24
0x14003bf03  test    byte ptr [rcx+1Ch], 1
0x14003bf07  jz      short loc_14003BF24
0x14003bf09  cmp     byte ptr [rcx+19h], 4
0x14003bf0d  jb      short loc_14003BF24
0x14003bf0f  mov     edx, 167h
0x14003bf14  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003bf1b  mov     rcx, [rcx+10h]
0x14003bf1f  call    WPP_SF_
0x14003bf24  mov     r12, [rbp+57h+var_98]
0x14003bf28  mov     r14, [rbp+57h+pv]
0x14003bf2c  lea     rsi, WPP_GLOBAL_Control
0x14003bf33  test    rdi, rdi
0x14003bf36  jz      short loc_14003BF41
0x14003bf38  mov     rcx, rdi; pv
0x14003bf3b  call    cs:__imp_CoTaskMemFree
0x14003bf41  test    r14, r14
0x14003bf44  jz      short loc_14003BF4F
0x14003bf46  mov     rcx, r14; pv
0x14003bf49  call    cs:__imp_CoTaskMemFree
0x14003bf4f  test    r15, r15
0x14003bf52  jz      short loc_14003BF5D
0x14003bf54  mov     rcx, r15; pv
0x14003bf57  call    cs:__imp_CoTaskMemFree
0x14003bf5d  test    r12, r12
0x14003bf60  jz      short loc_14003BF6B
0x14003bf62  mov     rcx, r12; pv
0x14003bf65  call    cs:__imp_CoTaskMemFree
0x14003bf6b  test    r13, r13
0x14003bf6e  jz      short loc_14003BF79
0x14003bf70  mov     rcx, r13; pv
0x14003bf73  call    cs:__imp_CoTaskMemFree
0x14003bf79  test    ebx, ebx
0x14003bf7b  jns     short loc_14003BFAD
0x14003bf7d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bf84  cmp     rcx, rsi
0x14003bf87  jz      short loc_14003BFAD
0x14003bf89  test    byte ptr [rcx+1Ch], 1
0x14003bf8d  jz      short loc_14003BFAD
0x14003bf8f  cmp     byte ptr [rcx+19h], 2
0x14003bf93  jb      short loc_14003BFAD
0x14003bf95  mov     edx, 169h
0x14003bf9a  mov     r9d, ebx
0x14003bf9d  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003bfa4  mov     rcx, [rcx+10h]
0x14003bfa8  call    WPP_SF_d
0x14003bfad  mov     eax, ebx
0x14003bfaf  mov     rcx, [rbp+57h+var_50]
0x14003bfb3  xor     rcx, rsp; StackCookie
0x14003bfb6  call    __security_check_cookie
0x14003bfbb  add     rsp, 98h
0x14003bfc2  pop     r15
0x14003bfc4  pop     r14
0x14003bfc6  pop     r13
0x14003bfc8  pop     r12
0x14003bfca  pop     rdi
0x14003bfcb  pop     rsi
0x14003bfcc  pop     rbx
0x14003bfcd  pop     rbp
0x14003bfce  retn
0x14003bfcf  mov     [rbp+57h+var_88], r12d
0x14003bfd3  mov     rax, [rsi+1C8h]
0x14003bfda  cmp     r12d, [rax+8]
0x14003bfde  jnb     loc_14003BF24
0x14003bfe4  test    rdi, rdi
0x14003bfe7  jz      short loc_14003BFF8
0x14003bfe9  mov     rcx, rdi; pv
0x14003bfec  call    cs:__imp_CoTaskMemFree
0x14003bff2  xor     edi, edi
0x14003bff4  mov     [rbp+57h+var_90], rdi
0x14003bff8  lea     r9, [rbp+57h+var_90]; unsigned __int16 **
0x14003bffc  lea     r8, [rbp+57h+var_60]; struct _GUID *
0x14003c000  mov     edx, r12d; unsigned int
0x14003c003  mov     rcx, [rsi+1C8h]; struct _SPP_METADATA_PROP *
0x14003c00a  call    ?BlbGetWriterInfo@@YAJPEAU_SPP_METADATA_PROP@@KPEAU_GUID@@PEAPEAG@Z; BlbGetWriterInfo(_SPP_METADATA_PROP *,ulong,_GUID *,ushort * *)
0x14003c00f  mov     ebx, eax
0x14003c011  test    eax, eax
0x14003c013  js      loc_14003C2AE
0x14003c019  cmp     [rsi+1D8h], rdi
0x14003c020  jnz     short loc_14003C03A
0x14003c022  lea     r8, aMWszbackupsetd; "m_wszBackupSetDirectory"
0x14003c029  mov     edx, 1D29h; unsigned int
0x14003c02e  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14003c035  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14003c03a  test    byte ptr [rsi+154h], 4
0x14003c041  jz      loc_14003C120
0x14003c047  test    r14, r14
0x14003c04a  jz      short loc_14003C059
0x14003c04c  mov     rcx, r14; pv
0x14003c04f  call    cs:__imp_CoTaskMemFree
0x14003c055  mov     [rbp+57h+var_98], rdi
0x14003c059  lea     rax, [rbp+57h+var_98]
0x14003c05d  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 **
0x14003c062  xor     r9d, r9d; unsigned __int8
0x14003c065  lea     r8, [rbp+57h+var_60]; UUID *
0x14003c069  xor     edx, edx; Uuid
0x14003c06b  mov     rcx, [rsi+1D8h]; unsigned __int16 *
0x14003c072  call    ?BlbAppendWriterMetadataFile@@YAJPEAGPEAU_GUID@@1EPEAPEAG@Z; BlbAppendWriterMetadataFile(ushort *,_GUID *,_GUID *,uchar,ushort * *)
0x14003c077  mov     ebx, eax
0x14003c079  test    eax, eax
0x14003c07b  js      loc_14003C2AE
0x14003c081  test    r15, r15
0x14003c084  jz      short loc_14003C093
0x14003c086  mov     rcx, r15; pv
0x14003c089  call    cs:__imp_CoTaskMemFree
0x14003c08f  mov     [rbp+57h+lpFileName], rdi
0x14003c093  lea     rdx, [rbp+57h+lpFileName]; unsigned __int16 **
0x14003c097  mov     r12, [rbp+57h+var_98]
0x14003c09b  mov     rcx, r12; unsigned __int16 *
0x14003c09e  call    ?BlbFindFile@@YAJPEAGPEAPEAG@Z; BlbFindFile(ushort *,ushort * *)
0x14003c0a3  mov     ebx, eax
0x14003c0a5  mov     r15, [rbp+57h+lpFileName]
0x14003c0a9  test    eax, eax
0x14003c0ab  js      loc_14003C2E7
0x14003c0b1  test    r15, r15
0x14003c0b4  jz      short loc_14003C124
0x14003c0b6  mov     rcx, r15; lpFileName
0x14003c0b9  call    cs:__imp_DeleteFileW
0x14003c0bf  test    eax, eax
0x14003c0c1  jnz     short loc_14003C124
0x14003c0c3  call    cs:__imp_GetLastError
0x14003c0c9  mov     ebx, eax
0x14003c0cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c0d2  lea     rsi, WPP_GLOBAL_Control
0x14003c0d9  cmp     rcx, rsi
0x14003c0dc  jz      short loc_14003C106
0x14003c0de  test    byte ptr [rcx+1Ch], 1
0x14003c0e2  jz      short loc_14003C106
0x14003c0e4  cmp     byte ptr [rcx+19h], 2
0x14003c0e8  jb      short loc_14003C106
0x14003c0ea  mov     edx, 168h
0x14003c0ef  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14003c0f3  mov     r9, r15
0x14003c0f6  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003c0fd  mov     rcx, [rcx+10h]
0x14003c101  call    WPP_SF_Sd
0x14003c106  test    ebx, ebx
0x14003c108  jle     short loc_14003C113
0x14003c10a  movzx   ebx, bx
0x14003c10d  or      ebx, 80070000h
0x14003c113  mov     rdi, [rbp+57h+var_90]
0x14003c117  mov     r14, [rbp+57h+pv]
0x14003c11b  jmp     loc_14003BF33
0x14003c120  mov     r12, [rbp+57h+var_98]
0x14003c124  test    r13, r13
0x14003c127  jz      short loc_14003C136
0x14003c129  mov     rcx, r13; pv
0x14003c12c  call    cs:__imp_CoTaskMemFree
0x14003c132  mov     [rbp+57h+var_78], rdi
0x14003c136  lea     rdi, [rsi+128h]
0x14003c13d  lea     rax, [rbp+57h+var_78]
0x14003c141  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 **
0x14003c146  xor     r9d, r9d; unsigned __int8
0x14003c149  lea     r8, [rbp+57h+var_60]; UUID *
0x14003c14d  mov     rdx, rdi; Uuid
0x14003c150  mov     rcx, [rsi+1D8h]; unsigned __int16 *
0x14003c157  call    ?BlbAppendWriterMetadataFile@@YAJPEAGPEAU_GUID@@1EPEAPEAG@Z; BlbAppendWriterMetadataFile(ushort *,_GUID *,_GUID *,uchar,ushort * *)
0x14003c15c  mov     ebx, eax
0x14003c15e  xor     r14d, r14d
0x14003c161  test    eax, eax
0x14003c163  js      loc_14003C2E3
0x14003c169  mov     rcx, [rbp+57h+pv]; pv
0x14003c16d  test    rcx, rcx
0x14003c170  jz      short loc_14003C17C
0x14003c172  call    cs:__imp_CoTaskMemFree
0x14003c178  mov     [rbp+57h+pv], r14
0x14003c17c  mov     r13, [rbp+57h+var_78]
0x14003c180  test    byte ptr [rsi+154h], 1
0x14003c187  jz      short loc_14003C19A
0x14003c189  xor     r8d, r8d; unsigned __int64
0x14003c18c  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x14003c190  mov     rcx, r13; unsigned __int16 *
0x14003c193  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14003c198  jmp     short loc_14003C1B9
0x14003c19a  lea     rax, [rbp+57h+pv]
0x14003c19e  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 **
0x14003c1a3  mov     r9b, 1; unsigned __int8
0x14003c1a6  lea     r8, [rbp+57h+var_60]; UUID *
0x14003c1aa  mov     rdx, rdi; Uuid
0x14003c1ad  mov     rcx, [rsi+1D8h]; unsigned __int16 *
0x14003c1b4  call    ?BlbAppendWriterMetadataFile@@YAJPEAGPEAU_GUID@@1EPEAPEAG@Z; BlbAppendWriterMetadataFile(ushort *,_GUID *,_GUID *,uchar,ushort * *)
0x14003c1b9  test    eax, eax
0x14003c1bb  mov     ebx, eax
0x14003c1bd  mov     rdi, [rbp+57h+var_90]
0x14003c1c1  mov     r14, [rbp+57h+pv]
0x14003c1c5  js      loc_14003BF2C
0x14003c1cb  mov     r9, rdi
0x14003c1ce  mov     r8d, [rsi+150h]
0x14003c1d5  mov     rdx, r14
0x14003c1d8  mov     rcx, r13
0x14003c1db  call    ?BlbSafeDumpFile@@YAJPEBG0W4_BLB_MEDIA_TYPE@@0@Z; BlbSafeDumpFile(ushort const *,ushort const *,_BLB_MEDIA_TYPE,ushort const *)
0x14003c1e0  mov     ebx, eax
0x14003c1e2  test    eax, eax
0x14003c1e4  js      loc_14003BF2C
0x14003c1ea  test    byte ptr [rsi+154h], 80h
0x14003c1f1  jz      loc_14003C29E
0x14003c1f7  xor     r14d, r14d
0x14003c1fa  cmp     [rsi+114h], r14b
0x14003c201  jz      loc_14003C29E
0x14003c207  lea     ecx, [r14+40h]; Size
0x14003c20b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003c210  mov     [rbp+57h+var_68], rax
0x14003c214  test    rax, rax
0x14003c217  jz      short loc_14003C224
0x14003c219  mov     rcx, rax; this
0x14003c21c  call    ??0CBlbFileVerifier@@QEAA@XZ; CBlbFileVerifier::CBlbFileVerifier(void)
0x14003c221  mov     r14, rax
0x14003c224  mov     rdx, r13; unsigned __int16 *
0x14003c227  mov     rcx, r14; this
0x14003c22a  call    ?Init@CBlbFileVerifier@@QEAAJPEAG@Z; CBlbFileVerifier::Init(ushort *)
0x14003c22f  mov     ebx, eax
0x14003c231  test    eax, eax
0x14003c233  js      loc_14003C2C2
0x14003c239  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003c23d  xor     ebx, ebx
0x14003c23f  inc     r8
0x14003c242  cmp     [rdi+r8*2], bx
0x14003c247  jnz     short loc_14003C23F
0x14003c249  lea     r8, ds:2[r8*2]; unsigned __int64
0x14003c251  mov     rdx, rdi; void *
0x14003c254  mov     rcx, r14; this
0x14003c257  call    ?SetChecksumForData@CBlbFileVerifier@@QEAAJPEAX_K@Z; CBlbFileVerifier::SetChecksumForData(void *,unsigned __int64)
0x14003c25c  mov     ebx, eax
0x14003c25e  test    eax, eax
0x14003c260  js      short loc_14003C2C2
0x14003c262  lea     r12, [rsi+308h]
0x14003c269  mov     rax, [rsi+310h]
0x14003c270  mov     [rbp+57h+var_70], rax
0x14003c274  cmp     rax, [rsi+318h]
0x14003c27b  jb      short loc_14003C28D
0x14003c27d  lea     rdx, [rax+1]
0x14003c281  mov     rcx, r12
0x14003c284  call    ?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(unsigned __int64)
0x14003c289  test    al, al
0x14003c28b  jz      short loc_14003C2B7
0x14003c28d  mov     rax, [r12]
0x14003c291  mov     rcx, [rbp+57h+var_70]
0x14003c295  mov     [rax+rcx*8], r14
0x14003c299  inc     qword ptr [r12+8]
0x14003c29e  mov     r12d, [rbp+57h+var_88]
0x14003c2a2  inc     r12d
0x14003c2a5  mov     r14, [rbp+57h+var_98]
0x14003c2a9  jmp     loc_14003BFCF
0x14003c2ae  mov     rdi, [rbp+57h+var_90]
0x14003c2b2  jmp     loc_14003BF24
0x14003c2b7  mov     ecx, 8007000Eh; int
0x14003c2bc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14003c2c2  test    r14, r14
0x14003c2c5  jz      loc_14003BF28
0x14003c2cb  mov     rax, [r14]
0x14003c2ce  mov     edx, 1
0x14003c2d3  mov     rcx, r14
0x14003c2d6  mov     rax, [rax]
0x14003c2d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c2de  jmp     loc_14003BF28
0x14003c2e3  mov     r13, [rbp+57h+var_78]
0x14003c2e7  mov     rdi, [rbp+57h+var_90]
0x14003c2eb  jmp     loc_14003BF28
```

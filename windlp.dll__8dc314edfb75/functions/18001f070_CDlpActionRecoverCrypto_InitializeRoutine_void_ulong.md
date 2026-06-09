# CDlpActionRecoverCrypto::InitializeRoutine(void *,ulong)

- ea: `0x18001f070`
- end: `0x18001f890`
- name: `?InitializeRoutine@CDlpActionRecoverCrypto@@EEAAJPEAXK@Z`
- size: `2080`
- prototype: `__int64 __fastcall(CDlpActionRecoverCrypto *__hidden this, void *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callees

- `0x180002898`
- `0x18000aba4`
- `0x18000ea20`
- `0x18000ff7c`
- `0x180012f5c`
- `0x18001f070`
- `0x18001fd60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f6c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f6e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f6c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f6e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f6ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f6ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f6f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f6f1`

## string_xrefs

- `0x18001f16a`: `RecoverCrypto: Initializing Wim Source Path: [%s]`
- `0x18001f18e`: `RecoverCrypto: Initializing Wim Target Path: [%s]`
- `0x18001f1b2`: `RecoverCrypto: Initializing Remote Source Path: [%s]`
- `0x18001f291`: `RecoverCrypto: Initializing DeleteSource Value: [%s]`
- `0x18001f814`: `Ignoring delete source directive. We are in FastEncryption mode`
- `0x18001f83b`: `Ignoring delete source directive. Only recovery has been requested`

## pseudocode

```c
__int64 __fastcall CDlpActionRecoverCrypto::InitializeRoutine(CDlpActionRecoverCrypto *this, _QWORD *a2, int a3)
{
  __int64 v5; // rcx
  int v6; // ebx
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rax
  const wchar_t *v10; // rbx
  const wchar_t *v11; // r9
  __int64 v12; // rcx
  const wchar_t *v13; // r9
  __int64 v14; // rcx
  const wchar_t *v15; // r9
  __int64 v16; // rcx
  const wchar_t *v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  const wchar_t *v23; // r9
  int v24; // eax
  __int64 v25; // rcx
  int v26; // eax
  _WORD *v27; // r15
  int StringCch; // eax
  _WORD *v29; // r15
  unsigned int v30; // edx
  int Internal; // eax
  _WORD *v32; // r15
  unsigned int v33; // edx
  int v34; // eax
  __int64 v35; // rdx
  _WORD *v36; // r15
  int v37; // eax
  int v38; // eax
  unsigned int v39; // r15d
  HANDLE ProcessHeap; // rax
  LPVOID v41; // rax
  __int64 v42; // rdx
  void *v43; // r12
  LPVOID v44; // rbx
  HANDLE v45; // rax
  __int64 v46; // rcx
  int v47; // eax
  unsigned int v48; // edx
  _WORD *v49; // r15
  int v50; // eax
  int v51; // eax
  __int64 v52; // rcx
  int v53; // eax
  __int64 v54; // rcx
  int v56; // [rsp+20h] [rbp-10h]
  int v57; // [rsp+28h] [rbp-8h]
  SIZE_T dwBytes; // [rsp+78h] [rbp+48h] BYREF
  unsigned int v59; // [rsp+88h] [rbp+58h] BYREF

  LODWORD(dwBytes) = 0;
  if ( !a2 )
  {
    v5 = *((_QWORD *)this + 11);
    v6 = -2147024809;
    if ( !v5 )
      goto LABEL_150;
    v57 = -2147024809;
    v56 = 464;
    goto LABEL_4;
  }
  if ( a3 != 88 )
  {
    v5 = *((_QWORD *)this + 11);
    v6 = -2147024809;
    if ( !v5 )
      goto LABEL_150;
    v57 = -2147024809;
    v56 = 465;
    goto LABEL_4;
  }
  v9 = WINDLP_ACTION_RECOVERCRYPTO - *a2;
  if ( (_QWORD)WINDLP_ACTION_RECOVERCRYPTO == *a2 )
    v9 = *((_QWORD *)&WINDLP_ACTION_RECOVERCRYPTO + 1) - a2[1];
  v5 = *((_QWORD *)this + 11);
  if ( v9 )
  {
    v6 = -2147024809;
    if ( !v5 )
      goto LABEL_150;
    v57 = -2147024809;
    v56 = 470;
    goto LABEL_4;
  }
  v10 = L"NULL";
  if ( v5 )
  {
    v11 = L"NULL";
    if ( a2[3] )
      v11 = (const wchar_t *)a2[3];
    CDlpLogT<CEmptyType>::DlpLogFormat(v5, 2u, (__int64)L"RecoverCrypto: Initializing Wim Source Path: [%s]", v11);
  }
  v12 = *((_QWORD *)this + 11);
  if ( v12 )
  {
    v13 = L"NULL";
    if ( a2[4] )
      v13 = (const wchar_t *)a2[4];
    CDlpLogT<CEmptyType>::DlpLogFormat(v12, 2u, (__int64)L"RecoverCrypto: Initializing Wim Target Path: [%s]", v13);
  }
  v14 = *((_QWORD *)this + 11);
  if ( v14 )
  {
    v15 = L"NULL";
    if ( a2[6] )
      v15 = (const wchar_t *)a2[6];
    CDlpLogT<CEmptyType>::DlpLogFormat(v14, 2u, (__int64)L"RecoverCrypto: Initializing Remote Source Path: [%s]", v15);
  }
  v16 = *((_QWORD *)this + 11);
  if ( v16 )
  {
    v17 = L"Yes";
    if ( !a2[5] )
      v17 = L"No";
    CDlpLogT<CEmptyType>::DlpLogFormat(v16, 2u, (__int64)L"RecoverCrypto: Initializing Crypto Key [%s]", v17);
  }
  v18 = *((_QWORD *)this + 11);
  if ( v18 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v18, 2u, (__int64)L"RecoverCrypto: Initializing Size: [0x%I64X]", a2[2]);
  v19 = *((_QWORD *)this + 11);
  if ( v19 )
    CDlpLogT<CEmptyType>::DlpLogFormat(
      v19,
      2u,
      (__int64)L"RecoverCrypto: Initializing Flags: [0x%X]",
      *((unsigned int *)a2 + 18));
  v20 = *((_QWORD *)this + 11);
  if ( v20 )
    CDlpLogT<CEmptyType>::DlpLogFormat(
      v20,
      2u,
      (__int64)L"RecoverCrypto: Initializing Hash Type: [%u]",
      *((unsigned int *)a2 + 14));
  v21 = *((_QWORD *)this + 11);
  if ( v21 )
  {
    if ( a2[8] )
      v10 = (const wchar_t *)a2[8];
    CDlpLogT<CEmptyType>::DlpLogFormat(v21, 2u, (__int64)L"RecoverCrypto: Initializing Hash Value: [%s]", v10);
  }
  v22 = *((_QWORD *)this + 11);
  if ( v22 )
  {
    v23 = L"TRUE";
    if ( !*((_DWORD *)a2 + 20) )
      v23 = L"FALSE";
    CDlpLogT<CEmptyType>::DlpLogFormat(v22, 2u, (__int64)L"RecoverCrypto: Initializing DeleteSource Value: [%s]", v23);
  }
  v24 = *((_DWORD *)a2 + 18);
  if ( (v24 & 0xFFFFFFE8) != 0 )
  {
    v5 = *((_QWORD *)this + 11);
    v6 = -2147024809;
    if ( !v5 )
      goto LABEL_150;
    v57 = -2147024809;
    v56 = 504;
    goto LABEL_4;
  }
  if ( (v24 & 2) != 0 && (v24 & 4) != 0 )
  {
    v5 = *((_QWORD *)this + 11);
    v6 = -2147024809;
    if ( !v5 )
      goto LABEL_150;
    v57 = -2147024809;
    v56 = 507;
    goto LABEL_4;
  }
  if ( (v24 & 0x10) != 0 && (v24 & 2) == 0 && (v24 & 4) == 0 )
  {
    v5 = *((_QWORD *)this + 11);
    v6 = -2147024809;
    if ( !v5 )
      goto LABEL_150;
    v57 = -2147024809;
    v56 = 511;
    goto LABEL_4;
  }
  if ( (v24 & 1) != 0 )
  {
    if ( *((_DWORD *)a2 + 14) > 1u )
    {
      v5 = *((_QWORD *)this + 11);
      v6 = -2147024809;
      if ( !v5 )
        goto LABEL_150;
      v57 = -2147024809;
      v56 = 519;
      goto LABEL_4;
    }
    v25 = a2[8];
    if ( !v25 )
    {
      v5 = *((_QWORD *)this + 11);
      v6 = -2147024809;
      if ( !v5 )
        goto LABEL_150;
      v57 = -2147024809;
      v56 = 523;
      goto LABEL_4;
    }
    v26 = CHexEncodingT<CEmptyType>::DecodeDataInternal(v25, v24 & 2, 0, &dwBytes);
    v6 = v26;
    if ( v26 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v26);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
    if ( v6 < 0 )
    {
      v5 = *((_QWORD *)this + 11);
      if ( !v5 )
        goto LABEL_150;
      v57 = v6;
      v56 = 529;
      goto LABEL_4;
    }
    if ( *((_DWORD *)a2 + 14) )
    {
      if ( (_DWORD)dwBytes != 32 )
      {
        v5 = *((_QWORD *)this + 11);
        v6 = -2147024809;
        if ( !v5 )
          goto LABEL_150;
        v57 = -2147024809;
        v56 = 536;
        goto LABEL_4;
      }
    }
    else if ( (_DWORD)dwBytes != 20 )
    {
      v5 = *((_QWORD *)this + 11);
      v6 = -2147024809;
      if ( !v5 )
        goto LABEL_150;
      v57 = -2147024809;
      v56 = 532;
      goto LABEL_4;
    }
    if ( !a2[6] )
    {
      v5 = *((_QWORD *)this + 11);
      v6 = -2147024809;
      if ( !v5 )
        goto LABEL_150;
      v57 = -2147024809;
      v56 = 541;
      goto LABEL_4;
    }
    if ( !a2[2] )
    {
      v5 = *((_QWORD *)this + 11);
      v6 = -2147024809;
      if ( !v5 )
        goto LABEL_150;
      v57 = -2147024809;
      v56 = 545;
      goto LABEL_4;
    }
  }
  v27 = (_WORD *)a2[3];
  if ( !v27 )
  {
    v5 = *((_QWORD *)this + 11);
    v6 = -2147024809;
    if ( !v5 )
      goto LABEL_150;
    v57 = -2147024809;
    v56 = 550;
    goto LABEL_4;
  }
  v59 = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v27, &v59);
  v6 = StringCch;
  if ( StringCch < 0
    || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                      v27,
                      v59,
                      (_QWORD *)this + 69),
        v6 = StringCch,
        StringCch < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v6 < 0 )
  {
    v5 = *((_QWORD *)this + 11);
    if ( !v5 )
      goto LABEL_150;
    v57 = v6;
    v56 = 554;
    goto LABEL_4;
  }
  v29 = (_WORD *)a2[4];
  v30 = 0;
  v59 = 0;
  if ( !v29 )
  {
LABEL_94:
    Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                 v29,
                 v30,
                 (_QWORD *)this + 70);
    v6 = Internal;
    if ( Internal >= 0 )
      goto LABEL_96;
    goto LABEL_95;
  }
  Internal = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v29, &v59);
  v6 = Internal;
  if ( Internal >= 0 )
  {
    v30 = v59;
    goto LABEL_94;
  }
LABEL_95:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(Internal);
LABEL_96:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v6 < 0 )
  {
    v5 = *((_QWORD *)this + 11);
    if ( !v5 )
      goto LABEL_150;
    v57 = v6;
    v56 = 555;
    goto LABEL_4;
  }
  v32 = (_WORD *)a2[6];
  v33 = 0;
  v59 = 0;
  if ( !v32 )
  {
LABEL_102:
    v34 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
            v32,
            v33,
            (_QWORD *)this + 71);
    v6 = v34;
    if ( v34 >= 0 )
      goto LABEL_104;
    goto LABEL_103;
  }
  v34 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v32, &v59);
  v6 = v34;
  if ( v34 >= 0 )
  {
    v33 = v59;
    goto LABEL_102;
  }
LABEL_103:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v34);
LABEL_104:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v6 < 0 )
  {
    v5 = *((_QWORD *)this + 11);
    if ( !v5 )
      goto LABEL_150;
    v57 = v6;
    v56 = 556;
    goto LABEL_4;
  }
  v36 = (_WORD *)a2[5];
  if ( v36 )
  {
    v59 = 0;
    v37 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v36, &v59);
    v6 = v37;
    if ( v37 < 0
      || (v37 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                  v36,
                  v59,
                  (_QWORD *)this + 72),
          v6 = v37,
          v37 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v37);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
    if ( v6 < 0 )
    {
      v5 = *((_QWORD *)this + 11);
      if ( !v5 )
        goto LABEL_150;
      v57 = v6;
      v56 = 560;
      goto LABEL_4;
    }
  }
  *((_DWORD *)this + 158) = *((_DWORD *)a2 + 18);
  *((_QWORD *)this + 90) = a2[2];
  if ( (a2[9] & 1) == 0 )
    goto LABEL_138;
  *((_DWORD *)this + 162) = *((_DWORD *)a2 + 14);
  v38 = CHexEncodingT<CEmptyType>::DecodeDataInternal(a2[8], v35, 0, &dwBytes);
  v6 = v38;
  if ( v38 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v38);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v6 < 0 )
  {
    v5 = *((_QWORD *)this + 11);
    if ( !v5 )
      goto LABEL_150;
    v57 = v6;
    v56 = 574;
    goto LABEL_4;
  }
  v39 = dwBytes;
  ProcessHeap = GetProcessHeap();
  v41 = HeapAlloc(ProcessHeap, 0, v39);
  v43 = (void *)*((_QWORD *)this + 73);
  v44 = v41;
  if ( v43 )
  {
    v45 = GetProcessHeap();
    HeapFree(v45, 0, v43);
  }
  if ( !v44 )
  {
    *((_QWORD *)this + 73) = 0;
    v6 = -2147024882;
    v5 = *((_QWORD *)this + 11);
    if ( !v5 )
      goto LABEL_150;
    v57 = -2147024882;
    v56 = 576;
    goto LABEL_4;
  }
  *((_QWORD *)this + 73) = v44;
  v46 = a2[8];
  LODWORD(dwBytes) = v39;
  v47 = CHexEncodingT<CEmptyType>::DecodeDataInternal(v46, v42, v44, &dwBytes);
  v6 = v47;
  if ( v47 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v47);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v6 < 0 )
  {
    v5 = *((_QWORD *)this + 11);
    if ( !v5 )
      goto LABEL_150;
    v57 = v6;
    v56 = 578;
    goto LABEL_4;
  }
  *((_DWORD *)this + 161) = v39;
  v48 = 0;
  v49 = (_WORD *)a2[8];
  LODWORD(dwBytes) = 0;
  if ( !v49 )
  {
LABEL_133:
    v50 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
            v49,
            v48,
            (_QWORD *)this + 74);
    v6 = v50;
    if ( v50 >= 0 )
      goto LABEL_135;
    goto LABEL_134;
  }
  v50 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v49, &dwBytes);
  v6 = v50;
  if ( v50 >= 0 )
  {
    v48 = dwBytes;
    goto LABEL_133;
  }
LABEL_134:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v50);
LABEL_135:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v6 < 0 )
  {
    v5 = *((_QWORD *)this + 11);
    if ( !v5 )
      goto LABEL_150;
    v57 = v6;
    v56 = 583;
LABEL_4:
    v7 = CDlpLogT<CEmptyType>::DlpLogFormat(
           v5,
           4u,
           (__int64)L"%s(%d): Result = 0x%X",
           L"CDlpActionRecoverCrypto::InitializeRoutine",
           v56,
           v57);
    v8 = (unsigned int)v7;
    if ( v7 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
    goto LABEL_150;
  }
LABEL_138:
  v51 = 2;
  if ( *((_DWORD *)a2 + 19) )
    v51 = *((_DWORD *)a2 + 19);
  *((_DWORD *)this + 185) = v51;
  if ( (a2[9] & 0x10) != 0 )
  {
    v52 = *((_QWORD *)this + 11);
    *((_DWORD *)this + 159) = 0;
    if ( v52 )
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v52,
        2u,
        (__int64)L"Ignoring delete source directive. We are in FastEncryption mode");
  }
  else
  {
    v53 = *((_DWORD *)a2 + 20);
    if ( (a2[9] & 6) != 0 )
    {
      *((_DWORD *)this + 159) = v53;
    }
    else
    {
      if ( v53 )
      {
        v54 = *((_QWORD *)this + 11);
        if ( v54 )
          CDlpLogT<CEmptyType>::DlpLogFormat(
            v54,
            2u,
            (__int64)L"Ignoring delete source directive. Only recovery has been requested");
      }
      *((_DWORD *)this + 159) = 0;
    }
  }
  *((_DWORD *)this + 170) = 10000;
  *((_DWORD *)this + 184) = -1;
  *((_DWORD *)this + 183) = -1;
LABEL_150:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001f070  mov     [rsp-38h+arg_0], rbx
0x18001f075  push    rbp
0x18001f076  push    rsi
0x18001f077  push    rdi
0x18001f078  push    r12
0x18001f07a  push    r13
0x18001f07c  push    r14
0x18001f07e  push    r15
0x18001f080  mov     rbp, rsp
0x18001f083  sub     rsp, 30h
0x18001f087  xor     r13d, r13d
0x18001f08a  mov     rsi, rdx
0x18001f08d  mov     dword ptr [rbp+dwBytes], r13d
0x18001f091  mov     rdi, rcx
0x18001f094  test    rdx, rdx
0x18001f097  jnz     short loc_18001F0E6
0x18001f099  mov     rcx, [rcx+58h]
0x18001f09d  mov     eax, 80070057h
0x18001f0a2  mov     ebx, eax
0x18001f0a4  test    rcx, rcx
0x18001f0a7  jz      loc_18001F872
0x18001f0ad  mov     [rsp+30h+var_8], eax
0x18001f0b1  mov     [rsp+30h+var_10], 1D0h
0x18001f0b9  mov     edx, 4
0x18001f0be  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18001f0c5  lea     r9, aCdlpactionreco_4; "CDlpActionRecoverCrypto::InitializeRout"...
0x18001f0cc  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001f0d1  mov     ecx, eax
0x18001f0d3  test    eax, eax
0x18001f0d5  jns     short loc_18001F0DC
0x18001f0d7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001f0dc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001f0e1  jmp     loc_18001F872
0x18001f0e6  cmp     r8d, 58h ; 'X'
0x18001f0ea  jz      short loc_18001F10E
0x18001f0ec  mov     rcx, [rcx+58h]
0x18001f0f0  mov     eax, 80070057h
0x18001f0f5  mov     ebx, eax
0x18001f0f7  test    rcx, rcx
0x18001f0fa  jz      loc_18001F872
0x18001f100  mov     [rsp+30h+var_8], eax
0x18001f104  mov     [rsp+30h+var_10], 1D1h
0x18001f10c  jmp     short loc_18001F0B9
0x18001f10e  mov     rax, qword ptr cs:WINDLP_ACTION_RECOVERCRYPTO
0x18001f115  sub     rax, [rdx]
0x18001f118  jnz     short loc_18001F125
0x18001f11a  mov     rax, qword ptr cs:WINDLP_ACTION_RECOVERCRYPTO+8
0x18001f121  sub     rax, [rdx+8]
0x18001f125  mov     rcx, [rcx+58h]
0x18001f129  test    rax, rax
0x18001f12c  setz    al
0x18001f12f  test    al, al
0x18001f131  jnz     short loc_18001F154
0x18001f133  mov     eax, 80070057h
0x18001f138  mov     ebx, eax
0x18001f13a  test    rcx, rcx
0x18001f13d  jz      loc_18001F872
0x18001f143  mov     [rsp+30h+var_8], eax
0x18001f147  mov     [rsp+30h+var_10], 1D6h
0x18001f14f  jmp     loc_18001F0B9
0x18001f154  lea     rbx, aNull; "NULL"
0x18001f15b  mov     r12d, 2
0x18001f161  test    rcx, rcx
0x18001f164  jz      short loc_18001F181
0x18001f166  cmp     [rdx+18h], r13
0x18001f16a  lea     r8, aRecovercryptoI_6; "RecoverCrypto: Initializing Wim Source "...
0x18001f171  mov     r9, rbx
0x18001f174  cmovnz  r9, [rdx+18h]
0x18001f179  mov     edx, r12d
0x18001f17c  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001f181  mov     rcx, [rdi+58h]
0x18001f185  test    rcx, rcx
0x18001f188  jz      short loc_18001F1A5
0x18001f18a  cmp     [rsi+20h], r13
0x18001f18e  lea     r8, aRecovercryptoI_0; "RecoverCrypto: Initializing Wim Target "...
0x18001f195  mov     r9, rbx
0x18001f198  mov     edx, r12d
0x18001f19b  cmovnz  r9, [rsi+20h]
0x18001f1a0  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001f1a5  mov     rcx, [rdi+58h]
0x18001f1a9  test    rcx, rcx
0x18001f1ac  jz      short loc_18001F1C9
0x18001f1ae  cmp     [rsi+30h], r13
0x18001f1b2  lea     r8, aRecovercryptoI_1; "RecoverCrypto: Initializing Remote Sour"...
0x18001f1b9  mov     r9, rbx
0x18001f1bc  mov     edx, r12d
0x18001f1bf  cmovnz  r9, [rsi+30h]
0x18001f1c4  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001f1c9  mov     rcx, [rdi+58h]
0x18001f1cd  test    rcx, rcx
0x18001f1d0  jz      short loc_18001F1F7
0x18001f1d2  cmp     [rsi+28h], r13
0x18001f1d6  lea     rax, aNo; "No"
0x18001f1dd  lea     r9, aYes; "Yes"
0x18001f1e4  mov     edx, r12d
0x18001f1e7  cmovz   r9, rax
0x18001f1eb  lea     r8, aRecovercryptoI_5; "RecoverCrypto: Initializing Crypto Key "...
0x18001f1f2  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001f1f7  mov     rcx, [rdi+58h]
0x18001f1fb  test    rcx, rcx
0x18001f1fe  jz      short loc_18001F213
0x18001f200  mov     r9, [rsi+10h]
0x18001f204  lea     r8, aRecovercryptoI_2; "RecoverCrypto: Initializing Size: [0x%I"...
0x18001f20b  mov     edx, r12d
0x18001f20e  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001f213  mov     rcx, [rdi+58h]
0x18001f217  test    rcx, rcx
0x18001f21a  jz      short loc_18001F22F
0x18001f21c  mov     r9d, [rsi+48h]
0x18001f220  lea     r8, aRecovercryptoI_3; "RecoverCrypto: Initializing Flags: [0x%"...
0x18001f227  mov     edx, r12d
0x18001f22a  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001f22f  mov     rcx, [rdi+58h]
0x18001f233  test    rcx, rcx
0x18001f236  jz      short loc_18001F24B
0x18001f238  mov     r9d, [rsi+38h]
0x18001f23c  lea     r8, aRecovercryptoI_7; "RecoverCrypto: Initializing Hash Type: "...
0x18001f243  mov     edx, r12d
0x18001f246  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001f24b  mov     rcx, [rdi+58h]
0x18001f24f  test    rcx, rcx
0x18001f252  jz      short loc_18001F26F
0x18001f254  cmp     [rsi+40h], r13
0x18001f258  lea     r8, aRecovercryptoI_4; "RecoverCrypto: Initializing Hash Value:"...
0x18001f25f  mov     edx, r12d
0x18001f262  cmovnz  rbx, [rsi+40h]
0x18001f267  mov     r9, rbx
0x18001f26a  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001f26f  mov     rcx, [rdi+58h]
0x18001f273  test    rcx, rcx
0x18001f276  jz      short loc_18001F29D
0x18001f278  cmp     [rsi+50h], r13d
0x18001f27c  lea     rax, aFalse; "FALSE"
0x18001f283  lea     r9, aTrue_0; "TRUE"
0x18001f28a  mov     edx, r12d
0x18001f28d  cmovz   r9, rax
0x18001f291  lea     r8, aRecovercryptoI_8; "RecoverCrypto: Initializing DeleteSourc"...
0x18001f298  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001f29d  mov     eax, [rsi+48h]
0x18001f2a0  test    eax, 0FFFFFFE8h
0x18001f2a5  jz      short loc_18001F2CC
0x18001f2a7  mov     rcx, [rdi+58h]
0x18001f2ab  mov     eax, 80070057h
0x18001f2b0  mov     ebx, eax
0x18001f2b2  test    rcx, rcx
0x18001f2b5  jz      loc_18001F872
0x18001f2bb  mov     [rsp+30h+var_8], eax
0x18001f2bf  mov     [rsp+30h+var_10], 1F8h
0x18001f2c7  jmp     loc_18001F0B9
0x18001f2cc  mov     ecx, eax
0x18001f2ce  mov     r14d, 4
0x18001f2d4  and     ecx, r14d
0x18001f2d7  mov     edx, eax
0x18001f2d9  and     edx, r12d
0x18001f2dc  jz      short loc_18001F30A
0x18001f2de  test    ecx, ecx
0x18001f2e0  jz      short loc_18001F30A
0x18001f2e2  mov     rcx, [rdi+58h]
0x18001f2e6  mov     eax, 80070057h
0x18001f2eb  mov     ebx, eax
0x18001f2ed  test    rcx, rcx
0x18001f2f0  jz      loc_18001F872
0x18001f2f6  mov     [rsp+30h+var_8], eax
0x18001f2fa  mov     [rsp+30h+var_10], 1FBh
0x18001f302  mov     edx, r14d
0x18001f305  jmp     loc_18001F0BE
0x18001f30a  test    al, 10h
0x18001f30c  jz      short loc_18001F338
0x18001f30e  test    edx, edx
0x18001f310  jnz     short loc_18001F338
0x18001f312  test    ecx, ecx
0x18001f314  jnz     short loc_18001F338
0x18001f316  mov     rcx, [rdi+58h]
0x18001f31a  mov     eax, 80070057h
0x18001f31f  mov     ebx, eax
0x18001f321  test    rcx, rcx
0x18001f324  jz      loc_18001F872
0x18001f32a  mov     [rsp+30h+var_8], eax
0x18001f32e  mov     [rsp+30h+var_10], 1FFh
0x18001f336  jmp     short loc_18001F302
0x18001f338  test    al, 1
0x18001f33a  jz      loc_18001F48A
0x18001f340  cmp     dword ptr [rsi+38h], 1
0x18001f344  jbe     short loc_18001F368
0x18001f346  mov     rcx, [rdi+58h]
0x18001f34a  mov     eax, 80070057h
0x18001f34f  mov     ebx, eax
0x18001f351  test    rcx, rcx
0x18001f354  jz      loc_18001F872
0x18001f35a  mov     [rsp+30h+var_8], eax
0x18001f35e  mov     [rsp+30h+var_10], 207h
0x18001f366  jmp     short loc_18001F302
0x18001f368  mov     rcx, [rsi+40h]
0x18001f36c  test    rcx, rcx
0x18001f36f  jnz     short loc_18001F396
0x18001f371  mov     rcx, [rdi+58h]
0x18001f375  mov     eax, 80070057h
0x18001f37a  mov     ebx, eax
0x18001f37c  test    rcx, rcx
0x18001f37f  jz      loc_18001F872
0x18001f385  mov     [rsp+30h+var_8], eax
0x18001f389  mov     [rsp+30h+var_10], 20Bh
0x18001f391  jmp     loc_18001F302
0x18001f396  lea     r9, [rbp+dwBytes]
0x18001f39a  xor     r8d, r8d
0x18001f39d  call    ?DecodeDataInternal@?$CHexEncodingT@VCEmptyType@@@@CAJPEBGPEA_KPEAXPEAI@Z; CHexEncodingT<CEmptyType>::DecodeDataInternal(ushort const *,unsigned __int64 *,void *,uint *)
0x18001f3a2  mov     ebx, eax
0x18001f3a4  test    eax, eax
0x18001f3a6  jns     short loc_18001F3AF
0x18001f3a8  mov     ecx, eax
0x18001f3aa  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001f3af  mov     ecx, ebx
0x18001f3b1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001f3b6  test    ebx, ebx
0x18001f3b8  jns     short loc_18001F3D8
0x18001f3ba  mov     rcx, [rdi+58h]
0x18001f3be  test    rcx, rcx
0x18001f3c1  jz      loc_18001F872
0x18001f3c7  mov     [rsp+30h+var_8], ebx
0x18001f3cb  mov     [rsp+30h+var_10], 211h
0x18001f3d3  jmp     loc_18001F302
0x18001f3d8  cmp     [rsi+38h], r13d
0x18001f3dc  jnz     short loc_18001F409
0x18001f3de  cmp     dword ptr [rbp+dwBytes], 14h
0x18001f3e2  jz      short loc_18001F434
0x18001f3e4  mov     rcx, [rdi+58h]
0x18001f3e8  mov     eax, 80070057h
0x18001f3ed  mov     ebx, eax
0x18001f3ef  test    rcx, rcx
0x18001f3f2  jz      loc_18001F872
0x18001f3f8  mov     [rsp+30h+var_8], eax
0x18001f3fc  mov     [rsp+30h+var_10], 214h
0x18001f404  jmp     loc_18001F302
0x18001f409  cmp     dword ptr [rbp+dwBytes], 20h ; ' '
0x18001f40d  jz      short loc_18001F434
0x18001f40f  mov     rcx, [rdi+58h]
0x18001f413  mov     eax, 80070057h
0x18001f418  mov     ebx, eax
0x18001f41a  test    rcx, rcx
0x18001f41d  jz      loc_18001F872
0x18001f423  mov     [rsp+30h+var_8], eax
0x18001f427  mov     [rsp+30h+var_10], 218h
0x18001f42f  jmp     loc_18001F302
0x18001f434  cmp     [rsi+30h], r13
0x18001f438  jnz     short loc_18001F45F
0x18001f43a  mov     rcx, [rdi+58h]
0x18001f43e  mov     eax, 80070057h
0x18001f443  mov     ebx, eax
0x18001f445  test    rcx, rcx
0x18001f448  jz      loc_18001F872
0x18001f44e  mov     [rsp+30h+var_8], eax
0x18001f452  mov     [rsp+30h+var_10], 21Dh
0x18001f45a  jmp     loc_18001F302
0x18001f45f  cmp     [rsi+10h], r13
0x18001f463  jnz     short loc_18001F48A
0x18001f465  mov     rcx, [rdi+58h]
0x18001f469  mov     eax, 80070057h
0x18001f46e  mov     ebx, eax
0x18001f470  test    rcx, rcx
0x18001f473  jz      loc_18001F872
0x18001f479  mov     [rsp+30h+var_8], eax
0x18001f47d  mov     [rsp+30h+var_10], 221h
0x18001f485  jmp     loc_18001F302
0x18001f48a  mov     r15, [rsi+18h]
0x18001f48e  test    r15, r15
0x18001f491  jnz     short loc_18001F4B8
0x18001f493  mov     rcx, [rdi+58h]
0x18001f497  mov     eax, 80070057h
0x18001f49c  mov     ebx, eax
0x18001f49e  test    rcx, rcx
0x18001f4a1  jz      loc_18001F872
0x18001f4a7  mov     [rsp+30h+var_8], eax
0x18001f4ab  mov     [rsp+30h+var_10], 226h
0x18001f4b3  jmp     loc_18001F302
0x18001f4b8  lea     rdx, [rbp+arg_18]
0x18001f4bc  mov     [rbp+arg_18], r13d
0x18001f4c0  mov     rcx, r15
0x18001f4c3  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18001f4c8  mov     ebx, eax
0x18001f4ca  test    eax, eax
0x18001f4cc  js      short loc_18001F4E6
0x18001f4ce  mov     edx, [rbp+arg_18]
0x18001f4d1  lea     r8, [rdi+228h]
0x18001f4d8  mov     rcx, r15; Src
0x18001f4db  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18001f4e0  mov     ebx, eax
0x18001f4e2  test    eax, eax
0x18001f4e4  jns     short loc_18001F4ED
0x18001f4e6  mov     ecx, eax
0x18001f4e8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001f4ed  mov     ecx, ebx
0x18001f4ef  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001f4f4  test    ebx, ebx
0x18001f4f6  jns     short loc_18001F516
0x18001f4f8  mov     rcx, [rdi+58h]
0x18001f4fc  test    rcx, rcx
0x18001f4ff  jz      loc_18001F872
0x18001f505  mov     [rsp+30h+var_8], ebx
0x18001f509  mov     [rsp+30h+var_10], 22Ah
0x18001f511  jmp     loc_18001F302
  ... truncated ...
```

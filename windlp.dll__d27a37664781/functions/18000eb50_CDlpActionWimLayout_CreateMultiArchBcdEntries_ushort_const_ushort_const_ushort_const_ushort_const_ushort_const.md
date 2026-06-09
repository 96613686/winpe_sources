# CDlpActionWimLayout::CreateMultiArchBcdEntries(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000eb50`
- end: `0x18000efaf`
- name: `?CreateMultiArchBcdEntries@CDlpActionWimLayout@@AEAAJPEBG0000@Z`
- size: `1119`
- prototype: `int(CDlpActionWimLayout *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180006700`

## callees

- `0x180001ba8`
- `0x180007974`
- `0x1800097ec`
- `0x18000aba4`
- `0x18000bd74`
- `0x18000eb50`
- `0x180012f5c`
- `0x18001b95c`
- `0x18001cdb0`
- `0x18001ce28`
- `0x18001fd60`
- `0x18002b0b4`
- `0x18002b240`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `bcd!BcdCloseObject` at `0x18000ed4e`
- `bcd!BcdCloseObject` at `0x18000ee2e`
- `bcd!BcdCloseObject` at `0x18000ed4e`
- `bcd!BcdCloseObject` at `0x18000ee2e`
- `bcd!BcdOpenObject` at `0x18000ece1`
- `bcd!BcdOpenObject` at `0x18000edcd`
- `bcd!BcdOpenObject` at `0x18000ece1`
- `bcd!BcdOpenObject` at `0x18000edcd`
- `bcd!BcdGetElementData` at `0x18000ed1c`
- `bcd!BcdGetElementData` at `0x18000ed1c`
- `bcd!BcdOpenStoreFromFile` at `0x18000ec33`
- `bcd!BcdOpenStoreFromFile` at `0x18000ec33`
- `bcd!BcdSetElementData` at `0x18000edfe`
- `bcd!BcdSetElementData` at `0x18000edfe`

## string_xrefs

- `0x18000ef48`: `CDlpActionWimLayout::CreateMultiArchBcdEntries`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDlpActionWimLayout::CreateMultiArchBcdEntries(
        CDlpActionWimLayout *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  CBcdUtils *v8; // rsi
  char *v9; // r15
  char *v10; // rbx
  int NtFilePathFromWin32Path; // eax
  unsigned int v12; // edi
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  int ElementData; // eax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  __int64 v34; // rcx
  int v36; // [rsp+20h] [rbp-69h]
  unsigned int v37; // [rsp+28h] [rbp-61h]
  int v38; // [rsp+30h] [rbp-59h] BYREF
  char *v39; // [rsp+38h] [rbp-51h] BYREF
  __int64 v40; // [rsp+40h] [rbp-49h] BYREF
  char *v41; // [rsp+48h] [rbp-41h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-39h] BYREF
  struct _GUID v43; // [rsp+60h] [rbp-29h] BYREF
  struct _GUID v44; // [rsp+70h] [rbp-19h] BYREF

  v43 = 0;
  v44 = 0;
  v8 = 0;
  v41 = 0;
  DestinationString = 0;
  v9 = (char *)operator new(0x50u);
  v39 = v9;
  if ( !v9 )
  {
    v10 = 0;
    v12 = -2147024882;
LABEL_7:
    v13 = v12;
    goto LABEL_8;
  }
  *(_QWORD *)v9 = &CUnknownImpl<IUnknown>::`vftable';
  *((_QWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 2) = 0;
  *(_OWORD *)(v9 + 24) = 0;
  *(_OWORD *)(v9 + 40) = 0;
  *(_OWORD *)(v9 + 56) = 0;
  CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(v9 + 24));
  CDword::Init((CDword *)(v9 + 8), 0);
  CDword::Init((CDword *)(v9 + 8), 1u);
  *(_QWORD *)v9 = &CBcdUtils::`vftable';
  *((_QWORD *)v9 + 9) = 0;
  v10 = v9;
  v39 = v9;
  NtFilePathFromWin32Path = GetNtFilePathFromWin32Path(a2, &DestinationString);
  v12 = NtFilePathFromWin32Path;
  v38 = NtFilePathFromWin32Path;
  if ( NtFilePathFromWin32Path >= 0 )
  {
    v14 = BcdOpenStoreFromFile(&DestinationString, v9 + 72);
    v15 = SErrorConverter::C_NtStatus2HR(v14, &v38);
    v12 = v38;
    if ( v15 )
    {
      v10 = 0;
      v8 = (CBcdUtils *)v9;
      v41 = v9;
      goto LABEL_9;
    }
    goto LABEL_7;
  }
  v13 = (unsigned int)NtFilePathFromWin32Path;
LABEL_8:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
LABEL_9:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
  if ( v10 )
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v10 + 24LL))(v10, 1);
  if ( (v12 & 0x80000000) != 0 )
  {
    v16 = *((_QWORD *)this + 11);
    if ( !v16 )
      goto LABEL_60;
    v37 = v12;
    v36 = 1106;
    goto LABEL_57;
  }
  v39 = 0;
  LODWORD(v40) = 0;
  DestinationString = 0;
  v38 = 0;
  v17 = *((_QWORD *)v8 + 9);
  if ( !v17 )
  {
    v12 = -2147483638;
    v18 = 2147483658LL;
LABEL_16:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v18);
    goto LABEL_22;
  }
  v19 = BcdOpenObject(v17, &GUID_WINDOWS_BOOTMGR, &v39);
  if ( !(unsigned int)SErrorConverter::C_NtStatus2HR(v19, &v38) )
  {
    v12 = v38;
LABEL_19:
    v18 = v12;
    goto LABEL_16;
  }
  DestinationString = 0;
  LODWORD(v40) = 16;
  ElementData = BcdGetElementData(v39, 587202563, &DestinationString, &v40);
  v21 = SErrorConverter::C_NtStatus2HR(ElementData, &v38);
  v12 = v38;
  if ( !v21 )
    goto LABEL_19;
  v43 = (struct _GUID)DestinationString;
LABEL_22:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
  if ( v39 )
    BcdCloseObject();
  if ( (v12 & 0x80000000) != 0 )
  {
    v16 = *((_QWORD *)this + 11);
    if ( !v16 )
      goto LABEL_60;
    v37 = v12;
    v36 = 1110;
    goto LABEL_57;
  }
  v22 = CBcdUtils::SetBootEntryDescription(v8, &v43, a4);
  v12 = v22;
  if ( v22 < 0 )
  {
    v16 = *((_QWORD *)this + 11);
    if ( !v16 )
      goto LABEL_60;
    v37 = v22;
    v36 = 1111;
    goto LABEL_57;
  }
  v40 = 0;
  v39 = 0;
  v38 = 0;
  v23 = *((_QWORD *)v8 + 9);
  if ( v23 )
  {
    v25 = BcdOpenObject(v23, &v43, &v39);
    if ( (unsigned int)SErrorConverter::C_NtStatus2HR(v25, &v38) )
    {
      v40 = 0;
      v26 = BcdSetElementData(v39, 620757186, &v40, 8);
      v27 = SErrorConverter::C_NtStatus2HR(v26, &v38);
      v12 = v38;
      if ( v27 )
        goto LABEL_37;
    }
    else
    {
      v12 = v38;
    }
    v24 = v12;
  }
  else
  {
    v12 = -2147483638;
    v24 = 2147483658LL;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v24);
LABEL_37:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
  if ( v39 )
    BcdCloseObject();
  if ( (v12 & 0x80000000) == 0 )
  {
    v28 = CBcdUtils::SetDeviceElementFilePath(v8, &v43, L"\\x64\\sources\\boot.wim");
    v12 = v28;
    if ( v28 >= 0 )
    {
      v29 = CBcdUtils::CopyBcdEntry(v8, &v43, &v44);
      v12 = v29;
      if ( v29 >= 0 )
      {
        v30 = CBcdUtils::SetBootEntryDescription(v8, &v44, a3);
        v12 = v30;
        if ( v30 >= 0 )
        {
          v31 = CBcdUtils::SetDeviceElementFilePath(v8, &v44, L"\\x86\\sources\\boot.wim");
          v12 = v31;
          if ( v31 >= 0 )
          {
            v32 = CBcdUtils::AddEntryToBootDisplayOrder(v8, &v44);
            v12 = v32;
            if ( v32 >= 0 )
              goto LABEL_60;
            v16 = *((_QWORD *)this + 11);
            if ( !v16 )
              goto LABEL_60;
            v37 = v32;
            v36 = 1120;
          }
          else
          {
            v16 = *((_QWORD *)this + 11);
            if ( !v16 )
              goto LABEL_60;
            v37 = v31;
            v36 = 1119;
          }
        }
        else
        {
          v16 = *((_QWORD *)this + 11);
          if ( !v16 )
            goto LABEL_60;
          v37 = v30;
          v36 = 1118;
        }
      }
      else
      {
        v16 = *((_QWORD *)this + 11);
        if ( !v16 )
          goto LABEL_60;
        v37 = v29;
        v36 = 1117;
      }
    }
    else
    {
      v16 = *((_QWORD *)this + 11);
      if ( !v16 )
        goto LABEL_60;
      v37 = v28;
      v36 = 1113;
    }
  }
  else
  {
    v16 = *((_QWORD *)this + 11);
    if ( !v16 )
      goto LABEL_60;
    v37 = v12;
    v36 = 1112;
  }
LABEL_57:
  v33 = CDlpLogT<CEmptyType>::DlpLogFormat(
          v16,
          4,
          L"%s(%d): Result = 0x%X",
          L"CDlpActionWimLayout::CreateMultiArchBcdEntries",
          v36,
          v37);
  v34 = (unsigned int)v33;
  if ( v33 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v33);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v34);
LABEL_60:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
  if ( v8 )
    (*(void (__fastcall **)(CBcdUtils *))(*(_QWORD *)v8 + 16LL))(v8);
  return v12;
}

```

## disassembly

```asm
0x18000eb50  push    rbp
0x18000eb52  push    rbx
0x18000eb53  push    rsi
0x18000eb54  push    rdi
0x18000eb55  push    r12
0x18000eb57  push    r13
0x18000eb59  push    r14
0x18000eb5b  push    r15
0x18000eb5d  lea     rbp, [rsp-0Fh]
0x18000eb62  sub     rsp, 98h
0x18000eb69  mov     rax, cs:__security_cookie
0x18000eb70  xor     rax, rsp
0x18000eb73  mov     [rbp+47h+var_50], rax
0x18000eb77  mov     r12, r9
0x18000eb7a  mov     r13, r8
0x18000eb7d  mov     rdi, rdx
0x18000eb80  mov     r14, rcx
0x18000eb83  xorps   xmm0, xmm0
0x18000eb86  movups  xmmword ptr [rbp+47h+var_70.Data1], xmm0
0x18000eb8a  xorps   xmm1, xmm1
0x18000eb8d  movups  xmmword ptr [rbp+47h+var_60.Data1], xmm1
0x18000eb91  xor     esi, esi
0x18000eb93  mov     [rbp+47h+var_88], rsi
0x18000eb97  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x18000eb9b  mov     [rbp+47h+var_98], rsi
0x18000eb9f  lea     ecx, [rsi+50h]; Size
0x18000eba2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000eba7  mov     r15, rax
0x18000ebaa  mov     [rbp+47h+var_98], rax
0x18000ebae  test    rax, rax
0x18000ebb1  jz      loc_18000EC56
0x18000ebb7  lea     rax, ??_7?$CUnknownImpl@UIUnknown@@@@6B@; const CUnknownImpl<IUnknown>::`vftable'
0x18000ebbe  mov     [r15], rax
0x18000ebc1  lea     rbx, [r15+8]
0x18000ebc5  mov     [rbx], rsi
0x18000ebc8  mov     [rbx+8], rsi
0x18000ebcc  lea     rcx, [rbx+10h]; this
0x18000ebd0  xorps   xmm0, xmm0
0x18000ebd3  movups  xmmword ptr [rcx], xmm0
0x18000ebd6  movups  xmmword ptr [rcx+10h], xmm0
0x18000ebda  movups  xmmword ptr [rcx+20h], xmm0
0x18000ebde  call    ?Init@CExclusiveAcquireLock@@QEAAJXZ; CExclusiveAcquireLock::Init(void)
0x18000ebe3  xor     edx, edx; unsigned int
0x18000ebe5  mov     rcx, rbx; this
0x18000ebe8  call    ?Init@CDword@@QEAAJK@Z; CDword::Init(ulong)
0x18000ebed  lea     edx, [rsi+1]; unsigned int
0x18000ebf0  mov     rcx, rbx; this
0x18000ebf3  call    ?Init@CDword@@QEAAJK@Z; CDword::Init(ulong)
0x18000ebf8  lea     rax, ??_7CBcdUtils@@6B@; const CBcdUtils::`vftable'
0x18000ebff  mov     [r15], rax
0x18000ec02  mov     [r15+48h], rsi
0x18000ec06  test    r15, r15
0x18000ec09  jz      short loc_18000EC56
0x18000ec0b  mov     rbx, r15
0x18000ec0e  mov     [rbp+47h+var_98], rbx
0x18000ec12  lea     rdx, [rbp+47h+DestinationString]; DestinationString
0x18000ec16  mov     rcx, rdi; DosPathName
0x18000ec19  call    ?GetNtFilePathFromWin32Path@@YAJPEBGPEAU_UNICODE_STRING@@@Z; GetNtFilePathFromWin32Path(ushort const *,_UNICODE_STRING *)
0x18000ec1e  mov     edi, eax
0x18000ec20  mov     [rbp+47h+var_A0], eax
0x18000ec23  test    eax, eax
0x18000ec25  jns     short loc_18000EC2B
0x18000ec27  mov     ecx, eax
0x18000ec29  jmp     short loc_18000EC5F
0x18000ec2b  lea     rdx, [r15+48h]
0x18000ec2f  lea     rcx, [rbp+47h+DestinationString]
0x18000ec33  call    cs:__imp_BcdOpenStoreFromFile
0x18000ec39  mov     ecx, eax; int
0x18000ec3b  lea     rdx, [rbp+47h+var_A0]; int *
0x18000ec3f  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x18000ec44  mov     edi, [rbp+47h+var_A0]
0x18000ec47  test    eax, eax
0x18000ec49  jz      short loc_18000EC5D
0x18000ec4b  xor     ebx, ebx
0x18000ec4d  mov     rsi, r15
0x18000ec50  mov     [rbp+47h+var_88], r15
0x18000ec54  jmp     short loc_18000EC64
0x18000ec56  xor     ebx, ebx
0x18000ec58  mov     edi, 8007000Eh
0x18000ec5d  mov     ecx, edi
0x18000ec5f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000ec64  mov     ecx, edi
0x18000ec66  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000ec6b  nop
0x18000ec6c  test    rbx, rbx
0x18000ec6f  jz      short loc_18000EC85
0x18000ec71  mov     rax, [rbx]
0x18000ec74  mov     edx, 1
0x18000ec79  mov     rcx, rbx
0x18000ec7c  mov     rax, [rax+18h]
0x18000ec80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec85  xor     ebx, ebx
0x18000ec87  test    edi, edi
0x18000ec89  jns     short loc_18000ECA9
0x18000ec8b  mov     rcx, [r14+58h]
0x18000ec8f  test    rcx, rcx
0x18000ec92  jz      loc_18000EF70
0x18000ec98  mov     [rsp+0D0h+var_A8], edi
0x18000ec9c  mov     [rsp+0D0h+var_B0], 452h
0x18000eca4  jmp     loc_18000EF48
0x18000eca9  mov     [rbp+47h+var_98], rbx
0x18000ecad  mov     dword ptr [rbp+47h+var_90], ebx
0x18000ecb0  xorps   xmm0, xmm0
0x18000ecb3  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x18000ecb7  mov     [rbp+47h+var_A0], ebx
0x18000ecba  mov     rcx, [rsi+48h]
0x18000ecbe  mov     r15d, 8000000Ah
0x18000ecc4  test    rcx, rcx
0x18000ecc7  jnz     short loc_18000ECD6
0x18000ecc9  mov     edi, r15d
0x18000eccc  mov     ecx, r15d
0x18000eccf  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000ecd4  jmp     short loc_18000ED3D
0x18000ecd6  lea     r8, [rbp+47h+var_98]
0x18000ecda  lea     rdx, GUID_WINDOWS_BOOTMGR
0x18000ece1  call    cs:__imp_BcdOpenObject
0x18000ece7  mov     ecx, eax; int
0x18000ece9  lea     rdx, [rbp+47h+var_A0]; int *
0x18000eced  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x18000ecf2  test    eax, eax
0x18000ecf4  jnz     short loc_18000ECFD
0x18000ecf6  mov     edi, [rbp+47h+var_A0]
0x18000ecf9  mov     ecx, edi
0x18000ecfb  jmp     short loc_18000ECCF
0x18000ecfd  xorps   xmm0, xmm0
0x18000ed00  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x18000ed04  mov     dword ptr [rbp+47h+var_90], 10h
0x18000ed0b  lea     r9, [rbp+47h+var_90]
0x18000ed0f  lea     r8, [rbp+47h+DestinationString]
0x18000ed13  mov     edx, 23000003h
0x18000ed18  mov     rcx, [rbp+47h+var_98]
0x18000ed1c  call    cs:__imp_BcdGetElementData
0x18000ed22  mov     ecx, eax; int
0x18000ed24  lea     rdx, [rbp+47h+var_A0]; int *
0x18000ed28  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x18000ed2d  mov     edi, [rbp+47h+var_A0]
0x18000ed30  test    eax, eax
0x18000ed32  jz      short loc_18000ECF9
0x18000ed34  movaps  xmm0, xmmword ptr [rbp+47h+DestinationString.Length]
0x18000ed38  movdqa  xmmword ptr [rbp+47h+var_70.Data1], xmm0
0x18000ed3d  mov     ecx, edi
0x18000ed3f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000ed44  nop
0x18000ed45  mov     rcx, [rbp+47h+var_98]
0x18000ed49  test    rcx, rcx
0x18000ed4c  jz      short loc_18000ED54
0x18000ed4e  call    cs:__imp_BcdCloseObject
0x18000ed54  test    edi, edi
0x18000ed56  jns     short loc_18000ED76
0x18000ed58  mov     rcx, [r14+58h]
0x18000ed5c  test    rcx, rcx
0x18000ed5f  jz      loc_18000EF70
0x18000ed65  mov     [rsp+0D0h+var_A8], edi
0x18000ed69  mov     [rsp+0D0h+var_B0], 456h
0x18000ed71  jmp     loc_18000EF48
0x18000ed76  mov     r8, r12; unsigned __int16 *
0x18000ed79  lea     rdx, [rbp+47h+var_70]; struct _GUID *
0x18000ed7d  mov     rcx, rsi; this
0x18000ed80  call    ?SetBootEntryDescription@CBcdUtils@@QEAAJAEBU_GUID@@PEBG@Z; CBcdUtils::SetBootEntryDescription(_GUID const &,ushort const *)
0x18000ed85  mov     edi, eax
0x18000ed87  test    eax, eax
0x18000ed89  jns     short loc_18000EDA9
0x18000ed8b  mov     rcx, [r14+58h]
0x18000ed8f  test    rcx, rcx
0x18000ed92  jz      loc_18000EF70
0x18000ed98  mov     [rsp+0D0h+var_A8], eax
0x18000ed9c  mov     [rsp+0D0h+var_B0], 457h
0x18000eda4  jmp     loc_18000EF48
0x18000eda9  mov     [rbp+47h+var_90], rbx
0x18000edad  mov     [rbp+47h+var_98], rbx
0x18000edb1  mov     [rbp+47h+var_A0], ebx
0x18000edb4  mov     rcx, [rsi+48h]
0x18000edb8  test    rcx, rcx
0x18000edbb  jnz     short loc_18000EDC5
0x18000edbd  mov     edi, r15d
0x18000edc0  mov     ecx, r15d
0x18000edc3  jmp     short loc_18000EE18
0x18000edc5  lea     r8, [rbp+47h+var_98]
0x18000edc9  lea     rdx, [rbp+47h+var_70]
0x18000edcd  call    cs:__imp_BcdOpenObject
0x18000edd3  mov     ecx, eax; int
0x18000edd5  lea     rdx, [rbp+47h+var_A0]; int *
0x18000edd9  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x18000edde  test    eax, eax
0x18000ede0  jnz     short loc_18000EDE7
0x18000ede2  mov     edi, [rbp+47h+var_A0]
0x18000ede5  jmp     short loc_18000EE16
0x18000ede7  mov     [rbp+47h+var_90], rbx
0x18000edeb  mov     r9d, 8
0x18000edf1  lea     r8, [rbp+47h+var_90]
0x18000edf5  mov     edx, 250000C2h
0x18000edfa  mov     rcx, [rbp+47h+var_98]
0x18000edfe  call    cs:__imp_BcdSetElementData
0x18000ee04  mov     ecx, eax; int
0x18000ee06  lea     rdx, [rbp+47h+var_A0]; int *
0x18000ee0a  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x18000ee0f  mov     edi, [rbp+47h+var_A0]
0x18000ee12  test    eax, eax
0x18000ee14  jnz     short loc_18000EE1D
0x18000ee16  mov     ecx, edi
0x18000ee18  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000ee1d  mov     ecx, edi
0x18000ee1f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000ee24  nop
0x18000ee25  mov     rcx, [rbp+47h+var_98]
0x18000ee29  test    rcx, rcx
0x18000ee2c  jz      short loc_18000EE34
0x18000ee2e  call    cs:__imp_BcdCloseObject
0x18000ee34  test    edi, edi
0x18000ee36  jns     short loc_18000EE56
0x18000ee38  mov     rcx, [r14+58h]
0x18000ee3c  test    rcx, rcx
0x18000ee3f  jz      loc_18000EF70
0x18000ee45  mov     [rsp+0D0h+var_A8], edi
0x18000ee49  mov     [rsp+0D0h+var_B0], 458h
0x18000ee51  jmp     loc_18000EF48
0x18000ee56  lea     r8, aX64SourcesBoot; "\\x64\\sources\\boot.wim"
0x18000ee5d  lea     rdx, [rbp+47h+var_70]; struct _GUID *
0x18000ee61  mov     rcx, rsi; this
0x18000ee64  call    ?SetDeviceElementFilePath@CBcdUtils@@QEAAJAEBU_GUID@@PEBG@Z; CBcdUtils::SetDeviceElementFilePath(_GUID const &,ushort const *)
0x18000ee69  mov     edi, eax
0x18000ee6b  test    eax, eax
0x18000ee6d  jns     short loc_18000EE8D
0x18000ee6f  mov     rcx, [r14+58h]
0x18000ee73  test    rcx, rcx
0x18000ee76  jz      loc_18000EF70
0x18000ee7c  mov     [rsp+0D0h+var_A8], eax
0x18000ee80  mov     [rsp+0D0h+var_B0], 459h
0x18000ee88  jmp     loc_18000EF48
0x18000ee8d  lea     r8, [rbp+47h+var_60]; struct _GUID *
0x18000ee91  lea     rdx, [rbp+47h+var_70]; struct _GUID *
0x18000ee95  mov     rcx, rsi; this
0x18000ee98  call    ?CopyBcdEntry@CBcdUtils@@QEAAJAEBU_GUID@@PEAU2@@Z; CBcdUtils::CopyBcdEntry(_GUID const &,_GUID *)
0x18000ee9d  mov     edi, eax
0x18000ee9f  test    eax, eax
0x18000eea1  jns     short loc_18000EEC1
0x18000eea3  mov     rcx, [r14+58h]
0x18000eea7  test    rcx, rcx
0x18000eeaa  jz      loc_18000EF70
0x18000eeb0  mov     [rsp+0D0h+var_A8], eax
0x18000eeb4  mov     [rsp+0D0h+var_B0], 45Dh
0x18000eebc  jmp     loc_18000EF48
0x18000eec1  mov     r8, r13; unsigned __int16 *
0x18000eec4  lea     rdx, [rbp+47h+var_60]; struct _GUID *
0x18000eec8  mov     rcx, rsi; this
0x18000eecb  call    ?SetBootEntryDescription@CBcdUtils@@QEAAJAEBU_GUID@@PEBG@Z; CBcdUtils::SetBootEntryDescription(_GUID const &,ushort const *)
0x18000eed0  mov     edi, eax
0x18000eed2  test    eax, eax
0x18000eed4  jns     short loc_18000EEF1
0x18000eed6  mov     rcx, [r14+58h]
0x18000eeda  test    rcx, rcx
0x18000eedd  jz      loc_18000EF70
0x18000eee3  mov     [rsp+0D0h+var_A8], eax
0x18000eee7  mov     [rsp+0D0h+var_B0], 45Eh
0x18000eeef  jmp     short loc_18000EF48
0x18000eef1  lea     r8, aX86SourcesBoot; "\\x86\\sources\\boot.wim"
0x18000eef8  lea     rdx, [rbp+47h+var_60]; struct _GUID *
0x18000eefc  mov     rcx, rsi; this
0x18000eeff  call    ?SetDeviceElementFilePath@CBcdUtils@@QEAAJAEBU_GUID@@PEBG@Z; CBcdUtils::SetDeviceElementFilePath(_GUID const &,ushort const *)
0x18000ef04  mov     edi, eax
0x18000ef06  test    eax, eax
0x18000ef08  jns     short loc_18000EF21
0x18000ef0a  mov     rcx, [r14+58h]
0x18000ef0e  test    rcx, rcx
0x18000ef11  jz      short loc_18000EF70
0x18000ef13  mov     [rsp+0D0h+var_A8], eax
0x18000ef17  mov     [rsp+0D0h+var_B0], 45Fh
0x18000ef1f  jmp     short loc_18000EF48
0x18000ef21  lea     rdx, [rbp+47h+var_60]; struct _GUID *
0x18000ef25  mov     rcx, rsi; this
0x18000ef28  call    ?AddEntryToBootDisplayOrder@CBcdUtils@@QEAAJAEBU_GUID@@@Z; CBcdUtils::AddEntryToBootDisplayOrder(_GUID const &)
0x18000ef2d  mov     edi, eax
0x18000ef2f  test    eax, eax
0x18000ef31  jns     short loc_18000EF70
0x18000ef33  mov     rcx, [r14+58h]
0x18000ef37  test    rcx, rcx
0x18000ef3a  jz      short loc_18000EF70
0x18000ef3c  mov     [rsp+0D0h+var_A8], eax
0x18000ef40  mov     [rsp+0D0h+var_B0], 460h
0x18000ef48  lea     r9, aCdlpactionwiml_11; "CDlpActionWimLayout::CreateMultiArchBcd"...
0x18000ef4f  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18000ef56  mov     edx, 4
0x18000ef5b  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000ef60  mov     ecx, eax
0x18000ef62  test    eax, eax
0x18000ef64  jns     short loc_18000EF6B
0x18000ef66  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000ef6b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000ef70  mov     ecx, edi
0x18000ef72  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000ef77  nop
0x18000ef78  test    rsi, rsi
0x18000ef7b  jz      short loc_18000EF8D
0x18000ef7d  mov     rax, [rsi]
0x18000ef80  mov     rcx, rsi
0x18000ef83  mov     rax, [rax+10h]
0x18000ef87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef8c  nop
0x18000ef8d  mov     eax, edi
0x18000ef8f  mov     rcx, [rbp+47h+var_50]
  ... truncated ...
```

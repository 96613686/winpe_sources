# CCuFileEnumeration::EnumerateSingleDirectory(EcsStack<CCuFileEnumItem> *,_FILE_ID_EXTD_DIR_INFORMATION *,unsigned __int64,ushort const *,long (*)(IChangeUpdateFileEnumItem const *,IFileSyncProgress *,void *,CCuEventLogger *,ISyncFileSystemInterface *),IFileSyncProgress *,void *,CCuEventLogger *)

- ea: `0x18012283c`
- end: `0x180122e1f`
- name: `?EnumerateSingleDirectory@CCuFileEnumeration@@AEBAJPEAV?$EcsStack@VCCuFileEnumItem@@@@PEAU_FILE_ID_EXTD_DIR_INFORMATION@@_KPEBGP6AJPEBUIChangeUpdateFileEnumItem@@PEAUIFileSyncProgress@@PEAXPEAVCCuEventLogger@@PEAUISyncFileSystemInterface@@@Z567@Z`
- size: `1507`
- prototype: `__int64(__int64, __int64, struct _UNICODE_STRING *, ...)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801223bc`

## callees

- `0x180006f5c`
- `0x180007e10`
- `0x180008080`
- `0x1800091ac`
- `0x180011314`
- `0x18001133c`
- `0x180058d88`
- `0x18008b634`
- `0x1800b85d4`
- `0x1800bbd60`
- `0x18011b650`
- `0x18011e708`
- `0x18011ede8`
- `0x18012283c`
- `0x180123ecc`
- `0x180123f60`
- `0x18012417c`
- `0x180124208`
- `0x18013e010`

## import_xrefs

- `ntdll!NtQueryDirectoryFile` at `0x180122ae1`
- `ntdll!NtQueryDirectoryFile` at `0x180122ae1`
- `ntdll!NtClose` at `0x180122de3`
- `ntdll!NtClose` at `0x180122de3`

## string_xrefs

- `0x1801228c3`: `CCuFileEnumeration::EnumerateSingleDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CCuFileEnumeration::EnumerateSingleDirectory(__int64 a1, __int64 a2, struct _UNICODE_STRING *a3, ...)
{
  struct _UNICODE_STRING *FileInformation; // r14
  char *v6; // rax
  char v7; // cl
  __int16 v8; // ax
  __int16 v9; // r11
  CCuFileEnumItem *v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rdx
  const unsigned __int16 *v13; // r8
  unsigned int v14; // eax
  int v15; // eax
  int v16; // ebx
  struct _UNICODE_STRING *ReturnSingleEntry; // r11
  BOOLEAN v18; // cl
  unsigned int v19; // eax
  int v20; // eax
  int v21; // edi
  struct _UNICODE_STRING *v22; // rbx
  const struct _FILE_ID_EXTD_DIR_INFORMATION *v23; // rdx
  CCuFileEnumItem *v24; // rbx
  __int64 (__fastcall ***v25)(_QWORD, GUID *, CCuFileEnumItem **); // rcx
  __int16 v26; // ax
  bool v27; // sf
  CCuFileEnumItem *v28; // rax
  unsigned int i; // ecx
  unsigned int v30; // ebx
  __int64 v32; // [rsp+68h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-39h] BYREF
  struct _FILE_ID_128 v34; // [rsp+80h] [rbp-29h] BYREF
  int v35; // [rsp+90h] [rbp-19h] BYREF
  int v36; // [rsp+94h] [rbp-15h]
  char v37; // [rsp+98h] [rbp-11h]
  const char *v38; // [rsp+A0h] [rbp-9h]
  __int64 v39; // [rsp+A8h] [rbp-1h]
  PCWSTR SourceString; // [rsp+F0h] [rbp+47h] BYREF
  struct _UNICODE_STRING *v41; // [rsp+F8h] [rbp+4Fh]
  CCuFileEnumItem *v42; // [rsp+100h] [rbp+57h] BYREF
  va_list va; // [rsp+100h] [rbp+57h]
  unsigned __int16 *v44; // [rsp+108h] [rbp+5Fh]
  HANDLE FileHandle; // [rsp+110h] [rbp+67h] BYREF
  va_list FileHandlea; // [rsp+110h] [rbp+67h]
  struct IFileSyncProgress *v47; // [rsp+118h] [rbp+6Fh]
  struct CCuCallbackHandlerContext::CallbackContext *v48; // [rsp+120h] [rbp+77h]
  struct CCuEventLogger *v49; // [rsp+128h] [rbp+7Fh]
  va_list va2; // [rsp+130h] [rbp+87h] BYREF

  va_start(va2, a3);
  va_start(FileHandlea, a3);
  va_start(va, a3);
  v42 = va_arg(FileHandlea, CCuFileEnumItem *);
  v44 = va_arg(FileHandlea, unsigned __int16 *);
  va_copy(va2, FileHandlea);
  FileHandle = va_arg(va2, HANDLE);
  v47 = va_arg(va2, struct IFileSyncProgress *);
  v48 = va_arg(va2, struct CCuCallbackHandlerContext::CallbackContext *);
  v49 = va_arg(va2, struct CCuEventLogger *);
  v41 = a3;
  FileInformation = a3;
  v6 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 68) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, WPP_fa6044148ddd38cc3a2ca04b2bf40a94_Traceguids);
    v6 = (char *)WPP_GLOBAL_Control;
  }
  if ( v6[68] >= 0 || (v7 = 1, (unsigned __int8)v6[65] < 6u) )
    v7 = 0;
  v35 = 0;
  v36 = 579;
  v37 = v7;
  v38 = "CCuFileEnumeration::EnumerateSingleDirectory";
  v39 = 0;
  FileHandle = 0;
  v42 = 0;
  IoStatusBlock = 0;
  SourceString = 0;
  v8 = 596;
  if ( !a2 )
    goto LABEL_69;
  LOWORD(v36) = 596;
  v8 = 597;
  if ( !FileInformation )
    goto LABEL_69;
  LOWORD(v36) = 597;
  if ( !v44 )
  {
    v8 = 598;
LABEL_69:
    v35 = -2147024809;
    goto LABEL_70;
  }
  LOWORD(v36) = 599;
  v8 = 600;
  if ( !v48 )
    goto LABEL_69;
  LOWORD(v36) = 600;
  v8 = 601;
  if ( !v49 )
    goto LABEL_69;
  LOWORD(v36) = 601;
  v35 = EcsStack<CCuFileEnumItem>::Top(a2, (CCuFileEnumItem **)va);
  v8 = 603;
  if ( v35 < 0 )
    goto LABEL_70;
  LOWORD(v36) = 603;
  v10 = v42;
  v34 = *(struct _FILE_ID_128 *)((char *)v42 + 72);
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(*((_QWORD *)v42 + 3) + 2 * v12) != v9 );
  v35 = CEcsMemPtr<unsigned short,0>::AllocBytes((void **)&SourceString, 2 * v12 + 2);
  v8 = 609;
  if ( v35 < 0 )
    goto LABEL_70;
  LOWORD(v36) = 609;
  v13 = (const unsigned __int16 *)*((_QWORD *)v10 + 3);
  do
    ++v11;
  while ( v13[v11] );
  v35 = StringCchCopyW((unsigned __int16 *)SourceString, v11 + 1, v13);
  v8 = 612;
  if ( v35 < 0 )
    goto LABEL_70;
  LOWORD(v36) = 612;
  ++*(_DWORD *)(a1 + 8);
  v35 = CCuFileEnumerationHandler::ChangeUpdateCallback(
          v10,
          v47,
          v48,
          v49,
          *(struct ISyncFileSystemInterface **)(a1 + 80));
  v8 = 618;
  if ( v35 < 0 )
    goto LABEL_70;
  LOWORD(v36) = 618;
  v35 = EcsStack<CCuFileEnumItem>::Pop(a2);
  v8 = 620;
  if ( v35 < 0 )
    goto LABEL_70;
  LOWORD(v36) = 620;
  v14 = CCuFileSystemOperations::OpenFile((PHANDLE)FileHandlea, 0x100021u, SourceString, 7u, 0x21u);
  v15 = HRESULTFromNTSTATUS(v14);
  v16 = v15;
  ReturnSingleEntry = 0;
  if ( v15 < 0 )
  {
    CCuEventLogger::LogEvent(v49, (unsigned int)v15, 0);
    v35 = v16;
    v8 = 635;
LABEL_70:
    HIWORD(v36) = v8;
    goto LABEL_71;
  }
  v35 = v15;
  v18 = 1;
  LOWORD(v36) = 635;
LABEL_25:
  IoStatusBlock.Status = -1073741823;
  IoStatusBlock.Information = (ULONG_PTR)ReturnSingleEntry;
  v19 = NtQueryDirectoryFile(
          FileHandle,
          0,
          0,
          0,
          &IoStatusBlock,
          FileInformation,
          0x10000u,
          FileMaximumInformation|FileBasicInformation,
          (BOOLEAN)ReturnSingleEntry,
          ReturnSingleEntry,
          v18);
  if ( v19 != -2147483642 )
  {
    v20 = HRESULTFromNTSTATUS(v19);
    v21 = v20;
    ReturnSingleEntry = 0;
    if ( v20 < 0 )
    {
      CCuEventLogger::LogEvent(v49, (unsigned int)v20, 1);
      v35 = v21;
      HIWORD(v36) = 666;
      goto LABEL_71;
    }
    v35 = v20;
    LOWORD(v36) = 666;
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
          if ( !FileInformation )
          {
            v18 = (unsigned __int8)ReturnSingleEntry;
            FileInformation = v41;
            goto LABEL_25;
          }
          v22 = FileInformation;
          v42 = (CCuFileEnumItem *)ReturnSingleEntry;
          if ( *(_DWORD *)&FileInformation->Length == (_DWORD)ReturnSingleEntry )
            FileInformation = ReturnSingleEntry;
          else
            FileInformation = (struct _UNICODE_STRING *)((char *)FileInformation
                                                       + *(unsigned int *)&FileInformation->Length);
        }
        while ( (unsigned int)CPathUtilities::IsDotOrDotDot(
                                (unsigned __int16 *)&v22[5].Buffer,
                                (unsigned __int64)HIDWORD(v22[3].Buffer) >> 1) );
        v35 = EcsStack<CCuFileEnumItem>::PushNew(a2);
        v8 = 695;
        if ( v35 < 0 )
          goto LABEL_70;
        LOWORD(v36) = 695;
        v35 = EcsStack<CCuFileEnumItem>::Top(a2, (CCuFileEnumItem **)va);
        v8 = 697;
        if ( v35 < 0 )
          goto LABEL_70;
        LOWORD(v36) = 697;
        v23 = (const struct _FILE_ID_EXTD_DIR_INFORMATION *)v22;
        v24 = v42;
        v35 = CCuFileEnumItem::PopulateItemInfo(v42, v23, SourceString, &v34, v44);
        v8 = 702;
        if ( v35 < 0 )
          goto LABEL_70;
        LOWORD(v36) = 702;
        LODWORD(v42) = 0;
        v35 = CSyncExcludeList::CheckExcludeList(*((LPCWSTR *)v24 + 1), *((_DWORD *)v24 + 16), (int *)va);
        ReturnSingleEntry = 0;
        v8 = 714;
        if ( v35 < 0 )
          goto LABEL_70;
        LOWORD(v36) = 714;
        if ( !(_DWORD)v42 )
          break;
        v25 = *(__int64 (__fastcall ****)(_QWORD, GUID *, CCuFileEnumItem **))(a1 + 80);
        if ( v25 && (*((_BYTE *)v24 + 64) & 0x10) == 0 )
        {
          v42 = 0;
          v35 = (**v25)(v25, &GUID_c516c4ce_8983_4dab_84a2_bf07aa683c78, (CCuFileEnumItem **)va);
          v26 = 722;
          if ( v35 < 0
            || (LOWORD(v36) = 722,
                v32 = 0,
                v35 = (*(__int64 (__fastcall **)(CCuFileEnumItem *, __int64 *))(*(_QWORD *)v24 + 24LL))(v24, &v32),
                v26 = 725,
                v35 < 0) )
          {
            HIWORD(v36) = v26;
            ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>((CCuFileEnumItem **)va);
            goto LABEL_71;
          }
          LOWORD(v36) = 725;
          if ( (*(int (__fastcall **)(CCuFileEnumItem *, __int64, _QWORD, _QWORD))(*(_QWORD *)v42 + 80LL))(
                 v42,
                 v32,
                 *((unsigned int *)v24 + 16),
                 *((unsigned int *)v24 + 17)) < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 68) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, WPP_fa6044148ddd38cc3a2ca04b2bf40a94_Traceguids);
          }
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>((CCuFileEnumItem **)va);
        }
        v35 = EcsStack<CCuFileEnumItem>::Pop(a2);
        ReturnSingleEntry = 0;
        v27 = v35 < 0;
        v8 = 735;
LABEL_63:
        if ( v27 )
          goto LABEL_70;
        LOWORD(v36) = v8;
      }
      if ( (*((_BYTE *)v24 + 64) & 0x10) == 0 )
      {
        ++*(_DWORD *)(a1 + 12);
        v42 = 0;
        if ( (*(int (__fastcall **)(CCuFileEnumItem *, CCuFileEnumItem **))(*(_QWORD *)v24 + 56LL))(
               v24,
               (CCuFileEnumItem **)va) >= 0 )
        {
          v28 = v42;
          if ( *(_QWORD *)(a1 + 24) < (unsigned __int64)v42 )
            *(_QWORD *)(a1 + 24) = v42;
          if ( *(_QWORD *)(a1 + 32) > (unsigned __int64)v28 )
            *(_QWORD *)(a1 + 32) = v28;
          for ( i = 0; i < 9; ++i )
          {
            if ( (const unsigned __int64 near *const)v28 < (&CCuFileEnumeration::s_dwFileSizeBucketsDetail)[i] )
            {
              ++*(_DWORD *)(a1 + 4LL * (int)i + 40);
              break;
            }
          }
          *(_QWORD *)(a1 + 16) += v28;
        }
        v35 = CCuFileEnumerationHandler::ChangeUpdateCallback(
                v24,
                v47,
                v48,
                v49,
                *(struct ISyncFileSystemInterface **)(a1 + 80));
        v8 = 752;
        if ( v35 < 0 )
          goto LABEL_70;
        LOWORD(v36) = 752;
        v35 = EcsStack<CCuFileEnumItem>::Pop(a2);
        ReturnSingleEntry = 0;
        v27 = v35 < 0;
        v8 = 754;
        goto LABEL_63;
      }
    }
  }
LABEL_71:
  if ( FileHandle )
  {
    NtClose(FileHandle);
    FileHandle = 0;
  }
  v30 = v35;
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&SourceString);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v35);
  return v30;
}

```

## disassembly

```asm
0x18012283c  mov     rax, rsp
0x18012283f  mov     [rax+8], rbx
0x180122843  mov     [rax+20h], r9
0x180122847  mov     [rax+18h], r8
0x18012284b  push    rbp
0x18012284c  push    rsi
0x18012284d  push    rdi
0x18012284e  push    r14
0x180122850  push    r15
0x180122852  lea     rbp, [rax-37h]
0x180122856  sub     rsp, 0B0h
0x18012285d  mov     r14, r8
0x180122860  mov     r15, rdx
0x180122863  mov     rsi, rcx
0x180122866  lea     rcx, WPP_GLOBAL_Control
0x18012286d  mov     rax, cs:WPP_GLOBAL_Control
0x180122874  cmp     rax, rcx
0x180122877  jz      short loc_1801228A1
0x180122879  test    byte ptr [rax+44h], 80h
0x18012287d  jz      short loc_1801228A1
0x18012287f  cmp     byte ptr [rax+41h], 6
0x180122883  jb      short loc_1801228A1
0x180122885  mov     edx, 18h
0x18012288a  lea     r8, WPP_fa6044148ddd38cc3a2ca04b2bf40a94_Traceguids
0x180122891  mov     rcx, [rax+38h]
0x180122895  call    WPP_SF_
0x18012289a  mov     rax, cs:WPP_GLOBAL_Control
0x1801228a1  xor     r11d, r11d
0x1801228a4  test    byte ptr [rax+44h], 80h
0x1801228a8  jz      short loc_1801228B2
0x1801228aa  cmp     byte ptr [rax+41h], 6
0x1801228ae  mov     cl, 1
0x1801228b0  jnb     short loc_1801228B5
0x1801228b2  mov     cl, r11b
0x1801228b5  mov     [rbp+2Fh+var_48], r11d
0x1801228b9  mov     [rbp+2Fh+var_44], 243h
0x1801228c0  mov     [rbp+2Fh+var_40], cl
0x1801228c3  lea     rax, aCcufileenumera_5; "CCuFileEnumeration::EnumerateSingleDire"...
0x1801228ca  mov     [rbp+2Fh+var_38], rax
0x1801228ce  mov     [rbp+2Fh+var_30], r11
0x1801228d2  mov     [rbp+2Fh+FileHandle], r11
0x1801228d6  mov     [rbp+2Fh+arg_18], r11
0x1801228da  xorps   xmm0, xmm0
0x1801228dd  movups  xmmword ptr [rbp+2Fh+var_68], xmm0
0x1801228e1  mov     [rbp+2Fh+SourceString], r11
0x1801228e5  mov     eax, 254h
0x1801228ea  test    r15, r15
0x1801228ed  jz      loc_180122DCF
0x1801228f3  mov     word ptr [rbp+2Fh+var_44], ax
0x1801228f7  mov     eax, 255h
0x1801228fc  test    r14, r14
0x1801228ff  jz      loc_180122DCF
0x180122905  mov     word ptr [rbp+2Fh+var_44], ax
0x180122909  cmp     [rbp+2Fh+arg_20], r11
0x18012290d  jz      loc_180122DCA
0x180122913  mov     eax, 257h
0x180122918  mov     word ptr [rbp+2Fh+var_44], ax
0x18012291c  mov     eax, 258h
0x180122921  cmp     [rbp+2Fh+arg_38], r11
0x180122925  jz      loc_180122DCF
0x18012292b  mov     word ptr [rbp+2Fh+var_44], ax
0x18012292f  mov     eax, 259h
0x180122934  cmp     [rbp+2Fh+arg_40], r11
0x180122938  jz      loc_180122DCF
0x18012293e  mov     [rbp+2Fh+var_48], r11d
0x180122942  mov     word ptr [rbp+2Fh+var_44], ax
0x180122946  lea     rdx, [rbp+2Fh+arg_18]
0x18012294a  mov     rcx, r15
0x18012294d  call    ?Top@?$EcsStack@VCCuFileEnumItem@@@@QEAAJPEAPEAVCCuFileEnumItem@@@Z; EcsStack<CCuFileEnumItem>::Top(CCuFileEnumItem * *)
0x180122952  mov     [rbp+2Fh+var_48], eax
0x180122955  test    eax, eax
0x180122957  mov     eax, 25Bh
0x18012295c  js      loc_180122DD6
0x180122962  mov     word ptr [rbp+2Fh+var_44], ax
0x180122966  mov     rdi, [rbp+2Fh+arg_18]
0x18012296a  movups  xmm0, xmmword ptr [rdi+48h]
0x18012296e  movdqu  xmmword ptr [rbp+2Fh+var_58.Identifier], xmm0
0x180122973  mov     rax, [rdi+18h]
0x180122977  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18012297b  mov     rdx, rbx
0x18012297e  inc     rdx
0x180122981  cmp     [rax+rdx*2], r11w
0x180122986  jnz     short loc_18012297E
0x180122988  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180122990  lea     rcx, [rbp+2Fh+SourceString]; void **
0x180122994  call    ?AllocBytes@?$CEcsMemPtr@G$0A@@@QEAAJ_K@Z; CEcsMemPtr<ushort,0>::AllocBytes(unsigned __int64)
0x180122999  mov     [rbp+2Fh+var_48], eax
0x18012299c  xor     r11d, r11d
0x18012299f  test    eax, eax
0x1801229a1  mov     eax, 261h
0x1801229a6  js      loc_180122DD6
0x1801229ac  mov     word ptr [rbp+2Fh+var_44], ax
0x1801229b0  mov     r8, [rdi+18h]; unsigned __int16 *
0x1801229b4  inc     rbx
0x1801229b7  cmp     [r8+rbx*2], r11w
0x1801229bc  jnz     short loc_1801229B4
0x1801229be  lea     rdx, [rbx+1]; unsigned __int64
0x1801229c2  mov     rcx, [rbp+2Fh+SourceString]; unsigned __int16 *
0x1801229c6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801229cb  mov     [rbp+2Fh+var_48], eax
0x1801229ce  test    eax, eax
0x1801229d0  mov     eax, 264h
0x1801229d5  js      loc_180122DD6
0x1801229db  mov     word ptr [rbp+2Fh+var_44], ax
0x1801229df  inc     dword ptr [rsi+8]
0x1801229e2  mov     rax, [rsi+50h]
0x1801229e6  mov     [rsp+0D0h+IoStatusBlock], rax; struct ISyncFileSystemInterface *
0x1801229eb  mov     r9, [rbp+2Fh+arg_40]; struct CCuEventLogger *
0x1801229ef  mov     r8, [rbp+2Fh+arg_38]; struct CCuCallbackHandlerContext::CallbackContext *
0x1801229f3  mov     rdx, [rbp+2Fh+arg_30]; struct IFileSyncProgress *
0x1801229f7  mov     rcx, rdi; struct IChangeUpdateFileEnumItem *
0x1801229fa  call    ?ChangeUpdateCallback@CCuFileEnumerationHandler@@CAJPEBUIChangeUpdateFileEnumItem@@PEAUIFileSyncProgress@@PEAXPEAVCCuEventLogger@@PEAUISyncFileSystemInterface@@@Z; CCuFileEnumerationHandler::ChangeUpdateCallback(IChangeUpdateFileEnumItem const *,IFileSyncProgress *,void *,CCuEventLogger *,ISyncFileSystemInterface *)
0x1801229ff  mov     [rbp+2Fh+var_48], eax
0x180122a02  test    eax, eax
0x180122a04  mov     eax, 26Ah
0x180122a09  js      loc_180122DD6
0x180122a0f  mov     word ptr [rbp+2Fh+var_44], ax
0x180122a13  mov     rcx, r15
0x180122a16  call    ?Pop@?$EcsStack@VCCuFileEnumItem@@@@QEAAJXZ; EcsStack<CCuFileEnumItem>::Pop(void)
0x180122a1b  mov     [rbp+2Fh+var_48], eax
0x180122a1e  test    eax, eax
0x180122a20  mov     eax, 26Ch
0x180122a25  js      loc_180122DD6
0x180122a2b  mov     word ptr [rbp+2Fh+var_44], ax
0x180122a2f  mov     dword ptr [rsp+0D0h+IoStatusBlock], 21h ; '!'; unsigned int
0x180122a37  mov     r9d, 7; ShareAccess
0x180122a3d  mov     r8, [rbp+2Fh+SourceString]; SourceString
0x180122a41  mov     edx, 100021h; DesiredAccess
0x180122a46  lea     rcx, [rbp+2Fh+FileHandle]; FileHandle
0x180122a4a  call    ?OpenFile@CCuFileSystemOperations@@SAJPEAPEAXKPEBGKK@Z; CCuFileSystemOperations::OpenFile(void * *,ulong,ushort const *,ulong,ulong)
0x180122a4f  mov     ecx, eax
0x180122a51  call    HRESULTFromNTSTATUS
0x180122a56  mov     ebx, eax
0x180122a58  xor     r11d, r11d
0x180122a5b  test    eax, eax
0x180122a5d  jns     short loc_180122A8B
0x180122a5f  mov     [rsp+0D0h+FileInformation], r11
0x180122a64  mov     rdx, [rbp+2Fh+SourceString]
0x180122a68  mov     [rsp+0D0h+IoStatusBlock], rdx
0x180122a6d  xor     r9d, r9d
0x180122a70  xor     r8d, r8d
0x180122a73  mov     edx, eax
0x180122a75  mov     rcx, [rbp+2Fh+arg_40]
0x180122a79  call    ?LogEvent@CCuEventLogger@@QEAAJJW4CCU_EVENT_ACTION@1@KPEBGPEAU_SYNC_GID@@@Z; CCuEventLogger::LogEvent(long,CCuEventLogger::CCU_EVENT_ACTION,ulong,ushort const *,_SYNC_GID *)
0x180122a7e  mov     [rbp+2Fh+var_48], ebx
0x180122a81  mov     eax, 27Bh
0x180122a86  jmp     loc_180122DD6
0x180122a8b  mov     [rbp+2Fh+var_48], ebx
0x180122a8e  mov     cl, 1
0x180122a90  mov     eax, 27Bh
0x180122a95  mov     word ptr [rbp+2Fh+var_44], ax
0x180122a99  mov     ebx, 29Ah
0x180122a9e  mov     dword ptr [rbp+2Fh+var_68], 0C0000001h
0x180122aa5  mov     [rbp+2Fh+var_68.Information], r11
0x180122aa9  mov     [rsp+50h], cl; RestartScan
0x180122aad  mov     [rsp+0D0h+FileName], r11; FileName
0x180122ab2  mov     [rsp+0D0h+ReturnSingleEntry], r11b; ReturnSingleEntry
0x180122ab7  mov     [rsp+0D0h+FileInformationClass], 3Ch ; '<'; FileInformationClass
0x180122abf  mov     [rsp+0D0h+Length], 10000h; Length
0x180122ac7  mov     [rsp+0D0h+FileInformation], r14; FileInformation
0x180122acc  lea     rax, [rbp+2Fh+var_68]
0x180122ad0  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x180122ad5  xor     r9d, r9d; ApcContext
0x180122ad8  xor     r8d, r8d; ApcRoutine
0x180122adb  xor     edx, edx; Event
0x180122add  mov     rcx, [rbp+2Fh+FileHandle]; FileHandle
0x180122ae1  call    cs:__imp_NtQueryDirectoryFile
0x180122ae7  cmp     eax, 80000006h
0x180122aec  jz      loc_180122DDA
0x180122af2  mov     ecx, eax
0x180122af4  call    HRESULTFromNTSTATUS
0x180122af9  mov     edi, eax
0x180122afb  xor     r11d, r11d
0x180122afe  test    eax, eax
0x180122b00  js      loc_180122DA1
0x180122b06  mov     [rbp+2Fh+var_48], eax
0x180122b09  mov     word ptr [rbp+2Fh+var_44], bx
0x180122b0d  test    r14, r14
0x180122b10  jz      loc_180122D86
0x180122b16  mov     rbx, r14
0x180122b19  mov     [rbp+2Fh+arg_18], r11
0x180122b1d  cmp     [r14], r11d
0x180122b20  jnz     short loc_180122B27
0x180122b22  mov     r14, r11
0x180122b25  jmp     short loc_180122B2D
0x180122b27  mov     eax, [r14]
0x180122b2a  add     r14, rax
0x180122b2d  mov     edx, [rbx+3Ch]
0x180122b30  shr     rdx, 1; unsigned __int64
0x180122b33  lea     rcx, [rbx+58h]; unsigned __int16 *
0x180122b37  call    ?IsDotOrDotDot@CPathUtilities@@SAHPEAG_K@Z; CPathUtilities::IsDotOrDotDot(ushort *,unsigned __int64)
0x180122b3c  test    eax, eax
0x180122b3e  jnz     short loc_180122B0D
0x180122b40  mov     rcx, r15
0x180122b43  call    ?PushNew@?$EcsStack@VCCuFileEnumItem@@@@QEAAJXZ; EcsStack<CCuFileEnumItem>::PushNew(void)
0x180122b48  mov     [rbp+2Fh+var_48], eax
0x180122b4b  test    eax, eax
0x180122b4d  mov     eax, 2B7h
0x180122b52  js      loc_180122DD6
0x180122b58  mov     word ptr [rbp+2Fh+var_44], ax
0x180122b5c  lea     rdx, [rbp+2Fh+arg_18]
0x180122b60  mov     rcx, r15
0x180122b63  call    ?Top@?$EcsStack@VCCuFileEnumItem@@@@QEAAJPEAPEAVCCuFileEnumItem@@@Z; EcsStack<CCuFileEnumItem>::Top(CCuFileEnumItem * *)
0x180122b68  mov     [rbp+2Fh+var_48], eax
0x180122b6b  test    eax, eax
0x180122b6d  mov     eax, 2B9h
0x180122b72  js      loc_180122DD6
0x180122b78  mov     word ptr [rbp+2Fh+var_44], ax
0x180122b7c  mov     rax, [rbp+2Fh+arg_20]
0x180122b80  mov     [rsp+0D0h+IoStatusBlock], rax; unsigned __int16 *
0x180122b85  lea     r9, [rbp+2Fh+var_58]; struct _FILE_ID_128 *
0x180122b89  mov     r8, [rbp+2Fh+SourceString]; unsigned __int16 *
0x180122b8d  mov     rdx, rbx; struct _FILE_ID_EXTD_DIR_INFORMATION *
0x180122b90  mov     rbx, [rbp+2Fh+arg_18]
0x180122b94  mov     rcx, rbx; this
0x180122b97  call    ?PopulateItemInfo@CCuFileEnumItem@@QEAAJPEBU_FILE_ID_EXTD_DIR_INFORMATION@@PEBGAEBU_FILE_ID_128@@1@Z; CCuFileEnumItem::PopulateItemInfo(_FILE_ID_EXTD_DIR_INFORMATION const *,ushort const *,_FILE_ID_128 const &,ushort const *)
0x180122b9c  mov     [rbp+2Fh+var_48], eax
0x180122b9f  xor     r11d, r11d
0x180122ba2  test    eax, eax
0x180122ba4  mov     eax, 2BEh
0x180122ba9  js      loc_180122DD6
0x180122baf  mov     word ptr [rbp+2Fh+var_44], ax
0x180122bb3  mov     dword ptr [rbp+2Fh+arg_18], r11d
0x180122bb7  lea     r8, [rbp+2Fh+arg_18]; int *
0x180122bbb  mov     edx, [rbx+40h]; unsigned int
0x180122bbe  mov     rcx, [rbx+8]; pszFile
0x180122bc2  call    ?CheckExcludeList@CSyncExcludeList@@SAJPEBGKPEAH@Z; CSyncExcludeList::CheckExcludeList(ushort const *,ulong,int *)
0x180122bc7  mov     [rbp+2Fh+var_48], eax
0x180122bca  xor     r11d, r11d
0x180122bcd  test    eax, eax
0x180122bcf  mov     eax, 2CAh
0x180122bd4  js      loc_180122DD6
0x180122bda  mov     word ptr [rbp+2Fh+var_44], ax
0x180122bde  cmp     dword ptr [rbp+2Fh+arg_18], r11d
0x180122be2  jz      loc_180122CD6
0x180122be8  mov     rcx, [rsi+50h]
0x180122bec  test    rcx, rcx
0x180122bef  jz      loc_180122CBC
0x180122bf5  test    byte ptr [rbx+40h], 10h
0x180122bf9  jnz     loc_180122CBC
0x180122bff  mov     [rbp+2Fh+arg_18], r11
0x180122c03  mov     rax, [rcx]
0x180122c06  lea     r8, [rbp+2Fh+arg_18]
0x180122c0a  lea     rdx, _GUID_c516c4ce_8983_4dab_84a2_bf07aa683c78
0x180122c11  mov     rax, [rax]
0x180122c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122c19  mov     [rbp+2Fh+var_48], eax
0x180122c1c  test    eax, eax
0x180122c1e  mov     eax, 2D2h
0x180122c23  js      loc_180122D92
0x180122c29  mov     word ptr [rbp+2Fh+var_44], ax
0x180122c2d  mov     [rbp+2Fh+var_70], 0
0x180122c35  mov     rax, [rbx]
0x180122c38  lea     rdx, [rbp+2Fh+var_70]
0x180122c3c  mov     rcx, rbx
0x180122c3f  mov     rax, [rax+18h]
0x180122c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122c48  mov     [rbp+2Fh+var_48], eax
0x180122c4b  test    eax, eax
0x180122c4d  mov     eax, 2D5h
0x180122c52  js      loc_180122D92
0x180122c58  mov     word ptr [rbp+2Fh+var_44], ax
0x180122c5c  mov     rcx, [rbp+2Fh+arg_18]
0x180122c60  mov     rax, [rcx]
0x180122c63  mov     r9d, [rbx+44h]
0x180122c67  mov     r8d, [rbx+40h]
0x180122c6b  mov     rdx, [rbp+2Fh+var_70]
0x180122c6f  mov     rax, [rax+50h]
0x180122c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122c78  test    eax, eax
0x180122c7a  jns     short loc_180122CB3
0x180122c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180122c83  lea     rax, WPP_GLOBAL_Control
0x180122c8a  cmp     rcx, rax
0x180122c8d  jz      short loc_180122CB3
0x180122c8f  test    byte ptr [rcx+44h], 80h
0x180122c93  jz      short loc_180122CB3
0x180122c95  cmp     byte ptr [rcx+41h], 2
0x180122c99  jb      short loc_180122CB3
0x180122c9b  mov     edx, 19h
0x180122ca0  mov     r9d, edi
0x180122ca3  lea     r8, WPP_fa6044148ddd38cc3a2ca04b2bf40a94_Traceguids
0x180122caa  mov     rcx, [rcx+38h]
0x180122cae  call    WPP_SF_d
0x180122cb3  lea     rcx, [rbp+2Fh+arg_18]
0x180122cb7  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180122cbc  mov     rcx, r15
0x180122cbf  call    ?Pop@?$EcsStack@VCCuFileEnumItem@@@@QEAAJXZ; EcsStack<CCuFileEnumItem>::Pop(void)
0x180122cc4  mov     [rbp+2Fh+var_48], eax
0x180122cc7  xor     r11d, r11d
0x180122cca  test    eax, eax
0x180122ccc  mov     eax, 2DFh
0x180122cd1  jmp     loc_180122D7B
0x180122cd6  test    byte ptr [rbx+40h], 10h
0x180122cda  jnz     loc_180122B0D
0x180122ce0  inc     dword ptr [rsi+0Ch]
0x180122ce3  mov     [rbp+2Fh+arg_18], r11
0x180122ce7  mov     rax, [rbx]
0x180122cea  lea     rdx, [rbp+2Fh+arg_18]
0x180122cee  mov     rcx, rbx
  ... truncated ...
```

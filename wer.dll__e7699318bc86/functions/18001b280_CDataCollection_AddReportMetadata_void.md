# CDataCollection::AddReportMetadata(void)

- ea: `0x18001b280`
- end: `0x18001b670`
- name: `?AddReportMetadata@CDataCollection@@QEAAJXZ`
- size: `1008`
- prototype: `__int64 __fastcall(CDataCollection *__hidden this)`
- caller_count: `4`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1800065e4`
- `0x18001b190`
- `0x18001eb2c`
- `0x1800429c0`

## callees

- `0x180004bb4`
- `0x180007e10`
- `0x180007e34`
- `0x18000bc10`
- `0x18001b280`
- `0x18001b678`
- `0x18001bbc4`
- `0x18001bfb0`
- `0x18001fe24`
- `0x18002c220`
- `0x180035ce0`
- `0x180044230`
- `0x180050db0`
- `0x180051ff8`
- `0x18008f958`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b633`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b633`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b585`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b649`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b585`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b649`
- `ext-ms-win-wer-xbox-l1-1-0!XerWriteMetadata` at `0x18001b45f`
- `ext-ms-win-wer-xbox-l1-1-0!XerWriteMetadata` at `0x18001b45f`

## string_xrefs

- `0x18001b31e`: `WERInternalMetadata.xml`
- `0x18001b5d3`: `WERInternalMetadata.xml`
- `0x18001b509`: `.WERInternalMetadata.xml`
- `0x18001b439`: `.WERXboxMetadata.xml`
- `0x18001b480`: `WERXboxMetadata.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDataCollection::AddReportMetadata(CDataCollection *this)
{
  __int64 v2; // rax
  unsigned int v3; // ebx
  __int64 v4; // r11
  __int64 v5; // rdi
  __int64 v6; // rsi
  unsigned __int64 v7; // rax
  __int64 v8; // rcx
  int v9; // r11d
  char v10; // r15
  int PathOfWERTempDirectory; // eax
  wchar_t *v12; // rcx
  int TempFile; // ebx
  int v14; // eax
  wchar_t *v15; // rcx
  __int64 v16; // rdx
  HANDLE v17; // rbx
  int v18; // r15d
  wchar_t *v20; // [rsp+20h] [rbp-E0h]
  void *v21; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v24; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v25[264]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[528]; // [rsp+280h] [rbp+180h] BYREF

  hObject = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
  v25[0] = 0;
  v2 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
  {
    v3 = -2147467259;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
    goto LABEL_46;
  }
  v4 = 0;
  v5 = *(_QWORD *)(v2 + 5816);
  v6 = *(_QWORD *)(v2 + 5824);
  while ( 1 )
  {
    v7 = (v6 - v5) >> 3;
    if ( (unsigned int)v4 >= (unsigned int)v7 )
      break;
    if ( (unsigned int)v4 >= v7 )
    {
      v3 = -2147352565;
LABEL_12:
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          112,
          WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
          (unsigned int)v4,
          v3);
      goto LABEL_46;
    }
    v8 = *(_QWORD *)(v5 + 8 * v4);
    v3 = 0;
    if ( !v8 )
      goto LABEL_12;
    if ( (unsigned __int8)utl::operator==<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                            v8 + 80,
                            L"WERInternalMetadata.xml") )
      goto LABEL_46;
    v4 = (unsigned int)(v9 + 1);
  }
  v10 = 1;
  PathOfWERTempDirectory = WerpGetPathOfWERTempDirectory(v26, 260);
  if ( PathOfWERTempDirectory < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        113,
        WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
        (unsigned int)PathOfWERTempDirectory);
    v10 = 0;
  }
  if ( (unsigned __int8)IsXerGetMachineIdPresent(v12) )
  {
    v21 = 0;
    TempFile = UtilGetTempFile(
                 &v21,
                 (WCHAR *)((unsigned __int64)v26 & -(__int64)(v10 != 0)),
                 (const size_t *)L".WERXboxMetadata.xml",
                 v25,
                 (__int64)v20,
                 0,
                 1u,
                 0);
    if ( TempFile < 0
      || (TempFile = XerWriteMetadata(*(_QWORD *)(*(_QWORD *)this + 6640LL), v21),
          tlx::unique_any<tlx::file_handle_traits>::reset(&v21, 0),
          TempFile < 0)
      || (TempFile = CReport::AddFile(*(CReport **)this, 5, 262147, v25, L"WERXboxMetadata.xml", 0), TempFile < 0) )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          114,
          WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
          (unsigned int)TempFile);
    }
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v21);
  }
  v14 = UtilGetTempFile(
          &hObject,
          (WCHAR *)((unsigned __int64)v26 & -(__int64)(v10 != 0)),
          (const size_t *)L".WERInternalMetadata.xml",
          v25,
          (__int64)v20,
          0,
          1u,
          0);
  v3 = v14;
  if ( v14 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_46;
    v16 = 115;
LABEL_32:
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, (unsigned int)v14);
    goto LABEL_46;
  }
  v17 = hObject;
  v18 = CWerInternalMetadata::Create(*(_QWORD *)this, hObject, *((_QWORD *)this + 1), (__int64)lpMem);
  hObject = 0;
  if ( (unsigned __int64)v17 + 1 > 1 )
    CloseHandle(v17);
  if ( v18 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      116,
      WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
      (unsigned int)v18);
  if ( lpMem[0] != lpMem[1] )
    CDataCollection::AddDataCollectionFailure((CReport **)this, (const wchar_t *)lpMem[0]);
  v14 = CReport::AddFile(*(CReport **)this, 5, 262147, v25, L"WERInternalMetadata.xml", 0);
  v3 = v14;
  if ( v14 >= 0 )
  {
    v3 = 0;
    goto LABEL_46;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v16 = 117;
    goto LABEL_32;
  }
LABEL_46:
  if ( lpMem[0] != &v24 )
    HeapFree(g_hWerheap, 0, lpMem[0]);
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return v3;
}

```

## disassembly

```asm
0x18001b280  push    rbp
0x18001b282  push    rbx
0x18001b283  push    rsi
0x18001b284  push    rdi
0x18001b285  push    r14
0x18001b287  push    r15
0x18001b289  lea     rbp, [rsp-3A8h]
0x18001b291  sub     rsp, 4A8h
0x18001b298  mov     rax, cs:__security_cookie
0x18001b29f  xor     rax, rsp
0x18001b2a2  mov     [rbp+3D0h+var_40], rax
0x18001b2a9  mov     r14, rcx
0x18001b2ac  mov     [rsp+4D0h+hObject], 0
0x18001b2b5  lea     rcx, [rsp+4D0h+lpMem]; void *
0x18001b2ba  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001b2bf  nop
0x18001b2c0  xor     eax, eax
0x18001b2c2  mov     [rsp+4D0h+var_460], ax
0x18001b2c7  mov     rax, [r14]
0x18001b2ca  test    rax, rax
0x18001b2cd  jnz     short loc_18001B30D
0x18001b2cf  mov     ebx, 80004005h
0x18001b2d4  lea     rdi, WPP_GLOBAL_Control
0x18001b2db  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2e2  cmp     rcx, rdi
0x18001b2e5  jz      loc_18001B61B
0x18001b2eb  test    byte ptr [rcx+1Ch], 1
0x18001b2ef  jz      loc_18001B61B
0x18001b2f5  lea     edx, [rax+6Fh]
0x18001b2f8  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18001b2ff  mov     rcx, [rcx+10h]
0x18001b303  call    WPP_SF_
0x18001b308  jmp     loc_18001B61B
0x18001b30d  xor     r11d, r11d
0x18001b310  mov     rdi, [rax+16B8h]
0x18001b317  mov     rsi, [rax+16C0h]
0x18001b31e  lea     rdx, aWerinternalmet; "WERInternalMetadata.xml"
0x18001b325  mov     rax, rsi
0x18001b328  sub     rax, rdi
0x18001b32b  sar     rax, 3
0x18001b32f  cmp     r11d, eax
0x18001b332  jnb     short loc_18001B3A4
0x18001b334  mov     ecx, r11d
0x18001b337  cmp     rcx, rax
0x18001b33a  jnb     short loc_18001B35D
0x18001b33c  mov     rcx, [rdi+r11*8]
0x18001b340  xor     ebx, ebx
0x18001b342  test    rcx, rcx
0x18001b345  jz      short loc_18001B362
0x18001b347  add     rcx, 50h ; 'P'
0x18001b34b  call    ??$?8_WU?$char_traits@_W@utl@@V?$allocator@_W@1@@utl@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@0@PEB_W@Z; utl::operator==<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,wchar_t const *)
0x18001b350  test    al, al
0x18001b352  jnz     loc_18001B61B
0x18001b358  inc     r11d
0x18001b35b  jmp     short loc_18001B31E
0x18001b35d  mov     ebx, 8002000Bh
0x18001b362  lea     rdi, WPP_GLOBAL_Control
0x18001b369  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b370  cmp     rcx, rdi
0x18001b373  jz      loc_18001B61B
0x18001b379  test    byte ptr [rcx+1Ch], 1
0x18001b37d  jz      loc_18001B61B
0x18001b383  mov     edx, 70h ; 'p'
0x18001b388  mov     dword ptr [rsp+4D0h+var_4B0], ebx
0x18001b38c  mov     r9d, r11d
0x18001b38f  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18001b396  mov     rcx, [rcx+10h]
0x18001b39a  call    WPP_SF_Dd
0x18001b39f  jmp     loc_18001B61B
0x18001b3a4  mov     r15b, 1
0x18001b3a7  mov     edx, 104h
0x18001b3ac  lea     rcx, [rbp+3D0h+var_250]
0x18001b3b3  call    WerpGetPathOfWERTempDirectory
0x18001b3b8  lea     rdi, WPP_GLOBAL_Control
0x18001b3bf  lea     rsi, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18001b3c6  test    eax, eax
0x18001b3c8  jns     short loc_18001B3F3
0x18001b3ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3d1  cmp     rcx, rdi
0x18001b3d4  jz      short loc_18001B3F0
0x18001b3d6  test    byte ptr [rcx+1Ch], 2
0x18001b3da  jz      short loc_18001B3F0
0x18001b3dc  mov     edx, 71h ; 'q'
0x18001b3e1  mov     r9d, eax
0x18001b3e4  mov     r8, rsi
0x18001b3e7  mov     rcx, [rcx+10h]
0x18001b3eb  call    WPP_SF_d
0x18001b3f0  xor     r15b, r15b
0x18001b3f3  call    IsXerGetMachineIdPresent
0x18001b3f8  test    al, al
0x18001b3fa  jz      loc_18001B4DB
0x18001b400  mov     [rsp+4D0h+var_490], 0
0x18001b409  mov     al, r15b
0x18001b40c  neg     al
0x18001b40e  sbb     rdx, rdx
0x18001b411  lea     rax, [rbp+3D0h+var_250]
0x18001b418  and     rdx, rax
0x18001b41b  mov     [rsp+4D0h+var_498], 0
0x18001b423  mov     [rsp+4D0h+var_4A0], 1
0x18001b42b  mov     [rsp+4D0h+var_4A8], 0
0x18001b434  lea     r9, [rsp+4D0h+var_460]
0x18001b439  lea     r8, aWerxboxmetadat_0; ".WERXboxMetadata.xml"
0x18001b440  lea     rcx, [rsp+4D0h+var_490]
0x18001b445  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18001b44a  mov     ebx, eax
0x18001b44c  test    eax, eax
0x18001b44e  js      short loc_18001B4AA
0x18001b450  mov     rcx, [r14]
0x18001b453  mov     rdx, [rsp+4D0h+var_490]
0x18001b458  mov     rcx, [rcx+19F0h]
0x18001b45f  call    cs:__imp_XerWriteMetadata
0x18001b465  mov     ebx, eax
0x18001b467  xor     edx, edx
0x18001b469  lea     rcx, [rsp+4D0h+var_490]
0x18001b46e  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18001b473  test    ebx, ebx
0x18001b475  js      short loc_18001B4AA
0x18001b477  mov     [rsp+4D0h+var_4A8], 0; wchar_t *
0x18001b480  lea     rax, aWerxboxmetadat; "WERXboxMetadata.xml"
0x18001b487  mov     [rsp+4D0h+var_4B0], rax; wchar_t *
0x18001b48c  lea     r9, [rsp+4D0h+var_460]; wchar_t *
0x18001b491  mov     edx, 5; enum _WER_FILE_TYPE
0x18001b496  mov     r8d, 40003h; unsigned int
0x18001b49c  mov     rcx, [r14]; this
0x18001b49f  call    ?AddFile@CReport@@QEAAJW4_WER_FILE_TYPE@@KPEB_W11@Z; CReport::AddFile(_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *,wchar_t const *)
0x18001b4a4  mov     ebx, eax
0x18001b4a6  test    eax, eax
0x18001b4a8  jns     short loc_18001B4D1
0x18001b4aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4b1  cmp     rcx, rdi
0x18001b4b4  jz      short loc_18001B4D1
0x18001b4b6  test    byte ptr [rcx+1Ch], 2
0x18001b4ba  jz      short loc_18001B4D1
0x18001b4bc  mov     edx, 72h ; 'r'
0x18001b4c1  mov     r9d, ebx
0x18001b4c4  mov     r8, rsi
0x18001b4c7  mov     rcx, [rcx+10h]
0x18001b4cb  call    WPP_SF_d
0x18001b4d0  nop
0x18001b4d1  lea     rcx, [rsp+4D0h+var_490]
0x18001b4d6  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18001b4db  neg     r15b
0x18001b4de  sbb     rdx, rdx
0x18001b4e1  lea     rax, [rbp+3D0h+var_250]
0x18001b4e8  and     rdx, rax
0x18001b4eb  mov     [rsp+4D0h+var_498], 0
0x18001b4f3  mov     [rsp+4D0h+var_4A0], 1
0x18001b4fb  mov     [rsp+4D0h+var_4A8], 0
0x18001b504  lea     r9, [rsp+4D0h+var_460]
0x18001b509  lea     r8, aWerinternalmet_0; ".WERInternalMetadata.xml"
0x18001b510  lea     rcx, [rsp+4D0h+hObject]
0x18001b515  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18001b51a  mov     ebx, eax
0x18001b51c  test    eax, eax
0x18001b51e  jns     short loc_18001B553
0x18001b520  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b527  cmp     rcx, rdi
0x18001b52a  jz      loc_18001B61B
0x18001b530  test    byte ptr [rcx+1Ch], 1
0x18001b534  jz      loc_18001B61B
0x18001b53a  mov     edx, 73h ; 's'
0x18001b53f  mov     r9d, eax
0x18001b542  mov     r8, rsi
0x18001b545  mov     rcx, [rcx+10h]
0x18001b549  call    WPP_SF_d
0x18001b54e  jmp     loc_18001B61B
0x18001b553  lea     r9, [rsp+4D0h+lpMem]
0x18001b558  mov     r8, [r14+8]
0x18001b55c  mov     rbx, [rsp+4D0h+hObject]
0x18001b561  mov     rdx, rbx
0x18001b564  mov     rcx, [r14]
0x18001b567  call    ?Create@CWerInternalMetadata@@SAJPEAVCReport@@PEAXPEAVCReportHandleInstance@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::Create(CReport *,void *,CReportHandleInstance *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001b56c  mov     r15d, eax
0x18001b56f  mov     [rsp+4D0h+hObject], 0
0x18001b578  lea     rdx, [rbx+1]
0x18001b57c  cmp     rdx, 1
0x18001b580  jbe     short loc_18001B58B
0x18001b582  mov     rcx, rbx; hObject
0x18001b585  call    cs:__imp_CloseHandle
0x18001b58b  test    r15d, r15d
0x18001b58e  jns     short loc_18001B5B6
0x18001b590  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b597  cmp     rcx, rdi
0x18001b59a  jz      short loc_18001B5B6
0x18001b59c  test    byte ptr [rcx+1Ch], 1
0x18001b5a0  jz      short loc_18001B5B6
0x18001b5a2  mov     edx, 74h ; 't'
0x18001b5a7  mov     r9d, r15d
0x18001b5aa  mov     r8, rsi
0x18001b5ad  mov     rcx, [rcx+10h]
0x18001b5b1  call    WPP_SF_d
0x18001b5b6  mov     rdx, [rsp+4D0h+lpMem]; wchar_t *
0x18001b5bb  cmp     rdx, [rsp+4D0h+var_478]
0x18001b5c0  jz      short loc_18001B5CA
0x18001b5c2  mov     rcx, r14; this
0x18001b5c5  call    ?AddDataCollectionFailure@CDataCollection@@QEAAJPEB_W@Z; CDataCollection::AddDataCollectionFailure(wchar_t const *)
0x18001b5ca  mov     [rsp+4D0h+var_4A8], 0; wchar_t *
0x18001b5d3  lea     rax, aWerinternalmet; "WERInternalMetadata.xml"
0x18001b5da  mov     [rsp+4D0h+var_4B0], rax; wchar_t *
0x18001b5df  lea     r9, [rsp+4D0h+var_460]; wchar_t *
0x18001b5e4  mov     edx, 5; enum _WER_FILE_TYPE
0x18001b5e9  mov     r8d, 40003h; unsigned int
0x18001b5ef  mov     rcx, [r14]; this
0x18001b5f2  call    ?AddFile@CReport@@QEAAJW4_WER_FILE_TYPE@@KPEB_W11@Z; CReport::AddFile(_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *,wchar_t const *)
0x18001b5f7  mov     ebx, eax
0x18001b5f9  test    eax, eax
0x18001b5fb  jns     short loc_18001B619
0x18001b5fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b604  cmp     rcx, rdi
0x18001b607  jz      short loc_18001B61B
0x18001b609  test    byte ptr [rcx+1Ch], 1
0x18001b60d  jz      short loc_18001B61B
0x18001b60f  mov     edx, 75h ; 'u'
0x18001b614  jmp     loc_18001B53F
0x18001b619  xor     ebx, ebx
0x18001b61b  lea     rax, [rsp+4D0h+var_470]
0x18001b620  mov     r8, [rsp+4D0h+lpMem]; lpMem
0x18001b625  cmp     r8, rax
0x18001b628  jz      short loc_18001B63A
0x18001b62a  xor     edx, edx; dwFlags
0x18001b62c  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18001b633  call    cs:__imp_HeapFree
0x18001b639  nop
0x18001b63a  mov     rcx, [rsp+4D0h+hObject]; hObject
0x18001b63f  lea     rax, [rcx+1]
0x18001b643  cmp     rax, 1
0x18001b647  jbe     short loc_18001B64F
0x18001b649  call    cs:__imp_CloseHandle
0x18001b64f  mov     eax, ebx
0x18001b651  mov     rcx, [rbp+3D0h+var_40]
0x18001b658  xor     rcx, rsp; StackCookie
0x18001b65b  call    __security_check_cookie
0x18001b660  add     rsp, 4A8h
0x18001b667  pop     r15
0x18001b669  pop     r14
0x18001b66b  pop     rdi
0x18001b66c  pop     rsi
0x18001b66d  pop     rbx
0x18001b66e  pop     rbp
0x18001b66f  retn
```

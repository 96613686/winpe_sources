# CDataCollection::AddReportMetadata(void)

- ea: `0x180009074`
- end: `0x18000945d`
- name: `?AddReportMetadata@CDataCollection@@QEAAJXZ`
- size: `1001`
- prototype: `__int64 __fastcall(CDataCollection *__hidden this)`
- caller_count: `4`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x180006ea8`
- `0x180008d48`
- `0x18001f718`
- `0x180044080`

## callees

- `0x180004c64`
- `0x180007fd8`
- `0x180008004`
- `0x180008254`
- `0x180008298`
- `0x180008698`
- `0x180009074`
- `0x180009464`
- `0x18000cf50`
- `0x180020680`
- `0x18002dc4c`
- `0x180037cb8`
- `0x180046150`
- `0x180053300`
- `0x180054568`
- `0x180093a2c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009423`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009423`
- `ext-ms-win-wer-xbox-l1-1-0!XerWriteMetadata` at `0x180009254`
- `ext-ms-win-wer-xbox-l1-1-0!XerWriteMetadata` at `0x180009254`

## string_xrefs

- `0x180009113`: `WERInternalMetadata.xml`
- `0x1800093c3`: `WERInternalMetadata.xml`
- `0x180009304`: `.WERInternalMetadata.xml`
- `0x18000922e`: `.WERXboxMetadata.xml`
- `0x18000927b`: `WERXboxMetadata.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDataCollection::AddReportMetadata(CDataCollection *this)
{
  __int64 v2; // rax
  unsigned int v3; // ebx
  wchar_t *v4; // rcx
  __int64 v5; // r11
  __int64 v6; // rdi
  __int64 v7; // r14
  unsigned __int64 v8; // rax
  __int64 v9; // rcx
  int v10; // r11d
  char v11; // r12
  int PathOfWERTempDirectory; // eax
  int TempFile; // ebx
  int v14; // eax
  __int64 v15; // rdx
  void *v16; // rbx
  int v17; // r12d
  __int64 v18; // rcx
  wchar_t *v20; // [rsp+20h] [rbp-E0h]
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  void *v22; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v24; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v25[264]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[528]; // [rsp+280h] [rbp+180h] BYREF

  v22 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
  v25[0] = 0;
  v2 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
  {
    v3 = -2147467259;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
    goto LABEL_44;
  }
  v5 = 0;
  v6 = *(_QWORD *)(v2 + 5816);
  v7 = *(_QWORD *)(v2 + 5824);
  while ( 1 )
  {
    v8 = (v7 - v6) >> 3;
    if ( (unsigned int)v5 >= (unsigned int)v8 )
      break;
    if ( (unsigned int)v5 >= v8 )
    {
      v3 = -2147352565;
LABEL_12:
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          112,
          WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
          (unsigned int)v5,
          v3);
      goto LABEL_44;
    }
    v9 = *(_QWORD *)(v6 + 8 * v5);
    v3 = 0;
    if ( !v9 )
      goto LABEL_12;
    if ( (unsigned __int8)utl::operator==<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                            v9 + 80,
                            L"WERInternalMetadata.xml") )
      goto LABEL_44;
    v5 = (unsigned int)(v10 + 1);
  }
  v11 = 1;
  PathOfWERTempDirectory = WerpGetPathOfWERTempDirectory(v26, 260);
  if ( PathOfWERTempDirectory < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        113,
        WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
        (unsigned int)PathOfWERTempDirectory);
    v11 = 0;
  }
  if ( (unsigned __int8)IsXerGetMachineIdPresent() )
  {
    v21 = 0;
    TempFile = UtilGetTempFile(
                 (__int64)&v21,
                 (WCHAR *)((unsigned __int64)v26 & -(__int64)(v11 != 0)),
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
          (__int64)&v22,
          (WCHAR *)((unsigned __int64)v26 & -(__int64)(v11 != 0)),
          (const size_t *)L".WERInternalMetadata.xml",
          v25,
          (__int64)v20,
          0,
          1u,
          0);
  v3 = v14;
  if ( v14 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_44;
    v15 = 115;
LABEL_32:
    WPP_SF_d(*((_QWORD *)v4 + 2), v15, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, (unsigned int)v14);
    goto LABEL_44;
  }
  v16 = v22;
  v17 = CWerInternalMetadata::Create(*(_QWORD *)this, v22, *((_QWORD *)this + 1), lpMem);
  v22 = 0;
  tlx::file_handle_traits::operator()(v18, v16);
  if ( v17 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      116,
      WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
      (unsigned int)v17);
  if ( lpMem[0] != lpMem[1] )
    CDataCollection::AddDataCollectionFailure((CReport **)this, (const wchar_t *)lpMem[0]);
  v14 = CReport::AddFile(*(CReport **)this, 5, 262147, v25, L"WERInternalMetadata.xml", 0);
  v3 = v14;
  if ( v14 >= 0 )
  {
    v3 = 0;
    goto LABEL_44;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v15 = 117;
    goto LABEL_32;
  }
LABEL_44:
  if ( lpMem[0] != &v24 )
    HeapFree(g_hWerheap, 0, lpMem[0]);
  tlx::file_handle_traits::operator()(v4, v22);
  return v3;
}

```

## disassembly

```asm
0x180009074  push    rbp
0x180009076  push    rbx
0x180009077  push    rdi
0x180009078  push    r12
0x18000907a  push    r14
0x18000907c  push    r15
0x18000907e  lea     rbp, [rsp-3A8h]
0x180009086  sub     rsp, 4A8h
0x18000908d  mov     rax, cs:__security_cookie
0x180009094  xor     rax, rsp
0x180009097  mov     [rbp+3D0h+var_40], rax
0x18000909e  mov     r15, rcx
0x1800090a1  mov     [rsp+4D0h+var_488], 0
0x1800090aa  lea     rcx, [rsp+4D0h+lpMem]; void *
0x1800090af  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800090b4  nop
0x1800090b5  xor     eax, eax
0x1800090b7  mov     [rsp+4D0h+var_460], ax
0x1800090bc  mov     rax, [r15]
0x1800090bf  test    rax, rax
0x1800090c2  jnz     short loc_180009102
0x1800090c4  mov     ebx, 80004005h
0x1800090c9  lea     rdi, WPP_GLOBAL_Control
0x1800090d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090d7  cmp     rcx, rdi
0x1800090da  jz      loc_18000940B
0x1800090e0  test    byte ptr [rcx+1Ch], 1
0x1800090e4  jz      loc_18000940B
0x1800090ea  lea     edx, [rax+6Fh]
0x1800090ed  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x1800090f4  mov     rcx, [rcx+10h]
0x1800090f8  call    WPP_SF_
0x1800090fd  jmp     loc_18000940B
0x180009102  xor     r11d, r11d
0x180009105  mov     rdi, [rax+16B8h]
0x18000910c  mov     r14, [rax+16C0h]
0x180009113  lea     rdx, aWerinternalmet; "WERInternalMetadata.xml"
0x18000911a  mov     rax, r14
0x18000911d  sub     rax, rdi
0x180009120  sar     rax, 3
0x180009124  cmp     r11d, eax
0x180009127  jnb     short loc_180009199
0x180009129  mov     ecx, r11d
0x18000912c  cmp     rcx, rax
0x18000912f  jnb     short loc_180009152
0x180009131  mov     rcx, [rdi+r11*8]
0x180009135  xor     ebx, ebx
0x180009137  test    rcx, rcx
0x18000913a  jz      short loc_180009157
0x18000913c  add     rcx, 50h ; 'P'
0x180009140  call    ??$?8_WU?$char_traits@_W@utl@@V?$allocator@_W@1@@utl@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@0@PEB_W@Z; utl::operator==<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,wchar_t const *)
0x180009145  test    al, al
0x180009147  jnz     loc_18000940B
0x18000914d  inc     r11d
0x180009150  jmp     short loc_180009113
0x180009152  mov     ebx, 8002000Bh
0x180009157  lea     rdi, WPP_GLOBAL_Control
0x18000915e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009165  cmp     rcx, rdi
0x180009168  jz      loc_18000940B
0x18000916e  test    byte ptr [rcx+1Ch], 1
0x180009172  jz      loc_18000940B
0x180009178  mov     edx, 70h ; 'p'
0x18000917d  mov     dword ptr [rsp+4D0h+var_4B0], ebx
0x180009181  mov     r9d, r11d
0x180009184  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18000918b  mov     rcx, [rcx+10h]
0x18000918f  call    WPP_SF_Dd
0x180009194  jmp     loc_18000940B
0x180009199  mov     r12b, 1
0x18000919c  mov     edx, 104h
0x1800091a1  lea     rcx, [rbp+3D0h+var_250]
0x1800091a8  call    WerpGetPathOfWERTempDirectory
0x1800091ad  lea     rdi, WPP_GLOBAL_Control
0x1800091b4  lea     r14, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x1800091bb  test    eax, eax
0x1800091bd  jns     short loc_1800091E8
0x1800091bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091c6  cmp     rcx, rdi
0x1800091c9  jz      short loc_1800091E5
0x1800091cb  test    byte ptr [rcx+1Ch], 2
0x1800091cf  jz      short loc_1800091E5
0x1800091d1  mov     edx, 71h ; 'q'
0x1800091d6  mov     r9d, eax
0x1800091d9  mov     r8, r14
0x1800091dc  mov     rcx, [rcx+10h]
0x1800091e0  call    WPP_SF_d
0x1800091e5  xor     r12b, r12b
0x1800091e8  call    IsXerGetMachineIdPresent
0x1800091ed  test    al, al
0x1800091ef  jz      loc_1800092D6
0x1800091f5  mov     [rsp+4D0h+var_490], 0
0x1800091fe  mov     al, r12b
0x180009201  neg     al
0x180009203  sbb     rdx, rdx
0x180009206  lea     rax, [rbp+3D0h+var_250]
0x18000920d  and     rdx, rax
0x180009210  mov     [rsp+4D0h+var_498], 0
0x180009218  mov     [rsp+4D0h+var_4A0], 1
0x180009220  mov     [rsp+4D0h+var_4A8], 0
0x180009229  lea     r9, [rsp+4D0h+var_460]
0x18000922e  lea     r8, aWerxboxmetadat_0; ".WERXboxMetadata.xml"
0x180009235  lea     rcx, [rsp+4D0h+var_490]
0x18000923a  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18000923f  mov     ebx, eax
0x180009241  test    eax, eax
0x180009243  js      short loc_1800092A5
0x180009245  mov     rcx, [r15]
0x180009248  mov     rdx, [rsp+4D0h+var_490]
0x18000924d  mov     rcx, [rcx+19F0h]
0x180009254  call    cs:__imp_XerWriteMetadata
0x18000925b  nop     dword ptr [rax+rax+00h]
0x180009260  mov     ebx, eax
0x180009262  xor     edx, edx
0x180009264  lea     rcx, [rsp+4D0h+var_490]
0x180009269  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18000926e  test    ebx, ebx
0x180009270  js      short loc_1800092A5
0x180009272  mov     [rsp+4D0h+var_4A8], 0; wchar_t *
0x18000927b  lea     rax, aWerxboxmetadat; "WERXboxMetadata.xml"
0x180009282  mov     [rsp+4D0h+var_4B0], rax; wchar_t *
0x180009287  lea     r9, [rsp+4D0h+var_460]; wchar_t *
0x18000928c  mov     edx, 5; enum _WER_FILE_TYPE
0x180009291  mov     r8d, 40003h; unsigned int
0x180009297  mov     rcx, [r15]; this
0x18000929a  call    ?AddFile@CReport@@QEAAJW4_WER_FILE_TYPE@@KPEB_W11@Z; CReport::AddFile(_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *,wchar_t const *)
0x18000929f  mov     ebx, eax
0x1800092a1  test    eax, eax
0x1800092a3  jns     short loc_1800092CC
0x1800092a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092ac  cmp     rcx, rdi
0x1800092af  jz      short loc_1800092CC
0x1800092b1  test    byte ptr [rcx+1Ch], 2
0x1800092b5  jz      short loc_1800092CC
0x1800092b7  mov     edx, 72h ; 'r'
0x1800092bc  mov     r9d, ebx
0x1800092bf  mov     r8, r14
0x1800092c2  mov     rcx, [rcx+10h]
0x1800092c6  call    WPP_SF_d
0x1800092cb  nop
0x1800092cc  lea     rcx, [rsp+4D0h+var_490]
0x1800092d1  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800092d6  neg     r12b
0x1800092d9  sbb     rdx, rdx
0x1800092dc  lea     rax, [rbp+3D0h+var_250]
0x1800092e3  and     rdx, rax
0x1800092e6  mov     [rsp+4D0h+var_498], 0
0x1800092ee  mov     [rsp+4D0h+var_4A0], 1
0x1800092f6  mov     [rsp+4D0h+var_4A8], 0
0x1800092ff  lea     r9, [rsp+4D0h+var_460]
0x180009304  lea     r8, aWerinternalmet_0; ".WERInternalMetadata.xml"
0x18000930b  lea     rcx, [rsp+4D0h+var_488]
0x180009310  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180009315  mov     ebx, eax
0x180009317  test    eax, eax
0x180009319  jns     short loc_18000934E
0x18000931b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009322  cmp     rcx, rdi
0x180009325  jz      loc_18000940B
0x18000932b  test    byte ptr [rcx+1Ch], 1
0x18000932f  jz      loc_18000940B
0x180009335  mov     edx, 73h ; 's'
0x18000933a  mov     r9d, eax
0x18000933d  mov     r8, r14
0x180009340  mov     rcx, [rcx+10h]
0x180009344  call    WPP_SF_d
0x180009349  jmp     loc_18000940B
0x18000934e  lea     r9, [rsp+4D0h+lpMem]
0x180009353  mov     r8, [r15+8]
0x180009357  mov     rbx, [rsp+4D0h+var_488]
0x18000935c  mov     rdx, rbx
0x18000935f  mov     rcx, [r15]
0x180009362  call    ?Create@CWerInternalMetadata@@SAJPEAVCReport@@PEAXPEAVCReportHandleInstance@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CWerInternalMetadata::Create(CReport *,void *,CReportHandleInstance *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180009367  mov     r12d, eax
0x18000936a  mov     [rsp+4D0h+var_488], 0
0x180009373  mov     rdx, rbx
0x180009376  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18000937b  test    r12d, r12d
0x18000937e  jns     short loc_1800093A6
0x180009380  mov     rcx, cs:WPP_GLOBAL_Control
0x180009387  cmp     rcx, rdi
0x18000938a  jz      short loc_1800093A6
0x18000938c  test    byte ptr [rcx+1Ch], 1
0x180009390  jz      short loc_1800093A6
0x180009392  mov     edx, 74h ; 't'
0x180009397  mov     r9d, r12d
0x18000939a  mov     r8, r14
0x18000939d  mov     rcx, [rcx+10h]
0x1800093a1  call    WPP_SF_d
0x1800093a6  mov     rdx, [rsp+4D0h+lpMem]; wchar_t *
0x1800093ab  cmp     rdx, [rsp+4D0h+var_478]
0x1800093b0  jz      short loc_1800093BA
0x1800093b2  mov     rcx, r15; this
0x1800093b5  call    ?AddDataCollectionFailure@CDataCollection@@QEAAJPEB_W@Z; CDataCollection::AddDataCollectionFailure(wchar_t const *)
0x1800093ba  mov     [rsp+4D0h+var_4A8], 0; wchar_t *
0x1800093c3  lea     rax, aWerinternalmet; "WERInternalMetadata.xml"
0x1800093ca  mov     [rsp+4D0h+var_4B0], rax; wchar_t *
0x1800093cf  lea     r9, [rsp+4D0h+var_460]; wchar_t *
0x1800093d4  mov     edx, 5; enum _WER_FILE_TYPE
0x1800093d9  mov     r8d, 40003h; unsigned int
0x1800093df  mov     rcx, [r15]; this
0x1800093e2  call    ?AddFile@CReport@@QEAAJW4_WER_FILE_TYPE@@KPEB_W11@Z; CReport::AddFile(_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *,wchar_t const *)
0x1800093e7  mov     ebx, eax
0x1800093e9  test    eax, eax
0x1800093eb  jns     short loc_180009409
0x1800093ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093f4  cmp     rcx, rdi
0x1800093f7  jz      short loc_18000940B
0x1800093f9  test    byte ptr [rcx+1Ch], 1
0x1800093fd  jz      short loc_18000940B
0x1800093ff  mov     edx, 75h ; 'u'
0x180009404  jmp     loc_18000933A
0x180009409  xor     ebx, ebx
0x18000940b  lea     rax, [rsp+4D0h+var_470]
0x180009410  mov     r8, [rsp+4D0h+lpMem]; lpMem
0x180009415  cmp     r8, rax
0x180009418  jz      short loc_180009430
0x18000941a  xor     edx, edx; dwFlags
0x18000941c  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180009423  call    cs:__imp_HeapFree
0x18000942a  nop     dword ptr [rax+rax+00h]
0x18000942f  nop
0x180009430  mov     rdx, [rsp+4D0h+var_488]
0x180009435  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18000943a  mov     eax, ebx
0x18000943c  mov     rcx, [rbp+3D0h+var_40]
0x180009443  xor     rcx, rsp; StackCookie
0x180009446  call    __security_check_cookie
0x18000944b  add     rsp, 4A8h
0x180009452  pop     r15
0x180009454  pop     r14
0x180009456  pop     r12
0x180009458  pop     rdi
0x180009459  pop     rbx
0x18000945a  pop     rbp
0x18000945b  retn
```

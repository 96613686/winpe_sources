# CReportManager::Initialize(void *,CSettings const *)

- ea: `0x180008a48`
- end: `0x180008e2e`
- name: `?Initialize@CReportManager@@QEAAJPEAXPEBVCSettings@@@Z`
- size: `998`
- prototype: `__int64 __fastcall(CReportManager *__hidden this, void *, const struct CSettings *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting`

## callers

- `0x1800083c8`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x180007e34`
- `0x180007f98`
- `0x18000805c`
- `0x180008088`
- `0x180008110`
- `0x180008568`
- `0x180008a48`
- `0x180009758`
- `0x18000bc10`
- `0x18000dad0`
- `0x18001fe24`
- `0x18002bed4`
- `0x18002ca58`
- `0x18003db78`
- `0x18004230c`
- `0x1800678f0`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008c82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008cad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008c82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008cad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008da6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008da6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dfe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008d4b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008dc8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008d4b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008dc8`

## string_xrefs

- `0x180008adb`: `onecore\windows\feedback\core\werdll\lib\reportmanager.cpp`
- `0x180008b13`: `onecore\windows\feedback\core\werdll\lib\reportmanager.cpp`
- `0x180008b73`: `onecore\windows\feedback\core\werdll\lib\reportmanager.cpp`
- `0x180008ba9`: `onecore\windows\feedback\core\werdll\lib\reportmanager.cpp`
- `0x180008bfd`: `onecore\windows\feedback\core\werdll\lib\reportmanager.cpp`
- `0x180008c5a`: `onecore\windows\feedback\core\werdll\lib\reportmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CReportManager::Initialize(void **this, void *a2, const struct CSettings *a3)
{
  void **v6; // rax
  __int64 result; // rax
  CReportArchive *v8; // rsi
  unsigned int v9; // edi
  __int64 v10; // r9
  __int64 v11; // rdx
  int v12; // eax
  int MachineStoreDir; // eax
  unsigned int v14; // ebx
  __int64 v15; // rcx
  int v16; // eax
  CReportQueue *v17; // rbx
  __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  __int64 v26; // rdx
  DWORD v27; // eax
  HANDLE v28; // rax
  CReportArchive *v29; // [rsp+20h] [rbp-50h] BYREF
  LPVOID lpMem[2]; // [rsp+28h] [rbp-48h] BYREF
  _BYTE v31[16]; // [rsp+38h] [rbp-38h] BYREF
  wchar_t *v32[2]; // [rsp+48h] [rbp-28h] BYREF
  char v33; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  CReportQueue *v35; // [rsp+B8h] [rbp+48h] BYREF

  if ( !UtilIsWinPE() )
  {
    v6 = tlx::replace<tlx::file_handle_traits>(this + 30);
    result = WerpCreateMachineStore(v6);
    if ( (int)result < 0 )
      return result;
  }
  if ( !UtilIsWinPE() )
  {
    utl::make_unique<CReportArchive,,0>(&v29);
    v8 = v29;
    if ( !v29 )
    {
      v9 = -2147024882;
      v10 = 2147942414LL;
      v11 = 233;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportmanager.cpp",
        (const char *)v10,
        (int)v29);
LABEL_26:
      utl::unique_ptr<CReportArchive,utl::default_delete<CReportArchive>>::~unique_ptr<CReportArchive,utl::default_delete<CReportArchive>>(&v29);
      return v9;
    }
    v12 = (*(__int64 (__fastcall **)(CReportArchive *))(*(_QWORD *)v29 + 24LL))(v29);
    v9 = v12;
    if ( v12 < 0 )
    {
      v10 = (unsigned int)v12;
      v11 = 236;
      goto LABEL_8;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
    MachineStoreDir = CReportStore::GetMachineStoreDir((__int64 (__fastcall ***)(_QWORD))v8, (__int64)lpMem);
    v14 = MachineStoreDir;
    if ( MachineStoreDir < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEF,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportmanager.cpp",
        (const char *)(unsigned int)MachineStoreDir,
        (int)v29);
      if ( lpMem[0] != v31 )
        HeapFree(g_hWerheap, 0, lpMem[0]);
      if ( v8 )
        utl::default_delete<CReportArchive>::operator()(v15, (__int64)v8);
      return v14;
    }
    v16 = UtilVerifyAndLockDirectory((wchar_t *)lpMem[0], (__int64)(this + 31));
    v9 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportmanager.cpp",
        (const char *)(unsigned int)v16,
        (int)v29);
LABEL_25:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpMem);
      goto LABEL_26;
    }
    utl::make_unique<CReportQueue,,0>(&v35);
    v17 = v35;
    if ( !v35 )
    {
      v9 = -2147024882;
      v18 = 2147942414LL;
      v19 = 243;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportmanager.cpp",
        (const char *)v18,
        (int)v29);
LABEL_24:
      utl::unique_ptr<CReportQueue,utl::default_delete<CReportQueue>>::~unique_ptr<CReportQueue,utl::default_delete<CReportQueue>>((__int64 *)&v35);
      goto LABEL_25;
    }
    v20 = (*(__int64 (__fastcall **)(CReportQueue *))(*(_QWORD *)v35 + 24LL))(v35);
    v9 = v20;
    if ( v20 < 0 )
    {
      v18 = (unsigned int)v20;
      v19 = 246;
      goto LABEL_19;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v32);
    v21 = CReportStore::GetMachineStoreDir((__int64 (__fastcall ***)(_QWORD))v17, (__int64)v32);
    v9 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF9,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportmanager.cpp",
        (const char *)(unsigned int)v21,
        (int)v29);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v32);
      goto LABEL_24;
    }
    v22 = UtilVerifyAndLockDirectory(v32[0], (__int64)(this + 32));
    v9 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFA,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportmanager.cpp",
        (const char *)(unsigned int)v22,
        (int)v29);
      if ( (char *)v32[0] != &v33 )
        HeapFree(g_hWerheap, 0, v32[0]);
      if ( v17 )
        utl::default_delete<CReportArchive>::operator()(v23, (__int64)v17);
      if ( lpMem[0] != v31 )
        HeapFree(g_hWerheap, 0, lpMem[0]);
      if ( v8 )
        utl::default_delete<CReportArchive>::operator()(v23, (__int64)v8);
      return v9;
    }
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v32);
    utl::unique_ptr<CReportQueue,utl::default_delete<CReportQueue>>::~unique_ptr<CReportQueue,utl::default_delete<CReportQueue>>((__int64 *)&v35);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpMem);
    utl::unique_ptr<CReportArchive,utl::default_delete<CReportArchive>>::~unique_ptr<CReportArchive,utl::default_delete<CReportArchive>>(&v29);
  }
  this[12] = a3;
  if ( a2 )
  {
    this[33] = a2;
    EventW = CreateEventW(0, 1, 0, 0);
    tlx::unique_any<tlx::file_handle_traits>::reset(this + 34, EventW);
    if ( this[34] == (void *)-1LL || (char *)this[34] + 1 == (void *)1 )
    {
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_48;
      LastError = GetLastError();
      v26 = 12;
    }
    else
    {
      v28 = CreateEventW(0, 1, 0, 0);
      tlx::unique_any<tlx::file_handle_traits>::reset(this + 35, v28);
      if ( this[35] != (void *)-1LL && (char *)this[35] + 1 != (void *)1 )
      {
        *((_DWORD *)this + 30) = 0;
        return 0;
      }
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      {
LABEL_48:
        v27 = GetLastError();
        return ERROR_HR_FROM_WIN32(v27);
      }
      LastError = GetLastError();
      v26 = 13;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, LastError);
    goto LABEL_48;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180008a48  mov     [rsp-28h+arg_0], rbx
0x180008a4d  mov     [rsp-28h+arg_8], rsi
0x180008a52  push    rbp
0x180008a53  push    rdi
0x180008a54  push    r12
0x180008a56  push    r14
0x180008a58  push    r15
0x180008a5a  mov     rbp, rsp
0x180008a5d  sub     rsp, 70h
0x180008a61  mov     r12, r8
0x180008a64  mov     r15, rdx
0x180008a67  mov     r14, rcx
0x180008a6a  call    ?UtilIsWinPE@@YA_NXZ; UtilIsWinPE(void)
0x180008a6f  test    al, al
0x180008a71  jnz     short loc_180008A8F
0x180008a73  lea     rcx, [r14+0F0h]
0x180008a7a  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180008a7f  mov     rcx, rax
0x180008a82  call    WerpCreateMachineStore
0x180008a87  test    eax, eax
0x180008a89  js      loc_180008E15
0x180008a8f  call    ?UtilIsWinPE@@YA_NXZ; UtilIsWinPE(void)
0x180008a94  test    al, al
0x180008a96  jnz     loc_180008CF1
0x180008a9c  lea     rcx, [rbp+var_50]
0x180008aa0  call    ??$make_unique@VCReportArchive@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCReportArchive@@U?$default_delete@VCReportArchive@@@utl@@@0@XZ; utl::make_unique<CReportArchive,,0>(void)
0x180008aa5  nop
0x180008aa6  mov     rsi, [rbp+var_50]
0x180008aaa  test    rsi, rsi
0x180008aad  jnz     short loc_180008ABE
0x180008aaf  mov     edi, 8007000Eh
0x180008ab4  mov     r9d, edi
0x180008ab7  mov     edx, 0E9h
0x180008abc  jmp     short loc_180008ADB
0x180008abe  mov     rax, [rsi]
0x180008ac1  mov     rcx, rsi
0x180008ac4  mov     rax, [rax+18h]
0x180008ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008acd  mov     edi, eax
0x180008acf  test    eax, eax
0x180008ad1  jns     short loc_180008AF0
0x180008ad3  mov     r9d, eax; char *
0x180008ad6  mov     edx, 0ECh; void *
0x180008adb  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werdl"...
0x180008ae2  mov     rcx, [rbp+28h]; this
0x180008ae6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008aeb  jmp     loc_180008C2D
0x180008af0  lea     rcx, [rbp+lpMem]; void *
0x180008af4  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180008af9  nop
0x180008afa  lea     rdx, [rbp+lpMem]
0x180008afe  mov     rcx, rsi
0x180008b01  call    ?GetMachineStoreDir@CReportStore@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::GetMachineStoreDir(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180008b06  mov     ebx, eax
0x180008b08  test    eax, eax
0x180008b0a  jns     short loc_180008B56
0x180008b0c  mov     rcx, [rbp+28h]; this
0x180008b10  mov     r9d, eax; char *
0x180008b13  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werdl"...
0x180008b1a  mov     edx, 0EFh; void *
0x180008b1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b24  nop
0x180008b25  lea     rax, [rbp+var_38]
0x180008b29  mov     r8, [rbp+lpMem]; lpMem
0x180008b2d  cmp     r8, rax
0x180008b30  jz      short loc_180008B42
0x180008b32  xor     edx, edx; dwFlags
0x180008b34  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180008b3b  call    cs:__imp_HeapFree
0x180008b41  nop
0x180008b42  test    rsi, rsi
0x180008b45  jz      short loc_180008B4F
0x180008b47  mov     rdx, rsi
0x180008b4a  call    ??R?$default_delete@VCReportArchive@@@utl@@QEBAXPEAVCReportArchive@@@Z; utl::default_delete<CReportArchive>::operator()(CReportArchive *)
0x180008b4f  mov     eax, ebx
0x180008b51  jmp     loc_180008E15
0x180008b56  lea     rdx, [r14+0F8h]
0x180008b5d  mov     rcx, [rbp+lpMem]; wchar_t *
0x180008b61  call    ?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)
0x180008b66  mov     edi, eax
0x180008b68  test    eax, eax
0x180008b6a  jns     short loc_180008B89
0x180008b6c  mov     rcx, [rbp+28h]; this
0x180008b70  mov     r9d, eax; char *
0x180008b73  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werdl"...
0x180008b7a  mov     edx, 0F0h; void *
0x180008b7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b84  jmp     loc_180008C23
0x180008b89  lea     rcx, [rbp+arg_18]
0x180008b8d  call    ??$make_unique@VCReportQueue@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCReportQueue@@U?$default_delete@VCReportQueue@@@utl@@@0@XZ; utl::make_unique<CReportQueue,,0>(void)
0x180008b92  nop
0x180008b93  mov     rbx, [rbp+arg_18]
0x180008b97  test    rbx, rbx
0x180008b9a  jnz     short loc_180008BBB
0x180008b9c  mov     edi, 8007000Eh
0x180008ba1  mov     r9d, edi; char *
0x180008ba4  mov     edx, 0F3h; void *
0x180008ba9  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werdl"...
0x180008bb0  mov     rcx, [rbp+28h]; this
0x180008bb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008bb9  jmp     short loc_180008C19
0x180008bbb  mov     rax, [rbx]
0x180008bbe  mov     rcx, rbx
0x180008bc1  mov     rax, [rax+18h]
0x180008bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bca  mov     edi, eax
0x180008bcc  test    eax, eax
0x180008bce  jns     short loc_180008BDA
0x180008bd0  mov     r9d, eax
0x180008bd3  mov     edx, 0F6h
0x180008bd8  jmp     short loc_180008BA9
0x180008bda  lea     rcx, [rbp+var_28]; void *
0x180008bde  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180008be3  nop
0x180008be4  lea     rdx, [rbp+var_28]
0x180008be8  mov     rcx, rbx
0x180008beb  call    ?GetMachineStoreDir@CReportStore@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::GetMachineStoreDir(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180008bf0  mov     edi, eax
0x180008bf2  test    eax, eax
0x180008bf4  jns     short loc_180008C3D
0x180008bf6  mov     rcx, [rbp+28h]; this
0x180008bfa  mov     r9d, eax; char *
0x180008bfd  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werdl"...
0x180008c04  mov     edx, 0F9h; void *
0x180008c09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c0e  nop
0x180008c0f  lea     rcx, [rbp+var_28]; void *
0x180008c13  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180008c18  nop
0x180008c19  lea     rcx, [rbp+arg_18]
0x180008c1d  call    ??1?$unique_ptr@VCReportQueue@@U?$default_delete@VCReportQueue@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CReportQueue,utl::default_delete<CReportQueue>>::~unique_ptr<CReportQueue,utl::default_delete<CReportQueue>>(void)
0x180008c22  nop
0x180008c23  lea     rcx, [rbp+lpMem]; void *
0x180008c27  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180008c2c  nop
0x180008c2d  lea     rcx, [rbp+var_50]
0x180008c31  call    ??1?$unique_ptr@VCReportArchive@@U?$default_delete@VCReportArchive@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CReportArchive,utl::default_delete<CReportArchive>>::~unique_ptr<CReportArchive,utl::default_delete<CReportArchive>>(void)
0x180008c36  mov     eax, edi
0x180008c38  jmp     loc_180008E15
0x180008c3d  lea     rdx, [r14+100h]
0x180008c44  mov     rcx, [rbp+var_28]; wchar_t *
0x180008c48  call    ?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)
0x180008c4d  mov     edi, eax
0x180008c4f  test    eax, eax
0x180008c51  jns     short loc_180008CCA
0x180008c53  mov     rcx, [rbp+28h]; this
0x180008c57  mov     r9d, eax; char *
0x180008c5a  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werdl"...
0x180008c61  mov     edx, 0FAh; void *
0x180008c66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c6b  nop
0x180008c6c  lea     rax, [rbp+var_18]
0x180008c70  mov     r8, [rbp+var_28]; lpMem
0x180008c74  cmp     r8, rax
0x180008c77  jz      short loc_180008C89
0x180008c79  xor     edx, edx; dwFlags
0x180008c7b  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180008c82  call    cs:__imp_HeapFree
0x180008c88  nop
0x180008c89  test    rbx, rbx
0x180008c8c  jz      short loc_180008C97
0x180008c8e  mov     rdx, rbx
0x180008c91  call    ??R?$default_delete@VCReportArchive@@@utl@@QEBAXPEAVCReportArchive@@@Z; utl::default_delete<CReportArchive>::operator()(CReportArchive *)
0x180008c96  nop
0x180008c97  lea     rax, [rbp+var_38]
0x180008c9b  mov     r8, [rbp+lpMem]; lpMem
0x180008c9f  cmp     r8, rax
0x180008ca2  jz      short loc_180008CB4
0x180008ca4  xor     edx, edx; dwFlags
0x180008ca6  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180008cad  call    cs:__imp_HeapFree
0x180008cb3  nop
0x180008cb4  test    rsi, rsi
0x180008cb7  jz      loc_180008C36
0x180008cbd  mov     rdx, rsi
0x180008cc0  call    ??R?$default_delete@VCReportArchive@@@utl@@QEBAXPEAVCReportArchive@@@Z; utl::default_delete<CReportArchive>::operator()(CReportArchive *)
0x180008cc5  jmp     loc_180008C36
0x180008cca  lea     rcx, [rbp+var_28]; void *
0x180008cce  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180008cd3  nop
0x180008cd4  lea     rcx, [rbp+arg_18]
0x180008cd8  call    ??1?$unique_ptr@VCReportQueue@@U?$default_delete@VCReportQueue@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CReportQueue,utl::default_delete<CReportQueue>>::~unique_ptr<CReportQueue,utl::default_delete<CReportQueue>>(void)
0x180008cdd  nop
0x180008cde  lea     rcx, [rbp+lpMem]; void *
0x180008ce2  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180008ce7  nop
0x180008ce8  lea     rcx, [rbp+var_50]
0x180008cec  call    ??1?$unique_ptr@VCReportArchive@@U?$default_delete@VCReportArchive@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CReportArchive,utl::default_delete<CReportArchive>>::~unique_ptr<CReportArchive,utl::default_delete<CReportArchive>>(void)
0x180008cf1  mov     [r14+60h], r12
0x180008cf5  test    r15, r15
0x180008cf8  jnz     short loc_180008D31
0x180008cfa  lea     rax, WPP_GLOBAL_Control
0x180008d01  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d08  cmp     rcx, rax
0x180008d0b  jz      short loc_180008D27
0x180008d0d  test    byte ptr [rcx+1Ch], 1
0x180008d11  jz      short loc_180008D27
0x180008d13  lea     edx, [r15+0Bh]
0x180008d17  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180008d1e  mov     rcx, [rcx+10h]
0x180008d22  call    WPP_SF_
0x180008d27  mov     eax, 80070057h
0x180008d2c  jmp     loc_180008E15
0x180008d31  mov     [r14+108h], r15
0x180008d38  lea     rbx, [r14+110h]
0x180008d3f  xor     r9d, r9d; lpName
0x180008d42  xor     r8d, r8d; bInitialState
0x180008d45  lea     edx, [r9+1]; bManualReset
0x180008d49  xor     ecx, ecx; lpEventAttributes
0x180008d4b  call    cs:__imp_CreateEventW
0x180008d51  mov     rdx, rax
0x180008d54  mov     rcx, rbx
0x180008d57  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180008d5c  mov     rax, [rbx]
0x180008d5f  inc     rax
0x180008d62  cmp     rax, 1
0x180008d66  ja      short loc_180008DB5
0x180008d68  lea     rax, WPP_GLOBAL_Control
0x180008d6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d76  cmp     rcx, rax
0x180008d79  jz      short loc_180008DA6
0x180008d7b  test    byte ptr [rcx+1Ch], 1
0x180008d7f  jz      short loc_180008DA6
0x180008d81  call    cs:__imp_GetLastError
0x180008d87  mov     edx, 0Ch
0x180008d8c  mov     r9d, eax
0x180008d8f  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180008d96  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d9d  mov     rcx, [rcx+10h]
0x180008da1  call    WPP_SF_d
0x180008da6  call    cs:__imp_GetLastError
0x180008dac  mov     ecx, eax; unsigned int
0x180008dae  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180008db3  jmp     short loc_180008E15
0x180008db5  lea     rbx, [r14+118h]
0x180008dbc  xor     r9d, r9d; lpName
0x180008dbf  xor     r8d, r8d; bInitialState
0x180008dc2  lea     edx, [r9+1]; bManualReset
0x180008dc6  xor     ecx, ecx; lpEventAttributes
0x180008dc8  call    cs:__imp_CreateEventW
0x180008dce  mov     rdx, rax
0x180008dd1  mov     rcx, rbx
0x180008dd4  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180008dd9  mov     rax, [rbx]
0x180008ddc  inc     rax
0x180008ddf  cmp     rax, 1
0x180008de3  ja      short loc_180008E0B
0x180008de5  lea     rax, WPP_GLOBAL_Control
0x180008dec  mov     rcx, cs:WPP_GLOBAL_Control
0x180008df3  cmp     rcx, rax
0x180008df6  jz      short loc_180008DA6
0x180008df8  test    byte ptr [rcx+1Ch], 1
0x180008dfc  jz      short loc_180008DA6
0x180008dfe  call    cs:__imp_GetLastError
0x180008e04  mov     edx, 0Dh
0x180008e09  jmp     short loc_180008D8C
0x180008e0b  mov     dword ptr [r14+78h], 0
0x180008e13  xor     eax, eax
0x180008e15  lea     r11, [rsp+70h+var_s0]
0x180008e1a  mov     rbx, [r11+30h]
0x180008e1e  mov     rsi, [r11+38h]
0x180008e22  mov     rsp, r11
0x180008e25  pop     r15
0x180008e27  pop     r14
0x180008e29  pop     r12
0x180008e2b  pop     rdi
0x180008e2c  pop     rbp
0x180008e2d  retn
```

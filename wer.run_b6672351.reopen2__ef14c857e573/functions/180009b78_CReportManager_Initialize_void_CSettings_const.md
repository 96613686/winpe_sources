# CReportManager::Initialize(void *,CSettings const *)

- ea: `0x180009b78`
- end: `0x180009f96`
- name: `?Initialize@CReportManager@@QEAAJPEAXPEBVCSettings@@@Z`
- size: `1054`
- prototype: `__int64 __fastcall(CReportManager *__hidden this, void *, const struct CSettings *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting`

## callers

- `0x1800094d0`

## callees

- `0x180004c64`
- `0x180008004`
- `0x180008184`
- `0x180008c1c`
- `0x180008c48`
- `0x180008cdc`
- `0x180009684`
- `0x180009b78`
- `0x18000a9f0`
- `0x18000cf50`
- `0x18000db80`
- `0x18001c368`
- `0x180020680`
- `0x18002d930`
- `0x18002e578`
- `0x18003fb94`
- `0x180045630`
- `0x18006aa00`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009dbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009ded`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009dbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009ded`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f5c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009e91`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009f20`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009e91`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009f20`

## string_xrefs

- `0x180009c0b`: `onecore\windows\feedback\core\werdll\lib\reportmanager.cpp`
- `0x180009c43`: `onecore\windows\feedback\core\werdll\lib\reportmanager.cpp`
- `0x180009ca9`: `onecore\windows\feedback\core\werdll\lib\reportmanager.cpp`
- `0x180009cdf`: `onecore\windows\feedback\core\werdll\lib\reportmanager.cpp`
- `0x180009d33`: `onecore\windows\feedback\core\werdll\lib\reportmanager.cpp`
- `0x180009d94`: `onecore\windows\feedback\core\werdll\lib\reportmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CReportManager::Initialize(CReportManager *this, void *a2, const struct CSettings *a3)
{
  __int64 v6; // rax
  __int64 result; // rax
  __int64 v8; // rsi
  unsigned int v9; // edi
  __int64 v10; // r9
  __int64 v11; // rdx
  int v12; // eax
  int MachineStoreDir; // eax
  unsigned int v14; // ebx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rbx
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
  __int64 v29; // [rsp+20h] [rbp-50h] BYREF
  LPVOID lpMem[2]; // [rsp+28h] [rbp-48h] BYREF
  _BYTE v31[16]; // [rsp+38h] [rbp-38h] BYREF
  wchar_t *v32[2]; // [rsp+48h] [rbp-28h] BYREF
  char v33; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  __int64 v35; // [rsp+B8h] [rbp+48h] BYREF

  if ( !UtilIsWinPE() )
  {
    v6 = tlx::replace<tlx::file_handle_traits>((char *)this + 240);
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
      v11 = 235;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportmanager.cpp",
        (const char *)v10,
        v29);
LABEL_26:
      utl::unique_ptr<CReportArchive,utl::default_delete<CReportArchive>>::~unique_ptr<CReportArchive,utl::default_delete<CReportArchive>>(&v29);
      return v9;
    }
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 24LL))(v29);
    v9 = v12;
    if ( v12 < 0 )
    {
      v10 = (unsigned int)v12;
      v11 = 238;
      goto LABEL_8;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
    MachineStoreDir = CReportStore::GetMachineStoreDir(v8, lpMem);
    v14 = MachineStoreDir;
    if ( MachineStoreDir < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF1,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportmanager.cpp",
        (const char *)(unsigned int)MachineStoreDir,
        v29);
      if ( lpMem[0] != v31 )
        HeapFree(g_hWerheap, 0, lpMem[0]);
      if ( v8 )
        utl::default_delete<CReportArchive>::operator()(v15, v8);
      return v14;
    }
    v16 = UtilVerifyAndLockDirectory((wchar_t *)lpMem[0], (__int64)this + 248);
    v9 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF2,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportmanager.cpp",
        (const char *)(unsigned int)v16,
        v29);
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
      v19 = 245;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportmanager.cpp",
        (const char *)v18,
        v29);
LABEL_24:
      utl::unique_ptr<CReportQueue,utl::default_delete<CReportQueue>>::~unique_ptr<CReportQueue,utl::default_delete<CReportQueue>>(&v35);
      goto LABEL_25;
    }
    v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 24LL))(v35);
    v9 = v20;
    if ( v20 < 0 )
    {
      v18 = (unsigned int)v20;
      v19 = 248;
      goto LABEL_19;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v32);
    v21 = CReportStore::GetMachineStoreDir(v17, v32);
    v9 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFB,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportmanager.cpp",
        (const char *)(unsigned int)v21,
        v29);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v32);
      goto LABEL_24;
    }
    v22 = UtilVerifyAndLockDirectory(v32[0], (__int64)this + 256);
    v9 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFC,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportmanager.cpp",
        (const char *)(unsigned int)v22,
        v29);
      if ( (char *)v32[0] != &v33 )
        HeapFree(g_hWerheap, 0, v32[0]);
      if ( v17 )
        utl::default_delete<CReportArchive>::operator()(v23, v17);
      if ( lpMem[0] != v31 )
        HeapFree(g_hWerheap, 0, lpMem[0]);
      if ( v8 )
        utl::default_delete<CReportArchive>::operator()(v23, v8);
      return v9;
    }
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v32);
    utl::unique_ptr<CReportQueue,utl::default_delete<CReportQueue>>::~unique_ptr<CReportQueue,utl::default_delete<CReportQueue>>(&v35);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpMem);
    utl::unique_ptr<CReportArchive,utl::default_delete<CReportArchive>>::~unique_ptr<CReportArchive,utl::default_delete<CReportArchive>>(&v29);
  }
  *((_QWORD *)this + 12) = a3;
  if ( a2 )
  {
    *((_QWORD *)this + 33) = a2;
    EventW = CreateEventW(0, 1, 0, 0);
    tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 272, EventW);
    if ( *((_QWORD *)this + 34) == -1 || *((_QWORD *)this + 34) == 0 )
    {
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_48;
      LastError = GetLastError();
      v26 = 12;
    }
    else
    {
      v28 = CreateEventW(0, 1, 0, 0);
      tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 280, v28);
      if ( *((_QWORD *)this + 35) != -1 && *((_QWORD *)this + 35) != 0 )
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, LastError);
    goto LABEL_48;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180009b78  mov     [rsp-28h+arg_0], rbx
0x180009b7d  mov     [rsp-28h+arg_8], rsi
0x180009b82  push    rbp
0x180009b83  push    rdi
0x180009b84  push    r12
0x180009b86  push    r14
0x180009b88  push    r15
0x180009b8a  mov     rbp, rsp
0x180009b8d  sub     rsp, 70h
0x180009b91  mov     r12, r8
0x180009b94  mov     r15, rdx
0x180009b97  mov     r14, rcx
0x180009b9a  call    ?UtilIsWinPE@@YA_NXZ; UtilIsWinPE(void)
0x180009b9f  test    al, al
0x180009ba1  jnz     short loc_180009BBF
0x180009ba3  lea     rcx, [r14+0F0h]
0x180009baa  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180009baf  mov     rcx, rax
0x180009bb2  call    WerpCreateMachineStore
0x180009bb7  test    eax, eax
0x180009bb9  js      loc_180009F7C
0x180009bbf  call    ?UtilIsWinPE@@YA_NXZ; UtilIsWinPE(void)
0x180009bc4  test    al, al
0x180009bc6  jnz     loc_180009E37
0x180009bcc  lea     rcx, [rbp+var_50]
0x180009bd0  call    ??$make_unique@VCReportArchive@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCReportArchive@@U?$default_delete@VCReportArchive@@@utl@@@0@XZ; utl::make_unique<CReportArchive,,0>(void)
0x180009bd5  nop
0x180009bd6  mov     rsi, [rbp+var_50]
0x180009bda  test    rsi, rsi
0x180009bdd  jnz     short loc_180009BEE
0x180009bdf  mov     edi, 8007000Eh
0x180009be4  mov     r9d, edi
0x180009be7  mov     edx, 0EBh
0x180009bec  jmp     short loc_180009C0B
0x180009bee  mov     rax, [rsi]
0x180009bf1  mov     rcx, rsi
0x180009bf4  mov     rax, [rax+18h]
0x180009bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bfd  mov     edi, eax
0x180009bff  test    eax, eax
0x180009c01  jns     short loc_180009C20
0x180009c03  mov     r9d, eax; char *
0x180009c06  mov     edx, 0EEh; void *
0x180009c0b  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werdl"...
0x180009c12  mov     rcx, [rbp+28h]; this
0x180009c16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c1b  jmp     loc_180009D63
0x180009c20  lea     rcx, [rbp+lpMem]; void *
0x180009c24  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180009c29  nop
0x180009c2a  lea     rdx, [rbp+lpMem]
0x180009c2e  mov     rcx, rsi
0x180009c31  call    ?GetMachineStoreDir@CReportStore@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::GetMachineStoreDir(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180009c36  mov     ebx, eax
0x180009c38  test    eax, eax
0x180009c3a  jns     short loc_180009C8C
0x180009c3c  mov     rcx, [rbp+28h]; this
0x180009c40  mov     r9d, eax; char *
0x180009c43  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werdl"...
0x180009c4a  mov     edx, 0F1h; void *
0x180009c4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c54  nop
0x180009c55  lea     rax, [rbp+var_38]
0x180009c59  mov     r8, [rbp+lpMem]; lpMem
0x180009c5d  cmp     r8, rax
0x180009c60  jz      short loc_180009C78
0x180009c62  xor     edx, edx; dwFlags
0x180009c64  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180009c6b  call    cs:__imp_HeapFree
0x180009c72  nop     dword ptr [rax+rax+00h]
0x180009c77  nop
0x180009c78  test    rsi, rsi
0x180009c7b  jz      short loc_180009C85
0x180009c7d  mov     rdx, rsi
0x180009c80  call    ??R?$default_delete@VCReportArchive@@@utl@@QEBAXPEAVCReportArchive@@@Z; utl::default_delete<CReportArchive>::operator()(CReportArchive *)
0x180009c85  mov     eax, ebx
0x180009c87  jmp     loc_180009F7C
0x180009c8c  lea     rdx, [r14+0F8h]
0x180009c93  mov     rcx, [rbp+lpMem]; wchar_t *
0x180009c97  call    ?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)
0x180009c9c  mov     edi, eax
0x180009c9e  test    eax, eax
0x180009ca0  jns     short loc_180009CBF
0x180009ca2  mov     rcx, [rbp+28h]; this
0x180009ca6  mov     r9d, eax; char *
0x180009ca9  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werdl"...
0x180009cb0  mov     edx, 0F2h; void *
0x180009cb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009cba  jmp     loc_180009D59
0x180009cbf  lea     rcx, [rbp+arg_18]
0x180009cc3  call    ??$make_unique@VCReportQueue@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCReportQueue@@U?$default_delete@VCReportQueue@@@utl@@@0@XZ; utl::make_unique<CReportQueue,,0>(void)
0x180009cc8  nop
0x180009cc9  mov     rbx, [rbp+arg_18]
0x180009ccd  test    rbx, rbx
0x180009cd0  jnz     short loc_180009CF1
0x180009cd2  mov     edi, 8007000Eh
0x180009cd7  mov     r9d, edi; char *
0x180009cda  mov     edx, 0F5h; void *
0x180009cdf  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werdl"...
0x180009ce6  mov     rcx, [rbp+28h]; this
0x180009cea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009cef  jmp     short loc_180009D4F
0x180009cf1  mov     rax, [rbx]
0x180009cf4  mov     rcx, rbx
0x180009cf7  mov     rax, [rax+18h]
0x180009cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d00  mov     edi, eax
0x180009d02  test    eax, eax
0x180009d04  jns     short loc_180009D10
0x180009d06  mov     r9d, eax
0x180009d09  mov     edx, 0F8h
0x180009d0e  jmp     short loc_180009CDF
0x180009d10  lea     rcx, [rbp+var_28]; void *
0x180009d14  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180009d19  nop
0x180009d1a  lea     rdx, [rbp+var_28]
0x180009d1e  mov     rcx, rbx
0x180009d21  call    ?GetMachineStoreDir@CReportStore@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::GetMachineStoreDir(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180009d26  mov     edi, eax
0x180009d28  test    eax, eax
0x180009d2a  jns     short loc_180009D73
0x180009d2c  mov     rcx, [rbp+28h]; this
0x180009d30  mov     r9d, eax; char *
0x180009d33  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werdl"...
0x180009d3a  mov     edx, 0FBh; void *
0x180009d3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009d44  nop
0x180009d45  lea     rcx, [rbp+var_28]; void *
0x180009d49  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180009d4e  nop
0x180009d4f  lea     rcx, [rbp+arg_18]
0x180009d53  call    ??1?$unique_ptr@VCReportQueue@@U?$default_delete@VCReportQueue@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CReportQueue,utl::default_delete<CReportQueue>>::~unique_ptr<CReportQueue,utl::default_delete<CReportQueue>>(void)
0x180009d58  nop
0x180009d59  lea     rcx, [rbp+lpMem]; void *
0x180009d5d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180009d62  nop
0x180009d63  lea     rcx, [rbp+var_50]
0x180009d67  call    ??1?$unique_ptr@VCReportArchive@@U?$default_delete@VCReportArchive@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CReportArchive,utl::default_delete<CReportArchive>>::~unique_ptr<CReportArchive,utl::default_delete<CReportArchive>>(void)
0x180009d6c  mov     eax, edi
0x180009d6e  jmp     loc_180009F7C
0x180009d73  lea     rdx, [r14+100h]
0x180009d7a  mov     rcx, [rbp+var_28]; wchar_t *
0x180009d7e  call    ?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)
0x180009d83  mov     edi, eax
0x180009d85  test    eax, eax
0x180009d87  jns     loc_180009E10
0x180009d8d  mov     rcx, [rbp+28h]; this
0x180009d91  mov     r9d, eax; char *
0x180009d94  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werdl"...
0x180009d9b  mov     edx, 0FCh; void *
0x180009da0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009da5  nop
0x180009da6  lea     rax, [rbp+var_18]
0x180009daa  mov     r8, [rbp+var_28]; lpMem
0x180009dae  cmp     r8, rax
0x180009db1  jz      short loc_180009DC9
0x180009db3  xor     edx, edx; dwFlags
0x180009db5  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180009dbc  call    cs:__imp_HeapFree
0x180009dc3  nop     dword ptr [rax+rax+00h]
0x180009dc8  nop
0x180009dc9  test    rbx, rbx
0x180009dcc  jz      short loc_180009DD7
0x180009dce  mov     rdx, rbx
0x180009dd1  call    ??R?$default_delete@VCReportArchive@@@utl@@QEBAXPEAVCReportArchive@@@Z; utl::default_delete<CReportArchive>::operator()(CReportArchive *)
0x180009dd6  nop
0x180009dd7  lea     rax, [rbp+var_38]
0x180009ddb  mov     r8, [rbp+lpMem]; lpMem
0x180009ddf  cmp     r8, rax
0x180009de2  jz      short loc_180009DFA
0x180009de4  xor     edx, edx; dwFlags
0x180009de6  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180009ded  call    cs:__imp_HeapFree
0x180009df4  nop     dword ptr [rax+rax+00h]
0x180009df9  nop
0x180009dfa  test    rsi, rsi
0x180009dfd  jz      loc_180009D6C
0x180009e03  mov     rdx, rsi
0x180009e06  call    ??R?$default_delete@VCReportArchive@@@utl@@QEBAXPEAVCReportArchive@@@Z; utl::default_delete<CReportArchive>::operator()(CReportArchive *)
0x180009e0b  jmp     loc_180009D6C
0x180009e10  lea     rcx, [rbp+var_28]; void *
0x180009e14  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180009e19  nop
0x180009e1a  lea     rcx, [rbp+arg_18]
0x180009e1e  call    ??1?$unique_ptr@VCReportQueue@@U?$default_delete@VCReportQueue@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CReportQueue,utl::default_delete<CReportQueue>>::~unique_ptr<CReportQueue,utl::default_delete<CReportQueue>>(void)
0x180009e23  nop
0x180009e24  lea     rcx, [rbp+lpMem]; void *
0x180009e28  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180009e2d  nop
0x180009e2e  lea     rcx, [rbp+var_50]
0x180009e32  call    ??1?$unique_ptr@VCReportArchive@@U?$default_delete@VCReportArchive@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CReportArchive,utl::default_delete<CReportArchive>>::~unique_ptr<CReportArchive,utl::default_delete<CReportArchive>>(void)
0x180009e37  mov     [r14+60h], r12
0x180009e3b  test    r15, r15
0x180009e3e  jnz     short loc_180009E77
0x180009e40  lea     rax, WPP_GLOBAL_Control
0x180009e47  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e4e  cmp     rcx, rax
0x180009e51  jz      short loc_180009E6D
0x180009e53  test    byte ptr [rcx+1Ch], 1
0x180009e57  jz      short loc_180009E6D
0x180009e59  lea     edx, [r15+0Bh]
0x180009e5d  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x180009e64  mov     rcx, [rcx+10h]
0x180009e68  call    WPP_SF_
0x180009e6d  mov     eax, 80070057h
0x180009e72  jmp     loc_180009F7C
0x180009e77  mov     [r14+108h], r15
0x180009e7e  lea     rbx, [r14+110h]
0x180009e85  xor     r9d, r9d; lpName
0x180009e88  xor     r8d, r8d; bInitialState
0x180009e8b  lea     edx, [r9+1]; bManualReset
0x180009e8f  xor     ecx, ecx; lpEventAttributes
0x180009e91  call    cs:__imp_CreateEventW
0x180009e98  nop     dword ptr [rax+rax+00h]
0x180009e9d  mov     rdx, rax
0x180009ea0  mov     rcx, rbx
0x180009ea3  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180009ea8  mov     rax, [rbx]
0x180009eab  inc     rax
0x180009eae  cmp     rax, 1
0x180009eb2  ja      short loc_180009F0D
0x180009eb4  lea     rax, WPP_GLOBAL_Control
0x180009ebb  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ec2  cmp     rcx, rax
0x180009ec5  jz      short loc_180009EF8
0x180009ec7  test    byte ptr [rcx+1Ch], 1
0x180009ecb  jz      short loc_180009EF8
0x180009ecd  call    cs:__imp_GetLastError
0x180009ed4  nop     dword ptr [rax+rax+00h]
0x180009ed9  mov     edx, 0Ch
0x180009ede  mov     r9d, eax
0x180009ee1  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x180009ee8  mov     rcx, cs:WPP_GLOBAL_Control
0x180009eef  mov     rcx, [rcx+10h]
0x180009ef3  call    WPP_SF_d
0x180009ef8  call    cs:__imp_GetLastError
0x180009eff  nop     dword ptr [rax+rax+00h]
0x180009f04  mov     ecx, eax; unsigned int
0x180009f06  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180009f0b  jmp     short loc_180009F7C
0x180009f0d  lea     rbx, [r14+118h]
0x180009f14  xor     r9d, r9d; lpName
0x180009f17  xor     r8d, r8d; bInitialState
0x180009f1a  lea     edx, [r9+1]; bManualReset
0x180009f1e  xor     ecx, ecx; lpEventAttributes
0x180009f20  call    cs:__imp_CreateEventW
0x180009f27  nop     dword ptr [rax+rax+00h]
0x180009f2c  mov     rdx, rax
0x180009f2f  mov     rcx, rbx
0x180009f32  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180009f37  mov     rax, [rbx]
0x180009f3a  inc     rax
0x180009f3d  cmp     rax, 1
0x180009f41  ja      short loc_180009F72
0x180009f43  lea     rax, WPP_GLOBAL_Control
0x180009f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f51  cmp     rcx, rax
0x180009f54  jz      short loc_180009EF8
0x180009f56  test    byte ptr [rcx+1Ch], 1
0x180009f5a  jz      short loc_180009EF8
0x180009f5c  call    cs:__imp_GetLastError
0x180009f63  nop     dword ptr [rax+rax+00h]
0x180009f68  mov     edx, 0Dh
0x180009f6d  jmp     loc_180009EDE
0x180009f72  mov     dword ptr [r14+78h], 0
0x180009f7a  xor     eax, eax
0x180009f7c  lea     r11, [rsp+70h+var_s0]
0x180009f81  mov     rbx, [r11+30h]
0x180009f85  mov     rsi, [r11+38h]
0x180009f89  mov     rsp, r11
0x180009f8c  pop     r15
0x180009f8e  pop     r14
0x180009f90  pop     r12
0x180009f92  pop     rdi
0x180009f93  pop     rbp
0x180009f94  retn
```

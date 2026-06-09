# ReadAndDecompress(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x1800602e4`
- end: `0x180060650`
- name: `?ReadAndDecompress@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z`
- size: `876`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180060660`

## callees

- `0x180001148`
- `0x180004560`
- `0x18000d030`
- `0x18000d400`
- `0x18000d5a4`
- `0x180019d4c`
- `0x18001c130`
- `0x18001c208`
- `0x18005e8cc`
- `0x1800602e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060399`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006047c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060399`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006047c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180060366`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180060366`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18006041b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18006041b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18006038f`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18006038f`
- `Cabinet!__imp_CreateDecompressor` at `0x18006043e`
- `Cabinet!__imp_CreateDecompressor` at `0x18006043e`
- `Cabinet!__imp_Decompress` at `0x18006046e`
- `Cabinet!__imp_Decompress` at `0x1800604f6`
- `Cabinet!__imp_Decompress` at `0x18006046e`
- `Cabinet!__imp_Decompress` at `0x1800604f6`
- `Cabinet!__imp_CloseDecompressor` at `0x180060553`
- `Cabinet!__imp_CloseDecompressor` at `0x180060553`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ReadAndDecompress(__int64 a1, __int64 a2)
{
  __int64 v2; // r13
  void *v3; // r14
  _BYTE *v4; // rsi
  __int64 LowPart; // r15
  const WCHAR *v6; // rax
  HANDLE FileW; // rax
  const struct std::nothrow_t *v8; // rdx
  void *v9; // rbx
  signed int v10; // ebx
  signed int LastError; // eax
  void *v12; // rax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  _BYTE v17[32]; // [rsp+0h] [rbp-D8h] BYREF
  DWORD v18; // [rsp+40h] [rbp-98h] BYREF
  __int64 v19; // [rsp+48h] [rbp-90h]
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp-88h] BYREF
  __int64 v21; // [rsp+58h] [rbp-80h] BYREF
  __int64 v22; // [rsp+60h] [rbp-78h] BYREF
  __int64 v23; // [rsp+68h] [rbp-70h] BYREF
  unsigned __int64 v24; // [rsp+70h] [rbp-68h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+78h] [rbp-60h] BYREF
  unsigned __int64 v26; // [rsp+80h] [rbp-58h] BYREF
  __int64 v27; // [rsp+88h] [rbp-50h] BYREF
  HANDLE v28; // [rsp+90h] [rbp-48h] BYREF
  __int64 v29; // [rsp+98h] [rbp-40h]

  v19 = a2;
  v2 = a1;
  v27 = a2;
  v29 = a1;
  v21 = 0;
  v3 = 0;
  v4 = 0;
  FileSize.QuadPart = 0;
  v26 = 0;
  v22 = 0;
  LODWORD(LowPart) = 0;
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  FileW = CreateFileW(v6, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v9 = FileW;
  v28 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v10 = -2147024890;
    goto LABEL_23;
  }
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
LABEL_4:
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError <= 0 )
      goto LABEL_23;
    goto LABEL_5;
  }
  if ( FileSize.QuadPart > 0x3FFFFFF )
  {
    v10 = -2147024673;
    goto LABEL_23;
  }
  LowPart = FileSize.LowPart;
  v18 = FileSize.LowPart;
  v12 = operator new[](FileSize.LowPart, (const struct std::nothrow_t *)std::nothrow);
  v3 = v12;
  v23 = (__int64)v12;
  if ( !v12 )
    goto LABEL_9;
  NumberOfBytesRead = 0;
  if ( !ReadFile(v9, v12, LowPart, &NumberOfBytesRead, 0)
    || NumberOfBytesRead != (_DWORD)LowPart
    || !(unsigned int)CreateDecompressor(2, 0, &v21) )
  {
    goto LABEL_4;
  }
  v10 = 0;
  if ( !(unsigned int)Decompress(v21, v3, LowPart, 0, 0, &v26) )
  {
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      if ( v26 > 0x3FFFFFF )
      {
        v10 = -2147023434;
        goto LABEL_23;
      }
      v4 = operator new[](v26 + 1, (const struct std::nothrow_t *)std::nothrow);
      v24 = (unsigned __int64)v4;
      if ( !v4 )
      {
LABEL_9:
        v10 = -2147024882;
        goto LABEL_23;
      }
      if ( !(unsigned int)Decompress(v21, v3, LowPart, v4, v26, &v22) )
        goto LABEL_4;
      if ( !v22 )
      {
        v10 = -2147024664;
        goto LABEL_23;
      }
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        v4[v22] = 0;
        std::string::_Assign<char>(v19, v4, v22);
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          v8 = (const struct std::nothrow_t *)v17;
          LODWORD(v19) = -2147024882;
          v2 = v29;
          LODWORD(LowPart) = v18;
          v4 = (_BYTE *)v24;
          v3 = (void *)v23;
          v10 = -2147024882;
          __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18006052E);
          goto LABEL_23;
        }
        if ( __eh34_catch_type(0, &std::length_error `RTTI Type Descriptor', 0) )
        {
          v8 = (const struct std::nothrow_t *)v17;
          LODWORD(v19) = -2147023434;
          v2 = v29;
          LODWORD(LowPart) = v18;
          v4 = (_BYTE *)v24;
          v3 = (void *)v23;
          v10 = -2147023434;
          __eh34_try_continuation(0, &std::length_error `RTTI Type Descriptor', &loc_18006052E);
        }
      }
    }
    else
    {
      if ( LastError > 0 )
      {
LABEL_5:
        v10 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_23;
      }
      v10 = LastError;
    }
  }
LABEL_23:
  if ( v21 )
    CloseDecompressor();
  if ( v3 )
    operator delete(v3, v8);
  if ( v4 )
    operator delete(v4, v8);
  if ( !*(_QWORD *)(v27 + 16) && v10 >= 0 )
    v10 = -2147467259;
  if ( (unsigned int)dword_1800BF100 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF100, 0x400000000000LL) )
  {
    v18 = v10;
    v27 = v22;
    v24 = (unsigned int)LowPart;
    v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v2);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v13,
      (int)byte_1800A88D3,
      v14,
      v15,
      (__int64)&v23,
      (__int64)&v24,
      (__int64)&v27,
      (__int64)&v18);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
  std::wstring::_Tidy_deallocate(v2);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800602e4  mov     r11, rsp
0x1800602e7  mov     [r11+18h], rbx
0x1800602eb  push    rsi
0x1800602ec  push    r12
0x1800602ee  push    r13
0x1800602f0  push    r14
0x1800602f2  push    r15
0x1800602f4  sub     rsp, 0B0h
0x1800602fb  mov     rax, cs:__security_cookie
0x180060302  xor     rax, rsp
0x180060305  mov     [rsp+0D8h+var_38], rax
0x18006030d  mov     [rsp+0D8h+var_90], rdx
0x180060312  mov     r13, rcx
0x180060315  mov     [rsp+0D8h+var_50], rdx
0x18006031d  mov     [r11-40h], rcx
0x180060321  mov     qword ptr [r11-80h], 0
0x180060329  xor     r14d, r14d
0x18006032c  xor     esi, esi
0x18006032e  mov     [r11-60h], rsi
0x180060332  mov     [r11-58h], rsi
0x180060336  mov     [r11-78h], rsi
0x18006033a  xor     r15d, r15d
0x18006033d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180060342  mov     [rsp+0D8h+hTemplateFile], rsi; hTemplateFile
0x180060347  mov     [rsp+0D8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18006034f  mov     [rsp+0D8h+dwCreationDisposition], 3; dwCreationDisposition
0x180060357  xor     r9d, r9d; lpSecurityAttributes
0x18006035a  mov     edx, 80000000h; dwDesiredAccess
0x18006035f  lea     r8d, [r14+1]; dwShareMode
0x180060363  mov     rcx, rax; lpFileName
0x180060366  call    cs:__imp_CreateFileW
0x18006036c  mov     rbx, rax
0x18006036f  mov     [rsp+0D8h+var_48], rax
0x180060377  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006037b  jnz     short loc_180060387
0x18006037d  mov     ebx, 80070006h
0x180060382  jmp     loc_180060549
0x180060387  lea     rdx, [rsp+0D8h+FileSize]; lpFileSize
0x18006038c  mov     rcx, rbx; hFile
0x18006038f  call    cs:__imp_GetFileSizeEx
0x180060395  test    eax, eax
0x180060397  jnz     short loc_1800603B7
0x180060399  call    cs:__imp_GetLastError
0x18006039f  mov     ebx, eax
0x1800603a1  test    eax, eax
0x1800603a3  jle     loc_180060549
0x1800603a9  movzx   ebx, ax
0x1800603ac  or      ebx, 80070000h
0x1800603b2  jmp     loc_180060549
0x1800603b7  cmp     qword ptr [rsp+0D8h+FileSize], 3FFFFFFh
0x1800603c0  jle     short loc_1800603CC
0x1800603c2  mov     ebx, 800700DFh
0x1800603c7  jmp     loc_180060549
0x1800603cc  mov     r15d, dword ptr [rsp+0D8h+FileSize]
0x1800603d1  mov     [rsp+0D8h+var_98], r15d
0x1800603d6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800603dd  mov     ecx, r15d; unsigned __int64
0x1800603e0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800603e5  mov     r14, rax
0x1800603e8  mov     [rsp+0D8h+var_70], rax
0x1800603ed  test    rax, rax
0x1800603f0  jnz     short loc_1800603FC
0x1800603f2  mov     ebx, 8007000Eh
0x1800603f7  jmp     loc_180060549
0x1800603fc  mov     [rsp+0D8h+NumberOfBytesRead], 0
0x180060404  mov     qword ptr [rsp+0D8h+dwCreationDisposition], 0; lpOverlapped
0x18006040d  lea     r9, [rsp+0D8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180060412  mov     r8d, r15d; nNumberOfBytesToRead
0x180060415  mov     rdx, r14; lpBuffer
0x180060418  mov     rcx, rbx; hFile
0x18006041b  call    cs:__imp_ReadFile
0x180060421  test    eax, eax
0x180060423  jz      loc_180060399
0x180060429  cmp     [rsp+0D8h+NumberOfBytesRead], r15d
0x18006042e  jnz     loc_180060399
0x180060434  lea     r8, [rsp+0D8h+var_80]
0x180060439  xor     edx, edx
0x18006043b  lea     ecx, [rdx+2]
0x18006043e  call    cs:__imp_CreateDecompressor
0x180060444  test    eax, eax
0x180060446  jz      loc_180060399
0x18006044c  xor     ebx, ebx
0x18006044e  lea     rax, [rsp+0D8h+var_58]
0x180060456  mov     qword ptr [rsp+0D8h+dwFlagsAndAttributes], rax
0x18006045b  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rbx
0x180060460  xor     r9d, r9d
0x180060463  mov     r8, r15
0x180060466  mov     rdx, r14
0x180060469  mov     rcx, [rsp+0D8h+var_80]
0x18006046e  call    cs:__imp_Decompress
0x180060474  test    eax, eax
0x180060476  jnz     loc_180060549
0x18006047c  call    cs:__imp_GetLastError
0x180060482  cmp     eax, 7Ah ; 'z'
0x180060485  jz      short loc_180060496
0x180060487  test    eax, eax
0x180060489  jg      loc_1800603A9
0x18006048f  mov     ebx, eax
0x180060491  jmp     loc_180060549
0x180060496  mov     rcx, [rsp+0D8h+var_58]
0x18006049e  cmp     rcx, 3FFFFFFh
0x1800604a5  jbe     short loc_1800604B1
0x1800604a7  mov     ebx, 800705B6h
0x1800604ac  jmp     loc_180060549
0x1800604b1  inc     rcx; unsigned __int64
0x1800604b4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800604bb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800604c0  mov     rsi, rax
0x1800604c3  mov     [rsp+0D8h+var_68], rax
0x1800604c8  test    rax, rax
0x1800604cb  jz      loc_1800603F2
0x1800604d1  lea     rax, [rsp+0D8h+var_78]
0x1800604d6  mov     qword ptr [rsp+0D8h+dwFlagsAndAttributes], rax
0x1800604db  mov     rax, [rsp+0D8h+var_58]
0x1800604e3  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rax
0x1800604e8  mov     r9, rsi
0x1800604eb  mov     r8, r15
0x1800604ee  mov     rdx, r14
0x1800604f1  mov     rcx, [rsp+0D8h+var_80]
0x1800604f6  call    cs:__imp_Decompress
0x1800604fc  test    eax, eax
0x1800604fe  jz      loc_180060399
0x180060504  mov     rax, [rsp+0D8h+var_78]
0x180060509  test    rax, rax
0x18006050c  jnz     short loc_180060515
0x18006050e  mov     ebx, 800700E8h
0x180060513  jmp     short loc_180060549
0x180060515  mov     byte ptr [rax+rsi], 0
0x180060519  mov     r8, [rsp+0D8h+var_78]
0x18006051e  mov     rdx, rsi
0x180060521  mov     rcx, [rsp+0D8h+var_90]
0x180060526  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x18006052b  nop
0x18006052c  jmp     short loc_180060549
0x18006052e  mov     r13, [rsp+0D8h+var_40]
0x180060536  mov     r15d, [rsp+0D8h+var_98]
0x18006053b  mov     rsi, [rsp+0D8h+var_68]
0x180060540  mov     r14, [rsp+0D8h+var_70]
0x180060545  mov     ebx, dword ptr [rsp+0D8h+var_90]
0x180060549  mov     rcx, [rsp+0D8h+var_80]
0x18006054e  test    rcx, rcx
0x180060551  jz      short loc_180060559
0x180060553  call    cs:__imp_CloseDecompressor
0x180060559  test    r14, r14
0x18006055c  jz      short loc_180060566
0x18006055e  mov     rcx, r14; void *
0x180060561  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180060566  test    rsi, rsi
0x180060569  jz      short loc_180060573
0x18006056b  mov     rcx, rsi; void *
0x18006056e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180060573  mov     rax, [rsp+0D8h+var_50]
0x18006057b  cmp     qword ptr [rax+10h], 0
0x180060580  jnz     short loc_18006058C
0x180060582  mov     eax, 80004005h
0x180060587  test    ebx, ebx
0x180060589  cmovns  ebx, eax
0x18006058c  mov     eax, cs:dword_1800BF100
0x180060592  cmp     eax, 5
0x180060595  jbe     short loc_18006060F
0x180060597  mov     rdx, 400000000000h
0x1800605a1  lea     rcx, dword_1800BF100
0x1800605a8  call    _tlgKeywordOn
0x1800605ad  test    al, al
0x1800605af  jz      short loc_18006060F
0x1800605b1  mov     [rsp+0D8h+var_98], ebx
0x1800605b5  mov     rax, [rsp+0D8h+var_78]
0x1800605ba  mov     [rsp+0D8h+var_50], rax
0x1800605c2  mov     eax, r15d
0x1800605c5  mov     [rsp+0D8h+var_68], rax
0x1800605ca  mov     rcx, r13
0x1800605cd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800605d2  mov     [rsp+0D8h+var_70], rax
0x1800605d7  lea     rax, [rsp+0D8h+var_98]
0x1800605dc  mov     [rsp+0D8h+var_A0], rax
0x1800605e1  lea     rax, [rsp+0D8h+var_50]
0x1800605e9  mov     [rsp+0D8h+hTemplateFile], rax
0x1800605ee  lea     rax, [rsp+0D8h+var_68]
0x1800605f3  mov     qword ptr [rsp+0D8h+dwFlagsAndAttributes], rax
0x1800605f8  lea     rax, [rsp+0D8h+var_70]
0x1800605fd  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rax
0x180060602  lea     rdx, byte_1800A88D3
0x180060609  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18006060e  nop
0x18006060f  lea     rcx, [rsp+0D8h+var_48]
0x180060617  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006061c  nop
0x18006061d  mov     rcx, r13
0x180060620  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180060625  mov     eax, ebx
0x180060627  mov     rcx, [rsp+0D8h+var_38]
0x18006062f  xor     rcx, rsp; StackCookie
0x180060632  call    __security_check_cookie
0x180060637  mov     rbx, [rsp+0D8h+arg_10]
0x18006063f  add     rsp, 0B0h
0x180060646  pop     r15
0x180060648  pop     r14
0x18006064a  pop     r13
0x18006064c  pop     r12
0x18006064e  pop     rsi
0x18006064f  retn
```

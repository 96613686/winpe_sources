# I_ReadFile(VCARD_DATA const *,ushort const *,ushort const *,std::vector<uchar,wil::secure_allocator<uchar>> *)

- ea: `0x18002b4a4`
- end: `0x18002b839`
- name: `?I_ReadFile@@YAKPEBUVCARD_DATA@@PEBG1PEAV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z`
- size: `917`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002b840`

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x18000d368`
- `0x180015384`
- `0x180015638`
- `0x180017b2c`
- `0x180017be4`
- `0x1800258f4`
- `0x18002a2a0`
- `0x18002a7dc`
- `0x18002a92c`
- `0x18002b4a4`
- `0x1800348a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b61c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b61c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b709`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b599`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b599`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002b60a`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002b60a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002b6f7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002b6f7`

## string_xrefs

- `0x18002b4df`: `I_ReadFile`
- `0x18002b5ef`: `Unable to open file`
- `0x18002b744`: `Unable to read file`
- `0x18002b797`: `Unable to read the whole file`

## pseudocode

```c
__int64 __fastcall I_ReadFile(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  const WCHAR *v10; // rax
  HANDLE FileW; // rax
  __int64 v12; // rcx
  void *v13; // rbx
  DWORD LastError; // ebx
  _QWORD *v15; // rax
  int v16; // edx
  const char *v17; // rcx
  __int64 v18; // rcx
  DWORD v19; // eax
  _QWORD *v20; // r10
  int v21; // edx
  const char *v22; // rcx
  LPVOID v23; // r8
  unsigned __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v29; // [rsp+40h] [rbp-49h] BYREF
  int v30; // [rsp+44h] [rbp-45h] BYREF
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-41h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp-39h] BYREF
  HANDLE v33; // [rsp+58h] [rbp-31h] BYREF
  _QWORD *v34; // [rsp+60h] [rbp-29h] BYREF
  _QWORD v35[3]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v36[32]; // [rsp+80h] [rbp-9h] BYREF
  char v37[16]; // [rsp+A0h] [rbp+17h] BYREF

  v29 = 0;
  v30 = 0;
  strcpy(v37, "I_ReadFile");
  v35[0] = v37;
  v35[1] = &v30;
  v35[2] = &v29;
  lambda_b448e88b2beeb7a27119ad6d20e4c8e5_::operator()(v35);
  v30 = 1;
  v34 = v35;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)v36);
  I_ComposeFilePath(a1, a2, a3, (__int64)v36);
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  FileW = CreateFileW(v10, 0x80000000, 0, 0, 3u, 0x80u, 0);
  v13 = FileW;
  v33 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    WppTraceIndent(v12, 2);
    LastError = GetLastError();
    v29 = LastError;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 29;
      v17 = "Unable to open file";
LABEL_43:
      WPP_SF_sDs(
        v15[2],
        v16,
        (unsigned int)&WPP_07138201f8c239aeb1d90374442b236d_Traceguids,
        (_DWORD)WPP_pszIndent,
        LastError,
        (__int64)v17);
      goto LABEL_44;
    }
    goto LABEL_45;
  }
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    WppTraceIndent(v18, 2);
    v19 = GetLastError();
    v29 = v19;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_20;
    }
    v21 = 30;
    v22 = "Unable to get file size";
LABEL_19:
    WPP_SF_sDs(
      v20[2],
      v21,
      (unsigned int)&WPP_07138201f8c239aeb1d90374442b236d_Traceguids,
      (_DWORD)WPP_pszIndent,
      v19,
      (__int64)v22);
    v19 = v29;
LABEL_20:
    LastError = v19;
    goto LABEL_45;
  }
  if ( FileSize.QuadPart > 0x100000uLL )
  {
    WppTraceIndent(v18, 2);
    LastError = 223;
    v29 = 223;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 31;
      v17 = "File is too large";
      goto LABEL_43;
    }
    goto LABEL_45;
  }
  v23 = (LPVOID)*a4;
  v24 = a4[1] - *a4;
  if ( FileSize.LowPart >= v24 )
  {
    if ( FileSize.LowPart <= v24 )
      goto LABEL_29;
    if ( (unsigned __int64)FileSize.LowPart > a4[2] - (_QWORD)v23 )
    {
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Resize_reallocate<std::_Value_init_tag>(
        a4,
        FileSize.LowPart);
      goto LABEL_29;
    }
    v25 = std::_Uninitialized_value_construct_n<wil::secure_allocator<unsigned char>>(
            a4[1],
            FileSize.LowPart - v24,
            (__int64)a4);
  }
  else
  {
    v25 = (__int64)v23 + FileSize.LowPart;
  }
  a4[1] = v25;
LABEL_29:
  NumberOfBytesRead = 0;
  if ( !ReadFile(v13, (LPVOID)*a4, *((_DWORD *)a4 + 2) - *(_DWORD *)a4, &NumberOfBytesRead, 0) )
  {
    WppTraceIndent(v26, 2);
    v19 = GetLastError();
    v29 = v19;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_20;
    }
    v21 = 32;
    v22 = "Unable to read file";
    goto LABEL_19;
  }
  v27 = a4[1] - *a4;
  if ( v27 == NumberOfBytesRead )
  {
LABEL_44:
    LastError = v29;
    goto LABEL_45;
  }
  WppTraceIndent(v27, 2);
  LastError = 30;
  v29 = 30;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = 33;
    v17 = "Unable to read the whole file";
    goto LABEL_43;
  }
LABEL_45:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
  std::wstring::_Tidy_deallocate((__int64)v36);
  WppTraceUnwinder__lambda_b448e88b2beeb7a27119ad6d20e4c8e5____::_WppTraceUnwinder__lambda_b448e88b2beeb7a27119ad6d20e4c8e5____(&v34);
  return LastError;
}

```

## disassembly

```asm
0x18002b4a4  push    rbp
0x18002b4a6  push    rbx
0x18002b4a7  push    rsi
0x18002b4a8  push    rdi
0x18002b4a9  push    r14
0x18002b4ab  lea     rbp, [rsp-37h]
0x18002b4b0  sub     rsp, 0C0h
0x18002b4b7  mov     rax, cs:__security_cookie
0x18002b4be  xor     rax, rsp
0x18002b4c1  mov     [rbp+57h+var_30], rax
0x18002b4c5  mov     rdi, r9
0x18002b4c8  mov     rsi, r8
0x18002b4cb  mov     rbx, rdx
0x18002b4ce  mov     r14, rcx
0x18002b4d1  mov     [rbp+57h+var_A0], 0
0x18002b4d8  mov     [rbp+57h+var_9C], 0
0x18002b4df  movsd   xmm0, qword ptr cs:aIReadfile; "I_ReadFile"
0x18002b4e7  movsd   qword ptr [rbp+57h+var_40], xmm0
0x18002b4ec  mov     eax, dword ptr cs:aIReadfile+7; "ile"
0x18002b4f2  mov     dword ptr [rbp+57h+var_40+7], eax
0x18002b4f5  lea     rax, [rbp+57h+var_40]
0x18002b4f9  mov     [rbp+57h+var_78], rax
0x18002b4fd  lea     rax, [rbp+57h+var_9C]
0x18002b501  mov     [rbp+57h+var_70], rax
0x18002b505  lea     rax, [rbp+57h+var_A0]
0x18002b509  mov     [rbp+57h+var_68], rax
0x18002b50d  lea     rcx, [rbp+57h+var_78]
0x18002b511  call    _lambda_b448e88b2beeb7a27119ad6d20e4c8e5___operator__
0x18002b516  mov     [rbp+57h+var_9C], 1
0x18002b51d  lea     rax, [rbp+57h+var_78]
0x18002b521  mov     [rbp+57h+var_80], rax
0x18002b525  test    r14, r14
0x18002b528  jnz     short loc_18002B52F
0x18002b52a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002b52f  test    rbx, rbx
0x18002b532  jnz     short loc_18002B539
0x18002b534  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002b539  test    rsi, rsi
0x18002b53c  jnz     short loc_18002B543
0x18002b53e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002b543  test    rdi, rdi
0x18002b546  jnz     short loc_18002B54D
0x18002b548  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002b54d  lea     rcx, [rbp+57h+var_60]
0x18002b551  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18002b556  nop
0x18002b557  lea     r9, [rbp+57h+var_60]
0x18002b55b  mov     r8, rsi
0x18002b55e  mov     rdx, rbx
0x18002b561  mov     rcx, r14
0x18002b564  call    I_ComposeFilePath
0x18002b569  lea     rcx, [rbp+57h+var_60]
0x18002b56d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b572  mov     rcx, rax; lpFileName
0x18002b575  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x18002b57e  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002b586  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002b58e  xor     r9d, r9d; lpSecurityAttributes
0x18002b591  xor     r8d, r8d; dwShareMode
0x18002b594  mov     edx, 80000000h; dwDesiredAccess
0x18002b599  call    cs:__imp_CreateFileW
0x18002b59f  mov     rbx, rax
0x18002b5a2  mov     [rbp+57h+var_88], rax
0x18002b5a6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b5aa  jnz     short loc_18002B5FB
0x18002b5ac  lea     edx, [rax+3]
0x18002b5af  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002b5b4  call    cs:__imp_GetLastError
0x18002b5ba  mov     ebx, eax
0x18002b5bc  mov     [rbp+57h+var_A0], eax
0x18002b5bf  lea     rcx, WPP_GLOBAL_Control
0x18002b5c6  mov     rax, cs:WPP_GLOBAL_Control
0x18002b5cd  cmp     rax, rcx
0x18002b5d0  jz      loc_18002B800
0x18002b5d6  test    byte ptr [rax+1Ch], 1
0x18002b5da  jz      loc_18002B800
0x18002b5e0  cmp     byte ptr [rax+19h], 2
0x18002b5e4  jb      loc_18002B800
0x18002b5ea  mov     edx, 1Dh
0x18002b5ef  lea     rcx, aUnableToOpenFi_0; "Unable to open file"
0x18002b5f6  jmp     loc_18002B7DD
0x18002b5fb  mov     qword ptr [rbp+57h+FileSize], 0
0x18002b603  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x18002b607  mov     rcx, rbx; hFile
0x18002b60a  call    cs:__imp_GetFileSizeEx
0x18002b610  test    eax, eax
0x18002b612  jnz     short loc_18002B67C
0x18002b614  lea     edx, [rax+2]
0x18002b617  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002b61c  call    cs:__imp_GetLastError
0x18002b622  mov     [rbp+57h+var_A0], eax
0x18002b625  lea     rcx, WPP_GLOBAL_Control
0x18002b62c  mov     r10, cs:WPP_GLOBAL_Control
0x18002b633  cmp     r10, rcx
0x18002b636  jz      short loc_18002B675
0x18002b638  test    byte ptr [r10+1Ch], 1
0x18002b63d  jz      short loc_18002B675
0x18002b63f  cmp     byte ptr [r10+19h], 2
0x18002b644  jb      short loc_18002B675
0x18002b646  mov     edx, 1Eh
0x18002b64b  lea     rcx, aUnableToGetFil; "Unable to get file size"
0x18002b652  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rcx
0x18002b657  mov     [rsp+0E0h+dwCreationDisposition], eax
0x18002b65b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002b662  lea     r8, WPP_07138201f8c239aeb1d90374442b236d_Traceguids
0x18002b669  mov     rcx, [r10+10h]
0x18002b66d  call    WPP_SF_sDs
0x18002b672  mov     eax, [rbp+57h+var_A0]
0x18002b675  mov     ebx, eax
0x18002b677  jmp     loc_18002B800
0x18002b67c  cmp     dword ptr [rbp+57h+FileSize+4], 0
0x18002b680  jnz     loc_18002B7A0
0x18002b686  cmp     dword ptr [rbp+57h+FileSize], 100000h
0x18002b68d  ja      loc_18002B7A0
0x18002b693  mov     edx, dword ptr [rbp+57h+FileSize]
0x18002b696  mov     r8, [rdi]
0x18002b699  mov     rcx, [rdi+8]
0x18002b69d  sub     rcx, r8
0x18002b6a0  cmp     rdx, rcx
0x18002b6a3  jnb     short loc_18002B6AB
0x18002b6a5  lea     rax, [r8+rdx]
0x18002b6a9  jmp     short loc_18002B6D2
0x18002b6ab  jbe     short loc_18002B6D6
0x18002b6ad  mov     rax, [rdi+10h]
0x18002b6b1  sub     rax, r8
0x18002b6b4  cmp     rdx, rax
0x18002b6b7  jbe     short loc_18002B6C3
0x18002b6b9  mov     rcx, rdi
0x18002b6bc  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002b6c1  jmp     short loc_18002B6D6
0x18002b6c3  sub     rdx, rcx
0x18002b6c6  mov     r8, rdi
0x18002b6c9  mov     rcx, [rdi+8]
0x18002b6cd  call    ??$_Uninitialized_value_construct_n@U?$secure_allocator@E@wil@@@std@@YAPEAEPEAE_KAEAU?$secure_allocator@E@wil@@@Z; std::_Uninitialized_value_construct_n<wil::secure_allocator<uchar>>(uchar *,unsigned __int64,wil::secure_allocator<uchar> &)
0x18002b6d2  mov     [rdi+8], rax
0x18002b6d6  mov     [rbp+57h+NumberOfBytesRead], 0
0x18002b6dd  mov     r8d, [rdi+8]
0x18002b6e1  sub     r8d, [rdi]; nNumberOfBytesToRead
0x18002b6e4  mov     qword ptr [rsp+0E0h+dwCreationDisposition], 0; lpOverlapped
0x18002b6ed  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002b6f1  mov     rdx, [rdi]; lpBuffer
0x18002b6f4  mov     rcx, rbx; hFile
0x18002b6f7  call    cs:__imp_ReadFile
0x18002b6fd  test    eax, eax
0x18002b6ff  jnz     short loc_18002B750
0x18002b701  lea     edx, [rax+2]
0x18002b704  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002b709  call    cs:__imp_GetLastError
0x18002b70f  mov     [rbp+57h+var_A0], eax
0x18002b712  lea     rcx, WPP_GLOBAL_Control
0x18002b719  mov     r10, cs:WPP_GLOBAL_Control
0x18002b720  cmp     r10, rcx
0x18002b723  jz      loc_18002B675
0x18002b729  test    byte ptr [r10+1Ch], 1
0x18002b72e  jz      loc_18002B675
0x18002b734  cmp     byte ptr [r10+19h], 2
0x18002b739  jb      loc_18002B675
0x18002b73f  mov     edx, 20h ; ' '
0x18002b744  lea     rcx, aUnableToReadFi; "Unable to read file"
0x18002b74b  jmp     loc_18002B652
0x18002b750  mov     rcx, [rdi+8]
0x18002b754  sub     rcx, [rdi]
0x18002b757  mov     eax, [rbp+57h+NumberOfBytesRead]
0x18002b75a  cmp     rcx, rax
0x18002b75d  jz      loc_18002B7FD
0x18002b763  mov     edx, 2
0x18002b768  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002b76d  mov     ebx, 1Eh
0x18002b772  mov     [rbp+57h+var_A0], ebx
0x18002b775  lea     rcx, WPP_GLOBAL_Control
0x18002b77c  mov     rax, cs:WPP_GLOBAL_Control
0x18002b783  cmp     rax, rcx
0x18002b786  jz      short loc_18002B800
0x18002b788  test    byte ptr [rax+1Ch], 1
0x18002b78c  jz      short loc_18002B800
0x18002b78e  cmp     byte ptr [rax+19h], 2
0x18002b792  jb      short loc_18002B800
0x18002b794  lea     edx, [rbx+3]
0x18002b797  lea     rcx, aUnableToReadTh; "Unable to read the whole file"
0x18002b79e  jmp     short loc_18002B7DD
0x18002b7a0  mov     edx, 2
0x18002b7a5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002b7aa  mov     ebx, 0DFh
0x18002b7af  mov     [rbp+57h+var_A0], ebx
0x18002b7b2  lea     rcx, WPP_GLOBAL_Control
0x18002b7b9  mov     rax, cs:WPP_GLOBAL_Control
0x18002b7c0  cmp     rax, rcx
0x18002b7c3  jz      short loc_18002B800
0x18002b7c5  test    byte ptr [rax+1Ch], 1
0x18002b7c9  jz      short loc_18002B800
0x18002b7cb  cmp     byte ptr [rax+19h], 2
0x18002b7cf  jb      short loc_18002B800
0x18002b7d1  mov     edx, 1Fh
0x18002b7d6  lea     rcx, aFileIsTooLarge; "File is too large"
0x18002b7dd  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rcx
0x18002b7e2  mov     [rsp+0E0h+dwCreationDisposition], ebx
0x18002b7e6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002b7ed  lea     r8, WPP_07138201f8c239aeb1d90374442b236d_Traceguids
0x18002b7f4  mov     rcx, [rax+10h]
0x18002b7f8  call    WPP_SF_sDs
0x18002b7fd  mov     ebx, [rbp+57h+var_A0]
0x18002b800  lea     rcx, [rbp+57h+var_88]
0x18002b804  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002b809  nop
0x18002b80a  lea     rcx, [rbp+57h+var_60]
0x18002b80e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b813  nop
0x18002b814  lea     rcx, [rbp+57h+var_80]
0x18002b818  call    WppTraceUnwinder__lambda_b448e88b2beeb7a27119ad6d20e4c8e5_______WppTraceUnwinder__lambda_b448e88b2beeb7a27119ad6d20e4c8e5____
0x18002b81d  mov     eax, ebx
0x18002b81f  mov     rcx, [rbp+57h+var_30]
0x18002b823  xor     rcx, rsp; StackCookie
0x18002b826  call    __security_check_cookie
0x18002b82b  add     rsp, 0C0h
0x18002b832  pop     r14
0x18002b834  pop     rdi
0x18002b835  pop     rsi
0x18002b836  pop     rbx
0x18002b837  pop     rbp
0x18002b838  retn
```

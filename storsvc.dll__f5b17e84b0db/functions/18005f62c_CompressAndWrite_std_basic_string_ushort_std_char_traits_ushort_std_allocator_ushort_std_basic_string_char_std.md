# CompressAndWrite(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>)

- ea: `0x18005f62c`
- end: `0x18005f8f5`
- name: `?CompressAndWrite@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z`
- size: `713`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180061950`

## callees

- `0x180001148`
- `0x180004624`
- `0x18000d030`
- `0x18000d400`
- `0x18000d5a4`
- `0x18001c130`
- `0x18001c208`
- `0x18002cd6c`
- `0x18002cd8c`
- `0x18005f62c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f6b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f6fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f6b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f6fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f821`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f821`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005f790`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005f790`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005f7b9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005f7b9`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18005f810`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18005f810`
- `Cabinet!__imp_CreateCompressor` at `0x18005f6a8`
- `Cabinet!__imp_CreateCompressor` at `0x18005f6a8`
- `Cabinet!__imp_Compress` at `0x18005f6f4`
- `Cabinet!__imp_Compress` at `0x18005f757`
- `Cabinet!__imp_Compress` at `0x18005f6f4`
- `Cabinet!__imp_Compress` at `0x18005f757`
- `Cabinet!__imp_CloseCompressor` at `0x18005f7dd`
- `Cabinet!__imp_CloseCompressor` at `0x18005f7dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CompressAndWrite(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // r12d
  unsigned __int8 v6; // r13
  BOOL v7; // edi
  __int64 v8; // r14
  BYTE *v9; // rdi
  signed int LastError; // eax
  const struct std::nothrow_t *v11; // rdx
  const BYTE *v12; // rax
  const BYTE *v13; // rax
  LONG output_buffer_size; // edx
  const WCHAR *v15; // rax
  HANDLE FileW; // rax
  __int64 v17; // r8
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  LONG *hTemplateFile; // [rsp+30h] [rbp-69h]
  LONG *hTemplateFilea; // [rsp+30h] [rbp-69h]
  INT v24; // [rsp+38h] [rbp-61h]
  INT v25; // [rsp+38h] [rbp-61h]
  char FileInformation[8]; // [rsp+50h] [rbp-49h] BYREF
  LONG input_buffer_size[2]; // [rsp+58h] [rbp-41h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp-39h] BYREF
  PVOID context; // [rsp+68h] [rbp-31h] BYREF
  unsigned int v30; // [rsp+70h] [rbp-29h] BYREF
  BOOL v31; // [rsp+74h] [rbp-25h] BYREF
  LONG input_used[2]; // [rsp+78h] [rbp-21h] BYREF
  LONG v33[2]; // [rsp+80h] [rbp-19h] BYREF
  __int64 v34; // [rsp+88h] [rbp-11h] BYREF
  __int64 v35; // [rsp+90h] [rbp-9h] BYREF
  _QWORD v36[3]; // [rsp+98h] [rbp-1h] BYREF

  v36[1] = a1;
  v36[2] = a2;
  v4 = 0;
  context = 0;
  *(_QWORD *)v33 = 0;
  *(_QWORD *)input_used = 0;
  NumberOfBytesWritten = 0;
  v5 = 0;
  v6 = 1;
  *(_QWORD *)input_buffer_size = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)input_buffer_size > 0x3FFFFFFu )
  {
    v4 = -2147023434;
    v7 = 0;
    goto LABEL_24;
  }
  v8 = -1;
  v9 = 0;
  if ( !(unsigned int)CreateCompressor(2, 0, &context) )
    goto LABEL_4;
  v12 = (const BYTE *)std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
  if ( Compress(context, v12, input_buffer_size[0], 0, 0, input_used, hTemplateFile, v24) )
    goto LABEL_11;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError != 122 )
  {
LABEL_5:
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_16;
  }
  v9 = (BYTE *)operator new[](*(unsigned __int64 *)input_used, (const struct std::nothrow_t *)std::nothrow);
  v4 = 0;
  if ( v9 )
  {
LABEL_11:
    v13 = (const BYTE *)std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
    if ( !Compress(context, v13, input_buffer_size[0], v9, output_buffer_size, v33, hTemplateFilea, v25)
      || (v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1),
          FileW = CreateFileW(v15, 0x40010000u, 0, 0, 2u, 0x80u, 0),
          v8 = (__int64)FileW,
          FileW == (HANDLE)-1LL)
      || (v5 = v33[0], !WriteFile(FileW, v9, v33[0], &NumberOfBytesWritten, 0))
      || NumberOfBytesWritten != v5 )
    {
LABEL_4:
      LastError = GetLastError();
      v4 = LastError;
      goto LABEL_5;
    }
    v6 = 0;
  }
  else
  {
    v4 = -2147024882;
  }
LABEL_16:
  if ( context )
    CloseCompressor();
  if ( v9 )
    operator delete(v9, v11);
  v7 = 0;
  if ( v8 != -1 )
  {
    if ( v6 )
    {
      FileInformation[0] = 1;
      v7 = !SetFileInformationByHandle((HANDLE)v8, FileDispositionInfo, FileInformation, 1u);
    }
    CloseHandle((HANDLE)v8);
  }
LABEL_24:
  if ( (unsigned int)dword_1800BF100 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF100, 0x400000000000LL) )
  {
    v30 = v4;
    v31 = v7;
    input_buffer_size[0] = v6;
    v34 = v5;
    v35 = v17;
    v36[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v18,
      (unsigned int)byte_1800A8843,
      v19,
      v20,
      (__int64)v36,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)input_buffer_size,
      (__int64)&v31,
      (__int64)&v30);
  }
  std::wstring::_Tidy_deallocate(a1);
  std::string::_Tidy_deallocate(a2);
  return v4;
}

```

## disassembly

```asm
0x18005f62c  mov     [rsp-8+arg_10], rbx
0x18005f631  push    rbp
0x18005f632  push    rsi
0x18005f633  push    rdi
0x18005f634  push    r12
0x18005f636  push    r13
0x18005f638  push    r14
0x18005f63a  push    r15
0x18005f63c  lea     rbp, [rsp-27h]
0x18005f641  sub     rsp, 0C0h
0x18005f648  mov     rax, cs:__security_cookie
0x18005f64f  xor     rax, rsp
0x18005f652  mov     [rbp+57h+var_40], rax
0x18005f656  mov     rsi, rdx
0x18005f659  mov     r15, rcx
0x18005f65c  mov     [rbp+57h+var_50], rcx
0x18005f660  mov     [rbp+57h+var_48], rdx
0x18005f664  xor     ebx, ebx
0x18005f666  mov     [rbp+57h+context], rbx
0x18005f66a  mov     qword ptr [rbp+57h+var_70], rbx
0x18005f66e  mov     qword ptr [rbp+57h+var_78], rbx
0x18005f672  mov     [rbp+57h+NumberOfBytesWritten], ebx
0x18005f675  mov     r12d, ebx
0x18005f678  mov     r13b, 1
0x18005f67b  mov     r8, [rdx+10h]
0x18005f67f  mov     qword ptr [rbp+57h+input_buffer_size], r8
0x18005f683  cmp     r8, 3FFFFFFh
0x18005f68a  jbe     short loc_18005F698
0x18005f68c  mov     ebx, 800705B6h
0x18005f691  xor     edi, edi
0x18005f693  jmp     loc_18005F82B
0x18005f698  or      r14, 0FFFFFFFFFFFFFFFFh
0x18005f69c  mov     rdi, rbx
0x18005f69f  lea     r8, [rbp+57h+context]
0x18005f6a3  xor     edx, edx
0x18005f6a5  lea     ecx, [rdx+2]
0x18005f6a8  call    cs:__imp_CreateCompressor
0x18005f6ae  test    eax, eax
0x18005f6b0  jnz     short loc_18005F6D0
0x18005f6b2  call    cs:__imp_GetLastError
0x18005f6b8  mov     ebx, eax
0x18005f6ba  test    eax, eax
0x18005f6bc  jle     loc_18005F7D4
0x18005f6c2  movzx   ebx, ax
0x18005f6c5  or      ebx, 80070000h
0x18005f6cb  jmp     loc_18005F7D4
0x18005f6d0  mov     rcx, rsi
0x18005f6d3  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18005f6d8  lea     rcx, [rbp+57h+var_78]
0x18005f6dc  mov     [rsp+0F0h+input_used], rcx; input_used
0x18005f6e1  mov     qword ptr [rsp+0F0h+output_buffer_size], rbx; output_buffer_size
0x18005f6e6  xor     r9d, r9d; output_buffer
0x18005f6e9  mov     r8, qword ptr [rbp+57h+input_buffer_size]; input_buffer_size
0x18005f6ed  mov     rdx, rax; input_buffer
0x18005f6f0  mov     rcx, [rbp+57h+context]; context
0x18005f6f4  call    cs:__imp_Compress
0x18005f6fa  test    eax, eax
0x18005f6fc  jnz     short loc_18005F72F
0x18005f6fe  call    cs:__imp_GetLastError
0x18005f704  mov     ebx, eax
0x18005f706  cmp     eax, 7Ah ; 'z'
0x18005f709  jnz     short loc_18005F6BA
0x18005f70b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005f712  mov     rcx, qword ptr [rbp+57h+var_78]; unsigned __int64
0x18005f716  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005f71b  mov     rdi, rax
0x18005f71e  xor     ebx, ebx
0x18005f720  test    rax, rax
0x18005f723  jnz     short loc_18005F72F
0x18005f725  mov     ebx, 8007000Eh
0x18005f72a  jmp     loc_18005F7D4
0x18005f72f  mov     rdx, qword ptr [rbp+57h+var_78]
0x18005f733  mov     rcx, rsi
0x18005f736  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18005f73b  lea     rcx, [rbp+57h+var_70]
0x18005f73f  mov     [rsp+0F0h+input_used], rcx; input_used
0x18005f744  mov     qword ptr [rsp+0F0h+output_buffer_size], rdx; output_buffer_size
0x18005f749  mov     r9, rdi; output_buffer
0x18005f74c  mov     r8, qword ptr [rbp+57h+input_buffer_size]; input_buffer_size
0x18005f750  mov     rdx, rax; input_buffer
0x18005f753  mov     rcx, [rbp+57h+context]; context
0x18005f757  call    cs:__imp_Compress
0x18005f75d  test    eax, eax
0x18005f75f  jz      loc_18005F6B2
0x18005f765  mov     rcx, r15
0x18005f768  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005f76d  mov     [rsp+0F0h+hTemplateFile], rbx; hTemplateFile
0x18005f772  mov     dword ptr [rsp+0F0h+input_used], 80h; dwFlagsAndAttributes
0x18005f77a  mov     [rsp+0F0h+output_buffer_size], 2; dwCreationDisposition
0x18005f782  xor     r9d, r9d; lpSecurityAttributes
0x18005f785  xor     r8d, r8d; dwShareMode
0x18005f788  mov     edx, 40010000h; dwDesiredAccess
0x18005f78d  mov     rcx, rax; lpFileName
0x18005f790  call    cs:__imp_CreateFileW
0x18005f796  mov     r14, rax
0x18005f799  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005f79d  jz      loc_18005F6B2
0x18005f7a3  mov     r12d, [rbp+57h+var_70]
0x18005f7a7  mov     qword ptr [rsp+0F0h+output_buffer_size], rbx; lpOverlapped
0x18005f7ac  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005f7b0  mov     r8d, r12d; nNumberOfBytesToWrite
0x18005f7b3  mov     rdx, rdi; lpBuffer
0x18005f7b6  mov     rcx, rax; hFile
0x18005f7b9  call    cs:__imp_WriteFile
0x18005f7bf  test    eax, eax
0x18005f7c1  jz      loc_18005F6B2
0x18005f7c7  cmp     [rbp+57h+NumberOfBytesWritten], r12d
0x18005f7cb  jnz     loc_18005F6B2
0x18005f7d1  xor     r13b, r13b
0x18005f7d4  mov     rcx, [rbp+57h+context]
0x18005f7d8  test    rcx, rcx
0x18005f7db  jz      short loc_18005F7E3
0x18005f7dd  call    cs:__imp_CloseCompressor
0x18005f7e3  test    rdi, rdi
0x18005f7e6  jz      short loc_18005F7F0
0x18005f7e8  mov     rcx, rdi; void *
0x18005f7eb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005f7f0  xor     edi, edi
0x18005f7f2  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18005f7f6  jz      short loc_18005F827
0x18005f7f8  test    r13b, r13b
0x18005f7fb  jz      short loc_18005F81E
0x18005f7fd  lea     eax, [rdi+1]
0x18005f800  mov     [rbp+57h+FileInformation], al
0x18005f803  mov     r9d, eax; dwBufferSize
0x18005f806  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x18005f80a  lea     edx, [rdi+4]; FileInformationClass
0x18005f80d  mov     rcx, r14; hFile
0x18005f810  call    cs:__imp_SetFileInformationByHandle
0x18005f816  test    eax, eax
0x18005f818  lea     eax, [rdi+1]
0x18005f81b  cmovz   edi, eax
0x18005f81e  mov     rcx, r14; hObject
0x18005f821  call    cs:__imp_CloseHandle
0x18005f827  mov     r8, qword ptr [rbp+57h+input_buffer_size]
0x18005f82b  mov     eax, cs:dword_1800BF100
0x18005f831  cmp     eax, 5
0x18005f834  jbe     loc_18005F8BB
0x18005f83a  mov     rdx, 400000000000h
0x18005f844  lea     rcx, dword_1800BF100
0x18005f84b  call    _tlgKeywordOn
0x18005f850  test    al, al
0x18005f852  jz      short loc_18005F8BB
0x18005f854  mov     [rbp+57h+var_80], ebx
0x18005f857  mov     [rbp+57h+var_7C], edi
0x18005f85a  movzx   eax, r13b
0x18005f85e  mov     [rbp+57h+input_buffer_size], eax
0x18005f861  mov     eax, r12d
0x18005f864  mov     [rbp+57h+var_68], rax
0x18005f868  mov     [rbp+57h+var_60], r8
0x18005f86c  mov     rcx, r15
0x18005f86f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005f874  mov     [rbp+57h+var_58], rax
0x18005f878  lea     rax, [rbp+57h+var_80]
0x18005f87c  mov     [rsp+0F0h+var_A8], rax
0x18005f881  lea     rax, [rbp+57h+var_7C]
0x18005f885  mov     [rsp+0F0h+var_B0], rax
0x18005f88a  lea     rax, [rbp+57h+input_buffer_size]
0x18005f88e  mov     [rsp+0F0h+var_B8], rax
0x18005f893  lea     rax, [rbp+57h+var_68]
0x18005f897  mov     [rsp+0F0h+hTemplateFile], rax
0x18005f89c  lea     rax, [rbp+57h+var_60]
0x18005f8a0  mov     [rsp+0F0h+input_used], rax
0x18005f8a5  lea     rax, [rbp+57h+var_58]
0x18005f8a9  mov     qword ptr [rsp+0F0h+output_buffer_size], rax
0x18005f8ae  lea     rdx, byte_1800A8843
0x18005f8b5  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U2@U?$_tlgWrapperByVal@$03@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@4AEBU?$_tlgWrapperByVal@$03@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005f8ba  nop
0x18005f8bb  mov     rcx, r15
0x18005f8be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005f8c3  nop
0x18005f8c4  mov     rcx, rsi
0x18005f8c7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005f8cc  mov     eax, ebx
0x18005f8ce  mov     rcx, [rbp+57h+var_40]
0x18005f8d2  xor     rcx, rsp; StackCookie
0x18005f8d5  call    __security_check_cookie
0x18005f8da  mov     rbx, [rsp+0F0h+arg_10]
0x18005f8e2  add     rsp, 0C0h
0x18005f8e9  pop     r15
0x18005f8eb  pop     r14
0x18005f8ed  pop     r13
0x18005f8ef  pop     r12
0x18005f8f1  pop     rdi
0x18005f8f2  pop     rsi
0x18005f8f3  pop     rbp
0x18005f8f4  retn
```

# HasExtendedAttribute(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::basic_zstring_view<char>)

- ea: `0x180057f2c`
- end: `0x180058187`
- name: `?HasExtendedAttribute@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_zstring_view@D@wil@@@Z`
- size: `603`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800582a8`

## callees

- `0x180002f50`
- `0x180004835`
- `0x18000e924`
- `0x180025228`
- `0x18002e898`
- `0x1800343d8`
- `0x180051ca8`
- `0x180055fa0`
- `0x180057f2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057fa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057fa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057fce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800580f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057fce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800580f2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180057f88`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180057f88`
- `ntdll!NtQueryEaFile` at `0x1800580c8`
- `ntdll!NtQueryEaFile` at `0x1800580c8`

## string_xrefs

- `0x180058127`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x18005816f`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall HasExtendedAttribute(char *a1, __int64 a2)
{
  char *v3; // rdi
  char *FileW; // rbx
  size_t v6; // rsi
  char *v7; // rax
  gsl::details *v8; // rcx
  unsigned int v9; // eax
  const char *v10; // rax
  const char *v11; // r9
  PVOID EaList[2]; // [rsp+50h] [rbp-9h] BYREF
  __int64 v13; // [rsp+60h] [rbp+7h]
  PVOID Buffer[2]; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v15; // [rsp+78h] [rbp+1Fh]
  char *v16; // [rsp+80h] [rbp+27h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v3 = a1;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(char **)a1;
  FileW = (char *)CreateFileW((LPCWSTR)a1, 8u, 1u, 0, 3u, 0, 0);
  v16 = FileW;
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( GetLastError() - 2 > 1 )
    {
      v10 = (const char *)std::wstring::c_str(v3);
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x14E,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
        v11,
        (unsigned int)"%ls",
        v10);
    }
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return 0;
    goto LABEL_6;
  }
  *(_OWORD *)EaList = 0;
  v13 = 0;
  v6 = *(_QWORD *)(a2 + 8);
  std::vector<enum gsl::byte>::vector<enum gsl::byte>(EaList, v6 + 8);
  v7 = (char *)EaList[0];
  *((_BYTE *)EaList[0] + 4) = v6;
  v8 = (gsl::details *)(v7 + 5);
  if ( v7 == (char *)-5LL && (_BYTE)v6 || v6 == -1 || !*(_QWORD *)a2 && v6 || (unsigned __int8)v6 < v6 )
  {
    gsl::details::terminate(v8);
    JUMPOUT(0x180058186LL);
  }
  if ( v6 )
    memmove_0(v8, *(const void **)a2, v6);
  *(_OWORD *)Buffer = 0;
  v15 = 0;
  std::vector<enum gsl::byte>::vector<enum gsl::byte>(Buffer, v6 + 12);
  IoStatusBlock = 0;
  v9 = NtQueryEaFile(
         FileW,
         &IoStatusBlock,
         Buffer[0],
         LODWORD(Buffer[1]) - LODWORD(Buffer[0]),
         0,
         EaList[0],
         LODWORD(EaList[1]) - LODWORD(EaList[0]),
         0,
         1u);
  if ( v9 != -2147483643 )
  {
    if ( *((_QWORD *)v3 + 3) > 7u )
      v3 = *(char **)v3;
    wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
      retaddr,
      (void *)0x167,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
      (const char *)v9,
      (int)"%ls",
      v3);
    std::vector<unsigned char>::~vector<unsigned char>(Buffer);
    std::vector<unsigned char>::~vector<unsigned char>(EaList);
LABEL_6:
    CloseHandle(FileW);
    return 0;
  }
  std::vector<unsigned char>::~vector<unsigned char>(Buffer);
  std::vector<unsigned char>::~vector<unsigned char>(EaList);
  CloseHandle(FileW);
  return 1;
}

```

## disassembly

```asm
0x180057f2c  mov     [rsp-8+arg_10], rbx
0x180057f31  mov     [rsp-8+arg_18], rsi
0x180057f36  push    rbp
0x180057f37  push    rdi
0x180057f38  push    r14
0x180057f3a  lea     rbp, [rsp-47h]
0x180057f3f  sub     rsp, 0A0h
0x180057f46  mov     rax, cs:__security_cookie
0x180057f4d  xor     rax, rsp
0x180057f50  mov     [rbp+57h+var_18], rax
0x180057f54  mov     r14, rdx
0x180057f57  mov     rdi, rcx
0x180057f5a  cmp     qword ptr [rcx+18h], 7
0x180057f5f  jbe     short loc_180057F64
0x180057f61  mov     rcx, [rcx]; lpFileName
0x180057f64  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x180057f6d  mov     [rsp+0B0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180057f75  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180057f7d  xor     r9d, r9d; lpSecurityAttributes
0x180057f80  lea     edx, [r9+8]; dwDesiredAccess
0x180057f84  lea     r8d, [r9+1]; dwShareMode
0x180057f88  call    cs:__imp_CreateFileW
0x180057f8f  nop     dword ptr [rax+rax+00h]
0x180057f94  mov     rbx, rax
0x180057f97  mov     [rbp+57h+var_30], rax
0x180057f9b  inc     rax
0x180057f9e  test    rax, 0FFFFFFFFFFFFFFFEh
0x180057fa4  jnz     short loc_180058001
0x180057fa6  call    cs:__imp_GetLastError
0x180057fad  nop     dword ptr [rax+rax+00h]
0x180057fb2  mov     r9d, eax
0x180057fb5  lea     edx, [rax-2]
0x180057fb8  cmp     edx, 1
0x180057fbb  ja      loc_180058152
0x180057fc1  lea     rax, [rbx-1]
0x180057fc5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180057fc9  ja      short loc_180057FDA
0x180057fcb  mov     rcx, rbx; hObject
0x180057fce  call    cs:__imp_CloseHandle
0x180057fd5  nop     dword ptr [rax+rax+00h]
0x180057fda  xor     al, al
0x180057fdc  mov     rcx, [rbp+57h+var_18]
0x180057fe0  xor     rcx, rsp; StackCookie
0x180057fe3  call    __security_check_cookie
0x180057fe8  lea     r11, [rsp+0B0h+var_10]
0x180057ff0  mov     rbx, [r11+30h]
0x180057ff4  mov     rsi, [r11+38h]
0x180057ff8  mov     rsp, r11
0x180057ffb  pop     r14
0x180057ffd  pop     rdi
0x180057ffe  pop     rbp
0x180057fff  retn
0x180058001  xorps   xmm0, xmm0
0x180058004  xor     eax, eax
0x180058006  movups  xmmword ptr [rbp+57h+EaList], xmm0
0x18005800a  mov     [rbp+57h+var_50], rax
0x18005800e  mov     rsi, [r14+8]
0x180058012  lea     rdx, [rsi+8]
0x180058016  lea     rcx, [rbp+57h+EaList]
0x18005801a  call    ??0?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,std::allocator<gsl::byte> const &)
0x18005801f  nop
0x180058020  mov     rax, [rbp+57h+EaList]
0x180058024  movzx   r8d, sil
0x180058028  mov     [rax+4], r8b
0x18005802c  lea     rcx, [rax+5]; this
0x180058030  test    rcx, rcx
0x180058033  jnz     short loc_18005803E
0x180058035  test    r8b, r8b
0x180058038  jnz     loc_180058181
0x18005803e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180058042  jz      loc_180058181
0x180058048  mov     rdx, [r14]; Src
0x18005804b  test    rdx, rdx
0x18005804e  jnz     short loc_180058059
0x180058050  test    rsi, rsi
0x180058053  jnz     loc_180058181
0x180058059  cmp     r8, rsi
0x18005805c  jb      loc_180058181
0x180058062  test    rsi, rsi
0x180058065  jz      short loc_18005806F
0x180058067  mov     r8, rsi; Size
0x18005806a  call    memmove_0
0x18005806f  xorps   xmm0, xmm0
0x180058072  xor     eax, eax
0x180058074  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x180058078  mov     [rbp+57h+var_38], rax
0x18005807c  lea     rdx, [rsi+0Ch]
0x180058080  lea     rcx, [rbp+57h+Buffer]
0x180058084  call    ??0?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,std::allocator<gsl::byte> const &)
0x180058089  nop
0x18005808a  xorps   xmm0, xmm0
0x18005808d  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180058091  mov     rcx, [rbp+57h+EaList]
0x180058095  mov     r8, [rbp+57h+Buffer]; Buffer
0x180058099  mov     eax, dword ptr [rbp+57h+EaList+8]
0x18005809c  sub     eax, ecx
0x18005809e  mov     r9d, dword ptr [rbp+57h+Buffer+8]
0x1800580a2  sub     r9d, r8d; Length
0x1800580a5  mov     [rsp+0B0h+RestartScan], 1; RestartScan
0x1800580aa  mov     [rsp+0B0h+EaIndex], 0; EaIndex
0x1800580b3  mov     dword ptr [rsp+0B0h+hTemplateFile], eax; EaListLength
0x1800580b7  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rcx; EaList
0x1800580bc  mov     byte ptr [rsp+0B0h+dwCreationDisposition], 0; ReturnSingleEntry
0x1800580c1  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800580c5  mov     rcx, rbx; FileHandle
0x1800580c8  call    cs:__imp_NtQueryEaFile
0x1800580cf  nop     dword ptr [rax+rax+00h]
0x1800580d4  cmp     eax, 80000005h
0x1800580d9  jnz     short loc_180058105
0x1800580db  lea     rcx, [rbp+57h+Buffer]
0x1800580df  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1800580e4  nop
0x1800580e5  lea     rcx, [rbp+57h+EaList]
0x1800580e9  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1800580ee  nop
0x1800580ef  mov     rcx, rbx; hObject
0x1800580f2  call    cs:__imp_CloseHandle
0x1800580f9  nop     dword ptr [rax+rax+00h]
0x1800580fe  mov     al, 1
0x180058100  jmp     loc_180057FDC
0x180058105  cmp     qword ptr [rdi+18h], 7
0x18005810a  jbe     short loc_18005810F
0x18005810c  mov     rdi, [rdi]
0x18005810f  mov     rcx, [rbp+5Fh]; this
0x180058113  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rdi; char *
0x180058118  lea     rdx, aLs; "%ls"
0x18005811f  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rdx; int
0x180058124  mov     r9d, eax; char *
0x180058127  lea     r8, aOnecoreVmCompu_17; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18005812e  mov     edx, 167h; void *
0x180058133  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180058138  nop
0x180058139  lea     rcx, [rbp+57h+Buffer]
0x18005813d  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180058142  nop
0x180058143  lea     rcx, [rbp+57h+EaList]
0x180058147  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18005814c  nop
0x18005814d  jmp     loc_180057FCB
0x180058152  mov     rcx, rdi
0x180058155  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18005815a  mov     rcx, [rbp+5Fh]; this
0x18005815e  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax; char *
0x180058163  lea     rdx, aLs; "%ls"
0x18005816a  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rdx; unsigned int
0x18005816f  lea     r8, aOnecoreVmCompu_17; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180058176  mov     edx, 14Eh; void *
0x18005817b  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180058181  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```

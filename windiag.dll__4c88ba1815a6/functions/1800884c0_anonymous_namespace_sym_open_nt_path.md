# _anonymous_namespace_::sym_open_nt_path

- ea: `0x1800884c0`
- end: `0x180088761`
- name: `_anonymous_namespace_::sym_open_nt_path`
- size: `673`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18008700c`

## callees

- `0x180004510`
- `0x180041400`
- `0x180041564`
- `0x1800416a0`
- `0x180041dd0`
- `0x1800884c0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088661`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800886c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088661`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800886c8`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800885a2`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800885d8`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800885a2`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800885d8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800886b0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800886b0`
- `ntdll!NtOpenFile` at `0x180088587`
- `ntdll!NtOpenFile` at `0x180088587`
- `ntdll!RtlInitUnicodeString` at `0x18008852b`
- `ntdll!RtlInitUnicodeString` at `0x18008852b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_OWORD *__fastcall anonymous_namespace_::sym_open_nt_path(_OWORD *a1, const CHAR *a2)
{
  const WCHAR *v3; // rdx
  DWORD FinalPathNameByHandleW; // eax
  DWORD v5; // ebx
  WCHAR *v6; // rdx
  DWORD v7; // eax
  __int128 v8; // xmm1
  __m128i si128; // xmm3
  void *v10; // rcx
  char **v11; // rcx
  void *v12; // rcx
  void *FileW; // rbx
  const WCHAR *v14; // rcx
  void *v15; // rcx
  __m128i v16; // xmm1
  __m128i v17; // xmm3
  void *FileHandle; // [rsp+40h] [rbp-C0h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-70h] BYREF
  PCWSTR SourceString[2]; // [rsp+A0h] [rbp-60h] BYREF
  __m128i v24; // [rsp+B0h] [rbp-50h]
  LPWSTR lpszFilePath[2]; // [rsp+C0h] [rbp-40h] BYREF
  DWORD cchFilePath[4]; // [rsp+D0h] [rbp-30h]
  __int128 v27; // [rsp+E0h] [rbp-20h] BYREF
  __m128i v28; // [rsp+F0h] [rbp-10h]
  __int64 v29; // [rsp+100h] [rbp+0h]

  FileHandle = a1;
  windiag::char_to_wstring((__int64)SourceString, a2);
  if ( (unsigned __int64)(v24.m128i_i64[0] - 1) > 0xFFF )
  {
    *((_BYTE *)a1 + 40) = 0;
    goto LABEL_25;
  }
  DestinationString = 0;
  v3 = (const WCHAR *)SourceString;
  if ( v24.m128i_i64[1] > 7uLL )
    v3 = SourceString[0];
  RtlInitUnicodeString(&DestinationString, v3);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  FileHandle = (void *)-1LL;
  if ( NtOpenFile(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 7u, 0) >= 0 )
  {
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileHandle, 0, 0, 0);
    v5 = FinalPathNameByHandleW;
    if ( FinalPathNameByHandleW )
    {
      std::wstring::wstring(lpszFilePath, FinalPathNameByHandleW);
      v6 = (WCHAR *)lpszFilePath;
      if ( *(_QWORD *)&cchFilePath[2] > 7u )
        v6 = lpszFilePath[0];
      v7 = GetFinalPathNameByHandleW(FileHandle, v6, cchFilePath[0], 0);
      if ( v7 && v7 <= v5 )
      {
        std::wstring::resize(lpszFilePath);
        v27 = *(_OWORD *)lpszFilePath;
        v8 = *(_OWORD *)cchFilePath;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        *(__m128i *)cchFilePath = si128;
        LOWORD(lpszFilePath[0]) = 0;
        v10 = FileHandle;
        FileHandle = (void *)-1LL;
        *a1 = v27;
        a1[1] = v8;
        v28 = si128;
        LOWORD(v27) = 0;
        *((_QWORD *)a1 + 4) = v10;
        *((_BYTE *)a1 + 40) = 1;
        v29 = -1;
        std::wstring::~wstring((char **)&v27);
        v11 = (char **)lpszFilePath;
        goto LABEL_11;
      }
      std::wstring::~wstring((char **)lpszFilePath);
    }
    FileW = FileHandle;
LABEL_21:
    *((_BYTE *)a1 + 40) = 0;
    if ( FileW == (void *)-1LL )
      goto LABEL_13;
    v12 = FileW;
    goto LABEL_12;
  }
  v14 = (const WCHAR *)SourceString;
  if ( v24.m128i_i64[1] > 7uLL )
    v14 = SourceString[0];
  FileW = CreateFileW(v14, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  v15 = FileHandle;
  if ( FileHandle != (void *)-1LL )
  {
    FileHandle = (void *)-1LL;
    CloseHandle(v15);
  }
  if ( FileW == (void *)-1LL )
    goto LABEL_21;
  v27 = *(_OWORD *)SourceString;
  v16 = v24;
  v17 = _mm_load_si128((const __m128i *)&_xmm);
  v24 = v17;
  LOWORD(SourceString[0]) = 0;
  FileHandle = (void *)-1LL;
  *a1 = v27;
  a1[1] = v16;
  v28 = v17;
  LOWORD(v27) = 0;
  *((_QWORD *)a1 + 4) = FileW;
  *((_BYTE *)a1 + 40) = 1;
  v29 = -1;
  v11 = (char **)&v27;
LABEL_11:
  std::wstring::~wstring(v11);
  v12 = FileHandle;
  if ( FileHandle != (void *)-1LL )
  {
LABEL_12:
    FileHandle = (void *)-1LL;
    CloseHandle(v12);
  }
LABEL_13:
  FileHandle = (void *)-1LL;
LABEL_25:
  std::wstring::~wstring((char **)SourceString);
  return a1;
}

```

## disassembly

```asm
0x1800884c0  mov     [rsp-8+arg_10], rbx
0x1800884c5  mov     [rsp-8+arg_18], rsi
0x1800884ca  push    rbp
0x1800884cb  push    rdi
0x1800884cc  push    r14
0x1800884ce  lea     rbp, [rsp-10h]
0x1800884d3  sub     rsp, 110h
0x1800884da  mov     rax, cs:__security_cookie
0x1800884e1  xor     rax, rsp
0x1800884e4  mov     [rbp+20h+var_18], rax
0x1800884e8  mov     rdi, rcx
0x1800884eb  mov     [rsp+120h+FileHandle], rcx
0x1800884f0  xor     r14d, r14d
0x1800884f3  lea     rcx, [rbp+20h+SourceString]
0x1800884f7  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x1800884fc  nop
0x1800884fd  mov     rax, qword ptr [rbp+20h+var_70]
0x180088501  dec     rax
0x180088504  cmp     rax, 0FFFh
0x18008850a  ja      loc_18008872D
0x180088510  xorps   xmm0, xmm0
0x180088513  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x180088518  lea     rdx, [rbp+20h+SourceString]
0x18008851c  cmp     qword ptr [rbp+20h+var_70+8], 7
0x180088521  cmova   rdx, [rbp+20h+SourceString]; SourceString
0x180088526  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x18008852b  call    cs:__imp_RtlInitUnicodeString
0x180088531  mov     qword ptr [rsp+120h+ObjectAttributes.Length], 30h ; '0'
0x18008853a  mov     qword ptr [rsp+120h+ObjectAttributes.Attributes], 40h ; '@'
0x180088543  mov     [rsp+120h+ObjectAttributes.RootDirectory], r14
0x180088548  lea     rax, [rsp+120h+DestinationString]
0x18008854d  mov     [rsp+120h+ObjectAttributes.ObjectName], rax
0x180088552  xorps   xmm0, xmm0
0x180088555  movdqu  xmmword ptr [rbp+20h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008855a  movups  xmmword ptr [rbp+20h+IoStatusBlock], xmm0
0x18008855e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180088562  mov     [rsp+120h+FileHandle], rsi
0x180088567  mov     [rsp+120h+OpenOptions], r14d; OpenOptions
0x18008856c  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x180088574  lea     r9, [rbp+20h+IoStatusBlock]; IoStatusBlock
0x180088578  lea     r8, [rsp+120h+ObjectAttributes]; ObjectAttributes
0x18008857d  mov     edx, 80100000h; DesiredAccess
0x180088582  lea     rcx, [rsp+120h+FileHandle]; FileHandle
0x180088587  call    cs:__imp_NtOpenFile
0x18008858d  test    eax, eax
0x18008858f  js      loc_180088681
0x180088595  xor     r9d, r9d; dwFlags
0x180088598  xor     r8d, r8d; cchFilePath
0x18008859b  xor     edx, edx; lpszFilePath
0x18008859d  mov     rcx, [rsp+120h+FileHandle]; hFile
0x1800885a2  call    cs:__imp_GetFinalPathNameByHandleW
0x1800885a8  mov     ebx, eax
0x1800885aa  test    eax, eax
0x1800885ac  jz      loc_18008867A
0x1800885b2  mov     edx, ebx
0x1800885b4  lea     rcx, [rbp+20h+lpszFilePath]
0x1800885b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x1800885bd  nop
0x1800885be  lea     rdx, [rbp+20h+lpszFilePath]
0x1800885c2  cmp     qword ptr [rbp+20h+cchFilePath+8], 7
0x1800885c7  cmova   rdx, [rbp+20h+lpszFilePath]; lpszFilePath
0x1800885cc  xor     r9d, r9d; dwFlags
0x1800885cf  mov     r8d, [rbp+20h+cchFilePath]; cchFilePath
0x1800885d3  mov     rcx, [rsp+120h+FileHandle]; hFile
0x1800885d8  call    cs:__imp_GetFinalPathNameByHandleW
0x1800885de  test    eax, eax
0x1800885e0  jz      loc_180088671
0x1800885e6  cmp     eax, ebx
0x1800885e8  ja      loc_180088671
0x1800885ee  mov     edx, eax
0x1800885f0  lea     rcx, [rbp+20h+lpszFilePath]; Src
0x1800885f4  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800885f9  movups  xmm2, xmmword ptr [rbp+20h+lpszFilePath]
0x1800885fd  movups  [rbp+20h+var_40], xmm2
0x180088601  movups  xmm1, xmmword ptr [rbp+20h+cchFilePath]
0x180088605  movdqa  xmm3, cs:__xmm@00000000000000070000000000000000
0x18008860d  movdqu  xmmword ptr [rbp+20h+cchFilePath], xmm3
0x180088612  mov     word ptr [rbp+20h+lpszFilePath], r14w
0x180088617  mov     rcx, [rsp+120h+FileHandle]
0x18008861c  mov     [rsp+120h+FileHandle], rsi
0x180088621  movups  xmmword ptr [rdi], xmm2
0x180088624  movups  xmmword ptr [rdi+10h], xmm1
0x180088628  movdqu  [rbp+20h+var_30], xmm3
0x18008862d  mov     word ptr [rbp+20h+var_40], r14w
0x180088632  mov     [rdi+20h], rcx
0x180088636  mov     byte ptr [rdi+28h], 1
0x18008863a  mov     [rbp+20h+var_20], rsi
0x18008863e  lea     rcx, [rbp+20h+var_40]
0x180088642  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180088647  nop
0x180088648  lea     rcx, [rbp+20h+lpszFilePath]
0x18008864c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180088651  nop
0x180088652  mov     rcx, [rsp+120h+FileHandle]; hObject
0x180088657  cmp     rcx, rsi
0x18008865a  jz      short loc_180088667
0x18008865c  mov     [rsp+120h+FileHandle], rsi
0x180088661  call    cs:__imp_CloseHandle
0x180088667  mov     [rsp+120h+FileHandle], rsi
0x18008866c  jmp     loc_180088731
0x180088671  lea     rcx, [rbp+20h+lpszFilePath]
0x180088675  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008867a  mov     rbx, [rsp+120h+FileHandle]
0x18008867f  jmp     short loc_1800886D3
0x180088681  lea     rcx, [rbp+20h+SourceString]
0x180088685  cmp     qword ptr [rbp+20h+var_70+8], 7
0x18008868a  cmova   rcx, [rbp+20h+SourceString]; lpFileName
0x18008868f  mov     [rsp+120h+hTemplateFile], r14; hTemplateFile
0x180088694  mov     [rsp+120h+OpenOptions], 80h; dwFlagsAndAttributes
0x18008869c  mov     [rsp+120h+ShareAccess], 3; dwCreationDisposition
0x1800886a4  xor     r9d, r9d; lpSecurityAttributes
0x1800886a7  mov     edx, 80000000h; dwDesiredAccess
0x1800886ac  lea     r8d, [r9+7]; dwShareMode
0x1800886b0  call    cs:__imp_CreateFileW
0x1800886b6  mov     rbx, rax
0x1800886b9  mov     rcx, [rsp+120h+FileHandle]; hObject
0x1800886be  cmp     rcx, rsi
0x1800886c1  jz      short loc_1800886CE
0x1800886c3  mov     [rsp+120h+FileHandle], rsi
0x1800886c8  call    cs:__imp_CloseHandle
0x1800886ce  cmp     rbx, rsi
0x1800886d1  jnz     short loc_1800886E4
0x1800886d3  mov     [rdi+28h], r14b
0x1800886d7  cmp     rbx, rsi
0x1800886da  jz      short loc_180088667
0x1800886dc  mov     rcx, rbx
0x1800886df  jmp     loc_18008865C
0x1800886e4  movups  xmm2, xmmword ptr [rbp+20h+SourceString]
0x1800886e8  movups  [rbp+20h+var_40], xmm2
0x1800886ec  movups  xmm1, [rbp+20h+var_70]
0x1800886f0  movdqa  xmm3, cs:__xmm@00000000000000070000000000000000
0x1800886f8  movdqu  [rbp+20h+var_70], xmm3
0x1800886fd  mov     word ptr [rbp+20h+SourceString], r14w
0x180088702  mov     [rsp+120h+FileHandle], rsi
0x180088707  movups  xmmword ptr [rdi], xmm2
0x18008870a  movups  xmmword ptr [rdi+10h], xmm1
0x18008870e  movdqu  [rbp+20h+var_30], xmm3
0x180088713  mov     word ptr [rbp+20h+var_40], r14w
0x180088718  mov     [rdi+20h], rbx
0x18008871c  mov     byte ptr [rdi+28h], 1
0x180088720  mov     [rbp+20h+var_20], rsi
0x180088724  lea     rcx, [rbp+20h+var_40]
0x180088728  jmp     loc_18008864C
0x18008872d  mov     [rdi+28h], r14b
0x180088731  lea     rcx, [rbp+20h+SourceString]
0x180088735  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008873a  mov     rax, rdi
0x18008873d  mov     rcx, [rbp+20h+var_18]
0x180088741  xor     rcx, rsp; StackCookie
0x180088744  call    __security_check_cookie
0x180088749  lea     r11, [rsp+120h+var_10]
0x180088751  mov     rbx, [r11+30h]
0x180088755  mov     rsi, [r11+38h]
0x180088759  mov     rsp, r11
0x18008875c  pop     r14
0x18008875e  pop     rdi
0x18008875f  pop     rbp
0x180088760  retn
```

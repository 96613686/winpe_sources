# _anonymous_namespace_::cab_file::add_data_file

- ea: `0x18003f904`
- end: `0x18003fc42`
- name: `_anonymous_namespace_::cab_file::add_data_file`
- size: `830`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18003fe00`

## callees

- `0x180004510`
- `0x180005520`
- `0x18003a52c`
- `0x18003af08`
- `0x18003b0bc`
- `0x18003d720`
- `0x18003f0b4`
- `0x18003f36c`
- `0x18003f6b8`
- `0x18003f904`
- `0x18003fc48`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fa83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003faba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fa83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003faba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fad1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fad1`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18003fa6f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18003fa6f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003fab0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003fab0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall anonymous_namespace_::cab_file::add_data_file(_QWORD *a1, __int64 a2, const void *a3, DWORD a4)
{
  __int64 v8; // r8
  unsigned __int64 v9; // r9
  LPCSTR v10; // r8
  unsigned __int64 v11; // rcx
  LPCSTR *v12; // rax
  const CHAR *v13; // rdx
  __int64 v14; // r10
  _QWORD *v15; // rdx
  LPCSTR *v16; // rax
  const CHAR *v17; // rcx
  HANDLE FileA; // rbx
  DWORD LastError; // eax
  DWORD v20; // eax
  LPCSTR *v21; // rdx
  __int64 v22; // rdx
  _QWORD *v23; // rcx
  _QWORD *v24; // rdx
  _QWORD *v25; // rdx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h]
  LPCSTR lpFileName[2]; // [rsp+50h] [rbp-B0h] BYREF
  __m128i si128; // [rsp+60h] [rbp-A0h]
  _QWORD v31[7]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v32; // [rsp+A8h] [rbp-58h]
  _BYTE v33[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+D0h] [rbp-30h] BYREF

  *(_OWORD *)lpFileName = 0;
  si128 = 0;
  v8 = -1;
  do
    ++v8;
  while ( *(_BYTE *)(a2 + v8) );
  std::string::_Construct<1,char const *>(lpFileName, a2, v8);
  v9 = si128.m128i_u64[1];
  v10 = lpFileName[0];
  v11 = si128.m128i_i64[0];
  if ( si128.m128i_i64[1] <= 0xFuLL )
  {
    v13 = (char *)lpFileName + si128.m128i_i64[0];
    v12 = lpFileName;
  }
  else
  {
    v12 = (LPCSTR *)lpFileName[0];
    v13 = &lpFileName[0][si128.m128i_i64[0]];
  }
  if ( v12 != (LPCSTR *)v13 )
  {
    do
    {
      if ( *(_BYTE *)v12 == 92 )
        *(_BYTE *)v12 = 95;
      v12 = (LPCSTR *)((char *)v12 + 1);
    }
    while ( v12 != (LPCSTR *)v13 );
    v9 = si128.m128i_u64[1];
    v11 = si128.m128i_i64[0];
    v10 = lpFileName[0];
  }
  v14 = a1[2];
  if ( 0x7FFFFFFFFFFFFFFFLL - v14 < v11 )
    std::_Xlen_string();
  if ( a1[3] <= 0xFu )
    v15 = a1;
  else
    v15 = (_QWORD *)*a1;
  v16 = lpFileName;
  if ( v9 > 0xF )
    v16 = (LPCSTR *)v10;
  std::string::string(v33, v15, v10, v15, v14, v16, v11);
  std::string::operator=(lpFileName, v33);
  std::string::~string(v33);
  v31[0] = off_18009F290;
  v31[1] = lpFileName;
  v32 = v31;
  v17 = (const CHAR *)lpFileName;
  if ( si128.m128i_i64[1] > 0xFuLL )
    v17 = lpFileName[0];
  FileA = CreateFileA(v17, 0x40000000u, 3u, 0, 2u, 0x80u, 0);
  v28 = (__int64)FileA;
  if ( FileA == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        LastError,
        0,
        "[%s:%d] failed; ",
        "add_data_file",
        100);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  NumberOfBytesWritten = 0;
  if ( !WriteFile(FileA, a3, a4, &NumberOfBytesWritten, 0) )
  {
    v20 = GetLastError();
    if ( v20 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v20,
        0,
        "[%s:%d] failed; ",
        "add_data_file",
        103);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  if ( FileA != (HANDLE)-1LL )
    CloseHandle(FileA);
  v28 = -1;
  v21 = lpFileName;
  if ( si128.m128i_i64[1] > 0xFuLL )
    v21 = (LPCSTR *)lpFileName[0];
  anonymous_namespace_::cab_file::add_file(a1, v21, a2);
  v22 = a1[11];
  if ( v22 == a1[12] )
  {
    std::vector<std::string>::_Emplace_reallocate<std::string>(a1 + 10, v22, lpFileName);
  }
  else
  {
    *(_OWORD *)v22 = 0;
    *(_QWORD *)(v22 + 16) = 0;
    *(_QWORD *)(v22 + 24) = 0;
    *(_OWORD *)v22 = *(_OWORD *)lpFileName;
    *(__m128i *)(v22 + 16) = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(lpFileName[0]) = 0;
    a1[11] += 32LL;
  }
  v23 = v32;
  if ( v32 )
  {
    v24 = v31;
    LOBYTE(v24) = v32 != v31;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v32 + 32LL))(v32, v24);
    v23 = 0;
    v32 = 0;
  }
  if ( v23 )
  {
    v25 = v31;
    LOBYTE(v25) = v23 != v31;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v23 + 32LL))(v23, v25);
    v32 = 0;
  }
  return std::string::~string(lpFileName);
}

```

## disassembly

```asm
0x18003f904  push    rbp
0x18003f906  push    rbx
0x18003f907  push    rsi
0x18003f908  push    rdi
0x18003f909  push    r14
0x18003f90b  push    r15
0x18003f90d  lea     rbp, [rsp-418h]
0x18003f915  sub     rsp, 518h
0x18003f91c  mov     rax, cs:__security_cookie
0x18003f923  xor     rax, rsp
0x18003f926  mov     [rbp+440h+var_40], rax
0x18003f92d  mov     r15d, r9d
0x18003f930  mov     r14, r8
0x18003f933  mov     rsi, rdx
0x18003f936  mov     rdi, rcx
0x18003f939  xorps   xmm0, xmm0
0x18003f93c  movups  xmmword ptr [rsp+540h+lpFileName], xmm0
0x18003f941  xorps   xmm1, xmm1
0x18003f944  movdqu  [rsp+540h+var_4E0], xmm1
0x18003f94a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003f94e  inc     r8
0x18003f951  cmp     byte ptr [rdx+r8], 0
0x18003f956  jnz     short loc_18003F94E
0x18003f958  lea     rcx, [rsp+540h+lpFileName]
0x18003f95d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18003f962  nop
0x18003f963  mov     r9, qword ptr [rsp+540h+var_4E0+8]
0x18003f968  mov     r8, [rsp+540h+lpFileName]
0x18003f96d  mov     rcx, qword ptr [rsp+540h+var_4E0]
0x18003f972  cmp     r9, 0Fh
0x18003f976  jbe     short loc_18003F981
0x18003f978  mov     rax, r8
0x18003f97b  lea     rdx, [rcx+r8]
0x18003f97f  jmp     short loc_18003F98E
0x18003f981  lea     rdx, [rsp+540h+lpFileName]
0x18003f986  add     rdx, rcx
0x18003f989  lea     rax, [rsp+540h+lpFileName]
0x18003f98e  cmp     rax, rdx
0x18003f991  jz      short loc_18003F9B2
0x18003f993  cmp     byte ptr [rax], 5Ch ; '\'
0x18003f996  jnz     short loc_18003F99B
0x18003f998  mov     byte ptr [rax], 5Fh ; '_'
0x18003f99b  inc     rax
0x18003f99e  cmp     rax, rdx
0x18003f9a1  jnz     short loc_18003F993
0x18003f9a3  mov     r9, qword ptr [rsp+540h+var_4E0+8]
0x18003f9a8  mov     rcx, qword ptr [rsp+540h+var_4E0]
0x18003f9ad  mov     r8, [rsp+540h+lpFileName]
0x18003f9b2  mov     r10, [rdi+10h]
0x18003f9b6  mov     rax, 7FFFFFFFFFFFFFFFh
0x18003f9c0  sub     rax, r10
0x18003f9c3  cmp     rax, rcx
0x18003f9c6  jb      loc_18003FC02
0x18003f9cc  cmp     qword ptr [rdi+18h], 0Fh
0x18003f9d1  jbe     short loc_18003F9D8
0x18003f9d3  mov     rdx, [rdi]
0x18003f9d6  jmp     short loc_18003F9DB
0x18003f9d8  mov     rdx, rdi
0x18003f9db  lea     rax, [rsp+540h+lpFileName]
0x18003f9e0  cmp     r9, 0Fh
0x18003f9e4  cmova   rax, r8
0x18003f9e8  mov     [rsp+540h+hTemplateFile], rcx
0x18003f9ed  mov     qword ptr [rsp+540h+dwFlagsAndAttributes], rax
0x18003f9f2  mov     qword ptr [rsp+540h+dwCreationDisposition], r10
0x18003f9f7  mov     r9, rdx
0x18003f9fa  lea     rcx, [rbp+440h+var_490]
0x18003f9fe  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z; std::string::string(std::_String_constructor_concat_tag,std::string const &,char const * const,unsigned __int64,char const * const,unsigned __int64)
0x18003fa03  lea     rdx, [rbp+440h+var_490]
0x18003fa07  lea     rcx, [rsp+540h+lpFileName]
0x18003fa0c  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18003fa11  lea     rcx, [rbp+440h+var_490]
0x18003fa15  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003fa1a  lea     rax, off_18009F290
0x18003fa21  mov     [rsp+540h+var_4D0], rax
0x18003fa26  lea     rax, [rsp+540h+lpFileName]
0x18003fa2b  mov     [rsp+540h+var_4C8], rax
0x18003fa30  lea     rax, [rsp+540h+var_4D0]
0x18003fa35  mov     [rbp+440h+var_498], rax
0x18003fa39  lea     rcx, [rsp+540h+lpFileName]
0x18003fa3e  cmp     qword ptr [rsp+540h+var_4E0+8], 0Fh
0x18003fa44  cmova   rcx, [rsp+540h+lpFileName]; lpFileName
0x18003fa4a  mov     [rsp+540h+hTemplateFile], 0; hTemplateFile
0x18003fa53  mov     [rsp+540h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003fa5b  mov     [rsp+540h+dwCreationDisposition], 2; dwCreationDisposition
0x18003fa63  xor     r9d, r9d; lpSecurityAttributes
0x18003fa66  mov     edx, 40000000h; dwDesiredAccess
0x18003fa6b  lea     r8d, [r9+3]; dwShareMode
0x18003fa6f  call    cs:__imp_CreateFileA
0x18003fa75  mov     rbx, rax
0x18003fa78  mov     [rsp+540h+var_4F8], rax
0x18003fa7d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003fa81  jnz     short loc_18003FA91
0x18003fa83  call    cs:__imp_GetLastError
0x18003fa89  test    eax, eax
0x18003fa8b  jnz     loc_18003FC08
0x18003fa91  mov     [rsp+540h+NumberOfBytesWritten], 0
0x18003fa99  mov     qword ptr [rsp+540h+dwCreationDisposition], 0; lpOverlapped
0x18003faa2  lea     r9, [rsp+540h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003faa7  mov     r8d, r15d; nNumberOfBytesToWrite
0x18003faaa  mov     rdx, r14; lpBuffer
0x18003faad  mov     rcx, rbx; hFile
0x18003fab0  call    cs:__imp_WriteFile
0x18003fab6  test    eax, eax
0x18003fab8  jnz     short loc_18003FAC8
0x18003faba  call    cs:__imp_GetLastError
0x18003fac0  test    eax, eax
0x18003fac2  jnz     loc_18003FBC8
0x18003fac8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003facc  jz      short loc_18003FAD7
0x18003face  mov     rcx, rbx; hObject
0x18003fad1  call    cs:__imp_CloseHandle
0x18003fad7  mov     [rsp+540h+var_4F8], 0FFFFFFFFFFFFFFFFh
0x18003fae0  lea     rdx, [rsp+540h+lpFileName]
0x18003fae5  cmp     qword ptr [rsp+540h+var_4E0+8], 0Fh
0x18003faeb  cmova   rdx, [rsp+540h+lpFileName]
0x18003faf1  mov     r8, rsi
0x18003faf4  mov     rcx, rdi
0x18003faf7  call    _anonymous_namespace___cab_file__add_file
0x18003fafc  lea     rcx, [rdi+50h]
0x18003fb00  mov     rdx, [rcx+8]
0x18003fb04  cmp     rdx, [rcx+10h]
0x18003fb08  jz      short loc_18003FB4B
0x18003fb0a  xorps   xmm0, xmm0
0x18003fb0d  movups  xmmword ptr [rdx], xmm0
0x18003fb10  mov     qword ptr [rdx+10h], 0
0x18003fb18  mov     qword ptr [rdx+18h], 0
0x18003fb20  movups  xmm0, xmmword ptr [rsp+540h+lpFileName]
0x18003fb25  movups  xmmword ptr [rdx], xmm0
0x18003fb28  movups  xmm1, [rsp+540h+var_4E0]
0x18003fb2d  movups  xmmword ptr [rdx+10h], xmm1
0x18003fb31  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18003fb39  movdqu  [rsp+540h+var_4E0], xmm0
0x18003fb3f  mov     byte ptr [rsp+540h+lpFileName], 0
0x18003fb44  add     qword ptr [rcx+8], 20h ; ' '
0x18003fb49  jmp     short loc_18003FB55
0x18003fb4b  lea     r8, [rsp+540h+lpFileName]
0x18003fb50  call    ??$_Emplace_reallocate@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::string>::_Emplace_reallocate<std::string>(std::string * const,std::string &&)
0x18003fb55  mov     rcx, [rbp+440h+var_498]
0x18003fb59  test    rcx, rcx
0x18003fb5c  jz      short loc_18003FB7B
0x18003fb5e  mov     rax, [rcx]
0x18003fb61  lea     rdx, [rsp+540h+var_4D0]
0x18003fb66  cmp     rcx, rdx
0x18003fb69  setnz   dl
0x18003fb6c  mov     rax, [rax+20h]
0x18003fb70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb75  xor     ecx, ecx
0x18003fb77  mov     [rbp+440h+var_498], rcx
0x18003fb7b  test    rcx, rcx
0x18003fb7e  jz      short loc_18003FB9F
0x18003fb80  mov     rax, [rcx]
0x18003fb83  lea     rdx, [rsp+540h+var_4D0]
0x18003fb88  cmp     rcx, rdx
0x18003fb8b  setnz   dl
0x18003fb8e  mov     rax, [rax+20h]
0x18003fb92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb97  mov     [rbp+440h+var_498], 0
0x18003fb9f  lea     rcx, [rsp+540h+lpFileName]
0x18003fba4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003fba9  mov     rcx, [rbp+440h+var_40]
0x18003fbb0  xor     rcx, rsp; StackCookie
0x18003fbb3  call    __security_check_cookie
0x18003fbb8  add     rsp, 518h
0x18003fbbf  pop     r15
0x18003fbc1  pop     r14
0x18003fbc3  pop     rdi
0x18003fbc4  pop     rsi
0x18003fbc5  pop     rbx
0x18003fbc6  pop     rbp
0x18003fbc7  retn
0x18003fbc8  mov     edx, eax; __int64
0x18003fbca  mov     [rsp+540h+dwFlagsAndAttributes], 67h ; 'g'
0x18003fbd2  lea     rax, aAddDataFile; "add_data_file"
0x18003fbd9  mov     qword ptr [rsp+540h+dwCreationDisposition], rax
0x18003fbde  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18003fbe5  xor     r8d, r8d; void *
0x18003fbe8  lea     rcx, [rbp+440h+pExceptionObject]; this
0x18003fbec  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18003fbf1  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18003fbf8  lea     rcx, [rbp+440h+pExceptionObject]; pExceptionObject
0x18003fbfc  call    _CxxThrowException_0
0x18003fc02  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18003fc08  mov     edx, eax; __int64
0x18003fc0a  mov     [rsp+540h+dwFlagsAndAttributes], 64h ; 'd'
0x18003fc12  lea     rax, aAddDataFile; "add_data_file"
0x18003fc19  mov     qword ptr [rsp+540h+dwCreationDisposition], rax
0x18003fc1e  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18003fc25  xor     r8d, r8d; void *
0x18003fc28  lea     rcx, [rbp+440h+pExceptionObject]; this
0x18003fc2c  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18003fc31  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18003fc38  lea     rcx, [rbp+440h+pExceptionObject]; pExceptionObject
0x18003fc3c  call    _CxxThrowException_0
```

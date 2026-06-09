# CSrmFileSafe::ReadFileContents(void)

- ea: `0x180078f5c`
- end: `0x180079454`
- name: `?ReadFileContents@CSrmFileSafe@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `1272`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x18000fd74`

## callees

- `0x180001350`
- `0x18000ed14`
- `0x18000ee10`
- `0x18001dbb0`
- `0x1800205f8`
- `0x18006fe68`
- `0x18006febc`
- `0x18007006c`
- `0x1800700b8`
- `0x180070380`
- `0x180071efc`
- `0x180073d04`
- `0x180074048`
- `0x180074a04`
- `0x180075034`
- `0x180078f5c`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1800790f0`
- `KERNEL32!ReadFile` at `0x1800790f0`
- `KERNEL32!GetFileSize` at `0x180079020`
- `KERNEL32!GetFileSize` at `0x180079020`
- `KERNEL32!GetLastError` at `0x1800790fa`
- `KERNEL32!GetLastError` at `0x1800790fa`

## string_xrefs

- `0x180079353`: `Volume not ready for SRM store file %s`
- `0x180078fa9`: `CSrmFileSafe::ReadFileContents`
- `0x1800793ee`: `File not yet opened`
- `0x1800793b5`: `ReadFile('%s')`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall CSrmFileSafe::ReadFileContents(__int64 a1, _QWORD *a2)
{
  DWORD FileSize; // ebx
  void *v5; // r14
  DWORD LastError; // eax
  signed int v7; // ebx
  __int64 v8; // rcx
  void **v9; // rbx
  unsigned __int16 *v11; // rax
  struct CSrmDebugInfo *v12; // r9
  CSrmDebugInfo *v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  _WORD v21[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+44h] [rbp-BCh]
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v24; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v25; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v26; // [rsp+68h] [rbp-98h]
  int v27; // [rsp+70h] [rbp-90h]
  int v28; // [rsp+74h] [rbp-8Ch]
  int v29; // [rsp+78h] [rbp-88h]
  _BYTE v30[96]; // [rsp+80h] [rbp-80h] BYREF
  int v31; // [rsp+E0h] [rbp-20h]
  LPVOID lpBuffer[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v33; // [rsp+F8h] [rbp-8h]
  _QWORD *v34; // [rsp+108h] [rbp+8h]
  _QWORD v35[3]; // [rsp+110h] [rbp+10h] BYREF
  int v36; // [rsp+128h] [rbp+28h]
  int v37; // [rsp+12Ch] [rbp+2Ch]
  int v38; // [rsp+130h] [rbp+30h]
  _BYTE v39[96]; // [rsp+138h] [rbp+38h] BYREF
  int v40; // [rsp+198h] [rbp+98h]
  void *Block[3]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int64 v42; // [rsp+1B8h] [rbp+B8h]
  _QWORD v43[22]; // [rsp+1D0h] [rbp+D0h] BYREF

  v34 = a2;
  v22 = 0;
  v35[0] = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
  v35[1] = L"CSrmFileSafe::ReadFileContents";
  v35[2] = L"FILESF_C";
  v36 = 456;
  v37 = 17;
  v38 = 255;
  v40 = 0x1000000;
  memset_0(v39, 0, sizeof(v39));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v43, (const struct CSrmDebugInfo *)v35, 0);
  if ( !*(_BYTE *)(a1 + 201) && !*(_BYTE *)(a1 + 200) )
  {
    v18 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)&v24,
            (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
            (__int64)L"FILESF_C",
            (__int64)L"CSrmFileSafe::ReadFileContents",
            460,
            17);
    CSrmFunctionTracer::Throw(v43, v18, 2147549183LL, L"File not yet opened");
  }
  FileSize = GetFileSize(*(HANDLE *)(a1 + 216), 0);
  if ( FileSize == -1 )
  {
    v19 = std::wstring::c_str(a1 + 80);
    v20 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)&v24,
            (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
            (__int64)L"FILESF_C",
            (__int64)L"CSrmFileSafe::ReadFileContents",
            466,
            17);
    CSrmFunctionTracer::TranslateWin32Error(v43, v20, L"GetFileSize('%s')", v19);
  }
  v24 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
  v25 = L"CSrmFileSafe::ReadFileContents";
  v26 = L"FILESF_C";
  v27 = 468;
  v28 = 17;
  v29 = 255;
  v31 = 0x1000000;
  memset_0(v30, 0, sizeof(v30));
  CSrmFunctionTracer::Trace(v43, &v24, L"- File size: %d", FileSize);
  a2[3] = 7;
  a2[2] = 0;
  *(_WORD *)a2 = 0;
  v22 = 1;
  if ( FileSize )
  {
    v21[0] = 0;
    *(_OWORD *)lpBuffer = 0;
    v33 = 0;
    std::vector<unsigned short>::_Construct_n(lpBuffer, (unsigned __int64)(FileSize + 1) >> 1, v21);
    NumberOfBytesRead = 0;
    v5 = lpBuffer[0];
    if ( !ReadFile(*(HANDLE *)(a1 + 216), lpBuffer[0], FileSize, &NumberOfBytesRead, 0) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError <= 0x37 && (v8 = 0x80000000280020LL, _bittest64(&v8, LastError)) || LastError == 1167 )
      {
        CSrmDebugInfo::CSrmDebugInfo(
          (__int64)v35,
          (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
          (__int64)L"FILESF_C",
          (__int64)L"CSrmFileSafe::ReadFileContents",
          500,
          17);
        v11 = (unsigned __int16 *)std::wstring::c_str(a1 + 80);
        v13 = CSrmDebugInfo::operator<<(v12, (CSrmDebugInfo *)&v24, v11);
        CSrmFunctionTracer::LogError((__int64)v43, 0x80042039, (__int64)v13, 2u);
        CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v35);
        v14 = std::wstring::c_str(a1 + 80);
        v15 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)&v24,
                (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
                (__int64)L"FILESF_C",
                (__int64)L"CSrmFileSafe::ReadFileContents",
                503,
                17);
        CSrmFunctionTracer::Throw(v43, v15, 2147767142LL, L"Volume not ready for SRM store file %s", v14);
      }
      v16 = std::wstring::c_str(a1 + 80);
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      v17 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)&v24,
              (__int64)L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
              (__int64)L"FILESF_C",
              (__int64)L"CSrmFileSafe::ReadFileContents",
              510,
              17);
      CSrmFunctionTracer::TranslateGenericError(v43, v17, (unsigned int)v7, L"ReadFile('%s')", v16);
    }
    v24 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
    v25 = L"CSrmFileSafe::ReadFileContents";
    v26 = L"FILESF_C";
    v27 = 513;
    v28 = 17;
    v29 = 255;
    v31 = 0x1000000;
    memset_0(v30, 0, sizeof(v30));
    CSrmFunctionTracer::Trace(v43, &v24, L"- File buffer: %d", FileSize);
    std::wstring::assign<std::_Vector_iterator<std::_Vector_val<unsigned short>>>(a2);
    v42 = 7;
    Block[2] = 0;
    LOWORD(Block[0]) = 0;
    std::wstring::assign(Block);
    v22 = 3;
    v9 = Block;
    if ( v42 >= 8 )
      v9 = (void **)Block[0];
    v24 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
    v25 = L"CSrmFileSafe::ReadFileContents";
    v26 = L"FILESF_C";
    v27 = 521;
    v28 = 17;
    v29 = 255;
    v31 = 0x1000000;
    memset_0(v30, 0, sizeof(v30));
    CSrmFunctionTracer::Trace(v43, &v24, L"- File text: '%s' ...", v9);
    if ( v42 >= 8 )
      operator delete(Block[0]);
    if ( v5 )
      operator delete(v5);
  }
  v43[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v43);
  return a2;
}

```

## disassembly

```asm
0x180078f5c  mov     [rsp-8+arg_10], rbx
0x180078f61  push    rbp
0x180078f62  push    rsi
0x180078f63  push    rdi
0x180078f64  push    r12
0x180078f66  push    r13
0x180078f68  push    r14
0x180078f6a  push    r15
0x180078f6c  lea     rbp, [rsp-190h]
0x180078f74  sub     rsp, 290h
0x180078f7b  mov     rax, cs:__security_cookie
0x180078f82  xor     rax, rsp
0x180078f85  mov     [rbp+1C0h+var_40], rax
0x180078f8c  mov     rsi, rdx
0x180078f8f  mov     rdi, rcx
0x180078f92  mov     [rbp+1C0h+var_1B8], rdx
0x180078f96  xor     r15d, r15d
0x180078f99  mov     [rsp+2C0h+var_27C], r15d
0x180078f9e  lea     r12, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x180078fa5  mov     [rbp+1C0h+var_1B0], r12
0x180078fa9  lea     r13, aCsrmfilesafeRe; "CSrmFileSafe::ReadFileContents"
0x180078fb0  mov     [rbp+1C0h+var_1A8], r13
0x180078fb4  lea     r14, aFilesfC; "FILESF_C"
0x180078fbb  mov     [rbp+1C0h+var_1A0], r14
0x180078fbf  mov     [rbp+1C0h+var_198], 1C8h
0x180078fc6  lea     ebx, [r15+11h]
0x180078fca  mov     [rbp+1C0h+var_194], ebx
0x180078fcd  mov     [rbp+1C0h+var_190], 0FFh
0x180078fd4  mov     [rbp+1C0h+var_128], 1000000h
0x180078fde  xor     edx, edx; Val
0x180078fe0  lea     r8d, [r15+60h]; Size
0x180078fe4  lea     rcx, [rbp+1C0h+var_188]; void *
0x180078fe8  call    memset_0
0x180078fed  xor     r8d, r8d
0x180078ff0  lea     rdx, [rbp+1C0h+var_1B0]
0x180078ff4  lea     rcx, [rbp+1C0h+var_F0]
0x180078ffb  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180079000  nop
0x180079001  cmp     [rdi+0C9h], r15b
0x180079008  jnz     short loc_180079017
0x18007900a  cmp     [rdi+0C8h], r15b
0x180079011  jz      loc_1800793CF
0x180079017  xor     edx, edx; lpFileSizeHigh
0x180079019  mov     rcx, [rdi+0D8h]; hFile
0x180079020  call    cs:__imp_GetFileSize
0x180079026  mov     ebx, eax
0x180079028  cmp     eax, 0FFFFFFFFh
0x18007902b  jz      loc_18007940B
0x180079031  mov     [rsp+2C0h+var_268], r12
0x180079036  mov     [rsp+2C0h+var_260], r13
0x18007903b  mov     [rsp+2C0h+var_258], r14
0x180079040  mov     [rsp+2C0h+var_250], 1D4h
0x180079048  mov     [rsp+2C0h+var_24C], 11h
0x180079050  mov     [rsp+2C0h+var_248], 0FFh
0x180079058  mov     [rbp+1C0h+var_1E0], 1000000h
0x18007905f  xor     edx, edx; Val
0x180079061  lea     r8d, [rdx+60h]; Size
0x180079065  lea     rcx, [rbp+1C0h+var_240]; void *
0x180079069  call    memset_0
0x18007906e  mov     r9d, ebx
0x180079071  lea     r8, aFileSizeD; "- File size: %d"
0x180079078  lea     rdx, [rsp+2C0h+var_268]
0x18007907d  lea     rcx, [rbp+1C0h+var_F0]
0x180079084  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180079089  mov     qword ptr [rsi+18h], 7
0x180079091  mov     [rsi+10h], r15
0x180079095  mov     [rsi], r15w
0x180079099  mov     [rsp+2C0h+var_27C], 1
0x1800790a1  test    ebx, ebx
0x1800790a3  jz      loc_180079273
0x1800790a9  mov     [rsp+2C0h+var_280], r15w
0x1800790af  xorps   xmm0, xmm0
0x1800790b2  movdqu  xmmword ptr [rbp+1C0h+lpBuffer], xmm0
0x1800790b7  mov     [rbp+1C0h+var_1C8], r15
0x1800790bb  lea     edx, [rbx+1]
0x1800790be  shr     rdx, 1
0x1800790c1  lea     r8, [rsp+2C0h+var_280]
0x1800790c6  lea     rcx, [rbp+1C0h+lpBuffer]
0x1800790ca  call    ?_Construct_n@?$vector@GV?$allocator@G@std@@@std@@QEAAX_KPEBG@Z; std::vector<ushort>::_Construct_n(unsigned __int64,ushort const *)
0x1800790cf  nop
0x1800790d0  mov     [rsp+2C0h+NumberOfBytesRead], r15d
0x1800790d5  mov     [rsp+2C0h+lpOverlapped], r15; lpOverlapped
0x1800790da  lea     r9, [rsp+2C0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800790df  mov     r8d, ebx; nNumberOfBytesToRead
0x1800790e2  mov     r14, [rbp+1C0h+lpBuffer]
0x1800790e6  mov     rdx, r14; lpBuffer
0x1800790e9  mov     rcx, [rdi+0D8h]; hFile
0x1800790f0  call    cs:__imp_ReadFile
0x1800790f6  test    eax, eax
0x1800790f8  jnz     short loc_18007912C
0x1800790fa  call    cs:__imp_GetLastError
0x180079100  mov     ebx, eax
0x180079102  cmp     eax, 37h ; '7'
0x180079105  ja      short loc_18007911B
0x180079107  mov     rcx, 80000000280020h
0x180079111  bt      rcx, rbx
0x180079115  jb      loc_1800792BA
0x18007911b  cmp     ebx, 48Fh
0x180079121  jnz     loc_180079370
0x180079127  jmp     loc_1800792BA
0x18007912c  mov     [rsp+2C0h+var_268], r12
0x180079131  mov     [rsp+2C0h+var_260], r13
0x180079136  lea     rdi, aFilesfC; "FILESF_C"
0x18007913d  mov     [rsp+2C0h+var_258], rdi
0x180079142  mov     [rsp+2C0h+var_250], 201h
0x18007914a  mov     [rsp+2C0h+var_24C], 11h
0x180079152  mov     [rsp+2C0h+var_248], 0FFh
0x18007915a  mov     [rbp+1C0h+var_1E0], 1000000h
0x180079161  xor     edx, edx; Val
0x180079163  lea     r8d, [rdx+60h]; Size
0x180079167  lea     rcx, [rbp+1C0h+var_240]; void *
0x18007916b  call    memset_0
0x180079170  mov     r9d, ebx
0x180079173  lea     r8, aFileBufferD; "- File buffer: %d"
0x18007917a  lea     rdx, [rsp+2C0h+var_268]
0x18007917f  lea     rcx, [rbp+1C0h+var_F0]
0x180079186  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18007918b  lea     rdx, [r14+2]
0x18007918f  mov     r8, [rbp+1C0h+lpBuffer+8]
0x180079193  mov     rcx, rsi; Src
0x180079196  call    ??$assign@V?$_Vector_iterator@V?$_Vector_val@GV?$allocator@G@std@@@std@@@std@@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@V?$_Vector_iterator@V?$_Vector_val@GV?$allocator@G@std@@@std@@@1@0@Z; std::wstring::assign<std::_Vector_iterator<std::_Vector_val<ushort>>>(std::_Vector_iterator<std::_Vector_val<ushort>>,std::_Vector_iterator<std::_Vector_val<ushort>>)
0x18007919b  mov     r9d, 32h ; '2'
0x1800791a1  cmp     [rsi+10h], r9
0x1800791a5  cmovb   r9, [rsi+10h]
0x1800791aa  mov     [rbp+1C0h+var_108], 7
0x1800791b5  mov     [rbp+1C0h+var_110], r15
0x1800791bc  mov     word ptr [rbp+1C0h+Block], r15w
0x1800791c4  xor     r8d, r8d
0x1800791c7  mov     rdx, rsi
0x1800791ca  lea     rcx, [rbp+1C0h+Block]; void *
0x1800791d1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800791d6  mov     [rsp+2C0h+var_27C], 3
0x1800791de  lea     rbx, [rbp+1C0h+Block]
0x1800791e5  cmp     [rbp+1C0h+var_108], 8
0x1800791ed  cmovnb  rbx, [rbp+1C0h+Block]
0x1800791f5  mov     [rsp+2C0h+var_268], r12
0x1800791fa  mov     [rsp+2C0h+var_260], r13
0x1800791ff  mov     [rsp+2C0h+var_258], rdi
0x180079204  mov     [rsp+2C0h+var_250], 209h
0x18007920c  mov     [rsp+2C0h+var_24C], 11h
0x180079214  mov     [rsp+2C0h+var_248], 0FFh
0x18007921c  mov     [rbp+1C0h+var_1E0], 1000000h
0x180079223  xor     edx, edx; Val
0x180079225  lea     r8d, [rdx+60h]; Size
0x180079229  lea     rcx, [rbp+1C0h+var_240]; void *
0x18007922d  call    memset_0
0x180079232  mov     r9, rbx
0x180079235  lea     r8, aFileTextS; "- File text: '%s' ..."
0x18007923c  lea     rdx, [rsp+2C0h+var_268]
0x180079241  lea     rcx, [rbp+1C0h+var_F0]
0x180079248  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18007924d  nop
0x18007924e  cmp     [rbp+1C0h+var_108], 8
0x180079256  jb      short loc_180079265
0x180079258  mov     rcx, [rbp+1C0h+Block]; Block
0x18007925f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180079264  nop
0x180079265  test    r14, r14
0x180079268  jz      short loc_180079273
0x18007926a  mov     rcx, r14; Block
0x18007926d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180079272  nop
0x180079273  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007927a  mov     [rbp+1C0h+var_F0], rax
0x180079281  lea     rcx, [rbp+1C0h+var_F0]; this
0x180079288  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007928d  mov     rax, rsi
0x180079290  mov     rcx, [rbp+1C0h+var_40]
0x180079297  xor     rcx, rsp; StackCookie
0x18007929a  call    __security_check_cookie
0x18007929f  mov     rbx, [rsp+2C0h+arg_10]
0x1800792a7  add     rsp, 290h
0x1800792ae  pop     r15
0x1800792b0  pop     r14
0x1800792b2  pop     r13
0x1800792b4  pop     r12
0x1800792b6  pop     rdi
0x1800792b7  pop     rsi
0x1800792b8  pop     rbp
0x1800792b9  retn
0x1800792ba  mov     esi, 11h
0x1800792bf  mov     [rsp+2C0h+var_298], esi
0x1800792c3  mov     dword ptr [rsp+2C0h+lpOverlapped], 1F4h
0x1800792cb  mov     r9, r13
0x1800792ce  lea     r8, aFilesfC; "FILESF_C"
0x1800792d5  mov     rdx, r12
0x1800792d8  lea     rcx, [rbp+1C0h+var_1B0]
0x1800792dc  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800792e1  mov     r9, rax
0x1800792e4  lea     rcx, [rdi+50h]
0x1800792e8  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1800792ed  mov     r8, rax; unsigned __int16 *
0x1800792f0  lea     rdx, [rsp+2C0h+var_268]; this
0x1800792f5  mov     rcx, r9; struct CSrmDebugInfo *
0x1800792f8  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x1800792fd  lea     r9d, [rsi-0Fh]
0x180079301  mov     r8, rax
0x180079304  mov     edx, 80042039h
0x180079309  lea     rcx, [rbp+1C0h+var_F0]
0x180079310  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x180079315  nop
0x180079316  lea     rcx, [rbp+1C0h+var_1B0]; this
0x18007931a  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x18007931f  lea     rcx, [rdi+50h]
0x180079323  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180079328  mov     rbx, rax
0x18007932b  mov     [rsp+2C0h+var_298], esi
0x18007932f  mov     dword ptr [rsp+2C0h+lpOverlapped], 1F7h
0x180079337  mov     r9, r13
0x18007933a  lea     r8, aFilesfC; "FILESF_C"
0x180079341  mov     rdx, r12
0x180079344  lea     rcx, [rsp+2C0h+var_268]
0x180079349  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007934e  mov     [rsp+2C0h+lpOverlapped], rbx
0x180079353  lea     r9, aVolumeNotReady; "Volume not ready for SRM store file %s"
0x18007935a  mov     r8d, 80045366h
0x180079360  mov     rdx, rax
0x180079363  lea     rcx, [rbp+1C0h+var_F0]
0x18007936a  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x180079370  lea     rcx, [rdi+50h]
0x180079374  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180079379  mov     rdi, rax
0x18007937c  test    ebx, ebx
0x18007937e  jle     short loc_180079389
0x180079380  movzx   ebx, bx
0x180079383  or      ebx, 80070000h
0x180079389  mov     [rsp+2C0h+var_298], 11h
0x180079391  mov     dword ptr [rsp+2C0h+lpOverlapped], 1FEh
0x180079399  mov     r9, r13
0x18007939c  lea     r8, aFilesfC; "FILESF_C"
0x1800793a3  mov     rdx, r12
0x1800793a6  lea     rcx, [rsp+2C0h+var_268]
0x1800793ab  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800793b0  mov     [rsp+2C0h+lpOverlapped], rdi
0x1800793b5  lea     r9, aReadfileS; "ReadFile('%s')"
0x1800793bc  mov     r8d, ebx
0x1800793bf  mov     rdx, rax
0x1800793c2  lea     rcx, [rbp+1C0h+var_F0]
0x1800793c9  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x1800793cf  mov     [rsp+2C0h+var_298], ebx
0x1800793d3  mov     dword ptr [rsp+2C0h+lpOverlapped], 1CCh
0x1800793db  mov     r9, r13
0x1800793de  mov     r8, r14
0x1800793e1  mov     rdx, r12
0x1800793e4  lea     rcx, [rsp+2C0h+var_268]
0x1800793e9  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800793ee  lea     r9, aFileNotYetOpen; "File not yet opened"
0x1800793f5  mov     r8d, 8000FFFFh
0x1800793fb  mov     rdx, rax
0x1800793fe  lea     rcx, [rbp+1C0h+var_F0]
0x180079405  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18007940b  lea     rcx, [rdi+50h]
0x18007940f  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180079414  mov     rbx, rax
0x180079417  mov     [rsp+2C0h+var_298], 11h
0x18007941f  mov     dword ptr [rsp+2C0h+lpOverlapped], 1D2h
0x180079427  mov     r9, r13
0x18007942a  mov     r8, r14
0x18007942d  mov     rdx, r12
0x180079430  lea     rcx, [rsp+2C0h+var_268]
0x180079435  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007943a  mov     r9, rbx
0x18007943d  lea     r8, aGetfilesizeS; "GetFileSize('%s')"
0x180079444  mov     rdx, rax
0x180079447  lea     rcx, [rbp+1C0h+var_F0]
0x18007944e  call    ?TranslateWin32Error@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateWin32Error(CSrmDebugInfo,ushort const *,...)
```

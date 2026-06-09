# CSrmFileSafe::SafeSave(void)

- ea: `0x18007a3b8`
- end: `0x18007a841`
- name: `?SafeSave@CSrmFileSafe@@QEAAXXZ`
- size: `1161`
- prototype: `void __fastcall(CSrmFileSafe *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x1800106e0`

## callees

- `0x18000ee10`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180074048`
- `0x180074a04`
- `0x180075034`
- `0x1800777a4`
- `0x180078128`
- `0x180078a88`
- `0x18007a3b8`
- `0x18007aa14`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!Sleep` at `0x18007a5d8`
- `KERNEL32!Sleep` at `0x18007a6d1`
- `KERNEL32!Sleep` at `0x18007a5d8`
- `KERNEL32!Sleep` at `0x18007a6d1`
- `KERNEL32!GetLastError` at `0x18007a52a`
- `KERNEL32!GetLastError` at `0x18007a62c`
- `KERNEL32!GetLastError` at `0x18007a52a`
- `KERNEL32!GetLastError` at `0x18007a62c`
- `KERNEL32!LocalFree` at `0x18007a4ad`
- `KERNEL32!LocalFree` at `0x18007a4ad`
- `KERNEL32!MoveFileExW` at `0x18007a519`
- `KERNEL32!MoveFileExW` at `0x18007a61b`
- `KERNEL32!MoveFileExW` at `0x18007a519`
- `KERNEL32!MoveFileExW` at `0x18007a61b`
- `KERNEL32!FlushFileBuffers` at `0x18007a4cc`
- `KERNEL32!FlushFileBuffers` at `0x18007a4cc`

## string_xrefs

- `0x18007a78a`: `File not yet opened`
- `0x18007a5b4`: `MoveFile(%d) of %s to %s failed %u`
- `0x18007a754`: `MoveFile 2 (%d)`
- `0x18007a82a`: `MoveFile(%d)`
- `0x18007a6b1`: `MoveFile of %s to %s failed %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CSrmFileSafe::SafeSave(CSrmFileSafe *this)
{
  unsigned int v2; // r9d
  char **v3; // r14
  void *v4; // rcx
  char **v5; // rdi
  int v6; // r12d
  const WCHAR *v7; // rdx
  const WCHAR *v8; // rcx
  signed int LastError; // esi
  char *v10; // r13
  char *v11; // r15
  int v12; // r12d
  _QWORD *v13; // rsi
  const WCHAR *v14; // rdx
  const WCHAR *v15; // rcx
  signed int v16; // ebx
  char *v17; // r15
  _QWORD *v18; // r14
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // [rsp+20h] [rbp-E0h]
  __int64 v25; // [rsp+20h] [rbp-E0h]
  __int64 v26; // [rsp+28h] [rbp-D8h]
  __int64 v27; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v28; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v29; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  int v33; // [rsp+68h] [rbp-98h]
  _BYTE v34[96]; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+D0h] [rbp-30h]
  _QWORD v36[3]; // [rsp+D8h] [rbp-28h] BYREF
  int v37; // [rsp+F0h] [rbp-10h]
  int v38; // [rsp+F4h] [rbp-Ch]
  int v39; // [rsp+F8h] [rbp-8h]
  char v40[96]; // [rsp+100h] [rbp+0h] BYREF
  int v41; // [rsp+160h] [rbp+60h]
  _QWORD v42[22]; // [rsp+170h] [rbp+70h] BYREF

  v36[0] = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
  v36[1] = L"CSrmFileSafe::SafeSave";
  v36[2] = L"FILESF_C";
  v37 = 761;
  v38 = 17;
  v39 = 255;
  v41 = 0x1000000;
  memset_0(v40, 0, sizeof(v40));
  CSrmFunctionTracer::CSrmFunctionTracer(v42, v36, 0);
  if ( !*((_BYTE *)this + 201) )
  {
    v20 = CSrmDebugInfo::CSrmDebugInfo(
            &v28,
            L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
            L"FILESF_C",
            L"CSrmFileSafe::SafeSave",
            767,
            17);
    CSrmFunctionTracer::TranslateGenericError(v42, v20, 2147767062LL, L"File not yet opened");
  }
  v2 = *((_DWORD *)this + 60);
  if ( v2 )
  {
    CSrmFileSafe::WriteToFile(this, (struct CSrmFunctionTracer *)v42, *((unsigned __int8 **)this + 29), v2);
    *((_DWORD *)this + 60) = 0;
    memset_0(*((void **)this + 29), 0, 0x10000u);
  }
  v3 = (char **)((char *)this + 160);
  CSrmFileSafe::DeleteInternal((LPCWSTR)this + 80, 0);
  v4 = (void *)*((_QWORD *)this + 29);
  if ( v4 )
    LocalFree(v4);
  *((_QWORD *)this + 29) = 0;
  *((_DWORD *)this + 60) = 0;
  v5 = (char **)((char *)this + 80);
  if ( !FlushFileBuffers(*((HANDLE *)this + 27)) )
  {
    v21 = std::wstring::c_str((char *)this + 80);
    v22 = CSrmDebugInfo::CSrmDebugInfo(
            &v28,
            L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
            L"FILESF_C",
            L"CSrmFileSafe::SafeSave",
            785,
            17);
    CSrmFunctionTracer::TranslateWin32Error(v42, v22, L"FlushFileBuffers(%s)", v21);
  }
  CSrmFileSafe::Close(this);
  if ( (unsigned __int8)CSrmFileSafe::IsFilePresent((LPCWSTR)this + 40) )
  {
    v6 = 0;
    while ( 1 )
    {
      v7 = *((_QWORD *)this + 23) < 8u ? (const WCHAR *)((char *)this + 160) : (const WCHAR *)*v3;
      v8 = *((_QWORD *)this + 13) < 8u ? (const WCHAR *)((char *)this + 80) : (const WCHAR *)*v5;
      if ( MoveFileExW(v8, v7, 1u) )
        break;
      ++v6;
      LastError = GetLastError();
      if ( *((_QWORD *)this + 23) < 8u )
        v10 = (char *)this + 160;
      else
        v10 = *v3;
      if ( *((_QWORD *)this + 13) < 8u )
        v11 = (char *)this + 80;
      else
        v11 = *v5;
      v28 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
      v29 = L"CSrmFileSafe::SafeSave";
      v30 = L"FILESF_C";
      v31 = 813;
      v32 = 1;
      v33 = 255;
      v35 = 0x1000000;
      memset_0(v34, 0, sizeof(v34));
      LODWORD(v27) = LastError;
      CSrmFunctionTracer::Trace(v42, &v28, L"MoveFile(%d) of %s to %s failed %u", (unsigned int)v6, v11, v10, v27);
      if ( v6 >= 10 )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v23 = CSrmDebugInfo::CSrmDebugInfo(
                &v28,
                L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
                L"FILESF_C",
                L"CSrmFileSafe::SafeSave",
                816,
                1);
        LODWORD(v25) = v6;
        CSrmFunctionTracer::TranslateGenericError(v42, v23, (unsigned int)LastError, L"MoveFile(%d)", v25);
      }
      Sleep(0x3E8u);
    }
  }
  CSrmFileSafe::DeleteInternal((LPCWSTR)this + 80, 0);
  v12 = 0;
  v13 = (_QWORD *)((char *)this + 120);
  while ( 1 )
  {
    v14 = (unsigned __int64)v5[3] < 8 ? (const WCHAR *)v5 : (const WCHAR *)*v5;
    v15 = v13[3] < 8u ? (const WCHAR *)v13 : (const WCHAR *)*v13;
    if ( MoveFileExW(v15, v14, 1u) )
      break;
    ++v12;
    v16 = GetLastError();
    if ( (unsigned __int64)v5[3] < 8 )
      v17 = (char *)v5;
    else
      v17 = *v5;
    if ( v13[3] < 8u )
      v18 = v13;
    else
      v18 = (_QWORD *)*v13;
    v28 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
    v29 = L"CSrmFileSafe::SafeSave";
    v30 = L"FILESF_C";
    v31 = 845;
    v32 = 1;
    v33 = 255;
    v35 = 0x1000000;
    memset_0(v34, 0, sizeof(v34));
    LODWORD(v26) = v16;
    CSrmFunctionTracer::Trace(v42, &v28, L"MoveFile of %s to %s failed %u", v18, v17, v26);
    if ( v12 >= 10 )
    {
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      v19 = CSrmDebugInfo::CSrmDebugInfo(
              &v28,
              L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
              L"FILESF_C",
              L"CSrmFileSafe::SafeSave",
              848,
              1);
      LODWORD(v24) = v12;
      CSrmFunctionTracer::TranslateGenericError(v42, v19, (unsigned int)v16, L"MoveFile 2 (%d)", v24);
    }
    Sleep(0x3E8u);
  }
  v42[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v42);
}

```

## disassembly

```asm
0x18007a3b8  push    rbp
0x18007a3ba  push    rbx
0x18007a3bb  push    rsi
0x18007a3bc  push    rdi
0x18007a3bd  push    r12
0x18007a3bf  push    r13
0x18007a3c1  push    r14
0x18007a3c3  push    r15
0x18007a3c5  lea     rbp, [rsp-138h]
0x18007a3cd  sub     rsp, 238h
0x18007a3d4  mov     rax, cs:__security_cookie
0x18007a3db  xor     rax, rsp
0x18007a3de  mov     [rbp+170h+var_50], rax
0x18007a3e5  mov     rbx, rcx
0x18007a3e8  lea     r15, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x18007a3ef  mov     [rbp+170h+var_198], r15
0x18007a3f3  lea     r12, aCsrmfilesafeSa_0; "CSrmFileSafe::SafeSave"
0x18007a3fa  mov     [rbp+170h+var_190], r12
0x18007a3fe  lea     rdi, aFilesfC; "FILESF_C"
0x18007a405  mov     [rbp+170h+var_188], rdi
0x18007a409  mov     [rbp+170h+var_180], 2F9h
0x18007a410  mov     esi, 11h
0x18007a415  mov     [rbp+170h+var_17C], esi
0x18007a418  mov     [rbp+170h+var_178], 0FFh
0x18007a41f  xor     r13d, r13d
0x18007a422  mov     [rbp+170h+var_110], 1000000h
0x18007a429  xor     edx, edx; Val
0x18007a42b  lea     r8d, [rsi+4Fh]; Size
0x18007a42f  lea     rcx, [rbp+170h+var_170]; void *
0x18007a433  call    memset_0
0x18007a438  xor     r8d, r8d
0x18007a43b  lea     rdx, [rbp+170h+var_198]
0x18007a43f  lea     rcx, [rbp+170h+var_100]
0x18007a443  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007a448  nop
0x18007a449  cmp     [rbx+0C9h], r13b
0x18007a450  jz      loc_18007A76B
0x18007a456  mov     r9d, [rbx+0F0h]; unsigned int
0x18007a45d  test    r9d, r9d
0x18007a460  jz      short loc_18007A490
0x18007a462  mov     r8, [rbx+0E8h]; unsigned __int8 *
0x18007a469  lea     rdx, [rbp+170h+var_100]; struct CSrmFunctionTracer *
0x18007a46d  mov     rcx, rbx; this
0x18007a470  call    ?WriteToFile@CSrmFileSafe@@AEAAXAEAVCSrmFunctionTracer@@PEAEK@Z; CSrmFileSafe::WriteToFile(CSrmFunctionTracer &,uchar *,ulong)
0x18007a475  mov     [rbx+0F0h], r13d
0x18007a47c  xor     edx, edx; Val
0x18007a47e  mov     r8d, 10000h; Size
0x18007a484  mov     rcx, [rbx+0E8h]; void *
0x18007a48b  call    memset_0
0x18007a490  lea     r14, [rbx+0A0h]
0x18007a497  xor     edx, edx
0x18007a499  mov     rcx, r14; lpFileName
0x18007a49c  call    ?DeleteInternal@CSrmFileSafe@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; CSrmFileSafe::DeleteInternal(std::wstring const &,int)
0x18007a4a1  mov     rcx, [rbx+0E8h]; hMem
0x18007a4a8  test    rcx, rcx
0x18007a4ab  jz      short loc_18007A4B3
0x18007a4ad  call    cs:__imp_LocalFree
0x18007a4b3  mov     [rbx+0E8h], r13
0x18007a4ba  mov     [rbx+0F0h], r13d
0x18007a4c1  lea     rdi, [rbx+50h]
0x18007a4c5  mov     rcx, [rbx+0D8h]; hFile
0x18007a4cc  call    cs:__imp_FlushFileBuffers
0x18007a4d2  test    eax, eax
0x18007a4d4  jz      loc_18007A7A4
0x18007a4da  mov     rcx, rbx; this
0x18007a4dd  call    ?Close@CSrmFileSafe@@QEAAXXZ; CSrmFileSafe::Close(void)
0x18007a4e2  mov     rcx, rdi; lpFileName
0x18007a4e5  call    ?IsFilePresent@CSrmFileSafe@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CSrmFileSafe::IsFilePresent(std::wstring const &)
0x18007a4ea  test    al, al
0x18007a4ec  jz      loc_18007A5E6
0x18007a4f2  mov     r12d, r13d
0x18007a4f5  cmp     qword ptr [r14+18h], 8
0x18007a4fa  jb      short loc_18007A501
0x18007a4fc  mov     rdx, [r14]
0x18007a4ff  jmp     short loc_18007A504
0x18007a501  mov     rdx, r14; lpNewFileName
0x18007a504  cmp     qword ptr [rdi+18h], 8
0x18007a509  jb      short loc_18007A510
0x18007a50b  mov     rcx, [rdi]
0x18007a50e  jmp     short loc_18007A513
0x18007a510  mov     rcx, rdi; lpExistingFileName
0x18007a513  mov     r8d, 1; dwFlags
0x18007a519  call    cs:__imp_MoveFileExW
0x18007a51f  test    eax, eax
0x18007a521  jnz     loc_18007A5E6
0x18007a527  inc     r12d
0x18007a52a  call    cs:__imp_GetLastError
0x18007a530  mov     esi, eax
0x18007a532  cmp     qword ptr [r14+18h], 8
0x18007a537  jb      short loc_18007A53E
0x18007a539  mov     r13, [r14]
0x18007a53c  jmp     short loc_18007A541
0x18007a53e  mov     r13, r14
0x18007a541  cmp     qword ptr [rdi+18h], 8
0x18007a546  jb      short loc_18007A54D
0x18007a548  mov     r15, [rdi]
0x18007a54b  jmp     short loc_18007A550
0x18007a54d  mov     r15, rdi
0x18007a550  lea     rax, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x18007a557  mov     [rsp+270h+var_228], rax
0x18007a55c  lea     rax, aCsrmfilesafeSa_0; "CSrmFileSafe::SafeSave"
0x18007a563  mov     [rsp+270h+var_220], rax
0x18007a568  lea     rax, aFilesfC; "FILESF_C"
0x18007a56f  mov     [rsp+270h+var_218], rax
0x18007a574  mov     [rsp+270h+var_210], 32Dh
0x18007a57c  mov     [rsp+270h+var_20C], 1
0x18007a584  mov     [rsp+270h+var_208], 0FFh
0x18007a58c  mov     [rbp+170h+var_1A0], 1000000h
0x18007a593  xor     edx, edx; Val
0x18007a595  lea     r8d, [rdx+60h]; Size
0x18007a599  lea     rcx, [rsp+270h+var_200]; void *
0x18007a59e  call    memset_0
0x18007a5a3  mov     dword ptr [rsp+270h+var_240], esi
0x18007a5a7  mov     [rsp+270h+var_248], r13
0x18007a5ac  mov     [rsp+270h+var_250], r15
0x18007a5b1  mov     r9d, r12d
0x18007a5b4  lea     r8, aMovefileDOfSTo; "MoveFile(%d) of %s to %s failed %u"
0x18007a5bb  lea     rdx, [rsp+270h+var_228]
0x18007a5c0  lea     rcx, [rbp+170h+var_100]
0x18007a5c4  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18007a5c9  cmp     r12d, 0Ah
0x18007a5cd  jge     loc_18007A7E9
0x18007a5d3  mov     ecx, 3E8h; dwMilliseconds
0x18007a5d8  call    cs:__imp_Sleep
0x18007a5de  xor     r13d, r13d
0x18007a5e1  jmp     loc_18007A4F5
0x18007a5e6  xor     edx, edx
0x18007a5e8  mov     rcx, r14; lpFileName
0x18007a5eb  call    ?DeleteInternal@CSrmFileSafe@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; CSrmFileSafe::DeleteInternal(std::wstring const &,int)
0x18007a5f0  mov     r12d, r13d
0x18007a5f3  lea     rsi, [rbx+78h]
0x18007a5f7  cmp     qword ptr [rdi+18h], 8
0x18007a5fc  jb      short loc_18007A603
0x18007a5fe  mov     rdx, [rdi]
0x18007a601  jmp     short loc_18007A606
0x18007a603  mov     rdx, rdi; lpNewFileName
0x18007a606  cmp     qword ptr [rsi+18h], 8
0x18007a60b  jb      short loc_18007A612
0x18007a60d  mov     rcx, [rsi]
0x18007a610  jmp     short loc_18007A615
0x18007a612  mov     rcx, rsi; lpExistingFileName
0x18007a615  mov     r8d, 1; dwFlags
0x18007a61b  call    cs:__imp_MoveFileExW
0x18007a621  test    eax, eax
0x18007a623  jnz     loc_18007A6DC
0x18007a629  inc     r12d
0x18007a62c  call    cs:__imp_GetLastError
0x18007a632  mov     ebx, eax
0x18007a634  cmp     qword ptr [rdi+18h], 8
0x18007a639  jb      short loc_18007A640
0x18007a63b  mov     r15, [rdi]
0x18007a63e  jmp     short loc_18007A643
0x18007a640  mov     r15, rdi
0x18007a643  cmp     qword ptr [rsi+18h], 8
0x18007a648  jb      short loc_18007A64F
0x18007a64a  mov     r14, [rsi]
0x18007a64d  jmp     short loc_18007A652
0x18007a64f  mov     r14, rsi
0x18007a652  lea     rax, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x18007a659  mov     [rsp+270h+var_228], rax
0x18007a65e  lea     rax, aCsrmfilesafeSa_0; "CSrmFileSafe::SafeSave"
0x18007a665  mov     [rsp+270h+var_220], rax
0x18007a66a  lea     rax, aFilesfC; "FILESF_C"
0x18007a671  mov     [rsp+270h+var_218], rax
0x18007a676  mov     [rsp+270h+var_210], 34Dh
0x18007a67e  mov     [rsp+270h+var_20C], 1
0x18007a686  mov     [rsp+270h+var_208], 0FFh
0x18007a68e  mov     [rbp+170h+var_1A0], 1000000h
0x18007a695  xor     edx, edx; Val
0x18007a697  lea     r8d, [rdx+60h]; Size
0x18007a69b  lea     rcx, [rsp+270h+var_200]; void *
0x18007a6a0  call    memset_0
0x18007a6a5  mov     dword ptr [rsp+270h+var_248], ebx
0x18007a6a9  mov     [rsp+270h+var_250], r15
0x18007a6ae  mov     r9, r14
0x18007a6b1  lea     r8, aMovefileOfSToS_0; "MoveFile of %s to %s failed %u"
0x18007a6b8  lea     rdx, [rsp+270h+var_228]
0x18007a6bd  lea     rcx, [rbp+170h+var_100]
0x18007a6c1  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18007a6c6  cmp     r12d, 0Ah
0x18007a6ca  jge     short loc_18007A713
0x18007a6cc  mov     ecx, 3E8h; dwMilliseconds
0x18007a6d1  call    cs:__imp_Sleep
0x18007a6d7  jmp     loc_18007A5F7
0x18007a6dc  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007a6e3  mov     [rbp+170h+var_100], rax
0x18007a6e7  lea     rcx, [rbp+170h+var_100]; this
0x18007a6eb  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007a6f0  mov     rcx, [rbp+170h+var_50]
0x18007a6f7  xor     rcx, rsp; StackCookie
0x18007a6fa  call    __security_check_cookie
0x18007a6ff  add     rsp, 238h
0x18007a706  pop     r15
0x18007a708  pop     r14
0x18007a70a  pop     r13
0x18007a70c  pop     r12
0x18007a70e  pop     rdi
0x18007a70f  pop     rsi
0x18007a710  pop     rbx
0x18007a711  pop     rbp
0x18007a712  retn
0x18007a713  test    ebx, ebx
0x18007a715  jle     short loc_18007A720
0x18007a717  movzx   ebx, bx
0x18007a71a  or      ebx, 80070000h
0x18007a720  mov     dword ptr [rsp+270h+var_248], 1
0x18007a728  mov     dword ptr [rsp+270h+var_250], 350h
0x18007a730  lea     r9, aCsrmfilesafeSa_0; "CSrmFileSafe::SafeSave"
0x18007a737  lea     r8, aFilesfC; "FILESF_C"
0x18007a73e  lea     rdx, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x18007a745  lea     rcx, [rsp+270h+var_228]
0x18007a74a  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007a74f  mov     dword ptr [rsp+270h+var_250], r12d
0x18007a754  lea     r9, aMovefile2D; "MoveFile 2 (%d)"
0x18007a75b  mov     r8d, ebx
0x18007a75e  mov     rdx, rax
0x18007a761  lea     rcx, [rbp+170h+var_100]
0x18007a765  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x18007a76b  mov     dword ptr [rsp+270h+var_248], esi
0x18007a76f  mov     dword ptr [rsp+270h+var_250], 2FFh
0x18007a777  mov     r9, r12
0x18007a77a  mov     r8, rdi
0x18007a77d  mov     rdx, r15
0x18007a780  lea     rcx, [rsp+270h+var_228]
0x18007a785  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007a78a  lea     r9, aFileNotYetOpen; "File not yet opened"
0x18007a791  mov     r8d, 80045316h
0x18007a797  mov     rdx, rax
0x18007a79a  lea     rcx, [rbp+170h+var_100]
0x18007a79e  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x18007a7a4  mov     rcx, rdi
0x18007a7a7  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18007a7ac  mov     rbx, rax
0x18007a7af  mov     dword ptr [rsp+270h+var_248], esi
0x18007a7b3  mov     dword ptr [rsp+270h+var_250], 311h
0x18007a7bb  mov     r9, r12
0x18007a7be  lea     r8, aFilesfC; "FILESF_C"
0x18007a7c5  mov     rdx, r15
0x18007a7c8  lea     rcx, [rsp+270h+var_228]
0x18007a7cd  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007a7d2  mov     r9, rbx
0x18007a7d5  lea     r8, aFlushfilebuffe; "FlushFileBuffers(%s)"
0x18007a7dc  mov     rdx, rax
0x18007a7df  lea     rcx, [rbp+170h+var_100]
0x18007a7e3  call    ?TranslateWin32Error@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateWin32Error(CSrmDebugInfo,ushort const *,...)
0x18007a7e9  test    esi, esi
0x18007a7eb  jle     short loc_18007A7F6
0x18007a7ed  movzx   esi, si
0x18007a7f0  or      esi, 80070000h
0x18007a7f6  mov     dword ptr [rsp+270h+var_248], 1
0x18007a7fe  mov     dword ptr [rsp+270h+var_250], 330h
0x18007a806  lea     r9, aCsrmfilesafeSa_0; "CSrmFileSafe::SafeSave"
0x18007a80d  lea     r8, aFilesfC; "FILESF_C"
0x18007a814  lea     rdx, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x18007a81b  lea     rcx, [rsp+270h+var_228]
0x18007a820  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007a825  mov     dword ptr [rsp+270h+var_250], r12d
0x18007a82a  lea     r9, aMovefileD; "MoveFile(%d)"
0x18007a831  mov     r8d, esi
0x18007a834  mov     rdx, rax
0x18007a837  lea     rcx, [rbp+170h+var_100]
0x18007a83b  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
```

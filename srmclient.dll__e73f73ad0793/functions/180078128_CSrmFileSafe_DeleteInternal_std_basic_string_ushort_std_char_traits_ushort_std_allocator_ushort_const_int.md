# CSrmFileSafe::DeleteInternal(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,int)

- ea: `0x180078128`
- end: `0x18007833b`
- name: `?DeleteInternal@CSrmFileSafe@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z`
- size: `531`
- prototype: `void __fastcall(LPCWSTR lpFileName, int)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180077fd8`
- `0x18007945c`
- `0x180079b9c`
- `0x18007a3b8`

## callees

- `0x18000ee10`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180074048`
- `0x180075034`
- `0x180078128`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800781d1`
- `KERNEL32!GetLastError` at `0x1800781e0`
- `KERNEL32!GetLastError` at `0x1800781f3`
- `KERNEL32!GetLastError` at `0x1800781d1`
- `KERNEL32!GetLastError` at `0x1800781e0`
- `KERNEL32!GetLastError` at `0x1800781f3`
- `KERNEL32!DeleteFileW` at `0x1800781c3`
- `KERNEL32!DeleteFileW` at `0x1800781c3`

## string_xrefs

- `0x18007824a`: `Error: DeleteFile(%s) = %u`
- `0x180078162`: `CSrmFileSafe::DeleteInternal`
- `0x180078327`: `DeleteFile(%s)`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall CSrmFileSafe::DeleteInternal(LPCWSTR lpFileName, int a2)
{
  const WCHAR *v4; // rcx
  DWORD LastError; // edi
  __int64 v6; // rbx
  __int64 v7; // rax
  DWORD v8; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v9; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v10; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v11; // [rsp+58h] [rbp-A8h]
  int v12; // [rsp+60h] [rbp-A0h]
  int v13; // [rsp+64h] [rbp-9Ch]
  int v14; // [rsp+68h] [rbp-98h]
  _BYTE v15[96]; // [rsp+70h] [rbp-90h] BYREF
  int v16; // [rsp+D0h] [rbp-30h]
  _QWORD v17[3]; // [rsp+D8h] [rbp-28h] BYREF
  int v18; // [rsp+F0h] [rbp-10h]
  int v19; // [rsp+F4h] [rbp-Ch]
  int v20; // [rsp+F8h] [rbp-8h]
  _BYTE v21[96]; // [rsp+100h] [rbp+0h] BYREF
  int v22; // [rsp+160h] [rbp+60h]
  _QWORD v23[22]; // [rsp+170h] [rbp+70h] BYREF

  v17[0] = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
  v17[1] = L"CSrmFileSafe::DeleteInternal";
  v17[2] = L"FILESF_C";
  v18 = 878;
  v19 = 17;
  v20 = 255;
  v22 = 0x1000000;
  memset_0(v21, 0, sizeof(v21));
  CSrmFunctionTracer::CSrmFunctionTracer(v23, v17, 0);
  if ( *((_QWORD *)lpFileName + 3) < 8u )
    v4 = lpFileName;
  else
    v4 = *(const WCHAR **)lpFileName;
  if ( !DeleteFileW(v4) )
  {
    if ( GetLastError() == 2 || GetLastError() == 3 )
    {
      if ( *((_QWORD *)lpFileName + 3) >= 8u )
        lpFileName = *(LPCWSTR *)lpFileName;
      v9 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
      v10 = L"CSrmFileSafe::DeleteInternal";
      v11 = L"FILESF_C";
      v12 = 884;
      v13 = 17;
      v14 = 255;
      v16 = 0x1000000;
      memset_0(v15, 0, sizeof(v15));
      CSrmFunctionTracer::Trace(v23, &v9, L"File '%s' not found ... ", lpFileName);
    }
    else
    {
      if ( a2 )
      {
        v6 = std::wstring::c_str(lpFileName);
        v7 = CSrmDebugInfo::CSrmDebugInfo(
               &v9,
               L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp",
               L"FILESF_C",
               L"CSrmFileSafe::DeleteInternal",
               890,
               17);
        CSrmFunctionTracer::TranslateWin32Error(v23, v7, L"DeleteFile(%s)", v6);
      }
      LastError = GetLastError();
      if ( *((_QWORD *)lpFileName + 3) >= 8u )
        lpFileName = *(LPCWSTR *)lpFileName;
      v9 = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
      v10 = L"CSrmFileSafe::DeleteInternal";
      v11 = L"FILESF_C";
      v12 = 894;
      v13 = 17;
      v14 = 255;
      v16 = 0x1000000;
      memset_0(v15, 0, sizeof(v15));
      v8 = LastError;
      CSrmFunctionTracer::Trace(v23, &v9, L"Error: DeleteFile(%s) = %u", lpFileName, v8);
    }
  }
  v23[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v23);
}

```

## disassembly

```asm
0x180078128  push    rbp
0x18007812a  push    rbx
0x18007812b  push    rdi
0x18007812c  push    r12
0x18007812e  push    r14
0x180078130  push    r15
0x180078132  lea     rbp, [rsp-138h]
0x18007813a  sub     rsp, 238h
0x180078141  mov     rax, cs:__security_cookie
0x180078148  xor     rax, rsp
0x18007814b  mov     [rbp+160h+var_40], rax
0x180078152  mov     edi, edx
0x180078154  mov     rbx, rcx
0x180078157  lea     r14, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x18007815e  mov     [rbp+160h+var_188], r14
0x180078162  lea     r15, aCsrmfilesafeDe_0; "CSrmFileSafe::DeleteInternal"
0x180078169  mov     [rbp+160h+var_180], r15
0x18007816d  lea     r12, aFilesfC; "FILESF_C"
0x180078174  mov     [rbp+160h+var_178], r12
0x180078178  mov     [rbp+160h+var_170], 36Eh
0x18007817f  mov     [rbp+160h+var_16C], 11h
0x180078186  mov     [rbp+160h+var_168], 0FFh
0x18007818d  mov     [rbp+160h+var_100], 1000000h
0x180078194  xor     edx, edx; Val
0x180078196  lea     r8d, [rdx+60h]; Size
0x18007819a  lea     rcx, [rbp+160h+var_160]; void *
0x18007819e  call    memset_0
0x1800781a3  xor     r8d, r8d
0x1800781a6  lea     rdx, [rbp+160h+var_188]
0x1800781aa  lea     rcx, [rbp+160h+var_F0]
0x1800781ae  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800781b3  nop
0x1800781b4  cmp     qword ptr [rbx+18h], 8
0x1800781b9  jb      short loc_1800781C0
0x1800781bb  mov     rcx, [rbx]
0x1800781be  jmp     short loc_1800781C3
0x1800781c0  mov     rcx, rbx; lpFileName
0x1800781c3  call    cs:__imp_DeleteFileW
0x1800781c9  test    eax, eax
0x1800781cb  jnz     loc_1800782C2
0x1800781d1  call    cs:__imp_GetLastError
0x1800781d7  cmp     eax, 2
0x1800781da  jz      loc_180078261
0x1800781e0  call    cs:__imp_GetLastError
0x1800781e6  cmp     eax, 3
0x1800781e9  jz      short loc_180078261
0x1800781eb  test    edi, edi
0x1800781ed  jnz     loc_1800782F6
0x1800781f3  call    cs:__imp_GetLastError
0x1800781f9  mov     edi, eax
0x1800781fb  cmp     qword ptr [rbx+18h], 8
0x180078200  jb      short loc_180078205
0x180078202  mov     rbx, [rbx]
0x180078205  mov     [rsp+260h+var_218], r14
0x18007820a  mov     [rsp+260h+var_210], r15
0x18007820f  mov     [rsp+260h+var_208], r12
0x180078214  mov     [rsp+260h+var_200], 37Eh
0x18007821c  mov     [rsp+260h+var_1FC], 11h
0x180078224  mov     [rsp+260h+var_1F8], 0FFh
0x18007822c  mov     [rbp+160h+var_190], 1000000h
0x180078233  xor     edx, edx; Val
0x180078235  lea     r8d, [rdx+60h]; Size
0x180078239  lea     rcx, [rsp+260h+var_1F0]; void *
0x18007823e  call    memset_0
0x180078243  mov     [rsp+260h+var_240], edi
0x180078247  mov     r9, rbx
0x18007824a  lea     r8, aErrorDeletefil; "Error: DeleteFile(%s) = %u"
0x180078251  lea     rdx, [rsp+260h+var_218]
0x180078256  lea     rcx, [rbp+160h+var_F0]
0x18007825a  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18007825f  jmp     short loc_1800782C2
0x180078261  cmp     qword ptr [rbx+18h], 8
0x180078266  jb      short loc_18007826B
0x180078268  mov     rbx, [rbx]
0x18007826b  mov     [rsp+260h+var_218], r14
0x180078270  mov     [rsp+260h+var_210], r15
0x180078275  mov     [rsp+260h+var_208], r12
0x18007827a  mov     [rsp+260h+var_200], 374h
0x180078282  mov     [rsp+260h+var_1FC], 11h
0x18007828a  mov     [rsp+260h+var_1F8], 0FFh
0x180078292  mov     [rbp+160h+var_190], 1000000h
0x180078299  xor     edx, edx; Val
0x18007829b  lea     r8d, [rdx+60h]; Size
0x18007829f  lea     rcx, [rsp+260h+var_1F0]; void *
0x1800782a4  call    memset_0
0x1800782a9  mov     r9, rbx
0x1800782ac  lea     r8, aFileSNotFound; "File '%s' not found ... "
0x1800782b3  lea     rdx, [rsp+260h+var_218]
0x1800782b8  lea     rcx, [rbp+160h+var_F0]
0x1800782bc  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x1800782c1  nop
0x1800782c2  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800782c9  mov     [rbp+160h+var_F0], rax
0x1800782cd  lea     rcx, [rbp+160h+var_F0]; this
0x1800782d1  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800782d6  mov     rcx, [rbp+160h+var_40]
0x1800782dd  xor     rcx, rsp; StackCookie
0x1800782e0  call    __security_check_cookie
0x1800782e5  add     rsp, 238h
0x1800782ec  pop     r15
0x1800782ee  pop     r14
0x1800782f0  pop     r12
0x1800782f2  pop     rdi
0x1800782f3  pop     rbx
0x1800782f4  pop     rbp
0x1800782f5  retn
0x1800782f6  mov     rcx, rbx
0x1800782f9  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1800782fe  mov     rbx, rax
0x180078301  mov     [rsp+260h+var_238], 11h
0x180078309  mov     [rsp+260h+var_240], 37Ah
0x180078311  mov     r9, r15
0x180078314  mov     r8, r12
0x180078317  mov     rdx, r14
0x18007831a  lea     rcx, [rsp+260h+var_218]
0x18007831f  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180078324  mov     r9, rbx
0x180078327  lea     r8, aDeletefileS; "DeleteFile(%s)"
0x18007832e  mov     rdx, rax
0x180078331  lea     rcx, [rbp+160h+var_F0]
0x180078335  call    ?TranslateWin32Error@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateWin32Error(CSrmDebugInfo,ushort const *,...)
```

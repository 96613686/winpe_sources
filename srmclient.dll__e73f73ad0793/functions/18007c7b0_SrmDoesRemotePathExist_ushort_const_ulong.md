# SrmDoesRemotePathExist(ushort const *,ulong *)

- ea: `0x18007c7b0`
- end: `0x18007ca6d`
- name: `?SrmDoesRemotePathExist@@YA_NPEBGPEAK@Z`
- size: `701`
- prototype: `bool __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task`

## callers

- `0x1800513f8`

## callees

- `0x180001350`
- `0x180006a1c`
- `0x18000ac44`
- `0x18000af40`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x18007b264`
- `0x18007c7b0`
- `0x18007e620`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18007c8ac`
- `msvcrt!_wcsnicmp` at `0x18007c8c9`
- `msvcrt!_wcsnicmp` at `0x18007c8ac`
- `msvcrt!_wcsnicmp` at `0x18007c8c9`
- `msvcrt!iswalpha` at `0x18007c8f5`
- `msvcrt!iswalpha` at `0x18007c8f5`
- `ole32!CoTaskMemFree` at `0x18007c95a`
- `ole32!CoTaskMemFree` at `0x18007c96d`
- `ole32!CoTaskMemFree` at `0x18007c95a`
- `ole32!CoTaskMemFree` at `0x18007c96d`
- `KERNEL32!GetFileAttributesW` at `0x18007c920`
- `KERNEL32!GetFileAttributesW` at `0x18007c920`

## string_xrefs

- `0x18007c7f2`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007c80a`: `SRMPATHC`
- `0x18007c9e9`: `SRMPATHC`
- `0x18007ca03`: `Specified path does not look like a share path: %s`
- `0x18007c7fe`: `SrmDoesRemotePathExist`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
bool __fastcall SrmDoesRemotePathExist(const unsigned __int16 *a1, unsigned int *a2)
{
  wchar_t *v4; // rbx
  char v5; // al
  const unsigned __int16 *v6; // rdx
  wint_t *v7; // rdi
  unsigned __int64 v8; // rax
  DWORD FileAttributesW; // eax
  bool v10; // di
  unsigned __int16 *Buffer; // rbx
  __int64 v13; // rax
  unsigned int Hr; // ebx
  __int64 v15; // rax
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String2; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v18; // [rsp+50h] [rbp-B0h]
  _QWORD v19[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v20; // [rsp+78h] [rbp-88h]
  _BYTE v21[96]; // [rsp+80h] [rbp-80h] BYREF
  int v22; // [rsp+E0h] [rbp-20h]
  void *Block; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v25; // [rsp+100h] [rbp+0h]
  void **v26; // [rsp+110h] [rbp+10h] BYREF
  int v27; // [rsp+118h] [rbp+18h]

  lpFileName = (LPCWSTR)v19;
  v19[0] = L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp";
  v19[1] = L"SrmDoesRemotePathExist";
  v19[2] = L"SRMPATHC";
  v19[3] = 1378;
  v20 = 255;
  v22 = 0x1000000;
  memset_0(v21, 0, sizeof(v21));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v26, (const struct CSrmDebugInfo *)v19, 0);
  String2 = 0;
  v27 = TrimEdgeQuotes(a1, &String2);
  if ( v27 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v26);
    v18 = v19;
    v15 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v19,
            (__int64)L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
            (__int64)L"SRMPATHC",
            (__int64)L"SrmDoesRemotePathExist",
            1386,
            17);
    CSrmFunctionTracer::Throw(&v26, v15, Hr, L"TrimEdgeQuotes failed");
  }
  lpFileName = 0;
  v25 = 7;
  v24 = 0;
  LOWORD(Block) = 0;
  v4 = String2;
  v5 = IsUncPath(String2, &Block);
  v6 = v4;
  if ( !v5 )
  {
    if ( _wcsnicmp(L"\\\\?\\", v4, 4u) )
    {
      v7 = v4 + 4;
      if ( _wcsnicmp(L"\\\\.\\", v4, 4u) )
        v7 = v4;
    }
    else
    {
      v7 = v4 + 4;
    }
    v8 = -1;
    do
      ++v8;
    while ( v7[v8] );
    if ( v8 < 2 || !iswalpha(*v7) || v7[1] != 58 )
    {
      Buffer = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)&String2);
      v18 = v19;
      v13 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v19,
              (__int64)L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
              (__int64)L"SRMPATHC",
              (__int64)L"SrmDoesRemotePathExist",
              1423,
              17);
      CSrmFunctionTracer::Throw(&v26, v13, 2147942487LL, L"Specified path does not look like a share path: %s", Buffer);
    }
    v6 = v4;
  }
  CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&lpFileName, v6);
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( a2 )
    *a2 = FileAttributesW;
  v10 = FileAttributesW != -1;
  if ( v25 >= 8 )
    operator delete(Block);
  v25 = 7;
  v24 = 0;
  LOWORD(Block) = 0;
  CoTaskMemFree((LPVOID)lpFileName);
  lpFileName = 0;
  CoTaskMemFree(v4);
  String2 = 0;
  v26 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v26);
  return v10;
}

```

## disassembly

```asm
0x18007c7b0  mov     [rsp-8+arg_10], rbx
0x18007c7b5  mov     [rsp-8+arg_18], rsi
0x18007c7ba  push    rbp
0x18007c7bb  push    rdi
0x18007c7bc  push    r12
0x18007c7be  push    r13
0x18007c7c0  push    r14
0x18007c7c2  lea     rbp, [rsp-0D0h]
0x18007c7ca  sub     rsp, 1D0h
0x18007c7d1  mov     rax, cs:__security_cookie
0x18007c7d8  xor     rax, rsp
0x18007c7db  mov     [rbp+0F0h+var_30], rax
0x18007c7e2  mov     rsi, rdx
0x18007c7e5  mov     rbx, rcx
0x18007c7e8  lea     rax, [rsp+1F0h+var_198]
0x18007c7ed  mov     [rsp+1F0h+lpFileName], rax
0x18007c7f2  lea     r12, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x18007c7f9  mov     [rsp+1F0h+var_198], r12
0x18007c7fe  lea     r13, aSrmdoesremotep; "SrmDoesRemotePathExist"
0x18007c805  mov     [rsp+1F0h+var_190], r13
0x18007c80a  lea     rdi, aSrmpathc; "SRMPATHC"
0x18007c811  mov     [rsp+1F0h+var_188], rdi
0x18007c816  mov     [rsp+1F0h+var_180], 562h
0x18007c81f  xor     r14d, r14d
0x18007c822  mov     [rsp+1F0h+var_178], 0FFh
0x18007c82a  mov     [rbp+0F0h+var_110], 1000000h
0x18007c831  xor     edx, edx; Val
0x18007c833  lea     r8d, [r14+60h]; Size
0x18007c837  lea     rcx, [rbp+0F0h+var_170]; void *
0x18007c83b  call    memset_0
0x18007c840  nop
0x18007c841  xor     r8d, r8d
0x18007c844  lea     rdx, [rsp+1F0h+var_198]
0x18007c849  lea     rcx, [rbp+0F0h+var_E0]
0x18007c84d  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007c852  nop
0x18007c853  mov     [rsp+1F0h+String2], r14
0x18007c858  lea     rdx, [rsp+1F0h+String2]; unsigned __int16 **
0x18007c85d  mov     rcx, rbx; unsigned __int16 *
0x18007c860  call    ?TrimEdgeQuotes@@YAJPEBGPEAPEAG@Z; TrimEdgeQuotes(ushort const *,ushort * *)
0x18007c865  mov     [rbp+0F0h+var_D8], eax
0x18007c868  test    eax, eax
0x18007c86a  js      loc_18007CA1D
0x18007c870  mov     [rsp+1F0h+lpFileName], r14
0x18007c875  mov     [rbp+0F0h+var_F0], 7
0x18007c87d  mov     [rbp+0F0h+var_F8], r14
0x18007c881  mov     word ptr [rbp+0F0h+Block], r14w
0x18007c886  lea     rdx, [rbp+0F0h+Block]; Src
0x18007c88a  mov     rbx, [rsp+1F0h+String2]
0x18007c88f  mov     rcx, rbx; String1
0x18007c892  call    ?IsUncPath@@YA_NPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IsUncPath(ushort const *,std::wstring &)
0x18007c897  mov     rdx, rbx; String2
0x18007c89a  test    al, al
0x18007c89c  jnz     short loc_18007C911
0x18007c89e  lea     edi, [r14+4]
0x18007c8a2  mov     r8d, edi; MaxCount
0x18007c8a5  lea     rcx, asc_1800EFAE0; "\\\\?\\"
0x18007c8ac  call    cs:__imp__wcsnicmp
0x18007c8b2  test    eax, eax
0x18007c8b4  jnz     short loc_18007C8BC
0x18007c8b6  lea     rdi, [rbx+8]
0x18007c8ba  jmp     short loc_18007C8DA
0x18007c8bc  mov     r8, rdi; MaxCount
0x18007c8bf  mov     rdx, rbx; String2
0x18007c8c2  lea     rcx, asc_1800EFB08; "\\\\.\\"
0x18007c8c9  call    cs:__imp__wcsnicmp
0x18007c8cf  test    eax, eax
0x18007c8d1  lea     rdi, [rbx+8]
0x18007c8d5  jz      short loc_18007C8DA
0x18007c8d7  mov     rdi, rbx
0x18007c8da  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007c8de  inc     rax
0x18007c8e1  cmp     [rdi+rax*2], r14w
0x18007c8e6  jnz     short loc_18007C8DE
0x18007c8e8  cmp     rax, 2
0x18007c8ec  jb      loc_18007C9BF
0x18007c8f2  movzx   ecx, word ptr [rdi]; C
0x18007c8f5  call    cs:__imp_iswalpha
0x18007c8fb  test    eax, eax
0x18007c8fd  jz      loc_18007C9BF
0x18007c903  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18007c908  jnz     loc_18007C9BF
0x18007c90e  mov     rdx, rbx; unsigned __int16 *
0x18007c911  lea     rcx, [rsp+1F0h+lpFileName]; this
0x18007c916  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18007c91b  mov     rcx, [rsp+1F0h+lpFileName]; lpFileName
0x18007c920  call    cs:__imp_GetFileAttributesW
0x18007c926  test    rsi, rsi
0x18007c929  jz      short loc_18007C92D
0x18007c92b  mov     [rsi], eax
0x18007c92d  cmp     eax, 0FFFFFFFFh
0x18007c930  setnz   dil
0x18007c934  cmp     [rbp+0F0h+var_F0], 8
0x18007c939  jb      short loc_18007C944
0x18007c93b  mov     rcx, [rbp+0F0h+Block]; Block
0x18007c93f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c944  mov     [rbp+0F0h+var_F0], 7
0x18007c94c  mov     [rbp+0F0h+var_F8], r14
0x18007c950  mov     word ptr [rbp+0F0h+Block], r14w
0x18007c955  mov     rcx, [rsp+1F0h+lpFileName]; pv
0x18007c95a  call    cs:__imp_CoTaskMemFree
0x18007c960  mov     [rsp+1F0h+lpFileName], r14
0x18007c965  mov     [rsp+1F0h+lpFileName], r14
0x18007c96a  mov     rcx, rbx; pv
0x18007c96d  call    cs:__imp_CoTaskMemFree
0x18007c973  mov     [rsp+1F0h+String2], r14
0x18007c978  mov     [rsp+1F0h+String2], r14
0x18007c97d  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007c984  mov     [rbp+0F0h+var_E0], rax
0x18007c988  lea     rcx, [rbp+0F0h+var_E0]; this
0x18007c98c  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007c991  mov     al, dil
0x18007c994  mov     rcx, [rbp+0F0h+var_30]
0x18007c99b  xor     rcx, rsp; StackCookie
0x18007c99e  call    __security_check_cookie
0x18007c9a3  lea     r11, [rsp+1F0h+var_20]
0x18007c9ab  mov     rbx, [r11+40h]
0x18007c9af  mov     rsi, [r11+48h]
0x18007c9b3  mov     rsp, r11
0x18007c9b6  pop     r14
0x18007c9b8  pop     r13
0x18007c9ba  pop     r12
0x18007c9bc  pop     rdi
0x18007c9bd  pop     rbp
0x18007c9be  retn
0x18007c9bf  lea     rcx, [rsp+1F0h+String2]; this
0x18007c9c4  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x18007c9c9  mov     rbx, rax
0x18007c9cc  lea     rax, [rsp+1F0h+var_198]
0x18007c9d1  mov     [rsp+1F0h+var_1A0], rax
0x18007c9d6  mov     [rsp+1F0h+var_1C8], 11h
0x18007c9de  mov     dword ptr [rsp+1F0h+var_1D0], 58Fh
0x18007c9e6  mov     r9, r13
0x18007c9e9  lea     r8, aSrmpathc; "SRMPATHC"
0x18007c9f0  mov     rdx, r12
0x18007c9f3  lea     rcx, [rsp+1F0h+var_198]
0x18007c9f8  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007c9fd  nop
0x18007c9fe  mov     [rsp+1F0h+var_1D0], rbx
0x18007ca03  lea     r9, aSpecifiedPathD; "Specified path does not look like a sha"...
0x18007ca0a  mov     r8d, 80070057h
0x18007ca10  mov     rdx, rax
0x18007ca13  lea     rcx, [rbp+0F0h+var_E0]
0x18007ca17  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18007ca1d  lea     rcx, [rbp+0F0h+var_E0]; this
0x18007ca21  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007ca26  mov     ebx, eax
0x18007ca28  lea     rax, [rsp+1F0h+var_198]
0x18007ca2d  mov     [rsp+1F0h+var_1A0], rax
0x18007ca32  mov     [rsp+1F0h+var_1C8], 11h
0x18007ca3a  mov     dword ptr [rsp+1F0h+var_1D0], 56Ah
0x18007ca42  mov     r9, r13
0x18007ca45  mov     r8, rdi
0x18007ca48  mov     rdx, r12
0x18007ca4b  lea     rcx, [rsp+1F0h+var_198]
0x18007ca50  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007ca55  nop
0x18007ca56  lea     r9, aTrimedgequotes; "TrimEdgeQuotes failed"
0x18007ca5d  mov     r8d, ebx
0x18007ca60  mov     rdx, rax
0x18007ca63  lea     rcx, [rbp+0F0h+var_E0]
0x18007ca67  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```

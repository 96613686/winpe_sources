# CExportImport::ReadXmlFromFile(ushort const *,CSrmComBSTR &)

- ea: `0x18000c35c`
- end: `0x18000c7f2`
- name: `?ReadXmlFromFile@CExportImport@@AEAAXPEBGAEAVCSrmComBSTR@@@Z`
- size: `1174`
- prototype: `void __fastcall(CExportImport *this, const unsigned __int16 *, BSTR *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000ba70`
- `0x18000bd50`
- `0x18000c030`

## callees

- `0x18000c35c`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x180073f10`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000c4f0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000c4f0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c420`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c544`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c420`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c544`
- `KERNEL32!ReadFile` at `0x18000c4ab`
- `KERNEL32!ReadFile` at `0x18000c51f`
- `KERNEL32!ReadFile` at `0x18000c4ab`
- `KERNEL32!ReadFile` at `0x18000c51f`
- `KERNEL32!CreateFileW` at `0x18000c44e`
- `KERNEL32!CreateFileW` at `0x18000c44e`
- `KERNEL32!CloseHandle` at `0x18000c55a`
- `KERNEL32!CloseHandle` at `0x18000c55a`
- `KERNEL32!GetFileSize` at `0x18000c46f`
- `KERNEL32!GetFileSize` at `0x18000c46f`
- `KERNEL32!GetLastError` at `0x18000c5b8`
- `KERNEL32!GetLastError` at `0x18000c625`
- `KERNEL32!GetLastError` at `0x18000c691`
- `KERNEL32!GetLastError` at `0x18000c6fd`
- `KERNEL32!GetLastError` at `0x18000c5b8`
- `KERNEL32!GetLastError` at `0x18000c625`
- `KERNEL32!GetLastError` at `0x18000c691`
- `KERNEL32!GetLastError` at `0x18000c6fd`

## string_xrefs

- `0x18000c3b4`: `SRMPATHH`
- `0x18000c5f0`: `SRMPATHH`
- `0x18000c65c`: `SRMPATHH`
- `0x18000c6c8`: `SRMPATHH`
- `0x18000c734`: `SRMPATHH`
- `0x18000c783`: `SRMPATHH`
- `0x18000c7d0`: `SRMPATHH`
- `0x18000c39c`: `base\fs\fsrm\service\srmclient\exportimport.cpp`
- `0x18000c3a8`: `CExportImport::ReadXmlFromFile`
- `0x18000c5e9`: `CExportImport::ReadXmlFromFile`
- `0x18000c655`: `CExportImport::ReadXmlFromFile`
- `0x18000c6c1`: `CExportImport::ReadXmlFromFile`
- `0x18000c72d`: `CExportImport::ReadXmlFromFile`
- `0x18000c7c9`: `CExportImport::ReadXmlFromFile`
- `0x18000c67a`: `CreateFile for XML import file %s failed with %lu`
- `0x18000c6e6`: `GetFileSize for XML import file %s failed with %lu`
- `0x18000c60e`: `ReadFile for XML import file %s failed with %lu`
- `0x18000c752`: `ReadFile for XML import file %s failed with %lu`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CExportImport::ReadXmlFromFile(CExportImport *this, const unsigned __int16 *a2, BSTR *a3)
{
  HANDLE FileW; // rax
  void *v6; // rsi
  DWORD FileSize; // eax
  DWORD v8; // edi
  bool v9; // cf
  int v10; // eax
  DWORD v11; // edi
  BSTR v12; // rax
  OLECHAR *v13; // rbx
  signed int v14; // eax
  signed int v15; // ebx
  unsigned int v16; // edi
  __int64 v17; // rax
  signed int LastError; // eax
  signed int v19; // ebx
  unsigned int v20; // edi
  __int64 v21; // rax
  signed int v22; // eax
  signed int v23; // ebx
  unsigned int v24; // edi
  __int64 v25; // rax
  signed int v26; // eax
  signed int v27; // ebx
  unsigned int v28; // edi
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  __int64 dwFlagsAndAttributesa; // [rsp+28h] [rbp-D8h]
  __int64 dwFlagsAndAttributesb; // [rsp+28h] [rbp-D8h]
  __int64 dwFlagsAndAttributesc; // [rsp+28h] [rbp-D8h]
  __int16 Buffer; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-BCh] BYREF
  _QWORD *v38; // [rsp+48h] [rbp-B8h]
  void **v39; // [rsp+50h] [rbp-B0h]
  __int64 v40; // [rsp+58h] [rbp-A8h]
  _QWORD *v41; // [rsp+60h] [rbp-A0h]
  _QWORD v42[4]; // [rsp+68h] [rbp-98h] BYREF
  int v43; // [rsp+88h] [rbp-78h]
  _BYTE v44[96]; // [rsp+90h] [rbp-70h] BYREF
  int v45; // [rsp+F0h] [rbp-10h]
  _QWORD v46[22]; // [rsp+100h] [rbp+0h] BYREF

  v38 = v42;
  v42[0] = L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp";
  v42[1] = L"CExportImport::ReadXmlFromFile";
  v42[2] = L"SRMPATHH";
  v42[3] = 362;
  v43 = 255;
  v45 = 0x1000000;
  memset_0(v44, 0, sizeof(v44));
  CSrmFunctionTracer::CSrmFunctionTracer(v46, v42, 0);
  v40 = -1;
  v39 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  SysFreeString(*a3);
  *a3 = 0;
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v6 = FileW;
  v40 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v19 = LastError;
    if ( LastError > 0 )
      v20 = (unsigned __int16)LastError | 0x80070000;
    else
      v20 = LastError;
    v38 = v42;
    v21 = CSrmDebugInfo::CSrmDebugInfo(
            v42,
            L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
            L"SRMPATHH",
            L"CExportImport::ReadXmlFromFile",
            383,
            0);
    LODWORD(dwFlagsAndAttributesa) = v19;
    CSrmFunctionTracer::Throw(
      v46,
      v21,
      v20,
      L"CreateFile for XML import file %s failed with %lu",
      a2,
      dwFlagsAndAttributesa);
  }
  FileSize = GetFileSize(FileW, 0);
  v8 = FileSize;
  if ( FileSize == -1 )
  {
    v22 = GetLastError();
    v23 = v22;
    if ( v22 > 0 )
      v24 = (unsigned __int16)v22 | 0x80070000;
    else
      v24 = v22;
    v38 = v42;
    v25 = CSrmDebugInfo::CSrmDebugInfo(
            v42,
            L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
            L"SRMPATHH",
            L"CExportImport::ReadXmlFromFile",
            391,
            0);
    LODWORD(dwFlagsAndAttributesb) = v23;
    CSrmFunctionTracer::Throw(
      v46,
      v25,
      v24,
      L"GetFileSize for XML import file %s failed with %lu",
      a2,
      dwFlagsAndAttributesb);
  }
  if ( FileSize > 1 )
  {
    NumberOfBytesRead = 0;
    Buffer = 0;
    if ( !ReadFile(v6, &Buffer, 2u, &NumberOfBytesRead, 0) )
    {
      v26 = GetLastError();
      v27 = v26;
      if ( v26 > 0 )
        v28 = (unsigned __int16)v26 | 0x80070000;
      else
        v28 = v26;
      v38 = v42;
      v29 = CSrmDebugInfo::CSrmDebugInfo(
              v42,
              L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
              L"SRMPATHH",
              L"CExportImport::ReadXmlFromFile",
              402,
              0);
      LODWORD(dwFlagsAndAttributesc) = v27;
      CSrmFunctionTracer::Throw(
        v46,
        v29,
        v28,
        L"ReadFile for XML import file %s failed with %lu",
        a2,
        dwFlagsAndAttributesc);
    }
    v9 = 0;
    if ( (_BYTE)Buffer == 0xFF && (v9 = HIBYTE(Buffer) == 0xFF, HIBYTE(Buffer) == 0xFE) )
      v10 = 0;
    else
      v10 = v9 ? -1 : 1;
    if ( v10 )
    {
      v38 = v42;
      v30 = CSrmDebugInfo::CSrmDebugInfo(
              v42,
              L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
              L"SRMPATHH",
              L"CExportImport::ReadXmlFromFile",
              408,
              0);
      CSrmFunctionTracer::Throw(v46, v30, 2147767057LL, L"The file is not UNICODE.");
    }
    v11 = v8 - NumberOfBytesRead;
    v38 = 0;
    v12 = SysAllocStringLen(0, ((v11 + 1) >> 1) + 1);
    v13 = v12;
    if ( !v12 )
    {
      v41 = v42;
      v31 = CSrmDebugInfo::CSrmDebugInfo(
              v42,
              L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
              L"SRMPATHH",
              L"CExportImport::ReadXmlFromFile",
              429,
              0);
      CSrmFunctionTracer::ThrowOutOfMemory(v46, v31);
    }
    v38 = v12;
    NumberOfBytesRead = 0;
    if ( !ReadFile(v6, v12, v11, &NumberOfBytesRead, 0) )
    {
      v14 = GetLastError();
      v15 = v14;
      if ( v14 > 0 )
        v16 = (unsigned __int16)v14 | 0x80070000;
      else
        v16 = v14;
      v41 = v42;
      v17 = CSrmDebugInfo::CSrmDebugInfo(
              v42,
              L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
              L"SRMPATHH",
              L"CExportImport::ReadXmlFromFile",
              438,
              0);
      LODWORD(dwFlagsAndAttributes) = v15;
      CSrmFunctionTracer::Throw(
        v46,
        v17,
        v16,
        L"ReadFile for XML import file %s failed with %lu",
        a2,
        dwFlagsAndAttributes);
    }
    *(OLECHAR *)((char *)v13 + (NumberOfBytesRead & 0xFFFFFFFE)) = 0;
    v38 = 0;
    *a3 = v13;
    SysFreeString(0);
  }
  v39 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  CloseHandle(v6);
  v39 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
  v40 = -1;
  v46[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v46);
}

```

## disassembly

```asm
0x18000c35c  mov     [rsp-8+arg_0], rbx
0x18000c361  push    rbp
0x18000c362  push    rsi
0x18000c363  push    rdi
0x18000c364  push    r12
0x18000c366  push    r13
0x18000c368  push    r14
0x18000c36a  push    r15
0x18000c36c  lea     rbp, [rsp-0C0h]
0x18000c374  sub     rsp, 1C0h
0x18000c37b  mov     rax, cs:__security_cookie
0x18000c382  xor     rax, rsp
0x18000c385  mov     [rbp+0F0h+var_40], rax
0x18000c38c  mov     r15, r8
0x18000c38f  mov     r14, rdx
0x18000c392  lea     rax, [rsp+1F0h+var_188]
0x18000c397  mov     [rsp+1F0h+var_1A8], rax
0x18000c39c  lea     r13, aBaseFsFsrmServ_0; "base\\fs\\fsrm\\service\\srmclient\\exp"...
0x18000c3a3  mov     [rsp+1F0h+var_188], r13
0x18000c3a8  lea     rbx, aCexportimportR; "CExportImport::ReadXmlFromFile"
0x18000c3af  mov     [rsp+1F0h+var_180], rbx
0x18000c3b4  lea     rax, aSrmpathh; "SRMPATHH"
0x18000c3bb  mov     [rsp+1F0h+var_178], rax
0x18000c3c0  mov     [rbp+0F0h+var_170], 16Ah
0x18000c3c8  xor     r12d, r12d
0x18000c3cb  mov     [rbp+0F0h+var_168], 0FFh
0x18000c3d2  mov     [rbp+0F0h+var_100], 1000000h
0x18000c3d9  xor     edx, edx; Val
0x18000c3db  lea     r8d, [r12+60h]; Size
0x18000c3e0  lea     rcx, [rbp+0F0h+var_160]; void *
0x18000c3e4  call    memset_0
0x18000c3e9  nop
0x18000c3ea  xor     r8d, r8d
0x18000c3ed  lea     rdx, [rsp+1F0h+var_188]
0x18000c3f2  lea     rcx, [rbp+0F0h+var_F0]
0x18000c3f6  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18000c3fb  nop
0x18000c3fc  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18000c403  mov     [rsp+1F0h+var_1A0], rax
0x18000c408  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000c40c  mov     [rsp+1F0h+var_198], rdi
0x18000c411  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18000c418  mov     [rsp+1F0h+var_1A0], rax
0x18000c41d  mov     rcx, [r15]; bstrString
0x18000c420  call    cs:__imp_SysFreeString
0x18000c426  mov     [r15], r12
0x18000c429  mov     [rsp+1F0h+hTemplateFile], r12; hTemplateFile
0x18000c42e  mov     dword ptr [rsp+1F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000c436  mov     [rsp+1F0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000c43e  xor     r9d, r9d; lpSecurityAttributes
0x18000c441  mov     edx, 80000000h; dwDesiredAccess
0x18000c446  lea     r8d, [r12+1]; dwShareMode
0x18000c44b  mov     rcx, r14; lpFileName
0x18000c44e  call    cs:__imp_CreateFileW
0x18000c454  mov     rsi, rax
0x18000c457  mov     [rsp+1F0h+var_198], rdi
0x18000c45c  mov     [rsp+1F0h+var_198], rax
0x18000c461  cmp     rax, rdi
0x18000c464  jz      loc_18000C625
0x18000c46a  xor     edx, edx; lpFileSizeHigh
0x18000c46c  mov     rcx, rax; hFile
0x18000c46f  call    cs:__imp_GetFileSize
0x18000c475  mov     edi, eax
0x18000c477  cmp     eax, 0FFFFFFFFh
0x18000c47a  jz      loc_18000C691
0x18000c480  cmp     eax, 1
0x18000c483  jbe     loc_18000C54B
0x18000c489  mov     [rsp+1F0h+NumberOfBytesRead], r12d
0x18000c48e  mov     [rsp+1F0h+Buffer], r12w
0x18000c494  mov     qword ptr [rsp+1F0h+dwCreationDisposition], r12; lpOverlapped
0x18000c499  lea     r9, [rsp+1F0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000c49e  lea     r8d, [r12+2]; nNumberOfBytesToRead
0x18000c4a3  lea     rdx, [rsp+1F0h+Buffer]; lpBuffer
0x18000c4a8  mov     rcx, rsi; hFile
0x18000c4ab  call    cs:__imp_ReadFile
0x18000c4b1  test    eax, eax
0x18000c4b3  jz      loc_18000C6FD
0x18000c4b9  mov     al, 0FEh
0x18000c4bb  mov     ecx, 0FFh
0x18000c4c0  cmp     cl, byte ptr [rsp+1F0h+Buffer]
0x18000c4c4  jnz     short loc_18000C4D1
0x18000c4c6  cmp     al, byte ptr [rsp+1F0h+Buffer+1]
0x18000c4ca  jnz     short loc_18000C4D1
0x18000c4cc  mov     eax, r12d
0x18000c4cf  jmp     short loc_18000C4D6
0x18000c4d1  sbb     eax, eax
0x18000c4d3  or      eax, 1
0x18000c4d6  test    eax, eax
0x18000c4d8  jnz     loc_18000C769
0x18000c4de  sub     edi, [rsp+1F0h+NumberOfBytesRead]
0x18000c4e2  mov     [rsp+1F0h+var_1A8], r12
0x18000c4e7  lea     edx, [rdi+1]
0x18000c4ea  shr     edx, 1
0x18000c4ec  inc     edx; ui
0x18000c4ee  xor     ecx, ecx; strIn
0x18000c4f0  call    cs:__imp_SysAllocStringLen
0x18000c4f6  mov     rbx, rax
0x18000c4f9  test    rax, rax
0x18000c4fc  jz      loc_18000C7B2
0x18000c502  mov     [rsp+1F0h+var_1A8], rax
0x18000c507  mov     [rsp+1F0h+NumberOfBytesRead], r12d
0x18000c50c  mov     qword ptr [rsp+1F0h+dwCreationDisposition], r12; lpOverlapped
0x18000c511  lea     r9, [rsp+1F0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000c516  mov     r8d, edi; nNumberOfBytesToRead
0x18000c519  mov     rdx, rax; lpBuffer
0x18000c51c  mov     rcx, rsi; hFile
0x18000c51f  call    cs:__imp_ReadFile
0x18000c525  test    eax, eax
0x18000c527  jz      loc_18000C5B8
0x18000c52d  mov     edx, [rsp+1F0h+NumberOfBytesRead]
0x18000c531  and     rdx, 0FFFFFFFFFFFFFFFEh
0x18000c535  mov     [rdx+rbx], r12w
0x18000c53a  mov     [rsp+1F0h+var_1A8], r12
0x18000c53f  mov     [r15], rbx
0x18000c542  xor     ecx, ecx; bstrString
0x18000c544  call    cs:__imp_SysFreeString
0x18000c54a  nop
0x18000c54b  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18000c552  mov     [rsp+1F0h+var_1A0], rax
0x18000c557  mov     rcx, rsi; hObject
0x18000c55a  call    cs:__imp_CloseHandle
0x18000c560  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c564  mov     [rsp+1F0h+var_198], rax
0x18000c569  lea     rcx, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18000c570  mov     [rsp+1F0h+var_1A0], rcx
0x18000c575  mov     [rsp+1F0h+var_198], rax
0x18000c57a  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18000c581  mov     [rbp+0F0h+var_F0], rax
0x18000c585  lea     rcx, [rbp+0F0h+var_F0]; this
0x18000c589  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18000c58e  mov     rcx, [rbp+0F0h+var_40]
0x18000c595  xor     rcx, rsp; StackCookie
0x18000c598  call    __security_check_cookie
0x18000c59d  mov     rbx, [rsp+1F0h+arg_0]
0x18000c5a5  add     rsp, 1C0h
0x18000c5ac  pop     r15
0x18000c5ae  pop     r14
0x18000c5b0  pop     r13
0x18000c5b2  pop     r12
0x18000c5b4  pop     rdi
0x18000c5b5  pop     rsi
0x18000c5b6  pop     rbp
0x18000c5b7  retn
0x18000c5b8  call    cs:__imp_GetLastError
0x18000c5be  nop
0x18000c5bf  mov     ebx, eax
0x18000c5c1  test    eax, eax
0x18000c5c3  jg      short loc_18000C5C9
0x18000c5c5  mov     edi, eax
0x18000c5c7  jmp     short loc_18000C5D2
0x18000c5c9  movzx   edi, bx
0x18000c5cc  or      edi, 80070000h
0x18000c5d2  lea     rax, [rsp+1F0h+var_188]
0x18000c5d7  mov     [rsp+1F0h+var_190], rax
0x18000c5dc  mov     dword ptr [rsp+1F0h+dwFlagsAndAttributes], r12d
0x18000c5e1  mov     [rsp+1F0h+dwCreationDisposition], 1B6h
0x18000c5e9  lea     r9, aCexportimportR; "CExportImport::ReadXmlFromFile"
0x18000c5f0  lea     r8, aSrmpathh; "SRMPATHH"
0x18000c5f7  mov     rdx, r13
0x18000c5fa  lea     rcx, [rsp+1F0h+var_188]
0x18000c5ff  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000c604  nop
0x18000c605  mov     dword ptr [rsp+1F0h+dwFlagsAndAttributes], ebx
0x18000c609  mov     qword ptr [rsp+1F0h+dwCreationDisposition], r14
0x18000c60e  lea     r9, aReadfileForXml; "ReadFile for XML import file %s failed "...
0x18000c615  mov     r8d, edi
0x18000c618  mov     rdx, rax
0x18000c61b  lea     rcx, [rbp+0F0h+var_F0]
0x18000c61f  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18000c625  call    cs:__imp_GetLastError
0x18000c62b  mov     ebx, eax
0x18000c62d  test    eax, eax
0x18000c62f  jg      short loc_18000C635
0x18000c631  mov     edi, eax
0x18000c633  jmp     short loc_18000C63E
0x18000c635  movzx   edi, bx
0x18000c638  or      edi, 80070000h
0x18000c63e  lea     rax, [rsp+1F0h+var_188]
0x18000c643  mov     [rsp+1F0h+var_1A8], rax
0x18000c648  mov     dword ptr [rsp+1F0h+dwFlagsAndAttributes], r12d
0x18000c64d  mov     [rsp+1F0h+dwCreationDisposition], 17Fh
0x18000c655  lea     r9, aCexportimportR; "CExportImport::ReadXmlFromFile"
0x18000c65c  lea     r8, aSrmpathh; "SRMPATHH"
0x18000c663  mov     rdx, r13
0x18000c666  lea     rcx, [rsp+1F0h+var_188]
0x18000c66b  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000c670  nop
0x18000c671  mov     dword ptr [rsp+1F0h+dwFlagsAndAttributes], ebx
0x18000c675  mov     qword ptr [rsp+1F0h+dwCreationDisposition], r14
0x18000c67a  lea     r9, aCreatefileForX; "CreateFile for XML import file %s faile"...
0x18000c681  mov     r8d, edi
0x18000c684  mov     rdx, rax
0x18000c687  lea     rcx, [rbp+0F0h+var_F0]
0x18000c68b  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18000c691  call    cs:__imp_GetLastError
0x18000c697  mov     ebx, eax
0x18000c699  test    eax, eax
0x18000c69b  jg      short loc_18000C6A1
0x18000c69d  mov     edi, eax
0x18000c69f  jmp     short loc_18000C6AA
0x18000c6a1  movzx   edi, bx
0x18000c6a4  or      edi, 80070000h
0x18000c6aa  lea     rax, [rsp+1F0h+var_188]
0x18000c6af  mov     [rsp+1F0h+var_1A8], rax
0x18000c6b4  mov     dword ptr [rsp+1F0h+dwFlagsAndAttributes], r12d
0x18000c6b9  mov     [rsp+1F0h+dwCreationDisposition], 187h
0x18000c6c1  lea     r9, aCexportimportR; "CExportImport::ReadXmlFromFile"
0x18000c6c8  lea     r8, aSrmpathh; "SRMPATHH"
0x18000c6cf  mov     rdx, r13
0x18000c6d2  lea     rcx, [rsp+1F0h+var_188]
0x18000c6d7  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000c6dc  nop
0x18000c6dd  mov     dword ptr [rsp+1F0h+dwFlagsAndAttributes], ebx
0x18000c6e1  mov     qword ptr [rsp+1F0h+dwCreationDisposition], r14
0x18000c6e6  lea     r9, aGetfilesizeFor; "GetFileSize for XML import file %s fail"...
0x18000c6ed  mov     r8d, edi
0x18000c6f0  mov     rdx, rax
0x18000c6f3  lea     rcx, [rbp+0F0h+var_F0]
0x18000c6f7  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18000c6fd  call    cs:__imp_GetLastError
0x18000c703  mov     ebx, eax
0x18000c705  test    eax, eax
0x18000c707  jg      short loc_18000C70D
0x18000c709  mov     edi, eax
0x18000c70b  jmp     short loc_18000C716
0x18000c70d  movzx   edi, bx
0x18000c710  or      edi, 80070000h
0x18000c716  lea     rax, [rsp+1F0h+var_188]
0x18000c71b  mov     [rsp+1F0h+var_1A8], rax
0x18000c720  mov     dword ptr [rsp+1F0h+dwFlagsAndAttributes], r12d
0x18000c725  mov     [rsp+1F0h+dwCreationDisposition], 192h
0x18000c72d  lea     r9, aCexportimportR; "CExportImport::ReadXmlFromFile"
0x18000c734  lea     r8, aSrmpathh; "SRMPATHH"
0x18000c73b  mov     rdx, r13
0x18000c73e  lea     rcx, [rsp+1F0h+var_188]
0x18000c743  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000c748  nop
0x18000c749  mov     dword ptr [rsp+1F0h+dwFlagsAndAttributes], ebx
0x18000c74d  mov     qword ptr [rsp+1F0h+dwCreationDisposition], r14
0x18000c752  lea     r9, aReadfileForXml; "ReadFile for XML import file %s failed "...
0x18000c759  mov     r8d, edi
0x18000c75c  mov     rdx, rax
0x18000c75f  lea     rcx, [rbp+0F0h+var_F0]
0x18000c763  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18000c769  lea     rax, [rsp+1F0h+var_188]
0x18000c76e  mov     [rsp+1F0h+var_1A8], rax
0x18000c773  mov     dword ptr [rsp+1F0h+dwFlagsAndAttributes], r12d
0x18000c778  mov     [rsp+1F0h+dwCreationDisposition], 198h
0x18000c780  mov     r9, rbx
0x18000c783  lea     r8, aSrmpathh; "SRMPATHH"
0x18000c78a  mov     rdx, r13
0x18000c78d  lea     rcx, [rsp+1F0h+var_188]
0x18000c792  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000c797  nop
0x18000c798  lea     r9, aTheFileIsNotUn; "The file is not UNICODE."
0x18000c79f  mov     r8d, 80045311h
0x18000c7a5  mov     rdx, rax
0x18000c7a8  lea     rcx, [rbp+0F0h+var_F0]
0x18000c7ac  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18000c7b2  lea     rax, [rsp+1F0h+var_188]
0x18000c7b7  mov     [rsp+1F0h+var_190], rax
0x18000c7bc  mov     dword ptr [rsp+1F0h+dwFlagsAndAttributes], r12d
0x18000c7c1  mov     [rsp+1F0h+dwCreationDisposition], 1ADh
0x18000c7c9  lea     r9, aCexportimportR; "CExportImport::ReadXmlFromFile"
0x18000c7d0  lea     r8, aSrmpathh; "SRMPATHH"
0x18000c7d7  mov     rdx, r13
0x18000c7da  lea     rcx, [rsp+1F0h+var_188]
0x18000c7df  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000c7e4  nop
0x18000c7e5  mov     rdx, rax
0x18000c7e8  lea     rcx, [rbp+0F0h+var_F0]
0x18000c7ec  call    ?ThrowOutOfMemory@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@@Z; CSrmFunctionTracer::ThrowOutOfMemory(CSrmDebugInfo)
```

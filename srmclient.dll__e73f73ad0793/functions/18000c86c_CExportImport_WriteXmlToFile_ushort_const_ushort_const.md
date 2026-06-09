# CExportImport::WriteXmlToFile(ushort const *,ushort const *)

- ea: `0x18000c86c`
- end: `0x18000cbe1`
- name: `?WriteXmlToFile@CExportImport@@AEAAXPEBG0@Z`
- size: `885`
- prototype: `void __fastcall(CExportImport *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18000b3a0`
- `0x18000b5e0`
- `0x18000b820`

## callees

- `0x18000c86c`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18000c99f`
- `KERNEL32!WriteFile` at `0x18000c9cd`
- `KERNEL32!WriteFile` at `0x18000c99f`
- `KERNEL32!WriteFile` at `0x18000c9cd`
- `KERNEL32!SetEndOfFile` at `0x18000c96f`
- `KERNEL32!SetEndOfFile` at `0x18000c96f`
- `KERNEL32!CreateFileW` at `0x18000c950`
- `KERNEL32!CreateFileW` at `0x18000c950`
- `KERNEL32!CloseHandle` at `0x18000c9e6`
- `KERNEL32!CloseHandle` at `0x18000c9e6`
- `KERNEL32!GetLastError` at `0x18000ca40`
- `KERNEL32!GetLastError` at `0x18000caa9`
- `KERNEL32!GetLastError` at `0x18000cb11`
- `KERNEL32!GetLastError` at `0x18000cb79`
- `KERNEL32!GetLastError` at `0x18000ca40`
- `KERNEL32!GetLastError` at `0x18000caa9`
- `KERNEL32!GetLastError` at `0x18000cb11`
- `KERNEL32!GetLastError` at `0x18000cb79`

## string_xrefs

- `0x18000c8c4`: `SRMPATHH`
- `0x18000ca74`: `SRMPATHH`
- `0x18000cadc`: `SRMPATHH`
- `0x18000cb44`: `SRMPATHH`
- `0x18000cbac`: `SRMPATHH`
- `0x18000c8ac`: `base\fs\fsrm\service\srmclient\exportimport.cpp`
- `0x18000c8b8`: `CExportImport::WriteXmlToFile`
- `0x18000cafa`: `CreateFile for XML export file %s failed with %lu`
- `0x18000cb62`: `SetEndOfFile for XML export file %s failed with %lu`
- `0x18000cbca`: `WriteFile of BOM to XML export file %s failed with %lu`
- `0x18000ca92`: `WriteFile of XML to export file %s failed with %lu`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CExportImport::WriteXmlToFile(
        CExportImport *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HANDLE FileW; // rax
  void *v6; // rbx
  __int64 v7; // r8
  signed int v8; // eax
  signed int v9; // ebx
  unsigned int v10; // edi
  __int64 v11; // rax
  signed int LastError; // eax
  signed int v13; // ebx
  unsigned int v14; // edi
  __int64 v15; // rax
  signed int v16; // eax
  signed int v17; // ebx
  unsigned int v18; // edi
  __int64 v19; // rax
  signed int v20; // eax
  signed int v21; // ebx
  unsigned int v22; // edi
  __int64 v23; // rax
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  __int64 dwFlagsAndAttributesa; // [rsp+28h] [rbp-D8h]
  __int64 dwFlagsAndAttributesb; // [rsp+28h] [rbp-D8h]
  __int64 dwFlagsAndAttributesc; // [rsp+28h] [rbp-D8h]
  __int16 Buffer[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-BCh] BYREF
  _QWORD *v30; // [rsp+48h] [rbp-B8h]
  void **v31; // [rsp+50h] [rbp-B0h]
  __int64 v32; // [rsp+58h] [rbp-A8h]
  _QWORD v33[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+80h] [rbp-80h]
  _BYTE v35[96]; // [rsp+88h] [rbp-78h] BYREF
  int v36; // [rsp+E8h] [rbp-18h]
  _QWORD v37[22]; // [rsp+F0h] [rbp-10h] BYREF

  v30 = v33;
  v33[0] = L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp";
  v33[1] = L"CExportImport::WriteXmlToFile";
  v33[2] = L"SRMPATHH";
  v33[3] = 454;
  v34 = 255;
  v36 = 0x1000000;
  memset_0(v35, 0, sizeof(v35));
  CSrmFunctionTracer::CSrmFunctionTracer(v37, v33, 0);
  v31 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  FileW = CreateFileW(a2, 0x40000000u, 1u, 0, 1u, 0x80u, 0);
  v6 = FileW;
  v32 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    else
      v14 = LastError;
    v30 = v33;
    v15 = CSrmDebugInfo::CSrmDebugInfo(
            v33,
            L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
            L"SRMPATHH",
            L"CExportImport::WriteXmlToFile",
            473,
            0);
    LODWORD(dwFlagsAndAttributesa) = v13;
    CSrmFunctionTracer::Throw(
      v37,
      v15,
      v14,
      L"CreateFile for XML export file %s failed with %lu",
      a2,
      dwFlagsAndAttributesa);
  }
  if ( !SetEndOfFile(FileW) )
  {
    v16 = GetLastError();
    v17 = v16;
    if ( v16 > 0 )
      v18 = (unsigned __int16)v16 | 0x80070000;
    else
      v18 = v16;
    v30 = v33;
    v19 = CSrmDebugInfo::CSrmDebugInfo(
            v33,
            L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
            L"SRMPATHH",
            L"CExportImport::WriteXmlToFile",
            480,
            0);
    LODWORD(dwFlagsAndAttributesb) = v17;
    CSrmFunctionTracer::Throw(
      v37,
      v19,
      v18,
      L"SetEndOfFile for XML export file %s failed with %lu",
      a2,
      dwFlagsAndAttributesb);
  }
  Buffer[0] = -257;
  NumberOfBytesWritten = 0;
  if ( !WriteFile(v6, Buffer, 2u, &NumberOfBytesWritten, 0) )
  {
    v20 = GetLastError();
    v21 = v20;
    if ( v20 > 0 )
      v22 = (unsigned __int16)v20 | 0x80070000;
    else
      v22 = v20;
    v30 = v33;
    v23 = CSrmDebugInfo::CSrmDebugInfo(
            v33,
            L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
            L"SRMPATHH",
            L"CExportImport::WriteXmlToFile",
            490,
            0);
    LODWORD(dwFlagsAndAttributesc) = v21;
    CSrmFunctionTracer::Throw(
      v37,
      v23,
      v22,
      L"WriteFile of BOM to XML export file %s failed with %lu",
      a2,
      dwFlagsAndAttributesc);
  }
  v7 = -1;
  do
    ++v7;
  while ( a3[v7] );
  if ( !WriteFile(v6, a3, 2 * v7, &NumberOfBytesWritten, 0) )
  {
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v10 = (unsigned __int16)v8 | 0x80070000;
    else
      v10 = v8;
    v30 = v33;
    v11 = CSrmDebugInfo::CSrmDebugInfo(
            v33,
            L"base\\fs\\fsrm\\service\\srmclient\\exportimport.cpp",
            L"SRMPATHH",
            L"CExportImport::WriteXmlToFile",
            499,
            0);
    LODWORD(dwFlagsAndAttributes) = v9;
    CSrmFunctionTracer::Throw(
      v37,
      v11,
      v10,
      L"WriteFile of XML to export file %s failed with %lu",
      a2,
      dwFlagsAndAttributes);
  }
  v31 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  CloseHandle(v6);
  v31 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
  v32 = -1;
  v37[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v37);
}

```

## disassembly

```asm
0x18000c86c  mov     [rsp-8+arg_0], rbx
0x18000c871  push    rbp
0x18000c872  push    rsi
0x18000c873  push    rdi
0x18000c874  push    r12
0x18000c876  push    r13
0x18000c878  push    r14
0x18000c87a  push    r15
0x18000c87c  lea     rbp, [rsp-0B0h]
0x18000c884  sub     rsp, 1B0h
0x18000c88b  mov     rax, cs:__security_cookie
0x18000c892  xor     rax, rsp
0x18000c895  mov     [rbp+0E0h+var_40], rax
0x18000c89c  mov     rdi, r8
0x18000c89f  mov     rsi, rdx
0x18000c8a2  lea     rax, [rsp+1E0h+var_180]
0x18000c8a7  mov     [rsp+1E0h+var_198], rax
0x18000c8ac  lea     r12, aBaseFsFsrmServ_0; "base\\fs\\fsrm\\service\\srmclient\\exp"...
0x18000c8b3  mov     [rsp+1E0h+var_180], r12
0x18000c8b8  lea     r13, aCexportimportW; "CExportImport::WriteXmlToFile"
0x18000c8bf  mov     [rsp+1E0h+var_178], r13
0x18000c8c4  lea     rax, aSrmpathh; "SRMPATHH"
0x18000c8cb  mov     [rsp+1E0h+var_170], rax
0x18000c8d0  mov     [rsp+1E0h+var_168], 1C6h
0x18000c8d9  xor     r14d, r14d
0x18000c8dc  mov     [rbp+0E0h+var_160], 0FFh
0x18000c8e3  mov     [rbp+0E0h+var_F8], 1000000h
0x18000c8ea  lea     ebx, [r14+1]
0x18000c8ee  xor     edx, edx; Val
0x18000c8f0  lea     r8d, [r14+60h]; Size
0x18000c8f4  lea     rcx, [rbp+0E0h+var_158]; void *
0x18000c8f8  call    memset_0
0x18000c8fd  nop
0x18000c8fe  xor     r8d, r8d
0x18000c901  lea     rdx, [rsp+1E0h+var_180]
0x18000c906  lea     rcx, [rbp+0E0h+var_F0]
0x18000c90a  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18000c90f  nop
0x18000c910  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18000c917  mov     [rsp+1E0h+var_190], rax
0x18000c91c  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000c920  mov     [rsp+1E0h+var_188], r15
0x18000c925  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18000c92c  mov     [rsp+1E0h+var_190], rax
0x18000c931  mov     [rsp+1E0h+hTemplateFile], r14; hTemplateFile
0x18000c936  mov     dword ptr [rsp+1E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000c93e  mov     [rsp+1E0h+dwCreationDisposition], ebx; dwCreationDisposition
0x18000c942  xor     r9d, r9d; lpSecurityAttributes
0x18000c945  mov     r8d, ebx; dwShareMode
0x18000c948  mov     edx, 40000000h; dwDesiredAccess
0x18000c94d  mov     rcx, rsi; lpFileName
0x18000c950  call    cs:__imp_CreateFileW
0x18000c956  mov     rbx, rax
0x18000c959  mov     [rsp+1E0h+var_188], r15
0x18000c95e  mov     [rsp+1E0h+var_188], rax
0x18000c963  cmp     rax, r15
0x18000c966  jz      loc_18000CAA9
0x18000c96c  mov     rcx, rax; hFile
0x18000c96f  call    cs:__imp_SetEndOfFile
0x18000c975  test    eax, eax
0x18000c977  jz      loc_18000CB11
0x18000c97d  mov     [rsp+1E0h+Buffer], 0FEFFh
0x18000c984  mov     [rsp+1E0h+NumberOfBytesWritten], r14d
0x18000c989  mov     qword ptr [rsp+1E0h+dwCreationDisposition], r14; lpOverlapped
0x18000c98e  lea     r9, [rsp+1E0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000c993  lea     r8d, [r14+2]; nNumberOfBytesToWrite
0x18000c997  lea     rdx, [rsp+1E0h+Buffer]; lpBuffer
0x18000c99c  mov     rcx, rbx; hFile
0x18000c99f  call    cs:__imp_WriteFile
0x18000c9a5  test    eax, eax
0x18000c9a7  jz      loc_18000CB79
0x18000c9ad  mov     r8, r15
0x18000c9b0  inc     r8
0x18000c9b3  cmp     [rdi+r8*2], r14w
0x18000c9b8  jnz     short loc_18000C9B0
0x18000c9ba  add     r8d, r8d; nNumberOfBytesToWrite
0x18000c9bd  mov     qword ptr [rsp+1E0h+dwCreationDisposition], r14; lpOverlapped
0x18000c9c2  lea     r9, [rsp+1E0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000c9c7  mov     rdx, rdi; lpBuffer
0x18000c9ca  mov     rcx, rbx; hFile
0x18000c9cd  call    cs:__imp_WriteFile
0x18000c9d3  test    eax, eax
0x18000c9d5  jz      short loc_18000CA40
0x18000c9d7  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18000c9de  mov     [rsp+1E0h+var_190], rax
0x18000c9e3  mov     rcx, rbx; hObject
0x18000c9e6  call    cs:__imp_CloseHandle
0x18000c9ec  mov     [rsp+1E0h+var_188], r15
0x18000c9f1  lea     rax, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x18000c9f8  mov     [rsp+1E0h+var_190], rax
0x18000c9fd  mov     [rsp+1E0h+var_188], r15
0x18000ca02  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18000ca09  mov     [rbp+0E0h+var_F0], rax
0x18000ca0d  lea     rcx, [rbp+0E0h+var_F0]; this
0x18000ca11  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18000ca16  mov     rcx, [rbp+0E0h+var_40]
0x18000ca1d  xor     rcx, rsp; StackCookie
0x18000ca20  call    __security_check_cookie
0x18000ca25  mov     rbx, [rsp+1E0h+arg_0]
0x18000ca2d  add     rsp, 1B0h
0x18000ca34  pop     r15
0x18000ca36  pop     r14
0x18000ca38  pop     r13
0x18000ca3a  pop     r12
0x18000ca3c  pop     rdi
0x18000ca3d  pop     rsi
0x18000ca3e  pop     rbp
0x18000ca3f  retn
0x18000ca40  call    cs:__imp_GetLastError
0x18000ca46  nop
0x18000ca47  mov     ebx, eax
0x18000ca49  test    eax, eax
0x18000ca4b  jg      short loc_18000CA51
0x18000ca4d  mov     edi, eax
0x18000ca4f  jmp     short loc_18000CA5A
0x18000ca51  movzx   edi, bx
0x18000ca54  or      edi, 80070000h
0x18000ca5a  lea     rax, [rsp+1E0h+var_180]
0x18000ca5f  mov     [rsp+1E0h+var_198], rax
0x18000ca64  mov     dword ptr [rsp+1E0h+dwFlagsAndAttributes], r14d
0x18000ca69  mov     [rsp+1E0h+dwCreationDisposition], 1F3h
0x18000ca71  mov     r9, r13
0x18000ca74  lea     r8, aSrmpathh; "SRMPATHH"
0x18000ca7b  mov     rdx, r12
0x18000ca7e  lea     rcx, [rsp+1E0h+var_180]
0x18000ca83  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000ca88  nop
0x18000ca89  mov     dword ptr [rsp+1E0h+dwFlagsAndAttributes], ebx
0x18000ca8d  mov     qword ptr [rsp+1E0h+dwCreationDisposition], rsi
0x18000ca92  lea     r9, aWritefileOfXml; "WriteFile of XML to export file %s fail"...
0x18000ca99  mov     r8d, edi
0x18000ca9c  mov     rdx, rax
0x18000ca9f  lea     rcx, [rbp+0E0h+var_F0]
0x18000caa3  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18000caa9  call    cs:__imp_GetLastError
0x18000caaf  mov     ebx, eax
0x18000cab1  test    eax, eax
0x18000cab3  jg      short loc_18000CAB9
0x18000cab5  mov     edi, eax
0x18000cab7  jmp     short loc_18000CAC2
0x18000cab9  movzx   edi, bx
0x18000cabc  or      edi, 80070000h
0x18000cac2  lea     rax, [rsp+1E0h+var_180]
0x18000cac7  mov     [rsp+1E0h+var_198], rax
0x18000cacc  mov     dword ptr [rsp+1E0h+dwFlagsAndAttributes], r14d
0x18000cad1  mov     [rsp+1E0h+dwCreationDisposition], 1D9h
0x18000cad9  mov     r9, r13
0x18000cadc  lea     r8, aSrmpathh; "SRMPATHH"
0x18000cae3  mov     rdx, r12
0x18000cae6  lea     rcx, [rsp+1E0h+var_180]
0x18000caeb  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000caf0  nop
0x18000caf1  mov     dword ptr [rsp+1E0h+dwFlagsAndAttributes], ebx
0x18000caf5  mov     qword ptr [rsp+1E0h+dwCreationDisposition], rsi
0x18000cafa  lea     r9, aCreatefileForX_0; "CreateFile for XML export file %s faile"...
0x18000cb01  mov     r8d, edi
0x18000cb04  mov     rdx, rax
0x18000cb07  lea     rcx, [rbp+0E0h+var_F0]
0x18000cb0b  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18000cb11  call    cs:__imp_GetLastError
0x18000cb17  mov     ebx, eax
0x18000cb19  test    eax, eax
0x18000cb1b  jg      short loc_18000CB21
0x18000cb1d  mov     edi, eax
0x18000cb1f  jmp     short loc_18000CB2A
0x18000cb21  movzx   edi, bx
0x18000cb24  or      edi, 80070000h
0x18000cb2a  lea     rax, [rsp+1E0h+var_180]
0x18000cb2f  mov     [rsp+1E0h+var_198], rax
0x18000cb34  mov     dword ptr [rsp+1E0h+dwFlagsAndAttributes], r14d
0x18000cb39  mov     [rsp+1E0h+dwCreationDisposition], 1E0h
0x18000cb41  mov     r9, r13
0x18000cb44  lea     r8, aSrmpathh; "SRMPATHH"
0x18000cb4b  mov     rdx, r12
0x18000cb4e  lea     rcx, [rsp+1E0h+var_180]
0x18000cb53  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000cb58  nop
0x18000cb59  mov     dword ptr [rsp+1E0h+dwFlagsAndAttributes], ebx
0x18000cb5d  mov     qword ptr [rsp+1E0h+dwCreationDisposition], rsi
0x18000cb62  lea     r9, aSetendoffileFo; "SetEndOfFile for XML export file %s fai"...
0x18000cb69  mov     r8d, edi
0x18000cb6c  mov     rdx, rax
0x18000cb6f  lea     rcx, [rbp+0E0h+var_F0]
0x18000cb73  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18000cb79  call    cs:__imp_GetLastError
0x18000cb7f  mov     ebx, eax
0x18000cb81  test    eax, eax
0x18000cb83  jg      short loc_18000CB89
0x18000cb85  mov     edi, eax
0x18000cb87  jmp     short loc_18000CB92
0x18000cb89  movzx   edi, bx
0x18000cb8c  or      edi, 80070000h
0x18000cb92  lea     rax, [rsp+1E0h+var_180]
0x18000cb97  mov     [rsp+1E0h+var_198], rax
0x18000cb9c  mov     dword ptr [rsp+1E0h+dwFlagsAndAttributes], r14d
0x18000cba1  mov     [rsp+1E0h+dwCreationDisposition], 1EAh
0x18000cba9  mov     r9, r13
0x18000cbac  lea     r8, aSrmpathh; "SRMPATHH"
0x18000cbb3  mov     rdx, r12
0x18000cbb6  lea     rcx, [rsp+1E0h+var_180]
0x18000cbbb  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18000cbc0  nop
0x18000cbc1  mov     dword ptr [rsp+1E0h+dwFlagsAndAttributes], ebx
0x18000cbc5  mov     qword ptr [rsp+1E0h+dwCreationDisposition], rsi
0x18000cbca  lea     r9, aWritefileOfBom; "WriteFile of BOM to XML export file %s "...
0x18000cbd1  mov     r8d, edi
0x18000cbd4  mov     rdx, rax
0x18000cbd7  lea     rcx, [rbp+0E0h+var_F0]
0x18000cbdb  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```

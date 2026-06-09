# CProcessDump::Initialize(CReportHandleInstance *,CReport *,void *,void *,_WER_DUMP_TYPE,ulong,_WER_EXCEPTION_INFORMATION * const,void * const,ulong)

- ea: `0x180084fdc`
- end: `0x1800856d8`
- name: `?Initialize@CProcessDump@@QEAAJPEAVCReportHandleInstance@@PEAVCReport@@PEAX2W4_WER_DUMP_TYPE@@KQEAU_WER_EXCEPTION_INFORMATION@@QEAXK@Z`
- size: `1788`
- prototype: `__int64 __usercall@<rax>(CProcessDump *__hidden this@<rcx>, struct CReportHandleInstance *@<rdx>, struct CReport *@<r8>, void *@<r9>, void *, enum _WER_DUMP_TYPE, unsigned int, struct _WER_EXCEPTION_INFORMATION *const, void *const, unsigned int)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180073964`
- `0x1800856e0`

## callees

- `0x180008004`
- `0x18000da00`
- `0x18001c368`
- `0x18002a0f4`
- `0x18002c5bc`
- `0x18002d930`
- `0x180030524`
- `0x180043f30`
- `0x18004b78c`
- `0x180053300`
- `0x180053d3c`
- `0x180054514`
- `0x180084fdc`
- `0x1800857c4`
- `0x180085964`
- `0x18009d26c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180085324`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180085333`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800853a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800853b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180085324`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180085333`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800853a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800853b0`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180085407`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180085407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085377`
- `ntdll!NtQueryInformationProcess` at `0x180085513`
- `ntdll!NtQueryInformationProcess` at `0x180085513`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerGetFlags` at `0x180085605`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerGetFlags` at `0x180085605`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180085365`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800853e2`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180085365`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800853e2`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180085463`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x1800854a7`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180085463`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x1800854a7`
- `ext-ms-win-wer-xbox-l1-1-3!XerEncryptDump` at `0x180085591`
- `ext-ms-win-wer-xbox-l1-1-3!XerEncryptDump` at `0x180085591`

## string_xrefs

- `0x180085221`: `DumpThreadPriority`
- `0x1800852ec`: `DumpWriteBufferSize`
- `0x180085668`: `Dump file could not be created: UtilGetProtectedProcessInfo failed %08X.`

## pseudocode

```c
signed int __fastcall CProcessDump::Initialize(
        DWORD *this,
        struct CReportHandleInstance *a2,
        struct CReport *a3,
        void *a4,
        void *a5,
        enum _WER_DUMP_TYPE a6,
        unsigned int a7,
        struct _WER_EXCEPTION_INFORMATION *const a8,
        _DWORD *a9,
        unsigned int a10)
{
  _WORD *v11; // rcx
  HANDLE *v12; // r15
  __int64 v13; // rdx
  _OWORD *v14; // rcx
  _OWORD *v15; // rax
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int64 v26; // rax
  HANDLE *v27; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v29; // rax
  DWORD LastError; // eax
  signed int result; // eax
  HANDLE *v32; // rdi
  HANDLE v33; // rbx
  HANDLE v34; // rax
  char *v35; // rcx
  __int64 v36; // rcx
  bool v37; // cc
  HANDLE v38; // rbx
  NTSTATUS InformationProcess; // eax
  HANDLE v40; // rcx
  HANDLE v41; // rcx
  bool v42; // zf
  int v43; // eax
  int ProtectedProcessInfo; // eax
  BOOL v45; // eax
  struct _CONTEXT *v46; // r9
  DWORD ExceptionCode; // eax
  PEXCEPTION_RECORD ExceptionRecord; // rax
  bool bInheritHandle; // [rsp+28h] [rbp-D8h]
  bool bInheritHandlea; // [rsp+28h] [rbp-D8h]
  bool bInheritHandleb; // [rsp+28h] [rbp-D8h]
  bool bInheritHandlec; // [rsp+28h] [rbp-D8h]
  bool bInheritHandled; // [rsp+28h] [rbp-D8h]
  bool bInheritHandlee; // [rsp+28h] [rbp-D8h]
  bool bInheritHandlef; // [rsp+28h] [rbp-D8h]
  HANDLE hSourceHandle; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v57; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hProcess; // [rsp+50h] [rbp-B0h] BYREF
  struct CReportHandleInstance *v59; // [rsp+58h] [rbp-A8h]
  struct CReport *v60; // [rsp+60h] [rbp-A0h]
  _QWORD ProcessInformation[5]; // [rsp+70h] [rbp-90h] BYREF
  DWORD v62; // [rsp+98h] [rbp-68h]
  _BYTE v63[592]; // [rsp+B0h] [rbp-50h] BYREF
  struct _EXCEPTION_RECORD v64; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v65[28]; // [rsp+3A0h] [rbp+2A0h] BYREF
  DWORD v66; // [rsp+3BCh] [rbp+2BCh]
  int v67; // [rsp+3C4h] [rbp+2C4h]
  char v68[524]; // [rsp+454h] [rbp+354h] BYREF

  v60 = a3;
  v59 = a2;
  v57 = a5;
  hProcess = 0;
  hSourceHandle = a4;
  memset_0(v65, 0, 0x2C0u);
  memset_0(ProcessInformation, 0, 0x40u);
  memset_0(&v64, 0, sizeof(v64));
  if ( (unsigned int)(a6 - 1) > 3 || a9 && (((*a9 - 552) & 0xFFFFFFD7) != 0 || *a9 == 592) )
    return -2147024809;
  CProcessDump::Uninitialize((CProcessDump *)this);
  v11 = (_WORD *)*((_QWORD *)this + 3);
  v12 = (HANDLE *)(this + 28);
  *((_QWORD *)this + 4) = v11;
  *v11 = 0;
  tlx::unique_any<tlx::file_handle_traits>::reset(this + 28, 0);
  *((_QWORD *)this + 15) = 0;
  this[32] = 0;
  tlx::unique_any<tlx::file_handle_traits>::reset(this + 46, 0);
  this[48] = 0;
  memset_0(v63, 0, 0x248u);
  v13 = 4;
  v14 = this + 50;
  v15 = v63;
  do
  {
    v16 = v15[1];
    *v14 = *v15;
    v17 = v15[2];
    v14[1] = v16;
    v18 = v15[3];
    v14[2] = v17;
    v19 = v15[4];
    v14[3] = v18;
    v20 = v15[5];
    v14[4] = v19;
    v21 = v15[6];
    v14[5] = v20;
    v22 = v15[7];
    v15 += 8;
    v14[6] = v21;
    v14[7] = v22;
    v14 += 8;
    --v13;
  }
  while ( v13 );
  v23 = v15[1];
  *v14 = *v15;
  v24 = v15[2];
  v14[1] = v23;
  v25 = v15[3];
  v26 = *((_QWORD *)v15 + 8);
  v14[2] = v24;
  v14[3] = v25;
  *((_QWORD *)v14 + 8) = v26;
  memset_0(this + 196, 0, 0x400u);
  *((_QWORD *)this + 1) = v59;
  *((_QWORD *)this + 2) = v60;
  this[50] = 584;
  this[42] = a6;
  this[43] = a7 & 0x5FFFFFF;
  *((_QWORD *)this + 226) = 0;
  this[454] = 0;
  this[44] = a10;
  *((_OWORD *)this + 114) = 0;
  this[14] = UtilRegGetDWORD(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
               L"DumpWait",
               0,
               0,
               bInheritHandle);
  this[15] = UtilRegGetDWORD(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
               L"DumpThreadPriority",
               0x80000000,
               0,
               bInheritHandlea);
  this[16] = UtilRegGetDWORD(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
               L"DumpProfilingEnabled",
               0,
               0,
               bInheritHandleb) != 0;
  this[17] = UtilRegGetDWORD(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
               L"DumpBgPriorityDisabled",
               0,
               0,
               bInheritHandlec) != 0;
  this[18] = UtilRegGetDWORD(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
               L"DumpUseTransientFile",
               0xFFFFFFFF,
               0,
               bInheritHandled);
  this[19] = UtilRegGetDWORD(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
               L"DumpFailGeneration",
               0,
               0,
               bInheritHandlee) != 0;
  this[20] = UtilRegGetDWORD(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
               L"DumpWriteBufferSize",
               0xFFFFFFFF,
               0,
               bInheritHandlef);
  CProcessDump::SetDefaultDumpOptions((CProcessDump *)this);
  if ( hSourceHandle
    && (v27 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(this + 28),
        CurrentProcess = GetCurrentProcess(),
        v29 = GetCurrentProcess(),
        !DuplicateHandle(v29, hSourceHandle, CurrentProcess, v27, 0, 0, 2u))
    || v57
    && (v32 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(this + 46),
        v33 = GetCurrentProcess(),
        v34 = GetCurrentProcess(),
        !DuplicateHandle(v34, v57, v33, v32, 0, 0, 2u)) )
  {
    LastError = GetLastError();
    return ERROR_HR_FROM_WIN32(LastError);
  }
  v35 = (char *)*((_QWORD *)this + 23);
  if ( v35 != (char *)-1LL && v35 + 1 != (char *)1 )
    this[48] = GetThreadId(v35);
  if ( a9 )
  {
    result = CProcessDump::SetDumpOptions((CProcessDump *)this, a9);
    if ( result < 0 )
      return result;
    if ( !this[48] )
      this[48] = this[194];
  }
  v36 = *((_QWORD *)this + 96);
  if ( !v36 )
  {
    v38 = *v12;
    if ( (unsigned __int64)*v12 + 1 > 1 )
    {
      ProcessInformation[0] = 64;
      InformationProcess = NtQueryInformationProcess(v38, ProcessBasicInformation, ProcessInformation, 0x40u, 0);
      if ( InformationProcess < 0 )
        return InformationProcess | 0x10000000;
      v40 = *v12;
      this[30] = v62;
      LODWORD(hSourceHandle) = 0;
      UtilGetProtectedProcessInfo(v40, (enum _PS_PROTECTED_TYPE *)&hSourceHandle, 0);
      v41 = *v12;
      this[32] = (int)hSourceHandle > 0;
      UtilGetProcessPathFromHandle(v41);
LABEL_29:
      this[21] = this[44] & 0x10000000;
      if ( (unsigned __int8)IsXerTransportEventUploadCompletePresent() )
      {
        if ( this[21]
          || (v42 = (unsigned int)XerEncryptDump(*(_QWORD *)(*((_QWORD *)this + 2) + 560LL), (unsigned int)a6) == 0,
              v43 = 0,
              !v42) )
        {
          v43 = 1;
        }
        this[21] = v43;
      }
      if ( this[32] )
      {
        LODWORD(v57) = 0;
        LODWORD(hSourceHandle) = 0;
        ProtectedProcessInfo = UtilGetProtectedProcessInfo(
                                 v38,
                                 (enum _PS_PROTECTED_TYPE *)&v57,
                                 (enum _PS_PROTECTED_SIGNER *)&hSourceHandle);
        if ( ProtectedProcessInfo < 0 )
        {
          CProcessDump::LogTrace(
            (CProcessDump *)this,
            0,
            L"Dump file could not be created: UtilGetProtectedProcessInfo failed %08X.",
            (unsigned int)ProtectedProcessInfo);
          return -2147024883;
        }
        v45 = this[21]
           || (_DWORD)v57 == 2
           || (_DWORD)v57 == 1 && (_DWORD)hSourceHandle != 3 && (_DWORD)hSourceHandle != 8;
        this[21] = v45;
      }
      WerGetFlags(v38, this + 31);
      if ( !a8 )
        goto LABEL_54;
      *((struct _WER_EXCEPTION_INFORMATION *)this + 114) = *a8;
      if ( !a8->pExceptionPointers )
        goto LABEL_54;
      if ( a8->bClientPointers && v38 )
      {
        if ( UtilReadExceptionInformationFromExceptionPointer(v38, a8->pExceptionPointers, &v64, v46) >= 0 )
        {
          *((_QWORD *)this + 226) = v64.ExceptionAddress;
          ExceptionCode = v64.ExceptionCode;
LABEL_53:
          this[454] = ExceptionCode;
        }
      }
      else
      {
        ExceptionRecord = a8->pExceptionPointers->ExceptionRecord;
        if ( ExceptionRecord )
        {
          *((_QWORD *)this + 226) = ExceptionRecord->ExceptionAddress;
          ExceptionCode = a8->pExceptionPointers->ExceptionRecord->ExceptionCode;
          goto LABEL_53;
        }
      }
LABEL_54:
      *this = 1;
      return 0;
    }
    return -2147024809;
  }
  result = PssQuerySnapshot(v36, 1, &hProcess);
  if ( result == 1168 )
    return -2147024809;
  v37 = result <= 0;
  if ( !result )
  {
    result = PssQuerySnapshot(*((_QWORD *)this + 96), 0, v65);
    v37 = result <= 0;
    if ( !result )
    {
      v38 = hProcess;
      this[30] = v66;
      this[32] = v67 & 1;
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(this + 34, v68);
      goto LABEL_29;
    }
  }
  if ( !v37 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180084fdc  mov     [rsp-8+arg_8], rbx
0x180084fe1  push    rbp
0x180084fe2  push    rsi
0x180084fe3  push    rdi
0x180084fe4  push    r12
0x180084fe6  push    r13
0x180084fe8  push    r14
0x180084fea  push    r15
0x180084fec  lea     rbp, [rsp-570h]
0x180084ff4  sub     rsp, 670h
0x180084ffb  mov     rax, cs:__security_cookie
0x180085002  xor     rax, rsp
0x180085005  mov     [rbp+5A0h+var_40], rax
0x18008500c  mov     rax, [rbp+5A0h+arg_20]
0x180085013  mov     rsi, rcx
0x180085016  mov     r14, [rbp+5A0h+arg_38]
0x18008501d  lea     rcx, [rbp+5A0h+var_300]; void *
0x180085024  mov     r12, [rbp+5A0h+arg_40]
0x18008502b  xor     edi, edi
0x18008502d  mov     [rsp+6A0h+var_640], r8
0x180085032  mov     r8d, 2C0h; Size
0x180085038  mov     [rsp+6A0h+var_648], rdx
0x18008503d  xor     edx, edx; Val
0x18008503f  mov     [rsp+6A0h+var_658], rax
0x180085044  mov     [rsp+6A0h+hProcess], rdi
0x180085049  mov     [rsp+6A0h+hSourceHandle], r9
0x18008504e  call    memset_0
0x180085053  xor     edx, edx; Val
0x180085055  lea     r8d, [rdi+40h]; Size
0x180085059  lea     rcx, [rsp+6A0h+ProcessInformation]; void *
0x18008505e  call    memset_0
0x180085063  xor     edx, edx; Val
0x180085065  lea     rcx, [rbp+5A0h+var_3A0]; void *
0x18008506c  mov     r8d, 98h; Size
0x180085072  call    memset_0
0x180085077  mov     ebx, [rbp+5A0h+arg_28]
0x18008507d  lea     eax, [rbx-1]
0x180085080  cmp     eax, 3
0x180085083  ja      loc_1800856A8
0x180085089  test    r12, r12
0x18008508c  jz      short loc_1800850AF
0x18008508e  mov     ecx, [r12]
0x180085092  lea     eax, [rcx-228h]
0x180085098  test    eax, 0FFFFFFD7h
0x18008509d  jnz     loc_1800856A8
0x1800850a3  cmp     ecx, 250h
0x1800850a9  jz      loc_1800856A8
0x1800850af  mov     rcx, rsi; this
0x1800850b2  call    ?Uninitialize@CProcessDump@@QEAAXXZ; CProcessDump::Uninitialize(void)
0x1800850b7  mov     rcx, [rsi+18h]
0x1800850bb  lea     r15, [rsi+70h]
0x1800850bf  mov     [rsi+20h], rcx
0x1800850c3  xor     edx, edx
0x1800850c5  mov     [rcx], di
0x1800850c8  mov     rcx, r15
0x1800850cb  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800850d0  lea     r13, [rsi+0B8h]
0x1800850d7  mov     [rsi+78h], rdi
0x1800850db  mov     rcx, r13
0x1800850de  mov     [rsi+80h], edi
0x1800850e4  xor     edx, edx
0x1800850e6  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800850eb  xor     edx, edx; Val
0x1800850ed  mov     [rsi+0C0h], edi
0x1800850f3  mov     r8d, 248h; Size
0x1800850f9  lea     rcx, [rbp+5A0h+var_5F0]; void *
0x1800850fd  call    memset_0
0x180085102  mov     edx, 4
0x180085107  lea     rdi, [rsi+0C8h]
0x18008510e  mov     rcx, rdi
0x180085111  lea     rax, [rbp+5A0h+var_5F0]
0x180085115  lea     r8d, [rdx+7Ch]
0x180085119  movups  xmm0, xmmword ptr [rax]
0x18008511c  movups  xmm1, xmmword ptr [rax+10h]
0x180085120  movups  xmmword ptr [rcx], xmm0
0x180085123  movups  xmm0, xmmword ptr [rax+20h]
0x180085127  movups  xmmword ptr [rcx+10h], xmm1
0x18008512b  movups  xmm1, xmmword ptr [rax+30h]
0x18008512f  movups  xmmword ptr [rcx+20h], xmm0
0x180085133  movups  xmm0, xmmword ptr [rax+40h]
0x180085137  movups  xmmword ptr [rcx+30h], xmm1
0x18008513b  movups  xmm1, xmmword ptr [rax+50h]
0x18008513f  movups  xmmword ptr [rcx+40h], xmm0
0x180085143  movups  xmm0, xmmword ptr [rax+60h]
0x180085147  movups  xmmword ptr [rcx+50h], xmm1
0x18008514b  movups  xmm1, xmmword ptr [rax+70h]
0x18008514f  add     rax, r8
0x180085152  movups  xmmword ptr [rcx+60h], xmm0
0x180085156  movups  xmmword ptr [rcx+70h], xmm1
0x18008515a  add     rcx, r8
0x18008515d  sub     rdx, 1; Val
0x180085161  jnz     short loc_180085119
0x180085163  movups  xmm0, xmmword ptr [rax]
0x180085166  mov     r8d, 400h; Size
0x18008516c  movups  xmm1, xmmword ptr [rax+10h]
0x180085170  movups  xmmword ptr [rcx], xmm0
0x180085173  movups  xmm0, xmmword ptr [rax+20h]
0x180085177  movups  xmmword ptr [rcx+10h], xmm1
0x18008517b  movups  xmm1, xmmword ptr [rax+30h]
0x18008517f  mov     rax, [rax+40h]
0x180085183  movups  xmmword ptr [rcx+20h], xmm0
0x180085187  movups  xmmword ptr [rcx+30h], xmm1
0x18008518b  mov     [rcx+40h], rax
0x18008518f  lea     rcx, [rsi+310h]; void *
0x180085196  call    memset_0
0x18008519b  mov     rax, [rsp+6A0h+var_648]
0x1800851a0  lea     r8, aDumpwait; "DumpWait"
0x1800851a7  mov     [rsi+8], rax
0x1800851ab  xor     ecx, ecx
0x1800851ad  mov     rax, [rsp+6A0h+var_640]
0x1800851b2  xorps   xmm0, xmm0
0x1800851b5  mov     [rsi+10h], rax
0x1800851b9  xor     r9d, r9d; unsigned int
0x1800851bc  mov     eax, [rbp+5A0h+arg_30]
0x1800851c2  and     eax, 5FFFFFFh
0x1800851c7  mov     dword ptr [rdi], 248h
0x1800851cd  mov     [rsi+0A8h], ebx
0x1800851d3  mov     rdi, 0FFFFFFFF80000002h
0x1800851da  mov     [rsi+0ACh], eax
0x1800851e0  lea     rbx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x1800851e7  mov     eax, [rbp+5A0h+arg_48]
0x1800851ed  mov     rdx, rbx; wchar_t *
0x1800851f0  mov     [rsi+710h], rcx
0x1800851f7  mov     [rsi+718h], ecx
0x1800851fd  mov     qword ptr [rsp+6A0h+dwDesiredAccess], rcx; bool *
0x180085202  mov     rcx, rdi; HKEY
0x180085205  mov     [rsi+0B0h], eax
0x18008520b  movdqu  xmmword ptr [rsi+720h], xmm0
0x180085213  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180085218  mov     r9d, 80000000h; unsigned int
0x18008521e  mov     [rsi+38h], eax
0x180085221  lea     r8, aDumpthreadprio; "DumpThreadPriority"
0x180085228  mov     qword ptr [rsp+6A0h+dwDesiredAccess], 0; bool *
0x180085231  mov     rdx, rbx; wchar_t *
0x180085234  mov     rcx, rdi; HKEY
0x180085237  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18008523c  xor     r9d, r9d; unsigned int
0x18008523f  mov     [rsi+3Ch], eax
0x180085242  lea     r8, aDumpprofilinge; "DumpProfilingEnabled"
0x180085249  mov     qword ptr [rsp+6A0h+dwDesiredAccess], 0; bool *
0x180085252  mov     rdx, rbx; wchar_t *
0x180085255  mov     rcx, rdi; HKEY
0x180085258  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18008525d  xor     ecx, ecx
0x18008525f  mov     qword ptr [rsp+6A0h+dwDesiredAccess], 0; bool *
0x180085268  test    eax, eax
0x18008526a  lea     r8, aDumpbgpriority; "DumpBgPriorityDisabled"
0x180085271  mov     rdx, rbx; wchar_t *
0x180085274  setnz   cl
0x180085277  xor     r9d, r9d; unsigned int
0x18008527a  mov     [rsi+40h], ecx
0x18008527d  mov     rcx, rdi; HKEY
0x180085280  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180085285  xor     ecx, ecx
0x180085287  mov     qword ptr [rsp+6A0h+dwDesiredAccess], 0; bool *
0x180085290  test    eax, eax
0x180085292  lea     r8, aDumpusetransie; "DumpUseTransientFile"
0x180085299  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x1800852a0  setnz   cl
0x1800852a3  or      ebx, 0FFFFFFFFh
0x1800852a6  mov     [rsi+44h], ecx
0x1800852a9  mov     r9d, ebx; unsigned int
0x1800852ac  mov     rcx, rdi; HKEY
0x1800852af  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x1800852b4  xor     r9d, r9d; unsigned int
0x1800852b7  mov     [rsi+48h], eax
0x1800852ba  lea     r8, aDumpfailgenera; "DumpFailGeneration"
0x1800852c1  mov     qword ptr [rsp+6A0h+dwDesiredAccess], 0; bool *
0x1800852ca  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x1800852d1  mov     rcx, rdi; HKEY
0x1800852d4  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x1800852d9  xor     ecx, ecx
0x1800852db  test    eax, eax
0x1800852dd  setnz   cl
0x1800852e0  mov     qword ptr [rsp+6A0h+dwDesiredAccess], 0; bool *
0x1800852e9  mov     [rsi+4Ch], ecx
0x1800852ec  lea     r8, aDumpwritebuffe; "DumpWriteBufferSize"
0x1800852f3  mov     rcx, rdi; HKEY
0x1800852f6  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x1800852fd  mov     r9d, ebx; unsigned int
0x180085300  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180085305  mov     rcx, rsi; this
0x180085308  mov     [rsi+50h], eax
0x18008530b  call    ?SetDefaultDumpOptions@CProcessDump@@AEAAXXZ; CProcessDump::SetDefaultDumpOptions(void)
0x180085310  xor     edi, edi
0x180085312  cmp     [rsp+6A0h+hSourceHandle], rdi
0x180085317  jz      short loc_18008538F
0x180085319  mov     rcx, r15
0x18008531c  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180085321  mov     rdi, rax
0x180085324  call    cs:__imp_GetCurrentProcess
0x18008532b  nop     dword ptr [rax+rax+00h]
0x180085330  mov     rbx, rax
0x180085333  call    cs:__imp_GetCurrentProcess
0x18008533a  nop     dword ptr [rax+rax+00h]
0x18008533f  mov     rdx, [rsp+6A0h+hSourceHandle]; hSourceHandle
0x180085344  mov     r9, rdi; lpTargetHandle
0x180085347  mov     [rsp+6A0h+dwOptions], 2; dwOptions
0x18008534f  mov     rcx, rax; hSourceProcessHandle
0x180085352  mov     dword ptr [rsp+6A0h+bInheritHandle], 0; bInheritHandle
0x18008535a  mov     r8, rbx; hTargetProcessHandle
0x18008535d  mov     [rsp+6A0h+dwDesiredAccess], 0; dwDesiredAccess
0x180085365  call    cs:__imp_DuplicateHandle
0x18008536c  nop     dword ptr [rax+rax+00h]
0x180085371  xor     edi, edi
0x180085373  test    eax, eax
0x180085375  jnz     short loc_18008538F
0x180085377  call    cs:__imp_GetLastError
0x18008537e  nop     dword ptr [rax+rax+00h]
0x180085383  mov     ecx, eax; unsigned int
0x180085385  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18008538a  jmp     loc_1800856AD
0x18008538f  cmp     [rsp+6A0h+var_658], rdi
0x180085394  jz      short loc_1800853F4
0x180085396  mov     rcx, r13
0x180085399  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18008539e  mov     rdi, rax
0x1800853a1  call    cs:__imp_GetCurrentProcess
0x1800853a8  nop     dword ptr [rax+rax+00h]
0x1800853ad  mov     rbx, rax
0x1800853b0  call    cs:__imp_GetCurrentProcess
0x1800853b7  nop     dword ptr [rax+rax+00h]
0x1800853bc  mov     rdx, [rsp+6A0h+var_658]; hSourceHandle
0x1800853c1  mov     r9, rdi; lpTargetHandle
0x1800853c4  mov     [rsp+6A0h+dwOptions], 2; dwOptions
0x1800853cc  mov     rcx, rax; hSourceProcessHandle
0x1800853cf  mov     dword ptr [rsp+6A0h+bInheritHandle], 0; bInheritHandle
0x1800853d7  mov     r8, rbx; hTargetProcessHandle
0x1800853da  mov     [rsp+6A0h+dwDesiredAccess], 0; dwDesiredAccess
0x1800853e2  call    cs:__imp_DuplicateHandle
0x1800853e9  nop     dword ptr [rax+rax+00h]
0x1800853ee  xor     edi, edi
0x1800853f0  test    eax, eax
0x1800853f2  jz      short loc_180085377
0x1800853f4  mov     rcx, [r13+0]; Thread
0x1800853f8  mov     r13d, 1
0x1800853fe  lea     rax, [rcx+1]
0x180085402  cmp     rax, r13
0x180085405  jbe     short loc_180085419
0x180085407  call    cs:__imp_GetThreadId
0x18008540e  nop     dword ptr [rax+rax+00h]
0x180085413  mov     [rsi+0C0h], eax
0x180085419  test    r12, r12
0x18008541c  jz      short loc_180085445
0x18008541e  mov     rdx, r12; void *
0x180085421  mov     rcx, rsi; this
0x180085424  call    ?SetDumpOptions@CProcessDump@@AEAAJPEAX@Z; CProcessDump::SetDumpOptions(void *)
0x180085429  test    eax, eax
0x18008542b  js      loc_1800856AD
0x180085431  cmp     [rsi+0C0h], edi
0x180085437  jnz     short loc_180085445
0x180085439  mov     eax, [rsi+308h]
0x18008543f  mov     [rsi+0C0h], eax
0x180085445  mov     rcx, [rsi+300h]
0x18008544c  test    rcx, rcx
0x18008544f  jz      loc_1800854E9
0x180085455  mov     r9d, 8
0x18008545b  lea     r8, [rsp+6A0h+hProcess]
0x180085460  mov     edx, r13d
0x180085463  call    cs:__imp_PssQuerySnapshot
0x18008546a  nop     dword ptr [rax+rax+00h]
0x18008546f  cmp     eax, 490h
0x180085474  jz      loc_1800856A8
0x18008547a  test    eax, eax
0x18008547c  jz      short loc_180085491
0x18008547e  jle     loc_1800856AD
0x180085484  movzx   eax, ax
0x180085487  or      eax, 80070000h
0x18008548c  jmp     loc_1800856AD
0x180085491  mov     rcx, [rsi+300h]
0x180085498  lea     r8, [rbp+5A0h+var_300]
0x18008549f  mov     r9d, 2C0h
0x1800854a5  xor     edx, edx
0x1800854a7  call    cs:__imp_PssQuerySnapshot
0x1800854ae  nop     dword ptr [rax+rax+00h]
0x1800854b3  test    eax, eax
0x1800854b5  jnz     short loc_18008547E
0x1800854b7  mov     eax, [rbp+5A0h+var_2E4]
0x1800854bd  lea     rcx, [rsi+88h]
0x1800854c4  mov     rbx, [rsp+6A0h+hProcess]
0x1800854c9  lea     rdx, [rbp+5A0h+var_24C]
0x1800854d0  mov     [rsi+78h], eax
0x1800854d3  mov     eax, [rbp+5A0h+var_2DC]
0x1800854d9  and     eax, r13d
0x1800854dc  mov     [rsi+80h], eax
0x1800854e2  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800854e7  jmp     short loc_180085564
0x1800854e9  mov     rbx, [r15]
0x1800854ec  lea     rax, [rbx+1]
0x1800854f0  cmp     rax, r13
0x1800854f3  jbe     loc_1800856A8
0x1800854f9  mov     r9d, 40h ; '@'; ProcessInformationLength
0x1800854ff  mov     qword ptr [rsp+6A0h+dwDesiredAccess], rdi; ReturnLength
0x180085504  lea     r8, [rsp+6A0h+ProcessInformation]; ProcessInformation
0x180085509  mov     [rsp+6A0h+ProcessInformation], r9
0x18008550e  xor     edx, edx; ProcessInformationClass
0x180085510  mov     rcx, rbx; ProcessHandle
0x180085513  call    cs:__imp_NtQueryInformationProcess
0x18008551a  nop     dword ptr [rax+rax+00h]
0x18008551f  test    eax, eax
  ... truncated ...
```

# CRegistryWriter::CreateWriter(void)

- ea: `0x14003de10`
- end: `0x14003e2a4`
- name: `?CreateWriter@CRegistryWriter@@SAJXZ`
- size: `1172`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140028d60`

## callees

- `0x140006020`
- `0x1400137c0`
- `0x140013cb0`
- `0x140015e38`
- `0x140028b48`
- `0x140032fcc`
- `0x1400330fc`
- `0x14003de10`
- `0x14009197c`
- `0x1400921dc`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003e180`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003e180`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e0ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e0ff`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14003e0f1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14003e0f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003e189`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003e189`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003dece`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003dece`
- `VssTrace!__imp_VssTraceMessage` at `0x14003dfd8`
- `VssTrace!__imp_VssTraceMessage` at `0x14003dfd8`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003df2f`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003df2f`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003df20`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003df20`

## string_xrefs

- `0x14003de27`: `base\stor\vss\modules\writers\regwriter.cxx`
- `0x14003e1b1`: `base\stor\vss\modules\writers\regwriter.cxx`
- `0x14003de35`: `CRegistryWriter::CreateWriter`
- `0x14003e1aa`: `CRegistryWriter::CreateWriter`
- `0x14003e161`: `CreateThread failed with error %d`
- `0x14003e0a9`: `Allocation of CRegistryWriter object failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CRegistryWriter::CreateWriter(void)
{
  int v0; // eax
  __int64 v1; // rcx
  int v2; // ebx
  CVssWriter *v4; // rax
  HANDLE Thread; // rax
  void *v6; // rbx
  DWORD LastError; // ebx
  CVssDebugInfo *v8; // rax
  DWORD v9; // ebx
  unsigned __int64 v10; // [rsp+50h] [rbp-1F8h] BYREF
  DWORD dwMessageId; // [rsp+58h] [rbp-1F0h]
  const unsigned __int16 *v12; // [rsp+60h] [rbp-1E8h]
  const unsigned __int16 *v13; // [rsp+68h] [rbp-1E0h]
  unsigned int v14; // [rsp+70h] [rbp-1D8h]
  unsigned int v15; // [rsp+74h] [rbp-1D4h]
  const unsigned __int16 *v16; // [rsp+78h] [rbp-1D0h]
  unsigned int v17; // [rsp+80h] [rbp-1C8h]
  DWORD TickCount; // [rsp+84h] [rbp-1C4h]
  int v19; // [rsp+88h] [rbp-1C0h]
  __int128 v20; // [rsp+90h] [rbp-1B8h]
  __int128 v21; // [rsp+A0h] [rbp-1A8h]
  __int64 v22; // [rsp+B0h] [rbp-198h]
  const unsigned __int16 *v23; // [rsp+C0h] [rbp-188h] BYREF
  const unsigned __int16 *v24; // [rsp+C8h] [rbp-180h]
  const unsigned __int16 *v25; // [rsp+D0h] [rbp-178h]
  int v26; // [rsp+D8h] [rbp-170h]
  int v27; // [rsp+DCh] [rbp-16Ch]
  int v28; // [rsp+E0h] [rbp-168h]
  _BYTE v29[120]; // [rsp+E8h] [rbp-160h] BYREF
  int v30; // [rsp+160h] [rbp-E8h]
  int v31; // [rsp+168h] [rbp-E0h] BYREF
  const std::exception *v32; // [rsp+170h] [rbp-D8h] BYREF
  _com_error *v33; // [rsp+178h] [rbp-D0h] BYREF
  _BYTE v34[176]; // [rsp+180h] [rbp-C8h] BYREF
  __int64 ThreadId; // [rsp+250h] [rbp+8h] BYREF
  CVssWriter *v36; // [rsp+258h] [rbp+10h]

  v23 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
  v24 = L"CRegistryWriter::CreateWriter";
  v25 = L"WRTREGRC";
  v26 = 484;
  v27 = 4;
  v28 = 255;
  v30 = 0x1000000;
  memset_0(v29, 0, sizeof(v29));
  dwMessageId = 0;
  v16 = L"CRegistryWriter::CreateWriter";
  v12 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
  v13 = L"WRTREGRC";
  v14 = 484;
  v15 = 4;
  TickCount = GetTickCount();
  v19 = 255;
  v10 = 0xFFFFFFFF00000000uLL;
  v22 = 0;
  v20 = 0;
  v21 = 0;
  ThreadId = 0;
  if ( (int)VssGetTracingContextPerThread(&ThreadId) < 0 )
  {
    v1 = v22;
  }
  else
  {
    v0 = VssSetTracingContextPerThread(&v10);
    v1 = v22;
    if ( v0 >= 0 )
      v1 = ThreadId;
    v22 = v1;
  }
  if ( v1 )
    v17 = *(_DWORD *)(v1 + 48) + 1;
  else
    v17 = 0;
  v2 = 160;
  if ( v19 != 255 )
    v2 = v19;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v10) )
    VssTraceMessage(v12, v13, v14, v17, v15, v16, L"ENTER", v2, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v23);
  if ( CRegistryWriter::sm_pWriter )
  {
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v10);
    return 0;
  }
  else
  {
    v4 = (CVssWriter *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v36 = v4;
    if ( v4 )
    {
      *((_QWORD *)v4 + 1) = 0;
      *(_QWORD *)v4 = &CRegistryWriter::`vftable';
      *((_QWORD *)v4 + 3) = 0;
      *((_QWORD *)v4 + 2) = &CVssAutoLocalPtr<unsigned short *>::`vftable';
    }
    else
    {
      v4 = 0;
    }
    try
    {
      CRegistryWriter::sm_pWriter = v4;
      if ( !v4 )
      {
        v23 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
        v24 = L"CRegistryWriter::CreateWriter";
        v25 = L"WRTREGRC";
        v26 = 496;
        v27 = 4;
        v28 = 255;
        v30 = 0x1000000;
        memset_0(v29, 0, sizeof(v29));
        CVssFunctionTracer::Throw(&v10, &v23, 2147942414LL, L"Allocation of CRegistryWriter object failed.");
      }
      LODWORD(ThreadId) = 0;
      Thread = CreateThread(0, 0x40000u, CRegistryWriter::InitializeThreadFunc, 0, 0, (LPDWORD)&ThreadId);
      v6 = Thread;
      if ( !Thread )
      {
        LastError = GetLastError();
        v23 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
        v24 = L"CRegistryWriter::CreateWriter";
        v25 = L"WRTREGRC";
        v26 = 513;
        v27 = 4;
        v28 = 255;
        v30 = 0x1000000;
        memset_0(v29, 0, sizeof(v29));
        CVssFunctionTracer::TranslateWin32Error(&v10, &v23, L"CreateThread failed with error %d", LastError);
      }
      WaitForSingleObject(Thread, 0xFFFFFFFF);
      CloseHandle(v6);
      dwMessageId = CRegistryWriter::sm_hrInitialize;
    }
    catch ( long v31 )
    {
      CVssFunctionTracer::HandleHresultException(
        (CVssFunctionTracer *)&v10,
        v31,
        L"base\\stor\\vss\\modules\\writers\\regwriter.cxx",
        L"WRTREGRC",
        L"CRegistryWriter::CreateWriter",
        0x20Bu,
        v15);
    }
    catch ( _com_error *v33 )
    {
      CVssFunctionTracer::HandleComException(
        (CVssFunctionTracer *)&v10,
        v33,
        L"base\\stor\\vss\\modules\\writers\\regwriter.cxx",
        L"WRTREGRC",
        L"CRegistryWriter::CreateWriter",
        0x20Bu,
        v15);
    }
    catch ( std::bad_alloc )
    {
      CVssFunctionTracer::HandleStdBadAllocException(
        (CVssFunctionTracer *)&v10,
        L"base\\stor\\vss\\modules\\writers\\regwriter.cxx",
        L"WRTREGRC",
        L"CRegistryWriter::CreateWriter",
        0x20Bu,
        v15);
    }
    catch ( const std::exception *v32 )
    {
      CVssFunctionTracer::HandleStdGenericException(
        (CVssFunctionTracer *)&v10,
        v32,
        L"base\\stor\\vss\\modules\\writers\\regwriter.cxx",
        L"WRTREGRC",
        L"CRegistryWriter::CreateWriter",
        0x20Bu,
        v15);
    }
    if ( (dwMessageId & 0x80000000) != 0 )
    {
      if ( CRegistryWriter::sm_pWriter )
      {
        (**(void (__fastcall ***)(CVssWriter *, __int64))CRegistryWriter::sm_pWriter)(CRegistryWriter::sm_pWriter, 1);
        CRegistryWriter::sm_pWriter = 0;
      }
      v23 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
      v24 = L"CRegistryWriter::CreateWriter";
      v25 = L"WRTREGRC";
      v26 = 532;
      v27 = 4;
      v28 = 255;
      v30 = 0x1000000;
      memset_0(v29, 0, sizeof(v29));
      v8 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v23, (CVssDebugInfo *)v34, dwMessageId);
      CVssFunctionTracer::LogError((__int64)&v10, 0x3036u, (__int64)v8, 1u);
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v23);
    }
    v9 = dwMessageId;
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v10);
    return v9;
  }
}

```

## disassembly

```asm
0x14003de10  mov     rax, rsp
0x14003de13  mov     [rax+18h], rbx
0x14003de17  mov     [rax+20h], rsi
0x14003de1b  push    rdi
0x14003de1c  push    r14
0x14003de1e  push    r15
0x14003de20  sub     rsp, 230h
0x14003de27  lea     rsi, aBaseStorVssMod_31; "base\\stor\\vss\\modules\\writers\\regw"...
0x14003de2e  mov     [rax-188h], rsi
0x14003de35  lea     r14, aCregistrywrite_1; "CRegistryWriter::CreateWriter"
0x14003de3c  mov     [rax-180h], r14
0x14003de43  lea     r15, aWrtregrc; "WRTREGRC"
0x14003de4a  mov     [rax-178h], r15
0x14003de51  mov     dword ptr [rax-170h], 1E4h
0x14003de5b  mov     dword ptr [rax-16Ch], 4
0x14003de65  mov     dword ptr [rax-168h], 0FFh
0x14003de6f  xor     edi, edi
0x14003de71  mov     dword ptr [rax-0E8h], 1000000h
0x14003de7b  xor     edx, edx; Val
0x14003de7d  lea     r8d, [rdi+78h]; Size
0x14003de81  lea     rcx, [rax-160h]; void *
0x14003de88  call    memset_0
0x14003de8d  mov     [rsp+248h+dwMessageId], edi
0x14003de91  mov     rax, [rsp+248h+var_180]
0x14003de99  mov     [rsp+248h+var_1D0], rax
0x14003de9e  mov     rax, [rsp+248h+var_188]
0x14003dea6  mov     [rsp+248h+var_1E8], rax
0x14003deab  mov     rax, [rsp+248h+var_178]
0x14003deb3  mov     [rsp+248h+var_1E0], rax
0x14003deb8  mov     eax, [rsp+248h+var_170]
0x14003debf  mov     [rsp+248h+var_1D8], eax
0x14003dec3  mov     eax, [rsp+248h+var_16C]
0x14003deca  mov     [rsp+248h+var_1D4], eax
0x14003dece  call    cs:__imp_GetTickCount
0x14003ded4  mov     [rsp+248h+var_1C4], eax
0x14003dedb  mov     [rsp+248h+var_1F4], 0FFFFFFFFh
0x14003dee3  mov     eax, [rsp+248h+var_168]
0x14003deea  mov     [rsp+248h+var_1C0], eax
0x14003def1  mov     [rsp+248h+var_1F8], edi
0x14003def5  mov     [rsp+248h+var_198], rdi
0x14003defd  xorps   xmm0, xmm0
0x14003df00  movups  [rsp+248h+var_1B8], xmm0
0x14003df08  movups  [rsp+248h+var_1A8], xmm0
0x14003df10  mov     [rsp+248h+ThreadId], rdi
0x14003df18  lea     rcx, [rsp+248h+ThreadId]
0x14003df20  call    cs:__imp_VssGetTracingContextPerThread
0x14003df26  test    eax, eax
0x14003df28  js      short loc_14003DF52
0x14003df2a  lea     rcx, [rsp+248h+var_1F8]
0x14003df2f  call    cs:__imp_VssSetTracingContextPerThread
0x14003df35  mov     rcx, [rsp+248h+var_198]
0x14003df3d  test    eax, eax
0x14003df3f  cmovns  rcx, [rsp+248h+ThreadId]
0x14003df48  mov     [rsp+248h+var_198], rcx
0x14003df50  jmp     short loc_14003DF5A
0x14003df52  mov     rcx, [rsp+248h+var_198]
0x14003df5a  test    rcx, rcx
0x14003df5d  jz      short loc_14003DF6D
0x14003df5f  mov     eax, [rcx+30h]
0x14003df62  inc     eax
0x14003df64  mov     [rsp+248h+var_1C8], eax
0x14003df6b  jmp     short loc_14003DF74
0x14003df6d  mov     [rsp+248h+var_1C8], edi
0x14003df74  mov     ebx, 0A0h
0x14003df79  cmp     [rsp+248h+var_1C0], 0FFh
0x14003df84  cmovnz  ebx, [rsp+248h+var_1C0]
0x14003df8c  lea     rcx, [rsp+248h+var_1F8]; this
0x14003df91  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14003df96  test    eax, eax
0x14003df98  jz      short loc_14003DFDE
0x14003df9a  mov     [rsp+248h+var_208], rdi
0x14003df9f  mov     [rsp+248h+var_210], ebx
0x14003dfa3  lea     rax, aEnter; "ENTER"
0x14003dfaa  mov     [rsp+248h+var_218], rax
0x14003dfaf  mov     rax, [rsp+248h+var_1D0]
0x14003dfb4  mov     [rsp+248h+lpThreadId], rax
0x14003dfb9  mov     eax, [rsp+248h+var_1D4]
0x14003dfbd  mov     [rsp+248h+dwCreationFlags], eax
0x14003dfc1  mov     r9d, [rsp+248h+var_1C8]
0x14003dfc9  mov     r8d, [rsp+248h+var_1D8]
0x14003dfce  mov     rdx, [rsp+248h+var_1E0]
0x14003dfd3  mov     rcx, [rsp+248h+var_1E8]
0x14003dfd8  call    cs:__imp_VssTraceMessage
0x14003dfde  lea     rcx, [rsp+248h+var_188]; this
0x14003dfe6  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14003dfeb  nop
0x14003dfec  cmp     cs:?sm_pWriter@CRegistryWriter@@0PEAV1@EA, rdi; CRegistryWriter * CRegistryWriter::sm_pWriter
0x14003dff3  jz      short loc_14003E006
0x14003dff5  lea     rcx, [rsp+248h+var_1F8]; this
0x14003dffa  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14003dfff  xor     eax, eax
0x14003e001  jmp     loc_14003E28B
0x14003e006  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003e00d  mov     ecx, 28h ; '('; unsigned __int64
0x14003e012  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14003e017  mov     [rsp+248h+arg_8], rax
0x14003e01f  test    rax, rax
0x14003e022  jz      short loc_14003E043
0x14003e024  mov     [rax+8], rdi
0x14003e028  lea     rcx, ??_7CRegistryWriter@@6B@; const CRegistryWriter::`vftable'
0x14003e02f  mov     [rax], rcx
0x14003e032  mov     [rax+18h], rdi
0x14003e036  lea     rcx, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x14003e03d  mov     [rax+10h], rcx
0x14003e041  jmp     short loc_14003E046
0x14003e043  mov     rax, rdi
0x14003e046  mov     cs:?sm_pWriter@CRegistryWriter@@0PEAV1@EA, rax; CRegistryWriter * CRegistryWriter::sm_pWriter
0x14003e04d  test    rax, rax
0x14003e050  jnz     short loc_14003E0C8
0x14003e052  mov     [rsp+248h+var_188], rsi
0x14003e05a  mov     [rsp+248h+var_180], r14
0x14003e062  mov     [rsp+248h+var_178], r15
0x14003e06a  mov     [rsp+248h+var_170], 1F0h
0x14003e075  mov     [rsp+248h+var_16C], 4
0x14003e080  mov     [rsp+248h+var_168], 0FFh
0x14003e08b  mov     [rsp+248h+var_E8], 1000000h
0x14003e096  xor     edx, edx; Val
0x14003e098  lea     r8d, [rax+78h]; Size
0x14003e09c  lea     rcx, [rsp+248h+var_160]; void *
0x14003e0a4  call    memset_0
0x14003e0a9  lea     r9, aAllocationOfCr; "Allocation of CRegistryWriter object fa"...
0x14003e0b0  mov     r8d, 8007000Eh
0x14003e0b6  lea     rdx, [rsp+248h+var_188]
0x14003e0be  lea     rcx, [rsp+248h+var_1F8]
0x14003e0c3  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14003e0c8  mov     dword ptr [rsp+248h+ThreadId], edi
0x14003e0cf  lea     rax, [rsp+248h+ThreadId]
0x14003e0d7  mov     [rsp+248h+lpThreadId], rax; lpThreadId
0x14003e0dc  mov     [rsp+248h+dwCreationFlags], edi; dwCreationFlags
0x14003e0e0  xor     r9d, r9d; lpParameter
0x14003e0e3  lea     r8, ?InitializeThreadFunc@CRegistryWriter@@CAKPEAX@Z; lpStartAddress
0x14003e0ea  mov     edx, 40000h; dwStackSize
0x14003e0ef  xor     ecx, ecx; lpThreadAttributes
0x14003e0f1  call    cs:__imp_CreateThread
0x14003e0f7  mov     rbx, rax
0x14003e0fa  test    rax, rax
0x14003e0fd  jnz     short loc_14003E17A
0x14003e0ff  call    cs:__imp_GetLastError
0x14003e105  mov     ebx, eax
0x14003e107  mov     [rsp+248h+var_188], rsi
0x14003e10f  mov     [rsp+248h+var_180], r14
0x14003e117  mov     [rsp+248h+var_178], r15
0x14003e11f  mov     [rsp+248h+var_170], 201h
0x14003e12a  mov     [rsp+248h+var_16C], 4
0x14003e135  mov     [rsp+248h+var_168], 0FFh
0x14003e140  mov     [rsp+248h+var_E8], 1000000h
0x14003e14b  xor     edx, edx; Val
0x14003e14d  lea     r8d, [rdx+78h]; Size
0x14003e151  lea     rcx, [rsp+248h+var_160]; void *
0x14003e159  call    memset_0
0x14003e15e  mov     r9d, ebx
0x14003e161  lea     r8, aCreatethreadFa; "CreateThread failed with error %d"
0x14003e168  lea     rdx, [rsp+248h+var_188]
0x14003e170  lea     rcx, [rsp+248h+var_1F8]
0x14003e175  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x14003e17a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14003e17d  mov     rcx, rbx; hHandle
0x14003e180  call    cs:__imp_WaitForSingleObject
0x14003e186  mov     rcx, rbx; hObject
0x14003e189  call    cs:__imp_CloseHandle
0x14003e18f  mov     eax, cs:?sm_hrInitialize@CRegistryWriter@@0JA; long CRegistryWriter::sm_hrInitialize
0x14003e195  mov     [rsp+248h+dwMessageId], eax
0x14003e199  jmp     short loc_14003E1B8
0x14003e19b  jmp     short loc_14003E1A1
0x14003e19d  jmp     short loc_14003E1A1
0x14003e19f  jmp     short $+2
0x14003e1a1  xor     edi, edi
0x14003e1a3  lea     r15, aWrtregrc; "WRTREGRC"
0x14003e1aa  lea     r14, aCregistrywrite_1; "CRegistryWriter::CreateWriter"
0x14003e1b1  lea     rsi, aBaseStorVssMod_31; "base\\stor\\vss\\modules\\writers\\regw"...
0x14003e1b8  cmp     [rsp+248h+dwMessageId], edi
0x14003e1bc  jge     loc_14003E27B
0x14003e1c2  mov     rcx, cs:?sm_pWriter@CRegistryWriter@@0PEAV1@EA; CRegistryWriter * CRegistryWriter::sm_pWriter
0x14003e1c9  test    rcx, rcx
0x14003e1cc  jz      short loc_14003E1E5
0x14003e1ce  mov     rax, [rcx]
0x14003e1d1  mov     edx, 1
0x14003e1d6  mov     rax, [rax]
0x14003e1d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e1de  mov     cs:?sm_pWriter@CRegistryWriter@@0PEAV1@EA, rdi; CRegistryWriter * CRegistryWriter::sm_pWriter
0x14003e1e5  mov     [rsp+248h+var_188], rsi
0x14003e1ed  mov     [rsp+248h+var_180], r14
0x14003e1f5  mov     [rsp+248h+var_178], r15
0x14003e1fd  mov     [rsp+248h+var_170], 214h
0x14003e208  mov     [rsp+248h+var_16C], 4
0x14003e213  mov     [rsp+248h+var_168], 0FFh
0x14003e21e  mov     [rsp+248h+var_E8], 1000000h
0x14003e229  xor     edx, edx; Val
0x14003e22b  lea     r8d, [rdx+78h]; Size
0x14003e22f  lea     rcx, [rsp+248h+var_160]; void *
0x14003e237  call    memset_0
0x14003e23c  mov     r8d, [rsp+248h+dwMessageId]; dwMessageId
0x14003e241  lea     rdx, [rsp+248h+var_C8]; this
0x14003e249  lea     rcx, [rsp+248h+var_188]; struct CVssDebugInfo *
0x14003e251  call    ??6CVssDebugInfo@@QEAA?AU0@J@Z; CVssDebugInfo::operator<<(long)
0x14003e256  mov     r9d, 1
0x14003e25c  mov     r8, rax
0x14003e25f  mov     edx, 3036h
0x14003e264  lea     rcx, [rsp+248h+var_1F8]
0x14003e269  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x14003e26e  lea     rcx, [rsp+248h+var_188]; this
0x14003e276  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14003e27b  mov     ebx, [rsp+248h+dwMessageId]
0x14003e27f  lea     rcx, [rsp+248h+var_1F8]; this
0x14003e284  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14003e289  mov     eax, ebx
0x14003e28b  lea     r11, [rsp+248h+var_18]
0x14003e293  mov     rbx, [r11+30h]
0x14003e297  mov     rsi, [r11+38h]
0x14003e29b  mov     rsp, r11
0x14003e29e  pop     r15
0x14003e2a0  pop     r14
0x14003e2a2  pop     rdi
0x14003e2a3  retn
```

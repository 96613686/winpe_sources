# CVssAsrWriterBackup::CreateWriter(void)

- ea: `0x1400041bc`
- end: `0x14000467e`
- name: `?CreateWriter@CVssAsrWriterBackup@@SAJXZ`
- size: `1218`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140028d60`

## callees

- `0x140003d7c`
- `0x1400041bc`
- `0x140006020`
- `0x1400137c0`
- `0x140013cb0`
- `0x140015e38`
- `0x140019e30`
- `0x14003c160`
- `0x140070fcc`
- `0x14009197c`
- `0x1400921dc`
- `0x1400921e8`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004608`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004584`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004584`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140004576`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140004576`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004611`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004611`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140004283`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140004283`
- `VssTrace!__imp_VssTraceMessage` at `0x140004392`
- `VssTrace!__imp_VssTraceMessage` at `0x140004392`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400042e4`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400042e4`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400042d5`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400042d5`

## string_xrefs

- `0x1400041e0`: `CVssAsrWriterBackup::CreateWriter`
- `0x1400041d2`: `base\stor\vss\modules\writers\asrwriter.cxx`
- `0x14000452f`: `CVssAsrAPIBackup::CreateObject`
- `0x1400045e3`: `CreateThread failed with error %d`
- `0x140004464`: `Allocation of CVssAsrWriterBackup object failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 CVssAsrWriterBackup::CreateWriter(void)
{
  int v0; // eax
  const unsigned __int16 **v1; // rcx
  int v2; // ebx
  const unsigned __int16 **v4; // rax
  const struct _GUID *v5; // rcx
  __int64 v6; // rdx
  int Object; // ebx
  CVssDebugInfo *v8; // rax
  HANDLE v9; // rax
  void *v10; // rbx
  DWORD LastError; // ebx
  unsigned int v12; // ebx
  unsigned __int16 i; // cx
  __int64 dwCreationFlags; // [rsp+20h] [rbp-248h]
  int pExceptionObject; // [rsp+50h] [rbp-218h] BYREF
  unsigned __int64 v16; // [rsp+60h] [rbp-208h] BYREF
  int v17; // [rsp+68h] [rbp-200h]
  const unsigned __int16 *v18; // [rsp+70h] [rbp-1F8h]
  const unsigned __int16 *v19; // [rsp+78h] [rbp-1F0h]
  unsigned int v20; // [rsp+80h] [rbp-1E8h]
  unsigned int v21; // [rsp+84h] [rbp-1E4h]
  const unsigned __int16 *v22; // [rsp+88h] [rbp-1E0h]
  unsigned int v23; // [rsp+90h] [rbp-1D8h]
  DWORD TickCount; // [rsp+94h] [rbp-1D4h]
  int v25; // [rsp+98h] [rbp-1D0h]
  __int128 v26; // [rsp+A0h] [rbp-1C8h]
  __int128 v27; // [rsp+B0h] [rbp-1B8h]
  const unsigned __int16 **v28; // [rsp+C0h] [rbp-1A8h]
  const unsigned __int16 *v29; // [rsp+D0h] [rbp-198h] BYREF
  const unsigned __int16 *v30; // [rsp+D8h] [rbp-190h]
  const unsigned __int16 *v31; // [rsp+E0h] [rbp-188h]
  __int64 v32; // [rsp+E8h] [rbp-180h]
  int v33; // [rsp+F0h] [rbp-178h]
  _QWORD v34[15]; // [rsp+F8h] [rbp-170h] BYREF
  int v35; // [rsp+170h] [rbp-F8h]
  int v36; // [rsp+178h] [rbp-F0h] BYREF
  const std::exception *v37; // [rsp+180h] [rbp-E8h] BYREF
  _com_error *v38; // [rsp+188h] [rbp-E0h] BYREF
  char v39[216]; // [rsp+190h] [rbp-D8h] BYREF
  DWORD ThreadId; // [rsp+270h] [rbp+8h] BYREF
  const unsigned __int16 **v41; // [rsp+278h] [rbp+10h] BYREF

  v29 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
  v30 = L"CVssAsrWriterBackup::CreateWriter";
  v31 = L"WRTASRWC";
  v32 = 0x4000002AELL;
  v33 = 255;
  v35 = 0x1000000;
  memset_0(v34, 0, sizeof(v34));
  v17 = 0;
  v22 = L"CVssAsrWriterBackup::CreateWriter";
  v18 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
  v19 = L"WRTASRWC";
  v20 = 686;
  v21 = 4;
  TickCount = GetTickCount();
  v25 = 255;
  v16 = 0xFFFFFFFF00000000uLL;
  v28 = 0;
  v26 = 0;
  v27 = 0;
  v41 = 0;
  if ( (int)VssGetTracingContextPerThread(&v41) < 0 )
  {
    v1 = v28;
  }
  else
  {
    v0 = VssSetTracingContextPerThread(&v16);
    v1 = v28;
    if ( v0 >= 0 )
      v1 = v41;
    v28 = v1;
  }
  if ( v1 )
    v23 = *((_DWORD *)v1 + 12) + 1;
  else
    v23 = 0;
  v2 = 160;
  if ( v25 != 255 )
    v2 = v25;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v16) )
    VssTraceMessage(v18, v19, v20, v23, v21, v22, L"ENTER", v2, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v29);
  ThreadId = 0;
  if ( CVssAsrWriterBackup::sm_pAsrWriterBackup )
  {
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v16);
    return 0;
  }
  else
  {
    v4 = (const unsigned __int16 **)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v41 = v4;
    if ( v4 )
    {
      v4[1] = 0;
      *v4 = (const unsigned __int16 *)&CVssAsrWriterBackup::`vftable';
      ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(v4 + 2);
      *(_DWORD *)(v6 + 24) = 0;
    }
    else
    {
      v6 = 0;
    }
    try
    {
      CVssAsrWriterBackup::sm_pAsrWriterBackup = (CVssWriter *)v6;
      if ( !v6 )
      {
        v29 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
        v30 = L"CVssAsrWriterBackup::CreateWriter";
        v31 = L"WRTASRWC";
        v32 = 0x4000002C0LL;
        v33 = 255;
        v35 = 0x1000000;
        memset_0(v34, 0, sizeof(v34));
        CVssFunctionTracer::Throw(&v16, &v29, 2147942414LL, L"Allocation of CVssAsrWriterBackup object failed.");
      }
      Object = CVssAsrAPIBackup::CreateObject(v5, (struct IUnknown **)(v6 + 16));
      v17 = Object;
      v29 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
      v30 = L"CVssAsrWriterBackup::CreateWriter";
      v31 = L"WRTASRWC";
      v32 = 0x4000002C4LL;
      v33 = 255;
      v35 = 0x1000000;
      memset_0(v34, 0, sizeof(v34));
      v41 = &v29;
      if ( Object < 0 )
      {
        if ( Object == -2147418113 )
        {
          pExceptionObject = -2147418113;
          throw (long *)&pExceptionObject;
        }
        v8 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v39, (const struct CVssDebugInfo *)&v29);
        CVssFunctionTracer::TranslateError(&v16, v8, (unsigned int)Object, L"CVssAsrAPIBackup::CreateObject");
      }
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v29);
      v9 = CreateThread(0, 0x40000u, CVssAsrWriterBackup::InitializeThreadFunc, 0, 0, &ThreadId);
      v10 = v9;
      if ( !v9 )
      {
        LastError = GetLastError();
        v29 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
        v30 = L"CVssAsrWriterBackup::CreateWriter";
        v31 = L"WRTASRWC";
        v32 = 0x4000002CALL;
        v33 = 255;
        v35 = 0x1000000;
        memset_0(v34, 0, sizeof(v34));
        LODWORD(dwCreationFlags) = LastError;
        CVssFunctionTracer::Throw(&v16, &v29, 2147549183LL, L"CreateThread failed with error %d", dwCreationFlags);
      }
      WaitForSingleObject(v9, 0xFFFFFFFF);
      CloseHandle(v10);
      v17 = CVssAsrWriterBackup::sm_hrInitialize;
    }
    catch ( long v36 )
    {
      CVssFunctionTracer::HandleHresultException(
        (CVssFunctionTracer *)&v16,
        v36,
        L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx",
        L"WRTASRWC",
        L"CVssAsrWriterBackup::CreateWriter",
        0x2D4u,
        v21);
    }
    catch ( _com_error *v38 )
    {
      CVssFunctionTracer::HandleComException(
        (CVssFunctionTracer *)&v16,
        v38,
        L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx",
        L"WRTASRWC",
        L"CVssAsrWriterBackup::CreateWriter",
        0x2D4u,
        v21);
    }
    catch ( std::bad_alloc )
    {
      CVssFunctionTracer::HandleStdBadAllocException(
        (CVssFunctionTracer *)&v16,
        L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx",
        L"WRTASRWC",
        L"CVssAsrWriterBackup::CreateWriter",
        0x2D4u,
        v21);
    }
    catch ( const std::exception *v37 )
    {
      CVssFunctionTracer::HandleStdGenericException(
        (CVssFunctionTracer *)&v16,
        v37,
        L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx",
        L"WRTASRWC",
        L"CVssAsrWriterBackup::CreateWriter",
        0x2D4u,
        v21);
    }
    catch ( ... )
    {
      v17 = -2147418113;
      v29 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
      v30 = L"CVssAsrWriterBackup::CreateWriter";
      v31 = L"WRTASRWC";
      v32 = 724;
      v33 = 255;
      v35 = 0x1000000;
      for ( i = 0; i < 0xFu; ++i )
        v34[i] = 0;
      CVssFunctionTracer::Trace(&v16, &v29, L"Exception caught!");
    }
    if ( v17 < 0 && CVssAsrWriterBackup::sm_pAsrWriterBackup )
    {
      (**(void (__fastcall ***)(CVssWriter *, __int64))CVssAsrWriterBackup::sm_pAsrWriterBackup)(
        CVssAsrWriterBackup::sm_pAsrWriterBackup,
        1);
      CVssAsrWriterBackup::sm_pAsrWriterBackup = 0;
    }
    v12 = v17;
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v16);
    return v12;
  }
}

```

## disassembly

```asm
0x1400041bc  mov     rax, rsp
0x1400041bf  mov     [rax+20h], rbx
0x1400041c3  push    rsi
0x1400041c4  push    rdi
0x1400041c5  push    r12
0x1400041c7  push    r14
0x1400041c9  push    r15
0x1400041cb  sub     rsp, 240h
0x1400041d2  lea     r14, aBaseStorVssMod_7; "base\\stor\\vss\\modules\\writers\\asrw"...
0x1400041d9  mov     [rax-198h], r14
0x1400041e0  lea     r15, aCvssasrwriterb_4; "CVssAsrWriterBackup::CreateWriter"
0x1400041e7  mov     [rax-190h], r15
0x1400041ee  lea     r12, aWrtasrwc; "WRTASRWC"
0x1400041f5  mov     [rax-188h], r12
0x1400041fc  mov     dword ptr [rax-180h], 2AEh
0x140004206  mov     dword ptr [rax-17Ch], 4
0x140004210  mov     esi, 0FFh
0x140004215  mov     [rax-178h], esi
0x14000421b  xor     edi, edi
0x14000421d  mov     dword ptr [rax-0F8h], 1000000h
0x140004227  xor     edx, edx; Val
0x140004229  lea     r8d, [rdi+78h]; Size
0x14000422d  lea     rcx, [rax-170h]; void *
0x140004234  call    memset_0
0x140004239  mov     [rsp+268h+var_200], edi
0x14000423d  mov     rax, [rsp+268h+var_190]
0x140004245  mov     [rsp+268h+var_1E0], rax
0x14000424d  mov     rax, [rsp+268h+var_198]
0x140004255  mov     [rsp+268h+var_1F8], rax
0x14000425a  mov     rax, [rsp+268h+var_188]
0x140004262  mov     [rsp+268h+var_1F0], rax
0x140004267  mov     eax, [rsp+268h+var_180]
0x14000426e  mov     [rsp+268h+var_1E8], eax
0x140004275  mov     eax, [rsp+268h+var_17C]
0x14000427c  mov     [rsp+268h+var_1E4], eax
0x140004283  call    cs:__imp_GetTickCount
0x140004289  mov     [rsp+268h+var_1D4], eax
0x140004290  mov     [rsp+268h+var_204], 0FFFFFFFFh
0x140004298  mov     eax, [rsp+268h+var_178]
0x14000429f  mov     [rsp+268h+var_1D0], eax
0x1400042a6  mov     [rsp+268h+var_208], edi
0x1400042aa  mov     [rsp+268h+var_1A8], rdi
0x1400042b2  xorps   xmm0, xmm0
0x1400042b5  movups  [rsp+268h+var_1C8], xmm0
0x1400042bd  movups  [rsp+268h+var_1B8], xmm0
0x1400042c5  mov     [rsp+268h+arg_8], rdi
0x1400042cd  lea     rcx, [rsp+268h+arg_8]
0x1400042d5  call    cs:__imp_VssGetTracingContextPerThread
0x1400042db  test    eax, eax
0x1400042dd  js      short loc_140004307
0x1400042df  lea     rcx, [rsp+268h+var_208]
0x1400042e4  call    cs:__imp_VssSetTracingContextPerThread
0x1400042ea  mov     rcx, [rsp+268h+var_1A8]
0x1400042f2  test    eax, eax
0x1400042f4  cmovns  rcx, [rsp+268h+arg_8]
0x1400042fd  mov     [rsp+268h+var_1A8], rcx
0x140004305  jmp     short loc_14000430F
0x140004307  mov     rcx, [rsp+268h+var_1A8]
0x14000430f  test    rcx, rcx
0x140004312  jz      short loc_140004322
0x140004314  mov     eax, [rcx+30h]
0x140004317  inc     eax
0x140004319  mov     [rsp+268h+var_1D8], eax
0x140004320  jmp     short loc_140004329
0x140004322  mov     [rsp+268h+var_1D8], edi
0x140004329  mov     ebx, 0A0h
0x14000432e  cmp     [rsp+268h+var_1D0], esi
0x140004335  cmovnz  ebx, [rsp+268h+var_1D0]
0x14000433d  lea     rcx, [rsp+268h+var_208]; this
0x140004342  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140004347  test    eax, eax
0x140004349  jz      short loc_140004398
0x14000434b  mov     [rsp+268h+var_228], rdi
0x140004350  mov     [rsp+268h+var_230], ebx
0x140004354  lea     rax, aEnter; "ENTER"
0x14000435b  mov     [rsp+268h+var_238], rax
0x140004360  mov     rax, [rsp+268h+var_1E0]
0x140004368  mov     [rsp+268h+lpThreadId], rax
0x14000436d  mov     eax, [rsp+268h+var_1E4]
0x140004374  mov     dword ptr [rsp+268h+dwCreationFlags], eax
0x140004378  mov     r9d, [rsp+268h+var_1D8]
0x140004380  mov     r8d, [rsp+268h+var_1E8]
0x140004388  mov     rdx, [rsp+268h+var_1F0]
0x14000438d  mov     rcx, [rsp+268h+var_1F8]
0x140004392  call    cs:__imp_VssTraceMessage
0x140004398  lea     rcx, [rsp+268h+var_198]; this
0x1400043a0  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x1400043a5  nop
0x1400043a6  mov     [rsp+268h+ThreadId], edi
0x1400043ad  cmp     cs:?sm_pAsrWriterBackup@CVssAsrWriterBackup@@0PEAV1@EA, rdi; CVssAsrWriterBackup * CVssAsrWriterBackup::sm_pAsrWriterBackup
0x1400043b4  jz      short loc_1400043C7
0x1400043b6  lea     rcx, [rsp+268h+var_208]; this
0x1400043bb  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1400043c0  xor     eax, eax
0x1400043c2  jmp     loc_140004666
0x1400043c7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400043ce  mov     ecx, 20h ; ' '; unsigned __int64
0x1400043d3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400043d8  mov     rdx, rax
0x1400043db  mov     [rsp+268h+arg_8], rax
0x1400043e3  test    rax, rax
0x1400043e6  jz      short loc_140004404
0x1400043e8  mov     [rax+8], rdi
0x1400043ec  lea     rax, ??_7CVssAsrWriterBackup@@6B@; const CVssAsrWriterBackup::`vftable'
0x1400043f3  mov     [rdx], rax
0x1400043f6  lea     rcx, [rdx+10h]
0x1400043fa  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x1400043ff  mov     [rdx+18h], edi
0x140004402  jmp     short loc_140004407
0x140004404  mov     rdx, rdi; Val
0x140004407  mov     cs:?sm_pAsrWriterBackup@CVssAsrWriterBackup@@0PEAV1@EA, rdx; CVssAsrWriterBackup * CVssAsrWriterBackup::sm_pAsrWriterBackup
0x14000440e  test    rdx, rdx
0x140004411  jnz     short loc_140004483
0x140004413  mov     [rsp+268h+var_198], r14
0x14000441b  mov     [rsp+268h+var_190], r15
0x140004423  mov     [rsp+268h+var_188], r12
0x14000442b  mov     [rsp+268h+var_180], 2C0h
0x140004436  mov     [rsp+268h+var_17C], 4
0x140004441  mov     [rsp+268h+var_178], esi
0x140004448  mov     [rsp+268h+var_F8], 1000000h
0x140004453  lea     r8d, [rdx+78h]; Size
0x140004457  lea     rcx, [rsp+268h+var_170]; void *
0x14000445f  call    memset_0
0x140004464  lea     r9, aAllocationOfCv; "Allocation of CVssAsrWriterBackup objec"...
0x14000446b  mov     r8d, 8007000Eh
0x140004471  lea     rdx, [rsp+268h+var_198]
0x140004479  lea     rcx, [rsp+268h+var_208]
0x14000447e  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140004483  add     rdx, 10h; struct IUnknown **
0x140004487  call    ?CreateObject@CVssAsrAPIBackup@@SAJAEBU_GUID@@PEAPEAUIUnknown@@@Z; CVssAsrAPIBackup::CreateObject(_GUID const &,IUnknown * *)
0x14000448c  mov     ebx, eax
0x14000448e  mov     [rsp+268h+var_200], eax
0x140004492  mov     [rsp+268h+var_198], r14
0x14000449a  mov     [rsp+268h+var_190], r15
0x1400044a2  mov     [rsp+268h+var_188], r12
0x1400044aa  mov     [rsp+268h+var_180], 2C4h
0x1400044b5  mov     [rsp+268h+var_17C], 4
0x1400044c0  mov     [rsp+268h+var_178], esi
0x1400044c7  mov     [rsp+268h+var_F8], 1000000h
0x1400044d2  xor     edx, edx; Val
0x1400044d4  lea     r8d, [rdx+78h]; Size
0x1400044d8  lea     rcx, [rsp+268h+var_170]; void *
0x1400044e0  call    memset_0
0x1400044e5  lea     rax, [rsp+268h+var_198]
0x1400044ed  mov     [rsp+268h+arg_8], rax
0x1400044f5  test    ebx, ebx
0x1400044f7  jns     short loc_140004547
0x1400044f9  mov     r8d, 8000FFFFh
0x1400044ff  cmp     ebx, r8d
0x140004502  jnz     short loc_14000451A
0x140004504  mov     [rsp+268h+pExceptionObject], r8d
0x140004509  lea     rdx, _TI1J; pThrowInfo
0x140004510  lea     rcx, [rsp+268h+pExceptionObject]; pExceptionObject
0x140004515  call    _CxxThrowException_0
0x14000451a  lea     rdx, [rsp+268h+var_198]; struct CVssDebugInfo *
0x140004522  lea     rcx, [rsp+268h+var_D8]; this
0x14000452a  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x14000452f  lea     r9, aCvssasrapiback_5; "CVssAsrAPIBackup::CreateObject"
0x140004536  mov     r8d, ebx
0x140004539  mov     rdx, rax
0x14000453c  lea     rcx, [rsp+268h+var_208]
0x140004541  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
0x140004547  lea     rcx, [rsp+268h+var_198]; this
0x14000454f  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140004554  lea     rax, [rsp+268h+ThreadId]
0x14000455c  mov     [rsp+268h+lpThreadId], rax; lpThreadId
0x140004561  mov     dword ptr [rsp+268h+dwCreationFlags], edi; dwCreationFlags
0x140004565  xor     r9d, r9d; lpParameter
0x140004568  lea     r8, ?InitializeThreadFunc@CVssAsrWriterBackup@@CAKPEAX@Z; lpStartAddress
0x14000456f  mov     edx, 40000h; dwStackSize
0x140004574  xor     ecx, ecx; lpThreadAttributes
0x140004576  call    cs:__imp_CreateThread
0x14000457c  mov     rbx, rax
0x14000457f  test    rax, rax
0x140004582  jnz     short loc_140004602
0x140004584  call    cs:__imp_GetLastError
0x14000458a  mov     ebx, eax
0x14000458c  mov     [rsp+268h+var_198], r14
0x140004594  mov     [rsp+268h+var_190], r15
0x14000459c  mov     [rsp+268h+var_188], r12
0x1400045a4  mov     [rsp+268h+var_180], 2CAh
0x1400045af  mov     [rsp+268h+var_17C], 4
0x1400045ba  mov     [rsp+268h+var_178], esi
0x1400045c1  mov     [rsp+268h+var_F8], 1000000h
0x1400045cc  xor     edx, edx; Val
0x1400045ce  lea     r8d, [rdx+78h]; Size
0x1400045d2  lea     rcx, [rsp+268h+var_170]; void *
0x1400045da  call    memset_0
0x1400045df  mov     dword ptr [rsp+268h+dwCreationFlags], ebx
0x1400045e3  lea     r9, aCreatethreadFa; "CreateThread failed with error %d"
0x1400045ea  mov     r8d, 8000FFFFh
0x1400045f0  lea     rdx, [rsp+268h+var_198]
0x1400045f8  lea     rcx, [rsp+268h+var_208]
0x1400045fd  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140004602  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140004605  mov     rcx, rbx; hHandle
0x140004608  call    cs:__imp_WaitForSingleObject
0x14000460e  mov     rcx, rbx; hObject
0x140004611  call    cs:__imp_CloseHandle
0x140004617  mov     eax, cs:?sm_hrInitialize@CVssAsrWriterBackup@@0JA; long CVssAsrWriterBackup::sm_hrInitialize
0x14000461d  mov     [rsp+268h+var_200], eax
0x140004621  jmp     short loc_14000462D
0x140004623  jmp     short loc_14000462B
0x140004625  jmp     short loc_14000462B
0x140004627  jmp     short loc_14000462B
0x140004629  jmp     short $+2
0x14000462b  xor     edi, edi
0x14000462d  cmp     [rsp+268h+var_200], edi
0x140004631  jge     short loc_140004656
0x140004633  mov     rcx, cs:?sm_pAsrWriterBackup@CVssAsrWriterBackup@@0PEAV1@EA; CVssAsrWriterBackup * CVssAsrWriterBackup::sm_pAsrWriterBackup
0x14000463a  test    rcx, rcx
0x14000463d  jz      short loc_140004656
0x14000463f  mov     rax, [rcx]
0x140004642  mov     edx, 1
0x140004647  mov     rax, [rax]
0x14000464a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000464f  mov     cs:?sm_pAsrWriterBackup@CVssAsrWriterBackup@@0PEAV1@EA, rdi; CVssAsrWriterBackup * CVssAsrWriterBackup::sm_pAsrWriterBackup
0x140004656  mov     ebx, [rsp+268h+var_200]
0x14000465a  lea     rcx, [rsp+268h+var_208]; this
0x14000465f  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140004664  mov     eax, ebx
0x140004666  mov     rbx, [rsp+268h+arg_18]
0x14000466e  add     rsp, 240h
0x140004675  pop     r15
0x140004677  pop     r14
0x140004679  pop     r12
0x14000467b  pop     rdi
0x14000467c  pop     rsi
0x14000467d  retn
```

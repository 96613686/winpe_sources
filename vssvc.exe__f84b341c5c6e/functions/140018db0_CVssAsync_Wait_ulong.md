# CVssAsync::Wait(ulong)

- ea: `0x140018db0`
- end: `0x140019403`
- name: `?Wait@CVssAsync@@UEAAJK@Z`
- size: `1619`
- prototype: `int(CVssAsync *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140001d54`
- `0x1400138e0`
- `0x140013cb0`
- `0x140015e38`
- `0x140018db0`
- `0x14001940c`
- `0x140049ec4`
- `0x1400921dc`
- `0x1400cda78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1400191aa`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1400191aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400191b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001925d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400191b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001925d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140018e71`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001931e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140018e71`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001931e`
- `VssTrace!__imp_VssTraceMessage` at `0x140018f7f`
- `VssTrace!__imp_VssTraceMessage` at `0x140018f7f`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140018ed2`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400193e9`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140018ed2`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400193e9`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140018ec3`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140018ec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018f9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140019307`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018f9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140019307`

## string_xrefs

- `0x1400190cd`: `The client process is not running under an administrator account or does not have backup privilege enabled`
- `0x140019175`: `Invalid hThread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVssAsync::Wait(PSECURITY_DESCRIPTOR *this, DWORD a2)
{
  int v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // r15d
  unsigned int v7; // ebx
  bool v8; // dl
  void *v9; // rcx
  __int64 i; // rbx
  DWORD LastError; // ebx
  PSECURITY_DESCRIPTOR v12; // rdi
  DWORD v13; // ebx
  unsigned int v14; // r12d
  __int64 j; // rbx
  DWORD v16; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-1A8h]
  BOOL bAlertablea[2]; // [rsp+20h] [rbp-1A8h]
  __int64 v20; // [rsp+28h] [rbp-1A0h]
  __int64 v21; // [rsp+30h] [rbp-198h]
  __int64 v22; // [rsp+38h] [rbp-190h]
  __int64 v23; // [rsp+40h] [rbp-188h]
  _DWORD v24[2]; // [rsp+50h] [rbp-178h] BYREF
  int v25; // [rsp+58h] [rbp-170h]
  const unsigned __int16 *v26; // [rsp+60h] [rbp-168h]
  const unsigned __int16 *v27; // [rsp+68h] [rbp-160h]
  unsigned int v28; // [rsp+70h] [rbp-158h]
  unsigned int v29; // [rsp+74h] [rbp-154h]
  const unsigned __int16 *v30; // [rsp+78h] [rbp-150h]
  unsigned int v31; // [rsp+80h] [rbp-148h]
  DWORD TickCount; // [rsp+84h] [rbp-144h]
  unsigned int v33; // [rsp+88h] [rbp-140h]
  LPVOID v34[2]; // [rsp+90h] [rbp-138h]
  __int128 v35; // [rsp+A0h] [rbp-128h]
  __int64 v36; // [rsp+B0h] [rbp-118h]
  const unsigned __int16 *v37; // [rsp+C0h] [rbp-108h] BYREF
  const unsigned __int16 *v38; // [rsp+C8h] [rbp-100h]
  const unsigned __int16 *v39; // [rsp+D0h] [rbp-F8h]
  int v40; // [rsp+D8h] [rbp-F0h]
  int v41; // [rsp+DCh] [rbp-ECh]
  int v42; // [rsp+E0h] [rbp-E8h]
  LPVOID pv[15]; // [rsp+E8h] [rbp-E0h] BYREF
  int v44; // [rsp+160h] [rbp-68h]
  HANDLE Handles; // [rsp+168h] [rbp-60h] BYREF
  PSECURITY_DESCRIPTOR v46; // [rsp+170h] [rbp-58h]
  int v47; // [rsp+178h] [rbp-50h] BYREF
  _com_error *v48; // [rsp+180h] [rbp-48h] BYREF
  const std::exception *v49; // [rsp+188h] [rbp-40h] BYREF
  __int64 v50; // [rsp+1D0h] [rbp+8h] BYREF

  v37 = L"base\\stor\\vss\\modules\\coord\\src\\async.cxx";
  v38 = L"CVssAsync::Wait";
  v39 = L"CORASYNC";
  v40 = 496;
  v41 = 1;
  v42 = 255;
  v44 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v25 = 0;
  v30 = L"CVssAsync::Wait";
  v26 = L"base\\stor\\vss\\modules\\coord\\src\\async.cxx";
  v27 = L"CORASYNC";
  v28 = 496;
  v29 = 1;
  TickCount = GetTickCount();
  v24[1] = -1;
  v33 = 255;
  v24[0] = 0;
  v36 = 0;
  *(_OWORD *)v34 = 0;
  v35 = 0;
  v50 = 0;
  if ( (int)VssGetTracingContextPerThread(&v50) < 0 )
  {
    v5 = v36;
  }
  else
  {
    v4 = VssSetTracingContextPerThread(v24);
    v5 = v36;
    if ( v4 >= 0 )
      v5 = v50;
    v36 = v5;
  }
  if ( v5 )
    v31 = *(_DWORD *)(v5 + 48) + 1;
  else
    v31 = 0;
  v6 = 160;
  v7 = 160;
  if ( v33 != 255 )
    v7 = v33;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v24) )
    VssTraceMessage(v26, v27, v28, v31, v29, v30, L"ENTER", v7, 0);
  if ( HIBYTE(v44) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v9 = pv[i];
      if ( v9 )
      {
        CoTaskMemFree(v9);
        pv[i] = 0;
      }
    }
  }
  try
  {
    if ( *((_BYTE *)this + 216) )
    {
      if ( !CVssSidCollection::IsClientValidRequestor(this + 28) )
      {
        v37 = L"base\\stor\\vss\\modules\\coord\\src\\async.cxx";
        v38 = L"CVssAsync::Wait";
        v39 = L"CORASYNC";
        v40 = 504;
        v41 = 1;
        v42 = 255;
        v44 = 0x1000000;
        memset_0(pv, 0, sizeof(pv));
        CVssFunctionTracer::Throw(
          v24,
          &v37,
          2147942405LL,
          L"The remote client process is not running under a valid user account for requestor");
      }
    }
    else if ( !IsBackupOperator((unsigned int)v9, v8) )
    {
      v37 = L"base\\stor\\vss\\modules\\coord\\src\\async.cxx";
      v38 = L"CVssAsync::Wait";
      v39 = L"CORASYNC";
      v40 = 510;
      v41 = 1;
      v42 = 255;
      v44 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      CVssFunctionTracer::Throw(
        v24,
        &v37,
        2147942405LL,
        L"The client process is not running under an administrator account or does not have backup privilege enabled");
    }
    Handles = this[3];
    v46 = this[44];
    if ( !Handles )
    {
      v37 = L"base\\stor\\vss\\modules\\coord\\src\\async.cxx";
      v38 = L"CVssAsync::Wait";
      v39 = L"CORASYNC";
      v40 = 518;
      v41 = 1;
      v42 = 255;
      v44 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      CVssFunctionTracer::TranslateGenericError(v24, &v37, 2147549183LL, L"Invalid hThread");
    }
    if ( WaitForMultipleObjectsEx(2u, &Handles, 0, a2, 0) == -1 )
    {
      LastError = GetLastError();
      v12 = v46;
      v37 = L"base\\stor\\vss\\modules\\coord\\src\\async.cxx";
      v38 = L"CVssAsync::Wait";
      v39 = L"CORASYNC";
      v40 = 521;
      v41 = 11;
      v42 = 255;
      v44 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      LODWORD(v21) = LastError;
      LODWORD(v20) = a2;
      CVssFunctionTracer::LogGenericWarning(
        v24,
        &v37,
        L"WaitForMultipleObjects(%p,%p, %d) == WAIT_FAILED, GetLastError() == 0x%08lx",
        Handles,
        v12,
        v20,
        v21);
      v13 = GetLastError();
      v37 = L"base\\stor\\vss\\modules\\coord\\src\\async.cxx";
      v38 = L"CVssAsync::Wait";
      v39 = L"CORASYNC";
      v40 = 524;
      v41 = 1;
      v42 = 255;
      v44 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      bAlertablea[0] = v13;
      CVssFunctionTracer::Throw(v24, &v37, 2147754754LL, L"Wait failed. [0x%08lx]", *(_QWORD *)bAlertablea);
    }
  }
  catch ( long v47 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)v24,
      v47,
      L"base\\stor\\vss\\modules\\coord\\src\\async.cxx",
      L"CORASYNC",
      L"CVssAsync::Wait",
      0x20Fu,
      v29);
    v6 = 160;
  }
  catch ( _com_error *v48 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)v24,
      v48,
      L"base\\stor\\vss\\modules\\coord\\src\\async.cxx",
      L"CORASYNC",
      L"CVssAsync::Wait",
      0x20Fu,
      v29);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)v24,
      L"base\\stor\\vss\\modules\\coord\\src\\async.cxx",
      L"CORASYNC",
      L"CVssAsync::Wait",
      0x20Fu,
      v29);
    v6 = 160;
  }
  catch ( const std::exception *v49 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)v24,
      v49,
      L"base\\stor\\vss\\modules\\coord\\src\\async.cxx",
      L"CORASYNC",
      L"CVssAsync::Wait",
      0x20Fu,
      v29);
  }
  v14 = v25;
  for ( j = 0; j != 4; ++j )
  {
    CoTaskMemFree(v34[j]);
    v34[j] = 0;
  }
  v16 = GetTickCount() - TickCount;
  if ( v33 != 255 )
    v6 = v33;
  LODWORD(v23) = v16;
  LODWORD(v22) = v16 % 0x3E8;
  LODWORD(v21) = v16 / 0x3E8 % 0x3C;
  LODWORD(v20) = v16 / 0xEA60 % 0x3C;
  bAlertable[0] = v16 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v24,
    L"EXIT",
    v6,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    *(_QWORD *)bAlertable,
    v20,
    v21,
    v22,
    v23,
    v25);
  VssSetTracingContextPerThread(v36);
  return v14;
}

```

## disassembly

```asm
0x140018db0  mov     r11, rsp
0x140018db3  push    rbx
0x140018db4  push    rsi
0x140018db5  push    rdi
0x140018db6  push    r12
0x140018db8  push    r13
0x140018dba  push    r15
0x140018dbc  sub     rsp, 198h
0x140018dc3  mov     r12d, edx
0x140018dc6  mov     rdi, rcx
0x140018dc9  lea     r13, aBaseStorVssMod_6; "base\\stor\\vss\\modules\\coord\\src\\a"...
0x140018dd0  mov     [r11-108h], r13
0x140018dd7  lea     rax, aCvssasyncWait; "CVssAsync::Wait"
0x140018dde  mov     [r11-100h], rax
0x140018de5  lea     rax, aCorasync; "CORASYNC"
0x140018dec  mov     [r11-0F8h], rax
0x140018df3  mov     [rsp+1C8h+var_F0], 1F0h
0x140018dfe  mov     [rsp+1C8h+var_EC], 1
0x140018e09  mov     [rsp+1C8h+var_E8], 0FFh
0x140018e14  xor     esi, esi
0x140018e16  mov     dword ptr [r11-68h], 1000000h
0x140018e1e  xor     edx, edx; Val
0x140018e20  lea     r8d, [rsi+78h]; Size
0x140018e24  lea     rcx, [r11-0E0h]; void *
0x140018e2b  call    memset_0
0x140018e30  mov     [rsp+1C8h+var_170], esi
0x140018e34  mov     rax, [rsp+1C8h+var_100]
0x140018e3c  mov     [rsp+1C8h+var_150], rax
0x140018e41  mov     rax, [rsp+1C8h+var_108]
0x140018e49  mov     [rsp+1C8h+var_168], rax
0x140018e4e  mov     rax, [rsp+1C8h+var_F8]
0x140018e56  mov     [rsp+1C8h+var_160], rax
0x140018e5b  mov     eax, [rsp+1C8h+var_F0]
0x140018e62  mov     [rsp+1C8h+var_158], eax
0x140018e66  mov     eax, [rsp+1C8h+var_EC]
0x140018e6d  mov     [rsp+1C8h+var_154], eax
0x140018e71  call    cs:__imp_GetTickCount
0x140018e77  mov     [rsp+1C8h+var_144], eax
0x140018e7e  mov     [rsp+1C8h+var_174], 0FFFFFFFFh
0x140018e86  mov     eax, [rsp+1C8h+var_E8]
0x140018e8d  mov     [rsp+1C8h+var_140], eax
0x140018e94  mov     [rsp+1C8h+var_178], esi
0x140018e98  mov     [rsp+1C8h+var_118], rsi
0x140018ea0  xorps   xmm0, xmm0
0x140018ea3  movups  xmmword ptr [rsp+1C8h+var_138], xmm0
0x140018eab  movups  [rsp+1C8h+var_128], xmm0
0x140018eb3  mov     [rsp+1C8h+arg_0], rsi
0x140018ebb  lea     rcx, [rsp+1C8h+arg_0]
0x140018ec3  call    cs:__imp_VssGetTracingContextPerThread
0x140018ec9  test    eax, eax
0x140018ecb  js      short loc_140018EF5
0x140018ecd  lea     rcx, [rsp+1C8h+var_178]
0x140018ed2  call    cs:__imp_VssSetTracingContextPerThread
0x140018ed8  mov     rcx, [rsp+1C8h+var_118]
0x140018ee0  test    eax, eax
0x140018ee2  cmovns  rcx, [rsp+1C8h+arg_0]
0x140018eeb  mov     [rsp+1C8h+var_118], rcx
0x140018ef3  jmp     short loc_140018EFD
0x140018ef5  mov     rcx, [rsp+1C8h+var_118]
0x140018efd  test    rcx, rcx
0x140018f00  jz      short loc_140018F10
0x140018f02  mov     eax, [rcx+30h]
0x140018f05  inc     eax
0x140018f07  mov     [rsp+1C8h+var_148], eax
0x140018f0e  jmp     short loc_140018F17
0x140018f10  mov     [rsp+1C8h+var_148], esi
0x140018f17  mov     r15d, 0A0h
0x140018f1d  mov     ebx, r15d
0x140018f20  cmp     [rsp+1C8h+var_140], 0FFh
0x140018f2b  cmovnz  ebx, [rsp+1C8h+var_140]
0x140018f33  lea     rcx, [rsp+1C8h+var_178]; this
0x140018f38  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140018f3d  test    eax, eax
0x140018f3f  jz      short loc_140018F85
0x140018f41  mov     [rsp+1C8h+var_188], rsi
0x140018f46  mov     dword ptr [rsp+1C8h+var_190], ebx
0x140018f4a  lea     rax, aEnter; "ENTER"
0x140018f51  mov     [rsp+1C8h+var_198], rax
0x140018f56  mov     rax, [rsp+1C8h+var_150]
0x140018f5b  mov     [rsp+1C8h+var_1A0], rax
0x140018f60  mov     eax, [rsp+1C8h+var_154]
0x140018f64  mov     [rsp+1C8h+bAlertable], eax
0x140018f68  mov     r9d, [rsp+1C8h+var_148]
0x140018f70  mov     r8d, [rsp+1C8h+var_158]
0x140018f75  mov     rdx, [rsp+1C8h+var_160]
0x140018f7a  mov     rcx, [rsp+1C8h+var_168]
0x140018f7f  call    cs:__imp_VssTraceMessage
0x140018f85  cmp     [rsp+1C8h+var_65], sil
0x140018f8d  jz      short loc_140018FB6
0x140018f8f  mov     rbx, rsi
0x140018f92  mov     rcx, [rsp+rbx*8+1C8h+pv]; pv
0x140018f9a  test    rcx, rcx
0x140018f9d  jz      short loc_140018FAD
0x140018f9f  call    cs:__imp_CoTaskMemFree
0x140018fa5  mov     [rsp+rbx*8+1C8h+pv], rsi
0x140018fad  inc     rbx
0x140018fb0  cmp     rbx, 0Fh
0x140018fb4  jnz     short loc_140018F92
0x140018fb6  cmp     [rdi+0D8h], sil
0x140018fbd  jz      loc_14001905B
0x140018fc3  lea     rcx, [rdi+0E0h]; this
0x140018fca  call    ?IsClientValidRequestor@CVssSidCollection@@QEAA_NXZ; CVssSidCollection::IsClientValidRequestor(void)
0x140018fcf  test    al, al
0x140018fd1  jnz     loc_1400190EC
0x140018fd7  mov     [rsp+1C8h+var_108], r13
0x140018fdf  lea     r15, aCvssasyncWait; "CVssAsync::Wait"
0x140018fe6  mov     [rsp+1C8h+var_100], r15
0x140018fee  lea     rax, aCorasync; "CORASYNC"
0x140018ff5  mov     [rsp+1C8h+var_F8], rax
0x140018ffd  mov     [rsp+1C8h+var_F0], 1F8h
0x140019008  mov     [rsp+1C8h+var_EC], 1
0x140019013  mov     [rsp+1C8h+var_E8], 0FFh
0x14001901e  mov     dword ptr [rsp+160h], 1000000h
0x140019029  xor     edx, edx; Val
0x14001902b  lea     r8d, [rdx+78h]; Size
0x14001902f  lea     rcx, [rsp+1C8h+pv]; void *
0x140019037  call    memset_0
0x14001903c  lea     r9, aTheRemoteClien; "The remote client process is not runnin"...
0x140019043  mov     r8d, 80070005h
0x140019049  lea     rdx, [rsp+1C8h+var_108]
0x140019051  lea     rcx, [rsp+1C8h+var_178]
0x140019056  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14001905b  call    ?IsBackupOperator@@YA_NXZ; IsBackupOperator(void)
0x140019060  test    al, al
0x140019062  jnz     loc_1400190EC
0x140019068  mov     [rsp+1C8h+var_108], r13
0x140019070  lea     r15, aCvssasyncWait; "CVssAsync::Wait"
0x140019077  mov     [rsp+1C8h+var_100], r15
0x14001907f  lea     rax, aCorasync; "CORASYNC"
0x140019086  mov     [rsp+1C8h+var_F8], rax
0x14001908e  mov     [rsp+1C8h+var_F0], 1FEh
0x140019099  mov     [rsp+1C8h+var_EC], 1
0x1400190a4  mov     [rsp+1C8h+var_E8], 0FFh
0x1400190af  mov     dword ptr [rsp+160h], 1000000h
0x1400190ba  xor     edx, edx; Val
0x1400190bc  lea     r8d, [rdx+78h]; Size
0x1400190c0  lea     rcx, [rsp+1C8h+pv]; void *
0x1400190c8  call    memset_0
0x1400190cd  lea     r9, aTheClientProce_0; "The client process is not running under"...
0x1400190d4  mov     r8d, 80070005h
0x1400190da  lea     rdx, [rsp+1C8h+var_108]
0x1400190e2  lea     rcx, [rsp+1C8h+var_178]
0x1400190e7  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1400190ec  mov     rcx, [rdi+18h]
0x1400190f0  mov     [rsp+1C8h+Handles], rcx
0x1400190f8  mov     rax, [rdi+160h]
0x1400190ff  mov     [rsp+1C8h+var_58], rax
0x140019107  test    rcx, rcx
0x14001910a  jnz     loc_140019194
0x140019110  mov     [rsp+1C8h+var_108], r13
0x140019118  lea     r15, aCvssasyncWait; "CVssAsync::Wait"
0x14001911f  mov     [rsp+1C8h+var_100], r15
0x140019127  lea     rax, aCorasync; "CORASYNC"
0x14001912e  mov     [rsp+1C8h+var_F8], rax
0x140019136  mov     [rsp+1C8h+var_F0], 206h
0x140019141  mov     [rsp+1C8h+var_EC], 1
0x14001914c  mov     [rsp+1C8h+var_E8], 0FFh
0x140019157  mov     dword ptr [rsp+160h], 1000000h
0x140019162  xor     edx, edx; Val
0x140019164  lea     r8d, [rcx+78h]; Size
0x140019168  lea     rcx, [rsp+1C8h+pv]; void *
0x140019170  call    memset_0
0x140019175  lea     r9, aInvalidHthread; "Invalid hThread"
0x14001917c  mov     r8d, 8000FFFFh
0x140019182  lea     rdx, [rsp+1C8h+var_108]
0x14001918a  lea     rcx, [rsp+1C8h+var_178]
0x14001918f  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x140019194  mov     [rsp+1C8h+bAlertable], esi; bAlertable
0x140019198  mov     r9d, r12d; dwMilliseconds
0x14001919b  xor     r8d, r8d; bWaitAll
0x14001919e  lea     rdx, [rsp+1C8h+Handles]; lpHandles
0x1400191a6  lea     ecx, [r8+2]; nCount
0x1400191aa  call    cs:__imp_WaitForMultipleObjectsEx
0x1400191b0  cmp     eax, 0FFFFFFFFh
0x1400191b3  jnz     loc_1400192E7
0x1400191b9  call    cs:__imp_GetLastError
0x1400191bf  mov     ebx, eax
0x1400191c1  mov     rdi, [rsp+1C8h+var_58]
0x1400191c9  mov     [rsp+1C8h+var_108], r13
0x1400191d1  lea     r15, aCvssasyncWait; "CVssAsync::Wait"
0x1400191d8  mov     [rsp+1C8h+var_100], r15
0x1400191e0  lea     rax, aCorasync; "CORASYNC"
0x1400191e7  mov     [rsp+1C8h+var_F8], rax
0x1400191ef  mov     [rsp+1C8h+var_F0], 209h
0x1400191fa  mov     [rsp+1C8h+var_EC], 0Bh
0x140019205  mov     [rsp+1C8h+var_E8], 0FFh
0x140019210  mov     dword ptr [rsp+160h], 1000000h
0x14001921b  xor     edx, edx; Val
0x14001921d  lea     r8d, [rdx+78h]; Size
0x140019221  lea     rcx, [rsp+1C8h+pv]; void *
0x140019229  call    memset_0
0x14001922e  mov     dword ptr [rsp+1C8h+var_198], ebx
0x140019232  mov     dword ptr [rsp+1C8h+var_1A0], r12d
0x140019237  mov     qword ptr [rsp+1C8h+bAlertable], rdi
0x14001923c  mov     r9, [rsp+1C8h+Handles]
0x140019244  lea     r8, aWaitformultipl; "WaitForMultipleObjects(%p,%p, %d) == WA"...
0x14001924b  lea     rdx, [rsp+1C8h+var_108]
0x140019253  lea     rcx, [rsp+1C8h+var_178]
0x140019258  call    ?LogGenericWarning@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::LogGenericWarning(CVssDebugInfo,ushort const *,...)
0x14001925d  call    cs:__imp_GetLastError
0x140019263  mov     ebx, eax
0x140019265  mov     [rsp+1C8h+var_108], r13
0x14001926d  mov     [rsp+1C8h+var_100], r15
0x140019275  lea     rax, aCorasync; "CORASYNC"
0x14001927c  mov     [rsp+1C8h+var_F8], rax
0x140019284  mov     [rsp+1C8h+var_F0], 20Ch
0x14001928f  mov     [rsp+1C8h+var_EC], 1
0x14001929a  mov     [rsp+1C8h+var_E8], 0FFh
0x1400192a5  mov     dword ptr [rsp+160h], 1000000h
0x1400192b0  xor     edx, edx; Val
0x1400192b2  lea     r8d, [rdx+78h]; Size
0x1400192b6  lea     rcx, [rsp+1C8h+pv]; void *
0x1400192be  call    memset_0
0x1400192c3  mov     [rsp+1C8h+bAlertable], ebx
0x1400192c7  lea     r9, aWaitFailed0x08; "Wait failed. [0x%08lx]"
0x1400192ce  mov     r8d, 80042302h
0x1400192d4  lea     rdx, [rsp+1C8h+var_108]
0x1400192dc  lea     rcx, [rsp+1C8h+var_178]
0x1400192e1  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1400192e7  jmp     short loc_1400192F7
0x1400192e9  jmp     short loc_1400192EF
0x1400192eb  jmp     short loc_1400192EF
0x1400192ed  jmp     short $+2
0x1400192ef  mov     r15d, 0A0h
0x1400192f5  xor     esi, esi
0x1400192f7  mov     r12d, [rsp+1C8h+var_170]
0x1400192fc  mov     rbx, rsi
0x1400192ff  mov     rcx, [rsp+rbx*8+1C8h+var_138]; pv
0x140019307  call    cs:__imp_CoTaskMemFree
0x14001930d  mov     [rsp+rbx*8+1C8h+var_138], rsi
0x140019315  inc     rbx
0x140019318  cmp     rbx, 4
0x14001931c  jnz     short loc_1400192FF
0x14001931e  call    cs:__imp_GetTickCount
0x140019324  mov     esi, eax
0x140019326  sub     esi, [rsp+1C8h+var_144]
0x14001932d  mov     eax, 10624DD3h
0x140019332  mul     esi
0x140019334  mov     edi, edx
0x140019336  shr     edi, 6
0x140019339  mov     r8d, 88888889h
0x14001933f  mov     eax, r8d
0x140019342  mul     edi
0x140019344  shr     edx, 5
0x140019347  imul    ecx, edx, 3Ch ; '<'
0x14001934a  mov     ebx, edi
0x14001934c  sub     ebx, ecx
0x14001934e  mov     eax, 45E7B273h
0x140019353  mul     esi
0x140019355  mov     r11d, edx
0x140019358  shr     r11d, 0Eh
0x14001935c  mov     eax, r8d
0x14001935f  mul     r11d
0x140019362  shr     edx, 5
0x140019365  imul    ecx, edx, 3Ch ; '<'
0x140019368  sub     r11d, ecx
0x14001936b  mov     eax, 95217CB1h
0x140019370  mul     esi
0x140019372  mov     r10d, edx
0x140019375  shr     r10d, 15h
0x140019379  mov     eax, r8d
0x14001937c  mul     r10d
0x14001937f  shr     edx, 5
0x140019382  imul    eax, edx, 3Ch ; '<'
0x140019385  sub     r10d, eax
0x140019388  mov     r9d, [rsp+1C8h+var_170]
0x14001938d  cmp     [rsp+1C8h+var_140], 0FFh
0x140019398  cmovnz  r15d, [rsp+1C8h+var_140]
0x1400193a1  imul    ecx, edi, 3E8h
0x1400193a7  mov     edx, esi
0x1400193a9  sub     edx, ecx
0x1400193ab  mov     [rsp+1C8h+var_180], r9d
0x1400193b0  mov     dword ptr [rsp+1C8h+var_188], esi
0x1400193b4  mov     dword ptr [rsp+1C8h+var_190], edx
0x1400193b8  mov     dword ptr [rsp+1C8h+var_198], ebx
0x1400193bc  mov     dword ptr [rsp+1C8h+var_1A0], r11d
0x1400193c1  mov     [rsp+1C8h+bAlertable], r10d
0x1400193c6  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x1400193cd  mov     r8d, r15d; unsigned int
0x1400193d0  lea     rdx, aExit; "EXIT"
0x1400193d7  lea     rcx, [rsp+1C8h+var_178]; this
0x1400193dc  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1400193e1  mov     rcx, [rsp+1C8h+var_118]
0x1400193e9  call    cs:__imp_VssSetTracingContextPerThread
0x1400193ef  mov     eax, r12d
0x1400193f2  add     rsp, 198h
0x1400193f9  pop     r15
0x1400193fb  pop     r13
0x1400193fd  pop     r12
0x1400193ff  pop     rdi
0x140019400  pop     rsi
0x140019401  pop     rbx
0x140019402  retn
```

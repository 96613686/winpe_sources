# CVssCoordinatorCallback::GetContent(ushort *,ushort *,ushort * *)

- ea: `0x14002f950`
- end: `0x14002fdda`
- name: `?GetContent@CVssCoordinatorCallback@@UEAAJPEAG0PEAPEAG@Z`
- size: `1162`
- prototype: `__int64 __fastcall(CVssCoordinatorCallback *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400088fc`
- `0x1400137c0`
- `0x140013cb0`
- `0x140015e38`
- `0x14002f950`
- `0x14002fde0`
- `0x140030790`
- `0x140031760`
- `0x14003c160`
- `0x140091584`
- `0x1400921dc`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002fd73`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002fd73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002fa22`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002fa22`
- `VssTrace!__imp_VssTraceMessage` at `0x14002fb2a`
- `VssTrace!__imp_VssTraceMessage` at `0x14002fb2a`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002fa7e`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002fa7e`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002fa6f`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002fa6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002fb4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002fb4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVssCoordinatorCallback::GetContent(
        PACL *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  int v7; // eax
  struct IVssCoordinatorCallback *v8; // rcx
  int v9; // ebx
  __int64 i; // rbx
  void *v11; // rcx
  struct _TOKEN_OWNER *ClientTokenOwner; // rsi
  PSID Owner; // r14
  struct IVssCoordinatorCallback *v14; // rdi
  __int64 (__fastcall *v15)(struct IVssCoordinatorCallback *, unsigned __int16 *, _QWORD, PSID, unsigned __int16 **); // rbx
  DWORD LengthSid; // eax
  unsigned int v17; // ebx
  struct IVssCoordinatorCallback *v19[2]; // [rsp+50h] [rbp-198h] BYREF
  unsigned __int64 v20; // [rsp+60h] [rbp-188h] BYREF
  unsigned int v21; // [rsp+68h] [rbp-180h]
  const unsigned __int16 *v22; // [rsp+70h] [rbp-178h]
  const unsigned __int16 *v23; // [rsp+78h] [rbp-170h]
  unsigned int v24; // [rsp+80h] [rbp-168h]
  unsigned int v25; // [rsp+84h] [rbp-164h]
  const unsigned __int16 *v26; // [rsp+88h] [rbp-160h]
  unsigned int v27; // [rsp+90h] [rbp-158h]
  DWORD TickCount; // [rsp+94h] [rbp-154h]
  int v29; // [rsp+98h] [rbp-150h]
  __int128 v30; // [rsp+A0h] [rbp-148h]
  __int128 v31; // [rsp+B0h] [rbp-138h]
  struct IVssCoordinatorCallback *v32; // [rsp+C0h] [rbp-128h]
  const unsigned __int16 *v33; // [rsp+D8h] [rbp-110h] BYREF
  const unsigned __int16 *v34; // [rsp+E0h] [rbp-108h]
  const unsigned __int16 *v35; // [rsp+E8h] [rbp-100h]
  int v36; // [rsp+F0h] [rbp-F8h]
  int v37; // [rsp+F4h] [rbp-F4h]
  int v38; // [rsp+F8h] [rbp-F0h]
  LPVOID pv[15]; // [rsp+100h] [rbp-E8h] BYREF
  int v40; // [rsp+178h] [rbp-70h]
  int v41; // [rsp+180h] [rbp-68h] BYREF
  _com_error *v42; // [rsp+188h] [rbp-60h] BYREF
  const std::exception *v43[11]; // [rsp+190h] [rbp-58h] BYREF

  v33 = L"base\\stor\\vss\\modules\\coord\\src\\callback.cxx";
  v34 = L"CVssCoordinatorCallback::GetContent";
  v35 = L"CORCALBC";
  v36 = 195;
  v37 = 1;
  v38 = 255;
  v40 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v21 = 0;
  v26 = L"CVssCoordinatorCallback::GetContent";
  v22 = L"base\\stor\\vss\\modules\\coord\\src\\callback.cxx";
  v23 = L"CORCALBC";
  v24 = 195;
  v25 = 1;
  TickCount = GetTickCount();
  v29 = 255;
  v20 = 0xFFFFFFFF00000000uLL;
  v32 = 0;
  v30 = 0;
  v31 = 0;
  v19[0] = 0;
  if ( (int)VssGetTracingContextPerThread(v19) < 0 )
  {
    v8 = v32;
  }
  else
  {
    v7 = VssSetTracingContextPerThread(&v20);
    v8 = v32;
    if ( v7 >= 0 )
      v8 = v19[0];
    v32 = v8;
  }
  if ( v8 )
    v27 = *((_DWORD *)v8 + 12) + 1;
  else
    v27 = 0;
  v9 = 160;
  if ( v29 != 255 )
    v9 = v29;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v20) )
    VssTraceMessage(v22, v23, v24, v27, v25, v26, L"ENTER", v9, 0);
  if ( HIBYTE(v40) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v11 = pv[i];
      if ( v11 )
      {
        CoTaskMemFree(v11);
        pv[i] = 0;
      }
    }
  }
  try
  {
    ClientTokenOwner = GetClientTokenOwner();
    v43[2] = (const std::exception *)ClientTokenOwner;
    v43[1] = (const std::exception *)&CVssAuto<unsigned short * *,CVssAutoCppPtr_Storage<unsigned short * *>>::`vftable';
    Owner = ClientTokenOwner->Owner;
    if ( !CVssSidCollection::IsSidAllowedToFire(this + 9, ClientTokenOwner->Owner) )
    {
      v33 = L"base\\stor\\vss\\modules\\coord\\src\\callback.cxx";
      v34 = L"CVssCoordinatorCallback::GetContent";
      v35 = L"CORCALBC";
      v36 = 206;
      v37 = 1;
      v38 = 255;
      v40 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      CVssFunctionTracer::Throw(&v20, &v33, 2147942405LL, L"Invalid account called function");
    }
    if ( !a2 )
    {
      v33 = L"base\\stor\\vss\\modules\\coord\\src\\callback.cxx";
      v34 = L"CVssCoordinatorCallback::GetContent";
      v35 = L"CORCALBC";
      v36 = 209;
      v37 = 1;
      v38 = 255;
      v40 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      CVssFunctionTracer::Throw(&v20, &v33, 2147942487LL, L"NULL required input parameter");
    }
    ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(v19);
    CVssCoordinatorCallback::GetCoordinatorCallback((CVssCoordinatorCallback *)(this - 1), v19);
    if ( !a4 )
    {
      v33 = L"base\\stor\\vss\\modules\\coord\\src\\callback.cxx";
      v34 = L"CVssCoordinatorCallback::GetContent";
      v35 = L"CORCALBC";
      v36 = 216;
      v37 = 1;
      v38 = 255;
      v40 = 0x1000000;
      memset_0(pv, 0, sizeof(pv));
      CVssFunctionTracer::Throw(&v20, &v33, 2147942487LL, L"Null output paramater.");
    }
    v14 = v19[0];
    v15 = *(__int64 (__fastcall **)(struct IVssCoordinatorCallback *, unsigned __int16 *, _QWORD, PSID, unsigned __int16 **))(*(_QWORD *)v19[0] + 24LL);
    LengthSid = GetLengthSid(Owner);
    v21 = v15(v14, a2, LengthSid, Owner, a4);
    ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)v19);
    if ( ClientTokenOwner )
      operator delete(ClientTokenOwner);
  }
  catch ( long v41 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v20,
      v41,
      L"base\\stor\\vss\\modules\\coord\\src\\callback.cxx",
      L"CORCALBC",
      L"CVssCoordinatorCallback::GetContent",
      0xE3u,
      v25);
  }
  catch ( _com_error *v42 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v20,
      v42,
      L"base\\stor\\vss\\modules\\coord\\src\\callback.cxx",
      L"CORCALBC",
      L"CVssCoordinatorCallback::GetContent",
      0xE3u,
      v25);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v20,
      L"base\\stor\\vss\\modules\\coord\\src\\callback.cxx",
      L"CORCALBC",
      L"CVssCoordinatorCallback::GetContent",
      0xE3u,
      v25);
  }
  catch ( const std::exception *v43 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v20,
      v43[0],
      L"base\\stor\\vss\\modules\\coord\\src\\callback.cxx",
      L"CORCALBC",
      L"CVssCoordinatorCallback::GetContent",
      0xE3u,
      v25);
  }
  v17 = v21;
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v20);
  return v17;
}

```

## disassembly

```asm
0x14002f950  mov     r11, rsp
0x14002f953  push    rbx
0x14002f954  push    rsi
0x14002f955  push    rdi
0x14002f956  push    r12
0x14002f958  push    r13
0x14002f95a  push    r14
0x14002f95c  push    r15
0x14002f95e  sub     rsp, 1B0h
0x14002f965  mov     r15, r9
0x14002f968  mov     r12, rdx
0x14002f96b  mov     rdi, rcx
0x14002f96e  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x14002f975  mov     [r11-110h], rax
0x14002f97c  lea     rax, aCvsscoordinato_33; "CVssCoordinatorCallback::GetContent"
0x14002f983  mov     [r11-108h], rax
0x14002f98a  lea     rax, aCorcalbc; "CORCALBC"
0x14002f991  mov     [r11-100h], rax
0x14002f998  mov     [rsp+1E8h+var_F8], 0C3h
0x14002f9a3  mov     [rsp+1E8h+var_F4], 1
0x14002f9ae  mov     esi, 0FFh
0x14002f9b3  mov     [rsp+1E8h+var_F0], esi
0x14002f9ba  xor     r13d, r13d
0x14002f9bd  mov     dword ptr [r11-70h], 1000000h
0x14002f9c5  xor     edx, edx; Val
0x14002f9c7  lea     r8d, [r13+78h]; Size
0x14002f9cb  lea     rcx, [r11-0E8h]; void *
0x14002f9d2  call    memset_0
0x14002f9d7  mov     [rsp+1E8h+var_180], r13d
0x14002f9dc  mov     rax, [rsp+1E8h+var_108]
0x14002f9e4  mov     [rsp+1E8h+var_160], rax
0x14002f9ec  mov     rax, [rsp+1E8h+var_110]
0x14002f9f4  mov     [rsp+1E8h+var_178], rax
0x14002f9f9  mov     rax, [rsp+1E8h+var_100]
0x14002fa01  mov     [rsp+1E8h+var_170], rax
0x14002fa06  mov     eax, [rsp+1E8h+var_F8]
0x14002fa0d  mov     [rsp+1E8h+var_168], eax
0x14002fa14  mov     eax, [rsp+1E8h+var_F4]
0x14002fa1b  mov     [rsp+1E8h+var_164], eax
0x14002fa22  call    cs:__imp_GetTickCount
0x14002fa28  mov     [rsp+1E8h+var_154], eax
0x14002fa2f  mov     [rsp+1E8h+var_184], 0FFFFFFFFh
0x14002fa37  mov     eax, [rsp+1E8h+var_F0]
0x14002fa3e  mov     [rsp+1E8h+var_150], eax
0x14002fa45  mov     [rsp+1E8h+var_188], r13d
0x14002fa4a  mov     [rsp+1E8h+var_128], r13
0x14002fa52  xorps   xmm0, xmm0
0x14002fa55  movups  [rsp+1E8h+var_148], xmm0
0x14002fa5d  movups  [rsp+1E8h+var_138], xmm0
0x14002fa65  mov     [rsp+1E8h+var_198], r13
0x14002fa6a  lea     rcx, [rsp+1E8h+var_198]
0x14002fa6f  call    cs:__imp_VssGetTracingContextPerThread
0x14002fa75  test    eax, eax
0x14002fa77  js      short loc_14002FA9E
0x14002fa79  lea     rcx, [rsp+1E8h+var_188]
0x14002fa7e  call    cs:__imp_VssSetTracingContextPerThread
0x14002fa84  mov     rcx, [rsp+1E8h+var_128]
0x14002fa8c  test    eax, eax
0x14002fa8e  cmovns  rcx, [rsp+1E8h+var_198]
0x14002fa94  mov     [rsp+1E8h+var_128], rcx
0x14002fa9c  jmp     short loc_14002FAA6
0x14002fa9e  mov     rcx, [rsp+1E8h+var_128]
0x14002faa6  test    rcx, rcx
0x14002faa9  jz      short loc_14002FAB9
0x14002faab  mov     eax, [rcx+30h]
0x14002faae  inc     eax
0x14002fab0  mov     [rsp+1E8h+var_158], eax
0x14002fab7  jmp     short loc_14002FAC1
0x14002fab9  mov     [rsp+1E8h+var_158], r13d
0x14002fac1  mov     ebx, 0A0h
0x14002fac6  cmp     [rsp+1E8h+var_150], esi
0x14002facd  cmovnz  ebx, [rsp+1E8h+var_150]
0x14002fad5  lea     rcx, [rsp+1E8h+var_188]; this
0x14002fada  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14002fadf  test    eax, eax
0x14002fae1  jz      short loc_14002FB30
0x14002fae3  mov     [rsp+1E8h+var_1A8], r13
0x14002fae8  mov     [rsp+1E8h+var_1B0], ebx
0x14002faec  lea     rax, aEnter; "ENTER"
0x14002faf3  mov     [rsp+1E8h+var_1B8], rax
0x14002faf8  mov     rax, [rsp+1E8h+var_160]
0x14002fb00  mov     [rsp+1E8h+var_1C0], rax
0x14002fb05  mov     eax, [rsp+1E8h+var_164]
0x14002fb0c  mov     dword ptr [rsp+1E8h+var_1C8], eax
0x14002fb10  mov     r9d, [rsp+1E8h+var_158]
0x14002fb18  mov     r8d, [rsp+1E8h+var_168]
0x14002fb20  mov     rdx, [rsp+1E8h+var_170]
0x14002fb25  mov     rcx, [rsp+1E8h+var_178]
0x14002fb2a  call    cs:__imp_VssTraceMessage
0x14002fb30  cmp     [rsp+1E8h+var_6D], r13b
0x14002fb38  jz      short loc_14002FB61
0x14002fb3a  mov     rbx, r13
0x14002fb3d  mov     rcx, [rsp+rbx*8+1E8h+pv]; pv
0x14002fb45  test    rcx, rcx
0x14002fb48  jz      short loc_14002FB58
0x14002fb4a  call    cs:__imp_CoTaskMemFree
0x14002fb50  mov     [rsp+rbx*8+1E8h+pv], r13
0x14002fb58  inc     rbx
0x14002fb5b  cmp     rbx, 0Fh
0x14002fb5f  jnz     short loc_14002FB3D
0x14002fb61  call    ?GetClientTokenOwner@@YAPEAU_TOKEN_OWNER@@H@Z; GetClientTokenOwner(int)
0x14002fb66  mov     rsi, rax
0x14002fb69  mov     [rsp+1E8h+var_48], rax
0x14002fb71  lea     rax, ??_7?$CVssAuto@PEAPEAGV?$CVssAutoCppPtr_Storage@PEAPEAG@@@@6B@; const CVssAuto<ushort * *,CVssAutoCppPtr_Storage<ushort * *>>::`vftable'
0x14002fb78  mov     [rsp+1E8h+var_50], rax
0x14002fb80  mov     r14, [rsi]
0x14002fb83  lea     rcx, [rdi+48h]; this
0x14002fb87  mov     rdx, r14; void *
0x14002fb8a  call    ?IsSidAllowedToFire@CVssSidCollection@@QEAA_NPEAX@Z; CVssSidCollection::IsSidAllowedToFire(void *)
0x14002fb8f  test    al, al
0x14002fb91  jnz     loc_14002FC22
0x14002fb97  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x14002fb9e  mov     [rsp+1E8h+var_110], rax
0x14002fba6  lea     rax, aCvsscoordinato_33; "CVssCoordinatorCallback::GetContent"
0x14002fbad  mov     [rsp+1E8h+var_108], rax
0x14002fbb5  lea     rax, aCorcalbc; "CORCALBC"
0x14002fbbc  mov     [rsp+1E8h+var_100], rax
0x14002fbc4  mov     [rsp+1E8h+var_F8], 0CEh
0x14002fbcf  mov     [rsp+1E8h+var_F4], 1
0x14002fbda  mov     [rsp+1E8h+var_F0], 0FFh
0x14002fbe5  mov     dword ptr [rsp+178h], 1000000h
0x14002fbf0  xor     edx, edx; Val
0x14002fbf2  lea     r8d, [rdx+78h]; Size
0x14002fbf6  lea     rcx, [rsp+1E8h+pv]; void *
0x14002fbfe  call    memset_0
0x14002fc03  lea     r9, aInvalidAccount; "Invalid account called function"
0x14002fc0a  mov     r8d, 80070005h
0x14002fc10  lea     rdx, [rsp+1E8h+var_110]
0x14002fc18  lea     rcx, [rsp+1E8h+var_188]
0x14002fc1d  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14002fc22  test    r12, r12
0x14002fc25  jnz     loc_14002FCB7
0x14002fc2b  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x14002fc32  mov     [rsp+1E8h+var_110], rax
0x14002fc3a  lea     rax, aCvsscoordinato_33; "CVssCoordinatorCallback::GetContent"
0x14002fc41  mov     [rsp+1E8h+var_108], rax
0x14002fc49  lea     rax, aCorcalbc; "CORCALBC"
0x14002fc50  mov     [rsp+1E8h+var_100], rax
0x14002fc58  mov     [rsp+1E8h+var_F8], 0D1h
0x14002fc63  mov     [rsp+1E8h+var_F4], 1
0x14002fc6e  mov     [rsp+1E8h+var_F0], 0FFh
0x14002fc79  mov     dword ptr [rsp+178h], 1000000h
0x14002fc84  xor     edx, edx; Val
0x14002fc86  lea     r8d, [r12+78h]; Size
0x14002fc8b  lea     rcx, [rsp+1E8h+pv]; void *
0x14002fc93  call    memset_0
0x14002fc98  lea     r9, aNullRequiredIn_1; "NULL required input parameter"
0x14002fc9f  mov     r8d, 80070057h
0x14002fca5  lea     rdx, [rsp+1E8h+var_110]
0x14002fcad  lea     rcx, [rsp+1E8h+var_188]
0x14002fcb2  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14002fcb7  lea     rcx, [rsp+1E8h+var_198]
0x14002fcbc  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x14002fcc1  nop
0x14002fcc2  lea     rcx, [rdi-8]; this
0x14002fcc6  lea     rdx, [rsp+1E8h+var_198]; struct IVssCoordinatorCallback **
0x14002fccb  call    ?GetCoordinatorCallback@CVssCoordinatorCallback@@QEAAXPEAPEAUIVssCoordinatorCallback@@@Z; CVssCoordinatorCallback::GetCoordinatorCallback(IVssCoordinatorCallback * *)
0x14002fcd0  test    r15, r15
0x14002fcd3  jnz     loc_14002FD64
0x14002fcd9  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x14002fce0  mov     [rsp+1E8h+var_110], rax
0x14002fce8  lea     rax, aCvsscoordinato_33; "CVssCoordinatorCallback::GetContent"
0x14002fcef  mov     [rsp+1E8h+var_108], rax
0x14002fcf7  lea     rax, aCorcalbc; "CORCALBC"
0x14002fcfe  mov     [rsp+1E8h+var_100], rax
0x14002fd06  mov     [rsp+1E8h+var_F8], 0D8h
0x14002fd11  mov     [rsp+1E8h+var_F4], 1
0x14002fd1c  mov     [rsp+1E8h+var_F0], 0FFh
0x14002fd27  mov     dword ptr [rsp+178h], 1000000h
0x14002fd32  xor     edx, edx; Val
0x14002fd34  lea     r8d, [r15+78h]; Size
0x14002fd38  lea     rcx, [rsp+1E8h+pv]; void *
0x14002fd40  call    memset_0
0x14002fd45  lea     r9, aNullOutputPara; "Null output paramater."
0x14002fd4c  mov     r8d, 80070057h
0x14002fd52  lea     rdx, [rsp+1E8h+var_110]
0x14002fd5a  lea     rcx, [rsp+1E8h+var_188]
0x14002fd5f  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14002fd64  mov     rdi, [rsp+1E8h+var_198]
0x14002fd69  mov     rax, [rdi]
0x14002fd6c  mov     rbx, [rax+18h]
0x14002fd70  mov     rcx, r14; pSid
0x14002fd73  call    cs:__imp_GetLengthSid
0x14002fd79  mov     [rsp+1E8h+var_1C8], r15
0x14002fd7e  mov     r9, r14
0x14002fd81  mov     r8d, eax
0x14002fd84  mov     rdx, r12
0x14002fd87  mov     rcx, rdi
0x14002fd8a  mov     rax, rbx
0x14002fd8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fd92  mov     [rsp+1E8h+var_180], eax
0x14002fd96  lea     rcx, [rsp+1E8h+var_198]
0x14002fd9b  call    ??1?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>(void)
0x14002fda0  nop
0x14002fda1  test    rsi, rsi
0x14002fda4  jz      short loc_14002FDAF
0x14002fda6  mov     rcx, rsi; Block
0x14002fda9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002fdae  nop
0x14002fdaf  jmp     short loc_14002FDB7
0x14002fdb1  jmp     short loc_14002FDB7
0x14002fdb3  jmp     short loc_14002FDB7
0x14002fdb5  jmp     short $+2
0x14002fdb7  mov     ebx, [rsp+1E8h+var_180]
0x14002fdbb  lea     rcx, [rsp+1E8h+var_188]; this
0x14002fdc0  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14002fdc5  mov     eax, ebx
0x14002fdc7  add     rsp, 1B0h
0x14002fdce  pop     r15
0x14002fdd0  pop     r14
0x14002fdd2  pop     r13
0x14002fdd4  pop     r12
0x14002fdd6  pop     rdi
0x14002fdd7  pop     rsi
0x14002fdd8  pop     rbx
0x14002fdd9  retn
```

# WebCreateHttpRequest

- ea: `0x180039210`
- end: `0x180039cc2`
- name: `WebCreateHttpRequest`
- size: `2738`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180081d08`

## callees

- `0x180013820`
- `0x1800180e0`
- `0x180018210`
- `0x18001b150`
- `0x18001cb10`
- `0x18001cd80`
- `0x18001ce10`
- `0x18001d320`
- `0x18001f9e8`
- `0x180023a30`
- `0x1800391c0`
- `0x180039210`
- `0x180039e50`
- `0x18004e5a0`
- `0x18006ad9c`
- `0x1800722f0`
- `0x180083b8c`
- `0x180091678`
- `0x180092500`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800399fe`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800399fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800395c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800395c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800395da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800395da`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18003951d`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18003951d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180039331`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180039331`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180039357`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180039357`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180039539`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180039539`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039584`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039584`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800393ab`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800393cc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180039611`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180039659`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003969a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003991c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800393ab`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800393cc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180039611`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180039659`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003969a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003991c`
- `ntdll!RtlGetCurrentProcessorNumber` at `0x1800394fb`
- `ntdll!RtlGetCurrentProcessorNumber` at `0x1800394fb`

## pseudocode

```c
__int64 __fastcall WebCreateHttpRequest(unsigned __int64 a1, int a2, __int64 a3, _QWORD *a4)
{
  unsigned __int64 v5; // r13
  unsigned __int64 v6; // rcx
  RTL_SRWLOCK *v7; // rbx
  char *Ptr; // r14
  ULONG v9; // eax
  char v10; // cl
  unsigned int appended; // esi
  __int64 v12; // r13
  __int64 v13; // rcx
  __int64 Heap; // rax
  __int64 v15; // rbx
  _BYTE *v16; // r15
  __int64 v17; // rsi
  unsigned int i; // edi
  __int64 CurrentProcessorNumber; // r15
  union _SLIST_HEADER *v20; // rbx
  PSLIST_ENTRY v21; // rax
  PSLIST_ENTRY v22; // rdi
  int v23; // r8d
  _QWORD *v24; // rcx
  __int64 v25; // rdi
  DWORD v26; // ebx
  DWORD v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rcx
  char v32; // al
  ULONG v33; // eax
  const wchar_t *v34; // r8
  const char *v35; // rdx
  __int64 v36; // rax
  int v37; // ecx
  const char *v38; // rax
  __int64 v39; // rax
  int v40; // ecx
  const wchar_t *v41; // rax
  __int64 v42; // r15
  __int64 v43; // rax
  unsigned int v44; // edi
  _BYTE *v45; // rcx
  __int64 v46; // rax
  size_t v47; // rdi
  void *v48; // rax
  __int64 v52; // [rsp+B0h] [rbp-188h] BYREF
  __int64 v53; // [rsp+B8h] [rbp-180h]
  int v54; // [rsp+C0h] [rbp-178h]
  DWORD v55; // [rsp+C4h] [rbp-174h]
  _QWORD *v56; // [rsp+C8h] [rbp-170h] BYREF
  __int64 v57; // [rsp+D0h] [rbp-168h] BYREF
  char *v58; // [rsp+D8h] [rbp-160h] BYREF
  signed __int32 v59; // [rsp+E0h] [rbp-158h] BYREF
  __int16 v60; // [rsp+E8h] [rbp-150h] BYREF
  __int16 v61; // [rsp+F0h] [rbp-148h] BYREF
  __int128 v62; // [rsp+F8h] [rbp-140h]
  GUID ActivityId; // [rsp+108h] [rbp-130h] BYREF
  int v64; // [rsp+118h] [rbp-120h]
  __int64 v65; // [rsp+120h] [rbp-118h] BYREF
  unsigned __int64 v66; // [rsp+128h] [rbp-110h] BYREF
  char v67[16]; // [rsp+130h] [rbp-108h] BYREF
  _QWORD **v68; // [rsp+140h] [rbp-F8h]
  __int64 v69; // [rsp+148h] [rbp-F0h]
  __int64 *v70; // [rsp+150h] [rbp-E8h]
  __int64 v71; // [rsp+158h] [rbp-E0h]
  char **v72; // [rsp+160h] [rbp-D8h]
  __int64 v73; // [rsp+168h] [rbp-D0h]
  unsigned __int64 *v74; // [rsp+170h] [rbp-C8h]
  __int64 v75; // [rsp+178h] [rbp-C0h]
  const char *v76; // [rsp+180h] [rbp-B8h]
  int v77; // [rsp+188h] [rbp-B0h]
  int v78; // [rsp+18Ch] [rbp-ACh]
  const wchar_t *v79; // [rsp+190h] [rbp-A8h]
  int v80; // [rsp+198h] [rbp-A0h]
  int v81; // [rsp+19Ch] [rbp-9Ch]
  __int16 *v82; // [rsp+1A0h] [rbp-98h]
  __int64 v83; // [rsp+1A8h] [rbp-90h]
  __int16 *v84; // [rsp+1B0h] [rbp-88h]
  __int64 v85; // [rsp+1B8h] [rbp-80h]
  signed __int32 *v86; // [rsp+1C0h] [rbp-78h]
  __int64 v87; // [rsp+1C8h] [rbp-70h]
  char v88[16]; // [rsp+1D0h] [rbp-68h] BYREF
  __int64 *v89; // [rsp+1E0h] [rbp-58h]
  __int64 v90; // [rsp+1E8h] [rbp-50h]

  v56 = a4;
  v5 = a1;
  v62 = 0;
  ActivityId = 0;
  v64 = 0;
  if ( a2 || !a3 || !a4 )
    return 87;
  *a4 = 0;
  if ( !WaHandleTableInitialized )
    return 6;
  if ( (a1 & 0xF0000000) != 0x20000000 )
    return 6;
  v6 = (unsigned __int64)BYTE4(a1) << 6;
  if ( (unsigned int)(unsigned __int16)(HIDWORD(v5) >> 8) >= *(_DWORD *)((char *)WaHandleTable + v6 + 16) )
    return 6;
  v7 = (RTL_SRWLOCK *)(32 * HIBYTE(v5)
                     + *(_QWORD *)(*(_QWORD *)((char *)WaHandleTable + v6 + 8)
                                 + 8LL * (unsigned __int16)(HIDWORD(v5) >> 8)));
  if ( v7[3].Ptr != (PVOID)v5 )
    v7 = 0;
  if ( !v7 )
    return 6;
  AcquireSRWLockShared(v7 + 2);
  if ( v7[3].Ptr == (PVOID)v5 )
  {
    Ptr = (char *)v7->Ptr;
    _InterlockedAdd((volatile signed __int32 *)v7->Ptr + 1, 1u);
  }
  else
  {
    Ptr = 0;
  }
  ReleaseSRWLockShared(v7 + 2);
  if ( !Ptr )
    return 6;
  v62 = 0;
  ActivityId = 0;
  v64 = 0;
  v62 = *(_OWORD *)(Ptr + 120);
  if ( !EventActivityIdControl(1u, &ActivityId) )
  {
    if ( (_BYTE)v64 )
      goto LABEL_20;
    v9 = EventActivityIdControl(2u, (LPGUID)(Ptr + 120));
    v10 = v64;
    if ( !v9 )
      v10 = 1;
    LOBYTE(v64) = v10;
  }
  if ( !(_BYTE)v64 )
    ActivityId = 0;
LABEL_20:
  appended = 0;
  if ( !Ptr[33] )
    appended = WaImpersonateToken(*((HANDLE *)Ptr + 14));
  if ( appended && (xmmword_1800AD710 & 2) != 0 )
    WPP_SF_qD(513, 17, WPP_247e30510a1b3c47cfbd7b690ee005cd_Traceguids, Ptr, appended);
  if ( !appended )
  {
    v12 = 0;
    appended = WapValidateUserHttpRequest(a3);
    if ( appended )
      goto LABEL_36;
    Heap = WxAllocateHeapEx(v13, 5992);
    v15 = Heap;
    if ( !Heap )
    {
      appended = 8;
      goto LABEL_36;
    }
    appended = WapInitializeHttpRequest(Heap, Ptr);
    if ( appended )
    {
      v52 = v15;
      WxFreeHeapEx(&v52);
      goto LABEL_36;
    }
    v16 = *(_BYTE **)a3;
    v17 = -1;
    do
      ++v17;
    while ( v16[v17] );
    for ( i = 1; i < 9; ++i )
    {
      if ( (&off_180099410)[2 * i + 1] == (char *)v17 && !(unsigned int)_o__stricmp((&off_180099410)[2 * i], v16) )
        goto LABEL_83;
    }
    i = 0;
LABEL_83:
    *(_DWORD *)(v15 + 320) = i;
    if ( i )
    {
      *(_QWORD *)(v15 + 312) = (&off_180099410)[2 * (int)i];
      v42 = a3;
    }
    else
    {
      v42 = a3;
      v45 = *(_BYTE **)a3;
      v46 = -1;
      do
        ++v46;
      while ( v45[v46] );
      v47 = v46 + 1;
      v48 = (void *)WxAllocateHeapEx(v45, v46 + 1);
      *(_QWORD *)(v15 + 312) = v48;
      if ( !v48 )
      {
        appended = 8;
        v44 = 0;
LABEL_86:
        if ( !appended )
        {
          appended = 0;
          while ( v44 < *(_DWORD *)(v42 + 32) )
          {
            appended = WaAppendRequestHeader(v15 + 4928, v15 + 344, *(_QWORD *)(v42 + 24) + 16LL * v44);
            if ( appended )
              break;
            ++v44;
          }
          if ( !appended )
          {
            v12 = v15;
            v15 = 0;
          }
        }
        if ( v15 )
        {
          v59 = _InterlockedDecrement((volatile signed __int32 *)(v15 + 4));
          if ( !v59 )
            WapDestroyHttpRequest((LPVOID)v15);
        }
LABEL_36:
        if ( !appended )
        {
          CurrentProcessorNumber = (unsigned __int8)RtlGetCurrentProcessorNumber();
          v20 = (union _SLIST_HEADER *)((char *)WaHandleTable + 64 * CurrentProcessorNumber);
          do
          {
            v21 = InterlockedPopEntrySList(v20 + 2);
            v22 = v21;
            if ( v21 )
            {
              AcquireSRWLockExclusive((PSRWLOCK)&v21[1]);
              v22->Next = (struct _SLIST_ENTRY *)v12;
              v23 = *((_DWORD *)&v22[1].Next + 2);
              *((_DWORD *)&v22[1].Next + 2) = v23 ^ (v23 ^ (v23 + 1)) & 0xFFFFFFF;
              *((_DWORD *)&v22[1].Next + 2) = (v23 + 1) & 0xFFFFFFF | 0x30000000;
              *v56 = *((_QWORD *)&v22[1].Next + 1);
              ReleaseSRWLockExclusive((PSRWLOCK)&v22[1]);
              appended = 0;
              v24 = v56;
              goto LABEL_40;
            }
            appended = WapExpandHandleTable((unsigned int)CurrentProcessorNumber);
          }
          while ( !appended );
          v24 = v56;
          *v56 = 0;
LABEL_40:
          if ( appended )
          {
            *v24 = 0;
            v59 = _InterlockedDecrement((volatile signed __int32 *)(v12 + 4));
            if ( !v59 )
              WapDestroyHttpRequest((LPVOID)v12);
          }
          else
          {
            *(_QWORD *)(v12 + 64) = *v24;
            v53 = *v24;
            v25 = v53;
            v54 = v12;
            v26 = GetCurrentThreadId() << 16;
            v27 = v26 ^ GetCurrentProcessId();
            v55 = v27;
            *(_QWORD *)(v12 + 4572) = v25;
            *(_DWORD *)(v12 + 4580) = v12;
            *(_DWORD *)(v12 + 4584) = v27;
            if ( (_BYTE)v64 )
              EventActivityIdControl(2u, &ActivityId);
            v62 = 0;
            ActivityId = 0;
            v64 = 0;
            v62 = *(_OWORD *)(v12 + 4572);
            if ( !EventActivityIdControl(1u, &ActivityId) )
            {
              if ( Microsoft_Windows_Networking_CorrelationEnabled )
                v31 = (unsigned int)EtwEx_tidActivityInfo(v29, ActivityStart, v12 + 4572);
              else
                v31 = 0;
              v32 = v64;
              if ( !(_DWORD)v31 )
                v32 = 1;
              LOBYTE(v64) = v32;
              if ( !v32 )
              {
                v33 = EventActivityIdControl(2u, (LPGUID)(v12 + 4572));
                v31 = (unsigned __int8)v64;
                if ( !v33 )
                  v31 = 1;
                LOBYTE(v64) = v31;
              }
              if ( Microsoft_Windows_Networking_CorrelationEnabled )
                EtwEx_tidActivityInfoTransfer(v31, v28, v12 + 4572, &ActivityId);
            }
            if ( !(_BYTE)v64 )
              ActivityId = 0;
            if ( (Microsoft_Windows_WebIOEnableBits & 0x40) != 0 )
            {
              v57 = v12;
              v89 = &v57;
              v90 = 8;
              McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, RequestInitialize, v30, 2, v88);
            }
            if ( (Microsoft_Windows_WebIOEnableBits & 4) != 0 )
            {
              v34 = *(const wchar_t **)(*(_QWORD *)(*(_QWORD *)(v12 + 328) + 32LL) + 216LL);
              v59 = 0;
              v61 = *(_WORD *)(v12 + 338);
              v60 = *(_WORD *)(v12 + 336);
              v35 = *(const char **)(v12 + 312);
              v66 = a1;
              v58 = Ptr;
              v65 = *v56;
              v56 = (_QWORD *)v12;
              v68 = &v56;
              v69 = 8;
              v70 = &v65;
              v71 = 8;
              v72 = &v58;
              v73 = 8;
              v74 = &v66;
              v75 = 8;
              if ( v35 )
              {
                v36 = -1;
                do
                  ++v36;
                while ( v35[v36] );
                v37 = v36 + 1;
              }
              else
              {
                v37 = 5;
              }
              v38 = "NULL";
              if ( v35 )
                v38 = v35;
              v76 = v38;
              v77 = v37;
              v78 = 0;
              if ( v34 )
              {
                v39 = -1;
                do
                  ++v39;
                while ( v34[v39] );
                v40 = 2 * v39 + 2;
              }
              else
              {
                v40 = 10;
              }
              v41 = L"NULL";
              if ( v34 )
                v41 = v34;
              v79 = v41;
              v80 = v40;
              v81 = 0;
              v82 = &v60;
              v83 = 2;
              v84 = &v61;
              v85 = 2;
              v86 = &v59;
              v87 = 4;
              McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, ApiCreateRequest, v34, 10, v67);
            }
          }
        }
        LOBYTE(v5) = a1;
        if ( !appended )
          goto LABEL_73;
        goto LABEL_108;
      }
      memcpy_0(v48, *(const void **)a3, v47);
    }
    v43 = *(_QWORD *)(v42 + 8);
    *(_QWORD *)(v15 + 328) = v43;
    _InterlockedAdd((volatile signed __int32 *)(v43 + 4), 1u);
    *(_DWORD *)(v15 + 336) = *(_DWORD *)(v42 + 16);
    v44 = 0;
    appended = 0;
    goto LABEL_86;
  }
LABEL_108:
  if ( (Microsoft_Windows_WebIOEnableBits & 8) != 0 )
    McTemplateU0pxpxszhhq_EventWriteTransfer(
      *(_QWORD *)(*(_QWORD *)(a3 + 8) + 32LL),
      (unsigned int)ApiCreateRequestFailed,
      0,
      0,
      (char)Ptr,
      v5,
      *(_QWORD *)a3,
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 32LL) + 216LL),
      *(_WORD *)(a3 + 16),
      *(_WORD *)(a3 + 18),
      appended);
LABEL_73:
  v59 = _InterlockedDecrement((volatile signed __int32 *)Ptr + 1);
  if ( !v59 )
    WapDestroySession(Ptr);
  WaRestoreToken((HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( (_BYTE)v64 )
    EventActivityIdControl(2u, &ActivityId);
  return appended;
}

```

## disassembly

```asm
0x180039210  push    rbx
0x180039212  push    rsi
0x180039213  push    rdi
0x180039214  push    r12
0x180039216  push    r13
0x180039218  push    r14
0x18003921a  push    r15
0x18003921c  sub     rsp, 200h
0x180039223  mov     rax, cs:__security_cookie
0x18003922a  xor     rax, rsp
0x18003922d  mov     [rsp+238h+var_48], rax
0x180039235  mov     rax, r9
0x180039238  mov     [rsp+238h+var_170], rax
0x180039240  mov     r15, r8
0x180039243  mov     [rsp+238h+var_1A0], r8
0x18003924b  mov     r13, rcx
0x18003924e  mov     [rsp+238h+var_1D0], rcx
0x180039253  xor     esi, esi
0x180039255  mov     [rsp+238h+var_1C0], esi
0x180039259  mov     [rsp+238h+var_1D4], esi
0x18003925d  mov     [rsp+238h+var_198], rsi
0x180039265  mov     [rsp+238h+var_1A8], 0FFFFFFFFFFFFFFFFh
0x180039271  xorps   xmm0, xmm0
0x180039274  xor     ecx, ecx
0x180039276  movups  [rsp+238h+var_140], xmm0
0x18003927e  movups  xmmword ptr [rsp+238h+ActivityId.Data1], xmm0
0x180039286  mov     [rsp+238h+var_120], ecx
0x18003928d  test    edx, edx
0x18003928f  jnz     loc_180039C8D
0x180039295  test    r8, r8
0x180039298  jz      loc_180039C8D
0x18003929e  test    rax, rax
0x1800392a1  jz      loc_180039C8D
0x1800392a7  mov     [r9], rsi
0x1800392aa  mov     [rsp+238h+hObject], rsi
0x1800392b2  cmp     cs:WaHandleTableInitialized, sil
0x1800392b9  jz      loc_180039ACB
0x1800392bf  mov     eax, r13d
0x1800392c2  and     eax, 0F0000000h
0x1800392c7  cmp     eax, 20000000h
0x1800392cc  jnz     loc_180039ACB
0x1800392d2  mov     rax, r13
0x1800392d5  shr     rax, 20h
0x1800392d9  mov     r8, rax
0x1800392dc  movzx   ecx, al
0x1800392df  shl     rcx, 6
0x1800392e3  mov     r9, cs:WaHandleTable
0x1800392ea  shr     eax, 8
0x1800392ed  movzx   eax, ax
0x1800392f0  cmp     eax, [rcx+r9+10h]
0x1800392f5  jnb     loc_180039ACB
0x1800392fb  mov     rax, r8
0x1800392fe  shr     rax, 8
0x180039302  movzx   edx, ax
0x180039305  mov     rax, [rcx+r9+8]
0x18003930a  mov     rcx, r8
0x18003930d  shr     rcx, 18h
0x180039311  shl     rcx, 5
0x180039315  mov     rbx, [rax+rdx*8]
0x180039319  add     rbx, rcx
0x18003931c  cmp     [rbx+18h], r13
0x180039320  cmovnz  rbx, rsi
0x180039324  test    rbx, rbx
0x180039327  jz      loc_180039ACB
0x18003932d  lea     rcx, [rbx+10h]; SRWLock
0x180039331  call    cs:__imp_AcquireSRWLockShared
0x180039338  nop     dword ptr [rax+rax+00h]
0x18003933d  lea     r12d, [rsi+1]
0x180039341  cmp     [rbx+18h], r13
0x180039345  jnz     loc_180039AE5
0x18003934b  mov     r14, [rbx]
0x18003934e  lock add [r14+4], r12d
0x180039353  lea     rcx, [rbx+10h]; SRWLock
0x180039357  call    cs:__imp_ReleaseSRWLockShared
0x18003935e  nop     dword ptr [rax+rax+00h]
0x180039363  xor     edi, edi
0x180039365  test    r14, r14
0x180039368  jz      loc_180039ACB
0x18003936e  xorps   xmm0, xmm0
0x180039371  xor     eax, eax
0x180039373  movups  [rsp+238h+var_140], xmm0
0x18003937b  movups  xmmword ptr [rsp+238h+ActivityId.Data1], xmm0
0x180039383  mov     [rsp+238h+var_120], eax
0x18003938a  movups  xmm0, xmmword ptr [r14+78h]
0x18003938f  movdqu  [rsp+238h+var_140], xmm0
0x180039398  mov     byte ptr [rsp+238h+var_120], dil
0x1800393a0  lea     rdx, [rsp+238h+ActivityId]; ActivityId
0x1800393a8  mov     ecx, r12d; ControlCode
0x1800393ab  call    cs:__imp_EventActivityIdControl
0x1800393b2  nop     dword ptr [rax+rax+00h]
0x1800393b7  test    eax, eax
0x1800393b9  jnz     short loc_1800393ED
0x1800393bb  cmp     byte ptr [rsp+238h+var_120], dil
0x1800393c3  jnz     short loc_1800393FB
0x1800393c5  lea     rdx, [r14+78h]; ActivityId
0x1800393c9  lea     ecx, [rdi+2]; ControlCode
0x1800393cc  call    cs:__imp_EventActivityIdControl
0x1800393d3  nop     dword ptr [rax+rax+00h]
0x1800393d8  movzx   ecx, byte ptr [rsp+238h+var_120]
0x1800393e0  test    eax, eax
0x1800393e2  cmovz   ecx, r12d
0x1800393e6  mov     byte ptr [rsp+238h+var_120], cl
0x1800393ed  cmp     byte ptr [rsp+238h+var_120], dil
0x1800393f5  jz      loc_180039AD5
0x1800393fb  mov     esi, edi
0x1800393fd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180039401  mov     [rsp+238h+hObject], rax
0x180039409  mov     [rsp+238h+var_1A8], rax
0x180039411  cmp     [r14+21h], dil
0x180039415  jz      loc_180039AED
0x18003941b  test    esi, esi
0x18003941d  jnz     loc_180039BC8
0x180039423  mov     [rsp+238h+var_1D4], esi
0x180039427  test    esi, esi
0x180039429  jnz     loc_180039C25
0x18003942f  mov     [rsp+238h+var_1D8], edi
0x180039433  mov     [rsp+238h+var_190], rdi
0x18003943b  mov     r13, rdi
0x18003943e  mov     [rsp+238h+var_198], rdi
0x180039446  mov     rcx, r15
0x180039449  call    WapValidateUserHttpRequest
0x18003944e  mov     esi, eax
0x180039450  mov     [rsp+238h+var_1D8], eax
0x180039454  test    eax, eax
0x180039456  jnz     loc_1800394EF
0x18003945c  mov     edx, 1768h
0x180039461  call    WxAllocateHeapEx
0x180039466  mov     rbx, rax
0x180039469  mov     [rsp+238h+var_190], rax
0x180039471  test    rax, rax
0x180039474  jz      loc_180039B64
0x18003947a  mov     rdx, r14
0x18003947d  mov     rcx, rax
0x180039480  call    WapInitializeHttpRequest
0x180039485  mov     esi, eax
0x180039487  mov     [rsp+238h+var_1D8], eax
0x18003948b  test    eax, eax
0x18003948d  jnz     loc_180039BF7
0x180039493  mov     r15, [r15]
0x180039496  mov     [rsp+238h+var_1C8], edi
0x18003949a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003949e  inc     rsi
0x1800394a1  cmp     [r15+rsi], dil
0x1800394a5  jnz     short loc_18003949E
0x1800394a7  mov     edi, r12d
0x1800394aa  mov     [rsp+238h+var_1C8], r12d
0x1800394af  lea     r8, off_180099410
0x1800394b6  cmp     edi, 9
0x1800394b9  jnb     loc_180039A1A
0x1800394bf  mov     ecx, edi
0x1800394c1  add     rcx, rcx
0x1800394c4  cmp     [r8+rcx*8+8], rsi
0x1800394c9  jz      loc_1800399F7
0x1800394cf  add     edi, r12d
0x1800394d2  mov     [rsp+238h+var_1C8], edi
0x1800394d6  jmp     short loc_1800394B6
0x1800394d8  mov     [rsp+238h+var_1D8], esi
0x1800394dc  xor     edi, edi
0x1800394de  test    esi, esi
0x1800394e0  jz      loc_18003998C
0x1800394e6  test    rbx, rbx
0x1800394e9  jnz     loc_180039B7A
0x1800394ef  mov     [rsp+238h+var_1D4], esi
0x1800394f3  test    esi, esi
0x1800394f5  jnz     loc_1800398CA
0x1800394fb  call    cs:__imp_RtlGetCurrentProcessorNumber
0x180039502  nop     dword ptr [rax+rax+00h]
0x180039507  movzx   r15d, al
0x18003950b  mov     ebx, r15d
0x18003950e  shl     rbx, 6
0x180039512  add     rbx, cs:WaHandleTable
0x180039519  lea     rcx, [rbx+20h]; ListHead
0x18003951d  call    cs:__imp_InterlockedPopEntrySList
0x180039524  nop     dword ptr [rax+rax+00h]
0x180039529  mov     rdi, rax
0x18003952c  test    rax, rax
0x18003952f  jz      loc_1800399A7
0x180039535  lea     rcx, [rax+10h]; SRWLock
0x180039539  call    cs:__imp_AcquireSRWLockExclusive
0x180039540  nop     dword ptr [rax+rax+00h]
0x180039545  mov     [rdi], r13
0x180039548  mov     r8d, [rdi+18h]
0x18003954c  lea     r9d, [r8+1]
0x180039550  mov     edx, r9d
0x180039553  xor     edx, r8d
0x180039556  mov     eax, 0FFFFFFFh
0x18003955b  and     edx, eax
0x18003955d  xor     edx, r8d
0x180039560  mov     [rdi+18h], edx
0x180039563  and     r9d, eax
0x180039566  or      r9d, 30000000h
0x18003956d  mov     [rdi+18h], r9d
0x180039571  mov     rax, [rdi+18h]
0x180039575  mov     rcx, [rsp+238h+var_170]
0x18003957d  mov     [rcx], rax
0x180039580  lea     rcx, [rdi+10h]; SRWLock
0x180039584  call    cs:__imp_ReleaseSRWLockExclusive
0x18003958b  nop     dword ptr [rax+rax+00h]
0x180039590  xor     edi, edi
0x180039592  mov     esi, edi
0x180039594  mov     rcx, [rsp+238h+var_170]
0x18003959c  mov     [rsp+238h+var_1D4], esi
0x1800395a0  test    esi, esi
0x1800395a2  jnz     loc_180039B9F
0x1800395a8  mov     rax, [rcx]
0x1800395ab  mov     [r13+40h], rax
0x1800395af  lea     r15, [r13+11DCh]
0x1800395b6  mov     rdi, [rcx]
0x1800395b9  mov     [rsp+238h+var_180], rdi
0x1800395c1  mov     [rsp+238h+var_178], r13d
0x1800395c9  call    cs:__imp_GetCurrentThreadId
0x1800395d0  nop     dword ptr [rax+rax+00h]
0x1800395d5  mov     ebx, eax
0x1800395d7  shl     ebx, 10h
0x1800395da  call    cs:__imp_GetCurrentProcessId
0x1800395e1  nop     dword ptr [rax+rax+00h]
0x1800395e6  xor     eax, ebx
0x1800395e8  mov     [rsp+238h+var_174], eax
0x1800395ef  mov     [r15], rdi
0x1800395f2  mov     [r15+8], r13d
0x1800395f6  mov     [r15+0Ch], eax
0x1800395fa  xor     edi, edi
0x1800395fc  cmp     byte ptr [rsp+238h+var_120], dil
0x180039604  jz      short loc_18003961D
0x180039606  lea     rdx, [rsp+238h+ActivityId]; ActivityId
0x18003960e  lea     ecx, [rsi+2]; ControlCode
0x180039611  call    cs:__imp_EventActivityIdControl
0x180039618  nop     dword ptr [rax+rax+00h]
0x18003961d  xorps   xmm0, xmm0
0x180039620  xor     eax, eax
0x180039622  movups  [rsp+238h+var_140], xmm0
0x18003962a  movups  xmmword ptr [rsp+238h+ActivityId.Data1], xmm0
0x180039632  mov     [rsp+238h+var_120], eax
0x180039639  movups  xmm0, xmmword ptr [r15]
0x18003963d  movdqu  [rsp+238h+var_140], xmm0
0x180039646  mov     byte ptr [rsp+238h+var_120], dil
0x18003964e  lea     rdx, [rsp+238h+ActivityId]; ActivityId
0x180039656  mov     ecx, r12d; ControlCode
0x180039659  call    cs:__imp_EventActivityIdControl
0x180039660  nop     dword ptr [rax+rax+00h]
0x180039665  test    eax, eax
0x180039667  jnz     short loc_1800396C9
0x180039669  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x18003966f  test    eax, eax
0x180039671  jnz     loc_1800399E1
0x180039677  mov     ecx, edi
0x180039679  movzx   eax, byte ptr [rsp+238h+var_120]
0x180039681  test    ecx, ecx
0x180039683  cmovz   eax, r12d
0x180039687  mov     byte ptr [rsp+238h+var_120], al
0x18003968e  test    al, al
0x180039690  jnz     short loc_1800396BB
0x180039692  mov     rdx, r15; ActivityId
0x180039695  mov     ecx, 2; ControlCode
0x18003969a  call    cs:__imp_EventActivityIdControl
0x1800396a1  nop     dword ptr [rax+rax+00h]
0x1800396a6  movzx   ecx, byte ptr [rsp+238h+var_120]
0x1800396ae  test    eax, eax
0x1800396b0  cmovz   ecx, r12d
0x1800396b4  mov     byte ptr [rsp+238h+var_120], cl
0x1800396bb  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1800396c1  test    eax, eax
0x1800396c3  jnz     loc_1800399CC
0x1800396c9  cmp     byte ptr [rsp+238h+var_120], dil
0x1800396d1  jz      loc_18003997C
0x1800396d7  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits, 40h
0x1800396de  jnz     loc_18003992D
0x1800396e4  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits, 4
0x1800396eb  jz      loc_1800398CA
0x1800396f1  mov     rax, [r13+148h]
0x1800396f8  mov     rcx, [rax+20h]
0x1800396fc  mov     r8, [rcx+0D8h]
0x180039703  mov     [rsp+238h+var_158], edi
0x18003970a  movzx   eax, word ptr [r13+152h]
0x180039712  mov     [rsp+238h+var_148], ax
0x18003971a  movzx   eax, word ptr [r13+150h]
0x180039722  mov     [rsp+238h+var_150], ax
0x18003972a  mov     rdx, [r13+138h]
0x180039731  mov     rax, [rsp+238h+var_1D0]
0x180039736  mov     [rsp+238h+var_110], rax
0x18003973e  mov     [rsp+238h+var_160], r14
0x180039746  mov     rcx, [rsp+238h+var_170]
0x18003974e  mov     rax, [rcx]
0x180039751  mov     [rsp+238h+var_118], rax
0x180039759  mov     [rsp+238h+var_170], r13
0x180039761  lea     rax, [rsp+238h+var_170]
0x180039769  mov     [rsp+238h+var_F8], rax
0x180039771  mov     [rsp+238h+var_F0], 8
0x18003977d  lea     rax, [rsp+238h+var_118]
0x180039785  mov     [rsp+238h+var_E8], rax
0x18003978d  mov     [rsp+238h+var_E0], 8
0x180039799  lea     rax, [rsp+238h+var_160]
0x1800397a1  mov     [rsp+238h+var_D8], rax
0x1800397a9  mov     [rsp+238h+var_D0], 8
0x1800397b5  lea     rax, [rsp+238h+var_110]
0x1800397bd  mov     [rsp+238h+var_C8], rax
0x1800397c5  mov     [rsp+238h+var_C0], 8
0x1800397d1  test    rdx, rdx
0x1800397d4  jz      loc_180039C11
0x1800397da  or      rax, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```

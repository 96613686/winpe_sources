# MyLogSourceChangeEvent(ushort *,ulong,ulong,ulong)

- ea: `0x18000a41c`
- end: `0x18000a7d9`
- name: `?MyLogSourceChangeEvent@@YAJPEAGKKK@Z`
- size: `957`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, __int64, char)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x18000fae0`

## callees

- `0x180003ac0`
- `0x18000a41c`
- `0x18000a7e0`
- `0x18000bde0`
- `0x180018138`
- `0x18001d9a0`
- `0x18002c840`
- `0x18002c88c`
- `0x18003cc50`
- `0x18003d270`
- `0x18003d294`
- `0x18003d2d8`
- `0x18003dd2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000a6b8`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000a6fa`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000a6b8`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000a6fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a54f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a54f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a51c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a51c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a456`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a456`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000a629`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000a629`
- `ntdll!RtlReleaseResource` at `0x18000a58e`
- `ntdll!RtlReleaseResource` at `0x18000a58e`
- `ntdll!RtlInitUnicodeString` at `0x18000a48c`
- `ntdll!RtlInitUnicodeString` at `0x18000a48c`

## string_xrefs

- `0x18000a7ab`: `Logging information: The time service is now synchronizing the system time with the time source %s.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall MyLogSourceChangeEvent(unsigned __int16 *a1, unsigned int a2, __int64 a3, char a4)
{
  int v7; // ebx
  __int64 v8; // rax
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rdi
  bool v12; // zf
  void *v13; // rdi
  SourceChangeLogEntry *v15; // rcx
  unsigned __int16 **v16; // rbx
  _QWORD *v17; // rax
  unsigned int v18; // edx
  _QWORD ***v19; // r9
  _QWORD *v20; // rcx
  void **v21; // rdx
  volatile signed __int32 *v22; // rax
  _QWORD **v23; // rcx
  _QWORD *v24; // r11
  unsigned __int16 *v25; // r8
  bool v26; // zf
  __int64 v27; // r11
  int v28; // ecx
  int v29; // r10d
  unsigned int v30; // eax
  unsigned int v31; // [rsp+40h] [rbp-198h]
  void *v32; // [rsp+48h] [rbp-190h] BYREF
  __int64 v33; // [rsp+50h] [rbp-188h]
  _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-180h] BYREF
  _BYTE v35[24]; // [rsp+68h] [rbp-170h] BYREF
  int v36; // [rsp+80h] [rbp-158h]
  _BYTE v37[24]; // [rsp+88h] [rbp-150h] BYREF
  unsigned __int16 v38; // [rsp+A0h] [rbp-138h] BYREF
  char v39[254]; // [rsp+A2h] [rbp-136h] BYREF

  DestinationString = 0;
  GetTickCount64();
  v38 = 0;
  memset_0(v39, 0, sizeof(v39));
  RtlInitUnicodeString(&DestinationString, a1);
  v38 = 0;
  StringCchPrintfW(&v38, 0x80u, L"0x%08X", _byteswap_ulong(a2));
  v7 = LogEvent(&_W32TimeRegistrationHandle, W32TIME_OPS_TIME_SOURCE_REFERENCE, L"uSdi", &DestinationString);
  if ( (a4 & 2) == 0 )
    return (unsigned int)v7;
  v8 = -1;
  do
    ++v8;
  while ( a1[v8] );
  v9 = v8 + 1;
  v10 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v8 + 1));
  v11 = v10;
  if ( !v10 )
    return (unsigned int)-2147024882;
  v7 = StringCchCopyW(v10, v9, a1);
  if ( v7 < 0 )
  {
    LocalFree(v11);
    return (unsigned int)v7;
  }
  v16 = (unsigned __int16 **)operator new(8u);
  v33 = (__int64)v16;
  *v16 = v11;
  if ( v16 )
  {
    v17 = operator new(0x10u);
    v33 = (__int64)v17;
    *(_DWORD *)v17 = 1;
    v17[1] = v16;
    v32 = v17;
  }
  else
  {
    v32 = 0;
  }
  if ( !RtlAcquireResourceExclusive(&_csState, 1u) )
  {
    v7 = -2147023537;
    AutoPtr<SourceChangeLogEntry>::~AutoPtr<SourceChangeLogEntry>(&v32);
    return (unsigned int)v7;
  }
  v18 = (unsigned int)_pscvec;
  v19 = *(_QWORD ****)_pscvec;
  if ( *(_QWORD *)_pscvec == *((_QWORD *)_pscvec + 1) )
    goto LABEL_21;
  v7 = 0;
  do
  {
    v23 = *v19;
    if ( !*v19 || !v32 )
    {
      if ( v23 == v32 )
        break;
      goto LABEL_47;
    }
    v24 = (_QWORD *)*((_QWORD *)v32 + 1);
    v25 = (unsigned __int16 *)*v23[1];
    if ( v25 )
    {
      v27 = *v24 - (_QWORD)v25;
      do
      {
        v28 = *(unsigned __int16 *)((char *)v25 + v27);
        v29 = *v25 - v28;
        if ( v29 )
          break;
        ++v25;
      }
      while ( v28 );
      v26 = v29 == 0;
    }
    else
    {
      v26 = *v24 == 0;
    }
    if ( v26 )
      break;
LABEL_47:
    ++v19;
  }
  while ( v19 != *((_QWORD ****)_pscvec + 1) );
  if ( v19 != *((_QWORD ****)_pscvec + 1) )
    goto LABEL_8;
LABEL_21:
  if ( (unsigned __int8)FileLogAllowEntry(68) )
    FileLogAdd(
      L"Logging information: The time service is now synchronizing the system time with the time source %s.\n",
      a1);
  v7 = LogEvent(&_W32TimeRegistrationHandle, "#", L"udd", &DestinationString);
  if ( v7 >= 0 )
  {
    v33 = _set_se_translator(SeTransFunc);
    v7 = 0;
    try
    {
      v20 = _pscvec;
      v21 = (void **)*((_QWORD *)_pscvec + 1);
      if ( v21 == *((void ***)_pscvec + 2) )
      {
        std::vector<AutoPtr<SourceChangeLogEntry>,MyThrowingAllocator<AutoPtr<SourceChangeLogEntry>>>::_Emplace_reallocate<AutoPtr<SourceChangeLogEntry> const &>(
          _pscvec,
          v21,
          &v32);
      }
      else
      {
        v22 = (volatile signed __int32 *)v32;
        *v21 = v32;
        if ( v22 )
          _InterlockedIncrement(v22);
        v20[1] += 8LL;
      }
    }
    catch ( SeException v35 )
    {
      v30 = v36;
      if ( v36 > 0 )
        v30 = (unsigned __int16)v36 | 0x80070000;
      v31 = v30;
      SeException::~SeException((SeException *)v35);
      v7 = v31;
    }
    catch ( std::bad_alloc v37 )
    {
      SeException::~SeException((SeException *)v37);
      v7 = -2147024882;
    }
    catch ( ... )
    {
      v7 = -2147418113;
    }
    _set_se_translator(v33);
LABEL_8:
    if ( v32 )
    {
      v12 = _InterlockedExchangeAdd((volatile signed __int32 *)v32, 0xFFFFFFFF) == 1;
      goto LABEL_10;
    }
  }
  else if ( v32 )
  {
    v18 = _InterlockedExchangeAdd((volatile signed __int32 *)v32, 0xFFFFFFFF);
    v12 = v18 == 1;
LABEL_10:
    if ( v12 )
    {
      v13 = v32;
      if ( v32 )
      {
        v15 = (SourceChangeLogEntry *)*((_QWORD *)v32 + 1);
        if ( v15 )
          SourceChangeLogEntry::`scalar deleting destructor'(v15, v18);
        operator delete(v13);
      }
    }
  }
  RtlReleaseResource(&_csState);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000a41c  mov     [rsp+arg_18], rbx
0x18000a421  push    rsi
0x18000a422  push    rdi
0x18000a423  push    r12
0x18000a425  push    r14
0x18000a427  push    r15
0x18000a429  sub     rsp, 1B0h
0x18000a430  mov     rax, cs:__security_cookie
0x18000a437  xor     rax, rsp
0x18000a43a  mov     [rsp+1D8h+var_38], rax
0x18000a442  mov     edi, r9d
0x18000a445  mov     r12d, r8d
0x18000a448  mov     r15d, edx
0x18000a44b  mov     r14, rcx
0x18000a44e  xorps   xmm0, xmm0
0x18000a451  movups  xmmword ptr [rsp+1D8h+DestinationString.Length], xmm0
0x18000a456  call    cs:__imp_GetTickCount64
0x18000a45d  nop     dword ptr [rax+rax+00h]
0x18000a462  mov     rbx, rax
0x18000a465  xor     esi, esi
0x18000a467  mov     [rsp+1D8h+var_138], si
0x18000a46f  xor     edx, edx; Val
0x18000a471  mov     r8d, 0FEh; Size
0x18000a477  lea     rcx, [rsp+1D8h+var_136]; void *
0x18000a47f  call    memset_0
0x18000a484  mov     rdx, r14; SourceString
0x18000a487  lea     rcx, [rsp+1D8h+DestinationString]; DestinationString
0x18000a48c  call    cs:__imp_RtlInitUnicodeString
0x18000a493  nop     dword ptr [rax+rax+00h]
0x18000a498  mov     [rsp+1D8h+var_138], si
0x18000a4a0  mov     r9d, r15d
0x18000a4a3  bswap   r9d
0x18000a4a6  lea     r8, a0x08x; "0x%08X"
0x18000a4ad  mov     edx, 80h; unsigned __int64
0x18000a4b2  lea     rcx, [rsp+1D8h+var_138]; unsigned __int16 *
0x18000a4ba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a4bf  mov     [rsp+1D8h+var_1A8], rbx
0x18000a4c4  mov     [rsp+1D8h+var_1B0], r12d
0x18000a4c9  lea     rax, [rsp+1D8h+var_138]
0x18000a4d1  mov     [rsp+1D8h+var_1B8], rax
0x18000a4d6  lea     r9, [rsp+1D8h+DestinationString]
0x18000a4db  lea     r8, aUsdi; "uSdi"
0x18000a4e2  lea     rdx, W32TIME_OPS_TIME_SOURCE_REFERENCE
0x18000a4e9  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x18000a4f0  call    LogEvent
0x18000a4f5  mov     ebx, eax
0x18000a4f7  test    dil, 2
0x18000a4fb  jz      loc_18000A59A
0x18000a501  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a505  inc     rax
0x18000a508  cmp     [r14+rax*2], si
0x18000a50d  jnz     short loc_18000A505
0x18000a50f  lea     rbx, [rax+1]
0x18000a513  lea     rdx, [rbx+rbx]; uBytes
0x18000a517  mov     ecx, 40h ; '@'; uFlags
0x18000a51c  call    cs:__imp_LocalAlloc
0x18000a523  nop     dword ptr [rax+rax+00h]
0x18000a528  mov     rdi, rax
0x18000a52b  test    rax, rax
0x18000a52e  jz      loc_18000A728
0x18000a534  mov     r8, r14; unsigned __int16 *
0x18000a537  mov     rdx, rbx; unsigned __int64
0x18000a53a  mov     rcx, rax; unsigned __int16 *
0x18000a53d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a542  mov     ebx, eax
0x18000a544  test    eax, eax
0x18000a546  jns     loc_18000A5E4
0x18000a54c  mov     rcx, rdi; hMem
0x18000a54f  call    cs:__imp_LocalFree
0x18000a556  nop     dword ptr [rax+rax+00h]
0x18000a55b  jmp     short loc_18000A59A
0x18000a55d  cmp     r9, [rdx+8]
0x18000a561  jz      loc_18000A653
0x18000a567  mov     rax, [rsp+1D8h+var_190]
0x18000a56c  test    rax, rax
0x18000a56f  jz      short loc_18000A587
0x18000a571  or      ecx, 0FFFFFFFFh
0x18000a574  lock xadd [rax], ecx
0x18000a578  cmp     ecx, 1
0x18000a57b  jnz     short loc_18000A587
0x18000a57d  mov     rdi, [rsp+1D8h+var_190]
0x18000a582  test    rdi, rdi
0x18000a585  jnz     short loc_18000A5C5
0x18000a587  lea     rcx, ?_csState@@3U_RTL_RESOURCE@@A; Resource
0x18000a58e  call    cs:__imp_RtlReleaseResource
0x18000a595  nop     dword ptr [rax+rax+00h]
0x18000a59a  mov     eax, ebx
0x18000a59c  mov     rcx, [rsp+1D8h+var_38]
0x18000a5a4  xor     rcx, rsp; StackCookie
0x18000a5a7  call    __security_check_cookie
0x18000a5ac  mov     rbx, [rsp+1D8h+arg_18]
0x18000a5b4  add     rsp, 1B0h
0x18000a5bb  pop     r15
0x18000a5bd  pop     r14
0x18000a5bf  pop     r12
0x18000a5c1  pop     rdi
0x18000a5c2  pop     rsi
0x18000a5c3  retn
0x18000a5c5  mov     rcx, [rdi+8]; this
0x18000a5c9  test    rcx, rcx
0x18000a5cc  jnz     short loc_18000A5DD
0x18000a5ce  mov     edx, 10h; unsigned __int64
0x18000a5d3  mov     rcx, rdi; void *
0x18000a5d6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a5db  jmp     short loc_18000A587
0x18000a5dd  call    ??_GSourceChangeLogEntry@@QEAAPEAXI@Z; SourceChangeLogEntry::`scalar deleting destructor'(uint)
0x18000a5e2  jmp     short loc_18000A5CE
0x18000a5e4  mov     ecx, 8; Size
0x18000a5e9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a5ee  mov     rbx, rax
0x18000a5f1  mov     [rsp+1D8h+var_188], rax
0x18000a5f6  mov     [rax], rdi
0x18000a5f9  test    rax, rax
0x18000a5fc  jz      loc_18000A70B
0x18000a602  mov     ecx, 10h; Size
0x18000a607  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a60c  mov     [rsp+1D8h+var_188], rax
0x18000a611  mov     dword ptr [rax], 1
0x18000a617  mov     [rax+8], rbx
0x18000a61b  mov     [rsp+1D8h+var_190], rax
0x18000a620  mov     dl, 1; Wait
0x18000a622  lea     rcx, ?_csState@@3U_RTL_RESOURCE@@A; Resource
0x18000a629  call    cs:__imp_RtlAcquireResourceExclusive
0x18000a630  nop     dword ptr [rax+rax+00h]
0x18000a635  test    al, al
0x18000a637  jz      loc_18000A732
0x18000a63d  mov     rdx, cs:?_pscvec@@3PEAV?$vector@V?$AutoPtr@VSourceChangeLogEntry@@@@V?$MyThrowingAllocator@V?$AutoPtr@VSourceChangeLogEntry@@@@@@@std@@EA; unsigned int
0x18000a644  mov     r9, [rdx]
0x18000a647  mov     ebx, esi
0x18000a649  cmp     r9, [rdx+8]
0x18000a64d  jnz     loc_18000A746
0x18000a653  mov     ecx, 44h ; 'D'
0x18000a658  call    FileLogAllowEntry
0x18000a65d  test    al, al
0x18000a65f  jnz     loc_18000A7A8
0x18000a665  mov     [rsp+1D8h+var_1B0], r12d
0x18000a66a  mov     dword ptr [rsp+1D8h+var_1B8], r15d
0x18000a66f  lea     r9, [rsp+1D8h+DestinationString]
0x18000a674  lea     r8, aUdd; "udd"
0x18000a67b  lea     rdx, W32TIME_EVENT_TIME_SOURCE_CHOSEN; "#"
0x18000a682  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x18000a689  call    LogEvent
0x18000a68e  mov     ebx, eax
0x18000a690  test    eax, eax
0x18000a692  jns     short loc_18000A6B1
0x18000a694  mov     rcx, [rsp+1D8h+var_190]
0x18000a699  test    rcx, rcx
0x18000a69c  jz      loc_18000A587
0x18000a6a2  or      edx, 0FFFFFFFFh
0x18000a6a5  lock xadd [rcx], edx
0x18000a6a9  cmp     edx, 1
0x18000a6ac  jmp     loc_18000A57B
0x18000a6b1  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18000a6b8  call    cs:__imp__set_se_translator
0x18000a6bf  nop     dword ptr [rax+rax+00h]
0x18000a6c4  mov     [rsp+1D8h+var_188], rax
0x18000a6c9  mov     ebx, esi
0x18000a6cb  mov     rcx, cs:?_pscvec@@3PEAV?$vector@V?$AutoPtr@VSourceChangeLogEntry@@@@V?$MyThrowingAllocator@V?$AutoPtr@VSourceChangeLogEntry@@@@@@@std@@EA; std::vector<AutoPtr<SourceChangeLogEntry>,MyThrowingAllocator<AutoPtr<SourceChangeLogEntry>>> * _pscvec
0x18000a6d2  mov     rdx, [rcx+8]
0x18000a6d6  cmp     rdx, [rcx+10h]
0x18000a6da  jz      loc_18000A7BC
0x18000a6e0  mov     rax, [rsp+1D8h+var_190]
0x18000a6e5  mov     [rdx], rax
0x18000a6e8  test    rax, rax
0x18000a6eb  jz      short loc_18000A6F0
0x18000a6ed  lock inc dword ptr [rax]
0x18000a6f0  add     qword ptr [rcx+8], 8
0x18000a6f5  mov     rcx, [rsp+1D8h+var_188]
0x18000a6fa  call    cs:__imp__set_se_translator
0x18000a701  nop     dword ptr [rax+rax+00h]
0x18000a706  jmp     loc_18000A567
0x18000a70b  mov     [rsp+1D8h+var_190], rsi
0x18000a710  jmp     loc_18000A620
0x18000a715  mov     rcx, [r9]
0x18000a718  test    rcx, rcx
0x18000a71b  jnz     short loc_18000A74F
0x18000a71d  cmp     rcx, rax
0x18000a720  jz      loc_18000A55D
0x18000a726  jmp     short loc_18000A795
0x18000a728  mov     ebx, 8007000Eh
0x18000a72d  jmp     loc_18000A59A
0x18000a732  mov     ebx, 8007054Fh
0x18000a737  lea     rcx, [rsp+1D8h+var_190]
0x18000a73c  call    ??1?$AutoPtr@VSourceChangeLogEntry@@@@QEAA@XZ; AutoPtr<SourceChangeLogEntry>::~AutoPtr<SourceChangeLogEntry>(void)
0x18000a741  jmp     loc_18000A59A
0x18000a746  mov     rax, [rsp+1D8h+var_190]
0x18000a74b  mov     ebx, esi
0x18000a74d  jmp     short loc_18000A715
0x18000a74f  test    rax, rax
0x18000a752  jz      short loc_18000A71D
0x18000a754  mov     r11, [rax+8]
0x18000a758  mov     rcx, [rcx+8]
0x18000a75c  mov     r8, [rcx]
0x18000a75f  test    r8, r8
0x18000a762  jnz     short loc_18000A769
0x18000a764  cmp     [r11], rsi
0x18000a767  jmp     short loc_18000A788
0x18000a769  mov     r11, [r11]
0x18000a76c  sub     r11, r8
0x18000a76f  movzx   r10d, word ptr [r8]
0x18000a773  movzx   ecx, word ptr [r8+r11]
0x18000a778  sub     r10d, ecx
0x18000a77b  jnz     short loc_18000A785
0x18000a77d  add     r8, 2
0x18000a781  test    ecx, ecx
0x18000a783  jnz     short loc_18000A76F
0x18000a785  test    r10d, r10d
0x18000a788  mov     ecx, esi
0x18000a78a  setz    cl
0x18000a78d  test    ecx, ecx
0x18000a78f  jnz     loc_18000A55D
0x18000a795  add     r9, 8
0x18000a799  cmp     r9, [rdx+8]
0x18000a79d  jnz     loc_18000A715
0x18000a7a3  jmp     loc_18000A55D
0x18000a7a8  mov     rdx, r14
0x18000a7ab  lea     rcx, aLoggingInforma_4; "Logging information: The time service i"...
0x18000a7b2  call    FileLogAdd
0x18000a7b7  jmp     loc_18000A665
0x18000a7bc  lea     r8, [rsp+1D8h+var_190]
0x18000a7c1  call    ??$_Emplace_reallocate@AEBV?$AutoPtr@VSourceChangeLogEntry@@@@@?$vector@V?$AutoPtr@VSourceChangeLogEntry@@@@V?$MyThrowingAllocator@V?$AutoPtr@VSourceChangeLogEntry@@@@@@@std@@AEAAPEAV?$AutoPtr@VSourceChangeLogEntry@@@@QEAV2@AEBV2@@Z; std::vector<AutoPtr<SourceChangeLogEntry>,MyThrowingAllocator<AutoPtr<SourceChangeLogEntry>>>::_Emplace_reallocate<AutoPtr<SourceChangeLogEntry> const &>(AutoPtr<SourceChangeLogEntry> * const,AutoPtr<SourceChangeLogEntry> const &)
0x18000a7c6  jmp     loc_18000A6F5
0x18000a7cb  jmp     short loc_18000A7CF
0x18000a7cd  jmp     short $+2
0x18000a7cf  mov     ebx, [rsp+1D8h+var_198]
0x18000a7d3  jmp     loc_18000A6F5
```

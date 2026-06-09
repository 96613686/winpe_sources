# EvtQuery

- ea: `0x18001cb20`
- end: `0x18001ce91`
- name: `EvtQuery`
- size: `881`
- prototype: `EVT_HANDLE __stdcall(EVT_HANDLE Session, LPCWSTR Path, LPCWSTR Query, DWORD Flags)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callees

- `0x180006870`
- `0x180006aec`
- `0x180007010`
- `0x180007940`
- `0x18000a100`
- `0x18000c404`
- `0x180013f6c`
- `0x18001cb20`
- `0x1800212dc`
- `0x180023548`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cc49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cc49`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
EVT_HANDLE __stdcall EvtQuery(EVT_HANDLE Session, LPCWSTR Path, LPCWSTR Query, DWORD Flags)
{
  __int64 v7; // rsi
  LPCWSTR v8; // rax
  int v9; // ecx
  __int64 v10; // rcx
  DWORD v11; // r14d
  void *v12; // r14
  __int64 v14; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v15; // [rsp+38h] [rbp-D0h] BYREF
  wmi::RefBase *v16; // [rsp+40h] [rbp-C8h] BYREF
  LPCWSTR v17; // [rsp+48h] [rbp-C0h] BYREF
  __int128 pExceptionObject; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+60h] [rbp-A8h]
  int v20; // [rsp+68h] [rbp-A0h]
  int v21; // [rsp+6Ch] [rbp-9Ch]
  int v22; // [rsp+70h] [rbp-98h]
  __int128 v23; // [rsp+78h] [rbp-90h] BYREF
  __int64 v24; // [rsp+88h] [rbp-80h]
  int v25; // [rsp+90h] [rbp-78h]
  int v26; // [rsp+94h] [rbp-74h]
  int v27; // [rsp+98h] [rbp-70h]
  __int128 v28; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v29; // [rsp+B0h] [rbp-58h]
  int v30; // [rsp+B8h] [rbp-50h]
  int v31; // [rsp+BCh] [rbp-4Ch]
  int v32; // [rsp+C0h] [rbp-48h]
  void *v33[2]; // [rsp+C8h] [rbp-40h] BYREF
  char v34; // [rsp+D8h] [rbp-30h] BYREF
  LPCWSTR v35; // [rsp+120h] [rbp+18h] BYREF
  DWORD v36; // [rsp+128h] [rbp+20h] BYREF

  v36 = Flags;
  v7 = 0;
  v14 = 0;
  LastErrInfo::Reset((LastErrInfo *)Session);
  if ( !Flags || (Flags & 0xFFFFECFC) != 0 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
    }
    v28 = 0;
    v29 = 0;
    v30 = 87;
    v31 = -1;
    v32 = 337;
    throw (EvtException *)&v28;
  }
  if ( (Flags & 3) == 3 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
    }
    pExceptionObject = 0;
    v19 = 0;
    v20 = 87;
    v21 = -1;
    v22 = 344;
    throw (EvtException *)&pExceptionObject;
  }
  if ( (Flags & 0x300) == 0x300 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
    }
    v23 = 0;
    v24 = 0;
    v25 = 87;
    v26 = -1;
    v27 = 351;
    throw (EvtException *)&v23;
  }
  v8 = L"*";
  if ( Query )
    v8 = Query;
  v35 = v8;
  v17 = Path;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v33);
  if ( (Flags & 2) != 0 && Path )
  {
    FullyQualifyFilePath(v33, Path);
    v17 = (LPCWSTR)v33[0];
  }
  GetSession(&v16);
  v15 = 0;
  v10 = HandleTable::Emplace<QueryResult,wmi::AutoRef<Session> &,wchar_t const * &,wchar_t const * &,unsigned long &>(
          v9,
          (unsigned int)&v15,
          (unsigned int)&v16,
          (unsigned int)&v17,
          (__int64)&v35,
          (__int64)&v36);
  if ( v10 )
  {
    *(_QWORD *)(v10 + 16) = v15;
    _InterlockedAdd((volatile signed __int32 *)(v10 + 8), 1u);
    _InterlockedAdd((volatile signed __int32 *)(v10 + 24), 1u);
    v7 = v10;
    v14 = v10;
    v15 = 0;
    EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v15);
    v11 = 0;
  }
  else
  {
    v11 = 14;
  }
  if ( v16 )
    wmi::RefBase::Release(v16);
  v16 = 0;
  if ( v33[0] != &v34 )
    operator delete(v33[0]);
  SetLastError(v11);
  if ( v7 )
  {
    v12 = *(void **)(v7 + 16);
    v14 = 0;
    *(_BYTE *)(v7 + 29) = 1;
  }
  else
  {
    v12 = 0;
  }
  EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v14);
  return v12;
}

```

## disassembly

```asm
0x18001cb20  mov     [rsp+arg_0], rsi
0x18001cb25  mov     [rsp+arg_8], rdi
0x18001cb2a  mov     [rsp+arg_18], r9d
0x18001cb2f  push    r12
0x18001cb31  push    r14
0x18001cb33  push    r15
0x18001cb35  sub     rsp, 0F0h
0x18001cb3c  mov     edi, r9d
0x18001cb3f  mov     r15, r8
0x18001cb42  mov     r14, rdx
0x18001cb45  mov     r12, rcx
0x18001cb48  xor     esi, esi
0x18001cb4a  mov     [rsp+108h+var_D8], rsi
0x18001cb4f  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x18001cb54  test    edi, edi
0x18001cb56  jz      loc_18001CDE8
0x18001cb5c  test    edi, 0FFFFECFCh
0x18001cb62  jnz     loc_18001CDE8
0x18001cb68  mov     eax, edi
0x18001cb6a  and     eax, 3
0x18001cb6d  cmp     al, 3
0x18001cb6f  jz      loc_18001CC90
0x18001cb75  mov     eax, edi
0x18001cb77  mov     ecx, 300h
0x18001cb7c  and     eax, ecx
0x18001cb7e  cmp     eax, ecx
0x18001cb80  jz      loc_18001CD06
0x18001cb86  lea     rax, asc_180040200; "*"
0x18001cb8d  test    r15, r15
0x18001cb90  cmovnz  rax, r15
0x18001cb94  mov     [rsp+108h+arg_10], rax
0x18001cb9c  mov     [rsp+108h+var_C0], r14
0x18001cba1  lea     rcx, [rsp+108h+var_40]
0x18001cba9  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001cbae  nop
0x18001cbaf  test    dil, 2
0x18001cbb3  jnz     loc_18001CD89
0x18001cbb9  mov     rdx, r12
0x18001cbbc  lea     rcx, [rsp+108h+var_C8]; void *
0x18001cbc1  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x18001cbc6  nop
0x18001cbc7  mov     [rsp+108h+var_D0], 0
0x18001cbd0  lea     rax, [rsp+108h+arg_18]
0x18001cbd8  mov     [rsp+108h+var_E0], rax
0x18001cbdd  lea     rax, [rsp+108h+arg_10]
0x18001cbe5  mov     [rsp+108h+var_E8], rax
0x18001cbea  lea     r9, [rsp+108h+var_C0]
0x18001cbef  lea     r8, [rsp+108h+var_C8]
0x18001cbf4  lea     rdx, [rsp+108h+var_D0]
0x18001cbf9  call    ??$Emplace@VQueryResult@@AEAV?$AutoRef@VSession@@@wmi@@AEAPEB_WAEAPEB_WAEAK@HandleTable@@QEAAPEAVQueryResult@@AEAPEAXAEAV?$AutoRef@VSession@@@wmi@@AEAPEB_W2AEAK@Z; HandleTable::Emplace<QueryResult,wmi::AutoRef<Session> &,wchar_t const * &,wchar_t const * &,ulong &>(void * &,wmi::AutoRef<Session> &,wchar_t const * &,wchar_t const * &,ulong &)
0x18001cbfe  mov     rcx, rax
0x18001cc01  mov     edi, 1
0x18001cc06  test    rax, rax
0x18001cc09  jnz     loc_18001CDB4
0x18001cc0f  lea     r14d, [rax+0Eh]
0x18001cc13  mov     rcx, [rsp+108h+var_C8]; this
0x18001cc18  test    rcx, rcx
0x18001cc1b  jz      short loc_18001CC22
0x18001cc1d  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18001cc22  mov     [rsp+108h+var_C8], 0
0x18001cc2b  lea     rax, [rsp+108h+var_30]
0x18001cc33  mov     rcx, [rsp+108h+var_40]; void *
0x18001cc3b  cmp     rcx, rax
0x18001cc3e  jz      short loc_18001CC46
0x18001cc40  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cc45  nop
0x18001cc46  mov     ecx, r14d; dwErrCode
0x18001cc49  call    cs:__imp_SetLastError
0x18001cc4f  test    rsi, rsi
0x18001cc52  jz      loc_18001CE88
0x18001cc58  mov     r14, [rsi+10h]
0x18001cc5c  mov     [rsp+108h+var_D8], 0
0x18001cc65  xchg    dil, [rsi+1Dh]
0x18001cc69  lea     rcx, [rsp+108h+var_D8]; this
0x18001cc6e  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x18001cc73  mov     rax, r14
0x18001cc76  lea     r11, [rsp+108h+var_18]
0x18001cc7e  mov     rsi, [r11+20h]
0x18001cc82  mov     rdi, [r11+28h]
0x18001cc86  mov     rsp, r11
0x18001cc89  pop     r15
0x18001cc8b  pop     r14
0x18001cc8d  pop     r12
0x18001cc8f  retn
0x18001cc90  lea     rax, WPP_GLOBAL_Control
0x18001cc97  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc9e  cmp     rcx, rax
0x18001cca1  jz      short loc_18001CCCB
0x18001cca3  mov     edi, 1
0x18001cca8  test    [rcx+1Ch], dil
0x18001ccac  jz      short loc_18001CCCB
0x18001ccae  cmp     byte ptr [rcx+19h], 2
0x18001ccb2  jb      short loc_18001CCCB
0x18001ccb4  lea     edx, [rdi+14h]
0x18001ccb7  lea     r9d, [rdi+56h]
0x18001ccbb  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18001ccc2  mov     rcx, [rcx+10h]
0x18001ccc6  call    WPP_SF_D
0x18001cccb  xorps   xmm0, xmm0
0x18001ccce  movdqu  [rsp+108h+pExceptionObject], xmm0
0x18001ccd4  mov     [rsp+108h+var_A8], 0
0x18001ccdd  mov     [rsp+108h+var_A0], 57h ; 'W'
0x18001cce5  mov     [rsp+108h+var_9C], 0FFFFFFFFh
0x18001cced  mov     [rsp+108h+var_98], 158h
0x18001ccf5  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001ccfc  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18001cd01  call    _CxxThrowException_0
0x18001cd06  lea     rax, WPP_GLOBAL_Control
0x18001cd0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd14  cmp     rcx, rax
0x18001cd17  jz      short loc_18001CD41
0x18001cd19  mov     edi, 1
0x18001cd1e  test    [rcx+1Ch], dil
0x18001cd22  jz      short loc_18001CD41
0x18001cd24  cmp     byte ptr [rcx+19h], 2
0x18001cd28  jb      short loc_18001CD41
0x18001cd2a  lea     edx, [rdi+15h]
0x18001cd2d  lea     r9d, [rdi+56h]
0x18001cd31  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18001cd38  mov     rcx, [rcx+10h]
0x18001cd3c  call    WPP_SF_D
0x18001cd41  xorps   xmm0, xmm0
0x18001cd44  movdqu  [rsp+108h+var_90], xmm0
0x18001cd4a  mov     [rsp+108h+var_80], 0
0x18001cd56  mov     [rsp+108h+var_78], 57h ; 'W'
0x18001cd61  mov     [rsp+108h+var_74], 0FFFFFFFFh
0x18001cd6c  mov     [rsp+108h+var_70], 15Fh
0x18001cd77  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001cd7e  lea     rcx, [rsp+108h+var_90]; pExceptionObject
0x18001cd83  call    _CxxThrowException_0
0x18001cd89  test    r14, r14
0x18001cd8c  jz      loc_18001CBB9
0x18001cd92  mov     rdx, r14
0x18001cd95  lea     rcx, [rsp+108h+var_40]
0x18001cd9d  call    FullyQualifyFilePath
0x18001cda2  mov     rax, [rsp+108h+var_40]
0x18001cdaa  mov     [rsp+108h+var_C0], rax
0x18001cdaf  jmp     loc_18001CBB9
0x18001cdb4  mov     rax, [rsp+108h+var_D0]
0x18001cdb9  mov     [rcx+10h], rax
0x18001cdbd  lock add [rcx+8], edi
0x18001cdc1  lock add [rcx+18h], edi
0x18001cdc5  mov     rsi, rcx
0x18001cdc8  mov     [rsp+108h+var_D8], rcx
0x18001cdcd  mov     [rsp+108h+var_D0], 0
0x18001cdd6  lea     rcx, [rsp+108h+var_D0]; this
0x18001cddb  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x18001cde0  xor     r14d, r14d
0x18001cde3  jmp     loc_18001CC13
0x18001cde8  lea     rax, WPP_GLOBAL_Control
0x18001cdef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cdf6  cmp     rcx, rax
0x18001cdf9  jz      short loc_18001CE23
0x18001cdfb  mov     edi, 1
0x18001ce00  test    [rcx+1Ch], dil
0x18001ce04  jz      short loc_18001CE23
0x18001ce06  cmp     byte ptr [rcx+19h], 2
0x18001ce0a  jb      short loc_18001CE23
0x18001ce0c  lea     edx, [rdi+13h]
0x18001ce0f  lea     r9d, [rdi+56h]
0x18001ce13  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x18001ce1a  mov     rcx, [rcx+10h]
0x18001ce1e  call    WPP_SF_D
0x18001ce23  xorps   xmm0, xmm0
0x18001ce26  movdqu  [rsp+108h+var_68], xmm0
0x18001ce2f  mov     [rsp+108h+var_58], 0
0x18001ce3b  mov     [rsp+108h+var_50], 57h ; 'W'
0x18001ce46  mov     [rsp+108h+var_4C], 0FFFFFFFFh
0x18001ce51  mov     [rsp+108h+var_48], 151h
0x18001ce5c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001ce63  lea     rcx, [rsp+108h+var_68]; pExceptionObject
0x18001ce6b  call    _CxxThrowException_0
0x18001ce71  mov     edi, 1
0x18001ce76  mov     r14d, [rsp+108h+arg_18]
0x18001ce7e  mov     rsi, [rsp+108h+var_D8]
0x18001ce83  jmp     loc_18001CC46
0x18001ce88  xor     r14d, r14d
0x18001ce8b  jmp     loc_18001CC69
```

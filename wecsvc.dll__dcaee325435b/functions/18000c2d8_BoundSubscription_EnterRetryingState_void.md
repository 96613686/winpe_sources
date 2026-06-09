# BoundSubscription::EnterRetryingState(void)

- ea: `0x18000c2d8`
- end: `0x18000c71c`
- name: `?EnterRetryingState@BoundSubscription@@AEAAXXZ`
- size: `1092`
- prototype: `void __fastcall(BoundSubscription *__hidden this)`
- caller_count: `4`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18000c0e8`
- `0x18000c724`
- `0x18000e81c`
- `0x18000eaf0`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18000bf44`
- `0x18000c2d8`
- `0x18000d480`
- `0x180011a10`
- `0x18001fe50`
- `0x180023010`

## import_xrefs

- `msvcrt!wcstol` at `0x18000c3db`
- `msvcrt!wcstol` at `0x18000c3db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c558`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000c54a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000c54a`

## string_xrefs

- `0x18000c5a1`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall BoundSubscription::EnterRetryingState(BoundSubscription *this)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rax
  __int64 v4; // r14
  unsigned int v5; // ecx
  unsigned int v6; // eax
  _QWORD *v7; // r14
  unsigned __int64 v8; // rsi
  bool v9; // r15
  bool v10; // cl
  __int64 v11; // rcx
  int v12; // ebx
  unsigned int v13; // eax
  unsigned int v14; // ecx
  _QWORD *v15; // r9
  const wchar_t *v16; // rax
  const wchar_t *v17; // rdx
  const wchar_t *v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rax
  const wchar_t *v21; // rax
  bool v22; // cf
  const wchar_t *v23; // r8
  __int64 v24; // rax
  const wchar_t *v25; // rax
  DWORD LastError; // ebx
  unsigned int v27; // ecx
  unsigned int v28; // eax
  _QWORD *v29; // r9
  const wchar_t *v30; // rax
  const wchar_t *v31; // rdx
  const wchar_t *v32; // r8
  __int64 v33; // rcx
  __int64 v34; // rax
  const wchar_t *v35; // rax
  const wchar_t *v36; // r8
  __int64 v37; // rax
  char *v38; // rax
  const wchar_t *v39; // rdi
  void **pExceptionObject; // [rsp+40h] [rbp-39h] BYREF
  int v41; // [rsp+48h] [rbp-31h]
  int v42; // [rsp+4Ch] [rbp-2Dh]
  const char *v43; // [rsp+50h] [rbp-29h]
  __int64 v44; // [rsp+58h] [rbp-21h]
  char *v45; // [rsp+60h] [rbp-19h]
  unsigned __int64 v46; // [rsp+68h] [rbp-11h]
  const wchar_t *v47; // [rsp+70h] [rbp-9h]
  int v48; // [rsp+78h] [rbp-1h]
  int v49; // [rsp+7Ch] [rbp+3h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v2 = (_QWORD *)((char *)this + 72);
    if ( v2[3] >= 8u )
      v2 = (_QWORD *)*v2;
    v3 = (_QWORD *)(*((_QWORD *)this + 8) + 56LL);
    if ( *(_QWORD *)(*((_QWORD *)this + 8) + 80LL) >= 8u )
      v3 = (_QWORD *)*v3;
    WPP_SF_dSSq(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v3, (__int64)v2, (char)this);
  }
  ++*((_DWORD *)this + 62);
  v4 = *((_QWORD *)this + 8);
  v5 = *((_DWORD *)this + 71);
  v6 = *(_DWORD *)(v4 + 144);
  if ( !v6 )
    v6 = -1;
  if ( v6 >= v5 )
    v7 = (_QWORD *)(v4 + 120);
  else
    v7 = 0;
  v8 = 0;
  v9 = v6 < v5;
  v10 = v6 < v5;
  if ( v7 )
  {
    while ( 1 )
    {
      v10 = v9;
      if ( v8 >= (__int64)(v7[1] - *v7) >> 5 )
        break;
      v11 = *v7 + 32 * v8;
      if ( *(_QWORD *)(v11 + 24) >= 8u )
        v11 = *(_QWORD *)v11;
      v12 = *((_DWORD *)this + 45);
      if ( v12 == wcstol((const wchar_t *)v11, 0, 0) )
        goto LABEL_55;
      ++v8;
    }
  }
  if ( v10 || (v13 = *((_DWORD *)this + 66), v14 = *((_DWORD *)this + 62), v14 >= v13) && v13 != -1 )
  {
LABEL_55:
    BoundSubscription::EnterInactiveState(this);
    v29 = (_QWORD *)*((_QWORD *)this + 8);
    v30 = (const wchar_t *)(v29 + 7);
    if ( v29[10] >= 8u )
      v30 = *(const wchar_t **)v30;
    v31 = &word_180026AD8;
    v32 = &word_180026AD8;
    if ( v30 )
      v32 = v30;
    v33 = -1;
    v34 = -1;
    do
      ++v34;
    while ( v32[v34] );
    pExceptionObject = (void **)v32;
    v41 = 2 * v34 + 2;
    v35 = (const wchar_t *)((char *)this + 72);
    v22 = *((_QWORD *)this + 12) < 8u;
    v42 = 0;
    if ( !v22 )
      v35 = *(const wchar_t **)v35;
    v36 = &word_180026AD8;
    if ( v35 )
      v36 = v35;
    v37 = -1;
    do
      ++v37;
    while ( v36[v37] );
    v43 = (const char *)v36;
    v44 = (unsigned int)(2 * v37 + 2);
    v38 = (char *)this + 180;
    v39 = (const wchar_t *)((char *)this + 184);
    v45 = v38;
    v46 = 4;
    if ( *((_QWORD *)v39 + 3) >= 8u )
      v39 = *(const wchar_t **)v39;
    if ( v39 )
      v31 = v39;
    do
      ++v33;
    while ( v31[v33] );
    v47 = v31;
    v48 = 2 * v33 + 2;
    v49 = 0;
    (*(void (__fastcall **)(_QWORD, __int64 *, __int64, void ***))(**(_QWORD **)(v29[13] + 136LL) + 8LL))(
      *(_QWORD *)(v29[13] + 136LL),
      EVTCOLL_EVENT_SOURCE_UNAVAILABLE,
      4,
      &pExceptionObject);
  }
  else
  {
    if ( v14 == 1 )
      *((_DWORD *)this + 63) = *((_DWORD *)this + 65);
    if ( v14 == 5 )
    {
      v15 = (_QWORD *)*((_QWORD *)this + 8);
      v16 = (const wchar_t *)(v15 + 7);
      if ( v15[10] >= 8u )
        v16 = *(const wchar_t **)v16;
      v17 = &word_180026AD8;
      v18 = &word_180026AD8;
      if ( v16 )
        v18 = v16;
      v19 = -1;
      v20 = -1;
      do
        ++v20;
      while ( v18[v20] );
      pExceptionObject = (void **)v18;
      v41 = 2 * v20 + 2;
      v21 = (const wchar_t *)((char *)this + 72);
      v22 = *((_QWORD *)this + 12) < 8u;
      v42 = 0;
      if ( !v22 )
        v21 = *(const wchar_t **)v21;
      v23 = &word_180026AD8;
      if ( v21 )
        v23 = v21;
      v24 = -1;
      do
        ++v24;
      while ( v23[v24] );
      v43 = (const char *)v23;
      v44 = (unsigned int)(2 * v24 + 2);
      v45 = (char *)this + 180;
      v25 = (const wchar_t *)((char *)this + 184);
      v22 = *((_QWORD *)this + 26) < 8u;
      v46 = 4;
      if ( !v22 )
        v25 = *(const wchar_t **)v25;
      if ( v25 )
        v17 = v25;
      do
        ++v19;
      while ( v17[v19] );
      v47 = v17;
      v48 = 2 * v19 + 2;
      v49 = 0;
      (*(void (__fastcall **)(_QWORD, __int64 *, __int64, void ***))(**(_QWORD **)(v15[13] + 136LL) + 8LL))(
        *(_QWORD *)(v15[13] + 136LL),
        EVTCOLL_SUBSCRIPTION_FIRSTFAILURE,
        4,
        &pExceptionObject);
    }
    *((_QWORD *)this + 34) = GetNextRetryTime(*((_DWORD *)this + 63));
    if ( !CreateTimerQueueTimer(
            (PHANDLE)this + 30,
            0,
            BoundSubscription::RetryTimerCallback,
            this,
            *((_DWORD *)this + 63),
            0,
            0) )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, LastError);
      }
      LOBYTE(v41) = 0;
      v43 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
      v44 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v45 = 0;
      v46 = LastError | 0xFFFFFFFF00000000uLL;
      LODWORD(v47) = 2004;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v27 = *((_DWORD *)this + 64);
    v28 = 2 * *((_DWORD *)this + 63);
    *((_DWORD *)this + 63) = v28;
    if ( v28 > v27 )
      *((_DWORD *)this + 63) = v27;
    *((_DWORD *)this + 14) = 3;
  }
}

```

## disassembly

```asm
0x18000c2d8  push    rbp
0x18000c2da  push    rbx
0x18000c2db  push    rsi
0x18000c2dc  push    rdi
0x18000c2dd  push    r12
0x18000c2df  push    r13
0x18000c2e1  push    r14
0x18000c2e3  push    r15
0x18000c2e5  lea     rbp, [rsp-1Fh]
0x18000c2ea  sub     rsp, 98h
0x18000c2f1  mov     rax, cs:__security_cookie
0x18000c2f8  xor     rax, rsp
0x18000c2fb  mov     [rbp+57h+var_50], rax
0x18000c2ff  mov     rdi, rcx
0x18000c302  mov     r8, cs:WPP_GLOBAL_Control
0x18000c309  lea     rax, WPP_GLOBAL_Control
0x18000c310  cmp     r8, rax
0x18000c313  jz      short loc_18000C364
0x18000c315  test    byte ptr [r8+1Ch], 10h
0x18000c31a  jz      short loc_18000C364
0x18000c31c  cmp     byte ptr [r8+19h], 5
0x18000c321  jb      short loc_18000C364
0x18000c323  add     rcx, 48h ; 'H'
0x18000c327  cmp     qword ptr [rcx+18h], 8
0x18000c32c  jb      short loc_18000C331
0x18000c32e  mov     rcx, [rcx]
0x18000c331  mov     rax, [rdi+40h]
0x18000c335  add     rax, 38h ; '8'
0x18000c339  cmp     qword ptr [rax+18h], 8
0x18000c33e  jb      short loc_18000C343
0x18000c340  mov     rax, [rax]
0x18000c343  mov     r9d, [rdi+38h]
0x18000c347  mov     edx, 33h ; '3'
0x18000c34c  mov     qword ptr [rsp+0D0h+Flags], rdi; char
0x18000c351  mov     qword ptr [rsp+0D0h+Period], rcx; __int64
0x18000c356  mov     rcx, [r8+10h]; LoggerHandle
0x18000c35a  mov     qword ptr [rsp+0D0h+DueTime], rax; __int64
0x18000c35f  call    WPP_SF_dSSq
0x18000c364  inc     dword ptr [rdi+0F8h]
0x18000c36a  or      r13d, 0FFFFFFFFh
0x18000c36e  mov     r14, [rdi+40h]
0x18000c372  xor     r12d, r12d
0x18000c375  mov     ecx, [rdi+11Ch]
0x18000c37b  mov     eax, [r14+90h]
0x18000c382  test    eax, eax
0x18000c384  cmovz   eax, r13d
0x18000c388  cmp     eax, ecx
0x18000c38a  jnb     short loc_18000C391
0x18000c38c  mov     r14d, r12d
0x18000c38f  jmp     short loc_18000C395
0x18000c391  add     r14, 78h ; 'x'
0x18000c395  cmp     eax, ecx
0x18000c397  mov     rsi, r12
0x18000c39a  setb    r15b
0x18000c39e  mov     cl, r15b
0x18000c3a1  test    r14, r14
0x18000c3a4  jz      short loc_18000C3EE
0x18000c3a6  mov     rdx, [r14]
0x18000c3a9  mov     cl, r15b
0x18000c3ac  mov     rax, [r14+8]
0x18000c3b0  sub     rax, rdx
0x18000c3b3  sar     rax, 5
0x18000c3b7  cmp     rsi, rax
0x18000c3ba  jnb     short loc_18000C3EE
0x18000c3bc  mov     rcx, rsi
0x18000c3bf  shl     rcx, 5
0x18000c3c3  add     rcx, rdx
0x18000c3c6  cmp     qword ptr [rcx+18h], 8
0x18000c3cb  jb      short loc_18000C3D0
0x18000c3cd  mov     rcx, [rcx]; String
0x18000c3d0  mov     ebx, [rdi+0B4h]
0x18000c3d6  xor     r8d, r8d; Radix
0x18000c3d9  xor     edx, edx; EndPtr
0x18000c3db  call    cs:__imp_wcstol
0x18000c3e1  cmp     ebx, eax
0x18000c3e3  jz      loc_18000C60C
0x18000c3e9  inc     rsi
0x18000c3ec  jmp     short loc_18000C3A6
0x18000c3ee  test    cl, cl
0x18000c3f0  jnz     loc_18000C60C
0x18000c3f6  mov     eax, [rdi+108h]
0x18000c3fc  mov     ecx, [rdi+0F8h]
0x18000c402  cmp     ecx, eax
0x18000c404  jb      short loc_18000C40F
0x18000c406  cmp     eax, r13d
0x18000c409  jnz     loc_18000C60C
0x18000c40f  cmp     ecx, 1
0x18000c412  jnz     short loc_18000C420
0x18000c414  mov     eax, [rdi+104h]
0x18000c41a  mov     [rdi+0FCh], eax
0x18000c420  cmp     ecx, 5
0x18000c423  jnz     loc_18000C511
0x18000c429  mov     r9, [rdi+40h]
0x18000c42d  lea     rax, [r9+38h]
0x18000c431  cmp     qword ptr [rax+18h], 8
0x18000c436  jb      short loc_18000C43B
0x18000c438  mov     rax, [rax]
0x18000c43b  test    rax, rax
0x18000c43e  lea     rdx, word_180026AD8
0x18000c445  mov     r8, rdx
0x18000c448  cmovnz  r8, rax
0x18000c44c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000c450  mov     rax, rcx
0x18000c453  inc     rax
0x18000c456  cmp     [r8+rax*2], r12w
0x18000c45b  jnz     short loc_18000C453
0x18000c45d  lea     eax, ds:2[rax*2]
0x18000c464  mov     [rbp+57h+pExceptionObject], r8
0x18000c468  mov     [rbp+57h+var_88], eax
0x18000c46b  lea     rax, [rdi+48h]
0x18000c46f  cmp     qword ptr [rax+18h], 8
0x18000c474  mov     [rbp+57h+var_84], r12d
0x18000c478  jb      short loc_18000C47D
0x18000c47a  mov     rax, [rax]
0x18000c47d  test    rax, rax
0x18000c480  mov     r8, rdx
0x18000c483  cmovnz  r8, rax
0x18000c487  mov     rax, rcx
0x18000c48a  inc     rax
0x18000c48d  cmp     [r8+rax*2], r12w
0x18000c492  jnz     short loc_18000C48A
0x18000c494  lea     eax, ds:2[rax*2]
0x18000c49b  mov     [rbp+57h+var_80], r8
0x18000c49f  mov     dword ptr [rbp+57h+var_78], eax
0x18000c4a2  mov     r8d, 4
0x18000c4a8  lea     rax, [rdi+0B4h]
0x18000c4af  mov     dword ptr [rbp+57h+var_78+4], r12d
0x18000c4b3  mov     [rbp+57h+var_70], rax
0x18000c4b7  lea     rax, [rdi+0B8h]
0x18000c4be  cmp     qword ptr [rax+18h], 8
0x18000c4c3  mov     [rbp+57h+var_68], r8
0x18000c4c7  jb      short loc_18000C4CC
0x18000c4c9  mov     rax, [rax]
0x18000c4cc  test    rax, rax
0x18000c4cf  cmovnz  rdx, rax
0x18000c4d3  inc     rcx
0x18000c4d6  cmp     [rdx+rcx*2], r12w
0x18000c4db  jnz     short loc_18000C4D3
0x18000c4dd  mov     [rbp+57h+var_60], rdx
0x18000c4e1  lea     eax, ds:2[rcx*2]
0x18000c4e8  mov     [rbp+57h+var_58], eax
0x18000c4eb  lea     rdx, EVTCOLL_SUBSCRIPTION_FIRSTFAILURE
0x18000c4f2  mov     [rbp+57h+var_54], r12d
0x18000c4f6  mov     rax, [r9+68h]
0x18000c4fa  lea     r9, [rbp+57h+pExceptionObject]
0x18000c4fe  mov     rcx, [rax+88h]
0x18000c505  mov     rax, [rcx]
0x18000c508  mov     rax, [rax+8]
0x18000c50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c511  mov     ecx, [rdi+0FCh]; unsigned int
0x18000c517  call    ?GetNextRetryTime@@YA_KK@Z; GetNextRetryTime(ulong)
0x18000c51c  mov     [rdi+110h], rax
0x18000c523  lea     rcx, [rdi+0F0h]; phNewTimer
0x18000c52a  mov     eax, [rdi+0FCh]
0x18000c530  lea     r8, ?RetryTimerCallback@BoundSubscription@@CAXPEAXE@Z; Callback
0x18000c537  mov     [rsp+0D0h+Flags], r12d; Flags
0x18000c53c  mov     r9, rdi; Parameter
0x18000c53f  mov     [rsp+0D0h+Period], r12d; Period
0x18000c544  xor     edx, edx; TimerQueue
0x18000c546  mov     [rsp+0D0h+DueTime], eax; DueTime
0x18000c54a  call    cs:__imp_CreateTimerQueueTimer
0x18000c550  test    eax, eax
0x18000c552  jnz     loc_18000C5E2
0x18000c558  call    cs:__imp_GetLastError
0x18000c55e  mov     ebx, eax
0x18000c560  mov     eax, 507h
0x18000c565  test    ebx, ebx
0x18000c567  cmovz   ebx, eax
0x18000c56a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c571  lea     rax, WPP_GLOBAL_Control
0x18000c578  cmp     rcx, rax
0x18000c57b  jz      short loc_18000C5A1
0x18000c57d  test    byte ptr [rcx+1Ch], 10h
0x18000c581  jz      short loc_18000C5A1
0x18000c583  cmp     byte ptr [rcx+19h], 2
0x18000c587  jb      short loc_18000C5A1
0x18000c589  mov     rcx, [rcx+10h]
0x18000c58d  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000c594  mov     edx, 34h ; '4'
0x18000c599  mov     r9d, ebx
0x18000c59c  call    WPP_SF_D
0x18000c5a1  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000c5a8  mov     byte ptr [rbp+57h+var_88], r12b
0x18000c5ac  mov     [rbp+57h+var_80], rax
0x18000c5b0  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000c5b7  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000c5be  mov     [rbp+57h+var_78], r12
0x18000c5c2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000c5c6  mov     [rbp+57h+pExceptionObject], rax
0x18000c5ca  mov     [rbp+57h+var_70], r12
0x18000c5ce  mov     dword ptr [rbp+57h+var_68], ebx
0x18000c5d1  mov     dword ptr [rbp+57h+var_68+4], r13d
0x18000c5d5  mov     dword ptr [rbp+57h+var_60], 7D4h
0x18000c5dc  call    _CxxThrowException_0
0x18000c5e2  mov     eax, [rdi+0FCh]
0x18000c5e8  mov     ecx, [rdi+100h]
0x18000c5ee  add     eax, eax
0x18000c5f0  mov     [rdi+0FCh], eax
0x18000c5f6  cmp     eax, ecx
0x18000c5f8  jbe     short loc_18000C600
0x18000c5fa  mov     [rdi+0FCh], ecx
0x18000c600  mov     dword ptr [rdi+38h], 3
0x18000c607  jmp     loc_18000C6FC
0x18000c60c  mov     rcx, rdi; this
0x18000c60f  call    ?EnterInactiveState@BoundSubscription@@AEAAXXZ; BoundSubscription::EnterInactiveState(void)
0x18000c614  mov     r9, [rdi+40h]
0x18000c618  lea     rax, [r9+38h]
0x18000c61c  cmp     qword ptr [rax+18h], 8
0x18000c621  jb      short loc_18000C626
0x18000c623  mov     rax, [rax]
0x18000c626  test    rax, rax
0x18000c629  lea     rdx, word_180026AD8
0x18000c630  mov     r8, rdx
0x18000c633  cmovnz  r8, rax
0x18000c637  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000c63b  mov     rax, rcx
0x18000c63e  inc     rax
0x18000c641  cmp     [r8+rax*2], r12w
0x18000c646  jnz     short loc_18000C63E
0x18000c648  lea     eax, ds:2[rax*2]
0x18000c64f  mov     [rbp+57h+pExceptionObject], r8
0x18000c653  mov     [rbp+57h+var_88], eax
0x18000c656  lea     rax, [rdi+48h]
0x18000c65a  cmp     qword ptr [rax+18h], 8
0x18000c65f  mov     [rbp+57h+var_84], r12d
0x18000c663  jb      short loc_18000C668
0x18000c665  mov     rax, [rax]
0x18000c668  test    rax, rax
0x18000c66b  mov     r8, rdx
0x18000c66e  cmovnz  r8, rax
0x18000c672  mov     rax, rcx
0x18000c675  inc     rax
0x18000c678  cmp     [r8+rax*2], r12w
0x18000c67d  jnz     short loc_18000C675
0x18000c67f  lea     eax, ds:2[rax*2]
0x18000c686  mov     [rbp+57h+var_80], r8
0x18000c68a  mov     dword ptr [rbp+57h+var_78], eax
0x18000c68d  mov     r8d, 4
0x18000c693  lea     rax, [rdi+0B4h]
0x18000c69a  mov     dword ptr [rbp+57h+var_78+4], r12d
0x18000c69e  add     rdi, 0B8h
0x18000c6a5  mov     [rbp+57h+var_70], rax
0x18000c6a9  mov     [rbp+57h+var_68], r8
0x18000c6ad  cmp     qword ptr [rdi+18h], 8
0x18000c6b2  jb      short loc_18000C6B7
0x18000c6b4  mov     rdi, [rdi]
0x18000c6b7  test    rdi, rdi
0x18000c6ba  cmovnz  rdx, rdi
0x18000c6be  inc     rcx
0x18000c6c1  cmp     [rdx+rcx*2], r12w
0x18000c6c6  jnz     short loc_18000C6BE
0x18000c6c8  mov     [rbp+57h+var_60], rdx
0x18000c6cc  lea     eax, ds:2[rcx*2]
0x18000c6d3  mov     [rbp+57h+var_58], eax
0x18000c6d6  lea     rdx, EVTCOLL_EVENT_SOURCE_UNAVAILABLE
0x18000c6dd  mov     [rbp+57h+var_54], r12d
0x18000c6e1  mov     rax, [r9+68h]
0x18000c6e5  lea     r9, [rbp+57h+pExceptionObject]
0x18000c6e9  mov     rcx, [rax+88h]
0x18000c6f0  mov     rax, [rcx]
0x18000c6f3  mov     rax, [rax+8]
0x18000c6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6fc  mov     rcx, [rbp+57h+var_50]
0x18000c700  xor     rcx, rsp; StackCookie
0x18000c703  call    __security_check_cookie
0x18000c708  add     rsp, 98h
0x18000c70f  pop     r15
0x18000c711  pop     r14
0x18000c713  pop     r13
0x18000c715  pop     r12
0x18000c717  pop     rdi
0x18000c718  pop     rsi
0x18000c719  pop     rbx
0x18000c71a  pop     rbp
0x18000c71b  retn
```

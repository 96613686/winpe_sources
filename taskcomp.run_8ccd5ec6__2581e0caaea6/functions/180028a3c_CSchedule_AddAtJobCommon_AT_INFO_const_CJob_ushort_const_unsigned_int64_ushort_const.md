# CSchedule::AddAtJobCommon(_AT_INFO const &,CJob * *,ushort * const,unsigned __int64,ushort * const)

- ea: `0x180028a3c`
- end: `0x180029150`
- name: `?AddAtJobCommon@CSchedule@@AEAAJAEBU_AT_INFO@@PEAPEAVCJob@@QEAG_K2@Z`
- size: `1812`
- prototype: `__int64 __usercall@<rax>(CSchedule *__hidden this@<rcx>, const struct _AT_INFO *@<rdx>, struct CJob **@<r8>, unsigned __int16 *const@<r9>, unsigned __int64, unsigned __int16 *const)`
- caller_count: `2`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800148d0`
- `0x180028990`

## callees

- `0x180003320`
- `0x1800040c0`
- `0x1800115d0`
- `0x180025234`
- `0x1800267fc`
- `0x18002729c`
- `0x180028664`
- `0x180028a3c`
- `0x180029158`
- `0x1800293f4`
- `0x180029658`
- `0x180029680`
- `0x1800297e4`
- `0x18002cfd4`
- `0x18002d0f0`
- `0x180030700`
- `0x180033010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180028ae4`
- `msvcrt!_itow_s` at `0x1800290c6`
- `msvcrt!_itow_s` at `0x180028ae4`
- `msvcrt!_itow_s` at `0x1800290c6`
- `msvcrt!wcspbrk` at `0x180028b7d`
- `msvcrt!wcspbrk` at `0x180028b7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180028ca6`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180028ca6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180028c5b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180028c5b`

## pseudocode

```c
__int64 __fastcall CSchedule::AddAtJobCommon(
        CSchedule *this,
        const struct _AT_INFO *a2,
        struct CJob **a3,
        unsigned __int16 *const a4,
        unsigned __int64 a5,
        unsigned __int16 *const Buffer)
{
  unsigned __int16 *v6; // r12
  CSchedule *v8; // r13
  CJob *v9; // rbx
  wchar_t *p_String; // r14
  unsigned __int64 i; // rdi
  __int16 v13; // ax
  int v14; // r14d
  int v15; // edi
  HINSTANCE v16; // rcx
  DWORD_PTR JobTime; // r8
  DWORD DaysOfMonth; // edi
  __int64 v19; // rdx
  DWORD_PTR v20; // r8
  bool v21; // zf
  char v22; // al
  CSchedule *v23; // rcx
  int v24; // r15d
  __int16 v25; // ax
  __int16 v26; // ax
  struct _SYSTEMTIME v27; // xmm6
  WORD v28; // si
  WORD v29; // r15
  unsigned __int16 v30; // di
  WORD v31; // r12
  int v32; // eax
  unsigned int v33; // [rsp+48h] [rbp-C0h] BYREF
  __int16 v34; // [rsp+50h] [rbp-B8h] BYREF
  __int16 v35; // [rsp+52h] [rbp-B6h]
  WORD wYear; // [rsp+54h] [rbp-B4h]
  WORD wMonth; // [rsp+56h] [rbp-B2h]
  WORD wDay; // [rsp+58h] [rbp-B0h]
  int v39; // [rsp+5Ah] [rbp-AEh]
  WORD v40; // [rsp+5Eh] [rbp-AAh]
  int v41; // [rsp+60h] [rbp-A8h]
  __int64 v42; // [rsp+64h] [rbp-A4h]
  int v43; // [rsp+6Ch] [rbp-9Ch]
  __int64 v44; // [rsp+70h] [rbp-98h]
  int v45; // [rsp+78h] [rbp-90h]
  int v46; // [rsp+7Ch] [rbp-8Ch]
  struct _SYSTEMTIME v47; // [rsp+88h] [rbp-80h] BYREF
  struct _SYSTEMTIME v48; // [rsp+98h] [rbp-70h] BYREF
  struct _SYSTEMTIME v49; // [rsp+A8h] [rbp-60h] BYREF
  struct _SYSTEMTIME v50; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int16 *v51; // [rsp+C8h] [rbp-40h]
  CSchedule *v52; // [rsp+D0h] [rbp-38h]
  wchar_t *v53; // [rsp+D8h] [rbp-30h]
  struct CJob **v54; // [rsp+E0h] [rbp-28h]
  struct _SYSTEMTIME v55; // [rsp+E8h] [rbp-20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+F8h] [rbp-10h] BYREF
  wchar_t String; // [rsp+108h] [rbp+0h] BYREF
  __int16 v58; // [rsp+10Ah] [rbp+2h] BYREF
  char v59; // [rsp+10Ch] [rbp+4h] BYREF
  WCHAR v60[88]; // [rsp+318h] [rbp+210h] BYREF

  v6 = a4;
  v51 = a4;
  v54 = a3;
  v8 = this;
  v52 = this;
  v53 = Buffer;
  if ( *((_DWORD *)this + 12) > 1u && (unsigned int)CSchedule::_AtTaskExists(this) == 1 )
    CSchedule::ResetAtID(v8);
  StringCchCopyW(v6, 0x105u, *((const unsigned __int16 **)v8 + 8));
  StringCchCatW(v6, 0x105u, L"\\At");
  _itow_s(*((_DWORD *)v8 + 12), Buffer, 0x10u, 10);
  StringCchCatW(v6, 0x105u, Buffer);
  StringCchCatW(v6, 0x105u, L".job");
  v9 = CJob::Create();
  if ( !v9 )
    return 2147942414LL;
  StringCchCopyW(&String, 0x104u, a2->Command);
  if ( String == 34 )
  {
    p_String = (wchar_t *)&v58;
    if ( !v58 )
    {
      i = 0;
      goto LABEL_21;
    }
    for ( i = (unsigned __int64)&v59; *(_WORD *)i; i += 2LL )
    {
      if ( *(_WORD *)i == 34 )
        goto LABEL_15;
    }
    i = 0;
  }
  else
  {
    p_String = &String;
    i = (unsigned __int64)wcspbrk(&String, L" \t");
  }
LABEL_15:
  if ( i )
  {
    *(_WORD *)i = 0;
    do
    {
      i += 2LL;
      v13 = *(_WORD *)i;
    }
    while ( *(_WORD *)i && (v13 == 32 || v13 == 9) );
    i &= -(__int64)(*(_WORD *)i != 0);
  }
LABEL_21:
  v14 = (*(__int64 (__fastcall **)(CJob *, wchar_t *))(*(_QWORD *)v9 + 256LL))(v9, p_String);
  if ( v14 < 0 )
  {
    (*(void (__fastcall **)(CJob *))(*(_QWORD *)v9 + 16LL))(v9);
    return (unsigned int)v14;
  }
  if ( i )
  {
    v15 = (*(__int64 (__fastcall **)(CJob *, unsigned __int64))(*(_QWORD *)v9 + 272LL))(v9, i);
    if ( v15 < 0 )
      goto LABEL_25;
  }
  *((_DWORD *)v9 + 22) |= 0x200002u;
  if ( (a2->Flags & 0x10) == 0 )
    *((_DWORD *)v9 + 22) |= 1u;
  v16 = g_hInstance;
  *((_DWORD *)v9 + 21) = 267008;
  if ( LoadStringW(v16, 0x44Bu, v60, 80) > 0 )
    (*(void (__fastcall **)(CJob *, WCHAR *))(*(_QWORD *)v9 + 144LL))(v9, v60);
  SystemTime = 0;
  v55 = 0;
  v47 = 0;
  v49 = 0;
  v50 = 0;
  v48 = 0;
  GetLocalTime(&SystemTime);
  JobTime = a2->JobTime;
  DaysOfMonth = a2->DaysOfMonth;
  v19 = (a2->JobTime * (unsigned __int128)0x179EC9CBD821DC3BuLL) >> 64;
  v55 = SystemTime;
  *(_DWORD *)&v55.wSecond = 0;
  v33 = DaysOfMonth;
  v44 = 0;
  v20 = (v19 + ((JobTime - v19) >> 1)) >> 15;
  v45 = 0;
  v55.wHour = (unsigned int)v20 / 0x3C;
  v21 = (a2->Flags & 8) == 0;
  *(_DWORD *)&v55.wMinute = (unsigned int)v20 % 0x3C;
  if ( v21 )
  {
    if ( !DaysOfMonth && !a2->DaysOfWeek && !(unsigned int)IsFirstTimeEarlier(&SystemTime, &v55) )
      IncrementDay(&v55);
  }
  else
  {
    DaysOfMonth |= 1 << (LOBYTE(v55.wDay) - 1);
    v33 = DaysOfMonth;
  }
  v39 = 0;
  v34 = 48;
  v35 = *((_WORD *)v9 + 16);
  wYear = v55.wYear;
  wMonth = v55.wMonth;
  wDay = v55.wDay;
  v41 = *(_DWORD *)&v55.wHour;
  v22 = ~a2->Flags;
  v40 = 0;
  v23 = (CSchedule *)(v22 & 1);
  v46 = 0;
  v43 = v22 & 1;
  v42 = 0;
  if ( DaysOfMonth )
  {
    v21 = (a2->Flags & 1) == 0;
    HIWORD(v44) = HIWORD(v33);
    LOWORD(v45) = 4095;
    LODWORD(v44) = 3;
    WORD2(v44) = DaysOfMonth;
    if ( v21 )
    {
      CalcDomTriggerDates(DaysOfMonth, &SystemTime, &v55, &v47, &v49, &v50, &v48);
      wYear = v47.wYear;
      wMonth = v47.wMonth;
      wDay = v47.wDay;
      v39 = *(_DWORD *)&v49.wYear;
      v40 = v49.wDay;
    }
    v15 = CDynamicArray<_TASK_TRIGGER>::Add((char *)v9 + 24, &v34);
    if ( v15 < 0 )
      goto LABEL_25;
    v23 = (CSchedule *)v50.wDay;
    if ( v50.wDay )
    {
      wYear = v50.wYear;
      wMonth = v50.wMonth;
      v39 = *(_DWORD *)&v48.wYear;
      v40 = v48.wDay;
      v25 = *((_WORD *)v9 + 16);
      wDay = v50.wDay;
      v35 = v25;
      v15 = CDynamicArray<_TASK_TRIGGER>::Add((char *)v9 + 24, &v34);
      if ( v15 < 0 )
        goto LABEL_25;
    }
  }
  else if ( !a2->DaysOfWeek )
  {
    v43 = 0;
    v24 = CDynamicArray<_TASK_TRIGGER>::Add((char *)v9 + 24, &v34);
    if ( v24 < 0 )
    {
      (*(void (__fastcall **)(CJob *))(*(_QWORD *)v9 + 16LL))(v9);
      return (unsigned int)v24;
    }
  }
  if ( a2->DaysOfWeek )
  {
    v35 = *((_WORD *)v9 + 16);
    v26 = 2 * a2->DaysOfWeek;
    LODWORD(v44) = 2;
    WORD2(v44) = 1;
    HIWORD(v44) = v26;
    if ( (v26 & 0x80u) != 0 )
      HIWORD(v44) = v26 & 0xFF7E | 1;
    if ( (a2->Flags & 1) == 0 )
    {
      v27 = SystemTime;
      v48 = SystemTime;
      if ( (unsigned int)IsFirstTimeEarlier(&v55, &SystemTime) )
      {
        IncrementDay(&v48);
        v27 = v48;
      }
      v47 = v27;
      v28 = v27.wYear;
      LOWORD(v33) = 0;
      v29 = v27.wMonth;
      v30 = v27.wDay + 6;
      v31 = v27.wDay + 6;
      if ( (int)MonthDays(v27.wMonth, v27.wYear, (unsigned __int16 *)&v33) >= 0 && v30 > (unsigned __int16)v33 )
      {
        v47.wDay = v30 - v33;
        IncrementMonth(&v47);
        v31 = v47.wDay;
        v29 = v47.wMonth;
        v28 = v47.wYear;
      }
      wYear = v27.wYear;
      v8 = v52;
      HIWORD(v39) = v29;
      wMonth = _mm_extract_epi16((__m128i)v27, 1);
      v40 = v31;
      v6 = v51;
      LOWORD(v39) = v28;
      wDay = _mm_extract_epi16((__m128i)v27, 3);
    }
    v15 = CDynamicArray<_TASK_TRIGGER>::Add((char *)v9 + 24, &v34);
    if ( v15 < 0 )
      goto LABEL_25;
  }
  v33 = 0;
  if ( CSchedule::GetAtTaskMaxHours(v23, &v33) >= 0 )
    (*(void (__fastcall **)(CJob *, _QWORD))(*(_QWORD *)v9 + 336LL))(v9, v33);
  *((_DWORD *)v9 + 22) = *((_DWORD *)v9 + 22) & 0xFFFFFFF | 0xD0000000;
  v32 = CJob::SaveWithRetry(v9, v6, 1, 5u);
  v15 = v32;
  if ( v32 < 0 )
  {
    if ( v32 != -2147024816
      || (GetNextAtID((unsigned int *)v8 + 12),
          StringCchCopyW(v6, 0x105u, *((const unsigned __int16 **)v8 + 8)),
          StringCchCatW(v6, 0x105u, L"\\At"),
          _itow_s(*((_DWORD *)v8 + 12), v53, 0x10u, 10),
          StringCchCatW(v6, 0x105u, v53),
          StringCchCatW(v6, 0x105u, L".job"),
          v15 = CJob::SaveWithRetry(v9, v6, 1, 5u),
          v15 < 0) )
    {
LABEL_25:
      (*(void (__fastcall **)(CJob *))(*(_QWORD *)v9 + 16LL))(v9);
      return (unsigned int)v15;
    }
  }
  *v54 = v9;
  return 0;
}

```

## disassembly

```asm
0x180028a3c  mov     rax, rsp
0x180028a3f  push    rbp
0x180028a40  push    rbx
0x180028a41  push    rsi
0x180028a42  push    rdi
0x180028a43  push    r12
0x180028a45  push    r13
0x180028a47  push    r14
0x180028a49  push    r15
0x180028a4b  lea     rbp, [rax-328h]
0x180028a52  sub     rsp, 3E8h
0x180028a59  movaps  xmmword ptr [rax-58h], xmm6
0x180028a5d  mov     rax, cs:__security_cookie
0x180028a64  xor     rax, rsp
0x180028a67  mov     [rbp+320h+var_60], rax
0x180028a6e  mov     rdi, [rbp+320h+Buffer]
0x180028a75  mov     r14d, 1
0x180028a7b  mov     r12, r9
0x180028a7e  mov     [rbp+320h+var_360], r9
0x180028a82  mov     rsi, rdx
0x180028a85  mov     [rbp+320h+var_348], r8
0x180028a89  mov     r13, rcx
0x180028a8c  mov     [rbp+320h+var_358], rcx
0x180028a90  mov     [rbp+320h+var_350], rdi
0x180028a94  cmp     [rcx+30h], r14d
0x180028a98  jbe     short loc_180028AAC
0x180028a9a  call    ?_AtTaskExists@CSchedule@@AEAAJXZ; CSchedule::_AtTaskExists(void)
0x180028a9f  cmp     eax, r14d
0x180028aa2  jnz     short loc_180028AAC
0x180028aa4  mov     rcx, r13; this
0x180028aa7  call    ?ResetAtID@CSchedule@@QEAAJXZ; CSchedule::ResetAtID(void)
0x180028aac  mov     r8, [r13+40h]; unsigned __int16 *
0x180028ab0  mov     r14d, 105h
0x180028ab6  mov     edx, r14d; unsigned __int64
0x180028ab9  mov     rcx, r12; unsigned __int16 *
0x180028abc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028ac1  lea     r8, aAt; "\\At"
0x180028ac8  mov     edx, r14d; unsigned __int64
0x180028acb  mov     rcx, r12; unsigned __int16 *
0x180028ace  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180028ad3  mov     ecx, [r13+30h]; Value
0x180028ad7  mov     r9d, 0Ah; Radix
0x180028add  mov     rdx, rdi; Buffer
0x180028ae0  lea     r8d, [r9+6]; BufferCount
0x180028ae4  call    cs:__imp__itow_s
0x180028aeb  nop     dword ptr [rax+rax+00h]
0x180028af0  mov     r8, rdi; unsigned __int16 *
0x180028af3  mov     edx, r14d; unsigned __int64
0x180028af6  mov     rcx, r12; unsigned __int16 *
0x180028af9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180028afe  lea     r8, aJob; ".job"
0x180028b05  mov     edx, r14d; unsigned __int64
0x180028b08  mov     rcx, r12; unsigned __int16 *
0x180028b0b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180028b10  call    ?Create@CJob@@SAPEAV1@XZ; CJob::Create(void)
0x180028b15  xor     r15d, r15d
0x180028b18  mov     rbx, rax
0x180028b1b  test    rax, rax
0x180028b1e  jnz     short loc_180028B2A
0x180028b20  mov     eax, 8007000Eh
0x180028b25  jmp     loc_180029118
0x180028b2a  mov     r8, [rsi+10h]; unsigned __int16 *
0x180028b2e  lea     rcx, [rbp+320h+String]; unsigned __int16 *
0x180028b32  mov     edx, 104h; unsigned __int64
0x180028b37  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028b3c  cmp     [rbp+320h+String], 22h ; '"'
0x180028b41  jnz     short loc_180028B6E
0x180028b43  lea     r14, [rbp+320h+var_31E]
0x180028b47  cmp     [rbp+320h+var_31E], r15w
0x180028b4c  jnz     short loc_180028B53
0x180028b4e  mov     rdi, r15
0x180028b51  jmp     short loc_180028BBB
0x180028b53  lea     rdi, [rbp+320h+var_31C]
0x180028b57  cmp     [rdi], r15w
0x180028b5b  jz      short loc_180028B69
0x180028b5d  cmp     word ptr [rdi], 22h ; '"'
0x180028b61  jz      short loc_180028B8C
0x180028b63  add     rdi, 2
0x180028b67  jmp     short loc_180028B57
0x180028b69  mov     rdi, r15
0x180028b6c  jmp     short loc_180028B8C
0x180028b6e  lea     rdx, Control; " \t"
0x180028b75  lea     rcx, [rbp+320h+String]; String
0x180028b79  lea     r14, [rbp+320h+String]
0x180028b7d  call    cs:__imp_wcspbrk
0x180028b84  nop     dword ptr [rax+rax+00h]
0x180028b89  mov     rdi, rax
0x180028b8c  test    rdi, rdi
0x180028b8f  jz      short loc_180028BBB
0x180028b91  mov     [rdi], r15w
0x180028b95  jmp     short loc_180028BA3
0x180028b97  cmp     ax, 20h ; ' '
0x180028b9b  jz      short loc_180028BA3
0x180028b9d  cmp     ax, 9
0x180028ba1  jnz     short loc_180028BAF
0x180028ba3  add     rdi, 2
0x180028ba7  movzx   eax, word ptr [rdi]
0x180028baa  test    ax, ax
0x180028bad  jnz     short loc_180028B97
0x180028baf  movzx   eax, word ptr [rdi]
0x180028bb2  neg     ax
0x180028bb5  sbb     rcx, rcx
0x180028bb8  and     rdi, rcx
0x180028bbb  mov     rax, [rbx]
0x180028bbe  mov     rdx, r14
0x180028bc1  mov     rcx, rbx
0x180028bc4  mov     rax, [rax+100h]
0x180028bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028bd0  mov     r14d, eax
0x180028bd3  test    eax, eax
0x180028bd5  jns     short loc_180028BEE
0x180028bd7  mov     rcx, [rbx]
0x180028bda  mov     rax, [rcx+10h]
0x180028bde  mov     rcx, rbx
0x180028be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028be6  mov     eax, r14d
0x180028be9  jmp     loc_180029118
0x180028bee  test    rdi, rdi
0x180028bf1  jz      short loc_180028C24
0x180028bf3  mov     rax, [rbx]
0x180028bf6  mov     rdx, rdi
0x180028bf9  mov     rcx, rbx
0x180028bfc  mov     rax, [rax+110h]
0x180028c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c08  mov     edi, eax
0x180028c0a  test    eax, eax
0x180028c0c  jns     short loc_180028C24
0x180028c0e  mov     rcx, [rbx]
0x180028c11  mov     rax, [rcx+10h]
0x180028c15  mov     rcx, rbx
0x180028c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c1d  mov     eax, edi
0x180028c1f  jmp     loc_180029118
0x180028c24  or      dword ptr [rbx+58h], 200002h
0x180028c2b  mov     r14d, 1
0x180028c31  test    byte ptr [rsi+0Dh], 10h
0x180028c35  jnz     short loc_180028C3B
0x180028c37  or      [rbx+58h], r14d
0x180028c3b  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180028c42  lea     r8, [rbp+320h+var_110]; lpBuffer
0x180028c49  mov     r9d, 50h ; 'P'; cchBufferMax
0x180028c4f  mov     dword ptr [rbx+54h], 41300h
0x180028c56  mov     edx, 44Bh; uID
0x180028c5b  call    cs:__imp_LoadStringW
0x180028c62  nop     dword ptr [rax+rax+00h]
0x180028c67  test    eax, eax
0x180028c69  jle     short loc_180028C84
0x180028c6b  mov     rax, [rbx]
0x180028c6e  lea     rdx, [rbp+320h+var_110]
0x180028c75  mov     rcx, rbx
0x180028c78  mov     rax, [rax+90h]
0x180028c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c84  xorps   xmm0, xmm0
0x180028c87  lea     rcx, [rbp+320h+SystemTime]; lpSystemTime
0x180028c8b  xorps   xmm1, xmm1
0x180028c8e  movups  xmmword ptr [rbp+320h+SystemTime.wYear], xmm0
0x180028c92  movups  xmmword ptr [rbp+320h+var_340.wYear], xmm1
0x180028c96  movups  xmmword ptr [rbp+320h+var_3A0.wYear], xmm0
0x180028c9a  movups  xmmword ptr [rbp+320h+var_380.wYear], xmm1
0x180028c9e  movups  xmmword ptr [rbp+320h+var_370.wYear], xmm0
0x180028ca2  movups  xmmword ptr [rbp+320h+var_390.wYear], xmm1
0x180028ca6  call    cs:__imp_GetLocalTime
0x180028cad  nop     dword ptr [rax+rax+00h]
0x180028cb2  mov     r8, [rsi]
0x180028cb5  mov     rax, 179EC9CBD821DC3Bh
0x180028cbf  movaps  xmm0, xmmword ptr [rbp+320h+SystemTime.wYear]
0x180028cc3  mov     edi, [rsi+8]
0x180028cc6  mul     r8
0x180028cc9  movdqa  xmmword ptr [rbp+320h+var_340.wYear], xmm0
0x180028cce  mov     eax, 88888889h
0x180028cd3  mov     dword ptr [rbp+320h+var_340.wSecond], r15d
0x180028cd7  sub     r8, rdx
0x180028cda  mov     [rsp+420h+var_3E0], edi
0x180028cde  shr     r8, 1
0x180028ce1  add     r8, rdx
0x180028ce4  mov     qword ptr [rsp+420h+var_3B8], r15
0x180028ce9  shr     r8, 0Fh
0x180028ced  mul     r8d
0x180028cf0  mov     [rsp+420h+var_3B0], r15d
0x180028cf5  shr     edx, 5
0x180028cf8  movzx   eax, dx
0x180028cfb  imul    ecx, eax, 3Ch ; '<'
0x180028cfe  mov     [rbp+320h+var_340.wHour], dx
0x180028d02  sub     r8w, cx
0x180028d06  test    byte ptr [rsi+0Dh], 8
0x180028d0a  mov     [rbp+320h+var_340.wMinute], r8w
0x180028d0f  jz      short loc_180028D2B
0x180028d11  mov     rcx, qword ptr [rbp+320h+var_340.wYear]
0x180028d15  mov     eax, r14d
0x180028d18  shr     rcx, 30h
0x180028d1c  sub     ecx, r14d
0x180028d1f  shl     eax, cl
0x180028d21  or      eax, edi
0x180028d23  mov     edi, eax
0x180028d25  mov     [rsp+420h+var_3E0], eax
0x180028d29  jmp     short loc_180028D4F
0x180028d2b  test    edi, edi
0x180028d2d  jnz     short loc_180028D4F
0x180028d2f  cmp     [rsi+0Ch], r15b
0x180028d33  jnz     short loc_180028D4F
0x180028d35  lea     rdx, [rbp+320h+var_340]; struct _SYSTEMTIME *
0x180028d39  lea     rcx, [rbp+320h+SystemTime]; struct _SYSTEMTIME *
0x180028d3d  call    ?IsFirstTimeEarlier@@YAHPEBU_SYSTEMTIME@@0@Z; IsFirstTimeEarlier(_SYSTEMTIME const *,_SYSTEMTIME const *)
0x180028d42  test    eax, eax
0x180028d44  jnz     short loc_180028D4F
0x180028d46  lea     rcx, [rbp+320h+var_340]; struct _SYSTEMTIME *
0x180028d4a  call    ?IncrementDay@@YAXPEAU_SYSTEMTIME@@@Z; IncrementDay(_SYSTEMTIME *)
0x180028d4f  mov     eax, 30h ; '0'
0x180028d54  mov     dword ptr [rsp+420h+var_3CE], r15d
0x180028d59  mov     [rsp+420h+var_3D8], ax
0x180028d5e  lea     r14, [rbx+18h]
0x180028d62  movzx   eax, word ptr [r14+8]
0x180028d67  mov     word ptr [rsp+420h+var_3D6], ax
0x180028d6c  movzx   eax, [rbp+320h+var_340.wYear]
0x180028d70  mov     word ptr [rsp+420h+var_3D6+2], ax
0x180028d75  movzx   eax, [rbp+320h+var_340.wMonth]
0x180028d79  mov     [rsp+420h+var_3D2], ax
0x180028d7e  movzx   eax, [rbp+320h+var_340.wDay]
0x180028d82  mov     [rsp+420h+var_3D0], ax
0x180028d87  movzx   eax, [rbp+320h+var_340.wHour]
0x180028d8b  mov     word ptr [rsp+420h+var_3CC+4], ax
0x180028d90  movzx   eax, [rbp+320h+var_340.wMinute]
0x180028d94  mov     word ptr [rsp+420h+var_3CC+6], ax
0x180028d99  mov     al, [rsi+0Dh]
0x180028d9c  not     al
0x180028d9e  mov     word ptr [rsp+420h+var_3CC+2], r15w
0x180028da4  movzx   ecx, al
0x180028da7  and     ecx, 1
0x180028daa  mov     [rsp+420h+var_3AC], r15d
0x180028daf  mov     dword ptr [rsp+420h+var_3C0+4], ecx
0x180028db3  mov     qword ptr [rsp+420h+var_3C4], r15
0x180028db8  test    edi, edi
0x180028dba  jnz     short loc_180028DFD
0x180028dbc  cmp     [rsi+0Ch], r15b
0x180028dc0  jnz     short loc_180028DF5
0x180028dc2  lea     rdx, [rsp+420h+var_3D8]
0x180028dc7  mov     dword ptr [rsp+420h+var_3C0+4], r15d
0x180028dcc  mov     rcx, r14
0x180028dcf  call    ?Add@?$CDynamicArray@U_TASK_TRIGGER@@@@QEAAJAEBU_TASK_TRIGGER@@@Z; CDynamicArray<_TASK_TRIGGER>::Add(_TASK_TRIGGER const &)
0x180028dd4  mov     r15d, eax
0x180028dd7  test    eax, eax
0x180028dd9  jns     short loc_180028DF2
0x180028ddb  mov     rcx, [rbx]
0x180028dde  mov     rax, [rcx+10h]
0x180028de2  mov     rcx, rbx
0x180028de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028dea  mov     eax, r15d
0x180028ded  jmp     loc_180029118
0x180028df2  xor     r15d, r15d
0x180028df5  test    edi, edi
0x180028df7  jz      loc_180028EFA
0x180028dfd  test    byte ptr [rsi+0Dh], 1
0x180028e01  movzx   eax, word ptr [rsp+420h+var_3E0+2]
0x180028e06  mov     word ptr [rsp+420h+var_3B4+2], ax
0x180028e0b  mov     eax, 0FFFh
0x180028e10  mov     word ptr [rsp+420h+var_3B0], ax
0x180028e15  mov     [rsp+420h+var_3B8], 3
0x180028e1d  mov     word ptr [rsp+420h+var_3B4], di
0x180028e22  jnz     short loc_180028E88
0x180028e24  lea     rax, [rbp+320h+var_390]
0x180028e28  mov     ecx, edi; unsigned int
0x180028e2a  mov     [rsp+30h], rax; struct _SYSTEMTIME *
0x180028e2f  lea     r9, [rbp+320h+var_3A0]; struct _SYSTEMTIME *
0x180028e33  lea     rax, [rbp+320h+var_370]
0x180028e37  mov     [rsp+420h+var_3F8], rax; struct _SYSTEMTIME *
0x180028e3c  lea     r8, [rbp+320h+var_340]; struct _SYSTEMTIME *
0x180028e40  lea     rax, [rbp+320h+var_380]
0x180028e44  lea     rdx, [rbp+320h+SystemTime]; struct _SYSTEMTIME *
0x180028e48  mov     [rsp+420h+var_400], rax; struct _SYSTEMTIME *
0x180028e4d  call    ?CalcDomTriggerDates@@YAXKAEBU_SYSTEMTIME@@0PEAU1@111@Z; CalcDomTriggerDates(ulong,_SYSTEMTIME const &,_SYSTEMTIME const &,_SYSTEMTIME *,_SYSTEMTIME *,_SYSTEMTIME *,_SYSTEMTIME *)
0x180028e52  movzx   eax, [rbp+320h+var_3A0.wYear]
0x180028e56  mov     word ptr [rsp+420h+var_3D6+2], ax
0x180028e5b  movzx   eax, [rbp+320h+var_3A0.wMonth]
0x180028e5f  mov     [rsp+420h+var_3D2], ax
0x180028e64  movzx   eax, [rbp+320h+var_3A0.wDay]
0x180028e68  mov     [rsp+420h+var_3D0], ax
0x180028e6d  movzx   eax, [rbp+320h+var_380.wYear]
0x180028e71  mov     [rsp+420h+var_3CE], ax
0x180028e76  movzx   eax, [rbp+320h+var_380.wMonth]
0x180028e7a  mov     word ptr [rsp+420h+var_3CC], ax
0x180028e7f  movzx   eax, [rbp+320h+var_380.wDay]
0x180028e83  mov     word ptr [rsp+420h+var_3CC+2], ax
0x180028e88  lea     rdx, [rsp+420h+var_3D8]
0x180028e8d  mov     rcx, r14
0x180028e90  call    ?Add@?$CDynamicArray@U_TASK_TRIGGER@@@@QEAAJAEBU_TASK_TRIGGER@@@Z; CDynamicArray<_TASK_TRIGGER>::Add(_TASK_TRIGGER const &)
0x180028e95  mov     edi, eax
0x180028e97  test    eax, eax
0x180028e99  js      loc_180028C0E
0x180028e9f  movzx   ecx, [rbp+320h+var_370.wDay]
0x180028ea3  test    cx, cx
0x180028ea6  jz      short loc_180028EFA
0x180028ea8  movzx   eax, [rbp+320h+var_370.wYear]
0x180028eac  lea     rdx, [rsp+420h+var_3D8]
0x180028eb1  mov     word ptr [rsp+420h+var_3D6+2], ax
0x180028eb6  movzx   eax, [rbp+320h+var_370.wMonth]
0x180028eba  mov     [rsp+420h+var_3D2], ax
0x180028ebf  movzx   eax, [rbp+320h+var_390.wYear]
0x180028ec3  mov     [rsp+420h+var_3CE], ax
0x180028ec8  movzx   eax, [rbp+320h+var_390.wMonth]
0x180028ecc  mov     word ptr [rsp+420h+var_3CC], ax
  ... truncated ...
```

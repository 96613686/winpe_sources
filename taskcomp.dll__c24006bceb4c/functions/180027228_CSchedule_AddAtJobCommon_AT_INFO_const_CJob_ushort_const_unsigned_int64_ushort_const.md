# CSchedule::AddAtJobCommon(_AT_INFO const &,CJob * *,ushort * const,unsigned __int64,ushort * const)

- ea: `0x180027228`
- end: `0x18002791d`
- name: `?AddAtJobCommon@CSchedule@@AEAAJAEBU_AT_INFO@@PEAPEAVCJob@@QEAG_K2@Z`
- size: `1781`
- prototype: `__int64 __fastcall(CSchedule *this, const struct _AT_INFO *, struct CJob **, unsigned __int16 *const, unsigned __int64, unsigned __int16 *const Buffer)`
- caller_count: `2`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013c80`
- `0x180027180`

## callees

- `0x1800031a0`
- `0x180003ef0`
- `0x180010b94`
- `0x180023ba0`
- `0x180025090`
- `0x180025b20`
- `0x180026e78`
- `0x180027228`
- `0x180027924`
- `0x180027bc4`
- `0x180027de4`
- `0x180027e08`
- `0x180027f48`
- `0x18002b398`
- `0x18002b4ac`
- `0x18002e5b0`
- `0x180031010`

## import_xrefs

- `msvcrt!_itow_s` at `0x1800272d0`
- `msvcrt!_itow_s` at `0x18002789a`
- `msvcrt!_itow_s` at `0x1800272d0`
- `msvcrt!_itow_s` at `0x18002789a`
- `msvcrt!wcspbrk` at `0x180027363`
- `msvcrt!wcspbrk` at `0x180027363`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180027480`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180027480`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002743b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002743b`

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
  CSchedule *wDay; // rcx
  signed int v24; // r15d
  __int16 v25; // ax
  __int16 v26; // ax
  struct _SYSTEMTIME v27; // xmm6
  WORD wYear; // si
  WORD wMonth; // r15
  unsigned __int16 v30; // di
  WORD v31; // r12
  int v32; // eax
  unsigned int v33; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v34; // [rsp+50h] [rbp-B8h] BYREF
  int v35; // [rsp+60h] [rbp-A8h]
  __int64 v36; // [rsp+64h] [rbp-A4h]
  int v37; // [rsp+6Ch] [rbp-9Ch]
  __int64 v38; // [rsp+70h] [rbp-98h]
  int v39; // [rsp+78h] [rbp-90h]
  int v40; // [rsp+7Ch] [rbp-8Ch]
  struct _SYSTEMTIME v41; // [rsp+88h] [rbp-80h] BYREF
  struct _SYSTEMTIME v42; // [rsp+98h] [rbp-70h] BYREF
  struct _SYSTEMTIME v43; // [rsp+A8h] [rbp-60h] BYREF
  struct _SYSTEMTIME v44; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int16 *v45; // [rsp+C8h] [rbp-40h]
  CSchedule *v46; // [rsp+D0h] [rbp-38h]
  wchar_t *v47; // [rsp+D8h] [rbp-30h]
  struct CJob **v48; // [rsp+E0h] [rbp-28h]
  struct _SYSTEMTIME v49; // [rsp+E8h] [rbp-20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+F8h] [rbp-10h] BYREF
  wchar_t String; // [rsp+108h] [rbp+0h] BYREF
  __int16 v52; // [rsp+10Ah] [rbp+2h] BYREF
  char v53; // [rsp+10Ch] [rbp+4h] BYREF
  WCHAR v54[88]; // [rsp+318h] [rbp+210h] BYREF

  v6 = a4;
  v45 = a4;
  v48 = a3;
  v8 = this;
  v46 = this;
  v47 = Buffer;
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
    p_String = (wchar_t *)&v52;
    if ( !v52 )
    {
      i = 0;
      goto LABEL_21;
    }
    for ( i = (unsigned __int64)&v53; *(_WORD *)i; i += 2LL )
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
  if ( LoadStringW(v16, 0x44Bu, v54, 80) > 0 )
    (*(void (__fastcall **)(CJob *, WCHAR *))(*(_QWORD *)v9 + 144LL))(v9, v54);
  SystemTime = 0;
  v49 = 0;
  v41 = 0;
  v43 = 0;
  v44 = 0;
  v42 = 0;
  GetLocalTime(&SystemTime);
  JobTime = a2->JobTime;
  DaysOfMonth = a2->DaysOfMonth;
  v19 = (a2->JobTime * (unsigned __int128)0x179EC9CBD821DC3BuLL) >> 64;
  v49 = SystemTime;
  *(_DWORD *)&v49.wSecond = 0;
  v33 = DaysOfMonth;
  v38 = 0;
  v20 = (v19 + ((JobTime - v19) >> 1)) >> 15;
  v39 = 0;
  v49.wHour = (unsigned int)v20 / 0x3C;
  v21 = (a2->Flags & 8) == 0;
  *(_DWORD *)&v49.wMinute = (unsigned int)v20 % 0x3C;
  if ( v21 )
  {
    if ( !DaysOfMonth && !a2->DaysOfWeek && !IsFirstTimeEarlier(&SystemTime, &v49) )
      IncrementDay(&v49);
  }
  else
  {
    DaysOfMonth |= 1 << (LOBYTE(v49.wDay) - 1);
    v33 = DaysOfMonth;
  }
  *(_DWORD *)((char *)&v34 + 10) = 0;
  LOWORD(v34) = 48;
  WORD1(v34) = *((_WORD *)v9 + 16);
  DWORD1(v34) = *(_DWORD *)&v49.wYear;
  WORD4(v34) = v49.wDay;
  v35 = *(_DWORD *)&v49.wHour;
  v22 = ~a2->Flags;
  HIWORD(v34) = 0;
  wDay = (CSchedule *)(v22 & 1);
  v40 = 0;
  v37 = v22 & 1;
  v36 = 0;
  if ( DaysOfMonth )
  {
    v21 = (a2->Flags & 1) == 0;
    HIWORD(v38) = HIWORD(v33);
    LOWORD(v39) = 4095;
    LODWORD(v38) = 3;
    WORD2(v38) = DaysOfMonth;
    if ( v21 )
    {
      CalcDomTriggerDates(DaysOfMonth, &SystemTime, &v49, &v41, &v43, &v44, &v42);
      DWORD1(v34) = *(_DWORD *)&v41.wYear;
      WORD4(v34) = v41.wDay;
      *(_DWORD *)((char *)&v34 + 10) = *(_DWORD *)&v43.wYear;
      HIWORD(v34) = v43.wDay;
    }
    v15 = CDynamicArray<_TASK_TRIGGER>::Add((char **)v9 + 3, &v34);
    if ( v15 < 0 )
      goto LABEL_25;
    wDay = (CSchedule *)v44.wDay;
    if ( v44.wDay )
    {
      DWORD1(v34) = *(_DWORD *)&v44.wYear;
      *(_DWORD *)((char *)&v34 + 10) = *(_DWORD *)&v42.wYear;
      HIWORD(v34) = v42.wDay;
      v25 = *((_WORD *)v9 + 16);
      WORD4(v34) = v44.wDay;
      WORD1(v34) = v25;
      v15 = CDynamicArray<_TASK_TRIGGER>::Add((char **)v9 + 3, &v34);
      if ( v15 < 0 )
        goto LABEL_25;
    }
  }
  else if ( !a2->DaysOfWeek )
  {
    v37 = 0;
    v24 = CDynamicArray<_TASK_TRIGGER>::Add((char **)v9 + 3, &v34);
    if ( v24 < 0 )
    {
      (*(void (__fastcall **)(CJob *))(*(_QWORD *)v9 + 16LL))(v9);
      return (unsigned int)v24;
    }
  }
  if ( a2->DaysOfWeek )
  {
    WORD1(v34) = *((_WORD *)v9 + 16);
    v26 = 2 * a2->DaysOfWeek;
    LODWORD(v38) = 2;
    WORD2(v38) = 1;
    HIWORD(v38) = v26;
    if ( (v26 & 0x80u) != 0 )
      HIWORD(v38) = v26 & 0xFF7E | 1;
    if ( (a2->Flags & 1) == 0 )
    {
      v27 = SystemTime;
      v42 = SystemTime;
      if ( IsFirstTimeEarlier(&v49, &SystemTime) )
      {
        IncrementDay(&v42);
        v27 = v42;
      }
      v41 = v27;
      wYear = v27.wYear;
      LOWORD(v33) = 0;
      wMonth = v27.wMonth;
      v30 = v27.wDay + 6;
      v31 = v27.wDay + 6;
      if ( (int)MonthDays(v27.wMonth, v27.wYear, (unsigned __int16 *)&v33) >= 0 && v30 > (unsigned __int16)v33 )
      {
        v41.wDay = v30 - v33;
        IncrementMonth(&v41);
        v31 = v41.wDay;
        wMonth = v41.wMonth;
        wYear = v41.wYear;
      }
      WORD2(v34) = v27.wYear;
      v8 = v46;
      WORD6(v34) = wMonth;
      WORD3(v34) = _mm_extract_epi16((__m128i)v27, 1);
      HIWORD(v34) = v31;
      v6 = v45;
      WORD5(v34) = wYear;
      WORD4(v34) = _mm_extract_epi16((__m128i)v27, 3);
    }
    v15 = CDynamicArray<_TASK_TRIGGER>::Add((char **)v9 + 3, &v34);
    if ( v15 < 0 )
      goto LABEL_25;
  }
  v33 = 0;
  if ( (int)CSchedule::GetAtTaskMaxHours(wDay, &v33) >= 0 )
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
          _itow_s(*((_DWORD *)v8 + 12), v47, 0x10u, 10),
          StringCchCatW(v6, 0x105u, v47),
          StringCchCatW(v6, 0x105u, L".job"),
          v15 = CJob::SaveWithRetry(v9, v6, 1, 5u),
          v15 < 0) )
    {
LABEL_25:
      (*(void (__fastcall **)(CJob *))(*(_QWORD *)v9 + 16LL))(v9);
      return (unsigned int)v15;
    }
  }
  *v48 = v9;
  return 0;
}

```

## disassembly

```asm
0x180027228  mov     rax, rsp
0x18002722b  push    rbp
0x18002722c  push    rbx
0x18002722d  push    rsi
0x18002722e  push    rdi
0x18002722f  push    r12
0x180027231  push    r13
0x180027233  push    r14
0x180027235  push    r15
0x180027237  lea     rbp, [rax-328h]
0x18002723e  sub     rsp, 3E8h
0x180027245  movaps  xmmword ptr [rax-58h], xmm6
0x180027249  mov     rax, cs:__security_cookie
0x180027250  xor     rax, rsp
0x180027253  mov     [rbp+320h+var_60], rax
0x18002725a  mov     rdi, [rbp+320h+Buffer]
0x180027261  mov     r14d, 1
0x180027267  mov     r12, r9
0x18002726a  mov     [rbp+320h+var_360], r9
0x18002726e  mov     rsi, rdx
0x180027271  mov     [rbp+320h+var_348], r8
0x180027275  mov     r13, rcx
0x180027278  mov     [rbp+320h+var_358], rcx
0x18002727c  mov     [rbp+320h+var_350], rdi
0x180027280  cmp     [rcx+30h], r14d
0x180027284  jbe     short loc_180027298
0x180027286  call    ?_AtTaskExists@CSchedule@@AEAAJXZ; CSchedule::_AtTaskExists(void)
0x18002728b  cmp     eax, r14d
0x18002728e  jnz     short loc_180027298
0x180027290  mov     rcx, r13; this
0x180027293  call    ?ResetAtID@CSchedule@@QEAAJXZ; CSchedule::ResetAtID(void)
0x180027298  mov     r8, [r13+40h]; unsigned __int16 *
0x18002729c  mov     r14d, 105h
0x1800272a2  mov     edx, r14d; unsigned __int64
0x1800272a5  mov     rcx, r12; unsigned __int16 *
0x1800272a8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800272ad  lea     r8, aAt; "\\At"
0x1800272b4  mov     edx, r14d; unsigned __int64
0x1800272b7  mov     rcx, r12; unsigned __int16 *
0x1800272ba  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800272bf  mov     ecx, [r13+30h]; Value
0x1800272c3  mov     r9d, 0Ah; Radix
0x1800272c9  mov     rdx, rdi; Buffer
0x1800272cc  lea     r8d, [r9+6]; BufferCount
0x1800272d0  call    cs:__imp__itow_s
0x1800272d6  mov     r8, rdi; unsigned __int16 *
0x1800272d9  mov     edx, r14d; unsigned __int64
0x1800272dc  mov     rcx, r12; unsigned __int16 *
0x1800272df  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800272e4  lea     r8, aJob; ".job"
0x1800272eb  mov     edx, r14d; unsigned __int64
0x1800272ee  mov     rcx, r12; unsigned __int16 *
0x1800272f1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800272f6  call    ?Create@CJob@@SAPEAV1@XZ; CJob::Create(void)
0x1800272fb  xor     r15d, r15d
0x1800272fe  mov     rbx, rax
0x180027301  test    rax, rax
0x180027304  jnz     short loc_180027310
0x180027306  mov     eax, 8007000Eh
0x18002730b  jmp     loc_1800278E6
0x180027310  mov     r8, [rsi+10h]; unsigned __int16 *
0x180027314  lea     rcx, [rbp+320h+String]; unsigned __int16 *
0x180027318  mov     edx, 104h; unsigned __int64
0x18002731d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027322  cmp     [rbp+320h+String], 22h ; '"'
0x180027327  jnz     short loc_180027354
0x180027329  lea     r14, [rbp+320h+var_31E]
0x18002732d  cmp     [rbp+320h+var_31E], r15w
0x180027332  jnz     short loc_180027339
0x180027334  mov     rdi, r15
0x180027337  jmp     short loc_18002739B
0x180027339  lea     rdi, [rbp+320h+var_31C]
0x18002733d  cmp     [rdi], r15w
0x180027341  jz      short loc_18002734F
0x180027343  cmp     word ptr [rdi], 22h ; '"'
0x180027347  jz      short loc_18002736C
0x180027349  add     rdi, 2
0x18002734d  jmp     short loc_18002733D
0x18002734f  mov     rdi, r15
0x180027352  jmp     short loc_18002736C
0x180027354  lea     rdx, Control; " \t"
0x18002735b  lea     rcx, [rbp+320h+String]; String
0x18002735f  lea     r14, [rbp+320h+String]
0x180027363  call    cs:__imp_wcspbrk
0x180027369  mov     rdi, rax
0x18002736c  test    rdi, rdi
0x18002736f  jz      short loc_18002739B
0x180027371  mov     [rdi], r15w
0x180027375  jmp     short loc_180027383
0x180027377  cmp     ax, 20h ; ' '
0x18002737b  jz      short loc_180027383
0x18002737d  cmp     ax, 9
0x180027381  jnz     short loc_18002738F
0x180027383  add     rdi, 2
0x180027387  movzx   eax, word ptr [rdi]
0x18002738a  test    ax, ax
0x18002738d  jnz     short loc_180027377
0x18002738f  movzx   eax, word ptr [rdi]
0x180027392  neg     ax
0x180027395  sbb     rcx, rcx
0x180027398  and     rdi, rcx
0x18002739b  mov     rax, [rbx]
0x18002739e  mov     rdx, r14
0x1800273a1  mov     rcx, rbx
0x1800273a4  mov     rax, [rax+100h]
0x1800273ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273b0  mov     r14d, eax
0x1800273b3  test    eax, eax
0x1800273b5  jns     short loc_1800273CE
0x1800273b7  mov     rcx, [rbx]
0x1800273ba  mov     rax, [rcx+10h]
0x1800273be  mov     rcx, rbx
0x1800273c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273c6  mov     eax, r14d
0x1800273c9  jmp     loc_1800278E6
0x1800273ce  test    rdi, rdi
0x1800273d1  jz      short loc_180027404
0x1800273d3  mov     rax, [rbx]
0x1800273d6  mov     rdx, rdi
0x1800273d9  mov     rcx, rbx
0x1800273dc  mov     rax, [rax+110h]
0x1800273e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273e8  mov     edi, eax
0x1800273ea  test    eax, eax
0x1800273ec  jns     short loc_180027404
0x1800273ee  mov     rcx, [rbx]
0x1800273f1  mov     rax, [rcx+10h]
0x1800273f5  mov     rcx, rbx
0x1800273f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273fd  mov     eax, edi
0x1800273ff  jmp     loc_1800278E6
0x180027404  or      dword ptr [rbx+58h], 200002h
0x18002740b  mov     r14d, 1
0x180027411  test    byte ptr [rsi+0Dh], 10h
0x180027415  jnz     short loc_18002741B
0x180027417  or      [rbx+58h], r14d
0x18002741b  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180027422  lea     r8, [rbp+320h+var_110]; lpBuffer
0x180027429  mov     r9d, 50h ; 'P'; cchBufferMax
0x18002742f  mov     dword ptr [rbx+54h], 41300h
0x180027436  mov     edx, 44Bh; uID
0x18002743b  call    cs:__imp_LoadStringW
0x180027441  test    eax, eax
0x180027443  jle     short loc_18002745E
0x180027445  mov     rax, [rbx]
0x180027448  lea     rdx, [rbp+320h+var_110]
0x18002744f  mov     rcx, rbx
0x180027452  mov     rax, [rax+90h]
0x180027459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002745e  xorps   xmm0, xmm0
0x180027461  lea     rcx, [rbp+320h+SystemTime]; lpSystemTime
0x180027465  xorps   xmm1, xmm1
0x180027468  movups  xmmword ptr [rbp+320h+SystemTime.wYear], xmm0
0x18002746c  movups  xmmword ptr [rbp+320h+var_340.wYear], xmm1
0x180027470  movups  xmmword ptr [rbp+320h+var_3A0.wYear], xmm0
0x180027474  movups  xmmword ptr [rbp+320h+var_380.wYear], xmm1
0x180027478  movups  xmmword ptr [rbp+320h+var_370.wYear], xmm0
0x18002747c  movups  xmmword ptr [rbp+320h+var_390.wYear], xmm1
0x180027480  call    cs:__imp_GetLocalTime
0x180027486  mov     r8, [rsi]
0x180027489  mov     rax, 179EC9CBD821DC3Bh
0x180027493  movaps  xmm0, xmmword ptr [rbp+320h+SystemTime.wYear]
0x180027497  mov     edi, [rsi+8]
0x18002749a  mul     r8
0x18002749d  movdqa  xmmword ptr [rbp+320h+var_340.wYear], xmm0
0x1800274a2  mov     eax, 88888889h
0x1800274a7  mov     dword ptr [rbp+320h+var_340.wSecond], r15d
0x1800274ab  sub     r8, rdx
0x1800274ae  mov     [rsp+420h+var_3E0], edi
0x1800274b2  shr     r8, 1
0x1800274b5  add     r8, rdx
0x1800274b8  mov     qword ptr [rsp+420h+var_3B8], r15
0x1800274bd  shr     r8, 0Fh
0x1800274c1  mul     r8d
0x1800274c4  mov     [rsp+420h+var_3B0], r15d
0x1800274c9  shr     edx, 5
0x1800274cc  movzx   eax, dx
0x1800274cf  imul    ecx, eax, 3Ch ; '<'
0x1800274d2  mov     [rbp+320h+var_340.wHour], dx
0x1800274d6  sub     r8w, cx
0x1800274da  test    byte ptr [rsi+0Dh], 8
0x1800274de  mov     [rbp+320h+var_340.wMinute], r8w
0x1800274e3  jz      short loc_1800274FF
0x1800274e5  mov     rcx, qword ptr [rbp+320h+var_340.wYear]
0x1800274e9  mov     eax, r14d
0x1800274ec  shr     rcx, 30h
0x1800274f0  sub     ecx, r14d
0x1800274f3  shl     eax, cl
0x1800274f5  or      eax, edi
0x1800274f7  mov     edi, eax
0x1800274f9  mov     [rsp+420h+var_3E0], eax
0x1800274fd  jmp     short loc_180027523
0x1800274ff  test    edi, edi
0x180027501  jnz     short loc_180027523
0x180027503  cmp     [rsi+0Ch], r15b
0x180027507  jnz     short loc_180027523
0x180027509  lea     rdx, [rbp+320h+var_340]; struct _SYSTEMTIME *
0x18002750d  lea     rcx, [rbp+320h+SystemTime]; struct _SYSTEMTIME *
0x180027511  call    ?IsFirstTimeEarlier@@YAHPEBU_SYSTEMTIME@@0@Z; IsFirstTimeEarlier(_SYSTEMTIME const *,_SYSTEMTIME const *)
0x180027516  test    eax, eax
0x180027518  jnz     short loc_180027523
0x18002751a  lea     rcx, [rbp+320h+var_340]; struct _SYSTEMTIME *
0x18002751e  call    ?IncrementDay@@YAXPEAU_SYSTEMTIME@@@Z; IncrementDay(_SYSTEMTIME *)
0x180027523  mov     eax, 30h ; '0'
0x180027528  mov     dword ptr [rsp+420h+var_3CE], r15d
0x18002752d  mov     [rsp+420h+var_3D8], ax
0x180027532  lea     r14, [rbx+18h]
0x180027536  movzx   eax, word ptr [r14+8]
0x18002753b  mov     word ptr [rsp+420h+var_3D6], ax
0x180027540  movzx   eax, [rbp+320h+var_340.wYear]
0x180027544  mov     word ptr [rsp+420h+var_3D6+2], ax
0x180027549  movzx   eax, [rbp+320h+var_340.wMonth]
0x18002754d  mov     [rsp+420h+var_3D2], ax
0x180027552  movzx   eax, [rbp+320h+var_340.wDay]
0x180027556  mov     [rsp+420h+var_3D0], ax
0x18002755b  movzx   eax, [rbp+320h+var_340.wHour]
0x18002755f  mov     word ptr [rsp+420h+var_3CC+4], ax
0x180027564  movzx   eax, [rbp+320h+var_340.wMinute]
0x180027568  mov     word ptr [rsp+420h+var_3CC+6], ax
0x18002756d  mov     al, [rsi+0Dh]
0x180027570  not     al
0x180027572  mov     word ptr [rsp+420h+var_3CC+2], r15w
0x180027578  movzx   ecx, al
0x18002757b  and     ecx, 1
0x18002757e  mov     [rsp+420h+var_3AC], r15d
0x180027583  mov     dword ptr [rsp+420h+var_3C0+4], ecx
0x180027587  mov     qword ptr [rsp+420h+var_3C4], r15
0x18002758c  test    edi, edi
0x18002758e  jnz     short loc_1800275D1
0x180027590  cmp     [rsi+0Ch], r15b
0x180027594  jnz     short loc_1800275C9
0x180027596  lea     rdx, [rsp+420h+var_3D8]
0x18002759b  mov     dword ptr [rsp+420h+var_3C0+4], r15d
0x1800275a0  mov     rcx, r14
0x1800275a3  call    ?Add@?$CDynamicArray@U_TASK_TRIGGER@@@@QEAAJAEBU_TASK_TRIGGER@@@Z; CDynamicArray<_TASK_TRIGGER>::Add(_TASK_TRIGGER const &)
0x1800275a8  mov     r15d, eax
0x1800275ab  test    eax, eax
0x1800275ad  jns     short loc_1800275C6
0x1800275af  mov     rcx, [rbx]
0x1800275b2  mov     rax, [rcx+10h]
0x1800275b6  mov     rcx, rbx
0x1800275b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275be  mov     eax, r15d
0x1800275c1  jmp     loc_1800278E6
0x1800275c6  xor     r15d, r15d
0x1800275c9  test    edi, edi
0x1800275cb  jz      loc_1800276CE
0x1800275d1  test    byte ptr [rsi+0Dh], 1
0x1800275d5  movzx   eax, word ptr [rsp+420h+var_3E0+2]
0x1800275da  mov     word ptr [rsp+420h+var_3B4+2], ax
0x1800275df  mov     eax, 0FFFh
0x1800275e4  mov     word ptr [rsp+420h+var_3B0], ax
0x1800275e9  mov     [rsp+420h+var_3B8], 3
0x1800275f1  mov     word ptr [rsp+420h+var_3B4], di
0x1800275f6  jnz     short loc_18002765C
0x1800275f8  lea     rax, [rbp+320h+var_390]
0x1800275fc  mov     ecx, edi; unsigned int
0x1800275fe  mov     [rsp+30h], rax; struct _SYSTEMTIME *
0x180027603  lea     r9, [rbp+320h+var_3A0]; struct _SYSTEMTIME *
0x180027607  lea     rax, [rbp+320h+var_370]
0x18002760b  mov     [rsp+420h+var_3F8], rax; struct _SYSTEMTIME *
0x180027610  lea     r8, [rbp+320h+var_340]; struct _SYSTEMTIME *
0x180027614  lea     rax, [rbp+320h+var_380]
0x180027618  lea     rdx, [rbp+320h+SystemTime]; struct _SYSTEMTIME *
0x18002761c  mov     [rsp+420h+var_400], rax; struct _SYSTEMTIME *
0x180027621  call    ?CalcDomTriggerDates@@YAXKAEBU_SYSTEMTIME@@0PEAU1@111@Z; CalcDomTriggerDates(ulong,_SYSTEMTIME const &,_SYSTEMTIME const &,_SYSTEMTIME *,_SYSTEMTIME *,_SYSTEMTIME *,_SYSTEMTIME *)
0x180027626  movzx   eax, [rbp+320h+var_3A0.wYear]
0x18002762a  mov     word ptr [rsp+420h+var_3D6+2], ax
0x18002762f  movzx   eax, [rbp+320h+var_3A0.wMonth]
0x180027633  mov     [rsp+420h+var_3D2], ax
0x180027638  movzx   eax, [rbp+320h+var_3A0.wDay]
0x18002763c  mov     [rsp+420h+var_3D0], ax
0x180027641  movzx   eax, [rbp+320h+var_380.wYear]
0x180027645  mov     [rsp+420h+var_3CE], ax
0x18002764a  movzx   eax, [rbp+320h+var_380.wMonth]
0x18002764e  mov     word ptr [rsp+420h+var_3CC], ax
0x180027653  movzx   eax, [rbp+320h+var_380.wDay]
0x180027657  mov     word ptr [rsp+420h+var_3CC+2], ax
0x18002765c  lea     rdx, [rsp+420h+var_3D8]
0x180027661  mov     rcx, r14
0x180027664  call    ?Add@?$CDynamicArray@U_TASK_TRIGGER@@@@QEAAJAEBU_TASK_TRIGGER@@@Z; CDynamicArray<_TASK_TRIGGER>::Add(_TASK_TRIGGER const &)
0x180027669  mov     edi, eax
0x18002766b  test    eax, eax
0x18002766d  js      loc_1800273EE
0x180027673  movzx   ecx, [rbp+320h+var_370.wDay]
0x180027677  test    cx, cx
0x18002767a  jz      short loc_1800276CE
0x18002767c  movzx   eax, [rbp+320h+var_370.wYear]
0x180027680  lea     rdx, [rsp+420h+var_3D8]
0x180027685  mov     word ptr [rsp+420h+var_3D6+2], ax
0x18002768a  movzx   eax, [rbp+320h+var_370.wMonth]
0x18002768e  mov     [rsp+420h+var_3D2], ax
0x180027693  movzx   eax, [rbp+320h+var_390.wYear]
0x180027697  mov     [rsp+420h+var_3CE], ax
0x18002769c  movzx   eax, [rbp+320h+var_390.wMonth]
0x1800276a0  mov     word ptr [rsp+420h+var_3CC], ax
0x1800276a5  movzx   eax, [rbp+320h+var_390.wDay]
0x1800276a9  mov     word ptr [rsp+420h+var_3CC+2], ax
0x1800276ae  movzx   eax, word ptr [rbx+20h]
0x1800276b2  mov     [rsp+420h+var_3D0], cx
  ... truncated ...
```

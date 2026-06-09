# CPropertyStore::_EnsureItems(uchar const *,uint)

- ea: `0x18000af70`
- end: `0x18000b72c`
- name: `?_EnsureItems@CPropertyStore@@AEAAJPEBEI@Z`
- size: `1980`
- prototype: `__int64 __fastcall(CPropertyStore *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a8e0`
- `0x18000ac40`
- `0x18001f800`

## callees

- `0x18000af70`
- `0x180022c04`
- `0x18002e0d8`
- `0x18002ff5c`
- `0x180035590`
- `0x180041ab0`
- `0x18006d490`
- `0x18006ef64`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000b295`
- `KERNEL32!GetLastError` at `0x18000b295`
- `KERNEL32!DeactivateActCtx` at `0x18000b2a4`
- `KERNEL32!DeactivateActCtx` at `0x18000b2c2`
- `KERNEL32!DeactivateActCtx` at `0x18000b2a4`
- `KERNEL32!DeactivateActCtx` at `0x18000b2c2`
- `KERNEL32!QueryPerformanceCounter` at `0x18000b2d8`
- `KERNEL32!QueryPerformanceCounter` at `0x18000b356`
- `KERNEL32!QueryPerformanceCounter` at `0x18000b4bb`
- `KERNEL32!QueryPerformanceCounter` at `0x18000b4f2`
- `KERNEL32!QueryPerformanceCounter` at `0x18000b565`
- `KERNEL32!QueryPerformanceCounter` at `0x18000b6c2`
- `KERNEL32!QueryPerformanceCounter` at `0x18000b2d8`
- `KERNEL32!QueryPerformanceCounter` at `0x18000b356`
- `KERNEL32!QueryPerformanceCounter` at `0x18000b4bb`
- `KERNEL32!QueryPerformanceCounter` at `0x18000b4f2`
- `KERNEL32!QueryPerformanceCounter` at `0x18000b565`
- `KERNEL32!QueryPerformanceCounter` at `0x18000b6c2`
- `KERNEL32!QueryPerformanceFrequency` at `0x18000b369`
- `KERNEL32!QueryPerformanceFrequency` at `0x18000b578`
- `KERNEL32!QueryPerformanceFrequency` at `0x18000b369`
- `KERNEL32!QueryPerformanceFrequency` at `0x18000b578`
- `KERNEL32!GetCurrentThreadId` at `0x18000b45b`
- `KERNEL32!GetCurrentThreadId` at `0x18000b669`
- `KERNEL32!GetCurrentThreadId` at `0x18000b45b`
- `KERNEL32!GetCurrentThreadId` at `0x18000b669`
- `KERNEL32!SetLastError` at `0x18000b2ac`
- `KERNEL32!SetLastError` at `0x18000b2ac`
- `ole32!CoCreateInstance` at `0x18000b048`
- `ole32!CoCreateInstance` at `0x18000b048`

## string_xrefs

- `0x18000b231`: `DPA_Create`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPropertyStore::_EnsureItems(CPropertyStore *this, const unsigned __int8 *a2, unsigned int a3)
{
  __int64 (__fastcall *v6)(__int64); // rbx
  __int64 v7; // rax
  HRESULT v8; // eax
  int v9; // r15d
  int v10; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  DWORD LastError; // ebx
  __int64 v16; // r9
  signed int LowPart; // ecx
  signed int v18; // ebx
  PVOID *v19; // rax
  double v20; // xmm1_8
  char v21; // bl
  char v22; // di
  DWORD CurrentThreadId; // eax
  const unsigned __int16 *CommandName; // rax
  char v25; // cl
  char v26; // r8
  signed int v27; // ecx
  signed int v28; // ebx
  PVOID *v29; // rax
  double v30; // xmm1_8
  char v31; // bl
  char v32; // di
  DWORD v33; // eax
  const unsigned __int16 *v34; // rax
  char v35; // cl
  char v36; // r8
  int v37; // [rsp+50h] [rbp-B8h]
  int v38; // [rsp+60h] [rbp-A8h]
  ULONG_PTR ulCookie[2]; // [rsp+78h] [rbp-90h] BYREF
  char v40[8]; // [rsp+88h] [rbp-80h]
  char v41[8]; // [rsp+90h] [rbp-78h]
  LARGE_INTEGER PerformanceCount[2]; // [rsp+98h] [rbp-70h] BYREF
  __int128 v43; // [rsp+A8h] [rbp-60h]
  LARGE_INTEGER Frequency; // [rsp+B8h] [rbp-50h] BYREF
  char v45; // [rsp+C0h] [rbp-48h]
  __int64 v46; // [rsp+C8h] [rbp-40h] BYREF
  LPVOID ppv; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v48; // [rsp+D8h] [rbp-30h] BYREF

  *(_QWORD *)v40 = 0;
  *(_QWORD *)v41 = 0;
  v45 = 0;
  *(_OWORD *)&PerformanceCount[0].LowPart = 0;
  v43 = 0;
  Frequency.QuadPart = 0;
  v48 = 0;
  ppv = 0;
  v46 = 0;
  if ( *((_QWORD *)this + 14) )
  {
    v9 = -2147418113;
    *((_DWORD *)this + 20) = 1;
    goto LABEL_30;
  }
  v6 = (__int64 (__fastcall *)(__int64))`IsolationAwareDPA_Create'::`2'::s_pfn;
  if ( `IsolationAwareDPA_Create'::`2'::s_pfn )
    goto LABEL_3;
  ulCookie[0] = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(ulCookie) )
  {
    *((_QWORD *)this + 14) = 0;
    goto LABEL_25;
  }
  v14 = Dpa_dsaIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("DPA_Create");
  v6 = (__int64 (__fastcall *)(__int64))v14;
  if ( !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( !v14 )
    {
      LastError = GetLastError();
      DeactivateActCtx(0, ulCookie[0]);
      SetLastError(LastError);
      *((_QWORD *)this + 14) = 0;
LABEL_25:
      v9 = -2147024882;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_29;
      v13 = 37;
      goto LABEL_70;
    }
    DeactivateActCtx(0, ulCookie[0]);
LABEL_44:
    `IsolationAwareDPA_Create'::`2'::s_pfn = (__int64)v6;
LABEL_3:
    v7 = v6(10);
    goto LABEL_4;
  }
  v7 = 0;
  if ( v6 )
    goto LABEL_44;
LABEL_4:
  *((_QWORD *)this + 14) = v7;
  if ( !v7 )
    goto LABEL_25;
  if ( !v45 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
  {
    QueryPerformanceCounter(PerformanceCount);
    *(_QWORD *)v40 = 22;
    *(_QWORD *)v41 = 0;
    v43 = 0;
    v45 = 1;
  }
  v8 = CoCreateInstance(&CLSID_WpdSerializer, 0, 1u, &GUID_b32f4002_bb27_45ff_af4f_06631c1e8dad, &ppv);
  v9 = v8;
  if ( v8 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_29;
    v13 = 38;
    v16 = (unsigned int)v8;
    goto LABEL_71;
  }
  v9 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int8 *, _QWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(
         ppv,
         a2,
         a3,
         &v46);
  if ( v9 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_29;
    v13 = 39;
    goto LABEL_70;
  }
  ulCookie[0] = 0;
  if ( *(_DWORD *)v40 == 22 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
  {
    QueryPerformanceCounter((LARGE_INTEGER *)ulCookie);
    LowPart = Frequency.LowPart;
    if ( Frequency.QuadPart
      || QueryPerformanceFrequency(&Frequency) && (LowPart = Frequency.LowPart, Frequency.QuadPart) )
    {
      v18 = LODWORD(ulCookie[0]) - PerformanceCount[0].LowPart;
      switch ( *(_DWORD *)v40 )
      {
        case 1:
          v19 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
            goto LABEL_60;
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids);
          LowPart = Frequency.LowPart;
          goto LABEL_58;
        case 2:
        case 4:
        case 5:
        case 6:
        case 7:
        case 8:
        case 9:
        case 0xA:
        case 0xB:
LABEL_58:
          v19 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_60;
        default:
          v19 = (PVOID *)WPP_GLOBAL_Control;
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          {
LABEL_60:
            if ( v19 != &WPP_GLOBAL_Control && (*((_DWORD *)v19 + 7) & 0x800) != 0 )
            {
              v20 = (double)v18 / (double)LowPart * 1000.0;
              v21 = v40[4];
              v22 = v41[0];
              CurrentThreadId = GetCurrentThreadId();
              CommandName = CPerfTraceHelper::GetCommandName((CPerfTraceHelper *)CurrentThreadId, *(unsigned int *)v40);
              WPP_SF_dDSdiddddDS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v26,
                (__int64)CommandName,
                v25,
                v22,
                (int)v20,
                v37,
                v21,
                v38,
                v9,
                (__int64)L"N/A");
            }
            QueryPerformanceCounter(&PerformanceCount[1]);
            v45 = 0;
          }
          break;
      }
    }
  }
  if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v46 + 224LL))(
         v46,
         &WPD_OBJECT_CONTENT_TYPE,
         &v48) >= 0 )
    *((_OWORD *)this + 3) = v48;
  *((_DWORD *)this + 20) = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, CPropertyStore *))(*(_QWORD *)v46 + 328LL))(v46, this);
  v9 = v10;
  if ( v10 >= 0 )
  {
    if ( !v45 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      QueryPerformanceCounter(PerformanceCount);
      *(_QWORD *)v40 = 21;
      *(_QWORD *)v41 = 0;
      v43 = 0;
      v45 = 1;
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, CPropertyStore *))(**((_QWORD **)this + 4) + 40LL))(
           *((_QWORD *)this + 4),
           *((_QWORD *)this + 5),
           0,
           this);
    if ( v9 >= 0 )
    {
      ulCookie[0] = 0;
      if ( *(_DWORD *)v40 == 21 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        QueryPerformanceCounter((LARGE_INTEGER *)ulCookie);
        v27 = Frequency.LowPart;
        if ( Frequency.QuadPart
          || QueryPerformanceFrequency(&Frequency) && (v27 = Frequency.LowPart, Frequency.QuadPart) )
        {
          v28 = LODWORD(ulCookie[0]) - PerformanceCount[0].LowPart;
          switch ( *(_DWORD *)v40 )
          {
            case 1:
              v29 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
                goto LABEL_82;
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids);
              v27 = Frequency.LowPart;
              goto LABEL_80;
            case 2:
            case 4:
            case 5:
            case 6:
            case 7:
            case 8:
            case 9:
            case 0xA:
            case 0xB:
LABEL_80:
              v29 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_82;
            default:
              v29 = (PVOID *)WPP_GLOBAL_Control;
              if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
              {
LABEL_82:
                if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x800) != 0 )
                {
                  v30 = (double)v28 / (double)v27 * 1000.0;
                  v31 = v40[4];
                  v32 = v41[0];
                  v33 = GetCurrentThreadId();
                  v34 = CPerfTraceHelper::GetCommandName((CPerfTraceHelper *)v33, *(unsigned int *)v40);
                  WPP_SF_dDSdiddddDS(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v36,
                    (__int64)v34,
                    v35,
                    v32,
                    (int)v30,
                    v37,
                    v31,
                    v38,
                    v9,
                    (__int64)L"N/A");
                }
                QueryPerformanceCounter(&PerformanceCount[1]);
                v45 = 0;
              }
              break;
          }
        }
      }
      *((_DWORD *)this + 20) = 1;
      goto LABEL_20;
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_29;
    v13 = 41;
LABEL_70:
    v16 = (unsigned int)v9;
    goto LABEL_71;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    goto LABEL_29;
  v13 = 40;
  v16 = (unsigned int)v10;
LABEL_71:
  WPP_SF_d(v12[2], v13, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids, v16);
LABEL_29:
  *((_DWORD *)this + 20) = 1;
LABEL_30:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids, (unsigned int)v9);
LABEL_20:
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000af70  mov     rax, rsp
0x18000af73  mov     [rax+20h], rbx
0x18000af77  push    rbp
0x18000af78  push    rsi
0x18000af79  push    rdi
0x18000af7a  push    r12
0x18000af7c  push    r13
0x18000af7e  push    r14
0x18000af80  push    r15
0x18000af82  lea     rbp, [rax-48h]
0x18000af86  sub     rsp, 110h
0x18000af8d  movaps  xmmword ptr [rax-48h], xmm6
0x18000af91  movaps  xmmword ptr [rax-58h], xmm7
0x18000af95  mov     rax, cs:__security_cookie
0x18000af9c  xor     rax, rsp
0x18000af9f  mov     [rbp+40h+var_60], rax
0x18000afa3  mov     esi, r8d
0x18000afa6  mov     rdi, rdx
0x18000afa9  mov     r14, rcx
0x18000afac  xor     r13d, r13d
0x18000afaf  mov     qword ptr [rbp+40h+var_C0], r13
0x18000afb3  mov     qword ptr [rbp+40h+var_B8], r13
0x18000afb7  mov     [rbp+40h+var_88], r13b
0x18000afbb  xorps   xmm0, xmm0
0x18000afbe  movdqa  xmmword ptr [rbp+40h+PerformanceCount], xmm0
0x18000afc3  xorps   xmm1, xmm1
0x18000afc6  movdqa  [rbp+40h+var_A0], xmm1
0x18000afcb  mov     qword ptr [rbp+40h+Frequency], r13
0x18000afcf  movups  [rbp+40h+var_70], xmm0
0x18000afd3  mov     [rbp+40h+var_78], r13
0x18000afd7  mov     [rbp+40h+var_80], r13
0x18000afdb  cmp     [rcx+70h], r13
0x18000afdf  jnz     loc_18000B257
0x18000afe5  mov     rbx, cs:?s_pfn@?1??IsolationAwareDPA_Create@@9@4P6APEAU_DPA@@H@ZEA; _DPA * (*`IsolationAwareDPA_Create'::`2'::s_pfn)(int)
0x18000afec  test    rbx, rbx
0x18000afef  jz      loc_18000B223
0x18000aff5  mov     ecx, 0Ah
0x18000affa  mov     rax, rbx
0x18000affd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b002  mov     [r14+70h], rax
0x18000b006  test    rax, rax
0x18000b009  jz      loc_18000B1A4
0x18000b00f  cmp     [rbp+40h+var_88], 0
0x18000b013  jnz     short loc_18000B029
0x18000b015  mov     rax, cs:WPP_GLOBAL_Control
0x18000b01c  test    dword ptr [rax+1Ch], 800h
0x18000b023  jnz     loc_18000B2D4
0x18000b029  lea     rax, [rbp+40h+var_78]
0x18000b02d  mov     [rsp+140h+ppv], rax; ppv
0x18000b032  lea     r9, _GUID_b32f4002_bb27_45ff_af4f_06631c1e8dad; riid
0x18000b039  xor     edx, edx; pUnkOuter
0x18000b03b  mov     r8d, 1; dwClsContext
0x18000b041  lea     rcx, CLSID_WpdSerializer; rclsid
0x18000b048  call    cs:__imp_CoCreateInstance
0x18000b04e  mov     r15d, eax
0x18000b051  test    eax, eax
0x18000b053  js      loc_18000B1CD
0x18000b059  mov     rcx, [rbp+40h+var_78]
0x18000b05d  mov     rax, [rcx]
0x18000b060  lea     r9, [rbp+40h+var_80]
0x18000b064  mov     r8d, esi
0x18000b067  mov     rdx, rdi
0x18000b06a  mov     rax, [rax+18h]
0x18000b06e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b073  mov     r15d, eax
0x18000b076  test    eax, eax
0x18000b078  js      loc_18000B312
0x18000b07e  mov     [rsp+140h+ulCookie], r13
0x18000b083  lea     r12, WPP_GLOBAL_Control
0x18000b08a  lea     rdi, __ImageBase
0x18000b091  xorps   xmm6, xmm6
0x18000b094  cmp     dword ptr [rbp+40h+var_C0], 16h
0x18000b098  jz      loc_18000B33D
0x18000b09e  mov     rcx, [rbp+40h+var_80]
0x18000b0a2  mov     rax, [rcx]
0x18000b0a5  lea     r8, [rbp+40h+var_70]
0x18000b0a9  lea     rdx, WPD_OBJECT_CONTENT_TYPE
0x18000b0b0  mov     rax, [rax+0E0h]
0x18000b0b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0bc  test    eax, eax
0x18000b0be  js      short loc_18000B0C9
0x18000b0c0  movups  xmm0, [rbp+40h+var_70]
0x18000b0c4  movups  xmmword ptr [r14+30h], xmm0
0x18000b0c9  mov     [r14+50h], r13d
0x18000b0cd  mov     rcx, [rbp+40h+var_80]
0x18000b0d1  mov     rax, [rcx]
0x18000b0d4  mov     rdx, r14
0x18000b0d7  mov     rax, [rax+148h]
0x18000b0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0e3  mov     r15d, eax
0x18000b0e6  test    eax, eax
0x18000b0e8  js      loc_18000B4CA
0x18000b0ee  cmp     [rbp+40h+var_88], 0
0x18000b0f2  jnz     short loc_18000B108
0x18000b0f4  mov     rax, cs:WPP_GLOBAL_Control
0x18000b0fb  test    dword ptr [rax+1Ch], 800h
0x18000b102  jnz     loc_18000B4EE
0x18000b108  mov     rcx, [r14+20h]
0x18000b10c  mov     rax, [rcx]
0x18000b10f  mov     r9, r14
0x18000b112  xor     r8d, r8d
0x18000b115  mov     rdx, [r14+28h]
0x18000b119  mov     rax, [rax+28h]
0x18000b11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b122  mov     r15d, eax
0x18000b125  test    eax, eax
0x18000b127  js      loc_18000B515
0x18000b12d  mov     [rsp+140h+ulCookie], r13
0x18000b132  cmp     dword ptr [rbp+40h+var_C0], 15h
0x18000b136  jz      loc_18000B54C
0x18000b13c  mov     dword ptr [r14+50h], 1
0x18000b144  mov     rcx, [rbp+40h+var_80]
0x18000b148  test    rcx, rcx
0x18000b14b  jz      short loc_18000B15A
0x18000b14d  mov     rax, [rcx]
0x18000b150  mov     rax, [rax+10h]
0x18000b154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b159  nop
0x18000b15a  mov     rcx, [rbp+40h+var_78]
0x18000b15e  test    rcx, rcx
0x18000b161  jz      short loc_18000B170
0x18000b163  mov     rax, [rcx]
0x18000b166  mov     rax, [rax+10h]
0x18000b16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b16f  nop
0x18000b170  mov     eax, r15d
0x18000b173  mov     rcx, [rbp+40h+var_60]
0x18000b177  xor     rcx, rsp; StackCookie
0x18000b17a  call    __security_check_cookie
0x18000b17f  lea     r11, [rsp+140h+var_30]
0x18000b187  mov     rbx, [r11+58h]
0x18000b18b  movaps  xmm6, xmmword ptr [r11-10h]
0x18000b190  movaps  xmm7, xmmword ptr [r11-20h]
0x18000b195  mov     rsp, r11
0x18000b198  pop     r15
0x18000b19a  pop     r14
0x18000b19c  pop     r13
0x18000b19e  pop     r12
0x18000b1a0  pop     rdi
0x18000b1a1  pop     rsi
0x18000b1a2  pop     rbp
0x18000b1a3  retn
0x18000b1a4  mov     r15d, 8007000Eh
0x18000b1aa  lea     r12, WPP_GLOBAL_Control
0x18000b1b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1b8  cmp     rcx, r12
0x18000b1bb  jz      short loc_18000B1E4
0x18000b1bd  test    byte ptr [rcx+1Ch], 2
0x18000b1c1  jz      short loc_18000B1E4
0x18000b1c3  mov     edx, 25h ; '%'
0x18000b1c8  jmp     loc_18000B534
0x18000b1cd  lea     r12, WPP_GLOBAL_Control
0x18000b1d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1db  cmp     rcx, r12
0x18000b1de  jnz     loc_18000B2FB
0x18000b1e4  mov     dword ptr [r14+50h], 1
0x18000b1ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1f3  cmp     rcx, r12
0x18000b1f6  jz      loc_18000B144
0x18000b1fc  test    byte ptr [rcx+1Ch], 2
0x18000b200  jz      loc_18000B144
0x18000b206  mov     edx, 2Ah ; '*'
0x18000b20b  mov     r9d, r15d
0x18000b20e  lea     r8, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids
0x18000b215  mov     rcx, [rcx+10h]
0x18000b219  call    WPP_SF_d
0x18000b21e  jmp     loc_18000B144
0x18000b223  mov     [rsp+140h+ulCookie], r13
0x18000b228  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000b22f  jz      short loc_18000B270
0x18000b231  lea     rcx, aDpaCreate; "DPA_Create"
0x18000b238  call    Dpa_dsaIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18000b23d  mov     rbx, rax
0x18000b240  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000b247  jz      short loc_18000B290
0x18000b249  mov     rax, r13
0x18000b24c  test    rbx, rbx
0x18000b24f  jz      loc_18000B002
0x18000b255  jmp     short loc_18000B2C8
0x18000b257  mov     r15d, 8000FFFFh
0x18000b25d  mov     dword ptr [rcx+50h], 1
0x18000b264  lea     r12, WPP_GLOBAL_Control
0x18000b26b  jmp     loc_18000B1EC
0x18000b270  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000b277  jnz     short loc_18000B231
0x18000b279  lea     rcx, [rsp+140h+ulCookie]; lpCookie
0x18000b27e  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000b283  test    eax, eax
0x18000b285  jnz     short loc_18000B231
0x18000b287  mov     [r14+70h], r13
0x18000b28b  jmp     loc_18000B1A4
0x18000b290  test    rbx, rbx
0x18000b293  jnz     short loc_18000B2BB
0x18000b295  call    cs:__imp_GetLastError
0x18000b29b  mov     ebx, eax
0x18000b29d  mov     rdx, [rsp+140h+ulCookie]; ulCookie
0x18000b2a2  xor     ecx, ecx; dwFlags
0x18000b2a4  call    cs:__imp_DeactivateActCtx
0x18000b2aa  mov     ecx, ebx; dwErrCode
0x18000b2ac  call    cs:__imp_SetLastError
0x18000b2b2  mov     [r14+70h], r13
0x18000b2b6  jmp     loc_18000B1A4
0x18000b2bb  mov     rdx, [rsp+140h+ulCookie]; ulCookie
0x18000b2c0  xor     ecx, ecx; dwFlags
0x18000b2c2  call    cs:__imp_DeactivateActCtx
0x18000b2c8  mov     cs:?s_pfn@?1??IsolationAwareDPA_Create@@9@4P6APEAU_DPA@@H@ZEA, rbx; _DPA * (*`IsolationAwareDPA_Create'::`2'::s_pfn)(int)
0x18000b2cf  jmp     loc_18000AFF5
0x18000b2d4  lea     rcx, [rbp+40h+PerformanceCount]; lpPerformanceCount
0x18000b2d8  call    cs:__imp_QueryPerformanceCounter
0x18000b2de  mov     qword ptr [rbp+40h+var_C0], 16h
0x18000b2e6  mov     qword ptr [rbp+40h+var_B8], r13
0x18000b2ea  xorps   xmm0, xmm0
0x18000b2ed  movdqa  [rbp+40h+var_A0], xmm0
0x18000b2f2  mov     [rbp+40h+var_88], 1
0x18000b2f6  jmp     loc_18000B029
0x18000b2fb  test    byte ptr [rcx+1Ch], 2
0x18000b2ff  jz      loc_18000B1E4
0x18000b305  mov     edx, 26h ; '&'
0x18000b30a  mov     r9d, eax
0x18000b30d  jmp     loc_18000B537
0x18000b312  lea     r12, WPP_GLOBAL_Control
0x18000b319  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b320  cmp     rcx, r12
0x18000b323  jz      loc_18000B1E4
0x18000b329  test    byte ptr [rcx+1Ch], 2
0x18000b32d  jz      loc_18000B1E4
0x18000b333  mov     edx, 27h ; '''
0x18000b338  jmp     loc_18000B534
0x18000b33d  mov     rax, cs:WPP_GLOBAL_Control
0x18000b344  test    dword ptr [rax+1Ch], 800h
0x18000b34b  jz      loc_18000B09E
0x18000b351  lea     rcx, [rsp+140h+ulCookie]; lpPerformanceCount
0x18000b356  call    cs:__imp_QueryPerformanceCounter
0x18000b35c  mov     rcx, qword ptr [rbp+40h+Frequency]
0x18000b360  test    rcx, rcx
0x18000b363  jnz     short loc_18000B384
0x18000b365  lea     rcx, [rbp+40h+Frequency]; lpFrequency
0x18000b369  call    cs:__imp_QueryPerformanceFrequency
0x18000b36f  test    eax, eax
0x18000b371  jz      loc_18000B09E
0x18000b377  mov     rcx, qword ptr [rbp+40h+Frequency]
0x18000b37b  test    rcx, rcx
0x18000b37e  jz      loc_18000B09E
0x18000b384  mov     rbx, [rsp+140h+ulCookie]
0x18000b389  mov     rdx, qword ptr [rbp+40h+PerformanceCount]
0x18000b38d  sub     rbx, rdx
0x18000b390  mov     eax, dword ptr [rbp+40h+var_C0]
0x18000b393  dec     eax; switch 11 cases
0x18000b395  cmp     eax, 0Ah
0x18000b398  ja      short def_18000B3A4; jumptable 000000018000B3A4 default case, case 3
0x18000b39a  mov     eax, ds:(jpt_18000B3A4 - 180000000h)[rdi+rax*4]
0x18000b3a1  add     rax, rdi
0x18000b3a4  jmp     rax; switch jump
0x18000b3a6  mov     rax, cs:WPP_GLOBAL_Control; jumptable 000000018000B3A4 case 1
0x18000b3ad  cmp     rax, r12
0x18000b3b0  jz      short loc_18000B3F5
0x18000b3b2  test    dword ptr [rax+1Ch], 800h
0x18000b3b9  jz      short loc_18000B3F5
0x18000b3bb  mov     edx, 7Dh ; '}'
0x18000b3c0  lea     r8, WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids
0x18000b3c7  mov     rcx, [rax+10h]
0x18000b3cb  call    WPP_SF_
0x18000b3d0  mov     rcx, qword ptr [rbp+40h+Frequency]
0x18000b3d4  mov     rdx, qword ptr [rbp+40h+PerformanceCount]
0x18000b3d8  mov     rax, cs:WPP_GLOBAL_Control; jumptable 000000018000B3A4 cases 2,4-11
0x18000b3df  jmp     short loc_18000B3F5
0x18000b3e1  mov     rax, cs:WPP_GLOBAL_Control; jumptable 000000018000B3A4 default case, case 3
0x18000b3e8  test    dword ptr [rax+1Ch], 1000h
0x18000b3ef  jz      loc_18000B09E
0x18000b3f5  mov     r8, qword ptr [rbp+40h+PerformanceCount+8]
0x18000b3f9  xorps   xmm7, xmm7
0x18000b3fc  test    r8, r8
0x18000b3ff  jz      short loc_18000B41D
0x18000b401  sub     rdx, r8
0x18000b404  cvtsi2sd xmm7, rdx
0x18000b409  xorps   xmm0, xmm0
0x18000b40c  cvtsi2sd xmm0, rcx
0x18000b411  divsd   xmm7, xmm0
0x18000b415  mulsd   xmm7, cs:__real@408f400000000000
0x18000b41d  cmp     rax, r12
0x18000b420  jz      loc_18000B4B7
0x18000b426  test    dword ptr [rax+1Ch], 800h
0x18000b42d  jz      loc_18000B4B7
0x18000b433  xorps   xmm1, xmm1
0x18000b436  cvtsi2sd xmm1, rbx
0x18000b43b  xorps   xmm0, xmm0
0x18000b43e  cvtsi2sd xmm0, rcx
0x18000b443  divsd   xmm1, xmm0
0x18000b447  mulsd   xmm1, cs:__real@408f400000000000
0x18000b44f  cvttsd2si rsi, xmm1
0x18000b454  mov     ebx, dword ptr [rbp+40h+var_C0+4]
0x18000b457  mov     rdi, qword ptr [rbp+40h+var_B8]
0x18000b45b  call    cs:__imp_GetCurrentThreadId
0x18000b461  mov     ecx, eax; this
0x18000b463  mov     r8d, dword ptr [rbp+40h+var_C0]
0x18000b467  mov     edx, r8d; unsigned int
0x18000b46a  call    ?GetCommandName@CPerfTraceHelper@@QEAAPEBGK@Z; CPerfTraceHelper::GetCommandName(ulong)
0x18000b46f  cvttsd2si r9, xmm7
0x18000b474  lea     rdx, aNA; "N/A"
0x18000b47b  mov     [rsp+140h+var_D8], rdx; __int64
  ... truncated ...
```

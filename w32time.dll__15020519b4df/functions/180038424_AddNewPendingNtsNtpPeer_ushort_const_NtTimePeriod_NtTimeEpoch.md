# AddNewPendingNtsNtpPeer(ushort const *,NtTimePeriod,NtTimeEpoch)

- ea: `0x180038424`
- end: `0x1800386ce`
- name: `?AddNewPendingNtsNtpPeer@@YAJPEBGUNtTimePeriod@@UNtTimeEpoch@@@Z`
- size: `682`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180022060`
- `0x18003a900`
- `0x1800462f4`

## callees

- `0x18000bde0`
- `0x1800164b0`
- `0x1800173bc`
- `0x180018138`
- `0x180019714`
- `0x18001d9a0`
- `0x18002cc6c`
- `0x180038424`
- `0x18003d294`
- `0x18003dd2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180038562`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180038562`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180038548`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180038548`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800385fa`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18003865d`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800385fa`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18003865d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800384f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800384f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038698`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038698`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800385e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800385e7`

## string_xrefs

- `0x18003845b`: `Failing as we are attempting to call AddNewPendingNtsNtpPeer when nts feature is not enabled.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AddNewPendingNtsNtpPeer(const unsigned __int16 *a1, __int64 a2, __int64 a3)
{
  __int64 v7; // rcx
  __int64 v8; // rax
  unsigned __int64 v9; // rsi
  unsigned __int16 *v10; // rcx
  int v11; // esi
  wchar_t *v12; // rax
  unsigned int v13; // eax
  volatile signed __int32 *v14; // rax
  __int64 v15; // rdx
  char *v16; // rcx
  _QWORD *v17; // rdx
  volatile signed __int32 *v18; // rax
  unsigned int v19; // eax
  volatile signed __int32 *v20; // [rsp+20h] [rbp-68h] BYREF
  __int64 v21; // [rsp+28h] [rbp-60h]
  _BYTE v22[24]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v23[24]; // [rsp+48h] [rbp-40h] BYREF
  int v24; // [rsp+60h] [rbp-28h]
  void *v25; // [rsp+A8h] [rbp+20h]
  unsigned int v27; // [rsp+A8h] [rbp+20h]
  int v28; // [rsp+A8h] [rbp+20h]
  int v29; // [rsp+A8h] [rbp+20h]

  if ( *((_BYTE *)g_pnpstate + 50) )
  {
    v25 = operator new(0x610u);
    memset_0(v25, 0, 0x610u);
    AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v20, v25);
    if ( !v20 )
      goto LABEL_29;
    v7 = *((_QWORD *)v20 + 1);
    if ( !v7 )
      goto LABEL_29;
    *(_DWORD *)(v7 + 48) = 4;
    *(_DWORD *)(*((_QWORD *)v20 + 1) + 56LL) = 3;
    v8 = -1;
    do
      ++v8;
    while ( a1[v8] );
    v9 = v8 + 1;
    *(_QWORD *)(*((_QWORD *)v20 + 1) + 72LL) = LocalAlloc(0x40u, 2 * (v8 + 1));
    v10 = *(unsigned __int16 **)(*((_QWORD *)v20 + 1) + 72LL);
    if ( v10 )
    {
      v11 = StringCchCopyW(v10, v9, a1);
      if ( v11 >= 0 )
      {
        v12 = wcschr(*(const wchar_t **)(*((_QWORD *)v20 + 1) + 72LL), 0x2Cu);
        if ( v12 )
        {
          v13 = wcstoul(v12 + 1, 0, 0);
          *(_DWORD *)(*((_QWORD *)v20 + 1) + 80LL) = v13;
        }
        else
        {
          *(_DWORD *)(*((_QWORD *)v20 + 1) + 80LL) = 0;
        }
        v14 = v20;
        v15 = *((_QWORD *)v20 + 1);
        if ( (*(_DWORD *)(v15 + 80) & 1) != 0 )
        {
          *(_QWORD *)(v15 + 280) = a2;
          v14 = v20;
        }
        *(_QWORD *)(*((_QWORD *)v14 + 1) + 832LL) = a3;
        v11 = myInitializeCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)v20 + 1) + 8LL));
        if ( v11 >= 0 )
        {
          **((_BYTE **)v20 + 1) = 1;
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
          v21 = _set_se_translator(SeTransFunc);
          v11 = 0;
          try
          {
            v16 = (char *)g_pnpstate + 432;
            v17 = (_QWORD *)*((_QWORD *)g_pnpstate + 55);
            if ( v17 == *((_QWORD **)g_pnpstate + 56) )
            {
              std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::_Emplace_reallocate<AutoPtr<NtpPeer> const &>(
                v16,
                v17,
                &v20);
            }
            else
            {
              v18 = v20;
              *v17 = v20;
              if ( v18 )
                _InterlockedIncrement(v18);
              *((_QWORD *)v16 + 1) += 8LL;
            }
          }
          catch ( SeException v23 )
          {
            v19 = v24;
            if ( v24 > 0 )
              v19 = (unsigned __int16)v24 | 0x80070000;
            v27 = v19;
            SeException::~SeException((SeException *)v23);
            v11 = v27;
          }
          catch ( std::bad_alloc v22 )
          {
            v28 = -2147024882;
            SeException::~SeException((SeException *)v22);
            v11 = v28;
          }
          catch ( ... )
          {
            v29 = -2147418113;
            v11 = v29;
          }
          _set_se_translator(v21);
          if ( v11 >= 0 )
          {
            if ( (unsigned __int8)FileLogAllowEntry(50) )
              FileLogAdd(L"AddNewPendingPeer: NtsNtp peer\n");
            v11 = 0;
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
        }
      }
    }
    else
    {
LABEL_29:
      v11 = -2147024882;
    }
    AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(&v20);
    return (unsigned int)v11;
  }
  else
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"Failing as we are attempting to call AddNewPendingNtsNtpPeer when nts feature is not enabled.\n");
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x180038424  mov     [rsp+arg_0], rbx
0x180038429  mov     [rsp+arg_8], rsi
0x18003842e  push    rdi
0x18003842f  push    r14
0x180038431  push    r15
0x180038433  sub     rsp, 70h
0x180038437  mov     rdi, r8
0x18003843a  mov     rbx, rdx
0x18003843d  mov     r15, rcx
0x180038440  xor     r14d, r14d
0x180038443  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18003844a  cmp     [rax+32h], r14b
0x18003844e  jnz     short loc_180038471
0x180038450  xor     ecx, ecx
0x180038452  call    FileLogAllowEntry
0x180038457  test    al, al
0x180038459  jz      short loc_180038467
0x18003845b  lea     rcx, aFailingAsWeAre_1; "Failing as we are attempting to call Ad"...
0x180038462  call    FileLogAdd
0x180038467  mov     eax, 80004001h
0x18003846c  jmp     loc_1800386B7
0x180038471  mov     ecx, 610h; Size
0x180038476  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003847b  mov     rsi, rax
0x18003847e  mov     [rsp+88h+arg_18], rax
0x180038486  xor     edx, edx; Val
0x180038488  mov     r8d, 610h; Size
0x18003848e  mov     rcx, rax; void *
0x180038491  call    memset_0
0x180038496  nop
0x180038497  mov     rdx, rsi
0x18003849a  lea     rcx, [rsp+88h+var_68]
0x18003849f  call    ??0?$AutoPtr@UNtpPeer@@@@QEAA@PEAUNtpPeer@@@Z; AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(NtpPeer *)
0x1800384a4  nop
0x1800384a5  mov     rax, [rsp+88h+var_68]
0x1800384aa  test    rax, rax
0x1800384ad  jz      loc_1800386A6
0x1800384b3  mov     rcx, [rax+8]
0x1800384b7  test    rcx, rcx
0x1800384ba  jz      loc_1800386A6
0x1800384c0  mov     dword ptr [rcx+30h], 4
0x1800384c7  mov     rax, [rsp+88h+var_68]
0x1800384cc  mov     rcx, [rax+8]
0x1800384d0  mov     dword ptr [rcx+38h], 3
0x1800384d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800384db  inc     rax
0x1800384de  cmp     [r15+rax*2], r14w
0x1800384e3  jnz     short loc_1800384DB
0x1800384e5  lea     rsi, [rax+1]
0x1800384e9  lea     rdx, [rsi+rsi]; uBytes
0x1800384ed  mov     ecx, 40h ; '@'; uFlags
0x1800384f2  call    cs:__imp_LocalAlloc
0x1800384f9  nop     dword ptr [rax+rax+00h]
0x1800384fe  mov     rcx, [rsp+88h+var_68]
0x180038503  mov     rdx, [rcx+8]
0x180038507  mov     [rdx+48h], rax
0x18003850b  mov     rax, [rsp+88h+var_68]
0x180038510  mov     rcx, [rax+8]
0x180038514  mov     rcx, [rcx+48h]; unsigned __int16 *
0x180038518  test    rcx, rcx
0x18003851b  jz      loc_1800386A6
0x180038521  mov     r8, r15; unsigned __int16 *
0x180038524  mov     rdx, rsi; unsigned __int64
0x180038527  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003852c  mov     esi, eax
0x18003852e  test    eax, eax
0x180038530  js      loc_1800386AB
0x180038536  mov     edx, 2Ch ; ','; Ch
0x18003853b  mov     rax, [rsp+88h+var_68]
0x180038540  mov     rcx, [rax+8]
0x180038544  mov     rcx, [rcx+48h]; Str
0x180038548  call    cs:__imp_wcschr
0x18003854f  nop     dword ptr [rax+rax+00h]
0x180038554  test    rax, rax
0x180038557  jz      short loc_18003857C
0x180038559  lea     rcx, [rax+2]; String
0x18003855d  xor     r8d, r8d; Radix
0x180038560  xor     edx, edx; EndPtr
0x180038562  call    cs:__imp_wcstoul
0x180038569  nop     dword ptr [rax+rax+00h]
0x18003856e  mov     rcx, [rsp+88h+var_68]
0x180038573  mov     rdx, [rcx+8]
0x180038577  mov     [rdx+50h], eax
0x18003857a  jmp     short loc_180038589
0x18003857c  mov     rax, [rsp+88h+var_68]
0x180038581  mov     rcx, [rax+8]
0x180038585  mov     [rcx+50h], r14d
0x180038589  mov     rax, [rsp+88h+var_68]
0x18003858e  mov     rdx, [rax+8]
0x180038592  mov     ecx, [rdx+50h]
0x180038595  test    cl, 1
0x180038598  jz      short loc_1800385A6
0x18003859a  mov     [rdx+118h], rbx
0x1800385a1  mov     rax, [rsp+88h+var_68]
0x1800385a6  mov     rcx, [rax+8]
0x1800385aa  mov     [rcx+340h], rdi
0x1800385b1  mov     rax, [rsp+88h+var_68]
0x1800385b6  mov     rcx, [rax+8]
0x1800385ba  add     rcx, 8; lpCriticalSection
0x1800385be  call    ?myInitializeCriticalSection@@YAJPEAU_RTL_CRITICAL_SECTION@@@Z; myInitializeCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800385c3  mov     esi, eax
0x1800385c5  test    eax, eax
0x1800385c7  js      loc_1800386AB
0x1800385cd  mov     rax, [rsp+88h+var_68]
0x1800385d2  mov     rcx, [rax+8]
0x1800385d6  mov     byte ptr [rcx], 1
0x1800385d9  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800385e0  add     rcx, 148h; lpCriticalSection
0x1800385e7  call    cs:__imp_EnterCriticalSection
0x1800385ee  nop     dword ptr [rax+rax+00h]
0x1800385f3  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x1800385fa  call    cs:__imp__set_se_translator
0x180038601  nop     dword ptr [rax+rax+00h]
0x180038606  mov     [rsp+88h+var_60], rax
0x18003860b  mov     esi, r14d
0x18003860e  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180038615  add     rcx, 1B0h
0x18003861c  mov     rdx, [rcx+8]
0x180038620  cmp     rdx, [rcx+10h]
0x180038624  jz      short loc_18003863D
0x180038626  mov     rax, [rsp+88h+var_68]
0x18003862b  mov     [rdx], rax
0x18003862e  test    rax, rax
0x180038631  jz      short loc_180038636
0x180038633  lock inc dword ptr [rax]
0x180038636  add     qword ptr [rcx+8], 8
0x18003863b  jmp     short loc_180038648
0x18003863d  lea     r8, [rsp+88h+var_68]
0x180038642  call    ??$_Emplace_reallocate@AEBV?$AutoPtr@UNtpPeer@@@@@?$vector@V?$AutoPtr@UNtpPeer@@@@V?$MyThrowingAllocator@V?$AutoPtr@UNtpPeer@@@@@@@std@@AEAAPEAV?$AutoPtr@UNtpPeer@@@@QEAV2@AEBV2@@Z; std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::_Emplace_reallocate<AutoPtr<NtpPeer> const &>(AutoPtr<NtpPeer> * const,AutoPtr<NtpPeer> const &)
0x180038647  nop
0x180038648  jmp     short loc_180038658
0x18003864a  jmp     short loc_18003864E
0x18003864c  jmp     short $+2
0x18003864e  xor     r14d, r14d
0x180038651  mov     esi, dword ptr [rsp+88h+arg_18]
0x180038658  mov     rcx, [rsp+88h+var_60]
0x18003865d  call    cs:__imp__set_se_translator
0x180038664  nop     dword ptr [rax+rax+00h]
0x180038669  test    esi, esi
0x18003866b  js      short loc_18003868A
0x18003866d  mov     ecx, 32h ; '2'
0x180038672  call    FileLogAllowEntry
0x180038677  test    al, al
0x180038679  jz      short loc_180038687
0x18003867b  lea     rcx, aAddnewpendingp_1; "AddNewPendingPeer: NtsNtp peer\n"
0x180038682  call    FileLogAdd
0x180038687  mov     esi, r14d
0x18003868a  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180038691  add     rcx, 148h; lpCriticalSection
0x180038698  call    cs:__imp_LeaveCriticalSection
0x18003869f  nop     dword ptr [rax+rax+00h]
0x1800386a4  jmp     short loc_1800386AB
0x1800386a6  mov     esi, 8007000Eh
0x1800386ab  lea     rcx, [rsp+88h+var_68]
0x1800386b0  call    ??1?$AutoPtr@UNtpPeer@@@@QEAA@XZ; AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(void)
0x1800386b5  mov     eax, esi
0x1800386b7  lea     r11, [rsp+88h+var_18]
0x1800386bc  mov     rbx, [r11+20h]
0x1800386c0  mov     rsi, [r11+28h]
0x1800386c4  mov     rsp, r11
0x1800386c7  pop     r15
0x1800386c9  pop     r14
0x1800386cb  pop     rdi
0x1800386cc  retn
```

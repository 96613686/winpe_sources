# CWinInetHelperClass::Initialize(ulong,tagHELPER_ATTRIBUTE * const)

- ea: `0x1800082f0`
- end: `0x1800086a2`
- name: `?Initialize@CWinInetHelperClass@@UEAAJKQEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `946`
- prototype: `__int64 __fastcall(CWinInetHelperClass *__hidden this, unsigned int, struct tagHELPER_ATTRIBUTE *const)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800048cc`
- `0x1800082f0`
- `0x18000e2a4`
- `0x180012d62`
- `0x180012d7a`
- `0x180014010`

## import_xrefs

- `msvcrt!wcsnlen` at `0x1800085a9`
- `msvcrt!wcsnlen` at `0x1800085a9`
- `msvcrt!wcsncpy_s` at `0x1800085cc`
- `msvcrt!wcsncpy_s` at `0x1800085cc`
- `ADVAPI32!IsValidSid` at `0x18000854c`
- `ADVAPI32!IsValidSid` at `0x18000854c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000850c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000850c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000856f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000856f`

## pseudocode

```c
__int64 __fastcall CWinInetHelperClass::Initialize(
        CWinInetHelperClass *this,
        unsigned int a2,
        struct tagHELPER_ATTRIBUTE *const a3)
{
  unsigned int v6; // ebp
  unsigned int i; // r12d
  __int64 v8; // rsi
  const wchar_t *pwszName; // r15
  ATTRIBUTE_TYPE *p_type; // rbx
  LPWSTR PWStr; // r8
  _WORD *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  _WORD *v15; // rcx
  int v16; // eax
  __int64 v17; // rbx
  unsigned int DWord; // eax
  void *v19; // rax
  void *v20; // rcx
  void *v21; // rcx
  size_t v22; // rbx
  __int64 v23; // rcx
  unsigned int v25; // [rsp+20h] [rbp-68h]
  __int64 v26; // [rsp+90h] [rbp+8h] BYREF

  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 1, 0) )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    v6 = 0;
    for ( i = 0; i < a2; ++i )
    {
      v8 = i;
      pwszName = a3[v8].pwszName;
      p_type = &a3[v8].type;
      if ( !wcscmp_0(pwszName, L"URL") && *p_type == AT_STRING )
      {
        PWStr = a3[v8].PWStr;
        v12 = (_WORD *)((char *)this + 1750);
        v13 = 2147483646;
        v14 = 299;
        do
        {
          if ( !v13 )
            break;
          if ( !*PWStr )
            break;
          *v12++ = *PWStr++;
          --v13;
          --v14;
        }
        while ( v14 );
        v15 = v12 - 1;
        if ( v14 )
          v15 = v12;
        *v15 = 0;
        v6 = v14 == 0 ? 0x8007007A : 0;
        if ( !v14 )
          return v6;
        v16 = CrackURL(
                a3[v8].PWStr,
                (unsigned __int16 *)this + 576,
                (unsigned int)PWStr,
                (unsigned __int16 *)this + 60,
                v25,
                (unsigned __int16 *)this + 572,
                (CWinInetHelperClass *)((char *)this + 1148),
                (int *)this + 755);
        v6 = v16;
        if ( v16 < 0 )
        {
          if ( v16 != -2147012891 )
            return (unsigned int)-2147024809;
          *((_DWORD *)this + 1274) = 0;
          v6 = 0;
        }
        if ( *((_QWORD *)this + 602) )
        {
          if ( *((_DWORD *)this + 755) )
          {
            v26 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
              &v26,
              L"No URL passed, using URL %s.",
              (char *)this + 1152);
            v17 = v26;
            v25 = v26;
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const wchar_t *))(**((_QWORD **)this + 602) + 24LL))(
              *((_QWORD *)this + 602),
              2,
              0,
              L"WinInetHelperClass");
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v17 - 24 + 16), 0xFFFFFFFF) <= 1 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v17 - 24) + 8LL))(*(_QWORD *)(v17 - 24));
          }
        }
      }
      else if ( !wcscmp_0(pwszName, L"UserID") && (p_type = &a3[v8].type, *p_type == AT_OCTET_STRING) )
      {
        if ( a3[v8].OctetString.lpValue )
        {
          DWord = a3[v8].DWord;
          if ( DWord )
          {
            v19 = CoTaskMemAlloc(DWord);
            *((_QWORD *)this + 360) = v19;
            if ( v19 )
            {
              memcpy_0(v19, a3[v8].OctetString.lpValue, a3[v8].DWord);
              v20 = (void *)*((_QWORD *)this + 360);
              *((_DWORD *)this + 718) = a3[v8].Boolean;
              if ( !IsValidSid(v20) )
              {
                v21 = (void *)*((_QWORD *)this + 360);
                *((_DWORD *)this + 718) = 0;
                CoTaskMemFree(v21);
                *((_QWORD *)this + 360) = 0;
              }
            }
          }
        }
      }
      else if ( !wcscmp_0(pwszName, L"AppID") && *p_type == AT_STRING )
      {
        v22 = wcsnlen(a3[v8].PWStr, 0x103u);
        wcsncpy_s((wchar_t *)this + 1174, 0x104u, a3[v8].PWStr, v22);
        *((_WORD *)this + v22 + 1174) = 0;
      }
      else if ( !wcscmp_0(pwszName, L"UseWinHTTP") && *p_type == AT_BOOLEAN )
      {
        *((_DWORD *)this + 1202) = a3[v8].Boolean;
      }
    }
    if ( !*((_WORD *)this + 576) && !*((_DWORD *)this + 755) )
      *((_DWORD *)this + 1274) = 0;
    if ( !*((_WORD *)this + 572) )
      *((_WORD *)this + 572) = 80;
    if ( *((_DWORD *)this + 287) == 2 && *((_DWORD *)this + 1202) )
    {
      v23 = *((_QWORD *)this + 602);
      if ( v23 )
        (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v23 + 24LL))(
          v23,
          2,
          0,
          L"WinInetHelperClass",
          L"WinHTTP doesn't support FTP. Using WinInet instead.");
      *((_DWORD *)this + 1202) = 0;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800082f0  push    rbx
0x1800082f2  push    rbp
0x1800082f3  push    rsi
0x1800082f4  push    rdi
0x1800082f5  push    r12
0x1800082f7  push    r13
0x1800082f9  push    r14
0x1800082fb  push    r15
0x1800082fd  sub     rsp, 48h
0x180008301  mov     rdi, rcx
0x180008304  mov     r14, r8
0x180008307  mov     ecx, 1
0x18000830c  mov     r13d, edx
0x18000830f  xor     eax, eax
0x180008311  lock cmpxchg [rdi+10h], ecx
0x180008316  jz      short loc_180008322
0x180008318  mov     ebp, 80004005h
0x18000831d  jmp     loc_180008687
0x180008322  xor     esi, esi
0x180008324  mov     ebp, esi
0x180008326  mov     r12d, esi
0x180008329  test    r13d, r13d
0x18000832c  jz      loc_180008615
0x180008332  mov     eax, r12d
0x180008335  lea     rdx, aUrl; "URL"
0x18000833c  lea     rsi, [rax+rax*8]
0x180008340  shl     rsi, 4
0x180008344  mov     r15, [rsi+r14]
0x180008348  mov     rcx, r15; String1
0x18000834b  call    wcscmp_0
0x180008350  lea     rbx, [r14+8]
0x180008354  xor     r10d, r10d
0x180008357  add     rbx, rsi
0x18000835a  test    eax, eax
0x18000835c  jnz     loc_1800084CA
0x180008362  cmp     dword ptr [rbx], 0Ah
0x180008365  jnz     loc_1800084CA
0x18000836b  mov     r8, [rsi+r14+10h]
0x180008370  lea     rax, [rdi+6D6h]
0x180008377  mov     ecx, 7FFFFFFEh
0x18000837c  mov     edx, 12Bh
0x180008381  test    rcx, rcx
0x180008384  jz      short loc_1800083A5
0x180008386  movzx   r9d, word ptr [r8]
0x18000838a  test    r9w, r9w
0x18000838e  jz      short loc_1800083A5
0x180008390  mov     [rax], r9w
0x180008394  add     r8, 2; unsigned int
0x180008398  add     rax, 2
0x18000839c  dec     rcx
0x18000839f  sub     rdx, 1
0x1800083a3  jnz     short loc_180008381
0x1800083a5  test    rdx, rdx
0x1800083a8  lea     rcx, [rax-2]
0x1800083ac  cmovnz  rcx, rax
0x1800083b0  mov     rax, rdx
0x1800083b3  neg     rax
0x1800083b6  sbb     ebp, ebp
0x1800083b8  not     ebp
0x1800083ba  mov     [rcx], r10w
0x1800083be  and     ebp, 8007007Ah
0x1800083c4  test    rdx, rdx
0x1800083c7  jz      loc_180008687
0x1800083cd  lea     rax, [rdi+47Ch]
0x1800083d4  lea     rcx, [rdi+478h]
0x1800083db  lea     rbx, [rdi+0BCCh]
0x1800083e2  mov     [rsp+88h+var_50], rbx; int *
0x1800083e7  lea     r15, [rdi+480h]
0x1800083ee  mov     [rsp+88h+var_58], rax; enum WHCInternetScheme *
0x1800083f3  lea     r9, [rdi+78h]; unsigned __int16 *
0x1800083f7  mov     [rsp+88h+var_60], rcx; unsigned __int16 *
0x1800083fc  mov     rdx, r15; unsigned __int16 *
0x1800083ff  mov     rcx, [rsi+r14+10h]; unsigned __int16 *
0x180008404  call    ?CrackURL@@YAJPEBGPEAGK1K1PEAW4WHCInternetScheme@@PEAH@Z; CrackURL(ushort const *,ushort *,ulong,ushort *,ulong,ushort *,WHCInternetScheme *,int *)
0x180008409  xor     esi, esi
0x18000840b  mov     ebp, eax
0x18000840d  test    eax, eax
0x18000840f  jns     short loc_180008424
0x180008411  cmp     eax, 80072EE5h
0x180008416  jnz     loc_18000869B
0x18000841c  mov     [rdi+13E8h], esi
0x180008422  mov     ebp, esi
0x180008424  cmp     [rdi+12D0h], rsi
0x18000842b  jz      loc_180008609
0x180008431  cmp     [rbx], esi
0x180008433  jz      loc_180008609
0x180008439  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180008440  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180008447  mov     rax, [rax+18h]
0x18000844b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008450  add     rax, 18h
0x180008454  lea     rdx, aNoUrlPassedUsi; "No URL passed, using URL %s."
0x18000845b  mov     r8, r15
0x18000845e  mov     [rsp+88h+arg_0], rax
0x180008466  lea     rcx, [rsp+88h+arg_0]
0x18000846e  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180008473  mov     rcx, [rdi+12D0h]
0x18000847a  lea     r9, aWininethelperc; "WinInetHelperClass"
0x180008481  mov     rbx, [rsp+88h+arg_0]
0x180008489  xor     r8d, r8d
0x18000848c  mov     [rsp+88h+var_68], rbx
0x180008491  mov     rax, [rcx]
0x180008494  lea     edx, [r8+2]
0x180008498  mov     rax, [rax+18h]
0x18000849c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084a1  lea     rdx, [rbx-18h]
0x1800084a5  or      eax, 0FFFFFFFFh
0x1800084a8  lock xadd [rdx+10h], eax
0x1800084ad  sub     eax, 1
0x1800084b0  jg      loc_180008609
0x1800084b6  mov     rcx, [rdx]
0x1800084b9  mov     rax, [rcx]
0x1800084bc  mov     rax, [rax+8]
0x1800084c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084c5  jmp     loc_180008609
0x1800084ca  lea     rdx, aUserid_0; "UserID"
0x1800084d1  mov     rcx, r15; String1
0x1800084d4  call    wcscmp_0
0x1800084d9  test    eax, eax
0x1800084db  jnz     loc_180008587
0x1800084e1  lea     rbx, [r14+8]
0x1800084e5  add     rbx, rsi
0x1800084e8  cmp     dword ptr [rbx], 0Eh
0x1800084eb  jnz     loc_180008587
0x1800084f1  cmp     qword ptr [rsi+r14+18h], 0
0x1800084f7  jz      loc_180008607
0x1800084fd  mov     eax, [rsi+r14+10h]
0x180008502  test    eax, eax
0x180008504  jz      loc_180008607
0x18000850a  mov     ecx, eax; cb
0x18000850c  call    cs:__imp_CoTaskMemAlloc
0x180008513  nop     dword ptr [rax+rax+00h]
0x180008518  mov     [rdi+0B40h], rax
0x18000851f  test    rax, rax
0x180008522  jz      loc_180008607
0x180008528  mov     r8d, [rsi+r14+10h]; Size
0x18000852d  mov     rcx, rax; void *
0x180008530  mov     rdx, [rsi+r14+18h]; Src
0x180008535  call    memcpy_0
0x18000853a  mov     eax, [rsi+r14+10h]
0x18000853f  mov     rcx, [rdi+0B40h]; pSid
0x180008546  mov     [rdi+0B38h], eax
0x18000854c  call    cs:__imp_IsValidSid
0x180008553  nop     dword ptr [rax+rax+00h]
0x180008558  xor     esi, esi
0x18000855a  test    eax, eax
0x18000855c  jnz     loc_180008609
0x180008562  mov     rcx, [rdi+0B40h]; pv
0x180008569  mov     [rdi+0B38h], esi
0x18000856f  call    cs:__imp_CoTaskMemFree
0x180008576  nop     dword ptr [rax+rax+00h]
0x18000857b  mov     [rdi+0B40h], rsi
0x180008582  jmp     loc_180008609
0x180008587  lea     rdx, aAppid_1; "AppID"
0x18000858e  mov     rcx, r15; String1
0x180008591  call    wcscmp_0
0x180008596  test    eax, eax
0x180008598  jnz     short loc_1800085E4
0x18000859a  cmp     dword ptr [rbx], 0Ah
0x18000859d  jnz     short loc_1800085E4
0x18000859f  mov     rcx, [rsi+r14+10h]; Source
0x1800085a4  mov     edx, 103h; MaxCount
0x1800085a9  call    cs:__imp_wcsnlen
0x1800085b0  nop     dword ptr [rax+rax+00h]
0x1800085b5  mov     r8, [rsi+r14+10h]; Source
0x1800085ba  lea     rcx, [rdi+92Ch]; Destination
0x1800085c1  mov     r9, rax; MaxCount
0x1800085c4  mov     edx, 104h; SizeInWords
0x1800085c9  mov     rbx, rax
0x1800085cc  call    cs:__imp_wcsncpy_s
0x1800085d3  nop     dword ptr [rax+rax+00h]
0x1800085d8  xor     esi, esi
0x1800085da  mov     [rdi+rbx*2+92Ch], si
0x1800085e2  jmp     short loc_180008609
0x1800085e4  lea     rdx, aUsewinhttp; "UseWinHTTP"
0x1800085eb  mov     rcx, r15; String1
0x1800085ee  call    wcscmp_0
0x1800085f3  test    eax, eax
0x1800085f5  jnz     short loc_180008607
0x1800085f7  cmp     dword ptr [rbx], 1
0x1800085fa  jnz     short loc_180008607
0x1800085fc  mov     eax, [rsi+r14+10h]
0x180008601  mov     [rdi+12C8h], eax
0x180008607  xor     esi, esi
0x180008609  inc     r12d
0x18000860c  cmp     r12d, r13d
0x18000860f  jb      loc_180008332
0x180008615  cmp     [rdi+480h], si
0x18000861c  jnz     short loc_18000862C
0x18000861e  cmp     [rdi+0BCCh], esi
0x180008624  jnz     short loc_18000862C
0x180008626  mov     [rdi+13E8h], esi
0x18000862c  cmp     [rdi+478h], si
0x180008633  jnz     short loc_18000863E
0x180008635  mov     word ptr [rdi+478h], 50h ; 'P'
0x18000863e  cmp     dword ptr [rdi+47Ch], 2
0x180008645  jnz     short loc_180008687
0x180008647  cmp     [rdi+12C8h], esi
0x18000864d  jz      short loc_180008687
0x18000864f  mov     rcx, [rdi+12D0h]
0x180008656  test    rcx, rcx
0x180008659  jz      short loc_180008681
0x18000865b  mov     rax, [rcx]
0x18000865e  lea     r10, aWinhttpDoesnTS; "WinHTTP doesn't support FTP. Using WinI"...
0x180008665  xor     r8d, r8d
0x180008668  mov     [rsp+88h+var_68], r10
0x18000866d  lea     r9, aWininethelperc; "WinInetHelperClass"
0x180008674  mov     rax, [rax+18h]
0x180008678  lea     edx, [r8+2]
0x18000867c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008681  mov     [rdi+12C8h], esi
0x180008687  mov     eax, ebp
0x180008689  add     rsp, 48h
0x18000868d  pop     r15
0x18000868f  pop     r14
0x180008691  pop     r13
0x180008693  pop     r12
0x180008695  pop     rdi
0x180008696  pop     rsi
0x180008697  pop     rbp
0x180008698  pop     rbx
0x180008699  retn
0x18000869b  mov     ebp, 80070057h
0x1800086a0  jmp     short loc_180008687
```

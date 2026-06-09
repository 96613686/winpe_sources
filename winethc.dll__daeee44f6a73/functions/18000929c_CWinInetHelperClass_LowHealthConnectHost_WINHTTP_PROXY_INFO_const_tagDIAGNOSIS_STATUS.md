# CWinInetHelperClass::LowHealthConnectHost(_WINHTTP_PROXY_INFO * const,tagDIAGNOSIS_STATUS *)

- ea: `0x18000929c`
- end: `0x180009520`
- name: `?LowHealthConnectHost@CWinInetHelperClass@@AEAAJQEAU_WINHTTP_PROXY_INFO@@PEAW4tagDIAGNOSIS_STATUS@@@Z`
- size: `644`
- prototype: `__int64 __fastcall(CWinInetHelperClass *__hidden this, struct _WINHTTP_PROXY_INFO *const, enum tagDIAGNOSIS_STATUS *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008ec0`

## callees

- `0x1800048cc`
- `0x18000929c`
- `0x18000f91c`
- `0x180014010`

## string_xrefs

- `0x180009373`: `Host connection thread using %s timed out.`
- `0x18000939b`: `Host connection thread using %s failed with error hr=0x%x [WHCError #%i].`

## pseudocode

```c
__int64 __fastcall CWinInetHelperClass::LowHealthConnectHost(
        CWinInetHelperClass *this,
        struct _WINHTTP_PROXY_INFO *const a2,
        enum tagDIAGNOSIS_STATUS *a3)
{
  int *v3; // rsi
  enum tagDIAGNOSIS_STATUS v5; // edi
  unsigned int v7; // r15d
  __int64 v8; // rax
  int v9; // edx
  const wchar_t *v10; // r8
  int v11; // ecx
  __int64 v12; // rcx
  __int64 v13; // rbx
  _QWORD *v14; // rdx
  bool v15; // cc
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 v22; // [rsp+20h] [rbp-20h]
  __int64 v23; // [rsp+70h] [rbp+30h] BYREF
  __int64 v24; // [rsp+88h] [rbp+48h] BYREF

  LODWORD(v24) = 0;
  v3 = (int *)((char *)this + 3016);
  v5 = DS_CONFIRMED;
  LODWORD(v23) = 0;
  v7 = CWinInetHelperClass::ExecuteConnectionThread(
         this,
         1,
         (CWinInetHelperClass *)((char *)this + 3016),
         (int *)&v24,
         (unsigned int *)&v23,
         a2,
         (struct sockaddr_storage *)((char *)this + 4968));
  if ( (v7 & 0x80000000) != 0 )
    return v7;
  if ( *v3 )
  {
    if ( *v3 == 2 && *((_DWORD *)this + 755) && !*((_DWORD *)this + 1239) )
      v5 = DS_INDETERMINATE;
    *a3 = v5;
    if ( *((_QWORD *)this + 602) )
    {
      v8 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
      v9 = *v3;
      v10 = L"WinHTTP";
      v11 = *((_DWORD *)this + 1202);
      v23 = v8 + 24;
      if ( v9 == 2 )
      {
        if ( !v11 )
          v10 = L"WinInet";
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v23,
          L"Host connection thread using %s timed out.",
          v10);
      }
      else
      {
        LODWORD(v22) = v9;
        if ( !v11 )
          v10 = L"WinInet";
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v23,
          L"Host connection thread using %s failed with error hr=0x%x [WHCError #%i].",
          v10,
          (unsigned int)v24,
          v22);
      }
      v12 = *((_QWORD *)this + 602);
      v13 = v23;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, __int64))(*(_QWORD *)v12 + 24LL))(
        v12,
        2,
        0,
        L"WinInetHelperClass",
        v23);
      v14 = (_QWORD *)(v13 - 24);
      v15 = _InterlockedExchangeAdd((volatile signed __int32 *)(v13 - 24 + 16), 0xFFFFFFFF) <= 1;
LABEL_16:
      if ( v15 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 8LL))(*v14);
    }
  }
  else
  {
    v16 = *((_QWORD *)this + 602);
    if ( (_DWORD)v23 != 200 )
    {
      if ( !v16 )
        return v7;
      v24 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v24,
        L"Unhandled HTTP status code: %i",
        (unsigned int)v23);
      v17 = *((_QWORD *)this + 602);
      v18 = v24;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, __int64))(*(_QWORD *)v17 + 24LL))(
        v17,
        2,
        0,
        L"WinInetHelperClass",
        v24);
      v14 = (_QWORD *)(v18 - 24);
      v15 = _InterlockedExchangeAdd((volatile signed __int32 *)(v18 - 24 + 16), 0xFFFFFFFF) <= 1;
      goto LABEL_16;
    }
    if ( v16 )
    {
      v23 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v23,
        L"Successfully received 200 from: %s",
        (char *)this + 120);
      v19 = *((_QWORD *)this + 602);
      v20 = v23;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, __int64))(*(_QWORD *)v19 + 24LL))(
        v19,
        2,
        0,
        L"WinInetHelperClass",
        v23);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v20 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v20 - 24) + 8LL))(*(_QWORD *)(v20 - 24));
    }
    *a3 = DS_REJECTED;
  }
  return v7;
}

```

## disassembly

```asm
0x18000929c  mov     r11, rsp
0x18000929f  mov     [r11+10h], rbx
0x1800092a3  push    rbp
0x1800092a4  push    rsi
0x1800092a5  push    rdi
0x1800092a6  push    r14
0x1800092a8  push    r15
0x1800092aa  mov     rbp, rsp
0x1800092ad  sub     rsp, 40h
0x1800092b1  lea     rax, [rcx+1368h]
0x1800092b8  mov     dword ptr [rbp+arg_18], 0
0x1800092bf  mov     [r11-38h], rax
0x1800092c3  lea     rsi, [rcx+0BC8h]
0x1800092ca  mov     [r11-40h], rdx
0x1800092ce  lea     rax, [rbp+arg_0]
0x1800092d2  mov     r14, r8
0x1800092d5  mov     [r11-48h], rax
0x1800092d9  mov     edi, 1
0x1800092de  mov     dword ptr [rbp+arg_0], 0
0x1800092e5  mov     edx, edi; int
0x1800092e7  lea     r9, [rbp+arg_18]; int *
0x1800092eb  mov     r8, rsi; enum WHCConnectionErrors *
0x1800092ee  mov     rbx, rcx
0x1800092f1  call    ?ExecuteConnectionThread@CWinInetHelperClass@@AEAAJHPEAW4WHCConnectionErrors@@PEAJPEAKQEAU_WINHTTP_PROXY_INFO@@PEAUsockaddr_storage@@@Z; CWinInetHelperClass::ExecuteConnectionThread(int,WHCConnectionErrors *,long *,ulong *,_WINHTTP_PROXY_INFO * const,sockaddr_storage *)
0x1800092f6  mov     r15d, eax
0x1800092f9  test    eax, eax
0x1800092fb  js      loc_18000950B
0x180009301  cmp     dword ptr [rsi], 0
0x180009304  jz      loc_1800093FA
0x18000930a  cmp     dword ptr [rsi], 2
0x18000930d  jnz     short loc_180009326
0x18000930f  cmp     dword ptr [rbx+0BCCh], 0
0x180009316  jz      short loc_180009326
0x180009318  cmp     dword ptr [rbx+135Ch], 0
0x18000931f  jnz     short loc_180009326
0x180009321  mov     edi, 3
0x180009326  mov     [r14], edi
0x180009329  cmp     qword ptr [rbx+12D0h], 0
0x180009331  jz      loc_18000950B
0x180009337  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000933e  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009345  mov     rax, [rax+18h]
0x180009349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000934e  mov     edx, [rsi]
0x180009350  lea     r8, aWinhttp; "WinHTTP"
0x180009357  mov     ecx, [rbx+12C8h]
0x18000935d  add     rax, 18h
0x180009361  mov     [rbp+arg_0], rax
0x180009365  lea     rax, aWininet; "WinInet"
0x18000936c  cmp     edx, 2
0x18000936f  jnz     short loc_180009389
0x180009371  test    ecx, ecx
0x180009373  lea     rdx, aHostConnection; "Host connection thread using %s timed o"...
0x18000937a  lea     rcx, [rbp+arg_0]
0x18000937e  cmovz   r8, rax
0x180009382  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180009387  jmp     short loc_1800093A7
0x180009389  mov     r9d, dword ptr [rbp+arg_18]
0x18000938d  test    ecx, ecx
0x18000938f  mov     dword ptr [rsp+40h+var_20], edx
0x180009393  lea     rcx, [rbp+arg_0]
0x180009397  cmovz   r8, rax
0x18000939b  lea     rdx, aHostConnection_0; "Host connection thread using %s failed "...
0x1800093a2  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800093a7  mov     rcx, [rbx+12D0h]
0x1800093ae  lea     r9, aWininethelperc; "WinInetHelperClass"
0x1800093b5  mov     rbx, [rbp+arg_0]
0x1800093b9  xor     r8d, r8d
0x1800093bc  mov     [rsp+40h+var_20], rbx
0x1800093c1  mov     rax, [rcx]
0x1800093c4  lea     edx, [r8+2]
0x1800093c8  mov     rax, [rax+18h]
0x1800093cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093d1  lea     rdx, [rbx-18h]
0x1800093d5  or      eax, 0FFFFFFFFh
0x1800093d8  lock xadd [rdx+10h], eax
0x1800093dd  sub     eax, 1
0x1800093e0  jg      loc_18000950B
0x1800093e6  mov     rcx, [rdx]
0x1800093e9  mov     rax, [rcx]
0x1800093ec  mov     rax, [rax+8]
0x1800093f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093f5  jmp     loc_18000950B
0x1800093fa  cmp     dword ptr [rbp+arg_0], 0C8h
0x180009401  mov     rax, [rbx+12D0h]
0x180009408  jz      short loc_180009483
0x18000940a  test    rax, rax
0x18000940d  jz      loc_18000950B
0x180009413  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000941a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009421  mov     rax, [rax+18h]
0x180009425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000942a  mov     r8d, dword ptr [rbp+arg_0]
0x18000942e  lea     rdx, aUnhandledHttpS; "Unhandled HTTP status code: %i"
0x180009435  add     rax, 18h
0x180009439  lea     rcx, [rbp+arg_18]
0x18000943d  mov     [rbp+arg_18], rax
0x180009441  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180009446  mov     rcx, [rbx+12D0h]
0x18000944d  lea     r9, aWininethelperc; "WinInetHelperClass"
0x180009454  mov     rbx, [rbp+arg_18]
0x180009458  xor     r8d, r8d
0x18000945b  mov     [rsp+40h+var_20], rbx
0x180009460  mov     rax, [rcx]
0x180009463  lea     edx, [r8+2]
0x180009467  mov     rax, [rax+18h]
0x18000946b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009470  lea     rdx, [rbx-18h]
0x180009474  or      eax, 0FFFFFFFFh
0x180009477  lock xadd [rdx+10h], eax
0x18000947c  sub     eax, edi
0x18000947e  jmp     loc_1800093E0
0x180009483  test    rax, rax
0x180009486  jz      short loc_180009504
0x180009488  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000948f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009496  mov     rax, [rax+18h]
0x18000949a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000949f  add     rax, 18h
0x1800094a3  lea     r8, [rbx+78h]
0x1800094a7  lea     rdx, aSuccessfullyRe; "Successfully received 200 from: %s"
0x1800094ae  mov     [rbp+arg_0], rax
0x1800094b2  lea     rcx, [rbp+arg_0]
0x1800094b6  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800094bb  mov     rcx, [rbx+12D0h]
0x1800094c2  lea     r9, aWininethelperc; "WinInetHelperClass"
0x1800094c9  mov     rbx, [rbp+arg_0]
0x1800094cd  xor     r8d, r8d
0x1800094d0  mov     [rsp+40h+var_20], rbx
0x1800094d5  mov     rax, [rcx]
0x1800094d8  lea     edx, [r8+2]
0x1800094dc  mov     rax, [rax+18h]
0x1800094e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094e5  lea     rdx, [rbx-18h]
0x1800094e9  or      eax, 0FFFFFFFFh
0x1800094ec  lock xadd [rdx+10h], eax
0x1800094f1  sub     eax, edi
0x1800094f3  jg      short loc_180009504
0x1800094f5  mov     rcx, [rdx]
0x1800094f8  mov     rax, [rcx]
0x1800094fb  mov     rax, [rax+8]
0x1800094ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009504  mov     dword ptr [r14], 2
0x18000950b  mov     rbx, [rsp+40h+arg_8]
0x180009510  mov     eax, r15d
0x180009513  add     rsp, 40h
0x180009517  pop     r15
0x180009519  pop     r14
0x18000951b  pop     rdi
0x18000951c  pop     rsi
0x18000951d  pop     rbp
0x18000951e  retn
```

# CDlpManager::SetStringProperty(ushort const *,ushort const *)

- ea: `0x180075850`
- end: `0x180075bfd`
- name: `?SetStringProperty@CDlpManager@@UEAAJPEBG0@Z`
- size: `941`
- prototype: `int(CDlpManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x180047c30`
- `0x180075850`
- `0x180081010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18007598c`
- `OLEAUT32!__imp_SysAllocString` at `0x180075a41`
- `OLEAUT32!__imp_SysAllocString` at `0x18007598c`
- `OLEAUT32!__imp_SysAllocString` at `0x180075a41`
- `OLEAUT32!__imp_SysFreeString` at `0x180075ab8`
- `OLEAUT32!__imp_SysFreeString` at `0x180075bb5`
- `OLEAUT32!__imp_SysFreeString` at `0x180075bc5`
- `OLEAUT32!__imp_SysFreeString` at `0x180075ab8`
- `OLEAUT32!__imp_SysFreeString` at `0x180075bb5`
- `OLEAUT32!__imp_SysFreeString` at `0x180075bc5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180075a2c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180075a2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800758a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800758a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075bd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075bd6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDlpManager::SetStringProperty(
        CDlpManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r13
  OLECHAR *v7; // rbx
  int v8; // edi
  __int64 v9; // rax
  __int64 v10; // rcx
  int v11; // eax
  BSTR v12; // rax
  unsigned int v13; // r14d
  int v14; // edi
  __int64 v15; // r15
  OLECHAR *v16; // rax
  __int64 v17; // rsi
  OLECHAR *v18; // r14
  OLECHAR *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  int v22; // eax
  PCNZWCH lpString2; // [rsp+20h] [rbp-30h]
  __int64 cchCount2; // [rsp+28h] [rbp-28h]
  char *v26; // [rsp+38h] [rbp-18h]
  OLECHAR *v27; // [rsp+90h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp+48h] BYREF

  v26 = (char *)this + 464;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 472);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 472));
  bstrString = 0;
  v7 = 0;
  v27 = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
      goto LABEL_37;
    v9 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
    v10 = 0;
    if ( !v9 )
      goto LABEL_7;
    LODWORD(cchCount2) = -2147024809;
    LODWORD(lpString2) = 2114;
    goto LABEL_5;
  }
  if ( a3 )
  {
    v12 = SysAllocString(a3);
    v7 = v12;
    if ( v12 )
    {
      v27 = v12;
      v13 = *((_DWORD *)this + 135);
      v14 = 0;
      if ( v13 )
      {
        while ( 1 )
        {
          v15 = v14;
          if ( CompareStringW(0x409u, 1u, a2, -1, *(PCNZWCH *)(*((_QWORD *)this + 68) + 8LL * v14), -1) == 2 )
            break;
          if ( ++v14 >= v13 )
            goto LABEL_19;
        }
        v8 = 0;
        v17 = *((_QWORD *)this + 70);
        v18 = v7;
        v7 = 0;
        v19 = *(OLECHAR **)(v17 + 8 * v15);
        if ( v19 )
          SysFreeString(v19);
        *(_QWORD *)(v17 + 8 * v15) = v18;
        goto LABEL_37;
      }
LABEL_19:
      v16 = SysAllocString(a2);
      if ( v16 )
      {
        bstrString = v16;
        v8 = CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 536, &bstrString);
        if ( v8 >= 0 )
        {
          v8 = CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 552, &v27);
          if ( v8 < 0 && (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
          {
            v20 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
            v21 = 0;
            if ( v20 )
            {
              LODWORD(cchCount2) = v8;
              LODWORD(lpString2) = 2146;
              v22 = CDlpLogT<CEmptyType>::DlpLogFormat(
                      v20,
                      4,
                      L"%s(%d): Result = 0x%X",
                      L"CDlpManager::SetStringProperty",
                      lpString2,
                      cchCount2,
                      &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable',
                      v26);
              v21 = (unsigned int)v22;
              if ( v22 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v22);
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v21);
          }
          v7 = v27;
          goto LABEL_37;
        }
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
          goto LABEL_37;
        v9 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
        v10 = 0;
        if ( !v9 )
          goto LABEL_7;
        LODWORD(cchCount2) = v8;
        LODWORD(lpString2) = 2145;
      }
      else
      {
        bstrString = 0;
        v8 = -2147024882;
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
          goto LABEL_37;
        v9 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
        v10 = 0;
        if ( !v9 )
          goto LABEL_7;
        LODWORD(cchCount2) = -2147024882;
        LODWORD(lpString2) = 2141;
      }
    }
    else
    {
      v27 = 0;
      v8 = -2147024882;
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
        goto LABEL_37;
      v9 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
      v10 = 0;
      if ( !v9 )
        goto LABEL_7;
      LODWORD(cchCount2) = -2147024882;
      LODWORD(lpString2) = 2120;
    }
LABEL_5:
    v11 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v9,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpManager::SetStringProperty",
            lpString2,
            cchCount2,
            &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable',
            v26);
    v10 = (unsigned int)v11;
    if ( v11 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v11);
    goto LABEL_7;
  }
  v8 = -2147024809;
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
  {
    v9 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
    v10 = 0;
    if ( v9 )
    {
      LODWORD(cchCount2) = -2147024809;
      LODWORD(lpString2) = 2115;
      goto LABEL_5;
    }
LABEL_7:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
  }
LABEL_37:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  if ( v7 )
    SysFreeString(v7);
  if ( bstrString )
    SysFreeString(bstrString);
  LeaveCriticalSection(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180075850  mov     [rsp-38h+arg_10], rbx
0x180075855  push    rbp
0x180075856  push    rsi
0x180075857  push    rdi
0x180075858  push    r12
0x18007585a  push    r13
0x18007585c  push    r14
0x18007585e  push    r15
0x180075860  mov     rbp, rsp
0x180075863  sub     rsp, 50h
0x180075867  mov     rdi, r8
0x18007586a  mov     r12, rdx
0x18007586d  mov     rsi, rcx
0x180075870  mov     [rbp+var_8], 0
0x180075878  xorps   xmm0, xmm0
0x18007587b  xor     eax, eax
0x18007587d  movups  [rbp+var_20], xmm0
0x180075881  mov     [rbp+var_10], rax
0x180075885  lea     rax, [rcx+1D0h]
0x18007588c  mov     qword ptr [rbp+var_20+8], rax
0x180075890  lea     rcx, ??_7?$CDlpAutoDelayLockT@V?$CDlpAutoExclusiveAcquireLockT@VCEmptyType@@@@@@6B@; const CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable'
0x180075897  mov     qword ptr [rbp+var_20], rcx
0x18007589b  lea     r13, [rax+8]
0x18007589f  mov     rcx, r13; lpCriticalSection
0x1800758a2  call    cs:__imp_EnterCriticalSection
0x1800758a8  mov     dword ptr [rbp+var_10], 1
0x1800758af  mov     [rbp+bstrString], 0
0x1800758b7  xor     ebx, ebx
0x1800758b9  mov     [rbp+arg_0], rbx
0x1800758bd  test    r12, r12
0x1800758c0  jnz     short loc_18007593A
0x1800758c2  mov     r14d, 80070057h
0x1800758c8  mov     edi, r14d
0x1800758cb  mov     rax, [rsi+48h]
0x1800758cf  lea     rcx, [rsi+48h]
0x1800758d3  mov     rax, [rax+10h]
0x1800758d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800758dc  test    rax, rax
0x1800758df  jz      loc_180075BA5
0x1800758e5  mov     rax, [rsi+48h]
0x1800758e9  lea     rcx, [rsi+48h]
0x1800758ed  mov     rax, [rax+10h]
0x1800758f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800758f6  xor     ecx, ecx
0x1800758f8  test    rax, rax
0x1800758fb  jz      short loc_180075930
0x1800758fd  mov     dword ptr [rsp+50h+cchCount2], r14d
0x180075902  mov     dword ptr [rsp+50h+lpString2], 842h
0x18007590a  lea     r9, aCdlpmanagerSet_1; "CDlpManager::SetStringProperty"
0x180075911  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180075918  mov     edx, 4
0x18007591d  mov     rcx, rax
0x180075920  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180075925  test    eax, eax
0x180075927  mov     ecx, eax
0x180075929  jns     short loc_180075930
0x18007592b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180075930  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180075935  jmp     loc_180075BA5
0x18007593a  test    rdi, rdi
0x18007593d  jnz     short loc_180075989
0x18007593f  mov     r14d, 80070057h
0x180075945  mov     edi, r14d
0x180075948  mov     rax, [rsi+48h]
0x18007594c  lea     rcx, [rsi+48h]
0x180075950  mov     rax, [rax+10h]
0x180075954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075959  test    rax, rax
0x18007595c  jz      loc_180075BA5
0x180075962  mov     rax, [rsi+48h]
0x180075966  lea     rcx, [rsi+48h]
0x18007596a  mov     rax, [rax+10h]
0x18007596e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075973  xor     ecx, ecx
0x180075975  test    rax, rax
0x180075978  jz      short loc_180075930
0x18007597a  mov     dword ptr [rsp+50h+cchCount2], r14d
0x18007597f  mov     dword ptr [rsp+50h+lpString2], 843h
0x180075987  jmp     short loc_18007590A
0x180075989  mov     rcx, rdi; psz
0x18007598c  call    cs:__imp_SysAllocString
0x180075992  mov     rbx, rax
0x180075995  test    rax, rax
0x180075998  jnz     short loc_1800759EF
0x18007599a  mov     [rbp+arg_0], rax
0x18007599e  mov     r14d, 8007000Eh
0x1800759a4  mov     edi, r14d
0x1800759a7  mov     rax, [rsi+48h]
0x1800759ab  lea     rcx, [rsi+48h]
0x1800759af  mov     rax, [rax+10h]
0x1800759b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800759b8  test    rax, rax
0x1800759bb  jz      loc_180075BA5
0x1800759c1  mov     rax, [rsi+48h]
0x1800759c5  lea     rcx, [rsi+48h]
0x1800759c9  mov     rax, [rax+10h]
0x1800759cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800759d2  xor     ecx, ecx
0x1800759d4  test    rax, rax
0x1800759d7  jz      loc_180075930
0x1800759dd  mov     dword ptr [rsp+50h+cchCount2], r14d
0x1800759e2  mov     dword ptr [rsp+50h+lpString2], 848h
0x1800759ea  jmp     loc_18007590A
0x1800759ef  mov     [rbp+arg_0], rbx
0x1800759f3  mov     r14d, [rsi+21Ch]
0x1800759fa  xor     edi, edi
0x1800759fc  test    r14d, r14d
0x1800759ff  jz      short loc_180075A3E
0x180075a01  mov     rax, [rsi+220h]
0x180075a08  movsxd  r15, edi
0x180075a0b  mov     rax, [rax+r15*8]
0x180075a0f  mov     dword ptr [rsp+50h+cchCount2], 0FFFFFFFFh; cchCount2
0x180075a17  mov     [rsp+50h+lpString2], rax; lpString2
0x180075a1c  or      r9d, 0FFFFFFFFh; cchCount1
0x180075a20  mov     r8, r12; lpString1
0x180075a23  lea     edx, [r9+2]; dwCmpFlags
0x180075a27  mov     ecx, 409h; Locale
0x180075a2c  call    cs:__imp_CompareStringW
0x180075a32  cmp     eax, 2
0x180075a35  jz      short loc_180075AA1
0x180075a37  inc     edi
0x180075a39  cmp     edi, r14d
0x180075a3c  jb      short loc_180075A01
0x180075a3e  mov     rcx, r12; psz
0x180075a41  call    cs:__imp_SysAllocString
0x180075a47  test    rax, rax
0x180075a4a  jnz     short loc_180075AC7
0x180075a4c  mov     [rbp+bstrString], rax
0x180075a50  mov     r14d, 8007000Eh
0x180075a56  mov     edi, r14d
0x180075a59  mov     rax, [rsi+48h]
0x180075a5d  lea     rcx, [rsi+48h]
0x180075a61  mov     rax, [rax+10h]
0x180075a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075a6a  test    rax, rax
0x180075a6d  jz      loc_180075BA5
0x180075a73  mov     rax, [rsi+48h]
0x180075a77  lea     rcx, [rsi+48h]
0x180075a7b  mov     rax, [rax+10h]
0x180075a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075a84  xor     ecx, ecx
0x180075a86  test    rax, rax
0x180075a89  jz      loc_180075930
0x180075a8f  mov     dword ptr [rsp+50h+cchCount2], r14d
0x180075a94  mov     dword ptr [rsp+50h+lpString2], 85Dh
0x180075a9c  jmp     loc_18007590A
0x180075aa1  xor     edi, edi
0x180075aa3  mov     rsi, [rsi+230h]
0x180075aaa  mov     r14, rbx
0x180075aad  xor     ebx, ebx
0x180075aaf  mov     rcx, [rsi+r15*8]; bstrString
0x180075ab3  test    rcx, rcx
0x180075ab6  jz      short loc_180075ABE
0x180075ab8  call    cs:__imp_SysFreeString
0x180075abe  mov     [rsi+r15*8], r14
0x180075ac2  jmp     loc_180075BA5
0x180075ac7  mov     [rbp+bstrString], rax
0x180075acb  lea     rcx, [rsi+218h]
0x180075ad2  lea     rdx, [rbp+bstrString]
0x180075ad6  call    ?Append@?$CArray@VDH_BSTR@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_BSTR@@@Z; CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append(DH_BSTR const &)
0x180075adb  mov     edi, eax
0x180075add  test    eax, eax
0x180075adf  jns     short loc_180075B28
0x180075ae1  mov     rdx, [rsi+48h]
0x180075ae5  lea     rcx, [rsi+48h]
0x180075ae9  mov     rax, [rdx+10h]
0x180075aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075af2  test    rax, rax
0x180075af5  jz      loc_180075BA5
0x180075afb  mov     rax, [rsi+48h]
0x180075aff  lea     rcx, [rsi+48h]
0x180075b03  mov     rax, [rax+10h]
0x180075b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075b0c  xor     ecx, ecx
0x180075b0e  test    rax, rax
0x180075b11  jz      loc_180075930
0x180075b17  mov     dword ptr [rsp+50h+cchCount2], edi
0x180075b1b  mov     dword ptr [rsp+50h+lpString2], 861h
0x180075b23  jmp     loc_18007590A
0x180075b28  lea     rcx, [rsi+228h]
0x180075b2f  lea     rdx, [rbp+arg_0]
0x180075b33  call    ?Append@?$CArray@VDH_BSTR@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_BSTR@@@Z; CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append(DH_BSTR const &)
0x180075b38  mov     edi, eax
0x180075b3a  test    eax, eax
0x180075b3c  jns     short loc_180075BA1
0x180075b3e  mov     rax, [rsi+48h]
0x180075b42  lea     rcx, [rsi+48h]
0x180075b46  mov     rax, [rax+10h]
0x180075b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075b4f  test    rax, rax
0x180075b52  jz      short loc_180075BA1
0x180075b54  mov     rax, [rsi+48h]
0x180075b58  lea     rcx, [rsi+48h]
0x180075b5c  mov     rax, [rax+10h]
0x180075b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075b65  xor     ecx, ecx
0x180075b67  test    rax, rax
0x180075b6a  jz      short loc_180075B9C
0x180075b6c  mov     dword ptr [rsp+50h+cchCount2], edi
0x180075b70  mov     dword ptr [rsp+50h+lpString2], 862h
0x180075b78  lea     r9, aCdlpmanagerSet_1; "CDlpManager::SetStringProperty"
0x180075b7f  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180075b86  lea     edx, [rcx+4]
0x180075b89  mov     rcx, rax
0x180075b8c  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180075b91  mov     ecx, eax
0x180075b93  test    eax, eax
0x180075b95  jns     short loc_180075B9C
0x180075b97  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180075b9c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180075ba1  mov     rbx, [rbp+arg_0]
0x180075ba5  mov     ecx, edi
0x180075ba7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180075bac  nop
0x180075bad  test    rbx, rbx
0x180075bb0  jz      short loc_180075BBC
0x180075bb2  mov     rcx, rbx; bstrString
0x180075bb5  call    cs:__imp_SysFreeString
0x180075bbb  nop
0x180075bbc  mov     rcx, [rbp+bstrString]; bstrString
0x180075bc0  test    rcx, rcx
0x180075bc3  jz      short loc_180075BCC
0x180075bc5  call    cs:__imp_SysFreeString
0x180075bcb  nop
0x180075bcc  mov     eax, dword ptr [rbp+var_10]
0x180075bcf  test    eax, eax
0x180075bd1  jz      short loc_180075BE3
0x180075bd3  mov     rcx, r13; lpCriticalSection
0x180075bd6  call    cs:__imp_LeaveCriticalSection
0x180075bdc  mov     dword ptr [rbp+var_10], 0
0x180075be3  mov     eax, edi
0x180075be5  mov     rbx, [rsp+50h+arg_10]
0x180075bed  add     rsp, 50h
0x180075bf1  pop     r15
0x180075bf3  pop     r14
0x180075bf5  pop     r13
0x180075bf7  pop     r12
0x180075bf9  pop     rdi
0x180075bfa  pop     rsi
0x180075bfb  pop     rbp
0x180075bfc  retn
```

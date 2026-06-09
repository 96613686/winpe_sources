# CAuthContext::UpdateSvcHandle(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x18000bf58`
- end: `0x18000c18e`
- name: `?UpdateSvcHandle@CAuthContext@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `566`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x18003c770`

## callees

- `0x180003298`
- `0x18000ae00`
- `0x18000af14`
- `0x18000b0bc`
- `0x18000ba8c`
- `0x18000bf58`
- `0x180047a84`
- `0x18004b8cc`
- `0x180052ba0`
- `0x180052cf4`
- `0x180052d2c`
- `0x180052e48`
- `0x1800530e4`
- `0x180053890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c069`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c069`

## string_xrefs

- `0x18000c040`: `CAuthContext::UpdateSvcHandle`
- `0x18000c13b`: `Failed CreateContext for %ls. (0x%x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAuthContext::UpdateSvcHandle(__int64 a1, const unsigned __int16 **a2, __int64 a3)
{
  int v4; // edi
  RefWLIDHandle *v5; // rsi
  void *v6; // rbx
  char v7; // r14
  unsigned __int16 *v8; // rbx
  unsigned __int8 v9; // dl
  PPTraceStatus *v10; // rcx
  const unsigned __int16 *String; // rax
  int v13; // [rsp+28h] [rbp-28h]
  _QWORD v14[3]; // [rsp+30h] [rbp-20h] BYREF
  char v15; // [rsp+48h] [rbp-8h]
  unsigned __int16 *v16; // [rsp+90h] [rbp+40h] BYREF
  const unsigned __int16 **v17; // [rsp+98h] [rbp+48h]
  void *v18; // [rsp+A0h] [rbp+50h]

  v17 = a2;
  v4 = 0;
  v5 = (RefWLIDHandle *)(a1 + 16);
  v6 = *(void **)(a1 + 16);
  v7 = 1;
  if ( !v6 )
  {
    v6 = operator new(0x28u);
    v16 = (unsigned __int16 *)v6;
    *((_QWORD *)v6 + 1) = 0;
    *((_DWORD *)v6 + 6) = 1;
    *(_QWORD *)v6 = &SmartWLIDHandle::`vftable'{for `SmartObj<void *>'};
    *((_QWORD *)v6 + 2) = &SmartWLIDHandle::`vftable'{for `CRefCounted'};
    *((_QWORD *)v6 + 4) = 0;
    CAutoRefPtr<SmartWLIDHandle>::Deinit(v5);
    *(_QWORD *)v5 = v6;
  }
  if ( *((_QWORD *)v6 + 1) )
  {
    v16 = 0;
    if ( !v6 )
    {
      v6 = operator new(0x28u);
      v18 = v6;
      *((_QWORD *)v6 + 1) = 0;
      *((_DWORD *)v6 + 6) = 1;
      *(_QWORD *)v6 = &SmartWLIDHandle::`vftable'{for `SmartObj<void *>'};
      *((_QWORD *)v6 + 2) = &SmartWLIDHandle::`vftable'{for `CRefCounted'};
      *((_QWORD *)v6 + 4) = 0;
      CAutoRefPtr<SmartWLIDHandle>::Deinit(v5);
      *(_QWORD *)v5 = v6;
    }
    v4 = WLIDCGetIdName(*((void *const *)v6 + 1), &v16);
    if ( v4 < 0 )
    {
      Telemetry::IfFailExit(
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\authenticationcontext.cpp",
        "CAuthContext::UpdateSvcHandle",
        0x2Fu,
        v4,
        "hr = ::WLIDCGetIdName(m_hSvcHandle, &wstrCurrentUser)");
      CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>((void **)&v16);
      goto LABEL_20;
    }
    if ( (unsigned int)_o__wcsicmp(*a2, v16) )
      CAutoRefPtr<SmartWLIDHandle>::Deinit(v5);
    CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>((void **)&v16);
  }
  v8 = *(unsigned __int16 **)v5;
  if ( !*(_QWORD *)v5 )
  {
    v8 = (unsigned __int16 *)operator new(0x28u);
    v16 = v8;
    *((_QWORD *)v8 + 1) = 0;
    *((_DWORD *)v8 + 6) = 1;
    *(_QWORD *)v8 = &SmartWLIDHandle::`vftable'{for `SmartObj<void *>'};
    *((_QWORD *)v8 + 2) = &SmartWLIDHandle::`vftable'{for `CRefCounted'};
    *((_QWORD *)v8 + 4) = 0;
    CAutoRefPtr<SmartWLIDHandle>::Deinit(v5);
    *(_QWORD *)v5 = v8;
  }
  if ( !*((_QWORD *)v8 + 1) )
  {
    v16 = 0;
    v4 = WLIDCCreateContextEx(*a2, (const unsigned __int16 *)a2, a3, (void **)&v16);
    if ( v4 >= 0 )
    {
      RefWLIDHandle::Attach(v5, v16);
    }
    else
    {
      if ( !PPTraceShouldRedact() || (LOBYTE(v10) = 1, !PPTraceStatus::TraceOnFlag(v10, v9)) )
        v7 = 0;
      v14[1] = *a2;
      v14[2] = 0;
      v15 = v7;
      v14[0] = &PPRedactedStringW::`vftable';
      String = PPRedactedStringW::GetString((PPRedactedStringW *)v14);
      v13 = v4;
      TracePrintW(
        2u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\authenticationcontext.cpp",
        0x41u,
        L"Failed CreateContext for %ls. (0x%x)",
        String,
        v13);
      PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)v14);
    }
  }
LABEL_20:
  ATL::CStringData::Release((ATL::CStringData *)(*a2 - 12));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000bf58  mov     [rsp-38h+arg_8], rdx
0x18000bf5d  push    rbp
0x18000bf5e  push    rbx
0x18000bf5f  push    rsi
0x18000bf60  push    rdi
0x18000bf61  push    r13
0x18000bf63  push    r14
0x18000bf65  push    r15
0x18000bf67  mov     rbp, rsp
0x18000bf6a  sub     rsp, 50h
0x18000bf6e  mov     r15, rdx
0x18000bf71  xor     edi, edi
0x18000bf73  lea     rsi, [rcx+10h]
0x18000bf77  mov     rbx, [rsi]
0x18000bf7a  lea     r13d, [rdi+28h]
0x18000bf7e  lea     r14d, [rdi+1]
0x18000bf82  test    rbx, rbx
0x18000bf85  jnz     short loc_18000BFC4
0x18000bf87  mov     ecx, r13d; Size
0x18000bf8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bf8f  mov     rbx, rax
0x18000bf92  mov     [rbp+arg_0], rax
0x18000bf96  xor     eax, eax
0x18000bf98  mov     [rbx+8], rax
0x18000bf9c  mov     [rbx+18h], r14d
0x18000bfa0  lea     rax, ??_7SmartWLIDHandle@@6B?$SmartObj@PEAX@@@; const SmartWLIDHandle::`vftable'{for `SmartObj<void *>'}
0x18000bfa7  mov     [rbx], rax
0x18000bfaa  lea     rax, ??_7SmartWLIDHandle@@6BCRefCounted@@@; const SmartWLIDHandle::`vftable'{for `CRefCounted'}
0x18000bfb1  mov     [rbx+10h], rax
0x18000bfb5  mov     [rbx+20h], rdi
0x18000bfb9  mov     rcx, rsi
0x18000bfbc  call    ?Deinit@?$CAutoRefPtr@VSmartWLIDHandle@@@@IEAAXXZ; CAutoRefPtr<SmartWLIDHandle>::Deinit(void)
0x18000bfc1  mov     [rsi], rbx
0x18000bfc4  cmp     [rbx+8], rdi
0x18000bfc8  jz      loc_18000C085
0x18000bfce  mov     [rbp+arg_0], rdi
0x18000bfd2  test    rbx, rbx
0x18000bfd5  jnz     short loc_18000C018
0x18000bfd7  mov     rcx, r13; Size
0x18000bfda  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bfdf  mov     rbx, rax
0x18000bfe2  mov     [rbp+arg_10], rax
0x18000bfe6  xor     eax, eax
0x18000bfe8  mov     [rbx+8], rax
0x18000bfec  mov     [rbx+18h], r14d
0x18000bff0  lea     rax, ??_7SmartWLIDHandle@@6B?$SmartObj@PEAX@@@; const SmartWLIDHandle::`vftable'{for `SmartObj<void *>'}
0x18000bff7  mov     [rbx], rax
0x18000bffa  lea     rax, ??_7SmartWLIDHandle@@6BCRefCounted@@@; const SmartWLIDHandle::`vftable'{for `CRefCounted'}
0x18000c001  mov     [rbx+10h], rax
0x18000c005  mov     qword ptr [rbx+20h], 0
0x18000c00d  mov     rcx, rsi
0x18000c010  call    ?Deinit@?$CAutoRefPtr@VSmartWLIDHandle@@@@IEAAXXZ; CAutoRefPtr<SmartWLIDHandle>::Deinit(void)
0x18000c015  mov     [rsi], rbx
0x18000c018  lea     rdx, [rbp+arg_0]; unsigned __int16 **
0x18000c01c  mov     rcx, [rbx+8]; void *
0x18000c020  call    ?WLIDCGetIdName@@YAJQEAXPEAPEAG@Z; WLIDCGetIdName(void * const,ushort * *)
0x18000c025  mov     edi, eax
0x18000c027  test    eax, eax
0x18000c029  jns     short loc_18000C062
0x18000c02b  lea     rax, aHrWlidcgetidna; "hr = ::WLIDCGetIdName(m_hSvcHandle, &ws"...
0x18000c032  mov     [rsp+50h+var_30], rax; char *
0x18000c037  mov     r9d, edi; int
0x18000c03a  mov     r8d, 2Fh ; '/'; unsigned int
0x18000c040  lea     rdx, aCauthcontextUp; "CAuthContext::UpdateSvcHandle"
0x18000c047  lea     rcx, aClientcoreDsEx_10; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18000c04e  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18000c053  nop
0x18000c054  lea     rcx, [rbp+arg_0]
0x18000c058  call    ??1?$CMIDLStringT@PEADPEBD@@QEAA@XZ; CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(void)
0x18000c05d  jmp     loc_18000C171
0x18000c062  mov     rdx, [rbp+arg_0]
0x18000c066  mov     rcx, [r15]
0x18000c069  call    cs:__imp__o__wcsicmp
0x18000c06f  test    eax, eax
0x18000c071  jz      short loc_18000C07C
0x18000c073  mov     rcx, rsi
0x18000c076  call    ?Deinit@?$CAutoRefPtr@VSmartWLIDHandle@@@@IEAAXXZ; CAutoRefPtr<SmartWLIDHandle>::Deinit(void)
0x18000c07b  nop
0x18000c07c  lea     rcx, [rbp+arg_0]
0x18000c080  call    ??1?$CMIDLStringT@PEADPEBD@@QEAA@XZ; CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(void)
0x18000c085  mov     rbx, [rsi]
0x18000c088  test    rbx, rbx
0x18000c08b  jnz     short loc_18000C0CE
0x18000c08d  mov     rcx, r13; Size
0x18000c090  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c095  mov     rbx, rax
0x18000c098  mov     [rbp+arg_0], rax
0x18000c09c  xor     eax, eax
0x18000c09e  mov     [rbx+8], rax
0x18000c0a2  mov     [rbx+18h], r14d
0x18000c0a6  lea     rax, ??_7SmartWLIDHandle@@6B?$SmartObj@PEAX@@@; const SmartWLIDHandle::`vftable'{for `SmartObj<void *>'}
0x18000c0ad  mov     [rbx], rax
0x18000c0b0  lea     rax, ??_7SmartWLIDHandle@@6BCRefCounted@@@; const SmartWLIDHandle::`vftable'{for `CRefCounted'}
0x18000c0b7  mov     [rbx+10h], rax
0x18000c0bb  mov     qword ptr [rbx+20h], 0
0x18000c0c3  mov     rcx, rsi
0x18000c0c6  call    ?Deinit@?$CAutoRefPtr@VSmartWLIDHandle@@@@IEAAXXZ; CAutoRefPtr<SmartWLIDHandle>::Deinit(void)
0x18000c0cb  mov     [rsi], rbx
0x18000c0ce  cmp     qword ptr [rbx+8], 0
0x18000c0d3  jnz     loc_18000C171
0x18000c0d9  mov     [rbp+arg_0], 0
0x18000c0e1  lea     r9, [rbp+arg_0]; void **
0x18000c0e5  mov     rcx, [r15]; unsigned __int16 *
0x18000c0e8  call    ?WLIDCCreateContextEx@@YAJPEBG0_KPEAPEAX@Z; WLIDCCreateContextEx(ushort const *,ushort const *,unsigned __int64,void * *)
0x18000c0ed  mov     edi, eax
0x18000c0ef  test    eax, eax
0x18000c0f1  jns     short loc_18000C164
0x18000c0f3  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x18000c0f8  test    al, al
0x18000c0fa  jz      short loc_18000C108
0x18000c0fc  mov     cl, r14b; this
0x18000c0ff  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x18000c104  test    al, al
0x18000c106  jnz     short loc_18000C10B
0x18000c108  xor     r14b, r14b
0x18000c10b  mov     rax, [r15]
0x18000c10e  mov     [rbp+var_18], rax
0x18000c112  mov     [rbp+var_10], 0
0x18000c11a  mov     [rbp+var_8], r14b
0x18000c11e  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x18000c125  mov     [rbp+var_20], rax
0x18000c129  lea     rcx, [rbp+var_20]; this
0x18000c12d  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x18000c132  mov     [rsp+50h+var_28], edi
0x18000c136  mov     [rsp+50h+var_30], rax
0x18000c13b  lea     r9, aFailedCreateco; "Failed CreateContext for %ls. (0x%x)"
0x18000c142  mov     r8d, 41h ; 'A'; unsigned int
0x18000c148  lea     rdx, aClientcoreDsEx_10; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18000c14f  lea     ecx, [r8-3Fh]; unsigned __int8
0x18000c153  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000c158  nop
0x18000c159  lea     rcx, [rbp+var_20]; this
0x18000c15d  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x18000c162  jmp     short loc_18000C171
0x18000c164  mov     rdx, [rbp+arg_0]; void *
0x18000c168  mov     rcx, rsi; this
0x18000c16b  call    ?Attach@RefWLIDHandle@@QEAAXPEAX@Z; RefWLIDHandle::Attach(void *)
0x18000c170  nop
0x18000c171  mov     rcx, [r15]
0x18000c174  sub     rcx, 18h; this
0x18000c178  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000c17d  mov     eax, edi
0x18000c17f  add     rsp, 50h
0x18000c183  pop     r15
0x18000c185  pop     r14
0x18000c187  pop     r13
0x18000c189  pop     rdi
0x18000c18a  pop     rsi
0x18000c18b  pop     rbx
0x18000c18c  pop     rbp
0x18000c18d  retn
```

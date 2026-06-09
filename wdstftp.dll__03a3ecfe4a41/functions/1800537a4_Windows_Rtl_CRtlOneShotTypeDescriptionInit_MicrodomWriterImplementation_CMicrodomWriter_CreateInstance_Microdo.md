# Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomWriterImplementation::CMicrodomWriter>::CreateInstance<MicrodomWriterImplementation::CMicrodomWriter_IRtlMicrodomXmlWriter,int,Windows::Microdom::Rtl::IRtlMicrodomXmlWriter>(int const &,Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *> *)

- ea: `0x1800537a4`
- end: `0x180053a3f`
- name: `??$CreateInstance@VCMicrodomWriter_IRtlMicrodomXmlWriter@MicrodomWriterImplementation@@HUIRtlMicrodomXmlWriter@Rtl@Microdom@Windows@@@?$CRtlOneShotTypeDescriptionInit@VCMicrodomWriter@MicrodomWriterImplementation@@@Rtl@Windows@@QEAAJAEBHPEAV?$Auto@PEAUIRtlMicrodomXmlWriter@Rtl@Microdom@Windows@@@2@@Z`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005330c`

## callees

- `0x18000a918`
- `0x1800370f4`
- `0x1800537a4`
- `0x1800607b0`
- `0x180060e70`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18005388a`
- `ntdll!RtlRaiseStatus` at `0x18005388a`
- `ntdll!NtYieldExecution` at `0x180053855`
- `ntdll!NtYieldExecution` at `0x1800538b9`
- `ntdll!NtYieldExecution` at `0x180053855`
- `ntdll!NtYieldExecution` at `0x1800538b9`

## string_xrefs

- `0x180053935`: `Windows::Rtl::CRtlObjectTypeDescription<class MicrodomWriterImplementation::CMicrodomWriter>::CreateInstance`
- `0x1800539b3`: `Windows::Rtl::CRtlObjectTypeDescription<class MicrodomWriterImplementation::CMicrodomWriter>::CreateInstance`

## pseudocode

```c
NTSTATUS __fastcall Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomWriterImplementation::CMicrodomWriter>::CreateInstance<MicrodomWriterImplementation::CMicrodomWriter_IRtlMicrodomXmlWriter,int,Windows::Microdom::Rtl::IRtlMicrodomXmlWriter>(
        CHpAllocator *a1,
        __int64 a2,
        _QWORD *a3)
{
  signed __int32 v4; // eax
  volatile __int32 *v5; // rdi
  NTSTATUS result; // eax
  _QWORD *v7; // rax
  __int64 v8; // rdx
  CHpAllocator *v9; // rcx
  _QWORD *v10; // rbx
  _QWORD *v11; // rax
  __int64 v12; // rdx
  _QWORD *v13; // rdi
  _QWORD *v14; // rdi
  signed __int32 v15[10]; // [rsp+0h] [rbp-80h] BYREF
  _QWORD v16[2]; // [rsp+28h] [rbp-58h] BYREF
  int v17; // [rsp+38h] [rbp-48h]
  const char *v18; // [rsp+40h] [rbp-40h]
  _QWORD v19[2]; // [rsp+48h] [rbp-38h] BYREF
  int v20; // [rsp+58h] [rbp-28h]
  const char *v21; // [rsp+60h] [rbp-20h]
  NTSTATUS v22; // [rsp+68h] [rbp-18h]
  NTSTATUS v23; // [rsp+6Ch] [rbp-14h]
  int v24; // [rsp+70h] [rbp-10h]

  v24 = 0;
  if ( dword_180077998 != 2 )
  {
    _InterlockedOr(v15, 0);
    v4 = _InterlockedCompareExchange(&dword_180077998, 1, 0);
    if ( v4 )
    {
      if ( v4 == 1 )
      {
        while ( dword_180077998 != 2 )
          NtYieldExecution();
      }
    }
    else
    {
      qword_1800779B0 = (__int64)&MicrodomWriterImplementation::g_pMicrodomWriterTypeDescription;
      qword_1800779B8 = (__int64)Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomWriterImplementation::CMicrodomWriter>::Teardown;
      if ( MicrodomWriterImplementation::g_pMicrodomWriterTypeDescription )
        __debugbreak();
      dword_180077988 = 0;
      MicrodomWriterImplementation::g_pMicrodomWriterTypeDescription = (__int64)&dword_180077988;
      dword_18007798C = 0;
      _InterlockedExchange(&dword_180077998, 2);
    }
    _InterlockedOr(v15, 0);
  }
  if ( dword_180077998 != 2 )
  {
    __debugbreak();
    RtlRaiseStatus(-1073741595);
  }
  v5 = (volatile __int32 *)MicrodomWriterImplementation::g_pMicrodomWriterTypeDescription;
  v23 = 0;
  v22 = 0;
  if ( !*(_DWORD *)MicrodomWriterImplementation::g_pMicrodomWriterTypeDescription
    && !_InterlockedCompareExchange(
          (volatile signed __int32 *)MicrodomWriterImplementation::g_pMicrodomWriterTypeDescription,
          1,
          0) )
  {
    _InterlockedExchange(v5, 2);
  }
  do
  {
    if ( *v5 == 2 )
    {
      result = 0;
      goto LABEL_19;
    }
    result = NtYieldExecution();
  }
  while ( result >= 0 );
  v22 = result;
LABEL_19:
  if ( result >= 0 )
  {
    v7 = CHpAllocator::Allocate(a1, 0x20u);
    v10 = v7;
    if ( v7 )
    {
      v7[1] = 0;
      v7[2] = 0;
      v7[3] = 0;
      *v7 = &Windows::Rtl::CRtlObjectBase<MicrodomImplementation::CMicrodom>::`vftable';
      *v7 = &Windows::Rtl::CRtlObjectBase<MicrodomImplementation::CMicrodom>::`vftable';
      *((_DWORD *)v7 + 2) = 0;
    }
    else
    {
      v10 = 0;
    }
    if ( !v10 )
    {
      v17 = 467;
      v16[0] = "internal\\onecorebase\\inc\\rtl_object_library.h";
      v16[1] = "Windows::Rtl::CRtlObjectTypeDescription<class MicrodomWriterImplementation::CMicrodomWriter>::CreateInstance";
      v18 = "NewInstance.Allocate()";
      RtlReportErrorOrigination(v16, v8, 3221225495LL);
      return -1073741801;
    }
    v10[2] = v10;
    v10[3] = v5;
    v11 = CHpAllocator::Allocate(v9, 0x18u);
    v13 = v11;
    if ( v11 )
    {
      v11[1] = 0;
      *v11 = &Windows::Rtl::CRtlTearoffObject<MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff>::`vftable'{for `Windows::Rtl::CRtlTearoffBase<MicrodomImplementation::CMicrodom>'};
      v11[2] = &Windows::Rtl::CRtlTearoffObject<MicrodomWriterImplementation::CMicrodomWriter_IRtlMicrodomXmlWriter>::`vftable'{for `Windows::Microdom::Rtl::IRtlMicrodomXmlWriter'};
    }
    else
    {
      v13 = 0;
    }
    if ( !v13 )
    {
      v20 = 484;
      v19[0] = "internal\\onecorebase\\inc\\rtl_object_library.h";
      v19[1] = "Windows::Rtl::CRtlObjectTypeDescription<class MicrodomWriterImplementation::CMicrodomWriter>::CreateInstance";
      v21 = "NewTearoff.Allocate()";
      RtlReportErrorOrigination(v19, v12, 3221225495LL);
      (*(void (__fastcall **)(_QWORD *, __int64))*v10)(v10, 1);
      return -1073741801;
    }
    v13[1] = v10;
    (*(void (__fastcall **)(_QWORD *))(*v10 + 8LL))(v10);
    v14 = v13 + 2;
    if ( *a3 )
      __debugbreak();
    result = v23;
    *a3 = v14;
    if ( result >= 0 )
      return v24;
  }
  return result;
}

```

## disassembly

```asm
0x1800537a4  mov     [rsp-18h+arg_0], rbx
0x1800537a9  mov     [rsp-18h+arg_8], rsi
0x1800537ae  mov     [rsp-18h+arg_18], rdi
0x1800537b3  push    rbp
0x1800537b4  push    r14
0x1800537b6  push    r15
0x1800537b8  mov     rbp, rsp
0x1800537bb  sub     rsp, 80h
0x1800537c2  mov     rax, cs:__security_cookie
0x1800537c9  xor     rax, rsp
0x1800537cc  mov     [rbp+var_8], rax
0x1800537d0  mov     eax, cs:dword_180077998
0x1800537d6  xor     r14d, r14d
0x1800537d9  mov     rsi, r8
0x1800537dc  mov     [rbp+var_10], r14d
0x1800537e0  lea     ebx, [r14+2]
0x1800537e4  lea     r15d, [r14+1]
0x1800537e8  cmp     eax, ebx
0x1800537ea  jz      loc_180053870
0x1800537f0  lock or [rsp+80h+var_80], r14d
0x1800537f5  xor     eax, eax
0x1800537f7  lock cmpxchg cs:dword_180077998, r15d
0x180053800  jnz     short loc_18005384E
0x180053802  cmp     cs:?g_pMicrodomWriterTypeDescription@MicrodomWriterImplementation@@3V?$CRtlOneShotTypeDescriptionInit@VCMicrodomWriter@MicrodomWriterImplementation@@@Rtl@Windows@@A, r14; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomWriterImplementation::CMicrodomWriter> MicrodomWriterImplementation::g_pMicrodomWriterTypeDescription
0x180053809  lea     rax, ?g_pMicrodomWriterTypeDescription@MicrodomWriterImplementation@@3V?$CRtlOneShotTypeDescriptionInit@VCMicrodomWriter@MicrodomWriterImplementation@@@Rtl@Windows@@A; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomWriterImplementation::CMicrodomWriter> MicrodomWriterImplementation::g_pMicrodomWriterTypeDescription
0x180053810  mov     cs:qword_1800779B0, rax
0x180053817  lea     rax, ?Teardown@?$CRtlOneShotTypeDescriptionInit@VCMicrodomWriter@MicrodomWriterImplementation@@@Rtl@Windows@@CAXPEAX@Z; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomWriterImplementation::CMicrodomWriter>::Teardown(void *)
0x18005381e  mov     cs:qword_1800779B8, rax
0x180053825  jz      short loc_180053828
0x180053827  int     3; Trap to Debugger
0x180053828  lea     rax, dword_180077988
0x18005382f  mov     cs:dword_180077988, r14d
0x180053836  mov     cs:?g_pMicrodomWriterTypeDescription@MicrodomWriterImplementation@@3V?$CRtlOneShotTypeDescriptionInit@VCMicrodomWriter@MicrodomWriterImplementation@@@Rtl@Windows@@A, rax; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomWriterImplementation::CMicrodomWriter> MicrodomWriterImplementation::g_pMicrodomWriterTypeDescription
0x18005383d  mov     eax, ebx
0x18005383f  mov     cs:dword_18007798C, r14d
0x180053846  xchg    eax, cs:dword_180077998
0x18005384c  jmp     short loc_18005386B
0x18005384e  cmp     eax, r15d
0x180053851  jnz     short loc_18005386B
0x180053853  jmp     short loc_180053861
0x180053855  call    cs:__imp_NtYieldExecution
0x18005385c  nop     dword ptr [rax+rax+00h]
0x180053861  mov     eax, cs:dword_180077998
0x180053867  cmp     eax, ebx
0x180053869  jnz     short loc_180053855
0x18005386b  lock or [rsp+80h+var_80], r14d
0x180053870  mov     eax, cs:dword_180077998
0x180053876  cmp     eax, ebx
0x180053878  jz      short loc_18005387B
0x18005387a  int     3; Trap to Debugger
0x18005387b  mov     eax, cs:dword_180077998
0x180053881  cmp     eax, ebx
0x180053883  jz      short loc_180053897
0x180053885  mov     ecx, 0C00000E5h; Status
0x18005388a  call    cs:__imp_RtlRaiseStatus
0x180053891  nop     dword ptr [rax+rax+00h]
0x180053896  int     3; Trap to Debugger
0x180053897  mov     rdi, cs:?g_pMicrodomWriterTypeDescription@MicrodomWriterImplementation@@3V?$CRtlOneShotTypeDescriptionInit@VCMicrodomWriter@MicrodomWriterImplementation@@@Rtl@Windows@@A; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomWriterImplementation::CMicrodomWriter> MicrodomWriterImplementation::g_pMicrodomWriterTypeDescription
0x18005389e  mov     [rbp+var_14], r14d
0x1800538a2  mov     [rbp+var_18], r14d
0x1800538a6  mov     eax, [rdi]
0x1800538a8  test    eax, eax
0x1800538aa  jnz     short loc_1800538C9
0x1800538ac  lock cmpxchg [rdi], r15d
0x1800538b1  jnz     short loc_1800538C9
0x1800538b3  mov     eax, ebx
0x1800538b5  xchg    eax, [rdi]
0x1800538b7  jmp     short loc_1800538C9
0x1800538b9  call    cs:__imp_NtYieldExecution
0x1800538c0  nop     dword ptr [rax+rax+00h]
0x1800538c5  test    eax, eax
0x1800538c7  js      short loc_180053912
0x1800538c9  mov     eax, [rdi]
0x1800538cb  cmp     eax, ebx
0x1800538cd  jnz     short loc_1800538B9
0x1800538cf  mov     eax, r14d
0x1800538d2  test    eax, eax
0x1800538d4  js      loc_180053A16
0x1800538da  mov     edx, 20h ; ' '; unsigned __int64
0x1800538df  call    ?Allocate@CHpAllocator@@QEAAPEAX_K@Z; CHpAllocator::Allocate(unsigned __int64)
0x1800538e4  mov     rbx, rax
0x1800538e7  test    rax, rax
0x1800538ea  jz      short loc_180053917
0x1800538ec  mov     [rax+8], r14
0x1800538f0  mov     [rax+10h], r14
0x1800538f4  mov     [rax+18h], r14
0x1800538f8  lea     rax, ??_7?$CRtlObjectBase@VCMicrodom@MicrodomImplementation@@@Rtl@Windows@@6B@; const Windows::Rtl::CRtlObjectBase<MicrodomImplementation::CMicrodom>::`vftable'
0x1800538ff  mov     [rbx], rax
0x180053902  lea     rax, ??_7?$CRtlObjectBase@VCMicrodom@MicrodomImplementation@@@Rtl@Windows@@6B@; const Windows::Rtl::CRtlObjectBase<MicrodomImplementation::CMicrodom>::`vftable'
0x180053909  mov     [rbx], rax
0x18005390c  mov     [rbx+8], r14d
0x180053910  jmp     short loc_18005391A
0x180053912  mov     [rbp+var_18], eax
0x180053915  jmp     short loc_1800538D2
0x180053917  mov     rbx, r14
0x18005391a  test    rbx, rbx
0x18005391d  jnz     short loc_180053960
0x18005391f  lea     rax, aInternalOnecor; "internal\\onecorebase\\inc\\rtl_object_"...
0x180053926  mov     [rbp+var_48], 1D3h
0x18005392d  mov     [rbp+var_58], rax
0x180053931  lea     rcx, [rbp+var_58]
0x180053935  lea     rax, aWindowsRtlCrtl_0; "Windows::Rtl::CRtlObjectTypeDescription"...
0x18005393c  mov     r8d, 0C0000017h
0x180053942  mov     [rbp+var_50], rax
0x180053946  lea     rax, aNewinstanceAll; "NewInstance.Allocate()"
0x18005394d  mov     [rbp+var_40], rax
0x180053951  call    RtlReportErrorOrigination
0x180053956  mov     eax, 0C0000017h
0x18005395b  jmp     loc_180053A16
0x180053960  mov     edx, 18h; unsigned __int64
0x180053965  mov     [rbx+10h], rbx
0x180053969  mov     [rbx+18h], rdi
0x18005396d  call    ?Allocate@CHpAllocator@@QEAAPEAX_K@Z; CHpAllocator::Allocate(unsigned __int64)
0x180053972  mov     rdi, rax
0x180053975  test    rax, rax
0x180053978  jz      short loc_180053995
0x18005397a  mov     [rax+8], r14
0x18005397e  lea     rax, ??_7?$CRtlTearoffObject@VCMicrodom_IRtlMicrodomTearoff@MicrodomImplementation@@@Rtl@Windows@@6B?$CRtlTearoffBase@VCMicrodom@MicrodomImplementation@@@12@@; const Windows::Rtl::CRtlTearoffObject<MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff>::`vftable'{for `Windows::Rtl::CRtlTearoffBase<MicrodomImplementation::CMicrodom>'}
0x180053985  mov     [rdi], rax
0x180053988  lea     rax, ??_7?$CRtlTearoffObject@VCMicrodomWriter_IRtlMicrodomXmlWriter@MicrodomWriterImplementation@@@Rtl@Windows@@6BIRtlMicrodomXmlWriter@1Microdom@2@@; const Windows::Rtl::CRtlTearoffObject<MicrodomWriterImplementation::CMicrodomWriter_IRtlMicrodomXmlWriter>::`vftable'{for `Windows::Microdom::Rtl::IRtlMicrodomXmlWriter'}
0x18005398f  mov     [rdi+10h], rax
0x180053993  jmp     short loc_180053998
0x180053995  mov     rdi, r14
0x180053998  test    rdi, rdi
0x18005399b  jnz     short loc_1800539EB
0x18005399d  lea     rax, aInternalOnecor; "internal\\onecorebase\\inc\\rtl_object_"...
0x1800539a4  mov     [rbp+var_28], 1E4h
0x1800539ab  mov     [rbp+var_38], rax
0x1800539af  lea     rcx, [rbp+var_38]
0x1800539b3  lea     rax, aWindowsRtlCrtl_0; "Windows::Rtl::CRtlObjectTypeDescription"...
0x1800539ba  mov     r8d, 0C0000017h
0x1800539c0  mov     [rbp+var_30], rax
0x1800539c4  lea     rax, aNewtearoffAllo; "NewTearoff.Allocate()"
0x1800539cb  mov     [rbp+var_20], rax
0x1800539cf  call    RtlReportErrorOrigination
0x1800539d4  mov     rax, [rbx]
0x1800539d7  mov     edx, r15d
0x1800539da  mov     rcx, rbx
0x1800539dd  mov     rax, [rax]
0x1800539e0  call    cs:__guard_dispatch_icall_fptr
0x1800539e6  jmp     loc_180053956
0x1800539eb  mov     [rdi+8], rbx
0x1800539ef  mov     rcx, rbx
0x1800539f2  mov     rax, [rbx]
0x1800539f5  mov     rax, [rax+8]
0x1800539f9  call    cs:__guard_dispatch_icall_fptr
0x1800539ff  add     rdi, 10h
0x180053a03  cmp     [rsi], r14
0x180053a06  jz      short loc_180053A09
0x180053a08  int     3; Trap to Debugger
0x180053a09  mov     eax, [rbp+var_14]
0x180053a0c  mov     [rsi], rdi
0x180053a0f  test    eax, eax
0x180053a11  js      short loc_180053A16
0x180053a13  mov     eax, [rbp+var_10]
0x180053a16  mov     rcx, [rbp+var_8]
0x180053a1a  xor     rcx, rsp; StackCookie
0x180053a1d  call    __security_check_cookie
0x180053a22  lea     r11, [rsp+80h+var_s0]
0x180053a2a  mov     rbx, [r11+20h]
0x180053a2e  mov     rsi, [r11+28h]
0x180053a32  mov     rdi, [r11+38h]
0x180053a36  mov     rsp, r11
0x180053a39  pop     r15
0x180053a3b  pop     r14
0x180053a3d  pop     rbp
0x180053a3e  retn
```

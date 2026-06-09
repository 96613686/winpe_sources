# TaskSettingsImpl::FinalConstruct(void)

- ea: `0x1800244bc`
- end: `0x180024761`
- name: `?FinalConstruct@TaskSettingsImpl@@QEAAJXZ`
- size: `677`
- prototype: `__int64 __fastcall(TaskSettingsImpl *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800064f8`

## callees

- `0x1800244bc`
- `0x1800247d0`
- `0x1800248f0`
- `0x180039524`
- `0x18003b51c`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002468a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002468a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800244e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800244e9`
- `OLEAUT32!__imp_SysAllocString` at `0x180024635`
- `OLEAUT32!__imp_SysAllocString` at `0x180024635`
- `OLEAUT32!__imp_SysFreeString` at `0x1800245e4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800245f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002460c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002462c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800245e4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800245f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002460c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002462c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TaskSettingsImpl::FinalConstruct(TaskSettingsImpl *this)
{
  unsigned __int64 v2; // rdi
  __int64 v3; // rcx
  int v4; // eax
  __int64 v5; // rcx
  int v6; // esi
  OLECHAR *v7; // rcx
  BSTR v8; // rax
  __int64 v9; // rcx
  __int64 result; // rax
  void **pExceptionObject; // [rsp+20h] [rbp-A8h] BYREF
  char v13; // [rsp+28h] [rbp-A0h]
  __int64 *v14; // [rsp+30h] [rbp-98h]
  __int64 v15; // [rsp+38h] [rbp-90h]
  __int64 v16; // [rsp+40h] [rbp-88h]
  int v17; // [rsp+48h] [rbp-80h]
  int v18; // [rsp+4Ch] [rbp-7Ch]
  int v19; // [rsp+50h] [rbp-78h]
  void **v20; // [rsp+58h] [rbp-70h] BYREF
  char v21; // [rsp+60h] [rbp-68h]
  __int64 *v22; // [rsp+68h] [rbp-60h]
  __int64 v23; // [rsp+70h] [rbp-58h]
  __int64 v24; // [rsp+78h] [rbp-50h]
  int v25; // [rsp+80h] [rbp-48h]
  int v26; // [rsp+84h] [rbp-44h]
  int v27; // [rsp+88h] [rbp-40h]
  wmi::Exception *v28; // [rsp+90h] [rbp-38h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, char *); // [rsp+D0h] [rbp+8h] BYREF
  unsigned __int64 v30; // [rsp+D8h] [rbp+10h]

  v2 = ((unsigned __int64)this + 16) & -(__int64)(this != 0);
  if ( v2 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
  try
  {
    v30 = v2;
    v3 = *((_QWORD *)this + 9);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    v29 = 0;
    v4 = ATL::CComObject<IdleSettingsImpl>::CreateInstance(&v29);
    if ( v4 < 0 || (v4 = (**v29)(v29, &GUID_84594461_0053_4342_a8fd_088fabf11f32, (char *)this + 72), v4 < 0) )
    {
      v21 = 0;
      v20 = &wmi::GenericException::`vftable';
      v22 = &qword_180077320;
      v23 = 0;
      v24 = 0;
      v25 = v4;
      v26 = -1;
      v27 = -1;
      throw (wmi::GenericException *)&v20;
    }
    v5 = *((_QWORD *)this + 10);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v29 = 0;
    v6 = ATL::CComObject<NetworkSettingsImpl>::CreateInstance(&v29);
    if ( v6 < 0 || (v6 = (**v29)(v29, &GUID_9f7dea84_c30b_4245_80b6_00e9f646f1b4, (char *)this + 80), v6 < 0) )
    {
      v13 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v14 = &qword_180077320;
      v15 = 0;
      v16 = 0;
      v17 = v6;
      v18 = -1;
      v19 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    *((_WORD *)this + 48) = -1;
    *((_WORD *)this + 49) = -1;
    *((_WORD *)this + 50) = -1;
    *((_WORD *)this + 51) = -1;
    *((_DWORD *)this + 26) = 0;
    *((_WORD *)this + 54) = -1;
    *(_DWORD *)((char *)this + 110) = 0;
    *((_WORD *)this + 57) = 0;
    *((_DWORD *)this + 42) = 2;
    SysFreeString(*((BSTR *)this + 16));
    *((_QWORD *)this + 16) = 0;
    SysFreeString(*((BSTR *)this + 18));
    *((_QWORD *)this + 18) = 0;
    SysFreeString(*((BSTR *)this + 19));
    *((_QWORD *)this + 19) = 0;
    v7 = (OLECHAR *)*((_QWORD *)this + 17);
    if ( L"PT72H" != v7 )
    {
      SysFreeString(v7);
      v8 = SysAllocString(L"PT72H");
      *((_QWORD *)this + 17) = v8;
      if ( !v8 )
        ATL::PrivateAtlThrow(-2147024882);
    }
    *((_DWORD *)this + 40) = 0;
    *((_DWORD *)this + 41) = 7;
    *((_DWORD *)this + 43) = 2;
    *((_DWORD *)this + 29) = 0;
    v9 = *((_QWORD *)this + 11);
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *((_QWORD *)this + 11) = 0;
    }
    *((_WORD *)this + 60) = 0;
    if ( v2 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
    result = (unsigned int)v6;
  }
  catch ( wmi::Exception *v28 )
  {
    LODWORD(result) = (**(__int64 (__fastcall ***)(wmi::Exception *))v28)(v28);
    if ( (int)result > 0 )
      LODWORD(result) = (unsigned __int16)result | 0x80070000;
    LODWORD(v29) = result;
    return (unsigned int)result;
  }
  return result;
}

```

## disassembly

```asm
0x1800244bc  mov     [rsp+arg_10], rbx
0x1800244c1  push    rsi
0x1800244c2  push    rdi
0x1800244c3  push    r12
0x1800244c5  push    r14
0x1800244c7  push    r15
0x1800244c9  sub     rsp, 0A0h
0x1800244d0  mov     rbx, rcx
0x1800244d3  mov     rax, rcx
0x1800244d6  lea     rdx, [rcx+10h]
0x1800244da  neg     rax
0x1800244dd  sbb     rdi, rdi
0x1800244e0  and     rdi, rdx
0x1800244e3  jz      short loc_1800244EF
0x1800244e5  lea     rcx, [rdi+8]; lpCriticalSection
0x1800244e9  call    cs:__imp_EnterCriticalSection
0x1800244ef  mov     [rsp+0C8h+arg_8], rdi
0x1800244f7  mov     rcx, [rbx+48h]
0x1800244fb  xor     r15d, r15d
0x1800244fe  test    rcx, rcx
0x180024501  jz      short loc_18002450F
0x180024503  mov     rax, [rcx]
0x180024506  mov     rax, [rax+10h]
0x18002450a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002450f  mov     [rsp+0C8h+arg_0], r15
0x180024517  lea     rcx, [rsp+0C8h+arg_0]
0x18002451f  call    ?CreateInstance@?$CComObject@VIdleSettingsImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<IdleSettingsImpl>::CreateInstance(ATL::CComObject<IdleSettingsImpl> * *)
0x180024524  test    eax, eax
0x180024526  js      loc_180024700
0x18002452c  mov     rcx, [rsp+0C8h+arg_0]
0x180024534  mov     rax, [rcx]
0x180024537  lea     r8, [rbx+48h]
0x18002453b  lea     rdx, _GUID_84594461_0053_4342_a8fd_088fabf11f32
0x180024542  mov     rax, [rax]
0x180024545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002454a  test    eax, eax
0x18002454c  js      loc_180024700
0x180024552  mov     rcx, [rbx+50h]
0x180024556  test    rcx, rcx
0x180024559  jz      short loc_180024567
0x18002455b  mov     rax, [rcx]
0x18002455e  mov     rax, [rax+10h]
0x180024562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024567  mov     [rsp+0C8h+arg_0], r15
0x18002456f  lea     rcx, [rsp+0C8h+arg_0]
0x180024577  call    ?CreateInstance@?$CComObject@VNetworkSettingsImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<NetworkSettingsImpl>::CreateInstance(ATL::CComObject<NetworkSettingsImpl> * *)
0x18002457c  mov     esi, eax
0x18002457e  test    eax, eax
0x180024580  js      loc_1800246B5
0x180024586  mov     rcx, [rsp+0C8h+arg_0]
0x18002458e  mov     rax, [rcx]
0x180024591  lea     r8, [rbx+50h]
0x180024595  lea     rdx, _GUID_9f7dea84_c30b_4245_80b6_00e9f646f1b4
0x18002459c  mov     rax, [rax]
0x18002459f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245a4  mov     esi, eax
0x1800245a6  test    eax, eax
0x1800245a8  js      loc_1800246B5
0x1800245ae  or      ecx, 0FFFFFFFFh
0x1800245b1  mov     [rbx+60h], cx
0x1800245b5  mov     [rbx+62h], cx
0x1800245b9  mov     [rbx+64h], cx
0x1800245bd  mov     [rbx+66h], cx
0x1800245c1  mov     [rbx+68h], r15d
0x1800245c5  mov     [rbx+6Ch], cx
0x1800245c9  mov     [rbx+6Eh], r15d
0x1800245cd  mov     [rbx+72h], r15w
0x1800245d2  lea     r14d, [rcx+3]
0x1800245d6  mov     [rbx+0A8h], r14d
0x1800245dd  mov     rcx, [rbx+80h]; bstrString
0x1800245e4  call    cs:__imp_SysFreeString
0x1800245ea  mov     [rbx+80h], r15
0x1800245f1  mov     rcx, [rbx+90h]; bstrString
0x1800245f8  call    cs:__imp_SysFreeString
0x1800245fe  mov     [rbx+90h], r15
0x180024605  mov     rcx, [rbx+98h]; bstrString
0x18002460c  call    cs:__imp_SysFreeString
0x180024612  mov     [rbx+98h], r15
0x180024619  mov     rcx, [rbx+88h]; bstrString
0x180024620  lea     r12, aPt72h; "PT72H"
0x180024627  cmp     r12, rcx
0x18002462a  jz      short loc_180024647
0x18002462c  call    cs:__imp_SysFreeString
0x180024632  mov     rcx, r12; psz
0x180024635  call    cs:__imp_SysAllocString
0x18002463b  mov     [rbx+88h], rax
0x180024642  test    rax, rax
0x180024645  jz      short loc_1800246AB
0x180024647  mov     [rbx+0A0h], r15d
0x18002464e  mov     dword ptr [rbx+0A4h], 7
0x180024658  mov     [rbx+0ACh], r14d
0x18002465f  mov     [rbx+74h], r15d
0x180024663  mov     rcx, [rbx+58h]
0x180024667  test    rcx, rcx
0x18002466a  jz      short loc_18002467C
0x18002466c  mov     rax, [rcx]
0x18002466f  mov     rax, [rax+10h]
0x180024673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024678  mov     [rbx+58h], r15
0x18002467c  mov     [rbx+78h], r15w
0x180024681  test    rdi, rdi
0x180024684  jz      short loc_180024691
0x180024686  lea     rcx, [rdi+8]; lpCriticalSection
0x18002468a  call    cs:__imp_LeaveCriticalSection
0x180024690  nop
0x180024691  mov     eax, esi
0x180024693  mov     rbx, [rsp+0C8h+arg_10]
0x18002469b  add     rsp, 0A0h
0x1800246a2  pop     r15
0x1800246a4  pop     r14
0x1800246a6  pop     r12
0x1800246a8  pop     rdi
0x1800246a9  pop     rsi
0x1800246aa  retn
0x1800246ab  mov     ecx, 8007000Eh; int
0x1800246b0  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1800246b5  mov     [rsp+0C8h+var_A0], r15b
0x1800246ba  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800246c1  mov     [rsp+0C8h+pExceptionObject], rcx
0x1800246c6  lea     rcx, qword_180077320
0x1800246cd  mov     [rsp+0C8h+var_98], rcx
0x1800246d2  mov     [rsp+0C8h+var_90], r15
0x1800246d7  mov     [rsp+0C8h+var_88], r15
0x1800246dc  mov     [rsp+0C8h+var_80], esi
0x1800246e0  mov     [rsp+0C8h+var_7C], 0FFFFFFFFh
0x1800246e8  or      ecx, 0FFFFFFFFh
0x1800246eb  mov     [rsp+0C8h+var_78], ecx
0x1800246ef  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800246f6  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x1800246fb  call    _CxxThrowException_0
0x180024700  mov     [rsp+0C8h+var_68], r15b
0x180024705  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002470c  mov     [rsp+0C8h+var_70], rcx
0x180024711  lea     rcx, qword_180077320
0x180024718  mov     [rsp+0C8h+var_60], rcx
0x18002471d  mov     [rsp+0C8h+var_58], r15
0x180024722  mov     [rsp+0C8h+var_50], r15
0x180024727  mov     [rsp+0C8h+var_48], eax
0x18002472e  mov     [rsp+0C8h+var_44], 0FFFFFFFFh
0x180024739  or      ecx, 0FFFFFFFFh
0x18002473c  mov     [rsp+0C8h+var_40], ecx
0x180024743  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18002474a  lea     rcx, [rsp+0C8h+var_70]; pExceptionObject
0x18002474f  call    _CxxThrowException_0
0x180024755  mov     eax, dword ptr [rsp+0C8h+arg_0]
0x18002475c  jmp     loc_180024693
```

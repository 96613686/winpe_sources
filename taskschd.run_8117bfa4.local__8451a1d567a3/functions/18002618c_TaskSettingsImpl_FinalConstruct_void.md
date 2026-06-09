# TaskSettingsImpl::FinalConstruct(void)

- ea: `0x18002618c`
- end: `0x18002645c`
- name: `?FinalConstruct@TaskSettingsImpl@@QEAAJXZ`
- size: `720`
- prototype: `__int64 __fastcall(TaskSettingsImpl *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000684c`

## callees

- `0x18002618c`
- `0x1800264d0`
- `0x1800265f0`
- `0x18003c664`
- `0x18003e88c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002637e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002637e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800261b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800261b9`
- `OLEAUT32!__imp_SysAllocString` at `0x180026323`
- `OLEAUT32!__imp_SysAllocString` at `0x180026323`
- `OLEAUT32!__imp_SysFreeString` at `0x1800262ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800262d4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800262ee`
- `OLEAUT32!__imp_SysFreeString` at `0x180026314`
- `OLEAUT32!__imp_SysFreeString` at `0x1800262ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800262d4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800262ee`
- `OLEAUT32!__imp_SysFreeString` at `0x180026314`

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
      v22 = &qword_18007B2F0;
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
      v14 = &qword_18007B2F0;
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
0x18002618c  mov     [rsp+arg_10], rbx
0x180026191  push    rsi
0x180026192  push    rdi
0x180026193  push    r12
0x180026195  push    r14
0x180026197  push    r15
0x180026199  sub     rsp, 0A0h
0x1800261a0  mov     rbx, rcx
0x1800261a3  mov     rax, rcx
0x1800261a6  lea     rdx, [rcx+10h]
0x1800261aa  neg     rax
0x1800261ad  sbb     rdi, rdi
0x1800261b0  and     rdi, rdx
0x1800261b3  jz      short loc_1800261C5
0x1800261b5  lea     rcx, [rdi+8]; lpCriticalSection
0x1800261b9  call    cs:__imp_EnterCriticalSection
0x1800261c0  nop     dword ptr [rax+rax+00h]
0x1800261c5  mov     [rsp+0C8h+arg_8], rdi
0x1800261cd  mov     rcx, [rbx+48h]
0x1800261d1  xor     r15d, r15d
0x1800261d4  test    rcx, rcx
0x1800261d7  jz      short loc_1800261E5
0x1800261d9  mov     rax, [rcx]
0x1800261dc  mov     rax, [rax+10h]
0x1800261e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261e5  mov     [rsp+0C8h+arg_0], r15
0x1800261ed  lea     rcx, [rsp+0C8h+arg_0]
0x1800261f5  call    ?CreateInstance@?$CComObject@VIdleSettingsImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<IdleSettingsImpl>::CreateInstance(ATL::CComObject<IdleSettingsImpl> * *)
0x1800261fa  test    eax, eax
0x1800261fc  js      loc_1800263FB
0x180026202  mov     rcx, [rsp+0C8h+arg_0]
0x18002620a  mov     rax, [rcx]
0x18002620d  lea     r8, [rbx+48h]
0x180026211  lea     rdx, _GUID_84594461_0053_4342_a8fd_088fabf11f32
0x180026218  mov     rax, [rax]
0x18002621b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026220  test    eax, eax
0x180026222  js      loc_1800263FB
0x180026228  mov     rcx, [rbx+50h]
0x18002622c  test    rcx, rcx
0x18002622f  jz      short loc_18002623D
0x180026231  mov     rax, [rcx]
0x180026234  mov     rax, [rax+10h]
0x180026238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002623d  mov     [rsp+0C8h+arg_0], r15
0x180026245  lea     rcx, [rsp+0C8h+arg_0]
0x18002624d  call    ?CreateInstance@?$CComObject@VNetworkSettingsImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<NetworkSettingsImpl>::CreateInstance(ATL::CComObject<NetworkSettingsImpl> * *)
0x180026252  mov     esi, eax
0x180026254  test    eax, eax
0x180026256  js      loc_1800263B0
0x18002625c  mov     rcx, [rsp+0C8h+arg_0]
0x180026264  mov     rax, [rcx]
0x180026267  lea     r8, [rbx+50h]
0x18002626b  lea     rdx, _GUID_9f7dea84_c30b_4245_80b6_00e9f646f1b4
0x180026272  mov     rax, [rax]
0x180026275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002627a  mov     esi, eax
0x18002627c  test    eax, eax
0x18002627e  js      loc_1800263B0
0x180026284  or      ecx, 0FFFFFFFFh
0x180026287  mov     [rbx+60h], cx
0x18002628b  mov     [rbx+62h], cx
0x18002628f  mov     [rbx+64h], cx
0x180026293  mov     [rbx+66h], cx
0x180026297  mov     [rbx+68h], r15d
0x18002629b  mov     [rbx+6Ch], cx
0x18002629f  mov     [rbx+6Eh], r15d
0x1800262a3  mov     [rbx+72h], r15w
0x1800262a8  lea     r14d, [rcx+3]
0x1800262ac  mov     [rbx+0A8h], r14d
0x1800262b3  mov     rcx, [rbx+80h]; bstrString
0x1800262ba  call    cs:__imp_SysFreeString
0x1800262c1  nop     dword ptr [rax+rax+00h]
0x1800262c6  mov     [rbx+80h], r15
0x1800262cd  mov     rcx, [rbx+90h]; bstrString
0x1800262d4  call    cs:__imp_SysFreeString
0x1800262db  nop     dword ptr [rax+rax+00h]
0x1800262e0  mov     [rbx+90h], r15
0x1800262e7  mov     rcx, [rbx+98h]; bstrString
0x1800262ee  call    cs:__imp_SysFreeString
0x1800262f5  nop     dword ptr [rax+rax+00h]
0x1800262fa  mov     [rbx+98h], r15
0x180026301  mov     rcx, [rbx+88h]; bstrString
0x180026308  lea     r12, aPt72h; "PT72H"
0x18002630f  cmp     r12, rcx
0x180026312  jz      short loc_18002633B
0x180026314  call    cs:__imp_SysFreeString
0x18002631b  nop     dword ptr [rax+rax+00h]
0x180026320  mov     rcx, r12; psz
0x180026323  call    cs:__imp_SysAllocString
0x18002632a  nop     dword ptr [rax+rax+00h]
0x18002632f  mov     [rbx+88h], rax
0x180026336  test    rax, rax
0x180026339  jz      short loc_1800263A6
0x18002633b  mov     [rbx+0A0h], r15d
0x180026342  mov     dword ptr [rbx+0A4h], 7
0x18002634c  mov     [rbx+0ACh], r14d
0x180026353  mov     [rbx+74h], r15d
0x180026357  mov     rcx, [rbx+58h]
0x18002635b  test    rcx, rcx
0x18002635e  jz      short loc_180026370
0x180026360  mov     rax, [rcx]
0x180026363  mov     rax, [rax+10h]
0x180026367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002636c  mov     [rbx+58h], r15
0x180026370  mov     [rbx+78h], r15w
0x180026375  test    rdi, rdi
0x180026378  jz      short loc_18002638B
0x18002637a  lea     rcx, [rdi+8]; lpCriticalSection
0x18002637e  call    cs:__imp_LeaveCriticalSection
0x180026385  nop     dword ptr [rax+rax+00h]
0x18002638a  nop
0x18002638b  mov     eax, esi
0x18002638d  mov     rbx, [rsp+0C8h+arg_10]
0x180026395  add     rsp, 0A0h
0x18002639c  pop     r15
0x18002639e  pop     r14
0x1800263a0  pop     r12
0x1800263a2  pop     rdi
0x1800263a3  pop     rsi
0x1800263a4  retn
0x1800263a6  mov     ecx, 8007000Eh; int
0x1800263ab  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1800263b0  mov     [rsp+0C8h+var_A0], r15b
0x1800263b5  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800263bc  mov     [rsp+0C8h+pExceptionObject], rcx
0x1800263c1  lea     rcx, qword_18007B2F0
0x1800263c8  mov     [rsp+0C8h+var_98], rcx
0x1800263cd  mov     [rsp+0C8h+var_90], r15
0x1800263d2  mov     [rsp+0C8h+var_88], r15
0x1800263d7  mov     [rsp+0C8h+var_80], esi
0x1800263db  mov     [rsp+0C8h+var_7C], 0FFFFFFFFh
0x1800263e3  or      ecx, 0FFFFFFFFh
0x1800263e6  mov     [rsp+0C8h+var_78], ecx
0x1800263ea  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800263f1  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x1800263f6  call    _CxxThrowException_0
0x1800263fb  mov     [rsp+0C8h+var_68], r15b
0x180026400  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180026407  mov     [rsp+0C8h+var_70], rcx
0x18002640c  lea     rcx, qword_18007B2F0
0x180026413  mov     [rsp+0C8h+var_60], rcx
0x180026418  mov     [rsp+0C8h+var_58], r15
0x18002641d  mov     [rsp+0C8h+var_50], r15
0x180026422  mov     [rsp+0C8h+var_48], eax
0x180026429  mov     [rsp+0C8h+var_44], 0FFFFFFFFh
0x180026434  or      ecx, 0FFFFFFFFh
0x180026437  mov     [rsp+0C8h+var_40], ecx
0x18002643e  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180026445  lea     rcx, [rsp+0C8h+var_70]; pExceptionObject
0x18002644a  call    _CxxThrowException_0
0x180026450  mov     eax, dword ptr [rsp+0C8h+arg_0]
0x180026457  jmp     loc_18002638D
```

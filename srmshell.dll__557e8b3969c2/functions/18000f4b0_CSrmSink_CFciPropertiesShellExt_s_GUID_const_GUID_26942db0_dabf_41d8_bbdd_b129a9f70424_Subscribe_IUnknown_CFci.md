# CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::Subscribe(IUnknown *,CFciPropertiesShellExt *)

- ea: `0x18000f4b0`
- end: `0x18000f6d6`
- name: `?Subscribe@?$CSrmSink@VCFciPropertiesShellExt@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@B@@QEAAXPEAUIUnknown@@PEAVCFciPropertiesShellExt@@@Z`
- size: `550`
- prototype: `void __fastcall(__int64, __int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *), __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180006688`

## callees

- `0x1800083e0`
- `0x18000d368`
- `0x18000f4b0`
- `0x18001623c`
- `0x180016564`
- `0x180018f68`
- `0x18001b3ee`
- `0x18001b420`
- `0x180020010`

## string_xrefs

- `0x18000f4f7`: `CSrmSink<class CFciPropertiesShellExt,&struct __s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::Subscribe`

## pseudocode

```c
void __fastcall CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::Subscribe(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, _QWORD *),
        __int64 a3)
{
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  char v10; // al
  int Hr; // eax
  char v12; // al
  int v13; // eax
  char v14; // al
  __int64 v15; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v16[2]; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v17[3]; // [rsp+38h] [rbp-C8h] BYREF
  int v18; // [rsp+50h] [rbp-B0h]
  int v19; // [rsp+54h] [rbp-ACh]
  int v20; // [rsp+58h] [rbp-A8h]
  _BYTE v21[96]; // [rsp+60h] [rbp-A0h] BYREF
  int v22; // [rsp+C0h] [rbp-40h]
  void **v23; // [rsp+D0h] [rbp-30h] BYREF
  int v24; // [rsp+D8h] [rbp-28h]

  v16[1] = v17;
  v17[0] = L"base\\fs\\fsrm\\utilities\\inc\\srmcputil.h";
  v17[1] = L"CSrmSink<class CFciPropertiesShellExt,&struct __s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::Subscribe";
  v17[2] = L"SRMCPUTH";
  v18 = 303;
  v19 = 17;
  v20 = 255;
  v22 = 0x1000000;
  memset_0(v21, 0, sizeof(v21));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v23, (const struct CSrmDebugInfo *)v17, 0);
  v16[0] = 0;
  v6 = (**a2)(a2, &GUID_b196b284_bab4_101a_b69c_00aa00341d07, v16);
  v24 = v6;
  if ( v6 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v23);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v23, Hr);
    v12 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v23);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v23, 0x136u, v12, 0);
  }
  v24 = v6;
  v15 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(*(_QWORD *)v16[0] + 32LL))(
         v16[0],
         &GUID_26942db0_dabf_41d8_bbdd_b129a9f70424,
         &v15);
  v24 = v7;
  if ( v7 < 0 )
  {
    v13 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v23);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v23, v13);
    v14 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v23);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v23, 0x138u, v14, 0);
  }
  v24 = v7;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v15 + 40LL))(v15, a1, a1 + 72);
  v24 = v8;
  if ( v8 < 0 )
  {
    v9 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v23);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v23, v9);
    v10 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v23);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v23, 0x139u, v10, 0);
  }
  v24 = v8;
  *(_QWORD *)(a1 + 64) = a3;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v16[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v16[0] + 16LL))(v16[0]);
  v23 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v23);
}

```

## disassembly

```asm
0x18000f4b0  mov     [rsp-8+arg_10], rbx
0x18000f4b5  push    rbp
0x18000f4b6  push    rsi
0x18000f4b7  push    rdi
0x18000f4b8  lea     rbp, [rsp-90h]
0x18000f4c0  sub     rsp, 190h
0x18000f4c7  mov     rax, cs:__security_cookie
0x18000f4ce  xor     rax, rsp
0x18000f4d1  mov     [rbp+0A0h+var_20], rax
0x18000f4d8  mov     rsi, r8
0x18000f4db  mov     rbx, rdx
0x18000f4de  mov     rdi, rcx
0x18000f4e1  lea     rax, [rsp+1A0h+var_168]
0x18000f4e6  mov     [rsp+1A0h+var_170], rax
0x18000f4eb  lea     rax, aBaseFsFsrmUtil_2; "base\\fs\\fsrm\\utilities\\inc\\srmcput"...
0x18000f4f2  mov     [rsp+1A0h+var_168], rax
0x18000f4f7  lea     rax, aCsrmsinkClassC; "CSrmSink<class CFciPropertiesShellExt,&"...
0x18000f4fe  mov     [rsp+1A0h+var_160], rax
0x18000f503  lea     rax, aSrmcputh; "SRMCPUTH"
0x18000f50a  mov     [rsp+1A0h+var_158], rax
0x18000f50f  mov     [rsp+1A0h+var_150], 12Fh
0x18000f517  mov     [rsp+1A0h+var_14C], 11h
0x18000f51f  mov     [rsp+1A0h+var_148], 0FFh
0x18000f527  mov     [rbp+0A0h+var_E0], 1000000h
0x18000f52e  xor     edx, edx; Val
0x18000f530  lea     r8d, [rdx+60h]; Size
0x18000f534  lea     rcx, [rsp+1A0h+var_140]; void *
0x18000f539  call    memset_0
0x18000f53e  nop
0x18000f53f  xor     r8d, r8d
0x18000f542  lea     rdx, [rsp+1A0h+var_168]
0x18000f547  lea     rcx, [rbp+0A0h+var_D0]
0x18000f54b  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18000f550  nop
0x18000f551  mov     [rsp+1A0h+var_178], 0
0x18000f55a  mov     rax, [rbx]
0x18000f55d  lea     r8, [rsp+1A0h+var_178]
0x18000f562  lea     rdx, _GUID_b196b284_bab4_101a_b69c_00aa00341d07
0x18000f569  mov     rcx, rbx
0x18000f56c  mov     rax, [rax]
0x18000f56f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f574  mov     [rbp+0A0h+var_C8], eax
0x18000f577  test    eax, eax
0x18000f579  js      loc_18000F672
0x18000f57f  mov     [rbp+0A0h+var_C8], eax
0x18000f582  mov     [rsp+1A0h+var_180], 0
0x18000f58b  mov     rcx, [rsp+1A0h+var_178]
0x18000f590  mov     rax, [rcx]
0x18000f593  lea     r8, [rsp+1A0h+var_180]
0x18000f598  lea     rdx, _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424
0x18000f59f  mov     rax, [rax+20h]
0x18000f5a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5a8  mov     [rbp+0A0h+var_C8], eax
0x18000f5ab  test    eax, eax
0x18000f5ad  js      loc_18000F6A4
0x18000f5b3  mov     [rbp+0A0h+var_C8], eax
0x18000f5b6  mov     rcx, [rsp+1A0h+var_180]
0x18000f5bb  mov     rax, [rcx]
0x18000f5be  lea     r8, [rdi+48h]
0x18000f5c2  mov     rdx, rdi
0x18000f5c5  mov     rax, [rax+28h]
0x18000f5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5ce  mov     [rbp+0A0h+var_C8], eax
0x18000f5d1  test    eax, eax
0x18000f5d3  js      short loc_18000F640
0x18000f5d5  mov     [rbp+0A0h+var_C8], eax
0x18000f5d8  mov     [rdi+40h], rsi
0x18000f5dc  mov     rcx, [rsp+1A0h+var_180]
0x18000f5e1  test    rcx, rcx
0x18000f5e4  jz      short loc_18000F5F3
0x18000f5e6  mov     rax, [rcx]
0x18000f5e9  mov     rax, [rax+10h]
0x18000f5ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5f2  nop
0x18000f5f3  mov     rcx, [rsp+1A0h+var_178]
0x18000f5f8  test    rcx, rcx
0x18000f5fb  jz      short loc_18000F60A
0x18000f5fd  mov     rax, [rcx]
0x18000f600  mov     rax, [rax+10h]
0x18000f604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f609  nop
0x18000f60a  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18000f611  mov     [rbp+0A0h+var_D0], rax
0x18000f615  lea     rcx, [rbp+0A0h+var_D0]; this
0x18000f619  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18000f61e  mov     rcx, [rbp+0A0h+var_20]
0x18000f625  xor     rcx, rsp; StackCookie
0x18000f628  call    __security_check_cookie
0x18000f62d  mov     rbx, [rsp+1A0h+arg_10]
0x18000f635  add     rsp, 190h
0x18000f63c  pop     rdi
0x18000f63d  pop     rsi
0x18000f63e  pop     rbp
0x18000f63f  retn
0x18000f640  lea     rcx, [rbp+0A0h+var_D0]; this
0x18000f644  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000f649  mov     edx, eax; int
0x18000f64b  lea     rcx, [rbp+0A0h+var_D0]; this
0x18000f64f  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000f654  lea     rcx, [rbp+0A0h+var_D0]; this
0x18000f658  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000f65d  mov     r8d, eax; char
0x18000f660  xor     r9d, r9d; unsigned __int16 *
0x18000f663  mov     edx, 139h; unsigned int
0x18000f668  lea     rcx, [rbp+0A0h+var_D0]; this
0x18000f66c  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18000f672  lea     rcx, [rbp+0A0h+var_D0]; this
0x18000f676  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000f67b  mov     edx, eax; int
0x18000f67d  lea     rcx, [rbp+0A0h+var_D0]; this
0x18000f681  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000f686  lea     rcx, [rbp+0A0h+var_D0]; this
0x18000f68a  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000f68f  mov     r8d, eax; char
0x18000f692  xor     r9d, r9d; unsigned __int16 *
0x18000f695  mov     edx, 136h; unsigned int
0x18000f69a  lea     rcx, [rbp+0A0h+var_D0]; this
0x18000f69e  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18000f6a4  lea     rcx, [rbp+0A0h+var_D0]; this
0x18000f6a8  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000f6ad  mov     edx, eax; int
0x18000f6af  lea     rcx, [rbp+0A0h+var_D0]; this
0x18000f6b3  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000f6b8  lea     rcx, [rbp+0A0h+var_D0]; this
0x18000f6bc  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000f6c1  mov     r8d, eax; char
0x18000f6c4  xor     r9d, r9d; unsigned __int16 *
0x18000f6c7  mov     edx, 138h; unsigned int
0x18000f6cc  lea     rcx, [rbp+0A0h+var_D0]; this
0x18000f6d0  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```

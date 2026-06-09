# CWdsTransportCollection::CreateInstance(_GUID const &,CWdsTransportCollection * *)

- ea: `0x180006de0`
- end: `0x180006f20`
- name: `?CreateInstance@CWdsTransportCollection@@SAJAEBU_GUID@@PEAPEAV1@@Z`
- size: `320`
- prototype: `__int64 __fastcall(const struct _GUID *, struct CWdsTransportCollection **)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000aa90`
- `0x180010710`
- `0x180012844`
- `0x180014e40`
- `0x180015ae0`
- `0x180019cb0`

## callees

- `0x180006cc4`
- `0x180006de0`
- `0x180007b14`
- `0x180020010`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180006e0e`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180006e65`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180006e97`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180006f01`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180006e0e`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180006e65`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180006e97`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180006f01`

## string_xrefs

- `0x180006df5`: `-> CWdsTransportCollection::CreateInstance`
- `0x180006eee`: `<- CWdsTransportCollection::CreateInstance=%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportCollection::CreateInstance(const struct _GUID *a1, struct _GUID **a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // r8
  struct _GUID *v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // r8
  struct _GUID *v12; // [rsp+48h] [rbp+10h] BYREF

  v12 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportCollection::CreateInstance");
  if ( a2 )
  {
    v5 = (unsigned int)ATL::CComObject<CWdsTransportCollection>::CreateInstance(&v12);
    if ( (int)ElValidateHr_0(v5, v6, v7, 380) < 0 )
    {
      v4 = v5;
      if ( (int)v5 < 0 && v12 )
        (*(void (__fastcall **)(struct _GUID *, __int64))(*(_QWORD *)&v12->Data1 + 80LL))(v12, 1);
    }
    else
    {
      v8 = v12;
      CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportCollection::Initialize(0x%p)", v12);
      v8[8] = *a1;
      CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportCollection::Initialize(0x%p) =%x", v8, 0);
      v4 = 0;
      if ( (int)ElValidateHr_0(0, v9, v10, 383) >= 0 )
      {
        (*(void (__fastcall **)(struct _GUID *))(*(_QWORD *)&v8->Data1 + 8LL))(v8);
        *a2 = v8;
      }
    }
  }
  else
  {
    v4 = -2147024809;
  }
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportCollection::CreateInstance=%x", v4);
  return v4;
}

```

## disassembly

```asm
0x180006de0  mov     [rsp+arg_0], rbx
0x180006de5  mov     [rsp+arg_10], rsi
0x180006dea  push    rdi
0x180006deb  sub     rsp, 30h
0x180006def  and     [rsp+38h+arg_8], 0
0x180006df5  lea     r8, aCwdstransportc_7; "-> CWdsTransportCollection::CreateInsta"...
0x180006dfc  mov     rsi, rdx
0x180006dff  mov     rbx, rcx
0x180006e02  mov     edx, 10000h
0x180006e07  lea     rcx, qword_18003B770
0x180006e0e  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180006e15  nop     dword ptr [rax+rax+00h]
0x180006e1a  test    rsi, rsi
0x180006e1d  jnz     short loc_180006E29
0x180006e1f  mov     ebx, 80070057h
0x180006e24  jmp     loc_180006EEB
0x180006e29  lea     rcx, [rsp+38h+arg_8]
0x180006e2e  call    ?CreateInstance@?$CComObject@VCWdsTransportCollection@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWdsTransportCollection>::CreateInstance(ATL::CComObject<CWdsTransportCollection> * *)
0x180006e33  mov     r9d, 17Ch
0x180006e39  mov     ecx, eax
0x180006e3b  mov     edi, eax
0x180006e3d  call    ElValidateHr_0
0x180006e42  test    eax, eax
0x180006e44  js      loc_180006ECA
0x180006e4a  mov     rdi, [rsp+38h+arg_8]
0x180006e4f  lea     r8, aCwdstransportc_19; "-> CWdsTransportCollection::Initialize("...
0x180006e56  mov     r9, rdi
0x180006e59  lea     rcx, qword_18003B770
0x180006e60  mov     edx, 10000h
0x180006e65  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180006e6c  nop     dword ptr [rax+rax+00h]
0x180006e71  movups  xmm0, xmmword ptr [rbx]
0x180006e74  and     [rsp+38h+var_18], 0
0x180006e79  lea     r8, aCwdstransportc_37; "<- CWdsTransportCollection::Initialize("...
0x180006e80  mov     r9, rdi
0x180006e83  lea     rcx, qword_18003B770
0x180006e8a  mov     edx, 10000h
0x180006e8f  movdqu  xmmword ptr [rdi+80h], xmm0
0x180006e97  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180006e9e  nop     dword ptr [rax+rax+00h]
0x180006ea3  xor     ecx, ecx
0x180006ea5  mov     r9d, 17Fh
0x180006eab  xor     ebx, ebx
0x180006ead  call    ElValidateHr_0
0x180006eb2  test    eax, eax
0x180006eb4  js      short loc_180006EEB
0x180006eb6  mov     rax, [rdi]
0x180006eb9  mov     rcx, rdi
0x180006ebc  mov     rax, [rax+8]
0x180006ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ec5  mov     [rsi], rdi
0x180006ec8  jmp     short loc_180006EEB
0x180006eca  mov     ebx, edi
0x180006ecc  test    edi, edi
0x180006ece  jns     short loc_180006EEB
0x180006ed0  mov     rcx, [rsp+38h+arg_8]
0x180006ed5  test    rcx, rcx
0x180006ed8  jz      short loc_180006EEB
0x180006eda  mov     rax, [rcx]
0x180006edd  mov     edx, 1
0x180006ee2  mov     rax, [rax+50h]
0x180006ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eeb  mov     r9d, ebx
0x180006eee  lea     r8, aCwdstransportc_27; "<- CWdsTransportCollection::CreateInsta"...
0x180006ef5  mov     edx, 10000h
0x180006efa  lea     rcx, qword_18003B770
0x180006f01  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180006f08  nop     dword ptr [rax+rax+00h]
0x180006f0d  mov     rsi, [rsp+38h+arg_10]
0x180006f12  mov     eax, ebx
0x180006f14  mov     rbx, [rsp+38h+arg_0]
0x180006f19  add     rsp, 30h
0x180006f1d  pop     rdi
0x180006f1e  retn
```

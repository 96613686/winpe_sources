# CClientSingleIdentity::CClientSingleIdentity(void)

- ea: `0x18001c1e0`
- end: `0x18001c372`
- name: `??0CClientSingleIdentity@@IEAA@XZ`
- size: `402`
- prototype: `CClientSingleIdentity *__fastcall(CClientSingleIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180021190`

## callees

- `0x18000a7a8`
- `0x18000a914`
- `0x18000c2ec`
- `0x18000c328`
- `0x18001c378`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c351`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c351`

## pseudocode

```c
CClientSingleIdentity *__fastcall CClientSingleIdentity::CClientSingleIdentity(CClientSingleIdentity *this)
{
  int v2; // edx
  int v3; // r8d
  int v4; // r9d
  __int64 v5; // rcx
  int v6; // edx
  int v7; // r8d
  int v8; // r9d
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  int v12; // edx
  int v13; // r8d
  int v14; // r9d

  *(_QWORD *)this = &CRefCounted::`vftable';
  *((_DWORD *)this + 2) = 1;
  CThreadProtected::CThreadProtected((CClientSingleIdentity *)((char *)this + 16));
  *(_QWORD *)this = &CClientSingleIdentity::`vftable';
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)this + 56);
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>(
    (_DWORD)this + 80,
    v2,
    v3,
    v4,
    (_DWORD)FLOAT_2_25);
  *(_QWORD *)(v5 + 72) = this;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 42) = -2147186688;
  *(_QWORD *)((char *)this + 172) = 0;
  *((_DWORD *)this + 45) = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)this + 184);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)this + 192);
  *((_DWORD *)this + 50) = 0;
  *(_QWORD *)((char *)this + 204) = 0;
  CIdcrlPropBag::CIdcrlPropBag((CClientSingleIdentity *)((char *)this + 216));
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>(
    (_DWORD)this + 296,
    v6,
    v7,
    v8,
    (_DWORD)FLOAT_2_25);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>(
    (_DWORD)this + 368,
    v9,
    v10,
    v11,
    (_DWORD)FLOAT_2_25);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>(
    (_DWORD)this + 440,
    v12,
    v13,
    v14,
    (_DWORD)FLOAT_2_25);
  *((_QWORD *)this + 64) = 0;
  *((_QWORD *)this + 65) = 0;
  *((_BYTE *)this + 528) = 0;
  ATL::CComAutoCriticalSection::CComAutoCriticalSection((CClientSingleIdentity *)((char *)this + 536));
  *((_QWORD *)this + 72) = 1;
  *((_QWORD *)this + 73) = 0;
  *((_QWORD *)this + 74) = 0;
  *((_QWORD *)this + 73) = CreateEventW(0, 1, 0, 0);
  return this;
}

```

## disassembly

```asm
0x18001c1e0  mov     [rsp+arg_10], rbx
0x18001c1e5  mov     [rsp+arg_0], rcx
0x18001c1ea  push    rdi
0x18001c1eb  sub     rsp, 40h
0x18001c1ef  movaps  [rsp+48h+var_18], xmm8
0x18001c1f5  mov     rbx, rcx
0x18001c1f8  lea     rax, ??_7CRefCounted@@6B@; const CRefCounted::`vftable'
0x18001c1ff  mov     [rcx], rax
0x18001c202  mov     dword ptr [rcx+8], 1
0x18001c209  add     rcx, 10h; this
0x18001c20d  call    ??0CThreadProtected@@QEAA@XZ; CThreadProtected::CThreadProtected(void)
0x18001c212  nop
0x18001c213  lea     rax, ??_7CClientSingleIdentity@@6B@; const CClientSingleIdentity::`vftable'
0x18001c21a  mov     [rbx], rax
0x18001c21d  lea     rcx, [rbx+38h]
0x18001c221  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18001c226  nop
0x18001c227  xor     edi, edi
0x18001c229  mov     [rbx+40h], rdi
0x18001c22d  mov     [rbx+48h], rdi
0x18001c231  lea     rcx, [rbx+50h]
0x18001c235  movss   xmm8, cs:__real@40100000
0x18001c23e  movss   [rsp+48h+var_28], xmm8
0x18001c245  movss   xmm3, cs:__real@3e800000
0x18001c24d  movss   xmm2, cs:__real@3f400000
0x18001c255  call    ??0?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(uint,float,float,float,uint)
0x18001c25a  mov     [rcx+48h], rbx
0x18001c25e  mov     [rbx+0A0h], rdi
0x18001c265  mov     dword ptr [rbx+0A8h], 80048800h
0x18001c26f  mov     [rbx+0ACh], rdi
0x18001c276  mov     [rbx+0B4h], edi
0x18001c27c  lea     rcx, [rbx+0B8h]
0x18001c283  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18001c288  nop
0x18001c289  lea     rcx, [rbx+0C0h]
0x18001c290  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18001c295  nop
0x18001c296  mov     [rbx+0C8h], edi
0x18001c29c  mov     [rbx+0CCh], rdi
0x18001c2a3  lea     rcx, [rbx+0D8h]; this
0x18001c2aa  call    ??0CIdcrlPropBag@@QEAA@XZ; CIdcrlPropBag::CIdcrlPropBag(void)
0x18001c2af  nop
0x18001c2b0  lea     rcx, [rbx+128h]
0x18001c2b7  movss   [rsp+48h+var_28], xmm8
0x18001c2be  movss   xmm3, cs:__real@3e800000
0x18001c2c6  movss   xmm2, cs:__real@3f400000
0x18001c2ce  call    ??0?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(uint,float,float,float,uint)
0x18001c2d3  nop
0x18001c2d4  lea     rcx, [rbx+170h]
0x18001c2db  movss   [rsp+48h+var_28], xmm8
0x18001c2e2  movss   xmm2, cs:__real@3f400000
0x18001c2ea  call    ??0?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(uint,float,float,float,uint)
0x18001c2ef  nop
0x18001c2f0  lea     rcx, [rbx+1B8h]
0x18001c2f7  movss   [rsp+48h+var_28], xmm8
0x18001c2fe  movss   xmm2, cs:__real@3f400000
0x18001c306  call    ??0?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(uint,float,float,float,uint)
0x18001c30b  nop
0x18001c30c  mov     [rbx+200h], rdi
0x18001c313  mov     [rbx+208h], rdi
0x18001c31a  mov     [rbx+210h], dil
0x18001c321  lea     rcx, [rbx+218h]; this
0x18001c328  call    ??0CComAutoCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoCriticalSection::CComAutoCriticalSection(void)
0x18001c32d  mov     qword ptr [rbx+240h], 1
0x18001c338  mov     [rbx+248h], rdi
0x18001c33f  mov     [rbx+250h], rdi
0x18001c346  xor     r9d, r9d; lpName
0x18001c349  xor     r8d, r8d; bInitialState
0x18001c34c  lea     edx, [rdi+1]; bManualReset
0x18001c34f  xor     ecx, ecx; lpEventAttributes
0x18001c351  call    cs:__imp_CreateEventW
0x18001c357  mov     [rbx+248h], rax
0x18001c35e  mov     rax, rbx
0x18001c361  mov     rbx, [rsp+48h+arg_10]
0x18001c366  movaps  xmm8, [rsp+48h+var_18]
0x18001c36c  add     rsp, 40h
0x18001c370  pop     rdi
0x18001c371  retn
```

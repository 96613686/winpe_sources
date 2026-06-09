# CClientSingleIdentity::~CClientSingleIdentity(void)

- ea: `0x18001c598`
- end: `0x18001c6c7`
- name: `??1CClientSingleIdentity@@MEAA@XZ`
- size: `303`
- prototype: `void __fastcall(CClientSingleIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001c9a0`

## callees

- `0x18000b0bc`
- `0x18000ba8c`
- `0x18000babc`
- `0x18000c538`
- `0x18001c598`
- `0x18001c8ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c61d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c6ac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c61d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c6ac`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c5cd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c5cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c5da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c5da`
- `CRYPT32!CertFreeCertificateContext` at `0x18001c5bb`
- `CRYPT32!CertFreeCertificateContext` at `0x18001c5bb`

## pseudocode

```c
void __fastcall CClientSingleIdentity::~CClientSingleIdentity(CClientSingleIdentity *this)
{
  const CERT_CONTEXT *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CClientSingleIdentity::`vftable';
  v2 = (const CERT_CONTEXT *)*((_QWORD *)this + 20);
  if ( v2 )
    CertFreeCertificateContext(v2);
  v3 = (void *)*((_QWORD *)this + 73);
  if ( v3 )
  {
    SetEvent(v3);
    CloseHandle(*((HANDLE *)this + 73));
  }
  if ( *((_DWORD *)this + 148) )
    *(_DWORD *)(RefWLIDHandle::operator->((char *)this + 64) + 32) = 1;
  if ( *((_DWORD *)this + 149) )
    *(_DWORD *)(RefWLIDHandle::operator->((char *)this + 64) + 36) = *((_DWORD *)this + 149);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll((char *)this + 440);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll((char *)this + 368);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll((char *)this + 296);
  *((_QWORD *)this + 27) = &CIdcrlPropBag::`vftable';
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll((char *)this + 224);
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 24) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 23) - 24LL));
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll((char *)this + 80);
  CAutoRefPtr<CAuthContext>::Deinit((char *)this + 72);
  CAutoRefPtr<SmartWLIDHandle>::Deinit((char *)this + 64);
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 7) - 24LL));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *(_QWORD *)this = &CRefCounted::`vftable';
}

```

## disassembly

```asm
0x18001c598  mov     [rsp+arg_0], rbx
0x18001c59d  push    rdi
0x18001c59e  sub     rsp, 20h
0x18001c5a2  mov     rbx, rcx
0x18001c5a5  lea     rax, ??_7CClientSingleIdentity@@6B@; const CClientSingleIdentity::`vftable'
0x18001c5ac  mov     [rcx], rax
0x18001c5af  mov     rcx, [rcx+0A0h]; pCertContext
0x18001c5b6  test    rcx, rcx
0x18001c5b9  jz      short loc_18001C5C1
0x18001c5bb  call    cs:__imp_CertFreeCertificateContext
0x18001c5c1  mov     rcx, [rbx+248h]; hEvent
0x18001c5c8  test    rcx, rcx
0x18001c5cb  jz      short loc_18001C5E0
0x18001c5cd  call    cs:__imp_SetEvent
0x18001c5d3  mov     rcx, [rbx+248h]; hObject
0x18001c5da  call    cs:__imp_CloseHandle
0x18001c5e0  lea     rdi, [rbx+40h]
0x18001c5e4  cmp     dword ptr [rbx+250h], 0
0x18001c5eb  jz      short loc_18001C5FC
0x18001c5ed  mov     rcx, rdi
0x18001c5f0  call    ??CRefWLIDHandle@@QEAAPEAVSmartWLIDHandle@@XZ; RefWLIDHandle::operator->(void)
0x18001c5f5  mov     dword ptr [rax+20h], 1
0x18001c5fc  cmp     dword ptr [rbx+254h], 0
0x18001c603  jz      short loc_18001C616
0x18001c605  mov     rcx, rdi
0x18001c608  call    ??CRefWLIDHandle@@QEAAPEAVSmartWLIDHandle@@XZ; RefWLIDHandle::operator->(void)
0x18001c60d  mov     ecx, [rbx+254h]
0x18001c613  mov     [rax+24h], ecx
0x18001c616  lea     rcx, [rbx+218h]; lpCriticalSection
0x18001c61d  call    cs:__imp_DeleteCriticalSection
0x18001c623  lea     rcx, [rbx+1B8h]
0x18001c62a  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x18001c62f  lea     rcx, [rbx+170h]
0x18001c636  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x18001c63b  lea     rcx, [rbx+128h]
0x18001c642  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x18001c647  lea     rax, ??_7CIdcrlPropBag@@6B@; const CIdcrlPropBag::`vftable'
0x18001c64e  mov     [rbx+0D8h], rax
0x18001c655  lea     rcx, [rbx+0E0h]
0x18001c65c  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x18001c661  mov     rcx, [rbx+0C0h]
0x18001c668  sub     rcx, 18h; this
0x18001c66c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001c671  mov     rcx, [rbx+0B8h]
0x18001c678  sub     rcx, 18h; this
0x18001c67c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001c681  lea     rcx, [rbx+50h]
0x18001c685  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x18001c68a  lea     rcx, [rbx+48h]
0x18001c68e  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
0x18001c693  mov     rcx, rdi
0x18001c696  call    ?Deinit@?$CAutoRefPtr@VSmartWLIDHandle@@@@IEAAXXZ; CAutoRefPtr<SmartWLIDHandle>::Deinit(void)
0x18001c69b  mov     rcx, [rbx+38h]
0x18001c69f  sub     rcx, 18h; this
0x18001c6a3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001c6a8  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001c6ac  call    cs:__imp_DeleteCriticalSection
0x18001c6b2  lea     rax, ??_7CRefCounted@@6B@; const CRefCounted::`vftable'
0x18001c6b9  mov     [rbx], rax
0x18001c6bc  mov     rbx, [rsp+28h+arg_0]
0x18001c6c1  add     rsp, 20h
0x18001c6c5  pop     rdi
0x18001c6c6  retn
```

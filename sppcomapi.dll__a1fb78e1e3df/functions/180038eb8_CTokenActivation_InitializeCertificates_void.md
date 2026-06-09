# CTokenActivation::InitializeCertificates(void)

- ea: `0x180038eb8`
- end: `0x180038f87`
- name: `?InitializeCertificates@CTokenActivation@@IEAAJXZ`
- size: `207`
- prototype: `__int64 __fastcall(CTokenActivation *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003a800`

## callees

- `0x180003520`
- `0x180004288`
- `0x180038028`
- `0x180038eb8`

## import_xrefs

- `sppcext!SLGetTokenActivationGrants` at `0x180038efd`
- `sppcext!SLGetTokenActivationGrants` at `0x180038efd`
- `sppcext!SLFreeTokenActivationCertificates` at `0x180038f32`
- `sppcext!SLFreeTokenActivationCertificates` at `0x180038f32`
- `sppcext!SLGetTokenActivationCertificates` at `0x180038f58`
- `sppcext!SLGetTokenActivationCertificates` at `0x180038f58`
- `sppcext!SLFreeTokenActivationGrants` at `0x180038ed9`
- `sppcext!SLFreeTokenActivationGrants` at `0x180038ed9`

## pseudocode

```c
__int64 __fastcall CTokenActivation::InitializeCertificates(CTokenActivation *this)
{
  _QWORD *v1; // rsi
  int SmartCardCertificates; // eax
  unsigned int v4; // ebx

  v1 = (_QWORD *)((char *)this + 232);
  if ( *((_QWORD *)this + 29) )
  {
    SLFreeTokenActivationGrants();
    *v1 = 0;
  }
  SmartCardCertificates = SLGetTokenActivationGrants(*((_QWORD *)this + 24), (char *)this + 200, v1);
  v4 = SmartCardCertificates;
  if ( SmartCardCertificates < 0
    || (SmartCardCertificates = CTokenActivation::GetSmartCardCertificates(this),
        v4 = SmartCardCertificates,
        SmartCardCertificates < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)SmartCardCertificates);
  }
  else
  {
    if ( *((_QWORD *)this + 27) )
    {
      SLFreeTokenActivationCertificates();
      *((_QWORD *)this + 27) = 0;
    }
    SLGetTokenActivationCertificates(*v1, 2, (char *)this + 216);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v4 = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  return v4;
}

```

## disassembly

```asm
0x180038eb8  mov     [rsp+arg_0], rbx
0x180038ebd  mov     [rsp+arg_8], rsi
0x180038ec2  push    rdi
0x180038ec3  sub     rsp, 20h
0x180038ec7  lea     rsi, [rcx+0E8h]
0x180038ece  mov     rdi, rcx
0x180038ed1  mov     rcx, [rsi]
0x180038ed4  test    rcx, rcx
0x180038ed7  jz      short loc_180038EEC
0x180038ed9  call    cs:__imp_SLFreeTokenActivationGrants
0x180038ee0  nop     dword ptr [rax+rax+00h]
0x180038ee5  mov     qword ptr [rsi], 0
0x180038eec  mov     rcx, [rdi+0C0h]
0x180038ef3  lea     rdx, [rdi+0C8h]
0x180038efa  mov     r8, rsi
0x180038efd  call    cs:__imp_SLGetTokenActivationGrants
0x180038f04  nop     dword ptr [rax+rax+00h]
0x180038f09  mov     ebx, eax
0x180038f0b  test    eax, eax
0x180038f0d  jns     short loc_180038F18
0x180038f0f  mov     ecx, eax
0x180038f11  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180038f16  jmp     short loc_180038F6D
0x180038f18  mov     rcx, rdi; this
0x180038f1b  call    ?GetSmartCardCertificates@CTokenActivation@@IEAAJXZ; CTokenActivation::GetSmartCardCertificates(void)
0x180038f20  mov     ebx, eax
0x180038f22  test    eax, eax
0x180038f24  js      short loc_180038F0F
0x180038f26  mov     rcx, [rdi+0D8h]
0x180038f2d  test    rcx, rcx
0x180038f30  jz      short loc_180038F49
0x180038f32  call    cs:__imp_SLFreeTokenActivationCertificates
0x180038f39  nop     dword ptr [rax+rax+00h]
0x180038f3e  mov     qword ptr [rdi+0D8h], 0
0x180038f49  mov     rcx, [rsi]
0x180038f4c  lea     r8, [rdi+0D8h]
0x180038f53  mov     edx, 2
0x180038f58  call    cs:__imp_SLGetTokenActivationCertificates
0x180038f5f  nop     dword ptr [rax+rax+00h]
0x180038f64  xor     ecx, ecx
0x180038f66  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180038f6b  xor     ebx, ebx
0x180038f6d  mov     ecx, ebx
0x180038f6f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180038f74  mov     rsi, [rsp+28h+arg_8]
0x180038f79  mov     eax, ebx
0x180038f7b  mov     rbx, [rsp+28h+arg_0]
0x180038f80  add     rsp, 20h
0x180038f84  pop     rdi
0x180038f85  retn
```

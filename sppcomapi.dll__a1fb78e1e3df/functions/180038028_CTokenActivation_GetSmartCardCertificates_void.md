# CTokenActivation::GetSmartCardCertificates(void)

- ea: `0x180038028`
- end: `0x180038087`
- name: `?GetSmartCardCertificates@CTokenActivation@@IEAAJXZ`
- size: `95`
- prototype: `__int64 __fastcall(CTokenActivation *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180038eb8`
- `0x180039398`
- `0x18003a800`

## callees

- `0x180004288`
- `0x180038028`

## import_xrefs

- `sppcext!SLFreeTokenActivationCertificates` at `0x180038044`
- `sppcext!SLFreeTokenActivationCertificates` at `0x180038044`
- `sppcext!SLGetTokenActivationCertificates` at `0x180038066`
- `sppcext!SLGetTokenActivationCertificates` at `0x180038066`

## pseudocode

```c
__int64 __fastcall CTokenActivation::GetSmartCardCertificates(CTokenActivation *this)
{
  _QWORD *v1; // rbx

  v1 = (_QWORD *)((char *)this + 224);
  if ( *((_QWORD *)this + 28) )
  {
    SLFreeTokenActivationCertificates();
    *v1 = 0;
  }
  SLGetTokenActivationCertificates(*((_QWORD *)this + 29), 1, v1);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  return 0;
}

```

## disassembly

```asm
0x180038028  mov     [rsp+arg_0], rbx
0x18003802d  push    rdi
0x18003802e  sub     rsp, 20h
0x180038032  lea     rbx, [rcx+0E0h]
0x180038039  mov     rdi, rcx
0x18003803c  mov     rcx, [rbx]
0x18003803f  test    rcx, rcx
0x180038042  jz      short loc_180038057
0x180038044  call    cs:__imp_SLFreeTokenActivationCertificates
0x18003804b  nop     dword ptr [rax+rax+00h]
0x180038050  mov     qword ptr [rbx], 0
0x180038057  mov     rcx, [rdi+0E8h]
0x18003805e  mov     r8, rbx
0x180038061  mov     edx, 1
0x180038066  call    cs:__imp_SLGetTokenActivationCertificates
0x18003806d  nop     dword ptr [rax+rax+00h]
0x180038072  xor     ecx, ecx
0x180038074  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180038079  mov     rbx, [rsp+28h+arg_0]
0x18003807e  xor     eax, eax
0x180038080  add     rsp, 20h
0x180038084  pop     rdi
0x180038085  retn
```

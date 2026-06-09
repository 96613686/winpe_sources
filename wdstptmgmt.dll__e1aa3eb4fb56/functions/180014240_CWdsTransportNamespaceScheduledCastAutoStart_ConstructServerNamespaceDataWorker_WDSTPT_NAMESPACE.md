# CWdsTransportNamespaceScheduledCastAutoStart::ConstructServerNamespaceDataWorker(_WDSTPT_NAMESPACE *)

- ea: `0x180014240`
- end: `0x180014324`
- name: `?ConstructServerNamespaceDataWorker@CWdsTransportNamespaceScheduledCastAutoStart@@EEAAJPEAU_WDSTPT_NAMESPACE@@@Z`
- size: `228`
- prototype: `__int64 __fastcall(CWdsTransportNamespaceScheduledCastAutoStart *__hidden this, struct _WDSTPT_NAMESPACE *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180014240`

## import_xrefs

- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1800142c8`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1800142c8`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001427c`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800142fa`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001427c`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800142fa`

## string_xrefs

- `0x180014269`: `-> CWdsTransportNamespaceScheduledCastAutoStart::ConstructServerNamespaceDataWorker(0x%p)`
- `0x1800142e7`: `<- CWdsTransportNamespaceScheduledCastAutoStart::ConstructServerNamespaceDataWorker(0x%p) =%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWdsTransportNamespaceScheduledCastAutoStart::ConstructServerNamespaceDataWorker(
        CWdsTransportNamespaceScheduledCastAutoStart *this,
        struct _WDSTPT_NAMESPACE *a2)
{
  unsigned int v4; // ebx
  unsigned int v6; // [rsp+20h] [rbp-28h]
  _BYTE v7[24]; // [rsp+30h] [rbp-18h] BYREF

  v4 = 0;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v7, (char *)this + 64);
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportNamespaceScheduledCastAutoStart::ConstructServerNamespaceDataWorker(0x%p)",
    this);
  if ( *((_DWORD *)this + 56) )
  {
    *((_DWORD *)a2 + 2) = 2;
    *((_DWORD *)a2 + 20) = 2;
    *((_DWORD *)a2 + 21) = *((_DWORD *)this + 56);
    *((_DWORD *)a2 + 22) = *((_DWORD *)this + 57);
    if ( (*((_BYTE *)this + 224) & 2) != 0
      && !VariantTimeToSystemTime(*((DOUBLE *)this + 29), (LPSYSTEMTIME)((char *)a2 + 92)) )
    {
      v4 = -1055915763;
    }
  }
  else
  {
    v4 = -1055915758;
  }
  v6 = v4;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportNamespaceScheduledCastAutoStart::ConstructServerNamespaceDataWorker(0x%p) =%x",
    this,
    v6);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v7);
  return v4;
}

```

## disassembly

```asm
0x180014240  mov     [rsp+arg_0], rbx
0x180014245  mov     [rsp+arg_8], rsi
0x18001424a  push    rdi
0x18001424b  sub     rsp, 40h
0x18001424f  mov     rsi, rdx
0x180014252  mov     rdi, rcx
0x180014255  xor     ebx, ebx
0x180014257  lea     rdx, [rcx+40h]
0x18001425b  lea     rcx, [rsp+48h+var_18]
0x180014260  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x180014265  nop
0x180014266  mov     r9, rdi
0x180014269  lea     r8, aCwdstransportn; "-> CWdsTransportNamespaceScheduledCastA"...
0x180014270  mov     edx, 10000h
0x180014275  lea     rcx, qword_18003B770
0x18001427c  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180014283  nop     dword ptr [rax+rax+00h]
0x180014288  cmp     [rdi+0E0h], ebx
0x18001428e  jnz     short loc_180014297
0x180014290  mov     ebx, 0C1100112h
0x180014295  jmp     short loc_1800142E0
0x180014297  mov     ecx, 2
0x18001429c  mov     [rsi+8], ecx
0x18001429f  mov     [rsi+50h], ecx
0x1800142a2  mov     eax, [rdi+0E0h]
0x1800142a8  mov     [rsi+54h], eax
0x1800142ab  mov     eax, [rdi+0E4h]
0x1800142b1  mov     [rsi+58h], eax
0x1800142b4  test    [rdi+0E0h], cl
0x1800142ba  jz      short loc_1800142E0
0x1800142bc  lea     rdx, [rsi+5Ch]; lpSystemTime
0x1800142c0  movsd   xmm0, qword ptr [rdi+0E8h]; vtime
0x1800142c8  call    cs:__imp_VariantTimeToSystemTime
0x1800142cf  nop     dword ptr [rax+rax+00h]
0x1800142d4  mov     r8d, 0C110010Dh
0x1800142da  test    eax, eax
0x1800142dc  cmovz   ebx, r8d
0x1800142e0  mov     [rsp+48h+var_28], ebx
0x1800142e4  mov     r9, rdi
0x1800142e7  lea     r8, aCwdstransportn_8; "<- CWdsTransportNamespaceScheduledCastA"...
0x1800142ee  mov     edx, 10000h
0x1800142f3  lea     rcx, qword_18003B770
0x1800142fa  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180014301  nop     dword ptr [rax+rax+00h]
0x180014306  nop
0x180014307  lea     rcx, [rsp+48h+var_18]
0x18001430c  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180014311  mov     eax, ebx
0x180014313  mov     rbx, [rsp+48h+arg_0]
0x180014318  mov     rsi, [rsp+48h+arg_8]
0x18001431d  add     rsp, 40h
0x180014321  pop     rdi
0x180014322  retn
```

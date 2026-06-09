# SlbNatIpsSetInterfaceContext

- ea: `0x140034550`
- end: `0x140034632`
- name: `SlbNatIpsSetInterfaceContext`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14000820c`
- `0x140014f60`

## callees

- `0x14001ef70`
- `0x14002d400`
- `0x14002d450`
- `0x140033204`
- `0x140034550`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14003461a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14003461a`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x140034581`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x140034581`

## pseudocode

```c
void __fastcall SlbNatIpsSetInterfaceContext(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // edi
  __int64 v7; // r8

  if ( (*(_DWORD *)(a1 + 24) & 1) == 0
    && BYTE2(SlbNatIpsIpv4Provider)
    && ExAcquireRundownProtectionCacheAwareEx(*((PEX_RUNDOWN_REF_CACHE_AWARE *)&SlbNatIpsIpv4Provider + 1), 1u) )
  {
    if ( (xmmword_1400262E0 & 4) != 0 )
      WPP_SF_qd(v2, 10, v3, a1, *(_DWORD *)(a1 + 28));
    v6 = (*((__int64 (__fastcall **)(PVOID, __int64, _QWORD, __int64))*(&ProviderBindingContext + 1) + 3))(
           ProviderBindingContext,
           1,
           *(unsigned int *)(a1 + 28),
           a1);
    if ( v6 < 0 )
    {
      if ( (xmmword_1400262D0 & 4) != 0 )
        WPP_SF_qdd(v5, v4, v7, a1, *(_DWORD *)(a1 + 28), v6);
      SlbNatInsertErrorEntry(*(unsigned int *)(a1 + 28), (unsigned int)v6, L"SlbNatIpsSetInterfaceContext");
    }
    else
    {
      *(_DWORD *)(a1 + 24) |= 1u;
    }
    ExReleaseRundownProtectionCacheAwareEx(*((PEX_RUNDOWN_REF_CACHE_AWARE *)&SlbNatIpsIpv4Provider + 1), 1u);
  }
}

```

## disassembly

```asm
0x140034550  mov     [rsp+arg_0], rbx
0x140034555  push    rdi
0x140034556  sub     rsp, 30h
0x14003455a  mov     eax, [rcx+18h]
0x14003455d  mov     rbx, rcx
0x140034560  test    al, 1
0x140034562  jnz     loc_140034626
0x140034568  cmp     byte ptr cs:SlbNatIpsIpv4Provider+2, 0
0x14003456f  jz      loc_140034626
0x140034575  mov     rcx, qword ptr cs:SlbNatIpsIpv4Provider+8; RunRefCacheAware
0x14003457c  mov     edx, 1; Count
0x140034581  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x140034588  nop     dword ptr [rax+rax+00h]
0x14003458d  test    al, al
0x14003458f  jz      loc_140034626
0x140034595  test    byte ptr cs:xmmword_1400262E0, 4
0x14003459c  jz      short loc_1400345B2
0x14003459e  mov     eax, [rbx+1Ch]
0x1400345a1  mov     edx, 0Ah
0x1400345a6  mov     r9, rbx
0x1400345a9  mov     [rsp+38h+var_18], eax
0x1400345ad  call    WPP_SF_qd
0x1400345b2  mov     rax, qword ptr cs:ProviderBindingContext+8
0x1400345b9  mov     r9, rbx
0x1400345bc  mov     r8d, [rbx+1Ch]
0x1400345c0  mov     edx, 1
0x1400345c5  mov     rcx, qword ptr cs:ProviderBindingContext
0x1400345cc  mov     rax, [rax+18h]
0x1400345d0  call    _guard_dispatch_icall
0x1400345d5  mov     edi, eax
0x1400345d7  test    eax, eax
0x1400345d9  js      short loc_1400345E1
0x1400345db  or      dword ptr [rbx+18h], 1
0x1400345df  jmp     short loc_14003460E
0x1400345e1  test    byte ptr cs:xmmword_1400262D0, 4
0x1400345e8  jz      short loc_1400345FD
0x1400345ea  mov     eax, [rbx+1Ch]
0x1400345ed  mov     r9, rbx
0x1400345f0  mov     [rsp+38h+var_10], edi
0x1400345f4  mov     [rsp+38h+var_18], eax
0x1400345f8  call    WPP_SF_qdd
0x1400345fd  mov     ecx, [rbx+1Ch]
0x140034600  lea     r8, aSlbnatipssetin; "SlbNatIpsSetInterfaceContext"
0x140034607  mov     edx, edi
0x140034609  call    SlbNatInsertErrorEntry
0x14003460e  mov     rcx, qword ptr cs:SlbNatIpsIpv4Provider+8; RunRef
0x140034615  mov     edx, 1; Count
0x14003461a  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x140034621  nop     dword ptr [rax+rax+00h]
0x140034626  mov     rbx, [rsp+38h+arg_0]
0x14003462b  add     rsp, 30h
0x14003462f  pop     rdi
0x140034630  retn
```

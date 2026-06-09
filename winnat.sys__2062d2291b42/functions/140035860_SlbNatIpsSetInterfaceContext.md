# SlbNatIpsSetInterfaceContext

- ea: `0x140035860`
- end: `0x140035942`
- name: `SlbNatIpsSetInterfaceContext`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14000820c`
- `0x1400158dc`

## callees

- `0x14001f4b0`
- `0x14002e400`
- `0x14002e450`
- `0x140034334`
- `0x140035860`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14003592a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14003592a`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x140035891`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x140035891`

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
    if ( (xmmword_1400272E0 & 4) != 0 )
      WPP_SF_qd(v2, 10, v3, a1, *(_DWORD *)(a1 + 28));
    v6 = (*((__int64 (__fastcall **)(PVOID, __int64, _QWORD, __int64))*(&ProviderBindingContext + 1) + 3))(
           ProviderBindingContext,
           1,
           *(unsigned int *)(a1 + 28),
           a1);
    if ( v6 < 0 )
    {
      if ( (xmmword_1400272D0 & 4) != 0 )
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
0x140035860  mov     [rsp+arg_0], rbx
0x140035865  push    rdi
0x140035866  sub     rsp, 30h
0x14003586a  mov     eax, [rcx+18h]
0x14003586d  mov     rbx, rcx
0x140035870  test    al, 1
0x140035872  jnz     loc_140035936
0x140035878  cmp     byte ptr cs:SlbNatIpsIpv4Provider+2, 0
0x14003587f  jz      loc_140035936
0x140035885  mov     rcx, qword ptr cs:SlbNatIpsIpv4Provider+8; RunRefCacheAware
0x14003588c  mov     edx, 1; Count
0x140035891  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x140035898  nop     dword ptr [rax+rax+00h]
0x14003589d  test    al, al
0x14003589f  jz      loc_140035936
0x1400358a5  test    byte ptr cs:xmmword_1400272E0, 4
0x1400358ac  jz      short loc_1400358C2
0x1400358ae  mov     eax, [rbx+1Ch]
0x1400358b1  mov     edx, 0Ah
0x1400358b6  mov     r9, rbx
0x1400358b9  mov     [rsp+38h+var_18], eax
0x1400358bd  call    WPP_SF_qd
0x1400358c2  mov     rax, qword ptr cs:ProviderBindingContext+8
0x1400358c9  mov     r9, rbx
0x1400358cc  mov     r8d, [rbx+1Ch]
0x1400358d0  mov     edx, 1
0x1400358d5  mov     rcx, qword ptr cs:ProviderBindingContext
0x1400358dc  mov     rax, [rax+18h]
0x1400358e0  call    _guard_dispatch_icall
0x1400358e5  mov     edi, eax
0x1400358e7  test    eax, eax
0x1400358e9  js      short loc_1400358F1
0x1400358eb  or      dword ptr [rbx+18h], 1
0x1400358ef  jmp     short loc_14003591E
0x1400358f1  test    byte ptr cs:xmmword_1400272D0, 4
0x1400358f8  jz      short loc_14003590D
0x1400358fa  mov     eax, [rbx+1Ch]
0x1400358fd  mov     r9, rbx
0x140035900  mov     [rsp+38h+var_10], edi
0x140035904  mov     [rsp+38h+var_18], eax
0x140035908  call    WPP_SF_qdd
0x14003590d  mov     ecx, [rbx+1Ch]
0x140035910  lea     r8, aSlbnatipssetin; "SlbNatIpsSetInterfaceContext"
0x140035917  mov     edx, edi
0x140035919  call    SlbNatInsertErrorEntry
0x14003591e  mov     rcx, qword ptr cs:SlbNatIpsIpv4Provider+8; RunRef
0x140035925  mov     edx, 1; Count
0x14003592a  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x140035931  nop     dword ptr [rax+rax+00h]
0x140035936  mov     rbx, [rsp+38h+arg_0]
0x14003593b  add     rsp, 30h
0x14003593f  pop     rdi
0x140035940  retn
```

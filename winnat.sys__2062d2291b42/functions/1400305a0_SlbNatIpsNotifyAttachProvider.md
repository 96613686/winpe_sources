# SlbNatIpsNotifyAttachProvider

- ea: `0x1400305a0`
- end: `0x14003069a`
- name: `SlbNatIpsNotifyAttachProvider`
- size: `250`
- prototype: `__int64 __fastcall(HANDLE NmrBindingHandle)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000caa0`
- `0x1400305a0`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14003067e`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14003067e`
- `NETIO!NmrClientAttachProvider` at `0x140030660`
- `NETIO!NmrClientAttachProvider` at `0x140030660`

## pseudocode

```c
NTSTATUS __fastcall SlbNatIpsNotifyAttachProvider(HANDLE NmrBindingHandle, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  __int64 v5; // rdx
  int v6; // eax
  bool v7; // zf
  NTSTATUS result; // eax

  v3 = *(_QWORD *)(a3 + 32);
  if ( !v3 )
    return -1073741127;
  if ( *(_WORD *)(v3 + 4) != 2 )
    return -1073741127;
  v5 = *(_QWORD *)(a3 + 16);
  v6 = *(_DWORD *)(v5 + 4);
  if ( v6 != NPI_MS_IPV4_MODULEID.Type )
    return -1073741127;
  if ( v6 == 1 )
  {
    if ( *(_DWORD *)(v5 + 8) != NPI_MS_IPV4_MODULEID.Guid.Data1
      || *(_QWORD *)(v5 + 12) != *(_QWORD *)&NPI_MS_IPV4_MODULEID.IfLuid.HighPart )
    {
      return -1073741127;
    }
    v7 = *(_DWORD *)(v5 + 20) == *((_DWORD *)&NPI_MS_IPV4_MODULEID.IfLuid + 3);
  }
  else
  {
    if ( v6 != 2 )
      return -1073741127;
    v7 = *(_QWORD *)(v5 + 8) == *(_QWORD *)&NPI_MS_IPV4_MODULEID.Guid.Data1;
  }
  if ( !v7 )
    return -1073741127;
  if ( BYTE2(SlbNatIpsIpv4Provider) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(2, v5, a3);
  *(_QWORD *)&xmmword_140027A40 = NmrBindingHandle;
  result = NmrClientAttachProvider(
             NmrBindingHandle,
             &SlbNatIpsIpv4Provider,
             &SlbNatIpsClientDispatch,
             &ProviderBindingContext,
             (const void **)&ProviderBindingContext + 1);
  if ( result >= 0 )
  {
    BYTE2(SlbNatIpsIpv4Provider) = 1;
    ExReInitializeRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)&SlbNatIpsIpv4Provider + 1));
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400305a0  push    rbx
0x1400305a2  sub     rsp, 30h
0x1400305a6  mov     rax, [r8+20h]
0x1400305aa  mov     rbx, rcx
0x1400305ad  test    rax, rax
0x1400305b0  jz      loc_14003068E
0x1400305b6  mov     ecx, 2
0x1400305bb  cmp     [rax+4], cx
0x1400305bf  jnz     loc_14003068E
0x1400305c5  mov     rdx, [r8+10h]
0x1400305c9  mov     eax, [rdx+4]
0x1400305cc  cmp     eax, cs:NPI_MS_IPV4_MODULEID.Type
0x1400305d2  jnz     loc_14003068E
0x1400305d8  cmp     eax, 1
0x1400305db  jnz     short loc_140030616
0x1400305dd  mov     rax, qword ptr cs:NPI_MS_IPV4_MODULEID.8
0x1400305e4  cmp     [rdx+8], eax
0x1400305e7  jnz     loc_14003068E
0x1400305ed  mov     eax, dword ptr cs:NPI_MS_IPV4_MODULEID.8+4
0x1400305f3  cmp     [rdx+0Ch], eax
0x1400305f6  jnz     loc_14003068E
0x1400305fc  mov     eax, dword ptr cs:NPI_MS_IPV4_MODULEID.8+8
0x140030602  cmp     [rdx+10h], eax
0x140030605  jnz     loc_14003068E
0x14003060b  mov     eax, dword ptr cs:NPI_MS_IPV4_MODULEID.8+0Ch
0x140030611  cmp     [rdx+14h], eax
0x140030614  jmp     short loc_140030625
0x140030616  cmp     eax, ecx
0x140030618  jnz     short loc_14003068E
0x14003061a  mov     rax, [rdx+8]
0x14003061e  cmp     rax, qword ptr cs:NPI_MS_IPV4_MODULEID.8
0x140030625  jnz     short loc_14003068E
0x140030627  cmp     byte ptr cs:SlbNatIpsIpv4Provider+2, 0
0x14003062e  jz      short loc_140030635
0x140030630  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140030635  lea     rax, ProviderBindingContext+8
0x14003063c  mov     qword ptr cs:xmmword_140027A40, rbx
0x140030643  lea     r9, ProviderBindingContext; ProviderBindingContext
0x14003064a  mov     [rsp+38h+ProviderDispatch], rax; ProviderDispatch
0x14003064f  lea     r8, SlbNatIpsClientDispatch; ClientDispatch
0x140030656  mov     rcx, rbx; NmrBindingHandle
0x140030659  lea     rdx, SlbNatIpsIpv4Provider; ClientBindingContext
0x140030660  call    cs:__imp_NmrClientAttachProvider
0x140030667  nop     dword ptr [rax+rax+00h]
0x14003066c  test    eax, eax
0x14003066e  js      short loc_140030693
0x140030670  mov     rcx, qword ptr cs:SlbNatIpsIpv4Provider+8; RunRefCacheAware
0x140030677  mov     byte ptr cs:SlbNatIpsIpv4Provider+2, 1
0x14003067e  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x140030685  nop     dword ptr [rax+rax+00h]
0x14003068a  xor     eax, eax
0x14003068c  jmp     short loc_140030693
0x14003068e  mov     eax, 0C00002B9h
0x140030693  add     rsp, 30h
0x140030697  pop     rbx
0x140030698  retn
```

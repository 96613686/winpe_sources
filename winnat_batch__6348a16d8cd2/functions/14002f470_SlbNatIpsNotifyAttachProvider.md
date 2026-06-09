# SlbNatIpsNotifyAttachProvider

- ea: `0x14002f470`
- end: `0x14002f56a`
- name: `SlbNatIpsNotifyAttachProvider`
- size: `250`
- prototype: `__int64 __fastcall(HANDLE NmrBindingHandle)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000caa0`
- `0x14002f470`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14002f54e`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14002f54e`
- `NETIO!NmrClientAttachProvider` at `0x14002f530`
- `NETIO!NmrClientAttachProvider` at `0x14002f530`

## pseudocode

```c
NTSTATUS __fastcall SlbNatIpsNotifyAttachProvider(HANDLE NmrBindingHandle, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 v6; // rdx
  int v7; // eax
  bool v8; // zf
  NTSTATUS result; // eax

  v4 = *(_QWORD *)(a3 + 32);
  if ( !v4 )
    return -1073741127;
  if ( *(_WORD *)(v4 + 4) != 2 )
    return -1073741127;
  v6 = *(_QWORD *)(a3 + 16);
  v7 = *(_DWORD *)(v6 + 4);
  if ( v7 != NPI_MS_IPV4_MODULEID.Type )
    return -1073741127;
  if ( v7 == 1 )
  {
    if ( *(_DWORD *)(v6 + 8) != NPI_MS_IPV4_MODULEID.Guid.Data1
      || *(_QWORD *)(v6 + 12) != *(_QWORD *)&NPI_MS_IPV4_MODULEID.IfLuid.HighPart )
    {
      return -1073741127;
    }
    v8 = *(_DWORD *)(v6 + 20) == *((_DWORD *)&NPI_MS_IPV4_MODULEID.IfLuid + 3);
  }
  else
  {
    if ( v7 != 2 )
      return -1073741127;
    v8 = *(_QWORD *)(v6 + 8) == *(_QWORD *)&NPI_MS_IPV4_MODULEID.Guid.Data1;
  }
  if ( !v8 )
    return -1073741127;
  if ( BYTE2(SlbNatIpsIpv4Provider) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(2, v6, a3, a4);
  *(_QWORD *)&xmmword_140026A40 = NmrBindingHandle;
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
0x14002f470  push    rbx
0x14002f472  sub     rsp, 30h
0x14002f476  mov     rax, [r8+20h]
0x14002f47a  mov     rbx, rcx
0x14002f47d  test    rax, rax
0x14002f480  jz      loc_14002F55E
0x14002f486  mov     ecx, 2
0x14002f48b  cmp     [rax+4], cx
0x14002f48f  jnz     loc_14002F55E
0x14002f495  mov     rdx, [r8+10h]
0x14002f499  mov     eax, [rdx+4]
0x14002f49c  cmp     eax, cs:NPI_MS_IPV4_MODULEID.Type
0x14002f4a2  jnz     loc_14002F55E
0x14002f4a8  cmp     eax, 1
0x14002f4ab  jnz     short loc_14002F4E6
0x14002f4ad  mov     rax, qword ptr cs:NPI_MS_IPV4_MODULEID.8
0x14002f4b4  cmp     [rdx+8], eax
0x14002f4b7  jnz     loc_14002F55E
0x14002f4bd  mov     eax, dword ptr cs:NPI_MS_IPV4_MODULEID.8+4
0x14002f4c3  cmp     [rdx+0Ch], eax
0x14002f4c6  jnz     loc_14002F55E
0x14002f4cc  mov     eax, dword ptr cs:NPI_MS_IPV4_MODULEID.8+8
0x14002f4d2  cmp     [rdx+10h], eax
0x14002f4d5  jnz     loc_14002F55E
0x14002f4db  mov     eax, dword ptr cs:NPI_MS_IPV4_MODULEID.8+0Ch
0x14002f4e1  cmp     [rdx+14h], eax
0x14002f4e4  jmp     short loc_14002F4F5
0x14002f4e6  cmp     eax, ecx
0x14002f4e8  jnz     short loc_14002F55E
0x14002f4ea  mov     rax, [rdx+8]
0x14002f4ee  cmp     rax, qword ptr cs:NPI_MS_IPV4_MODULEID.8
0x14002f4f5  jnz     short loc_14002F55E
0x14002f4f7  cmp     byte ptr cs:SlbNatIpsIpv4Provider+2, 0
0x14002f4fe  jz      short loc_14002F505
0x14002f500  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002f505  lea     rax, ProviderBindingContext+8
0x14002f50c  mov     qword ptr cs:xmmword_140026A40, rbx
0x14002f513  lea     r9, ProviderBindingContext; ProviderBindingContext
0x14002f51a  mov     [rsp+38h+ProviderDispatch], rax; ProviderDispatch
0x14002f51f  lea     r8, SlbNatIpsClientDispatch; ClientDispatch
0x14002f526  mov     rcx, rbx; NmrBindingHandle
0x14002f529  lea     rdx, SlbNatIpsIpv4Provider; ClientBindingContext
0x14002f530  call    cs:__imp_NmrClientAttachProvider
0x14002f537  nop     dword ptr [rax+rax+00h]
0x14002f53c  test    eax, eax
0x14002f53e  js      short loc_14002F563
0x14002f540  mov     rcx, qword ptr cs:SlbNatIpsIpv4Provider+8; RunRefCacheAware
0x14002f547  mov     byte ptr cs:SlbNatIpsIpv4Provider+2, 1
0x14002f54e  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14002f555  nop     dword ptr [rax+rax+00h]
0x14002f55a  xor     eax, eax
0x14002f55c  jmp     short loc_14002F563
0x14002f55e  mov     eax, 0C00002B9h
0x14002f563  add     rsp, 30h
0x14002f567  pop     rbx
0x14002f568  retn
```

# WinNatCleanupBinding

- ea: `0x140019edc`
- end: `0x140019fd3`
- name: `WinNatCleanupBinding`
- size: `247`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400020e0`
- `0x140009b04`
- `0x14000a7dc`
- `0x14001ae34`
- `0x14001b994`

## callees

- `0x14000c9d8`
- `0x14000caa0`
- `0x1400124d0`
- `0x140019edc`

## import_xrefs

- `NETIO!PtDestroyTable` at `0x140019f60`
- `NETIO!PtDestroyTable` at `0x140019f60`
- `NETIO!PtGetNumNodes` at `0x140019f48`
- `NETIO!PtGetNumNodes` at `0x140019f48`

## pseudocode

```c
void __fastcall WinNatCleanupBinding(__int64 a1)
{
  __int64 v2; // rbx
  bool v3; // zf
  __int64 *v4; // r9
  _WORD *v5; // rax
  __int64 *v6; // rcx
  __int64 *v7; // r8
  _WORD *v8; // rax
  __int64 *v9; // rcx

  if ( (*(_BYTE *)(a1 + 88) & 4) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  if ( (*(_BYTE *)(a1 + 88) & 8) != 0 )
  {
    v2 = *(_QWORD *)(a1 + 48);
    if ( v2 )
    {
      if ( (*(_BYTE *)(v2 + 88) & 4) == 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      WinNatLibDereferenceAddressEntry(*(volatile signed __int64 **)(v2 + 72));
      v3 = *(_DWORD *)(v2 + 64) == 0;
      *(_QWORD *)(v2 + 72) = 0;
      if ( !v3 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      if ( (unsigned int)PtGetNumNodes(*(_QWORD *)(v2 + 16)) )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      if ( (int)PtDestroyTable(v2 + 16) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      v4 = *(__int64 **)(v2 + 80);
      v5 = *(_WORD **)(v2 + 104);
      *(_QWORD *)(v2 + 16) = 0;
      v6 = v4 + 1;
      if ( *v5 != 2 )
        v6 = v4;
      PplFreeToLookasideList(*v6, (void *)v2);
    }
  }
  else
  {
    WinNatLibDereferenceAddressEntry(*(volatile signed __int64 **)(a1 + 72));
  }
  v7 = *(__int64 **)(a1 + 80);
  v8 = *(_WORD **)(a1 + 104);
  *(_QWORD *)(a1 + 72) = 0;
  v9 = v7 + 1;
  if ( *v8 != 2 )
    v9 = v7;
  PplFreeToLookasideList(*v9, (void *)a1);
}

```

## disassembly

```asm
0x140019edc  mov     [rsp+arg_0], rbx
0x140019ee1  mov     [rsp+arg_8], rsi
0x140019ee6  push    rdi
0x140019ee7  sub     rsp, 20h
0x140019eeb  test    byte ptr [rcx+58h], 4
0x140019eef  mov     rdi, rcx
0x140019ef2  jz      short loc_140019EF9
0x140019ef4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019ef9  test    byte ptr [rdi+58h], 8
0x140019efd  jnz     short loc_140019F0D
0x140019eff  mov     rcx, [rdi+48h]
0x140019f03  call    WinNatLibDereferenceAddressEntry
0x140019f08  jmp     loc_140019F9B
0x140019f0d  mov     rbx, [rdi+30h]
0x140019f11  test    rbx, rbx
0x140019f14  jz      loc_140019F9B
0x140019f1a  test    byte ptr [rbx+58h], 4
0x140019f1e  jnz     short loc_140019F25
0x140019f20  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019f25  mov     rcx, [rbx+48h]
0x140019f29  call    WinNatLibDereferenceAddressEntry
0x140019f2e  cmp     dword ptr [rbx+40h], 0
0x140019f32  mov     qword ptr [rbx+48h], 0
0x140019f3a  jz      short loc_140019F41
0x140019f3c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019f41  lea     rsi, [rbx+10h]
0x140019f45  mov     rcx, [rsi]
0x140019f48  call    cs:__imp_PtGetNumNodes
0x140019f4f  nop     dword ptr [rax+rax+00h]
0x140019f54  test    eax, eax
0x140019f56  jz      short loc_140019F5D
0x140019f58  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019f5d  mov     rcx, rsi
0x140019f60  call    cs:__imp_PtDestroyTable
0x140019f67  nop     dword ptr [rax+rax+00h]
0x140019f6c  test    eax, eax
0x140019f6e  jns     short loc_140019F75
0x140019f70  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019f75  mov     r9, [rbx+50h]
0x140019f79  mov     rdx, rbx
0x140019f7c  mov     rax, [rbx+68h]
0x140019f80  mov     qword ptr [rsi], 0
0x140019f87  lea     rcx, [r9+8]
0x140019f8b  cmp     word ptr [rax], 2
0x140019f8f  cmovnz  rcx, r9
0x140019f93  mov     rcx, [rcx]
0x140019f96  call    PplFreeToLookasideList
0x140019f9b  mov     r8, [rdi+50h]
0x140019f9f  mov     rdx, rdi
0x140019fa2  mov     rax, [rdi+68h]
0x140019fa6  mov     qword ptr [rdi+48h], 0
0x140019fae  lea     rcx, [r8+8]
0x140019fb2  cmp     word ptr [rax], 2
0x140019fb6  cmovnz  rcx, r8
0x140019fba  mov     rcx, [rcx]
0x140019fbd  call    PplFreeToLookasideList
0x140019fc2  mov     rbx, [rsp+28h+arg_0]
0x140019fc7  mov     rsi, [rsp+28h+arg_8]
0x140019fcc  add     rsp, 20h
0x140019fd0  pop     rdi
0x140019fd1  retn
```

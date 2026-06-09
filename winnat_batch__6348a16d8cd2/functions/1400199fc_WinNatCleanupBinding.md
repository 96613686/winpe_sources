# WinNatCleanupBinding

- ea: `0x1400199fc`
- end: `0x140019af3`
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
- `0x14001a954`
- `0x14001b4b4`

## callees

- `0x14000c9d8`
- `0x14000caa0`
- `0x140011b90`
- `0x1400199fc`

## import_xrefs

- `NETIO!PtDestroyTable` at `0x140019a80`
- `NETIO!PtDestroyTable` at `0x140019a80`
- `NETIO!PtGetNumNodes` at `0x140019a68`
- `NETIO!PtGetNumNodes` at `0x140019a68`

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
0x1400199fc  mov     [rsp+arg_0], rbx
0x140019a01  mov     [rsp+arg_8], rsi
0x140019a06  push    rdi
0x140019a07  sub     rsp, 20h
0x140019a0b  test    byte ptr [rcx+58h], 4
0x140019a0f  mov     rdi, rcx
0x140019a12  jz      short loc_140019A19
0x140019a14  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019a19  test    byte ptr [rdi+58h], 8
0x140019a1d  jnz     short loc_140019A2D
0x140019a1f  mov     rcx, [rdi+48h]
0x140019a23  call    WinNatLibDereferenceAddressEntry
0x140019a28  jmp     loc_140019ABB
0x140019a2d  mov     rbx, [rdi+30h]
0x140019a31  test    rbx, rbx
0x140019a34  jz      loc_140019ABB
0x140019a3a  test    byte ptr [rbx+58h], 4
0x140019a3e  jnz     short loc_140019A45
0x140019a40  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019a45  mov     rcx, [rbx+48h]
0x140019a49  call    WinNatLibDereferenceAddressEntry
0x140019a4e  cmp     dword ptr [rbx+40h], 0
0x140019a52  mov     qword ptr [rbx+48h], 0
0x140019a5a  jz      short loc_140019A61
0x140019a5c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019a61  lea     rsi, [rbx+10h]
0x140019a65  mov     rcx, [rsi]
0x140019a68  call    cs:__imp_PtGetNumNodes
0x140019a6f  nop     dword ptr [rax+rax+00h]
0x140019a74  test    eax, eax
0x140019a76  jz      short loc_140019A7D
0x140019a78  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019a7d  mov     rcx, rsi
0x140019a80  call    cs:__imp_PtDestroyTable
0x140019a87  nop     dword ptr [rax+rax+00h]
0x140019a8c  test    eax, eax
0x140019a8e  jns     short loc_140019A95
0x140019a90  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019a95  mov     r9, [rbx+50h]
0x140019a99  mov     rdx, rbx
0x140019a9c  mov     rax, [rbx+68h]
0x140019aa0  mov     qword ptr [rsi], 0
0x140019aa7  lea     rcx, [r9+8]
0x140019aab  cmp     word ptr [rax], 2
0x140019aaf  cmovnz  rcx, r9
0x140019ab3  mov     rcx, [rcx]
0x140019ab6  call    PplFreeToLookasideList
0x140019abb  mov     r8, [rdi+50h]
0x140019abf  mov     rdx, rdi
0x140019ac2  mov     rax, [rdi+68h]
0x140019ac6  mov     qword ptr [rdi+48h], 0
0x140019ace  lea     rcx, [r8+8]
0x140019ad2  cmp     word ptr [rax], 2
0x140019ad6  cmovnz  rcx, r8
0x140019ada  mov     rcx, [rcx]
0x140019add  call    PplFreeToLookasideList
0x140019ae2  mov     rbx, [rsp+28h+arg_0]
0x140019ae7  mov     rsi, [rsp+28h+arg_8]
0x140019aec  add     rsp, 20h
0x140019af0  pop     rdi
0x140019af1  retn
```

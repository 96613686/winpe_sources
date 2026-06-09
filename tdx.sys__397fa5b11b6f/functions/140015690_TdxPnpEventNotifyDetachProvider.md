# TdxPnpEventNotifyDetachProvider

- ea: `0x140015690`
- end: `0x1400156cb`
- name: `TdxPnpEventNotifyDetachProvider`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140015690`

## import_xrefs

- `NETIO!NmrClientDetachProviderComplete` at `0x1400156b4`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400156b4`

## pseudocode

```c
__int64 __fastcall TdxPnpEventNotifyDetachProvider(__int64 a1)
{
  *(_QWORD *)&WPP_MAIN_CB.DeviceType = 0;
  *(_BYTE *)(a1 + 28) = 1;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 24), 0xFFFFFFFF) == 1 )
    NmrClientDetachProviderComplete(*(HANDLE *)(a1 + 32));
  return 259;
}

```

## disassembly

```asm
0x140015690  sub     rsp, 28h
0x140015694  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, 0
0x14001569f  or      eax, 0FFFFFFFFh
0x1400156a2  mov     byte ptr [rcx+1Ch], 1
0x1400156a6  lock xadd [rcx+18h], eax
0x1400156ab  cmp     eax, 1
0x1400156ae  jnz     short loc_1400156C0
0x1400156b0  mov     rcx, [rcx+20h]; NmrBindingHandle
0x1400156b4  call    cs:__imp_NmrClientDetachProviderComplete
0x1400156bb  nop     dword ptr [rax+rax+00h]
0x1400156c0  mov     eax, 103h
0x1400156c5  add     rsp, 28h
0x1400156c9  retn
```

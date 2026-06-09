# TdxDereferenceNaProviderContext

- ea: `0x140014958`
- end: `0x14001497f`
- name: `TdxDereferenceNaProviderContext`
- size: `39`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140014ab0`
- `0x140014c20`
- `0x140014c84`

## callees

- `0x140014958`

## import_xrefs

- `NETIO!NmrClientDetachProviderComplete` at `0x14001496d`
- `NETIO!NmrClientDetachProviderComplete` at `0x14001496d`

## pseudocode

```c
void __fastcall TdxDereferenceNaProviderContext(__int64 a1)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF) == 1 )
    NmrClientDetachProviderComplete(*(HANDLE *)(a1 + 24));
}

```

## disassembly

```asm
0x140014958  sub     rsp, 28h
0x14001495c  or      eax, 0FFFFFFFFh
0x14001495f  lock xadd [rcx+10h], eax
0x140014964  cmp     eax, 1
0x140014967  jnz     short loc_140014979
0x140014969  mov     rcx, [rcx+18h]; NmrBindingHandle
0x14001496d  call    cs:__imp_NmrClientDetachProviderComplete
0x140014974  nop     dword ptr [rax+rax+00h]
0x140014979  add     rsp, 28h
0x14001497d  retn
```

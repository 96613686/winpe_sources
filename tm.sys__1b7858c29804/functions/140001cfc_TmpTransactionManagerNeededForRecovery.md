# TmpTransactionManagerNeededForRecovery

- ea: `0x140001cfc`
- end: `0x140001d7b`
- name: `TmpTransactionManagerNeededForRecovery`
- size: `127`
- prototype: `__int64 __fastcall(void *Source1)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001c4a0`

## callees

- `0x1400018f8`
- `0x140001b84`
- `0x140001cfc`
- `0x1400024e0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140001d27`
- `ntoskrnl!RtlCompareMemory` at `0x140001d50`
- `ntoskrnl!RtlCompareMemory` at `0x140001d27`
- `ntoskrnl!RtlCompareMemory` at `0x140001d50`

## pseudocode

```c
SIZE_T __fastcall TmpTransactionManagerNeededForRecovery(void *Source1)
{
  SIZE_T result; // rax
  __int128 Source2; // [rsp+20h] [rbp-28h] BYREF

  Source2 = 0;
  if ( RtlCompareMemory(Source1, &Source2, 0x10u) == 16 )
    return TmpReadKtmRmTmId();
  result = RtlCompareMemory(Source1, &TmpKtmRmTmGuid, 0x10u);
  if ( result == 16 )
    return TmpStartKtmRm();
  return result;
}

```

## disassembly

```asm
0x140001cfc  push    rbx
0x140001cfe  sub     rsp, 40h
0x140001d02  mov     rax, cs:__security_cookie
0x140001d09  xor     rax, rsp
0x140001d0c  mov     [rsp+48h+var_18], rax
0x140001d11  xorps   xmm0, xmm0
0x140001d14  lea     rdx, [rsp+48h+Source2]; Source2
0x140001d19  mov     r8d, 10h; Length
0x140001d1f  mov     rbx, rcx
0x140001d22  movups  [rsp+48h+Source2], xmm0
0x140001d27  call    cs:__imp_RtlCompareMemory
0x140001d2e  nop     dword ptr [rax+rax+00h]
0x140001d33  cmp     rax, 10h
0x140001d37  jnz     short loc_140001D40
0x140001d39  call    TmpReadKtmRmTmId
0x140001d3e  jmp     short loc_140001D67
0x140001d40  mov     r8d, 10h; Length
0x140001d46  lea     rdx, TmpKtmRmTmGuid; Source2
0x140001d4d  mov     rcx, rbx; Source1
0x140001d50  call    cs:__imp_RtlCompareMemory
0x140001d57  nop     dword ptr [rax+rax+00h]
0x140001d5c  cmp     rax, 10h
0x140001d60  jnz     short loc_140001D67
0x140001d62  call    TmpStartKtmRm
0x140001d67  mov     rcx, [rsp+48h+var_18]
0x140001d6c  xor     rcx, rsp; StackCookie
0x140001d6f  call    __security_check_cookie
0x140001d74  add     rsp, 40h
0x140001d78  pop     rbx
0x140001d79  retn
```

# PipeCompleteChannelHold

- ea: `0x140015a14`
- end: `0x140015a4c`
- name: `PipeCompleteChannelHold`
- size: `56`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002000`
- `0x140002d20`
- `0x140016030`

## callees

- `0x140015a14`

## import_xrefs

- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x140015a3a`
- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x140015a3a`

## pseudocode

```c
__int64 __fastcall PipeCompleteChannelHold(__int64 a1)
{
  signed __int32 v1; // edx
  __int64 result; // rax

  v1 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 280), 1u);
  result = *(unsigned int *)(a1 + 276);
  if ( v1 + 1 == (_DWORD)result )
    return ExUnblockOnAddressPushLockEx(a1 + 288, 0);
  return result;
}

```

## disassembly

```asm
0x140015a14  sub     rsp, 28h
0x140015a18  mov     edx, 1
0x140015a1d  lock xadd [rcx+118h], edx
0x140015a25  mov     eax, [rcx+114h]
0x140015a2b  inc     edx
0x140015a2d  cmp     edx, eax
0x140015a2f  jnz     short loc_140015A46
0x140015a31  add     rcx, 120h
0x140015a38  xor     edx, edx
0x140015a3a  call    cs:__imp_ExUnblockOnAddressPushLockEx
0x140015a41  nop     dword ptr [rax+rax+00h]
0x140015a46  add     rsp, 28h
0x140015a4a  retn
```

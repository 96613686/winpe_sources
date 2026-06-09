# I_CommitPinToCache

- ea: `0x180038e28`
- end: `0x180038e75`
- name: `I_CommitPinToCache`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800391c4`
- `0x180039670`

## callees

- `0x180038e28`
- `0x180038f2c`

## import_xrefs

- `msvcrt!time` at `0x180038e41`
- `msvcrt!time` at `0x180038e41`

## pseudocode

```c
__int64 __fastcall I_CommitPinToCache(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, int a5)
{
  time((time_t *const)(a1 + 40));
  if ( a4 && *(_DWORD *)(a4 + 24) == 1 )
    *(_DWORD *)(a1 + 48) = *(_DWORD *)(a4 + 28);
  *(_DWORD *)(a1 + 32) = a5;
  return I_PinCacheEncryptPin(a1, a2, a3);
}

```

## disassembly

```asm
0x180038e28  push    rbx
0x180038e2a  push    rbp
0x180038e2b  push    rsi
0x180038e2c  push    rdi
0x180038e2d  sub     rsp, 28h
0x180038e31  mov     rdi, rcx
0x180038e34  mov     rbx, r9
0x180038e37  add     rcx, 28h ; '('; Time
0x180038e3b  mov     esi, r8d
0x180038e3e  mov     rbp, rdx
0x180038e41  call    cs:__imp_time
0x180038e47  test    rbx, rbx
0x180038e4a  jz      short loc_180038E58
0x180038e4c  cmp     dword ptr [rbx+18h], 1
0x180038e50  jnz     short loc_180038E58
0x180038e52  mov     eax, [rbx+1Ch]
0x180038e55  mov     [rdi+30h], eax
0x180038e58  mov     eax, [rsp+48h+arg_20]
0x180038e5c  mov     r8d, esi
0x180038e5f  mov     rdx, rbp
0x180038e62  mov     [rdi+20h], eax
0x180038e65  mov     rcx, rdi
0x180038e68  add     rsp, 28h
0x180038e6c  pop     rdi
0x180038e6d  pop     rsi
0x180038e6e  pop     rbp
0x180038e6f  pop     rbx
0x180038e70  jmp     I_PinCacheEncryptPin
```

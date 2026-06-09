# FileProvReferenceReadCompletionContext

- ea: `0x140009a50`
- end: `0x140009aa0`
- name: `FileProvReferenceReadCompletionContext`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140038710`

## callees

- `0x140009a50`
- `0x140010654`

## pseudocode

```c
__int64 __fastcall FileProvReferenceReadCompletionContext(__int64 a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_eaaba969f297373d9ffb29335f34480c_Traceguids, v1, a1);
  return v1;
}

```

## disassembly

```asm
0x140009a50  push    rbx
0x140009a52  sub     rsp, 30h
0x140009a56  mov     ebx, 1
0x140009a5b  lock xadd [rcx+10h], ebx
0x140009a60  inc     ebx
0x140009a62  mov     r10, cs:WPP_GLOBAL_Control
0x140009a69  mov     eax, [r10+2Ch]
0x140009a6d  test    al, 20h
0x140009a6f  jnz     short loc_140009A7A
0x140009a71  mov     eax, ebx
0x140009a73  add     rsp, 30h
0x140009a77  pop     rbx
0x140009a78  retn
0x140009a7a  cmp     byte ptr [r10+29h], 5
0x140009a7f  jb      short loc_140009A71
0x140009a81  mov     [rsp+38h+var_18], rcx
0x140009a86  lea     r8, WPP_eaaba969f297373d9ffb29335f34480c_Traceguids
0x140009a8d  mov     rcx, [r10+18h]
0x140009a91  mov     edx, 0Ch
0x140009a96  mov     r9d, ebx
0x140009a99  call    WPP_SF_dq
0x140009a9e  jmp     short loc_140009A71
```

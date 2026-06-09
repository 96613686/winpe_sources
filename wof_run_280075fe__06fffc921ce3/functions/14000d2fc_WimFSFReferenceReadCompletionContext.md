# WimFSFReferenceReadCompletionContext

- ea: `0x14000d2fc`
- end: `0x14000d34c`
- name: `WimFSFReferenceReadCompletionContext`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14003ccf0`

## callees

- `0x14000d2fc`
- `0x140010654`

## pseudocode

```c
__int64 __fastcall WimFSFReferenceReadCompletionContext(__int64 a1)
{
  signed __int32 v1; // ebx

  v1 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 1u);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_dq(
      WPP_GLOBAL_Control->AttachedDevice,
      14,
      WPP_b091599abfd73b8a76031cd442416986_Traceguids,
      (unsigned int)(v1 + 1),
      a1);
  return (unsigned int)(v1 + 1);
}

```

## disassembly

```asm
0x14000d2fc  push    rbx
0x14000d2fe  sub     rsp, 30h
0x14000d302  mov     rax, rcx
0x14000d305  mov     ebx, 1
0x14000d30a  lock xadd [rcx+10h], ebx
0x14000d30f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d316  mov     edx, [rcx+2Ch]
0x14000d319  test    dl, 20h
0x14000d31c  jz      short loc_14000D342
0x14000d31e  cmp     byte ptr [rcx+29h], 5
0x14000d322  jb      short loc_14000D342
0x14000d324  mov     rcx, [rcx+18h]
0x14000d328  lea     r9d, [rbx+1]
0x14000d32c  mov     edx, 0Eh
0x14000d331  mov     [rsp+38h+var_18], rax
0x14000d336  lea     r8, WPP_b091599abfd73b8a76031cd442416986_Traceguids
0x14000d33d  call    WPP_SF_dq
0x14000d342  lea     eax, [rbx+1]
0x14000d345  add     rsp, 30h
0x14000d349  pop     rbx
0x14000d34a  retn
```

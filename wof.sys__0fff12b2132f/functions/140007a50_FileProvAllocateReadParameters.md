# FileProvAllocateReadParameters

- ea: `0x140007a50`
- end: `0x140007b0e`
- name: `FileProvAllocateReadParameters`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140039700`

## callees

- `0x140007a50`
- `0x14000d3fc`
- `0x1400119c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140007a80`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140007a80`

## pseudocode

```c
__int64 __fastcall FileProvAllocateReadParameters(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rcx
  _DWORD *v5; // rax
  _DWORD *v6; // rbx
  __int64 result; // rax

  v3 = 104LL * *(unsigned int *)(a1 + 4);
  *a2 = 0;
  v5 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&qword_140019500[v3]);
  v6 = v5;
  if ( !v5 )
    return 3221225626LL;
  memset(v5, 0, 0xE0u);
  v6[3] |= 1u;
  *((_QWORD *)v6 + 7) = a1;
  v6[4] = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_eaaba969f297373d9ffb29335f34480c_Traceguids, v6);
  result = 0;
  *a2 = v6 + 6;
  return result;
}

```

## disassembly

```asm
0x140007a50  mov     [rsp+arg_8], rbx
0x140007a55  mov     [rsp+arg_10], rsi
0x140007a5a  push    rdi
0x140007a5b  sub     rsp, 20h
0x140007a5f  mov     eax, [rcx+4]
0x140007a62  mov     rsi, rcx
0x140007a65  imul    rcx, rax, 340h
0x140007a6c  lea     rax, qword_140019500
0x140007a73  mov     qword ptr [rdx], 0
0x140007a7a  add     rcx, rax; Lookaside
0x140007a7d  mov     rdi, rdx
0x140007a80  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140007a87  nop     dword ptr [rax+rax+00h]
0x140007a8c  mov     rbx, rax
0x140007a8f  test    rax, rax
0x140007a92  jz      short loc_140007AE7
0x140007a94  mov     [rsp+28h+arg_0], rbp
0x140007a99  xor     edx, edx; Val
0x140007a9b  mov     r8d, 0E0h; Size
0x140007aa1  mov     rcx, rax; void *
0x140007aa4  xor     ebp, ebp
0x140007aa6  call    memset
0x140007aab  or      dword ptr [rbx+0Ch], 1
0x140007aaf  mov     [rbx+38h], rsi
0x140007ab3  mov     dword ptr [rbx+10h], 1
0x140007aba  mov     rcx, cs:WPP_GLOBAL_Control
0x140007ac1  mov     eax, [rcx+2Ch]
0x140007ac4  test    al, 20h
0x140007ac6  jnz     short loc_140007AEE
0x140007ac8  add     rbx, 18h
0x140007acc  mov     eax, ebp
0x140007ace  mov     rbp, [rsp+28h+arg_0]
0x140007ad3  mov     [rdi], rbx
0x140007ad6  mov     rbx, [rsp+28h+arg_8]
0x140007adb  mov     rsi, [rsp+28h+arg_10]
0x140007ae0  add     rsp, 20h
0x140007ae4  pop     rdi
0x140007ae5  retn
0x140007ae7  mov     eax, 0C000009Ah
0x140007aec  jmp     short loc_140007AD6
0x140007aee  cmp     byte ptr [rcx+29h], 5
0x140007af2  jb      short loc_140007AC8
0x140007af4  mov     rcx, [rcx+18h]
0x140007af8  lea     r8, WPP_eaaba969f297373d9ffb29335f34480c_Traceguids
0x140007aff  mov     edx, 0Bh
0x140007b04  mov     r9, rbx
0x140007b07  call    WPP_SF_q
0x140007b0c  jmp     short loc_140007AC8
```

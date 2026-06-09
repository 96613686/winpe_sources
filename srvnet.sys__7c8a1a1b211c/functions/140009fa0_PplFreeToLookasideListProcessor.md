# PplFreeToLookasideListProcessor

- ea: `0x140009fa0`
- end: `0x140009feb`
- name: `PplFreeToLookasideListProcessor`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400204a8`

## callees

- `0x140009fa0`
- `0x14000f3dc`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140009fd3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140009fd3`

## pseudocode

```c
void __fastcall PplFreeToLookasideListProcessor(__int64 a1, void *a2, int a3)
{
  unsigned __int64 v4; // rbx

  v4 = a1 + ((unsigned __int64)(unsigned int)(a3 + 1) << 7);
  if ( !*(_BYTE *)(v4 + 176) )
    PplpLazyInitializeLookasideList(a1, v4 + 64);
  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v4 + 64), a2);
}

```

## disassembly

```asm
0x140009fa0  mov     [rsp+arg_0], rbx
0x140009fa5  push    rdi
0x140009fa6  sub     rsp, 20h
0x140009faa  lea     ebx, [r8+1]
0x140009fae  mov     rdi, rdx
0x140009fb1  shl     rbx, 7
0x140009fb5  add     rbx, rcx
0x140009fb8  movzx   eax, byte ptr [rbx+0B0h]
0x140009fbf  test    al, al
0x140009fc1  jnz     short loc_140009FCC
0x140009fc3  lea     rdx, [rbx+40h]
0x140009fc7  call    PplpLazyInitializeLookasideList
0x140009fcc  mov     rdx, rdi; Entry
0x140009fcf  lea     rcx, [rbx+40h]; Lookaside
0x140009fd3  call    cs:__imp_ExFreeToLookasideListEx
0x140009fda  nop     dword ptr [rax+rax+00h]
0x140009fdf  mov     rbx, [rsp+28h+arg_0]
0x140009fe4  add     rsp, 20h
0x140009fe8  pop     rdi
0x140009fe9  retn
```

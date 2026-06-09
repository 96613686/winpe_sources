# FreeNakContext

- ea: `0x14000f0a0`
- end: `0x14000f10f`
- name: `FreeNakContext`
- size: `111`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000d210`
- `0x14000dd10`
- `0x14000e03c`
- `0x14000f2d8`

## callees

- `0x14000ef98`
- `0x14000f0a0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000f0f9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000f0f9`

## pseudocode

```c
void __fastcall FreeNakContext(__int64 a1, _BYTE *a2)
{
  unsigned __int8 v4; // di
  unsigned __int8 v5; // bp
  __int64 v6; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v7; // rcx

  v4 = 0;
  v5 = a2[58] + a2[59];
  if ( v5 )
  {
    do
    {
      FreeDataBuffer(a1, (__int64)&a2[32 * v4 + 96 + 8 * v4]);
      ++v4;
    }
    while ( v4 < v5 );
  }
  v6 = *(_QWORD *)(a1 + 48);
  if ( a2[62] <= 1u )
    v7 = (struct _NPAGED_LOOKASIDE_LIST *)(v6 + 448);
  else
    v7 = (struct _NPAGED_LOOKASIDE_LIST *)(v6 + 576);
  ExFreeToNPagedLookasideList(v7, a2);
}

```

## disassembly

```asm
0x14000f0a0  push    rbx
0x14000f0a2  push    rbp
0x14000f0a3  push    rsi
0x14000f0a4  push    rdi
0x14000f0a5  sub     rsp, 28h
0x14000f0a9  mov     bpl, [rdx+3Bh]
0x14000f0ad  mov     rbx, rdx
0x14000f0b0  mov     rsi, rcx
0x14000f0b3  mov     dil, 0
0x14000f0b6  add     bpl, [rdx+3Ah]
0x14000f0ba  jz      short loc_14000F0DC
0x14000f0bc  movzx   eax, dil
0x14000f0c0  lea     rcx, [rax+3]
0x14000f0c4  lea     rcx, [rax+rcx*4]
0x14000f0c8  lea     rdx, [rbx+rcx*8]
0x14000f0cc  mov     rcx, rsi
0x14000f0cf  call    FreeDataBuffer
0x14000f0d4  inc     dil
0x14000f0d7  cmp     dil, bpl
0x14000f0da  jb      short loc_14000F0BC
0x14000f0dc  cmp     byte ptr [rbx+3Eh], 1
0x14000f0e0  mov     rdx, rbx; Entry
0x14000f0e3  mov     rcx, [rsi+30h]
0x14000f0e7  jbe     short loc_14000F0F2
0x14000f0e9  add     rcx, 240h
0x14000f0f0  jmp     short loc_14000F0F9
0x14000f0f2  add     rcx, 1C0h; Lookaside
0x14000f0f9  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000f100  nop     dword ptr [rax+rax+00h]
0x14000f105  add     rsp, 28h
0x14000f109  pop     rdi
0x14000f10a  pop     rsi
0x14000f10b  pop     rbp
0x14000f10c  pop     rbx
0x14000f10d  retn
```

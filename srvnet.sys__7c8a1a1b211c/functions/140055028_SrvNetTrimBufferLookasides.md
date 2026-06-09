# SrvNetTrimBufferLookasides

- ea: `0x140055028`
- end: `0x1400550b3`
- name: `SrvNetTrimBufferLookasides`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14001b6e0`

## callees

- `0x14002a4c0`
- `0x140055028`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140055061`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140055061`
- `ntoskrnl!ExQueryDepthSList` at `0x140055085`
- `ntoskrnl!ExQueryDepthSList` at `0x140055085`

## pseudocode

```c
void SrvNetTrimBufferLookasides()
{
  __int64 i; // rbx
  unsigned int *v1; // r14
  unsigned int v2; // edi
  unsigned __int64 v3; // rsi
  PSLIST_ENTRY v4; // rcx

  for ( i = 0; i != 9; ++i )
  {
    v1 = (unsigned int *)SrvNetBufferLookasides[i];
    v2 = *v1;
    while ( (--v2 & 0x80000000) == 0 )
    {
      v3 = (unsigned __int64)v2 << 7;
      if ( *((_BYTE *)v1 + v3 + 176) )
      {
        do
        {
          v4 = ExpInterlockedPopEntrySList((PSLIST_HEADER)((char *)v1 + v3 + 64));
          if ( v4 )
            (*(void (__fastcall **)(PSLIST_ENTRY, unsigned __int64))((char *)v1 + v3 + 120))(
              v4,
              (unsigned __int64)v1 + v3 + 64);
        }
        while ( ExQueryDepthSList((PSLIST_HEADER)((char *)v1 + v3 + 64)) > *(_WORD *)((char *)v1 + v3 + 80) );
      }
    }
  }
}

```

## disassembly

```asm
0x140055028  push    rbx
0x14005502a  push    rbp
0x14005502b  push    rsi
0x14005502c  push    rdi
0x14005502d  push    r14
0x14005502f  sub     rsp, 20h
0x140055033  xor     ebx, ebx
0x140055035  lea     r14, SrvNetBufferLookasides
0x14005503c  mov     r14, [r14+rbx*8]
0x140055040  mov     edi, [r14]
0x140055043  jmp     short loc_140055099
0x140055045  mov     esi, edi
0x140055047  shl     rsi, 7
0x14005504b  mov     al, [rsi+r14+0B0h]
0x140055053  lea     rbp, [rsi+40h]
0x140055057  add     rbp, r14
0x14005505a  test    al, al
0x14005505c  jz      short loc_140055099
0x14005505e  mov     rcx, rbp; ListHead
0x140055061  call    cs:__imp_ExpInterlockedPopEntrySList
0x140055068  nop     dword ptr [rax+rax+00h]
0x14005506d  mov     rcx, rax
0x140055070  test    rax, rax
0x140055073  jz      short loc_140055082
0x140055075  mov     rax, [rsi+r14+78h]
0x14005507a  mov     rdx, rbp
0x14005507d  call    _guard_dispatch_icall
0x140055082  mov     rcx, rbp; SListHead
0x140055085  call    cs:__imp_ExQueryDepthSList
0x14005508c  nop     dword ptr [rax+rax+00h]
0x140055091  cmp     ax, [rsi+r14+50h]
0x140055097  ja      short loc_14005505E
0x140055099  sub     edi, 1
0x14005509c  jns     short loc_140055045
0x14005509e  inc     rbx
0x1400550a1  cmp     rbx, 9
0x1400550a5  jnz     short loc_140055035
0x1400550a7  add     rsp, 20h
0x1400550ab  pop     r14
0x1400550ad  pop     rdi
0x1400550ae  pop     rsi
0x1400550af  pop     rbp
0x1400550b0  pop     rbx
0x1400550b1  retn
```

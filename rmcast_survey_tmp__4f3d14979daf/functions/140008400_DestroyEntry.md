# DestroyEntry

- ea: `0x140008400`
- end: `0x140008447`
- name: `DestroyEntry`
- size: `71`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140008868`
- `0x140008fb0`
- `0x140018d80`
- `0x1400192d0`

## callees

- `0x140008400`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000842a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000842a`

## pseudocode

```c
void __fastcall DestroyEntry(__int64 a1, _QWORD *a2)
{
  __int64 v3; // r9
  _QWORD *v4; // r8

  v3 = a2[10];
  if ( *(_QWORD **)(v3 + 8) != a2 + 10 || (v4 = (_QWORD *)a2[11], (_QWORD *)*v4 != a2 + 10) )
    __fastfail(3u);
  *v4 = v3;
  *(_QWORD *)(v3 + 8) = v4;
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 64), a2);
  --*(_DWORD *)(a1 + 36);
}

```

## disassembly

```asm
0x140008400  push    rbx
0x140008402  sub     rsp, 20h
0x140008406  lea     rax, [rdx+50h]
0x14000840a  mov     rbx, rcx
0x14000840d  mov     r9, [rax]
0x140008410  cmp     [r9+8], rax
0x140008414  jnz     short loc_140008440
0x140008416  mov     r8, [rax+8]
0x14000841a  cmp     [r8], rax
0x14000841d  jnz     short loc_140008440
0x14000841f  mov     [r8], r9
0x140008422  add     rcx, 40h ; '@'; Lookaside
0x140008426  mov     [r9+8], r8
0x14000842a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140008431  nop     dword ptr [rax+rax+00h]
0x140008436  dec     dword ptr [rbx+24h]
0x140008439  add     rsp, 20h
0x14000843d  pop     rbx
0x14000843e  retn
0x140008440  mov     ecx, 3
0x140008445  int     29h; Win8: RtlFailFast(ecx)
```

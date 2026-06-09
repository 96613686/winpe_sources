# StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)

- ea: `0x18001d0d4`
- end: `0x18001d156`
- name: `??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Package_NoThrow *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b894`
- `0x180038c20`
- `0x180038f40`

## callees

- `0x18001d0d4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001d0ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001d105`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001d11c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001d133`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001d14a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001d0ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001d105`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001d11c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001d133`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001d14a`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(
        StateRepository::Cache::Entity::Package_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = *((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v2 )
    SRCache_Free();
  v3 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v5 )
    SRCache_Free();
  v6 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v6 )
    SRCache_Free();
}

```

## disassembly

```asm
0x18001d0d4  push    rbx
0x18001d0d6  sub     rsp, 20h
0x18001d0da  mov     rbx, rcx
0x18001d0dd  mov     rcx, [rcx+58h]
0x18001d0e1  mov     qword ptr [rbx+58h], 0
0x18001d0e9  test    rcx, rcx
0x18001d0ec  jz      short loc_18001D0F4
0x18001d0ee  call    cs:__imp_SRCache_Free
0x18001d0f4  mov     rcx, [rbx+48h]
0x18001d0f8  mov     qword ptr [rbx+48h], 0
0x18001d100  test    rcx, rcx
0x18001d103  jz      short loc_18001D10B
0x18001d105  call    cs:__imp_SRCache_Free
0x18001d10b  mov     rcx, [rbx+40h]
0x18001d10f  mov     qword ptr [rbx+40h], 0
0x18001d117  test    rcx, rcx
0x18001d11a  jz      short loc_18001D122
0x18001d11c  call    cs:__imp_SRCache_Free
0x18001d122  mov     rcx, [rbx+38h]
0x18001d126  mov     qword ptr [rbx+38h], 0
0x18001d12e  test    rcx, rcx
0x18001d131  jz      short loc_18001D139
0x18001d133  call    cs:__imp_SRCache_Free
0x18001d139  mov     rcx, [rbx+8]
0x18001d13d  mov     qword ptr [rbx+8], 0
0x18001d145  test    rcx, rcx
0x18001d148  jz      short loc_18001D150
0x18001d14a  call    cs:__imp_SRCache_Free
0x18001d150  add     rsp, 20h
0x18001d154  pop     rbx
0x18001d155  retn
```

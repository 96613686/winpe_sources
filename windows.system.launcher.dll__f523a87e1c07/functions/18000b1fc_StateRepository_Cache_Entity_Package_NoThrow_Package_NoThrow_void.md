# StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)

- ea: `0x18000b1fc`
- end: `0x18000b27e`
- name: `??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Package_NoThrow *__hidden this)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x1800056d0`
- `0x180006280`
- `0x180008db8`
- `0x180009ad8`
- `0x18000c398`
- `0x180010c30`
- `0x180014bd0`
- `0x180017b70`
- `0x180065450`
- `0x180066144`
- `0x180099c54`
- `0x180107e7b`
- `0x180107f0b`
- `0x180107ffa`
- `0x1801083c0`
- `0x180108460`
- `0x180108500`
- `0x18010be9b`

## callees

- `0x18000b1fc`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b216`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b22d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b244`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b25b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b272`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b216`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b22d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b244`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b25b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b272`

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
    SRCache_Free(v2);
  v3 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v3 )
    SRCache_Free(v3);
  v4 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v4 )
    SRCache_Free(v4);
  v5 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v5 )
    SRCache_Free(v5);
  v6 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v6 )
    SRCache_Free(v6);
}

```

## disassembly

```asm
0x18000b1fc  push    rbx
0x18000b1fe  sub     rsp, 20h
0x18000b202  mov     rbx, rcx
0x18000b205  mov     rcx, [rcx+58h]
0x18000b209  mov     qword ptr [rbx+58h], 0
0x18000b211  test    rcx, rcx
0x18000b214  jz      short loc_18000B21C
0x18000b216  call    cs:__imp_SRCache_Free
0x18000b21c  mov     rcx, [rbx+48h]
0x18000b220  mov     qword ptr [rbx+48h], 0
0x18000b228  test    rcx, rcx
0x18000b22b  jz      short loc_18000B233
0x18000b22d  call    cs:__imp_SRCache_Free
0x18000b233  mov     rcx, [rbx+40h]
0x18000b237  mov     qword ptr [rbx+40h], 0
0x18000b23f  test    rcx, rcx
0x18000b242  jz      short loc_18000B24A
0x18000b244  call    cs:__imp_SRCache_Free
0x18000b24a  mov     rcx, [rbx+38h]
0x18000b24e  mov     qword ptr [rbx+38h], 0
0x18000b256  test    rcx, rcx
0x18000b259  jz      short loc_18000B261
0x18000b25b  call    cs:__imp_SRCache_Free
0x18000b261  mov     rcx, [rbx+8]
0x18000b265  mov     qword ptr [rbx+8], 0
0x18000b26d  test    rcx, rcx
0x18000b270  jz      short loc_18000B278
0x18000b272  call    cs:__imp_SRCache_Free
0x18000b278  add     rsp, 20h
0x18000b27c  pop     rbx
0x18000b27d  retn
```

# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)

- ea: `0x18001a528`
- end: `0x18001a5ac`
- name: `??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `132`
- prototype: `void __fastcall(StateRepository::Cache::Entity::ApplicationExtension_NoThrow *__hidden this)`
- caller_count: `16`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006280`
- `0x180009ad8`
- `0x18000c398`
- `0x180010c30`
- `0x180014bd0`
- `0x180017b70`
- `0x180065450`
- `0x180070600`
- `0x180078874`
- `0x180107fd6`
- `0x180108380`
- `0x180108420`
- `0x1801084c0`
- `0x18010bdba`
- `0x18010c5ad`
- `0x18010cc7c`

## callees

- `0x18001a528`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a553`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a56a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a581`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a598`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a5a4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a553`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a56a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a581`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a598`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001a5a4`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(
        StateRepository::Cache::Entity::ApplicationExtension_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v2 )
    SRCache_Free(v2);
  v3 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v3 )
    SRCache_Free(v3);
  v4 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v4 )
    SRCache_Free(v4);
  v5 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v5 )
    SRCache_Free(v5);
  v6 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v6 )
    SRCache_Free(v6);
}

```

## disassembly

```asm
0x18001a528  push    rbx
0x18001a52a  sub     rsp, 20h
0x18001a52e  mov     rbx, rcx
0x18001a531  mov     rcx, [rcx+40h]
0x18001a535  mov     qword ptr [rbx+40h], 0
0x18001a53d  test    rcx, rcx
0x18001a540  jnz     short loc_18001A5A4
0x18001a542  mov     rcx, [rbx+38h]
0x18001a546  mov     qword ptr [rbx+38h], 0
0x18001a54e  test    rcx, rcx
0x18001a551  jz      short loc_18001A559
0x18001a553  call    cs:__imp_SRCache_Free
0x18001a559  mov     rcx, [rbx+30h]
0x18001a55d  mov     qword ptr [rbx+30h], 0
0x18001a565  test    rcx, rcx
0x18001a568  jz      short loc_18001A570
0x18001a56a  call    cs:__imp_SRCache_Free
0x18001a570  mov     rcx, [rbx+28h]
0x18001a574  mov     qword ptr [rbx+28h], 0
0x18001a57c  test    rcx, rcx
0x18001a57f  jz      short loc_18001A587
0x18001a581  call    cs:__imp_SRCache_Free
0x18001a587  mov     rcx, [rbx+18h]
0x18001a58b  mov     qword ptr [rbx+18h], 0
0x18001a593  test    rcx, rcx
0x18001a596  jz      short loc_18001A59E
0x18001a598  call    cs:__imp_SRCache_Free
0x18001a59e  add     rsp, 20h
0x18001a5a2  pop     rbx
0x18001a5a3  retn
0x18001a5a4  call    cs:__imp_SRCache_Free
0x18001a5aa  jmp     short loc_18001A542
```

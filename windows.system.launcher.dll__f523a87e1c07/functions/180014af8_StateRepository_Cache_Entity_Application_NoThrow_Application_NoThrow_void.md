# StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)

- ea: `0x180014af8`
- end: `0x180014bbf`
- name: `??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `199`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Application_NoThrow *__hidden this)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x180006280`
- `0x180008db8`
- `0x180009ad8`
- `0x18000c398`
- `0x180010c30`
- `0x180014bd0`
- `0x180017b70`
- `0x180065450`
- `0x180078874`
- `0x1800b74d0`
- `0x180107f32`
- `0x180107fe8`
- `0x1801083a0`
- `0x180108440`
- `0x1801084e0`
- `0x18010bd96`
- `0x18010cc8e`
- `0x18010e276`

## callees

- `0x180014af8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014b12`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014b29`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014b40`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014b57`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014b6e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014b85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014b9c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014bb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014b12`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014b29`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014b40`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014b57`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014b6e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014b85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014b9c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014bb3`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(
        StateRepository::Cache::Entity::Application_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx

  v2 = *((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v2 )
    SRCache_Free(v2);
  v3 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v3 )
    SRCache_Free(v3);
  v4 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v4 )
    SRCache_Free(v4);
  v5 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v5 )
    SRCache_Free(v5);
  v6 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v6 )
    SRCache_Free(v6);
  v7 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v7 )
    SRCache_Free(v7);
  v8 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v8 )
    SRCache_Free(v8);
  v9 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v9 )
    SRCache_Free(v9);
}

```

## disassembly

```asm
0x180014af8  push    rbx
0x180014afa  sub     rsp, 20h
0x180014afe  mov     rbx, rcx
0x180014b01  mov     rcx, [rcx+58h]
0x180014b05  mov     qword ptr [rbx+58h], 0
0x180014b0d  test    rcx, rcx
0x180014b10  jz      short loc_180014B18
0x180014b12  call    cs:__imp_SRCache_Free
0x180014b18  mov     rcx, [rbx+50h]
0x180014b1c  mov     qword ptr [rbx+50h], 0
0x180014b24  test    rcx, rcx
0x180014b27  jz      short loc_180014B2F
0x180014b29  call    cs:__imp_SRCache_Free
0x180014b2f  mov     rcx, [rbx+48h]
0x180014b33  mov     qword ptr [rbx+48h], 0
0x180014b3b  test    rcx, rcx
0x180014b3e  jz      short loc_180014B46
0x180014b40  call    cs:__imp_SRCache_Free
0x180014b46  mov     rcx, [rbx+40h]
0x180014b4a  mov     qword ptr [rbx+40h], 0
0x180014b52  test    rcx, rcx
0x180014b55  jz      short loc_180014B5D
0x180014b57  call    cs:__imp_SRCache_Free
0x180014b5d  mov     rcx, [rbx+38h]
0x180014b61  mov     qword ptr [rbx+38h], 0
0x180014b69  test    rcx, rcx
0x180014b6c  jz      short loc_180014B74
0x180014b6e  call    cs:__imp_SRCache_Free
0x180014b74  mov     rcx, [rbx+30h]
0x180014b78  mov     qword ptr [rbx+30h], 0
0x180014b80  test    rcx, rcx
0x180014b83  jz      short loc_180014B8B
0x180014b85  call    cs:__imp_SRCache_Free
0x180014b8b  mov     rcx, [rbx+20h]
0x180014b8f  mov     qword ptr [rbx+20h], 0
0x180014b97  test    rcx, rcx
0x180014b9a  jz      short loc_180014BA2
0x180014b9c  call    cs:__imp_SRCache_Free
0x180014ba2  mov     rcx, [rbx+18h]
0x180014ba6  mov     qword ptr [rbx+18h], 0
0x180014bae  test    rcx, rcx
0x180014bb1  jz      short loc_180014BB9
0x180014bb3  call    cs:__imp_SRCache_Free
0x180014bb9  add     rsp, 20h
0x180014bbd  pop     rbx
0x180014bbe  retn
```

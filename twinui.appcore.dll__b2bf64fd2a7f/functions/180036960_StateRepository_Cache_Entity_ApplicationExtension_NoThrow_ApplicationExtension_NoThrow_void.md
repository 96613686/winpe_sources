# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)

- ea: `0x180036960`
- end: `0x1800369e2`
- name: `??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(StateRepository::Cache::Entity::ApplicationExtension_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180037230`

## callees

- `0x180036960`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003697a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180036991`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800369a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800369bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800369d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003697a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180036991`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800369a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800369bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800369d6`

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
    SRCache_Free();
  v3 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v5 )
    SRCache_Free();
  v6 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v6 )
    SRCache_Free();
}

```

## disassembly

```asm
0x180036960  push    rbx
0x180036962  sub     rsp, 20h
0x180036966  mov     rbx, rcx
0x180036969  mov     rcx, [rcx+40h]
0x18003696d  mov     qword ptr [rbx+40h], 0
0x180036975  test    rcx, rcx
0x180036978  jz      short loc_180036980
0x18003697a  call    cs:__imp_SRCache_Free
0x180036980  mov     rcx, [rbx+38h]
0x180036984  mov     qword ptr [rbx+38h], 0
0x18003698c  test    rcx, rcx
0x18003698f  jz      short loc_180036997
0x180036991  call    cs:__imp_SRCache_Free
0x180036997  mov     rcx, [rbx+30h]
0x18003699b  mov     qword ptr [rbx+30h], 0
0x1800369a3  test    rcx, rcx
0x1800369a6  jz      short loc_1800369AE
0x1800369a8  call    cs:__imp_SRCache_Free
0x1800369ae  mov     rcx, [rbx+28h]
0x1800369b2  mov     qword ptr [rbx+28h], 0
0x1800369ba  test    rcx, rcx
0x1800369bd  jz      short loc_1800369C5
0x1800369bf  call    cs:__imp_SRCache_Free
0x1800369c5  mov     rcx, [rbx+18h]
0x1800369c9  mov     qword ptr [rbx+18h], 0
0x1800369d1  test    rcx, rcx
0x1800369d4  jz      short loc_1800369DC
0x1800369d6  call    cs:__imp_SRCache_Free
0x1800369dc  add     rsp, 20h
0x1800369e0  pop     rbx
0x1800369e1  retn
```

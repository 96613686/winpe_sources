# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)

- ea: `0x1802b1de0`
- end: `0x1802b1e62`
- name: `??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(StateRepository::Cache::Entity::ApplicationExtension_NoThrow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1802b42dc`
- `0x180484eab`

## callees

- `0x1802b1de0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1dfa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1e11`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1e28`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1e3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1e56`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1dfa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1e11`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1e28`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1e3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1e56`

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
0x1802b1de0  push    rbx
0x1802b1de2  sub     rsp, 20h
0x1802b1de6  mov     rbx, rcx
0x1802b1de9  mov     rcx, [rcx+40h]
0x1802b1ded  mov     qword ptr [rbx+40h], 0
0x1802b1df5  test    rcx, rcx
0x1802b1df8  jz      short loc_1802B1E00
0x1802b1dfa  call    cs:__imp_SRCache_Free
0x1802b1e00  mov     rcx, [rbx+38h]
0x1802b1e04  mov     qword ptr [rbx+38h], 0
0x1802b1e0c  test    rcx, rcx
0x1802b1e0f  jz      short loc_1802B1E17
0x1802b1e11  call    cs:__imp_SRCache_Free
0x1802b1e17  mov     rcx, [rbx+30h]
0x1802b1e1b  mov     qword ptr [rbx+30h], 0
0x1802b1e23  test    rcx, rcx
0x1802b1e26  jz      short loc_1802B1E2E
0x1802b1e28  call    cs:__imp_SRCache_Free
0x1802b1e2e  mov     rcx, [rbx+28h]
0x1802b1e32  mov     qword ptr [rbx+28h], 0
0x1802b1e3a  test    rcx, rcx
0x1802b1e3d  jz      short loc_1802B1E45
0x1802b1e3f  call    cs:__imp_SRCache_Free
0x1802b1e45  mov     rcx, [rbx+18h]
0x1802b1e49  mov     qword ptr [rbx+18h], 0
0x1802b1e51  test    rcx, rcx
0x1802b1e54  jz      short loc_1802B1E5C
0x1802b1e56  call    cs:__imp_SRCache_Free
0x1802b1e5c  add     rsp, 20h
0x1802b1e60  pop     rbx
0x1802b1e61  retn
```

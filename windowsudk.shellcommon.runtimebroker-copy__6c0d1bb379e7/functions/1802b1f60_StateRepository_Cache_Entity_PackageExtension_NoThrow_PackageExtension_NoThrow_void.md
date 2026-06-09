# StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)

- ea: `0x1802b1f60`
- end: `0x1802b1fcb`
- name: `??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `107`
- prototype: `void __fastcall(StateRepository::Cache::Entity::PackageExtension_NoThrow *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1802b3bcc`
- `0x1802b42dc`
- `0x180484d8f`
- `0x180484e63`

## callees

- `0x1802b1f60`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1f7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1f91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1fa8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1fbf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1f7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1f91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1fa8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1fbf`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(
        StateRepository::Cache::Entity::PackageExtension_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  v2 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v2 )
    SRCache_Free();
  v3 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v5 )
    SRCache_Free();
}

```

## disassembly

```asm
0x1802b1f60  push    rbx
0x1802b1f62  sub     rsp, 20h
0x1802b1f66  mov     rbx, rcx
0x1802b1f69  mov     rcx, [rcx+38h]
0x1802b1f6d  mov     qword ptr [rbx+38h], 0
0x1802b1f75  test    rcx, rcx
0x1802b1f78  jz      short loc_1802B1F80
0x1802b1f7a  call    cs:__imp_SRCache_Free
0x1802b1f80  mov     rcx, [rbx+30h]
0x1802b1f84  mov     qword ptr [rbx+30h], 0
0x1802b1f8c  test    rcx, rcx
0x1802b1f8f  jz      short loc_1802B1F97
0x1802b1f91  call    cs:__imp_SRCache_Free
0x1802b1f97  mov     rcx, [rbx+28h]
0x1802b1f9b  mov     qword ptr [rbx+28h], 0
0x1802b1fa3  test    rcx, rcx
0x1802b1fa6  jz      short loc_1802B1FAE
0x1802b1fa8  call    cs:__imp_SRCache_Free
0x1802b1fae  mov     rcx, [rbx+18h]
0x1802b1fb2  mov     qword ptr [rbx+18h], 0
0x1802b1fba  test    rcx, rcx
0x1802b1fbd  jz      short loc_1802B1FC5
0x1802b1fbf  call    cs:__imp_SRCache_Free
0x1802b1fc5  add     rsp, 20h
0x1802b1fc9  pop     rbx
0x1802b1fca  retn
```

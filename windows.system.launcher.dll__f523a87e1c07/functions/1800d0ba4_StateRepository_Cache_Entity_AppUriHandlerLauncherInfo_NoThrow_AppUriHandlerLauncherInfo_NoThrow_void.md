# StateRepository::Cache::Entity::AppUriHandlerLauncherInfo_NoThrow::~AppUriHandlerLauncherInfo_NoThrow(void)

- ea: `0x1800d0ba4`
- end: `0x1800d0c26`
- name: `??1AppUriHandlerLauncherInfo_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(StateRepository::Cache::Entity::AppUriHandlerLauncherInfo_NoThrow *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008db8`
- `0x1800d12d8`
- `0x180107f8c`
- `0x18010e563`

## callees

- `0x1800d0ba4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d0bbe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d0bd5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d0bec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d0c03`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d0c1a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d0bbe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d0bd5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d0bec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d0c03`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d0c1a`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::AppUriHandlerLauncherInfo_NoThrow::~AppUriHandlerLauncherInfo_NoThrow(
        StateRepository::Cache::Entity::AppUriHandlerLauncherInfo_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v2 )
    SRCache_Free(v2);
  v3 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v3 )
    SRCache_Free(v3);
  v4 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v4 )
    SRCache_Free(v4);
  v5 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v5 )
    SRCache_Free(v5);
  v6 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v6 )
    SRCache_Free(v6);
}

```

## disassembly

```asm
0x1800d0ba4  push    rbx
0x1800d0ba6  sub     rsp, 20h
0x1800d0baa  mov     rbx, rcx
0x1800d0bad  mov     rcx, [rcx+38h]
0x1800d0bb1  mov     qword ptr [rbx+38h], 0
0x1800d0bb9  test    rcx, rcx
0x1800d0bbc  jz      short loc_1800D0BC4
0x1800d0bbe  call    cs:__imp_SRCache_Free
0x1800d0bc4  mov     rcx, [rbx+30h]
0x1800d0bc8  mov     qword ptr [rbx+30h], 0
0x1800d0bd0  test    rcx, rcx
0x1800d0bd3  jz      short loc_1800D0BDB
0x1800d0bd5  call    cs:__imp_SRCache_Free
0x1800d0bdb  mov     rcx, [rbx+28h]
0x1800d0bdf  mov     qword ptr [rbx+28h], 0
0x1800d0be7  test    rcx, rcx
0x1800d0bea  jz      short loc_1800D0BF2
0x1800d0bec  call    cs:__imp_SRCache_Free
0x1800d0bf2  mov     rcx, [rbx+18h]
0x1800d0bf6  mov     qword ptr [rbx+18h], 0
0x1800d0bfe  test    rcx, rcx
0x1800d0c01  jz      short loc_1800D0C09
0x1800d0c03  call    cs:__imp_SRCache_Free
0x1800d0c09  mov     rcx, [rbx+10h]
0x1800d0c0d  mov     qword ptr [rbx+10h], 0
0x1800d0c15  test    rcx, rcx
0x1800d0c18  jz      short loc_1800D0C20
0x1800d0c1a  call    cs:__imp_SRCache_Free
0x1800d0c20  add     rsp, 20h
0x1800d0c24  pop     rbx
0x1800d0c25  retn
```

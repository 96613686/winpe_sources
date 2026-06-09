# StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)

- ea: `0x180071e54`
- end: `0x180071f1b`
- name: `??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `199`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Application_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180094190`

## callees

- `0x180071e54`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180071e6e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180071e85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180071e9c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180071eb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180071eca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180071ee1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180071ef8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180071f0f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180071e6e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180071e85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180071e9c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180071eb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180071eca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180071ee1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180071ef8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180071f0f`

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
    SRCache_Free();
  v3 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v5 )
    SRCache_Free();
  v6 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v6 )
    SRCache_Free();
  v7 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v7 )
    SRCache_Free();
  v8 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v8 )
    SRCache_Free();
  v9 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v9 )
    SRCache_Free();
}

```

## disassembly

```asm
0x180071e54  push    rbx
0x180071e56  sub     rsp, 20h
0x180071e5a  mov     rbx, rcx
0x180071e5d  mov     rcx, [rcx+58h]
0x180071e61  mov     qword ptr [rbx+58h], 0
0x180071e69  test    rcx, rcx
0x180071e6c  jz      short loc_180071E74
0x180071e6e  call    cs:__imp_SRCache_Free
0x180071e74  mov     rcx, [rbx+50h]
0x180071e78  mov     qword ptr [rbx+50h], 0
0x180071e80  test    rcx, rcx
0x180071e83  jz      short loc_180071E8B
0x180071e85  call    cs:__imp_SRCache_Free
0x180071e8b  mov     rcx, [rbx+48h]
0x180071e8f  mov     qword ptr [rbx+48h], 0
0x180071e97  test    rcx, rcx
0x180071e9a  jz      short loc_180071EA2
0x180071e9c  call    cs:__imp_SRCache_Free
0x180071ea2  mov     rcx, [rbx+40h]
0x180071ea6  mov     qword ptr [rbx+40h], 0
0x180071eae  test    rcx, rcx
0x180071eb1  jz      short loc_180071EB9
0x180071eb3  call    cs:__imp_SRCache_Free
0x180071eb9  mov     rcx, [rbx+38h]
0x180071ebd  mov     qword ptr [rbx+38h], 0
0x180071ec5  test    rcx, rcx
0x180071ec8  jz      short loc_180071ED0
0x180071eca  call    cs:__imp_SRCache_Free
0x180071ed0  mov     rcx, [rbx+30h]
0x180071ed4  mov     qword ptr [rbx+30h], 0
0x180071edc  test    rcx, rcx
0x180071edf  jz      short loc_180071EE7
0x180071ee1  call    cs:__imp_SRCache_Free
0x180071ee7  mov     rcx, [rbx+20h]
0x180071eeb  mov     qword ptr [rbx+20h], 0
0x180071ef3  test    rcx, rcx
0x180071ef6  jz      short loc_180071EFE
0x180071ef8  call    cs:__imp_SRCache_Free
0x180071efe  mov     rcx, [rbx+18h]
0x180071f02  mov     qword ptr [rbx+18h], 0
0x180071f0a  test    rcx, rcx
0x180071f0d  jz      short loc_180071F15
0x180071f0f  call    cs:__imp_SRCache_Free
0x180071f15  add     rsp, 20h
0x180071f19  pop     rbx
0x180071f1a  retn
```

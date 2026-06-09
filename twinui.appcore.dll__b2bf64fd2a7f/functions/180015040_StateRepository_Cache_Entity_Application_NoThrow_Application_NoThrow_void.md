# StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)

- ea: `0x180015040`
- end: `0x180015107`
- name: `??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `199`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Application_NoThrow *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180037230`
- `0x180039b88`
- `0x180081b70`

## callees

- `0x180015040`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001505a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015071`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015088`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001509f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800150b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800150cd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800150e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800150fb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001505a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015071`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015088`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001509f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800150b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800150cd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800150e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800150fb`

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
0x180015040  push    rbx
0x180015042  sub     rsp, 20h
0x180015046  mov     rbx, rcx
0x180015049  mov     rcx, [rcx+58h]
0x18001504d  mov     qword ptr [rbx+58h], 0
0x180015055  test    rcx, rcx
0x180015058  jz      short loc_180015060
0x18001505a  call    cs:__imp_SRCache_Free
0x180015060  mov     rcx, [rbx+50h]
0x180015064  mov     qword ptr [rbx+50h], 0
0x18001506c  test    rcx, rcx
0x18001506f  jz      short loc_180015077
0x180015071  call    cs:__imp_SRCache_Free
0x180015077  mov     rcx, [rbx+48h]
0x18001507b  mov     qword ptr [rbx+48h], 0
0x180015083  test    rcx, rcx
0x180015086  jz      short loc_18001508E
0x180015088  call    cs:__imp_SRCache_Free
0x18001508e  mov     rcx, [rbx+40h]
0x180015092  mov     qword ptr [rbx+40h], 0
0x18001509a  test    rcx, rcx
0x18001509d  jz      short loc_1800150A5
0x18001509f  call    cs:__imp_SRCache_Free
0x1800150a5  mov     rcx, [rbx+38h]
0x1800150a9  mov     qword ptr [rbx+38h], 0
0x1800150b1  test    rcx, rcx
0x1800150b4  jz      short loc_1800150BC
0x1800150b6  call    cs:__imp_SRCache_Free
0x1800150bc  mov     rcx, [rbx+30h]
0x1800150c0  mov     qword ptr [rbx+30h], 0
0x1800150c8  test    rcx, rcx
0x1800150cb  jz      short loc_1800150D3
0x1800150cd  call    cs:__imp_SRCache_Free
0x1800150d3  mov     rcx, [rbx+20h]
0x1800150d7  mov     qword ptr [rbx+20h], 0
0x1800150df  test    rcx, rcx
0x1800150e2  jz      short loc_1800150EA
0x1800150e4  call    cs:__imp_SRCache_Free
0x1800150ea  mov     rcx, [rbx+18h]
0x1800150ee  mov     qword ptr [rbx+18h], 0
0x1800150f6  test    rcx, rcx
0x1800150f9  jz      short loc_180015101
0x1800150fb  call    cs:__imp_SRCache_Free
0x180015101  add     rsp, 20h
0x180015105  pop     rbx
0x180015106  retn
```

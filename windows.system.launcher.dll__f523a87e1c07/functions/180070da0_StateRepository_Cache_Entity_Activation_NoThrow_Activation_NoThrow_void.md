# StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)

- ea: `0x180070da0`
- end: `0x180070e50`
- name: `??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `176`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Activation_NoThrow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180070600`
- `0x18010c5bf`

## callees

- `0x180070da0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180070dba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180070dd1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180070de8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180070dff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180070e16`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180070e2d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180070e44`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180070dba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180070dd1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180070de8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180070dff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180070e16`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180070e2d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180070e44`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(
        StateRepository::Cache::Entity::Activation_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx

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
  v6 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v6 )
    SRCache_Free(v6);
  v7 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v7 )
    SRCache_Free(v7);
  v8 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v8 )
    SRCache_Free(v8);
}

```

## disassembly

```asm
0x180070da0  push    rbx
0x180070da2  sub     rsp, 20h
0x180070da6  mov     rbx, rcx
0x180070da9  mov     rcx, [rcx+40h]
0x180070dad  mov     qword ptr [rbx+40h], 0
0x180070db5  test    rcx, rcx
0x180070db8  jz      short loc_180070DC0
0x180070dba  call    cs:__imp_SRCache_Free
0x180070dc0  mov     rcx, [rbx+38h]
0x180070dc4  mov     qword ptr [rbx+38h], 0
0x180070dcc  test    rcx, rcx
0x180070dcf  jz      short loc_180070DD7
0x180070dd1  call    cs:__imp_SRCache_Free
0x180070dd7  mov     rcx, [rbx+30h]
0x180070ddb  mov     qword ptr [rbx+30h], 0
0x180070de3  test    rcx, rcx
0x180070de6  jz      short loc_180070DEE
0x180070de8  call    cs:__imp_SRCache_Free
0x180070dee  mov     rcx, [rbx+28h]
0x180070df2  mov     qword ptr [rbx+28h], 0
0x180070dfa  test    rcx, rcx
0x180070dfd  jz      short loc_180070E05
0x180070dff  call    cs:__imp_SRCache_Free
0x180070e05  mov     rcx, [rbx+20h]
0x180070e09  mov     qword ptr [rbx+20h], 0
0x180070e11  test    rcx, rcx
0x180070e14  jz      short loc_180070E1C
0x180070e16  call    cs:__imp_SRCache_Free
0x180070e1c  mov     rcx, [rbx+18h]
0x180070e20  mov     qword ptr [rbx+18h], 0
0x180070e28  test    rcx, rcx
0x180070e2b  jz      short loc_180070E33
0x180070e2d  call    cs:__imp_SRCache_Free
0x180070e33  mov     rcx, [rbx+8]
0x180070e37  mov     qword ptr [rbx+8], 0
0x180070e3f  test    rcx, rcx
0x180070e42  jz      short loc_180070E4A
0x180070e44  call    cs:__imp_SRCache_Free
0x180070e4a  add     rsp, 20h
0x180070e4e  pop     rbx
0x180070e4f  retn
```

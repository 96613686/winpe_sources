# StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)

- ea: `0x1802b1e68`
- end: `0x1802b1f2f`
- name: `??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `199`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Application_NoThrow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1802b42dc`
- `0x180484ebd`

## callees

- `0x1802b1e68`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1e82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1e99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1eb0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1ec7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1ede`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1ef5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1f0c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1f23`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1e82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1e99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1eb0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1ec7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1ede`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1ef5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1f0c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1f23`

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
0x1802b1e68  push    rbx
0x1802b1e6a  sub     rsp, 20h
0x1802b1e6e  mov     rbx, rcx
0x1802b1e71  mov     rcx, [rcx+58h]
0x1802b1e75  mov     qword ptr [rbx+58h], 0
0x1802b1e7d  test    rcx, rcx
0x1802b1e80  jz      short loc_1802B1E88
0x1802b1e82  call    cs:__imp_SRCache_Free
0x1802b1e88  mov     rcx, [rbx+50h]
0x1802b1e8c  mov     qword ptr [rbx+50h], 0
0x1802b1e94  test    rcx, rcx
0x1802b1e97  jz      short loc_1802B1E9F
0x1802b1e99  call    cs:__imp_SRCache_Free
0x1802b1e9f  mov     rcx, [rbx+48h]
0x1802b1ea3  mov     qword ptr [rbx+48h], 0
0x1802b1eab  test    rcx, rcx
0x1802b1eae  jz      short loc_1802B1EB6
0x1802b1eb0  call    cs:__imp_SRCache_Free
0x1802b1eb6  mov     rcx, [rbx+40h]
0x1802b1eba  mov     qword ptr [rbx+40h], 0
0x1802b1ec2  test    rcx, rcx
0x1802b1ec5  jz      short loc_1802B1ECD
0x1802b1ec7  call    cs:__imp_SRCache_Free
0x1802b1ecd  mov     rcx, [rbx+38h]
0x1802b1ed1  mov     qword ptr [rbx+38h], 0
0x1802b1ed9  test    rcx, rcx
0x1802b1edc  jz      short loc_1802B1EE4
0x1802b1ede  call    cs:__imp_SRCache_Free
0x1802b1ee4  mov     rcx, [rbx+30h]
0x1802b1ee8  mov     qword ptr [rbx+30h], 0
0x1802b1ef0  test    rcx, rcx
0x1802b1ef3  jz      short loc_1802B1EFB
0x1802b1ef5  call    cs:__imp_SRCache_Free
0x1802b1efb  mov     rcx, [rbx+20h]
0x1802b1eff  mov     qword ptr [rbx+20h], 0
0x1802b1f07  test    rcx, rcx
0x1802b1f0a  jz      short loc_1802B1F12
0x1802b1f0c  call    cs:__imp_SRCache_Free
0x1802b1f12  mov     rcx, [rbx+18h]
0x1802b1f16  mov     qword ptr [rbx+18h], 0
0x1802b1f1e  test    rcx, rcx
0x1802b1f21  jz      short loc_1802B1F29
0x1802b1f23  call    cs:__imp_SRCache_Free
0x1802b1f29  add     rsp, 20h
0x1802b1f2d  pop     rbx
0x1802b1f2e  retn
```

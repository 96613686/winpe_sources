# StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)

- ea: `0x1800765c4`
- end: `0x1800766bc`
- name: `??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `248`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Application_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18009979c`

## callees

- `0x1800765c4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800765de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800765fb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180076618`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180076635`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180076652`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007666f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007668c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800766a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800765de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800765fb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180076618`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180076635`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180076652`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007666f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007668c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800766a9`

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
0x1800765c4  push    rbx
0x1800765c6  sub     rsp, 20h
0x1800765ca  mov     rbx, rcx
0x1800765cd  mov     rcx, [rcx+58h]
0x1800765d1  mov     qword ptr [rbx+58h], 0
0x1800765d9  test    rcx, rcx
0x1800765dc  jz      short loc_1800765EA
0x1800765de  call    cs:__imp_SRCache_Free
0x1800765e5  nop     dword ptr [rax+rax+00h]
0x1800765ea  mov     rcx, [rbx+50h]
0x1800765ee  mov     qword ptr [rbx+50h], 0
0x1800765f6  test    rcx, rcx
0x1800765f9  jz      short loc_180076607
0x1800765fb  call    cs:__imp_SRCache_Free
0x180076602  nop     dword ptr [rax+rax+00h]
0x180076607  mov     rcx, [rbx+48h]
0x18007660b  mov     qword ptr [rbx+48h], 0
0x180076613  test    rcx, rcx
0x180076616  jz      short loc_180076624
0x180076618  call    cs:__imp_SRCache_Free
0x18007661f  nop     dword ptr [rax+rax+00h]
0x180076624  mov     rcx, [rbx+40h]
0x180076628  mov     qword ptr [rbx+40h], 0
0x180076630  test    rcx, rcx
0x180076633  jz      short loc_180076641
0x180076635  call    cs:__imp_SRCache_Free
0x18007663c  nop     dword ptr [rax+rax+00h]
0x180076641  mov     rcx, [rbx+38h]
0x180076645  mov     qword ptr [rbx+38h], 0
0x18007664d  test    rcx, rcx
0x180076650  jz      short loc_18007665E
0x180076652  call    cs:__imp_SRCache_Free
0x180076659  nop     dword ptr [rax+rax+00h]
0x18007665e  mov     rcx, [rbx+30h]
0x180076662  mov     qword ptr [rbx+30h], 0
0x18007666a  test    rcx, rcx
0x18007666d  jz      short loc_18007667B
0x18007666f  call    cs:__imp_SRCache_Free
0x180076676  nop     dword ptr [rax+rax+00h]
0x18007667b  mov     rcx, [rbx+20h]
0x18007667f  mov     qword ptr [rbx+20h], 0
0x180076687  test    rcx, rcx
0x18007668a  jz      short loc_180076698
0x18007668c  call    cs:__imp_SRCache_Free
0x180076693  nop     dword ptr [rax+rax+00h]
0x180076698  mov     rcx, [rbx+18h]
0x18007669c  mov     qword ptr [rbx+18h], 0
0x1800766a4  test    rcx, rcx
0x1800766a7  jz      short loc_1800766B5
0x1800766a9  call    cs:__imp_SRCache_Free
0x1800766b0  nop     dword ptr [rax+rax+00h]
0x1800766b5  add     rsp, 20h
0x1800766b9  pop     rbx
0x1800766ba  retn
```

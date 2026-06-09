# StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)

- ea: `0x1801d1800`
- end: `0x1801d18a1`
- name: `??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `161`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Package_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1801dd69c`

## callees

- `0x1801d1800`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801d181a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801d1837`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801d1854`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801d1871`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801d188e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801d181a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801d1837`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801d1854`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801d1871`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801d188e`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(
        StateRepository::Cache::Entity::Package_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = *((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v2 )
    SRCache_Free();
  v3 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v5 )
    SRCache_Free();
  v6 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v6 )
    SRCache_Free();
}

```

## disassembly

```asm
0x1801d1800  push    rbx
0x1801d1802  sub     rsp, 20h
0x1801d1806  mov     rbx, rcx
0x1801d1809  mov     rcx, [rcx+58h]
0x1801d180d  mov     qword ptr [rbx+58h], 0
0x1801d1815  test    rcx, rcx
0x1801d1818  jz      short loc_1801D1826
0x1801d181a  call    cs:__imp_SRCache_Free
0x1801d1821  nop     dword ptr [rax+rax+00h]
0x1801d1826  mov     rcx, [rbx+48h]
0x1801d182a  mov     qword ptr [rbx+48h], 0
0x1801d1832  test    rcx, rcx
0x1801d1835  jz      short loc_1801D1843
0x1801d1837  call    cs:__imp_SRCache_Free
0x1801d183e  nop     dword ptr [rax+rax+00h]
0x1801d1843  mov     rcx, [rbx+40h]
0x1801d1847  mov     qword ptr [rbx+40h], 0
0x1801d184f  test    rcx, rcx
0x1801d1852  jz      short loc_1801D1860
0x1801d1854  call    cs:__imp_SRCache_Free
0x1801d185b  nop     dword ptr [rax+rax+00h]
0x1801d1860  mov     rcx, [rbx+38h]
0x1801d1864  mov     qword ptr [rbx+38h], 0
0x1801d186c  test    rcx, rcx
0x1801d186f  jz      short loc_1801D187D
0x1801d1871  call    cs:__imp_SRCache_Free
0x1801d1878  nop     dword ptr [rax+rax+00h]
0x1801d187d  mov     rcx, [rbx+8]
0x1801d1881  mov     qword ptr [rbx+8], 0
0x1801d1889  test    rcx, rcx
0x1801d188c  jz      short loc_1801D189A
0x1801d188e  call    cs:__imp_SRCache_Free
0x1801d1895  nop     dword ptr [rax+rax+00h]
0x1801d189a  add     rsp, 20h
0x1801d189e  pop     rbx
0x1801d189f  retn
```

# StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)

- ea: `0x1802b1fd4`
- end: `0x1802b2056`
- name: `??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Package_NoThrow *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1802b3bcc`
- `0x1802b42dc`
- `0x180484da1`
- `0x180484e75`

## callees

- `0x1802b1fd4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1fee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b2005`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b201c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b2033`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b204a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1fee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b2005`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b201c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b2033`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b204a`

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
0x1802b1fd4  push    rbx
0x1802b1fd6  sub     rsp, 20h
0x1802b1fda  mov     rbx, rcx
0x1802b1fdd  mov     rcx, [rcx+58h]
0x1802b1fe1  mov     qword ptr [rbx+58h], 0
0x1802b1fe9  test    rcx, rcx
0x1802b1fec  jz      short loc_1802B1FF4
0x1802b1fee  call    cs:__imp_SRCache_Free
0x1802b1ff4  mov     rcx, [rbx+48h]
0x1802b1ff8  mov     qword ptr [rbx+48h], 0
0x1802b2000  test    rcx, rcx
0x1802b2003  jz      short loc_1802B200B
0x1802b2005  call    cs:__imp_SRCache_Free
0x1802b200b  mov     rcx, [rbx+40h]
0x1802b200f  mov     qword ptr [rbx+40h], 0
0x1802b2017  test    rcx, rcx
0x1802b201a  jz      short loc_1802B2022
0x1802b201c  call    cs:__imp_SRCache_Free
0x1802b2022  mov     rcx, [rbx+38h]
0x1802b2026  mov     qword ptr [rbx+38h], 0
0x1802b202e  test    rcx, rcx
0x1802b2031  jz      short loc_1802B2039
0x1802b2033  call    cs:__imp_SRCache_Free
0x1802b2039  mov     rcx, [rbx+8]
0x1802b203d  mov     qword ptr [rbx+8], 0
0x1802b2045  test    rcx, rcx
0x1802b2048  jz      short loc_1802B2050
0x1802b204a  call    cs:__imp_SRCache_Free
0x1802b2050  add     rsp, 20h
0x1802b2054  pop     rbx
0x1802b2055  retn
```

# StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)

- ea: `0x1802b1d40`
- end: `0x1802b1dd9`
- name: `??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `153`
- prototype: `void __fastcall(StateRepository::Cache::Entity::PkgExtension_NoThrow *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1802b3bcc`
- `0x1802b42dc`
- `0x180484d7d`
- `0x180484e51`
- `0x180484e99`

## callees

- `0x1802b1d40`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1d5a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1d71`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1d88`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1d9f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1db6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1dcd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1d5a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1d71`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1d88`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1d9f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1db6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802b1dcd`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(
        StateRepository::Cache::Entity::PkgExtension_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx

  v2 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v2 )
    SRCache_Free();
  v3 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v5 )
    SRCache_Free();
  v6 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v6 )
    SRCache_Free();
  v7 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v7 )
    SRCache_Free();
}

```

## disassembly

```asm
0x1802b1d40  push    rbx
0x1802b1d42  sub     rsp, 20h
0x1802b1d46  mov     rbx, rcx
0x1802b1d49  mov     rcx, [rcx+38h]
0x1802b1d4d  mov     qword ptr [rbx+38h], 0
0x1802b1d55  test    rcx, rcx
0x1802b1d58  jz      short loc_1802B1D60
0x1802b1d5a  call    cs:__imp_SRCache_Free
0x1802b1d60  mov     rcx, [rbx+28h]
0x1802b1d64  mov     qword ptr [rbx+28h], 0
0x1802b1d6c  test    rcx, rcx
0x1802b1d6f  jz      short loc_1802B1D77
0x1802b1d71  call    cs:__imp_SRCache_Free
0x1802b1d77  mov     rcx, [rbx+20h]
0x1802b1d7b  mov     qword ptr [rbx+20h], 0
0x1802b1d83  test    rcx, rcx
0x1802b1d86  jz      short loc_1802B1D8E
0x1802b1d88  call    cs:__imp_SRCache_Free
0x1802b1d8e  mov     rcx, [rbx+18h]
0x1802b1d92  mov     qword ptr [rbx+18h], 0
0x1802b1d9a  test    rcx, rcx
0x1802b1d9d  jz      short loc_1802B1DA5
0x1802b1d9f  call    cs:__imp_SRCache_Free
0x1802b1da5  mov     rcx, [rbx+10h]
0x1802b1da9  mov     qword ptr [rbx+10h], 0
0x1802b1db1  test    rcx, rcx
0x1802b1db4  jz      short loc_1802B1DBC
0x1802b1db6  call    cs:__imp_SRCache_Free
0x1802b1dbc  mov     rcx, [rbx+8]
0x1802b1dc0  mov     qword ptr [rbx+8], 0
0x1802b1dc8  test    rcx, rcx
0x1802b1dcb  jz      short loc_1802B1DD3
0x1802b1dcd  call    cs:__imp_SRCache_Free
0x1802b1dd3  add     rsp, 20h
0x1802b1dd7  pop     rbx
0x1802b1dd8  retn
```

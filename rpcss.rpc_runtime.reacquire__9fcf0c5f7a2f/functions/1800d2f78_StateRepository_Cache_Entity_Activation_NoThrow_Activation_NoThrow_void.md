# StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)

- ea: `0x1800d2f78`
- end: `0x1800d3053`
- name: `??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `219`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Activation_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18007693c`

## callees

- `0x1800d2f78`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d2f92`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d2faf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d2fcc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d2fe9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d3006`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d3023`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d3040`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d2f92`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d2faf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d2fcc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d2fe9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d3006`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d3023`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d3040`

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
    SRCache_Free();
  v3 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v5 )
    SRCache_Free();
  v6 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v6 )
    SRCache_Free();
  v7 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v7 )
    SRCache_Free();
  v8 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v8 )
    SRCache_Free();
}

```

## disassembly

```asm
0x1800d2f78  push    rbx
0x1800d2f7a  sub     rsp, 20h
0x1800d2f7e  mov     rbx, rcx
0x1800d2f81  mov     rcx, [rcx+40h]
0x1800d2f85  mov     qword ptr [rbx+40h], 0
0x1800d2f8d  test    rcx, rcx
0x1800d2f90  jz      short loc_1800D2F9E
0x1800d2f92  call    cs:__imp_SRCache_Free
0x1800d2f99  nop     dword ptr [rax+rax+00h]
0x1800d2f9e  mov     rcx, [rbx+38h]
0x1800d2fa2  mov     qword ptr [rbx+38h], 0
0x1800d2faa  test    rcx, rcx
0x1800d2fad  jz      short loc_1800D2FBB
0x1800d2faf  call    cs:__imp_SRCache_Free
0x1800d2fb6  nop     dword ptr [rax+rax+00h]
0x1800d2fbb  mov     rcx, [rbx+30h]
0x1800d2fbf  mov     qword ptr [rbx+30h], 0
0x1800d2fc7  test    rcx, rcx
0x1800d2fca  jz      short loc_1800D2FD8
0x1800d2fcc  call    cs:__imp_SRCache_Free
0x1800d2fd3  nop     dword ptr [rax+rax+00h]
0x1800d2fd8  mov     rcx, [rbx+28h]
0x1800d2fdc  mov     qword ptr [rbx+28h], 0
0x1800d2fe4  test    rcx, rcx
0x1800d2fe7  jz      short loc_1800D2FF5
0x1800d2fe9  call    cs:__imp_SRCache_Free
0x1800d2ff0  nop     dword ptr [rax+rax+00h]
0x1800d2ff5  mov     rcx, [rbx+20h]
0x1800d2ff9  mov     qword ptr [rbx+20h], 0
0x1800d3001  test    rcx, rcx
0x1800d3004  jz      short loc_1800D3012
0x1800d3006  call    cs:__imp_SRCache_Free
0x1800d300d  nop     dword ptr [rax+rax+00h]
0x1800d3012  mov     rcx, [rbx+18h]
0x1800d3016  mov     qword ptr [rbx+18h], 0
0x1800d301e  test    rcx, rcx
0x1800d3021  jz      short loc_1800D302F
0x1800d3023  call    cs:__imp_SRCache_Free
0x1800d302a  nop     dword ptr [rax+rax+00h]
0x1800d302f  mov     rcx, [rbx+8]
0x1800d3033  mov     qword ptr [rbx+8], 0
0x1800d303b  test    rcx, rcx
0x1800d303e  jz      short loc_1800D304C
0x1800d3040  call    cs:__imp_SRCache_Free
0x1800d3047  nop     dword ptr [rax+rax+00h]
0x1800d304c  add     rsp, 20h
0x1800d3050  pop     rbx
0x1800d3051  retn
```

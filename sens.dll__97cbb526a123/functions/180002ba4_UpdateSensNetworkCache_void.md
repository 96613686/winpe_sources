# UpdateSensNetworkCache(void)

- ea: `0x180002ba4`
- end: `0x180002bfe`
- name: `?UpdateSensNetworkCache@@YAXXZ`
- size: `90`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180001470`
- `0x180002060`

## callees

- `0x180002ba4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002bf7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002bcb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002bcb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002bdb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002bdb`

## pseudocode

```c
void UpdateSensNetworkCache(void)
{
  int v0; // ebx

  v0 = gdwLANState != 0;
  if ( gdwWANState )
    v0 |= 2u;
  EnterCriticalSection(&gSensLock);
  *((_DWORD *)gpSensCache + 4) = v0;
  *((_DWORD *)gpSensCache + 3) = GetTickCount();
  LeaveCriticalSection(&gSensLock);
}

```

## disassembly

```asm
0x180002ba4  push    rbx
0x180002ba6  sub     rsp, 20h
0x180002baa  xor     ebx, ebx
0x180002bac  cmp     cs:?gdwLANState@@3JA, ebx; long gdwLANState
0x180002bb2  lea     eax, [rbx+1]
0x180002bb5  cmovnz  ebx, eax
0x180002bb8  cmp     cs:?gdwWANState@@3JA, 0; long gdwWANState
0x180002bbf  jz      short loc_180002BC4
0x180002bc1  or      ebx, 2
0x180002bc4  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002bcb  call    cs:__imp_EnterCriticalSection
0x180002bd1  mov     rax, cs:?gpSensCache@@3PEAU_SENS_CACHE@@EA; _SENS_CACHE * gpSensCache
0x180002bd8  mov     [rax+10h], ebx
0x180002bdb  call    cs:__imp_GetTickCount
0x180002be1  mov     rdx, cs:?gpSensCache@@3PEAU_SENS_CACHE@@EA; _SENS_CACHE * gpSensCache
0x180002be8  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION gSensLock
0x180002bef  mov     [rdx+0Ch], eax
0x180002bf2  add     rsp, 20h
0x180002bf6  pop     rbx
0x180002bf7  jmp     cs:__imp_LeaveCriticalSection
```

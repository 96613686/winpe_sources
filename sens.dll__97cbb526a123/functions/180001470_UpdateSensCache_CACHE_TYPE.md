# UpdateSensCache(CACHE_TYPE)

- ea: `0x180001470`
- end: `0x1800014ff`
- name: `?UpdateSensCache@@YAXW4CACHE_TYPE@@@Z`
- size: `143`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180001850`
- `0x180009b4c`

## callees

- `0x180001470`
- `0x180002ba4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800014ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800014da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000147f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000147f`

## pseudocode

```c
void __fastcall UpdateSensCache(int a1)
{
  _DWORD *v2; // rcx
  int v3; // ebx

  EnterCriticalSection(&gSensLock);
  v2 = gpSensCache;
  if ( !gpSensCache )
    goto LABEL_4;
  if ( a1 == 6 )
  {
    *((_DWORD *)gpSensCache + 9) = gdwLocked;
LABEL_4:
    LeaveCriticalSection(&gSensLock);
    return;
  }
  v3 = a1 - 2;
  if ( v3 )
  {
    if ( v3 == 1 )
    {
      *((_DWORD *)gpSensCache + 7) = gdwWANState;
      v2[8] = gdwLastWANTime;
      UpdateSensNetworkCache();
    }
    goto LABEL_4;
  }
  *((_DWORD *)gpSensCache + 5) = gdwLANState;
  v2[6] = gdwLastLANTime;
  UpdateSensNetworkCache();
  LeaveCriticalSection(&gSensLock);
}

```

## disassembly

```asm
0x180001470  push    rbx
0x180001472  sub     rsp, 20h
0x180001476  mov     ebx, ecx
0x180001478  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000147f  call    cs:__imp_EnterCriticalSection
0x180001485  mov     rcx, cs:?gpSensCache@@3PEAU_SENS_CACHE@@EA; _SENS_CACHE * gpSensCache
0x18000148c  test    rcx, rcx
0x18000148f  jz      short loc_18000149F
0x180001491  cmp     ebx, 6
0x180001494  jnz     short loc_1800014B2
0x180001496  mov     eax, cs:?gdwLocked@@3KA; ulong gdwLocked
0x18000149c  mov     [rcx+24h], eax
0x18000149f  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION gSensLock
0x1800014a6  add     rsp, 20h
0x1800014aa  pop     rbx
0x1800014ab  jmp     cs:__imp_LeaveCriticalSection
0x1800014b2  sub     ebx, 2
0x1800014b5  jnz     short loc_1800014E1
0x1800014b7  mov     eax, cs:?gdwLANState@@3JA; long gdwLANState
0x1800014bd  mov     [rcx+14h], eax
0x1800014c0  mov     eax, cs:?gdwLastLANTime@@3JA; long gdwLastLANTime
0x1800014c6  mov     [rcx+18h], eax
0x1800014c9  call    ?UpdateSensNetworkCache@@YAXXZ; UpdateSensNetworkCache(void)
0x1800014ce  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION gSensLock
0x1800014d5  add     rsp, 20h
0x1800014d9  pop     rbx
0x1800014da  jmp     cs:__imp_LeaveCriticalSection
0x1800014e1  cmp     ebx, 1
0x1800014e4  jnz     short loc_18000149F
0x1800014e6  mov     eax, cs:?gdwWANState@@3JA; long gdwWANState
0x1800014ec  mov     [rcx+1Ch], eax
0x1800014ef  mov     eax, cs:?gdwLastWANTime@@3JA; long gdwLastWANTime
0x1800014f5  mov     [rcx+20h], eax
0x1800014f8  call    ?UpdateSensNetworkCache@@YAXXZ; UpdateSensNetworkCache(void)
0x1800014fd  jmp     short loc_18000149F
```

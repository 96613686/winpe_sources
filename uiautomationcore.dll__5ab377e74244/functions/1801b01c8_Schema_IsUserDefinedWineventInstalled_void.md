# Schema::IsUserDefinedWineventInstalled(void)

- ea: `0x1801b01c8`
- end: `0x1801b0246`
- name: `?IsUserDefinedWineventInstalled@Schema@@SA_NXZ`
- size: `126`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18010caa0`

## callees

- `0x180080cc0`
- `0x1801b01c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801b01de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801b01de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b0227`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b0238`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b0227`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b0238`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!IsWinEventHookInstalled` at `0x1801b01f3`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!IsWinEventHookInstalled` at `0x1801b0211`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!IsWinEventHookInstalled` at `0x1801b01f3`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!IsWinEventHookInstalled` at `0x1801b0211`

## pseudocode

```c
char Schema::IsUserDefinedWineventInstalled(void)
{
  struct UserDefinedPropertyInfo *i; // rbx
  struct UserDefinedEventInfo *j; // rbx

  if ( BasicUiaUtils::IsDesktop() )
  {
    EnterCriticalSection(&_schemaLock);
    for ( i = g_pUserDefinedProperties; i; i = *(struct UserDefinedPropertyInfo **)i )
    {
      if ( IsWinEventHookInstalled(*((_DWORD *)i + 6)) )
      {
LABEL_10:
        LeaveCriticalSection(&_schemaLock);
        return 1;
      }
    }
    for ( j = g_pUserDefinedEvents; j; j = *(struct UserDefinedEventInfo **)j )
    {
      if ( IsWinEventHookInstalled(*((_DWORD *)j + 6)) )
        goto LABEL_10;
    }
    LeaveCriticalSection(&_schemaLock);
  }
  return 0;
}

```

## disassembly

```asm
0x1801b01c8  push    rbx
0x1801b01ca  sub     rsp, 20h
0x1801b01ce  call    ?IsDesktop@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsDesktop(void)
0x1801b01d3  test    al, al
0x1801b01d5  jz      short loc_1801B023E
0x1801b01d7  lea     rcx, ?_schemaLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801b01de  call    cs:__imp_EnterCriticalSection
0x1801b01e4  mov     rbx, cs:?g_pUserDefinedProperties@@3PEAUUserDefinedPropertyInfo@@EA; UserDefinedPropertyInfo * g_pUserDefinedProperties
0x1801b01eb  test    rbx, rbx
0x1801b01ee  jz      short loc_1801B0202
0x1801b01f0  mov     ecx, [rbx+18h]; event
0x1801b01f3  call    cs:__imp_IsWinEventHookInstalled
0x1801b01f9  test    eax, eax
0x1801b01fb  jnz     short loc_1801B0220
0x1801b01fd  mov     rbx, [rbx]
0x1801b0200  jmp     short loc_1801B01EB
0x1801b0202  mov     rbx, cs:?g_pUserDefinedEvents@@3PEAUUserDefinedEventInfo@@EA; UserDefinedEventInfo * g_pUserDefinedEvents
0x1801b0209  test    rbx, rbx
0x1801b020c  jz      short loc_1801B0231
0x1801b020e  mov     ecx, [rbx+18h]; event
0x1801b0211  call    cs:__imp_IsWinEventHookInstalled
0x1801b0217  test    eax, eax
0x1801b0219  jnz     short loc_1801B0220
0x1801b021b  mov     rbx, [rbx]
0x1801b021e  jmp     short loc_1801B0209
0x1801b0220  lea     rcx, ?_schemaLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801b0227  call    cs:__imp_LeaveCriticalSection
0x1801b022d  mov     al, 1
0x1801b022f  jmp     short loc_1801B0240
0x1801b0231  lea     rcx, ?_schemaLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801b0238  call    cs:__imp_LeaveCriticalSection
0x1801b023e  xor     al, al
0x1801b0240  add     rsp, 20h
0x1801b0244  pop     rbx
0x1801b0245  retn
```

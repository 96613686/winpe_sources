# UserServerCleanup

- ea: `0x1800044c8`
- end: `0x18000469b`
- name: `UserServerCleanup`
- size: `467`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800046b0`

## callees

- `0x180003588`
- `0x1800044c8`

## import_xrefs

- `ntdll!NtClose` at `0x18000454b`
- `ntdll!NtClose` at `0x180004563`
- `ntdll!NtClose` at `0x18000457b`
- `ntdll!NtClose` at `0x180004593`
- `ntdll!NtClose` at `0x1800045ab`
- `ntdll!NtClose` at `0x1800045c3`
- `ntdll!NtClose` at `0x1800045db`
- `ntdll!NtClose` at `0x1800045f3`
- `ntdll!NtClose` at `0x18000460b`
- `ntdll!NtClose` at `0x180004623`
- `ntdll!NtClose` at `0x18000463b`
- `ntdll!NtClose` at `0x18000454b`
- `ntdll!NtClose` at `0x180004563`
- `ntdll!NtClose` at `0x18000457b`
- `ntdll!NtClose` at `0x180004593`
- `ntdll!NtClose` at `0x1800045ab`
- `ntdll!NtClose` at `0x1800045c3`
- `ntdll!NtClose` at `0x1800045db`
- `ntdll!NtClose` at `0x1800045f3`
- `ntdll!NtClose` at `0x18000460b`
- `ntdll!NtClose` at `0x180004623`
- `ntdll!NtClose` at `0x18000463b`
- `ntdll!RtlDeleteCriticalSection` at `0x1800044d3`
- `ntdll!RtlDeleteCriticalSection` at `0x1800044d3`
- `ntdll!EtwEventUnregister` at `0x180004658`
- `ntdll!EtwEventUnregister` at `0x180004658`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000468f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800044eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004503`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000451b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004533`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800044eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004503`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000451b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004533`

## pseudocode

```c
ULONG UserServerCleanup()
{
  REGHANDLE v0; // rcx

  RtlDeleteCriticalSection(&gcsUserSrv);
  if ( gpwszaSUCCESS )
    LocalFree(gpwszaSUCCESS);
  if ( gpwszaSYSTEM_INFORMATION )
    LocalFree(gpwszaSYSTEM_INFORMATION);
  if ( gpwszaSYSTEM_WARNING )
    LocalFree(gpwszaSYSTEM_WARNING);
  if ( gpwszaSYSTEM_ERROR )
    LocalFree(gpwszaSYSTEM_ERROR);
  if ( gheventCancel )
    NtClose(gheventCancel);
  if ( gheventCancelled )
    NtClose(gheventCancelled);
  if ( ghPowerRequestEvent )
    NtClose(ghPowerRequestEvent);
  if ( ghMediaRequestEvent )
    NtClose(ghMediaRequestEvent);
  if ( ghNlsEvent )
    NtClose(ghNlsEvent);
  if ( ghFontChangeEventHKLM )
    NtClose(ghFontChangeEventHKLM);
  if ( ghFontChangeEventHKCU )
    NtClose(ghFontChangeEventHKCU);
  if ( ghFontLinkChangeEvent )
    NtClose(ghFontLinkChangeEvent);
  if ( ghFontRegistryHKLM )
    NtClose(ghFontRegistryHKLM);
  if ( ghFontRegistryHKCU )
    NtClose(ghFontRegistryHKCU);
  if ( ghFontLinkKey )
    NtClose(ghFontLinkKey);
  McGenEventUnregister_EventUnregister();
  if ( g_EtwRegHandle )
  {
    EtwEventUnregister();
    g_EtwRegHandle = 0;
  }
  v0 = RegHandle;
  dword_18001D0D8 = 0;
  RegHandle = 0;
  return EventUnregister(v0);
}

```

## disassembly

```asm
0x1800044c8  sub     rsp, 28h
0x1800044cc  lea     rcx, gcsUserSrv; CriticalSection
0x1800044d3  call    cs:__imp_RtlDeleteCriticalSection
0x1800044da  nop     dword ptr [rax+rax+00h]
0x1800044df  mov     rcx, cs:gpwszaSUCCESS; hMem
0x1800044e6  test    rcx, rcx
0x1800044e9  jz      short loc_1800044F7
0x1800044eb  call    cs:__imp_LocalFree
0x1800044f2  nop     dword ptr [rax+rax+00h]
0x1800044f7  mov     rcx, cs:gpwszaSYSTEM_INFORMATION; hMem
0x1800044fe  test    rcx, rcx
0x180004501  jz      short loc_18000450F
0x180004503  call    cs:__imp_LocalFree
0x18000450a  nop     dword ptr [rax+rax+00h]
0x18000450f  mov     rcx, cs:gpwszaSYSTEM_WARNING; hMem
0x180004516  test    rcx, rcx
0x180004519  jz      short loc_180004527
0x18000451b  call    cs:__imp_LocalFree
0x180004522  nop     dword ptr [rax+rax+00h]
0x180004527  mov     rcx, cs:gpwszaSYSTEM_ERROR; hMem
0x18000452e  test    rcx, rcx
0x180004531  jz      short loc_18000453F
0x180004533  call    cs:__imp_LocalFree
0x18000453a  nop     dword ptr [rax+rax+00h]
0x18000453f  mov     rcx, cs:gheventCancel; Handle
0x180004546  test    rcx, rcx
0x180004549  jz      short loc_180004557
0x18000454b  call    cs:__imp_NtClose
0x180004552  nop     dword ptr [rax+rax+00h]
0x180004557  mov     rcx, cs:gheventCancelled; Handle
0x18000455e  test    rcx, rcx
0x180004561  jz      short loc_18000456F
0x180004563  call    cs:__imp_NtClose
0x18000456a  nop     dword ptr [rax+rax+00h]
0x18000456f  mov     rcx, cs:ghPowerRequestEvent; Handle
0x180004576  test    rcx, rcx
0x180004579  jz      short loc_180004587
0x18000457b  call    cs:__imp_NtClose
0x180004582  nop     dword ptr [rax+rax+00h]
0x180004587  mov     rcx, cs:ghMediaRequestEvent; Handle
0x18000458e  test    rcx, rcx
0x180004591  jz      short loc_18000459F
0x180004593  call    cs:__imp_NtClose
0x18000459a  nop     dword ptr [rax+rax+00h]
0x18000459f  mov     rcx, cs:ghNlsEvent; Handle
0x1800045a6  test    rcx, rcx
0x1800045a9  jz      short loc_1800045B7
0x1800045ab  call    cs:__imp_NtClose
0x1800045b2  nop     dword ptr [rax+rax+00h]
0x1800045b7  mov     rcx, cs:ghFontChangeEventHKLM; Handle
0x1800045be  test    rcx, rcx
0x1800045c1  jz      short loc_1800045CF
0x1800045c3  call    cs:__imp_NtClose
0x1800045ca  nop     dword ptr [rax+rax+00h]
0x1800045cf  mov     rcx, cs:ghFontChangeEventHKCU; Handle
0x1800045d6  test    rcx, rcx
0x1800045d9  jz      short loc_1800045E7
0x1800045db  call    cs:__imp_NtClose
0x1800045e2  nop     dword ptr [rax+rax+00h]
0x1800045e7  mov     rcx, cs:ghFontLinkChangeEvent; Handle
0x1800045ee  test    rcx, rcx
0x1800045f1  jz      short loc_1800045FF
0x1800045f3  call    cs:__imp_NtClose
0x1800045fa  nop     dword ptr [rax+rax+00h]
0x1800045ff  mov     rcx, cs:ghFontRegistryHKLM; Handle
0x180004606  test    rcx, rcx
0x180004609  jz      short loc_180004617
0x18000460b  call    cs:__imp_NtClose
0x180004612  nop     dword ptr [rax+rax+00h]
0x180004617  mov     rcx, cs:ghFontRegistryHKCU; Handle
0x18000461e  test    rcx, rcx
0x180004621  jz      short loc_18000462F
0x180004623  call    cs:__imp_NtClose
0x18000462a  nop     dword ptr [rax+rax+00h]
0x18000462f  mov     rcx, cs:ghFontLinkKey; Handle
0x180004636  test    rcx, rcx
0x180004639  jz      short loc_180004647
0x18000463b  call    cs:__imp_NtClose
0x180004642  nop     dword ptr [rax+rax+00h]
0x180004647  call    McGenEventUnregister_EventUnregister
0x18000464c  mov     rcx, cs:g_EtwRegHandle
0x180004653  test    rcx, rcx
0x180004656  jz      short loc_18000466F
0x180004658  call    cs:__imp_EtwEventUnregister
0x18000465f  nop     dword ptr [rax+rax+00h]
0x180004664  mov     cs:g_EtwRegHandle, 0
0x18000466f  mov     rcx, cs:RegHandle
0x180004676  mov     cs:dword_18001D0D8, 0
0x180004680  mov     cs:RegHandle, 0
0x18000468b  add     rsp, 28h
0x18000468f  jmp     cs:__imp_EventUnregister
```

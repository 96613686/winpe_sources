# DllMain

- ea: `0x18003ad70`
- end: `0x18003adeb`
- name: `DllMain`
- size: `123`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180033b34`

## callees

- `0x180001380`
- `0x180027260`
- `0x18003ad70`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18003ad90`
- `KERNEL32!InitializeCriticalSection` at `0x18003ad9d`
- `KERNEL32!InitializeCriticalSection` at `0x18003ad90`
- `KERNEL32!InitializeCriticalSection` at `0x18003ad9d`
- `KERNEL32!DeleteCriticalSection` at `0x18003adc1`
- `KERNEL32!DeleteCriticalSection` at `0x18003adce`
- `KERNEL32!DeleteCriticalSection` at `0x18003adc1`
- `KERNEL32!DeleteCriticalSection` at `0x18003adce`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18003ada6`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18003ada6`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      g_hInst = hinstDLL;
      InitializeCriticalSection(&CriticalSection);
      InitializeCriticalSection(&g_csServiceComponentHolder);
      DisableThreadLibraryCalls(hinstDLL);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1800AE1F0);
    }
  }
  else
  {
    DeleteCriticalSection(&CriticalSection);
    DeleteCriticalSection(&g_csServiceComponentHolder);
    TraceLoggingUnregister_EventUnregister(&dword_1800AE1F0);
  }
  return 1;
}

```

## disassembly

```asm
0x18003ad70  push    rbx
0x18003ad72  sub     rsp, 20h
0x18003ad76  mov     rbx, rcx
0x18003ad79  test    edx, edx
0x18003ad7b  jz      short loc_18003ADBA
0x18003ad7d  cmp     edx, 1
0x18003ad80  jnz     short loc_18003ADE0
0x18003ad82  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInst
0x18003ad89  lea     rcx, CriticalSection; lpCriticalSection
0x18003ad90  call    cs:__imp_InitializeCriticalSection
0x18003ad96  lea     rcx, ?g_csServiceComponentHolder@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003ad9d  call    cs:__imp_InitializeCriticalSection
0x18003ada3  mov     rcx, rbx; hLibModule
0x18003ada6  call    cs:__imp_DisableThreadLibraryCalls
0x18003adac  lea     rcx, dword_1800AE1F0; CallbackContext
0x18003adb3  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18003adb8  jmp     short loc_18003ADE0
0x18003adba  lea     rcx, CriticalSection; lpCriticalSection
0x18003adc1  call    cs:__imp_DeleteCriticalSection
0x18003adc7  lea     rcx, ?g_csServiceComponentHolder@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003adce  call    cs:__imp_DeleteCriticalSection
0x18003add4  lea     rcx, dword_1800AE1F0
0x18003addb  call    TraceLoggingUnregister_EventUnregister
0x18003ade0  mov     eax, 1
0x18003ade5  add     rsp, 20h
0x18003ade9  pop     rbx
0x18003adea  retn
```

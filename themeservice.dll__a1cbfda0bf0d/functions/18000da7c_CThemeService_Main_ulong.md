# CThemeService::Main(ulong)

- ea: `0x18000da7c`
- end: `0x18000daeb`
- name: `?Main@CThemeService@@SAHK@Z`
- size: `111`
- prototype: `_BOOL8 __fastcall(int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000a48c`

## callees

- `0x18000c174`
- `0x18000c290`
- `0x18000da7c`
- `0x18000ddb8`
- `0x18000ddf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000daa4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000daa4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dacc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dacc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000daae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000daae`

## pseudocode

```c
_BOOL8 __fastcall CThemeService::Main(int a1)
{
  int v1; // ebx
  signed int LastError; // eax

  if ( !a1 )
  {
    DeleteCriticalSection(&g_csThemeService);
    CThemeManagerAPIRequest::StaticTerminate();
    McGenEventUnregister_EventUnregister();
    goto LABEL_9;
  }
  if ( a1 != 1 )
    goto LABEL_9;
  McGenEventRegister_EventRegister();
  v1 = CThemeManagerAPIRequest::StaticInitialize();
  if ( v1 < 0 )
    return v1 >= 0;
  if ( InitializeCriticalSectionAndSpinCount(&g_csThemeService, 0) )
  {
LABEL_9:
    v1 = 0;
    return v1 >= 0;
  }
  LastError = GetLastError();
  v1 = -1073283072;
  if ( LastError <= 0 )
    v1 = LastError;
  CThemeManagerAPIRequest::StaticTerminate();
  return v1 >= 0;
}

```

## disassembly

```asm
0x18000da7c  push    rbx
0x18000da7e  sub     rsp, 20h
0x18000da82  test    ecx, ecx
0x18000da84  jz      short loc_18000DAC5
0x18000da86  cmp     ecx, 1
0x18000da89  jnz     short loc_18000DADC
0x18000da8b  call    McGenEventRegister_EventRegister
0x18000da90  call    ?StaticInitialize@CThemeManagerAPIRequest@@SAJXZ; CThemeManagerAPIRequest::StaticInitialize(void)
0x18000da95  mov     ebx, eax
0x18000da97  test    eax, eax
0x18000da99  js      short loc_18000DADE
0x18000da9b  xor     edx, edx; dwSpinCount
0x18000da9d  lea     rcx, ?g_csThemeService@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000daa4  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000daaa  test    eax, eax
0x18000daac  jnz     short loc_18000DADC
0x18000daae  call    cs:__imp_GetLastError
0x18000dab4  test    eax, eax
0x18000dab6  mov     ebx, 0C0070000h
0x18000dabb  cmovle  ebx, eax
0x18000dabe  call    ?StaticTerminate@CThemeManagerAPIRequest@@SAJXZ; CThemeManagerAPIRequest::StaticTerminate(void)
0x18000dac3  jmp     short loc_18000DADE
0x18000dac5  lea     rcx, ?g_csThemeService@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dacc  call    cs:__imp_DeleteCriticalSection
0x18000dad2  call    ?StaticTerminate@CThemeManagerAPIRequest@@SAJXZ; CThemeManagerAPIRequest::StaticTerminate(void)
0x18000dad7  call    McGenEventUnregister_EventUnregister
0x18000dadc  xor     ebx, ebx
0x18000dade  not     ebx
0x18000dae0  shr     ebx, 1Fh
0x18000dae3  mov     eax, ebx
0x18000dae5  add     rsp, 20h
0x18000dae9  pop     rbx
0x18000daea  retn
```

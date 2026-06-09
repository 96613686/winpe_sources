# DllMain

- ea: `0x18000af64`
- end: `0x18000b043`
- name: `DllMain`
- size: `223`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800245e4`

## callees

- `0x180005b40`
- `0x18000af64`
- `0x18000b04c`
- `0x18000b1f0`
- `0x18000b254`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x18000afd1`
- `ntdll!RtlInitializeCriticalSection` at `0x18000afd1`
- `ntdll!RtlDeleteCriticalSection` at `0x18000b022`
- `ntdll!RtlDeleteCriticalSection` at `0x18000b022`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000af86`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000af86`

## string_xrefs

- `0x18000af92`: `DLL_PROCESS_ATTACH`
- `0x18000b005`: `DLL_PROCESS_DETTACH`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  int v3; // ebx
  int v5; // ecx

  _InterlockedCompareExchange(&dword_18005A668, 1, 0);
  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    _DbgPrintMessage(1, "DLL_PROCESS_ATTACH");
    v3 = _tsrpcInitialize();
    if ( v3 )
    {
      v3 = RtlInitializeCriticalSection(&g_WstHandleLock) >= 0;
      g_bWstHandleLock = v3;
    }
  }
  else
  {
    v3 = 1;
    if ( !fdwReason )
    {
      _DbgPrintMessage(1, "DLL_PROCESS_DETTACH", lpvReserved);
      if ( g_bWstHandleLock )
      {
        RtlDeleteCriticalSection(&g_WstHandleLock);
        g_bWstHandleLock = 0;
      }
      _tsrpcUnInitialize(v5);
      UnregisterTraceLoggingProvider();
    }
  }
  _InterlockedCompareExchange(&dword_18005A668, 0, 1);
  return v3;
}

```

## disassembly

```asm
0x18000af64  mov     [rsp+arg_0], rbx
0x18000af69  mov     [rsp+arg_8], rsi
0x18000af6e  push    rdi
0x18000af6f  sub     rsp, 30h
0x18000af73  mov     esi, 1
0x18000af78  xor     eax, eax
0x18000af7a  lock cmpxchg cs:dword_18005A668, esi
0x18000af82  cmp     edx, esi
0x18000af84  jnz     short loc_18000AFFD
0x18000af86  call    cs:__imp_DisableThreadLibraryCalls
0x18000af8d  nop     dword ptr [rax+rax+00h]
0x18000af92  lea     rdx, aDllProcessAtta; "DLL_PROCESS_ATTACH"
0x18000af99  mov     ecx, esi; int
0x18000af9b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000afa0  call    ?_tsrpcInitialize@@YAHXZ; _tsrpcInitialize(void)
0x18000afa5  mov     ebx, eax
0x18000afa7  xor     edi, edi
0x18000afa9  test    eax, eax
0x18000afab  jnz     short loc_18000AFCA
0x18000afad  mov     eax, esi
0x18000afaf  lock cmpxchg cs:dword_18005A668, edi
0x18000afb7  mov     eax, ebx
0x18000afb9  mov     rbx, [rsp+38h+arg_0]
0x18000afbe  mov     rsi, [rsp+38h+arg_8]
0x18000afc3  add     rsp, 30h
0x18000afc7  pop     rdi
0x18000afc8  retn
0x18000afca  lea     rcx, ?g_WstHandleLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000afd1  call    cs:__imp_RtlInitializeCriticalSection
0x18000afd8  nop     dword ptr [rax+rax+00h]
0x18000afdd  mov     ebx, eax
0x18000afdf  not     ebx
0x18000afe1  shr     ebx, 1Fh
0x18000afe4  mov     cs:?g_bWstHandleLock@@3HA, ebx; int g_bWstHandleLock
0x18000afea  mov     [rsp+38h+var_18], ebx
0x18000afee  jmp     short loc_18000AFAD
0x18000aff0  xor     ebx, ebx
0x18000aff2  mov     [rsp+38h+var_18], ebx
0x18000aff6  lea     esi, [rbx+1]
0x18000aff9  xor     edi, edi
0x18000affb  jmp     short loc_18000AFAD
0x18000affd  mov     ebx, esi
0x18000afff  xor     edi, edi
0x18000b001  test    edx, edx
0x18000b003  jnz     short loc_18000AFAD
0x18000b005  lea     rdx, aDllProcessDett; "DLL_PROCESS_DETTACH"
0x18000b00c  mov     ecx, esi; int
0x18000b00e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b013  cmp     cs:?g_bWstHandleLock@@3HA, edi; int g_bWstHandleLock
0x18000b019  jz      short loc_18000B034
0x18000b01b  lea     rcx, ?g_WstHandleLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000b022  call    cs:__imp_RtlDeleteCriticalSection
0x18000b029  nop     dword ptr [rax+rax+00h]
0x18000b02e  mov     cs:?g_bWstHandleLock@@3HA, edi; int g_bWstHandleLock
0x18000b034  call    ?_tsrpcUnInitialize@@YAHH@Z; _tsrpcUnInitialize(int)
0x18000b039  call    ?UnregisterTraceLoggingProvider@@YAXXZ; UnregisterTraceLoggingProvider(void)
0x18000b03e  jmp     loc_18000AFAD
```

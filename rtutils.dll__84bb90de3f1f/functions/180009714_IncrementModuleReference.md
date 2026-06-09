# IncrementModuleReference

- ea: `0x180009714`
- end: `0x180009807`
- name: `IncrementModuleReference`
- size: `243`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001c20`

## callees

- `0x180003bb0`
- `0x180009714`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009764`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009786`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009764`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009786`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000973f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000973f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800097a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009792`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800097dc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800097dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x1800097c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x1800097c1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000976e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000976e`

## pseudocode

```c
HMODULE IncrementModuleReference()
{
  HANDLE EventA; // rax
  void *v1; // rdi
  void *v2; // rax
  DWORD v3; // ebx
  DWORD ModuleFileNameA; // eax
  CHAR Filename[272]; // [rsp+20h] [rbp-128h] BYREF

  EventA = CreateEventA(0, 1, 0, 0);
  v1 = EventA;
  if ( !EventA )
    return 0;
  v2 = (void *)_InterlockedCompareExchange64(&g_loadevent, (signed __int64)EventA, 0);
  if ( v2 )
  {
    if ( v2 == (void *)-1LL )
    {
      v3 = 0;
    }
    else
    {
      v3 = WaitForSingleObject(v2, 0xFFFFFFFF);
      if ( v3 && GetLastError() == 6 )
        v3 = 0;
    }
  }
  else
  {
    v3 = WaitForSingleObject(v1, 0xFFFFFFFF);
    Sleep(0);
  }
  CloseHandle(v1);
  if ( v3 )
    return 0;
  ModuleFileNameA = GetModuleFileNameA(g_module, Filename, 0x105u);
  if ( !ModuleFileNameA || ModuleFileNameA == 261 )
    return 0;
  else
    return LoadLibraryExA(Filename, 0, 0x800u);
}

```

## disassembly

```asm
0x180009714  mov     [rsp+arg_0], rbx
0x180009719  push    rdi
0x18000971a  sub     rsp, 140h
0x180009721  mov     rax, cs:__security_cookie
0x180009728  xor     rax, rsp
0x18000972b  mov     [rsp+148h+var_18], rax
0x180009733  xor     r9d, r9d; lpName
0x180009736  xor     r8d, r8d; bInitialState
0x180009739  xor     ecx, ecx; lpEventAttributes
0x18000973b  lea     edx, [r9+1]; bManualReset
0x18000973f  call    cs:__imp_CreateEventA
0x180009745  mov     rdi, rax
0x180009748  test    rax, rax
0x18000974b  jz      loc_1800097E4
0x180009751  xor     eax, eax
0x180009753  lock cmpxchg cs:g_loadevent, rdi
0x18000975c  jnz     short loc_180009776
0x18000975e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009761  mov     rcx, rdi; hHandle
0x180009764  call    cs:__imp_WaitForSingleObject
0x18000976a  xor     ecx, ecx; dwMilliseconds
0x18000976c  mov     ebx, eax
0x18000976e  call    cs:__imp_Sleep
0x180009774  jmp     short loc_1800097A0
0x180009776  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000977a  jnz     short loc_180009780
0x18000977c  xor     ebx, ebx
0x18000977e  jmp     short loc_1800097A0
0x180009780  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009783  mov     rcx, rax; hHandle
0x180009786  call    cs:__imp_WaitForSingleObject
0x18000978c  mov     ebx, eax
0x18000978e  test    eax, eax
0x180009790  jz      short loc_1800097A0
0x180009792  call    cs:__imp_GetLastError
0x180009798  xor     ecx, ecx
0x18000979a  cmp     eax, 6
0x18000979d  cmovz   ebx, ecx
0x1800097a0  mov     rcx, rdi; hObject
0x1800097a3  call    cs:__imp_CloseHandle
0x1800097a9  test    ebx, ebx
0x1800097ab  jnz     short loc_1800097E4
0x1800097ad  mov     rcx, cs:g_module; hModule
0x1800097b4  lea     rdx, [rsp+148h+Filename]; lpFilename
0x1800097b9  mov     ebx, 105h
0x1800097be  mov     r8d, ebx; nSize
0x1800097c1  call    cs:__imp_GetModuleFileNameA
0x1800097c7  test    eax, eax
0x1800097c9  jz      short loc_1800097E4
0x1800097cb  cmp     eax, ebx
0x1800097cd  jz      short loc_1800097E4
0x1800097cf  xor     edx, edx; hFile
0x1800097d1  lea     rcx, [rsp+148h+Filename]; lpLibFileName
0x1800097d6  mov     r8d, 800h; dwFlags
0x1800097dc  call    cs:__imp_LoadLibraryExA
0x1800097e2  jmp     short loc_1800097E6
0x1800097e4  xor     eax, eax
0x1800097e6  mov     rcx, [rsp+148h+var_18]
0x1800097ee  xor     rcx, rsp; StackCookie
0x1800097f1  call    __security_check_cookie
0x1800097f6  mov     rbx, [rsp+148h+arg_0]
0x1800097fe  add     rsp, 140h
0x180009805  pop     rdi
0x180009806  retn
```

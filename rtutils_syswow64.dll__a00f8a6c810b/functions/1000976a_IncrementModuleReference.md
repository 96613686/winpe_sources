# IncrementModuleReference()

- ea: `0x1000976a`
- end: `0x10009836`
- name: `_IncrementModuleReference@0`
- size: `204`
- prototype: `_DWORD __stdcall()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10002160`

## callees

- `0x10003c20`
- `0x1000976a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x100097ad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x100097ca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x100097ad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x100097ca`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10009789`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10009789`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100097e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100097e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100097d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100097d6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1000981d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1000981d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x10009802`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x10009802`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x100097b6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x100097b6`

## pseudocode

```c
HMODULE __stdcall IncrementModuleReference()
{
  HANDLE EventA; // eax
  void *v1; // edi
  void *v2; // eax
  DWORD v3; // esi
  DWORD ModuleFileNameA; // eax
  CHAR Filename[264]; // [esp+Ch] [ebp-10Ch] BYREF

  EventA = CreateEventA(0, 1, 0, 0);
  v1 = EventA;
  if ( !EventA )
    return 0;
  v2 = (void *)_InterlockedCompareExchange(&g_loadevent, (signed __int32)EventA, 0);
  if ( v2 )
  {
    if ( v2 == (void *)-1 )
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
0x1000976a  mov     edi, edi
0x1000976c  push    ebp
0x1000976d  mov     ebp, esp
0x1000976f  sub     esp, 10Ch
0x10009775  mov     eax, ___security_cookie
0x1000977a  xor     eax, ebp
0x1000977c  mov     [ebp+var_4], eax
0x1000977f  push    ebx
0x10009780  push    esi
0x10009781  push    edi
0x10009782  xor     ebx, ebx
0x10009784  push    ebx; lpName
0x10009785  push    ebx; bInitialState
0x10009786  push    1; bManualReset
0x10009788  push    ebx; lpEventAttributes
0x10009789  call    ds:__imp__CreateEventA@16; CreateEventA(x,x,x,x)
0x1000978f  mov     edi, eax
0x10009791  test    edi, edi
0x10009793  jz      loc_10009825
0x10009799  mov     ecx, edi
0x1000979b  mov     edx, offset _g_loadevent
0x100097a0  xor     eax, eax
0x100097a2  lock cmpxchg [edx], ecx
0x100097a6  test    eax, eax
0x100097a8  jnz     short loc_100097BE
0x100097aa  push    0FFFFFFFFh; dwMilliseconds
0x100097ac  push    edi; hHandle
0x100097ad  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x100097b3  push    ebx; dwMilliseconds
0x100097b4  mov     esi, eax
0x100097b6  call    ds:__imp__Sleep@4; Sleep(x)
0x100097bc  jmp     short loc_100097E4
0x100097be  cmp     eax, 0FFFFFFFFh
0x100097c1  jnz     short loc_100097C7
0x100097c3  mov     esi, ebx
0x100097c5  jmp     short loc_100097E4
0x100097c7  push    0FFFFFFFFh; dwMilliseconds
0x100097c9  push    eax; hHandle
0x100097ca  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x100097d0  mov     esi, eax
0x100097d2  test    esi, esi
0x100097d4  jz      short loc_100097E4
0x100097d6  call    ds:__imp__GetLastError@0; GetLastError()
0x100097dc  xor     ecx, ecx
0x100097de  cmp     eax, 6
0x100097e1  cmovz   esi, ecx
0x100097e4  push    edi; hObject
0x100097e5  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100097eb  test    esi, esi
0x100097ed  jnz     short loc_10009825
0x100097ef  mov     esi, 105h
0x100097f4  lea     eax, [ebp+Filename]
0x100097fa  push    esi; nSize
0x100097fb  push    eax; lpFilename
0x100097fc  push    _g_module; hModule
0x10009802  call    ds:__imp__GetModuleFileNameA@12; GetModuleFileNameA(x,x,x)
0x10009808  test    eax, eax
0x1000980a  jz      short loc_10009825
0x1000980c  cmp     eax, esi
0x1000980e  jz      short loc_10009825
0x10009810  push    800h; dwFlags
0x10009815  push    ebx; hFile
0x10009816  lea     eax, [ebp+Filename]
0x1000981c  push    eax; lpLibFileName
0x1000981d  call    ds:__imp__LoadLibraryExA@12; LoadLibraryExA(x,x,x)
0x10009823  jmp     short loc_10009827
0x10009825  xor     eax, eax
0x10009827  mov     ecx, [ebp+var_4]
0x1000982a  pop     edi
0x1000982b  pop     esi
0x1000982c  xor     ecx, ebp; StackCookie
0x1000982e  pop     ebx
0x1000982f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10009834  leave
0x10009835  retn
```

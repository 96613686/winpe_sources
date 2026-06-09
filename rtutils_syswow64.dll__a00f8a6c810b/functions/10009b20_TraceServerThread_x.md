# TraceServerThread(x)

- ea: `0x10009b20`
- end: `0x10009dc9`
- name: `_TraceServerThread@4`
- size: `681`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x100022f0`
- `0x100027e0`
- `0x1000983c`
- `0x10009977`
- `0x10009b20`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10009cdc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10009cdc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10009b54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10009b6f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10009b54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10009b6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10009b4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10009b68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10009cd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10009b4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10009b68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10009cd5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x10009d1a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x10009d1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10009bd1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10009be2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10009d91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10009bd1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10009be2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10009d91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10009bd8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10009bd8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10009cf5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10009cf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10009cc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10009cc7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x10009dc3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x10009dc3`

## pseudocode

```c
void __stdcall __noreturn TraceServerThread(char *Parameter)
{
  HANDLE ProcessHeap; // eax
  LPVOID v2; // eax
  HANDLE v3; // eax
  LPVOID v4; // eax
  char *v5; // eax
  char *i; // edi
  volatile signed __int32 *v7; // ebx
  int v8; // eax
  char *v9; // ecx
  int v10; // edi
  char *v11; // eax
  int v12; // edx
  char *v13; // eax
  char *v14; // edi
  int v15; // edx
  char *v16; // eax
  char **v17; // ecx
  HANDLE v18; // eax
  unsigned int v19; // edi
  int v20; // edx
  char *lpMem; // [esp+Ch] [ebp-21Ch]
  HANDLE hObject; // [esp+10h] [ebp-218h]
  unsigned int v23; // [esp+1Ch] [ebp-20Ch]
  int v24; // [esp+20h] [ebp-208h]
  _DWORD v25[64]; // [esp+24h] [ebp-204h]
  _DWORD v26[64]; // [esp+124h] [ebp-104h] BYREF

  _InterlockedExchange((volatile __int32 *)Parameter + 8, *((_DWORD *)Parameter + 8) | 0x10);
  ProcessHeap = GetProcessHeap();
  v2 = HeapAlloc(ProcessHeap, 0, 0x1388u);
  if ( v2 )
    _InterlockedExchange((volatile __int32 *)&g_FormatBuffer, (__int32)v2);
  v3 = GetProcessHeap();
  v4 = HeapAlloc(v3, 0, 0x1388u);
  if ( v4 )
    _InterlockedExchange((volatile __int32 *)&g_PrintBuffer, (__int32)v4);
  AcquireWriteLock((LPCRITICAL_SECTION)Parameter);
  v5 = Parameter + 548;
  for ( i = Parameter + 308; i < v5; i += 4 )
  {
    if ( *(_DWORD *)i && (*(_BYTE *)(*(_DWORD *)i + 32) & 1) == 0 )
    {
      TraceEnableClientA(0);
      v5 = Parameter + 548;
    }
  }
  v7 = (volatile signed __int32 *)(Parameter + 24);
  *((_DWORD *)Parameter + 6) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)Parameter);
  while ( 1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)Parameter);
    _InterlockedIncrement(v7);
    LeaveCriticalSection((LPCRITICAL_SECTION)Parameter);
    v8 = *((_DWORD *)Parameter + 12);
    if ( !v8 || v8 == -1 )
    {
      v24 = 1;
      v26[0] = 0;
    }
    else
    {
      v24 = 0;
      v26[0] = *((_DWORD *)Parameter + 12);
    }
    v26[1] = *((_DWORD *)Parameter + 13);
    v26[2] = *((_DWORD *)Parameter + 14);
    v9 = Parameter + 308;
    v10 = 3;
    v23 = 3;
    if ( Parameter + 308 < Parameter + 548 )
    {
      v11 = Parameter + 548;
      do
      {
        v12 = *(_DWORD *)v9;
        if ( *(_DWORD *)v9 && (*(_BYTE *)(v12 + 32) & 8) != 0 )
        {
          v25[v10] = (v9 - (Parameter + 308)) >> 2;
          v26[v10++] = *(_DWORD *)(v12 + 1040);
          v11 = Parameter + 548;
        }
        v9 += 4;
      }
      while ( v9 < v11 );
      v23 = v10;
    }
    v13 = Parameter + 60;
    v14 = (char *)*((_DWORD *)Parameter + 15);
    while ( v14 != v13 )
    {
      v15 = *(_DWORD *)v14;
      hObject = (HANDLE)*((_DWORD *)v14 + 2);
      v16 = v14;
      lpMem = v14;
      v14 = (char *)v15;
      v17 = (char **)*((_DWORD *)lpMem + 1);
      if ( *(char **)(v15 + 4) != lpMem || *v17 != v16 )
        __fastfail(3u);
      *v17 = (char *)v15;
      *(_DWORD *)(v15 + 4) = v17;
      CloseHandle(hObject);
      v18 = GetProcessHeap();
      HeapFree(v18, 0, lpMem);
      v13 = Parameter + 60;
    }
    if ( _InterlockedExchangeAdd(v7, 0xFFFFFFFF) < 0 )
      SetEvent(*((HANDLE *)Parameter + 7));
    v19 = v24 + WaitForMultipleObjectsEx(v23 - v24, (const HANDLE *)&v26[v24], 0, 0xFFFFFFFF, 0);
    if ( !v19 )
      break;
    if ( v19 == 1 )
    {
      TraceCleanUpServer(Parameter);
      FreeLibraryAndExitThread(g_moduleRef, 0);
    }
    if ( v19 > 2 && v19 <= v23 )
    {
      _mm_lfence();
      AcquireWriteLock((LPCRITICAL_SECTION)Parameter);
      v20 = *(_DWORD *)&Parameter[4 * v25[v19] + 308];
      if ( v20 && (*(_BYTE *)(v20 + 32) & 1) == 0 )
        TraceEnableClientA(0);
LABEL_37:
      *((_DWORD *)Parameter + 6) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)Parameter);
      v7 = (volatile signed __int32 *)(Parameter + 24);
    }
  }
  AcquireWriteLock((LPCRITICAL_SECTION)Parameter);
  if ( *((_DWORD *)Parameter + 12) )
  {
    if ( *((_DWORD *)Parameter + 12) != -1 )
      TraceProcessConsoleInput(Parameter);
  }
  goto LABEL_37;
}

```

## disassembly

```asm
0x10009b20  mov     edi, edi
0x10009b22  push    ebp
0x10009b23  mov     ebp, esp
0x10009b25  sub     esp, 21Ch
0x10009b2b  mov     eax, ___security_cookie
0x10009b30  xor     eax, ebp
0x10009b32  mov     [ebp+var_4], eax
0x10009b35  push    ebx
0x10009b36  push    esi
0x10009b37  mov     esi, [ebp+Parameter]
0x10009b3a  push    edi
0x10009b3b  lea     ecx, [esi+20h]
0x10009b3e  mov     eax, [ecx]
0x10009b40  or      eax, 10h
0x10009b43  xchg    eax, [ecx]
0x10009b45  mov     edi, 1388h
0x10009b4a  push    edi; dwBytes
0x10009b4b  push    0; dwFlags
0x10009b4d  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10009b53  push    eax; hHeap
0x10009b54  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x10009b5a  test    eax, eax
0x10009b5c  jz      short loc_10009B65
0x10009b5e  mov     ecx, offset _g_FormatBuffer
0x10009b63  xchg    eax, [ecx]
0x10009b65  push    edi; dwBytes
0x10009b66  push    0; dwFlags
0x10009b68  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10009b6e  push    eax; hHeap
0x10009b6f  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x10009b75  test    eax, eax
0x10009b77  jz      short loc_10009B80
0x10009b79  mov     ecx, offset _g_PrintBuffer
0x10009b7e  xchg    eax, [ecx]
0x10009b80  lea     ebx, [esi+134h]
0x10009b86  mov     ecx, esi; lpCriticalSection
0x10009b88  mov     [ebp+var_214], ebx
0x10009b8e  call    _AcquireWriteLock@4; AcquireWriteLock(x)
0x10009b93  lea     eax, [esi+224h]
0x10009b99  mov     edi, ebx
0x10009b9b  cmp     ebx, eax
0x10009b9d  jnb     short loc_10009BC1
0x10009b9f  mov     edx, [edi]
0x10009ba1  test    edx, edx
0x10009ba3  jz      short loc_10009BBA
0x10009ba5  test    byte ptr [edx+20h], 1
0x10009ba9  jnz     short loc_10009BBA
0x10009bab  push    0
0x10009bad  mov     ecx, esi
0x10009baf  call    _TraceEnableClientA@12; TraceEnableClientA(x,x,x)
0x10009bb4  lea     eax, [esi+224h]
0x10009bba  add     edi, 4
0x10009bbd  cmp     edi, eax
0x10009bbf  jb      short loc_10009B9F
0x10009bc1  lea     ebx, [esi+18h]
0x10009bc4  push    esi; lpCriticalSection
0x10009bc5  mov     [ebp+var_210], ebx
0x10009bcb  mov     dword ptr [ebx], 0
0x10009bd1  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10009bd7  push    esi; lpCriticalSection
0x10009bd8  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10009bde  lock inc dword ptr [ebx]
0x10009be1  push    esi; lpCriticalSection
0x10009be2  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10009be8  mov     eax, [esi+30h]
0x10009beb  test    eax, eax
0x10009bed  jz      short loc_10009C06
0x10009bef  cmp     eax, 0FFFFFFFFh
0x10009bf2  jz      short loc_10009C06
0x10009bf4  mov     [ebp+var_208], 0
0x10009bfe  mov     [ebp+var_104], eax
0x10009c04  jmp     short loc_10009C1A
0x10009c06  mov     [ebp+var_208], 1
0x10009c10  mov     [ebp+var_104], 0
0x10009c1a  mov     eax, [esi+34h]
0x10009c1d  lea     edx, [esi+224h]
0x10009c23  mov     [ebp+var_100], eax
0x10009c29  mov     eax, [esi+38h]
0x10009c2c  mov     [ebp+var_FC], eax
0x10009c32  lea     eax, [esi+134h]
0x10009c38  mov     ecx, eax
0x10009c3a  push    3
0x10009c3c  pop     edi
0x10009c3d  mov     [ebp+var_20C], edi
0x10009c43  cmp     eax, edx
0x10009c45  jnb     short loc_10009C8C
0x10009c47  lea     eax, [esi+224h]
0x10009c4d  mov     edx, [ecx]
0x10009c4f  test    edx, edx
0x10009c51  jz      short loc_10009C7F
0x10009c53  test    byte ptr [edx+20h], 8
0x10009c57  jz      short loc_10009C7F
0x10009c59  mov     eax, ecx
0x10009c5b  sub     eax, [ebp+var_214]
0x10009c61  sar     eax, 2
0x10009c64  mov     [ebp+edi*4+var_204], eax
0x10009c6b  mov     eax, [edx+410h]
0x10009c71  mov     [ebp+edi*4+var_104], eax
0x10009c78  inc     edi
0x10009c79  lea     eax, [esi+224h]
0x10009c7f  add     ecx, 4
0x10009c82  cmp     ecx, eax
0x10009c84  jb      short loc_10009C4D
0x10009c86  mov     [ebp+var_20C], edi
0x10009c8c  lea     eax, [esi+3Ch]
0x10009c8f  mov     edi, [eax]
0x10009c91  jmp     short loc_10009CE5
0x10009c93  mov     eax, [edi+8]
0x10009c96  mov     edx, [edi]
0x10009c98  mov     [ebp+hObject], eax
0x10009c9e  mov     eax, edi
0x10009ca0  mov     [ebp+lpMem], eax
0x10009ca6  mov     edi, edx
0x10009ca8  mov     ecx, [eax+4]
0x10009cab  cmp     [edx+4], eax
0x10009cae  jnz     loc_10009DAF
0x10009cb4  cmp     [ecx], eax
0x10009cb6  jnz     loc_10009DAF
0x10009cbc  push    [ebp+hObject]; hObject
0x10009cc2  mov     [ecx], edx
0x10009cc4  mov     [edx+4], ecx
0x10009cc7  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10009ccd  push    [ebp+lpMem]; lpMem
0x10009cd3  push    0; dwFlags
0x10009cd5  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10009cdb  push    eax; hHeap
0x10009cdc  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x10009ce2  lea     eax, [esi+3Ch]
0x10009ce5  cmp     edi, eax
0x10009ce7  jnz     short loc_10009C93
0x10009ce9  or      eax, 0FFFFFFFFh
0x10009cec  lock xadd [ebx], eax
0x10009cf0  jns     short loc_10009CFB
0x10009cf2  push    dword ptr [esi+1Ch]; hEvent
0x10009cf5  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10009cfb  mov     ecx, [ebp+var_208]
0x10009d01  lea     eax, [ebp+var_104]
0x10009d07  push    0; bAlertable
0x10009d09  push    0FFFFFFFFh; dwMilliseconds
0x10009d0b  push    0; bWaitAll
0x10009d0d  lea     eax, [eax+ecx*4]
0x10009d10  push    eax; lpHandles
0x10009d11  mov     eax, [ebp+var_20C]
0x10009d17  sub     eax, ecx
0x10009d19  push    eax; nCount
0x10009d1a  call    ds:__imp__WaitForMultipleObjectsEx@20; WaitForMultipleObjectsEx(x,x,x,x,x)
0x10009d20  mov     edi, eax
0x10009d22  add     edi, [ebp+var_208]
0x10009d28  jnz     short loc_10009D45
0x10009d2a  mov     ecx, esi; lpCriticalSection
0x10009d2c  call    _AcquireWriteLock@4; AcquireWriteLock(x)
0x10009d31  cmp     [esi+30h], edi
0x10009d34  jz      short loc_10009D84
0x10009d36  cmp     dword ptr [esi+30h], 0FFFFFFFFh
0x10009d3a  jz      short loc_10009D84
0x10009d3c  mov     ecx, esi
0x10009d3e  call    _TraceProcessConsoleInput@4; TraceProcessConsoleInput(x)
0x10009d43  jmp     short loc_10009D84
0x10009d45  cmp     edi, 1
0x10009d48  jz      short loc_10009DB4
0x10009d4a  cmp     edi, 2
0x10009d4d  jz      loc_10009BD7
0x10009d53  cmp     edi, 3
0x10009d56  jb      loc_10009BD7
0x10009d5c  cmp     edi, [ebp+var_20C]
0x10009d62  ja      loc_10009BD7
0x10009d68  mov     ecx, esi; lpCriticalSection
0x10009d6a  lfence
0x10009d6d  call    _AcquireWriteLock@4; AcquireWriteLock(x)
0x10009d72  mov     eax, [ebp+edi*4+var_204]
0x10009d79  mov     edx, [esi+eax*4+134h]
0x10009d80  test    edx, edx
0x10009d82  jnz     short loc_10009D9E
0x10009d84  mov     edi, [ebp+var_210]
0x10009d8a  push    esi; lpCriticalSection
0x10009d8b  mov     dword ptr [edi], 0
0x10009d91  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10009d97  mov     ebx, edi
0x10009d99  jmp     loc_10009BD7
0x10009d9e  test    byte ptr [edx+20h], 1
0x10009da2  jnz     short loc_10009D84
0x10009da4  push    0
0x10009da6  mov     ecx, esi
0x10009da8  call    _TraceEnableClientA@12; TraceEnableClientA(x,x,x)
0x10009dad  jmp     short loc_10009D84
0x10009daf  push    3
0x10009db1  pop     ecx
0x10009db2  int     29h; Win8: RtlFailFast(ecx)
0x10009db4  mov     ecx, esi; hMem
0x10009db6  call    _TraceCleanUpServer@4; TraceCleanUpServer(x)
0x10009dbb  push    0; dwExitCode
0x10009dbd  push    _g_moduleRef; hLibModule
0x10009dc3  call    ds:__imp__FreeLibraryAndExitThread@8; FreeLibraryAndExitThread(x,x)
```

# TraceCreateClientA(x)

- ea: `0x10002610`
- end: `0x100026eb`
- name: `_TraceCreateClientA@4`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10002470`

## callees

- `0x10002610`
- `0x10002f10`
- `0x10004567`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x100026c1`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x100026c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x100055c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x100055c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10002624`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10002624`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000261d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x100055c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000261d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x100055c1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x100026a6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x100026a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100026e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100026e3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x100026b1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x100026b1`

## pseudocode

```c
int __thiscall TraceCreateClientA(volatile __int32 *this)
{
  HANDLE ProcessHeap; // eax
  char *v3; // esi
  int v4; // eax
  DWORD LastError; // eax
  DWORD v6; // edi
  HANDLE v8; // eax

  ProcessHeap = GetProcessHeap();
  v3 = (char *)HeapAlloc(ProcessHeap, 0, 0x414u);
  if ( !v3 )
    return 8;
  *((_DWORD *)v3 + 9) = 60;
  *((_DWORD *)v3 + 8) = 0;
  *((_DWORD *)v3 + 58) = 0;
  *((_DWORD *)v3 + 59) = 0;
  *((_DWORD *)v3 + 259) = 0;
  *((_DWORD *)v3 + 260) = 0;
  *((_DWORD *)v3 + 62) = 0x100000;
  memset(v3 + 40, 0, 0x40u);
  memset(v3 + 104, 0, 0x80u);
  if ( ExpandEnvironmentStringsA("%windir%\\tracing", v3 + 252, 0x104u) )
  {
    v4 = lstrlenA(v3 + 252);
    __o_mbstowcs(v3 + 514, v3 + 252, v4 + 1);
    LastError = CreateReadWriteLock((LPCRITICAL_SECTION)v3);
  }
  else
  {
    LastError = GetLastError();
  }
  v6 = LastError;
  if ( LastError )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v3);
    v3 = 0;
  }
  _InterlockedExchange(this, (__int32)v3);
  return v6;
}

```

## disassembly

```asm
0x10002610  mov     edi, edi
0x10002612  push    ebx
0x10002613  push    esi
0x10002614  push    414h; dwBytes
0x10002619  push    0; dwFlags
0x1000261b  mov     ebx, ecx
0x1000261d  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10002623  push    eax; hHeap
0x10002624  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x1000262a  mov     esi, eax
0x1000262c  test    esi, esi
0x1000262e  jz      loc_100055B4
0x10002634  push    edi
0x10002635  push    40h ; '@'; Size
0x10002637  lea     eax, [esi+28h]
0x1000263a  mov     dword ptr [esi+24h], 3Ch ; '<'
0x10002641  push    0; Val
0x10002643  push    eax; void *
0x10002644  mov     dword ptr [esi+20h], 0
0x1000264b  mov     dword ptr [esi+0E8h], 0
0x10002655  mov     dword ptr [esi+0ECh], 0
0x1000265f  mov     dword ptr [esi+40Ch], 0
0x10002669  mov     dword ptr [esi+410h], 0
0x10002673  mov     dword ptr [esi+0F8h], 100000h
0x1000267d  call    _memset
0x10002682  push    80h; Size
0x10002687  lea     eax, [esi+68h]
0x1000268a  push    0; Val
0x1000268c  push    eax; void *
0x1000268d  call    _memset
0x10002692  add     esp, 18h
0x10002695  lea     edi, [esi+0FCh]
0x1000269b  push    104h; nSize
0x100026a0  push    edi; lpDst
0x100026a1  push    offset Src; "%windir%\\tracing"
0x100026a6  call    ds:__imp__ExpandEnvironmentStringsA@12; ExpandEnvironmentStringsA(x,x,x)
0x100026ac  test    eax, eax
0x100026ae  jz      short loc_100026E3
0x100026b0  push    edi; lpString
0x100026b1  call    ds:__imp__lstrlenA@4; lstrlenA(x)
0x100026b7  inc     eax
0x100026b8  push    eax
0x100026b9  lea     eax, [esi+202h]
0x100026bf  push    edi
0x100026c0  push    eax
0x100026c1  call    ds:__imp___o_mbstowcs
0x100026c7  add     esp, 0Ch
0x100026ca  mov     ecx, esi; lpCriticalSection
0x100026cc  call    _CreateReadWriteLock@4; CreateReadWriteLock(x)
0x100026d1  mov     edi, eax
0x100026d3  test    edi, edi
0x100026d5  jnz     loc_100055BE
0x100026db  xchg    esi, [ebx]
0x100026dd  mov     eax, edi
0x100026df  pop     edi
0x100026e0  pop     esi
0x100026e1  pop     ebx
0x100026e2  retn
0x100026e3  call    ds:__imp__GetLastError@0; GetLastError()
0x100026e9  jmp     short loc_100026D1
0x100055b4  mov     eax, 8
0x100055b9  jmp     loc_100026E0
0x100055be  push    esi; lpMem
0x100055bf  push    0; dwFlags
0x100055c1  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x100055c7  push    eax; hHeap
0x100055c8  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x100055ce  xor     esi, esi
0x100055d0  jmp     loc_100026DB
```

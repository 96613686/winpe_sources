# TraceCreateClientW(x)

- ea: `0x100031ff`
- end: `0x100032ca`
- name: `_TraceCreateClientW@4`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x100030b0`

## callees

- `0x10002f10`
- `0x100031ff`
- `0x10004567`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1000329b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1000329b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10005b6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10005b6f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10003215`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10003215`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000320e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10005b68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000320e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10005b68`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x10003280`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x10003280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100032c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100032c2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1000328b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1000328b`

## pseudocode

```c
int __thiscall TraceCreateClientW(volatile __int32 *this)
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
  if ( ExpandEnvironmentStringsW(L"%windir%\\tracing", (LPWSTR)v3 + 257, 0x104u) )
  {
    v4 = lstrlenW((LPCWSTR)v3 + 257);
    _wcstombs(v3 + 252, (const wchar_t *)v3 + 257, v4 + 1);
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
0x100031ff  mov     edi, edi
0x10003201  push    ebx
0x10003202  push    esi
0x10003203  push    edi
0x10003204  push    414h; dwBytes
0x10003209  xor     edi, edi
0x1000320b  mov     ebx, ecx
0x1000320d  push    edi; dwFlags
0x1000320e  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10003214  push    eax; hHeap
0x10003215  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x1000321b  mov     esi, eax
0x1000321d  test    esi, esi
0x1000321f  jz      loc_100032BD
0x10003225  push    40h ; '@'; Size
0x10003227  lea     eax, [esi+28h]
0x1000322a  mov     dword ptr [esi+24h], 3Ch ; '<'
0x10003231  push    edi; Val
0x10003232  push    eax; void *
0x10003233  mov     [esi+20h], edi
0x10003236  mov     [esi+0E8h], edi
0x1000323c  mov     [esi+0ECh], edi
0x10003242  mov     [esi+40Ch], edi
0x10003248  mov     [esi+410h], edi
0x1000324e  mov     dword ptr [esi+0F8h], 100000h
0x10003258  call    _memset
0x1000325d  push    80h; Size
0x10003262  lea     eax, [esi+68h]
0x10003265  push    edi; Val
0x10003266  push    eax; void *
0x10003267  call    _memset
0x1000326c  add     esp, 18h
0x1000326f  lea     edi, [esi+202h]
0x10003275  push    104h; nSize
0x1000327a  push    edi; lpDst
0x1000327b  push    offset aWindirTracing; "%windir%\\tracing"
0x10003280  call    ds:__imp__ExpandEnvironmentStringsW@12; ExpandEnvironmentStringsW(x,x,x)
0x10003286  test    eax, eax
0x10003288  jz      short loc_100032C2
0x1000328a  push    edi; lpString
0x1000328b  call    ds:__imp__lstrlenW@4; lstrlenW(x)
0x10003291  inc     eax
0x10003292  push    eax; MaxCount
0x10003293  lea     eax, [esi+0FCh]
0x10003299  push    edi; Source
0x1000329a  push    eax; Dest
0x1000329b  call    ds:__imp__wcstombs
0x100032a1  add     esp, 0Ch
0x100032a4  mov     ecx, esi; lpCriticalSection
0x100032a6  call    _CreateReadWriteLock@4; CreateReadWriteLock(x)
0x100032ab  mov     edi, eax
0x100032ad  test    edi, edi
0x100032af  jnz     loc_10005B65
0x100032b5  xchg    esi, [ebx]
0x100032b7  mov     eax, edi
0x100032b9  pop     edi
0x100032ba  pop     esi
0x100032bb  pop     ebx
0x100032bc  retn
0x100032bd  push    8
0x100032bf  pop     eax
0x100032c0  jmp     short loc_100032B9
0x100032c2  call    ds:__imp__GetLastError@0; GetLastError()
0x100032c8  jmp     short loc_100032AB
0x10005b65  push    esi; lpMem
0x10005b66  push    0; dwFlags
0x10005b68  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10005b6e  push    eax; hHeap
0x10005b6f  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x10005b75  xor     esi, esi
0x10005b77  jmp     loc_100032B5
```

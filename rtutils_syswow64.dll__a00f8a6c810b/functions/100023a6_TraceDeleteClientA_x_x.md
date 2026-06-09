# TraceDeleteClientA(x,x)

- ea: `0x100023a6`
- end: `0x10002433`
- name: `_TraceDeleteClientA@8`
- size: `141`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x10002320`
- `0x10002470`
- `0x1000983c`

## callees

- `0x100023a6`
- `0x10002439`
- `0x10006f22`
- `0x10006fac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000241a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000241a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x100054c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x100054c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10002413`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x100054be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10002413`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x100054be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100023fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100023fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100023df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100023df`

## pseudocode

```c
int __fastcall TraceDeleteClientA(int a1, volatile __int32 *a2)
{
  volatile __int32 v3; // esi
  HANDLE v4; // eax
  HANDLE ProcessHeap; // eax
  _DWORD *v7; // eax
  _DWORD *v8; // ecx
  int v9; // edx

  if ( !a2 )
    return 87;
  v3 = *a2;
  if ( !*a2 )
    return 87;
  _InterlockedExchange(a2, 0);
  _InterlockedExchange((volatile __int32 *)(a1 + 4 * (*(_DWORD *)(v3 + 36) + 17)), 0);
  if ( *(_DWORD *)(v3 + 28) )
    DeleteReadWriteLock((LPCRITICAL_SECTION)v3);
  if ( *(_DWORD *)(v3 + 1036) )
    RegCloseKey(*(HKEY *)(v3 + 1036));
  if ( *(_DWORD *)(v3 + 1040) )
  {
    if ( (*(_BYTE *)(a1 + 32) & 0x10) != 0 )
    {
      ProcessHeap = GetProcessHeap();
      v7 = HeapAlloc(ProcessHeap, 0, 0xCu);
      if ( v7 )
      {
        v7[2] = *(_DWORD *)(v3 + 1040);
        v8 = (_DWORD *)(a1 + 60);
        v9 = *(_DWORD *)(a1 + 60);
        if ( *(_DWORD *)(v9 + 4) != a1 + 60 )
          __fastfail(3u);
        *v7 = v9;
        v7[1] = v8;
        *(_DWORD *)(v9 + 4) = v7;
        *v8 = v7;
      }
    }
    else
    {
      CloseHandle(*(HANDLE *)(v3 + 1040));
    }
  }
  if ( (*(_BYTE *)(v3 + 32) & 4) != 0 )
    TraceCloseClientConsoleA(a1, v3);
  if ( (*(_BYTE *)(v3 + 32) & 2) != 0 )
    TraceCloseClientFileW(v3);
  v4 = GetProcessHeap();
  HeapFree(v4, 0, (LPVOID)v3);
  return 0;
}

```

## disassembly

```asm
0x100023a6  mov     edi, edi
0x100023a8  push    esi
0x100023a9  push    edi
0x100023aa  mov     edi, ecx
0x100023ac  test    edx, edx
0x100023ae  jz      short loc_1000242E
0x100023b0  mov     esi, [edx]
0x100023b2  test    esi, esi
0x100023b4  jz      short loc_1000242E
0x100023b6  xor     eax, eax
0x100023b8  xchg    eax, [edx]
0x100023ba  mov     eax, [esi+24h]
0x100023bd  xor     ecx, ecx
0x100023bf  add     eax, 11h
0x100023c2  lea     eax, [edi+eax*4]
0x100023c5  xchg    ecx, [eax]
0x100023c7  cmp     dword ptr [esi+1Ch], 0
0x100023cb  jz      short loc_100023D4
0x100023cd  mov     ecx, esi; lpCriticalSection
0x100023cf  call    _DeleteReadWriteLock@4; DeleteReadWriteLock(x)
0x100023d4  mov     eax, [esi+40Ch]
0x100023da  test    eax, eax
0x100023dc  jz      short loc_100023E5
0x100023de  push    eax; hKey
0x100023df  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100023e5  mov     eax, [esi+410h]
0x100023eb  test    eax, eax
0x100023ed  jz      short loc_10002400
0x100023ef  test    byte ptr [edi+20h], 10h
0x100023f3  jnz     loc_100054BA
0x100023f9  push    eax; hObject
0x100023fa  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10002400  test    byte ptr [esi+20h], 4
0x10002404  jnz     loc_100054FA
0x1000240a  test    byte ptr [esi+20h], 2
0x1000240e  jnz     short loc_10002425
0x10002410  push    esi; lpMem
0x10002411  push    0; dwFlags
0x10002413  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10002419  push    eax; hHeap
0x1000241a  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x10002420  xor     eax, eax
0x10002422  pop     edi
0x10002423  pop     esi
0x10002424  retn
0x10002425  mov     ecx, esi
0x10002427  call    _TraceCloseClientFileW@4; TraceCloseClientFileW(x)
0x1000242c  jmp     short loc_10002410
0x1000242e  push    57h ; 'W'
0x10002430  pop     eax
0x10002431  jmp     short loc_10002422
0x100054ba  push    0Ch; dwBytes
0x100054bc  push    0; dwFlags
0x100054be  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x100054c4  push    eax; hHeap
0x100054c5  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x100054cb  test    eax, eax
0x100054cd  jz      loc_10002400
0x100054d3  mov     ecx, [esi+410h]
0x100054d9  mov     [eax+8], ecx
0x100054dc  lea     ecx, [edi+3Ch]
0x100054df  mov     edx, [ecx]
0x100054e1  cmp     [edx+4], ecx
0x100054e4  jz      short loc_100054EB
0x100054e6  push    3
0x100054e8  pop     ecx
0x100054e9  int     29h; Win8: RtlFailFast(ecx)
0x100054eb  mov     [eax], edx
0x100054ed  mov     [eax+4], ecx
0x100054f0  mov     [edx+4], eax
0x100054f3  mov     [ecx], eax
0x100054f5  jmp     loc_10002400
0x100054fa  mov     edx, esi
0x100054fc  mov     ecx, edi
0x100054fe  call    _TraceCloseClientConsoleA@8; TraceCloseClientConsoleA(x,x)
0x10005503  jmp     loc_1000240A
```

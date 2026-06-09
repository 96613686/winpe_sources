# TraceDeleteClientW(x,x)

- ea: `0x10007af9`
- end: `0x10007bc6`
- name: `_TraceDeleteClientW@8`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x100030b0`
- `0x100066c0`

## callees

- `0x10002439`
- `0x10006f22`
- `0x10006fac`
- `0x10007af9`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10007bb6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10007bb6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10007b5b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10007b5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10007b54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10007baf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10007b54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10007baf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10007b8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10007b8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10007b3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10007b3a`

## pseudocode

```c
int __fastcall TraceDeleteClientW(int a1, volatile __int32 *a2)
{
  volatile __int32 v3; // esi
  HANDLE ProcessHeap; // eax
  _DWORD *v5; // eax
  _DWORD *v6; // ecx
  int v7; // edx
  HANDLE v8; // eax

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
      v5 = HeapAlloc(ProcessHeap, 0, 0xCu);
      if ( v5 )
      {
        v5[2] = *(_DWORD *)(v3 + 1040);
        v6 = (_DWORD *)(a1 + 60);
        v7 = *(_DWORD *)(a1 + 60);
        if ( *(_DWORD *)(v7 + 4) != a1 + 60 )
          __fastfail(3u);
        *v5 = v7;
        v5[1] = v6;
        *(_DWORD *)(v7 + 4) = v5;
        *v6 = v5;
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
  v8 = GetProcessHeap();
  HeapFree(v8, 0, (LPVOID)v3);
  return 0;
}

```

## disassembly

```asm
0x10007af9  mov     edi, edi
0x10007afb  push    esi
0x10007afc  push    edi
0x10007afd  mov     edi, ecx
0x10007aff  test    edx, edx
0x10007b01  jz      loc_10007BC0
0x10007b07  mov     esi, [edx]
0x10007b09  test    esi, esi
0x10007b0b  jz      loc_10007BC0
0x10007b11  xor     eax, eax
0x10007b13  xchg    eax, [edx]
0x10007b15  mov     eax, [esi+24h]
0x10007b18  xor     ecx, ecx
0x10007b1a  add     eax, 11h
0x10007b1d  lea     eax, [edi+eax*4]
0x10007b20  xchg    ecx, [eax]
0x10007b22  cmp     dword ptr [esi+1Ch], 0
0x10007b26  jz      short loc_10007B2F
0x10007b28  mov     ecx, esi; lpCriticalSection
0x10007b2a  call    _DeleteReadWriteLock@4; DeleteReadWriteLock(x)
0x10007b2f  mov     eax, [esi+40Ch]
0x10007b35  test    eax, eax
0x10007b37  jz      short loc_10007B40
0x10007b39  push    eax; hKey
0x10007b3a  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10007b40  mov     eax, [esi+410h]
0x10007b46  test    eax, eax
0x10007b48  jz      short loc_10007B90
0x10007b4a  test    byte ptr [edi+20h], 10h
0x10007b4e  jz      short loc_10007B89
0x10007b50  push    0Ch; dwBytes
0x10007b52  push    0; dwFlags
0x10007b54  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10007b5a  push    eax; hHeap
0x10007b5b  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x10007b61  test    eax, eax
0x10007b63  jz      short loc_10007B90
0x10007b65  mov     ecx, [esi+410h]
0x10007b6b  mov     [eax+8], ecx
0x10007b6e  lea     ecx, [edi+3Ch]
0x10007b71  mov     edx, [ecx]
0x10007b73  cmp     [edx+4], ecx
0x10007b76  jz      short loc_10007B7D
0x10007b78  push    3
0x10007b7a  pop     ecx
0x10007b7b  int     29h; Win8: RtlFailFast(ecx)
0x10007b7d  mov     [eax], edx
0x10007b7f  mov     [eax+4], ecx
0x10007b82  mov     [edx+4], eax
0x10007b85  mov     [ecx], eax
0x10007b87  jmp     short loc_10007B90
0x10007b89  push    eax; hObject
0x10007b8a  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10007b90  test    byte ptr [esi+20h], 4
0x10007b94  jz      short loc_10007B9F
0x10007b96  mov     edx, esi
0x10007b98  mov     ecx, edi
0x10007b9a  call    _TraceCloseClientConsoleA@8; TraceCloseClientConsoleA(x,x)
0x10007b9f  test    byte ptr [esi+20h], 2
0x10007ba3  jz      short loc_10007BAC
0x10007ba5  mov     ecx, esi
0x10007ba7  call    _TraceCloseClientFileW@4; TraceCloseClientFileW(x)
0x10007bac  push    esi; lpMem
0x10007bad  push    0; dwFlags
0x10007baf  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10007bb5  push    eax; hHeap
0x10007bb6  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x10007bbc  xor     eax, eax
0x10007bbe  jmp     short loc_10007BC3
0x10007bc0  push    57h ; 'W'
0x10007bc2  pop     eax
0x10007bc3  pop     edi
0x10007bc4  pop     esi
0x10007bc5  retn
```

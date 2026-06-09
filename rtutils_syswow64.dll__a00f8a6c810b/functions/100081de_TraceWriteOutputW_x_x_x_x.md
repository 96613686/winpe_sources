# TraceWriteOutputW(x,x,x,x)

- ea: `0x100081de`
- end: `0x1000836c`
- name: `_TraceWriteOutputW@16`
- size: `398`
- prototype: `int __stdcall(_DWORD, _DWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x100020d0`
- `0x10006b80`
- `0x10007bcc`

## callees

- `0x100022f0`
- `0x100080a7`
- `0x100081de`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1000829e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100082af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100082eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100082fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1000829e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100082af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100082eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100082fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100082a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100082f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100082a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100082f2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10008275`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10008275`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x10008355`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x10008355`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x10008327`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x10008327`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1000824e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1000828a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1000824e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1000828a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x100081f8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x100081f8`

## pseudocode

```c
DWORD __fastcall TraceWriteOutputW(int a1, int a2, int a3, const WCHAR *lpString)
{
  BOOL v5; // edi
  DWORD v6; // ebx
  int v7; // eax
  void *v8; // eax
  volatile signed __int32 *v9; // edi
  DWORD FileSize; // ecx
  DWORD result; // eax
  int v12; // eax
  void *v13; // ecx
  DWORD NumberOfCharsWritten; // [esp+Ch] [ebp-Ch] BYREF
  DWORD NumberOfBytesWritten; // [esp+10h] [ebp-8h] BYREF
  int v16; // [esp+14h] [ebp-4h]

  NumberOfBytesWritten = 0;
  v5 = 1;
  v16 = 1;
  v6 = 2 * lstrlenW(lpString);
  v7 = 1;
  if ( (a3 & 2) != 0 )
  {
    v7 = a3 & *(_DWORD *)(a2 + 240);
    v16 = a3 & *(_DWORD *)(a2 + 244);
  }
  if ( (*(_BYTE *)(a2 + 32) & 2) != 0 )
  {
    if ( v7 )
    {
      v8 = *(void **)(a2 + 232);
      if ( v8 )
      {
        if ( v8 != (void *)-1 )
        {
          if ( GetFileSize(v8, 0) > *(_DWORD *)(a2 + 248) - v6 )
          {
            v9 = (volatile signed __int32 *)(a2 + 24);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 24), 0xFFFFFFFF) < 0 )
              SetEvent(*(HANDLE *)(a2 + 28));
            AcquireWriteLock((LPCRITICAL_SECTION)a2);
            FileSize = GetFileSize(*(HANDLE *)(a2 + 232), 0);
            if ( FileSize == -1 )
              goto LABEL_11;
            if ( FileSize <= *(_DWORD *)(a2 + 248) - v6 )
            {
              v12 = *(_DWORD *)(a2 + 232);
              if ( !v12 || v12 == -1 )
                goto LABEL_11;
            }
            else if ( TraceMoveClientFileW(a2) )
            {
LABEL_11:
              *v9 = 0;
              LeaveCriticalSection((LPCRITICAL_SECTION)a2);
              EnterCriticalSection((LPCRITICAL_SECTION)a2);
              _InterlockedIncrement(v9);
              LeaveCriticalSection((LPCRITICAL_SECTION)a2);
              return 0;
            }
            *v9 = 0;
            LeaveCriticalSection((LPCRITICAL_SECTION)a2);
            EnterCriticalSection((LPCRITICAL_SECTION)a2);
            _InterlockedIncrement(v9);
            LeaveCriticalSection((LPCRITICAL_SECTION)a2);
            v5 = 1;
          }
          if ( *(_DWORD *)(a2 + 232) && *(_DWORD *)(a2 + 232) != -1 )
            v5 = WriteFile(*(HANDLE *)(a2 + 232), lpString, v6, &NumberOfBytesWritten, 0);
        }
      }
    }
  }
  if ( (*(_BYTE *)(a2 + 32) & 4) != 0 )
  {
    if ( v16 )
    {
      v13 = *(void **)(a2 + 236);
      if ( v13 )
      {
        NumberOfCharsWritten = v6 >> 1;
        v5 = WriteConsoleW(v13, lpString, v6 >> 1, &NumberOfCharsWritten, 0);
      }
    }
  }
  result = 0;
  if ( v5 )
    return NumberOfBytesWritten;
  return result;
}

```

## disassembly

```asm
0x100081de  mov     edi, edi
0x100081e0  push    ebp
0x100081e1  mov     ebp, esp
0x100081e3  sub     esp, 0Ch
0x100081e6  push    ebx
0x100081e7  push    esi
0x100081e8  push    edi
0x100081e9  push    [ebp+lpString]; lpString
0x100081ec  xor     edi, edi
0x100081ee  mov     [ebp+NumberOfBytesWritten], 0
0x100081f5  mov     esi, edx
0x100081f7  inc     edi
0x100081f8  call    ds:__imp__lstrlenW@4; lstrlenW(x)
0x100081fe  mov     ebx, eax
0x10008200  mov     [ebp+var_4], edi
0x10008203  add     ebx, ebx
0x10008205  mov     eax, edi
0x10008207  test    byte ptr [ebp+arg_0], 2
0x1000820b  jz      short loc_10008222
0x1000820d  mov     eax, [esi+0F0h]
0x10008213  mov     ecx, [esi+0F4h]
0x10008219  and     eax, [ebp+arg_0]
0x1000821c  and     ecx, [ebp+arg_0]
0x1000821f  mov     [ebp+var_4], ecx
0x10008222  test    byte ptr [esi+20h], 2
0x10008226  jz      loc_1000832F
0x1000822c  test    eax, eax
0x1000822e  jz      loc_1000832F
0x10008234  mov     eax, [esi+0E8h]
0x1000823a  test    eax, eax
0x1000823c  jz      loc_1000832F
0x10008242  cmp     eax, 0FFFFFFFFh
0x10008245  jz      loc_1000832F
0x1000824b  push    0; lpFileSizeHigh
0x1000824d  push    eax; hFile
0x1000824e  call    ds:__imp__GetFileSize@8; GetFileSize(x,x)
0x10008254  mov     ecx, eax
0x10008256  mov     eax, [esi+0F8h]
0x1000825c  sub     eax, ebx
0x1000825e  cmp     ecx, eax
0x10008260  jbe     loc_10008305
0x10008266  lea     edi, [esi+18h]
0x10008269  or      eax, 0FFFFFFFFh
0x1000826c  lock xadd [edi], eax
0x10008270  jns     short loc_1000827B
0x10008272  push    dword ptr [esi+1Ch]; hEvent
0x10008275  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1000827b  mov     ecx, esi; lpCriticalSection
0x1000827d  call    _AcquireWriteLock@4; AcquireWriteLock(x)
0x10008282  push    0; lpFileSizeHigh
0x10008284  push    dword ptr [esi+0E8h]; hFile
0x1000828a  call    ds:__imp__GetFileSize@8; GetFileSize(x,x)
0x10008290  mov     ecx, eax
0x10008292  cmp     ecx, 0FFFFFFFFh
0x10008295  jnz     short loc_100082BC
0x10008297  push    esi; lpCriticalSection
0x10008298  mov     dword ptr [edi], 0
0x1000829e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100082a4  push    esi; lpCriticalSection
0x100082a5  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100082ab  lock inc dword ptr [edi]
0x100082ae  push    esi; lpCriticalSection
0x100082af  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100082b5  xor     eax, eax
0x100082b7  jmp     loc_10008365
0x100082bc  mov     eax, [esi+0F8h]
0x100082c2  sub     eax, ebx
0x100082c4  cmp     ecx, eax
0x100082c6  jbe     short loc_100082D5
0x100082c8  mov     ecx, esi
0x100082ca  call    _TraceMoveClientFileW@4; TraceMoveClientFileW(x)
0x100082cf  test    eax, eax
0x100082d1  jz      short loc_100082E4
0x100082d3  jmp     short loc_10008297
0x100082d5  mov     eax, [esi+0E8h]
0x100082db  test    eax, eax
0x100082dd  jz      short loc_10008297
0x100082df  cmp     eax, 0FFFFFFFFh
0x100082e2  jz      short loc_10008297
0x100082e4  push    esi; lpCriticalSection
0x100082e5  mov     dword ptr [edi], 0
0x100082eb  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100082f1  push    esi; lpCriticalSection
0x100082f2  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100082f8  lock inc dword ptr [edi]
0x100082fb  push    esi; lpCriticalSection
0x100082fc  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10008302  xor     edi, edi
0x10008304  inc     edi
0x10008305  cmp     dword ptr [esi+0E8h], 0
0x1000830c  jz      short loc_1000832F
0x1000830e  cmp     dword ptr [esi+0E8h], 0FFFFFFFFh
0x10008315  jz      short loc_1000832F
0x10008317  push    0; lpOverlapped
0x10008319  lea     eax, [ebp+NumberOfBytesWritten]
0x1000831c  push    eax; lpNumberOfBytesWritten
0x1000831d  push    ebx; nNumberOfBytesToWrite
0x1000831e  push    [ebp+lpString]; lpBuffer
0x10008321  push    dword ptr [esi+0E8h]; hFile
0x10008327  call    ds:__imp__WriteFile@20; WriteFile(x,x,x,x,x)
0x1000832d  mov     edi, eax
0x1000832f  test    byte ptr [esi+20h], 4
0x10008333  jz      short loc_1000835D
0x10008335  cmp     [ebp+var_4], 0
0x10008339  jz      short loc_1000835D
0x1000833b  mov     ecx, [esi+0ECh]
0x10008341  test    ecx, ecx
0x10008343  jz      short loc_1000835D
0x10008345  push    0; lpReserved
0x10008347  lea     eax, [ebp+NumberOfCharsWritten]
0x1000834a  shr     ebx, 1
0x1000834c  push    eax; lpNumberOfCharsWritten
0x1000834d  push    ebx; nNumberOfCharsToWrite
0x1000834e  push    [ebp+lpString]; lpBuffer
0x10008351  mov     [ebp+NumberOfCharsWritten], ebx
0x10008354  push    ecx; hConsoleOutput
0x10008355  call    ds:__imp__WriteConsoleW@20; WriteConsoleW(x,x,x,x,x)
0x1000835b  mov     edi, eax
0x1000835d  xor     eax, eax
0x1000835f  test    edi, edi
0x10008361  cmovnz  eax, [ebp+NumberOfBytesWritten]
0x10008365  pop     edi
0x10008366  pop     esi
0x10008367  pop     ebx
0x10008368  leave
0x10008369  retn    8
```

# TraceWriteOutputA(x,x,x,x)

- ea: `0x100077c0`
- end: `0x1000794e`
- name: `_TraceWriteOutputA@16`
- size: `398`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x10003000`
- `0x100062d0`
- `0x10007174`

## callees

- `0x100022f0`
- `0x100075de`
- `0x100077c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10007881`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10007892`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100078cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100078e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10007881`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10007892`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100078cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100078e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10007888`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100078d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10007888`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100078d6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10007858`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10007858`
- `api-ms-win-core-console-l1-1-0!WriteConsoleA` at `0x10007937`
- `api-ms-win-core-console-l1-1-0!WriteConsoleA` at `0x10007937`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1000790b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1000790b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x10007831`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1000786d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x10007831`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1000786d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x100077da`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x100077da`

## pseudocode

```c
DWORD __fastcall TraceWriteOutputA(int a1, int a2, int a3, const CHAR *lpString)
{
  BOOL v5; // ebx
  DWORD v6; // edi
  int v7; // eax
  void *v8; // eax
  volatile signed __int32 *v9; // edi
  DWORD FileSize; // ecx
  DWORD result; // eax
  int v12; // eax
  void *v13; // ecx
  DWORD NumberOfCharsWritten; // [esp+Ch] [ebp-10h] BYREF
  DWORD NumberOfBytesWritten; // [esp+10h] [ebp-Ch] BYREF
  int v16; // [esp+14h] [ebp-8h]
  DWORD v17; // [esp+18h] [ebp-4h]

  NumberOfBytesWritten = 0;
  v5 = 1;
  v6 = lstrlenA(lpString);
  v17 = v6;
  v7 = 1;
  v16 = 1;
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
            if ( FileSize <= *(_DWORD *)(a2 + 248) - v17 )
            {
              v12 = *(_DWORD *)(a2 + 232);
              if ( !v12 || v12 == -1 )
                goto LABEL_11;
            }
            else if ( TraceMoveClientFileA(a2) )
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
            v6 = v17;
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
        NumberOfCharsWritten = v6;
        v5 = WriteConsoleA(v13, lpString, v6, &NumberOfCharsWritten, 0);
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
0x100077c0  mov     edi, edi
0x100077c2  push    ebp
0x100077c3  mov     ebp, esp
0x100077c5  sub     esp, 10h
0x100077c8  push    ebx
0x100077c9  push    esi
0x100077ca  push    edi
0x100077cb  push    [ebp+lpString]; lpString
0x100077ce  xor     ebx, ebx
0x100077d0  mov     [ebp+NumberOfBytesWritten], 0
0x100077d7  mov     esi, edx
0x100077d9  inc     ebx
0x100077da  call    ds:__imp__lstrlenA@4; lstrlenA(x)
0x100077e0  test    byte ptr [ebp+arg_0], 2
0x100077e4  mov     edi, eax
0x100077e6  mov     [ebp+var_4], edi
0x100077e9  mov     eax, ebx
0x100077eb  mov     [ebp+var_8], ebx
0x100077ee  jz      short loc_10007805
0x100077f0  mov     eax, [esi+0F0h]
0x100077f6  mov     ecx, [esi+0F4h]
0x100077fc  and     eax, [ebp+arg_0]
0x100077ff  and     ecx, [ebp+arg_0]
0x10007802  mov     [ebp+var_8], ecx
0x10007805  test    byte ptr [esi+20h], 2
0x10007809  jz      loc_10007913
0x1000780f  test    eax, eax
0x10007811  jz      loc_10007913
0x10007817  mov     eax, [esi+0E8h]
0x1000781d  test    eax, eax
0x1000781f  jz      loc_10007913
0x10007825  cmp     eax, 0FFFFFFFFh
0x10007828  jz      loc_10007913
0x1000782e  push    0; lpFileSizeHigh
0x10007830  push    eax; hFile
0x10007831  call    ds:__imp__GetFileSize@8; GetFileSize(x,x)
0x10007837  mov     ecx, eax
0x10007839  mov     eax, [esi+0F8h]
0x1000783f  sub     eax, edi
0x10007841  cmp     ecx, eax
0x10007843  jbe     loc_100078E9
0x10007849  lea     edi, [esi+18h]
0x1000784c  or      eax, 0FFFFFFFFh
0x1000784f  lock xadd [edi], eax
0x10007853  jns     short loc_1000785E
0x10007855  push    dword ptr [esi+1Ch]; hEvent
0x10007858  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1000785e  mov     ecx, esi; lpCriticalSection
0x10007860  call    _AcquireWriteLock@4; AcquireWriteLock(x)
0x10007865  push    0; lpFileSizeHigh
0x10007867  push    dword ptr [esi+0E8h]; hFile
0x1000786d  call    ds:__imp__GetFileSize@8; GetFileSize(x,x)
0x10007873  mov     ecx, eax
0x10007875  cmp     ecx, 0FFFFFFFFh
0x10007878  jnz     short loc_1000789F
0x1000787a  push    esi; lpCriticalSection
0x1000787b  mov     dword ptr [edi], 0
0x10007881  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10007887  push    esi; lpCriticalSection
0x10007888  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000788e  lock inc dword ptr [edi]
0x10007891  push    esi; lpCriticalSection
0x10007892  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10007898  xor     eax, eax
0x1000789a  jmp     loc_10007947
0x1000789f  mov     eax, [esi+0F8h]
0x100078a5  sub     eax, [ebp+var_4]
0x100078a8  cmp     ecx, eax
0x100078aa  jbe     short loc_100078B9
0x100078ac  mov     ecx, esi
0x100078ae  call    _TraceMoveClientFileA@4; TraceMoveClientFileA(x)
0x100078b3  test    eax, eax
0x100078b5  jz      short loc_100078C8
0x100078b7  jmp     short loc_1000787A
0x100078b9  mov     eax, [esi+0E8h]
0x100078bf  test    eax, eax
0x100078c1  jz      short loc_1000787A
0x100078c3  cmp     eax, 0FFFFFFFFh
0x100078c6  jz      short loc_1000787A
0x100078c8  push    esi; lpCriticalSection
0x100078c9  mov     dword ptr [edi], 0
0x100078cf  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100078d5  push    esi; lpCriticalSection
0x100078d6  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100078dc  lock inc dword ptr [edi]
0x100078df  push    esi; lpCriticalSection
0x100078e0  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100078e6  mov     edi, [ebp+var_4]
0x100078e9  cmp     dword ptr [esi+0E8h], 0
0x100078f0  jz      short loc_10007913
0x100078f2  cmp     dword ptr [esi+0E8h], 0FFFFFFFFh
0x100078f9  jz      short loc_10007913
0x100078fb  push    0; lpOverlapped
0x100078fd  lea     eax, [ebp+NumberOfBytesWritten]
0x10007900  push    eax; lpNumberOfBytesWritten
0x10007901  push    edi; nNumberOfBytesToWrite
0x10007902  push    [ebp+lpString]; lpBuffer
0x10007905  push    dword ptr [esi+0E8h]; hFile
0x1000790b  call    ds:__imp__WriteFile@20; WriteFile(x,x,x,x,x)
0x10007911  mov     ebx, eax
0x10007913  test    byte ptr [esi+20h], 4
0x10007917  jz      short loc_1000793F
0x10007919  cmp     [ebp+var_8], 0
0x1000791d  jz      short loc_1000793F
0x1000791f  mov     ecx, [esi+0ECh]
0x10007925  test    ecx, ecx
0x10007927  jz      short loc_1000793F
0x10007929  push    0; lpReserved
0x1000792b  lea     eax, [ebp+NumberOfCharsWritten]
0x1000792e  mov     [ebp+NumberOfCharsWritten], edi
0x10007931  push    eax; lpNumberOfCharsWritten
0x10007932  push    edi; nNumberOfCharsToWrite
0x10007933  push    [ebp+lpString]; lpBuffer
0x10007936  push    ecx; hConsoleOutput
0x10007937  call    ds:__imp__WriteConsoleA@20; WriteConsoleA(x,x,x,x,x)
0x1000793d  mov     ebx, eax
0x1000793f  xor     eax, eax
0x10007941  test    ebx, ebx
0x10007943  cmovnz  eax, [ebp+NumberOfBytesWritten]
0x10007947  pop     edi
0x10007948  pop     esi
0x10007949  pop     ebx
0x1000794a  leave
0x1000794b  retn    8
```

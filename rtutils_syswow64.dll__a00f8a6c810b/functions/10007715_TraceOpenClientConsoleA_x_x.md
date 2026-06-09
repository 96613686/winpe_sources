# TraceOpenClientConsoleA(x,x)

- ea: `0x10007715`
- end: `0x100077ba`
- name: `_TraceOpenClientConsoleA@8`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x100027e0`
- `0x100037bd`

## callees

- `0x10007715`
- `0x10009eb2`

## import_xrefs

- `api-ms-win-core-console-l2-1-0!CreateConsoleScreenBuffer` at `0x1000777f`
- `api-ms-win-core-console-l2-1-0!CreateConsoleScreenBuffer` at `0x1000777f`
- `api-ms-win-core-console-l2-1-0!SetConsoleScreenBufferSize` at `0x10007797`
- `api-ms-win-core-console-l2-1-0!SetConsoleScreenBufferSize` at `0x10007797`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1000775e`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1000775e`
- `api-ms-win-core-console-l1-1-0!AllocConsole` at `0x1000773b`
- `api-ms-win-core-console-l1-1-0!AllocConsole` at `0x1000773b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10007745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000776c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10007745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000776c`

## pseudocode

```c
DWORD __fastcall TraceOpenClientConsoleA(int a1, int a2)
{
  DWORD result; // eax
  HANDLE StdHandle; // eax
  HANDLE ConsoleScreenBuffer; // eax
  HANDLE v7; // edi

  if ( (*(_BYTE *)(a1 + 32) & 4) != 0 )
  {
    if ( !*(_DWORD *)(a1 + 48) || *(_DWORD *)(a1 + 48) == -1 )
    {
      if ( AllocConsole() )
      {
        *(_DWORD *)(a1 + 44) = 1;
      }
      else
      {
        result = GetLastError();
        if ( result != 5 )
        {
          *(_DWORD *)(a1 + 48) = -1;
          return result;
        }
      }
      StdHandle = GetStdHandle(0xFFFFFFF6);
      *(_DWORD *)(a1 + 48) = StdHandle;
      if ( StdHandle == (HANDLE)-1 )
        return GetLastError();
    }
    ConsoleScreenBuffer = CreateConsoleScreenBuffer(0xC0000000, 0, 0, 1u, 0);
    v7 = ConsoleScreenBuffer;
    if ( ConsoleScreenBuffer == (HANDLE)-1 )
      return GetLastError();
    SetConsoleScreenBufferSize(ConsoleScreenBuffer, (COORD)262144128);
    *(_DWORD *)(a2 + 236) = v7;
    if ( *(_DWORD *)(a1 + 40) == 60 )
      TraceUpdateConsoleOwner(a1, 1);
  }
  return 0;
}

```

## disassembly

```asm
0x10007715  mov     edi, edi
0x10007717  push    ebp
0x10007718  mov     ebp, esp
0x1000771a  push    ecx
0x1000771b  push    ebx
0x1000771c  push    esi
0x1000771d  mov     esi, ecx
0x1000771f  mov     ebx, edx
0x10007721  push    edi
0x10007722  test    byte ptr [esi+20h], 4
0x10007726  jz      loc_100077B3
0x1000772c  xor     edi, edi
0x1000772e  inc     edi
0x1000772f  cmp     dword ptr [esi+30h], 0
0x10007733  jz      short loc_1000773B
0x10007735  cmp     dword ptr [esi+30h], 0FFFFFFFFh
0x10007739  jnz     short loc_10007774
0x1000773b  call    ds:__imp__AllocConsole@0; AllocConsole()
0x10007741  test    eax, eax
0x10007743  jnz     short loc_10007759
0x10007745  call    ds:__imp__GetLastError@0; GetLastError()
0x1000774b  cmp     eax, 5
0x1000774e  jz      short loc_1000775C
0x10007750  mov     dword ptr [esi+30h], 0FFFFFFFFh
0x10007757  jmp     short loc_100077B5
0x10007759  mov     [esi+2Ch], edi
0x1000775c  push    0FFFFFFF6h; nStdHandle
0x1000775e  call    ds:__imp__GetStdHandle@4; GetStdHandle(x)
0x10007764  mov     [esi+30h], eax
0x10007767  cmp     eax, 0FFFFFFFFh
0x1000776a  jnz     short loc_10007774
0x1000776c  call    ds:__imp__GetLastError@0; GetLastError()
0x10007772  jmp     short loc_100077B5
0x10007774  xor     eax, eax
0x10007776  push    eax; lpScreenBufferData
0x10007777  push    edi; dwFlags
0x10007778  push    eax; lpSecurityAttributes
0x10007779  push    eax; dwShareMode
0x1000777a  push    0C0000000h; dwDesiredAccess
0x1000777f  call    ds:__imp__CreateConsoleScreenBuffer@20; CreateConsoleScreenBuffer(x,x,x,x,x)
0x10007785  mov     edi, eax
0x10007787  cmp     edi, 0FFFFFFFFh
0x1000778a  jz      short loc_1000776C
0x1000778c  mov     dword ptr [ebp+dwSize.X], 0FA00080h
0x10007793  push    dword ptr [ebp+dwSize.X]; dwSize
0x10007796  push    edi; hConsoleOutput
0x10007797  call    ds:__imp__SetConsoleScreenBufferSize@8; SetConsoleScreenBufferSize(x,x)
0x1000779d  mov     [ebx+0ECh], edi
0x100077a3  cmp     dword ptr [esi+28h], 3Ch ; '<'
0x100077a7  jnz     short loc_100077B3
0x100077a9  xor     edx, edx
0x100077ab  mov     ecx, esi
0x100077ad  inc     edx
0x100077ae  call    _TraceUpdateConsoleOwner@8; TraceUpdateConsoleOwner(x,x)
0x100077b3  xor     eax, eax
0x100077b5  pop     edi
0x100077b6  pop     esi
0x100077b7  pop     ebx
0x100077b8  leave
0x100077b9  retn
```

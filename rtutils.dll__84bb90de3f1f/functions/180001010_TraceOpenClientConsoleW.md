# TraceOpenClientConsoleW

- ea: `0x180001010`
- end: `0x1800010f8`
- name: `TraceOpenClientConsoleW`
- size: `232`
- prototype: `DWORD __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180001100`
- `0x180001c20`
- `0x180005450`

## callees

- `0x180001010`
- `0x1800026d0`

## import_xrefs

- `api-ms-win-core-console-l2-1-0!CreateConsoleScreenBuffer` at `0x1800010a8`
- `api-ms-win-core-console-l2-1-0!CreateConsoleScreenBuffer` at `0x1800010a8`
- `api-ms-win-core-console-l2-1-0!SetConsoleScreenBufferSize` at `0x1800010c6`
- `api-ms-win-core-console-l2-1-0!SetConsoleScreenBufferSize` at `0x1800010c6`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x180001077`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x180001077`
- `api-ms-win-core-console-l1-1-0!AllocConsole` at `0x18000103e`
- `api-ms-win-core-console-l1-1-0!AllocConsole` at `0x18000103e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001087`

## pseudocode

```c
DWORD __fastcall TraceOpenClientConsoleW(__int64 a1, __int64 a2)
{
  DWORD result; // eax
  HANDLE StdHandle; // rax
  HANDLE ConsoleScreenBuffer; // rax
  HANDLE v7; // rsi

  if ( (*(_BYTE *)(a1 + 56) & 4) != 0 )
  {
    if ( ((*(_QWORD *)(a1 + 72) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( AllocConsole() )
      {
        *(_DWORD *)(a1 + 68) = 1;
      }
      else
      {
        result = GetLastError();
        if ( result != 5 )
        {
          *(_QWORD *)(a1 + 72) = -1;
          return result;
        }
      }
      StdHandle = GetStdHandle(0xFFFFFFF6);
      *(_QWORD *)(a1 + 72) = StdHandle;
      if ( StdHandle == (HANDLE)-1LL )
        return GetLastError();
    }
    ConsoleScreenBuffer = CreateConsoleScreenBuffer(0xC0000000, 0, 0, 1u, 0);
    v7 = ConsoleScreenBuffer;
    if ( ConsoleScreenBuffer == (HANDLE)-1LL )
      return GetLastError();
    SetConsoleScreenBufferSize(ConsoleScreenBuffer, (COORD)262144128);
    *(_QWORD *)(a2 + 264) = v7;
    if ( *(_DWORD *)(a1 + 64) == 60 )
      TraceUpdateConsoleOwner(a1, 1);
  }
  return 0;
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_8], rbx
0x180001015  mov     [rsp+arg_10], rsi
0x18000101a  push    rdi
0x18000101b  sub     rsp, 30h
0x18000101f  test    byte ptr [rcx+38h], 4
0x180001023  mov     rdi, rdx
0x180001026  mov     rbx, rcx
0x180001029  jz      loc_1800010E6
0x18000102f  mov     rax, [rcx+48h]
0x180001033  inc     rax
0x180001036  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000103c  jnz     short loc_18000108F
0x18000103e  call    cs:__imp_AllocConsole
0x180001044  test    eax, eax
0x180001046  jnz     short loc_18000106B
0x180001048  call    cs:__imp_GetLastError
0x18000104e  cmp     eax, 5
0x180001051  jz      short loc_180001072
0x180001053  mov     qword ptr [rbx+48h], 0FFFFFFFFFFFFFFFFh
0x18000105b  mov     rbx, [rsp+38h+arg_8]
0x180001060  mov     rsi, [rsp+38h+arg_10]
0x180001065  add     rsp, 30h
0x180001069  pop     rdi
0x18000106a  retn
0x18000106b  mov     dword ptr [rbx+44h], 1
0x180001072  mov     ecx, 0FFFFFFF6h; nStdHandle
0x180001077  call    cs:__imp_GetStdHandle
0x18000107d  mov     [rbx+48h], rax
0x180001081  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001085  jnz     short loc_18000108F
0x180001087  call    cs:__imp_GetLastError
0x18000108d  jmp     short loc_1800010E8
0x18000108f  mov     r9d, 1; dwFlags
0x180001095  mov     [rsp+38h+lpScreenBufferData], 0; lpScreenBufferData
0x18000109e  xor     r8d, r8d; lpSecurityAttributes
0x1800010a1  xor     edx, edx; dwShareMode
0x1800010a3  mov     ecx, 0C0000000h; dwDesiredAccess
0x1800010a8  call    cs:__imp_CreateConsoleScreenBuffer
0x1800010ae  mov     rsi, rax
0x1800010b1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800010b5  jz      short loc_180001087
0x1800010b7  mov     dword ptr [rsp+38h+dwSize.X], 0FA00080h
0x1800010bf  mov     rcx, rax; hConsoleOutput
0x1800010c2  mov     edx, dword ptr [rsp+38h+dwSize.X]; dwSize
0x1800010c6  call    cs:__imp_SetConsoleScreenBufferSize
0x1800010cc  mov     [rdi+108h], rsi
0x1800010d3  cmp     dword ptr [rbx+40h], 3Ch ; '<'
0x1800010d7  jnz     short loc_1800010E6
0x1800010d9  mov     edx, 1
0x1800010de  mov     rcx, rbx
0x1800010e1  call    TraceUpdateConsoleOwner
0x1800010e6  xor     eax, eax
0x1800010e8  mov     rbx, [rsp+38h+arg_8]
0x1800010ed  mov     rsi, [rsp+38h+arg_10]
0x1800010f2  add     rsp, 30h
0x1800010f6  pop     rdi
0x1800010f7  retn
```

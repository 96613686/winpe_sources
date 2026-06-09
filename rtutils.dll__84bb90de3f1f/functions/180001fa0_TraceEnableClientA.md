# TraceEnableClientA

- ea: `0x180001fa0`
- end: `0x18000211c`
- name: `TraceEnableClientA`
- size: `380`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180009838`
- `0x180009a30`

## callees

- `0x180001fa0`
- `0x180002130`
- `0x1800026d0`
- `0x180005e98`
- `0x180005f3c`
- `0x180005f70`

## import_xrefs

- `api-ms-win-core-console-l2-1-0!CreateConsoleScreenBuffer` at `0x18000205e`
- `api-ms-win-core-console-l2-1-0!CreateConsoleScreenBuffer` at `0x18000205e`
- `api-ms-win-core-console-l2-1-0!SetConsoleScreenBufferSize` at `0x18000208b`
- `api-ms-win-core-console-l2-1-0!SetConsoleScreenBufferSize` at `0x18000208b`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x180002036`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x180002036`
- `api-ms-win-core-console-l1-1-0!AllocConsole` at `0x18000200b`
- `api-ms-win-core-console-l1-1-0!AllocConsole` at `0x18000200b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000206d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000206d`

## pseudocode

```c
DWORD __fastcall TraceEnableClientA(__int64 a1, __int64 a2, int a3)
{
  int v4; // edi
  DWORD result; // eax
  HANDLE StdHandle; // rax
  HANDLE ConsoleScreenBuffer; // rax
  HANDLE v10; // r14
  int v11; // r14d

  *(_DWORD *)(a2 + 56) &= ~1u;
  v4 = *(_DWORD *)(a2 + 56);
  if ( (v4 & 8) != 0 )
  {
    result = TraceRegConfigClientA(a2, a3);
    if ( result )
      return result;
  }
  if ( (*(_BYTE *)(a2 + 56) & 4) != 0 )
  {
    if ( !a3 && (v4 & 4) != 0 || (*(_BYTE *)(a1 + 56) & 4) == 0 )
      goto LABEL_19;
    if ( ((*(_QWORD *)(a1 + 72) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      goto LABEL_13;
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
        goto LABEL_15;
      }
    }
    StdHandle = GetStdHandle(0xFFFFFFF6);
    *(_QWORD *)(a1 + 72) = StdHandle;
    if ( StdHandle != (HANDLE)-1LL )
    {
LABEL_13:
      ConsoleScreenBuffer = CreateConsoleScreenBuffer(0xC0000000, 0, 0, 1u, 0);
      v10 = ConsoleScreenBuffer;
      if ( ConsoleScreenBuffer != (HANDLE)-1LL )
      {
        SetConsoleScreenBufferSize(ConsoleScreenBuffer, (COORD)262144128);
        *(_QWORD *)(a2 + 264) = v10;
        if ( *(_DWORD *)(a1 + 64) == 60 )
          TraceUpdateConsoleOwner(a1, 1);
        goto LABEL_19;
      }
    }
    result = GetLastError();
LABEL_15:
    if ( result )
      return result;
LABEL_19:
    v11 = *(_DWORD *)(a2 + 276) | 4;
    if ( a3 )
      goto LABEL_26;
LABEL_24:
    if ( (v4 & 2) != 0 )
      TraceCloseClientFileW(a2);
    goto LABEL_26;
  }
  v11 = 0;
  if ( !a3 )
  {
    if ( (v4 & 4) != 0 )
      TraceCloseClientConsoleW(a1, a2);
    goto LABEL_24;
  }
LABEL_26:
  if ( (*(_BYTE *)(a2 + 56) & 2) != 0 )
  {
    result = TraceCreateClientFileA(a2);
    if ( result )
      return result;
    v11 |= *(_DWORD *)(a2 + 272) | 2;
  }
  _InterlockedExchange((volatile __int32 *)(a1 + 4LL * *(unsigned int *)(a2 + 60) + 112), v11);
  return 0;
}

```

## disassembly

```asm
0x180001fa0  mov     [rsp+arg_10], rbx
0x180001fa5  push    rbp
0x180001fa6  push    rsi
0x180001fa7  push    rdi
0x180001fa8  sub     rsp, 30h
0x180001fac  and     dword ptr [rdx+38h], 0FFFFFFFEh
0x180001fb0  mov     esi, r8d
0x180001fb3  mov     edi, [rdx+38h]
0x180001fb6  mov     rbx, rdx
0x180001fb9  mov     rbp, rcx
0x180001fbc  test    dil, 8
0x180001fc0  jz      short loc_180001FD5
0x180001fc2  mov     edx, r8d
0x180001fc5  mov     rcx, rbx
0x180001fc8  call    TraceRegConfigClientA
0x180001fcd  test    eax, eax
0x180001fcf  jnz     loc_18000210F
0x180001fd5  test    byte ptr [rbx+38h], 4
0x180001fd9  mov     [rsp+48h+arg_0], r14
0x180001fde  jz      loc_1800020BC
0x180001fe4  test    esi, esi
0x180001fe6  jnz     short loc_180001FF2
0x180001fe8  test    dil, 4
0x180001fec  jnz     loc_1800020AB
0x180001ff2  test    byte ptr [rbp+38h], 4
0x180001ff6  jz      loc_1800020AB
0x180001ffc  mov     rax, [rbp+48h]
0x180002000  inc     rax
0x180002003  test    rax, 0FFFFFFFFFFFFFFFEh
0x180002009  jnz     short loc_180002046
0x18000200b  call    cs:__imp_AllocConsole
0x180002011  test    eax, eax
0x180002013  jnz     short loc_18000202A
0x180002015  call    cs:__imp_GetLastError
0x18000201b  cmp     eax, 5
0x18000201e  jz      short loc_180002031
0x180002020  mov     qword ptr [rbp+48h], 0FFFFFFFFFFFFFFFFh
0x180002028  jmp     short loc_180002073
0x18000202a  mov     dword ptr [rbp+44h], 1
0x180002031  mov     ecx, 0FFFFFFF6h; nStdHandle
0x180002036  call    cs:__imp_GetStdHandle
0x18000203c  mov     [rbp+48h], rax
0x180002040  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002044  jz      short loc_18000206D
0x180002046  xor     r14d, r14d
0x180002049  mov     r9d, 1; dwFlags
0x18000204f  xor     r8d, r8d; lpSecurityAttributes
0x180002052  mov     [rsp+48h+lpScreenBufferData], r14; lpScreenBufferData
0x180002057  xor     edx, edx; dwShareMode
0x180002059  mov     ecx, 0C0000000h; dwDesiredAccess
0x18000205e  call    cs:__imp_CreateConsoleScreenBuffer
0x180002064  mov     r14, rax
0x180002067  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000206b  jnz     short loc_18000207C
0x18000206d  call    cs:__imp_GetLastError
0x180002073  test    eax, eax
0x180002075  jz      short loc_1800020AB
0x180002077  jmp     loc_18000210A
0x18000207c  mov     dword ptr [rsp+48h+dwSize.X], 0FA00080h
0x180002084  mov     rcx, r14; hConsoleOutput
0x180002087  mov     edx, dword ptr [rsp+48h+dwSize.X]; dwSize
0x18000208b  call    cs:__imp_SetConsoleScreenBufferSize
0x180002091  mov     [rbx+108h], r14
0x180002098  cmp     dword ptr [rbp+40h], 3Ch ; '<'
0x18000209c  jnz     short loc_1800020AB
0x18000209e  mov     edx, 1
0x1800020a3  mov     rcx, rbp
0x1800020a6  call    TraceUpdateConsoleOwner
0x1800020ab  mov     r14d, [rbx+114h]
0x1800020b2  or      r14d, 4
0x1800020b6  test    esi, esi
0x1800020b8  jz      short loc_1800020D4
0x1800020ba  jmp     short loc_1800020E2
0x1800020bc  xor     r14d, r14d
0x1800020bf  test    esi, esi
0x1800020c1  jnz     short loc_1800020E2
0x1800020c3  test    dil, 4
0x1800020c7  jz      short loc_1800020D4
0x1800020c9  mov     rdx, rbx
0x1800020cc  mov     rcx, rbp
0x1800020cf  call    TraceCloseClientConsoleW
0x1800020d4  test    dil, 2
0x1800020d8  jz      short loc_1800020E2
0x1800020da  mov     rcx, rbx
0x1800020dd  call    TraceCloseClientFileW
0x1800020e2  test    byte ptr [rbx+38h], 2
0x1800020e6  jz      short loc_180002100
0x1800020e8  mov     rcx, rbx
0x1800020eb  call    TraceCreateClientFileA
0x1800020f0  test    eax, eax
0x1800020f2  jnz     short loc_18000210A
0x1800020f4  mov     eax, [rbx+110h]
0x1800020fa  or      eax, 2
0x1800020fd  or      r14d, eax
0x180002100  mov     eax, [rbx+3Ch]
0x180002103  xchg    r14d, [rbp+rax*4+70h]
0x180002108  xor     eax, eax
0x18000210a  mov     r14, [rsp+48h+arg_0]
0x18000210f  mov     rbx, [rsp+48h+arg_10]
0x180002114  add     rsp, 30h
0x180002118  pop     rdi
0x180002119  pop     rsi
0x18000211a  pop     rbp
0x18000211b  retn
```

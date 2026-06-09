# CReadWriteLock::CReadWriteLock(void)

- ea: `0x1800229a0`
- end: `0x180022a3f`
- name: `??0CReadWriteLock@@QEAA@XZ`
- size: `159`
- prototype: `CReadWriteLock *__fastcall(CReadWriteLock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180022a48`

## callees

- `0x1800039f0`
- `0x1800229a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800229bc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800229ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800229bc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800229ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CReadWriteLock *__fastcall CReadWriteLock::CReadWriteLock(CReadWriteLock *this)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE v4; // rax
  signed int v5; // eax
  signed int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 1) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    pExceptionObject = LastError;
    throw (long *)&pExceptionObject;
  }
  v4 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 2) = v4;
  if ( !v4 )
  {
    v5 = GetLastError();
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    pExceptionObject = v5;
    throw (long *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x1800229a0  push    rbx
0x1800229a2  sub     rsp, 20h
0x1800229a6  xor     r9d, r9d; lpName
0x1800229a9  mov     qword ptr [rcx], 0
0x1800229b0  mov     rbx, rcx
0x1800229b3  xor     r8d, r8d; bInitialState
0x1800229b6  xor     ecx, ecx; lpEventAttributes
0x1800229b8  lea     edx, [r9+1]; bManualReset
0x1800229bc  call    cs:__imp_CreateEventW
0x1800229c2  mov     [rbx+8], rax
0x1800229c6  test    rax, rax
0x1800229c9  jnz     short loc_1800229F3
0x1800229cb  call    cs:__imp_GetLastError
0x1800229d1  test    eax, eax
0x1800229d3  jle     short loc_1800229DD
0x1800229d5  movzx   eax, ax
0x1800229d8  or      eax, 80070000h
0x1800229dd  lea     rdx, _TI1J; pThrowInfo
0x1800229e4  mov     [rsp+28h+pExceptionObject], eax
0x1800229e8  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800229ed  call    _CxxThrowException_0
0x1800229f3  xor     r9d, r9d; lpName
0x1800229f6  xor     r8d, r8d; bInitialState
0x1800229f9  xor     ecx, ecx; lpEventAttributes
0x1800229fb  lea     edx, [r9+1]; bManualReset
0x1800229ff  call    cs:__imp_CreateEventW
0x180022a05  mov     [rbx+10h], rax
0x180022a09  test    rax, rax
0x180022a0c  jnz     short loc_180022A36
0x180022a0e  call    cs:__imp_GetLastError
0x180022a14  test    eax, eax
0x180022a16  jle     short loc_180022A20
0x180022a18  movzx   eax, ax
0x180022a1b  or      eax, 80070000h
0x180022a20  lea     rdx, _TI1J; pThrowInfo
0x180022a27  mov     [rsp+28h+pExceptionObject], eax
0x180022a2b  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180022a30  call    _CxxThrowException_0
0x180022a36  mov     rax, rbx
0x180022a39  add     rsp, 20h
0x180022a3d  pop     rbx
0x180022a3e  retn
```

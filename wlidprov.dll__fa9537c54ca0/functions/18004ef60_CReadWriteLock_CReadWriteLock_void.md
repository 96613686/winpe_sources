# CReadWriteLock::CReadWriteLock(void)

- ea: `0x18004ef60`
- end: `0x18004efff`
- name: `??0CReadWriteLock@@QEAA@XZ`
- size: `159`
- prototype: `CReadWriteLock *__fastcall(CReadWriteLock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004f8cc`

## callees

- `0x18001ac48`
- `0x18004ef60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004ef7c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004efbf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004ef7c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004efbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ef8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004efce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ef8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004efce`

## pseudocode

```c
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
0x18004ef60  push    rbx
0x18004ef62  sub     rsp, 20h
0x18004ef66  xor     r9d, r9d; lpName
0x18004ef69  mov     qword ptr [rcx], 0
0x18004ef70  mov     rbx, rcx
0x18004ef73  xor     r8d, r8d; bInitialState
0x18004ef76  xor     ecx, ecx; lpEventAttributes
0x18004ef78  lea     edx, [r9+1]; bManualReset
0x18004ef7c  call    cs:__imp_CreateEventW
0x18004ef82  mov     [rbx+8], rax
0x18004ef86  test    rax, rax
0x18004ef89  jnz     short loc_18004EFB3
0x18004ef8b  call    cs:__imp_GetLastError
0x18004ef91  test    eax, eax
0x18004ef93  jle     short loc_18004EF9D
0x18004ef95  movzx   eax, ax
0x18004ef98  or      eax, 80070000h
0x18004ef9d  lea     rdx, _TI1J; pThrowInfo
0x18004efa4  mov     [rsp+28h+pExceptionObject], eax
0x18004efa8  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18004efad  call    _CxxThrowException_0
0x18004efb3  xor     r9d, r9d; lpName
0x18004efb6  xor     r8d, r8d; bInitialState
0x18004efb9  xor     ecx, ecx; lpEventAttributes
0x18004efbb  lea     edx, [r9+1]; bManualReset
0x18004efbf  call    cs:__imp_CreateEventW
0x18004efc5  mov     [rbx+10h], rax
0x18004efc9  test    rax, rax
0x18004efcc  jnz     short loc_18004EFF6
0x18004efce  call    cs:__imp_GetLastError
0x18004efd4  test    eax, eax
0x18004efd6  jle     short loc_18004EFE0
0x18004efd8  movzx   eax, ax
0x18004efdb  or      eax, 80070000h
0x18004efe0  lea     rdx, _TI1J; pThrowInfo
0x18004efe7  mov     [rsp+28h+pExceptionObject], eax
0x18004efeb  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18004eff0  call    _CxxThrowException_0
0x18004eff6  mov     rax, rbx
0x18004eff9  add     rsp, 20h
0x18004effd  pop     rbx
0x18004effe  retn
```

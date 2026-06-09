# mi::ManualResetEvent::ManualResetEvent(bool)

- ea: `0x18007ff20`
- end: `0x18007ff82`
- name: `??0ManualResetEvent@mi@@QEAA@_N@Z`
- size: `98`
- prototype: `__int64 __fastcall(mi::ManualResetEvent *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18007c420`

## callees

- `0x180003520`
- `0x18005073c`
- `0x18007ff20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007ff35`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007ff35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ff40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ff40`

## string_xrefs

- `0x18007ff48`: `::CreateEventW( nullptr, true, initialState == true, nullptr )`

## pseudocode

```c
mi::ManualResetEvent *__fastcall mi::ManualResetEvent::ManualResetEvent(mi::ManualResetEvent *this)
{
  HANDLE EventW; // rax
  DWORD LastError; // eax
  mi::ManualResetEvent *result; // rax
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF

  EventW = CreateEventW(0, 1, 0, 0);
  if ( !EventW )
  {
    LastError = GetLastError();
    std::system_error::system_error(
      (std::system_error *)pExceptionObject,
      LastError,
      (const struct std::error_category *)&mi::win32_category_var,
      "::CreateEventW( nullptr, true, initialState == true, nullptr )");
    throw (std::system_error *)pExceptionObject;
  }
  *(_QWORD *)this = EventW;
  result = this;
  *((_BYTE *)this + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x18007ff20  push    rbx
0x18007ff22  sub     rsp, 50h
0x18007ff26  xor     r9d, r9d; lpName
0x18007ff29  mov     rbx, rcx
0x18007ff2c  xor     r8d, r8d; bInitialState
0x18007ff2f  xor     ecx, ecx; lpEventAttributes
0x18007ff31  lea     edx, [r9+1]; bManualReset
0x18007ff35  call    cs:__imp_CreateEventW
0x18007ff3b  test    rax, rax
0x18007ff3e  jnz     short loc_18007FF72
0x18007ff40  call    cs:__imp_GetLastError
0x18007ff46  mov     edx, eax; int
0x18007ff48  lea     r9, aCreateeventwNu; "::CreateEventW( nullptr, true, initialS"...
0x18007ff4f  lea     r8, ?win32_category_var@mi@@3Vwin32_error_categoryImpl@1@A; struct std::error_category *
0x18007ff56  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18007ff5b  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x18007ff60  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18007ff67  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18007ff6c  call    _CxxThrowException_0
0x18007ff72  mov     [rbx], rax
0x18007ff75  mov     rax, rbx
0x18007ff78  mov     byte ptr [rbx+8], 0
0x18007ff7c  add     rsp, 50h
0x18007ff80  pop     rbx
0x18007ff81  retn
```

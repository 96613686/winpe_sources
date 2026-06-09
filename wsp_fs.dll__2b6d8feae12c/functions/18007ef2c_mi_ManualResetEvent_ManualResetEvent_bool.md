# mi::ManualResetEvent::ManualResetEvent(bool)

- ea: `0x18007ef2c`
- end: `0x18007ef8e`
- name: `??0ManualResetEvent@mi@@QEAA@_N@Z`
- size: `98`
- prototype: `__int64 __fastcall(mi::ManualResetEvent *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18007bf6c`

## callees

- `0x1800034a4`
- `0x180056f34`
- `0x18007ef2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007ef41`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007ef41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ef4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ef4c`

## string_xrefs

- `0x18007ef54`: `::CreateEventW( nullptr, true, initialState == true, nullptr )`

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
0x18007ef2c  push    rbx
0x18007ef2e  sub     rsp, 50h
0x18007ef32  xor     r9d, r9d; lpName
0x18007ef35  mov     rbx, rcx
0x18007ef38  xor     r8d, r8d; bInitialState
0x18007ef3b  xor     ecx, ecx; lpEventAttributes
0x18007ef3d  lea     edx, [r9+1]; bManualReset
0x18007ef41  call    cs:__imp_CreateEventW
0x18007ef47  test    rax, rax
0x18007ef4a  jnz     short loc_18007EF7E
0x18007ef4c  call    cs:__imp_GetLastError
0x18007ef52  mov     edx, eax; int
0x18007ef54  lea     r9, aCreateeventwNu; "::CreateEventW( nullptr, true, initialS"...
0x18007ef5b  lea     r8, ?win32_category_var@mi@@3Vwin32_error_categoryImpl@1@A; struct std::error_category *
0x18007ef62  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18007ef67  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x18007ef6c  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18007ef73  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18007ef78  call    _CxxThrowException_0
0x18007ef7e  mov     [rbx], rax
0x18007ef81  mov     rax, rbx
0x18007ef84  mov     byte ptr [rbx+8], 0
0x18007ef88  add     rsp, 50h
0x18007ef8c  pop     rbx
0x18007ef8d  retn
```

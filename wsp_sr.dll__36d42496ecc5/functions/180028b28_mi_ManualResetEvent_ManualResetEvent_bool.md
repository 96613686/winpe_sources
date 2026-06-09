# mi::ManualResetEvent::ManualResetEvent(bool)

- ea: `0x180028b28`
- end: `0x180028b8a`
- name: `??0ManualResetEvent@mi@@QEAA@_N@Z`
- size: `98`
- prototype: `mi::ManualResetEvent *__fastcall(mi::ManualResetEvent *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800279b8`

## callees

- `0x18000296b`
- `0x180008668`
- `0x180028b28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028b48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028b48`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028b3d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028b3d`

## string_xrefs

- `0x180028b50`: `::CreateEventW( nullptr, true, initialState == true, nullptr )`

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
0x180028b28  push    rbx
0x180028b2a  sub     rsp, 50h
0x180028b2e  xor     r9d, r9d; lpName
0x180028b31  mov     rbx, rcx
0x180028b34  xor     r8d, r8d; bInitialState
0x180028b37  xor     ecx, ecx; lpEventAttributes
0x180028b39  lea     edx, [r9+1]; bManualReset
0x180028b3d  call    cs:__imp_CreateEventW
0x180028b43  test    rax, rax
0x180028b46  jnz     short loc_180028B7A
0x180028b48  call    cs:__imp_GetLastError
0x180028b4e  mov     edx, eax; int
0x180028b50  lea     r9, aCreateeventwNu; "::CreateEventW( nullptr, true, initialS"...
0x180028b57  lea     r8, ?win32_category_var@mi@@3Vwin32_error_categoryImpl@1@A; struct std::error_category *
0x180028b5e  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180028b63  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x180028b68  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x180028b6f  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180028b74  call    _CxxThrowException_0
0x180028b7a  mov     [rbx], rax
0x180028b7d  mov     rax, rbx
0x180028b80  mov     byte ptr [rbx+8], 0
0x180028b84  add     rsp, 50h
0x180028b88  pop     rbx
0x180028b89  retn
```

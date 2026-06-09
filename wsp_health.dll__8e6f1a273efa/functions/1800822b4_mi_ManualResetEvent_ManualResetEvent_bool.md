# mi::ManualResetEvent::ManualResetEvent(bool)

- ea: `0x1800822b4`
- end: `0x180082323`
- name: `??0ManualResetEvent@mi@@QEAA@_N@Z`
- size: `111`
- prototype: `__int64 __fastcall(mi::ManualResetEvent *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18007e668`

## callees

- `0x1800035c0`
- `0x1800521c4`
- `0x1800822b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800822c9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800822c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800822da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800822da`

## string_xrefs

- `0x1800822e8`: `::CreateEventW( nullptr, true, initialState == true, nullptr )`

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
0x1800822b4  push    rbx
0x1800822b6  sub     rsp, 50h
0x1800822ba  xor     r9d, r9d; lpName
0x1800822bd  mov     rbx, rcx
0x1800822c0  xor     r8d, r8d; bInitialState
0x1800822c3  xor     ecx, ecx; lpEventAttributes
0x1800822c5  lea     edx, [r9+1]; bManualReset
0x1800822c9  call    cs:__imp_CreateEventW
0x1800822d0  nop     dword ptr [rax+rax+00h]
0x1800822d5  test    rax, rax
0x1800822d8  jnz     short loc_180082312
0x1800822da  call    cs:__imp_GetLastError
0x1800822e1  nop     dword ptr [rax+rax+00h]
0x1800822e6  mov     edx, eax; int
0x1800822e8  lea     r9, aCreateeventwNu; "::CreateEventW( nullptr, true, initialS"...
0x1800822ef  lea     r8, ?win32_category_var@mi@@3Vwin32_error_categoryImpl@1@A; struct std::error_category *
0x1800822f6  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800822fb  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x180082300  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x180082307  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18008230c  call    _CxxThrowException_0
0x180082312  mov     [rbx], rax
0x180082315  mov     rax, rbx
0x180082318  mov     byte ptr [rbx+8], 0
0x18008231c  add     rsp, 50h
0x180082320  pop     rbx
0x180082321  retn
```

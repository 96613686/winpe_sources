# mi::ManualResetEvent::ManualResetEvent(bool)

- ea: `0x180080e30`
- end: `0x180080e9f`
- name: `??0ManualResetEvent@mi@@QEAA@_N@Z`
- size: `111`
- prototype: `__int64 __fastcall(mi::ManualResetEvent *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18007dd48`

## callees

- `0x180003534`
- `0x180057fdc`
- `0x180080e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180080e45`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180080e45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080e56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080e56`

## string_xrefs

- `0x180080e64`: `::CreateEventW( nullptr, true, initialState == true, nullptr )`

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
0x180080e30  push    rbx
0x180080e32  sub     rsp, 50h
0x180080e36  xor     r9d, r9d; lpName
0x180080e39  mov     rbx, rcx
0x180080e3c  xor     r8d, r8d; bInitialState
0x180080e3f  xor     ecx, ecx; lpEventAttributes
0x180080e41  lea     edx, [r9+1]; bManualReset
0x180080e45  call    cs:__imp_CreateEventW
0x180080e4c  nop     dword ptr [rax+rax+00h]
0x180080e51  test    rax, rax
0x180080e54  jnz     short loc_180080E8E
0x180080e56  call    cs:__imp_GetLastError
0x180080e5d  nop     dword ptr [rax+rax+00h]
0x180080e62  mov     edx, eax; int
0x180080e64  lea     r9, aCreateeventwNu; "::CreateEventW( nullptr, true, initialS"...
0x180080e6b  lea     r8, ?win32_category_var@mi@@3Vwin32_error_categoryImpl@1@A; struct std::error_category *
0x180080e72  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180080e77  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x180080e7c  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x180080e83  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180080e88  call    _CxxThrowException_0
0x180080e8e  mov     [rbx], rax
0x180080e91  mov     rax, rbx
0x180080e94  mov     byte ptr [rbx+8], 0
0x180080e98  add     rsp, 50h
0x180080e9c  pop     rbx
0x180080e9d  retn
```

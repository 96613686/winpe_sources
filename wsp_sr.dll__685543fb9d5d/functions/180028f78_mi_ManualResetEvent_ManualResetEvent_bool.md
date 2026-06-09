# mi::ManualResetEvent::ManualResetEvent(bool)

- ea: `0x180028f78`
- end: `0x180028fe7`
- name: `??0ManualResetEvent@mi@@QEAA@_N@Z`
- size: `111`
- prototype: `__int64 __fastcall(mi::ManualResetEvent *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180027d24`

## callees

- `0x18000299b`
- `0x1800087cc`
- `0x180028f78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f9e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028f8d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028f8d`

## string_xrefs

- `0x180028fac`: `::CreateEventW( nullptr, true, initialState == true, nullptr )`

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
0x180028f78  push    rbx
0x180028f7a  sub     rsp, 50h
0x180028f7e  xor     r9d, r9d; lpName
0x180028f81  mov     rbx, rcx
0x180028f84  xor     r8d, r8d; bInitialState
0x180028f87  xor     ecx, ecx; lpEventAttributes
0x180028f89  lea     edx, [r9+1]; bManualReset
0x180028f8d  call    cs:__imp_CreateEventW
0x180028f94  nop     dword ptr [rax+rax+00h]
0x180028f99  test    rax, rax
0x180028f9c  jnz     short loc_180028FD6
0x180028f9e  call    cs:__imp_GetLastError
0x180028fa5  nop     dword ptr [rax+rax+00h]
0x180028faa  mov     edx, eax; int
0x180028fac  lea     r9, aCreateeventwNu; "::CreateEventW( nullptr, true, initialS"...
0x180028fb3  lea     r8, ?win32_category_var@mi@@3Vwin32_error_categoryImpl@1@A; struct std::error_category *
0x180028fba  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180028fbf  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x180028fc4  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x180028fcb  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180028fd0  call    _CxxThrowException_0
0x180028fd6  mov     [rbx], rax
0x180028fd9  mov     rax, rbx
0x180028fdc  mov     byte ptr [rbx+8], 0
0x180028fe0  add     rsp, 50h
0x180028fe4  pop     rbx
0x180028fe5  retn
```

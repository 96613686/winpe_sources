# cxl::ManualResetEvent::ManualResetEvent(bool)

- ea: `0x18001a994`
- end: `0x18001aa5a`
- name: `??0ManualResetEvent@cxl@@QEAA@_N@Z`
- size: `198`
- prototype: `__int64 __fastcall(cxl::ManualResetEvent *__hidden this, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001b6b4`
- `0x1800217e8`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000d298`
- `0x18000d33c`
- `0x18000e140`
- `0x18001a994`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a9c3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a9c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9e3`

## string_xrefs

- `0x18001a9d1`: `::CreateEventW(nullptr, true, initialState, nullptr)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
cxl::ManualResetEvent *__fastcall cxl::ManualResetEvent::ManualResetEvent(cxl::ManualResetEvent *this)
{
  __int64 v2; // rdx
  cxl::ManualResetEvent *LastError; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v5[40]; // [rsp+28h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+50h] [rbp-88h] BYREF

  LastError = this;
  if ( !CreateEventW(0, 1, 0, 0) )
  {
    std::wstring::wstring(v5, L"::CreateEventW(nullptr, true, initialState, nullptr)");
    LastError = (cxl::ManualResetEvent *)GetLastError();
    cxl::Exception::Exception(pExceptionObject, &LastError, v5);
    throw (cxl::Exception *)pExceptionObject;
  }
  cxl::RefCounted::RefCounted(this);
  *((_QWORD *)this + 3) = v2;
  *((_BYTE *)this + 32) = 0;
  std::wstring::wstring((char *)this + 40);
  *(_QWORD *)this = &cxl::ManualResetEvent::`vftable';
  return this;
}

```

## disassembly

```asm
0x18001a994  push    rbx
0x18001a996  sub     rsp, 0D0h
0x18001a99d  mov     rax, cs:__security_cookie
0x18001a9a4  xor     rax, rsp
0x18001a9a7  mov     [rsp+0D8h+var_18], rax
0x18001a9af  mov     rbx, rcx
0x18001a9b2  mov     [rsp+0D8h+var_B8], rcx
0x18001a9b7  xor     r9d, r9d; lpName
0x18001a9ba  xor     r8d, r8d; bInitialState
0x18001a9bd  lea     edx, [r9+1]; bManualReset
0x18001a9c1  xor     ecx, ecx; lpEventAttributes
0x18001a9c3  call    cs:__imp_CreateEventW
0x18001a9c9  mov     rdx, rax
0x18001a9cc  test    rax, rax
0x18001a9cf  jnz     short loc_18001AA1B
0x18001a9d1  lea     rdx, aCreateeventwNu_0; "::CreateEventW(nullptr, true, initialSt"...
0x18001a9d8  lea     rcx, [rsp+0D8h+var_B0]
0x18001a9dd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001a9e2  nop
0x18001a9e3  call    cs:__imp_GetLastError
0x18001a9e9  mov     dword ptr [rsp+0D8h+var_B8], eax
0x18001a9ed  mov     dword ptr [rsp+0D8h+var_B8+4], 0
0x18001a9f5  lea     r8, [rsp+0D8h+var_B0]
0x18001a9fa  lea     rdx, [rsp+0D8h+var_B8]
0x18001a9ff  lea     rcx, [rsp+0D8h+pExceptionObject]
0x18001aa04  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001aa09  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001aa10  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18001aa15  call    _CxxThrowException_0
0x18001aa1b  mov     rcx, rbx; this
0x18001aa1e  call    ??0RefCounted@cxl@@QEAA@XZ; cxl::RefCounted::RefCounted(void)
0x18001aa23  mov     [rbx+18h], rdx
0x18001aa27  mov     byte ptr [rbx+20h], 0
0x18001aa2b  lea     rcx, [rbx+28h]
0x18001aa2f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001aa34  lea     rcx, ??_7ManualResetEvent@cxl@@6B@; const cxl::ManualResetEvent::`vftable'
0x18001aa3b  mov     [rbx], rcx
0x18001aa3e  mov     rax, rbx
0x18001aa41  mov     rcx, [rsp+0D8h+var_18]
0x18001aa49  xor     rcx, rsp; StackCookie
0x18001aa4c  call    __security_check_cookie
0x18001aa51  add     rsp, 0D0h
0x18001aa58  pop     rbx
0x18001aa59  retn
```

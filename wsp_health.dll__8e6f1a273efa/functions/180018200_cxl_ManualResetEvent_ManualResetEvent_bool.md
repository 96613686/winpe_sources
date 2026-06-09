# cxl::ManualResetEvent::ManualResetEvent(bool)

- ea: `0x180018200`
- end: `0x1800182d3`
- name: `??0ManualResetEvent@cxl@@QEAA@_N@Z`
- size: `211`
- prototype: `__int64 __fastcall(cxl::ManualResetEvent *__hidden this, bool)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180018f88`
- `0x18001ee7c`
- `0x180075b80`
- `0x18007c648`

## callees

- `0x180002b50`
- `0x1800035c0`
- `0x18000cd9c`
- `0x18000cde0`
- `0x18000ce84`
- `0x18000dec0`
- `0x180018200`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001822f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001822f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018255`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018255`

## string_xrefs

- `0x180018243`: `::CreateEventW(nullptr, true, initialState, nullptr)`

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
0x180018200  push    rbx
0x180018202  sub     rsp, 0D0h
0x180018209  mov     rax, cs:__security_cookie
0x180018210  xor     rax, rsp
0x180018213  mov     [rsp+0D8h+var_18], rax
0x18001821b  mov     rbx, rcx
0x18001821e  mov     [rsp+0D8h+var_B8], rcx
0x180018223  xor     r9d, r9d; lpName
0x180018226  xor     r8d, r8d; bInitialState
0x180018229  lea     edx, [r9+1]; bManualReset
0x18001822d  xor     ecx, ecx; lpEventAttributes
0x18001822f  call    cs:__imp_CreateEventW
0x180018236  nop     dword ptr [rax+rax+00h]
0x18001823b  mov     rdx, rax
0x18001823e  test    rax, rax
0x180018241  jnz     short loc_180018293
0x180018243  lea     rdx, aCreateeventwNu_0; "::CreateEventW(nullptr, true, initialSt"...
0x18001824a  lea     rcx, [rsp+0D8h+var_B0]
0x18001824f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180018254  nop
0x180018255  call    cs:__imp_GetLastError
0x18001825c  nop     dword ptr [rax+rax+00h]
0x180018261  mov     dword ptr [rsp+0D8h+var_B8], eax
0x180018265  mov     dword ptr [rsp+0D8h+var_B8+4], 0
0x18001826d  lea     r8, [rsp+0D8h+var_B0]
0x180018272  lea     rdx, [rsp+0D8h+var_B8]
0x180018277  lea     rcx, [rsp+0D8h+pExceptionObject]
0x18001827c  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180018281  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180018288  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18001828d  call    _CxxThrowException_0
0x180018293  mov     rcx, rbx; this
0x180018296  call    ??0RefCounted@cxl@@QEAA@XZ; cxl::RefCounted::RefCounted(void)
0x18001829b  mov     [rbx+18h], rdx
0x18001829f  mov     byte ptr [rbx+20h], 0
0x1800182a3  lea     rcx, [rbx+28h]
0x1800182a7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800182ac  lea     rcx, ??_7ManualResetEvent@cxl@@6B@; const cxl::ManualResetEvent::`vftable'
0x1800182b3  mov     [rbx], rcx
0x1800182b6  mov     rax, rbx
0x1800182b9  mov     rcx, [rsp+0D8h+var_18]
0x1800182c1  xor     rcx, rsp; StackCookie
0x1800182c4  call    __security_check_cookie
0x1800182c9  add     rsp, 0D0h
0x1800182d0  pop     rbx
0x1800182d1  retn
```

# cxl::ManualResetEvent::ManualResetEvent(bool)

- ea: `0x1800178ac`
- end: `0x180017972`
- name: `??0ManualResetEvent@cxl@@QEAA@_N@Z`
- size: `198`
- prototype: `__int64 __fastcall(cxl::ManualResetEvent *__hidden this, bool)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x1800185d4`
- `0x18001e2bc`
- `0x180073d60`
- `0x18007a4d8`

## callees

- `0x180002ae0`
- `0x180003520`
- `0x18000c9f0`
- `0x18000ca34`
- `0x18000cad8`
- `0x18000da90`
- `0x1800178ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800178db`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800178db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178fb`

## string_xrefs

- `0x1800178e9`: `::CreateEventW(nullptr, true, initialState, nullptr)`

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
0x1800178ac  push    rbx
0x1800178ae  sub     rsp, 0D0h
0x1800178b5  mov     rax, cs:__security_cookie
0x1800178bc  xor     rax, rsp
0x1800178bf  mov     [rsp+0D8h+var_18], rax
0x1800178c7  mov     rbx, rcx
0x1800178ca  mov     [rsp+0D8h+var_B8], rcx
0x1800178cf  xor     r9d, r9d; lpName
0x1800178d2  xor     r8d, r8d; bInitialState
0x1800178d5  lea     edx, [r9+1]; bManualReset
0x1800178d9  xor     ecx, ecx; lpEventAttributes
0x1800178db  call    cs:__imp_CreateEventW
0x1800178e1  mov     rdx, rax
0x1800178e4  test    rax, rax
0x1800178e7  jnz     short loc_180017933
0x1800178e9  lea     rdx, aCreateeventwNu_0; "::CreateEventW(nullptr, true, initialSt"...
0x1800178f0  lea     rcx, [rsp+0D8h+var_B0]
0x1800178f5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800178fa  nop
0x1800178fb  call    cs:__imp_GetLastError
0x180017901  mov     dword ptr [rsp+0D8h+var_B8], eax
0x180017905  mov     dword ptr [rsp+0D8h+var_B8+4], 0
0x18001790d  lea     r8, [rsp+0D8h+var_B0]
0x180017912  lea     rdx, [rsp+0D8h+var_B8]
0x180017917  lea     rcx, [rsp+0D8h+pExceptionObject]
0x18001791c  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180017921  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180017928  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18001792d  call    _CxxThrowException_0
0x180017933  mov     rcx, rbx; this
0x180017936  call    ??0RefCounted@cxl@@QEAA@XZ; cxl::RefCounted::RefCounted(void)
0x18001793b  mov     [rbx+18h], rdx
0x18001793f  mov     byte ptr [rbx+20h], 0
0x180017943  lea     rcx, [rbx+28h]
0x180017947  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001794c  lea     rcx, ??_7ManualResetEvent@cxl@@6B@; const cxl::ManualResetEvent::`vftable'
0x180017953  mov     [rbx], rcx
0x180017956  mov     rax, rbx
0x180017959  mov     rcx, [rsp+0D8h+var_18]
0x180017961  xor     rcx, rsp; StackCookie
0x180017964  call    __security_check_cookie
0x180017969  add     rsp, 0D0h
0x180017970  pop     rbx
0x180017971  retn
```

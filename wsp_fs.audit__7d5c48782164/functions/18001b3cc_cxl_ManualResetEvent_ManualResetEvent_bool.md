# cxl::ManualResetEvent::ManualResetEvent(bool)

- ea: `0x18001b3cc`
- end: `0x18001b49f`
- name: `??0ManualResetEvent@cxl@@QEAA@_N@Z`
- size: `211`
- prototype: `__int64 __fastcall(cxl::ManualResetEvent *__hidden this, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001c158`
- `0x1800224ec`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000e520`
- `0x18001b3cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b3fb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b3fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b421`

## string_xrefs

- `0x18001b40f`: `::CreateEventW(nullptr, true, initialState, nullptr)`

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
0x18001b3cc  push    rbx
0x18001b3ce  sub     rsp, 0D0h
0x18001b3d5  mov     rax, cs:__security_cookie
0x18001b3dc  xor     rax, rsp
0x18001b3df  mov     [rsp+0D8h+var_18], rax
0x18001b3e7  mov     rbx, rcx
0x18001b3ea  mov     [rsp+0D8h+var_B8], rcx
0x18001b3ef  xor     r9d, r9d; lpName
0x18001b3f2  xor     r8d, r8d; bInitialState
0x18001b3f5  lea     edx, [r9+1]; bManualReset
0x18001b3f9  xor     ecx, ecx; lpEventAttributes
0x18001b3fb  call    cs:__imp_CreateEventW
0x18001b402  nop     dword ptr [rax+rax+00h]
0x18001b407  mov     rdx, rax
0x18001b40a  test    rax, rax
0x18001b40d  jnz     short loc_18001B45F
0x18001b40f  lea     rdx, aCreateeventwNu_0; "::CreateEventW(nullptr, true, initialSt"...
0x18001b416  lea     rcx, [rsp+0D8h+var_B0]
0x18001b41b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001b420  nop
0x18001b421  call    cs:__imp_GetLastError
0x18001b428  nop     dword ptr [rax+rax+00h]
0x18001b42d  mov     dword ptr [rsp+0D8h+var_B8], eax
0x18001b431  mov     dword ptr [rsp+0D8h+var_B8+4], 0
0x18001b439  lea     r8, [rsp+0D8h+var_B0]
0x18001b43e  lea     rdx, [rsp+0D8h+var_B8]
0x18001b443  lea     rcx, [rsp+0D8h+pExceptionObject]
0x18001b448  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001b44d  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001b454  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18001b459  call    _CxxThrowException_0
0x18001b45f  mov     rcx, rbx; this
0x18001b462  call    ??0RefCounted@cxl@@QEAA@XZ; cxl::RefCounted::RefCounted(void)
0x18001b467  mov     [rbx+18h], rdx
0x18001b46b  mov     byte ptr [rbx+20h], 0
0x18001b46f  lea     rcx, [rbx+28h]
0x18001b473  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001b478  lea     rcx, ??_7ManualResetEvent@cxl@@6B@; const cxl::ManualResetEvent::`vftable'
0x18001b47f  mov     [rbx], rcx
0x18001b482  mov     rax, rbx
0x18001b485  mov     rcx, [rsp+0D8h+var_18]
0x18001b48d  xor     rcx, rsp; StackCookie
0x18001b490  call    __security_check_cookie
0x18001b495  add     rsp, 0D0h
0x18001b49c  pop     rbx
0x18001b49d  retn
```

# ClusWmi::TaskManager::Initialize(void)

- ea: `0x18001d094`
- end: `0x18001d17d`
- name: `?Initialize@TaskManager@ClusWmi@@AEAAXXZ`
- size: `233`
- prototype: `void __fastcall(ClusWmi::TaskManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800176d4`

## callees

- `0x180002ae0`
- `0x180003520`
- `0x18000c9f0`
- `0x18000cad8`
- `0x180013f94`
- `0x1800140e8`
- `0x180015964`
- `0x18001d094`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d0f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d0f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d0cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d0cf`

## string_xrefs

- `0x18001d13b`: `Failed to open token`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ClusWmi::TaskManager::Initialize(ClusWmi::TaskManager *this)
{
  cxl::Token *v1; // rdi
  HANDLE CurrentThread; // rax
  unsigned int v3; // ebx
  HANDLE CurrentProcess; // rax
  __int64 v5; // rax
  _DWORD v6[2]; // [rsp+20h] [rbp-C8h] BYREF
  _QWORD v7[3]; // [rsp+28h] [rbp-C0h] BYREF
  _BYTE v8[32]; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+60h] [rbp-88h] BYREF

  v7[2] = 0;
  v7[0] = &cxl::Sid::`vftable';
  v1 = (ClusWmi::TaskManager *)((char *)this + 224);
  CurrentThread = GetCurrentThread();
  v3 = cxl::Token::TryOpenThreadToken(v1, 0x2000Eu, 1, CurrentThread);
  if ( v3 == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    cxl::Token::OpenProcessToken((void **)v1, 0x2000Eu, CurrentProcess);
  }
  else if ( v3 )
  {
    v5 = std::wstring::wstring(v8, L"Failed to open token");
    v6[0] = v3;
    v6[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v6, v5);
    throw (cxl::Exception *)pExceptionObject;
  }
  cxl::Sid::~Sid((cxl::Sid *)v7);
}

```

## disassembly

```asm
0x18001d094  mov     [rsp+arg_8], rbx
0x18001d099  push    rdi
0x18001d09a  sub     rsp, 0E0h
0x18001d0a1  mov     rax, cs:__security_cookie
0x18001d0a8  xor     rax, rsp
0x18001d0ab  mov     [rsp+0E8h+var_18], rax
0x18001d0b3  mov     [rsp+0E8h+var_B0], 0
0x18001d0bc  lea     rax, ??_7Sid@cxl@@6B@; const cxl::Sid::`vftable'
0x18001d0c3  mov     [rsp+0E8h+var_C0], rax
0x18001d0c8  lea     rdi, [rcx+0E0h]
0x18001d0cf  call    cs:__imp_GetCurrentThread
0x18001d0d5  mov     r9, rax; void *
0x18001d0d8  mov     edx, 2000Eh; unsigned int
0x18001d0dd  mov     r8d, 1; int
0x18001d0e3  mov     rcx, rdi; this
0x18001d0e6  call    ?TryOpenThreadToken@Token@cxl@@QEAAKKHPEAX@Z; cxl::Token::TryOpenThreadToken(ulong,int,void *)
0x18001d0eb  mov     ebx, eax
0x18001d0ed  cmp     eax, 3F0h
0x18001d0f2  jnz     short loc_18001D10C
0x18001d0f4  call    cs:__imp_GetCurrentProcess
0x18001d0fa  mov     r8, rax; void *
0x18001d0fd  mov     edx, 2000Eh; unsigned int
0x18001d102  mov     rcx, rdi; this
0x18001d105  call    ?OpenProcessToken@Token@cxl@@QEAAXKPEAX@Z; cxl::Token::OpenProcessToken(ulong,void *)
0x18001d10a  jmp     short loc_18001D110
0x18001d10c  test    ebx, ebx
0x18001d10e  jnz     short loc_18001D13B
0x18001d110  lea     rcx, [rsp+0E8h+var_C0]; this
0x18001d115  call    ??1Sid@cxl@@UEAA@XZ; cxl::Sid::~Sid(void)
0x18001d11a  mov     rcx, [rsp+0E8h+var_18]
0x18001d122  xor     rcx, rsp; StackCookie
0x18001d125  call    __security_check_cookie
0x18001d12a  mov     rbx, [rsp+0E8h+arg_8]
0x18001d132  add     rsp, 0E0h
0x18001d139  pop     rdi
0x18001d13a  retn
0x18001d13b  lea     rdx, aFailedToOpenTo; "Failed to open token"
0x18001d142  lea     rcx, [rsp+0E8h+var_A8]
0x18001d147  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001d14c  nop
0x18001d14d  mov     [rsp+0E8h+var_C8], ebx
0x18001d151  mov     [rsp+0E8h+var_C4], 0
0x18001d159  mov     r8, rax
0x18001d15c  lea     rdx, [rsp+0E8h+var_C8]
0x18001d161  lea     rcx, [rsp+0E8h+pExceptionObject]
0x18001d166  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001d16b  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001d172  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18001d177  call    _CxxThrowException_0
```

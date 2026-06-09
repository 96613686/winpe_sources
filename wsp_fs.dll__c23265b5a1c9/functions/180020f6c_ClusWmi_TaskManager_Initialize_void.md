# ClusWmi::TaskManager::Initialize(void)

- ea: `0x180020f6c`
- end: `0x180021062`
- name: `?Initialize@TaskManager@ClusWmi@@AEAAXXZ`
- size: `246`
- prototype: `void __fastcall(ClusWmi::TaskManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callers

- `0x18001b1f4`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000d6a4`
- `0x1800160a8`
- `0x180016300`
- `0x180018f08`
- `0x180020f6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020fd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020fd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020fa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020fa7`

## string_xrefs

- `0x180021020`: `Failed to open token`

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
0x180020f6c  mov     [rsp+arg_8], rbx
0x180020f71  push    rdi
0x180020f72  sub     rsp, 0E0h
0x180020f79  mov     rax, cs:__security_cookie
0x180020f80  xor     rax, rsp
0x180020f83  mov     [rsp+0E8h+var_18], rax
0x180020f8b  mov     [rsp+0E8h+var_B0], 0
0x180020f94  lea     rax, ??_7Sid@cxl@@6B@; const cxl::Sid::`vftable'
0x180020f9b  mov     [rsp+0E8h+var_C0], rax
0x180020fa0  lea     rdi, [rcx+0E0h]
0x180020fa7  call    cs:__imp_GetCurrentThread
0x180020fae  nop     dword ptr [rax+rax+00h]
0x180020fb3  mov     r9, rax; void *
0x180020fb6  mov     edx, 2000Eh; unsigned int
0x180020fbb  mov     r8d, 1; int
0x180020fc1  mov     rcx, rdi; this
0x180020fc4  call    ?TryOpenThreadToken@Token@cxl@@QEAAKKHPEAX@Z; cxl::Token::TryOpenThreadToken(ulong,int,void *)
0x180020fc9  mov     ebx, eax
0x180020fcb  cmp     eax, 3F0h
0x180020fd0  jnz     short loc_180020FF0
0x180020fd2  call    cs:__imp_GetCurrentProcess
0x180020fd9  nop     dword ptr [rax+rax+00h]
0x180020fde  mov     r8, rax; void *
0x180020fe1  mov     edx, 2000Eh; unsigned int
0x180020fe6  mov     rcx, rdi; this
0x180020fe9  call    ?OpenProcessToken@Token@cxl@@QEAAXKPEAX@Z; cxl::Token::OpenProcessToken(ulong,void *)
0x180020fee  jmp     short loc_180020FF4
0x180020ff0  test    ebx, ebx
0x180020ff2  jnz     short loc_180021020
0x180020ff4  lea     rcx, [rsp+0E8h+var_C0]; this
0x180020ff9  call    ??1Sid@cxl@@UEAA@XZ; cxl::Sid::~Sid(void)
0x180020ffe  mov     rcx, [rsp+0E8h+var_18]
0x180021006  xor     rcx, rsp; StackCookie
0x180021009  call    __security_check_cookie
0x18002100e  mov     rbx, [rsp+0E8h+arg_8]
0x180021016  add     rsp, 0E0h
0x18002101d  pop     rdi
0x18002101e  retn
0x180021020  lea     rdx, aFailedToOpenTo; "Failed to open token"
0x180021027  lea     rcx, [rsp+0E8h+var_A8]
0x18002102c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180021031  nop
0x180021032  mov     [rsp+0E8h+var_C8], ebx
0x180021036  mov     [rsp+0E8h+var_C4], 0
0x18002103e  mov     r8, rax
0x180021041  lea     rdx, [rsp+0E8h+var_C8]
0x180021046  lea     rcx, [rsp+0E8h+pExceptionObject]
0x18002104b  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180021050  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180021057  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18002105c  call    _CxxThrowException_0
```

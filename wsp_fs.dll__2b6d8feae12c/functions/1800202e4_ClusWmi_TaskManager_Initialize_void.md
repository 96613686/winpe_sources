# ClusWmi::TaskManager::Initialize(void)

- ea: `0x1800202e4`
- end: `0x1800203cd`
- name: `?Initialize@TaskManager@ClusWmi@@AEAAXXZ`
- size: `233`
- prototype: `void __fastcall(ClusWmi::TaskManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callers

- `0x18001a7bc`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000d33c`
- `0x180015968`
- `0x180015b9c`
- `0x180018698`
- `0x1800202e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020344`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020344`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002031f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002031f`

## string_xrefs

- `0x18002038b`: `Failed to open token`

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
0x1800202e4  mov     [rsp+arg_8], rbx
0x1800202e9  push    rdi
0x1800202ea  sub     rsp, 0E0h
0x1800202f1  mov     rax, cs:__security_cookie
0x1800202f8  xor     rax, rsp
0x1800202fb  mov     [rsp+0E8h+var_18], rax
0x180020303  mov     [rsp+0E8h+var_B0], 0
0x18002030c  lea     rax, ??_7Sid@cxl@@6B@; const cxl::Sid::`vftable'
0x180020313  mov     [rsp+0E8h+var_C0], rax
0x180020318  lea     rdi, [rcx+0E0h]
0x18002031f  call    cs:__imp_GetCurrentThread
0x180020325  mov     r9, rax; void *
0x180020328  mov     edx, 2000Eh; unsigned int
0x18002032d  mov     r8d, 1; int
0x180020333  mov     rcx, rdi; this
0x180020336  call    ?TryOpenThreadToken@Token@cxl@@QEAAKKHPEAX@Z; cxl::Token::TryOpenThreadToken(ulong,int,void *)
0x18002033b  mov     ebx, eax
0x18002033d  cmp     eax, 3F0h
0x180020342  jnz     short loc_18002035C
0x180020344  call    cs:__imp_GetCurrentProcess
0x18002034a  mov     r8, rax; void *
0x18002034d  mov     edx, 2000Eh; unsigned int
0x180020352  mov     rcx, rdi; this
0x180020355  call    ?OpenProcessToken@Token@cxl@@QEAAXKPEAX@Z; cxl::Token::OpenProcessToken(ulong,void *)
0x18002035a  jmp     short loc_180020360
0x18002035c  test    ebx, ebx
0x18002035e  jnz     short loc_18002038B
0x180020360  lea     rcx, [rsp+0E8h+var_C0]; this
0x180020365  call    ??1Sid@cxl@@UEAA@XZ; cxl::Sid::~Sid(void)
0x18002036a  mov     rcx, [rsp+0E8h+var_18]
0x180020372  xor     rcx, rsp; StackCookie
0x180020375  call    __security_check_cookie
0x18002037a  mov     rbx, [rsp+0E8h+arg_8]
0x180020382  add     rsp, 0E0h
0x180020389  pop     rdi
0x18002038a  retn
0x18002038b  lea     rdx, aFailedToOpenTo; "Failed to open token"
0x180020392  lea     rcx, [rsp+0E8h+var_A8]
0x180020397  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002039c  nop
0x18002039d  mov     [rsp+0E8h+var_C8], ebx
0x1800203a1  mov     [rsp+0E8h+var_C4], 0
0x1800203a9  mov     r8, rax
0x1800203ac  lea     rdx, [rsp+0E8h+var_C8]
0x1800203b1  lea     rcx, [rsp+0E8h+pExceptionObject]
0x1800203b6  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800203bb  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800203c2  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x1800203c7  call    _CxxThrowException_0
```

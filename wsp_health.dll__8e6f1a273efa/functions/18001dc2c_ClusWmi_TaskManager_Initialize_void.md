# ClusWmi::TaskManager::Initialize(void)

- ea: `0x18001dc2c`
- end: `0x18001dd22`
- name: `?Initialize@TaskManager@ClusWmi@@AEAAXXZ`
- size: `246`
- prototype: `void __fastcall(ClusWmi::TaskManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callers

- `0x180018028`

## callees

- `0x180002b50`
- `0x1800035c0`
- `0x18000cd9c`
- `0x18000ce84`
- `0x180014708`
- `0x180014878`
- `0x180016148`
- `0x18001dc2c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001dc92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001dc92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001dc67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001dc67`

## string_xrefs

- `0x18001dce0`: `Failed to open token`

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
0x18001dc2c  mov     [rsp+arg_8], rbx
0x18001dc31  push    rdi
0x18001dc32  sub     rsp, 0E0h
0x18001dc39  mov     rax, cs:__security_cookie
0x18001dc40  xor     rax, rsp
0x18001dc43  mov     [rsp+0E8h+var_18], rax
0x18001dc4b  mov     [rsp+0E8h+var_B0], 0
0x18001dc54  lea     rax, ??_7Sid@cxl@@6B@; const cxl::Sid::`vftable'
0x18001dc5b  mov     [rsp+0E8h+var_C0], rax
0x18001dc60  lea     rdi, [rcx+0E0h]
0x18001dc67  call    cs:__imp_GetCurrentThread
0x18001dc6e  nop     dword ptr [rax+rax+00h]
0x18001dc73  mov     r9, rax; void *
0x18001dc76  mov     edx, 2000Eh; unsigned int
0x18001dc7b  mov     r8d, 1; int
0x18001dc81  mov     rcx, rdi; this
0x18001dc84  call    ?TryOpenThreadToken@Token@cxl@@QEAAKKHPEAX@Z; cxl::Token::TryOpenThreadToken(ulong,int,void *)
0x18001dc89  mov     ebx, eax
0x18001dc8b  cmp     eax, 3F0h
0x18001dc90  jnz     short loc_18001DCB0
0x18001dc92  call    cs:__imp_GetCurrentProcess
0x18001dc99  nop     dword ptr [rax+rax+00h]
0x18001dc9e  mov     r8, rax; void *
0x18001dca1  mov     edx, 2000Eh; unsigned int
0x18001dca6  mov     rcx, rdi; this
0x18001dca9  call    ?OpenProcessToken@Token@cxl@@QEAAXKPEAX@Z; cxl::Token::OpenProcessToken(ulong,void *)
0x18001dcae  jmp     short loc_18001DCB4
0x18001dcb0  test    ebx, ebx
0x18001dcb2  jnz     short loc_18001DCE0
0x18001dcb4  lea     rcx, [rsp+0E8h+var_C0]; this
0x18001dcb9  call    ??1Sid@cxl@@UEAA@XZ; cxl::Sid::~Sid(void)
0x18001dcbe  mov     rcx, [rsp+0E8h+var_18]
0x18001dcc6  xor     rcx, rsp; StackCookie
0x18001dcc9  call    __security_check_cookie
0x18001dcce  mov     rbx, [rsp+0E8h+arg_8]
0x18001dcd6  add     rsp, 0E0h
0x18001dcdd  pop     rdi
0x18001dcde  retn
0x18001dce0  lea     rdx, aFailedToOpenTo; "Failed to open token"
0x18001dce7  lea     rcx, [rsp+0E8h+var_A8]
0x18001dcec  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dcf1  nop
0x18001dcf2  mov     [rsp+0E8h+var_C8], ebx
0x18001dcf6  mov     [rsp+0E8h+var_C4], 0
0x18001dcfe  mov     r8, rax
0x18001dd01  lea     rdx, [rsp+0E8h+var_C8]
0x18001dd06  lea     rcx, [rsp+0E8h+pExceptionObject]
0x18001dd0b  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001dd10  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001dd17  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18001dd1c  call    _CxxThrowException_0
```

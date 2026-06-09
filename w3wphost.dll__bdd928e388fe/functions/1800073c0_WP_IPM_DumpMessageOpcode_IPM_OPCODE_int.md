# WP_IPM::DumpMessageOpcode(IPM_OPCODE,int)

- ea: `0x1800073c0`
- end: `0x180007478`
- name: `?DumpMessageOpcode@WP_IPM@@AEAAXW4IPM_OPCODE@@H@Z`
- size: `184`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001170`
- `0x180001830`

## callees

- `0x18000c39e`
- `0x18000c3d0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180007446`
- `msvcrt!swprintf_s` at `0x180007446`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007451`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007451`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007404`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007404`
- `iisutil!?GetStringizedIpmOpcode@IPM_MESSAGE_PIPE@@SAPEBGW4IPM_OPCODE@@@Z` at `0x18000740c`
- `iisutil!?GetStringizedIpmOpcode@IPM_MESSAGE_PIPE@@SAPEBGW4IPM_OPCODE@@@Z` at `0x18000740c`

## pseudocode

```c
void __fastcall WP_IPM::DumpMessageOpcode(__int64 a1, unsigned int a2, int a3)
{
  __int64 StringizedIpmOpcode; // rax
  const wchar_t *v6; // rcx
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-228h] BYREF
  wchar_t Buffer[256]; // [rsp+40h] [rbp-218h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  StringizedIpmOpcode = IPM_MESSAGE_PIPE::GetStringizedIpmOpcode(a2);
  v6 = L"Sent";
  if ( !a3 )
    v6 = L"Received";
  swprintf_s(Buffer, 0x100u, L"(%I64u) W3WP %s: %s\n", PerformanceCount.QuadPart, v6, StringizedIpmOpcode);
  OutputDebugStringW(Buffer);
}

```

## disassembly

```asm
0x1800073c0  mov     [rsp+arg_0], rbx
0x1800073c5  push    rdi
0x1800073c6  sub     rsp, 250h
0x1800073cd  mov     rax, cs:__security_cookie
0x1800073d4  xor     rax, rsp
0x1800073d7  mov     [rsp+258h+var_18], rax
0x1800073df  mov     edi, r8d
0x1800073e2  lea     rcx, [rsp+258h+Buffer]; void *
0x1800073e7  mov     ebx, edx
0x1800073e9  mov     r8d, 200h; Size
0x1800073ef  xor     edx, edx; Val
0x1800073f1  call    memset_0
0x1800073f6  lea     rcx, [rsp+258h+PerformanceCount]; lpPerformanceCount
0x1800073fb  mov     qword ptr [rsp+258h+PerformanceCount], 0
0x180007404  call    cs:__imp_QueryPerformanceCounter
0x18000740a  mov     ecx, ebx
0x18000740c  call    cs:__imp_?GetStringizedIpmOpcode@IPM_MESSAGE_PIPE@@SAPEBGW4IPM_OPCODE@@@Z; IPM_MESSAGE_PIPE::GetStringizedIpmOpcode(IPM_OPCODE)
0x180007412  mov     r9, qword ptr [rsp+258h+PerformanceCount]
0x180007417  lea     rdx, aReceived; "Received"
0x18000741e  mov     [rsp+258h+var_230], rax
0x180007423  lea     rcx, aSent; "Sent"
0x18000742a  test    edi, edi
0x18000742c  lea     r8, aI64uW3wpSS; "(%I64u) W3WP %s: %s\n"
0x180007433  cmovz   rcx, rdx
0x180007437  mov     edx, 100h; BufferCount
0x18000743c  mov     [rsp+258h+var_238], rcx
0x180007441  lea     rcx, [rsp+258h+Buffer]; Buffer
0x180007446  call    cs:__imp_swprintf_s
0x18000744c  lea     rcx, [rsp+258h+Buffer]; lpOutputString
0x180007451  call    cs:__imp_OutputDebugStringW
0x180007457  mov     rcx, [rsp+258h+var_18]
0x18000745f  xor     rcx, rsp; StackCookie
0x180007462  call    __security_check_cookie
0x180007467  mov     rbx, [rsp+258h+arg_0]
0x18000746f  add     rsp, 250h
0x180007476  pop     rdi
0x180007477  retn
```

# WP_IPM::DumpMessageOpcode(IPM_OPCODE,int)

- ea: `0x180007b48`
- end: `0x180007c19`
- name: `?DumpMessageOpcode@WP_IPM@@AEAAXW4IPM_OPCODE@@H@Z`
- size: `209`
- prototype: `void __fastcall(__int64, unsigned int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001180`
- `0x180001890`

## callees

- `0x18000d2be`
- `0x18000d2f0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180007bda`
- `msvcrt!swprintf_s` at `0x180007bda`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007beb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007beb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007b8c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007b8c`
- `iisutil!?GetStringizedIpmOpcode@IPM_MESSAGE_PIPE@@SAPEBGW4IPM_OPCODE@@@Z` at `0x180007b9a`
- `iisutil!?GetStringizedIpmOpcode@IPM_MESSAGE_PIPE@@SAPEBGW4IPM_OPCODE@@@Z` at `0x180007b9a`

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
0x180007b48  mov     [rsp+arg_0], rbx
0x180007b4d  push    rdi
0x180007b4e  sub     rsp, 250h
0x180007b55  mov     rax, cs:__security_cookie
0x180007b5c  xor     rax, rsp
0x180007b5f  mov     [rsp+258h+var_18], rax
0x180007b67  mov     edi, r8d
0x180007b6a  lea     rcx, [rsp+258h+Buffer]; void *
0x180007b6f  mov     ebx, edx
0x180007b71  mov     r8d, 200h; Size
0x180007b77  xor     edx, edx; Val
0x180007b79  call    memset_0
0x180007b7e  lea     rcx, [rsp+258h+PerformanceCount]; lpPerformanceCount
0x180007b83  mov     qword ptr [rsp+258h+PerformanceCount], 0
0x180007b8c  call    cs:__imp_QueryPerformanceCounter
0x180007b93  nop     dword ptr [rax+rax+00h]
0x180007b98  mov     ecx, ebx
0x180007b9a  call    cs:__imp_?GetStringizedIpmOpcode@IPM_MESSAGE_PIPE@@SAPEBGW4IPM_OPCODE@@@Z; IPM_MESSAGE_PIPE::GetStringizedIpmOpcode(IPM_OPCODE)
0x180007ba1  nop     dword ptr [rax+rax+00h]
0x180007ba6  mov     r9, qword ptr [rsp+258h+PerformanceCount]
0x180007bab  lea     rdx, aReceived; "Received"
0x180007bb2  mov     [rsp+258h+var_230], rax
0x180007bb7  lea     rcx, aSent; "Sent"
0x180007bbe  test    edi, edi
0x180007bc0  lea     r8, aI64uW3wpSS; "(%I64u) W3WP %s: %s\n"
0x180007bc7  cmovz   rcx, rdx
0x180007bcb  mov     edx, 100h; BufferCount
0x180007bd0  mov     [rsp+258h+var_238], rcx
0x180007bd5  lea     rcx, [rsp+258h+Buffer]; Buffer
0x180007bda  call    cs:__imp_swprintf_s
0x180007be1  nop     dword ptr [rax+rax+00h]
0x180007be6  lea     rcx, [rsp+258h+Buffer]; lpOutputString
0x180007beb  call    cs:__imp_OutputDebugStringW
0x180007bf2  nop     dword ptr [rax+rax+00h]
0x180007bf7  mov     rcx, [rsp+258h+var_18]
0x180007bff  xor     rcx, rsp; StackCookie
0x180007c02  call    __security_check_cookie
0x180007c07  mov     rbx, [rsp+258h+arg_0]
0x180007c0f  add     rsp, 250h
0x180007c16  pop     rdi
0x180007c17  retn
```

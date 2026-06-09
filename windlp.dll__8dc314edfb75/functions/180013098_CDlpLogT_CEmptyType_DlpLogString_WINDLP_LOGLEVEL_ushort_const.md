# CDlpLogT<CEmptyType>::DlpLogString(WINDLP_LOGLEVEL,ushort const *)

- ea: `0x180013098`
- end: `0x1800131e6`
- name: `?DlpLogString@?$CDlpLogT@VCEmptyType@@@@SAJW4WINDLP_LOGLEVEL@@PEBG@Z`
- size: `334`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180012f5c`

## callees

- `0x18000aba4`
- `0x180013098`
- `0x180017488`
- `0x18001fd60`
- `0x180028640`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013121`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001315c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013121`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001315c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001319a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800131bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001319a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800131bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800131a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800131ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800131a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800131ca`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013188`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013188`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800130b7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800130b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDlpLogT<CEmptyType>::DlpLogString(int a1, __int64 a2)
{
  unsigned __int16 *v2; // rbp
  LPCWSTR v3; // rdi
  unsigned int v6; // esi
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  const wchar_t *v10; // rbx
  int v11; // eax
  DWORD v12; // eax
  int v13; // eax
  DWORD CurrentThreadId; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v16; // rax
  LPCWSTR lpOutputString; // [rsp+60h] [rbp+18h] BYREF
  unsigned __int16 *v19; // [rsp+68h] [rbp+20h] BYREF

  v2 = 0;
  v3 = 0;
  v19 = 0;
  lpOutputString = 0;
  if ( IsDebuggerPresent() )
  {
    v7 = a1 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          if ( v9 == 1 )
            v10 = L"ERROR";
          else
            v10 = L"UNKNOWN";
        }
        else
        {
          v10 = L"WARNING";
        }
      }
      else
      {
        v10 = L"INFO";
      }
    }
    else
    {
      v10 = L"DEBUG";
    }
    v11 = CDlpHelpersT<CEmptyType>::FormatSystemTime(&v19);
    v2 = v19;
    if ( v11 < 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = STRAPI_Format(
              (unsigned __int16 **)&lpOutputString,
              L"DLPLOG: [0x%X] [%s] [%s]\n\r",
              CurrentThreadId,
              v10,
              a2);
    }
    else
    {
      v12 = GetCurrentThreadId();
      v13 = STRAPI_Format((unsigned __int16 **)&lpOutputString, L"%s, DLPLOG: [0x%X] [%s] [%s]\n\r", v2, v12, v10, a2);
    }
    v6 = v13;
    if ( v13 >= 0 )
    {
      v3 = lpOutputString;
      OutputDebugStringW(lpOutputString);
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
      v3 = lpOutputString;
    }
  }
  else
  {
    v6 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(0);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v3 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v2 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v2 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v6;
}

```

## disassembly

```asm
0x180013098  mov     [rsp+arg_0], rbx
0x18001309d  push    rbp
0x18001309e  push    rsi
0x18001309f  push    rdi
0x1800130a0  sub     rsp, 30h
0x1800130a4  xor     ebp, ebp
0x1800130a6  xor     edi, edi
0x1800130a8  mov     [rsp+48h+arg_18], rbp
0x1800130ad  mov     rsi, rdx
0x1800130b0  mov     [rsp+48h+lpOutputString], rdi
0x1800130b5  mov     ebx, ecx
0x1800130b7  call    cs:__imp_IsDebuggerPresent
0x1800130bd  test    eax, eax
0x1800130bf  jnz     short loc_1800130CF
0x1800130c1  xor     esi, esi
0x1800130c3  xor     ecx, ecx
0x1800130c5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800130ca  jmp     loc_18001318E
0x1800130cf  sub     ebx, 1
0x1800130d2  jz      short loc_180013107
0x1800130d4  sub     ebx, 1
0x1800130d7  jz      short loc_1800130FE
0x1800130d9  sub     ebx, 1
0x1800130dc  jz      short loc_1800130F5
0x1800130de  cmp     ebx, 1
0x1800130e1  jz      short loc_1800130EC
0x1800130e3  lea     rbx, aUnknown; "UNKNOWN"
0x1800130ea  jmp     short loc_18001310E
0x1800130ec  lea     rbx, aError_0; "ERROR"
0x1800130f3  jmp     short loc_18001310E
0x1800130f5  lea     rbx, aWarning; "WARNING"
0x1800130fc  jmp     short loc_18001310E
0x1800130fe  lea     rbx, aInfo; "INFO"
0x180013105  jmp     short loc_18001310E
0x180013107  lea     rbx, aDebug; "DEBUG"
0x18001310e  lea     rcx, [rsp+48h+arg_18]; unsigned __int16 **
0x180013113  call    ?FormatSystemTime@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z; CDlpHelpersT<CEmptyType>::FormatSystemTime(ushort * *)
0x180013118  mov     rbp, [rsp+48h+arg_18]
0x18001311d  test    eax, eax
0x18001311f  js      short loc_18001315C
0x180013121  call    cs:__imp_GetCurrentThreadId
0x180013127  mov     [rsp+48h+var_20], rsi
0x18001312c  lea     rdx, aSDlplog0xXSS; "%s, DLPLOG: [0x%X] [%s] [%s]\n\r"
0x180013133  mov     r9d, eax
0x180013136  mov     [rsp+48h+var_28], rbx
0x18001313b  mov     r8, rbp
0x18001313e  lea     rcx, [rsp+48h+lpOutputString]; unsigned __int16 **
0x180013143  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x180013148  mov     esi, eax
0x18001314a  test    eax, eax
0x18001314c  jns     short loc_180013180
0x18001314e  mov     ecx, eax
0x180013150  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180013155  mov     rdi, [rsp+48h+lpOutputString]
0x18001315a  jmp     short loc_18001318E
0x18001315c  call    cs:__imp_GetCurrentThreadId
0x180013162  mov     r9, rbx
0x180013165  mov     [rsp+48h+var_28], rsi
0x18001316a  mov     r8d, eax
0x18001316d  lea     rdx, aDlplog0xXSS; "DLPLOG: [0x%X] [%s] [%s]\n\r"
0x180013174  lea     rcx, [rsp+48h+lpOutputString]; unsigned __int16 **
0x180013179  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x18001317e  jmp     short loc_180013148
0x180013180  mov     rdi, [rsp+48h+lpOutputString]
0x180013185  mov     rcx, rdi; lpOutputString
0x180013188  call    cs:__imp_OutputDebugStringW
0x18001318e  mov     ecx, esi
0x180013190  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180013195  test    rdi, rdi
0x180013198  jz      short loc_1800131B6
0x18001319a  call    cs:__imp_GetProcessHeap
0x1800131a0  lea     r8, [rdi-4]; lpMem
0x1800131a4  xor     edx, edx; dwFlags
0x1800131a6  mov     rcx, rax; hHeap
0x1800131a9  call    cs:__imp_HeapFree
0x1800131af  xor     ecx, ecx
0x1800131b1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800131b6  test    rbp, rbp
0x1800131b9  jz      short loc_1800131D7
0x1800131bb  call    cs:__imp_GetProcessHeap
0x1800131c1  lea     r8, [rbp-4]; lpMem
0x1800131c5  xor     edx, edx; dwFlags
0x1800131c7  mov     rcx, rax; hHeap
0x1800131ca  call    cs:__imp_HeapFree
0x1800131d0  xor     ecx, ecx
0x1800131d2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800131d7  mov     rbx, [rsp+48h+arg_0]
0x1800131dc  mov     eax, esi
0x1800131de  add     rsp, 30h
0x1800131e2  pop     rdi
0x1800131e3  pop     rsi
0x1800131e4  pop     rbp
0x1800131e5  retn
```

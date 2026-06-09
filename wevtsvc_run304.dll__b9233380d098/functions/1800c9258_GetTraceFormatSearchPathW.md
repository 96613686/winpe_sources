# GetTraceFormatSearchPathW

- ea: `0x1800c9258`
- end: `0x1800c938b`
- name: `GetTraceFormatSearchPathW`
- size: `307`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800cc044`
- `0x1800ccc10`

## callees

- `0x18009bb88`
- `0x1800c9258`
- `0x1800cce68`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c9295`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c92ef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c9356`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c936e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c9295`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c92ef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c9356`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c936e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800c92a7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800c9304`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800c92a7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800c9304`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800c931a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800c931a`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800c9283`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800c92d1`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800c9283`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800c92d1`

## string_xrefs

- `0x1800c9277`: `TRACE_FORMAT_SEARCH_PATH`
- `0x1800c92c5`: `TRACE_FORMAT_SEARCH_PATH`

## pseudocode

```c
__int64 GetTraceFormatSearchPathW()
{
  void *v0; // rdi
  signed int EnvironmentVariableW; // eax
  DWORD i; // esi
  void *v3; // rax
  DWORD v4; // ebx
  WCHAR *v5; // rax
  WCHAR *v6; // rbx
  signed int CurrentDirectoryW; // eax

  if ( !qword_180111990 )
  {
    v0 = 0;
    EnvironmentVariableW = GetEnvironmentVariableW(L"TRACE_FORMAT_SEARCH_PATH", 0, 0);
    for ( i = EnvironmentVariableW; EnvironmentVariableW > 0; EnvironmentVariableW = i - v4 )
    {
      if ( v0 )
        free(v0);
      v3 = malloc(2LL * (int)(i + 1));
      v0 = v3;
      if ( !v3 )
        break;
      memset_0(v3, 0, 2LL * (int)(i + 1));
      v4 = i;
      i = GetEnvironmentVariableW(L"TRACE_FORMAT_SEARCH_PATH", (LPWSTR)v0, i);
    }
    if ( _InterlockedCompareExchange64(&qword_180111990, (signed __int64)v0, 0) )
      free(v0);
    if ( !qword_180111990 )
    {
      v5 = (WCHAR *)malloc(0x208u);
      v6 = v5;
      if ( v5 )
      {
        CurrentDirectoryW = GetCurrentDirectoryW(0x104u, v5);
        if ( !CurrentDirectoryW || CurrentDirectoryW > 259 )
        {
          if ( TracePrinter )
          {
            if ( DebugExtPrint )
              TracePrinterExt((wchar_t *)L"Could Not get current dir\n");
            else
              TracePrinter(L"Could Not get current dir\n");
          }
          free(v6);
          v6 = 0;
        }
      }
      if ( _InterlockedCompareExchange64(&qword_180111990, (signed __int64)v6, 0) )
        free(v6);
    }
  }
  return qword_180111990;
}

```

## disassembly

```asm
0x1800c9258  mov     [rsp+arg_8], rbx
0x1800c925d  mov     [rsp+arg_10], rsi
0x1800c9262  push    rdi
0x1800c9263  sub     rsp, 20h
0x1800c9267  cmp     cs:qword_180111990, 0
0x1800c926f  jnz     loc_1800C9374
0x1800c9275  xor     edi, edi
0x1800c9277  lea     rcx, aTraceFormatSea; "TRACE_FORMAT_SEARCH_PATH"
0x1800c927e  xor     r8d, r8d; nSize
0x1800c9281  xor     edx, edx; lpBuffer
0x1800c9283  call    cs:__imp_GetEnvironmentVariableW
0x1800c9289  mov     esi, eax
0x1800c928b  jmp     short loc_1800C92DB
0x1800c928d  test    rdi, rdi
0x1800c9290  jz      short loc_1800C929B
0x1800c9292  mov     rcx, rdi; Block
0x1800c9295  call    cs:__imp_free
0x1800c929b  lea     eax, [rsi+1]
0x1800c929e  movsxd  rbx, eax
0x1800c92a1  add     rbx, rbx
0x1800c92a4  mov     rcx, rbx; Size
0x1800c92a7  call    cs:__imp_malloc
0x1800c92ad  mov     rdi, rax
0x1800c92b0  test    rax, rax
0x1800c92b3  jz      short loc_1800C92DF
0x1800c92b5  mov     r8, rbx; Size
0x1800c92b8  xor     edx, edx; Val
0x1800c92ba  mov     rcx, rax; void *
0x1800c92bd  call    memset_0
0x1800c92c2  mov     r8d, esi; nSize
0x1800c92c5  lea     rcx, aTraceFormatSea; "TRACE_FORMAT_SEARCH_PATH"
0x1800c92cc  mov     rdx, rdi; lpBuffer
0x1800c92cf  mov     ebx, esi
0x1800c92d1  call    cs:__imp_GetEnvironmentVariableW
0x1800c92d7  mov     esi, eax
0x1800c92d9  sub     eax, ebx
0x1800c92db  test    eax, eax
0x1800c92dd  jg      short loc_1800C928D
0x1800c92df  xor     eax, eax
0x1800c92e1  lock cmpxchg cs:qword_180111990, rdi
0x1800c92ea  jz      short loc_1800C92F5
0x1800c92ec  mov     rcx, rdi; Block
0x1800c92ef  call    cs:__imp_free
0x1800c92f5  cmp     cs:qword_180111990, 0
0x1800c92fd  jnz     short loc_1800C9374
0x1800c92ff  mov     ecx, 208h; Size
0x1800c9304  call    cs:__imp_malloc
0x1800c930a  mov     rbx, rax
0x1800c930d  test    rax, rax
0x1800c9310  jz      short loc_1800C935E
0x1800c9312  mov     rdx, rax; lpBuffer
0x1800c9315  mov     ecx, 104h; nBufferLength
0x1800c931a  call    cs:__imp_GetCurrentDirectoryW
0x1800c9320  test    eax, eax
0x1800c9322  jz      short loc_1800C932B
0x1800c9324  cmp     eax, 103h
0x1800c9329  jle     short loc_1800C935E
0x1800c932b  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x1800c9332  test    rax, rax
0x1800c9335  jz      short loc_1800C9353
0x1800c9337  cmp     cs:?DebugExtPrint@@3HA, 0; int DebugExtPrint
0x1800c933e  lea     rcx, aCouldNotGetCur; "Could Not get current dir\n"
0x1800c9345  jnz     short loc_1800C934E
0x1800c9347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c934c  jmp     short loc_1800C9353
0x1800c934e  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x1800c9353  mov     rcx, rbx; Block
0x1800c9356  call    cs:__imp_free
0x1800c935c  xor     ebx, ebx
0x1800c935e  xor     eax, eax
0x1800c9360  lock cmpxchg cs:qword_180111990, rbx
0x1800c9369  jz      short loc_1800C9374
0x1800c936b  mov     rcx, rbx; Block
0x1800c936e  call    cs:__imp_free
0x1800c9374  mov     rax, cs:qword_180111990
0x1800c937b  mov     rbx, [rsp+28h+arg_8]
0x1800c9380  mov     rsi, [rsp+28h+arg_10]
0x1800c9385  add     rsp, 20h
0x1800c9389  pop     rdi
0x1800c938a  retn
```

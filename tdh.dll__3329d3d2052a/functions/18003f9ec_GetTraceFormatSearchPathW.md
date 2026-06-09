# GetTraceFormatSearchPathW

- ea: `0x18003f9ec`
- end: `0x18003fb1f`
- name: `GetTraceFormatSearchPathW`
- size: `307`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004260c`
- `0x180042d84`

## callees

- `0x180021490`
- `0x18003f9ec`
- `0x180042f7c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003fa29`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003fa83`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003faea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003fb02`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003fa29`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003fa83`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003faea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003fb02`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003fa3b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003fa98`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003fa3b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003fa98`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18003fa17`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18003fa65`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18003fa17`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18003fa65`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18003faae`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18003faae`

## string_xrefs

- `0x18003fa0b`: `TRACE_FORMAT_SEARCH_PATH`
- `0x18003fa59`: `TRACE_FORMAT_SEARCH_PATH`

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

  if ( !qword_18006CE18 )
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
    if ( _InterlockedCompareExchange64(&qword_18006CE18, (signed __int64)v0, 0) )
      free(v0);
    if ( !qword_18006CE18 )
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
      if ( _InterlockedCompareExchange64(&qword_18006CE18, (signed __int64)v6, 0) )
        free(v6);
    }
  }
  return qword_18006CE18;
}

```

## disassembly

```asm
0x18003f9ec  mov     [rsp+arg_8], rbx
0x18003f9f1  mov     [rsp+arg_10], rsi
0x18003f9f6  push    rdi
0x18003f9f7  sub     rsp, 20h
0x18003f9fb  cmp     cs:qword_18006CE18, 0
0x18003fa03  jnz     loc_18003FB08
0x18003fa09  xor     edi, edi
0x18003fa0b  lea     rcx, Name; "TRACE_FORMAT_SEARCH_PATH"
0x18003fa12  xor     r8d, r8d; nSize
0x18003fa15  xor     edx, edx; lpBuffer
0x18003fa17  call    cs:__imp_GetEnvironmentVariableW
0x18003fa1d  mov     esi, eax
0x18003fa1f  jmp     short loc_18003FA6F
0x18003fa21  test    rdi, rdi
0x18003fa24  jz      short loc_18003FA2F
0x18003fa26  mov     rcx, rdi; Block
0x18003fa29  call    cs:__imp_free
0x18003fa2f  lea     eax, [rsi+1]
0x18003fa32  movsxd  rbx, eax
0x18003fa35  add     rbx, rbx
0x18003fa38  mov     rcx, rbx; Size
0x18003fa3b  call    cs:__imp_malloc
0x18003fa41  mov     rdi, rax
0x18003fa44  test    rax, rax
0x18003fa47  jz      short loc_18003FA73
0x18003fa49  mov     r8, rbx; Size
0x18003fa4c  xor     edx, edx; Val
0x18003fa4e  mov     rcx, rax; void *
0x18003fa51  call    memset_0
0x18003fa56  mov     r8d, esi; nSize
0x18003fa59  lea     rcx, Name; "TRACE_FORMAT_SEARCH_PATH"
0x18003fa60  mov     rdx, rdi; lpBuffer
0x18003fa63  mov     ebx, esi
0x18003fa65  call    cs:__imp_GetEnvironmentVariableW
0x18003fa6b  mov     esi, eax
0x18003fa6d  sub     eax, ebx
0x18003fa6f  test    eax, eax
0x18003fa71  jg      short loc_18003FA21
0x18003fa73  xor     eax, eax
0x18003fa75  lock cmpxchg cs:qword_18006CE18, rdi
0x18003fa7e  jz      short loc_18003FA89
0x18003fa80  mov     rcx, rdi; Block
0x18003fa83  call    cs:__imp_free
0x18003fa89  cmp     cs:qword_18006CE18, 0
0x18003fa91  jnz     short loc_18003FB08
0x18003fa93  mov     ecx, 208h; Size
0x18003fa98  call    cs:__imp_malloc
0x18003fa9e  mov     rbx, rax
0x18003faa1  test    rax, rax
0x18003faa4  jz      short loc_18003FAF2
0x18003faa6  mov     rdx, rax; lpBuffer
0x18003faa9  mov     ecx, 104h; nBufferLength
0x18003faae  call    cs:__imp_GetCurrentDirectoryW
0x18003fab4  test    eax, eax
0x18003fab6  jz      short loc_18003FABF
0x18003fab8  cmp     eax, 103h
0x18003fabd  jle     short loc_18003FAF2
0x18003fabf  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x18003fac6  test    rax, rax
0x18003fac9  jz      short loc_18003FAE7
0x18003facb  cmp     cs:?DebugExtPrint@@3HA, 0; int DebugExtPrint
0x18003fad2  lea     rcx, aCouldNotGetCur; "Could Not get current dir\n"
0x18003fad9  jnz     short loc_18003FAE2
0x18003fadb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fae0  jmp     short loc_18003FAE7
0x18003fae2  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x18003fae7  mov     rcx, rbx; Block
0x18003faea  call    cs:__imp_free
0x18003faf0  xor     ebx, ebx
0x18003faf2  xor     eax, eax
0x18003faf4  lock cmpxchg cs:qword_18006CE18, rbx
0x18003fafd  jz      short loc_18003FB08
0x18003faff  mov     rcx, rbx; Block
0x18003fb02  call    cs:__imp_free
0x18003fb08  mov     rax, cs:qword_18006CE18
0x18003fb0f  mov     rbx, [rsp+28h+arg_8]
0x18003fb14  mov     rsi, [rsp+28h+arg_10]
0x18003fb19  add     rsp, 20h
0x18003fb1d  pop     rdi
0x18003fb1e  retn
```

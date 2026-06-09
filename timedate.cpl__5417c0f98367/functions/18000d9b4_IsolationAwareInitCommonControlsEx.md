# IsolationAwareInitCommonControlsEx

- ea: `0x18000d9b4`
- end: `0x18000da77`
- name: `IsolationAwareInitCommonControlsEx`
- size: `195`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b24c`
- `0x1800175b8`
- `0x18001f928`

## callees

- `0x180009a60`
- `0x18000d908`
- `0x18000d9b4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029478`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000da5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029498`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000da5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029498`
- `KERNEL32!DeactivateActCtx` at `0x18000da53`
- `KERNEL32!DeactivateActCtx` at `0x18002948c`
- `KERNEL32!DeactivateActCtx` at `0x18000da53`
- `KERNEL32!DeactivateActCtx` at `0x18002948c`

## string_xrefs

- `0x18000d9f9`: `InitCommonControlsEx`

## pseudocode

```c
__int64 __fastcall IsolationAwareInitCommonControlsEx(__int64 a1)
{
  unsigned int v2; // edi
  __int64 (__fastcall *v3)(__int64); // rbx
  __int64 result; // rax
  __int64 v5; // rax
  int v6; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v3 = (__int64 (__fastcall *)(__int64))`IsolationAwareInitCommonControlsEx'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk && !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    result = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie);
    if ( !(_DWORD)result )
      return result;
  }
  if ( !v3 )
  {
    v5 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("InitCommonControlsEx");
    v3 = (__int64 (__fastcall *)(__int64))v5;
    if ( !v5 )
      goto LABEL_8;
    `IsolationAwareInitCommonControlsEx'::`2'::s_pfn = v5;
  }
  v2 = v3(a1);
LABEL_8:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v2 )
    {
      v6 = 0;
      LastError = 0;
    }
    else
    {
      v6 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v6 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x18000d9b4  mov     rax, rsp
0x18000d9b7  mov     [rax+8], rbx
0x18000d9bb  mov     [rax+18h], rsi
0x18000d9bf  push    rdi
0x18000d9c0  sub     rsp, 30h
0x18000d9c4  mov     rsi, rcx
0x18000d9c7  xor     edi, edi
0x18000d9c9  mov     [rax-18h], edi
0x18000d9cc  mov     rbx, cs:?s_pfn@?1??IsolationAwareInitCommonControlsEx@@9@4P6AHPEBUtagINITCOMMONCONTROLSEX@@@ZEA; int (*`IsolationAwareInitCommonControlsEx'::`2'::s_pfn)(tagINITCOMMONCONTROLSEX const *)
0x18000d9d3  mov     [rax+10h], rdi
0x18000d9d7  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x18000d9dd  jnz     short loc_18000D9F4
0x18000d9df  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x18000d9e5  jnz     short loc_18000D9F4
0x18000d9e7  lea     rcx, [rax+10h]; lpCookie
0x18000d9eb  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000d9f0  test    eax, eax
0x18000d9f2  jz      short loc_18000DA67
0x18000d9f4  test    rbx, rbx
0x18000d9f7  jnz     short loc_18000DA14
0x18000d9f9  lea     rcx, aInitcommoncont; "InitCommonControlsEx"
0x18000da00  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18000da05  mov     rbx, rax
0x18000da08  test    rax, rax
0x18000da0b  jz      short loc_18000DA25
0x18000da0d  mov     cs:?s_pfn@?1??IsolationAwareInitCommonControlsEx@@9@4P6AHPEBUtagINITCOMMONCONTROLSEX@@@ZEA, rax; int (*`IsolationAwareInitCommonControlsEx'::`2'::s_pfn)(tagINITCOMMONCONTROLSEX const *)
0x18000da14  mov     rcx, rsi
0x18000da17  mov     rax, rbx
0x18000da1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da1f  mov     edi, eax
0x18000da21  mov     [rsp+38h+var_18], eax
0x18000da25  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000da2c  jz      short loc_18000DA37
0x18000da2e  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000da35  jnz     short loc_18000DA65
0x18000da37  test    edi, edi
0x18000da39  jnz     short loc_18000DA48
0x18000da3b  lea     esi, [rdi+1]
0x18000da3e  call    cs:__imp_GetLastError
0x18000da44  mov     ebx, eax
0x18000da46  jmp     short loc_18000DA4C
0x18000da48  xor     esi, esi
0x18000da4a  xor     ebx, ebx
0x18000da4c  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000da51  xor     ecx, ecx; dwFlags
0x18000da53  call    cs:__imp_DeactivateActCtx
0x18000da59  test    esi, esi
0x18000da5b  jz      short loc_18000DA65
0x18000da5d  mov     ecx, ebx; dwErrCode
0x18000da5f  call    cs:__imp_SetLastError
0x18000da65  mov     eax, edi
0x18000da67  mov     rbx, [rsp+38h+arg_0]
0x18000da6c  mov     rsi, [rsp+38h+arg_10]
0x18000da71  add     rsp, 30h
0x18000da75  pop     rdi
0x18000da76  retn
0x180029450  push    rbx
0x180029452  push    rbp
0x180029453  push    rdi
0x180029454  sub     rsp, 20h
0x180029458  mov     rbp, rdx
0x18002945b  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180029462  jz      short loc_18002946D
0x180029464  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002946b  jnz     short loc_18002949F
0x18002946d  cmp     dword ptr [rbp+20h], 0
0x180029471  jnz     short loc_180029482
0x180029473  mov     edi, 1
0x180029478  call    cs:__imp_GetLastError
0x18002947e  mov     ebx, eax
0x180029480  jmp     short loc_180029486
0x180029482  xor     edi, edi
0x180029484  xor     ebx, ebx
0x180029486  mov     rdx, [rbp+48h]; ulCookie
0x18002948a  xor     ecx, ecx; dwFlags
0x18002948c  call    cs:__imp_DeactivateActCtx
0x180029492  test    edi, edi
0x180029494  jz      short loc_18002949F
0x180029496  mov     ecx, ebx; dwErrCode
0x180029498  call    cs:__imp_SetLastError
0x18002949e  nop
0x18002949f  add     rsp, 20h
0x1800294a3  pop     rdi
0x1800294a4  pop     rbp
0x1800294a5  pop     rbx
0x1800294a6  retn
```

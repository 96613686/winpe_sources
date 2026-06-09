# IsolationAwareLoadLibraryExW

- ea: `0x18000d368`
- end: `0x18000d41f`
- name: `IsolationAwareLoadLibraryExW`
- size: `183`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002d788`

## callees

- `0x18000d368`
- `0x18000d428`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000d3cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000d3cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fa26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fa26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d414`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fa46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d414`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fa46`
- `KERNEL32!DeactivateActCtx` at `0x18000d408`
- `KERNEL32!DeactivateActCtx` at `0x18002fa3a`
- `KERNEL32!DeactivateActCtx` at `0x18000d408`
- `KERNEL32!DeactivateActCtx` at `0x18002fa3a`

## pseudocode

```c
HMODULE __fastcall IsolationAwareLoadLibraryExW(LPCWSTR lpLibFileName, __int64 a2, DWORD a3)
{
  HMODULE Library; // rax
  HMODULE v7; // rbx
  int v8; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Library = LoadLibraryExW(lpLibFileName, 0, a3);
  v7 = Library;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Library )
    {
      v8 = 0;
      LastError = 0;
    }
    else
    {
      v8 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v8 )
      SetLastError(LastError);
  }
  return v7;
}

```

## disassembly

```asm
0x18000d368  mov     rax, rsp
0x18000d36b  mov     [rax+8], rbx
0x18000d36f  mov     [rax+18h], rsi
0x18000d373  mov     [rax+10h], rdx
0x18000d377  push    rdi
0x18000d378  sub     rsp, 30h
0x18000d37c  mov     ebx, r8d
0x18000d37f  mov     rdi, rcx
0x18000d382  mov     qword ptr [rax-18h], 0
0x18000d38a  mov     qword ptr [rax+10h], 0
0x18000d392  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000d399  jnz     short loc_18000D3C3
0x18000d39b  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000d3a2  jnz     short loc_18000D3C3
0x18000d3a4  lea     rcx, [rax+10h]; lpCookie
0x18000d3a8  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000d3ad  test    eax, eax
0x18000d3af  jnz     short loc_18000D3C3
0x18000d3b1  xor     eax, eax
0x18000d3b3  mov     rbx, [rsp+38h+arg_0]
0x18000d3b8  mov     rsi, [rsp+38h+arg_10]
0x18000d3bd  add     rsp, 30h
0x18000d3c1  pop     rdi
0x18000d3c2  retn
0x18000d3c3  mov     r8d, ebx; dwFlags
0x18000d3c6  xor     edx, edx; hFile
0x18000d3c8  mov     rcx, rdi; lpLibFileName
0x18000d3cb  call    cs:__imp_LoadLibraryExW
0x18000d3d1  mov     rbx, rax
0x18000d3d4  mov     [rsp+38h+var_18], rax
0x18000d3d9  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000d3e0  jz      short loc_18000D3EB
0x18000d3e2  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000d3e9  jnz     short loc_18000D41A
0x18000d3eb  test    rbx, rbx
0x18000d3ee  jnz     short loc_18000D3FD
0x18000d3f0  lea     esi, [rbx+1]
0x18000d3f3  call    cs:__imp_GetLastError
0x18000d3f9  mov     edi, eax
0x18000d3fb  jmp     short loc_18000D401
0x18000d3fd  xor     esi, esi
0x18000d3ff  xor     edi, edi
0x18000d401  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000d406  xor     ecx, ecx; dwFlags
0x18000d408  call    cs:__imp_DeactivateActCtx
0x18000d40e  test    esi, esi
0x18000d410  jz      short loc_18000D41A
0x18000d412  mov     ecx, edi; dwErrCode
0x18000d414  call    cs:__imp_SetLastError
0x18000d41a  mov     rax, rbx
0x18000d41d  jmp     short loc_18000D3B3
0x18002f9fd  push    rbx
0x18002f9ff  push    rbp
0x18002fa00  push    rdi
0x18002fa01  sub     rsp, 20h
0x18002fa05  mov     rbp, rdx
0x18002fa08  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002fa0f  jz      short loc_18002FA1A
0x18002fa11  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002fa18  jnz     short loc_18002FA4D
0x18002fa1a  cmp     qword ptr [rbp+20h], 0
0x18002fa1f  jnz     short loc_18002FA30
0x18002fa21  mov     edi, 1
0x18002fa26  call    cs:__imp_GetLastError
0x18002fa2c  mov     ebx, eax
0x18002fa2e  jmp     short loc_18002FA34
0x18002fa30  xor     edi, edi
0x18002fa32  xor     ebx, ebx
0x18002fa34  mov     rdx, [rbp+48h]; ulCookie
0x18002fa38  xor     ecx, ecx; dwFlags
0x18002fa3a  call    cs:__imp_DeactivateActCtx
0x18002fa40  test    edi, edi
0x18002fa42  jz      short loc_18002FA4D
0x18002fa44  mov     ecx, ebx; dwErrCode
0x18002fa46  call    cs:__imp_SetLastError
0x18002fa4c  nop
0x18002fa4d  add     rsp, 20h
0x18002fa51  pop     rdi
0x18002fa52  pop     rbp
0x18002fa53  pop     rbx
0x18002fa54  retn
```

# PrvImpersonatePrinterClient

- ea: `0x180001e38`
- end: `0x180001e8e`
- name: `PrvImpersonatePrinterClient`
- size: `86`
- prototype: `__int64 __fastcall(HANDLE hObject)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180001e00`

## callees

- `0x180001e38`
- `0x180001e94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001e4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001e4d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001e65`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001e65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001e7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001e7b`

## pseudocode

```c
_BOOL8 __fastcall PrvImpersonatePrinterClient(HANDLE hObject)
{
  BOOL v3; // edi

  if ( hObject )
  {
    v3 = !(unsigned int)ImpersonationToken(hObject) || SetThreadToken(0, hObject);
    CloseHandle(hObject);
    return v3;
  }
  else
  {
    SetLastError(6u);
    return 0;
  }
}

```

## disassembly

```asm
0x180001e38  mov     [rsp+arg_0], rbx
0x180001e3d  push    rdi
0x180001e3e  sub     rsp, 20h
0x180001e42  mov     rbx, rcx
0x180001e45  test    rcx, rcx
0x180001e48  jnz     short loc_180001E57
0x180001e4a  lea     ecx, [rbx+6]; dwErrCode
0x180001e4d  call    cs:__imp_SetLastError
0x180001e53  xor     eax, eax
0x180001e55  jmp     short loc_180001E83
0x180001e57  call    ?ImpersonationToken@@YAHPEAX@Z; ImpersonationToken(void *)
0x180001e5c  test    eax, eax
0x180001e5e  jz      short loc_180001E73
0x180001e60  mov     rdx, rbx; Token
0x180001e63  xor     ecx, ecx; Thread
0x180001e65  call    cs:__imp_SetThreadToken
0x180001e6b  test    eax, eax
0x180001e6d  jnz     short loc_180001E73
0x180001e6f  xor     edi, edi
0x180001e71  jmp     short loc_180001E78
0x180001e73  mov     edi, 1
0x180001e78  mov     rcx, rbx; hObject
0x180001e7b  call    cs:__imp_CloseHandle
0x180001e81  mov     eax, edi
0x180001e83  mov     rbx, [rsp+28h+arg_0]
0x180001e88  add     rsp, 20h
0x180001e8c  pop     rdi
0x180001e8d  retn
```

# CreateEnvironmentBlock

- ea: `0x180008b40`
- end: `0x180008b72`
- name: `CreateEnvironmentBlock`
- size: `50`
- prototype: `BOOL __stdcall(LPVOID *lpEnvironment, HANDLE hToken, BOOL bInherit)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b62`
- `profapi!__imp_CreateEnvBlock` at `0x180008b44`
- `profapi!__imp_CreateEnvBlock` at `0x180008b44`

## pseudocode

```c
BOOL __stdcall CreateEnvironmentBlock(LPVOID *lpEnvironment, HANDLE hToken, BOOL bInherit)
{
  int EnvBlock; // eax

  EnvBlock = CreateEnvBlock(lpEnvironment, hToken, bInherit);
  if ( EnvBlock >= 0 )
    return 1;
  SetLastError((unsigned __int16)EnvBlock);
  return 0;
}

```

## disassembly

```asm
0x180008b40  sub     rsp, 28h
0x180008b44  call    cs:__imp_CreateEnvBlock
0x180008b4b  nop     dword ptr [rax+rax+00h]
0x180008b50  test    eax, eax
0x180008b52  js      short loc_180008B5F
0x180008b54  mov     eax, 1
0x180008b59  add     rsp, 28h
0x180008b5d  retn
0x180008b5f  movzx   ecx, ax; dwErrCode
0x180008b62  call    cs:__imp_SetLastError
0x180008b69  nop     dword ptr [rax+rax+00h]
0x180008b6e  xor     eax, eax
0x180008b70  jmp     short loc_180008B59
```

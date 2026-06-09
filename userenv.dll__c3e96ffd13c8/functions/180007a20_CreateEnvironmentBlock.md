# CreateEnvironmentBlock

- ea: `0x180007a20`
- end: `0x180007a45`
- name: `CreateEnvironmentBlock`
- size: `37`
- prototype: `BOOL __stdcall(LPVOID *lpEnvironment, HANDLE hToken, BOOL bInherit)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007a20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007a3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007a3b`
- `profapi!__imp_CreateEnvBlock` at `0x180007a24`
- `profapi!__imp_CreateEnvBlock` at `0x180007a24`

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
0x180007a20  sub     rsp, 28h
0x180007a24  call    cs:__imp_CreateEnvBlock
0x180007a2a  test    eax, eax
0x180007a2c  js      short loc_180007A38
0x180007a2e  mov     eax, 1
0x180007a33  add     rsp, 28h
0x180007a37  retn
0x180007a38  movzx   ecx, ax; dwErrCode
0x180007a3b  call    cs:__imp_SetLastError
0x180007a41  xor     eax, eax
0x180007a43  jmp     short loc_180007A33
```

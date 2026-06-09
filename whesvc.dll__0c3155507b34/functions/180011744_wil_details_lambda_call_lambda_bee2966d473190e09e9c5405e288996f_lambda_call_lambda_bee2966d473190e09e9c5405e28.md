# wil::details::lambda_call__lambda_bee2966d473190e09e9c5405e288996f___::_lambda_call__lambda_bee2966d473190e09e9c5405e288996f___

- ea: `0x180011744`
- end: `0x180011765`
- name: `wil::details::lambda_call__lambda_bee2966d473190e09e9c5405e288996f___::_lambda_call__lambda_bee2966d473190e09e9c5405e288996f___`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002755e`

## callees

- `0x180011744`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18001175a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18001175a`

## pseudocode

```c
BOOL __fastcall wil::details::lambda_call__lambda_bee2966d473190e09e9c5405e288996f___::_lambda_call__lambda_bee2966d473190e09e9c5405e288996f___(
        __int64 a1)
{
  BOOL result; // eax

  if ( *(_BYTE *)(a1 + 8) )
  {
    *(_BYTE *)(a1 + 8) = 0;
    return TerminateThread(*(HANDLE *)a1, 0x3E3u);
  }
  return result;
}

```

## disassembly

```asm
0x180011744  sub     rsp, 28h
0x180011748  cmp     byte ptr [rcx+8], 0
0x18001174c  jz      short loc_180011760
0x18001174e  mov     byte ptr [rcx+8], 0
0x180011752  mov     edx, 3E3h; dwExitCode
0x180011757  mov     rcx, [rcx]; hThread
0x18001175a  call    cs:__imp_TerminateThread
0x180011760  add     rsp, 28h
0x180011764  retn
```

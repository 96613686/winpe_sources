# PrvImpersonatePrinterClient

- ea: `0x180001e98`
- end: `0x180001f01`
- name: `PrvImpersonatePrinterClient`
- size: `105`
- prototype: `_BOOL8 __fastcall(HANDLE hObject)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180001e60`

## callees

- `0x180001e98`
- `0x180001f08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001ead`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001ead`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001ecb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001ecb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001ee7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001ee7`

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
0x180001e98  mov     [rsp+arg_0], rbx
0x180001e9d  push    rdi
0x180001e9e  sub     rsp, 20h
0x180001ea2  mov     rbx, rcx
0x180001ea5  test    rcx, rcx
0x180001ea8  jnz     short loc_180001EBD
0x180001eaa  lea     ecx, [rbx+6]; dwErrCode
0x180001ead  call    cs:__imp_SetLastError
0x180001eb4  nop     dword ptr [rax+rax+00h]
0x180001eb9  xor     eax, eax
0x180001ebb  jmp     short loc_180001EF5
0x180001ebd  call    ?ImpersonationToken@@YAHPEAX@Z; ImpersonationToken(void *)
0x180001ec2  test    eax, eax
0x180001ec4  jz      short loc_180001EDF
0x180001ec6  mov     rdx, rbx; Token
0x180001ec9  xor     ecx, ecx; Thread
0x180001ecb  call    cs:__imp_SetThreadToken
0x180001ed2  nop     dword ptr [rax+rax+00h]
0x180001ed7  test    eax, eax
0x180001ed9  jnz     short loc_180001EDF
0x180001edb  xor     edi, edi
0x180001edd  jmp     short loc_180001EE4
0x180001edf  mov     edi, 1
0x180001ee4  mov     rcx, rbx; hObject
0x180001ee7  call    cs:__imp_CloseHandle
0x180001eee  nop     dword ptr [rax+rax+00h]
0x180001ef3  mov     eax, edi
0x180001ef5  mov     rbx, [rsp+28h+arg_0]
0x180001efa  add     rsp, 20h
0x180001efe  pop     rdi
0x180001eff  retn
```

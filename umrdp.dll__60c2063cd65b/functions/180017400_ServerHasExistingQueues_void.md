# ServerHasExistingQueues(void *)

- ea: `0x180017400`
- end: `0x18001748e`
- name: `?ServerHasExistingQueues@@YAHPEAX@Z`
- size: `142`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015428`

## callees

- `0x180017400`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017422`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001745a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017422`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001745a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017479`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001746f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001746f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180017416`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180017416`
- `WINSPOOL!EnumPrintersW` at `0x180017450`
- `WINSPOOL!EnumPrintersW` at `0x180017450`

## pseudocode

```c
_BOOL8 __fastcall ServerHasExistingQueues(void *a1)
{
  BOOL v1; // ebx
  DWORD pcbNeeded; // [rsp+58h] [rbp+10h] BYREF
  DWORD pcReturned; // [rsp+60h] [rbp+18h] BYREF

  pcbNeeded = 0;
  pcReturned = 0;
  v1 = ImpersonateLoggedOnUser(a1);
  if ( !v1 )
    GetLastError();
  if ( !EnumPrintersW(2u, 0, 4u, 0, 0, &pcbNeeded, &pcReturned) && GetLastError() != 122 )
    GetLastError();
  if ( v1 && !RevertToSelf() )
    GetLastError();
  return pcbNeeded != 0;
}

```

## disassembly

```asm
0x180017400  push    rbx
0x180017402  sub     rsp, 40h
0x180017406  mov     [rsp+48h+arg_8], 0
0x18001740e  mov     [rsp+48h+arg_10], 0
0x180017416  call    cs:__imp_ImpersonateLoggedOnUser
0x18001741c  mov     ebx, eax
0x18001741e  test    eax, eax
0x180017420  jnz     short loc_180017428
0x180017422  call    cs:__imp_GetLastError
0x180017428  lea     rax, [rsp+48h+arg_10]
0x18001742d  xor     r9d, r9d; pPrinterEnum
0x180017430  mov     [rsp+48h+pcReturned], rax; pcReturned
0x180017435  xor     edx, edx; Name
0x180017437  lea     rax, [rsp+48h+arg_8]
0x18001743c  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x180017441  lea     r8d, [r9+4]; Level
0x180017445  mov     [rsp+48h+cbBuf], 0; cbBuf
0x18001744d  lea     ecx, [rdx+2]; Flags
0x180017450  call    cs:__imp_EnumPrintersW
0x180017456  test    eax, eax
0x180017458  jnz     short loc_18001746B
0x18001745a  call    cs:__imp_GetLastError
0x180017460  cmp     eax, 7Ah ; 'z'
0x180017463  jz      short loc_18001746B
0x180017465  call    cs:__imp_GetLastError
0x18001746b  test    ebx, ebx
0x18001746d  jz      short loc_18001747F
0x18001746f  call    cs:__imp_RevertToSelf
0x180017475  test    eax, eax
0x180017477  jnz     short loc_18001747F
0x180017479  call    cs:__imp_GetLastError
0x18001747f  xor     eax, eax
0x180017481  cmp     [rsp+48h+arg_8], eax
0x180017485  setnbe  al
0x180017488  add     rsp, 40h
0x18001748c  pop     rbx
0x18001748d  retn
```

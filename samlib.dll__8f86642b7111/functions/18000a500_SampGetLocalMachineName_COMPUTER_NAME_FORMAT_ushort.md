# SampGetLocalMachineName(_COMPUTER_NAME_FORMAT,ushort * *)

- ea: `0x18000a500`
- end: `0x18000a598`
- name: `?SampGetLocalMachineName@@YAJW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z`
- size: `152`
- prototype: `__int64 __fastcall(COMPUTER_NAME_FORMAT NameType, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a840`

## callees

- `0x18000a500`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000a51e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000a56c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000a51e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000a56c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a580`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a580`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a54a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a54a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a52a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a52a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a558`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000a588`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000a588`

## pseudocode

```c
int __fastcall SampGetLocalMachineName(COMPUTER_NAME_FORMAT NameType, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rdi
  RPC_STATUS LastError; // ebx
  WCHAR *v6; // rax
  DWORD nSize; // [rsp+60h] [rbp+18h] BYREF

  nSize = 0;
  if ( GetComputerNameExW(NameType, 0, &nSize) || (v4 = 0, LastError = GetLastError(), LastError == 234) )
  {
    v6 = (WCHAR *)LocalAlloc(0x40u, 2LL * nSize + 2);
    v4 = v6;
    if ( v6 && GetComputerNameExW(NameType, v6, &nSize) )
    {
      *a2 = v4;
      v4 = 0;
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
    }
  }
  LocalFree(v4);
  return I_RpcMapWin32Status(LastError);
}

```

## disassembly

```asm
0x18000a500  push    rbx
0x18000a502  push    rsi
0x18000a503  push    rdi
0x18000a504  push    r14
0x18000a506  sub     rsp, 28h
0x18000a50a  mov     r14, rdx
0x18000a50d  mov     [rsp+48h+nSize], 0
0x18000a515  xor     edx, edx; lpBuffer
0x18000a517  lea     r8, [rsp+48h+nSize]; nSize
0x18000a51c  mov     esi, ecx
0x18000a51e  call    cs:__imp_GetComputerNameExW
0x18000a524  test    eax, eax
0x18000a526  jnz     short loc_18000A539
0x18000a528  xor     edi, edi
0x18000a52a  call    cs:__imp_GetLastError
0x18000a530  mov     ebx, eax
0x18000a532  cmp     eax, 0EAh
0x18000a537  jnz     short loc_18000A57D
0x18000a539  mov     edx, [rsp+48h+nSize]
0x18000a53d  mov     ecx, 40h ; '@'; uFlags
0x18000a542  lea     rdx, ds:2[rdx*2]; uBytes
0x18000a54a  call    cs:__imp_LocalAlloc
0x18000a550  mov     rdi, rax
0x18000a553  test    rax, rax
0x18000a556  jnz     short loc_18000A562
0x18000a558  call    cs:__imp_GetLastError
0x18000a55e  mov     ebx, eax
0x18000a560  jmp     short loc_18000A57D
0x18000a562  lea     r8, [rsp+48h+nSize]; nSize
0x18000a567  mov     rdx, rdi; lpBuffer
0x18000a56a  mov     ecx, esi; NameType
0x18000a56c  call    cs:__imp_GetComputerNameExW
0x18000a572  test    eax, eax
0x18000a574  jz      short loc_18000A558
0x18000a576  mov     [r14], rdi
0x18000a579  xor     edi, edi
0x18000a57b  xor     ebx, ebx
0x18000a57d  mov     rcx, rdi; hMem
0x18000a580  call    cs:__imp_LocalFree
0x18000a586  mov     ecx, ebx; Status
0x18000a588  call    cs:__imp_I_RpcMapWin32Status
0x18000a58e  add     rsp, 28h
0x18000a592  pop     r14
0x18000a594  pop     rdi
0x18000a595  pop     rsi
0x18000a596  pop     rbx
0x18000a597  retn
```

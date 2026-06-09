# NetpGetComputerNameEx2

- ea: `0x1800067e4`
- end: `0x1800068cf`
- name: `NetpGetComputerNameEx2`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800061d8`
- `0x1800288a8`

## callees

- `0x1800067e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000688f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000688f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180006829`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180006875`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180006829`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180006875`
- `netutils!NetApiBufferFree` at `0x1800068a2`
- `netutils!NetApiBufferFree` at `0x1800068a2`
- `netutils!NetApiBufferAllocate` at `0x180006857`
- `netutils!NetApiBufferAllocate` at `0x180006857`

## pseudocode

```c
__int64 __fastcall NetpGetComputerNameEx2(LPVOID *a1, COMPUTER_NAME_FORMAT a2)
{
  DWORD LastError; // ebx
  DWORD nSize; // [rsp+30h] [rbp+8h] BYREF
  LPVOID Buffer; // [rsp+40h] [rbp+18h] BYREF

  nSize = 0;
  Buffer = 0;
  if ( !a1 )
    return 87;
  *a1 = 0;
  if ( (unsigned int)a2 >= ComputerNameMax )
    return 87;
  if ( GetComputerNameExW(a2, 0, &nSize) || GetLastError() != 234 )
  {
    return 87;
  }
  else
  {
    LastError = NetApiBufferAllocate(2 * nSize, &Buffer);
    if ( !LastError )
    {
      if ( GetComputerNameExW(a2, (LPWSTR)Buffer, &nSize) )
      {
        *a1 = Buffer;
      }
      else
      {
        LastError = GetLastError();
        NetApiBufferFree(Buffer);
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800067e4  mov     rax, rsp
0x1800067e7  mov     [rax+10h], rbx
0x1800067eb  mov     [rax+20h], rsi
0x1800067ef  push    rdi
0x1800067f0  sub     rsp, 20h
0x1800067f4  mov     dword ptr [rax+8], 0
0x1800067fb  mov     esi, edx
0x1800067fd  mov     qword ptr [rax+18h], 0
0x180006805  mov     rdi, rcx
0x180006808  test    rcx, rcx
0x18000680b  jz      loc_1800068B9
0x180006811  mov     qword ptr [rcx], 0
0x180006818  cmp     edx, 8
0x18000681b  jnb     loc_1800068B9
0x180006821  lea     r8, [rax+8]; nSize
0x180006825  xor     edx, edx; lpBuffer
0x180006827  mov     ecx, esi; NameType
0x180006829  call    cs:__imp_GetComputerNameExW
0x180006830  nop     dword ptr [rax+rax+00h]
0x180006835  test    eax, eax
0x180006837  jnz     short loc_1800068B0
0x180006839  call    cs:__imp_GetLastError
0x180006840  nop     dword ptr [rax+rax+00h]
0x180006845  cmp     eax, 0EAh
0x18000684a  jnz     short loc_1800068B0
0x18000684c  mov     ecx, [rsp+28h+nSize]
0x180006850  lea     rdx, [rsp+28h+Buffer]; Buffer
0x180006855  add     ecx, ecx; ByteCount
0x180006857  call    cs:__imp_NetApiBufferAllocate
0x18000685e  nop     dword ptr [rax+rax+00h]
0x180006863  mov     ebx, eax
0x180006865  test    eax, eax
0x180006867  jnz     short loc_1800068B5
0x180006869  mov     rdx, [rsp+28h+Buffer]; lpBuffer
0x18000686e  lea     r8, [rsp+28h+nSize]; nSize
0x180006873  mov     ecx, esi; NameType
0x180006875  call    cs:__imp_GetComputerNameExW
0x18000687c  nop     dword ptr [rax+rax+00h]
0x180006881  test    eax, eax
0x180006883  jz      short loc_18000688F
0x180006885  mov     rcx, [rsp+28h+Buffer]
0x18000688a  mov     [rdi], rcx
0x18000688d  jmp     short loc_1800068B5
0x18000688f  call    cs:__imp_GetLastError
0x180006896  nop     dword ptr [rax+rax+00h]
0x18000689b  mov     rcx, [rsp+28h+Buffer]; Buffer
0x1800068a0  mov     ebx, eax
0x1800068a2  call    cs:__imp_NetApiBufferFree
0x1800068a9  nop     dword ptr [rax+rax+00h]
0x1800068ae  jmp     short loc_1800068B5
0x1800068b0  mov     ebx, 57h ; 'W'
0x1800068b5  mov     eax, ebx
0x1800068b7  jmp     short loc_1800068BE
0x1800068b9  mov     eax, 57h ; 'W'
0x1800068be  mov     rbx, [rsp+28h+arg_8]
0x1800068c3  mov     rsi, [rsp+28h+arg_18]
0x1800068c8  add     rsp, 20h
0x1800068cc  pop     rdi
0x1800068cd  retn
```

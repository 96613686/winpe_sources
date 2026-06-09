# bAreWeLocal(ushort *)

- ea: `0x18000e200`
- end: `0x18000e287`
- name: `?bAreWeLocal@@YAHPEAG@Z`
- size: `135`
- prototype: `BOOL __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000dee0`
- `0x18000e200`
- `0x180044310`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000e265`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000e265`

## pseudocode

```c
BOOL __fastcall bAreWeLocal(unsigned __int16 *a1)
{
  BOOL result; // eax
  DWORD nSize[4]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( !a1 || !(unsigned int)wbem_wcsicmp(a1, L".") )
    return 1;
  nSize[0] = 260;
  result = GetComputerNameExW(ComputerNameNetBIOS, Buffer, nSize);
  if ( result )
    return wbem_wcsicmp(Buffer, a1) == 0;
  return result;
}

```

## disassembly

```asm
0x18000e200  push    rbx
0x18000e202  sub     rsp, 250h
0x18000e209  mov     rax, cs:__security_cookie
0x18000e210  xor     rax, rsp
0x18000e213  mov     [rsp+258h+var_18], rax
0x18000e21b  mov     rbx, rcx
0x18000e21e  test    rcx, rcx
0x18000e221  jz      short loc_18000E233
0x18000e223  lea     rdx, asc_18004B384; "."
0x18000e22a  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x18000e22f  test    eax, eax
0x18000e231  jnz     short loc_18000E251
0x18000e233  mov     eax, 1
0x18000e238  mov     rcx, [rsp+258h+var_18]
0x18000e240  xor     rcx, rsp; StackCookie
0x18000e243  call    __security_check_cookie
0x18000e248  add     rsp, 250h
0x18000e24f  pop     rbx
0x18000e250  retn
0x18000e251  lea     r8, [rsp+258h+nSize]; nSize
0x18000e256  mov     [rsp+258h+nSize], 104h
0x18000e25e  lea     rdx, [rsp+258h+Buffer]; lpBuffer
0x18000e263  xor     ecx, ecx; NameType
0x18000e265  call    cs:__imp_GetComputerNameExW
0x18000e26b  test    eax, eax
0x18000e26d  jz      short loc_18000E238
0x18000e26f  mov     rdx, rbx; unsigned __int16 *
0x18000e272  lea     rcx, [rsp+258h+Buffer]; unsigned __int16 *
0x18000e277  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x18000e27c  xor     ecx, ecx
0x18000e27e  test    eax, eax
0x18000e280  setz    cl
0x18000e283  mov     eax, ecx
0x18000e285  jmp     short loc_18000E238
```

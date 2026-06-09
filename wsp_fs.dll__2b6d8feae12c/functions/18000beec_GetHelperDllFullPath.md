# GetHelperDllFullPath

- ea: `0x18000beec`
- end: `0x18000bf8f`
- name: `GetHelperDllFullPath`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000bfc0`

## callees

- `0x180002a70`
- `0x180003504`
- `0x18000beec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bf69`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bf69`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000bf2e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000bf2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000bf18`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000bf18`

## string_xrefs

- `0x18000bf3c`: `wmitomi.dll`

## pseudocode

```c
void *GetHelperDllFullPath()
{
  signed int SystemDirectoryW; // eax
  void *v1; // rbx
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  Buffer[0] = 0;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( !SystemDirectoryW )
    return 0;
  if ( SystemDirectoryW > 260 )
    return 0;
  v1 = malloc(0x208u);
  if ( !v1 )
    return 0;
  if ( swprintf_s((wchar_t *const)v1, 0x104u, L"%s\\%s", Buffer, L"wmitomi.dll") == -1 )
  {
    free(v1);
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x18000beec  push    rbx
0x18000beee  sub     rsp, 250h
0x18000bef5  mov     rax, cs:__security_cookie
0x18000befc  xor     rax, rsp
0x18000beff  mov     [rsp+258h+var_18], rax
0x18000bf07  xor     eax, eax
0x18000bf09  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18000bf0e  mov     edx, 104h; uSize
0x18000bf13  mov     [rsp+258h+Buffer], ax
0x18000bf18  call    cs:__imp_GetSystemDirectoryW
0x18000bf1e  test    eax, eax
0x18000bf20  jz      short loc_18000BF6F
0x18000bf22  cmp     eax, 104h
0x18000bf27  jg      short loc_18000BF6F
0x18000bf29  mov     ecx, 208h; Size
0x18000bf2e  call    cs:__imp_malloc
0x18000bf34  mov     rbx, rax
0x18000bf37  test    rax, rax
0x18000bf3a  jz      short loc_18000BF6F
0x18000bf3c  lea     rax, aWmitomiDll; "wmitomi.dll"
0x18000bf43  mov     edx, 104h; BufferCount
0x18000bf48  lea     r9, [rsp+258h+Buffer]
0x18000bf4d  mov     [rsp+258h+var_238], rax
0x18000bf52  lea     r8, aSS; "%s\\%s"
0x18000bf59  mov     rcx, rbx; Buffer
0x18000bf5c  call    swprintf_s
0x18000bf61  cmp     eax, 0FFFFFFFFh
0x18000bf64  jnz     short loc_18000BF8A
0x18000bf66  mov     rcx, rbx; Block
0x18000bf69  call    cs:__imp_free
0x18000bf6f  xor     eax, eax
0x18000bf71  mov     rcx, [rsp+258h+var_18]
0x18000bf79  xor     rcx, rsp; StackCookie
0x18000bf7c  call    __security_check_cookie
0x18000bf81  add     rsp, 250h
0x18000bf88  pop     rbx
0x18000bf89  retn
0x18000bf8a  mov     rax, rbx
0x18000bf8d  jmp     short loc_18000BF71
```

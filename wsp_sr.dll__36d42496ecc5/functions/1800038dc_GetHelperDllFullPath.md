# GetHelperDllFullPath

- ea: `0x1800038dc`
- end: `0x18000397f`
- name: `GetHelperDllFullPath`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800039b0`

## callees

- `0x1800014e0`
- `0x180001e14`
- `0x1800038dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003959`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003959`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000391e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000391e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180003908`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180003908`

## string_xrefs

- `0x18000392c`: `wmitomi.dll`

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
0x1800038dc  push    rbx
0x1800038de  sub     rsp, 250h
0x1800038e5  mov     rax, cs:__security_cookie
0x1800038ec  xor     rax, rsp
0x1800038ef  mov     [rsp+258h+var_18], rax
0x1800038f7  xor     eax, eax
0x1800038f9  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x1800038fe  mov     edx, 104h; uSize
0x180003903  mov     [rsp+258h+Buffer], ax
0x180003908  call    cs:__imp_GetSystemDirectoryW
0x18000390e  test    eax, eax
0x180003910  jz      short loc_18000395F
0x180003912  cmp     eax, 104h
0x180003917  jg      short loc_18000395F
0x180003919  mov     ecx, 208h; Size
0x18000391e  call    cs:__imp_malloc
0x180003924  mov     rbx, rax
0x180003927  test    rax, rax
0x18000392a  jz      short loc_18000395F
0x18000392c  lea     rax, aWmitomiDll; "wmitomi.dll"
0x180003933  mov     edx, 104h; BufferCount
0x180003938  lea     r9, [rsp+258h+Buffer]
0x18000393d  mov     [rsp+258h+var_238], rax
0x180003942  lea     r8, aSS; "%s\\%s"
0x180003949  mov     rcx, rbx; Buffer
0x18000394c  call    swprintf_s
0x180003951  cmp     eax, 0FFFFFFFFh
0x180003954  jnz     short loc_18000397A
0x180003956  mov     rcx, rbx; Block
0x180003959  call    cs:__imp_free
0x18000395f  xor     eax, eax
0x180003961  mov     rcx, [rsp+258h+var_18]
0x180003969  xor     rcx, rsp; StackCookie
0x18000396c  call    __security_check_cookie
0x180003971  add     rsp, 250h
0x180003978  pop     rbx
0x180003979  retn
0x18000397a  mov     rax, rbx
0x18000397d  jmp     short loc_180003961
```

# GetHelperDllFullPath

- ea: `0x18000b928`
- end: `0x18000b9de`
- name: `GetHelperDllFullPath`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000ba10`

## callees

- `0x180002b50`
- `0x180003620`
- `0x18000b928`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b9b1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b9b1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b970`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b970`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000b954`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000b954`

## string_xrefs

- `0x18000b984`: `wmitomi.dll`

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
0x18000b928  push    rbx
0x18000b92a  sub     rsp, 250h
0x18000b931  mov     rax, cs:__security_cookie
0x18000b938  xor     rax, rsp
0x18000b93b  mov     [rsp+258h+var_18], rax
0x18000b943  xor     eax, eax
0x18000b945  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18000b94a  mov     edx, 104h; uSize
0x18000b94f  mov     [rsp+258h+Buffer], ax
0x18000b954  call    cs:__imp_GetSystemDirectoryW
0x18000b95b  nop     dword ptr [rax+rax+00h]
0x18000b960  test    eax, eax
0x18000b962  jz      short loc_18000B9BD
0x18000b964  cmp     eax, 104h
0x18000b969  jg      short loc_18000B9BD
0x18000b96b  mov     ecx, 208h; Size
0x18000b970  call    cs:__imp_malloc
0x18000b977  nop     dword ptr [rax+rax+00h]
0x18000b97c  mov     rbx, rax
0x18000b97f  test    rax, rax
0x18000b982  jz      short loc_18000B9BD
0x18000b984  lea     rax, aWmitomiDll; "wmitomi.dll"
0x18000b98b  mov     edx, 104h; BufferCount
0x18000b990  lea     r9, [rsp+258h+Buffer]
0x18000b995  mov     [rsp+258h+var_238], rax
0x18000b99a  lea     r8, aSS; "%s\\%s"
0x18000b9a1  mov     rcx, rbx; Buffer
0x18000b9a4  call    swprintf_s
0x18000b9a9  cmp     eax, 0FFFFFFFFh
0x18000b9ac  jnz     short loc_18000B9D9
0x18000b9ae  mov     rcx, rbx; Block
0x18000b9b1  call    cs:__imp_free
0x18000b9b8  nop     dword ptr [rax+rax+00h]
0x18000b9bd  xor     eax, eax
0x18000b9bf  mov     rcx, [rsp+258h+var_18]
0x18000b9c7  xor     rcx, rsp; StackCookie
0x18000b9ca  call    __security_check_cookie
0x18000b9cf  add     rsp, 250h
0x18000b9d6  pop     rbx
0x18000b9d7  retn
0x18000b9d9  mov     rax, rbx
0x18000b9dc  jmp     short loc_18000B9BF
```

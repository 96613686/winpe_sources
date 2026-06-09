# GetHelperDllFullPath

- ea: `0x18000c1f8`
- end: `0x18000c2ae`
- name: `GetHelperDllFullPath`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000c2e0`

## callees

- `0x180002ad0`
- `0x180003594`
- `0x18000c1f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c281`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c281`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c240`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c240`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000c224`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000c224`

## string_xrefs

- `0x18000c254`: `wmitomi.dll`

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
0x18000c1f8  push    rbx
0x18000c1fa  sub     rsp, 250h
0x18000c201  mov     rax, cs:__security_cookie
0x18000c208  xor     rax, rsp
0x18000c20b  mov     [rsp+258h+var_18], rax
0x18000c213  xor     eax, eax
0x18000c215  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18000c21a  mov     edx, 104h; uSize
0x18000c21f  mov     [rsp+258h+Buffer], ax
0x18000c224  call    cs:__imp_GetSystemDirectoryW
0x18000c22b  nop     dword ptr [rax+rax+00h]
0x18000c230  test    eax, eax
0x18000c232  jz      short loc_18000C28D
0x18000c234  cmp     eax, 104h
0x18000c239  jg      short loc_18000C28D
0x18000c23b  mov     ecx, 208h; Size
0x18000c240  call    cs:__imp_malloc
0x18000c247  nop     dword ptr [rax+rax+00h]
0x18000c24c  mov     rbx, rax
0x18000c24f  test    rax, rax
0x18000c252  jz      short loc_18000C28D
0x18000c254  lea     rax, aWmitomiDll; "wmitomi.dll"
0x18000c25b  mov     edx, 104h; BufferCount
0x18000c260  lea     r9, [rsp+258h+Buffer]
0x18000c265  mov     [rsp+258h+var_238], rax
0x18000c26a  lea     r8, aSS; "%s\\%s"
0x18000c271  mov     rcx, rbx; Buffer
0x18000c274  call    swprintf_s
0x18000c279  cmp     eax, 0FFFFFFFFh
0x18000c27c  jnz     short loc_18000C2A9
0x18000c27e  mov     rcx, rbx; Block
0x18000c281  call    cs:__imp_free
0x18000c288  nop     dword ptr [rax+rax+00h]
0x18000c28d  xor     eax, eax
0x18000c28f  mov     rcx, [rsp+258h+var_18]
0x18000c297  xor     rcx, rsp; StackCookie
0x18000c29a  call    __security_check_cookie
0x18000c29f  add     rsp, 250h
0x18000c2a6  pop     rbx
0x18000c2a7  retn
0x18000c2a9  mov     rax, rbx
0x18000c2ac  jmp     short loc_18000C28F
```

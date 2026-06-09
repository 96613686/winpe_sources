# GetHelperDllFullPath

- ea: `0x18000b5dc`
- end: `0x18000b67f`
- name: `GetHelperDllFullPath`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000b6b0`

## callees

- `0x180002ae0`
- `0x180003580`
- `0x18000b5dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b659`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b659`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b61e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b61e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000b608`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000b608`

## string_xrefs

- `0x18000b62c`: `wmitomi.dll`

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
0x18000b5dc  push    rbx
0x18000b5de  sub     rsp, 250h
0x18000b5e5  mov     rax, cs:__security_cookie
0x18000b5ec  xor     rax, rsp
0x18000b5ef  mov     [rsp+258h+var_18], rax
0x18000b5f7  xor     eax, eax
0x18000b5f9  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18000b5fe  mov     edx, 104h; uSize
0x18000b603  mov     [rsp+258h+Buffer], ax
0x18000b608  call    cs:__imp_GetSystemDirectoryW
0x18000b60e  test    eax, eax
0x18000b610  jz      short loc_18000B65F
0x18000b612  cmp     eax, 104h
0x18000b617  jg      short loc_18000B65F
0x18000b619  mov     ecx, 208h; Size
0x18000b61e  call    cs:__imp_malloc
0x18000b624  mov     rbx, rax
0x18000b627  test    rax, rax
0x18000b62a  jz      short loc_18000B65F
0x18000b62c  lea     rax, aWmitomiDll; "wmitomi.dll"
0x18000b633  mov     edx, 104h; BufferCount
0x18000b638  lea     r9, [rsp+258h+Buffer]
0x18000b63d  mov     [rsp+258h+var_238], rax
0x18000b642  lea     r8, aSS; "%s\\%s"
0x18000b649  mov     rcx, rbx; Buffer
0x18000b64c  call    swprintf_s
0x18000b651  cmp     eax, 0FFFFFFFFh
0x18000b654  jnz     short loc_18000B67A
0x18000b656  mov     rcx, rbx; Block
0x18000b659  call    cs:__imp_free
0x18000b65f  xor     eax, eax
0x18000b661  mov     rcx, [rsp+258h+var_18]
0x18000b669  xor     rcx, rsp; StackCookie
0x18000b66c  call    __security_check_cookie
0x18000b671  add     rsp, 250h
0x18000b678  pop     rbx
0x18000b679  retn
0x18000b67a  mov     rax, rbx
0x18000b67d  jmp     short loc_18000B661
```

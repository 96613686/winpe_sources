# GetHelperDllFullPath

- ea: `0x180003818`
- end: `0x1800038ce`
- name: `GetHelperDllFullPath`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003900`

## callees

- `0x1800014e0`
- `0x180001e44`
- `0x180003818`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800038a1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800038a1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003860`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003860`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180003844`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180003844`

## string_xrefs

- `0x180003874`: `wmitomi.dll`

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
0x180003818  push    rbx
0x18000381a  sub     rsp, 250h
0x180003821  mov     rax, cs:__security_cookie
0x180003828  xor     rax, rsp
0x18000382b  mov     [rsp+258h+var_18], rax
0x180003833  xor     eax, eax
0x180003835  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18000383a  mov     edx, 104h; uSize
0x18000383f  mov     [rsp+258h+Buffer], ax
0x180003844  call    cs:__imp_GetSystemDirectoryW
0x18000384b  nop     dword ptr [rax+rax+00h]
0x180003850  test    eax, eax
0x180003852  jz      short loc_1800038AD
0x180003854  cmp     eax, 104h
0x180003859  jg      short loc_1800038AD
0x18000385b  mov     ecx, 208h; Size
0x180003860  call    cs:__imp_malloc
0x180003867  nop     dword ptr [rax+rax+00h]
0x18000386c  mov     rbx, rax
0x18000386f  test    rax, rax
0x180003872  jz      short loc_1800038AD
0x180003874  lea     rax, aWmitomiDll; "wmitomi.dll"
0x18000387b  mov     edx, 104h; BufferCount
0x180003880  lea     r9, [rsp+258h+Buffer]
0x180003885  mov     [rsp+258h+var_238], rax
0x18000388a  lea     r8, aSS; "%s\\%s"
0x180003891  mov     rcx, rbx; Buffer
0x180003894  call    swprintf_s
0x180003899  cmp     eax, 0FFFFFFFFh
0x18000389c  jnz     short loc_1800038C9
0x18000389e  mov     rcx, rbx; Block
0x1800038a1  call    cs:__imp_free
0x1800038a8  nop     dword ptr [rax+rax+00h]
0x1800038ad  xor     eax, eax
0x1800038af  mov     rcx, [rsp+258h+var_18]
0x1800038b7  xor     rcx, rsp; StackCookie
0x1800038ba  call    __security_check_cookie
0x1800038bf  add     rsp, 250h
0x1800038c6  pop     rbx
0x1800038c7  retn
0x1800038c9  mov     rax, rbx
0x1800038cc  jmp     short loc_1800038AF
```

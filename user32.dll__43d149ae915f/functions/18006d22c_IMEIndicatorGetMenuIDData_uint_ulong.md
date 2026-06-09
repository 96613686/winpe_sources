# IMEIndicatorGetMenuIDData(uint *,ulong *)

- ea: `0x18006d22c`
- end: `0x18006d32d`
- name: `?IMEIndicatorGetMenuIDData@@YAHPEAIPEAK@Z`
- size: `257`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800151d0`

## callees

- `0x18006d22c`
- `0x180096e00`
- `0x1800a2010`

## import_xrefs

- `ntdll!wcsncpy_s` at `0x18006d2aa`
- `ntdll!wcsncpy_s` at `0x18006d2aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006d2d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006d2d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006d2bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006d2bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006d25f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006d25f`

## string_xrefs

- `0x18006d2a3`: `indicdll.dll`

## pseudocode

```c
__int64 __fastcall IMEIndicatorGetMenuIDData(unsigned int *a1, unsigned int *a2)
{
  UINT SystemDirectoryW; // eax
  __int64 v5; // rbx
  HMODULE ModuleHandleW; // rcx
  FARPROC ProcAddress; // rax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-238h] BYREF

  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x105u);
  v5 = SystemDirectoryW;
  if ( SystemDirectoryW >= 0x105 )
    goto LABEL_12;
  if ( SystemDirectoryW )
  {
    if ( Buffer[SystemDirectoryW - 1] != 92 )
    {
      Buffer[SystemDirectoryW] = 92;
      v5 = SystemDirectoryW + 1;
      if ( (unsigned int)v5 >= 0x105 )
        goto LABEL_12;
    }
    if ( (unsigned int)(261 - v5) <= 0xC )
      goto LABEL_12;
    wcsncpy_s(&Buffer[v5], (unsigned int)(261 - v5), L"indicdll.dll", 0xFFFFFFFFFFFFFFFFuLL);
    LODWORD(v5) = v5 + 12;
  }
  if ( !(_DWORD)v5 || (ModuleHandleW = GetModuleHandleW(Buffer)) == 0 )
  {
LABEL_12:
    gpfnGetIMEMenuItemData = 0;
    return 0;
  }
  ProcAddress = gpfnGetIMEMenuItemData;
  if ( gpfnGetIMEMenuItemData
    || (ProcAddress = GetProcAddress(ModuleHandleW, (LPCSTR)0xC), (gpfnGetIMEMenuItemData = ProcAddress) != 0) )
  {
    ((void (__fastcall *)(unsigned int *, unsigned int *))ProcAddress)(a1, a2);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18006d22c  mov     [rsp+arg_10], rbx
0x18006d231  push    rbp
0x18006d232  push    rsi
0x18006d233  push    rdi
0x18006d234  sub     rsp, 240h
0x18006d23b  mov     rax, cs:__security_cookie
0x18006d242  xor     rax, rsp
0x18006d245  mov     [rsp+258h+var_28], rax
0x18006d24d  mov     rbp, rdx
0x18006d250  mov     rsi, rcx
0x18006d253  mov     edi, 105h
0x18006d258  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18006d25d  mov     edx, edi; uSize
0x18006d25f  call    cs:__imp_GetSystemDirectoryW
0x18006d265  mov     ebx, eax
0x18006d267  cmp     eax, edi
0x18006d269  jnb     loc_18006D2FD
0x18006d26f  test    eax, eax
0x18006d271  jz      short loc_18006D2B3
0x18006d273  lea     edx, [rbx-1]
0x18006d276  mov     ecx, 5Ch ; '\'
0x18006d27b  cmp     [rsp+rdx*2+258h+Buffer], cx
0x18006d280  jz      short loc_18006D28D
0x18006d282  mov     [rsp+rbx*2+258h+Buffer], cx
0x18006d287  inc     ebx
0x18006d289  cmp     ebx, edi
0x18006d28b  jnb     short loc_18006D2FD
0x18006d28d  sub     edi, ebx
0x18006d28f  cmp     edi, 0Ch
0x18006d292  jbe     short loc_18006D2FD
0x18006d294  lea     rcx, [rsp+258h+Buffer]
0x18006d299  mov     edx, edi; SizeInWords
0x18006d29b  lea     rcx, [rcx+rbx*2]; Destination
0x18006d29f  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18006d2a3  lea     r8, aIndicdllDll; "indicdll.dll"
0x18006d2aa  call    cs:__imp_wcsncpy_s
0x18006d2b0  add     ebx, 0Ch
0x18006d2b3  test    ebx, ebx
0x18006d2b5  jz      short loc_18006D2FD
0x18006d2b7  lea     rcx, [rsp+258h+Buffer]; lpModuleName
0x18006d2bc  call    cs:__imp_GetModuleHandleW
0x18006d2c2  mov     rcx, rax; hModule
0x18006d2c5  test    rax, rax
0x18006d2c8  jz      short loc_18006D2FD
0x18006d2ca  mov     rax, cs:?gpfnGetIMEMenuItemData@@3P6A_JXZEA; __int64 (*gpfnGetIMEMenuItemData)(void)
0x18006d2d1  test    rax, rax
0x18006d2d4  jnz     short loc_18006D2EB
0x18006d2d6  lea     edx, [rax+0Ch]; lpProcName
0x18006d2d9  call    cs:__imp_GetProcAddress
0x18006d2df  mov     cs:?gpfnGetIMEMenuItemData@@3P6A_JXZEA, rax; __int64 (*gpfnGetIMEMenuItemData)(void)
0x18006d2e6  test    rax, rax
0x18006d2e9  jz      short loc_18006D308
0x18006d2eb  mov     rdx, rbp
0x18006d2ee  mov     rcx, rsi
0x18006d2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d2f6  mov     eax, 1
0x18006d2fb  jmp     short loc_18006D30A
0x18006d2fd  mov     cs:?gpfnGetIMEMenuItemData@@3P6A_JXZEA, 0; __int64 (*gpfnGetIMEMenuItemData)(void)
0x18006d308  xor     eax, eax
0x18006d30a  mov     rcx, [rsp+258h+var_28]
0x18006d312  xor     rcx, rsp; StackCookie
0x18006d315  call    __security_check_cookie
0x18006d31a  mov     rbx, [rsp+258h+arg_10]
0x18006d322  add     rsp, 240h
0x18006d329  pop     rdi
0x18006d32a  pop     rsi
0x18006d32b  pop     rbp
0x18006d32c  retn
```

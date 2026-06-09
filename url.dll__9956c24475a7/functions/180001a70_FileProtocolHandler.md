# FileProtocolHandler

- ea: `0x180001a70`
- end: `0x180001b02`
- name: `FileProtocolHandler`
- size: `146`
- prototype: `__int64 __fastcall(HWND hwnd)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800021e0`

## import_xrefs

- `SHELL32!ShellExecuteA` at `0x180001ada`
- `SHELL32!ShellExecuteA` at `0x180001ada`
- `SHLWAPI!PathCreateFromUrlA` at `0x180001aae`
- `SHLWAPI!PathCreateFromUrlA` at `0x180001aae`

## pseudocode

```c
HINSTANCE __fastcall FileProtocolHandler(HWND hwnd, __int64 a2, const CHAR *a3, INT a4)
{
  HRESULT v7; // eax
  CHAR *v8; // r8
  DWORD pcchPath[4]; // [rsp+30h] [rbp-148h] BYREF
  CHAR pszPath[272]; // [rsp+40h] [rbp-138h] BYREF

  pcchPath[0] = 260;
  v7 = PathCreateFromUrlA(a3, pszPath, pcchPath, 0);
  v8 = pszPath;
  if ( v7 < 0 )
    v8 = (CHAR *)a3;
  return ShellExecuteA(hwnd, 0, v8, 0, 0, a4);
}

```

## disassembly

```asm
0x180001a70  push    rbx; FileProtocolHandler
0x180001a72  push    rsi
0x180001a73  push    rdi
0x180001a74  sub     rsp, 160h
0x180001a7b  mov     rax, cs:__security_cookie
0x180001a82  xor     rax, rsp
0x180001a85  mov     [rsp+178h+var_28], rax
0x180001a8d  mov     rbx, r8
0x180001a90  mov     [rsp+178h+pcchPath], 104h
0x180001a98  mov     edi, r9d
0x180001a9b  lea     r8, [rsp+178h+pcchPath]; pcchPath
0x180001aa0  mov     rsi, rcx
0x180001aa3  lea     rdx, [rsp+178h+pszPath]; pszPath
0x180001aa8  mov     rcx, rbx; pszUrl
0x180001aab  xor     r9d, r9d; dwFlags
0x180001aae  call    cs:__imp_PathCreateFromUrlA
0x180001ab5  nop     dword ptr [rax+rax+00h]
0x180001aba  lea     r8, [rsp+178h+pszPath]
0x180001abf  mov     [rsp+178h+nShowCmd], edi; nShowCmd
0x180001ac3  test    eax, eax
0x180001ac5  mov     [rsp+178h+lpDirectory], 0; lpDirectory
0x180001ace  mov     rcx, rsi; hwnd
0x180001ad1  cmovs   r8, rbx; lpFile
0x180001ad5  xor     r9d, r9d; lpParameters
0x180001ad8  xor     edx, edx; lpOperation
0x180001ada  call    cs:__imp_ShellExecuteA
0x180001ae1  nop     dword ptr [rax+rax+00h]
0x180001ae6  mov     rcx, [rsp+178h+var_28]
0x180001aee  xor     rcx, rsp; StackCookie
0x180001af1  call    __security_check_cookie
0x180001af6  add     rsp, 160h
0x180001afd  pop     rdi
0x180001afe  pop     rsi
0x180001aff  pop     rbx
0x180001b00  retn
```

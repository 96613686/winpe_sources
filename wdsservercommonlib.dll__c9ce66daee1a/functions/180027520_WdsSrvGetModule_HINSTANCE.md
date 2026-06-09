# WdsSrvGetModule(HINSTANCE__ * *)

- ea: `0x180027520`
- end: `0x180027570`
- name: `?WdsSrvGetModule@@YAKPEAPEAUHINSTANCE__@@@Z`
- size: `80`
- prototype: `unsigned int __fastcall(HINSTANCE *phModule)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180027470`
- `0x180027580`

## callees

- `0x180027520`
- `0x180027610`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180027544`
- `KERNEL32!GetLastError` at `0x180027544`
- `KERNEL32!GetModuleHandleExW` at `0x180027534`
- `KERNEL32!GetModuleHandleExW` at `0x180027534`

## string_xrefs

- `0x180027529`: `wdssrv.dll`

## pseudocode

```c
__int64 __fastcall WdsSrvGetModule(HINSTANCE *phModule)
{
  unsigned int v1; // ebx
  DWORD LastError; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  unsigned int v5; // eax

  v1 = 0;
  if ( !GetModuleHandleExW(0, L"wdssrv.dll", phModule) )
  {
    LastError = GetLastError();
    v5 = ElValidateWin32_15(LastError, v3, v4, 0xA4u);
    if ( !v5 )
      return 31;
    return v5;
  }
  return v1;
}

```

## disassembly

```asm
0x180027520  push    rbx
0x180027522  sub     rsp, 20h
0x180027526  mov     r8, rcx; phModule
0x180027529  lea     rdx, aWdssrvDll; "wdssrv.dll"
0x180027530  xor     ecx, ecx; dwFlags
0x180027532  xor     ebx, ebx
0x180027534  call    cs:__imp_GetModuleHandleExW
0x18002753b  nop     dword ptr [rax+rax+00h]
0x180027540  test    eax, eax
0x180027542  jnz     short loc_180027567
0x180027544  call    cs:__imp_GetLastError
0x18002754b  nop     dword ptr [rax+rax+00h]
0x180027550  mov     ecx, eax
0x180027552  mov     r9d, 0A4h
0x180027558  call    ElValidateWin32_15
0x18002755d  lea     ecx, [rbx+1Fh]
0x180027560  test    eax, eax
0x180027562  cmovz   eax, ecx
0x180027565  mov     ebx, eax
0x180027567  mov     eax, ebx
0x180027569  add     rsp, 20h
0x18002756d  pop     rbx
0x18002756e  retn
```

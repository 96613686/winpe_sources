# WdsSrvGetModule(HINSTANCE__ * *)

- ea: `0x180028670`
- end: `0x1800286c0`
- name: `?WdsSrvGetModule@@YAKPEAPEAUHINSTANCE__@@@Z`
- size: `80`
- prototype: `unsigned int __fastcall(HINSTANCE *phModule)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800285c0`
- `0x1800286d0`

## callees

- `0x180028670`
- `0x180028760`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180028694`
- `KERNEL32!GetLastError` at `0x180028694`
- `KERNEL32!GetModuleHandleExW` at `0x180028684`
- `KERNEL32!GetModuleHandleExW` at `0x180028684`

## string_xrefs

- `0x180028679`: `wdssrv.dll`

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
0x180028670  push    rbx
0x180028672  sub     rsp, 20h
0x180028676  mov     r8, rcx; phModule
0x180028679  lea     rdx, aWdssrvDll; "wdssrv.dll"
0x180028680  xor     ecx, ecx; dwFlags
0x180028682  xor     ebx, ebx
0x180028684  call    cs:__imp_GetModuleHandleExW
0x18002868b  nop     dword ptr [rax+rax+00h]
0x180028690  test    eax, eax
0x180028692  jnz     short loc_1800286B7
0x180028694  call    cs:__imp_GetLastError
0x18002869b  nop     dword ptr [rax+rax+00h]
0x1800286a0  mov     ecx, eax
0x1800286a2  mov     r9d, 0A4h
0x1800286a8  call    ElValidateWin32_15
0x1800286ad  lea     ecx, [rbx+1Fh]
0x1800286b0  test    eax, eax
0x1800286b2  cmovz   eax, ecx
0x1800286b5  mov     ebx, eax
0x1800286b7  mov     eax, ebx
0x1800286b9  add     rsp, 20h
0x1800286bd  pop     rbx
0x1800286be  retn
```

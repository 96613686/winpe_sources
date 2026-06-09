# DllMain

- ea: `0x18001ec20`
- end: `0x18001ecf0`
- name: `DllMain`
- size: `208`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001e294`

## callees

- `0x18001ec20`
- `0x18002a566`
- `0x18002a590`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x18001ec96`
- `KERNEL32!GetModuleHandleA` at `0x18001ec96`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18001ec64`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18001ec64`
- `KERNEL32!GetVersionExA` at `0x18001ec77`
- `KERNEL32!GetVersionExA` at `0x18001ec77`
- `KERNEL32!GetProcAddress` at `0x18001ecae`
- `KERNEL32!GetProcAddress` at `0x18001ecc5`
- `KERNEL32!GetProcAddress` at `0x18001ecae`
- `KERNEL32!GetProcAddress` at `0x18001ecc5`

## string_xrefs

- `0x18001ecb4`: `RemoveFontMemResourceEx`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  HMODULE ModuleHandleA; // rax
  HMODULE v5; // rbx
  _OSVERSIONINFOA VersionInformation; // [rsp+20h] [rbp-B8h] BYREF

  if ( fdwReason == 1 )
  {
    memset_0(&VersionInformation, 0, sizeof(VersionInformation));
    DisableThreadLibraryCalls(hinstDLL);
    VersionInformation.dwOSVersionInfoSize = 148;
    if ( GetVersionExA(&VersionInformation) )
    {
      if ( VersionInformation.dwPlatformId == 2 && VersionInformation.dwMajorVersion >= 5 )
      {
        ModuleHandleA = GetModuleHandleA("GDI32");
        v5 = ModuleHandleA;
        if ( ModuleHandleA )
        {
          fnAddFontMemResourceEx = (__int64)GetProcAddress(ModuleHandleA, "AddFontMemResourceEx");
          fnRemoveFontMemResourceEx = GetProcAddress(v5, "RemoveFontMemResourceEx");
        }
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18001ec20  push    rbx
0x18001ec22  sub     rsp, 0D0h
0x18001ec29  mov     rax, cs:__security_cookie
0x18001ec30  xor     rax, rsp
0x18001ec33  mov     [rsp+0D8h+var_18], rax
0x18001ec3b  mov     rbx, rcx
0x18001ec3e  test    edx, edx
0x18001ec40  jz      loc_18001ECD2
0x18001ec46  cmp     edx, 1
0x18001ec49  jnz     loc_18001ECD2
0x18001ec4f  xor     edx, edx; Val
0x18001ec51  lea     rcx, [rsp+0D8h+VersionInformation]; void *
0x18001ec56  mov     r8d, 94h; Size
0x18001ec5c  call    memset_0
0x18001ec61  mov     rcx, rbx; hLibModule
0x18001ec64  call    cs:__imp_DisableThreadLibraryCalls
0x18001ec6a  lea     rcx, [rsp+0D8h+VersionInformation]; lpVersionInformation
0x18001ec6f  mov     [rsp+0D8h+VersionInformation.dwOSVersionInfoSize], 94h
0x18001ec77  call    cs:__imp_GetVersionExA
0x18001ec7d  test    eax, eax
0x18001ec7f  jz      short loc_18001ECD2
0x18001ec81  cmp     [rsp+0D8h+VersionInformation.dwPlatformId], 2
0x18001ec86  jnz     short loc_18001ECD2
0x18001ec88  cmp     [rsp+0D8h+VersionInformation.dwMajorVersion], 5
0x18001ec8d  jb      short loc_18001ECD2
0x18001ec8f  lea     rcx, aGdi32; "GDI32"
0x18001ec96  call    cs:__imp_GetModuleHandleA
0x18001ec9c  mov     rbx, rax
0x18001ec9f  test    rax, rax
0x18001eca2  jz      short loc_18001ECD2
0x18001eca4  lea     rdx, aAddfontmemreso; "AddFontMemResourceEx"
0x18001ecab  mov     rcx, rax; hModule
0x18001ecae  call    cs:__imp_GetProcAddress
0x18001ecb4  lea     rdx, aRemovefontmemr; "RemoveFontMemResourceEx"
0x18001ecbb  mov     rcx, rbx; hModule
0x18001ecbe  mov     cs:fnAddFontMemResourceEx, rax
0x18001ecc5  call    cs:__imp_GetProcAddress
0x18001eccb  mov     cs:fnRemoveFontMemResourceEx, rax
0x18001ecd2  mov     eax, 1
0x18001ecd7  mov     rcx, [rsp+0D8h+var_18]
0x18001ecdf  xor     rcx, rsp; StackCookie
0x18001ece2  call    __security_check_cookie
0x18001ece7  add     rsp, 0D0h
0x18001ecee  pop     rbx
0x18001ecef  retn
```

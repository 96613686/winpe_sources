# sub_1800CEFC0

- ea: `0x1800cefc0`
- end: `0x1800cf07b`
- name: `sub_1800CEFC0`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006a074`

## callees

- `0x1800cefc0`
- `0x18020ca70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800cefd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800cefd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cf01c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cf01c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800cf001`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800cf001`

## string_xrefs

- `0x1800cefca`: `api-ms-win-core-localregistry-l1-1-0.dll`
- `0x1800ceff4`: `api-ms-win-core-localregistry-l1-1-0.dll`

## pseudocode

```c
__int64 __fastcall sub_1800CEFC0(__int64 a1)
{
  HMODULE ModuleHandleW; // rax
  LSTATUS (__stdcall *RegGetValueW)(HKEY, LPCWSTR, LPCWSTR, DWORD, LPDWORD, PVOID, LPDWORD); // rax
  unsigned int v4; // ebx
  __int64 v5; // [rsp+50h] [rbp+8h] BYREF
  int v6; // [rsp+58h] [rbp+10h] BYREF

  v5 = a1;
  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-localregistry-l1-1-0.dll");
  v6 = 0;
  LODWORD(v5) = 0;
  if ( !ModuleHandleW )
  {
    ModuleHandleW = LoadLibraryExW(L"api-ms-win-core-localregistry-l1-1-0.dll", 0, 0x800u);
    if ( !ModuleHandleW )
      return 0;
  }
  RegGetValueW = (LSTATUS (__stdcall *)(HKEY, LPCWSTR, LPCWSTR, DWORD, LPDWORD, PVOID, LPDWORD))GetProcAddress(
                                                                                                  ModuleHandleW,
                                                                                                  "RegGetValueW");
  if ( !RegGetValueW )
    return 0;
  v4 = 0;
  if ( !((unsigned int (__fastcall *)(__int64, const wchar_t *, const wchar_t *, __int64, _QWORD, __int64 *, int *))RegGetValueW)(
          -2147483646,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SoftwareProtectionPlatform",
          L"AcgApi",
          16,
          0,
          &v5,
          &v6) )
    return (unsigned int)v5;
  return v4;
}

```

## disassembly

```asm
0x1800cefc0  mov     [rsp+arg_0], rcx
0x1800cefc5  push    rbx
0x1800cefc6  sub     rsp, 40h
0x1800cefca  lea     rcx, aApiMsWinCoreLo_0; "api-ms-win-core-localregistry-l1-1-0.dl"...
0x1800cefd1  call    cs:GetModuleHandleW
0x1800cefd8  nop     dword ptr [rax+rax+00h]
0x1800cefdd  mov     [rsp+48h+arg_8], 0
0x1800cefe5  mov     dword ptr [rsp+48h+arg_0], 0
0x1800cefed  test    rax, rax
0x1800ceff0  jnz     short loc_1800CF012
0x1800ceff2  xor     edx, edx; hFile
0x1800ceff4  lea     rcx, aApiMsWinCoreLo_0; "api-ms-win-core-localregistry-l1-1-0.dl"...
0x1800ceffb  mov     r8d, 800h; dwFlags
0x1800cf001  call    cs:LoadLibraryExW
0x1800cf008  nop     dword ptr [rax+rax+00h]
0x1800cf00d  test    rax, rax
0x1800cf010  jz      short loc_1800CF02D
0x1800cf012  lea     rdx, aReggetvaluew; "RegGetValueW"
0x1800cf019  mov     rcx, rax; hModule
0x1800cf01c  call    cs:GetProcAddress
0x1800cf023  nop     dword ptr [rax+rax+00h]
0x1800cf028  test    rax, rax
0x1800cf02b  jnz     short loc_1800CF031
0x1800cf02d  xor     eax, eax
0x1800cf02f  jmp     short loc_1800CF074
0x1800cf031  lea     rcx, [rsp+48h+arg_8]
0x1800cf036  xor     ebx, ebx
0x1800cf038  mov     [rsp+48h+var_18], rcx
0x1800cf03d  lea     r8, aAcgapi; "AcgApi"
0x1800cf044  lea     rcx, [rsp+48h+arg_0]
0x1800cf049  mov     [rsp+48h+var_20], rcx
0x1800cf04e  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800cf055  mov     rcx, 0FFFFFFFF80000002h
0x1800cf05c  mov     [rsp+48h+var_28], rbx
0x1800cf061  lea     r9d, [rbx+10h]
0x1800cf065  call    cs:__guard_dispatch_icall_fptr
0x1800cf06b  test    eax, eax
0x1800cf06d  cmovz   ebx, dword ptr [rsp+48h+arg_0]
0x1800cf072  mov     eax, ebx
0x1800cf074  add     rsp, 40h
0x1800cf078  pop     rbx
0x1800cf079  retn
```

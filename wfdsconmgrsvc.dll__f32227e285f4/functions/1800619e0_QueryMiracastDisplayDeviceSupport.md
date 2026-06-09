# QueryMiracastDisplayDeviceSupport

- ea: `0x1800619e0`
- end: `0x180061a77`
- name: `QueryMiracastDisplayDeviceSupport`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180042d10`

## callees

- `0x180002600`
- `0x1800619e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180061a2c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180061a2c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180061a1e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180061a1e`
- `api-ms-win-dx-d3dkmt-l1-1-1!D3DKMTNetDispQueryMiracastDisplayDeviceSupport` at `0x180061a37`
- `api-ms-win-dx-d3dkmt-l1-1-1!D3DKMTNetDispQueryMiracastDisplayDeviceSupport` at `0x180061a37`

## string_xrefs

- `0x180061a11`: `mfplat.dll`

## pseudocode

```c
int __fastcall QueryMiracastDisplayDeviceSupport(__int64 a1)
{
  HMODULE Library; // rax
  int v4; // eax
  __int64 v5; // [rsp+20h] [rbp-28h] BYREF
  int v6; // [rsp+28h] [rbp-20h]

  v5 = 0;
  v6 = 0;
  if ( !a1 )
    return -2147024809;
  Library = LoadLibraryExW(L"mfplat.dll", 0, 0x800u);
  if ( !Library )
    return -2147467263;
  FreeLibrary(Library);
  v4 = D3DKMTNetDispQueryMiracastDisplayDeviceSupport(&v5);
  if ( v4 < 0 )
    return v4 | 0x10000000;
  *(_BYTE *)a1 = v5;
  *(_DWORD *)(a1 + 4) = HIDWORD(v5);
  *(_BYTE *)(a1 + 8) = v6;
  return 0;
}

```

## disassembly

```asm
0x1800619e0  push    rbx
0x1800619e2  sub     rsp, 40h
0x1800619e6  mov     rax, cs:__security_cookie
0x1800619ed  xor     rax, rsp
0x1800619f0  mov     [rsp+48h+var_18], rax
0x1800619f5  xor     eax, eax
0x1800619f7  mov     rbx, rcx
0x1800619fa  mov     [rsp+48h+var_28], rax
0x1800619ff  mov     [rsp+48h+var_20], eax
0x180061a03  test    rcx, rcx
0x180061a06  jnz     short loc_180061A0F
0x180061a08  mov     eax, 80070057h
0x180061a0d  jmp     short loc_180061A64
0x180061a0f  xor     edx, edx; hFile
0x180061a11  lea     rcx, LibFileName; "mfplat.dll"
0x180061a18  mov     r8d, 800h; dwFlags
0x180061a1e  call    cs:__imp_LoadLibraryExW
0x180061a24  test    rax, rax
0x180061a27  jz      short loc_180061A5F
0x180061a29  mov     rcx, rax; hLibModule
0x180061a2c  call    cs:__imp_FreeLibrary
0x180061a32  lea     rcx, [rsp+48h+var_28]
0x180061a37  call    cs:__imp_D3DKMTNetDispQueryMiracastDisplayDeviceSupport
0x180061a3d  test    eax, eax
0x180061a3f  js      short loc_180061A59
0x180061a41  mov     al, byte ptr [rsp+48h+var_28]
0x180061a45  mov     [rbx], al
0x180061a47  mov     eax, dword ptr [rsp+48h+var_28+4]
0x180061a4b  mov     [rbx+4], eax
0x180061a4e  mov     al, byte ptr [rsp+48h+var_20]
0x180061a52  mov     [rbx+8], al
0x180061a55  xor     eax, eax
0x180061a57  jmp     short loc_180061A64
0x180061a59  bts     eax, 1Ch
0x180061a5d  jmp     short loc_180061A64
0x180061a5f  mov     eax, 80004001h
0x180061a64  mov     rcx, [rsp+48h+var_18]
0x180061a69  xor     rcx, rsp; StackCookie
0x180061a6c  call    __security_check_cookie
0x180061a71  add     rsp, 40h
0x180061a75  pop     rbx
0x180061a76  retn
```

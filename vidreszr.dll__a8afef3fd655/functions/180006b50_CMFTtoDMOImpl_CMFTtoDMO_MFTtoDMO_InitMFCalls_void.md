# CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_InitMFCalls(void)

- ea: `0x180006b50`
- end: `0x180006bdb`
- name: `?MFTtoDMO_InitMFCalls@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAJXZ`
- size: `139`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005800`
- `0x180005950`
- `0x180005c10`
- `0x180005d60`
- `0x180006110`
- `0x1800064a0`

## callees

- `0x180006b50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006baa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006bc4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006baa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006bc4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180006b7e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180006b7e`

## string_xrefs

- `0x180006b71`: `MFPLAT.DLL`
- `0x180006ba0`: `MFCreateMediaTypeFromRepresentation`
- `0x180006bbd`: `MFCreateLegacyMediaBufferOnMFMediaBuffer`

## pseudocode

```c
__int64 __fastcall CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_InitMFCalls(__int64 a1)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax

  if ( !*(_QWORD *)(a1 + 16) )
  {
    Library = *(HMODULE *)(a1 + 8);
    if ( Library != (HMODULE)-1LL )
    {
      if ( Library || (Library = LoadLibraryExA("MFPLAT.DLL", 0, 0x800u), (*(_QWORD *)(a1 + 8) = Library) != 0) )
      {
        ProcAddress = GetProcAddress(Library, "MFCreateMediaTypeFromRepresentation");
        *(_QWORD *)(a1 + 16) = ProcAddress;
        if ( ProcAddress )
        {
          v5 = GetProcAddress(*(HMODULE *)(a1 + 8), "MFCreateLegacyMediaBufferOnMFMediaBuffer");
          *(_QWORD *)(a1 + 24) = v5;
          if ( v5 )
            return 0;
        }
      }
      *(_QWORD *)(a1 + 8) = -1;
    }
    return 2147500037LL;
  }
  return 0;
}

```

## disassembly

```asm
0x180006b50  push    rbx
0x180006b52  sub     rsp, 20h
0x180006b56  cmp     qword ptr [rcx+10h], 0
0x180006b5b  mov     rbx, rcx
0x180006b5e  jnz     short loc_180006BD3
0x180006b60  mov     rax, [rcx+8]
0x180006b64  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006b68  jz      short loc_180006B95
0x180006b6a  test    rax, rax
0x180006b6d  jnz     short loc_180006BA0
0x180006b6f  xor     edx, edx; hFile
0x180006b71  lea     rcx, LibFileName; "MFPLAT.DLL"
0x180006b78  mov     r8d, 800h; dwFlags
0x180006b7e  call    cs:__imp_LoadLibraryExA
0x180006b84  mov     [rbx+8], rax
0x180006b88  test    rax, rax
0x180006b8b  jnz     short loc_180006BA0
0x180006b8d  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x180006b95  mov     eax, 80004005h
0x180006b9a  add     rsp, 20h
0x180006b9e  pop     rbx
0x180006b9f  retn
0x180006ba0  lea     rdx, ProcName; "MFCreateMediaTypeFromRepresentation"
0x180006ba7  mov     rcx, rax; hModule
0x180006baa  call    cs:__imp_GetProcAddress
0x180006bb0  mov     [rbx+10h], rax
0x180006bb4  test    rax, rax
0x180006bb7  jz      short loc_180006B8D
0x180006bb9  mov     rcx, [rbx+8]; hModule
0x180006bbd  lea     rdx, aMfcreatelegacy; "MFCreateLegacyMediaBufferOnMFMediaBuffe"...
0x180006bc4  call    cs:__imp_GetProcAddress
0x180006bca  mov     [rbx+18h], rax
0x180006bce  test    rax, rax
0x180006bd1  jz      short loc_180006B8D
0x180006bd3  xor     eax, eax
0x180006bd5  add     rsp, 20h
0x180006bd9  pop     rbx
0x180006bda  retn
```

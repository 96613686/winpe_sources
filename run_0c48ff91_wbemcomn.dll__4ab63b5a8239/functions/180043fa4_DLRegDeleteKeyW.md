# DLRegDeleteKeyW

- ea: `0x180043fa4`
- end: `0x180044069`
- name: `DLRegDeleteKeyW`
- size: `197`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180034e00`
- `0x180035070`

## callees

- `0x1800101cc`
- `0x180043fa4`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044035`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044035`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043feb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004400e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043feb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004400e`

## string_xrefs

- `0x180043fe4`: `RegDeleteKeyExW`
- `0x180044007`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall DLRegDeleteKeyW(__int64 a1, __int64 a2)
{
  int (*v2)(HKEY, const unsigned __int16 *, unsigned int, unsigned int); // r10
  FARPROC ProcAddress; // rax
  DWORD result; // eax

  v2 = g_pfnRegDeleteKeyExW;
  if ( !g_pfnRegDeleteKeyExW )
  {
    ProcAddress = (FARPROC)qword_1800703C8;
    if ( qword_1800703C8 )
      return ((__int64 (__fastcall *)(__int64, __int64))ProcAddress)(a1, a2);
    result = DLpLoadRegistryDll();
    if ( result )
      return result;
    g_pfnRegDeleteKeyExW = (int (*)(HKEY, const unsigned __int16 *, unsigned int, unsigned int))GetProcAddress(
                                                                                                  g_hInstRegistryDLL,
                                                                                                  "RegDeleteKeyExW");
    v2 = g_pfnRegDeleteKeyExW;
    if ( g_pfnRegDeleteKeyExW )
    {
      ProcAddress = (FARPROC)qword_1800703C8;
    }
    else
    {
      ProcAddress = GetProcAddress(g_hInstRegistryDLL, "RegDeleteKeyW");
      v2 = g_pfnRegDeleteKeyExW;
      qword_1800703C8 = (__int64)ProcAddress;
    }
    if ( !v2 )
    {
      if ( !ProcAddress )
        return GetLastError();
      return ((__int64 (__fastcall *)(__int64, __int64))ProcAddress)(a1, a2);
    }
  }
  return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD))v2)(a1, a2, 0, 0);
}

```

## disassembly

```asm
0x180043fa4  mov     [rsp+arg_0], rbx
0x180043fa9  push    rdi
0x180043faa  sub     rsp, 30h
0x180043fae  mov     r10, cs:?g_pfnRegDeleteKeyExW@@3P6AJPEAUHKEY__@@PEBGKK@ZEA; long (*g_pfnRegDeleteKeyExW)(HKEY__ *,ushort const *,ulong,ulong)
0x180043fb5  mov     rbx, rdx
0x180043fb8  mov     rdi, rcx
0x180043fbb  test    r10, r10
0x180043fbe  jnz     loc_18004404A
0x180043fc4  mov     rax, cs:qword_1800703C8
0x180043fcb  test    rax, rax
0x180043fce  jnz     short loc_18004403D
0x180043fd0  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x180043fd5  test    eax, eax
0x180043fd7  jnz     loc_18004405E
0x180043fdd  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180043fe4  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180043feb  call    cs:__imp_GetProcAddress
0x180043ff1  mov     cs:?g_pfnRegDeleteKeyExW@@3P6AJPEAUHKEY__@@PEBGKK@ZEA, rax; long (*g_pfnRegDeleteKeyExW)(HKEY__ *,ushort const *,ulong,ulong)
0x180043ff8  mov     r10, rax
0x180043ffb  test    rax, rax
0x180043ffe  jnz     short loc_180044024
0x180044000  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180044007  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18004400e  call    cs:__imp_GetProcAddress
0x180044014  mov     r10, cs:?g_pfnRegDeleteKeyExW@@3P6AJPEAUHKEY__@@PEBGKK@ZEA; long (*g_pfnRegDeleteKeyExW)(HKEY__ *,ushort const *,ulong,ulong)
0x18004401b  mov     cs:qword_1800703C8, rax
0x180044022  jmp     short loc_18004402B
0x180044024  mov     rax, cs:qword_1800703C8
0x18004402b  test    r10, r10
0x18004402e  jnz     short loc_18004404A
0x180044030  test    rax, rax
0x180044033  jnz     short loc_18004403D
0x180044035  call    cs:__imp_GetLastError
0x18004403b  jmp     short loc_18004405E
0x18004403d  mov     rdx, rbx
0x180044040  mov     rcx, rdi
0x180044043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044048  jmp     short loc_18004405E
0x18004404a  xor     r9d, r9d
0x18004404d  xor     r8d, r8d
0x180044050  mov     rdx, rbx
0x180044053  mov     rcx, rdi
0x180044056  mov     rax, r10
0x180044059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004405e  mov     rbx, [rsp+38h+arg_0]
0x180044063  add     rsp, 30h
0x180044067  pop     rdi
0x180044068  retn
```

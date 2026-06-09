# CreateAMoniker(IMoniker *,ushort const *,IMoniker * *)

- ea: `0x140009a90`
- end: `0x140009b4b`
- name: `?CreateAMoniker@@YAJPEAUIMoniker@@PEBGPEAPEAU1@@Z`
- size: `187`
- prototype: `int(struct IMoniker *, const unsigned __int16 *, struct IMoniker **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14000757c`
- `0x14000f700`

## callees

- `0x140009a90`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140009aed`
- `KERNEL32!GetLastError` at `0x140009aed`
- `KERNEL32!GetProcAddress` at `0x140009b0b`
- `KERNEL32!GetProcAddress` at `0x140009b0b`
- `KERNEL32!LoadLibraryExW` at `0x140009ad4`
- `KERNEL32!LoadLibraryExW` at `0x140009ad4`
- `ole32!CreateFileMoniker` at `0x140009b3a`
- `ole32!CreateFileMoniker` at `0x140009b3a`

## string_xrefs

- `0x140009ac7`: `urlmon.dll`
- `0x140009b01`: `CreateURLMonikerEx`

## pseudocode

```c
HRESULT __fastcall CreateAMoniker(struct IMoniker *a1, const unsigned __int16 *a2, struct IMoniker **a3)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  HRESULT result; // eax
  bool v8; // sf

  if ( !byte_1400209D0 )
  {
    ProcAddress = (FARPROC)qword_1400209C8;
    if ( qword_1400209C8
      || ((Library = Global::g_hURLMON) != 0
       || (Library = LoadLibraryExW(L"urlmon.dll", 0, 0x800u), (Global::g_hURLMON = Library) != 0))
      && (ProcAddress = GetProcAddress(Library, "CreateURLMonikerEx"), (qword_1400209C8 = (__int64)ProcAddress) != 0) )
    {
      result = ((__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, struct IMoniker **, __int64))ProcAddress)(
                 0,
                 a2,
                 a3,
                 1);
    }
    else
    {
      byte_1400209D0 = 1;
      result = GetLastError();
      v8 = result < 0;
      if ( result <= 0 )
        goto LABEL_10;
      result = (unsigned __int16)result | 0x80070000;
    }
    v8 = result < 0;
LABEL_10:
    if ( !v8 )
      return result;
  }
  return CreateFileMoniker(a2, a3);
}

```

## disassembly

```asm
0x140009a90  mov     [rsp+arg_0], rbx
0x140009a95  push    rdi
0x140009a96  sub     rsp, 30h
0x140009a9a  cmp     cs:byte_1400209D0, 0
0x140009aa1  mov     rbx, r8
0x140009aa4  mov     rdi, rdx
0x140009aa7  jnz     loc_140009B34
0x140009aad  mov     rax, cs:qword_1400209C8
0x140009ab4  test    rax, rax
0x140009ab7  jnz     short loc_140009B1D
0x140009ab9  mov     rax, cs:?g_hURLMON@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hURLMON
0x140009ac0  test    rax, rax
0x140009ac3  jnz     short loc_140009B01
0x140009ac5  xor     edx, edx; hFile
0x140009ac7  lea     rcx, aUrlmonDll; "urlmon.dll"
0x140009ace  mov     r8d, 800h; dwFlags
0x140009ad4  call    cs:__imp_LoadLibraryExW
0x140009ada  mov     cs:?g_hURLMON@Global@@2PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Global::g_hURLMON
0x140009ae1  test    rax, rax
0x140009ae4  jnz     short loc_140009B01
0x140009ae6  mov     cs:byte_1400209D0, 1
0x140009aed  call    cs:__imp_GetLastError
0x140009af3  test    eax, eax
0x140009af5  jle     short loc_140009B32
0x140009af7  movzx   eax, ax
0x140009afa  or      eax, 80070000h
0x140009aff  jmp     short loc_140009B30
0x140009b01  lea     rdx, aCreateurlmonik; "CreateURLMonikerEx"
0x140009b08  mov     rcx, rax; hModule
0x140009b0b  call    cs:__imp_GetProcAddress
0x140009b11  mov     cs:qword_1400209C8, rax
0x140009b18  test    rax, rax
0x140009b1b  jz      short loc_140009AE6
0x140009b1d  mov     r9d, 1
0x140009b23  mov     r8, rbx
0x140009b26  mov     rdx, rdi
0x140009b29  xor     ecx, ecx
0x140009b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b30  test    eax, eax
0x140009b32  jns     short loc_140009B40
0x140009b34  mov     rdx, rbx; ppmk
0x140009b37  mov     rcx, rdi; lpszPathName
0x140009b3a  call    cs:__imp_CreateFileMoniker
0x140009b40  mov     rbx, [rsp+38h+arg_0]
0x140009b45  add     rsp, 30h
0x140009b49  pop     rdi
0x140009b4a  retn
```

# LoadAvrt(void)

- ea: `0x18004fdb0`
- end: `0x18004fe6a`
- name: `?LoadAvrt@@YAHXZ`
- size: `186`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004fb9c`
- `0x18004fce8`

## callees

- `0x18004fdb0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004fe12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004fe2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004fe48`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004fe12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004fe2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004fe48`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004fdf6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004fdf6`

## string_xrefs

- `0x18004fded`: `avrt.dll`
- `0x18004fe08`: `AvSetMmThreadCharacteristicsW`
- `0x18004fe3a`: `AvSetMmThreadPriority`
- `0x18004fe1f`: `AvRevertMmThreadCharacteristics`

## pseudocode

```c
_BOOL8 LoadAvrt(void)
{
  _BOOL8 result; // rax
  HMODULE Library; // rax

  result = (ghmodAvrt
         || (Library = LoadLibraryExW(L"avrt.dll", 0, 0), (ghmodAvrt = Library) != 0)
         && (gpfnAvSetMmThreadCharacteristics = (void *(*)(const unsigned __int16 *, unsigned int *))GetProcAddress(Library, "AvSetMmThreadCharacteristicsW"),
             gpfnAvRevertMmThreadCharacteristics = (int (*)(void *))GetProcAddress(
                                                                      ghmodAvrt,
                                                                      "AvRevertMmThreadCharacteristics"),
             gpfnAvSetMmThreadPriority = (int (*)(void *, enum _AVRT_PRIORITY))GetProcAddress(
                                                                                 ghmodAvrt,
                                                                                 "AvSetMmThreadPriority"),
             ghmodAvrt))
        && gpfnAvSetMmThreadCharacteristics
        && gpfnAvRevertMmThreadCharacteristics
        && gpfnAvSetMmThreadPriority;
  return result;
}

```

## disassembly

```asm
0x18004fdb0  sub     rsp, 28h
0x18004fdb4  cmp     cs:?ghmodAvrt@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ghmodAvrt
0x18004fdbc  jz      short loc_18004FDEA
0x18004fdbe  cmp     cs:?gpfnAvSetMmThreadCharacteristics@@3P6APEAXPEBGPEAK@ZEA, 0; void * (*gpfnAvSetMmThreadCharacteristics)(ushort const *,ulong *)
0x18004fdc6  jz      short loc_18004FDE6
0x18004fdc8  cmp     cs:?gpfnAvRevertMmThreadCharacteristics@@3P6AHPEAX@ZEA, 0; int (*gpfnAvRevertMmThreadCharacteristics)(void *)
0x18004fdd0  jz      short loc_18004FDE6
0x18004fdd2  cmp     cs:?gpfnAvSetMmThreadPriority@@3P6AHPEAXW4_AVRT_PRIORITY@@@ZEA, 0; int (*gpfnAvSetMmThreadPriority)(void *,_AVRT_PRIORITY)
0x18004fdda  jz      short loc_18004FDE6
0x18004fddc  mov     eax, 1
0x18004fde1  add     rsp, 28h
0x18004fde5  retn
0x18004fde6  xor     eax, eax
0x18004fde8  jmp     short loc_18004FDE1
0x18004fdea  xor     r8d, r8d; dwFlags
0x18004fded  lea     rcx, LibFileName; "avrt.dll"
0x18004fdf4  xor     edx, edx; hFile
0x18004fdf6  call    cs:__imp_LoadLibraryExW
0x18004fdfc  mov     cs:?ghmodAvrt@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ghmodAvrt
0x18004fe03  test    rax, rax
0x18004fe06  jz      short loc_18004FDE6
0x18004fe08  lea     rdx, aAvsetmmthreadc; "AvSetMmThreadCharacteristicsW"
0x18004fe0f  mov     rcx, rax; hModule
0x18004fe12  call    cs:__imp_GetProcAddress
0x18004fe18  mov     rcx, cs:?ghmodAvrt@@3PEAUHINSTANCE__@@EA; hModule
0x18004fe1f  lea     rdx, aAvrevertmmthre; "AvRevertMmThreadCharacteristics"
0x18004fe26  mov     cs:?gpfnAvSetMmThreadCharacteristics@@3P6APEAXPEBGPEAK@ZEA, rax; void * (*gpfnAvSetMmThreadCharacteristics)(ushort const *,ulong *)
0x18004fe2d  call    cs:__imp_GetProcAddress
0x18004fe33  mov     rcx, cs:?ghmodAvrt@@3PEAUHINSTANCE__@@EA; hModule
0x18004fe3a  lea     rdx, aAvsetmmthreadp; "AvSetMmThreadPriority"
0x18004fe41  mov     cs:?gpfnAvRevertMmThreadCharacteristics@@3P6AHPEAX@ZEA, rax; int (*gpfnAvRevertMmThreadCharacteristics)(void *)
0x18004fe48  call    cs:__imp_GetProcAddress
0x18004fe4e  mov     cs:?gpfnAvSetMmThreadPriority@@3P6AHPEAXW4_AVRT_PRIORITY@@@ZEA, rax; int (*gpfnAvSetMmThreadPriority)(void *,_AVRT_PRIORITY)
0x18004fe55  mov     rax, cs:?ghmodAvrt@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * ghmodAvrt
0x18004fe5c  test    rax, rax
0x18004fe5f  jnz     loc_18004FDBE
0x18004fe65  jmp     loc_18004FDE6
```

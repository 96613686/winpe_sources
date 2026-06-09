# ModuleLoaderImpl::Load(HINSTANCE__ * &,wchar_t const *)

- ea: `0x180016290`
- end: `0x1800162c4`
- name: `?Load@ModuleLoaderImpl@@UEAAKAEAPEAUHINSTANCE__@@PEB_W@Z`
- size: `52`
- prototype: `unsigned int(ModuleLoaderImpl *__hidden this, HINSTANCE *, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180016290`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162b5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800162a2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800162a2`

## pseudocode

```c
DWORD __fastcall ModuleLoaderImpl::Load(ModuleLoaderImpl *this, HINSTANCE *a2, const wchar_t *a3)
{
  HMODULE Library; // rax

  Library = LoadLibraryExW(a3, 0, 2u);
  *a2 = Library;
  if ( Library )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180016290  push    rbx
0x180016292  sub     rsp, 20h
0x180016296  mov     rbx, rdx
0x180016299  mov     rcx, r8; lpLibFileName
0x18001629c  xor     edx, edx; hFile
0x18001629e  lea     r8d, [rdx+2]; dwFlags
0x1800162a2  call    cs:__imp_LoadLibraryExW
0x1800162a8  mov     [rbx], rax
0x1800162ab  test    rax, rax
0x1800162ae  jnz     short loc_1800162BC
0x1800162b0  add     rsp, 20h
0x1800162b4  pop     rbx
0x1800162b5  jmp     cs:__imp_GetLastError
0x1800162bc  xor     eax, eax
0x1800162be  add     rsp, 20h
0x1800162c2  pop     rbx
0x1800162c3  retn
```

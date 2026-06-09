# CDynamicLinkLibrary::Win32LoadLibrary(ushort const *,ulong)

- ea: `0x180059490`
- end: `0x1800594ea`
- name: `?Win32LoadLibrary@CDynamicLinkLibrary@@QEAAHPEBGK@Z`
- size: `90`
- prototype: `int(CDynamicLinkLibrary *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180055574`
- `0x18005fb10`

## callees

- `0x18000a804`
- `0x180059490`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800594a1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800594a1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800594d2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800594d2`

## pseudocode

```c
__int64 __fastcall CDynamicLinkLibrary::Win32LoadLibrary(HMODULE *this, const unsigned __int16 *a2, DWORD a3)
{
  HMODULE Library; // rax
  HMODULE v6; // rcx

  Library = LoadLibraryExW(a2, 0, a3);
  if ( Library )
  {
    v6 = *this;
    if ( Library != *this )
    {
      *this = Library;
      if ( v6 )
        FreeLibrary(v6);
    }
    return 1;
  }
  else
  {
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)`CDynamicLinkLibrary::Win32LoadLibrary'::`7'::__callsite);
    return 0;
  }
}

```

## disassembly

```asm
0x180059490  push    rbx
0x180059492  sub     rsp, 20h
0x180059496  mov     rax, rdx
0x180059499  mov     rbx, rcx
0x18005949c  mov     rcx, rax; lpLibFileName
0x18005949f  xor     edx, edx; hFile
0x1800594a1  call    cs:__imp_LoadLibraryExW
0x1800594a8  nop     dword ptr [rax+rax+00h]
0x1800594ad  test    rax, rax
0x1800594b0  jnz     short loc_1800594C2
0x1800594b2  lea     rcx, ?__callsite@?6??Win32LoadLibrary@CDynamicLinkLibrary@@QEAAHPEBGK@Z@4U_CALL_SITE_INFO@@B; struct _CALL_SITE_INFO *
0x1800594b9  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x1800594be  xor     eax, eax
0x1800594c0  jmp     short loc_1800594E3
0x1800594c2  mov     rcx, [rbx]; hLibModule
0x1800594c5  cmp     rax, rcx
0x1800594c8  jz      short loc_1800594DE
0x1800594ca  mov     [rbx], rax
0x1800594cd  test    rcx, rcx
0x1800594d0  jz      short loc_1800594DE
0x1800594d2  call    cs:__imp_FreeLibrary
0x1800594d9  nop     dword ptr [rax+rax+00h]
0x1800594de  mov     eax, 1
0x1800594e3  add     rsp, 20h
0x1800594e7  pop     rbx
0x1800594e8  retn
```

# LaunchURL(HWND__ *,ushort const *)

- ea: `0x180009d08`
- end: `0x180009d5a`
- name: `?LaunchURL@@YA_NPEAUHWND__@@PEBG@Z`
- size: `82`
- prototype: `bool __fastcall(HWND, OLECHAR *psz)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005bf0`
- `0x180006520`
- `0x180007248`

## callees

- `0x1800090b8`
- `0x180009988`
- `0x180009d08`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x180009d2d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x180009d2d`

## pseudocode

```c
char __fastcall LaunchURL(HWND a1, OLECHAR *psz, __int64 a3, int a4)
{
  if ( !psz || StrCmpNW(psz, L"mshelp://", 9) )
    return LaunchProgram(a1, psz, 0, a4);
  else
    return DisplayHelpTask(psz);
}

```

## disassembly

```asm
0x180009d08  mov     [rsp+arg_0], rbx
0x180009d0d  push    rdi
0x180009d0e  sub     rsp, 20h
0x180009d12  mov     rbx, rdx
0x180009d15  mov     rdi, rcx
0x180009d18  test    rdx, rdx
0x180009d1b  jz      short loc_180009D41
0x180009d1d  mov     r8d, 9; nChar
0x180009d23  lea     rdx, psz2; "mshelp://"
0x180009d2a  mov     rcx, rbx; psz1
0x180009d2d  call    cs:__imp_StrCmpNW
0x180009d33  test    eax, eax
0x180009d35  jnz     short loc_180009D41
0x180009d37  mov     rcx, rbx; psz
0x180009d3a  call    ?DisplayHelpTask@@YA_NPEBG@Z; DisplayHelpTask(ushort const *)
0x180009d3f  jmp     short loc_180009D4F
0x180009d41  xor     r8d, r8d; unsigned __int16 *
0x180009d44  mov     rdx, rbx; unsigned __int16 *
0x180009d47  mov     rcx, rdi; HWND
0x180009d4a  call    ?LaunchProgram@@YA_NPEAUHWND__@@PEBG1H@Z; LaunchProgram(HWND__ *,ushort const *,ushort const *,int)
0x180009d4f  mov     rbx, [rsp+28h+arg_0]
0x180009d54  add     rsp, 20h
0x180009d58  pop     rdi
0x180009d59  retn
```

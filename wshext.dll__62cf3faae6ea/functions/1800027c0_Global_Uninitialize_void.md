# Global::Uninitialize(void)

- ea: `0x1800027c0`
- end: `0x180002802`
- name: `?Uninitialize@Global@@SAXXZ`
- size: `66`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002760`

## callees

- `0x1800027c0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800027eb`
- `KERNEL32!FreeLibrary` at `0x1800027f2`
- `KERNEL32!FreeLibrary` at `0x1800027fa`
- `KERNEL32!FreeLibrary` at `0x1800027f2`
- `KERNEL32!FreeLibrary` at `0x1800027fa`

## pseudocode

```c
void Global::Uninitialize(void)
{
  if ( Global::g_hResource != Global::g_hInstance )
    FreeLibrary(Global::g_hResource);
  if ( Global::g_hURLMON )
    FreeLibrary(Global::g_hURLMON);
  DeleteCriticalSection(&CDispatch::s_oCS);
}

```

## disassembly

```asm
0x1800027c0  sub     rsp, 28h
0x1800027c4  mov     rcx, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; hLibModule
0x1800027cb  cmp     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x1800027d2  jnz     short loc_1800027F2
0x1800027d4  mov     rcx, cs:?g_hURLMON@Global@@2PEAUHINSTANCE__@@EA; hLibModule
0x1800027db  test    rcx, rcx
0x1800027de  jnz     short loc_1800027FA
0x1800027e0  lea     rcx, ?s_oCS@CDispatch@@2U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION CDispatch::s_oCS
0x1800027e7  add     rsp, 28h
0x1800027eb  jmp     cs:__imp_DeleteCriticalSection
0x1800027f2  call    cs:__imp_FreeLibrary
0x1800027f8  jmp     short loc_1800027D4
0x1800027fa  call    cs:__imp_FreeLibrary
0x180002800  jmp     short loc_1800027E0
```

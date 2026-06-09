# Global::Uninitialize(void)

- ea: `0x180005778`
- end: `0x1800057ba`
- name: `?Uninitialize@Global@@SAXXZ`
- size: `66`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002c00`

## callees

- `0x180005778`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800057a3`
- `KERNEL32!FreeLibrary` at `0x1800057aa`
- `KERNEL32!FreeLibrary` at `0x1800057b2`
- `KERNEL32!FreeLibrary` at `0x1800057aa`
- `KERNEL32!FreeLibrary` at `0x1800057b2`

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
0x180005778  sub     rsp, 28h
0x18000577c  mov     rcx, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; hLibModule
0x180005783  cmp     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x18000578a  jnz     short loc_1800057AA
0x18000578c  mov     rcx, cs:?g_hURLMON@Global@@2PEAUHINSTANCE__@@EA; hLibModule
0x180005793  test    rcx, rcx
0x180005796  jnz     short loc_1800057B2
0x180005798  lea     rcx, ?s_oCS@CDispatch@@2U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION CDispatch::s_oCS
0x18000579f  add     rsp, 28h
0x1800057a3  jmp     cs:__imp_DeleteCriticalSection
0x1800057aa  call    cs:__imp_FreeLibrary
0x1800057b0  jmp     short loc_18000578C
0x1800057b2  call    cs:__imp_FreeLibrary
0x1800057b8  jmp     short loc_180005798
```

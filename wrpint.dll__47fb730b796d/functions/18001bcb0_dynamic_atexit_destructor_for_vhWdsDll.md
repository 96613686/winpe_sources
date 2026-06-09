# _dynamic_atexit_destructor_for__vhWdsDll__

- ea: `0x18001bcb0`
- end: `0x18001bce7`
- name: `_dynamic_atexit_destructor_for__vhWdsDll__`
- size: `55`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001bcb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bcca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bcca`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001bcc0`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001bcc0`

## pseudocode

```c
void dynamic_atexit_destructor_for__vhWdsDll__()
{
  if ( vhWdsDll )
  {
    if ( !FreeLibrary(vhWdsDll) )
    {
      GetLastError();
      __fastfail(7u);
    }
    vhWdsDll = 0;
  }
}

```

## disassembly

```asm
0x18001bcb0  sub     rsp, 28h
0x18001bcb4  mov     rcx, cs:?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A; hLibModule
0x18001bcbb  test    rcx, rcx
0x18001bcbe  jz      short loc_18001BCE2
0x18001bcc0  call    cs:__imp_FreeLibrary
0x18001bcc6  test    eax, eax
0x18001bcc8  jnz     short loc_18001BCD7
0x18001bcca  call    cs:__imp_GetLastError
0x18001bcd0  mov     ecx, 7
0x18001bcd5  int     29h; Win8: RtlFailFast(ecx)
0x18001bcd7  mov     cs:?vhWdsDll@@3V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@A, 0; Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> vhWdsDll
0x18001bce2  add     rsp, 28h
0x18001bce6  retn
```

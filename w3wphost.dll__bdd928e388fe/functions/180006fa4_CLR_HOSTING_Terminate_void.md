# CLR_HOSTING::Terminate(void)

- ea: `0x180006fa4`
- end: `0x180006fe0`
- name: `?Terminate@CLR_HOSTING@@SAXXZ`
- size: `60`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003340`
- `0x180004750`
- `0x180004a40`

## callees

- `0x180006fa4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006fca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006fca`

## pseudocode

```c
void CLR_HOSTING::Terminate(void)
{
  CLR_HOSTING::s_pFnCoreBindToRuntimeEx = 0;
  CLR_HOSTING::s_pFnCoreBindToRuntimeHost = 0;
  if ( CLR_HOSTING::s_hClrModule )
  {
    FreeLibrary(CLR_HOSTING::s_hClrModule);
    CLR_HOSTING::s_hClrModule = 0;
  }
}

```

## disassembly

```asm
0x180006fa4  sub     rsp, 28h
0x180006fa8  mov     rcx, cs:?s_hClrModule@CLR_HOSTING@@0PEAUHINSTANCE__@@EA; hLibModule
0x180006faf  mov     cs:?s_pFnCoreBindToRuntimeEx@CLR_HOSTING@@0P6AJPEBG0KAEBU_GUID@@1PEAPEAX@ZEA, 0; long (*CLR_HOSTING::s_pFnCoreBindToRuntimeEx)(ushort const *,ushort const *,ulong,_GUID const &,_GUID const &,void * *)
0x180006fba  mov     cs:?s_pFnCoreBindToRuntimeHost@CLR_HOSTING@@0P6AJPEBG00PEAXKAEBU_GUID@@2PEAPEAX@ZEA, 0; long (*CLR_HOSTING::s_pFnCoreBindToRuntimeHost)(ushort const *,ushort const *,ushort const *,void *,ulong,_GUID const &,_GUID const &,void * *)
0x180006fc5  test    rcx, rcx
0x180006fc8  jz      short loc_180006FDB
0x180006fca  call    cs:__imp_FreeLibrary
0x180006fd0  mov     cs:?s_hClrModule@CLR_HOSTING@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * CLR_HOSTING::s_hClrModule
0x180006fdb  add     rsp, 28h
0x180006fdf  retn
```

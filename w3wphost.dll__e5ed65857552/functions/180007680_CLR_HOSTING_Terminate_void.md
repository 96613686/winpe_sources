# CLR_HOSTING::Terminate(void)

- ea: `0x180007680`
- end: `0x1800076c3`
- name: `?Terminate@CLR_HOSTING@@SAXXZ`
- size: `67`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003540`
- `0x180004b20`
- `0x180004e50`

## callees

- `0x180007680`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800076a6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800076a6`

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
0x180007680  sub     rsp, 28h
0x180007684  mov     rcx, cs:?s_hClrModule@CLR_HOSTING@@0PEAUHINSTANCE__@@EA; hLibModule
0x18000768b  mov     cs:?s_pFnCoreBindToRuntimeEx@CLR_HOSTING@@0P6AJPEBG0KAEBU_GUID@@1PEAPEAX@ZEA, 0; long (*CLR_HOSTING::s_pFnCoreBindToRuntimeEx)(ushort const *,ushort const *,ulong,_GUID const &,_GUID const &,void * *)
0x180007696  mov     cs:?s_pFnCoreBindToRuntimeHost@CLR_HOSTING@@0P6AJPEBG00PEAXKAEBU_GUID@@2PEAPEAX@ZEA, 0; long (*CLR_HOSTING::s_pFnCoreBindToRuntimeHost)(ushort const *,ushort const *,ushort const *,void *,ulong,_GUID const &,_GUID const &,void * *)
0x1800076a1  test    rcx, rcx
0x1800076a4  jz      short loc_1800076BD
0x1800076a6  call    cs:__imp_FreeLibrary
0x1800076ad  nop     dword ptr [rax+rax+00h]
0x1800076b2  mov     cs:?s_hClrModule@CLR_HOSTING@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * CLR_HOSTING::s_hClrModule
0x1800076bd  add     rsp, 28h
0x1800076c1  retn
```

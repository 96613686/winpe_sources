# WFDSConMgr::CWFDApiShim::StartOpenSession(void *,uchar const (*)[6],void *,void (*)(void *,void *,_GUID,ulong,ulong),ushort *,_WFD_FIREWALL_CONFIGURATION_PARAMETERS const *,void * *)

- ea: `0x18002ead0`
- end: `0x18002eb1a`
- name: `?StartOpenSession@CWFDApiShim@WFDSConMgr@@UEBAKPEAXPEAY05$$CBE0P6AX00U_GUID@@KK@ZPEAGPEBU_WFD_FIREWALL_CONFIGURATION_PARAMETERS@@PEAPEAX@Z`
- size: `74`
- prototype: `unsigned int __fastcall(WFDSConMgr::CWFDApiShim *__hidden this, void *, const unsigned __int8 (*)[6], void *, void (*)(void *, void *, struct _GUID *__struct_ptr, unsigned int, unsigned int), unsigned __int16 *, const struct _WFD_FIREWALL_CONFIGURATION_PARAMETERS *, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `wlanapi!WFDStartOpenSessionInt` at `0x18002eb0e`
- `wlanapi!WFDStartOpenSessionInt` at `0x18002eb0e`

## pseudocode

```c
__int64 __fastcall WFDSConMgr::CWFDApiShim::StartOpenSession(
        WFDSConMgr::CWFDApiShim *this,
        void *a2,
        const unsigned __int8 (*a3)[6],
        void *a4,
        void (*a5)(void *, void *, struct _GUID *__struct_ptr, unsigned int, unsigned int),
        unsigned __int16 *a6,
        const struct _WFD_FIREWALL_CONFIGURATION_PARAMETERS *a7,
        void **a8)
{
  return WFDStartOpenSessionInt(a2, (const unsigned __int8 *)a3, a4, a5, a6, a7, a8);
}

```

## disassembly

```asm
0x18002ead0  push    rbx
0x18002ead2  sub     rsp, 40h
0x18002ead6  mov     rax, [rsp+48h+arg_38]
0x18002eade  mov     r10, r9
0x18002eae1  mov     r9, [rsp+48h+arg_20]
0x18002eae6  mov     r11, r8
0x18002eae9  mov     [rsp+48h+var_18], rax
0x18002eaee  mov     rcx, rdx
0x18002eaf1  mov     rax, [rsp+48h+arg_30]
0x18002eaf9  mov     r8, r10
0x18002eafc  mov     [rsp+48h+var_20], rax
0x18002eb01  mov     rdx, r11
0x18002eb04  mov     rax, [rsp+48h+arg_28]
0x18002eb09  mov     [rsp+48h+var_28], rax
0x18002eb0e  call    cs:__imp_WFDStartOpenSessionInt
0x18002eb14  add     rsp, 40h
0x18002eb18  pop     rbx
0x18002eb19  retn
```

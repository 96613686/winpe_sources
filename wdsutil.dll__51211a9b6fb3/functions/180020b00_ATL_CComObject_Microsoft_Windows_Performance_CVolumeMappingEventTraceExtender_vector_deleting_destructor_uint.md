# ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x180020b00`
- end: `0x180020b37`
- name: `??_E?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180020a24`
- `0x180020b00`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180020b1c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020b1c`

## pseudocode

```c
void *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vector deleting destructor'(
        void *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180020b00  mov     [rsp+arg_0], rbx
0x180020b05  push    rdi
0x180020b06  sub     rsp, 20h
0x180020b0a  mov     ebx, edx
0x180020b0c  mov     rdi, rcx
0x180020b0f  call    ??1?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>(void)
0x180020b14  test    bl, 1
0x180020b17  jz      short loc_180020B28
0x180020b19  mov     rcx, rdi
0x180020b1c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180020b23  nop     dword ptr [rax+rax+00h]
0x180020b28  mov     rbx, [rsp+28h+arg_0]
0x180020b2d  mov     rax, rdi
0x180020b30  add     rsp, 20h
0x180020b34  pop     rdi
0x180020b35  retn
```

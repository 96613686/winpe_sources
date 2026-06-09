# ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x18000a6e0`
- end: `0x18000a717`
- name: `??_E?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000a1dc`
- `0x18000a6e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a6fc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a6fc`

## pseudocode

```c
void *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vector deleting destructor'(
        void *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a6e0  mov     [rsp+arg_0], rbx
0x18000a6e5  push    rdi
0x18000a6e6  sub     rsp, 20h
0x18000a6ea  mov     ebx, edx
0x18000a6ec  mov     rdi, rcx
0x18000a6ef  call    ??1?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>(void)
0x18000a6f4  test    bl, 1
0x18000a6f7  jz      short loc_18000A708
0x18000a6f9  mov     rcx, rdi
0x18000a6fc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a703  nop     dword ptr [rax+rax+00h]
0x18000a708  mov     rbx, [rsp+28h+arg_0]
0x18000a70d  mov     rax, rdi
0x18000a710  add     rsp, 20h
0x18000a714  pop     rdi
0x18000a715  retn
```

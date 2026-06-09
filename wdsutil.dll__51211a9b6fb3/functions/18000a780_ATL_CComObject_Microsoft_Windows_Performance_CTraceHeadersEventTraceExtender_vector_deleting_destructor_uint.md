# ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x18000a780`
- end: `0x18000a7b7`
- name: `??_E?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000a24c`
- `0x18000a780`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a79c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a79c`

## pseudocode

```c
void *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vector deleting destructor'(
        void *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a780  mov     [rsp+arg_0], rbx
0x18000a785  push    rdi
0x18000a786  sub     rsp, 20h
0x18000a78a  mov     ebx, edx
0x18000a78c  mov     rdi, rcx
0x18000a78f  call    ??1?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>(void)
0x18000a794  test    bl, 1
0x18000a797  jz      short loc_18000A7A8
0x18000a799  mov     rcx, rdi
0x18000a79c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a7a3  nop     dword ptr [rax+rax+00h]
0x18000a7a8  mov     rbx, [rsp+28h+arg_0]
0x18000a7ad  mov     rax, rdi
0x18000a7b0  add     rsp, 20h
0x18000a7b4  pop     rdi
0x18000a7b5  retn
```

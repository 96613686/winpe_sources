# ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x18002bdb0`
- end: `0x18002bde7`
- name: `??_E?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002bd38`
- `0x18002bdb0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002bdcc`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002bdcc`

## pseudocode

```c
void *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vector deleting destructor'(
        void *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18002bdb0  mov     [rsp+arg_0], rbx
0x18002bdb5  push    rdi
0x18002bdb6  sub     rsp, 20h
0x18002bdba  mov     ebx, edx
0x18002bdbc  mov     rdi, rcx
0x18002bdbf  call    ??1?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>(void)
0x18002bdc4  test    bl, 1
0x18002bdc7  jz      short loc_18002BDD8
0x18002bdc9  mov     rcx, rdi
0x18002bdcc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002bdd3  nop     dword ptr [rax+rax+00h]
0x18002bdd8  mov     rbx, [rsp+28h+arg_0]
0x18002bddd  mov     rax, rdi
0x18002bde0  add     rsp, 20h
0x18002bde4  pop     rdi
0x18002bde5  retn
```

# CWMPRichPreviewRemoteService::GetServiceType(ushort * *)

- ea: `0x140004f00`
- end: `0x140004f37`
- name: `?GetServiceType@CWMPRichPreviewRemoteService@@UEAAJPEAPEAG@Z`
- size: `55`
- prototype: `__int64 __fastcall(CWMPRichPreviewRemoteService *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140004f00`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140004f15`
- `OLEAUT32!__imp_SysAllocString` at `0x140004f15`

## pseudocode

```c
__int64 __fastcall CWMPRichPreviewRemoteService::GetServiceType(
        CWMPRichPreviewRemoteService *this,
        unsigned __int16 **a2)
{
  unsigned __int16 *v3; // rax

  if ( !a2 )
    return 2147942487LL;
  v3 = SysAllocString(L"Local");
  *a2 = v3;
  return v3 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x140004f00  push    rbx
0x140004f02  sub     rsp, 20h
0x140004f06  mov     rbx, rdx
0x140004f09  test    rdx, rdx
0x140004f0c  jz      short loc_140004F2C
0x140004f0e  lea     rcx, aLocal; "Local"
0x140004f15  call    cs:__imp_SysAllocString
0x140004f1b  mov     [rbx], rax
0x140004f1e  neg     rax
0x140004f21  sbb     eax, eax
0x140004f23  not     eax
0x140004f25  and     eax, 8007000Eh
0x140004f2a  jmp     short loc_140004F31
0x140004f2c  mov     eax, 80070057h
0x140004f31  add     rsp, 20h
0x140004f35  pop     rbx
0x140004f36  retn
```

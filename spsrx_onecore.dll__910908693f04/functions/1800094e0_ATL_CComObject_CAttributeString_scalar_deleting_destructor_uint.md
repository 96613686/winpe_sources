# ATL::CComObject<CAttributeString>::`scalar deleting destructor'(uint)

- ea: `0x1800094e0`
- end: `0x180009514`
- name: `??_G?$CComObject@VCAttributeString@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002594`
- `0x180009138`
- `0x1800094e0`

## pseudocode

```c
CAttributeString *__fastcall ATL::CComObject<CAttributeString>::`scalar deleting destructor'(
        CAttributeString *a1,
        char a2)
{
  ATL::CComObject<CAttributeString>::~CComObject<CAttributeString>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800094e0  mov     [rsp+arg_0], rbx
0x1800094e5  push    rdi
0x1800094e6  sub     rsp, 20h
0x1800094ea  mov     ebx, edx
0x1800094ec  mov     rdi, rcx
0x1800094ef  call    ??1?$CComObject@VCAttributeString@@@ATL@@UEAA@XZ; ATL::CComObject<CAttributeString>::~CComObject<CAttributeString>(void)
0x1800094f4  test    bl, 1
0x1800094f7  jz      short loc_180009506
0x1800094f9  mov     edx, 60h ; '`'; unsigned __int64
0x1800094fe  mov     rcx, rdi; void *
0x180009501  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009506  mov     rbx, [rsp+28h+arg_0]
0x18000950b  mov     rax, rdi
0x18000950e  add     rsp, 20h
0x180009512  pop     rdi
0x180009513  retn
```

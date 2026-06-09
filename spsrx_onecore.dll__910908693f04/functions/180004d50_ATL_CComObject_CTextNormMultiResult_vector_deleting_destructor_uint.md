# ATL::CComObject<CTextNormMultiResult>::`vector deleting destructor'(uint)

- ea: `0x180004d50`
- end: `0x180004d84`
- name: `??_E?$CComObject@VCTextNormMultiResult@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002594`
- `0x180004cbc`
- `0x180004d50`

## pseudocode

```c
CTextNormMultiResult *__fastcall ATL::CComObject<CTextNormMultiResult>::`vector deleting destructor'(
        CTextNormMultiResult *a1,
        char a2)
{
  ATL::CComObject<CTextNormMultiResult>::~CComObject<CTextNormMultiResult>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180004d50  mov     [rsp+arg_0], rbx
0x180004d55  push    rdi
0x180004d56  sub     rsp, 20h
0x180004d5a  mov     ebx, edx
0x180004d5c  mov     rdi, rcx
0x180004d5f  call    ??1?$CComObject@VCTextNormMultiResult@@@ATL@@UEAA@XZ; ATL::CComObject<CTextNormMultiResult>::~CComObject<CTextNormMultiResult>(void)
0x180004d64  test    bl, 1
0x180004d67  jz      short loc_180004D76
0x180004d69  mov     edx, 0B8h; unsigned __int64
0x180004d6e  mov     rcx, rdi; void *
0x180004d71  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004d76  mov     rbx, [rsp+28h+arg_0]
0x180004d7b  mov     rax, rdi
0x180004d7e  add     rsp, 20h
0x180004d82  pop     rdi
0x180004d83  retn
```

# CGenericTableMap<CWindowData *,CGenericSet<CWindowData *>::SetElement<CWindowData *>>::RemoveElement(CGenericSet<CWindowData *>::SetElement<CWindowData *> *)

- ea: `0x180073758`
- end: `0x180073788`
- name: `?RemoveElement@?$CGenericTableMap@PEAVCWindowData@@U?$SetElement@PEAVCWindowData@@@?$CGenericSet@PEAVCWindowData@@@@@@QEAAXPEAU?$SetElement@PEAVCWindowData@@@?$CGenericSet@PEAVCWindowData@@@@@Z`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800add70`
- `0x1800dae54`

## callees

- `0x180073758`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180073780`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180073780`
- `ntdll!RtlDeleteElementGenericTable` at `0x180073769`
- `ntdll!RtlDeleteElementGenericTable` at `0x180073769`

## pseudocode

```c
void __fastcall CGenericTableMap<CWindowData *,CGenericSet<CWindowData *>::SetElement<CWindowData *>>::RemoveElement(
        struct _RTL_GENERIC_TABLE *a1,
        __int64 *a2)
{
  __int64 Buffer; // [rsp+38h] [rbp+10h] BYREF

  Buffer = *a2;
  if ( !RtlDeleteElementGenericTable(a1, &Buffer) )
    RaiseFailFastException(0, 0, 1u);
}

```

## disassembly

```asm
0x180073758  sub     rsp, 28h
0x18007375c  mov     rax, [rdx]
0x18007375f  lea     rdx, [rsp+28h+Buffer]; Buffer
0x180073764  mov     [rsp+28h+Buffer], rax
0x180073769  call    cs:__imp_RtlDeleteElementGenericTable
0x18007376f  test    al, al
0x180073771  jz      short loc_180073778
0x180073773  add     rsp, 28h
0x180073777  retn
0x180073778  xor     edx, edx; pContextRecord
0x18007377a  xor     ecx, ecx; pExceptionRecord
0x18007377c  lea     r8d, [rdx+1]; dwFlags
0x180073780  call    cs:__imp_RaiseFailFastException
0x180073786  jmp     short loc_180073773
```

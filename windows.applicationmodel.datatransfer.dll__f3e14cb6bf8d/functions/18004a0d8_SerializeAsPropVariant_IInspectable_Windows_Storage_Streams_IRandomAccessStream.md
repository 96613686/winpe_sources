# SerializeAsPropVariant(IInspectable *,Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x18004a0d8`
- end: `0x18004a197`
- name: `?SerializeAsPropVariant@@YAJPEAUIInspectable@@PEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(IUnknown *, struct Windows::Storage::Streams::IRandomAccessStream **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004a1a0`

## callees

- `0x18002415c`
- `0x18004a0d8`
- `0x180081010`

## import_xrefs

- `SHCORE!SHCreateMemStream` at `0x18004a135`
- `SHCORE!SHCreateMemStream` at `0x18004a135`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a178`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004a182`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004a182`
- `PROPSYS!StgSerializePropVariant` at `0x18004a122`
- `PROPSYS!StgSerializePropVariant` at `0x18004a122`
- `PROPSYS!__imp_WinRTPropertyValueToPropVariant` at `0x18004a0fb`
- `PROPSYS!__imp_WinRTPropertyValueToPropVariant` at `0x18004a0fb`

## pseudocode

```c
__int64 __fastcall SerializeAsPropVariant(IUnknown *a1, struct Windows::Storage::Streams::IRandomAccessStream **a2)
{
  HRESULT OnlyRandomAccessStreamOverStream; // ebx
  struct IStream *v4; // rax
  struct IStream *v5; // rdi
  SERIALIZEDPROPERTYVALUE *v6; // rcx
  PROPVARIANT ppropvar[4]; // [rsp+20h] [rbp-20h] BYREF
  ULONG pcb; // [rsp+68h] [rbp+28h] BYREF
  SERIALIZEDPROPERTYVALUE *ppProp; // [rsp+70h] [rbp+30h] BYREF

  *a2 = 0;
  LOWORD(ppropvar[0]) = 0;
  OnlyRandomAccessStreamOverStream = WinRTPropertyValueToPropVariant(a1, ppropvar);
  if ( OnlyRandomAccessStreamOverStream >= 0 )
  {
    pcb = 0;
    ppProp = 0;
    OnlyRandomAccessStreamOverStream = StgSerializePropVariant(ppropvar, &ppProp, &pcb);
    if ( OnlyRandomAccessStreamOverStream >= 0 )
    {
      v4 = SHCreateMemStream((const BYTE *)ppProp, pcb);
      v5 = v4;
      if ( v4 )
        OnlyRandomAccessStreamOverStream = CreateReadOnlyRandomAccessStreamOverStream(v4, a2);
      else
        OnlyRandomAccessStreamOverStream = -2147024882;
      if ( v5 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v5 + 16LL))(v5);
    }
    v6 = ppProp;
    ppProp = 0;
    CoTaskMemFree(v6);
  }
  PropVariantClear(ppropvar);
  return (unsigned int)OnlyRandomAccessStreamOverStream;
}

```

## disassembly

```asm
0x18004a0d8  mov     [rsp-18h+arg_0], rbx
0x18004a0dd  push    rbp
0x18004a0de  push    rsi
0x18004a0df  push    rdi
0x18004a0e0  mov     rbp, rsp
0x18004a0e3  sub     rsp, 40h
0x18004a0e7  mov     rsi, rdx
0x18004a0ea  mov     qword ptr [rdx], 0
0x18004a0f1  xor     eax, eax
0x18004a0f3  mov     word ptr [rbp+ppropvar], ax
0x18004a0f7  lea     rdx, [rbp+ppropvar]; ppropvar
0x18004a0fb  call    cs:__imp_WinRTPropertyValueToPropVariant
0x18004a101  mov     ebx, eax
0x18004a103  test    eax, eax
0x18004a105  js      short loc_18004A17E
0x18004a107  mov     [rbp+pcb], 0
0x18004a10e  mov     [rbp+ppProp], 0
0x18004a116  lea     r8, [rbp+pcb]; pcb
0x18004a11a  lea     rdx, [rbp+ppProp]; ppProp
0x18004a11e  lea     rcx, [rbp+ppropvar]; ppropvar
0x18004a122  call    cs:__imp_StgSerializePropVariant
0x18004a128  mov     ebx, eax
0x18004a12a  test    eax, eax
0x18004a12c  js      short loc_18004A16C
0x18004a12e  mov     edx, [rbp+pcb]; cbInit
0x18004a131  mov     rcx, [rbp+ppProp]; pInit
0x18004a135  call    cs:__imp_SHCreateMemStream
0x18004a13b  mov     rdi, rax
0x18004a13e  test    rax, rax
0x18004a141  jz      short loc_18004A152
0x18004a143  mov     rdx, rsi; struct Windows::Storage::Streams::IRandomAccessStream **
0x18004a146  mov     rcx, rax; struct IStream *
0x18004a149  call    ?CreateReadOnlyRandomAccessStreamOverStream@@YAJPEAUIStream@@PEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; CreateReadOnlyRandomAccessStreamOverStream(IStream *,Windows::Storage::Streams::IRandomAccessStream * *)
0x18004a14e  mov     ebx, eax
0x18004a150  jmp     short loc_18004A157
0x18004a152  mov     ebx, 8007000Eh
0x18004a157  test    rdi, rdi
0x18004a15a  jz      short loc_18004A16C
0x18004a15c  mov     rax, [rdi]
0x18004a15f  mov     rcx, rdi
0x18004a162  mov     rax, [rax+10h]
0x18004a166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a16b  nop
0x18004a16c  mov     rcx, [rbp+ppProp]; pv
0x18004a170  mov     [rbp+ppProp], 0
0x18004a178  call    cs:__imp_CoTaskMemFree
0x18004a17e  lea     rcx, [rbp+ppropvar]; pvar
0x18004a182  call    cs:__imp_PropVariantClear
0x18004a188  mov     eax, ebx
0x18004a18a  mov     rbx, [rsp+40h+arg_0]
0x18004a18f  add     rsp, 40h
0x18004a193  pop     rdi
0x18004a194  pop     rsi
0x18004a195  pop     rbp
0x18004a196  retn
```

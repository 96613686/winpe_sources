# SlbNatConvertRdIdtoCompartmentId

- ea: `0x14002ffe4`
- end: `0x140030054`
- name: `SlbNatConvertRdIdtoCompartmentId`
- size: `112`
- prototype: `__int64 __fastcall(GUID *CompartmentGuid)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400300c4`
- `0x1400308ac`

## callees

- `0x14002ffe4`

## import_xrefs

- `NETIO!ConvertCompartmentGuidToId` at `0x14003001c`
- `NETIO!ConvertCompartmentGuidToId` at `0x14003001c`
- `NETIO!OpenCompartment` at `0x14002ffff`
- `NETIO!OpenCompartment` at `0x14002ffff`
- `NETIO!CloseCompartment` at `0x14003002f`
- `NETIO!CloseCompartment` at `0x14003002f`

## pseudocode

```c
__int64 __fastcall SlbNatConvertRdIdtoCompartmentId(GUID *CompartmentGuid, _QWORD *a2)
{
  unsigned int v2; // edi
  UINT32 CompartmentId; // [rsp+40h] [rbp+18h] BYREF

  v2 = 0;
  CompartmentId = 0;
  if ( (int)OpenCompartment() >= 0 )
  {
    if ( ConvertCompartmentGuidToId(CompartmentGuid, &CompartmentId) >= 0 )
      return CompartmentId;
    CloseCompartment(*a2);
  }
  *a2 = 0;
  return v2;
}

```

## disassembly

```asm
0x14002ffe4  mov     [rsp+arg_0], rbx
0x14002ffe9  mov     [rsp+arg_8], rsi
0x14002ffee  push    rdi
0x14002ffef  sub     rsp, 20h
0x14002fff3  xor     edi, edi
0x14002fff5  mov     rbx, rdx
0x14002fff8  mov     [rsp+28h+CompartmentId], edi
0x14002fffc  mov     rsi, rcx
0x14002ffff  call    cs:__imp_OpenCompartment
0x140030006  nop     dword ptr [rax+rax+00h]
0x14003000b  test    eax, eax
0x14003000d  jns     short loc_140030014
0x14003000f  mov     [rbx], rdi
0x140030012  jmp     short loc_140030041
0x140030014  lea     rdx, [rsp+28h+CompartmentId]; CompartmentId
0x140030019  mov     rcx, rsi; CompartmentGuid
0x14003001c  call    cs:__imp_ConvertCompartmentGuidToId
0x140030023  nop     dword ptr [rax+rax+00h]
0x140030028  test    eax, eax
0x14003002a  jns     short loc_14003003D
0x14003002c  mov     rcx, [rbx]
0x14003002f  call    cs:__imp_CloseCompartment
0x140030036  nop     dword ptr [rax+rax+00h]
0x14003003b  jmp     short loc_14003000F
0x14003003d  mov     edi, [rsp+28h+CompartmentId]
0x140030041  mov     rbx, [rsp+28h+arg_0]
0x140030046  mov     eax, edi
0x140030048  mov     rsi, [rsp+28h+arg_8]
0x14003004d  add     rsp, 20h
0x140030051  pop     rdi
0x140030052  retn
```

# SlbNatConvertRdIdtoCompartmentId

- ea: `0x140031114`
- end: `0x140031184`
- name: `SlbNatConvertRdIdtoCompartmentId`
- size: `112`
- prototype: `__int64 __fastcall(GUID *CompartmentGuid)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400311f4`
- `0x1400319dc`

## callees

- `0x140031114`

## import_xrefs

- `NETIO!ConvertCompartmentGuidToId` at `0x14003114c`
- `NETIO!ConvertCompartmentGuidToId` at `0x14003114c`
- `NETIO!OpenCompartment` at `0x14003112f`
- `NETIO!OpenCompartment` at `0x14003112f`
- `NETIO!CloseCompartment` at `0x14003115f`
- `NETIO!CloseCompartment` at `0x14003115f`

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
0x140031114  mov     [rsp+arg_0], rbx
0x140031119  mov     [rsp+arg_8], rsi
0x14003111e  push    rdi
0x14003111f  sub     rsp, 20h
0x140031123  xor     edi, edi
0x140031125  mov     rbx, rdx
0x140031128  mov     [rsp+28h+CompartmentId], edi
0x14003112c  mov     rsi, rcx
0x14003112f  call    cs:__imp_OpenCompartment
0x140031136  nop     dword ptr [rax+rax+00h]
0x14003113b  test    eax, eax
0x14003113d  jns     short loc_140031144
0x14003113f  mov     [rbx], rdi
0x140031142  jmp     short loc_140031171
0x140031144  lea     rdx, [rsp+28h+CompartmentId]; CompartmentId
0x140031149  mov     rcx, rsi; CompartmentGuid
0x14003114c  call    cs:__imp_ConvertCompartmentGuidToId
0x140031153  nop     dword ptr [rax+rax+00h]
0x140031158  test    eax, eax
0x14003115a  jns     short loc_14003116D
0x14003115c  mov     rcx, [rbx]
0x14003115f  call    cs:__imp_CloseCompartment
0x140031166  nop     dword ptr [rax+rax+00h]
0x14003116b  jmp     short loc_14003113F
0x14003116d  mov     edi, [rsp+28h+CompartmentId]
0x140031171  mov     rbx, [rsp+28h+arg_0]
0x140031176  mov     eax, edi
0x140031178  mov     rsi, [rsp+28h+arg_8]
0x14003117d  add     rsp, 20h
0x140031181  pop     rdi
0x140031182  retn
```

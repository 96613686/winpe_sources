# TSFreeDecoded(ulong,void *)

- ea: `0x180006440`
- end: `0x180006527`
- name: `?TSFreeDecoded@@YAXKPEAX@Z`
- size: `231`
- prototype: `void __fastcall(unsigned int, void *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180018e3c`
- `0x180019958`
- `0x18001a914`

## callees

- `0x180006440`

## import_xrefs

- `MSASN1!ASN1_CreateDecoder` at `0x180006482`
- `MSASN1!ASN1_CreateDecoder` at `0x180006482`
- `MSASN1!ASN1_CreateModule` at `0x180006515`
- `MSASN1!ASN1_CreateModule` at `0x180006515`
- `MSASN1!ASN1_FreeDecoded` at `0x180006497`
- `MSASN1!ASN1_FreeDecoded` at `0x180006497`
- `MSASN1!ASN1_CloseDecoder` at `0x1800064a7`
- `MSASN1!ASN1_CloseDecoder` at `0x1800064a7`

## pseudocode

```c
void __fastcall TSFreeDecoded(unsigned int a1, void *a2)
{
  __int64 Module; // rax
  __int64 v5; // [rsp+68h] [rbp+10h] BYREF

  if ( a2 )
  {
    v5 = 0;
    if ( fTSSSPModuleStarted )
    {
      Module = TSSSP_Module;
    }
    else
    {
      fTSSSPModuleStarted = 1;
      Module = ASN1_CreateModule(
                 0x10000,
                 1024,
                 4096,
                 6,
                 off_18001E1E0,
                 off_18001E1B0,
                 off_18001E180,
                 qword_18001F2E8,
                 1936946036);
      TSSSP_Module = Module;
    }
    if ( !(unsigned int)ASN1_CreateDecoder(Module, &v5, 0, 0, 0) )
    {
      ASN1_FreeDecoded(v5, a2, a1);
      if ( v5 )
        ASN1_CloseDecoder();
    }
  }
}

```

## disassembly

```asm
0x180006440  test    rdx, rdx
0x180006443  jz      short locret_1800064BC
0x180006445  mov     [rsp+arg_0], rbx
0x18000644a  mov     [rsp+arg_10], rsi
0x18000644f  push    rdi
0x180006450  sub     rsp, 50h
0x180006454  xor     esi, esi
0x180006456  mov     rbx, rdx
0x180006459  cmp     cs:?fTSSSPModuleStarted@@3HA, esi; int fTSSSPModuleStarted
0x18000645f  mov     edi, ecx
0x180006461  mov     [rsp+58h+arg_8], rsi
0x180006466  jz      short loc_1800064BD
0x180006468  mov     rax, cs:TSSSP_Module
0x18000646f  xor     r9d, r9d
0x180006472  mov     [rsp+58h+var_38], rsi
0x180006477  xor     r8d, r8d
0x18000647a  lea     rdx, [rsp+58h+arg_8]
0x18000647f  mov     rcx, rax
0x180006482  call    cs:__imp_ASN1_CreateDecoder
0x180006488  test    eax, eax
0x18000648a  jnz     short loc_1800064AD
0x18000648c  mov     rcx, [rsp+58h+arg_8]
0x180006491  mov     r8d, edi
0x180006494  mov     rdx, rbx
0x180006497  call    cs:__imp_ASN1_FreeDecoded
0x18000649d  mov     rcx, [rsp+58h+arg_8]
0x1800064a2  test    rcx, rcx
0x1800064a5  jz      short loc_1800064AD
0x1800064a7  call    cs:__imp_ASN1_CloseDecoder
0x1800064ad  mov     rbx, [rsp+58h+arg_0]
0x1800064b2  mov     rsi, [rsp+58h+arg_10]
0x1800064b7  add     rsp, 50h
0x1800064bb  pop     rdi
0x1800064bc  retn
0x1800064bd  mov     [rsp+58h+var_18], 73737374h
0x1800064c5  lea     rax, qword_18001F2E8
0x1800064cc  mov     [rsp+58h+var_20], rax
0x1800064d1  mov     edx, 400h
0x1800064d6  lea     rax, off_18001E180
0x1800064dd  mov     cs:?fTSSSPModuleStarted@@3HA, 1; int fTSSSPModuleStarted
0x1800064e7  mov     [rsp+58h+var_28], rax
0x1800064ec  mov     ecx, 10000h
0x1800064f1  lea     rax, off_18001E1B0
0x1800064f8  mov     r9d, 6
0x1800064fe  mov     [rsp+58h+var_30], rax
0x180006503  mov     r8d, 1000h
0x180006509  lea     rax, off_18001E1E0
0x180006510  mov     [rsp+58h+var_38], rax
0x180006515  call    cs:__imp_ASN1_CreateModule
0x18000651b  mov     cs:TSSSP_Module, rax
0x180006522  jmp     loc_18000646F
```

# TSDecodeData(uchar *,ulong,ulong,void * *)

- ea: `0x180005400`
- end: `0x180005511`
- name: `?TSDecodeData@@YAJPEAEKKPEAPEAX@Z`
- size: `273`
- prototype: `__int64 __fastcall(unsigned __int8 *, int, unsigned int, void **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180018e3c`
- `0x180019958`
- `0x18001a914`

## callees

- `0x180005400`

## import_xrefs

- `MSASN1!ASN1_Decode` at `0x180005469`
- `MSASN1!ASN1_Decode` at `0x180005469`
- `MSASN1!ASN1_CreateDecoder` at `0x180005441`
- `MSASN1!ASN1_CreateDecoder` at `0x180005441`
- `MSASN1!ASN1_CreateModule` at `0x1800054ed`
- `MSASN1!ASN1_CreateModule` at `0x1800054ed`
- `MSASN1!ASN1_CloseDecoder` at `0x180005481`
- `MSASN1!ASN1_CloseDecoder` at `0x180005481`

## pseudocode

```c
__int64 __fastcall TSDecodeData(unsigned __int8 *a1, int a2, unsigned int a3, void **a4)
{
  unsigned int v4; // r14d
  __int64 Module; // rax
  _QWORD v11[7]; // [rsp+50h] [rbp-38h] BYREF

  v4 = 0;
  v11[0] = 0;
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
  if ( (unsigned int)ASN1_CreateDecoder(Module, v11, 0, 0, 0) )
    return 3221225473LL;
  if ( (int)ASN1_Decode(v11[0], a4, a3, 8, a1, a2) < 0 )
    v4 = -1073741823;
  if ( v11[0] )
    ASN1_CloseDecoder();
  return v4;
}

```

## disassembly

```asm
0x180005400  push    rbx
0x180005402  push    rbp
0x180005403  push    rsi
0x180005404  push    rdi
0x180005405  push    r14
0x180005407  sub     rsp, 60h
0x18000540b  xor     r14d, r14d
0x18000540e  mov     rbx, r9
0x180005411  cmp     cs:?fTSSSPModuleStarted@@3HA, r14d; int fTSSSPModuleStarted
0x180005418  mov     edi, r8d
0x18000541b  mov     esi, edx
0x18000541d  mov     [rsp+88h+var_38], r14
0x180005422  mov     rbp, rcx
0x180005425  jz      short loc_180005495
0x180005427  mov     rax, cs:TSSSP_Module
0x18000542e  xor     r9d, r9d
0x180005431  mov     [rsp+88h+var_68], r14
0x180005436  xor     r8d, r8d
0x180005439  lea     rdx, [rsp+88h+var_38]
0x18000543e  mov     rcx, rax
0x180005441  call    cs:__imp_ASN1_CreateDecoder
0x180005447  test    eax, eax
0x180005449  jnz     loc_1800054FF
0x18000544f  mov     rcx, [rsp+88h+var_38]
0x180005454  mov     r9d, 8
0x18000545a  mov     dword ptr [rsp+88h+var_60], esi
0x18000545e  mov     r8d, edi
0x180005461  mov     rdx, rbx
0x180005464  mov     [rsp+88h+var_68], rbp
0x180005469  call    cs:__imp_ASN1_Decode
0x18000546f  test    eax, eax
0x180005471  js      loc_180005506
0x180005477  mov     rcx, [rsp+88h+var_38]
0x18000547c  test    rcx, rcx
0x18000547f  jz      short loc_180005487
0x180005481  call    cs:__imp_ASN1_CloseDecoder
0x180005487  mov     eax, r14d
0x18000548a  add     rsp, 60h
0x18000548e  pop     r14
0x180005490  pop     rdi
0x180005491  pop     rsi
0x180005492  pop     rbp
0x180005493  pop     rbx
0x180005494  retn
0x180005495  mov     [rsp+88h+var_48], 73737374h
0x18000549d  lea     rax, qword_18001F2E8
0x1800054a4  mov     [rsp+88h+var_50], rax
0x1800054a9  mov     edx, 400h
0x1800054ae  lea     rax, off_18001E180
0x1800054b5  mov     cs:?fTSSSPModuleStarted@@3HA, 1; int fTSSSPModuleStarted
0x1800054bf  mov     [rsp+88h+var_58], rax
0x1800054c4  mov     ecx, 10000h
0x1800054c9  lea     rax, off_18001E1B0
0x1800054d0  mov     r9d, 6
0x1800054d6  mov     [rsp+88h+var_60], rax
0x1800054db  mov     r8d, 1000h
0x1800054e1  lea     rax, off_18001E1E0
0x1800054e8  mov     [rsp+88h+var_68], rax
0x1800054ed  call    cs:__imp_ASN1_CreateModule
0x1800054f3  mov     cs:TSSSP_Module, rax
0x1800054fa  jmp     loc_18000542E
0x1800054ff  mov     eax, 0C0000001h
0x180005504  jmp     short loc_18000548A
0x180005506  mov     r14d, 0C0000001h
0x18000550c  jmp     loc_180005477
```

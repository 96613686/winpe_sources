# TpmApiReadPublic20

- ea: `0x140032eb4`
- end: `0x140032f52`
- name: `TpmApiReadPublic20`
- size: `158`
- prototype: `__int64 __fastcall(int, int, int, int, int, unsigned __int8 *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14002a6c4`
- `0x14002a89c`

## callees

- `0x140031df4`
- `0x140032eb4`
- `0x1400367d8`
- `0x140038688`
- `0x140038740`

## pseudocode

```c
__int64 __fastcall TpmApiReadPublic20(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int8 *a6,
        unsigned int *a7)
{
  int v8; // ebx
  _BYTE v10[196]; // [rsp+20h] [rbp-168h] BYREF
  int v11; // [rsp+E4h] [rbp-A4h]
  tpm12class::TpmDataObject *v12; // [rsp+E8h] [rbp-A0h]
  __int64 v13; // [rsp+1A8h] [rbp+20h] BYREF

  v13 = a4;
  if ( dword_1400480C8 == 1 )
  {
    return (unsigned int)-2147467263;
  }
  else if ( dword_1400480C8 == 2 )
  {
    v13 = a1;
    tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v10);
    v11 = a2;
    v8 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v10, &v13);
    if ( v8 >= 0 && a7 )
      v8 = tpm12class::TpmDataObject::Get(v12, a6, *a7, a7);
    tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v10);
  }
  else
  {
    return (unsigned int)-2144796371;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140032eb4  mov     [rsp+arg_18], r9
0x140032eb9  push    rbx
0x140032eba  sub     rsp, 180h
0x140032ec1  mov     eax, cs:dword_1400480C8
0x140032ec7  mov     ebx, edx
0x140032ec9  cmp     eax, 1
0x140032ecc  jnz     short loc_140032ED5
0x140032ece  mov     ebx, 80004001h
0x140032ed3  jmp     short loc_140032F46
0x140032ed5  cmp     eax, 2
0x140032ed8  jnz     short loc_140032F41
0x140032eda  mov     [rsp+188h+arg_18], rcx
0x140032ee2  lea     rcx, [rsp+188h+var_168]; this
0x140032ee7  call    ??0TPMW8_ReadPublic@tpm12class@@QEAA@XZ; tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic(void)
0x140032eec  lea     rdx, [rsp+188h+arg_18]; void *
0x140032ef4  mov     [rsp+188h+var_A4], ebx
0x140032efb  lea     rcx, [rsp+188h+var_168]; this
0x140032f00  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x140032f05  mov     ebx, eax
0x140032f07  test    eax, eax
0x140032f09  js      short loc_140032F35
0x140032f0b  mov     r8, [rsp+188h+arg_30]
0x140032f13  test    r8, r8
0x140032f16  jz      short loc_140032F35
0x140032f18  mov     rdx, [rsp+188h+arg_28]; unsigned __int8 *
0x140032f20  mov     r9, r8; unsigned int *
0x140032f23  mov     r8d, [r8]; unsigned int
0x140032f26  mov     rcx, [rsp+188h+var_A0]; this
0x140032f2e  call    ?Get@TpmDataObject@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TpmDataObject::Get(uchar *,uint,uint *)
0x140032f33  mov     ebx, eax
0x140032f35  lea     rcx, [rsp+188h+var_168]; this
0x140032f3a  call    ??1TPMW8_ReadPublic@tpm12class@@UEAA@XZ; tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic(void)
0x140032f3f  jmp     short loc_140032F46
0x140032f41  mov     ebx, 8029012Dh
0x140032f46  mov     eax, ebx
0x140032f48  add     rsp, 180h
0x140032f4f  pop     rbx
0x140032f50  retn
```

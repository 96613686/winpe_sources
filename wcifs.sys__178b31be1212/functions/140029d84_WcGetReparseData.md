# WcGetReparseData

- ea: `0x140029d84`
- end: `0x140029f7e`
- name: `WcGetReparseData`
- size: `506`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, int, unsigned __int16 **, ULONG *)`
- caller_count: `5`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x14001a62c`
- `0x14001d8dc`
- `0x140029658`
- `0x14002a664`
- `0x140030da4`

## callees

- `0x1400020c4`
- `0x1400053f8`
- `0x140029d84`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140029e2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029f55`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029e2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029f55`
- `ntoskrnl!ExAllocatePool2` at `0x140029db8`
- `ntoskrnl!ExAllocatePool2` at `0x140029db8`
- `FLTMGR!FltFsControlFile` at `0x140029dfd`
- `FLTMGR!FltFsControlFile` at `0x140029dfd`

## pseudocode

```c
__int64 __fastcall WcGetReparseData(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        int a3,
        unsigned __int16 **a4,
        ULONG *a5)
{
  ULONG OutputBufferLength; // ebx
  unsigned __int16 *OutputBuffer; // rdi
  NTSTATUS v10; // eax
  ULONG v11; // ecx
  unsigned int v12; // ebx
  int v13; // edx
  ULONG *v14; // rax
  ULONG LengthReturned; // [rsp+80h] [rbp+18h] BYREF

  LengthReturned = 0;
  OutputBufferLength = a3 + 36;
  while ( 1 )
  {
    OutputBuffer = (unsigned __int16 *)ExAllocatePool2(256, OutputBufferLength, 1769096023);
    if ( !OutputBuffer )
      return (unsigned int)-1073741670;
    v10 = FltFsControlFile(Instance, FileObject, 0x900A8u, 0, 0, OutputBuffer, OutputBufferLength, &LengthReturned);
    v11 = LengthReturned;
    v12 = v10;
    if ( LengthReturned < 8 || v10 != -2147483643 )
      break;
    OutputBufferLength = OutputBuffer[2] + 8;
    ExFreePoolWithTag(OutputBuffer, 0x69724357u);
  }
  v13 = -1073741195;
  if ( v10 == -1073741195 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 4;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v13,
        5,
        134,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        0,
        117);
    }
  }
  else if ( v10 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v13,
        5,
        135,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        8,
        v10);
    }
  }
  else
  {
    if ( LengthReturned >= (unsigned int)OutputBuffer[2] + 8 )
    {
      v14 = a5;
      *a4 = OutputBuffer;
      *v14 = v11;
      return v12;
    }
    v12 = -1073741566;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 4;
      WPP_RECORDER_SF_sDqd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v13,
        5,
        136,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        22,
        (char)FileObject,
        2);
    }
  }
  ExFreePoolWithTag(OutputBuffer, 0x69724357u);
  return v12;
}

```

## disassembly

```asm
0x140029d84  mov     rax, rsp
0x140029d87  mov     [rax+8], rbx
0x140029d8b  mov     [rax+10h], rbp
0x140029d8f  push    rsi
0x140029d90  push    rdi
0x140029d91  push    r14
0x140029d93  sub     rsp, 50h
0x140029d97  mov     rsi, r9
0x140029d9a  mov     dword ptr [rax+18h], 0
0x140029da1  mov     rbp, rdx
0x140029da4  lea     ebx, [r8+24h]
0x140029da8  mov     r14, rcx
0x140029dab  mov     edx, ebx
0x140029dad  mov     ecx, 100h
0x140029db2  mov     r8d, 69724357h
0x140029db8  call    cs:__imp_ExAllocatePool2
0x140029dbf  nop     dword ptr [rax+rax+00h]
0x140029dc4  mov     rdi, rax
0x140029dc7  test    rax, rax
0x140029dca  jz      loc_140029F63
0x140029dd0  lea     rax, [rsp+68h+arg_10]
0x140029dd8  xor     r9d, r9d; InputBuffer
0x140029ddb  mov     [rsp+68h+LengthReturned], rax; LengthReturned
0x140029de0  mov     r8d, 900A8h; FsControlCode
0x140029de6  mov     [rsp+68h+OutputBufferLength], ebx; OutputBufferLength
0x140029dea  mov     rdx, rbp; FileObject
0x140029ded  mov     [rsp+68h+OutputBuffer], rdi; OutputBuffer
0x140029df2  mov     rcx, r14; Instance
0x140029df5  mov     [rsp+68h+InputBufferLength], 0; InputBufferLength
0x140029dfd  call    cs:__imp_FltFsControlFile
0x140029e04  nop     dword ptr [rax+rax+00h]
0x140029e09  mov     ecx, [rsp+68h+arg_10]
0x140029e10  mov     ebx, eax
0x140029e12  cmp     ecx, 8
0x140029e15  jb      short loc_140029E3E
0x140029e17  cmp     eax, 80000005h
0x140029e1c  jnz     short loc_140029E3E
0x140029e1e  movzx   ebx, word ptr [rdi+4]
0x140029e22  mov     edx, 69724357h; Tag
0x140029e27  add     ebx, 8
0x140029e2a  mov     rcx, rdi; P
0x140029e2d  call    cs:__imp_ExFreePoolWithTag
0x140029e34  nop     dword ptr [rax+rax+00h]
0x140029e39  jmp     loc_140029DAB
0x140029e3e  mov     edx, 0C0000275h
0x140029e43  cmp     ebx, edx
0x140029e45  jz      loc_140029EFB
0x140029e4b  test    ebx, ebx
0x140029e4d  js      loc_140029ED5
0x140029e53  movzx   eax, word ptr [rdi+4]
0x140029e57  add     eax, 8
0x140029e5a  cmp     ecx, eax
0x140029e5c  jnb     short loc_140029EC3
0x140029e5e  mov     ebx, 0C0000102h
0x140029e63  lea     rax, WPP_RECORDER_INITIALIZED
0x140029e6a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140029e71  jz      loc_140029F4D
0x140029e77  mov     rcx, cs:wil_details_featureDescriptors_a
0x140029e7e  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x140029e85  mov     [rsp+68h+var_28], ebx
0x140029e89  mov     r9d, 88h
0x140029e8f  mov     [rsp+68h+LengthReturned], rbp
0x140029e94  mov     r8d, 5
0x140029e9a  mov     [rsp+68h+OutputBufferLength], 1216h
0x140029ea2  mov     dl, 4
0x140029ea4  mov     rcx, [rcx+40h]
0x140029ea8  mov     [rsp+68h+OutputBuffer], rax
0x140029ead  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x140029eb4  mov     qword ptr [rsp+68h+InputBufferLength], rax
0x140029eb9  call    WPP_RECORDER_SF_sDqd
0x140029ebe  jmp     loc_140029F4D
0x140029ec3  mov     rax, [rsp+68h+arg_20]
0x140029ecb  mov     [rsi], rdi
0x140029ece  mov     [rax], ecx
0x140029ed0  jmp     loc_140029F68
0x140029ed5  lea     rax, WPP_RECORDER_INITIALIZED
0x140029edc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140029ee3  jz      short loc_140029F4D
0x140029ee5  mov     dword ptr [rsp+68h+LengthReturned], ebx
0x140029ee9  mov     r9d, 87h
0x140029eef  mov     [rsp+68h+OutputBufferLength], 1208h
0x140029ef7  mov     dl, 2
0x140029ef9  jmp     short loc_140029F1F
0x140029efb  lea     rax, WPP_RECORDER_INITIALIZED
0x140029f02  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140029f09  jz      short loc_140029F4D
0x140029f0b  mov     dword ptr [rsp+68h+LengthReturned], edx
0x140029f0f  mov     r9d, 86h
0x140029f15  mov     [rsp+68h+OutputBufferLength], 1200h
0x140029f1d  mov     dl, 4
0x140029f1f  mov     rcx, cs:wil_details_featureDescriptors_a
0x140029f26  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x140029f2d  mov     [rsp+68h+OutputBuffer], rax
0x140029f32  mov     r8d, 5
0x140029f38  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x140029f3f  mov     qword ptr [rsp+68h+InputBufferLength], rax
0x140029f44  mov     rcx, [rcx+40h]
0x140029f48  call    WPP_RECORDER_SF_sDd
0x140029f4d  mov     edx, 69724357h; Tag
0x140029f52  mov     rcx, rdi; P
0x140029f55  call    cs:__imp_ExFreePoolWithTag
0x140029f5c  nop     dword ptr [rax+rax+00h]
0x140029f61  jmp     short loc_140029F68
0x140029f63  mov     ebx, 0C000009Ah
0x140029f68  mov     rbp, [rsp+68h+arg_8]
0x140029f6d  mov     eax, ebx
0x140029f6f  mov     rbx, [rsp+68h+arg_0]
0x140029f74  add     rsp, 50h
0x140029f78  pop     r14
0x140029f7a  pop     rdi
0x140029f7b  pop     rsi
0x140029f7c  retn
```

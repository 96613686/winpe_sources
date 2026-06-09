# WcGetReparseData

- ea: `0x140029d34`
- end: `0x140029f2e`
- name: `WcGetReparseData`
- size: `506`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x14001a62c`
- `0x14001d8dc`
- `0x140029608`
- `0x14002a614`
- `0x140030d54`

## callees

- `0x1400020c4`
- `0x1400053f8`
- `0x140029d34`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140029ddd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029f05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029ddd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029f05`
- `ntoskrnl!ExAllocatePool2` at `0x140029d68`
- `ntoskrnl!ExAllocatePool2` at `0x140029d68`
- `FLTMGR!FltFsControlFile` at `0x140029dad`
- `FLTMGR!FltFsControlFile` at `0x140029dad`

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
  PULONG LengthReturned; // [rsp+38h] [rbp-30h]
  ULONG v17; // [rsp+80h] [rbp+18h] BYREF

  v17 = 0;
  OutputBufferLength = a3 + 36;
  while ( 1 )
  {
    OutputBuffer = (unsigned __int16 *)ExAllocatePool2(256, OutputBufferLength, 1769096023);
    if ( !OutputBuffer )
      return (unsigned int)-1073741670;
    v10 = FltFsControlFile(Instance, FileObject, 0x900A8u, 0, 0, OutputBuffer, OutputBufferLength, &v17);
    v11 = v17;
    v12 = v10;
    if ( v17 < 8 || v10 != -2147483643 )
      break;
    OutputBufferLength = OutputBuffer[2] + 8;
    ExFreePoolWithTag(OutputBuffer, 0x69724357u);
  }
  v13 = -1073741195;
  if ( v10 == -1073741195 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(LengthReturned) = -1073741195;
      LOBYTE(v13) = 4;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        5,
        134,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        0,
        LengthReturned);
    }
  }
  else if ( v10 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(LengthReturned) = v10;
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        5,
        135,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        8,
        LengthReturned);
    }
  }
  else
  {
    if ( v17 >= (unsigned int)OutputBuffer[2] + 8 )
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
        WPP_GLOBAL_Control->DeviceExtension,
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
0x140029d34  mov     rax, rsp
0x140029d37  mov     [rax+8], rbx
0x140029d3b  mov     [rax+10h], rbp
0x140029d3f  push    rsi
0x140029d40  push    rdi
0x140029d41  push    r14
0x140029d43  sub     rsp, 50h
0x140029d47  mov     rsi, r9
0x140029d4a  mov     dword ptr [rax+18h], 0
0x140029d51  mov     rbp, rdx
0x140029d54  lea     ebx, [r8+24h]
0x140029d58  mov     r14, rcx
0x140029d5b  mov     edx, ebx
0x140029d5d  mov     ecx, 100h
0x140029d62  mov     r8d, 69724357h
0x140029d68  call    cs:__imp_ExAllocatePool2
0x140029d6f  nop     dword ptr [rax+rax+00h]
0x140029d74  mov     rdi, rax
0x140029d77  test    rax, rax
0x140029d7a  jz      loc_140029F13
0x140029d80  lea     rax, [rsp+68h+arg_10]
0x140029d88  xor     r9d, r9d; InputBuffer
0x140029d8b  mov     [rsp+68h+LengthReturned], rax; LengthReturned
0x140029d90  mov     r8d, 900A8h; FsControlCode
0x140029d96  mov     [rsp+68h+OutputBufferLength], ebx; OutputBufferLength
0x140029d9a  mov     rdx, rbp; FileObject
0x140029d9d  mov     [rsp+68h+OutputBuffer], rdi; OutputBuffer
0x140029da2  mov     rcx, r14; Instance
0x140029da5  mov     [rsp+68h+InputBufferLength], 0; InputBufferLength
0x140029dad  call    cs:__imp_FltFsControlFile
0x140029db4  nop     dword ptr [rax+rax+00h]
0x140029db9  mov     ecx, [rsp+68h+arg_10]
0x140029dc0  mov     ebx, eax
0x140029dc2  cmp     ecx, 8
0x140029dc5  jb      short loc_140029DEE
0x140029dc7  cmp     eax, 80000005h
0x140029dcc  jnz     short loc_140029DEE
0x140029dce  movzx   ebx, word ptr [rdi+4]
0x140029dd2  mov     edx, 69724357h; Tag
0x140029dd7  add     ebx, 8
0x140029dda  mov     rcx, rdi; P
0x140029ddd  call    cs:__imp_ExFreePoolWithTag
0x140029de4  nop     dword ptr [rax+rax+00h]
0x140029de9  jmp     loc_140029D5B
0x140029dee  mov     edx, 0C0000275h
0x140029df3  cmp     ebx, edx
0x140029df5  jz      loc_140029EAB
0x140029dfb  test    ebx, ebx
0x140029dfd  js      loc_140029E85
0x140029e03  movzx   eax, word ptr [rdi+4]
0x140029e07  add     eax, 8
0x140029e0a  cmp     ecx, eax
0x140029e0c  jnb     short loc_140029E73
0x140029e0e  mov     ebx, 0C0000102h
0x140029e13  lea     rax, WPP_RECORDER_INITIALIZED
0x140029e1a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140029e21  jz      loc_140029EFD
0x140029e27  mov     rcx, cs:WPP_GLOBAL_Control
0x140029e2e  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x140029e35  mov     [rsp+68h+var_28], ebx
0x140029e39  mov     r9d, 88h
0x140029e3f  mov     [rsp+68h+LengthReturned], rbp
0x140029e44  mov     r8d, 5
0x140029e4a  mov     [rsp+68h+OutputBufferLength], 1216h
0x140029e52  mov     dl, 4
0x140029e54  mov     rcx, [rcx+40h]
0x140029e58  mov     [rsp+68h+OutputBuffer], rax
0x140029e5d  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x140029e64  mov     qword ptr [rsp+68h+InputBufferLength], rax
0x140029e69  call    WPP_RECORDER_SF_sDqd
0x140029e6e  jmp     loc_140029EFD
0x140029e73  mov     rax, [rsp+68h+arg_20]
0x140029e7b  mov     [rsi], rdi
0x140029e7e  mov     [rax], ecx
0x140029e80  jmp     loc_140029F18
0x140029e85  lea     rax, WPP_RECORDER_INITIALIZED
0x140029e8c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140029e93  jz      short loc_140029EFD
0x140029e95  mov     dword ptr [rsp+68h+LengthReturned], ebx
0x140029e99  mov     r9d, 87h
0x140029e9f  mov     [rsp+68h+OutputBufferLength], 1208h
0x140029ea7  mov     dl, 2
0x140029ea9  jmp     short loc_140029ECF
0x140029eab  lea     rax, WPP_RECORDER_INITIALIZED
0x140029eb2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140029eb9  jz      short loc_140029EFD
0x140029ebb  mov     dword ptr [rsp+68h+LengthReturned], edx
0x140029ebf  mov     r9d, 86h
0x140029ec5  mov     [rsp+68h+OutputBufferLength], 1200h
0x140029ecd  mov     dl, 4
0x140029ecf  mov     rcx, cs:WPP_GLOBAL_Control
0x140029ed6  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x140029edd  mov     [rsp+68h+OutputBuffer], rax
0x140029ee2  mov     r8d, 5
0x140029ee8  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x140029eef  mov     qword ptr [rsp+68h+InputBufferLength], rax
0x140029ef4  mov     rcx, [rcx+40h]
0x140029ef8  call    WPP_RECORDER_SF_sDd
0x140029efd  mov     edx, 69724357h; Tag
0x140029f02  mov     rcx, rdi; P
0x140029f05  call    cs:__imp_ExFreePoolWithTag
0x140029f0c  nop     dword ptr [rax+rax+00h]
0x140029f11  jmp     short loc_140029F18
0x140029f13  mov     ebx, 0C000009Ah
0x140029f18  mov     rbp, [rsp+68h+arg_8]
0x140029f1d  mov     eax, ebx
0x140029f1f  mov     rbx, [rsp+68h+arg_0]
0x140029f24  add     rsp, 50h
0x140029f28  pop     r14
0x140029f2a  pop     rdi
0x140029f2b  pop     rsi
0x140029f2c  retn
```

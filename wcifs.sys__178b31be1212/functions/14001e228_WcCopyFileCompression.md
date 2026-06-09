# WcCopyFileCompression

- ea: `0x14001e228`
- end: `0x14001e36d`
- name: `WcCopyFileCompression`
- size: `325`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, PFLT_INSTANCE Instance, PFILE_OBJECT, PFLT_INSTANCE)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14001d8dc`
- `0x14001e028`
- `0x14002daa4`

## callees

- `0x1400020c4`
- `0x14001e228`

## import_xrefs

- `FLTMGR!FltFsControlFile` at `0x14001e273`
- `FLTMGR!FltFsControlFile` at `0x14001e310`
- `FLTMGR!FltFsControlFile` at `0x14001e273`
- `FLTMGR!FltFsControlFile` at `0x14001e310`

## pseudocode

```c
__int64 __fastcall WcCopyFileCompression(
        PFILE_OBJECT FileObject,
        PFLT_INSTANCE Instance,
        PFILE_OBJECT a3,
        PFLT_INSTANCE a4)
{
  NTSTATUS v6; // eax
  int v7; // edx
  NTSTATUS v8; // eax
  int v9; // edx
  unsigned int v10; // ebx
  _WORD InputBuffer[28]; // [rsp+40h] [rbp-38h] BYREF

  InputBuffer[0] = 0;
  v6 = FltFsControlFile(Instance, FileObject, 0x9003Cu, 0, 0, InputBuffer, 2u, 0);
  if ( v6 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v7,
        15,
        123,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        135,
        v6);
    }
    InputBuffer[0] = 1;
  }
  v8 = FltFsControlFile(a4, a3, 0x9C040u, InputBuffer, 2u, 0, 0, 0);
  v10 = v8;
  if ( v8 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_sDd(
      wil_details_featureDescriptors_a->DeviceExtension,
      v9,
      15,
      124,
      (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
      151,
      v8);
  }
  return v10;
}

```

## disassembly

```asm
0x14001e228  push    rbx
0x14001e22a  push    rdi
0x14001e22b  push    r12
0x14001e22d  push    r13
0x14001e22f  push    r14
0x14001e231  sub     rsp, 50h
0x14001e235  xor     eax, eax
0x14001e237  mov     r10, rdx
0x14001e23a  mov     [rsp+78h+LengthReturned], rax; LengthReturned
0x14001e23f  mov     rbx, r9
0x14001e242  mov     [rsp+78h+InputBuffer], ax
0x14001e247  mov     rdi, r8
0x14001e24a  lea     rax, [rsp+78h+InputBuffer]
0x14001e24f  mov     [rsp+78h+OutputBufferLength], 2; OutputBufferLength
0x14001e257  mov     rdx, rcx; FileObject
0x14001e25a  mov     [rsp+78h+OutputBuffer], rax; OutputBuffer
0x14001e25f  xor     r9d, r9d; InputBuffer
0x14001e262  mov     [rsp+78h+InputBufferLength], 0; InputBufferLength
0x14001e26a  mov     r8d, 9003Ch; FsControlCode
0x14001e270  mov     rcx, r10; Instance
0x14001e273  call    cs:__imp_FltFsControlFile
0x14001e27a  nop     dword ptr [rax+rax+00h]
0x14001e27f  lea     r14, WPP_RECORDER_INITIALIZED
0x14001e286  lea     r12, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001e28d  lea     r13, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001e294  test    eax, eax
0x14001e296  jns     short loc_14001E2DD
0x14001e298  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001e29f  jz      short loc_14001E2D3
0x14001e2a1  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001e2a8  mov     r9d, 7Bh ; '{'
0x14001e2ae  mov     dword ptr [rsp+78h+LengthReturned], eax
0x14001e2b2  mov     dl, 2
0x14001e2b4  mov     [rsp+78h+OutputBufferLength], 1087h
0x14001e2bc  mov     [rsp+78h+OutputBuffer], r12
0x14001e2c1  mov     rcx, [rcx+40h]
0x14001e2c5  lea     r8d, [r9-6Ch]
0x14001e2c9  mov     qword ptr [rsp+78h+InputBufferLength], r13
0x14001e2ce  call    WPP_RECORDER_SF_sDd
0x14001e2d3  mov     eax, 1
0x14001e2d8  mov     [rsp+78h+InputBuffer], ax
0x14001e2dd  mov     [rsp+78h+LengthReturned], 0; LengthReturned
0x14001e2e6  lea     r9, [rsp+78h+InputBuffer]; InputBuffer
0x14001e2eb  mov     [rsp+78h+OutputBufferLength], 0; OutputBufferLength
0x14001e2f3  mov     r8d, 9C040h; FsControlCode
0x14001e2f9  mov     [rsp+78h+OutputBuffer], 0; OutputBuffer
0x14001e302  mov     rdx, rdi; FileObject
0x14001e305  mov     rcx, rbx; Instance
0x14001e308  mov     [rsp+78h+InputBufferLength], 2; InputBufferLength
0x14001e310  call    cs:__imp_FltFsControlFile
0x14001e317  nop     dword ptr [rax+rax+00h]
0x14001e31c  mov     ebx, eax
0x14001e31e  test    eax, eax
0x14001e320  jns     short loc_14001E35D
0x14001e322  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001e329  jz      short loc_14001E35D
0x14001e32b  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001e332  mov     r9d, 7Ch ; '|'
0x14001e338  mov     dword ptr [rsp+78h+LengthReturned], eax
0x14001e33c  mov     dl, 2
0x14001e33e  mov     [rsp+78h+OutputBufferLength], 1097h
0x14001e346  mov     [rsp+78h+OutputBuffer], r12
0x14001e34b  mov     rcx, [rcx+40h]
0x14001e34f  lea     r8d, [r9-6Dh]
0x14001e353  mov     qword ptr [rsp+78h+InputBufferLength], r13
0x14001e358  call    WPP_RECORDER_SF_sDd
0x14001e35d  mov     eax, ebx
0x14001e35f  add     rsp, 50h
0x14001e363  pop     r14
0x14001e365  pop     r13
0x14001e367  pop     r12
0x14001e369  pop     rdi
0x14001e36a  pop     rbx
0x14001e36b  retn
```

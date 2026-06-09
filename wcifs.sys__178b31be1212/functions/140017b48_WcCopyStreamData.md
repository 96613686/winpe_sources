# WcCopyStreamData

- ea: `0x140017b48`
- end: `0x140017d92`
- name: `WcCopyStreamData`
- size: `586`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *, struct _FILE_OBJECT *, __int64, struct _FLT_INSTANCE *, PFILE_OBJECT, char)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x140018254`
- `0x14001d5b0`
- `0x14002fb70`

## callees

- `0x1400053f8`
- `0x140017b48`

## import_xrefs

- `FLTMGR!FltWriteFile` at `0x140017c65`
- `FLTMGR!FltWriteFile` at `0x140017c65`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x140017d6b`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x140017d6b`
- `FLTMGR!FltReadFile` at `0x140017c19`
- `FLTMGR!FltReadFile` at `0x140017c19`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x140017ba6`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x140017ba6`
- `FLTMGR!FltFlushBuffers` at `0x140017cf6`
- `FLTMGR!FltFlushBuffers` at `0x140017cf6`

## pseudocode

```c
__int64 __fastcall WcCopyStreamData(
        struct _FLT_INSTANCE *a1,
        struct _FILE_OBJECT *a2,
        __int64 a3,
        struct _FLT_INSTANCE *a4,
        PFILE_OBJECT a5,
        char a6)
{
  ULONG v6; // edi
  PVOID Buffer; // r13
  bool v11; // cf
  NTSTATUS v12; // ebx
  __int64 v13; // r12
  struct _FILE_OBJECT *v14; // r15
  FLT_IO_OPERATION_FLAGS Flags; // eax
  int v16; // edx
  int v17; // r9d
  char BytesRead; // [rsp+30h] [rbp-30h]
  char CallbackRoutine; // [rsp+38h] [rbp-28h]
  char CallbackContext; // [rsp+40h] [rbp-20h]
  ULONG BytesWritten; // [rsp+50h] [rbp-10h] BYREF
  FLT_IO_OPERATION_FLAGS v22; // [rsp+54h] [rbp-Ch]
  union _LARGE_INTEGER ByteOffset; // [rsp+58h] [rbp-8h] BYREF
  ULONG Length; // [rsp+B0h] [rbp+50h] BYREF

  v6 = 0x1000000;
  ByteOffset.QuadPart = 0;
  Length = 0;
  BytesWritten = 0;
  if ( a3 < 0x1000000 )
    v6 = (a3 + 4095) & 0xFFFFF000;
  Buffer = FltAllocatePoolAlignedWithTag(a4, (POOL_TYPE)512, v6, 0x62654357u);
  if ( !Buffer )
    return 3221225626LL;
  v11 = a6 != 0;
  a6 = -a6;
  v12 = 0;
  ByteOffset.QuadPart = 0;
  v13 = a3;
  v14 = a5;
  Flags = 5 - v11;
  v22 = Flags;
  while ( v13 )
  {
    v12 = FltReadFile(a1, a2, &ByteOffset, v6, Buffer, Flags, &Length, 0, 0);
    if ( v12 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_19;
      v17 = 13;
      CallbackContext = v12;
      CallbackRoutine = (char)a2;
      BytesRead = 21;
      goto LABEL_18;
    }
    v12 = FltWriteFile(a4, v14, &ByteOffset, Length, Buffer, 5u, &BytesWritten, 0, 0);
    if ( v12 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_19;
      CallbackContext = v12;
      v17 = 14;
      CallbackRoutine = (char)v14;
      BytesRead = 49;
      goto LABEL_18;
    }
    v13 -= Length;
    ByteOffset.QuadPart += Length;
    Flags = v22;
  }
  if ( a3 < 4096 )
  {
    v12 = FltFlushBuffers(a4, v14);
    if ( v12 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      CallbackContext = v12;
      v17 = 15;
      CallbackRoutine = (char)v14;
      BytesRead = 73;
LABEL_18:
      LOBYTE(v16) = 4;
      WPP_RECORDER_SF_sDqd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v16,
        10,
        v17,
        (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
        BytesRead,
        CallbackRoutine,
        CallbackContext);
    }
  }
LABEL_19:
  FltFreePoolAlignedWithTag(a4, Buffer, 0x62654357u);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140017b48  mov     [rsp-38h+arg_18], rbx
0x140017b4d  mov     [rsp-38h+FileObject], rdx
0x140017b52  mov     [rsp-38h+InitiatingInstance], rcx
0x140017b57  push    rbp
0x140017b58  push    rsi
0x140017b59  push    rdi
0x140017b5a  push    r12
0x140017b5c  push    r13
0x140017b5e  push    r14
0x140017b60  push    r15
0x140017b62  mov     rbp, rsp
0x140017b65  sub     rsp, 60h
0x140017b69  xor     r15d, r15d
0x140017b6c  mov     edi, 1000000h
0x140017b71  mov     qword ptr [rbp+ByteOffset], r15
0x140017b75  mov     r14, r9
0x140017b78  mov     [rbp+Length], r15d
0x140017b7c  mov     rsi, r8
0x140017b7f  mov     [rbp+BytesWritten], r15d
0x140017b83  cmp     r8, rdi
0x140017b86  jge     short loc_140017B95
0x140017b88  lea     edi, [r8+0FFFh]
0x140017b8f  and     edi, 0FFFFF000h
0x140017b95  mov     r8d, edi; NumberOfBytes
0x140017b98  mov     edx, 200h; PoolType
0x140017b9d  mov     r9d, 62654357h; Tag
0x140017ba3  mov     rcx, r14; Instance
0x140017ba6  call    cs:__imp_FltAllocatePoolAlignedWithTag
0x140017bad  nop     dword ptr [rax+rax+00h]
0x140017bb2  mov     r13, rax
0x140017bb5  test    rax, rax
0x140017bb8  jnz     short loc_140017BC4
0x140017bba  mov     eax, 0C000009Ah
0x140017bbf  jmp     loc_140017D79
0x140017bc4  neg     [rbp+arg_28]
0x140017bc7  mov     ebx, r15d
0x140017bca  mov     qword ptr [rbp+ByteOffset], r15
0x140017bce  mov     r12, rsi
0x140017bd1  mov     r15, [rbp+arg_20]
0x140017bd5  sbb     eax, eax
0x140017bd7  add     eax, 5
0x140017bda  mov     [rbp+var_C], eax
0x140017bdd  test    r12, r12
0x140017be0  jz      loc_140017CE7
0x140017be6  mov     rdx, [rbp+FileObject]; FileObject
0x140017bea  lea     rcx, [rbp+Length]
0x140017bee  mov     qword ptr [rsp+60h+CallbackContext], 0; CallbackContext
0x140017bf7  lea     r8, [rbp+ByteOffset]; ByteOffset
0x140017bfb  mov     [rsp+60h+CallbackRoutine], 0; CallbackRoutine
0x140017c04  mov     r9d, edi; Length
0x140017c07  mov     [rsp+60h+BytesRead], rcx; BytesRead
0x140017c0c  mov     rcx, [rbp+InitiatingInstance]; InitiatingInstance
0x140017c10  mov     [rsp+60h+Flags], eax; Flags
0x140017c14  mov     [rsp+60h+Buffer], r13; Buffer
0x140017c19  call    cs:__imp_FltReadFile
0x140017c20  nop     dword ptr [rax+rax+00h]
0x140017c25  mov     ebx, eax
0x140017c27  test    eax, eax
0x140017c29  js      loc_140017CB6
0x140017c2f  mov     r9d, [rbp+Length]; Length
0x140017c33  lea     rax, [rbp+BytesWritten]
0x140017c37  mov     qword ptr [rsp+60h+CallbackContext], 0; CallbackContext
0x140017c40  lea     r8, [rbp+ByteOffset]; ByteOffset
0x140017c44  mov     [rsp+60h+CallbackRoutine], 0; CallbackRoutine
0x140017c4d  mov     rdx, r15; FileObject
0x140017c50  mov     [rsp+60h+BytesRead], rax; BytesWritten
0x140017c55  mov     rcx, r14; InitiatingInstance
0x140017c58  mov     [rsp+60h+Flags], 5; Flags
0x140017c60  mov     [rsp+60h+Buffer], r13; Buffer
0x140017c65  call    cs:__imp_FltWriteFile
0x140017c6c  nop     dword ptr [rax+rax+00h]
0x140017c71  mov     ebx, eax
0x140017c73  test    eax, eax
0x140017c75  js      short loc_140017C89
0x140017c77  mov     eax, [rbp+Length]
0x140017c7a  sub     r12, rax
0x140017c7d  add     qword ptr [rbp+ByteOffset], rax
0x140017c81  mov     eax, [rbp+var_C]
0x140017c84  jmp     loc_140017BDD
0x140017c89  lea     rax, WPP_RECORDER_INITIALIZED
0x140017c90  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017c97  jz      loc_140017D5F
0x140017c9d  mov     dword ptr [rsp+60h+CallbackContext], ebx
0x140017ca1  mov     r9d, 0Eh
0x140017ca7  mov     [rsp+60h+CallbackRoutine], r15
0x140017cac  mov     dword ptr [rsp+60h+BytesRead], 331h
0x140017cb4  jmp     short loc_140017D2F
0x140017cb6  lea     rax, WPP_RECORDER_INITIALIZED
0x140017cbd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017cc4  jz      loc_140017D5F
0x140017cca  mov     rax, [rbp+FileObject]
0x140017cce  mov     r9d, 0Dh
0x140017cd4  mov     dword ptr [rsp+60h+CallbackContext], ebx
0x140017cd8  mov     [rsp+60h+CallbackRoutine], rax
0x140017cdd  mov     dword ptr [rsp+60h+BytesRead], 315h
0x140017ce5  jmp     short loc_140017D2F
0x140017ce7  cmp     rsi, 1000h
0x140017cee  jge     short loc_140017D5F
0x140017cf0  mov     rdx, r15; FileObject
0x140017cf3  mov     rcx, r14; Instance
0x140017cf6  call    cs:__imp_FltFlushBuffers
0x140017cfd  nop     dword ptr [rax+rax+00h]
0x140017d02  mov     ebx, eax
0x140017d04  test    eax, eax
0x140017d06  jns     short loc_140017D5F
0x140017d08  lea     rax, WPP_RECORDER_INITIALIZED
0x140017d0f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017d16  jz      short loc_140017D5F
0x140017d18  mov     dword ptr [rsp+60h+CallbackContext], ebx
0x140017d1c  mov     r9d, 0Fh
0x140017d22  mov     [rsp+60h+CallbackRoutine], r15
0x140017d27  mov     dword ptr [rsp+60h+BytesRead], 349h
0x140017d2f  mov     rcx, cs:wil_details_featureDescriptors_a
0x140017d36  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x140017d3d  mov     qword ptr [rsp+60h+Flags], rax
0x140017d42  mov     r8d, 0Ah
0x140017d48  lea     rax, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x140017d4f  mov     dl, 4
0x140017d51  mov     [rsp+60h+Buffer], rax
0x140017d56  mov     rcx, [rcx+40h]
0x140017d5a  call    WPP_RECORDER_SF_sDqd
0x140017d5f  mov     r8d, 62654357h; Tag
0x140017d65  mov     rdx, r13; Buffer
0x140017d68  mov     rcx, r14; Instance
0x140017d6b  call    cs:__imp_FltFreePoolAlignedWithTag
0x140017d72  nop     dword ptr [rax+rax+00h]
0x140017d77  mov     eax, ebx
0x140017d79  mov     rbx, [rsp+60h+arg_18]
0x140017d81  add     rsp, 60h
0x140017d85  pop     r15
0x140017d87  pop     r14
0x140017d89  pop     r13
0x140017d8b  pop     r12
0x140017d8d  pop     rdi
0x140017d8e  pop     rsi
0x140017d8f  pop     rbp
0x140017d90  retn
```

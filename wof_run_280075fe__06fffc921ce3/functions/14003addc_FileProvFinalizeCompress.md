# FileProvFinalizeCompress

- ea: `0x14003addc`
- end: `0x14003b072`
- name: `FileProvFinalizeCompress`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14003a4d8`

## callees

- `0x14000d158`
- `0x14000d354`
- `0x14003addc`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14003ae9c`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003ae9c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003af37`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003af37`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003afc2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003b04f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003afc2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003b04f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003afa1`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003afa1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b00f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b00f`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b029`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b039`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b029`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b039`
- `FLTMGR!FltWriteFile` at `0x14003ae6f`
- `FLTMGR!FltWriteFile` at `0x14003ae6f`

## pseudocode

```c
__int64 __fastcall FileProvFinalizeCompress(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // edi
  bool v6; // zf
  _DWORD *v7; // r14
  ULONG v8; // esi
  NTSTATUS v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // edx
  unsigned int i; // esi
  __int64 v14; // r14
  __int64 v15; // rbp
  __int64 v16; // rcx
  void *v17; // rdx
  unsigned int v18; // esi
  __int64 v19; // r14
  __int64 v20; // rbp
  union _LARGE_INTEGER Interval; // [rsp+88h] [rbp+10h] BYREF
  ULONG BytesWritten; // [rsp+90h] [rbp+18h] BYREF

  BytesWritten = 0;
  v3 = a3;
  if ( (int)a3 >= 0 )
  {
    v6 = *(_BYTE *)(a2 + 60) == 0;
    v7 = (_DWORD *)(a2 + 296);
    *(_QWORD *)(a2 + 40) = 0;
    v8 = v6 ? *(_DWORD *)(a2 + 108) : (*v7 + 4095) & 0xFFFFF000;
    while ( 1 )
    {
      v9 = FltWriteFile(
             *(PFLT_INSTANCE *)(a2 + 64),
             *(PFILE_OBJECT *)(a2 + 72),
             (PLARGE_INTEGER)(a2 + 40),
             v8,
             *(PVOID *)(a2 + 96),
             0xFu,
             &BytesWritten,
             0,
             0);
      v3 = v9;
      if ( v9 != -1073741740 )
        break;
      Interval.QuadPart = -100000;
      KeDelayExecutionThread(0, 1u, &Interval);
    }
    if ( v9 >= 0 )
    {
      v3 = 51314691;
      v10 = *(_QWORD *)(a1 + 8);
      *(_QWORD *)(a1 + 16) = *(_QWORD *)v7;
      a3 = -(__int64)**(unsigned int **)(a1 + 24);
      if ( (a3 & (*(_QWORD *)v7 + (unsigned __int64)**(unsigned int **)(a1 + 24) - 1)) >= (a3
                                                                                         & ((unsigned __int64)**(unsigned int **)(a1 + 24)
                                                                                          + v10
                                                                                          - 1)) )
        v3 = -1073740689;
    }
  }
  if ( a2 )
  {
    if ( *(_QWORD *)(a2 + 232) )
    {
      if ( *(_DWORD *)(a2 + 256) )
      {
        do
        {
          v11 = *(_QWORD *)(a2 + 232) + 136LL * *(unsigned int *)(a2 + 248);
          *(_QWORD *)(a2 + 240) = v11;
          KeWaitForSingleObject((PVOID)(v11 + 96), Executive, 0, 0, 0);
          v12 = (unsigned int)(*(_DWORD *)(a2 + 248) + 1) % *(_DWORD *)(a2 + 52);
          v6 = (*(_DWORD *)(a2 + 256))-- == 1;
          *(_DWORD *)(a2 + 248) = v12;
        }
        while ( !v6 );
      }
      for ( i = 0; i < *(_DWORD *)(a2 + 52); ++i )
      {
        v14 = *(_QWORD *)(a2 + 232);
        v15 = 136LL * i;
        v16 = *(_QWORD *)(v14 + v15 + 120);
        if ( v16 && *(_BYTE *)(v16 + 17348) )
          LZX_EncodeFree();
        v17 = *(void **)(v14 + v15 + 80);
        if ( v17 )
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(*(_QWORD *)(v14 + v15 + 40) + 64LL), v17);
      }
      ExFreeToNPagedLookasideList(&FileProvCompressWorkitemsLookaside, *(PVOID *)(a2 + 232));
    }
    v18 = 0;
    v19 = 0;
    do
    {
      v20 = v19 << 6;
      if ( *(_QWORD *)(a2 + (v19 << 6) + 96) )
      {
        if ( v18 != *(_DWORD *)(a2 + 224) )
        {
          LOBYTE(a3) = v3 > -1;
          FileProvWaitForWriteComplete(a2, v18, a3);
          if ( *(int *)(a2 + v20 + 112) < 0 && v3 >= 0 )
            v3 = *(_DWORD *)(a2 + v20 + 112);
        }
        ExFreePoolWithTag(*(PVOID *)(a2 + v20 + 96), 0);
      }
      ++v18;
      ++v19;
    }
    while ( v18 < 2 );
    ObfDereferenceObject(*(PVOID *)(a2 + 72));
    ObfDereferenceObject(*(PVOID *)(a2 + 80));
    ExFreeToNPagedLookasideList(&FileProvCompressContextLookaside, (PVOID)a2);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14003addc  mov     rax, rsp
0x14003addf  mov     [rax+8], rbx
0x14003ade3  push    rbp
0x14003ade4  push    rsi
0x14003ade5  push    rdi
0x14003ade6  push    r14
0x14003ade8  push    r15
0x14003adea  sub     rsp, 50h
0x14003adee  mov     dword ptr [rax+18h], 0
0x14003adf5  mov     edi, r8d
0x14003adf8  mov     rbx, rdx
0x14003adfb  mov     rbp, rcx
0x14003adfe  test    r8d, r8d
0x14003ae01  js      loc_14003AEE7
0x14003ae07  cmp     byte ptr [rdx+3Ch], 0
0x14003ae0b  lea     r14, [rdx+128h]
0x14003ae12  mov     qword ptr [rdx+28h], 0
0x14003ae1a  jz      short loc_14003AE2D
0x14003ae1c  mov     esi, [r14]
0x14003ae1f  add     esi, 0FFFh
0x14003ae25  and     esi, 0FFFFF000h
0x14003ae2b  jmp     short loc_14003AE30
0x14003ae2d  mov     esi, [rdx+6Ch]
0x14003ae30  mov     rdx, [rbx+48h]; FileObject
0x14003ae34  lea     rax, [rsp+78h+arg_10]
0x14003ae3c  mov     rcx, [rbx+40h]; InitiatingInstance
0x14003ae40  lea     r8, [rbx+28h]; ByteOffset
0x14003ae44  mov     [rsp+78h+CallbackContext], 0; CallbackContext
0x14003ae4d  mov     r9d, esi; Length
0x14003ae50  mov     [rsp+78h+CallbackRoutine], 0; CallbackRoutine
0x14003ae59  mov     [rsp+78h+BytesWritten], rax; BytesWritten
0x14003ae5e  mov     rax, [rbx+60h]
0x14003ae62  mov     [rsp+78h+Flags], 0Fh; Flags
0x14003ae6a  mov     [rsp+78h+Buffer], rax; Buffer
0x14003ae6f  call    cs:__imp_FltWriteFile
0x14003ae76  nop     dword ptr [rax+rax+00h]
0x14003ae7b  mov     edi, eax
0x14003ae7d  cmp     eax, 0C0000054h
0x14003ae82  jnz     short loc_14003AEAA
0x14003ae84  lea     r8, [rsp+78h+Interval]; Interval
0x14003ae8c  mov     qword ptr [rsp+78h+Interval], 0FFFFFFFFFFFE7960h
0x14003ae98  mov     dl, 1; Alertable
0x14003ae9a  xor     ecx, ecx; WaitMode
0x14003ae9c  call    cs:__imp_KeDelayExecutionThread
0x14003aea3  nop     dword ptr [rax+rax+00h]
0x14003aea8  jmp     short loc_14003AE30
0x14003aeaa  test    eax, eax
0x14003aeac  js      short loc_14003AEE7
0x14003aeae  mov     rax, [r14]
0x14003aeb1  mov     edi, 30F0003h
0x14003aeb6  mov     rdx, [rbp+8]
0x14003aeba  mov     [rbp+10h], rax
0x14003aebe  dec     rdx
0x14003aec1  mov     rax, [rbp+18h]
0x14003aec5  mov     ecx, [rax]
0x14003aec7  mov     eax, 0C000046Fh
0x14003aecc  add     rdx, rcx
0x14003aecf  mov     r8d, ecx
0x14003aed2  dec     rcx
0x14003aed5  neg     r8
0x14003aed8  add     rcx, [r14]
0x14003aedb  and     rdx, r8
0x14003aede  and     rcx, r8
0x14003aee1  cmp     rcx, rdx
0x14003aee4  cmovnb  edi, eax
0x14003aee7  test    rbx, rbx
0x14003aeea  jz      loc_14003B05B
0x14003aef0  cmp     qword ptr [rbx+0E8h], 0
0x14003aef8  jz      loc_14003AFCE
0x14003aefe  cmp     dword ptr [rbx+100h], 0
0x14003af05  jbe     short loc_14003AF5F
0x14003af07  mov     eax, [rbx+0F8h]
0x14003af0d  xor     r9d, r9d; Alertable
0x14003af10  imul    rcx, rax, 88h
0x14003af17  xor     r8d, r8d; WaitMode
0x14003af1a  mov     [rsp+78h+Buffer], 0; Timeout
0x14003af23  add     rcx, [rbx+0E8h]
0x14003af2a  xor     edx, edx; WaitReason
0x14003af2c  mov     [rbx+0F0h], rcx
0x14003af33  add     rcx, 60h ; '`'; Object
0x14003af37  call    cs:__imp_KeWaitForSingleObject
0x14003af3e  nop     dword ptr [rax+rax+00h]
0x14003af43  mov     eax, [rbx+0F8h]
0x14003af49  xor     edx, edx
0x14003af4b  inc     eax
0x14003af4d  div     dword ptr [rbx+34h]
0x14003af50  sub     dword ptr [rbx+100h], 1
0x14003af57  mov     [rbx+0F8h], edx
0x14003af5d  jnz     short loc_14003AF07
0x14003af5f  xor     esi, esi
0x14003af61  cmp     [rbx+34h], esi
0x14003af64  jbe     short loc_14003AFB4
0x14003af66  mov     r14, [rbx+0E8h]
0x14003af6d  mov     eax, esi
0x14003af6f  imul    rbp, rax, 88h
0x14003af76  mov     rcx, [r14+rbp+78h]
0x14003af7b  test    rcx, rcx
0x14003af7e  jz      short loc_14003AF8E
0x14003af80  cmp     byte ptr [rcx+43C4h], 0
0x14003af87  jz      short loc_14003AF8E
0x14003af89  call    LZX_EncodeFree
0x14003af8e  mov     rdx, [r14+rbp+50h]; Entry
0x14003af93  test    rdx, rdx
0x14003af96  jz      short loc_14003AFAD
0x14003af98  mov     rcx, [r14+rbp+28h]
0x14003af9d  add     rcx, 40h ; '@'; Lookaside
0x14003afa1  call    cs:__imp_ExFreeToPagedLookasideList
0x14003afa8  nop     dword ptr [rax+rax+00h]
0x14003afad  inc     esi
0x14003afaf  cmp     esi, [rbx+34h]
0x14003afb2  jb      short loc_14003AF66
0x14003afb4  mov     rdx, [rbx+0E8h]; Entry
0x14003afbb  lea     rcx, FileProvCompressWorkitemsLookaside; Lookaside
0x14003afc2  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003afc9  nop     dword ptr [rax+rax+00h]
0x14003afce  xor     esi, esi
0x14003afd0  xor     r14d, r14d
0x14003afd3  mov     rbp, r14
0x14003afd6  shl     rbp, 6
0x14003afda  cmp     qword ptr [rbx+rbp+60h], 0
0x14003afe0  jz      short loc_14003B01B
0x14003afe2  cmp     esi, [rbx+0E0h]
0x14003afe8  jz      short loc_14003B008
0x14003afea  cmp     edi, 0FFFFFFFFh
0x14003afed  mov     edx, esi
0x14003afef  mov     rcx, rbx
0x14003aff2  setnle  r8b
0x14003aff6  call    FileProvWaitForWriteComplete
0x14003affb  mov     eax, [rbx+rbp+70h]
0x14003afff  test    eax, eax
0x14003b001  jns     short loc_14003B008
0x14003b003  test    edi, edi
0x14003b005  cmovns  edi, eax
0x14003b008  mov     rcx, [rbx+rbp+60h]; P
0x14003b00d  xor     edx, edx; Tag
0x14003b00f  call    cs:__imp_ExFreePoolWithTag
0x14003b016  nop     dword ptr [rax+rax+00h]
0x14003b01b  inc     esi
0x14003b01d  inc     r14
0x14003b020  cmp     esi, 2
0x14003b023  jb      short loc_14003AFD3
0x14003b025  mov     rcx, [rbx+48h]; Object
0x14003b029  call    cs:__imp_ObfDereferenceObject
0x14003b030  nop     dword ptr [rax+rax+00h]
0x14003b035  mov     rcx, [rbx+50h]; Object
0x14003b039  call    cs:__imp_ObfDereferenceObject
0x14003b040  nop     dword ptr [rax+rax+00h]
0x14003b045  mov     rdx, rbx; Entry
0x14003b048  lea     rcx, FileProvCompressContextLookaside; Lookaside
0x14003b04f  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003b056  nop     dword ptr [rax+rax+00h]
0x14003b05b  mov     rbx, [rsp+78h+arg_0]
0x14003b063  mov     eax, edi
0x14003b065  add     rsp, 50h
0x14003b069  pop     r15
0x14003b06b  pop     r14
0x14003b06d  pop     rdi
0x14003b06e  pop     rsi
0x14003b06f  pop     rbp
0x14003b070  retn
```

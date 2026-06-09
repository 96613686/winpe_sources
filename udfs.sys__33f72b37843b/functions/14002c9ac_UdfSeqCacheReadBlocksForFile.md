# UdfSeqCacheReadBlocksForFile

- ea: `0x14002c9ac`
- end: `0x14002cc97`
- name: `UdfSeqCacheReadBlocksForFile`
- size: `747`
- prototype: `__int64 __fastcall(int, int, int, int, void *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140046d70`

## callees

- `0x140009f60`
- `0x14000bf00`
- `0x14000ca10`
- `0x14001bd80`
- `0x14001c080`
- `0x14002c9ac`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14002cc72`
- `ntoskrnl!ExRaiseStatus` at `0x14002cc8a`
- `ntoskrnl!ExRaiseStatus` at `0x14002cc72`
- `ntoskrnl!ExRaiseStatus` at `0x14002cc8a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002ca4a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002ca4a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cadd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002caec`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cb70`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cba2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cbe3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cc0d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cc1c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cc60`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cadd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002caec`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cb70`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cba2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cbe3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cc0d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cc1c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002cc60`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002cb91`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002cb91`

## pseudocode

```c
char __fastcall UdfSeqCacheReadBlocksForFile(__int64 a1, __int64 a2, int a3, int a4, void *a5, _DWORD *a6)
{
  __int64 v6; // rdi
  __int64 v7; // r12
  __int64 v10; // rsi
  bool v11; // zf
  int v12; // ebx
  __int64 v13; // r8
  char Data; // al
  int v15; // r12d
  const void *v16; // rbx
  NTSTATUS v18; // ebx
  int v19; // [rsp+30h] [rbp-49h] BYREF
  _DWORD v20[3]; // [rsp+34h] [rbp-45h] BYREF
  _QWORD v21[16]; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v22; // [rsp+D0h] [rbp+57h] BYREF
  __int64 v23; // [rsp+D8h] [rbp+5Fh]
  int v24; // [rsp+E0h] [rbp+67h]
  char v25; // [rsp+E8h] [rbp+6Fh]

  v24 = a3;
  v23 = a2;
  v6 = *(_QWORD *)(a1 + 16);
  v7 = a2;
  v10 = *(_QWORD *)(v6 + 104);
  memset(v21, 0, 0x40u);
  v11 = (*(_DWORD *)(v6 + 48) & 0x20000000) == 0;
  v22 = 0;
  v20[0] = 0;
  v19 = a4;
  if ( !v11 )
  {
    if ( v7 == *(_QWORD *)(v6 + 320) || v7 == *(_QWORD *)(v6 + 272) )
    {
      v10 = *(_QWORD *)(v6 + 112);
    }
    else if ( v7 == *(_QWORD *)(v6 + 328) )
    {
      v10 = *(_QWORD *)(v6 + 120);
    }
    else
    {
      v10 = *(_QWORD *)(v6 + 104);
    }
  }
  v12 = v24;
  while ( 1 )
  {
    if ( !ExAcquireResourceSharedLite((PERESOURCE)(v10 + 344), (*(_DWORD *)(a1 + 28) & 4) != 0) )
    {
      *(_DWORD *)(a1 + 24) = -1073741608;
      ExRaiseStatus(-1073741608);
    }
    if ( (*(_DWORD *)(*(_QWORD *)(v6 + 104) + 4LL) & 0x10) != 0 )
    {
      v18 = -1073741248;
LABEL_26:
      ExReleaseResourceLite((PERESOURCE)(v10 + 344));
      *(_DWORD *)(a1 + 24) = v18;
      ExRaiseStatus(v18);
    }
    v13 = *(_DWORD *)(a1 + 28) >> 2;
    LOBYTE(v13) = (*(_DWORD *)(a1 + 28) & 4) == 0;
    if ( !(unsigned __int8)UdfAcquireResource(a1, v10 + 448, v13, 1) )
    {
      v18 = -1073741608;
      goto LABEL_26;
    }
    Data = UdfSeqCacheFindData(v10, v7, v12, (unsigned int)&v19, (__int64)&v22, (__int64)v20);
    v15 = v19;
    v25 = Data;
    if ( !Data )
    {
      ExReleaseResourceLite((PERESOURCE)(v10 + 448));
      goto LABEL_23;
    }
    if ( v22 != -1 )
      break;
    ExReleaseResourceLite((PERESOURCE)(v10 + 448));
    ExReleaseResourceLite((PERESOURCE)(v10 + 344));
    UdfAcquireResource(a1, v10 + 448, 0, 0);
    if ( *(_DWORD *)(v10 + 704) )
    {
      UdfSeqCacheInsertFlushWaitBlock(v10, v21, *(unsigned int *)(v10 + 640));
      LOBYTE(v21[7]) = 1;
      v21[6] = 0;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          17,
          WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
      }
      ExReleaseResourceLite((PERESOURCE)(v10 + 448));
      KeWaitForSingleObject(&v21[2], Executive, 0, 0, 0);
    }
    else
    {
      ExReleaseResourceLite((PERESOURCE)(v10 + 448));
    }
    LODWORD(v7) = v23;
  }
  v16 = (const void *)(*(_QWORD *)(v10 + 40LL * v22 + 40)
                     + (unsigned int)((v20[0]
                                     - *(_DWORD *)(32LL * v20[0] + *(_QWORD *)(v10 + 40LL * v22 + 56) + 16)
                                     + v12) << *(_DWORD *)(*(_QWORD *)(a1 + 16) + 72LL)));
  ExReleaseResourceLite((PERESOURCE)(v10 + 448));
  memmove(a5, v16, (unsigned int)(v15 << *(_DWORD *)(*(_QWORD *)(a1 + 16) + 72LL)));
LABEL_23:
  ExReleaseResourceLite((PERESOURCE)(v10 + 344));
  *a6 = v15 << *(_DWORD *)(*(_QWORD *)(a1 + 16) + 72LL);
  return v25;
}

```

## disassembly

```asm
0x14002c9ac  mov     [rsp-8+arg_10], r8d
0x14002c9b1  mov     [rsp-8+arg_8], rdx
0x14002c9b6  push    rbp
0x14002c9b7  push    rbx
0x14002c9b8  push    rsi
0x14002c9b9  push    rdi
0x14002c9ba  push    r12
0x14002c9bc  push    r13
0x14002c9be  push    r14
0x14002c9c0  push    r15
0x14002c9c2  lea     rbp, [rsp-0Fh]
0x14002c9c7  sub     rsp, 88h
0x14002c9ce  mov     rdi, [rcx+10h]
0x14002c9d2  mov     r12, rdx
0x14002c9d5  xor     edx, edx; Val
0x14002c9d7  mov     r14, rcx
0x14002c9da  lea     rcx, [rbp+47h+var_80]; void *
0x14002c9de  mov     ebx, r9d
0x14002c9e1  mov     rsi, [rdi+68h]
0x14002c9e5  lea     r8d, [rdx+40h]; Size
0x14002c9e9  call    memset
0x14002c9ee  test    dword ptr [rdi+30h], 20000000h
0x14002c9f5  mov     [rbp+47h+arg_0], 0
0x14002c9fc  mov     [rbp+47h+var_8C], 0
0x14002ca03  mov     [rbp+47h+var_90], ebx
0x14002ca06  jz      short loc_14002CA33
0x14002ca08  cmp     r12, [rdi+140h]
0x14002ca0f  jz      short loc_14002CA2F
0x14002ca11  cmp     r12, [rdi+110h]
0x14002ca18  jz      short loc_14002CA2F
0x14002ca1a  cmp     r12, [rdi+148h]
0x14002ca21  jnz     short loc_14002CA29
0x14002ca23  mov     rsi, [rdi+78h]
0x14002ca27  jmp     short loc_14002CA33
0x14002ca29  mov     rsi, [rdi+68h]
0x14002ca2d  jmp     short loc_14002CA33
0x14002ca2f  mov     rsi, [rdi+70h]
0x14002ca33  mov     ebx, [rbp+47h+arg_10]
0x14002ca36  lea     r13, [rsi+158h]
0x14002ca3d  mov     edx, [r14+1Ch]
0x14002ca41  mov     rcx, r13; Resource
0x14002ca44  shr     edx, 2
0x14002ca47  and     dl, 1; Wait
0x14002ca4a  call    cs:__imp_ExAcquireResourceSharedLite
0x14002ca51  nop     dword ptr [rax+rax+00h]
0x14002ca56  test    al, al
0x14002ca58  jz      loc_14002CC7F
0x14002ca5e  mov     rax, [rdi+68h]
0x14002ca62  mov     ecx, [rax+4]
0x14002ca65  and     ecx, 10h
0x14002ca68  test    ecx, ecx
0x14002ca6a  jnz     loc_14002CC58
0x14002ca70  mov     r8d, [r14+1Ch]
0x14002ca74  lea     r9d, [rcx+1]
0x14002ca78  shr     r8d, 2
0x14002ca7c  lea     r15, [rsi+1C0h]
0x14002ca83  not     r8b
0x14002ca86  mov     rdx, r15
0x14002ca89  and     r8b, 1
0x14002ca8d  mov     rcx, r14
0x14002ca90  call    UdfAcquireResource
0x14002ca95  test    al, al
0x14002ca97  jz      loc_14002CC51
0x14002ca9d  lea     rax, [rbp+47h+var_8C]
0x14002caa1  mov     r8d, ebx
0x14002caa4  mov     [rsp+0C0h+var_98], rax
0x14002caa9  lea     r9, [rbp+47h+var_90]
0x14002caad  lea     rax, [rbp+47h+arg_0]
0x14002cab1  mov     rdx, r12
0x14002cab4  mov     rcx, rsi
0x14002cab7  mov     [rsp+0C0h+Timeout], rax
0x14002cabc  call    UdfSeqCacheFindData
0x14002cac1  mov     r12d, [rbp+47h+var_90]
0x14002cac5  mov     [rbp+47h+arg_18], al
0x14002cac8  test    al, al
0x14002caca  jz      loc_14002CC0A
0x14002cad0  cmp     [rbp+47h+arg_0], 0FFFFFFFFh
0x14002cad4  jnz     loc_14002CBB7
0x14002cada  mov     rcx, r15; Resource
0x14002cadd  call    cs:__imp_ExReleaseResourceLite
0x14002cae4  nop     dword ptr [rax+rax+00h]
0x14002cae9  mov     rcx, r13; Resource
0x14002caec  call    cs:__imp_ExReleaseResourceLite
0x14002caf3  nop     dword ptr [rax+rax+00h]
0x14002caf8  xor     r9d, r9d
0x14002cafb  xor     r8d, r8d
0x14002cafe  mov     rdx, r15
0x14002cb01  mov     rcx, r14
0x14002cb04  call    UdfAcquireResource
0x14002cb09  cmp     dword ptr [rsi+2C0h], 0
0x14002cb10  jz      loc_14002CB9F
0x14002cb16  mov     r8d, [rsi+280h]
0x14002cb1d  lea     rdx, [rbp+47h+var_80]
0x14002cb21  mov     rcx, rsi
0x14002cb24  call    UdfSeqCacheInsertFlushWaitBlock
0x14002cb29  mov     [rbp+47h+var_48], 1
0x14002cb2d  mov     [rbp+47h+var_50], 0
0x14002cb35  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cb3c  lea     rax, WPP_GLOBAL_Control
0x14002cb43  cmp     rcx, rax
0x14002cb46  jz      short loc_14002CB6D
0x14002cb48  test    dword ptr [rcx+2Ch], 20000000h
0x14002cb4f  jz      short loc_14002CB6D
0x14002cb51  mov     r9d, [rsi+280h]
0x14002cb58  lea     r8, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids
0x14002cb5f  mov     rcx, [rcx+18h]
0x14002cb63  mov     edx, 11h
0x14002cb68  call    WPP_SF_d
0x14002cb6d  mov     rcx, r15; Resource
0x14002cb70  call    cs:__imp_ExReleaseResourceLite
0x14002cb77  nop     dword ptr [rax+rax+00h]
0x14002cb7c  xor     r9d, r9d; Alertable
0x14002cb7f  mov     [rsp+0C0h+Timeout], 0; Timeout
0x14002cb88  xor     r8d, r8d; WaitMode
0x14002cb8b  lea     rcx, [rbp+47h+Object]; Object
0x14002cb8f  xor     edx, edx; WaitReason
0x14002cb91  call    cs:__imp_KeWaitForSingleObject
0x14002cb98  nop     dword ptr [rax+rax+00h]
0x14002cb9d  jmp     short loc_14002CBAE
0x14002cb9f  mov     rcx, r15; Resource
0x14002cba2  call    cs:__imp_ExReleaseResourceLite
0x14002cba9  nop     dword ptr [rax+rax+00h]
0x14002cbae  mov     r12, [rbp+47h+arg_8]
0x14002cbb2  jmp     loc_14002CA3D
0x14002cbb7  mov     edx, [rbp+47h+var_8C]
0x14002cbba  mov     eax, [rbp+47h+arg_0]
0x14002cbbd  mov     ecx, edx
0x14002cbbf  shl     rcx, 5
0x14002cbc3  lea     r8, [rax+rax*4]
0x14002cbc7  mov     rax, [rsi+r8*8+38h]
0x14002cbcc  sub     edx, [rcx+rax+10h]
0x14002cbd0  mov     rcx, [r14+10h]
0x14002cbd4  add     ebx, edx
0x14002cbd6  mov     ecx, [rcx+48h]
0x14002cbd9  shl     ebx, cl
0x14002cbdb  mov     rcx, r15; Resource
0x14002cbde  add     rbx, [rsi+r8*8+28h]
0x14002cbe3  call    cs:__imp_ExReleaseResourceLite
0x14002cbea  nop     dword ptr [rax+rax+00h]
0x14002cbef  mov     rcx, [r14+10h]
0x14002cbf3  mov     r8d, r12d
0x14002cbf6  mov     rdx, rbx; Src
0x14002cbf9  mov     ecx, [rcx+48h]
0x14002cbfc  shl     r8d, cl; Size
0x14002cbff  mov     rcx, [rbp+47h+arg_20]; void *
0x14002cc03  call    memmove
0x14002cc08  jmp     short loc_14002CC19
0x14002cc0a  mov     rcx, r15; Resource
0x14002cc0d  call    cs:__imp_ExReleaseResourceLite
0x14002cc14  nop     dword ptr [rax+rax+00h]
0x14002cc19  mov     rcx, r13; Resource
0x14002cc1c  call    cs:__imp_ExReleaseResourceLite
0x14002cc23  nop     dword ptr [rax+rax+00h]
0x14002cc28  mov     rax, [rbp+47h+arg_28]
0x14002cc2c  mov     rcx, [r14+10h]
0x14002cc30  mov     ecx, [rcx+48h]
0x14002cc33  shl     r12d, cl
0x14002cc36  mov     [rax], r12d
0x14002cc39  mov     al, [rbp+47h+arg_18]
0x14002cc3c  add     rsp, 88h
0x14002cc43  pop     r15
0x14002cc45  pop     r14
0x14002cc47  pop     r13
0x14002cc49  pop     r12
0x14002cc4b  pop     rdi
0x14002cc4c  pop     rsi
0x14002cc4d  pop     rbx
0x14002cc4e  pop     rbp
0x14002cc4f  retn
0x14002cc51  mov     ebx, 0C00000D8h
0x14002cc56  jmp     short loc_14002CC5D
0x14002cc58  mov     ebx, 0C0000240h
0x14002cc5d  mov     rcx, r13; Resource
0x14002cc60  call    cs:__imp_ExReleaseResourceLite
0x14002cc67  nop     dword ptr [rax+rax+00h]
0x14002cc6c  mov     ecx, ebx; Status
0x14002cc6e  mov     [r14+18h], ebx
0x14002cc72  call    cs:__imp_ExRaiseStatus
0x14002cc7f  mov     ebx, 0C00000D8h
0x14002cc84  mov     ecx, ebx; Status
0x14002cc86  mov     [r14+18h], ebx
0x14002cc8a  call    cs:__imp_ExRaiseStatus
```

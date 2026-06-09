# VhdmpiDeleteVirtualDisk

- ea: `0x1400ce218`
- end: `0x1400ce511`
- name: `VhdmpiDeleteVirtualDisk`
- size: `761`
- prototype: `__int64 __fastcall(struct _VHD_VIRTUAL_DISK *)`
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x140027388`
- `0x1400cf68c`

## callees

- `0x14001f6d8`
- `0x140023560`
- `0x1400270e4`
- `0x1400294cc`
- `0x14002fd08`
- `0x140031cf4`
- `0x1400358bc`
- `0x140035e94`
- `0x140049010`
- `0x140049460`
- `0x1400556dc`
- `0x14005d7c0`
- `0x14009e12c`
- `0x1400a7c58`
- `0x1400ce218`
- `0x1400cff8c`
- `0x1400e768c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce3f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce420`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce471`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce4a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce3f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce420`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce471`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce4a4`

## string_xrefs

- `0x1400ce260`: `VhdmpiDeleteVhdVirtualDisk: enter... VirtualDisk: 0x%p`
- `0x1400ce27d`: `VhdmpiDeleteVirtualDisk`
- `0x1400ce3b3`: `VhdmpiDeleteVirtualDisk`
- `0x1400ce4ed`: `VhdmpiDeleteVirtualDisk`
- `0x1400ce3a2`: `VhdmpiDeleteVirtualDisk: failed to query VHD modification time for log file ... `
- `0x1400ce4d3`: `VhdmpiDeleteVhdVirtualDisk: leaving...`

## pseudocode

```c
void __fastcall VhdmpiDeleteVirtualDisk(struct _VHD_VIRTUAL_DISK *a1)
{
  int v2; // edx
  int v3; // r8d
  __int64 v4; // rax
  const wchar_t *v5; // rax
  unsigned int v6; // edx
  unsigned __int8 v7; // r8
  __int64 v8; // rcx
  struct _VHD_VIRTUAL_DISK **v9; // rcx
  struct _VHD_VIRTUAL_DISK *v10; // rbx
  struct _VHD_VIRTUAL_DISK **v11; // rcx
  struct _VHD_VIRTUAL_DISK *v12; // rbx
  void *v13; // rcx
  int v14; // [rsp+40h] [rbp-48h] BYREF
  __int128 v15; // [rsp+48h] [rbp-40h] BYREF

  v15 = 0;
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
    TraceEvents(
      "VhdmpiDeleteVirtualDisk",
      0xC55u,
      5u,
      0x10u,
      "VhdmpiDeleteVhdVirtualDisk: enter... VirtualDisk: 0x%p",
      a1);
  v14 = 0;
  *((_BYTE *)a1 + 2448) = 1;
  VhdmpiDisableVirtualDiskCachedRundowns(a1);
  DvWaitRundownBarrier((char *)a1 + 2432, 0);
  VhdmpiWaitForMultiTrigerWorkItem((char *)a1 + 1472);
  DvRundownWorkQueue((char *)a1 + 2544);
  if ( *((_QWORD *)a1 + 192) )
  {
    v2 = VhdmpiCTGetVhdFileTimeAndDataWriteGuid(a1, &v14, &v15, 0);
    if ( v2 < 0 )
    {
      if ( (Microsoft_Windows_VHDMPEnableBits & 4) != 0 )
      {
        v4 = *((_QWORD *)a1 + 18);
        if ( v4 )
          v5 = *(const wchar_t **)(v4 + 120);
        else
          v5 = L" ";
        McTemplateK0zzqxx_EtwWriteTransfer(
          *(_DWORD *)(*((_QWORD *)a1 + 192) + 176LL),
          v2,
          v3,
          *(_QWORD *)(*((_QWORD *)a1 + 192) + 32LL),
          (__int64)v5,
          v2,
          1,
          *(_DWORD *)(*((_QWORD *)a1 + 192) + 176LL));
      }
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
        TraceEvents(
          "VhdmpiDeleteVirtualDisk",
          0xCACu,
          v7,
          v6,
          "VhdmpiDeleteVirtualDisk: failed to query VHD modification time for log file ... ");
    }
    else
    {
      *(_DWORD *)(*((_QWORD *)a1 + 192) + 176LL) = v14;
      if ( *(_BYTE *)(*((_QWORD *)a1 + 4) + 52LL) )
        *(_OWORD *)(*((_QWORD *)a1 + 192) + 194LL) = v15;
    }
  }
  v8 = *((_QWORD *)a1 + 18);
  if ( v8 )
  {
    *((_QWORD *)a1 + 18) = 0;
    VhdmpiReleaseBackingStore(v8);
  }
  v9 = (struct _VHD_VIRTUAL_DISK **)*((_QWORD *)a1 + 38);
  if ( v9 != (struct _VHD_VIRTUAL_DISK **)((char *)a1 + 304) )
  {
    do
    {
      v10 = *v9;
      ExFreePoolWithTag(v9, 0x45444856u);
      v9 = (struct _VHD_VIRTUAL_DISK **)v10;
    }
    while ( v10 != (struct _VHD_VIRTUAL_DISK *)((char *)a1 + 304) );
  }
  v11 = (struct _VHD_VIRTUAL_DISK **)*((_QWORD *)a1 + 40);
  if ( v11 != (struct _VHD_VIRTUAL_DISK **)((char *)a1 + 320) )
  {
    do
    {
      v12 = *v11;
      ExFreePoolWithTag(v11, 0x45444856u);
      v11 = (struct _VHD_VIRTUAL_DISK **)v12;
    }
    while ( v12 != (struct _VHD_VIRTUAL_DISK *)((char *)a1 + 320) );
  }
  VhdmpiCleanupLowResourcesQueue((struct _VHD_VIRTUAL_DISK *)((char *)a1 + 904));
  VhdmpiCTLogCleanupTracking(a1);
  VhdmpiTeardownIoTracker((char *)a1 + 384);
  IoPerfFreeEntityData((struct _VHD_VIRTUAL_DISK *)((char *)a1 + 2624));
  v13 = (void *)*((_QWORD *)a1 + 326);
  if ( v13 )
    ExFreePoolWithTag(v13, 0x73646856u);
  if ( (Microsoft_Windows_VHDMPEnableBits & 8) != 0 )
    McTemplateK0p_EtwWriteTransfer(v13, VirtualDiskDestroyed, 0);
  ExFreePoolWithTag(a1, 0x63444856u);
  VhdmpiDecrementDriverUserCount();
  if ( (unsigned int)dword_140087708 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
      TraceEvents("VhdmpiDeleteVirtualDisk", 0xD01u, 5u, 0x10u, "VhdmpiDeleteVhdVirtualDisk: leaving...");
  }
}

```

## disassembly

```asm
0x1400ce218  push    rbx
0x1400ce21a  push    rsi
0x1400ce21b  push    rdi
0x1400ce21c  push    r15
0x1400ce21e  sub     rsp, 68h
0x1400ce222  mov     rax, cs:__security_cookie
0x1400ce229  xor     rax, rsp
0x1400ce22c  mov     [rsp+88h+var_30], rax
0x1400ce231  mov     eax, cs:dword_140087708
0x1400ce237  xorps   xmm0, xmm0
0x1400ce23a  mov     rdi, rcx
0x1400ce23d  mov     r15d, 10h
0x1400ce243  movups  [rsp+88h+var_40], xmm0
0x1400ce248  cmp     eax, 5
0x1400ce24b  jbe     short loc_1400CE289
0x1400ce24d  mov     edx, r15d
0x1400ce250  lea     rcx, dword_140087708
0x1400ce257  call    _tlgKeywordOn
0x1400ce25c  test    al, al
0x1400ce25e  jz      short loc_1400CE289
0x1400ce260  lea     rax, aVhdmpideletevh_2; "VhdmpiDeleteVhdVirtualDisk: enter... Vi"...
0x1400ce267  mov     qword ptr [rsp+88h+var_60], rdi; char
0x1400ce26c  mov     edx, 0C55h; int
0x1400ce271  mov     [rsp+88h+var_68], rax; char *
0x1400ce276  mov     r9d, r15d; int
0x1400ce279  lea     r8d, [r15-0Bh]; int
0x1400ce27d  lea     rcx, aVhdmpideletevi; "VhdmpiDeleteVirtualDisk"
0x1400ce284  call    TraceEvents
0x1400ce289  mov     rcx, rdi
0x1400ce28c  mov     [rsp+88h+var_48], 0
0x1400ce294  mov     byte ptr [rdi+990h], 1
0x1400ce29b  call    VhdmpiDisableVirtualDiskCachedRundowns
0x1400ce2a0  lea     rcx, [rdi+980h]
0x1400ce2a7  xor     edx, edx
0x1400ce2a9  call    DvWaitRundownBarrier
0x1400ce2ae  lea     rcx, [rdi+5C0h]
0x1400ce2b5  call    VhdmpiWaitForMultiTrigerWorkItem
0x1400ce2ba  lea     rcx, [rdi+9F0h]
0x1400ce2c1  call    DvRundownWorkQueue
0x1400ce2c6  cmp     qword ptr [rdi+600h], 0
0x1400ce2ce  jz      loc_1400CE3BF
0x1400ce2d4  xor     r9d, r9d
0x1400ce2d7  lea     r8, [rsp+88h+var_40]
0x1400ce2dc  lea     rdx, [rsp+88h+var_48]
0x1400ce2e1  mov     rcx, rdi
0x1400ce2e4  call    VhdmpiCTGetVhdFileTimeAndDataWriteGuid
0x1400ce2e9  mov     edx, eax
0x1400ce2eb  test    eax, eax
0x1400ce2ed  js      short loc_1400CE327
0x1400ce2ef  mov     eax, [rsp+88h+var_48]
0x1400ce2f3  mov     rcx, [rdi+600h]
0x1400ce2fa  mov     [rcx+0B0h], eax
0x1400ce300  mov     rax, [rdi+20h]
0x1400ce304  cmp     byte ptr [rax+34h], 0
0x1400ce308  jz      loc_1400CE3BF
0x1400ce30e  mov     rax, [rdi+600h]
0x1400ce315  movups  xmm0, [rsp+88h+var_40]
0x1400ce31a  movdqu  xmmword ptr [rax+0C2h], xmm0
0x1400ce322  jmp     loc_1400CE3BF
0x1400ce327  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 4
0x1400ce32e  jz      short loc_1400CE377
0x1400ce330  mov     r9, [rdi+600h]
0x1400ce337  mov     rax, [rdi+90h]
0x1400ce33e  mov     ecx, [r9+0B0h]
0x1400ce345  test    rax, rax
0x1400ce348  jnz     short loc_1400CE353
0x1400ce34a  lea     rax, asc_14006270C; " "
0x1400ce351  jmp     short loc_1400CE357
0x1400ce353  mov     rax, [rax+78h]
0x1400ce357  mov     r9, [r9+20h]
0x1400ce35b  mov     [rsp+88h+var_50], rcx
0x1400ce360  mov     [rsp+88h+var_58], 1
0x1400ce369  mov     dword ptr [rsp+88h+var_60], edx; char
0x1400ce36d  mov     [rsp+88h+var_68], rax
0x1400ce372  call    McTemplateK0zzqxx_EtwWriteTransfer
0x1400ce377  mov     eax, cs:dword_140087708
0x1400ce37d  mov     r8d, 2
0x1400ce383  cmp     eax, r8d
0x1400ce386  jbe     short loc_1400CE3BF
0x1400ce388  mov     edx, 1000h
0x1400ce38d  lea     rcx, dword_140087708
0x1400ce394  call    _tlgKeywordOn
0x1400ce399  test    al, al
0x1400ce39b  jz      short loc_1400CE3BF
0x1400ce39d  mov     ecx, 0CACh
0x1400ce3a2  lea     rax, aVhdmpideletevi_0; "VhdmpiDeleteVirtualDisk: failed to quer"...
0x1400ce3a9  mov     r9d, edx; int
0x1400ce3ac  mov     [rsp+88h+var_68], rax; char *
0x1400ce3b1  mov     edx, ecx; int
0x1400ce3b3  lea     rcx, aVhdmpideletevi; "VhdmpiDeleteVirtualDisk"
0x1400ce3ba  call    TraceEvents
0x1400ce3bf  mov     rcx, [rdi+90h]; char
0x1400ce3c6  test    rcx, rcx
0x1400ce3c9  jz      short loc_1400CE3DE
0x1400ce3cb  mov     rdx, rdi
0x1400ce3ce  mov     qword ptr [rdi+90h], 0
0x1400ce3d9  call    VhdmpiReleaseBackingStore
0x1400ce3de  lea     rsi, [rdi+130h]
0x1400ce3e5  mov     rcx, [rsi]; P
0x1400ce3e8  cmp     rcx, rsi
0x1400ce3eb  jz      short loc_1400CE409
0x1400ce3ed  mov     rbx, [rcx]
0x1400ce3f0  mov     edx, 45444856h; Tag
0x1400ce3f5  call    cs:__imp_ExFreePoolWithTag
0x1400ce3fc  nop     dword ptr [rax+rax+00h]
0x1400ce401  mov     rcx, rbx
0x1400ce404  cmp     rbx, rsi
0x1400ce407  jnz     short loc_1400CE3ED
0x1400ce409  lea     rsi, [rdi+140h]
0x1400ce410  mov     rcx, [rsi]; P
0x1400ce413  cmp     rcx, rsi
0x1400ce416  jz      short loc_1400CE434
0x1400ce418  mov     rbx, [rcx]
0x1400ce41b  mov     edx, 45444856h; Tag
0x1400ce420  call    cs:__imp_ExFreePoolWithTag
0x1400ce427  nop     dword ptr [rax+rax+00h]
0x1400ce42c  mov     rcx, rbx
0x1400ce42f  cmp     rbx, rsi
0x1400ce432  jnz     short loc_1400CE418
0x1400ce434  lea     rcx, [rdi+388h]; struct VHD_LOW_RESOURCES_QUEUE *
0x1400ce43b  call    ?VhdmpiCleanupLowResourcesQueue@@YAXPEAUVHD_LOW_RESOURCES_QUEUE@@@Z; VhdmpiCleanupLowResourcesQueue(VHD_LOW_RESOURCES_QUEUE *)
0x1400ce440  mov     rcx, rdi; struct _VHD_VIRTUAL_DISK *
0x1400ce443  call    VhdmpiCTLogCleanupTracking
0x1400ce448  lea     rcx, [rdi+180h]
0x1400ce44f  call    VhdmpiTeardownIoTracker
0x1400ce454  lea     rcx, [rdi+0A40h]; struct _IO_PERF_ENTITY_DATA *
0x1400ce45b  call    IoPerfFreeEntityData
0x1400ce460  mov     rcx, [rdi+0A30h]; P
0x1400ce467  test    rcx, rcx
0x1400ce46a  jz      short loc_1400CE47D
0x1400ce46c  mov     edx, 73646856h; Tag
0x1400ce471  call    cs:__imp_ExFreePoolWithTag
0x1400ce478  nop     dword ptr [rax+rax+00h]
0x1400ce47d  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 8
0x1400ce484  jz      short loc_1400CE49C
0x1400ce486  mov     r9, [rdi+0B00h]
0x1400ce48d  lea     rdx, VirtualDiskDestroyed
0x1400ce494  xor     r8d, r8d
0x1400ce497  call    McTemplateK0p_EtwWriteTransfer
0x1400ce49c  mov     edx, 63444856h; Tag
0x1400ce4a1  mov     rcx, rdi; P
0x1400ce4a4  call    cs:__imp_ExFreePoolWithTag
0x1400ce4ab  nop     dword ptr [rax+rax+00h]
0x1400ce4b0  call    VhdmpiDecrementDriverUserCount
0x1400ce4b5  mov     edx, cs:dword_140087708
0x1400ce4bb  cmp     edx, 5
0x1400ce4be  jbe     short loc_1400CE4F9
0x1400ce4c0  mov     rdx, r15
0x1400ce4c3  lea     rcx, dword_140087708
0x1400ce4ca  call    _tlgKeywordOn
0x1400ce4cf  test    al, al
0x1400ce4d1  jz      short loc_1400CE4F9
0x1400ce4d3  lea     rax, aVhdmpideletevh; "VhdmpiDeleteVhdVirtualDisk: leaving..."
0x1400ce4da  mov     edx, 0D01h; int
0x1400ce4df  mov     r9d, r15d; int
0x1400ce4e2  mov     [rsp+88h+var_68], rax; char *
0x1400ce4e7  mov     r8d, 5; int
0x1400ce4ed  lea     rcx, aVhdmpideletevi; "VhdmpiDeleteVirtualDisk"
0x1400ce4f4  call    TraceEvents
0x1400ce4f9  mov     rcx, [rsp+88h+var_30]
0x1400ce4fe  xor     rcx, rsp; StackCookie
0x1400ce501  call    __security_check_cookie
0x1400ce506  add     rsp, 68h
0x1400ce50a  pop     r15
0x1400ce50c  pop     rdi
0x1400ce50d  pop     rsi
0x1400ce50e  pop     rbx
0x1400ce50f  retn
```

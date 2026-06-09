# VhdmpiDeleteVirtualDisk

- ea: `0x1400ce1a8`
- end: `0x1400ce4a1`
- name: `VhdmpiDeleteVirtualDisk`
- size: `761`
- prototype: `__int64 __fastcall(struct _VHD_VIRTUAL_DISK *)`
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1400278a8`
- `0x1400cf61c`

## callees

- `0x14001faf8`
- `0x140023980`
- `0x140027608`
- `0x1400299ec`
- `0x1400301c8`
- `0x1400321b4`
- `0x140035cac`
- `0x140036284`
- `0x140049400`
- `0x140049850`
- `0x140055acc`
- `0x14005dbb0`
- `0x14009e12c`
- `0x1400a7c58`
- `0x1400ce1a8`
- `0x1400cff1c`
- `0x1400e761c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce385`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce3b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce401`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce434`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce385`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce3b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce401`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce434`

## string_xrefs

- `0x1400ce463`: `VhdmpiDeleteVhdVirtualDisk: leaving...`
- `0x1400ce1f0`: `VhdmpiDeleteVhdVirtualDisk: enter... VirtualDisk: 0x%p`
- `0x1400ce20d`: `VhdmpiDeleteVirtualDisk`
- `0x1400ce343`: `VhdmpiDeleteVirtualDisk`
- `0x1400ce47d`: `VhdmpiDeleteVirtualDisk`
- `0x1400ce332`: `VhdmpiDeleteVirtualDisk: failed to query VHD modification time for log file ... `

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
  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
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
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
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
    McTemplateK0p_EtwWriteTransfer(v13, VirtualDiskDestroyed, 0, *((_QWORD *)a1 + 352));
  ExFreePoolWithTag(a1, 0x63444856u);
  VhdmpiDecrementDriverUserCount();
  if ( (unsigned int)dword_1400876D0 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
      TraceEvents("VhdmpiDeleteVirtualDisk", 0xD01u, 5u, 0x10u, "VhdmpiDeleteVhdVirtualDisk: leaving...");
  }
}

```

## disassembly

```asm
0x1400ce1a8  push    rbx
0x1400ce1aa  push    rsi
0x1400ce1ab  push    rdi
0x1400ce1ac  push    r15
0x1400ce1ae  sub     rsp, 68h
0x1400ce1b2  mov     rax, cs:__security_cookie
0x1400ce1b9  xor     rax, rsp
0x1400ce1bc  mov     [rsp+88h+var_30], rax
0x1400ce1c1  mov     eax, cs:dword_1400876D0
0x1400ce1c7  xorps   xmm0, xmm0
0x1400ce1ca  mov     rdi, rcx
0x1400ce1cd  mov     r15d, 10h
0x1400ce1d3  movups  [rsp+88h+var_40], xmm0
0x1400ce1d8  cmp     eax, 5
0x1400ce1db  jbe     short loc_1400CE219
0x1400ce1dd  mov     edx, r15d
0x1400ce1e0  lea     rcx, dword_1400876D0
0x1400ce1e7  call    _tlgKeywordOn
0x1400ce1ec  test    al, al
0x1400ce1ee  jz      short loc_1400CE219
0x1400ce1f0  lea     rax, aVhdmpideletevh_2; "VhdmpiDeleteVhdVirtualDisk: enter... Vi"...
0x1400ce1f7  mov     qword ptr [rsp+88h+var_60], rdi; char
0x1400ce1fc  mov     edx, 0C55h; int
0x1400ce201  mov     [rsp+88h+var_68], rax; char *
0x1400ce206  mov     r9d, r15d; int
0x1400ce209  lea     r8d, [r15-0Bh]; int
0x1400ce20d  lea     rcx, aVhdmpideletevi; "VhdmpiDeleteVirtualDisk"
0x1400ce214  call    TraceEvents
0x1400ce219  mov     rcx, rdi
0x1400ce21c  mov     [rsp+88h+var_48], 0
0x1400ce224  mov     byte ptr [rdi+990h], 1
0x1400ce22b  call    VhdmpiDisableVirtualDiskCachedRundowns
0x1400ce230  lea     rcx, [rdi+980h]
0x1400ce237  xor     edx, edx
0x1400ce239  call    DvWaitRundownBarrier
0x1400ce23e  lea     rcx, [rdi+5C0h]
0x1400ce245  call    VhdmpiWaitForMultiTrigerWorkItem
0x1400ce24a  lea     rcx, [rdi+9F0h]
0x1400ce251  call    DvRundownWorkQueue
0x1400ce256  cmp     qword ptr [rdi+600h], 0
0x1400ce25e  jz      loc_1400CE34F
0x1400ce264  xor     r9d, r9d
0x1400ce267  lea     r8, [rsp+88h+var_40]
0x1400ce26c  lea     rdx, [rsp+88h+var_48]
0x1400ce271  mov     rcx, rdi
0x1400ce274  call    VhdmpiCTGetVhdFileTimeAndDataWriteGuid
0x1400ce279  mov     edx, eax
0x1400ce27b  test    eax, eax
0x1400ce27d  js      short loc_1400CE2B7
0x1400ce27f  mov     eax, [rsp+88h+var_48]
0x1400ce283  mov     rcx, [rdi+600h]
0x1400ce28a  mov     [rcx+0B0h], eax
0x1400ce290  mov     rax, [rdi+20h]
0x1400ce294  cmp     byte ptr [rax+34h], 0
0x1400ce298  jz      loc_1400CE34F
0x1400ce29e  mov     rax, [rdi+600h]
0x1400ce2a5  movups  xmm0, [rsp+88h+var_40]
0x1400ce2aa  movdqu  xmmword ptr [rax+0C2h], xmm0
0x1400ce2b2  jmp     loc_1400CE34F
0x1400ce2b7  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 4
0x1400ce2be  jz      short loc_1400CE307
0x1400ce2c0  mov     r9, [rdi+600h]
0x1400ce2c7  mov     rax, [rdi+90h]
0x1400ce2ce  mov     ecx, [r9+0B0h]
0x1400ce2d5  test    rax, rax
0x1400ce2d8  jnz     short loc_1400CE2E3
0x1400ce2da  lea     rax, asc_140062814; " "
0x1400ce2e1  jmp     short loc_1400CE2E7
0x1400ce2e3  mov     rax, [rax+78h]
0x1400ce2e7  mov     r9, [r9+20h]
0x1400ce2eb  mov     [rsp+88h+var_50], rcx
0x1400ce2f0  mov     [rsp+88h+var_58], 1
0x1400ce2f9  mov     dword ptr [rsp+88h+var_60], edx; char
0x1400ce2fd  mov     [rsp+88h+var_68], rax
0x1400ce302  call    McTemplateK0zzqxx_EtwWriteTransfer
0x1400ce307  mov     eax, cs:dword_1400876D0
0x1400ce30d  mov     r8d, 2
0x1400ce313  cmp     eax, r8d
0x1400ce316  jbe     short loc_1400CE34F
0x1400ce318  mov     edx, 1000h
0x1400ce31d  lea     rcx, dword_1400876D0
0x1400ce324  call    _tlgKeywordOn
0x1400ce329  test    al, al
0x1400ce32b  jz      short loc_1400CE34F
0x1400ce32d  mov     ecx, 0CACh
0x1400ce332  lea     rax, aVhdmpideletevi_0; "VhdmpiDeleteVirtualDisk: failed to quer"...
0x1400ce339  mov     r9d, edx; int
0x1400ce33c  mov     [rsp+88h+var_68], rax; char *
0x1400ce341  mov     edx, ecx; int
0x1400ce343  lea     rcx, aVhdmpideletevi; "VhdmpiDeleteVirtualDisk"
0x1400ce34a  call    TraceEvents
0x1400ce34f  mov     rcx, [rdi+90h]; char
0x1400ce356  test    rcx, rcx
0x1400ce359  jz      short loc_1400CE36E
0x1400ce35b  mov     rdx, rdi
0x1400ce35e  mov     qword ptr [rdi+90h], 0
0x1400ce369  call    VhdmpiReleaseBackingStore
0x1400ce36e  lea     rsi, [rdi+130h]
0x1400ce375  mov     rcx, [rsi]; P
0x1400ce378  cmp     rcx, rsi
0x1400ce37b  jz      short loc_1400CE399
0x1400ce37d  mov     rbx, [rcx]
0x1400ce380  mov     edx, 45444856h; Tag
0x1400ce385  call    cs:__imp_ExFreePoolWithTag
0x1400ce38c  nop     dword ptr [rax+rax+00h]
0x1400ce391  mov     rcx, rbx
0x1400ce394  cmp     rbx, rsi
0x1400ce397  jnz     short loc_1400CE37D
0x1400ce399  lea     rsi, [rdi+140h]
0x1400ce3a0  mov     rcx, [rsi]; P
0x1400ce3a3  cmp     rcx, rsi
0x1400ce3a6  jz      short loc_1400CE3C4
0x1400ce3a8  mov     rbx, [rcx]
0x1400ce3ab  mov     edx, 45444856h; Tag
0x1400ce3b0  call    cs:__imp_ExFreePoolWithTag
0x1400ce3b7  nop     dword ptr [rax+rax+00h]
0x1400ce3bc  mov     rcx, rbx
0x1400ce3bf  cmp     rbx, rsi
0x1400ce3c2  jnz     short loc_1400CE3A8
0x1400ce3c4  lea     rcx, [rdi+388h]; struct VHD_LOW_RESOURCES_QUEUE *
0x1400ce3cb  call    ?VhdmpiCleanupLowResourcesQueue@@YAXPEAUVHD_LOW_RESOURCES_QUEUE@@@Z; VhdmpiCleanupLowResourcesQueue(VHD_LOW_RESOURCES_QUEUE *)
0x1400ce3d0  mov     rcx, rdi; struct _VHD_VIRTUAL_DISK *
0x1400ce3d3  call    VhdmpiCTLogCleanupTracking
0x1400ce3d8  lea     rcx, [rdi+180h]
0x1400ce3df  call    VhdmpiTeardownIoTracker
0x1400ce3e4  lea     rcx, [rdi+0A40h]; struct _IO_PERF_ENTITY_DATA *
0x1400ce3eb  call    IoPerfFreeEntityData
0x1400ce3f0  mov     rcx, [rdi+0A30h]; P
0x1400ce3f7  test    rcx, rcx
0x1400ce3fa  jz      short loc_1400CE40D
0x1400ce3fc  mov     edx, 73646856h; Tag
0x1400ce401  call    cs:__imp_ExFreePoolWithTag
0x1400ce408  nop     dword ptr [rax+rax+00h]
0x1400ce40d  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 8
0x1400ce414  jz      short loc_1400CE42C
0x1400ce416  mov     r9, [rdi+0B00h]
0x1400ce41d  lea     rdx, VirtualDiskDestroyed
0x1400ce424  xor     r8d, r8d
0x1400ce427  call    McTemplateK0p_EtwWriteTransfer
0x1400ce42c  mov     edx, 63444856h; Tag
0x1400ce431  mov     rcx, rdi; P
0x1400ce434  call    cs:__imp_ExFreePoolWithTag
0x1400ce43b  nop     dword ptr [rax+rax+00h]
0x1400ce440  call    VhdmpiDecrementDriverUserCount
0x1400ce445  mov     edx, cs:dword_1400876D0
0x1400ce44b  cmp     edx, 5
0x1400ce44e  jbe     short loc_1400CE489
0x1400ce450  mov     rdx, r15
0x1400ce453  lea     rcx, dword_1400876D0
0x1400ce45a  call    _tlgKeywordOn
0x1400ce45f  test    al, al
0x1400ce461  jz      short loc_1400CE489
0x1400ce463  lea     rax, aVhdmpideletevh; "VhdmpiDeleteVhdVirtualDisk: leaving..."
0x1400ce46a  mov     edx, 0D01h; int
0x1400ce46f  mov     r9d, r15d; int
0x1400ce472  mov     [rsp+88h+var_68], rax; char *
0x1400ce477  mov     r8d, 5; int
0x1400ce47d  lea     rcx, aVhdmpideletevi; "VhdmpiDeleteVirtualDisk"
0x1400ce484  call    TraceEvents
0x1400ce489  mov     rcx, [rsp+88h+var_30]
0x1400ce48e  xor     rcx, rsp; StackCookie
0x1400ce491  call    __security_check_cookie
0x1400ce496  add     rsp, 68h
0x1400ce49a  pop     r15
0x1400ce49c  pop     rdi
0x1400ce49d  pop     rsi
0x1400ce49e  pop     rbx
0x1400ce49f  retn
```

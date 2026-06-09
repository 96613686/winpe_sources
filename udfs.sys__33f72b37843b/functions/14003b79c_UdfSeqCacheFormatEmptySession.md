# UdfSeqCacheFormatEmptySession

- ea: `0x14003b79c`
- end: `0x14003bb11`
- name: `UdfSeqCacheFormatEmptySession`
- size: `885`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x140017c08`

## callees

- `0x140004340`
- `0x140007b90`
- `0x140009450`
- `0x14000a2e8`
- `0x14000cad4`
- `0x14000cbcc`
- `0x14001c080`
- `0x14002c774`
- `0x14003b730`
- `0x14003b79c`
- `0x140049020`
- `0x140049bb0`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003b880`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003b880`

## pseudocode

```c
__int64 __fastcall UdfSeqCacheFormatEmptySession(__int64 a1)
{
  __int64 v2; // rsi
  _DWORD *v3; // rbx
  int v4; // ecx
  bool v5; // al
  unsigned int v6; // r14d
  _DWORD *PoolWithTag; // rax
  _DWORD *v8; // r13
  __int64 v9; // rcx
  int FreeBlocksAndNWA; // ebx
  _DWORD *v12; // [rsp+48h] [rbp-50h]
  unsigned int v13; // [rsp+A8h] [rbp+10h]
  __int64 v14; // [rsp+A8h] [rbp+10h]
  __int64 v15; // [rsp+B0h] [rbp+18h] BYREF
  _DWORD *v16; // [rsp+B8h] [rbp+20h] BYREF

  v2 = *(_QWORD *)(a1 + 16);
  v3 = *(_DWORD **)(v2 + 104);
  v12 = v3;
  v15 = 0;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 41, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
  }
  v4 = *(_DWORD *)(*(_QWORD *)(v2 + 104) + 4LL) & 0x10;
  if ( (*(_DWORD *)(v2 + 48) & 0x20000000) != 0 )
  {
    if ( v4 )
      return 3221226048LL;
    v5 = 0;
  }
  else
  {
    v5 = v4 != 0;
  }
  if ( v5 )
    return 3221226048LL;
  if ( *(_DWORD *)(v2 + 68) != 2048 )
    return 3221225701LL;
  v6 = v3[2];
  if ( v6 < 0x20 || v3[177] )
    return 3221225701LL;
  v13 = ((unsigned __int8)v3[4] + 1) & 7;
  if ( v6 > 0x100 )
    v6 = 256;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1041, 0x800u, 0x62666455u);
  v8 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, 0x800u);
  v16 = v8;
  *(_DWORD *)(a1 + 28) |= 0x10000u;
  v14 = 5 * (v13 + 1LL);
  UdfReadWriteSectors(
    a1,
    (union _LARGE_INTEGER)((unsigned __int64)*(unsigned int *)(v2 + 244) << *(_DWORD *)(v2 + 72)),
    v6 << *(_DWORD *)(v2 + 72),
    0,
    *(PVOID *)&v3[2 * v14],
    *(PDEVICE_OBJECT *)(v2 + 24),
    0);
  UdfReadWriteSectors(
    a1,
    (union _LARGE_INTEGER)((unsigned __int64)(unsigned int)(*(_DWORD *)(v2 + 244) + 256) << *(_DWORD *)(v2 + 72)),
    *(unsigned int *)(v2 + 68),
    0,
    v8,
    *(PDEVICE_OBJECT *)(v2 + 24),
    0);
  UdfVerifyDescriptor(a1, (__int64)v8, 2, 0x200u, *(_DWORD *)(v2 + 244) + 256, 0);
  UdfAcquireResource(a1, v2 + 136, 0, 0);
  FreeBlocksAndNWA = UdfQueryFreeBlocksAndNWA(v2, v2 + 668, v2 + 684);
  if ( FreeBlocksAndNWA >= 0 )
  {
    v8[3] = *(_DWORD *)(v2 + 684) + 256;
    UdfUpdateChecksumAndCrc(v8, 512);
    FreeBlocksAndNWA = UdfSeqCacheWriteBlocksForFile(a1, -1, 0, v6, &v15, *(_QWORD *)&v12[2 * v14]);
    if ( FreeBlocksAndNWA >= 0 )
    {
      if ( v6 >= 0x100
        || (FreeBlocksAndNWA = UdfSeqCacheWriteBlocksForFile(a1, -1, 0, 256 - v6, &v15, 0), FreeBlocksAndNWA >= 0) )
      {
        FreeBlocksAndNWA = UdfSeqCacheWriteBlocksForFile(a1, -1, 0, 1u, &v15, (__int64)v8);
        if ( FreeBlocksAndNWA >= 0 )
        {
          UdfSeqCacheFlush(a1, v2);
          FreeBlocksAndNWA = UdfSeqCacheSyncCache(v2);
          if ( FreeBlocksAndNWA >= 0 )
          {
            v9 = *(_QWORD *)&WPP_GLOBAL_Control;
            if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
            {
              WPP_SF_(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                42,
                WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
            }
          }
        }
      }
    }
  }
  UdfReleaseDevice(v9, v2, 0);
  UdfFreePool(&v16);
  *(_DWORD *)(a1 + 28) &= ~0x10000u;
  return (unsigned int)FreeBlocksAndNWA;
}

```

## disassembly

```asm
0x14003b79c  mov     rax, rsp
0x14003b79f  mov     [rax+8], rcx
0x14003b7a3  push    rbx
0x14003b7a4  push    rsi
0x14003b7a5  push    rdi
0x14003b7a6  push    r13
0x14003b7a8  push    r14
0x14003b7aa  push    r15
0x14003b7ac  sub     rsp, 68h
0x14003b7b0  mov     rdi, rcx
0x14003b7b3  mov     rsi, [rcx+10h]
0x14003b7b7  mov     rbx, [rsi+68h]
0x14003b7bb  mov     [rsp+98h+var_50], rbx
0x14003b7c0  mov     qword ptr [rax+18h], 0
0x14003b7c8  lea     rax, WPP_GLOBAL_Control
0x14003b7cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b7d6  cmp     rcx, rax
0x14003b7d9  jz      short loc_14003B7F9
0x14003b7db  test    dword ptr [rcx+2Ch], 20000000h
0x14003b7e2  jz      short loc_14003B7F9
0x14003b7e4  mov     edx, 29h ; ')'
0x14003b7e9  lea     r8, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids
0x14003b7f0  mov     rcx, [rcx+18h]
0x14003b7f4  call    WPP_SF_
0x14003b7f9  mov     rax, [rsi+68h]
0x14003b7fd  mov     ecx, [rax+4]
0x14003b800  and     ecx, 10h
0x14003b803  test    dword ptr [rsi+30h], 20000000h
0x14003b80a  jnz     short loc_14003B813
0x14003b80c  test    ecx, ecx
0x14003b80e  setnz   al
0x14003b811  jmp     short loc_14003B81D
0x14003b813  test    ecx, ecx
0x14003b815  jnz     loc_14003BAFD
0x14003b81b  xor     al, al
0x14003b81d  test    al, al
0x14003b81f  jnz     loc_14003BAFD
0x14003b825  mov     ecx, 800h
0x14003b82a  cmp     [rsi+44h], ecx
0x14003b82d  jnz     loc_14003BAF6
0x14003b833  mov     r14d, [rbx+8]
0x14003b837  cmp     r14d, 20h ; ' '
0x14003b83b  jb      loc_14003BAF6
0x14003b841  cmp     dword ptr [rbx+2C4h], 0
0x14003b848  jnz     loc_14003BAF6
0x14003b84e  mov     [rsp+98h+var_48], rsi
0x14003b853  mov     [rsp+98h+var_58], al
0x14003b857  mov     eax, [rbx+10h]
0x14003b85a  inc     eax
0x14003b85c  and     eax, 7
0x14003b85f  mov     dword ptr [rsp+98h+arg_8], eax
0x14003b866  mov     r15d, 100h
0x14003b86c  cmp     r14d, r15d
0x14003b86f  cmova   r14d, r15d
0x14003b873  mov     r8d, 62666455h; Tag
0x14003b879  mov     edx, ecx; NumberOfBytes
0x14003b87b  mov     ecx, 411h; PoolType
0x14003b880  call    cs:__imp_ExAllocatePoolWithTag
0x14003b887  nop     dword ptr [rax+rax+00h]
0x14003b88c  mov     r13, rax
0x14003b88f  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14003b896  jnz     short loc_14003B8AD
0x14003b898  test    rax, rax
0x14003b89b  jz      short loc_14003B8AD
0x14003b89d  xor     edx, edx; Val
0x14003b89f  mov     r8d, 800h; Size
0x14003b8a5  mov     rcx, rax; void *
0x14003b8a8  call    memset
0x14003b8ad  mov     [rsp+98h+arg_18], r13
0x14003b8b5  bts     dword ptr [rdi+1Ch], 10h
0x14003b8ba  mov     ecx, [rsi+48h]
0x14003b8bd  mov     eax, dword ptr [rsp+98h+arg_8]
0x14003b8c4  inc     rax
0x14003b8c7  lea     r9, [rax+rax*4]
0x14003b8cb  mov     [rsp+98h+arg_8], r9
0x14003b8d3  mov     r8d, r14d
0x14003b8d6  shl     r8d, cl
0x14003b8d9  mov     edx, [rsi+0F4h]
0x14003b8df  shl     rdx, cl
0x14003b8e2  mov     byte ptr [rsp+98h+var_68], 0
0x14003b8e7  mov     rax, [rsi+18h]
0x14003b8eb  mov     [rsp+98h+var_70], rax
0x14003b8f0  mov     rax, [rbx+r9*8]
0x14003b8f4  mov     [rsp+98h+var_78], rax
0x14003b8f9  xor     r9d, r9d
0x14003b8fc  mov     rcx, rdi
0x14003b8ff  call    UdfReadWriteSectors
0x14003b904  mov     edx, [rsi+0F4h]
0x14003b90a  add     edx, r15d
0x14003b90d  mov     ecx, [rsi+48h]
0x14003b910  shl     rdx, cl
0x14003b913  mov     byte ptr [rsp+98h+var_68], 0
0x14003b918  mov     rax, [rsi+18h]
0x14003b91c  mov     [rsp+98h+var_70], rax
0x14003b921  mov     [rsp+98h+var_78], r13
0x14003b926  xor     r9d, r9d
0x14003b929  mov     r8d, [rsi+44h]
0x14003b92d  mov     rcx, rdi
0x14003b930  call    UdfReadWriteSectors
0x14003b935  mov     eax, [rsi+0F4h]
0x14003b93b  add     eax, r15d
0x14003b93e  mov     r8d, 2
0x14003b944  mov     dword ptr [rsp+98h+var_70], 0
0x14003b94c  mov     dword ptr [rsp+98h+var_78], eax
0x14003b950  mov     r9d, 200h
0x14003b956  mov     rdx, r13
0x14003b959  mov     rcx, rdi
0x14003b95c  call    UdfVerifyDescriptor
0x14003b961  lea     rdx, [rsi+88h]
0x14003b968  xor     r9d, r9d
0x14003b96b  xor     r8d, r8d
0x14003b96e  mov     rcx, rdi
0x14003b971  call    UdfAcquireResource
0x14003b976  mov     [rsp+98h+var_58], 1
0x14003b97b  lea     r8, [rsi+2ACh]
0x14003b982  lea     rdx, [rsi+29Ch]
0x14003b989  mov     rcx, rsi
0x14003b98c  call    UdfQueryFreeBlocksAndNWA
0x14003b991  mov     ebx, eax
0x14003b993  mov     [rsp+98h+var_54], eax
0x14003b997  test    eax, eax
0x14003b999  js      loc_14003BAD5
0x14003b99f  mov     eax, [rsi+2ACh]
0x14003b9a5  add     eax, r15d
0x14003b9a8  mov     [r13+0Ch], eax
0x14003b9ac  mov     edx, 200h
0x14003b9b1  mov     rcx, r13
0x14003b9b4  call    UdfUpdateChecksumAndCrc
0x14003b9b9  mov     [rsp+98h+var_68], 0
0x14003b9c2  mov     rax, [rsp+98h+var_50]
0x14003b9c7  mov     rcx, [rsp+98h+arg_8]
0x14003b9cf  mov     rax, [rax+rcx*8]
0x14003b9d3  mov     [rsp+98h+var_70], rax
0x14003b9d8  lea     rax, [rsp+98h+arg_10]
0x14003b9e0  mov     [rsp+98h+var_78], rax
0x14003b9e5  mov     r9d, r14d
0x14003b9e8  xor     r8d, r8d
0x14003b9eb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14003b9ef  mov     rcx, rdi
0x14003b9f2  call    UdfSeqCacheWriteBlocksForFile
0x14003b9f7  mov     ebx, eax
0x14003b9f9  mov     [rsp+98h+var_54], eax
0x14003b9fd  test    eax, eax
0x14003b9ff  js      loc_14003BAD5
0x14003ba05  cmp     r14d, r15d
0x14003ba08  jnb     short loc_14003BA4C
0x14003ba0a  sub     r15d, r14d
0x14003ba0d  mov     [rsp+98h+var_68], 0
0x14003ba16  mov     [rsp+98h+var_70], 0
0x14003ba1f  lea     rax, [rsp+98h+arg_10]
0x14003ba27  mov     [rsp+98h+var_78], rax
0x14003ba2c  mov     r9d, r15d
0x14003ba2f  xor     r8d, r8d
0x14003ba32  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14003ba36  mov     rcx, rdi
0x14003ba39  call    UdfSeqCacheWriteBlocksForFile
0x14003ba3e  mov     ebx, eax
0x14003ba40  mov     [rsp+98h+var_54], eax
0x14003ba44  test    eax, eax
0x14003ba46  js      loc_14003BAD5
0x14003ba4c  mov     [rsp+98h+var_68], 0
0x14003ba55  mov     [rsp+98h+var_70], r13
0x14003ba5a  lea     rax, [rsp+98h+arg_10]
0x14003ba62  mov     [rsp+98h+var_78], rax
0x14003ba67  mov     r9d, 1
0x14003ba6d  xor     r8d, r8d
0x14003ba70  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14003ba74  mov     rcx, rdi
0x14003ba77  call    UdfSeqCacheWriteBlocksForFile
0x14003ba7c  mov     ebx, eax
0x14003ba7e  mov     [rsp+98h+var_54], eax
0x14003ba82  test    eax, eax
0x14003ba84  js      short loc_14003BAD5
0x14003ba86  mov     rdx, rsi
0x14003ba89  mov     rcx, rdi
0x14003ba8c  call    UdfSeqCacheFlush
0x14003ba91  mov     rcx, rsi
0x14003ba94  call    UdfSeqCacheSyncCache
0x14003ba99  mov     ebx, eax
0x14003ba9b  mov     [rsp+98h+var_54], eax
0x14003ba9f  test    eax, eax
0x14003baa1  js      short loc_14003BAD5
0x14003baa3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003baaa  lea     rax, WPP_GLOBAL_Control
0x14003bab1  cmp     rcx, rax
0x14003bab4  jz      short loc_14003BAD5
0x14003bab6  test    dword ptr [rcx+2Ch], 20000000h
0x14003babd  jz      short loc_14003BAD5
0x14003babf  mov     edx, 2Ah ; '*'
0x14003bac4  lea     r8, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids
0x14003bacb  mov     rcx, [rcx+18h]
0x14003bacf  call    WPP_SF_
0x14003bad4  nop
0x14003bad5  xor     r8d, r8d
0x14003bad8  mov     rdx, rsi
0x14003badb  call    UdfReleaseDevice
0x14003bae0  lea     rcx, [rsp+98h+arg_18]
0x14003bae8  call    UdfFreePool
0x14003baed  btr     dword ptr [rdi+1Ch], 10h
0x14003baf2  mov     eax, ebx
0x14003baf4  jmp     short loc_14003BB02
0x14003baf6  mov     eax, 0C00000E5h
0x14003bafb  jmp     short loc_14003BB02
0x14003bafd  mov     eax, 0C0000240h
0x14003bb02  add     rsp, 68h
0x14003bb06  pop     r15
0x14003bb08  pop     r14
0x14003bb0a  pop     r13
0x14003bb0c  pop     rdi
0x14003bb0d  pop     rsi
0x14003bb0e  pop     rbx
0x14003bb0f  retn
0x14005c397  push    rbp
0x14005c399  sub     rsp, 40h
0x14005c39d  mov     rbp, rdx
0x14005c3a0  cmp     byte ptr [rbp+40h], 0
0x14005c3a4  jz      short loc_14005C3B3
0x14005c3a6  xor     r8d, r8d
0x14005c3a9  mov     rdx, [rbp+50h]
0x14005c3ad  call    UdfReleaseDevice
0x14005c3b2  nop
0x14005c3b3  lea     rcx, [rbp+0B8h]
0x14005c3ba  call    UdfFreePool
0x14005c3bf  mov     rcx, [rbp+0A0h]
0x14005c3c6  mov     eax, [rcx+1Ch]
0x14005c3c9  btr     eax, 10h
0x14005c3cd  mov     [rcx+1Ch], eax
0x14005c3d0  add     rsp, 40h
0x14005c3d4  pop     rbp
0x14005c3d5  retn
```

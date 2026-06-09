# WimCbUpdateOverlay

- ea: `0x140027870`
- end: `0x140027b87`
- name: `WimCbUpdateOverlay`
- size: `791`
- prototype: `__int64 __fastcall(int, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callees

- `0x14000c3bc`
- `0x14000d250`
- `0x14000edcc`
- `0x14000fce4`
- `0x14000fdc0`
- `0x140011560`
- `0x1400116c0`
- `0x140027870`
- `0x14002badc`
- `0x14002d990`
- `0x14003c44c`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140027a86`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140027ad2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140027a86`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140027ad2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027a97`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027aba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027b53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027a97`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027aba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027b53`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140027a27`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140027a27`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140027a70`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140027a70`
- `FLTMGR!FltObjectDereference` at `0x140027b28`
- `FLTMGR!FltObjectDereference` at `0x140027b28`
- `FLTMGR!FltReleaseContext` at `0x140027b3c`
- `FLTMGR!FltReleaseContext` at `0x140027b3c`

## pseudocode

```c
__int64 __fastcall WimCbUpdateOverlay(int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rsi
  int AttachVolumeFromPathName; // eax
  unsigned int v11; // edi
  const void **v13; // rdi
  __int64 v14; // r14
  int updated; // esi
  int v16; // r8d
  __int64 v17; // rbx
  char *PoolWithTag; // rax
  char *v19; // r14
  void *v20; // rcx
  PFLT_CONTEXT Context[2]; // [rsp+40h] [rbp-51h] BYREF
  void *Src[2]; // [rsp+50h] [rbp-41h] BYREF
  int v23[4]; // [rsp+60h] [rbp-31h] BYREF
  __int64 v24; // [rsp+70h] [rbp-21h] BYREF
  PVOID FltObject; // [rsp+78h] [rbp-19h] BYREF
  __int64 v26[2]; // [rsp+80h] [rbp-11h] BYREF

  FltObject = 0;
  Context[0] = 0;
  v24 = 0;
  *(_OWORD *)v23 = 0;
  *(_OWORD *)Src = 0;
  *(_OWORD *)v26 = 0;
  if ( a4 < 0x10 )
    return 3221225485LL;
  v7 = *(_DWORD *)(a3 + 12);
  if ( v7 >= 0xFFFF )
    return 3221225485LL;
  if ( (v7 & 1) != 0 )
    return 3221225485LL;
  v8 = *(unsigned int *)(a3 + 8);
  if ( (unsigned int)v8 > a4 || (unsigned int)v8 + v7 < (unsigned int)v8 || (unsigned int)v8 + v7 > a4 )
    return 3221225485LL;
  v9 = (unsigned int)dword_14001A2FC;
  LOWORD(v23[0]) = *(_DWORD *)(a3 + 12);
  HIWORD(v23[0]) = v7;
  *(_QWORD *)&v23[2] = a3 + v8;
  AttachVolumeFromPathName = WofGetAttachVolumeFromPathName(v23, Src, &FltObject, Context);
  v11 = AttachVolumeFromPathName;
  if ( AttachVolumeFromPathName >= 0 )
  {
    v13 = (const void **)Context[0];
    v14 = a2 - v9;
    updated = WimFSFMQueryWimGuid(a1, (int)a2 - (int)v9, (int)Context[0], (int)v23, (__int64)v26);
    if ( updated < 0
      || (WimFSFAcquireConfigLock(a2),
          updated = WimUpdateOverlayConfig(v14, (_DWORD)v13, a3, (unsigned int)Src, (__int64)v26),
          WimFSFReleaseConfigLock(a2),
          updated < 0)
      || (updated = WimFSFFindOverlayByDataSource(a2, *(_QWORD *)a3, &v24), updated < 0) )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_iZZZd(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v13 + 64,
          v16,
          *(_QWORD *)a3,
          (__int64)(v13 + 8),
          (__int64)Src,
          v14 + 64,
          updated);
    }
    else
    {
      v17 = v24;
      *(_OWORD *)Context = 0;
      if ( (*(_DWORD *)(v24 + 40) & 5) != 0 )
      {
        LOWORD(Context[0]) = *((_WORD *)v13 + 32) + LOWORD(Src[0]);
        WORD1(Context[0]) = Context[0];
        PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, LOWORD(Context[0]), 0x66637077u);
        Context[1] = PoolWithTag;
        v19 = PoolWithTag;
        if ( PoolWithTag )
        {
          memmove(PoolWithTag, v13[9], *((unsigned __int16 *)v13 + 32));
          memmove(&v19[*((unsigned __int16 *)v13 + 32)], Src[1], LOWORD(Src[0]));
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v17 + 112));
          if ( *(_QWORD *)(v17 + 104) )
          {
            ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v17 + 112));
            ExFreePoolWithTag(v19, 0);
          }
          else
          {
            _InterlockedOr((volatile signed __int32 *)(v17 + 40), 1u);
            _InterlockedAnd((volatile signed __int32 *)(v17 + 40), 0xFFFFFFEB);
            v20 = *(void **)(v17 + 64);
            if ( v20 )
              ExFreePoolWithTag(v20, 0);
            *(_OWORD *)(v17 + 56) = *(_OWORD *)Context;
            ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v17 + 112));
          }
        }
      }
    }
    if ( FltObject )
      FltObjectDereference(FltObject);
    if ( v13 )
      FltReleaseContext(v13);
    if ( Src[1] )
      ExFreePoolWithTag(Src[1], 0);
    return (unsigned int)updated;
  }
  else
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_Zd(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        (unsigned int)WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids,
        (unsigned int)v23,
        AttachVolumeFromPathName);
    return v11;
  }
}

```

## disassembly

```asm
0x140027870  push    rbp
0x140027872  push    rbx
0x140027873  push    rsi
0x140027874  push    rdi
0x140027875  push    r12
0x140027877  push    r14
0x140027879  push    r15
0x14002787b  lea     rbp, [rsp-0Fh]
0x140027880  sub     rsp, 0A0h
0x140027887  mov     rax, cs:__security_cookie
0x14002788e  xor     rax, rsp
0x140027891  mov     [rbp+3Fh+var_40], rax
0x140027895  mov     [rbp+3Fh+FltObject], 0
0x14002789d  xorps   xmm0, xmm0
0x1400278a0  mov     [rbp+3Fh+Context], 0
0x1400278a8  xorps   xmm1, xmm1
0x1400278ab  mov     [rbp+3Fh+var_60], 0
0x1400278b3  mov     rbx, r8
0x1400278b6  mov     r15, rdx
0x1400278b9  mov     r12, rcx
0x1400278bc  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x1400278c0  movups  xmmword ptr [rbp+3Fh+Src], xmm1
0x1400278c4  movups  xmmword ptr [rbp+3Fh+var_50], xmm0
0x1400278c8  cmp     r9d, 10h
0x1400278cc  jb      loc_140027B63
0x1400278d2  mov     eax, [r8+0Ch]
0x1400278d6  cmp     eax, 0FFFFh
0x1400278db  jnb     loc_140027B63
0x1400278e1  test    al, 1
0x1400278e3  jnz     loc_140027B63
0x1400278e9  mov     ecx, [r8+8]
0x1400278ed  cmp     ecx, r9d
0x1400278f0  ja      loc_140027B63
0x1400278f6  lea     edx, [rcx+rax]
0x1400278f9  cmp     edx, ecx
0x1400278fb  jb      loc_140027B63
0x140027901  cmp     edx, r9d
0x140027904  ja      loc_140027B63
0x14002790a  mov     esi, cs:dword_14001A2FC
0x140027910  lea     r9, [rbp+3Fh+Context]
0x140027914  mov     word ptr [rbp+3Fh+var_70], ax
0x140027918  lea     rdx, [rbp+3Fh+Src]
0x14002791c  mov     word ptr [rbp+3Fh+var_70+2], ax
0x140027920  lea     rax, [r8+rcx]
0x140027924  lea     r8, [rbp+3Fh+FltObject]
0x140027928  mov     qword ptr [rbp+3Fh+var_70+8], rax
0x14002792c  lea     rcx, [rbp+3Fh+var_70]
0x140027930  call    WofGetAttachVolumeFromPathName
0x140027935  mov     edi, eax
0x140027937  test    eax, eax
0x140027939  jns     short loc_140027976
0x14002793b  mov     r10, cs:WPP_GLOBAL_Control
0x140027942  mov     ecx, [r10+2Ch]
0x140027946  test    cl, 8
0x140027949  jz      short loc_14002796F
0x14002794b  cmp     byte ptr [r10+29h], 2
0x140027950  jb      short loc_14002796F
0x140027952  mov     rcx, [r10+18h]
0x140027956  lea     r9, [rbp+3Fh+var_70]
0x14002795a  mov     edx, 0Dh
0x14002795f  mov     dword ptr [rsp+0D0h+var_B0], eax
0x140027963  lea     r8, WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids
0x14002796a  call    WPP_SF_Zd
0x14002796f  mov     eax, edi
0x140027971  jmp     loc_140027B68
0x140027976  mov     rdi, [rbp+3Fh+Context]
0x14002797a  lea     rax, [rbp+3Fh+var_50]
0x14002797e  mov     r14, r15
0x140027981  mov     [rsp+0D0h+var_B0], rax; __int64
0x140027986  sub     r14, rsi
0x140027989  lea     r9, [rbp+3Fh+var_70]; int
0x14002798d  mov     rdx, r14; int
0x140027990  mov     r8, rdi; int
0x140027993  mov     rcx, r12; int
0x140027996  call    WimFSFMQueryWimGuid
0x14002799b  mov     esi, eax
0x14002799d  test    eax, eax
0x14002799f  js      loc_140027AE0
0x1400279a5  mov     rcx, r15
0x1400279a8  call    WimFSFAcquireConfigLock
0x1400279ad  lea     rax, [rbp+3Fh+var_50]
0x1400279b1  mov     r8, rbx
0x1400279b4  lea     r9, [rbp+3Fh+Src]
0x1400279b8  mov     [rsp+0D0h+var_B0], rax
0x1400279bd  mov     rdx, rdi
0x1400279c0  mov     rcx, r14
0x1400279c3  call    WimUpdateOverlayConfig
0x1400279c8  mov     rcx, r15
0x1400279cb  mov     esi, eax
0x1400279cd  call    WimFSFReleaseConfigLock
0x1400279d2  test    esi, esi
0x1400279d4  js      loc_140027AE0
0x1400279da  mov     rdx, [rbx]
0x1400279dd  lea     r8, [rbp+3Fh+var_60]
0x1400279e1  mov     rcx, r15
0x1400279e4  call    WimFSFFindOverlayByDataSource
0x1400279e9  mov     esi, eax
0x1400279eb  test    eax, eax
0x1400279ed  js      loc_140027AE0
0x1400279f3  mov     rbx, [rbp+3Fh+var_60]
0x1400279f7  xorps   xmm0, xmm0
0x1400279fa  movups  xmmword ptr [rbp+3Fh+Context], xmm0
0x1400279fe  mov     eax, [rbx+28h]
0x140027a01  test    al, 5
0x140027a03  jz      loc_140027B1F
0x140027a09  movzx   eax, word ptr [rbp+3Fh+Src]
0x140027a0d  mov     ecx, 1; PoolType
0x140027a12  add     ax, [rdi+40h]
0x140027a16  mov     r8d, 66637077h; Tag
0x140027a1c  movzx   edx, ax; NumberOfBytes
0x140027a1f  mov     word ptr [rbp+3Fh+Context], dx
0x140027a23  mov     word ptr [rbp+3Fh+Context+2], dx
0x140027a27  call    cs:__imp_ExAllocatePoolWithTag
0x140027a2e  nop     dword ptr [rax+rax+00h]
0x140027a33  mov     [rbp+3Fh+Context+8], rax
0x140027a37  mov     r14, rax
0x140027a3a  test    rax, rax
0x140027a3d  jz      loc_140027B1F
0x140027a43  movzx   r8d, word ptr [rdi+40h]; Size
0x140027a48  mov     rcx, rax; void *
0x140027a4b  mov     rdx, [rdi+48h]; Src
0x140027a4f  call    memmove
0x140027a54  movzx   ecx, word ptr [rdi+40h]
0x140027a58  movzx   r8d, word ptr [rbp+3Fh+Src]; Size
0x140027a5d  add     rcx, r14; void *
0x140027a60  mov     rdx, [rbp+3Fh+Src+8]; Src
0x140027a64  call    memmove
0x140027a69  lea     r15, [rbx+70h]
0x140027a6d  mov     rcx, r15; FastMutex
0x140027a70  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140027a77  nop     dword ptr [rax+rax+00h]
0x140027a7c  cmp     qword ptr [rbx+68h], 0
0x140027a81  jz      short loc_140027AA5
0x140027a83  mov     rcx, r15; FastMutex
0x140027a86  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140027a8d  nop     dword ptr [rax+rax+00h]
0x140027a92  xor     edx, edx; Tag
0x140027a94  mov     rcx, r14; P
0x140027a97  call    cs:__imp_ExFreePoolWithTag
0x140027a9e  nop     dword ptr [rax+rax+00h]
0x140027aa3  jmp     short loc_140027B1F
0x140027aa5  lock or dword ptr [rbx+28h], 1
0x140027aaa  lock and dword ptr [rbx+28h], 0FFFFFFEBh
0x140027aaf  mov     rcx, [rbx+40h]; P
0x140027ab3  test    rcx, rcx
0x140027ab6  jz      short loc_140027AC6
0x140027ab8  xor     edx, edx; Tag
0x140027aba  call    cs:__imp_ExFreePoolWithTag
0x140027ac1  nop     dword ptr [rax+rax+00h]
0x140027ac6  movups  xmm0, xmmword ptr [rbp+3Fh+Context]
0x140027aca  mov     rcx, r15; FastMutex
0x140027acd  movdqu  xmmword ptr [rbx+38h], xmm0
0x140027ad2  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140027ad9  nop     dword ptr [rax+rax+00h]
0x140027ade  jmp     short loc_140027B1F
0x140027ae0  mov     rcx, cs:WPP_GLOBAL_Control
0x140027ae7  mov     eax, [rcx+2Ch]
0x140027aea  test    al, 8
0x140027aec  jz      short loc_140027B1F
0x140027aee  cmp     byte ptr [rcx+29h], 2
0x140027af2  jb      short loc_140027B1F
0x140027af4  mov     r9, [rbx]
0x140027af7  lea     rax, [r14+40h]
0x140027afb  mov     rcx, [rcx+18h]
0x140027aff  lea     rdx, [rdi+40h]
0x140027b03  mov     [rsp+0D0h+var_98], esi
0x140027b07  mov     [rsp+0D0h+var_A0], rax
0x140027b0c  lea     rax, [rbp+3Fh+Src]
0x140027b10  mov     [rsp+0D0h+var_A8], rax
0x140027b15  mov     [rsp+0D0h+var_B0], rdx
0x140027b1a  call    WPP_SF_iZZZd
0x140027b1f  mov     rcx, [rbp+3Fh+FltObject]; FltObject
0x140027b23  test    rcx, rcx
0x140027b26  jz      short loc_140027B34
0x140027b28  call    cs:__imp_FltObjectDereference
0x140027b2f  nop     dword ptr [rax+rax+00h]
0x140027b34  test    rdi, rdi
0x140027b37  jz      short loc_140027B48
0x140027b39  mov     rcx, rdi; Context
0x140027b3c  call    cs:__imp_FltReleaseContext
0x140027b43  nop     dword ptr [rax+rax+00h]
0x140027b48  mov     rcx, [rbp+3Fh+Src+8]; P
0x140027b4c  test    rcx, rcx
0x140027b4f  jz      short loc_140027B5F
0x140027b51  xor     edx, edx; Tag
0x140027b53  call    cs:__imp_ExFreePoolWithTag
0x140027b5a  nop     dword ptr [rax+rax+00h]
0x140027b5f  mov     eax, esi
0x140027b61  jmp     short loc_140027B68
0x140027b63  mov     eax, 0C000000Dh
0x140027b68  mov     rcx, [rbp+3Fh+var_40]
0x140027b6c  xor     rcx, rsp; StackCookie
0x140027b6f  call    __security_check_cookie
0x140027b74  add     rsp, 0A0h
0x140027b7b  pop     r15
0x140027b7d  pop     r14
0x140027b7f  pop     r12
0x140027b81  pop     rdi
0x140027b82  pop     rsi
0x140027b83  pop     rbx
0x140027b84  pop     rbp
0x140027b85  retn
```

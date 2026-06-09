# WimCbUpdateOverlay

- ea: `0x140027820`
- end: `0x140027b37`
- name: `WimCbUpdateOverlay`
- size: `791`
- prototype: `__int64 __fastcall(int)`
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
- `0x140027820`
- `0x14002ba8c`
- `0x14002d940`
- `0x14003c3fc`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140027a36`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140027a82`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140027a36`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140027a82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027a47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027a6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027b03`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027a47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027a6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027b03`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400279d7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400279d7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140027a20`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140027a20`
- `FLTMGR!FltObjectDereference` at `0x140027ad8`
- `FLTMGR!FltObjectDereference` at `0x140027ad8`
- `FLTMGR!FltReleaseContext` at `0x140027aec`
- `FLTMGR!FltReleaseContext` at `0x140027aec`

## pseudocode

```c
__int64 __fastcall WimCbUpdateOverlay(int a1, __int64 a2, _QWORD *a3, unsigned int a4)
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
  v7 = *((_DWORD *)a3 + 3);
  if ( v7 >= 0xFFFF )
    return 3221225485LL;
  if ( (v7 & 1) != 0 )
    return 3221225485LL;
  v8 = *((unsigned int *)a3 + 2);
  if ( (unsigned int)v8 > a4 || (unsigned int)v8 + v7 < (unsigned int)v8 || (unsigned int)v8 + v7 > a4 )
    return 3221225485LL;
  v9 = (unsigned int)dword_14001A2FC;
  LOWORD(v23[0]) = *((_DWORD *)a3 + 3);
  HIWORD(v23[0]) = v7;
  *(_QWORD *)&v23[2] = (char *)a3 + v8;
  AttachVolumeFromPathName = WofGetAttachVolumeFromPathName(
                               (struct _UNICODE_STRING *)v23,
                               (struct _UNICODE_STRING *)Src,
                               &FltObject,
                               Context);
  v11 = AttachVolumeFromPathName;
  if ( AttachVolumeFromPathName >= 0 )
  {
    v13 = (const void **)Context[0];
    v14 = a2 - v9;
    updated = WimFSFMQueryWimGuid(a1, (int)a2 - (int)v9, (int)Context[0], (int)v23, (__int64)v26);
    if ( updated < 0
      || (WimFSFAcquireConfigLock(a2),
          updated = WimUpdateOverlayConfig(v14, (int)v13, a3, (int)Src, v26),
          WimFSFReleaseConfigLock(a2),
          updated < 0)
      || (updated = WimFSFFindOverlayByDataSource(a2, *a3, &v24), updated < 0) )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_iZZZd(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v13 + 64,
          v16,
          *a3,
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
0x140027820  push    rbp
0x140027822  push    rbx
0x140027823  push    rsi
0x140027824  push    rdi
0x140027825  push    r12
0x140027827  push    r14
0x140027829  push    r15
0x14002782b  lea     rbp, [rsp-0Fh]
0x140027830  sub     rsp, 0A0h
0x140027837  mov     rax, cs:__security_cookie
0x14002783e  xor     rax, rsp
0x140027841  mov     [rbp+3Fh+var_40], rax
0x140027845  mov     [rbp+3Fh+FltObject], 0
0x14002784d  xorps   xmm0, xmm0
0x140027850  mov     [rbp+3Fh+Context], 0
0x140027858  xorps   xmm1, xmm1
0x14002785b  mov     [rbp+3Fh+var_60], 0
0x140027863  mov     rbx, r8
0x140027866  mov     r15, rdx
0x140027869  mov     r12, rcx
0x14002786c  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x140027870  movups  xmmword ptr [rbp+3Fh+Src], xmm1
0x140027874  movups  xmmword ptr [rbp+3Fh+var_50], xmm0
0x140027878  cmp     r9d, 10h
0x14002787c  jb      loc_140027B13
0x140027882  mov     eax, [r8+0Ch]
0x140027886  cmp     eax, 0FFFFh
0x14002788b  jnb     loc_140027B13
0x140027891  test    al, 1
0x140027893  jnz     loc_140027B13
0x140027899  mov     ecx, [r8+8]
0x14002789d  cmp     ecx, r9d
0x1400278a0  ja      loc_140027B13
0x1400278a6  lea     edx, [rcx+rax]
0x1400278a9  cmp     edx, ecx
0x1400278ab  jb      loc_140027B13
0x1400278b1  cmp     edx, r9d
0x1400278b4  ja      loc_140027B13
0x1400278ba  mov     esi, cs:dword_14001A2FC
0x1400278c0  lea     r9, [rbp+3Fh+Context]
0x1400278c4  mov     word ptr [rbp+3Fh+var_70], ax
0x1400278c8  lea     rdx, [rbp+3Fh+Src]
0x1400278cc  mov     word ptr [rbp+3Fh+var_70+2], ax
0x1400278d0  lea     rax, [r8+rcx]
0x1400278d4  lea     r8, [rbp+3Fh+FltObject]
0x1400278d8  mov     qword ptr [rbp+3Fh+var_70+8], rax
0x1400278dc  lea     rcx, [rbp+3Fh+var_70]
0x1400278e0  call    WofGetAttachVolumeFromPathName
0x1400278e5  mov     edi, eax
0x1400278e7  test    eax, eax
0x1400278e9  jns     short loc_140027926
0x1400278eb  mov     r10, cs:WPP_GLOBAL_Control
0x1400278f2  mov     ecx, [r10+2Ch]
0x1400278f6  test    cl, 8
0x1400278f9  jz      short loc_14002791F
0x1400278fb  cmp     byte ptr [r10+29h], 2
0x140027900  jb      short loc_14002791F
0x140027902  mov     rcx, [r10+18h]
0x140027906  lea     r9, [rbp+3Fh+var_70]
0x14002790a  mov     edx, 0Dh
0x14002790f  mov     dword ptr [rsp+0D0h+var_B0], eax
0x140027913  lea     r8, WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids
0x14002791a  call    WPP_SF_Zd
0x14002791f  mov     eax, edi
0x140027921  jmp     loc_140027B18
0x140027926  mov     rdi, [rbp+3Fh+Context]
0x14002792a  lea     rax, [rbp+3Fh+var_50]
0x14002792e  mov     r14, r15
0x140027931  mov     [rsp+0D0h+var_B0], rax; __int64
0x140027936  sub     r14, rsi
0x140027939  lea     r9, [rbp+3Fh+var_70]; int
0x14002793d  mov     rdx, r14; int
0x140027940  mov     r8, rdi; int
0x140027943  mov     rcx, r12; int
0x140027946  call    WimFSFMQueryWimGuid
0x14002794b  mov     esi, eax
0x14002794d  test    eax, eax
0x14002794f  js      loc_140027A90
0x140027955  mov     rcx, r15
0x140027958  call    WimFSFAcquireConfigLock
0x14002795d  lea     rax, [rbp+3Fh+var_50]
0x140027961  mov     r8, rbx
0x140027964  lea     r9, [rbp+3Fh+Src]
0x140027968  mov     [rsp+0D0h+var_B0], rax
0x14002796d  mov     rdx, rdi
0x140027970  mov     rcx, r14
0x140027973  call    WimUpdateOverlayConfig
0x140027978  mov     rcx, r15
0x14002797b  mov     esi, eax
0x14002797d  call    WimFSFReleaseConfigLock
0x140027982  test    esi, esi
0x140027984  js      loc_140027A90
0x14002798a  mov     rdx, [rbx]
0x14002798d  lea     r8, [rbp+3Fh+var_60]
0x140027991  mov     rcx, r15
0x140027994  call    WimFSFFindOverlayByDataSource
0x140027999  mov     esi, eax
0x14002799b  test    eax, eax
0x14002799d  js      loc_140027A90
0x1400279a3  mov     rbx, [rbp+3Fh+var_60]
0x1400279a7  xorps   xmm0, xmm0
0x1400279aa  movups  xmmword ptr [rbp+3Fh+Context], xmm0
0x1400279ae  mov     eax, [rbx+28h]
0x1400279b1  test    al, 5
0x1400279b3  jz      loc_140027ACF
0x1400279b9  movzx   eax, word ptr [rbp+3Fh+Src]
0x1400279bd  mov     ecx, 1; PoolType
0x1400279c2  add     ax, [rdi+40h]
0x1400279c6  mov     r8d, 66637077h; Tag
0x1400279cc  movzx   edx, ax; NumberOfBytes
0x1400279cf  mov     word ptr [rbp+3Fh+Context], dx
0x1400279d3  mov     word ptr [rbp+3Fh+Context+2], dx
0x1400279d7  call    cs:__imp_ExAllocatePoolWithTag
0x1400279de  nop     dword ptr [rax+rax+00h]
0x1400279e3  mov     [rbp+3Fh+Context+8], rax
0x1400279e7  mov     r14, rax
0x1400279ea  test    rax, rax
0x1400279ed  jz      loc_140027ACF
0x1400279f3  movzx   r8d, word ptr [rdi+40h]; Size
0x1400279f8  mov     rcx, rax; void *
0x1400279fb  mov     rdx, [rdi+48h]; Src
0x1400279ff  call    memmove
0x140027a04  movzx   ecx, word ptr [rdi+40h]
0x140027a08  movzx   r8d, word ptr [rbp+3Fh+Src]; Size
0x140027a0d  add     rcx, r14; void *
0x140027a10  mov     rdx, [rbp+3Fh+Src+8]; Src
0x140027a14  call    memmove
0x140027a19  lea     r15, [rbx+70h]
0x140027a1d  mov     rcx, r15; FastMutex
0x140027a20  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140027a27  nop     dword ptr [rax+rax+00h]
0x140027a2c  cmp     qword ptr [rbx+68h], 0
0x140027a31  jz      short loc_140027A55
0x140027a33  mov     rcx, r15; FastMutex
0x140027a36  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140027a3d  nop     dword ptr [rax+rax+00h]
0x140027a42  xor     edx, edx; Tag
0x140027a44  mov     rcx, r14; P
0x140027a47  call    cs:__imp_ExFreePoolWithTag
0x140027a4e  nop     dword ptr [rax+rax+00h]
0x140027a53  jmp     short loc_140027ACF
0x140027a55  lock or dword ptr [rbx+28h], 1
0x140027a5a  lock and dword ptr [rbx+28h], 0FFFFFFEBh
0x140027a5f  mov     rcx, [rbx+40h]; P
0x140027a63  test    rcx, rcx
0x140027a66  jz      short loc_140027A76
0x140027a68  xor     edx, edx; Tag
0x140027a6a  call    cs:__imp_ExFreePoolWithTag
0x140027a71  nop     dword ptr [rax+rax+00h]
0x140027a76  movups  xmm0, xmmword ptr [rbp+3Fh+Context]
0x140027a7a  mov     rcx, r15; FastMutex
0x140027a7d  movdqu  xmmword ptr [rbx+38h], xmm0
0x140027a82  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140027a89  nop     dword ptr [rax+rax+00h]
0x140027a8e  jmp     short loc_140027ACF
0x140027a90  mov     rcx, cs:WPP_GLOBAL_Control
0x140027a97  mov     eax, [rcx+2Ch]
0x140027a9a  test    al, 8
0x140027a9c  jz      short loc_140027ACF
0x140027a9e  cmp     byte ptr [rcx+29h], 2
0x140027aa2  jb      short loc_140027ACF
0x140027aa4  mov     r9, [rbx]
0x140027aa7  lea     rax, [r14+40h]
0x140027aab  mov     rcx, [rcx+18h]
0x140027aaf  lea     rdx, [rdi+40h]
0x140027ab3  mov     [rsp+0D0h+var_98], esi
0x140027ab7  mov     [rsp+0D0h+var_A0], rax
0x140027abc  lea     rax, [rbp+3Fh+Src]
0x140027ac0  mov     [rsp+0D0h+var_A8], rax
0x140027ac5  mov     [rsp+0D0h+var_B0], rdx
0x140027aca  call    WPP_SF_iZZZd
0x140027acf  mov     rcx, [rbp+3Fh+FltObject]; FltObject
0x140027ad3  test    rcx, rcx
0x140027ad6  jz      short loc_140027AE4
0x140027ad8  call    cs:__imp_FltObjectDereference
0x140027adf  nop     dword ptr [rax+rax+00h]
0x140027ae4  test    rdi, rdi
0x140027ae7  jz      short loc_140027AF8
0x140027ae9  mov     rcx, rdi; Context
0x140027aec  call    cs:__imp_FltReleaseContext
0x140027af3  nop     dword ptr [rax+rax+00h]
0x140027af8  mov     rcx, [rbp+3Fh+Src+8]; P
0x140027afc  test    rcx, rcx
0x140027aff  jz      short loc_140027B0F
0x140027b01  xor     edx, edx; Tag
0x140027b03  call    cs:__imp_ExFreePoolWithTag
0x140027b0a  nop     dword ptr [rax+rax+00h]
0x140027b0f  mov     eax, esi
0x140027b11  jmp     short loc_140027B18
0x140027b13  mov     eax, 0C000000Dh
0x140027b18  mov     rcx, [rbp+3Fh+var_40]
0x140027b1c  xor     rcx, rsp; StackCookie
0x140027b1f  call    __security_check_cookie
0x140027b24  add     rsp, 0A0h
0x140027b2b  pop     r15
0x140027b2d  pop     r14
0x140027b2f  pop     r12
0x140027b31  pop     rdi
0x140027b32  pop     rsi
0x140027b33  pop     rbx
0x140027b34  pop     rbp
0x140027b35  retn
```

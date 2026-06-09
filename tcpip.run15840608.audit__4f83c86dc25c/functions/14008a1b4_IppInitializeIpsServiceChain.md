# IppInitializeIpsServiceChain

- ea: `0x14008a1b4`
- end: `0x14008a3fb`
- name: `IppInitializeIpsServiceChain`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x140088f8c`

## callees

- `0x140014a08`
- `0x14008a1b4`
- `0x14008ab84`
- `0x14008b610`
- `0x14008b640`
- `0x1400fa294`
- `0x140154840`
- `0x14018f8d0`
- `0x14018fb38`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401cc3d5`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401cc3d5`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14008a259`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14008a259`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008a2db`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008a2db`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008a287`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008a287`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14008a2cf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14008a2cf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14008a29f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14008a29f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401cc3e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401cc3e7`
- `ntoskrnl!ExAllocatePool2` at `0x14008a1fc`
- `ntoskrnl!ExAllocatePool2` at `0x14008a1fc`

## string_xrefs

- `0x14008a397`: `IPS service chain (IPNG)`
- `0x14008a27b`: `IPS service chain rundown object (IPNG)`

## pseudocode

```c
__int64 __fastcall IppInitializeIpsServiceChain(__int64 a1, _OWORD *a2)
{
  __int64 v4; // rdi
  __int64 Pool2; // rax
  __int64 v6; // r8
  _QWORD *v7; // rbx
  unsigned int v8; // edi
  PEX_RUNDOWN_REF_CACHE_AWARE CacheAwareRundownProtection; // rax
  const wchar_t *v10; // r9
  __int64 v11; // rbp
  __int64 v12; // rcx
  PDEVICE_OBJECT v13; // rcx
  unsigned int v14; // r8d
  _QWORD *v15; // r14
  _QWORD *i; // rdi
  __int64 v18; // rax
  int inserted; // eax
  __int64 v20; // r9
  unsigned int j; // edx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v22; // rcx
  __int64 v23; // rcx

  v4 = *(_QWORD *)(*(_QWORD *)a1 + 40LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      22,
      WPP_5233970d56413ab48eace6095c9c2fb5_Traceguids,
      *(unsigned int *)(a1 + 8));
  }
  Pool2 = ExAllocatePool2(64, 48, 1884508233);
  v7 = (_QWORD *)Pool2;
  if ( !Pool2 )
  {
    v8 = -1073741670;
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) >= 0 )
    {
LABEL_5:
      if ( *(_QWORD *)(a1 + 96) )
        IppCleanupIpsServiceChain(a1, *(_QWORD *)(*(_QWORD *)a1 + 40LL));
      if ( v7 )
      {
        v22 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)v7[2];
        if ( v22 )
          ExFreeCacheAwareRundownProtection(v22);
        ExFreePoolWithTag(v7, 0x70535049u);
      }
      return v8;
    }
    v10 = L"IPS service chain (IPNG)";
LABEL_29:
    McTemplateK0z_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, TCPIP_MEMORY_FAILURES, v6, v10);
    goto LABEL_5;
  }
  *(_OWORD *)(Pool2 + 24) = *a2;
  *(_QWORD *)(Pool2 + 8) = Pool2;
  *(_QWORD *)Pool2 = Pool2;
  CacheAwareRundownProtection = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x70535049u);
  v7[2] = CacheAwareRundownProtection;
  if ( !CacheAwareRundownProtection )
  {
    v8 = -1073741670;
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) >= 0 )
      goto LABEL_5;
    v10 = L"IPS service chain rundown object (IPNG)";
    goto LABEL_29;
  }
  KeEnterCriticalRegion();
  v11 = v4 + 19632;
  ExAcquirePushLockExclusiveEx(v4 + 19632, 0);
  IppDisableIpsServiceChain(v12, v7);
  v15 = (_QWORD *)(v4 + 19640);
  for ( i = *(_QWORD **)(v4 + 19640); i != v15; i = (_QWORD *)*i )
  {
    v18 = i[16];
    if ( v18 )
    {
      v14 = *(_DWORD *)(v18 + 4);
      v20 = v18 + 8;
      for ( j = 0; j < v14; ++j )
      {
        v23 = v7[3] - *(_QWORD *)v20;
        if ( !v23 )
          v23 = v7[4] - *(_QWORD *)(v20 + 8);
        if ( !v23 )
        {
          inserted = IppInsertIpsClientToServiceChain(a1, (_DWORD)v7, (_DWORD)i, *(_DWORD *)(v20 + 16), 0);
          if ( inserted >= 0 )
            goto LABEL_20;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0 )
          {
            WPP_SF_SDd(WPP_GLOBAL_Control->AttachedDevice, 23, v14, (_DWORD)i + 28, *(_DWORD *)(a1 + 8), inserted);
          }
          goto LABEL_12;
        }
        v20 += 20;
      }
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0 )
    {
      WPP_SF_DS(WPP_GLOBAL_Control->AttachedDevice, 24, v14, *(_DWORD *)(a1 + 8), (__int64)i + 28);
    }
LABEL_20:
    ;
  }
LABEL_12:
  IppEnableIpsServiceChain(v13, v7);
  ExReleasePushLockExclusiveEx(v11, 0);
  KeLeaveCriticalRegion();
  v8 = 0;
  *(_QWORD *)(a1 + 96) = v7;
  return v8;
}

```

## disassembly

```asm
0x14008a1b4  push    rbx
0x14008a1b6  push    rbp
0x14008a1b7  push    rsi
0x14008a1b8  push    rdi
0x14008a1b9  push    r13
0x14008a1bb  push    r14
0x14008a1bd  sub     rsp, 38h
0x14008a1c1  mov     rax, [rcx]
0x14008a1c4  mov     rbp, rdx
0x14008a1c7  mov     rsi, rcx
0x14008a1ca  mov     rdi, [rax+28h]
0x14008a1ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a1d5  lea     r13, WPP_GLOBAL_Control
0x14008a1dc  cmp     rcx, r13
0x14008a1df  jz      short loc_14008A1EB
0x14008a1e1  cmp     byte ptr [rcx+29h], 4
0x14008a1e5  jnb     loc_14008A36C
0x14008a1eb  mov     edx, 30h ; '0'
0x14008a1f0  mov     r14d, 70535049h
0x14008a1f6  mov     r8d, r14d
0x14008a1f9  lea     ecx, [rdx+10h]
0x14008a1fc  call    cs:__imp_ExAllocatePool2
0x14008a203  nop     dword ptr [rax+rax+00h]
0x14008a208  mov     rbx, rax
0x14008a20b  test    rax, rax
0x14008a20e  jnz     short loc_14008A241
0x14008a210  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, al
0x14008a216  mov     edi, 0C000009Ah
0x14008a21b  jl      loc_14008A397
0x14008a221  cmp     qword ptr [rsi+60h], 0
0x14008a226  jz      loc_1401CC3C3
0x14008a22c  mov     rdx, [rsi]
0x14008a22f  mov     rcx, rsi
0x14008a232  mov     rdx, [rdx+28h]
0x14008a236  call    IppCleanupIpsServiceChain
0x14008a23b  nop
0x14008a23c  jmp     loc_1401CC3C3
0x14008a241  movups  xmm0, xmmword ptr [rbp+0]
0x14008a245  mov     edx, r14d; PoolTag
0x14008a248  mov     ecx, 200h; PoolType
0x14008a24d  movdqu  xmmword ptr [rax+18h], xmm0
0x14008a252  mov     [rax+8], rbx
0x14008a256  mov     [rax], rbx
0x14008a259  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14008a260  nop     dword ptr [rax+rax+00h]
0x14008a265  mov     [rbx+10h], rax
0x14008a269  test    rax, rax
0x14008a26c  jnz     short loc_14008A287
0x14008a26e  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, al
0x14008a274  mov     edi, 0C000009Ah
0x14008a279  jge     short loc_14008A221
0x14008a27b  lea     r9, aIpsServiceChai_0; "IPS service chain rundown object (IPNG)"
0x14008a282  jmp     loc_1401CC3AA
0x14008a287  call    cs:__imp_KeEnterCriticalRegion
0x14008a28e  nop     dword ptr [rax+rax+00h]
0x14008a293  lea     rbp, [rdi+4CB0h]
0x14008a29a  xor     edx, edx
0x14008a29c  mov     rcx, rbp
0x14008a29f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14008a2a6  nop     dword ptr [rax+rax+00h]
0x14008a2ab  mov     rdx, rbx
0x14008a2ae  call    IppDisableIpsServiceChain
0x14008a2b3  lea     r14, [rdi+4CB8h]
0x14008a2ba  mov     rdi, [r14]
0x14008a2bd  cmp     rdi, r14
0x14008a2c0  jnz     short loc_14008A2FD
0x14008a2c2  mov     rdx, rbx
0x14008a2c5  call    IppEnableIpsServiceChain
0x14008a2ca  xor     edx, edx
0x14008a2cc  mov     rcx, rbp
0x14008a2cf  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14008a2d6  nop     dword ptr [rax+rax+00h]
0x14008a2db  call    cs:__imp_KeLeaveCriticalRegion
0x14008a2e2  nop     dword ptr [rax+rax+00h]
0x14008a2e7  xor     edi, edi
0x14008a2e9  mov     [rsi+60h], rbx
0x14008a2ed  mov     eax, edi
0x14008a2ef  add     rsp, 38h
0x14008a2f3  pop     r14
0x14008a2f5  pop     r13
0x14008a2f7  pop     rdi
0x14008a2f8  pop     rsi
0x14008a2f9  pop     rbp
0x14008a2fa  pop     rbx
0x14008a2fb  retn
0x14008a2fd  mov     rax, [rdi+80h]
0x14008a304  test    rax, rax
0x14008a307  jnz     loc_14008A3A3
0x14008a30d  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a314  cmp     rcx, r13
0x14008a317  jz      short loc_14008A364
0x14008a319  cmp     byte ptr [rcx+29h], 4
0x14008a31d  jb      short loc_14008A364
0x14008a31f  test    dword ptr [rcx+2Ch], 800000h
0x14008a326  jz      short loc_14008A364
0x14008a328  mov     r9d, [rsi+8]
0x14008a32c  lea     rax, [rdi+1Ch]
0x14008a330  mov     rcx, [rcx+18h]
0x14008a334  mov     edx, 18h
0x14008a339  mov     [rsp+68h+var_48], rax
0x14008a33e  call    WPP_SF_DS
0x14008a343  jmp     short loc_14008A364
0x14008a345  mov     r9d, [r9+10h]
0x14008a349  mov     r8, rdi
0x14008a34c  mov     rdx, rbx
0x14008a34f  mov     [rsp+68h+var_48], 0
0x14008a358  mov     rcx, rsi
0x14008a35b  call    IppInsertIpsClientToServiceChain
0x14008a360  test    eax, eax
0x14008a362  js      short loc_14008A3B2
0x14008a364  mov     rdi, [rdi]
0x14008a367  jmp     loc_14008A2BD
0x14008a36c  test    dword ptr [rcx+2Ch], 800000h
0x14008a373  jz      loc_14008A1EB
0x14008a379  mov     r9d, [rsi+8]
0x14008a37d  lea     r8, WPP_5233970d56413ab48eace6095c9c2fb5_Traceguids
0x14008a384  mov     rcx, [rcx+18h]
0x14008a388  mov     edx, 16h
0x14008a38d  call    WPP_SF_d
0x14008a392  jmp     loc_14008A1EB
0x14008a397  lea     r9, aIpsServiceChai_1; "IPS service chain (IPNG)"
0x14008a39e  jmp     loc_1401CC3AA
0x14008a3a3  mov     r8d, [rax+4]
0x14008a3a7  lea     r9, [rax+8]
0x14008a3ab  xor     edx, edx
0x14008a3ad  jmp     loc_1401CC3F9
0x14008a3b2  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a3b9  cmp     rcx, r13
0x14008a3bc  jz      loc_14008A2C2
0x14008a3c2  cmp     byte ptr [rcx+29h], 2
0x14008a3c6  jb      loc_14008A2C2
0x14008a3cc  test    dword ptr [rcx+2Ch], 800000h
0x14008a3d3  jz      loc_14008A2C2
0x14008a3d9  mov     rcx, [rcx+18h]
0x14008a3dd  lea     r9, [rdi+1Ch]
0x14008a3e1  mov     [rsp+68h+var_40], eax
0x14008a3e5  mov     edx, 17h
0x14008a3ea  mov     eax, [rsi+8]
0x14008a3ed  mov     dword ptr [rsp+68h+var_48], eax
0x14008a3f1  call    WPP_SF_SDd
0x14008a3f6  jmp     loc_14008A2C2
0x1401cc3aa  lea     rdx, TCPIP_MEMORY_FAILURES
0x1401cc3b1  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401cc3b8  call    McTemplateK0z_EtwWriteTransfer
0x1401cc3bd  nop
0x1401cc3be  jmp     loc_14008A221
0x1401cc3c3  test    rbx, rbx
0x1401cc3c6  jz      loc_14008A2ED
0x1401cc3cc  mov     rcx, [rbx+10h]; RunRefCacheAware
0x1401cc3d0  test    rcx, rcx
0x1401cc3d3  jz      short loc_1401CC3E1
0x1401cc3d5  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1401cc3dc  nop     dword ptr [rax+rax+00h]
0x1401cc3e1  mov     edx, r14d; Tag
0x1401cc3e4  mov     rcx, rbx; P
0x1401cc3e7  call    cs:__imp_ExFreePoolWithTag
0x1401cc3ee  nop     dword ptr [rax+rax+00h]
0x1401cc3f3  nop
0x1401cc3f4  jmp     loc_14008A2ED
0x1401cc3f9  cmp     edx, r8d
0x1401cc3fc  jnb     loc_14008A30D
0x1401cc402  mov     rcx, [rbx+18h]
0x1401cc406  sub     rcx, [r9]
0x1401cc409  jnz     short loc_1401CC413
0x1401cc40b  mov     rcx, [rbx+20h]
0x1401cc40f  sub     rcx, [r9+8]
0x1401cc413  test    rcx, rcx
0x1401cc416  jz      loc_14008A345
0x1401cc41c  add     r9, 14h
0x1401cc420  inc     edx
0x1401cc422  jmp     short loc_1401CC3F9
```

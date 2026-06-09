# NtUserFunctionalizeDisplayConfig

- ea: `0x1401da290`
- end: `0x1401da671`
- name: `NtUserFunctionalizeDisplayConfig`
- size: `993`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config`

## callees

- `0x14001bdf0`
- `0x14001c2d4`
- `0x1400325a4`
- `0x140033cf0`
- `0x14004a0d0`
- `0x14004c720`
- `0x140076b80`
- `0x1401767dc`
- `0x140181544`
- `0x140189344`
- `0x1401da290`
- `0x1402381f0`
- `0x1402bb1a0`
- `0x1402bb358`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401da4e7`
- `ntoskrnl!ProbeForRead` at `0x1401da4e7`
- `ntoskrnl!ExRaiseStatus` at `0x1401da388`
- `ntoskrnl!ExRaiseStatus` at `0x1401da3ec`
- `ntoskrnl!ExRaiseStatus` at `0x1401da42d`
- `ntoskrnl!ExRaiseStatus` at `0x1401da451`
- `ntoskrnl!ExRaiseStatus` at `0x1401da48d`
- `ntoskrnl!ExRaiseStatus` at `0x1401da5d7`
- `ntoskrnl!ExRaiseStatus` at `0x1401da5e6`
- `ntoskrnl!ExRaiseStatus` at `0x1401da388`
- `ntoskrnl!ExRaiseStatus` at `0x1401da3ec`
- `ntoskrnl!ExRaiseStatus` at `0x1401da42d`
- `ntoskrnl!ExRaiseStatus` at `0x1401da451`
- `ntoskrnl!ExRaiseStatus` at `0x1401da48d`
- `ntoskrnl!ExRaiseStatus` at `0x1401da5d7`
- `ntoskrnl!ExRaiseStatus` at `0x1401da5e6`
- `ntoskrnl!ProbeForWrite` at `0x1401da354`
- `ntoskrnl!ProbeForWrite` at `0x1401da4b7`
- `ntoskrnl!ProbeForWrite` at `0x1401da354`
- `ntoskrnl!ProbeForWrite` at `0x1401da4b7`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401da32c`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401da4c8`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401da32c`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401da4c8`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401da2f8`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401da2f8`

## pseudocode

```c
__int64 __fastcall NtUserFunctionalizeDisplayConfig(
        int a1,
        __int64 a2,
        volatile void *a3,
        _OWORD *a4,
        int a5,
        _DWORD *Address)
{
  void *v9; // r14
  int v10; // esi
  __int64 CurrentProcessWow64Process; // rax
  unsigned __int64 v12; // rcx
  unsigned int v13; // esi
  unsigned int v14; // ecx
  __int64 *i; // rdx
  __int64 *v16; // r13
  void *v17; // rcx
  unsigned int v18; // r12d
  unsigned int j; // edx
  __int64 v20; // rax
  unsigned int ULongFromUser; // [rsp+30h] [rbp-A8h] BYREF
  unsigned int v23; // [rsp+34h] [rbp-A4h]
  _DWORD v24[2]; // [rsp+38h] [rbp-A0h] BYREF
  __int64 *v25; // [rsp+40h] [rbp-98h]
  void *v26; // [rsp+48h] [rbp-90h]
  int v27; // [rsp+50h] [rbp-88h]
  int v28; // [rsp+54h] [rbp-84h]
  __int64 *v29; // [rsp+78h] [rbp-60h]
  _OWORD v30[2]; // [rsp+80h] [rbp-58h] BYREF
  __int64 v31; // [rsp+A0h] [rbp-38h] BYREF

  v9 = 0;
  v26 = 0;
  ULongFromUser = 0;
  v24[0] = -1;
  memset(v30, 0, 28);
  v24[1] = -1073741811;
  EnterLeaveCritShared::EnterLeaveCritShared(&v31, 1);
  PtiCurrent();
  if ( !*(_DWORD *)(W32GetUserGdiSessionState() + 32) )
  {
    v10 = -1073741823;
LABEL_39:
    if ( a4 && (unsigned int)DrvNeedDisplayStateCheck(v30) && !(unsigned int)DrvIsDisplayStateCurrent(1, v30) )
      v10 = -1071774921;
    goto LABEL_43;
  }
  ULongFromUser = RtlReadULongFromUser(a2);
  if ( ULongFromUser - 1 > 0x3FF )
    ExRaiseStatus(-1073741811);
  CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
  ProbeForWrite(a3, 216LL * ULongFromUser, CurrentProcessWow64Process != 0 ? 1 : 4);
  v9 = Win32AllocPoolWithQuotaZInitImpl(v12, 216LL * ULongFromUser, 0x63447355u);
  v26 = v9;
  if ( !v9 )
    ExRaiseStatus(-1073741801);
  v25 = 0;
  v29 = 0;
  v23 = 0;
  v13 = 0;
  v27 = 0;
  v14 = 0;
  for ( i = (__int64 *)a3; ; i += 27 )
  {
    v25 = i;
    v23 = v14;
    if ( v14 >= ULongFromUser )
      break;
    if ( *i < 0 )
      v27 = ++v13;
    ++v14;
  }
  if ( ULongFromUser != v13 )
    ExRaiseStatus(-1073741811);
  v16 = (__int64 *)a3;
  v25 = (__int64 *)a3;
  v17 = v9;
  v29 = (__int64 *)v9;
  v18 = 0;
  v28 = 0;
  for ( j = 0; ; ++j )
  {
    v23 = j;
    if ( j >= v13 )
      break;
    if ( *v16 < 0 )
    {
      if ( v18 >= v13 )
        ExRaiseStatus(-1073741811);
      RtlCopyVolatileMemory(v17, v16, 0xD8u);
      if ( *v29 >= 0 )
        ExRaiseStatus(-1073741790);
      v28 = ++v18;
      v17 = v29 + 27;
      v29 += 27;
      j = v23;
    }
    v16 += 27;
    v25 = v16;
  }
  if ( v18 != v13 )
    ExRaiseStatus(-1073741811);
  if ( !Address )
    ExRaiseStatus(-1073741811);
  ProbeForWrite(Address, 4u, 4u);
  if ( a4 )
  {
    v20 = PsGetCurrentProcessWow64Process();
    ProbeForRead(a4, 0x1Cu, v20 != 0 ? 1 : 4);
    v30[0] = *a4;
    *(_OWORD *)((char *)v30 + 12) = *(_OWORD *)((char *)a4 + 12);
  }
  if ( !(unsigned int)UserIsWddmConnectedSession() )
  {
    v10 = -1073741790;
    goto LABEL_39;
  }
  if ( a4 && (unsigned int)DrvNeedDisplayStateCheck(v30) && !(unsigned int)DrvIsDisplayStateCurrent(1, v30) )
  {
    v10 = -1071774921;
    goto LABEL_39;
  }
  v10 = DrvFunctionalizeDisplayConfig((unsigned int)&ULongFromUser, (_DWORD)v9, a1, a5, (__int64)v24);
  if ( v10 == -2147483643 )
    v10 = -1073741789;
  RtlCopyVolatileMemory((void *)a3, v9, 216LL * ULongFromUser);
  RtlWriteULongToUser(a2, ULongFromUser);
  *Address = v24[0];
  if ( v10 < 0 )
    goto LABEL_39;
LABEL_43:
  if ( v9 )
  {
    GreDeleteFastMutex(v9);
    v26 = 0;
  }
  UserSessionSwitchLeaveCritWithNonPaged();
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1401da290  mov     rax, rsp
0x1401da293  mov     [rax+10h], rbx
0x1401da297  mov     [rax+20h], r9
0x1401da29b  mov     [rax+18h], r8
0x1401da29f  mov     [rax+8], ecx
0x1401da2a2  push    rsi
0x1401da2a3  push    r12
0x1401da2a5  push    r13
0x1401da2a7  push    r14
0x1401da2a9  push    r15
0x1401da2ab  sub     rsp, 0B0h
0x1401da2b2  mov     r15, r9
0x1401da2b5  mov     r12, r8
0x1401da2b8  mov     rbx, rdx
0x1401da2bb  xor     r14d, r14d
0x1401da2be  mov     [rsp+0D8h+var_90], r14
0x1401da2c3  mov     [rsp+0D8h+var_A8], r14d
0x1401da2c8  mov     [rsp+0D8h+var_A0], 0FFFFFFFFh
0x1401da2d0  xorps   xmm0, xmm0
0x1401da2d3  movups  xmmword ptr [rax-58h], xmm0
0x1401da2d7  movups  xmmword ptr [rax-4Ch], xmm0
0x1401da2db  mov     r13d, 0C000000Dh
0x1401da2e1  mov     [rsp+0D8h+var_9C], r13d
0x1401da2e6  lea     edx, [r14+1]
0x1401da2ea  lea     rcx, [rax-38h]
0x1401da2ee  call    ??0EnterLeaveCritShared@@QEAA@W4HandleToObjILCheck@@@Z; EnterLeaveCritShared::EnterLeaveCritShared(HandleToObjILCheck)
0x1401da2f3  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401da2f8  call    cs:__imp_W32GetUserGdiSessionState
0x1401da2ff  nop     dword ptr [rax+rax+00h]
0x1401da304  cmp     [rax+20h], r14d
0x1401da308  jnz     short loc_1401DA313
0x1401da30a  lea     esi, [r13-0Ch]
0x1401da30e  jmp     loc_1401DA608
0x1401da313  mov     rcx, rbx
0x1401da316  call    RtlReadULongFromUser
0x1401da31b  mov     [rsp+0D8h+var_A8], eax
0x1401da31f  dec     eax
0x1401da321  cmp     eax, 3FFh
0x1401da326  ja      loc_1401DA5E3
0x1401da32c  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401da333  nop     dword ptr [rax+rax+00h]
0x1401da338  neg     rax
0x1401da33b  sbb     r8d, r8d
0x1401da33e  and     r8d, 0FFFFFFFDh
0x1401da342  add     r8d, 4; Alignment
0x1401da346  mov     eax, [rsp+0D8h+var_A8]
0x1401da34a  imul    rdx, rax, 0D8h; Length
0x1401da351  mov     rcx, r12; Address
0x1401da354  call    cs:__imp_ProbeForWrite
0x1401da35b  nop     dword ptr [rax+rax+00h]
0x1401da360  mov     eax, [rsp+0D8h+var_A8]
0x1401da364  imul    rdx, rax, 0D8h; unsigned __int64
0x1401da36b  mov     r8d, 63447355h; unsigned int
0x1401da371  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401da376  mov     r14, rax
0x1401da379  mov     [rsp+0D8h+var_90], rax
0x1401da37e  test    rax, rax
0x1401da381  jnz     short loc_1401DA394
0x1401da383  mov     ecx, 0C0000017h; Status
0x1401da388  call    cs:__imp_ExRaiseStatus
0x1401da394  mov     [rsp+0D8h+var_98], 0
0x1401da39d  mov     [rsp+0D8h+var_60], 0
0x1401da3a6  mov     [rsp+0D8h+var_A4], 0
0x1401da3ae  xor     esi, esi
0x1401da3b0  mov     [rsp+0D8h+var_88], esi
0x1401da3b4  xor     ecx, ecx
0x1401da3b6  mov     rdx, r12
0x1401da3b9  mov     r8d, 0D8h; Size
0x1401da3bf  mov     [rsp+0D8h+var_98], rdx
0x1401da3c4  mov     [rsp+0D8h+var_A4], ecx
0x1401da3c8  cmp     ecx, [rsp+0D8h+var_A8]
0x1401da3cc  jnb     short loc_1401DA3E3
0x1401da3ce  mov     rax, [rdx]
0x1401da3d1  test    rax, rax
0x1401da3d4  jns     short loc_1401DA3DC
0x1401da3d6  inc     esi
0x1401da3d8  mov     [rsp+0D8h+var_88], esi
0x1401da3dc  inc     ecx
0x1401da3de  add     rdx, r8
0x1401da3e1  jmp     short loc_1401DA3BF
0x1401da3e3  cmp     [rsp+0D8h+var_A8], esi
0x1401da3e7  jz      short loc_1401DA3F8
0x1401da3e9  mov     ecx, r13d; Status
0x1401da3ec  call    cs:__imp_ExRaiseStatus
0x1401da3f8  mov     r13, r12
0x1401da3fb  mov     [rsp+0D8h+var_98], r12
0x1401da400  mov     rcx, r14; void *
0x1401da403  mov     [rsp+0D8h+var_60], rcx
0x1401da408  xor     r12d, r12d
0x1401da40b  mov     [rsp+0D8h+var_84], r12d
0x1401da410  xor     edx, edx
0x1401da412  mov     [rsp+0D8h+var_A4], edx
0x1401da416  cmp     edx, esi
0x1401da418  jnb     short loc_1401DA483
0x1401da41a  mov     rax, [r13+0]
0x1401da41e  test    rax, rax
0x1401da421  jns     short loc_1401DA477
0x1401da423  cmp     r12d, esi
0x1401da426  jb      short loc_1401DA439
0x1401da428  mov     ecx, 0C000000Dh; Status
0x1401da42d  call    cs:__imp_ExRaiseStatus
0x1401da439  mov     rdx, r13; Src
0x1401da43c  call    RtlCopyVolatileMemory
0x1401da441  mov     rcx, [rsp+0D8h+var_60]
0x1401da446  cmp     qword ptr [rcx], 0
0x1401da44a  jl      short loc_1401DA45D
0x1401da44c  mov     ecx, 0C0000022h; Status
0x1401da451  call    cs:__imp_ExRaiseStatus
0x1401da45d  inc     r12d
0x1401da460  mov     [rsp+0D8h+var_84], r12d
0x1401da465  mov     r8d, 0D8h
0x1401da46b  add     rcx, r8
0x1401da46e  mov     [rsp+0D8h+var_60], rcx
0x1401da473  mov     edx, [rsp+0D8h+var_A4]
0x1401da477  inc     edx
0x1401da479  add     r13, r8
0x1401da47c  mov     [rsp+0D8h+var_98], r13
0x1401da481  jmp     short loc_1401DA412
0x1401da483  cmp     r12d, esi
0x1401da486  jz      short loc_1401DA499
0x1401da488  mov     ecx, 0C000000Dh; Status
0x1401da48d  call    cs:__imp_ExRaiseStatus
0x1401da499  mov     r12, [rsp+0D8h+Address]
0x1401da4a1  test    r12, r12
0x1401da4a4  jz      loc_1401DA5D2
0x1401da4aa  mov     esi, 4
0x1401da4af  mov     r8d, esi; Alignment
0x1401da4b2  mov     edx, esi; Length
0x1401da4b4  mov     rcx, r12; Address
0x1401da4b7  call    cs:__imp_ProbeForWrite
0x1401da4be  nop     dword ptr [rax+rax+00h]
0x1401da4c3  test    r15, r15
0x1401da4c6  jz      short loc_1401DA50C
0x1401da4c8  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401da4cf  nop     dword ptr [rax+rax+00h]
0x1401da4d4  neg     rax
0x1401da4d7  sbb     r8d, r8d
0x1401da4da  and     r8d, 0FFFFFFFDh
0x1401da4de  add     r8d, esi; Alignment
0x1401da4e1  lea     edx, [rsi+18h]; Length
0x1401da4e4  mov     rcx, r15; Address
0x1401da4e7  call    cs:__imp_ProbeForRead
0x1401da4ee  nop     dword ptr [rax+rax+00h]
0x1401da4f3  movups  xmm0, xmmword ptr [r15]
0x1401da4f7  movups  [rsp+0D8h+var_58], xmm0
0x1401da4ff  movups  xmm1, xmmword ptr [r15+0Ch]
0x1401da504  movups  [rsp+0D8h+var_58+0Ch], xmm1
0x1401da50c  call    UserIsWddmConnectedSession
0x1401da511  test    eax, eax
0x1401da513  jnz     short loc_1401DA51F
0x1401da515  mov     esi, 0C0000022h
0x1401da51a  jmp     loc_1401DA608
0x1401da51f  test    r15, r15
0x1401da522  jz      short loc_1401DA557
0x1401da524  lea     rcx, [rsp+0D8h+var_58]
0x1401da52c  call    DrvNeedDisplayStateCheck
0x1401da531  test    eax, eax
0x1401da533  jz      short loc_1401DA557
0x1401da535  lea     rdx, [rsp+0D8h+var_58]
0x1401da53d  mov     ecx, 1
0x1401da542  call    DrvIsDisplayStateCurrent
0x1401da547  test    eax, eax
0x1401da549  jnz     short loc_1401DA557
0x1401da54b  mov     ebx, 0C01E0337h
0x1401da550  mov     esi, ebx
0x1401da552  jmp     loc_1401DA60D
0x1401da557  lea     rax, [rsp+0D8h+var_A0]
0x1401da55c  mov     [rsp+0D8h+var_B8], rax
0x1401da561  mov     r9, [rsp+0D8h+arg_20]
0x1401da569  mov     r8d, [rsp+0D8h+arg_0]
0x1401da571  mov     rdx, r14
0x1401da574  lea     rcx, [rsp+0D8h+var_A8]
0x1401da579  call    DrvFunctionalizeDisplayConfig
0x1401da57e  mov     esi, eax
0x1401da580  mov     eax, 0C0000023h
0x1401da585  cmp     esi, 80000005h
0x1401da58b  cmovz   esi, eax
0x1401da58e  mov     eax, [rsp+0D8h+var_A8]
0x1401da592  imul    r8, rax, 0D8h; Size
0x1401da599  mov     rdx, r14; Src
0x1401da59c  mov     rcx, [rsp+0D8h+arg_10]; void *
0x1401da5a4  call    RtlCopyVolatileMemory
0x1401da5a9  mov     edx, [rsp+0D8h+var_A8]
0x1401da5ad  mov     rcx, rbx
0x1401da5b0  call    RtlWriteULongToUser
0x1401da5b5  mov     eax, [rsp+0D8h+var_A0]
0x1401da5b9  mov     [r12], eax
0x1401da5bd  jmp     short loc_1401DA604
0x1401da5bf  mov     esi, [rsp+0D8h+var_9C]
0x1401da5c3  mov     r15, [rsp+0D8h+arg_18]
0x1401da5cb  mov     r14, [rsp+0D8h+var_90]
0x1401da5d0  jmp     short loc_1401DA604
0x1401da5d2  mov     ecx, 0C000000Dh; Status
0x1401da5d7  call    cs:__imp_ExRaiseStatus
0x1401da5e3  mov     ecx, r13d; Status
0x1401da5e6  call    cs:__imp_ExRaiseStatus
0x1401da5f3  mov     esi, [rsp+0D8h+var_9C]
0x1401da5f7  mov     r15, [rsp+0D8h+arg_18]
0x1401da5ff  mov     r14, [rsp+0D8h+var_90]
0x1401da604  test    esi, esi
0x1401da606  jns     short loc_1401DA63A
0x1401da608  mov     ebx, 0C01E0337h
0x1401da60d  test    r15, r15
0x1401da610  jz      short loc_1401DA63A
0x1401da612  lea     rcx, [rsp+0D8h+var_58]
0x1401da61a  call    DrvNeedDisplayStateCheck
0x1401da61f  test    eax, eax
0x1401da621  jz      short loc_1401DA63A
0x1401da623  lea     rdx, [rsp+0D8h+var_58]
0x1401da62b  mov     ecx, 1
0x1401da630  call    DrvIsDisplayStateCurrent
0x1401da635  test    eax, eax
0x1401da637  cmovz   esi, ebx
0x1401da63a  test    r14, r14
0x1401da63d  jz      short loc_1401DA650
0x1401da63f  mov     rcx, r14; Buffer
0x1401da642  call    GreDeleteFastMutex
0x1401da647  mov     [rsp+0D8h+var_90], 0
0x1401da650  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401da655  mov     eax, esi
0x1401da657  mov     rbx, [rsp+0D8h+arg_8]
0x1401da65f  add     rsp, 0B0h
0x1401da666  pop     r15
0x1401da668  pop     r14
0x1401da66a  pop     r13
0x1401da66c  pop     r12
0x1401da66e  pop     rsi
0x1401da66f  retn
0x140239b43  push    rbp
0x140239b45  sub     rsp, 30h
0x140239b49  mov     rbp, rdx
0x140239b4c  mov     rax, [rcx]
0x140239b4f  mov     ecx, [rax]
0x140239b51  mov     [rbp+68h], ecx
0x140239b54  mov     ecx, [rbp+68h]
0x140239b57  call    SetLastNtError
0x140239b5c  mov     dword ptr [rbp+70h], 1
0x140239b63  mov     eax, [rbp+70h]
0x140239b66  add     rsp, 30h
0x140239b6a  pop     rbp
0x140239b6b  retn
0x140239b6d  push    rbp
0x140239b6f  sub     rsp, 30h
0x140239b73  mov     rbp, rdx
0x140239b76  mov     rax, [rcx]
0x140239b79  mov     ecx, [rax]
0x140239b7b  mov     [rbp+58h], ecx
0x140239b7e  mov     ecx, [rbp+58h]
0x140239b81  call    SetLastNtError
0x140239b86  mov     dword ptr [rbp+60h], 1
0x140239b8d  mov     eax, [rbp+60h]
0x140239b90  add     rsp, 30h
0x140239b94  pop     rbp
0x140239b95  retn
```

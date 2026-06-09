# NtUserFunctionalizeDisplayConfig

- ea: `0x1401dadd0`
- end: `0x1401db1b1`
- name: `NtUserFunctionalizeDisplayConfig`
- size: `993`
- prototype: `__int64 __fastcall(int, __int64, volatile void *, _OWORD *, int, _DWORD *Address)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config`

## callees

- `0x140029710`
- `0x140029bf4`
- `0x14004dfb0`
- `0x14006e970`
- `0x14006f3a4`
- `0x14007b930`
- `0x14007df80`
- `0x14017847c`
- `0x1401830b4`
- `0x14018ac84`
- `0x1401dadd0`
- `0x140238970`
- `0x1402bb1a0`
- `0x1402bb358`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401db027`
- `ntoskrnl!ProbeForRead` at `0x1401db027`
- `ntoskrnl!ExRaiseStatus` at `0x1401daec8`
- `ntoskrnl!ExRaiseStatus` at `0x1401daf2c`
- `ntoskrnl!ExRaiseStatus` at `0x1401daf6d`
- `ntoskrnl!ExRaiseStatus` at `0x1401daf91`
- `ntoskrnl!ExRaiseStatus` at `0x1401dafcd`
- `ntoskrnl!ExRaiseStatus` at `0x1401db117`
- `ntoskrnl!ExRaiseStatus` at `0x1401db126`
- `ntoskrnl!ExRaiseStatus` at `0x1401daec8`
- `ntoskrnl!ExRaiseStatus` at `0x1401daf2c`
- `ntoskrnl!ExRaiseStatus` at `0x1401daf6d`
- `ntoskrnl!ExRaiseStatus` at `0x1401daf91`
- `ntoskrnl!ExRaiseStatus` at `0x1401dafcd`
- `ntoskrnl!ExRaiseStatus` at `0x1401db117`
- `ntoskrnl!ExRaiseStatus` at `0x1401db126`
- `ntoskrnl!ProbeForWrite` at `0x1401dae94`
- `ntoskrnl!ProbeForWrite` at `0x1401daff7`
- `ntoskrnl!ProbeForWrite` at `0x1401dae94`
- `ntoskrnl!ProbeForWrite` at `0x1401daff7`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dae6c`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401db008`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dae6c`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401db008`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401dae38`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401dae38`

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
  __int64 v10; // rcx
  int v11; // esi
  __int64 CurrentProcessWow64Process; // rax
  unsigned __int64 v13; // rcx
  unsigned int v14; // esi
  unsigned int v15; // ecx
  __int64 *i; // rdx
  __int64 *v17; // r13
  void *v18; // rcx
  unsigned int v19; // r12d
  unsigned int j; // edx
  __int64 v21; // rax
  unsigned int ULongFromUser; // [rsp+30h] [rbp-A8h] BYREF
  unsigned int v24; // [rsp+34h] [rbp-A4h]
  _DWORD v25[2]; // [rsp+38h] [rbp-A0h] BYREF
  __int64 *v26; // [rsp+40h] [rbp-98h]
  void *v27; // [rsp+48h] [rbp-90h]
  int v28; // [rsp+50h] [rbp-88h]
  int v29; // [rsp+54h] [rbp-84h]
  __int64 *v30; // [rsp+78h] [rbp-60h]
  _OWORD v31[2]; // [rsp+80h] [rbp-58h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-38h] BYREF

  v9 = 0;
  v27 = 0;
  ULongFromUser = 0;
  v25[0] = -1;
  memset(v31, 0, 28);
  v25[1] = -1073741811;
  EnterLeaveCritShared::EnterLeaveCritShared(&v32, 1);
  PtiCurrent();
  if ( !*(_DWORD *)(W32GetUserGdiSessionState() + 32) )
  {
    v11 = -1073741823;
LABEL_39:
    if ( a4 && (unsigned int)DrvNeedDisplayStateCheck(v31) && !(unsigned int)DrvIsDisplayStateCurrent(1, v31) )
      v11 = -1071774921;
    goto LABEL_43;
  }
  ULongFromUser = RtlReadULongFromUser(a2);
  if ( ULongFromUser - 1 > 0x3FF )
    ExRaiseStatus(-1073741811);
  CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
  ProbeForWrite(a3, 216LL * ULongFromUser, CurrentProcessWow64Process != 0 ? 1 : 4);
  v9 = Win32AllocPoolWithQuotaZInitImpl(v13, 216LL * ULongFromUser, 0x63447355u);
  v27 = v9;
  if ( !v9 )
    ExRaiseStatus(-1073741801);
  v26 = 0;
  v30 = 0;
  v24 = 0;
  v14 = 0;
  v28 = 0;
  v15 = 0;
  for ( i = (__int64 *)a3; ; i += 27 )
  {
    v26 = i;
    v24 = v15;
    if ( v15 >= ULongFromUser )
      break;
    if ( *i < 0 )
      v28 = ++v14;
    ++v15;
  }
  if ( ULongFromUser != v14 )
    ExRaiseStatus(-1073741811);
  v17 = (__int64 *)a3;
  v26 = (__int64 *)a3;
  v18 = v9;
  v30 = (__int64 *)v9;
  v19 = 0;
  v29 = 0;
  for ( j = 0; ; ++j )
  {
    v24 = j;
    if ( j >= v14 )
      break;
    if ( *v17 < 0 )
    {
      if ( v19 >= v14 )
        ExRaiseStatus(-1073741811);
      RtlCopyVolatileMemory(v18, v17, 0xD8u);
      if ( *v30 >= 0 )
        ExRaiseStatus(-1073741790);
      v29 = ++v19;
      v18 = v30 + 27;
      v30 += 27;
      j = v24;
    }
    v17 += 27;
    v26 = v17;
  }
  if ( v19 != v14 )
    ExRaiseStatus(-1073741811);
  if ( !Address )
    ExRaiseStatus(-1073741811);
  ProbeForWrite(Address, 4u, 4u);
  if ( a4 )
  {
    v21 = PsGetCurrentProcessWow64Process();
    ProbeForRead(a4, 0x1Cu, v21 != 0 ? 1 : 4);
    v31[0] = *a4;
    *(_OWORD *)((char *)v31 + 12) = *(_OWORD *)((char *)a4 + 12);
  }
  if ( !(unsigned int)UserIsWddmConnectedSession() )
  {
    v11 = -1073741790;
    goto LABEL_39;
  }
  if ( a4 && (unsigned int)DrvNeedDisplayStateCheck(v31) && !(unsigned int)DrvIsDisplayStateCurrent(1, v31) )
  {
    v11 = -1071774921;
    goto LABEL_39;
  }
  v11 = DrvFunctionalizeDisplayConfig((unsigned int)&ULongFromUser, (_DWORD)v9, a1, a5, (__int64)v25);
  if ( v11 == -2147483643 )
    v11 = -1073741789;
  RtlCopyVolatileMemory((void *)a3, v9, 216LL * ULongFromUser);
  RtlWriteULongToUser(a2, ULongFromUser);
  *Address = v25[0];
  if ( v11 < 0 )
    goto LABEL_39;
LABEL_43:
  if ( v9 )
  {
    GreDeleteFastMutex(v9);
    v27 = 0;
  }
  UserSessionSwitchLeaveCritWithNonPaged(v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1401dadd0  mov     rax, rsp
0x1401dadd3  mov     [rax+10h], rbx
0x1401dadd7  mov     [rax+20h], r9
0x1401daddb  mov     [rax+18h], r8
0x1401daddf  mov     [rax+8], ecx
0x1401dade2  push    rsi
0x1401dade3  push    r12
0x1401dade5  push    r13
0x1401dade7  push    r14
0x1401dade9  push    r15
0x1401dadeb  sub     rsp, 0B0h
0x1401dadf2  mov     r15, r9
0x1401dadf5  mov     r12, r8
0x1401dadf8  mov     rbx, rdx
0x1401dadfb  xor     r14d, r14d
0x1401dadfe  mov     [rsp+0D8h+var_90], r14
0x1401dae03  mov     [rsp+0D8h+var_A8], r14d
0x1401dae08  mov     [rsp+0D8h+var_A0], 0FFFFFFFFh
0x1401dae10  xorps   xmm0, xmm0
0x1401dae13  movups  xmmword ptr [rax-58h], xmm0
0x1401dae17  movups  xmmword ptr [rax-4Ch], xmm0
0x1401dae1b  mov     r13d, 0C000000Dh
0x1401dae21  mov     [rsp+0D8h+var_9C], r13d
0x1401dae26  lea     edx, [r14+1]
0x1401dae2a  lea     rcx, [rax-38h]
0x1401dae2e  call    ??0EnterLeaveCritShared@@QEAA@W4HandleToObjILCheck@@@Z; EnterLeaveCritShared::EnterLeaveCritShared(HandleToObjILCheck)
0x1401dae33  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401dae38  call    cs:__imp_W32GetUserGdiSessionState
0x1401dae3f  nop     dword ptr [rax+rax+00h]
0x1401dae44  cmp     [rax+20h], r14d
0x1401dae48  jnz     short loc_1401DAE53
0x1401dae4a  lea     esi, [r13-0Ch]
0x1401dae4e  jmp     loc_1401DB148
0x1401dae53  mov     rcx, rbx
0x1401dae56  call    RtlReadULongFromUser
0x1401dae5b  mov     [rsp+0D8h+var_A8], eax
0x1401dae5f  dec     eax
0x1401dae61  cmp     eax, 3FFh
0x1401dae66  ja      loc_1401DB123
0x1401dae6c  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401dae73  nop     dword ptr [rax+rax+00h]
0x1401dae78  neg     rax
0x1401dae7b  sbb     r8d, r8d
0x1401dae7e  and     r8d, 0FFFFFFFDh
0x1401dae82  add     r8d, 4; Alignment
0x1401dae86  mov     eax, [rsp+0D8h+var_A8]
0x1401dae8a  imul    rdx, rax, 0D8h; Length
0x1401dae91  mov     rcx, r12; Address
0x1401dae94  call    cs:__imp_ProbeForWrite
0x1401dae9b  nop     dword ptr [rax+rax+00h]
0x1401daea0  mov     eax, [rsp+0D8h+var_A8]
0x1401daea4  imul    rdx, rax, 0D8h; unsigned __int64
0x1401daeab  mov     r8d, 63447355h; unsigned int
0x1401daeb1  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401daeb6  mov     r14, rax
0x1401daeb9  mov     [rsp+0D8h+var_90], rax
0x1401daebe  test    rax, rax
0x1401daec1  jnz     short loc_1401DAED4
0x1401daec3  mov     ecx, 0C0000017h; Status
0x1401daec8  call    cs:__imp_ExRaiseStatus
0x1401daed4  mov     [rsp+0D8h+var_98], 0
0x1401daedd  mov     [rsp+0D8h+var_60], 0
0x1401daee6  mov     [rsp+0D8h+var_A4], 0
0x1401daeee  xor     esi, esi
0x1401daef0  mov     [rsp+0D8h+var_88], esi
0x1401daef4  xor     ecx, ecx
0x1401daef6  mov     rdx, r12
0x1401daef9  mov     r8d, 0D8h; Size
0x1401daeff  mov     [rsp+0D8h+var_98], rdx
0x1401daf04  mov     [rsp+0D8h+var_A4], ecx
0x1401daf08  cmp     ecx, [rsp+0D8h+var_A8]
0x1401daf0c  jnb     short loc_1401DAF23
0x1401daf0e  mov     rax, [rdx]
0x1401daf11  test    rax, rax
0x1401daf14  jns     short loc_1401DAF1C
0x1401daf16  inc     esi
0x1401daf18  mov     [rsp+0D8h+var_88], esi
0x1401daf1c  inc     ecx
0x1401daf1e  add     rdx, r8
0x1401daf21  jmp     short loc_1401DAEFF
0x1401daf23  cmp     [rsp+0D8h+var_A8], esi
0x1401daf27  jz      short loc_1401DAF38
0x1401daf29  mov     ecx, r13d; Status
0x1401daf2c  call    cs:__imp_ExRaiseStatus
0x1401daf38  mov     r13, r12
0x1401daf3b  mov     [rsp+0D8h+var_98], r12
0x1401daf40  mov     rcx, r14; void *
0x1401daf43  mov     [rsp+0D8h+var_60], rcx
0x1401daf48  xor     r12d, r12d
0x1401daf4b  mov     [rsp+0D8h+var_84], r12d
0x1401daf50  xor     edx, edx
0x1401daf52  mov     [rsp+0D8h+var_A4], edx
0x1401daf56  cmp     edx, esi
0x1401daf58  jnb     short loc_1401DAFC3
0x1401daf5a  mov     rax, [r13+0]
0x1401daf5e  test    rax, rax
0x1401daf61  jns     short loc_1401DAFB7
0x1401daf63  cmp     r12d, esi
0x1401daf66  jb      short loc_1401DAF79
0x1401daf68  mov     ecx, 0C000000Dh; Status
0x1401daf6d  call    cs:__imp_ExRaiseStatus
0x1401daf79  mov     rdx, r13; Src
0x1401daf7c  call    RtlCopyVolatileMemory
0x1401daf81  mov     rcx, [rsp+0D8h+var_60]
0x1401daf86  cmp     qword ptr [rcx], 0
0x1401daf8a  jl      short loc_1401DAF9D
0x1401daf8c  mov     ecx, 0C0000022h; Status
0x1401daf91  call    cs:__imp_ExRaiseStatus
0x1401daf9d  inc     r12d
0x1401dafa0  mov     [rsp+0D8h+var_84], r12d
0x1401dafa5  mov     r8d, 0D8h
0x1401dafab  add     rcx, r8
0x1401dafae  mov     [rsp+0D8h+var_60], rcx
0x1401dafb3  mov     edx, [rsp+0D8h+var_A4]
0x1401dafb7  inc     edx
0x1401dafb9  add     r13, r8
0x1401dafbc  mov     [rsp+0D8h+var_98], r13
0x1401dafc1  jmp     short loc_1401DAF52
0x1401dafc3  cmp     r12d, esi
0x1401dafc6  jz      short loc_1401DAFD9
0x1401dafc8  mov     ecx, 0C000000Dh; Status
0x1401dafcd  call    cs:__imp_ExRaiseStatus
0x1401dafd9  mov     r12, [rsp+0D8h+Address]
0x1401dafe1  test    r12, r12
0x1401dafe4  jz      loc_1401DB112
0x1401dafea  mov     esi, 4
0x1401dafef  mov     r8d, esi; Alignment
0x1401daff2  mov     edx, esi; Length
0x1401daff4  mov     rcx, r12; Address
0x1401daff7  call    cs:__imp_ProbeForWrite
0x1401daffe  nop     dword ptr [rax+rax+00h]
0x1401db003  test    r15, r15
0x1401db006  jz      short loc_1401DB04C
0x1401db008  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401db00f  nop     dword ptr [rax+rax+00h]
0x1401db014  neg     rax
0x1401db017  sbb     r8d, r8d
0x1401db01a  and     r8d, 0FFFFFFFDh
0x1401db01e  add     r8d, esi; Alignment
0x1401db021  lea     edx, [rsi+18h]; Length
0x1401db024  mov     rcx, r15; Address
0x1401db027  call    cs:__imp_ProbeForRead
0x1401db02e  nop     dword ptr [rax+rax+00h]
0x1401db033  movups  xmm0, xmmword ptr [r15]
0x1401db037  movups  [rsp+0D8h+var_58], xmm0
0x1401db03f  movups  xmm1, xmmword ptr [r15+0Ch]
0x1401db044  movups  [rsp+0D8h+var_58+0Ch], xmm1
0x1401db04c  call    UserIsWddmConnectedSession
0x1401db051  test    eax, eax
0x1401db053  jnz     short loc_1401DB05F
0x1401db055  mov     esi, 0C0000022h
0x1401db05a  jmp     loc_1401DB148
0x1401db05f  test    r15, r15
0x1401db062  jz      short loc_1401DB097
0x1401db064  lea     rcx, [rsp+0D8h+var_58]
0x1401db06c  call    DrvNeedDisplayStateCheck
0x1401db071  test    eax, eax
0x1401db073  jz      short loc_1401DB097
0x1401db075  lea     rdx, [rsp+0D8h+var_58]
0x1401db07d  mov     ecx, 1
0x1401db082  call    DrvIsDisplayStateCurrent
0x1401db087  test    eax, eax
0x1401db089  jnz     short loc_1401DB097
0x1401db08b  mov     ebx, 0C01E0337h
0x1401db090  mov     esi, ebx
0x1401db092  jmp     loc_1401DB14D
0x1401db097  lea     rax, [rsp+0D8h+var_A0]
0x1401db09c  mov     [rsp+0D8h+var_B8], rax
0x1401db0a1  mov     r9, [rsp+0D8h+arg_20]
0x1401db0a9  mov     r8d, [rsp+0D8h+arg_0]
0x1401db0b1  mov     rdx, r14
0x1401db0b4  lea     rcx, [rsp+0D8h+var_A8]
0x1401db0b9  call    DrvFunctionalizeDisplayConfig
0x1401db0be  mov     esi, eax
0x1401db0c0  mov     eax, 0C0000023h
0x1401db0c5  cmp     esi, 80000005h
0x1401db0cb  cmovz   esi, eax
0x1401db0ce  mov     eax, [rsp+0D8h+var_A8]
0x1401db0d2  imul    r8, rax, 0D8h; Size
0x1401db0d9  mov     rdx, r14; Src
0x1401db0dc  mov     rcx, [rsp+0D8h+arg_10]; void *
0x1401db0e4  call    RtlCopyVolatileMemory
0x1401db0e9  mov     edx, [rsp+0D8h+var_A8]
0x1401db0ed  mov     rcx, rbx
0x1401db0f0  call    RtlWriteULongToUser
0x1401db0f5  mov     eax, [rsp+0D8h+var_A0]
0x1401db0f9  mov     [r12], eax
0x1401db0fd  jmp     short loc_1401DB144
0x1401db0ff  mov     esi, [rsp+0D8h+var_9C]
0x1401db103  mov     r15, [rsp+0D8h+arg_18]
0x1401db10b  mov     r14, [rsp+0D8h+var_90]
0x1401db110  jmp     short loc_1401DB144
0x1401db112  mov     ecx, 0C000000Dh; Status
0x1401db117  call    cs:__imp_ExRaiseStatus
0x1401db123  mov     ecx, r13d; Status
0x1401db126  call    cs:__imp_ExRaiseStatus
0x1401db133  mov     esi, [rsp+0D8h+var_9C]
0x1401db137  mov     r15, [rsp+0D8h+arg_18]
0x1401db13f  mov     r14, [rsp+0D8h+var_90]
0x1401db144  test    esi, esi
0x1401db146  jns     short loc_1401DB17A
0x1401db148  mov     ebx, 0C01E0337h
0x1401db14d  test    r15, r15
0x1401db150  jz      short loc_1401DB17A
0x1401db152  lea     rcx, [rsp+0D8h+var_58]
0x1401db15a  call    DrvNeedDisplayStateCheck
0x1401db15f  test    eax, eax
0x1401db161  jz      short loc_1401DB17A
0x1401db163  lea     rdx, [rsp+0D8h+var_58]
0x1401db16b  mov     ecx, 1
0x1401db170  call    DrvIsDisplayStateCurrent
0x1401db175  test    eax, eax
0x1401db177  cmovz   esi, ebx
0x1401db17a  test    r14, r14
0x1401db17d  jz      short loc_1401DB190
0x1401db17f  mov     rcx, r14; Buffer
0x1401db182  call    GreDeleteFastMutex
0x1401db187  mov     [rsp+0D8h+var_90], 0
0x1401db190  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401db195  mov     eax, esi
0x1401db197  mov     rbx, [rsp+0D8h+arg_8]
0x1401db19f  add     rsp, 0B0h
0x1401db1a6  pop     r15
0x1401db1a8  pop     r14
0x1401db1aa  pop     r13
0x1401db1ac  pop     r12
0x1401db1ae  pop     rsi
0x1401db1af  retn
0x14023a2e6  push    rbp
0x14023a2e8  sub     rsp, 30h
0x14023a2ec  mov     rbp, rdx
0x14023a2ef  mov     rax, [rcx]
0x14023a2f2  mov     ecx, [rax]
0x14023a2f4  mov     [rbp+68h], ecx
0x14023a2f7  mov     ecx, [rbp+68h]
0x14023a2fa  call    SetLastNtError
0x14023a2ff  mov     dword ptr [rbp+70h], 1
0x14023a306  mov     eax, [rbp+70h]
0x14023a309  add     rsp, 30h
0x14023a30d  pop     rbp
0x14023a30e  retn
0x14023a310  push    rbp
0x14023a312  sub     rsp, 30h
0x14023a316  mov     rbp, rdx
0x14023a319  mov     rax, [rcx]
0x14023a31c  mov     ecx, [rax]
0x14023a31e  mov     [rbp+58h], ecx
0x14023a321  mov     ecx, [rbp+58h]
0x14023a324  call    SetLastNtError
0x14023a329  mov     dword ptr [rbp+60h], 1
0x14023a330  mov     eax, [rbp+60h]
0x14023a333  add     rsp, 30h
0x14023a337  pop     rbp
0x14023a338  retn
```

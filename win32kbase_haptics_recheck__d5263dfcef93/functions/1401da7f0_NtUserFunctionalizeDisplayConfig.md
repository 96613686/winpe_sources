# NtUserFunctionalizeDisplayConfig

- ea: `0x1401da7f0`
- end: `0x1401dabd1`
- name: `NtUserFunctionalizeDisplayConfig`
- size: `993`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config`

## callees

- `0x140012c80`
- `0x140013164`
- `0x140029324`
- `0x14002aa70`
- `0x1400411c0`
- `0x140043810`
- `0x1400759e0`
- `0x140175a7c`
- `0x140180bf4`
- `0x1401881e4`
- `0x1401da7f0`
- `0x140238ba0`
- `0x1402bd244`
- `0x1402bd3fc`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401daa47`
- `ntoskrnl!ProbeForRead` at `0x1401daa47`
- `ntoskrnl!ExRaiseStatus` at `0x1401da8e8`
- `ntoskrnl!ExRaiseStatus` at `0x1401da94c`
- `ntoskrnl!ExRaiseStatus` at `0x1401da98d`
- `ntoskrnl!ExRaiseStatus` at `0x1401da9b1`
- `ntoskrnl!ExRaiseStatus` at `0x1401da9ed`
- `ntoskrnl!ExRaiseStatus` at `0x1401dab37`
- `ntoskrnl!ExRaiseStatus` at `0x1401dab46`
- `ntoskrnl!ExRaiseStatus` at `0x1401da8e8`
- `ntoskrnl!ExRaiseStatus` at `0x1401da94c`
- `ntoskrnl!ExRaiseStatus` at `0x1401da98d`
- `ntoskrnl!ExRaiseStatus` at `0x1401da9b1`
- `ntoskrnl!ExRaiseStatus` at `0x1401da9ed`
- `ntoskrnl!ExRaiseStatus` at `0x1401dab37`
- `ntoskrnl!ExRaiseStatus` at `0x1401dab46`
- `ntoskrnl!ProbeForWrite` at `0x1401da8b4`
- `ntoskrnl!ProbeForWrite` at `0x1401daa17`
- `ntoskrnl!ProbeForWrite` at `0x1401da8b4`
- `ntoskrnl!ProbeForWrite` at `0x1401daa17`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401da88c`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401daa28`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401da88c`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401daa28`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401da858`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401da858`

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
0x1401da7f0  mov     rax, rsp
0x1401da7f3  mov     [rax+10h], rbx
0x1401da7f7  mov     [rax+20h], r9
0x1401da7fb  mov     [rax+18h], r8
0x1401da7ff  mov     [rax+8], ecx
0x1401da802  push    rsi
0x1401da803  push    r12
0x1401da805  push    r13
0x1401da807  push    r14
0x1401da809  push    r15
0x1401da80b  sub     rsp, 0B0h
0x1401da812  mov     r15, r9
0x1401da815  mov     r12, r8
0x1401da818  mov     rbx, rdx
0x1401da81b  xor     r14d, r14d
0x1401da81e  mov     [rsp+0D8h+var_90], r14
0x1401da823  mov     [rsp+0D8h+var_A8], r14d
0x1401da828  mov     [rsp+0D8h+var_A0], 0FFFFFFFFh
0x1401da830  xorps   xmm0, xmm0
0x1401da833  movups  xmmword ptr [rax-58h], xmm0
0x1401da837  movups  xmmword ptr [rax-4Ch], xmm0
0x1401da83b  mov     r13d, 0C000000Dh
0x1401da841  mov     [rsp+0D8h+var_9C], r13d
0x1401da846  lea     edx, [r14+1]
0x1401da84a  lea     rcx, [rax-38h]
0x1401da84e  call    ??0EnterLeaveCritShared@@QEAA@W4HandleToObjILCheck@@@Z; EnterLeaveCritShared::EnterLeaveCritShared(HandleToObjILCheck)
0x1401da853  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401da858  call    cs:__imp_W32GetUserGdiSessionState
0x1401da85f  nop     dword ptr [rax+rax+00h]
0x1401da864  cmp     [rax+20h], r14d
0x1401da868  jnz     short loc_1401DA873
0x1401da86a  lea     esi, [r13-0Ch]
0x1401da86e  jmp     loc_1401DAB68
0x1401da873  mov     rcx, rbx
0x1401da876  call    RtlReadULongFromUser
0x1401da87b  mov     [rsp+0D8h+var_A8], eax
0x1401da87f  dec     eax
0x1401da881  cmp     eax, 3FFh
0x1401da886  ja      loc_1401DAB43
0x1401da88c  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401da893  nop     dword ptr [rax+rax+00h]
0x1401da898  neg     rax
0x1401da89b  sbb     r8d, r8d
0x1401da89e  and     r8d, 0FFFFFFFDh
0x1401da8a2  add     r8d, 4; Alignment
0x1401da8a6  mov     eax, [rsp+0D8h+var_A8]
0x1401da8aa  imul    rdx, rax, 0D8h; Length
0x1401da8b1  mov     rcx, r12; Address
0x1401da8b4  call    cs:__imp_ProbeForWrite
0x1401da8bb  nop     dword ptr [rax+rax+00h]
0x1401da8c0  mov     eax, [rsp+0D8h+var_A8]
0x1401da8c4  imul    rdx, rax, 0D8h; unsigned __int64
0x1401da8cb  mov     r8d, 63447355h; unsigned int
0x1401da8d1  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401da8d6  mov     r14, rax
0x1401da8d9  mov     [rsp+0D8h+var_90], rax
0x1401da8de  test    rax, rax
0x1401da8e1  jnz     short loc_1401DA8F4
0x1401da8e3  mov     ecx, 0C0000017h; Status
0x1401da8e8  call    cs:__imp_ExRaiseStatus
0x1401da8f4  mov     [rsp+0D8h+var_98], 0
0x1401da8fd  mov     [rsp+0D8h+var_60], 0
0x1401da906  mov     [rsp+0D8h+var_A4], 0
0x1401da90e  xor     esi, esi
0x1401da910  mov     [rsp+0D8h+var_88], esi
0x1401da914  xor     ecx, ecx
0x1401da916  mov     rdx, r12
0x1401da919  mov     r8d, 0D8h; Size
0x1401da91f  mov     [rsp+0D8h+var_98], rdx
0x1401da924  mov     [rsp+0D8h+var_A4], ecx
0x1401da928  cmp     ecx, [rsp+0D8h+var_A8]
0x1401da92c  jnb     short loc_1401DA943
0x1401da92e  mov     rax, [rdx]
0x1401da931  test    rax, rax
0x1401da934  jns     short loc_1401DA93C
0x1401da936  inc     esi
0x1401da938  mov     [rsp+0D8h+var_88], esi
0x1401da93c  inc     ecx
0x1401da93e  add     rdx, r8
0x1401da941  jmp     short loc_1401DA91F
0x1401da943  cmp     [rsp+0D8h+var_A8], esi
0x1401da947  jz      short loc_1401DA958
0x1401da949  mov     ecx, r13d; Status
0x1401da94c  call    cs:__imp_ExRaiseStatus
0x1401da958  mov     r13, r12
0x1401da95b  mov     [rsp+0D8h+var_98], r12
0x1401da960  mov     rcx, r14; void *
0x1401da963  mov     [rsp+0D8h+var_60], rcx
0x1401da968  xor     r12d, r12d
0x1401da96b  mov     [rsp+0D8h+var_84], r12d
0x1401da970  xor     edx, edx
0x1401da972  mov     [rsp+0D8h+var_A4], edx
0x1401da976  cmp     edx, esi
0x1401da978  jnb     short loc_1401DA9E3
0x1401da97a  mov     rax, [r13+0]
0x1401da97e  test    rax, rax
0x1401da981  jns     short loc_1401DA9D7
0x1401da983  cmp     r12d, esi
0x1401da986  jb      short loc_1401DA999
0x1401da988  mov     ecx, 0C000000Dh; Status
0x1401da98d  call    cs:__imp_ExRaiseStatus
0x1401da999  mov     rdx, r13; Src
0x1401da99c  call    RtlCopyVolatileMemory
0x1401da9a1  mov     rcx, [rsp+0D8h+var_60]
0x1401da9a6  cmp     qword ptr [rcx], 0
0x1401da9aa  jl      short loc_1401DA9BD
0x1401da9ac  mov     ecx, 0C0000022h; Status
0x1401da9b1  call    cs:__imp_ExRaiseStatus
0x1401da9bd  inc     r12d
0x1401da9c0  mov     [rsp+0D8h+var_84], r12d
0x1401da9c5  mov     r8d, 0D8h
0x1401da9cb  add     rcx, r8
0x1401da9ce  mov     [rsp+0D8h+var_60], rcx
0x1401da9d3  mov     edx, [rsp+0D8h+var_A4]
0x1401da9d7  inc     edx
0x1401da9d9  add     r13, r8
0x1401da9dc  mov     [rsp+0D8h+var_98], r13
0x1401da9e1  jmp     short loc_1401DA972
0x1401da9e3  cmp     r12d, esi
0x1401da9e6  jz      short loc_1401DA9F9
0x1401da9e8  mov     ecx, 0C000000Dh; Status
0x1401da9ed  call    cs:__imp_ExRaiseStatus
0x1401da9f9  mov     r12, [rsp+0D8h+Address]
0x1401daa01  test    r12, r12
0x1401daa04  jz      loc_1401DAB32
0x1401daa0a  mov     esi, 4
0x1401daa0f  mov     r8d, esi; Alignment
0x1401daa12  mov     edx, esi; Length
0x1401daa14  mov     rcx, r12; Address
0x1401daa17  call    cs:__imp_ProbeForWrite
0x1401daa1e  nop     dword ptr [rax+rax+00h]
0x1401daa23  test    r15, r15
0x1401daa26  jz      short loc_1401DAA6C
0x1401daa28  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401daa2f  nop     dword ptr [rax+rax+00h]
0x1401daa34  neg     rax
0x1401daa37  sbb     r8d, r8d
0x1401daa3a  and     r8d, 0FFFFFFFDh
0x1401daa3e  add     r8d, esi; Alignment
0x1401daa41  lea     edx, [rsi+18h]; Length
0x1401daa44  mov     rcx, r15; Address
0x1401daa47  call    cs:__imp_ProbeForRead
0x1401daa4e  nop     dword ptr [rax+rax+00h]
0x1401daa53  movups  xmm0, xmmword ptr [r15]
0x1401daa57  movups  [rsp+0D8h+var_58], xmm0
0x1401daa5f  movups  xmm1, xmmword ptr [r15+0Ch]
0x1401daa64  movups  [rsp+0D8h+var_58+0Ch], xmm1
0x1401daa6c  call    UserIsWddmConnectedSession
0x1401daa71  test    eax, eax
0x1401daa73  jnz     short loc_1401DAA7F
0x1401daa75  mov     esi, 0C0000022h
0x1401daa7a  jmp     loc_1401DAB68
0x1401daa7f  test    r15, r15
0x1401daa82  jz      short loc_1401DAAB7
0x1401daa84  lea     rcx, [rsp+0D8h+var_58]
0x1401daa8c  call    DrvNeedDisplayStateCheck
0x1401daa91  test    eax, eax
0x1401daa93  jz      short loc_1401DAAB7
0x1401daa95  lea     rdx, [rsp+0D8h+var_58]
0x1401daa9d  mov     ecx, 1
0x1401daaa2  call    DrvIsDisplayStateCurrent
0x1401daaa7  test    eax, eax
0x1401daaa9  jnz     short loc_1401DAAB7
0x1401daaab  mov     ebx, 0C01E0337h
0x1401daab0  mov     esi, ebx
0x1401daab2  jmp     loc_1401DAB6D
0x1401daab7  lea     rax, [rsp+0D8h+var_A0]
0x1401daabc  mov     [rsp+0D8h+var_B8], rax
0x1401daac1  mov     r9, [rsp+0D8h+arg_20]
0x1401daac9  mov     r8d, [rsp+0D8h+arg_0]
0x1401daad1  mov     rdx, r14
0x1401daad4  lea     rcx, [rsp+0D8h+var_A8]
0x1401daad9  call    DrvFunctionalizeDisplayConfig
0x1401daade  mov     esi, eax
0x1401daae0  mov     eax, 0C0000023h
0x1401daae5  cmp     esi, 80000005h
0x1401daaeb  cmovz   esi, eax
0x1401daaee  mov     eax, [rsp+0D8h+var_A8]
0x1401daaf2  imul    r8, rax, 0D8h; Size
0x1401daaf9  mov     rdx, r14; Src
0x1401daafc  mov     rcx, [rsp+0D8h+arg_10]; void *
0x1401dab04  call    RtlCopyVolatileMemory
0x1401dab09  mov     edx, [rsp+0D8h+var_A8]
0x1401dab0d  mov     rcx, rbx
0x1401dab10  call    RtlWriteULongToUser
0x1401dab15  mov     eax, [rsp+0D8h+var_A0]
0x1401dab19  mov     [r12], eax
0x1401dab1d  jmp     short loc_1401DAB64
0x1401dab1f  mov     esi, [rsp+0D8h+var_9C]
0x1401dab23  mov     r15, [rsp+0D8h+arg_18]
0x1401dab2b  mov     r14, [rsp+0D8h+var_90]
0x1401dab30  jmp     short loc_1401DAB64
0x1401dab32  mov     ecx, 0C000000Dh; Status
0x1401dab37  call    cs:__imp_ExRaiseStatus
0x1401dab43  mov     ecx, r13d; Status
0x1401dab46  call    cs:__imp_ExRaiseStatus
0x1401dab53  mov     esi, [rsp+0D8h+var_9C]
0x1401dab57  mov     r15, [rsp+0D8h+arg_18]
0x1401dab5f  mov     r14, [rsp+0D8h+var_90]
0x1401dab64  test    esi, esi
0x1401dab66  jns     short loc_1401DAB9A
0x1401dab68  mov     ebx, 0C01E0337h
0x1401dab6d  test    r15, r15
0x1401dab70  jz      short loc_1401DAB9A
0x1401dab72  lea     rcx, [rsp+0D8h+var_58]
0x1401dab7a  call    DrvNeedDisplayStateCheck
0x1401dab7f  test    eax, eax
0x1401dab81  jz      short loc_1401DAB9A
0x1401dab83  lea     rdx, [rsp+0D8h+var_58]
0x1401dab8b  mov     ecx, 1
0x1401dab90  call    DrvIsDisplayStateCurrent
0x1401dab95  test    eax, eax
0x1401dab97  cmovz   esi, ebx
0x1401dab9a  test    r14, r14
0x1401dab9d  jz      short loc_1401DABB0
0x1401dab9f  mov     rcx, r14; Buffer
0x1401daba2  call    GreDeleteFastMutex
0x1401daba7  mov     [rsp+0D8h+var_90], 0
0x1401dabb0  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401dabb5  mov     eax, esi
0x1401dabb7  mov     rbx, [rsp+0D8h+arg_8]
0x1401dabbf  add     rsp, 0B0h
0x1401dabc6  pop     r15
0x1401dabc8  pop     r14
0x1401dabca  pop     r13
0x1401dabcc  pop     r12
0x1401dabce  pop     rsi
0x1401dabcf  retn
0x14023a4cd  push    rbp
0x14023a4cf  sub     rsp, 30h
0x14023a4d3  mov     rbp, rdx
0x14023a4d6  mov     rax, [rcx]
0x14023a4d9  mov     ecx, [rax]
0x14023a4db  mov     [rbp+68h], ecx
0x14023a4de  mov     ecx, [rbp+68h]
0x14023a4e1  call    SetLastNtError
0x14023a4e6  mov     dword ptr [rbp+70h], 1
0x14023a4ed  mov     eax, [rbp+70h]
0x14023a4f0  add     rsp, 30h
0x14023a4f4  pop     rbp
0x14023a4f5  retn
0x14023a4f7  push    rbp
0x14023a4f9  sub     rsp, 30h
0x14023a4fd  mov     rbp, rdx
0x14023a500  mov     rax, [rcx]
0x14023a503  mov     ecx, [rax]
0x14023a505  mov     [rbp+58h], ecx
0x14023a508  mov     ecx, [rbp+58h]
0x14023a50b  call    SetLastNtError
0x14023a510  mov     dword ptr [rbp+60h], 1
0x14023a517  mov     eax, [rbp+60h]
0x14023a51a  add     rsp, 30h
0x14023a51e  pop     rbp
0x14023a51f  retn
```

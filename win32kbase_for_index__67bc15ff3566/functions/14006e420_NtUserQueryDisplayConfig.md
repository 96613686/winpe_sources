# NtUserQueryDisplayConfig

- ea: `0x14006e420`
- end: `0x14006e853`
- name: `NtUserQueryDisplayConfig`
- size: `1075`
- prototype: `__int64 __fastcall(unsigned int, __int64, volatile void *, int *, _OWORD *Address)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config`

## callees

- `0x1400278a0`
- `0x140029224`
- `0x14004dd98`
- `0x14004dfb0`
- `0x14006e420`
- `0x14006e85c`
- `0x14006e970`
- `0x14006f3a4`
- `0x140070130`
- `0x140070518`
- `0x14007df80`
- `0x1400a1c30`
- `0x14011a7d4`
- `0x140238970`
- `0x1402389c0`
- `0x1402bb1a0`
- `0x1402bb358`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14006e5fb`
- `ntoskrnl!KeBugCheckEx` at `0x14006e5fb`
- `ntoskrnl!ExRaiseStatus` at `0x14006e656`
- `ntoskrnl!ExRaiseStatus` at `0x14006e656`
- `ntoskrnl!ProbeForWrite` at `0x14006e532`
- `ntoskrnl!ProbeForWrite` at `0x14006e611`
- `ntoskrnl!ProbeForWrite` at `0x14006e640`
- `ntoskrnl!ProbeForWrite` at `0x14006e532`
- `ntoskrnl!ProbeForWrite` at `0x14006e611`
- `ntoskrnl!ProbeForWrite` at `0x14006e640`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14006e50a`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14006e61f`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14006e50a`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14006e61f`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14006e779`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14006e779`
- `WIN32K!W32GetUserGdiSessionState` at `0x14006e493`
- `WIN32K!W32GetUserGdiSessionState` at `0x14006e493`

## pseudocode

```c
__int64 __fastcall NtUserQueryDisplayConfig(unsigned int a1, __int64 a2, volatile void *a3, int *a4, _OWORD *Address)
{
  __int128 v9; // xmm6
  int v10; // r15d
  __int64 CurrentProcessWow64Process; // rax
  unsigned __int64 v12; // rcx
  _DWORD *v13; // r13
  struct tagTHREADINFO *v14; // rax
  int v15; // edi
  struct tagTHREADINFO *BugCheckParameter4; // rax
  __int64 v17; // rax
  bool v19; // si
  int *v20; // r9
  __int64 DxgkWin32kInterface; // rax
  unsigned int i; // ecx
  __int64 v23; // rax
  char v24[4]; // [rsp+30h] [rbp-C8h] BYREF
  unsigned int ULongFromUser; // [rsp+34h] [rbp-C4h] BYREF
  int v26; // [rsp+38h] [rbp-C0h] BYREF
  int v27; // [rsp+3Ch] [rbp-BCh]
  int v28; // [rsp+40h] [rbp-B8h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+68h] [rbp-90h] BYREF
  __int64 (__fastcall *v30)(PVOID); // [rsp+78h] [rbp-80h]
  _DWORD *v31; // [rsp+80h] [rbp-78h]
  _OWORD v32[2]; // [rsp+88h] [rbp-70h] BYREF
  _BYTE v33[40]; // [rsp+A8h] [rbp-50h] BYREF

  v31 = 0;
  ULongFromUser = 0;
  v26 = -1;
  v9 = 0;
  memset(v32, 0, 28);
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  v24[0] = 1;
  EnterSharedCrit(1, 1);
  DISPLAYCONFIG_USER_SESSION_STATE::CreateWithUserCritHeld(v33);
  if ( !*(_DWORD *)(W32GetUserGdiSessionState() + 32) )
  {
    v15 = -1073741823;
    goto LABEL_20;
  }
  if ( (a1 & 0xFFFFFF88) != 0 || (v10 = a1 & 7, ((v10 - 1) & 0xFFFFFFFC) != 0) || v10 == 3 )
  {
    v15 = -1073741811;
    goto LABEL_20;
  }
  if ( !(unsigned int)UserIsWddmConnectedSession() )
  {
    v15 = -1073741790;
    goto LABEL_20;
  }
  if ( !v33[8] )
  {
    v15 = -1073741637;
    goto LABEL_20;
  }
  PtiCurrent();
  ULongFromUser = RtlReadULongFromUser(a2);
  if ( !ULongFromUser )
  {
    v15 = -1073741811;
    v27 = -1073741811;
    goto LABEL_20;
  }
  CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
  ProbeForWrite(a3, 216LL * ULongFromUser, CurrentProcessWow64Process != 0 ? 1 : 4);
  v13 = Win32AllocPoolWithQuotaZInitImpl(v12, 216LL * ULongFromUser, 0x63447355u);
  v31 = v13;
  if ( !v13 )
    ExRaiseStatus(-1073741801);
  if ( v30 != (__int64 (__fastcall *)(PVOID))-1LL )
  {
    BugCheckParameter4 = PtiCurrent();
    KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)v13, (ULONG_PTR)BugCheckParameter4);
  }
  v14 = PtiCurrent();
  BugCheckParameter2[0] = *((_QWORD *)v14 + 47);
  *((_QWORD *)v14 + 47) = BugCheckParameter2;
  BugCheckParameter2[1] = (ULONG_PTR)v13;
  v30 = GreDeleteFastMutex;
  v28 = a1 & 4;
  if ( (a1 & 4) != 0 )
  {
    ProbeForWrite(a4, 4u, 4u);
  }
  else if ( a4 )
  {
    v15 = -1073741811;
    v27 = -1073741811;
    goto LABEL_20;
  }
  if ( Address )
  {
    v17 = PsGetCurrentProcessWow64Process();
    ProbeForWrite(Address, 0x1Cu, v17 != 0 ? 1 : 4);
  }
  v19 = 0;
  if ( v10 == 4 )
  {
    DxgkWin32kInterface = DxDdGetDxgkWin32kInterface();
    v19 = (*(unsigned __int8 (**)(void))(DxgkWin32kInterface + 536))() != 0;
  }
  if ( v19 )
    a1 = a1 & 0xEFFFFFF8 | 0x10000002;
  if ( Address )
  {
    DrvSampleDisplayState(v32);
    v9 = *(_OWORD *)((char *)v32 + 12);
  }
  v24[0] = 0;
  v20 = &v26;
  if ( v19 )
    v20 = 0;
  v15 = DrvQueryDisplayConfigAndLeaveUserCrit(a1, &ULongFromUser, v13, v20);
  if ( v15 >= 0 && v19 )
  {
    if ( ULongFromUser > 1 )
    {
      for ( i = 1; i < ULongFromUser; ++i )
      {
        v23 = 54LL * i;
        if ( v13[29] != v13[v23 + 29] )
          break;
        if ( v13[30] != v13[v23 + 30] )
          break;
      }
      v26 = i < ULongFromUser ? 4 : 2;
    }
    else
    {
      v26 = 1;
    }
  }
  if ( v15 != -1073741789 )
  {
    if ( v15 == -2147483643 )
      v15 = -1073741789;
    else
      v15 = QdcSdcTranslateStatusDefault((unsigned int)v15);
  }
  RtlCopyVolatileMemory((void *)a3, v13, 216LL * ULongFromUser);
  RtlWriteULongToUser(a2, ULongFromUser);
  if ( v28 )
    *a4 = v26;
  if ( Address )
  {
    *Address = v32[0];
    *(_OWORD *)((char *)Address + 12) = v9;
  }
LABEL_20:
  MaybeEnterLeaveCritSharedOnly::~MaybeEnterLeaveCritSharedOnly((MaybeEnterLeaveCritSharedOnly *)v24);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14006e420  mov     rax, rsp
0x14006e423  mov     [rax+8], rbx
0x14006e427  mov     [rax+10h], rsi
0x14006e42b  mov     [rax+18h], r8
0x14006e42f  push    rdi
0x14006e430  push    r12
0x14006e432  push    r13
0x14006e434  push    r14
0x14006e436  push    r15
0x14006e438  sub     rsp, 0D0h
0x14006e43f  movaps  xmmword ptr [rax-38h], xmm6
0x14006e443  mov     r12, r9
0x14006e446  mov     rsi, r8
0x14006e449  mov     rbx, rdx
0x14006e44c  mov     edi, ecx
0x14006e44e  xor     r14d, r14d
0x14006e451  mov     [rax-78h], r14
0x14006e455  mov     [rsp+0F8h+var_C4], r14d
0x14006e45a  mov     [rsp+0F8h+var_C0], 0FFFFFFFFh
0x14006e462  xorps   xmm6, xmm6
0x14006e465  movups  xmmword ptr [rax-70h], xmm6
0x14006e469  movups  xmmword ptr [rax-64h], xmm6
0x14006e46d  lea     rcx, [rsp+0F8h+BugCheckParameter2]
0x14006e472  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x14006e477  lea     ecx, [r14+1]
0x14006e47b  mov     [rsp+0F8h+var_C8], cl
0x14006e47f  mov     edx, ecx
0x14006e481  call    EnterSharedCrit
0x14006e486  lea     rcx, [rsp+0F8h+var_50]
0x14006e48e  call    ?CreateWithUserCritHeld@DISPLAYCONFIG_USER_SESSION_STATE@@SA?AV1@XZ; DISPLAYCONFIG_USER_SESSION_STATE::CreateWithUserCritHeld(void)
0x14006e493  call    cs:__imp_W32GetUserGdiSessionState
0x14006e49a  nop     dword ptr [rax+rax+00h]
0x14006e49f  cmp     [rax+20h], r14d
0x14006e4a3  jz      loc_14006E7A6
0x14006e4a9  test    edi, 0FFFFFF88h
0x14006e4af  jnz     loc_14006E849
0x14006e4b5  mov     r15d, edi
0x14006e4b8  and     r15d, 7
0x14006e4bc  lea     eax, [r15-1]
0x14006e4c0  test    eax, 0FFFFFFFCh
0x14006e4c5  jnz     loc_14006E849
0x14006e4cb  cmp     r15d, 3
0x14006e4cf  jz      loc_14006E849
0x14006e4d5  call    UserIsWddmConnectedSession
0x14006e4da  test    eax, eax
0x14006e4dc  jz      loc_14006E7B0
0x14006e4e2  cmp     [rsp+0F8h+var_48], r14b
0x14006e4ea  jz      loc_14006E7BA
0x14006e4f0  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14006e4f5  nop
0x14006e4f6  mov     rcx, rbx
0x14006e4f9  call    RtlReadULongFromUser
0x14006e4fe  mov     [rsp+0F8h+var_C4], eax
0x14006e502  test    eax, eax
0x14006e504  jz      loc_14006E5D1
0x14006e50a  call    cs:__imp_PsGetCurrentProcessWow64Process
0x14006e511  nop     dword ptr [rax+rax+00h]
0x14006e516  neg     rax
0x14006e519  sbb     r8d, r8d
0x14006e51c  and     r8d, 0FFFFFFFDh
0x14006e520  add     r8d, 4; Alignment
0x14006e524  mov     eax, [rsp+0F8h+var_C4]
0x14006e528  imul    rdx, rax, 0D8h; Length
0x14006e52f  mov     rcx, rsi; Address
0x14006e532  call    cs:__imp_ProbeForWrite
0x14006e539  nop     dword ptr [rax+rax+00h]
0x14006e53e  mov     eax, [rsp+0F8h+var_C4]
0x14006e542  imul    rdx, rax, 0D8h; unsigned __int64
0x14006e549  mov     r8d, 63447355h; unsigned int
0x14006e54f  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14006e554  mov     r13, rax
0x14006e557  mov     [rsp+0F8h+var_78], rax
0x14006e55f  test    rax, rax
0x14006e562  jz      loc_14006E651
0x14006e568  cmp     [rsp+0F8h+var_80], 0FFFFFFFFFFFFFFFFh
0x14006e56e  jnz     short loc_14006E5DF
0x14006e570  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14006e575  mov     rcx, [rax+178h]
0x14006e57c  mov     [rsp+0F8h+BugCheckParameter2], rcx
0x14006e581  lea     rcx, [rsp+0F8h+BugCheckParameter2]
0x14006e586  mov     [rax+178h], rcx
0x14006e58d  mov     [rsp+0F8h+var_88], r13
0x14006e592  lea     rax, GreDeleteFastMutex
0x14006e599  mov     [rsp+0F8h+var_80], rax
0x14006e59e  mov     eax, edi
0x14006e5a0  lea     esi, [r14+4]
0x14006e5a4  and     eax, esi
0x14006e5a6  mov     [rsp+0F8h+var_B8], eax
0x14006e5aa  jnz     short loc_14006E608
0x14006e5ac  test    r12, r12
0x14006e5af  jz      short loc_14006E5BF
0x14006e5b1  mov     edi, 0C000000Dh
0x14006e5b6  mov     [rsp+0F8h+var_BC], edi
0x14006e5ba  jmp     loc_14006E66C
0x14006e5bf  mov     r14, [rsp+0F8h+Address]
0x14006e5c7  test    r14, r14
0x14006e5ca  jnz     short loc_14006E61F
0x14006e5cc  jmp     loc_14006E6A5
0x14006e5d1  mov     edi, 0C000000Dh
0x14006e5d6  mov     [rsp+0F8h+var_BC], edi
0x14006e5da  jmp     loc_14006E66C
0x14006e5df  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14006e5e4  mov     [rsp+0F8h+BugCheckParameter4], rax; BugCheckParameter4
0x14006e5e9  mov     r9, r13; BugCheckParameter3
0x14006e5ec  lea     r8, [rsp+0F8h+BugCheckParameter2]; BugCheckParameter2
0x14006e5f1  mov     edx, 12h; BugCheckParameter1
0x14006e5f6  mov     ecx, 164h; BugCheckCode
0x14006e5fb  call    cs:__imp_KeBugCheckEx
0x14006e608  mov     r8d, esi; Alignment
0x14006e60b  mov     rdx, rsi; Length
0x14006e60e  mov     rcx, r12; Address
0x14006e611  call    cs:__imp_ProbeForWrite
0x14006e618  nop     dword ptr [rax+rax+00h]
0x14006e61d  jmp     short loc_14006E5BF
0x14006e61f  call    cs:__imp_PsGetCurrentProcessWow64Process
0x14006e626  nop     dword ptr [rax+rax+00h]
0x14006e62b  neg     rax
0x14006e62e  sbb     r8d, r8d
0x14006e631  and     r8d, 0FFFFFFFDh
0x14006e635  add     r8d, esi; Alignment
0x14006e638  mov     edx, 1Ch; Length
0x14006e63d  mov     rcx, r14; Address
0x14006e640  call    cs:__imp_ProbeForWrite
0x14006e647  nop     dword ptr [rax+rax+00h]
0x14006e64c  jmp     loc_14006E5CC
0x14006e651  mov     ecx, 0C0000017h; Status
0x14006e656  call    cs:__imp_ExRaiseStatus
0x14006e663  mov     edi, 0C000000Dh
0x14006e668  mov     [rsp+0F8h+var_BC], edi
0x14006e66c  lea     rcx, [rsp+0F8h+var_C8]; this
0x14006e671  call    ??1MaybeEnterLeaveCritSharedOnly@@QEAA@XZ; MaybeEnterLeaveCritSharedOnly::~MaybeEnterLeaveCritSharedOnly(void)
0x14006e676  lea     rcx, [rsp+0F8h+BugCheckParameter2]
0x14006e67b  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x14006e680  mov     eax, edi
0x14006e682  lea     r11, [rsp+0F8h+var_28]
0x14006e68a  mov     rbx, [r11+30h]
0x14006e68e  mov     rsi, [r11+38h]
0x14006e692  movaps  xmm6, xmmword ptr [r11-10h]
0x14006e697  mov     rsp, r11
0x14006e69a  pop     r15
0x14006e69c  pop     r14
0x14006e69e  pop     r13
0x14006e6a0  pop     r12
0x14006e6a2  pop     rdi
0x14006e6a3  retn
0x14006e6a5  xor     sil, sil
0x14006e6a8  cmp     r15d, 4
0x14006e6ac  jz      loc_14006E779
0x14006e6b2  mov     r15d, 1
0x14006e6b8  test    sil, sil
0x14006e6bb  jnz     loc_14006E7C4
0x14006e6c1  test    r14, r14
0x14006e6c4  jnz     loc_14006E7D2
0x14006e6ca  mov     [rsp+0F8h+var_C8], 0
0x14006e6cf  lea     r9, [rsp+0F8h+var_C0]
0x14006e6d4  xor     eax, eax
0x14006e6d6  test    sil, sil
0x14006e6d9  cmovnz  r9, rax
0x14006e6dd  mov     r8, r13
0x14006e6e0  lea     rdx, [rsp+0F8h+var_C4]
0x14006e6e5  mov     ecx, edi
0x14006e6e7  call    DrvQueryDisplayConfigAndLeaveUserCrit
0x14006e6ec  mov     edi, eax
0x14006e6ee  test    eax, eax
0x14006e6f0  js      short loc_14006E6FB
0x14006e6f2  test    sil, sil
0x14006e6f5  jnz     loc_14006E7EC
0x14006e6fb  cmp     edi, 0C0000023h
0x14006e701  jnz     short loc_14006E762
0x14006e703  mov     eax, [rsp+0F8h+var_C4]
0x14006e707  imul    r8, rax, 0D8h; Size
0x14006e70e  mov     rdx, r13; Src
0x14006e711  mov     rcx, [rsp+0F8h+arg_10]; void *
0x14006e719  call    RtlCopyVolatileMemory
0x14006e71e  mov     edx, [rsp+0F8h+var_C4]
0x14006e722  mov     rcx, rbx
0x14006e725  call    RtlWriteULongToUser
0x14006e72a  cmp     [rsp+0F8h+var_B8], 0
0x14006e72f  jnz     short loc_14006E749
0x14006e731  test    r14, r14
0x14006e734  jz      short loc_14006E753
0x14006e736  movups  xmm0, xmmword ptr [rsp+0F8h+var_70]
0x14006e73e  movups  xmmword ptr [r14], xmm0
0x14006e742  movups  xmmword ptr [r14+0Ch], xmm6
0x14006e747  jmp     short loc_14006E753
0x14006e749  mov     eax, [rsp+0F8h+var_C0]
0x14006e74d  mov     [r12], eax
0x14006e751  jmp     short loc_14006E731
0x14006e753  jmp     loc_14006E66C
0x14006e758  mov     edi, 0C000000Dh
0x14006e75d  jmp     loc_14006E66C
0x14006e762  cmp     edi, 80000005h
0x14006e768  jz      loc_14006E83F
0x14006e76e  mov     ecx, edi
0x14006e770  call    _QdcSdcTranslateStatusDefault
0x14006e775  mov     edi, eax
0x14006e777  jmp     short loc_14006E703
0x14006e779  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x14006e780  nop     dword ptr [rax+rax+00h]
0x14006e785  mov     rax, [rax+218h]
0x14006e78c  call    _guard_dispatch_icall
0x14006e791  movzx   esi, sil
0x14006e795  test    al, al
0x14006e797  mov     r15d, 1
0x14006e79d  cmovnz  esi, r15d
0x14006e7a1  jmp     loc_14006E6B8
0x14006e7a6  mov     edi, 0C0000001h
0x14006e7ab  jmp     loc_14006E66C
0x14006e7b0  mov     edi, 0C0000022h
0x14006e7b5  jmp     loc_14006E66C
0x14006e7ba  mov     edi, 0C00000BBh
0x14006e7bf  jmp     loc_14006E66C
0x14006e7c4  and     edi, 0FFFFFFFAh
0x14006e7c7  or      edi, 10000002h
0x14006e7cd  jmp     loc_14006E6C1
0x14006e7d2  lea     rcx, [rsp+0F8h+var_70]
0x14006e7da  call    DrvSampleDisplayState
0x14006e7df  movups  xmm6, xmmword ptr [rsp+0F8h+var_70+0Ch]
0x14006e7e7  jmp     loc_14006E6CA
0x14006e7ec  cmp     [rsp+0F8h+var_C4], r15d
0x14006e7f1  ja      short loc_14006E7FD
0x14006e7f3  mov     [rsp+0F8h+var_C0], r15d
0x14006e7f8  jmp     loc_14006E6FB
0x14006e7fd  mov     ecx, r15d
0x14006e800  jbe     short loc_14006E82A
0x14006e802  mov     edx, [r13+74h]
0x14006e806  mov     eax, ecx
0x14006e808  imul    rax, 0D8h
0x14006e80f  cmp     edx, [rax+r13+74h]
0x14006e814  jnz     short loc_14006E82A
0x14006e816  mov     eax, [rax+r13+78h]
0x14006e81b  cmp     [r13+78h], eax
0x14006e81f  jnz     short loc_14006E82A
0x14006e821  add     ecx, r15d
0x14006e824  cmp     ecx, [rsp+0F8h+var_C4]
0x14006e828  jb      short loc_14006E806
0x14006e82a  cmp     ecx, [rsp+0F8h+var_C4]
0x14006e82e  sbb     eax, eax
0x14006e830  and     eax, 2
0x14006e833  add     eax, 2
0x14006e836  mov     [rsp+0F8h+var_C0], eax
0x14006e83a  jmp     loc_14006E6FB
0x14006e83f  mov     edi, 0C0000023h
0x14006e844  jmp     loc_14006E703
0x14006e849  mov     edi, 0C000000Dh
0x14006e84e  jmp     loc_14006E66C
0x140239563  push    rbp
0x140239565  sub     rsp, 30h
0x140239569  mov     rbp, rdx
0x14023956c  mov     rax, [rcx]
0x14023956f  mov     ecx, [rax]
0x140239571  mov     [rbp+58h], ecx
0x140239574  mov     ecx, [rbp+58h]
0x140239577  call    SetLastNtError
0x14023957c  mov     dword ptr [rbp+60h], 1
0x140239583  mov     eax, [rbp+60h]
0x140239586  add     rsp, 30h
0x14023958a  pop     rbp
0x14023958b  retn
0x14023958d  push    rbp
0x14023958f  sub     rsp, 30h
0x140239593  mov     rbp, rdx
0x140239596  mov     rax, [rcx]
0x140239599  mov     ecx, [rax]
0x14023959b  mov     [rbp+48h], ecx
0x14023959e  mov     ecx, [rbp+48h]
0x1402395a1  call    SetLastNtError
0x1402395a6  mov     dword ptr [rbp+50h], 1
0x1402395ad  mov     eax, [rbp+50h]
0x1402395b0  add     rsp, 30h
0x1402395b4  pop     rbp
0x1402395b5  retn
```

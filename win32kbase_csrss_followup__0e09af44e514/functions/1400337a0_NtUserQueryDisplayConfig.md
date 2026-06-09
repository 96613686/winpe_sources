# NtUserQueryDisplayConfig

- ea: `0x1400337a0`
- end: `0x140033bd3`
- name: `NtUserQueryDisplayConfig`
- size: `1075`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config`

## callees

- `0x140019f88`
- `0x14001b904`
- `0x1400325a4`
- `0x1400332c0`
- `0x1400337a0`
- `0x140033bdc`
- `0x140033cf0`
- `0x140033d94`
- `0x14004c720`
- `0x140076968`
- `0x140076b80`
- `0x1400b05f0`
- `0x1401179a4`
- `0x1402381f0`
- `0x140238240`
- `0x1402bb1a0`
- `0x1402bb358`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14003397b`
- `ntoskrnl!KeBugCheckEx` at `0x14003397b`
- `ntoskrnl!ExRaiseStatus` at `0x1400339d6`
- `ntoskrnl!ExRaiseStatus` at `0x1400339d6`
- `ntoskrnl!ProbeForWrite` at `0x1400338b2`
- `ntoskrnl!ProbeForWrite` at `0x140033991`
- `ntoskrnl!ProbeForWrite` at `0x1400339c0`
- `ntoskrnl!ProbeForWrite` at `0x1400338b2`
- `ntoskrnl!ProbeForWrite` at `0x140033991`
- `ntoskrnl!ProbeForWrite` at `0x1400339c0`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14003388a`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14003399f`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14003388a`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14003399f`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140033af9`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140033af9`
- `WIN32K!W32GetUserGdiSessionState` at `0x140033813`
- `WIN32K!W32GetUserGdiSessionState` at `0x140033813`

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
  __int64 v15; // rdx
  __int64 v16; // r8
  ULONG_PTR *v17; // rcx
  int v18; // edi
  struct tagTHREADINFO *BugCheckParameter4; // rax
  __int64 v20; // rax
  bool v22; // si
  int *v23; // r9
  __int64 DxgkWin32kInterface; // rax
  unsigned int i; // ecx
  __int64 v26; // rax
  char v27[4]; // [rsp+30h] [rbp-C8h] BYREF
  unsigned int ULongFromUser; // [rsp+34h] [rbp-C4h] BYREF
  int v29; // [rsp+38h] [rbp-C0h] BYREF
  int v30; // [rsp+3Ch] [rbp-BCh]
  int v31; // [rsp+40h] [rbp-B8h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+68h] [rbp-90h] BYREF
  __int64 (__fastcall *v33)(PVOID); // [rsp+78h] [rbp-80h]
  _DWORD *v34; // [rsp+80h] [rbp-78h]
  _OWORD v35[2]; // [rsp+88h] [rbp-70h] BYREF
  _BYTE v36[40]; // [rsp+A8h] [rbp-50h] BYREF

  v34 = 0;
  ULongFromUser = 0;
  v29 = -1;
  v9 = 0;
  memset(v35, 0, 28);
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  v27[0] = 1;
  EnterSharedCrit(1, 1);
  DISPLAYCONFIG_USER_SESSION_STATE::CreateWithUserCritHeld(v36);
  if ( !*(_DWORD *)(W32GetUserGdiSessionState() + 32) )
  {
    v18 = -1073741823;
    goto LABEL_20;
  }
  if ( (a1 & 0xFFFFFF88) != 0 || (v10 = a1 & 7, ((v10 - 1) & 0xFFFFFFFC) != 0) || v10 == 3 )
  {
    v18 = -1073741811;
    goto LABEL_20;
  }
  if ( !(unsigned int)UserIsWddmConnectedSession() )
  {
    v18 = -1073741790;
    goto LABEL_20;
  }
  if ( !v36[8] )
  {
    v18 = -1073741637;
    goto LABEL_20;
  }
  PtiCurrent();
  ULongFromUser = RtlReadULongFromUser(a2);
  if ( !ULongFromUser )
  {
    v18 = -1073741811;
    v30 = -1073741811;
    goto LABEL_20;
  }
  CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
  ProbeForWrite(a3, 216LL * ULongFromUser, CurrentProcessWow64Process != 0 ? 1 : 4);
  v13 = Win32AllocPoolWithQuotaZInitImpl(v12, 216LL * ULongFromUser, 0x63447355u);
  v34 = v13;
  if ( !v13 )
    ExRaiseStatus(-1073741801);
  if ( v33 != (__int64 (__fastcall *)(PVOID))-1LL )
  {
    BugCheckParameter4 = PtiCurrent();
    KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)v13, (ULONG_PTR)BugCheckParameter4);
  }
  v14 = PtiCurrent();
  BugCheckParameter2[0] = *((_QWORD *)v14 + 47);
  v17 = BugCheckParameter2;
  *((_QWORD *)v14 + 47) = BugCheckParameter2;
  BugCheckParameter2[1] = (ULONG_PTR)v13;
  v33 = GreDeleteFastMutex;
  v31 = a1 & 4;
  if ( (a1 & 4) != 0 )
  {
    ProbeForWrite(a4, 4u, 4u);
  }
  else if ( a4 )
  {
    v18 = -1073741811;
    v30 = -1073741811;
    goto LABEL_20;
  }
  if ( Address )
  {
    v20 = PsGetCurrentProcessWow64Process();
    ProbeForWrite(Address, 0x1Cu, v20 != 0 ? 1 : 4);
  }
  v22 = 0;
  if ( v10 == 4 )
  {
    DxgkWin32kInterface = DxDdGetDxgkWin32kInterface(v17, v15, v16);
    v22 = (*(unsigned __int8 (**)(void))(DxgkWin32kInterface + 536))() != 0;
  }
  if ( v22 )
    a1 = a1 & 0xEFFFFFF8 | 0x10000002;
  if ( Address )
  {
    DrvSampleDisplayState(v35);
    v9 = *(_OWORD *)((char *)v35 + 12);
  }
  v27[0] = 0;
  v23 = &v29;
  if ( v22 )
    v23 = 0;
  v18 = DrvQueryDisplayConfigAndLeaveUserCrit(a1, &ULongFromUser, v13, v23);
  if ( v18 >= 0 && v22 )
  {
    if ( ULongFromUser > 1 )
    {
      for ( i = 1; i < ULongFromUser; ++i )
      {
        v26 = 54LL * i;
        if ( v13[29] != v13[v26 + 29] )
          break;
        if ( v13[30] != v13[v26 + 30] )
          break;
      }
      v29 = i < ULongFromUser ? 4 : 2;
    }
    else
    {
      v29 = 1;
    }
  }
  if ( v18 != -1073741789 )
  {
    if ( v18 == -2147483643 )
      v18 = -1073741789;
    else
      v18 = QdcSdcTranslateStatusDefault((unsigned int)v18);
  }
  RtlCopyVolatileMemory((void *)a3, v13, 216LL * ULongFromUser);
  RtlWriteULongToUser(a2, ULongFromUser);
  if ( v31 )
    *a4 = v29;
  if ( Address )
  {
    *Address = v35[0];
    *(_OWORD *)((char *)Address + 12) = v9;
  }
LABEL_20:
  MaybeEnterLeaveCritSharedOnly::~MaybeEnterLeaveCritSharedOnly((MaybeEnterLeaveCritSharedOnly *)v27);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1400337a0  mov     rax, rsp
0x1400337a3  mov     [rax+8], rbx
0x1400337a7  mov     [rax+10h], rsi
0x1400337ab  mov     [rax+18h], r8
0x1400337af  push    rdi
0x1400337b0  push    r12
0x1400337b2  push    r13
0x1400337b4  push    r14
0x1400337b6  push    r15
0x1400337b8  sub     rsp, 0D0h
0x1400337bf  movaps  xmmword ptr [rax-38h], xmm6
0x1400337c3  mov     r12, r9
0x1400337c6  mov     rsi, r8
0x1400337c9  mov     rbx, rdx
0x1400337cc  mov     edi, ecx
0x1400337ce  xor     r14d, r14d
0x1400337d1  mov     [rax-78h], r14
0x1400337d5  mov     [rsp+0F8h+var_C4], r14d
0x1400337da  mov     [rsp+0F8h+var_C0], 0FFFFFFFFh
0x1400337e2  xorps   xmm6, xmm6
0x1400337e5  movups  xmmword ptr [rax-70h], xmm6
0x1400337e9  movups  xmmword ptr [rax-64h], xmm6
0x1400337ed  lea     rcx, [rsp+0F8h+BugCheckParameter2]
0x1400337f2  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1400337f7  lea     ecx, [r14+1]
0x1400337fb  mov     [rsp+0F8h+var_C8], cl
0x1400337ff  mov     edx, ecx
0x140033801  call    EnterSharedCrit
0x140033806  lea     rcx, [rsp+0F8h+var_50]
0x14003380e  call    ?CreateWithUserCritHeld@DISPLAYCONFIG_USER_SESSION_STATE@@SA?AV1@XZ; DISPLAYCONFIG_USER_SESSION_STATE::CreateWithUserCritHeld(void)
0x140033813  call    cs:__imp_W32GetUserGdiSessionState
0x14003381a  nop     dword ptr [rax+rax+00h]
0x14003381f  cmp     [rax+20h], r14d
0x140033823  jz      loc_140033B26
0x140033829  test    edi, 0FFFFFF88h
0x14003382f  jnz     loc_140033BC9
0x140033835  mov     r15d, edi
0x140033838  and     r15d, 7
0x14003383c  lea     eax, [r15-1]
0x140033840  test    eax, 0FFFFFFFCh
0x140033845  jnz     loc_140033BC9
0x14003384b  cmp     r15d, 3
0x14003384f  jz      loc_140033BC9
0x140033855  call    UserIsWddmConnectedSession
0x14003385a  test    eax, eax
0x14003385c  jz      loc_140033B30
0x140033862  cmp     [rsp+0F8h+var_48], r14b
0x14003386a  jz      loc_140033B3A
0x140033870  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140033875  nop
0x140033876  mov     rcx, rbx
0x140033879  call    RtlReadULongFromUser
0x14003387e  mov     [rsp+0F8h+var_C4], eax
0x140033882  test    eax, eax
0x140033884  jz      loc_140033951
0x14003388a  call    cs:__imp_PsGetCurrentProcessWow64Process
0x140033891  nop     dword ptr [rax+rax+00h]
0x140033896  neg     rax
0x140033899  sbb     r8d, r8d
0x14003389c  and     r8d, 0FFFFFFFDh
0x1400338a0  add     r8d, 4; Alignment
0x1400338a4  mov     eax, [rsp+0F8h+var_C4]
0x1400338a8  imul    rdx, rax, 0D8h; Length
0x1400338af  mov     rcx, rsi; Address
0x1400338b2  call    cs:__imp_ProbeForWrite
0x1400338b9  nop     dword ptr [rax+rax+00h]
0x1400338be  mov     eax, [rsp+0F8h+var_C4]
0x1400338c2  imul    rdx, rax, 0D8h; unsigned __int64
0x1400338c9  mov     r8d, 63447355h; unsigned int
0x1400338cf  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400338d4  mov     r13, rax
0x1400338d7  mov     [rsp+0F8h+var_78], rax
0x1400338df  test    rax, rax
0x1400338e2  jz      loc_1400339D1
0x1400338e8  cmp     [rsp+0F8h+var_80], 0FFFFFFFFFFFFFFFFh
0x1400338ee  jnz     short loc_14003395F
0x1400338f0  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400338f5  mov     rcx, [rax+178h]
0x1400338fc  mov     [rsp+0F8h+BugCheckParameter2], rcx
0x140033901  lea     rcx, [rsp+0F8h+BugCheckParameter2]
0x140033906  mov     [rax+178h], rcx
0x14003390d  mov     [rsp+0F8h+var_88], r13
0x140033912  lea     rax, GreDeleteFastMutex
0x140033919  mov     [rsp+0F8h+var_80], rax
0x14003391e  mov     eax, edi
0x140033920  lea     esi, [r14+4]
0x140033924  and     eax, esi
0x140033926  mov     [rsp+0F8h+var_B8], eax
0x14003392a  jnz     short loc_140033988
0x14003392c  test    r12, r12
0x14003392f  jz      short loc_14003393F
0x140033931  mov     edi, 0C000000Dh
0x140033936  mov     [rsp+0F8h+var_BC], edi
0x14003393a  jmp     loc_1400339EC
0x14003393f  mov     r14, [rsp+0F8h+Address]
0x140033947  test    r14, r14
0x14003394a  jnz     short loc_14003399F
0x14003394c  jmp     loc_140033A25
0x140033951  mov     edi, 0C000000Dh
0x140033956  mov     [rsp+0F8h+var_BC], edi
0x14003395a  jmp     loc_1400339EC
0x14003395f  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140033964  mov     [rsp+0F8h+BugCheckParameter4], rax; BugCheckParameter4
0x140033969  mov     r9, r13; BugCheckParameter3
0x14003396c  lea     r8, [rsp+0F8h+BugCheckParameter2]; BugCheckParameter2
0x140033971  mov     edx, 12h; BugCheckParameter1
0x140033976  mov     ecx, 164h; BugCheckCode
0x14003397b  call    cs:__imp_KeBugCheckEx
0x140033988  mov     r8d, esi; Alignment
0x14003398b  mov     rdx, rsi; Length
0x14003398e  mov     rcx, r12; Address
0x140033991  call    cs:__imp_ProbeForWrite
0x140033998  nop     dword ptr [rax+rax+00h]
0x14003399d  jmp     short loc_14003393F
0x14003399f  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1400339a6  nop     dword ptr [rax+rax+00h]
0x1400339ab  neg     rax
0x1400339ae  sbb     r8d, r8d
0x1400339b1  and     r8d, 0FFFFFFFDh
0x1400339b5  add     r8d, esi; Alignment
0x1400339b8  mov     edx, 1Ch; Length
0x1400339bd  mov     rcx, r14; Address
0x1400339c0  call    cs:__imp_ProbeForWrite
0x1400339c7  nop     dword ptr [rax+rax+00h]
0x1400339cc  jmp     loc_14003394C
0x1400339d1  mov     ecx, 0C0000017h; Status
0x1400339d6  call    cs:__imp_ExRaiseStatus
0x1400339e3  mov     edi, 0C000000Dh
0x1400339e8  mov     [rsp+0F8h+var_BC], edi
0x1400339ec  lea     rcx, [rsp+0F8h+var_C8]; this
0x1400339f1  call    ??1MaybeEnterLeaveCritSharedOnly@@QEAA@XZ; MaybeEnterLeaveCritSharedOnly::~MaybeEnterLeaveCritSharedOnly(void)
0x1400339f6  lea     rcx, [rsp+0F8h+BugCheckParameter2]
0x1400339fb  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140033a00  mov     eax, edi
0x140033a02  lea     r11, [rsp+0F8h+var_28]
0x140033a0a  mov     rbx, [r11+30h]
0x140033a0e  mov     rsi, [r11+38h]
0x140033a12  movaps  xmm6, xmmword ptr [r11-10h]
0x140033a17  mov     rsp, r11
0x140033a1a  pop     r15
0x140033a1c  pop     r14
0x140033a1e  pop     r13
0x140033a20  pop     r12
0x140033a22  pop     rdi
0x140033a23  retn
0x140033a25  xor     sil, sil
0x140033a28  cmp     r15d, 4
0x140033a2c  jz      loc_140033AF9
0x140033a32  mov     r15d, 1
0x140033a38  test    sil, sil
0x140033a3b  jnz     loc_140033B44
0x140033a41  test    r14, r14
0x140033a44  jnz     loc_140033B52
0x140033a4a  mov     [rsp+0F8h+var_C8], 0
0x140033a4f  lea     r9, [rsp+0F8h+var_C0]
0x140033a54  xor     eax, eax
0x140033a56  test    sil, sil
0x140033a59  cmovnz  r9, rax
0x140033a5d  mov     r8, r13
0x140033a60  lea     rdx, [rsp+0F8h+var_C4]
0x140033a65  mov     ecx, edi
0x140033a67  call    DrvQueryDisplayConfigAndLeaveUserCrit
0x140033a6c  mov     edi, eax
0x140033a6e  test    eax, eax
0x140033a70  js      short loc_140033A7B
0x140033a72  test    sil, sil
0x140033a75  jnz     loc_140033B6C
0x140033a7b  cmp     edi, 0C0000023h
0x140033a81  jnz     short loc_140033AE2
0x140033a83  mov     eax, [rsp+0F8h+var_C4]
0x140033a87  imul    r8, rax, 0D8h; Size
0x140033a8e  mov     rdx, r13; Src
0x140033a91  mov     rcx, [rsp+0F8h+arg_10]; void *
0x140033a99  call    RtlCopyVolatileMemory
0x140033a9e  mov     edx, [rsp+0F8h+var_C4]
0x140033aa2  mov     rcx, rbx
0x140033aa5  call    RtlWriteULongToUser
0x140033aaa  cmp     [rsp+0F8h+var_B8], 0
0x140033aaf  jnz     short loc_140033AC9
0x140033ab1  test    r14, r14
0x140033ab4  jz      short loc_140033AD3
0x140033ab6  movups  xmm0, xmmword ptr [rsp+0F8h+var_70]
0x140033abe  movups  xmmword ptr [r14], xmm0
0x140033ac2  movups  xmmword ptr [r14+0Ch], xmm6
0x140033ac7  jmp     short loc_140033AD3
0x140033ac9  mov     eax, [rsp+0F8h+var_C0]
0x140033acd  mov     [r12], eax
0x140033ad1  jmp     short loc_140033AB1
0x140033ad3  jmp     loc_1400339EC
0x140033ad8  mov     edi, 0C000000Dh
0x140033add  jmp     loc_1400339EC
0x140033ae2  cmp     edi, 80000005h
0x140033ae8  jz      loc_140033BBF
0x140033aee  mov     ecx, edi
0x140033af0  call    _QdcSdcTranslateStatusDefault
0x140033af5  mov     edi, eax
0x140033af7  jmp     short loc_140033A83
0x140033af9  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x140033b00  nop     dword ptr [rax+rax+00h]
0x140033b05  mov     rax, [rax+218h]
0x140033b0c  call    _guard_dispatch_icall
0x140033b11  movzx   esi, sil
0x140033b15  test    al, al
0x140033b17  mov     r15d, 1
0x140033b1d  cmovnz  esi, r15d
0x140033b21  jmp     loc_140033A38
0x140033b26  mov     edi, 0C0000001h
0x140033b2b  jmp     loc_1400339EC
0x140033b30  mov     edi, 0C0000022h
0x140033b35  jmp     loc_1400339EC
0x140033b3a  mov     edi, 0C00000BBh
0x140033b3f  jmp     loc_1400339EC
0x140033b44  and     edi, 0FFFFFFFAh
0x140033b47  or      edi, 10000002h
0x140033b4d  jmp     loc_140033A41
0x140033b52  lea     rcx, [rsp+0F8h+var_70]
0x140033b5a  call    DrvSampleDisplayState
0x140033b5f  movups  xmm6, xmmword ptr [rsp+0F8h+var_70+0Ch]
0x140033b67  jmp     loc_140033A4A
0x140033b6c  cmp     [rsp+0F8h+var_C4], r15d
0x140033b71  ja      short loc_140033B7D
0x140033b73  mov     [rsp+0F8h+var_C0], r15d
0x140033b78  jmp     loc_140033A7B
0x140033b7d  mov     ecx, r15d
0x140033b80  jbe     short loc_140033BAA
0x140033b82  mov     edx, [r13+74h]
0x140033b86  mov     eax, ecx
0x140033b88  imul    rax, 0D8h
0x140033b8f  cmp     edx, [rax+r13+74h]
0x140033b94  jnz     short loc_140033BAA
0x140033b96  mov     eax, [rax+r13+78h]
0x140033b9b  cmp     [r13+78h], eax
0x140033b9f  jnz     short loc_140033BAA
0x140033ba1  add     ecx, r15d
0x140033ba4  cmp     ecx, [rsp+0F8h+var_C4]
0x140033ba8  jb      short loc_140033B86
0x140033baa  cmp     ecx, [rsp+0F8h+var_C4]
0x140033bae  sbb     eax, eax
0x140033bb0  and     eax, 2
0x140033bb3  add     eax, 2
0x140033bb6  mov     [rsp+0F8h+var_C0], eax
0x140033bba  jmp     loc_140033A7B
0x140033bbf  mov     edi, 0C0000023h
0x140033bc4  jmp     loc_140033A83
0x140033bc9  mov     edi, 0C000000Dh
0x140033bce  jmp     loc_1400339EC
0x140238c0e  push    rbp
0x140238c10  sub     rsp, 30h
0x140238c14  mov     rbp, rdx
0x140238c17  mov     rax, [rcx]
0x140238c1a  mov     ecx, [rax]
0x140238c1c  mov     [rbp+58h], ecx
0x140238c1f  mov     ecx, [rbp+58h]
0x140238c22  call    SetLastNtError
0x140238c27  mov     dword ptr [rbp+60h], 1
0x140238c2e  mov     eax, [rbp+60h]
0x140238c31  add     rsp, 30h
0x140238c35  pop     rbp
0x140238c36  retn
0x140238c38  push    rbp
0x140238c3a  sub     rsp, 30h
0x140238c3e  mov     rbp, rdx
0x140238c41  mov     rax, [rcx]
0x140238c44  mov     ecx, [rax]
0x140238c46  mov     [rbp+48h], ecx
0x140238c49  mov     ecx, [rbp+48h]
0x140238c4c  call    SetLastNtError
0x140238c51  mov     dword ptr [rbp+50h], 1
0x140238c58  mov     eax, [rbp+50h]
0x140238c5b  add     rsp, 30h
0x140238c5f  pop     rbp
0x140238c60  retn
```

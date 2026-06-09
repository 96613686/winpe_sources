# NtUserQueryDisplayConfig

- ea: `0x14002a520`
- end: `0x14002a953`
- name: `NtUserQueryDisplayConfig`
- size: `1075`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config`

## callees

- `0x140010e18`
- `0x140012794`
- `0x140029324`
- `0x14002a040`
- `0x14002a520`
- `0x14002a95c`
- `0x14002aa70`
- `0x14002ab14`
- `0x140043810`
- `0x1400757c8`
- `0x1400759e0`
- `0x1400c9d00`
- `0x1401175e4`
- `0x140238ba0`
- `0x140238bf0`
- `0x1402bd244`
- `0x1402bd3fc`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14002a6fb`
- `ntoskrnl!KeBugCheckEx` at `0x14002a6fb`
- `ntoskrnl!ExRaiseStatus` at `0x14002a756`
- `ntoskrnl!ExRaiseStatus` at `0x14002a756`
- `ntoskrnl!ProbeForWrite` at `0x14002a632`
- `ntoskrnl!ProbeForWrite` at `0x14002a711`
- `ntoskrnl!ProbeForWrite` at `0x14002a740`
- `ntoskrnl!ProbeForWrite` at `0x14002a632`
- `ntoskrnl!ProbeForWrite` at `0x14002a711`
- `ntoskrnl!ProbeForWrite` at `0x14002a740`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14002a60a`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14002a71f`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14002a60a`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14002a71f`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14002a879`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14002a879`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002a593`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002a593`

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
0x14002a520  mov     rax, rsp
0x14002a523  mov     [rax+8], rbx
0x14002a527  mov     [rax+10h], rsi
0x14002a52b  mov     [rax+18h], r8
0x14002a52f  push    rdi
0x14002a530  push    r12
0x14002a532  push    r13
0x14002a534  push    r14
0x14002a536  push    r15
0x14002a538  sub     rsp, 0D0h
0x14002a53f  movaps  xmmword ptr [rax-38h], xmm6
0x14002a543  mov     r12, r9
0x14002a546  mov     rsi, r8
0x14002a549  mov     rbx, rdx
0x14002a54c  mov     edi, ecx
0x14002a54e  xor     r14d, r14d
0x14002a551  mov     [rax-78h], r14
0x14002a555  mov     [rsp+0F8h+var_C4], r14d
0x14002a55a  mov     [rsp+0F8h+var_C0], 0FFFFFFFFh
0x14002a562  xorps   xmm6, xmm6
0x14002a565  movups  xmmword ptr [rax-70h], xmm6
0x14002a569  movups  xmmword ptr [rax-64h], xmm6
0x14002a56d  lea     rcx, [rsp+0F8h+BugCheckParameter2]
0x14002a572  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x14002a577  lea     ecx, [r14+1]
0x14002a57b  mov     [rsp+0F8h+var_C8], cl
0x14002a57f  mov     edx, ecx
0x14002a581  call    EnterSharedCrit
0x14002a586  lea     rcx, [rsp+0F8h+var_50]
0x14002a58e  call    ?CreateWithUserCritHeld@DISPLAYCONFIG_USER_SESSION_STATE@@SA?AV1@XZ; DISPLAYCONFIG_USER_SESSION_STATE::CreateWithUserCritHeld(void)
0x14002a593  call    cs:__imp_W32GetUserGdiSessionState
0x14002a59a  nop     dword ptr [rax+rax+00h]
0x14002a59f  cmp     [rax+20h], r14d
0x14002a5a3  jz      loc_14002A8A6
0x14002a5a9  test    edi, 0FFFFFF88h
0x14002a5af  jnz     loc_14002A949
0x14002a5b5  mov     r15d, edi
0x14002a5b8  and     r15d, 7
0x14002a5bc  lea     eax, [r15-1]
0x14002a5c0  test    eax, 0FFFFFFFCh
0x14002a5c5  jnz     loc_14002A949
0x14002a5cb  cmp     r15d, 3
0x14002a5cf  jz      loc_14002A949
0x14002a5d5  call    UserIsWddmConnectedSession
0x14002a5da  test    eax, eax
0x14002a5dc  jz      loc_14002A8B0
0x14002a5e2  cmp     [rsp+0F8h+var_48], r14b
0x14002a5ea  jz      loc_14002A8BA
0x14002a5f0  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14002a5f5  nop
0x14002a5f6  mov     rcx, rbx
0x14002a5f9  call    RtlReadULongFromUser
0x14002a5fe  mov     [rsp+0F8h+var_C4], eax
0x14002a602  test    eax, eax
0x14002a604  jz      loc_14002A6D1
0x14002a60a  call    cs:__imp_PsGetCurrentProcessWow64Process
0x14002a611  nop     dword ptr [rax+rax+00h]
0x14002a616  neg     rax
0x14002a619  sbb     r8d, r8d
0x14002a61c  and     r8d, 0FFFFFFFDh
0x14002a620  add     r8d, 4; Alignment
0x14002a624  mov     eax, [rsp+0F8h+var_C4]
0x14002a628  imul    rdx, rax, 0D8h; Length
0x14002a62f  mov     rcx, rsi; Address
0x14002a632  call    cs:__imp_ProbeForWrite
0x14002a639  nop     dword ptr [rax+rax+00h]
0x14002a63e  mov     eax, [rsp+0F8h+var_C4]
0x14002a642  imul    rdx, rax, 0D8h; unsigned __int64
0x14002a649  mov     r8d, 63447355h; unsigned int
0x14002a64f  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14002a654  mov     r13, rax
0x14002a657  mov     [rsp+0F8h+var_78], rax
0x14002a65f  test    rax, rax
0x14002a662  jz      loc_14002A751
0x14002a668  cmp     [rsp+0F8h+var_80], 0FFFFFFFFFFFFFFFFh
0x14002a66e  jnz     short loc_14002A6DF
0x14002a670  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14002a675  mov     rcx, [rax+178h]
0x14002a67c  mov     [rsp+0F8h+BugCheckParameter2], rcx
0x14002a681  lea     rcx, [rsp+0F8h+BugCheckParameter2]
0x14002a686  mov     [rax+178h], rcx
0x14002a68d  mov     [rsp+0F8h+var_88], r13
0x14002a692  lea     rax, GreDeleteFastMutex
0x14002a699  mov     [rsp+0F8h+var_80], rax
0x14002a69e  mov     eax, edi
0x14002a6a0  lea     esi, [r14+4]
0x14002a6a4  and     eax, esi
0x14002a6a6  mov     [rsp+0F8h+var_B8], eax
0x14002a6aa  jnz     short loc_14002A708
0x14002a6ac  test    r12, r12
0x14002a6af  jz      short loc_14002A6BF
0x14002a6b1  mov     edi, 0C000000Dh
0x14002a6b6  mov     [rsp+0F8h+var_BC], edi
0x14002a6ba  jmp     loc_14002A76C
0x14002a6bf  mov     r14, [rsp+0F8h+Address]
0x14002a6c7  test    r14, r14
0x14002a6ca  jnz     short loc_14002A71F
0x14002a6cc  jmp     loc_14002A7A5
0x14002a6d1  mov     edi, 0C000000Dh
0x14002a6d6  mov     [rsp+0F8h+var_BC], edi
0x14002a6da  jmp     loc_14002A76C
0x14002a6df  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14002a6e4  mov     [rsp+0F8h+BugCheckParameter4], rax; BugCheckParameter4
0x14002a6e9  mov     r9, r13; BugCheckParameter3
0x14002a6ec  lea     r8, [rsp+0F8h+BugCheckParameter2]; BugCheckParameter2
0x14002a6f1  mov     edx, 12h; BugCheckParameter1
0x14002a6f6  mov     ecx, 164h; BugCheckCode
0x14002a6fb  call    cs:__imp_KeBugCheckEx
0x14002a708  mov     r8d, esi; Alignment
0x14002a70b  mov     rdx, rsi; Length
0x14002a70e  mov     rcx, r12; Address
0x14002a711  call    cs:__imp_ProbeForWrite
0x14002a718  nop     dword ptr [rax+rax+00h]
0x14002a71d  jmp     short loc_14002A6BF
0x14002a71f  call    cs:__imp_PsGetCurrentProcessWow64Process
0x14002a726  nop     dword ptr [rax+rax+00h]
0x14002a72b  neg     rax
0x14002a72e  sbb     r8d, r8d
0x14002a731  and     r8d, 0FFFFFFFDh
0x14002a735  add     r8d, esi; Alignment
0x14002a738  mov     edx, 1Ch; Length
0x14002a73d  mov     rcx, r14; Address
0x14002a740  call    cs:__imp_ProbeForWrite
0x14002a747  nop     dword ptr [rax+rax+00h]
0x14002a74c  jmp     loc_14002A6CC
0x14002a751  mov     ecx, 0C0000017h; Status
0x14002a756  call    cs:__imp_ExRaiseStatus
0x14002a763  mov     edi, 0C000000Dh
0x14002a768  mov     [rsp+0F8h+var_BC], edi
0x14002a76c  lea     rcx, [rsp+0F8h+var_C8]; this
0x14002a771  call    ??1MaybeEnterLeaveCritSharedOnly@@QEAA@XZ; MaybeEnterLeaveCritSharedOnly::~MaybeEnterLeaveCritSharedOnly(void)
0x14002a776  lea     rcx, [rsp+0F8h+BugCheckParameter2]
0x14002a77b  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x14002a780  mov     eax, edi
0x14002a782  lea     r11, [rsp+0F8h+var_28]
0x14002a78a  mov     rbx, [r11+30h]
0x14002a78e  mov     rsi, [r11+38h]
0x14002a792  movaps  xmm6, xmmword ptr [r11-10h]
0x14002a797  mov     rsp, r11
0x14002a79a  pop     r15
0x14002a79c  pop     r14
0x14002a79e  pop     r13
0x14002a7a0  pop     r12
0x14002a7a2  pop     rdi
0x14002a7a3  retn
0x14002a7a5  xor     sil, sil
0x14002a7a8  cmp     r15d, 4
0x14002a7ac  jz      loc_14002A879
0x14002a7b2  mov     r15d, 1
0x14002a7b8  test    sil, sil
0x14002a7bb  jnz     loc_14002A8C4
0x14002a7c1  test    r14, r14
0x14002a7c4  jnz     loc_14002A8D2
0x14002a7ca  mov     [rsp+0F8h+var_C8], 0
0x14002a7cf  lea     r9, [rsp+0F8h+var_C0]
0x14002a7d4  xor     eax, eax
0x14002a7d6  test    sil, sil
0x14002a7d9  cmovnz  r9, rax
0x14002a7dd  mov     r8, r13
0x14002a7e0  lea     rdx, [rsp+0F8h+var_C4]
0x14002a7e5  mov     ecx, edi
0x14002a7e7  call    DrvQueryDisplayConfigAndLeaveUserCrit
0x14002a7ec  mov     edi, eax
0x14002a7ee  test    eax, eax
0x14002a7f0  js      short loc_14002A7FB
0x14002a7f2  test    sil, sil
0x14002a7f5  jnz     loc_14002A8EC
0x14002a7fb  cmp     edi, 0C0000023h
0x14002a801  jnz     short loc_14002A862
0x14002a803  mov     eax, [rsp+0F8h+var_C4]
0x14002a807  imul    r8, rax, 0D8h; Size
0x14002a80e  mov     rdx, r13; Src
0x14002a811  mov     rcx, [rsp+0F8h+arg_10]; void *
0x14002a819  call    RtlCopyVolatileMemory
0x14002a81e  mov     edx, [rsp+0F8h+var_C4]
0x14002a822  mov     rcx, rbx
0x14002a825  call    RtlWriteULongToUser
0x14002a82a  cmp     [rsp+0F8h+var_B8], 0
0x14002a82f  jnz     short loc_14002A849
0x14002a831  test    r14, r14
0x14002a834  jz      short loc_14002A853
0x14002a836  movups  xmm0, xmmword ptr [rsp+0F8h+var_70]
0x14002a83e  movups  xmmword ptr [r14], xmm0
0x14002a842  movups  xmmword ptr [r14+0Ch], xmm6
0x14002a847  jmp     short loc_14002A853
0x14002a849  mov     eax, [rsp+0F8h+var_C0]
0x14002a84d  mov     [r12], eax
0x14002a851  jmp     short loc_14002A831
0x14002a853  jmp     loc_14002A76C
0x14002a858  mov     edi, 0C000000Dh
0x14002a85d  jmp     loc_14002A76C
0x14002a862  cmp     edi, 80000005h
0x14002a868  jz      loc_14002A93F
0x14002a86e  mov     ecx, edi
0x14002a870  call    _QdcSdcTranslateStatusDefault
0x14002a875  mov     edi, eax
0x14002a877  jmp     short loc_14002A803
0x14002a879  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x14002a880  nop     dword ptr [rax+rax+00h]
0x14002a885  mov     rax, [rax+218h]
0x14002a88c  call    _guard_dispatch_icall
0x14002a891  movzx   esi, sil
0x14002a895  test    al, al
0x14002a897  mov     r15d, 1
0x14002a89d  cmovnz  esi, r15d
0x14002a8a1  jmp     loc_14002A7B8
0x14002a8a6  mov     edi, 0C0000001h
0x14002a8ab  jmp     loc_14002A76C
0x14002a8b0  mov     edi, 0C0000022h
0x14002a8b5  jmp     loc_14002A76C
0x14002a8ba  mov     edi, 0C00000BBh
0x14002a8bf  jmp     loc_14002A76C
0x14002a8c4  and     edi, 0FFFFFFFAh
0x14002a8c7  or      edi, 10000002h
0x14002a8cd  jmp     loc_14002A7C1
0x14002a8d2  lea     rcx, [rsp+0F8h+var_70]
0x14002a8da  call    DrvSampleDisplayState
0x14002a8df  movups  xmm6, xmmword ptr [rsp+0F8h+var_70+0Ch]
0x14002a8e7  jmp     loc_14002A7CA
0x14002a8ec  cmp     [rsp+0F8h+var_C4], r15d
0x14002a8f1  ja      short loc_14002A8FD
0x14002a8f3  mov     [rsp+0F8h+var_C0], r15d
0x14002a8f8  jmp     loc_14002A7FB
0x14002a8fd  mov     ecx, r15d
0x14002a900  jbe     short loc_14002A92A
0x14002a902  mov     edx, [r13+74h]
0x14002a906  mov     eax, ecx
0x14002a908  imul    rax, 0D8h
0x14002a90f  cmp     edx, [rax+r13+74h]
0x14002a914  jnz     short loc_14002A92A
0x14002a916  mov     eax, [rax+r13+78h]
0x14002a91b  cmp     [r13+78h], eax
0x14002a91f  jnz     short loc_14002A92A
0x14002a921  add     ecx, r15d
0x14002a924  cmp     ecx, [rsp+0F8h+var_C4]
0x14002a928  jb      short loc_14002A906
0x14002a92a  cmp     ecx, [rsp+0F8h+var_C4]
0x14002a92e  sbb     eax, eax
0x14002a930  and     eax, 2
0x14002a933  add     eax, 2
0x14002a936  mov     [rsp+0F8h+var_C0], eax
0x14002a93a  jmp     loc_14002A7FB
0x14002a93f  mov     edi, 0C0000023h
0x14002a944  jmp     loc_14002A803
0x14002a949  mov     edi, 0C000000Dh
0x14002a94e  jmp     loc_14002A76C
0x14023958e  push    rbp
0x140239590  sub     rsp, 30h
0x140239594  mov     rbp, rdx
0x140239597  mov     rax, [rcx]
0x14023959a  mov     ecx, [rax]
0x14023959c  mov     [rbp+58h], ecx
0x14023959f  mov     ecx, [rbp+58h]
0x1402395a2  call    SetLastNtError
0x1402395a7  mov     dword ptr [rbp+60h], 1
0x1402395ae  mov     eax, [rbp+60h]
0x1402395b1  add     rsp, 30h
0x1402395b5  pop     rbp
0x1402395b6  retn
0x1402395b8  push    rbp
0x1402395ba  sub     rsp, 30h
0x1402395be  mov     rbp, rdx
0x1402395c1  mov     rax, [rcx]
0x1402395c4  mov     ecx, [rax]
0x1402395c6  mov     [rbp+48h], ecx
0x1402395c9  mov     ecx, [rbp+48h]
0x1402395cc  call    SetLastNtError
0x1402395d1  mov     dword ptr [rbp+50h], 1
0x1402395d8  mov     eax, [rbp+50h]
0x1402395db  add     rsp, 30h
0x1402395df  pop     rbp
0x1402395e0  retn
```

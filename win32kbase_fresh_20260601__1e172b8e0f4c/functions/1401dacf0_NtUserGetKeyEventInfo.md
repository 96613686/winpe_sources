# NtUserGetKeyEventInfo

- ea: `0x1401dacf0`
- end: `0x1401db073`
- name: `NtUserGetKeyEventInfo`
- size: `899`
- prototype: `__int64 __fastcall(int, int, int, int, __int16, __int64, int, __int64, int, __int64, volatile void *Address, volatile void *, volatile void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x140012c80`
- `0x140013164`
- `0x140029324`
- `0x140029fe8`
- `0x14002ab14`
- `0x14002b0b4`
- `0x14002b2d0`
- `0x140043810`
- `0x1400757c8`
- `0x1400759e0`
- `0x1400e0460`
- `0x1400e0800`
- `0x1401b49e0`
- `0x1401dacf0`
- `0x140238b10`
- `0x140239180`

## import_xrefs

- `ntoskrnl!ExRaiseAccessViolation` at `0x1401dae22`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401dae57`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401dae22`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401dae57`
- `ntoskrnl!KeBugCheckEx` at `0x1401daef6`
- `ntoskrnl!KeBugCheckEx` at `0x1401daef6`
- `ntoskrnl!ExRaiseStatus` at `0x1401daeb8`
- `ntoskrnl!ExRaiseStatus` at `0x1401daeb8`
- `ntoskrnl!ProbeForWrite` at `0x1401dadfc`
- `ntoskrnl!ProbeForWrite` at `0x1401dae43`
- `ntoskrnl!ProbeForWrite` at `0x1401dae74`
- `ntoskrnl!ProbeForWrite` at `0x1401daf48`
- `ntoskrnl!ProbeForWrite` at `0x1401daf5f`
- `ntoskrnl!ProbeForWrite` at `0x1401dadfc`
- `ntoskrnl!ProbeForWrite` at `0x1401dae43`
- `ntoskrnl!ProbeForWrite` at `0x1401dae74`
- `ntoskrnl!ProbeForWrite` at `0x1401daf48`
- `ntoskrnl!ProbeForWrite` at `0x1401daf5f`

## pseudocode

```c
__int64 __fastcall NtUserGetKeyEventInfo(
        unsigned int a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        __int16 a5,
        __int64 a6,
        int a7,
        volatile void *a8,
        int a9,
        volatile void *a10,
        volatile void *Address,
        unsigned int *a12,
        _QWORD *a13)
{
  char v13; // si
  unsigned __int64 v14; // rcx
  __int64 *p_Src; // rdi
  struct tagTHREADINFO *BugCheckParameter4; // rax
  struct tagTHREADINFO *v17; // rax
  unsigned int v18; // ebx
  int KeyboardType; // r14d
  struct tagTHREADINFO *v24; // [rsp+90h] [rbp-78h] BYREF
  ULONG_PTR BugCheckParameter2[2]; // [rsp+98h] [rbp-70h] BYREF
  __int64 (__fastcall *v26)(PVOID); // [rsp+A8h] [rbp-60h]
  __int64 v27; // [rsp+B0h] [rbp-58h]
  volatile void *v28; // [rsp+B8h] [rbp-50h]
  __int64 Src; // [rsp+C0h] [rbp-48h] BYREF

  v27 = a6;
  v28 = Address;
  Src = 0;
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  EnterLeaveCritShared::EnterLeaveCritShared(&v24, 1);
  v24 = PtiCurrent();
  if ( a7 > 0 && a9 > 0 && a12 && (v13 = 0, a13) )
  {
    ProbeForWrite(Address, 0x100u, 1u);
    GetKeyboardState(Address);
    ProbeForWrite(a8, 2LL * a7, 2u);
    if ( (unsigned __int64)a9 > 0x7FFFFFFFFFFFFFFFLL )
      ExRaiseAccessViolation();
    ProbeForWrite(a10, 2LL * a9, 2u);
    if ( (unsigned __int64)a7 >= 4 )
    {
      p_Src = (__int64 *)Win32AllocPoolWithQuotaZInitImpl(v14, 2LL * a7, 0x62757355u);
      if ( !p_Src )
        ExRaiseStatus(-1073741801);
      v13 = 1;
      if ( v26 != (__int64 (__fastcall *)(PVOID))-1LL )
      {
        BugCheckParameter4 = PtiCurrent();
        KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)p_Src, (ULONG_PTR)BugCheckParameter4);
      }
      v17 = PtiCurrent();
      BugCheckParameter2[0] = *((_QWORD *)v17 + 47);
      *((_QWORD *)v17 + 47) = BugCheckParameter2;
      BugCheckParameter2[1] = (ULONG_PTR)p_Src;
      v26 = GreDeleteFastMutex;
    }
    else
    {
      p_Src = &Src;
    }
    ProbeForWrite(a12, 4u, 4u);
    ProbeForWrite(a13, 8u, 8u);
    v18 = xxxToUnicodeEx(a1, a7, a5, a4, v27);
    GetKeyNameText(a3, a10, (unsigned int)a9);
    KeyboardType = GetKeyboardType(2147483646);
    *a12 = ((unsigned int)GetKeyboardType(0x7FFFFFFF) << 16) | KeyboardType;
    *a13 = *(unsigned int *)(*((_QWORD *)v24 + 58) + 520LL);
    memmove((void *)a8, p_Src, 2LL * a7);
    if ( v13 )
      Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&void Win32FreePool(void *),1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
  }
  else
  {
    v18 = 0;
    UserSetLastError(87);
  }
  UserSessionSwitchLeaveCritWithNonPaged();
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  return v18;
}

```

## disassembly

```asm
0x1401dacf0  mov     r11, rsp
0x1401dacf3  push    rbx
0x1401dacf4  push    rsi
0x1401dacf5  push    rdi
0x1401dacf6  push    r12
0x1401dacf8  push    r13
0x1401dacfa  push    r14
0x1401dacfc  push    r15
0x1401dacfe  sub     rsp, 0D0h
0x1401dad05  mov     rax, cs:__security_cookie
0x1401dad0c  xor     rax, rsp
0x1401dad0f  mov     [rsp+108h+var_40], rax
0x1401dad17  mov     [rsp+108h+var_C4], r9d
0x1401dad1c  mov     [rsp+108h+var_B4], r8d
0x1401dad21  mov     [rsp+108h+var_BC], edx
0x1401dad25  mov     [rsp+108h+var_B8], ecx
0x1401dad29  mov     rax, [rsp+108h+arg_28]
0x1401dad31  mov     [rsp+108h+var_58], rax
0x1401dad39  movsxd  rdi, [rsp+108h+arg_30]
0x1401dad41  mov     rax, [rsp+108h+arg_38]
0x1401dad49  mov     [rsp+108h+var_80], rax
0x1401dad51  mov     rax, [rsp+108h+arg_48]
0x1401dad59  mov     [rsp+108h+var_88], rax
0x1401dad61  mov     rbx, [rsp+108h+Address]
0x1401dad69  mov     [rsp+108h+var_50], rbx
0x1401dad71  mov     r12, [rsp+108h+arg_58]
0x1401dad79  mov     r13, [rsp+108h+arg_60]
0x1401dad81  mov     qword ptr [r11-48h], 0
0x1401dad89  mov     [rsp+108h+var_90], 0
0x1401dad92  lea     rcx, [r11-70h]
0x1401dad96  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401dad9b  mov     r15d, 1
0x1401dada1  mov     edx, r15d
0x1401dada4  lea     rcx, [rsp+108h+var_78]
0x1401dadac  call    ??0EnterLeaveCritShared@@QEAA@W4HandleToObjILCheck@@@Z; EnterLeaveCritShared::EnterLeaveCritShared(HandleToObjILCheck)
0x1401dadb1  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401dadb6  mov     [rsp+108h+var_78], rax
0x1401dadbe  test    edi, edi
0x1401dadc0  jle     loc_1401DB031
0x1401dadc6  movsxd  r14, [rsp+108h+arg_40]
0x1401dadce  test    r14d, r14d
0x1401dadd1  jle     loc_1401DB031
0x1401dadd7  test    r12, r12
0x1401dadda  jz      loc_1401DB031
0x1401dade0  xor     sil, sil
0x1401dade3  mov     [rsp+108h+var_C8], sil
0x1401dade8  test    r13, r13
0x1401dadeb  jz      loc_1401DB031
0x1401dadf1  mov     r8d, r15d; Alignment
0x1401dadf4  mov     edx, 100h; Length
0x1401dadf9  mov     rcx, rbx; Address
0x1401dadfc  call    cs:__imp_ProbeForWrite
0x1401dae03  nop     dword ptr [rax+rax+00h]
0x1401dae08  mov     rcx, rbx
0x1401dae0b  call    _GetKeyboardState
0x1401dae10  mov     rbx, rdi
0x1401dae13  mov     rdi, 7FFFFFFFFFFFFFFFh
0x1401dae1d  cmp     rbx, rdi
0x1401dae20  jbe     short loc_1401DAE2E
0x1401dae22  call    cs:__imp_ExRaiseAccessViolation
0x1401dae29  nop     dword ptr [rax+rax+00h]
0x1401dae2e  lea     r15, [rbx+rbx]
0x1401dae32  mov     r8d, 2; Alignment
0x1401dae38  mov     rdx, r15; Length
0x1401dae3b  mov     rcx, [rsp+108h+var_80]; Address
0x1401dae43  call    cs:__imp_ProbeForWrite
0x1401dae4a  nop     dword ptr [rax+rax+00h]
0x1401dae4f  mov     rdx, r14
0x1401dae52  cmp     r14, rdi
0x1401dae55  jbe     short loc_1401DAE63
0x1401dae57  call    cs:__imp_ExRaiseAccessViolation
0x1401dae5e  nop     dword ptr [rax+rax+00h]
0x1401dae63  add     rdx, rdx; Length
0x1401dae66  mov     r8d, 2; Alignment
0x1401dae6c  mov     rcx, [rsp+108h+var_88]; Address
0x1401dae74  call    cs:__imp_ProbeForWrite
0x1401dae7b  nop     dword ptr [rax+rax+00h]
0x1401dae80  cmp     rbx, 4
0x1401dae84  jnb     short loc_1401DAE98
0x1401dae86  lea     rdi, [rsp+108h+Src]
0x1401dae8e  mov     [rsp+108h+var_90], rdi
0x1401dae93  jmp     loc_1401DAF3D
0x1401dae98  mov     r8d, 62757355h; unsigned int
0x1401dae9e  mov     rdx, r15; unsigned __int64
0x1401daea1  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401daea6  mov     rdi, rax
0x1401daea9  mov     [rsp+108h+var_90], rax
0x1401daeae  test    rax, rax
0x1401daeb1  jnz     short loc_1401DAEC4
0x1401daeb3  mov     ecx, 0C0000017h; Status
0x1401daeb8  call    cs:__imp_ExRaiseStatus
0x1401daec4  mov     sil, 1
0x1401daec7  mov     [rsp+108h+var_C8], sil
0x1401daecc  cmp     [rsp+108h+var_60], 0FFFFFFFFFFFFFFFFh
0x1401daed5  jz      short loc_1401DAF03
0x1401daed7  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401daedc  mov     [rsp+108h+BugCheckParameter4], rax; BugCheckParameter4
0x1401daee1  mov     r9, rdi; BugCheckParameter3
0x1401daee4  lea     r8, [rsp+108h+BugCheckParameter2]; BugCheckParameter2
0x1401daeec  mov     edx, 12h; BugCheckParameter1
0x1401daef1  mov     ecx, 164h; BugCheckCode
0x1401daef6  call    cs:__imp_KeBugCheckEx
0x1401daf03  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401daf08  mov     rcx, [rax+178h]
0x1401daf0f  mov     [rsp+108h+BugCheckParameter2], rcx
0x1401daf17  lea     rcx, [rsp+108h+BugCheckParameter2]
0x1401daf1f  mov     [rax+178h], rcx
0x1401daf26  mov     [rsp+108h+var_68], rdi
0x1401daf2e  lea     rax, GreDeleteFastMutex
0x1401daf35  mov     [rsp+108h+var_60], rax
0x1401daf3d  mov     edx, 4; Length
0x1401daf42  mov     r8d, edx; Alignment
0x1401daf45  mov     rcx, r12; Address
0x1401daf48  call    cs:__imp_ProbeForWrite
0x1401daf4f  nop     dword ptr [rax+rax+00h]
0x1401daf54  mov     edx, 8; Length
0x1401daf59  mov     r8d, edx; Alignment
0x1401daf5c  mov     rcx, r13; Address
0x1401daf5f  call    cs:__imp_ProbeForWrite
0x1401daf66  nop     dword ptr [rax+rax+00h]
0x1401daf6b  nop
0x1401daf6c  mov     rax, [rsp+108h+var_58]
0x1401daf74  mov     [rsp+108h+var_D0], rax
0x1401daf79  mov     eax, [rsp+108h+var_C4]
0x1401daf7d  mov     [rsp+108h+var_D8], eax
0x1401daf81  movzx   eax, [rsp+108h+arg_20]
0x1401daf89  mov     [rsp+108h+var_E0], ax
0x1401daf8e  mov     dword ptr [rsp+108h+BugCheckParameter4], ebx
0x1401daf92  mov     r9, rdi
0x1401daf95  mov     r8, [rsp+108h+var_50]
0x1401daf9d  mov     edx, [rsp+108h+var_BC]
0x1401dafa1  mov     ecx, [rsp+108h+var_B8]
0x1401dafa5  call    xxxToUnicodeEx
0x1401dafaa  mov     ebx, eax
0x1401dafac  mov     r8d, r14d
0x1401dafaf  mov     rdx, [rsp+108h+var_88]
0x1401dafb7  mov     ecx, [rsp+108h+var_B4]
0x1401dafbb  call    _GetKeyNameText
0x1401dafc0  mov     ecx, 7FFFFFFEh
0x1401dafc5  call    _GetKeyboardType
0x1401dafca  mov     r14d, eax
0x1401dafcd  mov     ecx, 7FFFFFFFh
0x1401dafd2  call    _GetKeyboardType
0x1401dafd7  shl     eax, 10h
0x1401dafda  or      r14d, eax
0x1401dafdd  mov     [r12], r14d
0x1401dafe1  mov     rax, [rsp+108h+var_78]
0x1401dafe9  mov     rax, [rax+1D0h]
0x1401daff0  mov     r9d, [rax+208h]
0x1401daff7  mov     [r13+0], r9
0x1401daffb  mov     r8, r15; Size
0x1401daffe  mov     rdx, rdi; Src
0x1401db001  mov     rcx, [rsp+108h+var_80]; void *
0x1401db009  call    memmove
0x1401db00e  jmp     short loc_1401DB017
0x1401db010  xor     ebx, ebx
0x1401db012  mov     sil, [rsp+108h+var_C8]
0x1401db017  test    sil, sil
0x1401db01a  jz      short loc_1401DB03B
0x1401db01c  xor     edx, edx
0x1401db01e  lea     rcx, [rsp+108h+BugCheckParameter2]; BugCheckParameter2
0x1401db026  call    ?UnlockWorker@?$Win32RawLockedItemBase@UDISPLAYCONFIG_DEVICE_INFO_HEADER@@$1?Win32FreePool@@YAXPEAX@Z$00$00$00@@AEAAX_N0@Z; Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&Win32FreePool(void *),1,1,1>::UnlockWorker(bool,bool)
0x1401db02b  jmp     short loc_1401DB03B
0x1401db02d  xor     ebx, ebx
0x1401db02f  jmp     short loc_1401DB03B
0x1401db031  xor     ebx, ebx
0x1401db033  lea     ecx, [rbx+57h]
0x1401db036  call    UserSetLastError
0x1401db03b  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401db040  lea     rcx, [rsp+108h+BugCheckParameter2]
0x1401db048  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401db04d  mov     eax, ebx
0x1401db04f  mov     rcx, [rsp+108h+var_40]
0x1401db057  xor     rcx, rsp; StackCookie
0x1401db05a  call    __security_check_cookie
0x1401db05f  add     rsp, 0D0h
0x1401db066  pop     r15
0x1401db068  pop     r14
0x1401db06a  pop     r13
0x1401db06c  pop     r12
0x1401db06e  pop     rdi
0x1401db06f  pop     rsi
0x1401db070  pop     rbx
0x1401db071  retn
0x14023a581  push    rbp
0x14023a583  sub     rsp, 40h
0x14023a587  mov     rbp, rdx
0x14023a58a  mov     rax, [rcx]
0x14023a58d  mov     ecx, [rax]
0x14023a58f  mov     [rbp+68h], ecx
0x14023a592  mov     ecx, [rbp+68h]
0x14023a595  call    SetLastNtError
0x14023a59a  mov     dword ptr [rbp+70h], 1
0x14023a5a1  mov     eax, [rbp+70h]
0x14023a5a4  add     rsp, 40h
0x14023a5a8  pop     rbp
0x14023a5a9  retn
0x14023a5ab  push    rbp
0x14023a5ad  sub     rsp, 40h
0x14023a5b1  mov     rbp, rdx
0x14023a5b4  mov     rax, [rcx]
0x14023a5b7  mov     ecx, [rax]
0x14023a5b9  mov     [rbp+58h], ecx
0x14023a5bc  mov     ecx, [rbp+58h]
0x14023a5bf  call    SetLastNtError
0x14023a5c4  mov     dword ptr [rbp+60h], 1
0x14023a5cb  mov     eax, [rbp+60h]
0x14023a5ce  add     rsp, 40h
0x14023a5d2  pop     rbp
0x14023a5d3  retn
```

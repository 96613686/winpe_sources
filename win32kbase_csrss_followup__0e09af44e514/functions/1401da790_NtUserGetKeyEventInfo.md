# NtUserGetKeyEventInfo

- ea: `0x1401da790`
- end: `0x1401dab13`
- name: `NtUserGetKeyEventInfo`
- size: `899`
- prototype: `__int64 __fastcall(int, int, int, int, __int16, __int64, int, __int64, int, __int64, volatile void *Address, volatile void *, volatile void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x14001bdf0`
- `0x14001c2d4`
- `0x1400325a4`
- `0x140033268`
- `0x140033d94`
- `0x140034334`
- `0x140034550`
- `0x14004c720`
- `0x140076968`
- `0x140076b80`
- `0x1400d67f0`
- `0x1400d6b90`
- `0x1401b4480`
- `0x1401da790`
- `0x140238160`
- `0x140238800`

## import_xrefs

- `ntoskrnl!ExRaiseAccessViolation` at `0x1401da8c2`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401da8f7`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401da8c2`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401da8f7`
- `ntoskrnl!KeBugCheckEx` at `0x1401da996`
- `ntoskrnl!KeBugCheckEx` at `0x1401da996`
- `ntoskrnl!ExRaiseStatus` at `0x1401da958`
- `ntoskrnl!ExRaiseStatus` at `0x1401da958`
- `ntoskrnl!ProbeForWrite` at `0x1401da89c`
- `ntoskrnl!ProbeForWrite` at `0x1401da8e3`
- `ntoskrnl!ProbeForWrite` at `0x1401da914`
- `ntoskrnl!ProbeForWrite` at `0x1401da9e8`
- `ntoskrnl!ProbeForWrite` at `0x1401da9ff`
- `ntoskrnl!ProbeForWrite` at `0x1401da89c`
- `ntoskrnl!ProbeForWrite` at `0x1401da8e3`
- `ntoskrnl!ProbeForWrite` at `0x1401da914`
- `ntoskrnl!ProbeForWrite` at `0x1401da9e8`
- `ntoskrnl!ProbeForWrite` at `0x1401da9ff`

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
0x1401da790  mov     r11, rsp
0x1401da793  push    rbx
0x1401da794  push    rsi
0x1401da795  push    rdi
0x1401da796  push    r12
0x1401da798  push    r13
0x1401da79a  push    r14
0x1401da79c  push    r15
0x1401da79e  sub     rsp, 0D0h
0x1401da7a5  mov     rax, cs:__security_cookie
0x1401da7ac  xor     rax, rsp
0x1401da7af  mov     [rsp+108h+var_40], rax
0x1401da7b7  mov     [rsp+108h+var_C4], r9d
0x1401da7bc  mov     [rsp+108h+var_B4], r8d
0x1401da7c1  mov     [rsp+108h+var_BC], edx
0x1401da7c5  mov     [rsp+108h+var_B8], ecx
0x1401da7c9  mov     rax, [rsp+108h+arg_28]
0x1401da7d1  mov     [rsp+108h+var_58], rax
0x1401da7d9  movsxd  rdi, [rsp+108h+arg_30]
0x1401da7e1  mov     rax, [rsp+108h+arg_38]
0x1401da7e9  mov     [rsp+108h+var_80], rax
0x1401da7f1  mov     rax, [rsp+108h+arg_48]
0x1401da7f9  mov     [rsp+108h+var_88], rax
0x1401da801  mov     rbx, [rsp+108h+Address]
0x1401da809  mov     [rsp+108h+var_50], rbx
0x1401da811  mov     r12, [rsp+108h+arg_58]
0x1401da819  mov     r13, [rsp+108h+arg_60]
0x1401da821  mov     qword ptr [r11-48h], 0
0x1401da829  mov     [rsp+108h+var_90], 0
0x1401da832  lea     rcx, [r11-70h]
0x1401da836  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401da83b  mov     r15d, 1
0x1401da841  mov     edx, r15d
0x1401da844  lea     rcx, [rsp+108h+var_78]
0x1401da84c  call    ??0EnterLeaveCritShared@@QEAA@W4HandleToObjILCheck@@@Z; EnterLeaveCritShared::EnterLeaveCritShared(HandleToObjILCheck)
0x1401da851  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401da856  mov     [rsp+108h+var_78], rax
0x1401da85e  test    edi, edi
0x1401da860  jle     loc_1401DAAD1
0x1401da866  movsxd  r14, [rsp+108h+arg_40]
0x1401da86e  test    r14d, r14d
0x1401da871  jle     loc_1401DAAD1
0x1401da877  test    r12, r12
0x1401da87a  jz      loc_1401DAAD1
0x1401da880  xor     sil, sil
0x1401da883  mov     [rsp+108h+var_C8], sil
0x1401da888  test    r13, r13
0x1401da88b  jz      loc_1401DAAD1
0x1401da891  mov     r8d, r15d; Alignment
0x1401da894  mov     edx, 100h; Length
0x1401da899  mov     rcx, rbx; Address
0x1401da89c  call    cs:__imp_ProbeForWrite
0x1401da8a3  nop     dword ptr [rax+rax+00h]
0x1401da8a8  mov     rcx, rbx
0x1401da8ab  call    _GetKeyboardState
0x1401da8b0  mov     rbx, rdi
0x1401da8b3  mov     rdi, 7FFFFFFFFFFFFFFFh
0x1401da8bd  cmp     rbx, rdi
0x1401da8c0  jbe     short loc_1401DA8CE
0x1401da8c2  call    cs:__imp_ExRaiseAccessViolation
0x1401da8c9  nop     dword ptr [rax+rax+00h]
0x1401da8ce  lea     r15, [rbx+rbx]
0x1401da8d2  mov     r8d, 2; Alignment
0x1401da8d8  mov     rdx, r15; Length
0x1401da8db  mov     rcx, [rsp+108h+var_80]; Address
0x1401da8e3  call    cs:__imp_ProbeForWrite
0x1401da8ea  nop     dword ptr [rax+rax+00h]
0x1401da8ef  mov     rdx, r14
0x1401da8f2  cmp     r14, rdi
0x1401da8f5  jbe     short loc_1401DA903
0x1401da8f7  call    cs:__imp_ExRaiseAccessViolation
0x1401da8fe  nop     dword ptr [rax+rax+00h]
0x1401da903  add     rdx, rdx; Length
0x1401da906  mov     r8d, 2; Alignment
0x1401da90c  mov     rcx, [rsp+108h+var_88]; Address
0x1401da914  call    cs:__imp_ProbeForWrite
0x1401da91b  nop     dword ptr [rax+rax+00h]
0x1401da920  cmp     rbx, 4
0x1401da924  jnb     short loc_1401DA938
0x1401da926  lea     rdi, [rsp+108h+Src]
0x1401da92e  mov     [rsp+108h+var_90], rdi
0x1401da933  jmp     loc_1401DA9DD
0x1401da938  mov     r8d, 62757355h; unsigned int
0x1401da93e  mov     rdx, r15; unsigned __int64
0x1401da941  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401da946  mov     rdi, rax
0x1401da949  mov     [rsp+108h+var_90], rax
0x1401da94e  test    rax, rax
0x1401da951  jnz     short loc_1401DA964
0x1401da953  mov     ecx, 0C0000017h; Status
0x1401da958  call    cs:__imp_ExRaiseStatus
0x1401da964  mov     sil, 1
0x1401da967  mov     [rsp+108h+var_C8], sil
0x1401da96c  cmp     [rsp+108h+var_60], 0FFFFFFFFFFFFFFFFh
0x1401da975  jz      short loc_1401DA9A3
0x1401da977  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401da97c  mov     [rsp+108h+BugCheckParameter4], rax; BugCheckParameter4
0x1401da981  mov     r9, rdi; BugCheckParameter3
0x1401da984  lea     r8, [rsp+108h+BugCheckParameter2]; BugCheckParameter2
0x1401da98c  mov     edx, 12h; BugCheckParameter1
0x1401da991  mov     ecx, 164h; BugCheckCode
0x1401da996  call    cs:__imp_KeBugCheckEx
0x1401da9a3  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401da9a8  mov     rcx, [rax+178h]
0x1401da9af  mov     [rsp+108h+BugCheckParameter2], rcx
0x1401da9b7  lea     rcx, [rsp+108h+BugCheckParameter2]
0x1401da9bf  mov     [rax+178h], rcx
0x1401da9c6  mov     [rsp+108h+var_68], rdi
0x1401da9ce  lea     rax, GreDeleteFastMutex
0x1401da9d5  mov     [rsp+108h+var_60], rax
0x1401da9dd  mov     edx, 4; Length
0x1401da9e2  mov     r8d, edx; Alignment
0x1401da9e5  mov     rcx, r12; Address
0x1401da9e8  call    cs:__imp_ProbeForWrite
0x1401da9ef  nop     dword ptr [rax+rax+00h]
0x1401da9f4  mov     edx, 8; Length
0x1401da9f9  mov     r8d, edx; Alignment
0x1401da9fc  mov     rcx, r13; Address
0x1401da9ff  call    cs:__imp_ProbeForWrite
0x1401daa06  nop     dword ptr [rax+rax+00h]
0x1401daa0b  nop
0x1401daa0c  mov     rax, [rsp+108h+var_58]
0x1401daa14  mov     [rsp+108h+var_D0], rax
0x1401daa19  mov     eax, [rsp+108h+var_C4]
0x1401daa1d  mov     [rsp+108h+var_D8], eax
0x1401daa21  movzx   eax, [rsp+108h+arg_20]
0x1401daa29  mov     [rsp+108h+var_E0], ax
0x1401daa2e  mov     dword ptr [rsp+108h+BugCheckParameter4], ebx
0x1401daa32  mov     r9, rdi
0x1401daa35  mov     r8, [rsp+108h+var_50]
0x1401daa3d  mov     edx, [rsp+108h+var_BC]
0x1401daa41  mov     ecx, [rsp+108h+var_B8]
0x1401daa45  call    xxxToUnicodeEx
0x1401daa4a  mov     ebx, eax
0x1401daa4c  mov     r8d, r14d
0x1401daa4f  mov     rdx, [rsp+108h+var_88]
0x1401daa57  mov     ecx, [rsp+108h+var_B4]
0x1401daa5b  call    _GetKeyNameText
0x1401daa60  mov     ecx, 7FFFFFFEh
0x1401daa65  call    _GetKeyboardType
0x1401daa6a  mov     r14d, eax
0x1401daa6d  mov     ecx, 7FFFFFFFh
0x1401daa72  call    _GetKeyboardType
0x1401daa77  shl     eax, 10h
0x1401daa7a  or      r14d, eax
0x1401daa7d  mov     [r12], r14d
0x1401daa81  mov     rax, [rsp+108h+var_78]
0x1401daa89  mov     rax, [rax+1D0h]
0x1401daa90  mov     r9d, [rax+208h]
0x1401daa97  mov     [r13+0], r9
0x1401daa9b  mov     r8, r15; Size
0x1401daa9e  mov     rdx, rdi; Src
0x1401daaa1  mov     rcx, [rsp+108h+var_80]; void *
0x1401daaa9  call    memmove
0x1401daaae  jmp     short loc_1401DAAB7
0x1401daab0  xor     ebx, ebx
0x1401daab2  mov     sil, [rsp+108h+var_C8]
0x1401daab7  test    sil, sil
0x1401daaba  jz      short loc_1401DAADB
0x1401daabc  xor     edx, edx
0x1401daabe  lea     rcx, [rsp+108h+BugCheckParameter2]; BugCheckParameter2
0x1401daac6  call    ?UnlockWorker@?$Win32RawLockedItemBase@UDISPLAYCONFIG_DEVICE_INFO_HEADER@@$1?Win32FreePool@@YAXPEAX@Z$00$00$00@@AEAAX_N0@Z; Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&Win32FreePool(void *),1,1,1>::UnlockWorker(bool,bool)
0x1401daacb  jmp     short loc_1401DAADB
0x1401daacd  xor     ebx, ebx
0x1401daacf  jmp     short loc_1401DAADB
0x1401daad1  xor     ebx, ebx
0x1401daad3  lea     ecx, [rbx+57h]
0x1401daad6  call    UserSetLastError
0x1401daadb  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401daae0  lea     rcx, [rsp+108h+BugCheckParameter2]
0x1401daae8  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401daaed  mov     eax, ebx
0x1401daaef  mov     rcx, [rsp+108h+var_40]
0x1401daaf7  xor     rcx, rsp; StackCookie
0x1401daafa  call    __security_check_cookie
0x1401daaff  add     rsp, 0D0h
0x1401dab06  pop     r15
0x1401dab08  pop     r14
0x1401dab0a  pop     r13
0x1401dab0c  pop     r12
0x1401dab0e  pop     rdi
0x1401dab0f  pop     rsi
0x1401dab10  pop     rbx
0x1401dab11  retn
0x140239bf7  push    rbp
0x140239bf9  sub     rsp, 40h
0x140239bfd  mov     rbp, rdx
0x140239c00  mov     rax, [rcx]
0x140239c03  mov     ecx, [rax]
0x140239c05  mov     [rbp+68h], ecx
0x140239c08  mov     ecx, [rbp+68h]
0x140239c0b  call    SetLastNtError
0x140239c10  mov     dword ptr [rbp+70h], 1
0x140239c17  mov     eax, [rbp+70h]
0x140239c1a  add     rsp, 40h
0x140239c1e  pop     rbp
0x140239c1f  retn
0x140239c21  push    rbp
0x140239c23  sub     rsp, 40h
0x140239c27  mov     rbp, rdx
0x140239c2a  mov     rax, [rcx]
0x140239c2d  mov     ecx, [rax]
0x140239c2f  mov     [rbp+58h], ecx
0x140239c32  mov     ecx, [rbp+58h]
0x140239c35  call    SetLastNtError
0x140239c3a  mov     dword ptr [rbp+60h], 1
0x140239c41  mov     eax, [rbp+60h]
0x140239c44  add     rsp, 40h
0x140239c48  pop     rbp
0x140239c49  retn
```

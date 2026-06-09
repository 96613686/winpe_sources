# NtUserGetKeyEventInfo

- ea: `0x1401db2d0`
- end: `0x1401db653`
- name: `NtUserGetKeyEventInfo`
- size: `899`
- prototype: `__int64 __fastcall(unsigned int, __int64, unsigned int, int, __int16, __int64, int, volatile void *, int, volatile void *, volatile void *Address, unsigned int *, _QWORD *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x140029710`
- `0x140029bf4`
- `0x14004dd98`
- `0x14004dfb0`
- `0x14006f3a4`
- `0x1400700d8`
- `0x140070518`
- `0x1400709e4`
- `0x140070c00`
- `0x14007df80`
- `0x1400c9b60`
- `0x1400c9f70`
- `0x1401b5600`
- `0x1401db2d0`
- `0x1402388e0`
- `0x140238f80`

## import_xrefs

- `ntoskrnl!ExRaiseAccessViolation` at `0x1401db402`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401db437`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401db402`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401db437`
- `ntoskrnl!KeBugCheckEx` at `0x1401db4d6`
- `ntoskrnl!KeBugCheckEx` at `0x1401db4d6`
- `ntoskrnl!ExRaiseStatus` at `0x1401db498`
- `ntoskrnl!ExRaiseStatus` at `0x1401db498`
- `ntoskrnl!ProbeForWrite` at `0x1401db3dc`
- `ntoskrnl!ProbeForWrite` at `0x1401db423`
- `ntoskrnl!ProbeForWrite` at `0x1401db454`
- `ntoskrnl!ProbeForWrite` at `0x1401db528`
- `ntoskrnl!ProbeForWrite` at `0x1401db53f`
- `ntoskrnl!ProbeForWrite` at `0x1401db3dc`
- `ntoskrnl!ProbeForWrite` at `0x1401db423`
- `ntoskrnl!ProbeForWrite` at `0x1401db454`
- `ntoskrnl!ProbeForWrite` at `0x1401db528`
- `ntoskrnl!ProbeForWrite` at `0x1401db53f`

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
  __int64 v20; // rcx
  struct tagTHREADINFO *v25; // [rsp+90h] [rbp-78h] BYREF
  ULONG_PTR BugCheckParameter2[2]; // [rsp+98h] [rbp-70h] BYREF
  __int64 (__fastcall *v27)(PVOID); // [rsp+A8h] [rbp-60h]
  __int64 v28; // [rsp+B0h] [rbp-58h]
  volatile void *v29; // [rsp+B8h] [rbp-50h]
  __int64 Src; // [rsp+C0h] [rbp-48h] BYREF

  v28 = a6;
  v29 = Address;
  Src = 0;
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  EnterLeaveCritShared::EnterLeaveCritShared(&v25, 1);
  v25 = PtiCurrent();
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
      if ( v27 != (__int64 (__fastcall *)(PVOID))-1LL )
      {
        BugCheckParameter4 = PtiCurrent();
        KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)p_Src, (ULONG_PTR)BugCheckParameter4);
      }
      v17 = PtiCurrent();
      BugCheckParameter2[0] = *((_QWORD *)v17 + 47);
      *((_QWORD *)v17 + 47) = BugCheckParameter2;
      BugCheckParameter2[1] = (ULONG_PTR)p_Src;
      v27 = GreDeleteFastMutex;
    }
    else
    {
      p_Src = &Src;
    }
    ProbeForWrite(a12, 4u, 4u);
    ProbeForWrite(a13, 8u, 8u);
    v18 = xxxToUnicodeEx(a1, a7, a5, a4, v28);
    GetKeyNameText(a3, a10, (unsigned int)a9);
    KeyboardType = GetKeyboardType(2147483646);
    *a12 = ((unsigned int)GetKeyboardType(0x7FFFFFFF) << 16) | KeyboardType;
    *a13 = *(unsigned int *)(*((_QWORD *)v25 + 58) + 520LL);
    memmove((void *)a8, p_Src, 2LL * a7);
    if ( v13 )
      Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&void Win32FreePool(void *),1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
  }
  else
  {
    v18 = 0;
    UserSetLastError(87);
  }
  UserSessionSwitchLeaveCritWithNonPaged(v20);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  return v18;
}

```

## disassembly

```asm
0x1401db2d0  mov     r11, rsp
0x1401db2d3  push    rbx
0x1401db2d4  push    rsi
0x1401db2d5  push    rdi
0x1401db2d6  push    r12
0x1401db2d8  push    r13
0x1401db2da  push    r14
0x1401db2dc  push    r15
0x1401db2de  sub     rsp, 0D0h
0x1401db2e5  mov     rax, cs:__security_cookie
0x1401db2ec  xor     rax, rsp
0x1401db2ef  mov     [rsp+108h+var_40], rax
0x1401db2f7  mov     [rsp+108h+var_C4], r9d
0x1401db2fc  mov     [rsp+108h+var_B4], r8d
0x1401db301  mov     [rsp+108h+var_BC], edx
0x1401db305  mov     [rsp+108h+var_B8], ecx
0x1401db309  mov     rax, [rsp+108h+arg_28]
0x1401db311  mov     [rsp+108h+var_58], rax
0x1401db319  movsxd  rdi, [rsp+108h+arg_30]
0x1401db321  mov     rax, [rsp+108h+arg_38]
0x1401db329  mov     [rsp+108h+var_80], rax
0x1401db331  mov     rax, [rsp+108h+arg_48]
0x1401db339  mov     [rsp+108h+var_88], rax
0x1401db341  mov     rbx, [rsp+108h+Address]
0x1401db349  mov     [rsp+108h+var_50], rbx
0x1401db351  mov     r12, [rsp+108h+arg_58]
0x1401db359  mov     r13, [rsp+108h+arg_60]
0x1401db361  mov     qword ptr [r11-48h], 0
0x1401db369  mov     [rsp+108h+var_90], 0
0x1401db372  lea     rcx, [r11-70h]
0x1401db376  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401db37b  mov     r15d, 1
0x1401db381  mov     edx, r15d
0x1401db384  lea     rcx, [rsp+108h+var_78]
0x1401db38c  call    ??0EnterLeaveCritShared@@QEAA@W4HandleToObjILCheck@@@Z; EnterLeaveCritShared::EnterLeaveCritShared(HandleToObjILCheck)
0x1401db391  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401db396  mov     [rsp+108h+var_78], rax
0x1401db39e  test    edi, edi
0x1401db3a0  jle     loc_1401DB611
0x1401db3a6  movsxd  r14, [rsp+108h+arg_40]
0x1401db3ae  test    r14d, r14d
0x1401db3b1  jle     loc_1401DB611
0x1401db3b7  test    r12, r12
0x1401db3ba  jz      loc_1401DB611
0x1401db3c0  xor     sil, sil
0x1401db3c3  mov     [rsp+108h+var_C8], sil
0x1401db3c8  test    r13, r13
0x1401db3cb  jz      loc_1401DB611
0x1401db3d1  mov     r8d, r15d; Alignment
0x1401db3d4  mov     edx, 100h; Length
0x1401db3d9  mov     rcx, rbx; Address
0x1401db3dc  call    cs:__imp_ProbeForWrite
0x1401db3e3  nop     dword ptr [rax+rax+00h]
0x1401db3e8  mov     rcx, rbx
0x1401db3eb  call    _GetKeyboardState
0x1401db3f0  mov     rbx, rdi
0x1401db3f3  mov     rdi, 7FFFFFFFFFFFFFFFh
0x1401db3fd  cmp     rbx, rdi
0x1401db400  jbe     short loc_1401DB40E
0x1401db402  call    cs:__imp_ExRaiseAccessViolation
0x1401db409  nop     dword ptr [rax+rax+00h]
0x1401db40e  lea     r15, [rbx+rbx]
0x1401db412  mov     r8d, 2; Alignment
0x1401db418  mov     rdx, r15; Length
0x1401db41b  mov     rcx, [rsp+108h+var_80]; Address
0x1401db423  call    cs:__imp_ProbeForWrite
0x1401db42a  nop     dword ptr [rax+rax+00h]
0x1401db42f  mov     rdx, r14
0x1401db432  cmp     r14, rdi
0x1401db435  jbe     short loc_1401DB443
0x1401db437  call    cs:__imp_ExRaiseAccessViolation
0x1401db43e  nop     dword ptr [rax+rax+00h]
0x1401db443  add     rdx, rdx; Length
0x1401db446  mov     r8d, 2; Alignment
0x1401db44c  mov     rcx, [rsp+108h+var_88]; Address
0x1401db454  call    cs:__imp_ProbeForWrite
0x1401db45b  nop     dword ptr [rax+rax+00h]
0x1401db460  cmp     rbx, 4
0x1401db464  jnb     short loc_1401DB478
0x1401db466  lea     rdi, [rsp+108h+Src]
0x1401db46e  mov     [rsp+108h+var_90], rdi
0x1401db473  jmp     loc_1401DB51D
0x1401db478  mov     r8d, 62757355h; unsigned int
0x1401db47e  mov     rdx, r15; unsigned __int64
0x1401db481  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401db486  mov     rdi, rax
0x1401db489  mov     [rsp+108h+var_90], rax
0x1401db48e  test    rax, rax
0x1401db491  jnz     short loc_1401DB4A4
0x1401db493  mov     ecx, 0C0000017h; Status
0x1401db498  call    cs:__imp_ExRaiseStatus
0x1401db4a4  mov     sil, 1
0x1401db4a7  mov     [rsp+108h+var_C8], sil
0x1401db4ac  cmp     [rsp+108h+var_60], 0FFFFFFFFFFFFFFFFh
0x1401db4b5  jz      short loc_1401DB4E3
0x1401db4b7  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401db4bc  mov     [rsp+108h+BugCheckParameter4], rax; BugCheckParameter4
0x1401db4c1  mov     r9, rdi; BugCheckParameter3
0x1401db4c4  lea     r8, [rsp+108h+BugCheckParameter2]; BugCheckParameter2
0x1401db4cc  mov     edx, 12h; BugCheckParameter1
0x1401db4d1  mov     ecx, 164h; BugCheckCode
0x1401db4d6  call    cs:__imp_KeBugCheckEx
0x1401db4e3  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401db4e8  mov     rcx, [rax+178h]
0x1401db4ef  mov     [rsp+108h+BugCheckParameter2], rcx
0x1401db4f7  lea     rcx, [rsp+108h+BugCheckParameter2]
0x1401db4ff  mov     [rax+178h], rcx
0x1401db506  mov     [rsp+108h+var_68], rdi
0x1401db50e  lea     rax, GreDeleteFastMutex
0x1401db515  mov     [rsp+108h+var_60], rax
0x1401db51d  mov     edx, 4; Length
0x1401db522  mov     r8d, edx; Alignment
0x1401db525  mov     rcx, r12; Address
0x1401db528  call    cs:__imp_ProbeForWrite
0x1401db52f  nop     dword ptr [rax+rax+00h]
0x1401db534  mov     edx, 8; Length
0x1401db539  mov     r8d, edx; Alignment
0x1401db53c  mov     rcx, r13; Address
0x1401db53f  call    cs:__imp_ProbeForWrite
0x1401db546  nop     dword ptr [rax+rax+00h]
0x1401db54b  nop
0x1401db54c  mov     rax, [rsp+108h+var_58]
0x1401db554  mov     [rsp+108h+var_D0], rax
0x1401db559  mov     eax, [rsp+108h+var_C4]
0x1401db55d  mov     [rsp+108h+var_D8], eax
0x1401db561  movzx   eax, [rsp+108h+arg_20]
0x1401db569  mov     [rsp+108h+var_E0], ax
0x1401db56e  mov     dword ptr [rsp+108h+BugCheckParameter4], ebx
0x1401db572  mov     r9, rdi
0x1401db575  mov     r8, [rsp+108h+var_50]
0x1401db57d  mov     edx, [rsp+108h+var_BC]
0x1401db581  mov     ecx, [rsp+108h+var_B8]
0x1401db585  call    xxxToUnicodeEx
0x1401db58a  mov     ebx, eax
0x1401db58c  mov     r8d, r14d
0x1401db58f  mov     rdx, [rsp+108h+var_88]
0x1401db597  mov     ecx, [rsp+108h+var_B4]
0x1401db59b  call    _GetKeyNameText
0x1401db5a0  mov     ecx, 7FFFFFFEh
0x1401db5a5  call    _GetKeyboardType
0x1401db5aa  mov     r14d, eax
0x1401db5ad  mov     ecx, 7FFFFFFFh
0x1401db5b2  call    _GetKeyboardType
0x1401db5b7  shl     eax, 10h
0x1401db5ba  or      r14d, eax
0x1401db5bd  mov     [r12], r14d
0x1401db5c1  mov     rax, [rsp+108h+var_78]
0x1401db5c9  mov     rax, [rax+1D0h]
0x1401db5d0  mov     r9d, [rax+208h]
0x1401db5d7  mov     [r13+0], r9
0x1401db5db  mov     r8, r15; Size
0x1401db5de  mov     rdx, rdi; Src
0x1401db5e1  mov     rcx, [rsp+108h+var_80]; void *
0x1401db5e9  call    memmove
0x1401db5ee  jmp     short loc_1401DB5F7
0x1401db5f0  xor     ebx, ebx
0x1401db5f2  mov     sil, [rsp+108h+var_C8]
0x1401db5f7  test    sil, sil
0x1401db5fa  jz      short loc_1401DB61B
0x1401db5fc  xor     edx, edx
0x1401db5fe  lea     rcx, [rsp+108h+BugCheckParameter2]; BugCheckParameter2
0x1401db606  call    ?UnlockWorker@?$Win32RawLockedItemBase@UDISPLAYCONFIG_DEVICE_INFO_HEADER@@$1?Win32FreePool@@YAXPEAX@Z$00$00$00@@AEAAX_N0@Z; Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&Win32FreePool(void *),1,1,1>::UnlockWorker(bool,bool)
0x1401db60b  jmp     short loc_1401DB61B
0x1401db60d  xor     ebx, ebx
0x1401db60f  jmp     short loc_1401DB61B
0x1401db611  xor     ebx, ebx
0x1401db613  lea     ecx, [rbx+57h]
0x1401db616  call    UserSetLastError
0x1401db61b  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401db620  lea     rcx, [rsp+108h+BugCheckParameter2]
0x1401db628  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401db62d  mov     eax, ebx
0x1401db62f  mov     rcx, [rsp+108h+var_40]
0x1401db637  xor     rcx, rsp; StackCookie
0x1401db63a  call    __security_check_cookie
0x1401db63f  add     rsp, 0D0h
0x1401db646  pop     r15
0x1401db648  pop     r14
0x1401db64a  pop     r13
0x1401db64c  pop     r12
0x1401db64e  pop     rdi
0x1401db64f  pop     rsi
0x1401db650  pop     rbx
0x1401db651  retn
0x14023a39a  push    rbp
0x14023a39c  sub     rsp, 40h
0x14023a3a0  mov     rbp, rdx
0x14023a3a3  mov     rax, [rcx]
0x14023a3a6  mov     ecx, [rax]
0x14023a3a8  mov     [rbp+68h], ecx
0x14023a3ab  mov     ecx, [rbp+68h]
0x14023a3ae  call    SetLastNtError
0x14023a3b3  mov     dword ptr [rbp+70h], 1
0x14023a3ba  mov     eax, [rbp+70h]
0x14023a3bd  add     rsp, 40h
0x14023a3c1  pop     rbp
0x14023a3c2  retn
0x14023a3c4  push    rbp
0x14023a3c6  sub     rsp, 40h
0x14023a3ca  mov     rbp, rdx
0x14023a3cd  mov     rax, [rcx]
0x14023a3d0  mov     ecx, [rax]
0x14023a3d2  mov     [rbp+58h], ecx
0x14023a3d5  mov     ecx, [rbp+58h]
0x14023a3d8  call    SetLastNtError
0x14023a3dd  mov     dword ptr [rbp+60h], 1
0x14023a3e4  mov     eax, [rbp+60h]
0x14023a3e7  add     rsp, 40h
0x14023a3eb  pop     rbp
0x14023a3ec  retn
```

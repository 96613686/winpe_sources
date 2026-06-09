# NtUserCreateWindowEx

- ea: `0x140009ce0`
- end: `0x14000a366`
- name: `NtUserCreateWindowEx`
- size: `1670`
- prototype: `__int64 __fastcall(unsigned int, ULONG64 p_Size, ULONG64, __m128i *, int, int, int, int, int, void *Src, __int64, __int64, __int64, int, __int16, int, __int64)`
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x140009ce0`
- `0x14000a36c`
- `0x14000a3ec`
- `0x14000a408`
- `0x14000a44c`
- `0x14001c76c`
- `0x1400241fc`
- `0x140033b58`
- `0x1400c0e10`
- `0x1400d6dd0`
- `0x1400d75c4`
- `0x1400d78bc`
- `0x1400d7aa0`
- `0x1400e2a2c`
- `0x1400e2cb0`
- `0x1400e52b0`
- `0x1400e8c20`
- `0x14013f4b4`
- `0x140343200`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14000a03a`
- `ntoskrnl!ExRaiseStatus` at `0x14000a03a`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14000a130`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14000a154`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14000a17b`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14000a130`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14000a154`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14000a17b`
- `ntoskrnl!ProbeForRead` at `0x140009ecb`
- `ntoskrnl!ProbeForRead` at `0x140009f58`
- `ntoskrnl!ProbeForRead` at `0x140009ffd`
- `ntoskrnl!ProbeForRead` at `0x140009ecb`
- `ntoskrnl!ProbeForRead` at `0x140009f58`
- `ntoskrnl!ProbeForRead` at `0x140009ffd`
- `ntoskrnl!MmUserProbeAddress` at `0x14000a121`
- `ntoskrnl!MmUserProbeAddress` at `0x14000a145`
- `ntoskrnl!MmUserProbeAddress` at `0x14000a16c`
- `ntoskrnl!MmIsUserAddress` at `0x140009e62`
- `ntoskrnl!MmIsUserAddress` at `0x140009eef`
- `ntoskrnl!MmIsUserAddress` at `0x140009f88`
- `ntoskrnl!MmIsUserAddress` at `0x140009e62`
- `ntoskrnl!MmIsUserAddress` at `0x140009eef`
- `ntoskrnl!MmIsUserAddress` at `0x140009f88`
- `ntoskrnl!KeBugCheckEx` at `0x14000a070`
- `ntoskrnl!KeBugCheckEx` at `0x14000a070`
- `win32kbase!ValidateHmenu` at `0x14000a328`
- `win32kbase!ValidateHmenu` at `0x14000a328`
- `win32kbase!ValidateHwnd` at `0x14000a2de`
- `win32kbase!ValidateHwnd` at `0x14000a2de`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x14000a019`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x14000a019`
- `win32kbase!EnterCrit` at `0x140009d20`
- `win32kbase!EnterCrit` at `0x140009d20`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x14000a289`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x14000a289`
- `win32kbase!Win32FreePool` at `0x14000a0a8`

## pseudocode

```c
__int64 __fastcall NtUserCreateWindowEx(
        unsigned int a1,
        ULONG64 p_Size,
        ULONG64 a3,
        __m128i *a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        void *Src,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        int a14,
        __int16 a15,
        int a16,
        __int64 a17)
{
  __int64 v21; // rbx
  __int64 v22; // r13
  struct tagTHREADINFO *v23; // rax
  __int64 v24; // rax
  struct tagTHREADINFO *v25; // r12
  __int64 v26; // rax
  __int16 AppCompatFlags2; // ax
  unsigned int v28; // ecx
  unsigned int v29; // r12d
  volatile void *v30; // xmm0_8
  volatile void *v31; // xmm0_8
  volatile void *v32; // xmm0_8
  ULONG_PTR v33; // rsi
  struct tagTHREADINFO *BugCheckParameter4; // rax
  struct tagTHREADINFO *v35; // rax
  __int64 *Window; // rax
  __int64 v38; // rdx
  __int64 v39; // rax
  __m128i Size; // [rsp+90h] [rbp-E8h] BYREF
  _QWORD v41[2]; // [rsp+B0h] [rbp-C8h] BYREF
  __int64 v42; // [rsp+C0h] [rbp-B8h]
  __m128i v43; // [rsp+C8h] [rbp-B0h] BYREF
  __m128i v44; // [rsp+D8h] [rbp-A0h] BYREF
  ULONG_PTR BugCheckParameter2[2]; // [rsp+E8h] [rbp-90h] BYREF
  void (*v46)(void *); // [rsp+F8h] [rbp-80h]
  ULONG_PTR v47[2]; // [rsp+100h] [rbp-78h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+110h] [rbp-68h] BYREF
  _BYTE v49[88]; // [rsp+120h] [rbp-58h] BYREF

  Size = 0;
  v43 = 0;
  v44 = 0;
  EnterCrit(0, 0);
  Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(BugCheckParameter3);
  tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_((tagTLBLOCK::_unnamed_type_list_ *)BugCheckParameter2);
  SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(v41);
  v21 = 0;
  if ( Src == (void *)-3LL )
  {
    v22 = 0;
    v23 = PtiCurrent();
    if ( v23 )
    {
      v24 = *((_QWORD *)v23 + 61);
      if ( v24 )
        v22 = *(_QWORD *)(v24 + 112);
    }
    if ( (a16 & 1) != 0 )
      goto LABEL_55;
  }
  else if ( Src )
  {
    v22 = ValidateHwnd();
    if ( !v22 )
      goto LABEL_47;
  }
  else
  {
    v22 = 0;
  }
  if ( (a16 & 0xFFFFFFF8) != 0 )
  {
LABEL_55:
    UserSetLastError(87);
    goto LABEL_47;
  }
  v25 = PtiCurrent();
  v47[0] = (ULONG_PTR)v25;
  if ( (a5 & 0xC0000000) == 0x40000000 || !a11 )
  {
    v26 = SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(v49, a11);
    v42 = *(_QWORD *)(v26 + 16);
    SmartObjStackRefBase<tagMENU>::operator=(v41, **(_QWORD **)v26);
    SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v49);
  }
  else
  {
    v39 = ValidateHmenu(a11, 1);
    v42 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v41, v39);
    if ( (unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v41) )
      goto LABEL_47;
    v38 = v42;
    if ( !v42 )
      v38 = *(_QWORD *)v41[0];
    Win32HM_LockIntoThread<0>(v25, v38, BugCheckParameter3);
  }
  AppCompatFlags2 = GetAppCompatFlags2(1024);
  v28 = a1 & 0x800777FF;
  if ( (AppCompatFlags2 & 0x800) == 0 )
    v28 = a1;
  v29 = v28 & 0x8A7F77FF;
  if ( (v28 & 0x8A7F77FF) == v28 )
    v29 = v28;
  if ( (p_Size & 0xFFFFFFFFFFFF0000uLL) != 0 )
  {
    if ( !(unsigned __int8)MmIsUserAddress(p_Size) )
      p_Size = MmUserProbeAddress;
    Size = *(__m128i *)p_Size;
    v32 = (volatile void *)_mm_srli_si128(Size, 8).m128i_u64[0];
    if ( v32 )
    {
      if ( Size.m128i_i32[0] > (Size.m128i_i32[1] & 0x7FFFFFFFu) )
        ExRaiseAccessViolation();
      ProbeForRead(v32, (Size.m128i_i32[1] >= 0) + Size.m128i_u32[0] + 1LL, (Size.m128i_i32[1] >= 0) + 1);
      v33 = Win32AllocPoolWithQuotaZInit(Size.m128i_u32[0] + 2LL, 2020897621);
      Size.m128i_i64[1] = v33;
      if ( !v33 )
        ExRaiseStatus(-1073741801);
      if ( v46 != (void (*)(void *))-1LL )
      {
        BugCheckParameter4 = PtiCurrent();
        KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, v33, (ULONG_PTR)BugCheckParameter4);
      }
      v35 = PtiCurrent();
      BugCheckParameter2[0] = *((_QWORD *)v35 + 47);
      *((_QWORD *)v35 + 47) = BugCheckParameter2;
      BugCheckParameter2[1] = v33;
      v46 = Win32FreePool;
      memmove((void *)Size.m128i_i64[1], (const void *)v32, Size.m128i_u32[0]);
      *(_WORD *)((Size.m128i_i32[0] & 0xFFFFFFFE) + Size.m128i_i64[1]) = 0;
      Size.m128i_i32[1] = Size.m128i_i32[1] & 0x80000000 | (Size.m128i_i32[0] + 2) & 0x7FFFFFFF;
    }
    else
    {
      Size.m128i_i32[0] = 0;
    }
    p_Size = (ULONG64)&Size;
  }
  if ( (a3 & 0xFFFFFFFFFFFF0000uLL) != 0 )
  {
    if ( !(unsigned __int8)MmIsUserAddress(a3) )
      a3 = MmUserProbeAddress;
    v43 = *(__m128i *)a3;
    v31 = (volatile void *)_mm_srli_si128(v43, 8).m128i_u64[0];
    if ( v31 )
    {
      if ( v43.m128i_i32[0] > (v43.m128i_i32[1] & 0x7FFFFFFFu) )
        ExRaiseAccessViolation();
      ProbeForRead(v31, v43.m128i_u32[0] + 1LL + (v43.m128i_i32[1] >= 0), (v43.m128i_i32[1] >= 0) + 1);
    }
    else
    {
      v43.m128i_i32[0] = 0;
    }
    a3 = (ULONG64)&v43;
  }
  if ( a4 )
  {
    if ( !(unsigned __int8)MmIsUserAddress(a4) )
      a4 = (__m128i *)MmUserProbeAddress;
    v44 = *a4;
    v30 = (volatile void *)_mm_srli_si128(v44, 8).m128i_u64[0];
    if ( v30 )
    {
      if ( v44.m128i_i32[0] > (v44.m128i_i32[1] & 0x7FFFFFFFu) )
        ExRaiseAccessViolation();
      ProbeForRead(v30, v44.m128i_u32[0] + 1LL + (v44.m128i_i32[1] >= 0), (v44.m128i_i32[1] >= 0) + 1);
    }
    else
    {
      v44.m128i_i32[0] = 0;
    }
    a4 = &v44;
  }
  Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(v47, v47[0], v22);
  Window = (__int64 *)xxxCreateWindowEx(
                        v29,
                        p_Size,
                        a3,
                        (_DWORD)a4,
                        a5,
                        a6,
                        a7,
                        a8,
                        a9,
                        v22,
                        (__int64)v41,
                        a12,
                        a13,
                        a14,
                        a15,
                        a16,
                        a17);
  if ( Window )
    v21 = *Window;
  Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v47);
LABEL_47:
  SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v41);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
  UserSessionSwitchLeaveCrit();
  return v21;
}

```

## disassembly

```asm
0x140009ce0  push    rbx
0x140009ce2  push    rsi
0x140009ce3  push    rdi
0x140009ce4  push    r12
0x140009ce6  push    r13
0x140009ce8  push    r14
0x140009cea  push    r15
0x140009cec  sub     rsp, 140h
0x140009cf3  mov     r14, r9
0x140009cf6  mov     r15, r8
0x140009cf9  mov     rsi, rdx
0x140009cfc  mov     edi, ecx
0x140009cfe  xorps   xmm0, xmm0
0x140009d01  movups  [rsp+178h+Size], xmm0
0x140009d09  xorps   xmm1, xmm1
0x140009d0c  movups  [rsp+178h+var_B0], xmm1
0x140009d14  movups  [rsp+178h+var_A0], xmm0
0x140009d1c  xor     edx, edx
0x140009d1e  xor     ecx, ecx
0x140009d20  call    cs:__imp_EnterCrit
0x140009d27  nop     dword ptr [rax+rax+00h]
0x140009d2c  lea     rcx, [rsp+178h+BugCheckParameter3]
0x140009d34  call    ??0?$Win32HMOptionalThreadLockAlways@UtagMENU@@@@QEAA@XZ; Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(void)
0x140009d39  lea     rcx, [rsp+178h+BugCheckParameter2]; this
0x140009d41  call    ??0_unnamed_type_list_@tagTLBLOCK@@QEAA@XZ; tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_(void)
0x140009d46  lea     rcx, [rsp+178h+var_C8]
0x140009d4e  call    ??0?$SmartObjStackRef@UtagMENU@@@@QEAA@XZ; SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(void)
0x140009d53  mov     rcx, [rsp+178h+Src]
0x140009d5b  xor     ebx, ebx
0x140009d5d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140009d61  jnz     loc_14000A2D9
0x140009d67  mov     r13d, ebx
0x140009d6a  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140009d6f  test    rax, rax
0x140009d72  jz      short loc_140009D84
0x140009d74  mov     rax, [rax+1E8h]
0x140009d7b  test    rax, rax
0x140009d7e  jz      short loc_140009D84
0x140009d80  mov     r13, [rax+70h]
0x140009d84  test    byte ptr [rsp+178h+arg_78], 1
0x140009d8c  jnz     loc_14000A303
0x140009d92  test    [rsp+178h+arg_78], 0FFFFFFF8h
0x140009d9d  jnz     loc_14000A303
0x140009da3  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140009da8  mov     r12, rax
0x140009dab  mov     [rsp+178h+var_78], rax
0x140009db3  mov     ecx, [rsp+178h+arg_20]
0x140009dba  and     ecx, 0C0000000h
0x140009dc0  cmp     ecx, 40000000h
0x140009dc6  jnz     loc_14000A312
0x140009dcc  mov     rdx, [rsp+178h+arg_50]
0x140009dd4  lea     rcx, [rsp+178h+var_58]
0x140009ddc  call    ??0?$SmartObjStackRef@UtagMENU@@@@QEAA@PEAUHMENU__@@@Z; SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(HMENU__ *)
0x140009de1  mov     rcx, [rax+10h]
0x140009de5  mov     [rsp+178h+var_B8], rcx
0x140009ded  mov     rdx, [rax]
0x140009df0  mov     rdx, [rdx]
0x140009df3  lea     rcx, [rsp+178h+var_C8]
0x140009dfb  call    ??4?$SmartObjStackRefBase@UtagMENU@@@@IEAAAEAV0@QEAUtagMENU@@@Z; SmartObjStackRefBase<tagMENU>::operator=(tagMENU * const)
0x140009e00  lea     rcx, [rsp+178h+var_58]
0x140009e08  call    ??1?$SmartObjStackRef@UtagMENU@@@@QEAA@XZ; SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(void)
0x140009e0d  mov     ecx, 400h
0x140009e12  call    GetAppCompatFlags2
0x140009e17  mov     ecx, edi
0x140009e19  and     ecx, 800777FFh
0x140009e1f  bt      eax, 0Bh
0x140009e23  cmovnb  ecx, edi
0x140009e26  mov     r12d, ecx
0x140009e29  and     r12d, 8A7F77FFh
0x140009e30  cmp     r12d, ecx
0x140009e33  cmovz   r12d, ecx
0x140009e37  test    rsi, 0FFFFFFFFFFFF0000h
0x140009e3e  jnz     loc_140009F85
0x140009e44  mov     edi, 7FFFFFFFh
0x140009e49  test    r15, 0FFFFFFFFFFFF0000h
0x140009e50  jnz     loc_140009EEC
0x140009e56  test    r14, r14
0x140009e59  jz      loc_14000A187
0x140009e5f  mov     rcx, r14
0x140009e62  call    cs:__imp_MmIsUserAddress
0x140009e69  nop     dword ptr [rax+rax+00h]
0x140009e6e  test    al, al
0x140009e70  jz      loc_14000A16C
0x140009e76  movups  xmm0, xmmword ptr [r14]
0x140009e7a  movups  [rsp+178h+var_A0], xmm0
0x140009e82  psrldq  xmm0, 8
0x140009e87  movq    r9, xmm0
0x140009e8c  test    r9, r9
0x140009e8f  jz      loc_140009F79
0x140009e95  mov     rcx, qword ptr [rsp+178h+var_A0]
0x140009e9d  mov     rax, rcx
0x140009ea0  shr     rax, 20h
0x140009ea4  and     eax, edi
0x140009ea6  cmp     ecx, eax
0x140009ea8  ja      loc_14000A17B
0x140009eae  mov     eax, dword ptr [rsp+178h+var_A0+4]
0x140009eb5  not     eax
0x140009eb7  shr     eax, 1Fh
0x140009eba  mov     edx, eax
0x140009ebc  lea     r8d, [rax+1]; Alignment
0x140009ec0  mov     eax, ecx
0x140009ec2  inc     rax
0x140009ec5  add     rdx, rax; Length
0x140009ec8  mov     rcx, r9; Address
0x140009ecb  call    cs:__imp_ProbeForRead
0x140009ed2  nop     dword ptr [rax+rax+00h]
0x140009ed7  lea     r14, [rsp+178h+var_A0]
0x140009edf  mov     [rsp+178h+arg_18], r14
0x140009ee7  jmp     loc_14000A187
0x140009eec  mov     rcx, r15
0x140009eef  call    cs:__imp_MmIsUserAddress
0x140009ef6  nop     dword ptr [rax+rax+00h]
0x140009efb  test    al, al
0x140009efd  jz      loc_14000A145
0x140009f03  movups  xmm0, xmmword ptr [r15]
0x140009f07  movups  [rsp+178h+var_B0], xmm0
0x140009f0f  psrldq  xmm0, 8
0x140009f14  movq    r9, xmm0
0x140009f19  test    r9, r9
0x140009f1c  jz      loc_14000A160
0x140009f22  mov     rcx, qword ptr [rsp+178h+var_B0]
0x140009f2a  mov     rax, rcx
0x140009f2d  shr     rax, 20h
0x140009f31  and     eax, edi
0x140009f33  cmp     ecx, eax
0x140009f35  ja      loc_14000A154
0x140009f3b  mov     eax, dword ptr [rsp+178h+var_B0+4]
0x140009f42  not     eax
0x140009f44  shr     eax, 1Fh
0x140009f47  mov     edx, eax
0x140009f49  lea     r8d, [rax+1]; Alignment
0x140009f4d  mov     eax, ecx
0x140009f4f  inc     rax
0x140009f52  add     rdx, rax; Length
0x140009f55  mov     rcx, r9; Address
0x140009f58  call    cs:__imp_ProbeForRead
0x140009f5f  nop     dword ptr [rax+rax+00h]
0x140009f64  lea     r15, [rsp+178h+var_B0]
0x140009f6c  mov     [rsp+178h+arg_10], r15
0x140009f74  jmp     loc_140009E56
0x140009f79  mov     dword ptr [rsp+178h+var_A0], ebx
0x140009f80  jmp     loc_140009ED7
0x140009f85  mov     rcx, rsi
0x140009f88  call    cs:__imp_MmIsUserAddress
0x140009f8f  nop     dword ptr [rax+rax+00h]
0x140009f94  test    al, al
0x140009f96  jz      loc_14000A121
0x140009f9c  movups  xmm0, xmmword ptr [rsi]
0x140009f9f  movups  [rsp+178h+Size], xmm0
0x140009fa7  psrldq  xmm0, 8
0x140009fac  movq    r9, xmm0
0x140009fb1  mov     [rsp+178h+Src], r9
0x140009fb9  mov     edi, 7FFFFFFFh
0x140009fbe  test    r9, r9
0x140009fc1  jz      loc_14000A13C
0x140009fc7  mov     rdx, qword ptr [rsp+178h+Size]
0x140009fcf  mov     rax, rdx
0x140009fd2  shr     rax, 20h
0x140009fd6  and     eax, edi
0x140009fd8  cmp     edx, eax
0x140009fda  ja      loc_14000A130
0x140009fe0  mov     eax, dword ptr [rsp+178h+Size+4]
0x140009fe7  not     eax
0x140009fe9  shr     eax, 1Fh
0x140009fec  mov     ecx, eax
0x140009fee  lea     r8d, [rax+1]; Alignment
0x140009ff2  mov     edx, edx
0x140009ff4  inc     rdx
0x140009ff7  add     rdx, rcx; Length
0x140009ffa  mov     rcx, r9; Address
0x140009ffd  call    cs:__imp_ProbeForRead
0x14000a004  nop     dword ptr [rax+rax+00h]
0x14000a009  mov     ecx, dword ptr [rsp+178h+Size]
0x14000a010  add     rcx, 2
0x14000a014  mov     edx, 78747355h
0x14000a019  call    cs:__imp_Win32AllocPoolWithQuotaZInit
0x14000a020  nop     dword ptr [rax+rax+00h]
0x14000a025  mov     rsi, rax
0x14000a028  mov     qword ptr [rsp+178h+Size+8], rax
0x14000a030  test    rax, rax
0x14000a033  jnz     short loc_14000A046
0x14000a035  mov     ecx, 0C0000017h; Status
0x14000a03a  call    cs:__imp_ExRaiseStatus
0x14000a046  cmp     [rsp+178h+var_80], 0FFFFFFFFFFFFFFFFh
0x14000a04f  jz      short loc_14000A07D
0x14000a051  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14000a056  mov     [rsp+178h+BugCheckParameter4], rax; BugCheckParameter4
0x14000a05b  mov     r9, rsi; BugCheckParameter3
0x14000a05e  lea     r8, [rsp+178h+BugCheckParameter2]; BugCheckParameter2
0x14000a066  mov     edx, 12h; BugCheckParameter1
0x14000a06b  mov     ecx, 164h; BugCheckCode
0x14000a070  call    cs:__imp_KeBugCheckEx
0x14000a07d  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14000a082  mov     rcx, [rax+178h]
0x14000a089  mov     [rsp+178h+BugCheckParameter2], rcx
0x14000a091  lea     rcx, [rsp+178h+BugCheckParameter2]
0x14000a099  mov     [rax+178h], rcx
0x14000a0a0  mov     [rsp+178h+var_88], rsi
0x14000a0a8  mov     rax, cs:__imp_Win32FreePool
0x14000a0af  mov     [rsp+178h+var_80], rax
0x14000a0b7  mov     r8d, dword ptr [rsp+178h+Size]; Size
0x14000a0bf  mov     rdx, [rsp+178h+Src]; Src
0x14000a0c7  mov     rcx, qword ptr [rsp+178h+Size+8]; void *
0x14000a0cf  call    memmove
0x14000a0d4  mov     ecx, dword ptr [rsp+178h+Size]
0x14000a0db  and     rcx, 0FFFFFFFFFFFFFFFEh
0x14000a0df  mov     rax, qword ptr [rsp+178h+Size+8]
0x14000a0e7  mov     [rcx+rax], bx
0x14000a0eb  mov     ecx, dword ptr [rsp+178h+Size]
0x14000a0f2  add     ecx, 2
0x14000a0f5  and     ecx, edi
0x14000a0f7  mov     eax, dword ptr [rsp+178h+Size+4]
0x14000a0fe  and     eax, 80000000h
0x14000a103  or      ecx, eax
0x14000a105  mov     dword ptr [rsp+178h+Size+4], ecx
0x14000a10c  lea     rsi, [rsp+178h+Size]
0x14000a114  mov     [rsp+178h+arg_8], rsi
0x14000a11c  jmp     loc_140009E49
0x14000a121  mov     rax, cs:MmUserProbeAddress
0x14000a128  mov     rsi, [rax]
0x14000a12b  jmp     loc_140009F9C
0x14000a130  call    cs:__imp_ExRaiseAccessViolation
0x14000a137  nop     dword ptr [rax+rax+00h]
0x14000a13c  mov     dword ptr [rsp+178h+Size], ebx
0x14000a143  jmp     short loc_14000A10C
0x14000a145  mov     rax, cs:MmUserProbeAddress
0x14000a14c  mov     r15, [rax]
0x14000a14f  jmp     loc_140009F03
0x14000a154  call    cs:__imp_ExRaiseAccessViolation
0x14000a15b  nop     dword ptr [rax+rax+00h]
0x14000a160  mov     dword ptr [rsp+178h+var_B0], ebx
0x14000a167  jmp     loc_140009F64
0x14000a16c  mov     rax, cs:MmUserProbeAddress
0x14000a173  mov     r14, [rax]
0x14000a176  jmp     loc_140009E76
0x14000a17b  call    cs:__imp_ExRaiseAccessViolation
0x14000a182  nop     dword ptr [rax+rax+00h]
0x14000a187  jmp     short loc_14000A190
0x14000a189  xor     ebx, ebx
0x14000a18b  jmp     loc_14000A262
0x14000a190  mov     r8, r13
0x14000a193  mov     rdx, [rsp+178h+var_78]
0x14000a19b  lea     rcx, [rsp+178h+var_78]
0x14000a1a3  call    ??0?$Win32HMOptionalThreadLock@UtagWND@@@@QEAA@PEAUtagTHREADINFO@@PEAUtagWND@@@Z; Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(tagTHREADINFO *,tagWND *)
0x14000a1a8  mov     rax, [rsp+178h+arg_80]
0x14000a1b0  mov     [rsp+178h+var_F8], rax
0x14000a1b8  mov     eax, [rsp+178h+arg_78]
0x14000a1bf  mov     [rsp+178h+var_100], eax
0x14000a1c3  mov     eax, dword ptr [rsp+178h+arg_70]
0x14000a1ca  mov     [rsp+178h+var_108], eax
0x14000a1ce  mov     eax, [rsp+178h+arg_68]
0x14000a1d5  mov     [rsp+178h+var_110], eax
0x14000a1d9  mov     rax, [rsp+178h+arg_60]
0x14000a1e1  mov     [rsp+178h+var_118], rax
0x14000a1e6  mov     rax, [rsp+178h+arg_58]
0x14000a1ee  mov     [rsp+178h+var_120], rax
0x14000a1f3  lea     rax, [rsp+178h+var_C8]
0x14000a1fb  mov     [rsp+178h+var_128], rax
0x14000a200  mov     [rsp+178h+var_130], r13
0x14000a205  mov     eax, [rsp+178h+arg_40]
0x14000a20c  mov     [rsp+178h+var_138], eax
0x14000a210  mov     eax, [rsp+178h+arg_38]
0x14000a217  mov     [rsp+178h+var_140], eax
0x14000a21b  mov     eax, [rsp+178h+arg_30]
0x14000a222  mov     [rsp+178h+var_148], eax
0x14000a226  mov     eax, [rsp+178h+arg_28]
0x14000a22d  mov     [rsp+178h+var_150], eax
0x14000a231  mov     eax, [rsp+178h+arg_20]
0x14000a238  mov     dword ptr [rsp+178h+BugCheckParameter4], eax
0x14000a23c  mov     r9, r14
0x14000a23f  mov     r8, r15
0x14000a242  mov     rdx, rsi
0x14000a245  mov     ecx, r12d
0x14000a248  call    xxxCreateWindowEx
0x14000a24d  test    rax, rax
0x14000a250  jz      short loc_14000A255
0x14000a252  mov     rbx, [rax]
0x14000a255  lea     rcx, [rsp+178h+var_78]; BugCheckParameter3
0x14000a25d  call    ??1?$Win32HMThreadLock@UtagCURSOR@@@@QEAA@XZ; Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>(void)
0x14000a262  lea     rcx, [rsp+178h+var_C8]
0x14000a26a  call    ??1?$SmartObjStackRef@UtagMENU@@@@QEAA@XZ; SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(void)
0x14000a26f  lea     rcx, [rsp+178h+BugCheckParameter2]
0x14000a277  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x14000a27c  lea     rcx, [rsp+178h+BugCheckParameter3]; BugCheckParameter3
0x14000a284  call    ??1?$Win32HMOptionalThreadLockAlways@UtagMENU@@@@QEAA@XZ; Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>(void)
0x14000a289  call    cs:__imp_UserSessionSwitchLeaveCrit
0x14000a290  nop     dword ptr [rax+rax+00h]
0x14000a295  mov     rax, rbx
0x14000a298  add     rsp, 140h
0x14000a29f  pop     r15
0x14000a2a1  pop     r14
0x14000a2a3  pop     r13
0x14000a2a5  pop     r12
0x14000a2a7  pop     rdi
0x14000a2a8  pop     rsi
0x14000a2a9  pop     rbx
0x14000a2aa  retn
0x14000a2ac  mov     rdx, [rsp+178h+var_B8]
0x14000a2b4  test    rdx, rdx
0x14000a2b7  jnz     short loc_14000A2C4
  ... truncated ...
```

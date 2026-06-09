# NtUserCreateWindowEx

- ea: `0x1400045b0`
- end: `0x140004c36`
- name: `NtUserCreateWindowEx`
- size: `1670`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, int, int, void *Src, __int64, __int64, __int64, int, int, int, __int64)`
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x1400045b0`
- `0x140004c3c`
- `0x140004cbc`
- `0x140004cd8`
- `0x140004d1c`
- `0x1400143c0`
- `0x14002193c`
- `0x1400292ec`
- `0x1400381a8`
- `0x1400b0b40`
- `0x1400b1334`
- `0x1400b162c`
- `0x1400b1810`
- `0x1400bc81c`
- `0x1400bcaa0`
- `0x1400bf0a0`
- `0x1400c2a10`
- `0x1401494f4`
- `0x140342240`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14000490a`
- `ntoskrnl!ExRaiseStatus` at `0x14000490a`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140004a00`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140004a24`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140004a4b`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140004a00`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140004a24`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140004a4b`
- `ntoskrnl!ProbeForRead` at `0x14000479b`
- `ntoskrnl!ProbeForRead` at `0x140004828`
- `ntoskrnl!ProbeForRead` at `0x1400048cd`
- `ntoskrnl!ProbeForRead` at `0x14000479b`
- `ntoskrnl!ProbeForRead` at `0x140004828`
- `ntoskrnl!ProbeForRead` at `0x1400048cd`
- `ntoskrnl!MmUserProbeAddress` at `0x1400049f1`
- `ntoskrnl!MmUserProbeAddress` at `0x140004a15`
- `ntoskrnl!MmUserProbeAddress` at `0x140004a3c`
- `ntoskrnl!MmIsUserAddress` at `0x140004732`
- `ntoskrnl!MmIsUserAddress` at `0x1400047bf`
- `ntoskrnl!MmIsUserAddress` at `0x140004858`
- `ntoskrnl!MmIsUserAddress` at `0x140004732`
- `ntoskrnl!MmIsUserAddress` at `0x1400047bf`
- `ntoskrnl!MmIsUserAddress` at `0x140004858`
- `ntoskrnl!KeBugCheckEx` at `0x140004940`
- `ntoskrnl!KeBugCheckEx` at `0x140004940`
- `win32kbase!ValidateHmenu` at `0x140004bf8`
- `win32kbase!ValidateHmenu` at `0x140004bf8`
- `win32kbase!ValidateHwnd` at `0x140004bae`
- `win32kbase!ValidateHwnd` at `0x140004bae`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1400048e9`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1400048e9`
- `win32kbase!EnterCrit` at `0x1400045f0`
- `win32kbase!EnterCrit` at `0x1400045f0`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140004b59`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140004b59`
- `win32kbase!Win32FreePool` at `0x140004978`

## pseudocode

```c
__int64 __fastcall NtUserCreateWindowEx(
        unsigned int a1,
        ULONG64 p_Size,
        ULONG64 a3,
        __m128i *a4,
        unsigned int a5,
        LONG a6,
        LONG a7,
        int a8,
        unsigned int a9,
        void *Src,
        __int64 a11,
        void *a12,
        __int64 a13,
        unsigned int a14,
        unsigned __int16 a15,
        int a16,
        __int64 a17)
{
  __int64 v21; // rbx
  struct tagWND *v22; // r13
  struct tagTHREADINFO *v23; // rax
  __int64 v24; // rax
  struct tagTHREADINFO *v25; // r12
  __int16 AppCompatFlags2; // ax
  unsigned int v27; // ecx
  unsigned int v28; // r12d
  volatile void *v29; // xmm0_8
  volatile void *v30; // xmm0_8
  volatile void *v31; // xmm0_8
  __int64 v32; // r8
  __int64 v33; // r9
  ULONG_PTR v34; // rsi
  struct tagTHREADINFO *BugCheckParameter4; // rax
  struct tagTHREADINFO *v36; // rax
  __int64 *Window; // rax
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v41; // rdx
  __int64 v42; // r9
  __m128i Size; // [rsp+90h] [rbp-E8h] BYREF
  _QWORD v44[2]; // [rsp+B0h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+C0h] [rbp-B8h]
  __m128i v46; // [rsp+C8h] [rbp-B0h] BYREF
  __m128i v47; // [rsp+D8h] [rbp-A0h] BYREF
  ULONG_PTR BugCheckParameter2[2]; // [rsp+E8h] [rbp-90h] BYREF
  void (*v49)(void *); // [rsp+F8h] [rbp-80h]
  ULONG_PTR v50[2]; // [rsp+100h] [rbp-78h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+110h] [rbp-68h] BYREF
  _BYTE v52[88]; // [rsp+120h] [rbp-58h] BYREF

  Size = 0;
  v46 = 0;
  v47 = 0;
  EnterCrit(0, 0);
  Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(BugCheckParameter3);
  tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_((tagTLBLOCK::_unnamed_type_list_ *)BugCheckParameter2);
  SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(v44);
  v21 = 0;
  if ( Src == (void *)-3LL )
  {
    v22 = 0;
    v23 = PtiCurrent();
    if ( v23 )
    {
      v24 = *((_QWORD *)v23 + 61);
      if ( v24 )
        v22 = *(struct tagWND **)(v24 + 112);
    }
    if ( (a16 & 1) != 0 )
      goto LABEL_55;
  }
  else if ( Src )
  {
    v22 = (struct tagWND *)ValidateHwnd();
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
  v50[0] = (ULONG_PTR)v25;
  if ( (a5 & 0xC0000000) == 0x40000000 || !a11 )
  {
    v45 = *(_QWORD *)(SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(v52, a11) + 16);
    SmartObjStackRefBase<tagMENU>::operator=(v44);
    SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v52);
  }
  else
  {
    ValidateHmenu(a11, 1);
    v45 = 0;
    SmartObjStackRefBase<tagMENU>::operator=(v44);
    if ( (unsigned __int8)SmartObjStackRef<tagMENU>::operator==(v44) )
      goto LABEL_47;
    v41 = v45;
    if ( !v45 )
      v41 = *(_QWORD *)v44[0];
    Win32HM_LockIntoThread<0>(v25, v41, BugCheckParameter3, v42);
  }
  AppCompatFlags2 = GetAppCompatFlags2(1024);
  v27 = a1 & 0x800777FF;
  if ( (AppCompatFlags2 & 0x800) == 0 )
    v27 = a1;
  v28 = v27 & 0x8A7F77FF;
  if ( (v27 & 0x8A7F77FF) == v27 )
    v28 = v27;
  if ( (p_Size & 0xFFFFFFFFFFFF0000uLL) != 0 )
  {
    if ( !(unsigned __int8)MmIsUserAddress(p_Size) )
      p_Size = MmUserProbeAddress;
    Size = *(__m128i *)p_Size;
    v31 = (volatile void *)_mm_srli_si128(Size, 8).m128i_u64[0];
    if ( v31 )
    {
      if ( Size.m128i_i32[0] > (Size.m128i_i32[1] & 0x7FFFFFFFu) )
        ExRaiseAccessViolation();
      ProbeForRead(v31, (Size.m128i_i32[1] >= 0) + Size.m128i_u32[0] + 1LL, (Size.m128i_i32[1] >= 0) + 1);
      v34 = Win32AllocPoolWithQuotaZInit(Size.m128i_u32[0] + 2LL, 2020897621, v32, v33);
      Size.m128i_i64[1] = v34;
      if ( !v34 )
        ExRaiseStatus(-1073741801);
      if ( v49 != (void (*)(void *))-1LL )
      {
        BugCheckParameter4 = PtiCurrent();
        KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, v34, (ULONG_PTR)BugCheckParameter4);
      }
      v36 = PtiCurrent();
      BugCheckParameter2[0] = *((_QWORD *)v36 + 47);
      *((_QWORD *)v36 + 47) = BugCheckParameter2;
      BugCheckParameter2[1] = v34;
      v49 = Win32FreePool;
      memmove((void *)Size.m128i_i64[1], (const void *)v31, Size.m128i_u32[0]);
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
    v46 = *(__m128i *)a3;
    v30 = (volatile void *)_mm_srli_si128(v46, 8).m128i_u64[0];
    if ( v30 )
    {
      if ( v46.m128i_i32[0] > (v46.m128i_i32[1] & 0x7FFFFFFFu) )
        ExRaiseAccessViolation();
      ProbeForRead(v30, v46.m128i_u32[0] + 1LL + (v46.m128i_i32[1] >= 0), (v46.m128i_i32[1] >= 0) + 1);
    }
    else
    {
      v46.m128i_i32[0] = 0;
    }
    a3 = (ULONG64)&v46;
  }
  if ( a4 )
  {
    if ( !(unsigned __int8)MmIsUserAddress(a4) )
      a4 = (__m128i *)MmUserProbeAddress;
    v47 = *a4;
    v29 = (volatile void *)_mm_srli_si128(v47, 8).m128i_u64[0];
    if ( v29 )
    {
      if ( v47.m128i_i32[0] > (v47.m128i_i32[1] & 0x7FFFFFFFu) )
        ExRaiseAccessViolation();
      ProbeForRead(v29, v47.m128i_u32[0] + 1LL + (v47.m128i_i32[1] >= 0), (v47.m128i_i32[1] >= 0) + 1);
    }
    else
    {
      v47.m128i_i32[0] = 0;
    }
    a4 = &v47;
  }
  Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(v50, v50[0], v22);
  Window = (__int64 *)xxxCreateWindowEx(
                        v28,
                        (wchar_t *)p_Size,
                        a3,
                        a4->m128i_i32,
                        a5,
                        a6,
                        a7,
                        a8,
                        a9,
                        v22,
                        (__int64)v44,
                        a12,
                        a13,
                        a14,
                        a15,
                        a16,
                        a17);
  if ( Window )
    v21 = *Window;
  Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)v50);
LABEL_47:
  SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(v44);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
  UserSessionSwitchLeaveCrit(v39, v38);
  return v21;
}

```

## disassembly

```asm
0x1400045b0  push    rbx
0x1400045b2  push    rsi
0x1400045b3  push    rdi
0x1400045b4  push    r12
0x1400045b6  push    r13
0x1400045b8  push    r14
0x1400045ba  push    r15
0x1400045bc  sub     rsp, 140h
0x1400045c3  mov     r14, r9
0x1400045c6  mov     r15, r8
0x1400045c9  mov     rsi, rdx
0x1400045cc  mov     edi, ecx
0x1400045ce  xorps   xmm0, xmm0
0x1400045d1  movups  [rsp+178h+Size], xmm0
0x1400045d9  xorps   xmm1, xmm1
0x1400045dc  movups  [rsp+178h+var_B0], xmm1
0x1400045e4  movups  [rsp+178h+var_A0], xmm0
0x1400045ec  xor     edx, edx
0x1400045ee  xor     ecx, ecx
0x1400045f0  call    cs:__imp_EnterCrit
0x1400045f7  nop     dword ptr [rax+rax+00h]
0x1400045fc  lea     rcx, [rsp+178h+BugCheckParameter3]
0x140004604  call    ??0?$Win32HMOptionalThreadLockAlways@UtagMENU@@@@QEAA@XZ; Win32HMOptionalThreadLockAlways<tagMENU>::Win32HMOptionalThreadLockAlways<tagMENU>(void)
0x140004609  lea     rcx, [rsp+178h+BugCheckParameter2]; this
0x140004611  call    ??0_unnamed_type_list_@tagTLBLOCK@@QEAA@XZ; tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_(void)
0x140004616  lea     rcx, [rsp+178h+var_C8]
0x14000461e  call    ??0?$SmartObjStackRef@UtagMENU@@@@QEAA@XZ; SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(void)
0x140004623  mov     rcx, [rsp+178h+Src]
0x14000462b  xor     ebx, ebx
0x14000462d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140004631  jnz     loc_140004BA9
0x140004637  mov     r13d, ebx
0x14000463a  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14000463f  test    rax, rax
0x140004642  jz      short loc_140004654
0x140004644  mov     rax, [rax+1E8h]
0x14000464b  test    rax, rax
0x14000464e  jz      short loc_140004654
0x140004650  mov     r13, [rax+70h]
0x140004654  test    byte ptr [rsp+178h+arg_78], 1
0x14000465c  jnz     loc_140004BD3
0x140004662  test    [rsp+178h+arg_78], 0FFFFFFF8h
0x14000466d  jnz     loc_140004BD3
0x140004673  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140004678  mov     r12, rax
0x14000467b  mov     [rsp+178h+var_78], rax
0x140004683  mov     ecx, [rsp+178h+arg_20]
0x14000468a  and     ecx, 0C0000000h
0x140004690  cmp     ecx, 40000000h
0x140004696  jnz     loc_140004BE2
0x14000469c  mov     rdx, [rsp+178h+arg_50]
0x1400046a4  lea     rcx, [rsp+178h+var_58]
0x1400046ac  call    ??0?$SmartObjStackRef@UtagMENU@@@@QEAA@PEAUHMENU__@@@Z; SmartObjStackRef<tagMENU>::SmartObjStackRef<tagMENU>(HMENU__ *)
0x1400046b1  mov     rcx, [rax+10h]
0x1400046b5  mov     [rsp+178h+var_B8], rcx
0x1400046bd  mov     rdx, [rax]
0x1400046c0  mov     rdx, [rdx]
0x1400046c3  lea     rcx, [rsp+178h+var_C8]
0x1400046cb  call    ??4?$SmartObjStackRefBase@UtagMENU@@@@IEAAAEAV0@QEAUtagMENU@@@Z; SmartObjStackRefBase<tagMENU>::operator=(tagMENU * const)
0x1400046d0  lea     rcx, [rsp+178h+var_58]
0x1400046d8  call    ??1?$SmartObjStackRef@UtagMENU@@@@QEAA@XZ; SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(void)
0x1400046dd  mov     ecx, 400h
0x1400046e2  call    GetAppCompatFlags2
0x1400046e7  mov     ecx, edi
0x1400046e9  and     ecx, 800777FFh
0x1400046ef  bt      eax, 0Bh
0x1400046f3  cmovnb  ecx, edi
0x1400046f6  mov     r12d, ecx
0x1400046f9  and     r12d, 8A7F77FFh
0x140004700  cmp     r12d, ecx
0x140004703  cmovz   r12d, ecx
0x140004707  test    rsi, 0FFFFFFFFFFFF0000h
0x14000470e  jnz     loc_140004855
0x140004714  mov     edi, 7FFFFFFFh
0x140004719  test    r15, 0FFFFFFFFFFFF0000h
0x140004720  jnz     loc_1400047BC
0x140004726  test    r14, r14
0x140004729  jz      loc_140004A57
0x14000472f  mov     rcx, r14
0x140004732  call    cs:__imp_MmIsUserAddress
0x140004739  nop     dword ptr [rax+rax+00h]
0x14000473e  test    al, al
0x140004740  jz      loc_140004A3C
0x140004746  movups  xmm0, xmmword ptr [r14]
0x14000474a  movups  [rsp+178h+var_A0], xmm0
0x140004752  psrldq  xmm0, 8
0x140004757  movq    r9, xmm0
0x14000475c  test    r9, r9
0x14000475f  jz      loc_140004849
0x140004765  mov     rcx, qword ptr [rsp+178h+var_A0]
0x14000476d  mov     rax, rcx
0x140004770  shr     rax, 20h
0x140004774  and     eax, edi
0x140004776  cmp     ecx, eax
0x140004778  ja      loc_140004A4B
0x14000477e  mov     eax, dword ptr [rsp+178h+var_A0+4]
0x140004785  not     eax
0x140004787  shr     eax, 1Fh
0x14000478a  mov     edx, eax
0x14000478c  lea     r8d, [rax+1]; Alignment
0x140004790  mov     eax, ecx
0x140004792  inc     rax
0x140004795  add     rdx, rax; Length
0x140004798  mov     rcx, r9; Address
0x14000479b  call    cs:__imp_ProbeForRead
0x1400047a2  nop     dword ptr [rax+rax+00h]
0x1400047a7  lea     r14, [rsp+178h+var_A0]
0x1400047af  mov     [rsp+178h+arg_18], r14
0x1400047b7  jmp     loc_140004A57
0x1400047bc  mov     rcx, r15
0x1400047bf  call    cs:__imp_MmIsUserAddress
0x1400047c6  nop     dword ptr [rax+rax+00h]
0x1400047cb  test    al, al
0x1400047cd  jz      loc_140004A15
0x1400047d3  movups  xmm0, xmmword ptr [r15]
0x1400047d7  movups  [rsp+178h+var_B0], xmm0
0x1400047df  psrldq  xmm0, 8
0x1400047e4  movq    r9, xmm0
0x1400047e9  test    r9, r9
0x1400047ec  jz      loc_140004A30
0x1400047f2  mov     rcx, qword ptr [rsp+178h+var_B0]
0x1400047fa  mov     rax, rcx
0x1400047fd  shr     rax, 20h
0x140004801  and     eax, edi
0x140004803  cmp     ecx, eax
0x140004805  ja      loc_140004A24
0x14000480b  mov     eax, dword ptr [rsp+178h+var_B0+4]
0x140004812  not     eax
0x140004814  shr     eax, 1Fh
0x140004817  mov     edx, eax
0x140004819  lea     r8d, [rax+1]; Alignment
0x14000481d  mov     eax, ecx
0x14000481f  inc     rax
0x140004822  add     rdx, rax; Length
0x140004825  mov     rcx, r9; Address
0x140004828  call    cs:__imp_ProbeForRead
0x14000482f  nop     dword ptr [rax+rax+00h]
0x140004834  lea     r15, [rsp+178h+var_B0]
0x14000483c  mov     [rsp+178h+arg_10], r15
0x140004844  jmp     loc_140004726
0x140004849  mov     dword ptr [rsp+178h+var_A0], ebx
0x140004850  jmp     loc_1400047A7
0x140004855  mov     rcx, rsi
0x140004858  call    cs:__imp_MmIsUserAddress
0x14000485f  nop     dword ptr [rax+rax+00h]
0x140004864  test    al, al
0x140004866  jz      loc_1400049F1
0x14000486c  movups  xmm0, xmmword ptr [rsi]
0x14000486f  movups  [rsp+178h+Size], xmm0
0x140004877  psrldq  xmm0, 8
0x14000487c  movq    r9, xmm0
0x140004881  mov     [rsp+178h+Src], r9
0x140004889  mov     edi, 7FFFFFFFh
0x14000488e  test    r9, r9
0x140004891  jz      loc_140004A0C
0x140004897  mov     rdx, qword ptr [rsp+178h+Size]
0x14000489f  mov     rax, rdx
0x1400048a2  shr     rax, 20h
0x1400048a6  and     eax, edi
0x1400048a8  cmp     edx, eax
0x1400048aa  ja      loc_140004A00
0x1400048b0  mov     eax, dword ptr [rsp+178h+Size+4]
0x1400048b7  not     eax
0x1400048b9  shr     eax, 1Fh
0x1400048bc  mov     ecx, eax
0x1400048be  lea     r8d, [rax+1]; Alignment
0x1400048c2  mov     edx, edx
0x1400048c4  inc     rdx
0x1400048c7  add     rdx, rcx; Length
0x1400048ca  mov     rcx, r9; Address
0x1400048cd  call    cs:__imp_ProbeForRead
0x1400048d4  nop     dword ptr [rax+rax+00h]
0x1400048d9  mov     ecx, dword ptr [rsp+178h+Size]
0x1400048e0  add     rcx, 2
0x1400048e4  mov     edx, 78747355h
0x1400048e9  call    cs:__imp_Win32AllocPoolWithQuotaZInit
0x1400048f0  nop     dword ptr [rax+rax+00h]
0x1400048f5  mov     rsi, rax
0x1400048f8  mov     qword ptr [rsp+178h+Size+8], rax
0x140004900  test    rax, rax
0x140004903  jnz     short loc_140004916
0x140004905  mov     ecx, 0C0000017h; Status
0x14000490a  call    cs:__imp_ExRaiseStatus
0x140004916  cmp     [rsp+178h+var_80], 0FFFFFFFFFFFFFFFFh
0x14000491f  jz      short loc_14000494D
0x140004921  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140004926  mov     [rsp+178h+BugCheckParameter4], rax; BugCheckParameter4
0x14000492b  mov     r9, rsi; BugCheckParameter3
0x14000492e  lea     r8, [rsp+178h+BugCheckParameter2]; BugCheckParameter2
0x140004936  mov     edx, 12h; BugCheckParameter1
0x14000493b  mov     ecx, 164h; BugCheckCode
0x140004940  call    cs:__imp_KeBugCheckEx
0x14000494d  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140004952  mov     rcx, [rax+178h]
0x140004959  mov     [rsp+178h+BugCheckParameter2], rcx
0x140004961  lea     rcx, [rsp+178h+BugCheckParameter2]
0x140004969  mov     [rax+178h], rcx
0x140004970  mov     [rsp+178h+var_88], rsi
0x140004978  mov     rax, cs:__imp_Win32FreePool
0x14000497f  mov     [rsp+178h+var_80], rax
0x140004987  mov     r8d, dword ptr [rsp+178h+Size]; Size
0x14000498f  mov     rdx, [rsp+178h+Src]; Src
0x140004997  mov     rcx, qword ptr [rsp+178h+Size+8]; void *
0x14000499f  call    memmove
0x1400049a4  mov     ecx, dword ptr [rsp+178h+Size]
0x1400049ab  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1400049af  mov     rax, qword ptr [rsp+178h+Size+8]
0x1400049b7  mov     [rcx+rax], bx
0x1400049bb  mov     ecx, dword ptr [rsp+178h+Size]
0x1400049c2  add     ecx, 2
0x1400049c5  and     ecx, edi
0x1400049c7  mov     eax, dword ptr [rsp+178h+Size+4]
0x1400049ce  and     eax, 80000000h
0x1400049d3  or      ecx, eax
0x1400049d5  mov     dword ptr [rsp+178h+Size+4], ecx
0x1400049dc  lea     rsi, [rsp+178h+Size]
0x1400049e4  mov     [rsp+178h+arg_8], rsi
0x1400049ec  jmp     loc_140004719
0x1400049f1  mov     rax, cs:MmUserProbeAddress
0x1400049f8  mov     rsi, [rax]
0x1400049fb  jmp     loc_14000486C
0x140004a00  call    cs:__imp_ExRaiseAccessViolation
0x140004a07  nop     dword ptr [rax+rax+00h]
0x140004a0c  mov     dword ptr [rsp+178h+Size], ebx
0x140004a13  jmp     short loc_1400049DC
0x140004a15  mov     rax, cs:MmUserProbeAddress
0x140004a1c  mov     r15, [rax]
0x140004a1f  jmp     loc_1400047D3
0x140004a24  call    cs:__imp_ExRaiseAccessViolation
0x140004a2b  nop     dword ptr [rax+rax+00h]
0x140004a30  mov     dword ptr [rsp+178h+var_B0], ebx
0x140004a37  jmp     loc_140004834
0x140004a3c  mov     rax, cs:MmUserProbeAddress
0x140004a43  mov     r14, [rax]
0x140004a46  jmp     loc_140004746
0x140004a4b  call    cs:__imp_ExRaiseAccessViolation
0x140004a52  nop     dword ptr [rax+rax+00h]
0x140004a57  jmp     short loc_140004A60
0x140004a59  xor     ebx, ebx
0x140004a5b  jmp     loc_140004B32
0x140004a60  mov     r8, r13
0x140004a63  mov     rdx, [rsp+178h+var_78]
0x140004a6b  lea     rcx, [rsp+178h+var_78]
0x140004a73  call    ??0?$Win32HMOptionalThreadLock@UtagWND@@@@QEAA@PEAUtagTHREADINFO@@PEAUtagWND@@@Z; Win32HMOptionalThreadLock<tagWND>::Win32HMOptionalThreadLock<tagWND>(tagTHREADINFO *,tagWND *)
0x140004a78  mov     rax, [rsp+178h+arg_80]
0x140004a80  mov     [rsp+178h+var_F8], rax
0x140004a88  mov     eax, [rsp+178h+arg_78]
0x140004a8f  mov     [rsp+178h+var_100], eax
0x140004a93  mov     eax, dword ptr [rsp+178h+arg_70]
0x140004a9a  mov     [rsp+178h+var_108], eax
0x140004a9e  mov     eax, [rsp+178h+arg_68]
0x140004aa5  mov     [rsp+178h+var_110], eax
0x140004aa9  mov     rax, [rsp+178h+arg_60]
0x140004ab1  mov     [rsp+178h+var_118], rax
0x140004ab6  mov     rax, [rsp+178h+arg_58]
0x140004abe  mov     [rsp+178h+var_120], rax
0x140004ac3  lea     rax, [rsp+178h+var_C8]
0x140004acb  mov     [rsp+178h+var_128], rax
0x140004ad0  mov     [rsp+178h+var_130], r13
0x140004ad5  mov     eax, [rsp+178h+arg_40]
0x140004adc  mov     [rsp+178h+var_138], eax
0x140004ae0  mov     eax, [rsp+178h+arg_38]
0x140004ae7  mov     [rsp+178h+var_140], eax
0x140004aeb  mov     eax, [rsp+178h+arg_30]
0x140004af2  mov     [rsp+178h+var_148], eax
0x140004af6  mov     eax, [rsp+178h+arg_28]
0x140004afd  mov     [rsp+178h+var_150], eax
0x140004b01  mov     eax, [rsp+178h+arg_20]
0x140004b08  mov     dword ptr [rsp+178h+BugCheckParameter4], eax
0x140004b0c  mov     r9, r14
0x140004b0f  mov     r8, r15
0x140004b12  mov     rdx, rsi
0x140004b15  mov     ecx, r12d
0x140004b18  call    xxxCreateWindowEx
0x140004b1d  test    rax, rax
0x140004b20  jz      short loc_140004B25
0x140004b22  mov     rbx, [rax]
0x140004b25  lea     rcx, [rsp+178h+var_78]; BugCheckParameter3
0x140004b2d  call    ??1?$Win32HMThreadLock@UtagCURSOR@@@@QEAA@XZ; Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>(void)
0x140004b32  lea     rcx, [rsp+178h+var_C8]
0x140004b3a  call    ??1?$SmartObjStackRef@UtagMENU@@@@QEAA@XZ; SmartObjStackRef<tagMENU>::~SmartObjStackRef<tagMENU>(void)
0x140004b3f  lea     rcx, [rsp+178h+BugCheckParameter2]
0x140004b47  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x140004b4c  lea     rcx, [rsp+178h+BugCheckParameter3]; BugCheckParameter3
0x140004b54  call    ??1?$Win32HMOptionalThreadLockAlways@UtagMENU@@@@QEAA@XZ; Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>(void)
0x140004b59  call    cs:__imp_UserSessionSwitchLeaveCrit
0x140004b60  nop     dword ptr [rax+rax+00h]
0x140004b65  mov     rax, rbx
0x140004b68  add     rsp, 140h
0x140004b6f  pop     r15
0x140004b71  pop     r14
0x140004b73  pop     r13
0x140004b75  pop     r12
0x140004b77  pop     rdi
0x140004b78  pop     rsi
0x140004b79  pop     rbx
0x140004b7a  retn
0x140004b7c  mov     rdx, [rsp+178h+var_B8]
0x140004b84  test    rdx, rdx
0x140004b87  jnz     short loc_140004B94
  ... truncated ...
```

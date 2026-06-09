# NtUserRegisterClassExWOW

- ea: `0x1401de740`
- end: `0x1401dee33`
- name: `NtUserRegisterClassExWOW`
- size: `1779`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, __int16, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x14002193c`
- `0x1400381a8`
- `0x1400b2dac`
- `0x1400bc81c`
- `0x1400bcaa0`
- `0x1400c2a10`
- `0x1401de740`
- `0x1401dee3c`
- `0x1401def48`
- `0x14022d028`
- `0x1402913f0`
- `0x1402a4d38`
- `0x140342240`
- `0x140342540`
- `0x1403d21c8`
- `0x1403d2204`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x1401deab1`
- `ntoskrnl!ExRaiseStatus` at `0x1401deb5a`
- `ntoskrnl!ExRaiseStatus` at `0x1401deb79`
- `ntoskrnl!ExRaiseStatus` at `0x1401debf8`
- `ntoskrnl!ExRaiseStatus` at `0x1401deab1`
- `ntoskrnl!ExRaiseStatus` at `0x1401deb5a`
- `ntoskrnl!ExRaiseStatus` at `0x1401deb79`
- `ntoskrnl!ExRaiseStatus` at `0x1401debf8`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401deb14`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401deb49`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401dec27`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401deb14`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401deb49`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401dec27`
- `ntoskrnl!ProbeForRead` at `0x1401de99a`
- `ntoskrnl!ProbeForRead` at `0x1401dea11`
- `ntoskrnl!ProbeForRead` at `0x1401deace`
- `ntoskrnl!ProbeForRead` at `0x1401de99a`
- `ntoskrnl!ProbeForRead` at `0x1401dea11`
- `ntoskrnl!ProbeForRead` at `0x1401deace`
- `win32kbase!UserFindAtom` at `0x1401dec98`
- `win32kbase!UserFindAtom` at `0x1401dec98`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1401dea56`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1401deb8e`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1401dea56`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1401deb8e`
- `win32kbase!EnterCrit` at `0x1401de782`
- `win32kbase!EnterCrit` at `0x1401de782`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1401de7e5`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1401de7e5`
- `win32kbase!Win32FreePool` at `0x1401dea6f`
- `win32kbase!Win32FreePool` at `0x1401debaa`
- `WIN32K!W32GetUserSessionState` at `0x1401ded0d`
- `WIN32K!W32GetUserSessionState` at `0x1401ded0d`

## pseudocode

```c
__int64 __fastcall NtUserRegisterClassExWOW(
        void *Src,
        __int64 a2,
        __int64 a3,
        void *a4,
        unsigned __int16 a5,
        unsigned int a6)
{
  __int64 v9; // rdx
  struct tagTHREADINFO *v10; // rcx
  unsigned __int16 v11; // si
  __int64 v12; // rcx
  int ULongFromUser; // r14d
  unsigned __int64 v15; // r12
  __int64 v16; // rdi
  __int64 v17; // r8
  __int64 v18; // r9
  char *v19; // rbx
  __int64 v20; // rax
  ULONG_PTR v21; // rax
  ULONG_PTR v22; // rax
  unsigned __int64 v23; // rcx
  __int16 Atom; // di
  unsigned int j; // ebx
  unsigned int i; // edx
  int v27; // eax
  int v28; // eax
  int v29; // [rsp+40h] [rbp-188h]
  __int64 ULong64FromUser; // [rsp+48h] [rbp-180h]
  struct tagTHREADINFO *v31; // [rsp+50h] [rbp-178h]
  int v32; // [rsp+58h] [rbp-170h]
  __int64 Address; // [rsp+60h] [rbp-168h]
  __int128 v34; // [rsp+68h] [rbp-160h] BYREF
  __int64 v35; // [rsp+78h] [rbp-150h]
  char *v36; // [rsp+80h] [rbp-148h]
  ULONG_PTR v37; // [rsp+88h] [rbp-140h]
  int v38; // [rsp+90h] [rbp-138h]
  void *Srca; // [rsp+98h] [rbp-130h]
  ULONG_PTR v40[3]; // [rsp+A0h] [rbp-128h] BYREF
  ULONG_PTR BugCheckParameter2[3]; // [rsp+B8h] [rbp-110h] BYREF
  __int128 v42; // [rsp+D0h] [rbp-F8h] BYREF
  __int128 v43; // [rsp+E0h] [rbp-E8h]
  __int128 v44; // [rsp+F0h] [rbp-D8h]
  __int128 v45; // [rsp+100h] [rbp-C8h]
  __int128 v46; // [rsp+110h] [rbp-B8h]
  unsigned __int64 v47; // [rsp+120h] [rbp-A8h]
  __int64 v48; // [rsp+128h] [rbp-A0h]
  __int128 v49; // [rsp+130h] [rbp-98h] BYREF
  __int64 v50; // [rsp+140h] [rbp-88h]
  _OWORD v51[5]; // [rsp+148h] [rbp-80h] BYREF

  memset_0(&v42, 0, 0x60u);
  EnterCrit(0, 0);
  v10 = PtiCurrent();
  v31 = v10;
  if ( (a6 & 0xFFFFFF3D) != 0 )
  {
    UserSetLastError(1004);
    v11 = 0;
  }
  else
  {
    v11 = 0;
    if ( a5 )
    {
      v12 = 666;
      if ( (unsigned __int16)(a5 - 666) <= 0x1Eu )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= 5 )
          {
            v10 = v31;
            goto LABEL_3;
          }
          if ( LOWORD(gDefaultServerClasses[12 * i + 1]) == a5 )
            break;
        }
        UserSetLastError(87);
      }
    }
    else
    {
LABEL_3:
      if ( (*(_DWORD *)(*((_QWORD *)v10 + 57) + 12LL) & 0x10000000) != 0 || (unsigned int)RegisterIconTitleClass() )
      {
        tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_((tagTLBLOCK::_unnamed_type_list_ *)BugCheckParameter2);
        tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_((tagTLBLOCK::_unnamed_type_list_ *)v40);
        ULongFromUser = RtlReadULongFromUser(a2);
        v38 = ULongFromUser;
        Srca = (void *)RtlReadULong64FromUser(a2 + 8);
        v15 = (unsigned __int64)Srca;
        v29 = RtlReadULongFromUser(a3);
        ULong64FromUser = RtlReadULong64FromUser(a3 + 8);
        v36 = (char *)ULong64FromUser;
        v34 = 0;
        v35 = 0;
        RtlCopyFromUser(&v34, a4, 0x18u);
        v49 = v34;
        v50 = v35;
        v16 = v35;
        v32 = RtlReadULongFromUser(v35);
        Address = RtlReadULong64FromUser(v16 + 8);
        memset_0(v51, 0, sizeof(v51));
        RtlCopyFromUser(v51, Src, 0x50u);
        v42 = v51[0];
        v43 = v51[1];
        v44 = v51[2];
        v45 = v51[3];
        v46 = v51[4];
        if ( (v15 & 0xFFFFFFFFFFFF0000uLL) != 0 )
        {
          ProbeForRead((volatile void *)v15, (unsigned __int16)ULongFromUser + 2LL, 2u);
          if ( (unsigned __int16)ULongFromUser > HIWORD(ULongFromUser) || (ULongFromUser & 1) != 0 )
          {
            if ( (ULongFromUser & 1) != 0 )
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 10279);
            ExRaiseAccessViolation();
          }
        }
        if ( (v15 & 0xFFFFFFFFFFFF0000uLL) != 0 )
        {
          if ( (unsigned __int16)(ULongFromUser + 2) < (unsigned __int16)ULongFromUser )
            ExRaiseStatus(-1073741675);
          v21 = Win32AllocPoolWithQuotaZInit((unsigned __int16)(ULongFromUser + 2), 2020897621, v17, v18);
          v15 = v21;
          *((_QWORD *)&v34 + 1) = v21;
          if ( !v21 )
            ExRaiseStatus(-1073741801);
          Win32RawLockedItemBase<unsigned short,&void Win32FreePool(void *),1,1,1>::ManualLock<void>(
            (ULONG_PTR)BugCheckParameter2,
            v21);
          memmove((void *)v15, Srca, (unsigned __int16)ULongFromUser);
          *(_WORD *)(((unsigned __int16)ULongFromUser & 0xFFFE) + v15) = 0;
          WORD1(v34) = ULongFromUser + 2;
        }
        if ( (ULong64FromUser & 0xFFFFFFFFFFFF0000uLL) != 0 )
        {
          ProbeForRead((volatile void *)ULong64FromUser, (unsigned __int16)v29 + 2LL, 2u);
          if ( (unsigned __int16)v29 > HIWORD(v29) || (v29 & 1) != 0 )
          {
            if ( (v29 & 1) != 0 )
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 10301);
            ExRaiseAccessViolation();
          }
        }
        if ( (ULong64FromUser & 0xFFFFFFFFFFFF0000uLL) != 0 )
        {
          if ( (unsigned __int16)(v29 + 2) < (unsigned __int16)v29 )
            ExRaiseStatus(-1073741675);
          v22 = Win32AllocPoolWithQuotaZInit((unsigned __int16)(v29 + 2), 2020897621, v17, v18);
          v19 = (char *)v22;
          v37 = v22;
          if ( !v22 )
            ExRaiseStatus(-1073741801);
          Win32RawLockedItemBase<unsigned short,&void Win32FreePool(void *),1,1,1>::ManualLock<void>(
            (ULONG_PTR)v40,
            v22);
          memmove(v19, (const void *)ULong64FromUser, (unsigned __int16)v29);
          *(_WORD *)&v19[v29 & 0xFFFE] = 0;
          WORD1(v36) = v29 + 2;
        }
        else
        {
          v19 = v36;
        }
        v20 = Address;
        if ( (Address & 0xFFFFFFFFFFFF0000uLL) != 0 )
        {
          ProbeForRead((volatile void *)Address, (unsigned __int16)v32 + 2LL, 2u);
          if ( (unsigned __int16)v32 > HIWORD(v32) || (v32 & 1) != 0 )
          {
            if ( (v32 & 1) != 0 )
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 10323);
            ExRaiseAccessViolation();
          }
          v20 = Address;
        }
        *(_QWORD *)&v46 = v15;
        v47 = (unsigned __int64)v19;
        *((_QWORD *)&v45 + 1) = v20;
        if ( (*(_DWORD *)(*((_QWORD *)v31 + 57) + 12LL) & 0x2000) != 0
          || (unsigned int)RegisterDefaultClass((wchar_t *)v15) )
        {
          v23 = v47;
          if ( (v47 & 0xFFFFFFFFFFFF0000uLL) != 0 )
            Atom = UserFindAtom(v47);
          else
            Atom = v47;
          v48 = 0;
          if ( Atom )
          {
            for ( j = 0; j < 5; ++j )
            {
              v23 = *(_QWORD *)(W32GetUserSessionState(v23) + 19704);
              if ( Atom == *(_WORD *)(v23 + 2LL * (((unsigned int)gDefaultServerClasses[12 * j] >> 3) & 0x1F) + 868) )
              {
                v27 = HIWORD(gDefaultServerClasses[12 * j + 1]);
                if ( (_WORD)v27 )
                {
                  a6 |= v27;
                  if ( (a6 & 0x200) != 0 && SDWORD1(v43) < gDefaultServerClasses[12 * j + 6] )
                  {
                    UserSetLastError(5);
                    UserSetLastError(0);
                    goto LABEL_43;
                  }
                  v28 = gDefaultServerClasses[12 * j + 6];
                  if ( SDWORD1(v43) >= v28 )
                  {
                    LODWORD(v48) = gDefaultServerClasses[12 * j + 6];
                    DWORD1(v43) -= v28;
                  }
                  break;
                }
              }
            }
          }
          v11 = RegisterClassEx(&v42, &v49, a5, a6);
        }
LABEL_43:
        Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(v40);
        Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
      }
    }
  }
  UserSessionSwitchLeaveCrit(v12, v9);
  return v11;
}

```

## disassembly

```asm
0x1401de740  mov     rax, rsp
0x1401de743  mov     [rax+8], rbx
0x1401de747  mov     [rax+10h], rsi
0x1401de74b  mov     [rax+20h], r9
0x1401de74f  mov     [rax+18h], r8
0x1401de753  push    rdi
0x1401de754  push    r12
0x1401de756  push    r13
0x1401de758  push    r14
0x1401de75a  push    r15
0x1401de75c  sub     rsp, 1A0h
0x1401de763  mov     rdi, r8
0x1401de766  mov     r12, rdx
0x1401de769  mov     rbx, rcx
0x1401de76c  xor     edx, edx; Val
0x1401de76e  lea     r8d, [rdx+60h]; Size
0x1401de772  lea     rcx, [rax-0F8h]; void *
0x1401de779  call    memset_0
0x1401de77e  xor     edx, edx
0x1401de780  xor     ecx, ecx
0x1401de782  call    cs:__imp_EnterCrit
0x1401de789  nop     dword ptr [rax+rax+00h]
0x1401de78e  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401de793  mov     rcx, rax
0x1401de796  mov     [rsp+1C8h+var_178], rax
0x1401de79b  test    [rsp+1C8h+arg_28], 0FFFFFF3Dh
0x1401de7a6  jnz     loc_1401DED92
0x1401de7ac  xor     esi, esi
0x1401de7ae  movzx   r8d, [rsp+1C8h+arg_20]
0x1401de7b7  test    r8w, r8w
0x1401de7bb  jnz     loc_1401DED48
0x1401de7c1  lea     r13, gDefaultServerClasses
0x1401de7c8  lea     r15d, [rsi+1]
0x1401de7cc  mov     rax, [rcx+1C8h]
0x1401de7d3  test    dword ptr [rax+0Ch], 10000000h
0x1401de7da  jnz     short loc_1401DE812
0x1401de7dc  call    RegisterIconTitleClass
0x1401de7e1  test    eax, eax
0x1401de7e3  jnz     short loc_1401DE812
0x1401de7e5  call    cs:__imp_UserSessionSwitchLeaveCrit
0x1401de7ec  nop     dword ptr [rax+rax+00h]
0x1401de7f1  movzx   eax, si
0x1401de7f4  lea     r11, [rsp+1C8h+var_28]
0x1401de7fc  mov     rbx, [r11+30h]
0x1401de800  mov     rsi, [r11+38h]
0x1401de804  mov     rsp, r11
0x1401de807  pop     r15
0x1401de809  pop     r14
0x1401de80b  pop     r13
0x1401de80d  pop     r12
0x1401de80f  pop     rdi
0x1401de810  retn
0x1401de812  lea     rcx, [rsp+1C8h+BugCheckParameter2]; this
0x1401de81a  call    ??0_unnamed_type_list_@tagTLBLOCK@@QEAA@XZ; tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_(void)
0x1401de81f  lea     rcx, [rsp+1C8h+var_128]; this
0x1401de827  call    ??0_unnamed_type_list_@tagTLBLOCK@@QEAA@XZ; tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_(void)
0x1401de82c  nop
0x1401de82d  mov     rcx, r12
0x1401de830  call    RtlReadULongFromUser
0x1401de835  mov     r14d, eax
0x1401de838  mov     [rsp+1C8h+var_138], r14d
0x1401de840  lea     rcx, [r12+8]
0x1401de845  call    RtlReadULong64FromUser
0x1401de84a  mov     [rsp+1C8h+Src], rax
0x1401de852  mov     ecx, r14d
0x1401de855  shr     ecx, 10h
0x1401de858  mov     [rsp+1C8h+var_1A4], ecx
0x1401de85c  mov     r12, rax
0x1401de85f  mov     rcx, rdi
0x1401de862  call    RtlReadULongFromUser
0x1401de867  mov     edi, eax
0x1401de869  mov     [rsp+1C8h+var_188], eax
0x1401de86d  mov     rcx, [rsp+1C8h+arg_10]
0x1401de875  add     rcx, 8
0x1401de879  call    RtlReadULong64FromUser
0x1401de87e  mov     [rsp+1C8h+var_180], rax
0x1401de883  mov     ecx, edi
0x1401de885  shr     ecx, 10h
0x1401de888  mov     [rsp+1C8h+var_1A8], ecx
0x1401de88c  mov     [rsp+1C8h+var_148], rax
0x1401de894  xorps   xmm0, xmm0
0x1401de897  xor     eax, eax
0x1401de899  movups  [rsp+1C8h+var_160], xmm0
0x1401de89e  mov     [rsp+1C8h+var_150], rax
0x1401de8a3  lea     r8d, [rax+18h]; Size
0x1401de8a7  mov     rdx, [rsp+1C8h+arg_18]; Src
0x1401de8af  lea     rcx, [rsp+1C8h+var_160]; void *
0x1401de8b4  call    RtlCopyFromUser
0x1401de8b9  movups  xmm0, [rsp+1C8h+var_160]
0x1401de8be  movups  [rsp+1C8h+var_98], xmm0
0x1401de8c6  movsd   xmm1, [rsp+1C8h+var_150]
0x1401de8cc  movsd   [rsp+1C8h+var_88], xmm1
0x1401de8d5  movq    rdi, xmm1
0x1401de8da  mov     rcx, rdi
0x1401de8dd  call    RtlReadULongFromUser
0x1401de8e2  mov     [rsp+1C8h+var_170], eax
0x1401de8e6  lea     rcx, [rdi+8]
0x1401de8ea  call    RtlReadULong64FromUser
0x1401de8ef  mov     [rsp+1C8h+Address], rax
0x1401de8f4  mov     eax, [rsp+1C8h+var_170]
0x1401de8f8  shr     eax, 10h
0x1401de8fb  mov     [rsp+1C8h+var_1A0], eax
0x1401de8ff  mov     edi, 50h ; 'P'
0x1401de904  mov     r8d, edi; Size
0x1401de907  xor     edx, edx; Val
0x1401de909  lea     rcx, [rsp+1C8h+var_80]; void *
0x1401de911  call    memset_0
0x1401de916  mov     r8d, edi; Size
0x1401de919  mov     rdx, rbx; Src
0x1401de91c  lea     rcx, [rsp+1C8h+var_80]; void *
0x1401de924  call    RtlCopyFromUser
0x1401de929  movups  xmm4, [rsp+1C8h+var_80]
0x1401de931  movups  xmm3, [rsp+1C8h+var_70]
0x1401de939  movups  xmm2, [rsp+1C8h+var_60]
0x1401de941  movups  xmm1, [rsp+1C8h+var_50]
0x1401de949  movups  xmm0, [rsp+1C8h+var_40]
0x1401de951  movaps  [rsp+1C8h+var_F8], xmm4
0x1401de959  movaps  [rsp+1C8h+var_E8], xmm3
0x1401de961  movaps  [rsp+1C8h+var_D8], xmm2
0x1401de969  movaps  [rsp+1C8h+var_C8], xmm1
0x1401de971  movaps  [rsp+1C8h+var_B8], xmm0
0x1401de979  mov     rax, r12
0x1401de97c  mov     rbx, rax
0x1401de97f  and     rbx, 0FFFFFFFFFFFF0000h
0x1401de986  mov     edi, 2
0x1401de98b  jz      short loc_1401DE9C3
0x1401de98d  movzx   edx, r14w
0x1401de991  add     rdx, rdi; Length
0x1401de994  mov     r8d, edi; Alignment
0x1401de997  mov     rcx, rax; Address
0x1401de99a  call    cs:__imp_ProbeForRead
0x1401de9a1  nop     dword ptr [rax+rax+00h]
0x1401de9a6  movzx   eax, r14w
0x1401de9aa  and     ax, r15w
0x1401de9ae  cmp     r14w, word ptr [rsp+1C8h+var_1A4]
0x1401de9b4  ja      loc_1401DEB20
0x1401de9ba  test    ax, ax
0x1401de9bd  jnz     loc_1401DEB20
0x1401de9c3  test    rbx, rbx
0x1401de9c6  jnz     short loc_1401DEA3C
0x1401de9c8  mov     rax, [rsp+1C8h+var_180]
0x1401de9cd  mov     r14, rax
0x1401de9d0  and     r14, 0FFFFFFFFFFFF0000h
0x1401de9d7  jnz     loc_1401DEABD
0x1401de9dd  test    r14, r14
0x1401de9e0  jnz     loc_1401DEB66
0x1401de9e6  mov     rbx, [rsp+1C8h+var_148]
0x1401de9ee  mov     rax, [rsp+1C8h+Address]
0x1401de9f3  test    rax, 0FFFFFFFFFFFF0000h
0x1401de9f9  jz      loc_1401DEC33
0x1401de9ff  mov     r14d, [rsp+1C8h+var_170]
0x1401dea04  movzx   edx, r14w
0x1401dea08  add     rdx, rdi; Length
0x1401dea0b  mov     r8d, edi; Alignment
0x1401dea0e  mov     rcx, rax; Address
0x1401dea11  call    cs:__imp_ProbeForRead
0x1401dea18  nop     dword ptr [rax+rax+00h]
0x1401dea1d  cmp     r14w, word ptr [rsp+1C8h+var_1A0]
0x1401dea23  ja      loc_1401DEC04
0x1401dea29  test    r15b, r14b
0x1401dea2c  jnz     loc_1401DEC04
0x1401dea32  mov     rax, [rsp+1C8h+Address]
0x1401dea37  jmp     loc_1401DEC33
0x1401dea3c  lea     ebx, [rdi+r14]
0x1401dea40  cmp     bx, r14w
0x1401dea44  jb      loc_1401DEB55
0x1401dea4a  movzx   r14d, r14w
0x1401dea4e  movzx   ecx, bx
0x1401dea51  mov     edx, 78747355h
0x1401dea56  call    cs:__imp_Win32AllocPoolWithQuotaZInit
0x1401dea5d  nop     dword ptr [rax+rax+00h]
0x1401dea62  mov     r12, rax
0x1401dea65  mov     qword ptr [rsp+1C8h+var_160+8], rax
0x1401dea6a  test    rax, rax
0x1401dea6d  jz      short loc_1401DEAAC
0x1401dea6f  mov     r8, cs:__imp_Win32FreePool
0x1401dea76  mov     rdx, rax; BugCheckParameter3
0x1401dea79  lea     rcx, [rsp+1C8h+BugCheckParameter2]; BugCheckParameter2
0x1401dea81  call    ??$ManualLock@X@?$Win32RawLockedItemBase@G$1?Win32FreePool@@YAXPEAX@Z$00$00$00@@QEAAXPEAGP6AXPEAX@Z@Z; Win32RawLockedItemBase<ushort,&Win32FreePool(void *),1,1,1>::ManualLock<void>(ushort *,void (*)(void *))
0x1401dea86  mov     r8d, r14d; Size
0x1401dea89  mov     rdx, [rsp+1C8h+Src]; Src
0x1401dea91  mov     rcx, r12; void *
0x1401dea94  call    memmove
0x1401dea99  and     r14, 0FFFFFFFFFFFFFFFEh
0x1401dea9d  mov     [r14+r12], si
0x1401deaa2  mov     word ptr [rsp+1C8h+var_160+2], bx
0x1401deaa7  jmp     loc_1401DE9C8
0x1401deaac  mov     ecx, 0C0000017h; Status
0x1401deab1  call    cs:__imp_ExRaiseStatus
0x1401deabd  mov     ecx, [rsp+1C8h+var_188]
0x1401deac1  movzx   ebx, cx
0x1401deac4  lea     rdx, [rdi+rbx]; Length
0x1401deac8  mov     r8d, edi; Alignment
0x1401deacb  mov     rcx, rax; Address
0x1401deace  call    cs:__imp_ProbeForRead
0x1401dead5  nop     dword ptr [rax+rax+00h]
0x1401deada  movzx   eax, bx
0x1401deadd  and     ax, r15w
0x1401deae1  cmp     bx, word ptr [rsp+1C8h+var_1A8]
0x1401deae6  ja      short loc_1401DEAF1
0x1401deae8  test    ax, ax
0x1401deaeb  jz      loc_1401DE9DD
0x1401deaf1  test    ax, ax
0x1401deaf4  jz      short loc_1401DEB14
0x1401deaf6  mov     [rsp+1C8h+var_1A8], 20000h
0x1401deafe  mov     r8d, 283Dh
0x1401deb04  mov     edx, [rsp+1C8h+var_1A8]
0x1401deb08  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401deb0f  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401deb14  call    cs:__imp_ExRaiseAccessViolation
0x1401deb1b  nop     dword ptr [rax+rax+00h]
0x1401deb20  test    ax, ax
0x1401deb23  jz      short loc_1401DEB49
0x1401deb25  mov     [rsp+1C8h+arg_28], 20000h
0x1401deb30  mov     r8d, 2827h
0x1401deb36  mov     edx, [rsp+1C8h+arg_28]
0x1401deb3d  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401deb44  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401deb49  call    cs:__imp_ExRaiseAccessViolation
0x1401deb50  nop     dword ptr [rax+rax+00h]
0x1401deb55  mov     ecx, 0C0000095h; Status
0x1401deb5a  call    cs:__imp_ExRaiseStatus
0x1401deb66  mov     eax, [rsp+1C8h+var_188]
0x1401deb6a  lea     r14d, [rdi+rax]
0x1401deb6e  cmp     r14w, ax
0x1401deb72  jnb     short loc_1401DEB85
0x1401deb74  mov     ecx, 0C0000095h; Status
0x1401deb79  call    cs:__imp_ExRaiseStatus
0x1401deb85  movzx   ecx, r14w
0x1401deb89  mov     edx, 78747355h
0x1401deb8e  call    cs:__imp_Win32AllocPoolWithQuotaZInit
0x1401deb95  nop     dword ptr [rax+rax+00h]
0x1401deb9a  mov     rbx, rax
0x1401deb9d  mov     [rsp+1C8h+var_140], rax
0x1401deba5  test    rax, rax
0x1401deba8  jz      short loc_1401DEBF3
0x1401debaa  mov     r8, cs:__imp_Win32FreePool
0x1401debb1  mov     rdx, rax; BugCheckParameter3
0x1401debb4  lea     rcx, [rsp+1C8h+var_128]; BugCheckParameter2
0x1401debbc  call    ??$ManualLock@X@?$Win32RawLockedItemBase@G$1?Win32FreePool@@YAXPEAX@Z$00$00$00@@QEAAXPEAGP6AXPEAX@Z@Z; Win32RawLockedItemBase<ushort,&Win32FreePool(void *),1,1,1>::ManualLock<void>(ushort *,void (*)(void *))
0x1401debc1  mov     eax, [rsp+1C8h+var_188]
0x1401debc5  movzx   r8d, ax; Size
0x1401debc9  mov     rdx, [rsp+1C8h+var_180]; Src
0x1401debce  mov     rcx, rbx; void *
0x1401debd1  call    memmove
0x1401debd6  mov     ecx, [rsp+1C8h+var_188]
0x1401debda  movzx   eax, cx
0x1401debdd  and     rax, 0FFFFFFFFFFFFFFFEh
0x1401debe1  mov     [rax+rbx], si
0x1401debe5  mov     word ptr [rsp+1C8h+var_148+2], r14w
0x1401debee  jmp     loc_1401DE9EE
0x1401debf3  mov     ecx, 0C0000017h; Status
0x1401debf8  call    cs:__imp_ExRaiseStatus
0x1401dec04  test    r15b, r14b
0x1401dec07  jz      short loc_1401DEC27
0x1401dec09  mov     [rsp+1C8h+var_1A4], 20000h
0x1401dec11  mov     r8d, 2853h
0x1401dec17  mov     edx, [rsp+1C8h+var_1A4]
0x1401dec1b  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401dec22  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401dec27  call    cs:__imp_ExRaiseAccessViolation
0x1401dec2e  nop     dword ptr [rax+rax+00h]
0x1401dec33  mov     qword ptr [rsp+1C8h+var_B8], r12
0x1401dec3b  mov     [rsp+1C8h+var_A8], rbx
0x1401dec43  mov     qword ptr [rsp+1C8h+var_C8+8], rax
0x1401dec4b  jmp     short loc_1401DEC6E
0x1401dec4d  xor     esi, esi
0x1401dec4f  lea     rcx, [rsp+1C8h+var_128]
0x1401dec57  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401dec5c  lea     rcx, [rsp+1C8h+BugCheckParameter2]
0x1401dec64  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401dec69  jmp     loc_1401DE7E5
0x1401dec6e  mov     rax, [rsp+1C8h+var_178]
0x1401dec73  mov     rax, [rax+1C8h]
0x1401dec7a  test    dword ptr [rax+0Ch], 2000h
0x1401dec81  jz      loc_1401DEDB2
0x1401dec87  mov     rcx, [rsp+1C8h+var_A8]
0x1401dec8f  test    rcx, 0FFFFFFFFFFFF0000h
0x1401dec96  jz      short loc_1401DECFC
0x1401dec98  call    cs:__imp_UserFindAtom
0x1401dec9f  nop     dword ptr [rax+rax+00h]
0x1401deca4  movzx   edi, ax
0x1401deca7  mov     [rsp+1C8h+var_A0], rsi
0x1401decaf  test    di, di
0x1401decb2  jnz     short loc_1401DED06
0x1401decb4  mov     r9d, [rsp+1C8h+arg_28]
0x1401decbc  movzx   r8d, [rsp+1C8h+arg_20]
0x1401decc5  lea     rdx, [rsp+1C8h+var_98]
0x1401deccd  lea     rcx, [rsp+1C8h+var_F8]
0x1401decd5  call    _RegisterClassEx
0x1401decda  movzx   esi, ax
0x1401decdd  lea     rcx, [rsp+1C8h+var_128]
0x1401dece5  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401decea  lea     rcx, [rsp+1C8h+BugCheckParameter2]
0x1401decf2  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401decf7  jmp     loc_1401DE7E5
0x1401decfc  movzx   edi, word ptr [rsp+1C8h+var_A8]
0x1401ded04  jmp     short loc_1401DECA7
0x1401ded06  mov     ebx, esi
0x1401ded08  cmp     ebx, 5
  ... truncated ...
```

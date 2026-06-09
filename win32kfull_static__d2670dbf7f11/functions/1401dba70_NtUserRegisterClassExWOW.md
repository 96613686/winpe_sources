# NtUserRegisterClassExWOW

- ea: `0x1401dba70`
- end: `0x1401dc163`
- name: `NtUserRegisterClassExWOW`
- size: `1779`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, __int16, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x14001c76c`
- `0x140033b58`
- `0x1400d903c`
- `0x1400e2a2c`
- `0x1400e2cb0`
- `0x1400e8c20`
- `0x1401dba70`
- `0x1401dc16c`
- `0x1401dc278`
- `0x14022e338`
- `0x1402938dc`
- `0x1402a7178`
- `0x140343200`
- `0x140343500`
- `0x1403d31c8`
- `0x1403d3204`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x1401dbde1`
- `ntoskrnl!ExRaiseStatus` at `0x1401dbe8a`
- `ntoskrnl!ExRaiseStatus` at `0x1401dbea9`
- `ntoskrnl!ExRaiseStatus` at `0x1401dbf28`
- `ntoskrnl!ExRaiseStatus` at `0x1401dbde1`
- `ntoskrnl!ExRaiseStatus` at `0x1401dbe8a`
- `ntoskrnl!ExRaiseStatus` at `0x1401dbea9`
- `ntoskrnl!ExRaiseStatus` at `0x1401dbf28`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401dbe44`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401dbe79`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401dbf57`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401dbe44`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401dbe79`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401dbf57`
- `ntoskrnl!ProbeForRead` at `0x1401dbcca`
- `ntoskrnl!ProbeForRead` at `0x1401dbd41`
- `ntoskrnl!ProbeForRead` at `0x1401dbdfe`
- `ntoskrnl!ProbeForRead` at `0x1401dbcca`
- `ntoskrnl!ProbeForRead` at `0x1401dbd41`
- `ntoskrnl!ProbeForRead` at `0x1401dbdfe`
- `win32kbase!UserFindAtom` at `0x1401dbfc8`
- `win32kbase!UserFindAtom` at `0x1401dbfc8`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1401dbd86`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1401dbebe`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1401dbd86`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1401dbebe`
- `win32kbase!EnterCrit` at `0x1401dbab2`
- `win32kbase!EnterCrit` at `0x1401dbab2`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1401dbb15`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1401dbb15`
- `win32kbase!Win32FreePool` at `0x1401dbd9f`
- `win32kbase!Win32FreePool` at `0x1401dbeda`
- `WIN32K!W32GetUserSessionState` at `0x1401dc03d`
- `WIN32K!W32GetUserSessionState` at `0x1401dc03d`

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
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 10401);
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
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 10423);
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
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 10445);
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
0x1401dba70  mov     rax, rsp
0x1401dba73  mov     [rax+8], rbx
0x1401dba77  mov     [rax+10h], rsi
0x1401dba7b  mov     [rax+20h], r9
0x1401dba7f  mov     [rax+18h], r8
0x1401dba83  push    rdi
0x1401dba84  push    r12
0x1401dba86  push    r13
0x1401dba88  push    r14
0x1401dba8a  push    r15
0x1401dba8c  sub     rsp, 1A0h
0x1401dba93  mov     rdi, r8
0x1401dba96  mov     r12, rdx
0x1401dba99  mov     rbx, rcx
0x1401dba9c  xor     edx, edx; Val
0x1401dba9e  lea     r8d, [rdx+60h]; Size
0x1401dbaa2  lea     rcx, [rax-0F8h]; void *
0x1401dbaa9  call    memset_0
0x1401dbaae  xor     edx, edx
0x1401dbab0  xor     ecx, ecx
0x1401dbab2  call    cs:__imp_EnterCrit
0x1401dbab9  nop     dword ptr [rax+rax+00h]
0x1401dbabe  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401dbac3  mov     rcx, rax
0x1401dbac6  mov     [rsp+1C8h+var_178], rax
0x1401dbacb  test    [rsp+1C8h+arg_28], 0FFFFFF3Dh
0x1401dbad6  jnz     loc_1401DC0C2
0x1401dbadc  xor     esi, esi
0x1401dbade  movzx   r8d, [rsp+1C8h+arg_20]
0x1401dbae7  test    r8w, r8w
0x1401dbaeb  jnz     loc_1401DC078
0x1401dbaf1  lea     r13, gDefaultServerClasses
0x1401dbaf8  lea     r15d, [rsi+1]
0x1401dbafc  mov     rax, [rcx+1C8h]
0x1401dbb03  test    dword ptr [rax+0Ch], 10000000h
0x1401dbb0a  jnz     short loc_1401DBB42
0x1401dbb0c  call    RegisterIconTitleClass
0x1401dbb11  test    eax, eax
0x1401dbb13  jnz     short loc_1401DBB42
0x1401dbb15  call    cs:__imp_UserSessionSwitchLeaveCrit
0x1401dbb1c  nop     dword ptr [rax+rax+00h]
0x1401dbb21  movzx   eax, si
0x1401dbb24  lea     r11, [rsp+1C8h+var_28]
0x1401dbb2c  mov     rbx, [r11+30h]
0x1401dbb30  mov     rsi, [r11+38h]
0x1401dbb34  mov     rsp, r11
0x1401dbb37  pop     r15
0x1401dbb39  pop     r14
0x1401dbb3b  pop     r13
0x1401dbb3d  pop     r12
0x1401dbb3f  pop     rdi
0x1401dbb40  retn
0x1401dbb42  lea     rcx, [rsp+1C8h+BugCheckParameter2]; this
0x1401dbb4a  call    ??0_unnamed_type_list_@tagTLBLOCK@@QEAA@XZ; tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_(void)
0x1401dbb4f  lea     rcx, [rsp+1C8h+var_128]; this
0x1401dbb57  call    ??0_unnamed_type_list_@tagTLBLOCK@@QEAA@XZ; tagTLBLOCK::_unnamed_type_list_::_unnamed_type_list_(void)
0x1401dbb5c  nop
0x1401dbb5d  mov     rcx, r12
0x1401dbb60  call    RtlReadULongFromUser
0x1401dbb65  mov     r14d, eax
0x1401dbb68  mov     [rsp+1C8h+var_138], r14d
0x1401dbb70  lea     rcx, [r12+8]
0x1401dbb75  call    RtlReadULong64FromUser
0x1401dbb7a  mov     [rsp+1C8h+Src], rax
0x1401dbb82  mov     ecx, r14d
0x1401dbb85  shr     ecx, 10h
0x1401dbb88  mov     [rsp+1C8h+var_1A4], ecx
0x1401dbb8c  mov     r12, rax
0x1401dbb8f  mov     rcx, rdi
0x1401dbb92  call    RtlReadULongFromUser
0x1401dbb97  mov     edi, eax
0x1401dbb99  mov     [rsp+1C8h+var_188], eax
0x1401dbb9d  mov     rcx, [rsp+1C8h+arg_10]
0x1401dbba5  add     rcx, 8
0x1401dbba9  call    RtlReadULong64FromUser
0x1401dbbae  mov     [rsp+1C8h+var_180], rax
0x1401dbbb3  mov     ecx, edi
0x1401dbbb5  shr     ecx, 10h
0x1401dbbb8  mov     [rsp+1C8h+var_1A8], ecx
0x1401dbbbc  mov     [rsp+1C8h+var_148], rax
0x1401dbbc4  xorps   xmm0, xmm0
0x1401dbbc7  xor     eax, eax
0x1401dbbc9  movups  [rsp+1C8h+var_160], xmm0
0x1401dbbce  mov     [rsp+1C8h+var_150], rax
0x1401dbbd3  lea     r8d, [rax+18h]; Size
0x1401dbbd7  mov     rdx, [rsp+1C8h+arg_18]; Src
0x1401dbbdf  lea     rcx, [rsp+1C8h+var_160]; void *
0x1401dbbe4  call    RtlCopyFromUser
0x1401dbbe9  movups  xmm0, [rsp+1C8h+var_160]
0x1401dbbee  movups  [rsp+1C8h+var_98], xmm0
0x1401dbbf6  movsd   xmm1, [rsp+1C8h+var_150]
0x1401dbbfc  movsd   [rsp+1C8h+var_88], xmm1
0x1401dbc05  movq    rdi, xmm1
0x1401dbc0a  mov     rcx, rdi
0x1401dbc0d  call    RtlReadULongFromUser
0x1401dbc12  mov     [rsp+1C8h+var_170], eax
0x1401dbc16  lea     rcx, [rdi+8]
0x1401dbc1a  call    RtlReadULong64FromUser
0x1401dbc1f  mov     [rsp+1C8h+Address], rax
0x1401dbc24  mov     eax, [rsp+1C8h+var_170]
0x1401dbc28  shr     eax, 10h
0x1401dbc2b  mov     [rsp+1C8h+var_1A0], eax
0x1401dbc2f  mov     edi, 50h ; 'P'
0x1401dbc34  mov     r8d, edi; Size
0x1401dbc37  xor     edx, edx; Val
0x1401dbc39  lea     rcx, [rsp+1C8h+var_80]; void *
0x1401dbc41  call    memset_0
0x1401dbc46  mov     r8d, edi; Size
0x1401dbc49  mov     rdx, rbx; Src
0x1401dbc4c  lea     rcx, [rsp+1C8h+var_80]; void *
0x1401dbc54  call    RtlCopyFromUser
0x1401dbc59  movups  xmm4, [rsp+1C8h+var_80]
0x1401dbc61  movups  xmm3, [rsp+1C8h+var_70]
0x1401dbc69  movups  xmm2, [rsp+1C8h+var_60]
0x1401dbc71  movups  xmm1, [rsp+1C8h+var_50]
0x1401dbc79  movups  xmm0, [rsp+1C8h+var_40]
0x1401dbc81  movaps  [rsp+1C8h+var_F8], xmm4
0x1401dbc89  movaps  [rsp+1C8h+var_E8], xmm3
0x1401dbc91  movaps  [rsp+1C8h+var_D8], xmm2
0x1401dbc99  movaps  [rsp+1C8h+var_C8], xmm1
0x1401dbca1  movaps  [rsp+1C8h+var_B8], xmm0
0x1401dbca9  mov     rax, r12
0x1401dbcac  mov     rbx, rax
0x1401dbcaf  and     rbx, 0FFFFFFFFFFFF0000h
0x1401dbcb6  mov     edi, 2
0x1401dbcbb  jz      short loc_1401DBCF3
0x1401dbcbd  movzx   edx, r14w
0x1401dbcc1  add     rdx, rdi; Length
0x1401dbcc4  mov     r8d, edi; Alignment
0x1401dbcc7  mov     rcx, rax; Address
0x1401dbcca  call    cs:__imp_ProbeForRead
0x1401dbcd1  nop     dword ptr [rax+rax+00h]
0x1401dbcd6  movzx   eax, r14w
0x1401dbcda  and     ax, r15w
0x1401dbcde  cmp     r14w, word ptr [rsp+1C8h+var_1A4]
0x1401dbce4  ja      loc_1401DBE50
0x1401dbcea  test    ax, ax
0x1401dbced  jnz     loc_1401DBE50
0x1401dbcf3  test    rbx, rbx
0x1401dbcf6  jnz     short loc_1401DBD6C
0x1401dbcf8  mov     rax, [rsp+1C8h+var_180]
0x1401dbcfd  mov     r14, rax
0x1401dbd00  and     r14, 0FFFFFFFFFFFF0000h
0x1401dbd07  jnz     loc_1401DBDED
0x1401dbd0d  test    r14, r14
0x1401dbd10  jnz     loc_1401DBE96
0x1401dbd16  mov     rbx, [rsp+1C8h+var_148]
0x1401dbd1e  mov     rax, [rsp+1C8h+Address]
0x1401dbd23  test    rax, 0FFFFFFFFFFFF0000h
0x1401dbd29  jz      loc_1401DBF63
0x1401dbd2f  mov     r14d, [rsp+1C8h+var_170]
0x1401dbd34  movzx   edx, r14w
0x1401dbd38  add     rdx, rdi; Length
0x1401dbd3b  mov     r8d, edi; Alignment
0x1401dbd3e  mov     rcx, rax; Address
0x1401dbd41  call    cs:__imp_ProbeForRead
0x1401dbd48  nop     dword ptr [rax+rax+00h]
0x1401dbd4d  cmp     r14w, word ptr [rsp+1C8h+var_1A0]
0x1401dbd53  ja      loc_1401DBF34
0x1401dbd59  test    r15b, r14b
0x1401dbd5c  jnz     loc_1401DBF34
0x1401dbd62  mov     rax, [rsp+1C8h+Address]
0x1401dbd67  jmp     loc_1401DBF63
0x1401dbd6c  lea     ebx, [rdi+r14]
0x1401dbd70  cmp     bx, r14w
0x1401dbd74  jb      loc_1401DBE85
0x1401dbd7a  movzx   r14d, r14w
0x1401dbd7e  movzx   ecx, bx
0x1401dbd81  mov     edx, 78747355h
0x1401dbd86  call    cs:__imp_Win32AllocPoolWithQuotaZInit
0x1401dbd8d  nop     dword ptr [rax+rax+00h]
0x1401dbd92  mov     r12, rax
0x1401dbd95  mov     qword ptr [rsp+1C8h+var_160+8], rax
0x1401dbd9a  test    rax, rax
0x1401dbd9d  jz      short loc_1401DBDDC
0x1401dbd9f  mov     r8, cs:__imp_Win32FreePool
0x1401dbda6  mov     rdx, rax; BugCheckParameter3
0x1401dbda9  lea     rcx, [rsp+1C8h+BugCheckParameter2]; BugCheckParameter2
0x1401dbdb1  call    ??$ManualLock@X@?$Win32RawLockedItemBase@G$1?Win32FreePool@@YAXPEAX@Z$00$00$00@@QEAAXPEAGP6AXPEAX@Z@Z; Win32RawLockedItemBase<ushort,&Win32FreePool(void *),1,1,1>::ManualLock<void>(ushort *,void (*)(void *))
0x1401dbdb6  mov     r8d, r14d; Size
0x1401dbdb9  mov     rdx, [rsp+1C8h+Src]; Src
0x1401dbdc1  mov     rcx, r12; void *
0x1401dbdc4  call    memmove
0x1401dbdc9  and     r14, 0FFFFFFFFFFFFFFFEh
0x1401dbdcd  mov     [r14+r12], si
0x1401dbdd2  mov     word ptr [rsp+1C8h+var_160+2], bx
0x1401dbdd7  jmp     loc_1401DBCF8
0x1401dbddc  mov     ecx, 0C0000017h; Status
0x1401dbde1  call    cs:__imp_ExRaiseStatus
0x1401dbded  mov     ecx, [rsp+1C8h+var_188]
0x1401dbdf1  movzx   ebx, cx
0x1401dbdf4  lea     rdx, [rdi+rbx]; Length
0x1401dbdf8  mov     r8d, edi; Alignment
0x1401dbdfb  mov     rcx, rax; Address
0x1401dbdfe  call    cs:__imp_ProbeForRead
0x1401dbe05  nop     dword ptr [rax+rax+00h]
0x1401dbe0a  movzx   eax, bx
0x1401dbe0d  and     ax, r15w
0x1401dbe11  cmp     bx, word ptr [rsp+1C8h+var_1A8]
0x1401dbe16  ja      short loc_1401DBE21
0x1401dbe18  test    ax, ax
0x1401dbe1b  jz      loc_1401DBD0D
0x1401dbe21  test    ax, ax
0x1401dbe24  jz      short loc_1401DBE44
0x1401dbe26  mov     [rsp+1C8h+var_1A8], 20000h
0x1401dbe2e  mov     r8d, 28B7h
0x1401dbe34  mov     edx, [rsp+1C8h+var_1A8]
0x1401dbe38  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401dbe3f  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401dbe44  call    cs:__imp_ExRaiseAccessViolation
0x1401dbe4b  nop     dword ptr [rax+rax+00h]
0x1401dbe50  test    ax, ax
0x1401dbe53  jz      short loc_1401DBE79
0x1401dbe55  mov     [rsp+1C8h+arg_28], 20000h
0x1401dbe60  mov     r8d, 28A1h
0x1401dbe66  mov     edx, [rsp+1C8h+arg_28]
0x1401dbe6d  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401dbe74  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401dbe79  call    cs:__imp_ExRaiseAccessViolation
0x1401dbe80  nop     dword ptr [rax+rax+00h]
0x1401dbe85  mov     ecx, 0C0000095h; Status
0x1401dbe8a  call    cs:__imp_ExRaiseStatus
0x1401dbe96  mov     eax, [rsp+1C8h+var_188]
0x1401dbe9a  lea     r14d, [rdi+rax]
0x1401dbe9e  cmp     r14w, ax
0x1401dbea2  jnb     short loc_1401DBEB5
0x1401dbea4  mov     ecx, 0C0000095h; Status
0x1401dbea9  call    cs:__imp_ExRaiseStatus
0x1401dbeb5  movzx   ecx, r14w
0x1401dbeb9  mov     edx, 78747355h
0x1401dbebe  call    cs:__imp_Win32AllocPoolWithQuotaZInit
0x1401dbec5  nop     dword ptr [rax+rax+00h]
0x1401dbeca  mov     rbx, rax
0x1401dbecd  mov     [rsp+1C8h+var_140], rax
0x1401dbed5  test    rax, rax
0x1401dbed8  jz      short loc_1401DBF23
0x1401dbeda  mov     r8, cs:__imp_Win32FreePool
0x1401dbee1  mov     rdx, rax; BugCheckParameter3
0x1401dbee4  lea     rcx, [rsp+1C8h+var_128]; BugCheckParameter2
0x1401dbeec  call    ??$ManualLock@X@?$Win32RawLockedItemBase@G$1?Win32FreePool@@YAXPEAX@Z$00$00$00@@QEAAXPEAGP6AXPEAX@Z@Z; Win32RawLockedItemBase<ushort,&Win32FreePool(void *),1,1,1>::ManualLock<void>(ushort *,void (*)(void *))
0x1401dbef1  mov     eax, [rsp+1C8h+var_188]
0x1401dbef5  movzx   r8d, ax; Size
0x1401dbef9  mov     rdx, [rsp+1C8h+var_180]; Src
0x1401dbefe  mov     rcx, rbx; void *
0x1401dbf01  call    memmove
0x1401dbf06  mov     ecx, [rsp+1C8h+var_188]
0x1401dbf0a  movzx   eax, cx
0x1401dbf0d  and     rax, 0FFFFFFFFFFFFFFFEh
0x1401dbf11  mov     [rax+rbx], si
0x1401dbf15  mov     word ptr [rsp+1C8h+var_148+2], r14w
0x1401dbf1e  jmp     loc_1401DBD1E
0x1401dbf23  mov     ecx, 0C0000017h; Status
0x1401dbf28  call    cs:__imp_ExRaiseStatus
0x1401dbf34  test    r15b, r14b
0x1401dbf37  jz      short loc_1401DBF57
0x1401dbf39  mov     [rsp+1C8h+var_1A4], 20000h
0x1401dbf41  mov     r8d, 28CDh
0x1401dbf47  mov     edx, [rsp+1C8h+var_1A4]
0x1401dbf4b  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401dbf52  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401dbf57  call    cs:__imp_ExRaiseAccessViolation
0x1401dbf5e  nop     dword ptr [rax+rax+00h]
0x1401dbf63  mov     qword ptr [rsp+1C8h+var_B8], r12
0x1401dbf6b  mov     [rsp+1C8h+var_A8], rbx
0x1401dbf73  mov     qword ptr [rsp+1C8h+var_C8+8], rax
0x1401dbf7b  jmp     short loc_1401DBF9E
0x1401dbf7d  xor     esi, esi
0x1401dbf7f  lea     rcx, [rsp+1C8h+var_128]
0x1401dbf87  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401dbf8c  lea     rcx, [rsp+1C8h+BugCheckParameter2]
0x1401dbf94  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401dbf99  jmp     loc_1401DBB15
0x1401dbf9e  mov     rax, [rsp+1C8h+var_178]
0x1401dbfa3  mov     rax, [rax+1C8h]
0x1401dbfaa  test    dword ptr [rax+0Ch], 2000h
0x1401dbfb1  jz      loc_1401DC0E2
0x1401dbfb7  mov     rcx, [rsp+1C8h+var_A8]
0x1401dbfbf  test    rcx, 0FFFFFFFFFFFF0000h
0x1401dbfc6  jz      short loc_1401DC02C
0x1401dbfc8  call    cs:__imp_UserFindAtom
0x1401dbfcf  nop     dword ptr [rax+rax+00h]
0x1401dbfd4  movzx   edi, ax
0x1401dbfd7  mov     [rsp+1C8h+var_A0], rsi
0x1401dbfdf  test    di, di
0x1401dbfe2  jnz     short loc_1401DC036
0x1401dbfe4  mov     r9d, [rsp+1C8h+arg_28]
0x1401dbfec  movzx   r8d, [rsp+1C8h+arg_20]
0x1401dbff5  lea     rdx, [rsp+1C8h+var_98]
0x1401dbffd  lea     rcx, [rsp+1C8h+var_F8]
0x1401dc005  call    _RegisterClassEx
0x1401dc00a  movzx   esi, ax
0x1401dc00d  lea     rcx, [rsp+1C8h+var_128]
0x1401dc015  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401dc01a  lea     rcx, [rsp+1C8h+BugCheckParameter2]
0x1401dc022  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401dc027  jmp     loc_1401DBB15
0x1401dc02c  movzx   edi, word ptr [rsp+1C8h+var_A8]
0x1401dc034  jmp     short loc_1401DBFD7
0x1401dc036  mov     ebx, esi
0x1401dc038  cmp     ebx, 5
  ... truncated ...
```

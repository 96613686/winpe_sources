# fnHkINLPMSG

- ea: `0x140010a10`
- end: `0x1400110de`
- name: `fnHkINLPMSG`
- size: `1742`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x14001070c`
- `0x14014ec30`

## callees

- `0x140010a10`
- `0x1400110e4`
- `0x140011784`
- `0x1400c2a10`
- `0x1401b3e80`
- `0x1401efb90`
- `0x1401efc40`
- `0x14026872c`
- `0x1402a4d38`

## import_xrefs

- `ntoskrnl!NlsAnsiCodePage` at `0x140010b82`
- `ntoskrnl!KeUserModeCallback` at `0x140010d31`
- `ntoskrnl!KeUserModeCallback` at `0x140010d31`
- `ntoskrnl!RtlUnicodeToMultiByteN` at `0x140010bac`
- `ntoskrnl!RtlUnicodeToMultiByteN` at `0x140010bac`
- `ntoskrnl!RtlNtStatusToDosError` at `0x140342d59`
- `ntoskrnl!RtlNtStatusToDosError` at `0x140342d59`
- `ntoskrnl!ProbeForRead` at `0x140010ecc`
- `ntoskrnl!ProbeForRead` at `0x140010ecc`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010c08`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010c2c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010c50`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010c6f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010cb1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010ccd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010d77`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010fa0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010c08`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010c2c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010c50`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010c6f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010cb1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010ccd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010d77`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010fa0`
- `win32kbase!EtwTraceBeginCallback` at `0x140010d03`
- `win32kbase!EtwTraceBeginCallback` at `0x140010d03`
- `win32kbase!EtwTraceEndCallback` at `0x140010d45`
- `win32kbase!EtwTraceEndCallback` at `0x140010d45`
- `win32kbase!EnterSharedCrit` at `0x140010df4`
- `win32kbase!EnterSharedCrit` at `0x140010df4`
- `win32kbase!_HMPheFromObject` at `0x140010bf2`
- `win32kbase!_HMPheFromObject` at `0x140010f76`
- `win32kbase!_HMPheFromObject` at `0x140010bf2`
- `win32kbase!_HMPheFromObject` at `0x140010f76`
- `win32kbase!EnterCrit` at `0x140010d62`
- `win32kbase!EnterCrit` at `0x140010d62`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140010cf2`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140010cf2`
- `WIN32K!W32GetUserSessionState` at `0x140010b5b`
- `WIN32K!W32GetUserSessionState` at `0x140011056`
- `WIN32K!W32GetUserSessionState` at `0x140010b5b`
- `WIN32K!W32GetUserSessionState` at `0x140011056`

## pseudocode

```c
__int64 __fastcall fnHkINLPMSG(
        unsigned __int64 a1,
        __int64 a2,
        __int128 *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _DWORD *a7)
{
  unsigned int v9; // r14d
  int v10; // r13d
  __int64 v11; // r12
  __int64 v12; // r15
  __int64 v13; // rax
  __int64 v14; // rdi
  unsigned int v16; // edi
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 UserSessionState; // rax
  ULONG BytesInUnicodeString; // edx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rcx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v28; // rcx
  __int64 *v29; // rax
  __int64 v30; // rcx
  __int64 *v31; // rax
  __int64 v32; // rcx
  unsigned __int64 *v33; // rax
  __int64 v34; // rcx
  int v35; // edi
  BOOL v36; // esi
  __int64 *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rcx
  int v41; // r15d
  __int64 v42; // rcx
  __int64 *v43; // rax
  __int64 v44; // rcx
  _QWORD *v45; // rax
  __int64 v46; // rsi
  _OWORD *v47; // rdi
  __int64 v48; // rcx
  int v49; // eax
  _QWORD *v50; // rdx
  __int64 v51; // rdi
  _QWORD v52[3]; // [rsp+30h] [rbp-F8h] BYREF
  void *Src; // [rsp+48h] [rbp-E0h] BYREF
  __int64 v54; // [rsp+50h] [rbp-D8h]
  _QWORD v55[2]; // [rsp+60h] [rbp-C8h] BYREF
  __int128 v56; // [rsp+70h] [rbp-B8h]
  __int128 v57; // [rsp+80h] [rbp-A8h]
  __m256i UnicodeString; // [rsp+90h] [rbp-98h] BYREF
  __int64 v59; // [rsp+B0h] [rbp-78h]
  __int128 v60; // [rsp+C0h] [rbp-68h] BYREF
  volatile void *Address; // [rsp+D0h] [rbp-58h]
  __int64 v62; // [rsp+D8h] [rbp-50h]
  unsigned int MultiByteString; // [rsp+130h] [rbp+8h] BYREF
  int v64; // [rsp+138h] [rbp+10h] BYREF
  __int64 v65; // [rsp+140h] [rbp+18h]

  Src = 0;
  v64 = 0;
  v65 = 0;
  v54 = 0;
  v52[0] = 0;
  v56 = 0;
  *(_OWORD *)UnicodeString.m256i_i8 = 0;
  v59 = 0;
  v55[0] = (unsigned int)a1;
  v55[1] = a2;
  *((_DWORD *)a3 + 3) = 0;
  *((_DWORD *)a3 + 11) = 0;
  v57 = *a3;
  UnicodeString.m256i_i32[0] = *((_DWORD *)a3 + 4);
  *(_OWORD *)((char *)UnicodeString.m256i_i64 + 4) = *(__int128 *)((char *)a3 + 20);
  *(_OWORD *)&UnicodeString.m256i_u64[2] = a3[2];
  v9 = *((_DWORD *)a3 + 2);
  v10 = a6;
  if ( ((v9 - 258) & 0xFFFFFFFB) != 0 || !(_DWORD)a6 )
  {
    if ( v9 == 283 || v9 == 576 || (v11 = 0, v9 == 281) )
    {
      v11 = *((_QWORD *)a3 + 2);
      v12 = *((_QWORD *)a3 + 3);
      v65 = v12;
      LOBYTE(a2) = -1;
      v13 = HMValidateHandleWithDescriptor(v12, a2);
      v14 = v13;
      if ( !v13 || *((_DWORD *)a3 + 2) == 576 && *(_BYTE *)(_HMPheFromObject(v13) + 24) != 20 )
        return 0;
      v26 = (unsigned int)(*((_DWORD *)a3 + 2) - 281);
      if ( (v26 & 0xFFFFFFFD) == 0 && *(_BYTE *)(_HMPheFromObject(v14) + 24) != 21 )
        return 0;
      CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v26);
      if ( CurrentThreadWin32Thread )
        v28 = *CurrentThreadWin32Thread;
      else
        v28 = 0;
      v54 = *(_QWORD *)(v28 + 728);
      v29 = (__int64 *)PsGetCurrentThreadWin32Thread(v28);
      if ( v29 )
        v30 = *v29;
      else
        v30 = 0;
      v52[0] = *(_QWORD *)(v30 + 736);
      v31 = (__int64 *)PsGetCurrentThreadWin32Thread(v30);
      if ( v31 )
        v32 = *v31;
      else
        v32 = 0;
      *(_QWORD *)(v32 + 728) = v12;
      v33 = (unsigned __int64 *)PsGetCurrentThreadWin32Thread(v32);
      if ( v33 )
        a1 = *v33;
      else
        a1 = 0;
      *(_QWORD *)(a1 + 736) = v11;
    }
  }
  else
  {
    v11 = *((_QWORD *)a3 + 2);
    MultiByteString = 0;
    if ( v9 != 288 )
    {
      if ( v9 > 0x106 )
      {
        if ( v9 != 263 && v9 != 271 && v9 != 646 )
          goto LABEL_29;
      }
      else if ( v9 != 262 && v9 != 47 && v9 != 204 && v9 - 258 > 1 )
      {
        goto LABEL_29;
      }
    }
    v16 = THREAD_CODEPAGE();
    MultiByteString = 0;
    UserSessionState = W32GetUserSessionState(v18, v17, v19, v20);
    BytesInUnicodeString = 2;
    if ( (**(_DWORD **)(UserSessionState + 19704) & 2) == 0 )
      BytesInUnicodeString = 4;
    if ( (_WORD)v16 == NlsAnsiCodePage || !(_WORD)v16 )
    {
      if ( RtlUnicodeToMultiByteN((PCHAR)&MultiByteString, 4u, 0, (PCWCH)&UnicodeString, BytesInUnicodeString) < 0 )
      {
        UnicodeString.m256i_i64[0] = 0;
        goto LABEL_29;
      }
    }
    else if ( !ConvertToAndFromWideChar(
                 v16,
                 (unsigned __int16 *)&UnicodeString,
                 BytesInUnicodeString,
                 (char *)&MultiByteString,
                 4,
                 0) )
    {
      UnicodeString.m256i_i64[0] = 0;
      goto LABEL_29;
    }
    a1 = *(_QWORD *)(W32GetUserSessionState(a1, v23, v24, v25) + 19704);
    if ( (*(_DWORD *)a1 & 2) != 0 )
    {
      a1 = 65280;
      if ( (MultiByteString & 0xFF00) != 0 )
      {
        a1 = ((unsigned __int64)(unsigned __int16)MultiByteString >> 8)
           | (((unsigned __int8)MultiByteString | ((unsigned __int64)UnicodeString.m256i_u16[1] << 8)) << 8);
        UnicodeString.m256i_i64[0] = a1;
      }
      else
      {
        UnicodeString.m256i_i64[0] = (unsigned __int8)MultiByteString;
      }
    }
    else
    {
      UnicodeString.m256i_i64[0] = MultiByteString;
    }
  }
LABEL_29:
  *(_QWORD *)&v56 = a4;
  *((_QWORD *)&v56 + 1) = a5;
  LODWORD(v59) = *a7;
  v35 = (*(_DWORD *)(PsGetCurrentThreadWin32Thread(a1) + 24) >> 2) & 3;
  v36 = 1;
  if ( v35 )
  {
    v37 = (__int64 *)PsGetCurrentThreadWin32Thread(v34);
    if ( v37 )
      v40 = *v37;
    else
      v40 = 0;
    v36 = *(_BYTE *)(v40 + 1708) != 1;
    UserSessionSwitchLeaveCrit(v40, v38, v39);
  }
  EtwTraceBeginCallback(47);
  v41 = KeUserModeCallback(47, v55, 88, &Src, &v64);
  EtwTraceEndCallback(47);
  if ( v35 )
  {
    if ( v35 == 1 )
      EnterSharedCrit(0, v36);
    else
      EnterCrit(0, v36);
  }
  if ( v9 == 283 || v9 == 576 || v9 == 281 )
  {
    v43 = (__int64 *)PsGetCurrentThreadWin32Thread(v42);
    if ( v43 )
      v44 = *v43;
    else
      v44 = 0;
    *(_QWORD *)(v44 + 728) = v54;
    v45 = (_QWORD *)PsGetCurrentThreadWin32Thread(v44);
    if ( v45 )
      v45 = (_QWORD *)*v45;
    v45[92] = v52[0];
  }
  if ( v41 < 0 || v64 != 24 )
    return 0;
  v52[0] = 0;
  RtlCopyFromUser(v52, Src, 8u);
  v46 = v52[0];
  v62 = v52[0];
  v60 = 0;
  Address = 0;
  RtlCopyFromUser(&v60, Src, 0x18u);
  v47 = Address;
  ProbeForRead(Address, 0x38u, 4u);
  *a3 = *v47;
  a3[1] = v47[1];
  a3[2] = v47[2];
  *a7 ^= (*((_DWORD *)v47 + 12) ^ *a7) & 0x10;
  v48 = *((unsigned int *)a3 + 2);
  if ( (((_DWORD)v48 - 258) & 0xFFFFFFFB) == 0 && v10 )
  {
    v50 = a3 + 1;
    if ( UnicodeString.m256i_i64[0] == *((_QWORD *)a3 + 2) )
      *v50 = v11;
    else
      RtlMBMessageWParamCharToWCS(v48, v50);
  }
  v49 = *((_DWORD *)a3 + 2);
  if ( v49 == 283 || v49 == 576 || v49 == 281 )
  {
    *((_DWORD *)a3 + 2) = v9;
    *((_QWORD *)a3 + 2) = v11;
    *((_QWORD *)a3 + 3) = v65;
  }
  else if ( v11 == 1 )
  {
    v51 = v65;
    if ( v9 == 576 )
      FreeTouchInputInfo(v65, 1);
    if ( ((v9 - 281) & 0xFFFFFFFD) == 0 )
      FreeGestureInfo(v51, 1);
  }
  return v46;
}

```

## disassembly

```asm
0x140010a10  mov     r11, rsp
0x140010a13  push    rbx
0x140010a14  push    rsi
0x140010a15  push    rdi
0x140010a16  push    r12
0x140010a18  push    r13
0x140010a1a  push    r14
0x140010a1c  push    r15
0x140010a1e  sub     rsp, 0F0h
0x140010a25  mov     rsi, r9
0x140010a28  mov     rbx, r8
0x140010a2b  xor     r8d, r8d
0x140010a2e  mov     [rsp+128h+Src], r8
0x140010a33  mov     [r11+10h], r8d
0x140010a37  mov     [rsp+128h+arg_10], r8
0x140010a3f  mov     [rsp+128h+var_D8], r8
0x140010a44  mov     [rsp+128h+var_F8], r8
0x140010a49  xorps   xmm0, xmm0
0x140010a4c  xor     eax, eax
0x140010a4e  movups  [rsp+128h+var_C8], xmm0
0x140010a53  movups  [rsp+128h+var_B8], xmm0
0x140010a58  movups  xmmword ptr [rsp+128h+UnicodeString], xmm0
0x140010a60  mov     [r11-78h], rax
0x140010a64  mov     dword ptr [rsp+128h+var_C8], ecx
0x140010a68  mov     qword ptr [rsp+128h+var_C8+8], rdx
0x140010a6d  mov     [rbx+0Ch], eax
0x140010a70  mov     [rbx+2Ch], eax
0x140010a73  movups  xmm0, xmmword ptr [rbx]
0x140010a76  movaps  [rsp+128h+var_A8], xmm0
0x140010a7e  movzx   eax, word ptr [rbx+10h]
0x140010a82  mov     [rsp+128h+UnicodeString], ax
0x140010a8a  movzx   eax, word ptr [rbx+12h]
0x140010a8e  mov     [rsp+128h+UnicodeString+2], ax
0x140010a96  movups  xmm0, xmmword ptr [rbx+14h]
0x140010a9a  movups  xmmword ptr [rsp+128h+UnicodeString+4], xmm0
0x140010aa2  movups  xmm1, xmmword ptr [rbx+20h]
0x140010aa6  movups  [rsp+128h+var_88], xmm1
0x140010aae  mov     r14d, [rbx+8]
0x140010ab2  lea     eax, [r14-102h]
0x140010ab9  mov     r13d, dword ptr [rsp+128h+arg_28]
0x140010ac1  test    eax, 0FFFFFFFBh
0x140010ac6  jz      short loc_140010B02
0x140010ac8  cmp     r14d, 11Bh
0x140010acf  jnz     loc_140010DD2
0x140010ad5  mov     r12, [rbx+10h]
0x140010ad9  mov     r15, [rbx+18h]
0x140010add  mov     [rsp+128h+arg_10], r15
0x140010ae5  mov     dl, 0FFh
0x140010ae7  mov     rcx, r15
0x140010aea  call    HMValidateHandleWithDescriptor
0x140010aef  mov     rdi, rax
0x140010af2  test    rax, rax
0x140010af5  jnz     loc_140010BD1
0x140010afb  xor     eax, eax
0x140010afd  jmp     loc_140010E1D
0x140010b02  test    r13d, r13d
0x140010b05  jz      short loc_140010AC8
0x140010b07  mov     r12, [rbx+10h]
0x140010b0b  mov     [rsp+128h+MultiByteString], r8d
0x140010b13  cmp     r14d, 120h
0x140010b1a  jz      short loc_140010B48
0x140010b1c  cmp     r14d, 106h
0x140010b23  ja      loc_140010DAB
0x140010b29  jz      short loc_140010B48
0x140010b2b  mov     eax, r14d
0x140010b2e  sub     eax, 2Fh ; '/'
0x140010b31  jz      short loc_140010B48
0x140010b33  sub     eax, 9Dh
0x140010b38  jz      short loc_140010B48
0x140010b3a  sub     eax, 36h ; '6'
0x140010b3d  jz      short loc_140010B48
0x140010b3f  cmp     eax, 1
0x140010b42  jnz     loc_140010C8E
0x140010b48  call    ?THREAD_CODEPAGE@@YAGXZ; THREAD_CODEPAGE(void)
0x140010b4d  movzx   edi, ax
0x140010b50  mov     [rsp+128h+MultiByteString], 0
0x140010b5b  call    cs:__imp_W32GetUserSessionState
0x140010b62  nop     dword ptr [rax+rax+00h]
0x140010b67  mov     rcx, [rax+4CF8h]
0x140010b6e  mov     edx, [rcx]
0x140010b70  test    dl, 2
0x140010b73  mov     edx, 2
0x140010b78  mov     r15d, 4
0x140010b7e  cmovz   edx, r15d
0x140010b82  mov     rcx, cs:__imp_NlsAnsiCodePage
0x140010b89  cmp     di, [rcx]
0x140010b8c  jnz     loc_140011011
0x140010b92  mov     [rsp+128h+BytesInUnicodeString], edx; BytesInUnicodeString
0x140010b96  lea     r9, [rsp+128h+UnicodeString]; UnicodeString
0x140010b9e  xor     r8d, r8d; BytesInMultiByteString
0x140010ba1  mov     edx, r15d; MaxBytesInMultiByteString
0x140010ba4  lea     rcx, [rsp+128h+MultiByteString]; MultiByteString
0x140010bac  call    cs:__imp_RtlUnicodeToMultiByteN
0x140010bb3  nop     dword ptr [rax+rax+00h]
0x140010bb8  test    eax, eax
0x140010bba  jns     loc_140011056
0x140010bc0  mov     qword ptr [rsp+128h+UnicodeString], 0
0x140010bcc  jmp     loc_140010C8E
0x140010bd1  cmp     dword ptr [rbx+8], 240h
0x140010bd8  jz      loc_140010F73
0x140010bde  mov     ecx, [rbx+8]
0x140010be1  sub     ecx, 119h
0x140010be7  test    ecx, 0FFFFFFFDh
0x140010bed  jnz     short loc_140010C08
0x140010bef  mov     rcx, rdi
0x140010bf2  call    cs:__imp__HMPheFromObject
0x140010bf9  nop     dword ptr [rax+rax+00h]
0x140010bfe  cmp     byte ptr [rax+18h], 15h
0x140010c02  jnz     loc_140010AFB
0x140010c08  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140010c0f  nop     dword ptr [rax+rax+00h]
0x140010c14  test    rax, rax
0x140010c17  jz      loc_140010FBA
0x140010c1d  mov     rcx, [rax]
0x140010c20  mov     rax, [rcx+2D8h]
0x140010c27  mov     [rsp+128h+var_D8], rax
0x140010c2c  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140010c33  nop     dword ptr [rax+rax+00h]
0x140010c38  test    rax, rax
0x140010c3b  jz      loc_140010FC1
0x140010c41  mov     rcx, [rax]
0x140010c44  mov     rax, [rcx+2E0h]
0x140010c4b  mov     [rsp+128h+var_F8], rax
0x140010c50  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140010c57  nop     dword ptr [rax+rax+00h]
0x140010c5c  test    rax, rax
0x140010c5f  jz      loc_140010FC8
0x140010c65  mov     rcx, [rax]
0x140010c68  mov     [rcx+2D8h], r15
0x140010c6f  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140010c76  nop     dword ptr [rax+rax+00h]
0x140010c7b  test    rax, rax
0x140010c7e  jz      loc_140010FCF
0x140010c84  mov     rcx, [rax]
0x140010c87  mov     [rcx+2E0h], r12
0x140010c8e  mov     qword ptr [rsp+128h+var_B8], rsi
0x140010c93  mov     rax, [rsp+128h+arg_20]
0x140010c9b  mov     qword ptr [rsp+128h+var_B8+8], rax
0x140010ca0  mov     rax, [rsp+128h+arg_30]
0x140010ca8  mov     eax, [rax]
0x140010caa  mov     dword ptr [rsp+128h+var_78], eax
0x140010cb1  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140010cb8  nop     dword ptr [rax+rax+00h]
0x140010cbd  mov     edi, [rax+18h]
0x140010cc0  shr     edi, 2
0x140010cc3  and     edi, 3
0x140010cc6  mov     esi, 1
0x140010ccb  jz      short loc_140010CFE
0x140010ccd  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140010cd4  nop     dword ptr [rax+rax+00h]
0x140010cd9  test    rax, rax
0x140010cdc  jz      loc_140010F6C
0x140010ce2  mov     rcx, [rax]
0x140010ce5  xor     esi, esi
0x140010ce7  cmp     byte ptr [rcx+6ACh], 1
0x140010cee  setnz   sil
0x140010cf2  call    cs:__imp_UserSessionSwitchLeaveCrit
0x140010cf9  nop     dword ptr [rax+rax+00h]
0x140010cfe  mov     ecx, 2Fh ; '/'
0x140010d03  call    cs:__imp_EtwTraceBeginCallback
0x140010d0a  nop     dword ptr [rax+rax+00h]
0x140010d0f  lea     rax, [rsp+128h+arg_8]
0x140010d17  mov     qword ptr [rsp+128h+BytesInUnicodeString], rax
0x140010d1c  lea     r9, [rsp+128h+Src]
0x140010d21  mov     r8d, 58h ; 'X'
0x140010d27  lea     rdx, [rsp+128h+var_C8]
0x140010d2c  mov     ecx, 2Fh ; '/'
0x140010d31  call    cs:__imp_KeUserModeCallback
0x140010d38  nop     dword ptr [rax+rax+00h]
0x140010d3d  mov     r15d, eax
0x140010d40  mov     ecx, 2Fh ; '/'
0x140010d45  call    cs:__imp_EtwTraceEndCallback
0x140010d4c  nop     dword ptr [rax+rax+00h]
0x140010d51  test    edi, edi
0x140010d53  jz      short loc_140010D6E
0x140010d55  mov     edx, esi
0x140010d57  xor     ecx, ecx
0x140010d59  cmp     edi, 1
0x140010d5c  jz      loc_140010DF4
0x140010d62  call    cs:__imp_EnterCrit
0x140010d69  nop     dword ptr [rax+rax+00h]
0x140010d6e  cmp     r14d, 11Bh
0x140010d75  jnz     short loc_140010D93
0x140010d77  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140010d7e  nop     dword ptr [rax+rax+00h]
0x140010d83  test    rax, rax
0x140010d86  jnz     loc_140010F91
0x140010d8c  xor     ecx, ecx
0x140010d8e  jmp     loc_140010F94
0x140010d93  cmp     r14d, 240h
0x140010d9a  jz      short loc_140010D77
0x140010d9c  cmp     r14d, 119h
0x140010da3  jnz     loc_140010E40
0x140010da9  jmp     short loc_140010D77
0x140010dab  mov     eax, r14d
0x140010dae  sub     eax, 107h
0x140010db3  jz      loc_140010B48
0x140010db9  sub     eax, 8
0x140010dbc  jz      loc_140010B48
0x140010dc2  cmp     eax, 177h
0x140010dc7  jnz     loc_140010C8E
0x140010dcd  jmp     loc_140010B48
0x140010dd2  cmp     r14d, 240h
0x140010dd9  jz      loc_140010AD5
0x140010ddf  mov     r12, r8
0x140010de2  cmp     r14d, 119h
0x140010de9  jnz     loc_140010C8E
0x140010def  jmp     loc_140010AD5
0x140010df4  call    cs:__imp_EnterSharedCrit
0x140010dfb  nop     dword ptr [rax+rax+00h]
0x140010e00  jmp     loc_140010D6E
0x140010e05  cmp     eax, 119h
0x140010e0a  jz      loc_140010F25
0x140010e10  cmp     r12, 1
0x140010e14  jz      loc_140010FD6
0x140010e1a  mov     rax, rsi
0x140010e1d  add     rsp, 0F0h
0x140010e24  pop     r15
0x140010e26  pop     r14
0x140010e28  pop     r13
0x140010e2a  pop     r12
0x140010e2c  pop     rdi
0x140010e2d  pop     rsi
0x140010e2e  pop     rbx
0x140010e2f  retn
0x140010e31  mov     rax, [rax]
0x140010e34  mov     rcx, [rsp+128h+var_F8]
0x140010e39  mov     [rax+2E0h], rcx
0x140010e40  test    r15d, r15d
0x140010e43  js      loc_140010AFB
0x140010e49  cmp     [rsp+128h+arg_8], 18h
0x140010e51  jnz     loc_140010AFB
0x140010e57  mov     [rsp+128h+var_F8], 0
0x140010e60  mov     r8d, 8; Size
0x140010e66  mov     rdx, [rsp+128h+Src]; Src
0x140010e6b  lea     rcx, [rsp+128h+var_F8]; void *
0x140010e70  call    RtlCopyFromUser
0x140010e75  mov     rsi, [rsp+128h+var_F8]
0x140010e7a  mov     [rsp+128h+var_50], rsi
0x140010e82  jmp     short loc_140010E89
0x140010e84  jmp     loc_140010AFB
0x140010e89  xorps   xmm0, xmm0
0x140010e8c  xor     eax, eax
0x140010e8e  movups  [rsp+128h+var_68], xmm0
0x140010e96  mov     [rsp+128h+Address], rax
0x140010e9e  mov     r8d, 18h; Size
0x140010ea4  mov     rdx, [rsp+128h+Src]; Src
0x140010ea9  lea     rcx, [rsp+128h+var_68]; void *
0x140010eb1  call    RtlCopyFromUser
0x140010eb6  mov     rdi, [rsp+128h+Address]
0x140010ebe  mov     edx, 38h ; '8'; Length
0x140010ec3  mov     r8d, 4; Alignment
0x140010ec9  mov     rcx, rdi; Address
0x140010ecc  call    cs:__imp_ProbeForRead
0x140010ed3  nop     dword ptr [rax+rax+00h]
0x140010ed8  movups  xmm0, xmmword ptr [rdi]
0x140010edb  movups  xmmword ptr [rbx], xmm0
0x140010ede  movups  xmm1, xmmword ptr [rdi+10h]
0x140010ee2  movups  xmmword ptr [rbx+10h], xmm1
0x140010ee6  movups  xmm0, xmmword ptr [rdi+20h]
0x140010eea  movups  xmmword ptr [rbx+20h], xmm0
0x140010eee  mov     rdx, [rsp+128h+arg_30]
0x140010ef6  mov     eax, [rdx]
0x140010ef8  mov     ecx, eax
0x140010efa  xor     ecx, [rdi+30h]
0x140010efd  and     ecx, 10h
0x140010f00  xor     ecx, eax
0x140010f02  mov     [rdx], ecx
0x140010f04  jmp     short loc_140010F0B
0x140010f06  jmp     loc_140010AFB
0x140010f0b  mov     ecx, [rbx+8]
0x140010f0e  lea     eax, [rcx-102h]
0x140010f14  test    eax, 0FFFFFFFBh
0x140010f19  jz      short loc_140010F4A
0x140010f1b  mov     eax, [rbx+8]
0x140010f1e  cmp     eax, 11Bh
0x140010f23  jnz     short loc_140010F3E
0x140010f25  mov     [rbx+8], r14d
0x140010f29  mov     [rbx+10h], r12
0x140010f2d  mov     rdi, [rsp+128h+arg_10]
0x140010f35  mov     [rbx+18h], rdi
0x140010f39  jmp     loc_140010E1A
0x140010f3e  cmp     eax, 240h
0x140010f43  jz      short loc_140010F25
0x140010f45  jmp     loc_140010E05
0x140010f4a  test    r13d, r13d
0x140010f4d  jz      short loc_140010F1B
0x140010f4f  lea     rdx, [rbx+10h]
0x140010f53  mov     rax, [rdx]
0x140010f56  cmp     qword ptr [rsp+128h+UnicodeString], rax
0x140010f5e  jnz     short loc_140010F65
0x140010f60  mov     [rdx], r12
0x140010f63  jmp     short loc_140010F1B
0x140010f65  call    RtlMBMessageWParamCharToWCS
0x140010f6a  jmp     short loc_140010F1B
0x140010f6c  xor     ecx, ecx
0x140010f6e  jmp     loc_140010CE5
0x140010f73  mov     rcx, rdi
0x140010f76  call    cs:__imp__HMPheFromObject
0x140010f7d  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```

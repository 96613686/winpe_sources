# fnHkINLPMSG

- ea: `0x1400c1d20`
- end: `0x1400c23ee`
- name: `fnHkINLPMSG`
- size: `1742`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int128 *, __int64, __int64, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1400c1a1c`
- `0x140144bf0`

## callees

- `0x140081d40`
- `0x1400824b0`
- `0x1400c1d20`
- `0x1400c23f4`
- `0x1400c2a94`
- `0x1400e8c20`
- `0x1401b1090`
- `0x14026bc4c`
- `0x1402a7178`

## import_xrefs

- `ntoskrnl!NlsAnsiCodePage` at `0x1400c1e92`
- `ntoskrnl!KeUserModeCallback` at `0x1400c2041`
- `ntoskrnl!KeUserModeCallback` at `0x1400c2041`
- `ntoskrnl!RtlUnicodeToMultiByteN` at `0x1400c1ebc`
- `ntoskrnl!RtlUnicodeToMultiByteN` at `0x1400c1ebc`
- `ntoskrnl!RtlNtStatusToDosError` at `0x140344609`
- `ntoskrnl!RtlNtStatusToDosError` at `0x140344609`
- `ntoskrnl!ProbeForRead` at `0x1400c21dc`
- `ntoskrnl!ProbeForRead` at `0x1400c21dc`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c1f18`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c1f3c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c1f60`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c1f7f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c1fc1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c1fdd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c2087`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c22b0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c1f18`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c1f3c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c1f60`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c1f7f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c1fc1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c1fdd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c2087`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c22b0`
- `win32kbase!EtwTraceBeginCallback` at `0x1400c2013`
- `win32kbase!EtwTraceBeginCallback` at `0x1400c2013`
- `win32kbase!EtwTraceEndCallback` at `0x1400c2055`
- `win32kbase!EtwTraceEndCallback` at `0x1400c2055`
- `win32kbase!EnterSharedCrit` at `0x1400c2104`
- `win32kbase!EnterSharedCrit` at `0x1400c2104`
- `win32kbase!_HMPheFromObject` at `0x1400c1f02`
- `win32kbase!_HMPheFromObject` at `0x1400c2286`
- `win32kbase!_HMPheFromObject` at `0x1400c1f02`
- `win32kbase!_HMPheFromObject` at `0x1400c2286`
- `win32kbase!EnterCrit` at `0x1400c2072`
- `win32kbase!EnterCrit` at `0x1400c2072`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400c2002`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400c2002`
- `WIN32K!W32GetUserSessionState` at `0x1400c1e6b`
- `WIN32K!W32GetUserSessionState` at `0x1400c2366`
- `WIN32K!W32GetUserSessionState` at `0x1400c1e6b`
- `WIN32K!W32GetUserSessionState` at `0x1400c2366`

## pseudocode

```c
__int64 __fastcall fnHkINLPMSG(
        unsigned int a1,
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
  __int64 UserSessionState; // rax
  ULONG BytesInUnicodeString; // edx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v24; // rcx
  __int64 *v25; // rax
  __int64 v26; // rcx
  __int64 *v27; // rax
  __int64 v28; // rcx
  __int64 *v29; // rax
  __int64 v30; // rcx
  int v31; // edi
  BOOL v32; // esi
  __int64 *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rcx
  int v37; // r15d
  __int64 *v38; // rax
  __int64 v39; // rcx
  _QWORD *v40; // rax
  __int64 v41; // rsi
  _OWORD *v42; // rdi
  int v43; // eax
  __int64 v44; // rdi
  _QWORD v45[3]; // [rsp+30h] [rbp-F8h] BYREF
  void *Src; // [rsp+48h] [rbp-E0h] BYREF
  __int64 v47; // [rsp+50h] [rbp-D8h]
  _QWORD v48[2]; // [rsp+60h] [rbp-C8h] BYREF
  __int128 v49; // [rsp+70h] [rbp-B8h]
  __int128 v50; // [rsp+80h] [rbp-A8h]
  __m256i UnicodeString; // [rsp+90h] [rbp-98h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-78h]
  __int128 v53; // [rsp+C0h] [rbp-68h] BYREF
  volatile void *Address; // [rsp+D0h] [rbp-58h]
  __int64 v55; // [rsp+D8h] [rbp-50h]
  unsigned int MultiByteString; // [rsp+130h] [rbp+8h] BYREF
  int v57; // [rsp+138h] [rbp+10h] BYREF
  __int64 v58; // [rsp+140h] [rbp+18h]

  Src = 0;
  v57 = 0;
  v58 = 0;
  v47 = 0;
  v45[0] = 0;
  v49 = 0;
  *(_OWORD *)UnicodeString.m256i_i8 = 0;
  v52 = 0;
  v48[0] = a1;
  v48[1] = a2;
  *((_DWORD *)a3 + 3) = 0;
  *((_DWORD *)a3 + 11) = 0;
  v50 = *a3;
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
      v58 = v12;
      LOBYTE(a2) = -1;
      v13 = HMValidateHandleWithDescriptor(v12, a2);
      v14 = v13;
      if ( !v13
        || *((_DWORD *)a3 + 2) == 576 && *(_BYTE *)(_HMPheFromObject(v13) + 24) != 20
        || ((*((_DWORD *)a3 + 2) - 281) & 0xFFFFFFFD) == 0 && *(_BYTE *)(_HMPheFromObject(v14) + 24) != 21 )
      {
        return 0;
      }
      CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread();
      if ( CurrentThreadWin32Thread )
        v24 = *CurrentThreadWin32Thread;
      else
        v24 = 0;
      v47 = *(_QWORD *)(v24 + 728);
      v25 = (__int64 *)PsGetCurrentThreadWin32Thread();
      if ( v25 )
        v26 = *v25;
      else
        v26 = 0;
      v45[0] = *(_QWORD *)(v26 + 736);
      v27 = (__int64 *)PsGetCurrentThreadWin32Thread();
      if ( v27 )
        v28 = *v27;
      else
        v28 = 0;
      *(_QWORD *)(v28 + 728) = v12;
      v29 = (__int64 *)PsGetCurrentThreadWin32Thread();
      if ( v29 )
        v30 = *v29;
      else
        v30 = 0;
      *(_QWORD *)(v30 + 736) = v11;
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
    UserSessionState = W32GetUserSessionState(v18, v17);
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
    else if ( !(unsigned int)ConvertToAndFromWideChar(
                               v16,
                               (unsigned __int16 *)&UnicodeString,
                               BytesInUnicodeString,
                               (char *)&MultiByteString,
                               4u,
                               0) )
    {
      UnicodeString.m256i_i64[0] = 0;
      goto LABEL_29;
    }
    if ( (**(_DWORD **)(W32GetUserSessionState(v22, v21) + 19704) & 2) != 0 )
    {
      if ( (MultiByteString & 0xFF00) != 0 )
        UnicodeString.m256i_i64[0] = ((unsigned __int64)(unsigned __int16)MultiByteString >> 8)
                                   | (((unsigned __int8)MultiByteString
                                     | ((unsigned __int64)UnicodeString.m256i_u16[1] << 8)) << 8);
      else
        UnicodeString.m256i_i64[0] = (unsigned __int8)MultiByteString;
    }
    else
    {
      UnicodeString.m256i_i64[0] = MultiByteString;
    }
  }
LABEL_29:
  *(_QWORD *)&v49 = a4;
  *((_QWORD *)&v49 + 1) = a5;
  LODWORD(v52) = *a7;
  v31 = (*(_DWORD *)(PsGetCurrentThreadWin32Thread() + 24) >> 2) & 3;
  v32 = 1;
  if ( v31 )
  {
    v33 = (__int64 *)PsGetCurrentThreadWin32Thread();
    if ( v33 )
      v36 = *v33;
    else
      v36 = 0;
    v32 = *(_BYTE *)(v36 + 1708) != 1;
    UserSessionSwitchLeaveCrit(v36, v34, v35);
  }
  EtwTraceBeginCallback(47);
  v37 = KeUserModeCallback(47, v48, 88, &Src, &v57);
  EtwTraceEndCallback(47);
  if ( v31 )
  {
    if ( v31 == 1 )
      EnterSharedCrit(0, v32);
    else
      EnterCrit(0, v32);
  }
  if ( v9 == 283 || v9 == 576 || v9 == 281 )
  {
    v38 = (__int64 *)PsGetCurrentThreadWin32Thread();
    if ( v38 )
      v39 = *v38;
    else
      v39 = 0;
    *(_QWORD *)(v39 + 728) = v47;
    v40 = (_QWORD *)PsGetCurrentThreadWin32Thread();
    if ( v40 )
      v40 = (_QWORD *)*v40;
    v40[92] = v45[0];
  }
  if ( v37 < 0 || v57 != 24 )
    return 0;
  v45[0] = 0;
  RtlCopyFromUser(v45, Src, 8u);
  v41 = v45[0];
  v55 = v45[0];
  v53 = 0;
  Address = 0;
  RtlCopyFromUser(&v53, Src, 0x18u);
  v42 = Address;
  ProbeForRead(Address, 0x38u, 4u);
  *a3 = *v42;
  a3[1] = v42[1];
  a3[2] = v42[2];
  *a7 ^= (*((_DWORD *)v42 + 12) ^ *a7) & 0x10;
  if ( ((*((_DWORD *)a3 + 2) - 258) & 0xFFFFFFFB) == 0 && v10 )
  {
    if ( UnicodeString.m256i_i64[0] == *((_QWORD *)a3 + 2) )
      *((_QWORD *)a3 + 2) = v11;
    else
      RtlMBMessageWParamCharToWCS();
  }
  v43 = *((_DWORD *)a3 + 2);
  if ( v43 == 283 || v43 == 576 || v43 == 281 )
  {
    *((_DWORD *)a3 + 2) = v9;
    *((_QWORD *)a3 + 2) = v11;
    *((_QWORD *)a3 + 3) = v58;
  }
  else if ( v11 == 1 )
  {
    v44 = v58;
    if ( v9 == 576 )
      FreeTouchInputInfo(v58, 1);
    if ( ((v9 - 281) & 0xFFFFFFFD) == 0 )
      FreeGestureInfo(v44, 1);
  }
  return v41;
}

```

## disassembly

```asm
0x1400c1d20  mov     r11, rsp
0x1400c1d23  push    rbx
0x1400c1d24  push    rsi
0x1400c1d25  push    rdi
0x1400c1d26  push    r12
0x1400c1d28  push    r13
0x1400c1d2a  push    r14
0x1400c1d2c  push    r15
0x1400c1d2e  sub     rsp, 0F0h
0x1400c1d35  mov     rsi, r9
0x1400c1d38  mov     rbx, r8
0x1400c1d3b  xor     r8d, r8d
0x1400c1d3e  mov     [rsp+128h+Src], r8
0x1400c1d43  mov     [r11+10h], r8d
0x1400c1d47  mov     [rsp+128h+arg_10], r8
0x1400c1d4f  mov     [rsp+128h+var_D8], r8
0x1400c1d54  mov     [rsp+128h+var_F8], r8
0x1400c1d59  xorps   xmm0, xmm0
0x1400c1d5c  xor     eax, eax
0x1400c1d5e  movups  [rsp+128h+var_C8], xmm0
0x1400c1d63  movups  [rsp+128h+var_B8], xmm0
0x1400c1d68  movups  xmmword ptr [rsp+128h+UnicodeString], xmm0
0x1400c1d70  mov     [r11-78h], rax
0x1400c1d74  mov     dword ptr [rsp+128h+var_C8], ecx
0x1400c1d78  mov     qword ptr [rsp+128h+var_C8+8], rdx
0x1400c1d7d  mov     [rbx+0Ch], eax
0x1400c1d80  mov     [rbx+2Ch], eax
0x1400c1d83  movups  xmm0, xmmword ptr [rbx]
0x1400c1d86  movaps  [rsp+128h+var_A8], xmm0
0x1400c1d8e  movzx   eax, word ptr [rbx+10h]
0x1400c1d92  mov     [rsp+128h+UnicodeString], ax
0x1400c1d9a  movzx   eax, word ptr [rbx+12h]
0x1400c1d9e  mov     [rsp+128h+UnicodeString+2], ax
0x1400c1da6  movups  xmm0, xmmword ptr [rbx+14h]
0x1400c1daa  movups  xmmword ptr [rsp+128h+UnicodeString+4], xmm0
0x1400c1db2  movups  xmm1, xmmword ptr [rbx+20h]
0x1400c1db6  movups  [rsp+128h+var_88], xmm1
0x1400c1dbe  mov     r14d, [rbx+8]
0x1400c1dc2  lea     eax, [r14-102h]
0x1400c1dc9  mov     r13d, dword ptr [rsp+128h+arg_28]
0x1400c1dd1  test    eax, 0FFFFFFFBh
0x1400c1dd6  jz      short loc_1400C1E12
0x1400c1dd8  cmp     r14d, 11Bh
0x1400c1ddf  jnz     loc_1400C20E2
0x1400c1de5  mov     r12, [rbx+10h]
0x1400c1de9  mov     r15, [rbx+18h]
0x1400c1ded  mov     [rsp+128h+arg_10], r15
0x1400c1df5  mov     dl, 0FFh
0x1400c1df7  mov     rcx, r15
0x1400c1dfa  call    HMValidateHandleWithDescriptor
0x1400c1dff  mov     rdi, rax
0x1400c1e02  test    rax, rax
0x1400c1e05  jnz     loc_1400C1EE1
0x1400c1e0b  xor     eax, eax
0x1400c1e0d  jmp     loc_1400C212D
0x1400c1e12  test    r13d, r13d
0x1400c1e15  jz      short loc_1400C1DD8
0x1400c1e17  mov     r12, [rbx+10h]
0x1400c1e1b  mov     [rsp+128h+MultiByteString], r8d
0x1400c1e23  cmp     r14d, 120h
0x1400c1e2a  jz      short loc_1400C1E58
0x1400c1e2c  cmp     r14d, 106h
0x1400c1e33  ja      loc_1400C20BB
0x1400c1e39  jz      short loc_1400C1E58
0x1400c1e3b  mov     eax, r14d
0x1400c1e3e  sub     eax, 2Fh ; '/'
0x1400c1e41  jz      short loc_1400C1E58
0x1400c1e43  sub     eax, 9Dh
0x1400c1e48  jz      short loc_1400C1E58
0x1400c1e4a  sub     eax, 36h ; '6'
0x1400c1e4d  jz      short loc_1400C1E58
0x1400c1e4f  cmp     eax, 1
0x1400c1e52  jnz     loc_1400C1F9E
0x1400c1e58  call    ?THREAD_CODEPAGE@@YAGXZ; THREAD_CODEPAGE(void)
0x1400c1e5d  movzx   edi, ax
0x1400c1e60  mov     [rsp+128h+MultiByteString], 0
0x1400c1e6b  call    cs:__imp_W32GetUserSessionState
0x1400c1e72  nop     dword ptr [rax+rax+00h]
0x1400c1e77  mov     rcx, [rax+4CF8h]
0x1400c1e7e  mov     edx, [rcx]
0x1400c1e80  test    dl, 2
0x1400c1e83  mov     edx, 2
0x1400c1e88  mov     r15d, 4
0x1400c1e8e  cmovz   edx, r15d
0x1400c1e92  mov     rcx, cs:__imp_NlsAnsiCodePage
0x1400c1e99  cmp     di, [rcx]
0x1400c1e9c  jnz     loc_1400C2321
0x1400c1ea2  mov     [rsp+128h+BytesInUnicodeString], edx; BytesInUnicodeString
0x1400c1ea6  lea     r9, [rsp+128h+UnicodeString]; UnicodeString
0x1400c1eae  xor     r8d, r8d; BytesInMultiByteString
0x1400c1eb1  mov     edx, r15d; MaxBytesInMultiByteString
0x1400c1eb4  lea     rcx, [rsp+128h+MultiByteString]; MultiByteString
0x1400c1ebc  call    cs:__imp_RtlUnicodeToMultiByteN
0x1400c1ec3  nop     dword ptr [rax+rax+00h]
0x1400c1ec8  test    eax, eax
0x1400c1eca  jns     loc_1400C2366
0x1400c1ed0  mov     qword ptr [rsp+128h+UnicodeString], 0
0x1400c1edc  jmp     loc_1400C1F9E
0x1400c1ee1  cmp     dword ptr [rbx+8], 240h
0x1400c1ee8  jz      loc_1400C2283
0x1400c1eee  mov     ecx, [rbx+8]
0x1400c1ef1  sub     ecx, 119h
0x1400c1ef7  test    ecx, 0FFFFFFFDh
0x1400c1efd  jnz     short loc_1400C1F18
0x1400c1eff  mov     rcx, rdi
0x1400c1f02  call    cs:__imp__HMPheFromObject
0x1400c1f09  nop     dword ptr [rax+rax+00h]
0x1400c1f0e  cmp     byte ptr [rax+18h], 15h
0x1400c1f12  jnz     loc_1400C1E0B
0x1400c1f18  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c1f1f  nop     dword ptr [rax+rax+00h]
0x1400c1f24  test    rax, rax
0x1400c1f27  jz      loc_1400C22CA
0x1400c1f2d  mov     rcx, [rax]
0x1400c1f30  mov     rax, [rcx+2D8h]
0x1400c1f37  mov     [rsp+128h+var_D8], rax
0x1400c1f3c  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c1f43  nop     dword ptr [rax+rax+00h]
0x1400c1f48  test    rax, rax
0x1400c1f4b  jz      loc_1400C22D1
0x1400c1f51  mov     rcx, [rax]
0x1400c1f54  mov     rax, [rcx+2E0h]
0x1400c1f5b  mov     [rsp+128h+var_F8], rax
0x1400c1f60  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c1f67  nop     dword ptr [rax+rax+00h]
0x1400c1f6c  test    rax, rax
0x1400c1f6f  jz      loc_1400C22D8
0x1400c1f75  mov     rcx, [rax]
0x1400c1f78  mov     [rcx+2D8h], r15
0x1400c1f7f  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c1f86  nop     dword ptr [rax+rax+00h]
0x1400c1f8b  test    rax, rax
0x1400c1f8e  jz      loc_1400C22DF
0x1400c1f94  mov     rcx, [rax]
0x1400c1f97  mov     [rcx+2E0h], r12
0x1400c1f9e  mov     qword ptr [rsp+128h+var_B8], rsi
0x1400c1fa3  mov     rax, [rsp+128h+arg_20]
0x1400c1fab  mov     qword ptr [rsp+128h+var_B8+8], rax
0x1400c1fb0  mov     rax, [rsp+128h+arg_30]
0x1400c1fb8  mov     eax, [rax]
0x1400c1fba  mov     dword ptr [rsp+128h+var_78], eax
0x1400c1fc1  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c1fc8  nop     dword ptr [rax+rax+00h]
0x1400c1fcd  mov     edi, [rax+18h]
0x1400c1fd0  shr     edi, 2
0x1400c1fd3  and     edi, 3
0x1400c1fd6  mov     esi, 1
0x1400c1fdb  jz      short loc_1400C200E
0x1400c1fdd  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c1fe4  nop     dword ptr [rax+rax+00h]
0x1400c1fe9  test    rax, rax
0x1400c1fec  jz      loc_1400C227C
0x1400c1ff2  mov     rcx, [rax]
0x1400c1ff5  xor     esi, esi
0x1400c1ff7  cmp     byte ptr [rcx+6ACh], 1
0x1400c1ffe  setnz   sil
0x1400c2002  call    cs:__imp_UserSessionSwitchLeaveCrit
0x1400c2009  nop     dword ptr [rax+rax+00h]
0x1400c200e  mov     ecx, 2Fh ; '/'
0x1400c2013  call    cs:__imp_EtwTraceBeginCallback
0x1400c201a  nop     dword ptr [rax+rax+00h]
0x1400c201f  lea     rax, [rsp+128h+arg_8]
0x1400c2027  mov     qword ptr [rsp+128h+BytesInUnicodeString], rax
0x1400c202c  lea     r9, [rsp+128h+Src]
0x1400c2031  mov     r8d, 58h ; 'X'
0x1400c2037  lea     rdx, [rsp+128h+var_C8]
0x1400c203c  mov     ecx, 2Fh ; '/'
0x1400c2041  call    cs:__imp_KeUserModeCallback
0x1400c2048  nop     dword ptr [rax+rax+00h]
0x1400c204d  mov     r15d, eax
0x1400c2050  mov     ecx, 2Fh ; '/'
0x1400c2055  call    cs:__imp_EtwTraceEndCallback
0x1400c205c  nop     dword ptr [rax+rax+00h]
0x1400c2061  test    edi, edi
0x1400c2063  jz      short loc_1400C207E
0x1400c2065  mov     edx, esi
0x1400c2067  xor     ecx, ecx
0x1400c2069  cmp     edi, 1
0x1400c206c  jz      loc_1400C2104
0x1400c2072  call    cs:__imp_EnterCrit
0x1400c2079  nop     dword ptr [rax+rax+00h]
0x1400c207e  cmp     r14d, 11Bh
0x1400c2085  jnz     short loc_1400C20A3
0x1400c2087  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c208e  nop     dword ptr [rax+rax+00h]
0x1400c2093  test    rax, rax
0x1400c2096  jnz     loc_1400C22A1
0x1400c209c  xor     ecx, ecx
0x1400c209e  jmp     loc_1400C22A4
0x1400c20a3  cmp     r14d, 240h
0x1400c20aa  jz      short loc_1400C2087
0x1400c20ac  cmp     r14d, 119h
0x1400c20b3  jnz     loc_1400C2150
0x1400c20b9  jmp     short loc_1400C2087
0x1400c20bb  mov     eax, r14d
0x1400c20be  sub     eax, 107h
0x1400c20c3  jz      loc_1400C1E58
0x1400c20c9  sub     eax, 8
0x1400c20cc  jz      loc_1400C1E58
0x1400c20d2  cmp     eax, 177h
0x1400c20d7  jnz     loc_1400C1F9E
0x1400c20dd  jmp     loc_1400C1E58
0x1400c20e2  cmp     r14d, 240h
0x1400c20e9  jz      loc_1400C1DE5
0x1400c20ef  mov     r12, r8
0x1400c20f2  cmp     r14d, 119h
0x1400c20f9  jnz     loc_1400C1F9E
0x1400c20ff  jmp     loc_1400C1DE5
0x1400c2104  call    cs:__imp_EnterSharedCrit
0x1400c210b  nop     dword ptr [rax+rax+00h]
0x1400c2110  jmp     loc_1400C207E
0x1400c2115  cmp     eax, 119h
0x1400c211a  jz      loc_1400C2235
0x1400c2120  cmp     r12, 1
0x1400c2124  jz      loc_1400C22E6
0x1400c212a  mov     rax, rsi
0x1400c212d  add     rsp, 0F0h
0x1400c2134  pop     r15
0x1400c2136  pop     r14
0x1400c2138  pop     r13
0x1400c213a  pop     r12
0x1400c213c  pop     rdi
0x1400c213d  pop     rsi
0x1400c213e  pop     rbx
0x1400c213f  retn
0x1400c2141  mov     rax, [rax]
0x1400c2144  mov     rcx, [rsp+128h+var_F8]
0x1400c2149  mov     [rax+2E0h], rcx
0x1400c2150  test    r15d, r15d
0x1400c2153  js      loc_1400C1E0B
0x1400c2159  cmp     [rsp+128h+arg_8], 18h
0x1400c2161  jnz     loc_1400C1E0B
0x1400c2167  mov     [rsp+128h+var_F8], 0
0x1400c2170  mov     r8d, 8; Size
0x1400c2176  mov     rdx, [rsp+128h+Src]; Src
0x1400c217b  lea     rcx, [rsp+128h+var_F8]; void *
0x1400c2180  call    RtlCopyFromUser
0x1400c2185  mov     rsi, [rsp+128h+var_F8]
0x1400c218a  mov     [rsp+128h+var_50], rsi
0x1400c2192  jmp     short loc_1400C2199
0x1400c2194  jmp     loc_1400C1E0B
0x1400c2199  xorps   xmm0, xmm0
0x1400c219c  xor     eax, eax
0x1400c219e  movups  [rsp+128h+var_68], xmm0
0x1400c21a6  mov     [rsp+128h+Address], rax
0x1400c21ae  mov     r8d, 18h; Size
0x1400c21b4  mov     rdx, [rsp+128h+Src]; Src
0x1400c21b9  lea     rcx, [rsp+128h+var_68]; void *
0x1400c21c1  call    RtlCopyFromUser
0x1400c21c6  mov     rdi, [rsp+128h+Address]
0x1400c21ce  mov     edx, 38h ; '8'; Length
0x1400c21d3  mov     r8d, 4; Alignment
0x1400c21d9  mov     rcx, rdi; Address
0x1400c21dc  call    cs:__imp_ProbeForRead
0x1400c21e3  nop     dword ptr [rax+rax+00h]
0x1400c21e8  movups  xmm0, xmmword ptr [rdi]
0x1400c21eb  movups  xmmword ptr [rbx], xmm0
0x1400c21ee  movups  xmm1, xmmword ptr [rdi+10h]
0x1400c21f2  movups  xmmword ptr [rbx+10h], xmm1
0x1400c21f6  movups  xmm0, xmmword ptr [rdi+20h]
0x1400c21fa  movups  xmmword ptr [rbx+20h], xmm0
0x1400c21fe  mov     rdx, [rsp+128h+arg_30]
0x1400c2206  mov     eax, [rdx]
0x1400c2208  mov     ecx, eax
0x1400c220a  xor     ecx, [rdi+30h]
0x1400c220d  and     ecx, 10h
0x1400c2210  xor     ecx, eax
0x1400c2212  mov     [rdx], ecx
0x1400c2214  jmp     short loc_1400C221B
0x1400c2216  jmp     loc_1400C1E0B
0x1400c221b  mov     ecx, [rbx+8]
0x1400c221e  lea     eax, [rcx-102h]
0x1400c2224  test    eax, 0FFFFFFFBh
0x1400c2229  jz      short loc_1400C225A
0x1400c222b  mov     eax, [rbx+8]
0x1400c222e  cmp     eax, 11Bh
0x1400c2233  jnz     short loc_1400C224E
0x1400c2235  mov     [rbx+8], r14d
0x1400c2239  mov     [rbx+10h], r12
0x1400c223d  mov     rdi, [rsp+128h+arg_10]
0x1400c2245  mov     [rbx+18h], rdi
0x1400c2249  jmp     loc_1400C212A
0x1400c224e  cmp     eax, 240h
0x1400c2253  jz      short loc_1400C2235
0x1400c2255  jmp     loc_1400C2115
0x1400c225a  test    r13d, r13d
0x1400c225d  jz      short loc_1400C222B
0x1400c225f  lea     rdx, [rbx+10h]
0x1400c2263  mov     rax, [rdx]
0x1400c2266  cmp     qword ptr [rsp+128h+UnicodeString], rax
0x1400c226e  jnz     short loc_1400C2275
0x1400c2270  mov     [rdx], r12
0x1400c2273  jmp     short loc_1400C222B
0x1400c2275  call    RtlMBMessageWParamCharToWCS
0x1400c227a  jmp     short loc_1400C222B
0x1400c227c  xor     ecx, ecx
0x1400c227e  jmp     loc_1400C1FF5
0x1400c2283  mov     rcx, rdi
0x1400c2286  call    cs:__imp__HMPheFromObject
0x1400c228d  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```

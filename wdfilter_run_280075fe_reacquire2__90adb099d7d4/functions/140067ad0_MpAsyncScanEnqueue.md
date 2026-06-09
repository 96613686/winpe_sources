# MpAsyncScanEnqueue

- ea: `0x140067ad0`
- end: `0x1400684e0`
- name: `MpAsyncScanEnqueue`
- size: `2576`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140055eb0`

## callees

- `0x1400018a4`
- `0x140003460`
- `0x140003d20`
- `0x140004530`
- `0x1400049dc`
- `0x1400054f0`
- `0x1400098d0`
- `0x140009a0c`
- `0x1400118d0`
- `0x140030060`
- `0x140055d50`
- `0x140067ad0`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140067bd3`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140067bd3`
- `ntoskrnl!KeReadStateEvent` at `0x140067b6b`
- `ntoskrnl!KeReadStateEvent` at `0x140067b6b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400680bd`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140068137`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400680bd`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140068137`
- `ntoskrnl!ExFreePoolWithTag` at `0x140067e81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140067e81`
- `ntoskrnl!ExAcquireFastMutex` at `0x140067c14`
- `ntoskrnl!ExAcquireFastMutex` at `0x140067c14`
- `ntoskrnl!KeReleaseSemaphore` at `0x14006801e`
- `ntoskrnl!KeReleaseSemaphore` at `0x14006801e`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140068183`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140068183`
- `ntoskrnl!KeBugCheck` at `0x14006828a`
- `ntoskrnl!KeBugCheck` at `0x14006828a`
- `ntoskrnl!ObfDereferenceObject` at `0x140067e25`
- `ntoskrnl!ObfDereferenceObject` at `0x140067e25`
- `ntoskrnl!ExReleaseFastMutex` at `0x140067d7f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140068236`
- `ntoskrnl!ExReleaseFastMutex` at `0x140067d7f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140068236`
- `FLTMGR!FltReleaseContext` at `0x140067e4d`
- `FLTMGR!FltReleaseContext` at `0x1400684cf`
- `FLTMGR!FltReleaseContext` at `0x140067e4d`
- `FLTMGR!FltReleaseContext` at `0x1400684cf`

## string_xrefs

- `0x1400681c0`: `OnOpen`
- `0x1400683d6`: `OnOpen`
- `0x140068478`: `OnOpen`

## pseudocode

```c
__int64 __fastcall MpAsyncScanEnqueue(_QWORD *Entry)
{
  _QWORD *v1; // r14
  __int64 v2; // rbx
  __int64 v3; // r12
  char v4; // r13
  unsigned __int64 v5; // rax
  WCHAR *v6; // r15
  WCHAR *v7; // rbx
  unsigned __int64 v8; // rsi
  __int64 v9; // rdi
  unsigned __int8 v10; // al
  char *v11; // rax
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 v14; // r9
  _QWORD *v15; // r10
  _QWORD *v16; // rax
  PVOID *v17; // rcx
  char v18; // bl
  __int64 v20; // rcx
  __int64 v21; // rdx
  void *v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  __int64 v25; // rcx
  void *v26; // rcx
  int v27; // r10d
  unsigned __int64 v28; // r13
  _QWORD *v29; // rcx
  __int64 v30; // r15
  USHORT v31; // si
  __int64 v32; // r14
  bool v33; // al
  const wchar_t *v34; // r8
  const char *v35; // r10
  __int64 v36; // r8
  unsigned int Value; // eax
  __int64 v38; // r9
  __int64 v39; // r8
  const wchar_t *v40; // r8
  const char *v41; // r10
  const wchar_t *v42; // r8
  const char *v43; // r10
  char *i; // [rsp+58h] [rbp-A0h]
  WCHAR *v45; // [rsp+60h] [rbp-98h]
  __int64 v47; // [rsp+78h] [rbp-80h]
  const UNICODE_STRING *String2; // [rsp+80h] [rbp-78h]
  _QWORD *v49; // [rsp+A0h] [rbp-58h] BYREF
  UNICODE_STRING v50; // [rsp+A8h] [rbp-50h] BYREF
  UNICODE_STRING String1; // [rsp+B8h] [rbp-40h] BYREF

  v1 = Entry;
  v49 = Entry;
  v2 = 0;
  i = 0;
  v3 = Entry[6];
  v47 = v3;
  String2 = (const UNICODE_STRING *)(*(_QWORD *)(Entry[8] + 8LL) + 24LL);
  if ( (*(_DWORD *)(MpData + 868) & 0x2000) != 0 )
  {
    v4 = 0;
  }
  else
  {
    v4 = 1;
    *((_DWORD *)Entry + 10) |= 2u;
  }
  if ( !MpAsyncScanData )
    return 3221225473LL;
  if ( !KeReadStateEvent((PRKEVENT)MpAsyncScanData + 6) )
  {
    v5 = *(unsigned __int16 *)(v3 + 522);
    v6 = (WCHAR *)(v3 + 820);
    if ( !(_WORD)v5 )
      v6 = 0;
    v45 = v6;
    if ( v4 )
    {
      if ( v6 )
      {
        v7 = v6;
        v8 = (unsigned __int64)&v6[v5 >> 1];
        v9 = 314159;
        if ( (unsigned __int64)v6 < v8 )
        {
          do
          {
            v10 = RtlUpcaseUnicodeChar(*v7++);
            v9 = 37 * (v10 + 37 * v9);
          }
          while ( (unsigned __int64)v7 < v8 );
        }
        v2 = 0;
      }
      else
      {
        v9 = *(unsigned __int8 *)(v3 + 391)
           + 37
           * (*(unsigned __int8 *)(v3 + 390)
            + 37
            * (*(unsigned __int8 *)(v3 + 389)
             + 37
             * (*(unsigned __int8 *)(v3 + 388)
              + 37
              * (*(unsigned __int8 *)(v3 + 387)
               + 37
               * (*(unsigned __int8 *)(v3 + 386)
                + 37 * (*(unsigned __int8 *)(v3 + 385) + 37 * (*(unsigned __int8 *)(v3 + 384) + 11623883LL)))))));
      }
    }
    else
    {
      v9 = 0;
    }
    v1[4] = v9;
    ExAcquireFastMutex((PFAST_MUTEX)((char *)MpAsyncScanData + 200));
    if ( v4 )
    {
      v11 = (char *)MpAsyncScanData + 1296;
      for ( i = (char *)MpAsyncScanData + 1296; ; v11 = i )
      {
        v12 = -1LL << (v11[4] & 0x1F);
        v13 = v9 & v12;
        if ( v2 )
          goto LABEL_15;
        v27 = *((_DWORD *)v11 + 1) >> 5;
        if ( v27 )
        {
          v2 = *((_QWORD *)i + 1)
             + 8
             * ((v27 - 1)
              & (442596621 * (unsigned __int8)v13
               - 877075889
               + ((v9 & (unsigned __int64)v12) >> 56)
               + 37
               * ((unsigned __int8)((v9 & (unsigned __int64)v12) >> 48)
                + 37
                * ((unsigned __int8)((unsigned __int16)((v9 & (unsigned __int64)v12) >> 32) >> 8)
                 + 37
                 * ((unsigned __int8)((v9 & (unsigned __int64)v12) >> 32)
                  + 37
                  * ((((unsigned int)v9 & (unsigned int)v12) >> 24)
                   + 37
                   * ((unsigned __int8)(((unsigned int)v9 & (unsigned int)v12) >> 16)
                    + 37 * (unsigned __int8)((unsigned __int16)(v9 & v12) >> 8))))))));
LABEL_15:
          while ( 1 )
          {
            v2 = *(_QWORD *)v2;
            if ( (v2 & 1) != 0 )
              break;
            if ( v13 == (v12 & *(_QWORD *)(v2 + 8)) )
              goto LABEL_17;
          }
        }
        v2 = 0;
LABEL_17:
        v3 = v47;
        if ( !v2 )
          break;
        v30 = *(_QWORD *)(v47 + 384);
        v31 = *(_WORD *)(v47 + 522);
        String1 = 0;
        v50 = 0;
        v32 = *(_QWORD *)(v2 + 24);
        if ( !RtlCompareUnicodeString((PCUNICODE_STRING)(*(_QWORD *)(*(_QWORD *)(v2 + 40) + 8LL) + 24LL), String2, 1u) )
        {
          if ( v31 && v31 == *(_WORD *)(v32 + 522) )
          {
            String1.Length = v31;
            String1.MaximumLength = v31;
            String1.Buffer = (PWSTR)(v32 + 820);
            v50.Length = v31;
            v50.MaximumLength = v31;
            v50.Buffer = v45;
            if ( RtlCompareUnicodeString(&String1, &v50, 1u) )
              v33 = v30 == *(_QWORD *)(v32 + 384);
            else
              v33 = 1;
            if ( v33 )
              break;
          }
          else if ( v30 == *(_QWORD *)(v32 + 384) )
          {
            break;
          }
        }
      }
      v1 = Entry;
      v6 = v45;
    }
    if ( v2 )
    {
      v20 = *(_QWORD *)(v2 + 24);
      v21 = v1[6];
      if ( *(_QWORD *)(v21 + 384) == *(_QWORD *)(v20 + 384)
        && *(_DWORD *)(v20 + 24) == 3
        && (*(_DWORD *)(v20 + 28) & 0x20) != 0
        && (*(_DWORD *)(v21 + 24) != 3 || (*(_DWORD *)(v21 + 28) & 0x20) == 0) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          v42 = L"n/a";
          if ( v6 )
            v42 = v6;
          v43 = "OnClose";
          if ( *(_DWORD *)(v3 + 24) != 4 )
            v43 = "OnOpen";
          WPP_SF_iisS(
            WPP_GLOBAL_Control->AttachedDevice,
            19,
            (_DWORD)v42,
            *(_QWORD *)(v3 + 384),
            *(_QWORD *)(v3 + 392),
            (__int64)v43,
            (__int64)v42);
        }
        MpCleanupScanRequestContext(&v49);
      }
      else
      {
        *(_BYTE *)(v3 + 818) = 1;
        *(_WORD *)(v3 + 816) = *((_WORD *)MpAsyncScanData + 128);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          v34 = L"n/a";
          if ( v6 )
            v34 = v6;
          v35 = "OnClose";
          if ( *(_DWORD *)(v3 + 24) != 4 )
            v35 = "OnOpen";
          WPP_SF_iisS(
            WPP_GLOBAL_Control->AttachedDevice,
            18,
            (_DWORD)v34,
            *(_QWORD *)(v3 + 384),
            *(_QWORD *)(v3 + 392),
            (__int64)v35,
            (__int64)v34);
        }
        v22 = *(void **)(v2 + 64);
        if ( v22 )
        {
          ObfDereferenceObject(v22);
          if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
          {
            if ( KdRefreshDebuggerNotPresent() )
              KeBugCheck(1u);
            __debugbreak();
          }
        }
        v23 = *(void **)(v2 + 40);
        if ( v23 )
          FltReleaseContext(v23);
        v24 = *(void **)(v2 + 48);
        if ( v24 )
          FltReleaseContext(v24);
        v25 = *(_QWORD *)(v2 + 56);
        if ( v25 )
          MpReleaseProcessContext(v25);
        v26 = *(void **)(v2 + 24);
        if ( v26 )
          ExFreePoolWithTag(v26, 0x7366504Du);
        *(_DWORD *)(v2 + 16) = *((_DWORD *)v1 + 10);
        *(_QWORD *)(v2 + 64) = v1[11];
        *(_QWORD *)(v2 + 40) = v1[8];
        *(_QWORD *)(v2 + 48) = v1[9];
        *(_QWORD *)(v2 + 56) = v1[10];
        *(_QWORD *)(v2 + 24) = v1[6];
        *(_DWORD *)(v2 + 32) = *((_DWORD *)v1 + 14);
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(MpData + 2240), v1);
      }
      v18 = 0;
      goto LABEL_27;
    }
    v14 = *((unsigned int *)MpAsyncScanData + 64);
    if ( (unsigned int)v14 < *(_DWORD *)(MpData + 4140) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        _mm_lfence();
        v40 = L"n/a";
        if ( v6 )
          v40 = v6;
        v41 = "OnClose";
        if ( *(_DWORD *)(v3 + 24) != 4 )
          v41 = "OnOpen";
        WPP_SF_LiisiS(
          WPP_GLOBAL_Control->AttachedDevice,
          (unsigned int)"OnOpen",
          (_DWORD)v40,
          v14,
          *(_QWORD *)(v3 + 384),
          *(_QWORD *)(v3 + 392),
          (__int64)v41,
          v9,
          (__int64)v40);
        v1 = v49;
      }
      v1[13] = 3735936477LL;
      v1[14] = 3735945215LL;
      *(_BYTE *)(v3 + 818) = 1;
      v15 = MpAsyncScanData;
      *(_WORD *)(v3 + 816) = *((_WORD *)MpAsyncScanData + 128);
      v16 = v1 + 1;
      v17 = (PVOID *)v15[1];
      if ( *v17 != v15 )
        __fastfail(3u);
      *v16 = v15;
      v1[2] = v17;
      *v17 = v16;
      v15[1] = v16;
      if ( v4 )
      {
        v28 = v1[4] & (-1LL << (*((_DWORD *)i + 1) & 0x1F));
        v29 = (_QWORD *)(*((_QWORD *)i + 1)
                       + 8
                       * (((*((_DWORD *)i + 1) >> 5) - 1)
                        & (442596621 * (unsigned __int8)v28
                         + HIBYTE(v28)
                         + 37
                         * (BYTE6(v28)
                          + 37
                          * (BYTE5(v28)
                           + 37 * (BYTE4(v28) + 37 * (BYTE3(v28) + 37 * (BYTE2(v28) + 37 * (unsigned int)BYTE1(v28))))))
                         - 877075889)));
        v1[3] = *v29;
        *v29 = v1 + 3;
        ++*(_DWORD *)i;
      }
      ++*((_DWORD *)v15 + 64);
      v18 = 1;
LABEL_27:
      ExReleaseFastMutex((PFAST_MUTEX)((char *)MpAsyncScanData + 200));
      if ( v18 )
        KeReleaseSemaphore((PRKSEMAPHORE)((char *)MpAsyncScanData + 168), 0, 1, 0);
      return 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      _mm_lfence();
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_e14b9b336f94348117623c9565965302_Traceguids, v14);
    }
    ExReleaseFastMutex((PFAST_MUTEX)((char *)MpAsyncScanData + 200));
    if ( (*(_DWORD *)(MpData + 868) & 0x20000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_e14b9b336f94348117623c9565965302_Traceguids);
      Value = MpFcKernelGetValue(291);
      LOBYTE(v38) = 1;
      MpTraceAsyncScanQueueExceeded(*((unsigned int *)MpAsyncScanData + 64), Value, v39, v38);
      MpCleanupScanRequestContext(&v49);
      return 0;
    }
    MpTraceAsyncScanQueueExceeded(*((unsigned int *)MpAsyncScanData + 64), *(unsigned int *)(MpData + 4140), v36, 0);
    return 3221225473LL;
  }
  return 3221226238LL;
}

```

## disassembly

```asm
0x140067ad0  mov     [rsp+arg_8], rbx
0x140067ad5  mov     [rsp+arg_10], rsi
0x140067ada  push    rdi
0x140067adb  push    r12
0x140067add  push    r13
0x140067adf  push    r14
0x140067ae1  push    r15
0x140067ae3  sub     rsp, 0D0h
0x140067aea  mov     rax, cs:__security_cookie
0x140067af1  xor     rax, rsp
0x140067af4  mov     [rsp+0F8h+var_30], rax
0x140067afc  mov     r14, rcx
0x140067aff  mov     [rsp+0F8h+var_88], rcx
0x140067b04  mov     [rsp+0F8h+var_58], rcx
0x140067b0c  xor     ebx, ebx
0x140067b0e  mov     [rsp+0F8h+var_A0], rbx
0x140067b13  mov     r12, [rcx+30h]
0x140067b17  mov     [rsp+0F8h+var_80], r12
0x140067b1c  mov     rax, [rcx+40h]
0x140067b20  mov     rax, [rax+8]
0x140067b24  add     rax, 18h
0x140067b28  mov     [rsp+0F8h+String2], rax
0x140067b30  mov     rax, cs:MpData
0x140067b37  mov     ecx, [rax+364h]
0x140067b3d  bt      ecx, 0Dh
0x140067b41  jb      loc_140068073
0x140067b47  mov     r13b, 1
0x140067b4a  or      dword ptr [r14+28h], 2
0x140067b4f  mov     [rsp+0F8h+var_A8], r13b
0x140067b54  mov     rcx, cs:MpAsyncScanData
0x140067b5b  test    rcx, rcx
0x140067b5e  jz      loc_14006827B
0x140067b64  add     rcx, 90h; Event
0x140067b6b  call    cs:__imp_KeReadStateEvent
0x140067b72  nop     dword ptr [rax+rax+00h]
0x140067b77  test    eax, eax
0x140067b79  jnz     loc_14006829E
0x140067b7f  movzx   eax, word ptr [r12+20Ah]
0x140067b88  lea     r15, [r12+334h]
0x140067b90  test    ax, ax
0x140067b93  cmovz   r15, rbx
0x140067b97  mov     [rsp+0F8h+var_98], r15
0x140067b9c  test    r13b, r13b
0x140067b9f  jz      loc_14006832C
0x140067ba5  test    r15, r15
0x140067ba8  jz      loc_1400682A8
0x140067bae  mov     rbx, r15
0x140067bb1  shr     rax, 1
0x140067bb4  lea     rsi, [r15+rax*2]
0x140067bb8  mov     edi, 4CB2Fh
0x140067bbd  cmp     r15, rsi
0x140067bc0  jnb     short loc_140067C00
0x140067bc2  nop     dword ptr [rax+00h]
0x140067bc6  nop     word ptr [rax+rax+00000000h]
0x140067bd0  movzx   ecx, word ptr [rbx]; SourceCharacter
0x140067bd3  call    cs:__imp_RtlUpcaseUnicodeChar
0x140067bda  nop     dword ptr [rax+rax+00h]
0x140067bdf  movzx   edx, ax
0x140067be2  add     rbx, 2
0x140067be6  imul    rcx, rdi, 25h ; '%'
0x140067bea  movzx   eax, dl
0x140067bed  add     rcx, rax
0x140067bf0  imul    rdi, rcx, 25h ; '%'
0x140067bf4  shr     rdx, 8
0x140067bf8  add     rdi, rdx
0x140067bfb  cmp     rbx, rsi
0x140067bfe  jb      short loc_140067BD0
0x140067c00  xor     ebx, ebx
0x140067c02  mov     [r14+20h], rdi
0x140067c06  mov     rcx, cs:MpAsyncScanData
0x140067c0d  add     rcx, 0C8h; FastMutex
0x140067c14  call    cs:__imp_ExAcquireFastMutex
0x140067c1b  nop     dword ptr [rax+rax+00h]
0x140067c20  test    r13b, r13b
0x140067c23  mov     r13, 0FFFFFFFFFFFFFFFFh
0x140067c2a  jz      loc_140067CC2
0x140067c30  mov     rax, cs:MpAsyncScanData
0x140067c37  add     rax, 510h
0x140067c3d  mov     [rsp+0F8h+var_A0], rax
0x140067c42  mov     r10d, [rax+4]
0x140067c46  mov     ecx, r10d
0x140067c49  and     ecx, 1Fh
0x140067c4c  mov     r9, r13
0x140067c4f  shl     r9, cl
0x140067c52  mov     r8, r9
0x140067c55  and     r8, rdi
0x140067c58  mov     r11, r8
0x140067c5b  shr     r11, 38h
0x140067c5f  mov     rsi, r8
0x140067c62  shr     rsi, 30h
0x140067c66  mov     r14, r8
0x140067c69  shr     r14, 28h
0x140067c6d  mov     r15, r8
0x140067c70  shr     r15, 20h
0x140067c74  mov     r12, r8
0x140067c77  shr     r12, 18h
0x140067c7b  mov     rdx, r8
0x140067c7e  shr     rdx, 10h
0x140067c82  mov     rax, r8
0x140067c85  shr     rax, 8
0x140067c89  test    rbx, rbx
0x140067c8c  jz      loc_140067EE0
0x140067c92  mov     rbx, [rbx]
0x140067c95  test    bl, 1
0x140067c98  jnz     loc_140067FFE
0x140067c9e  mov     rax, [rbx+8]
0x140067ca2  and     rax, r9
0x140067ca5  cmp     r8, rax
0x140067ca8  jnz     short loc_140067C92
0x140067caa  mov     r12, [rsp+0F8h+var_80]
0x140067caf  test    rbx, rbx
0x140067cb2  jnz     loc_14006807B
0x140067cb8  mov     r14, [rsp+0F8h+var_88]
0x140067cbd  mov     r15, [rsp+0F8h+var_98]
0x140067cc2  test    rbx, rbx
0x140067cc5  jnz     loc_140067DC3
0x140067ccb  mov     rax, cs:MpAsyncScanData
0x140067cd2  mov     r9d, [rax+100h]
0x140067cd9  mov     rax, cs:MpData
0x140067ce0  cmp     r9d, [rax+102Ch]
0x140067ce7  jnb     loc_14006820A
0x140067ced  lea     rsi, WPP_GLOBAL_Control
0x140067cf4  mov     rax, cs:WPP_GLOBAL_Control
0x140067cfb  cmp     rax, rsi
0x140067cfe  jz      short loc_140067D0B
0x140067d00  mov     eax, [rax+2Ch]
0x140067d03  test    al, 4
0x140067d05  jnz     loc_1400683C5
0x140067d0b  mov     eax, 0DEADDDDDh
0x140067d10  mov     [r14+68h], rax
0x140067d14  mov     eax, 0DEADFFFFh
0x140067d19  mov     [r14+70h], rax
0x140067d1d  mov     byte ptr [r12+332h], 1
0x140067d26  mov     r10, cs:MpAsyncScanData
0x140067d2d  movzx   eax, word ptr [r10+100h]
0x140067d35  mov     [r12+330h], ax
0x140067d3e  lea     rax, [r14+8]
0x140067d42  mov     rcx, [r10+8]
0x140067d46  cmp     [rcx], r10
0x140067d49  jnz     loc_140068167
0x140067d4f  mov     [rax], r10
0x140067d52  mov     [rax+8], rcx
0x140067d56  mov     [rcx], rax
0x140067d59  mov     [r10+8], rax
0x140067d5d  cmp     [rsp+0F8h+var_A8], 0
0x140067d62  jnz     loc_140067F4D
0x140067d68  inc     dword ptr [r10+100h]
0x140067d6f  mov     bl, 1
0x140067d71  mov     rcx, cs:MpAsyncScanData
0x140067d78  add     rcx, 0C8h; FastMutex
0x140067d7f  call    cs:__imp_ExReleaseFastMutex
0x140067d86  nop     dword ptr [rax+rax+00h]
0x140067d8b  test    bl, bl
0x140067d8d  jnz     loc_140068005
0x140067d93  xor     eax, eax
0x140067d95  mov     rcx, [rsp+0F8h+var_30]
0x140067d9d  xor     rcx, rsp; StackCookie
0x140067da0  call    __security_check_cookie
0x140067da5  lea     r11, [rsp+0F8h+var_28]
0x140067dad  mov     rbx, [r11+38h]
0x140067db1  mov     rsi, [r11+40h]
0x140067db5  mov     rsp, r11
0x140067db8  pop     r15
0x140067dba  pop     r14
0x140067dbc  pop     r13
0x140067dbe  pop     r12
0x140067dc0  pop     rdi
0x140067dc1  retn
0x140067dc3  mov     rcx, [rbx+18h]
0x140067dc7  mov     rdx, [r14+30h]
0x140067dcb  mov     rax, [rcx+180h]
0x140067dd2  cmp     [rdx+180h], rax
0x140067dd9  jnz     short loc_140067DE5
0x140067ddb  cmp     dword ptr [rcx+18h], 3
0x140067ddf  jz      loc_140068434
0x140067de5  mov     byte ptr [r12+332h], 1
0x140067dee  mov     rax, cs:MpAsyncScanData
0x140067df5  movzx   ecx, word ptr [rax+100h]
0x140067dfc  mov     [r12+330h], cx
0x140067e05  lea     rsi, WPP_GLOBAL_Control
0x140067e0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140067e13  cmp     rcx, rsi
0x140067e16  jnz     loc_1400681A7
0x140067e1c  mov     rcx, [rbx+40h]; Object
0x140067e20  test    rcx, rcx
0x140067e23  jz      short loc_140067E44
0x140067e25  call    cs:__imp_ObfDereferenceObject
0x140067e2c  nop     dword ptr [rax+rax+00h]
0x140067e31  lock xadd cs:ObTotalReferences, r13
0x140067e3a  cmp     r13, 1
0x140067e3e  js      loc_14006816E
0x140067e44  mov     rcx, [rbx+28h]; Context
0x140067e48  test    rcx, rcx
0x140067e4b  jz      short loc_140067E59
0x140067e4d  call    cs:__imp_FltReleaseContext
0x140067e54  nop     dword ptr [rax+rax+00h]
0x140067e59  mov     rcx, [rbx+30h]; Context
0x140067e5d  test    rcx, rcx
0x140067e60  jnz     loc_1400684CF
0x140067e66  mov     rcx, [rbx+38h]
0x140067e6a  test    rcx, rcx
0x140067e6d  jnz     loc_14006819D
0x140067e73  mov     rcx, [rbx+18h]; P
0x140067e77  test    rcx, rcx
0x140067e7a  jz      short loc_140067E8D
0x140067e7c  mov     edx, 7366504Dh; Tag
0x140067e81  call    cs:__imp_ExFreePoolWithTag
0x140067e88  nop     dword ptr [rax+rax+00h]
0x140067e8d  mov     eax, [r14+28h]
0x140067e91  mov     [rbx+10h], eax
0x140067e94  mov     rax, [r14+58h]
0x140067e98  mov     [rbx+40h], rax
0x140067e9c  mov     rax, [r14+40h]
0x140067ea0  mov     [rbx+28h], rax
0x140067ea4  mov     rax, [r14+48h]
0x140067ea8  mov     [rbx+30h], rax
0x140067eac  mov     rax, [r14+50h]
0x140067eb0  mov     [rbx+38h], rax
0x140067eb4  mov     rax, [r14+30h]
0x140067eb8  mov     [rbx+18h], rax
0x140067ebc  mov     eax, [r14+38h]
0x140067ec0  mov     [rbx+20h], eax
0x140067ec3  mov     rcx, cs:MpData
0x140067eca  add     rcx, 8C0h; Lookaside
0x140067ed1  mov     rdx, r14; Entry
0x140067ed4  call    ExFreeToNPagedLookasideList
0x140067ed9  xor     bl, bl
0x140067edb  jmp     loc_140067D71
0x140067ee0  shr     r10d, 5
0x140067ee4  test    r10d, r10d
0x140067ee7  jz      loc_140067FFE
0x140067eed  movzx   eax, al
0x140067ef0  imul    ecx, eax, 25h ; '%'
0x140067ef3  movzx   eax, dl
0x140067ef6  add     ecx, eax
0x140067ef8  imul    edx, ecx, 25h ; '%'
0x140067efb  movzx   eax, r12b
0x140067eff  add     edx, eax
0x140067f01  imul    ecx, edx, 25h ; '%'
0x140067f04  movzx   eax, r15b
0x140067f08  add     ecx, eax
0x140067f0a  imul    edx, ecx, 25h ; '%'
0x140067f0d  movzx   eax, r14b
0x140067f11  add     edx, eax
0x140067f13  imul    ecx, edx, 25h ; '%'
0x140067f16  movzx   eax, sil
0x140067f1a  add     ecx, eax
0x140067f1c  imul    edx, ecx, 25h ; '%'
0x140067f1f  movzx   eax, r8b
0x140067f23  imul    ecx, eax, 1A617D0Dh
0x140067f29  add     edx, r11d
0x140067f2c  add     ecx, 0CBB8E24Fh
0x140067f32  add     edx, ecx
0x140067f34  lea     ecx, [r10-1]
0x140067f38  and     rdx, rcx
0x140067f3b  mov     rax, [rsp+0F8h+var_A0]
0x140067f40  mov     rax, [rax+8]
0x140067f44  lea     rbx, [rax+rdx*8]
0x140067f48  jmp     loc_140067C92
0x140067f4d  lea     r9, [r14+18h]
0x140067f51  mov     r11, [rsp+0F8h+var_A0]
0x140067f56  mov     r8d, [r11+4]
0x140067f5a  mov     ecx, r8d
0x140067f5d  and     ecx, 1Fh
0x140067f60  shl     r13, cl
0x140067f63  and     r13, [r9+8]
0x140067f67  shr     r8d, 5
0x140067f6b  mov     rax, r13
0x140067f6e  shr     rax, 8
0x140067f72  movzx   eax, al
0x140067f75  imul    ecx, eax, 25h ; '%'
0x140067f78  mov     rax, r13
0x140067f7b  shr     rax, 10h
0x140067f7f  movzx   eax, al
0x140067f82  add     ecx, eax
0x140067f84  imul    edx, ecx, 25h ; '%'
0x140067f87  mov     rax, r13
0x140067f8a  shr     rax, 18h
0x140067f8e  movzx   eax, al
0x140067f91  add     edx, eax
0x140067f93  imul    ecx, edx, 25h ; '%'
0x140067f96  mov     rax, r13
0x140067f99  shr     rax, 20h
0x140067f9d  movzx   eax, al
0x140067fa0  add     ecx, eax
0x140067fa2  imul    edx, ecx, 25h ; '%'
0x140067fa5  mov     rax, r13
0x140067fa8  shr     rax, 28h
0x140067fac  movzx   eax, al
0x140067faf  add     edx, eax
0x140067fb1  imul    ecx, edx, 25h ; '%'
0x140067fb4  mov     rax, r13
0x140067fb7  shr     rax, 30h
0x140067fbb  movzx   eax, al
0x140067fbe  add     ecx, eax
0x140067fc0  imul    edx, ecx, 25h ; '%'
0x140067fc3  mov     rax, r13
0x140067fc6  shr     rax, 38h
0x140067fca  add     edx, eax
0x140067fcc  movzx   eax, r13b
  ... truncated ...
```

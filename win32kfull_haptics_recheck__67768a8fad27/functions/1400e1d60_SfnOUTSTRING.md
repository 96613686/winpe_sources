# SfnOUTSTRING

- ea: `0x1400e1d60`
- end: `0x1400e25a5`
- name: `SfnOUTSTRING`
- size: `2117`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14001cb60`
- `0x1400827f0`
- `0x1400cf1d0`
- `0x1400e177c`
- `0x140144bf0`
- `0x14018f810`

## callees

- `0x1400241fc`
- `0x140033b58`
- `0x1400bbd30`
- `0x1400bc610`
- `0x1400e1d60`
- `0x1400e2cb0`
- `0x1402a7178`
- `0x140342fa0`
- `0x140343080`
- `0x140343500`

## import_xrefs

- `ntoskrnl!KeUserModeCallback` at `0x1400e20f6`
- `ntoskrnl!KeUserModeCallback` at `0x1400e20f6`
- `ntoskrnl!RtlMultiByteToUnicodeSize` at `0x1400e22f6`
- `ntoskrnl!RtlMultiByteToUnicodeSize` at `0x1400e22f6`
- `ntoskrnl!RtlUnicodeToMultiByteSize` at `0x1400e22c8`
- `ntoskrnl!RtlUnicodeToMultiByteSize` at `0x1400e22c8`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x1400e2385`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x1400e2385`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x1400e251c`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x1400e251c`
- `ntoskrnl!ProbeForRead` at `0x1400e2247`
- `ntoskrnl!ProbeForRead` at `0x1400e2247`
- `ntoskrnl!MmUserProbeAddress` at `0x1400e230d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e1dd8`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e1e25`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e1edd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e2070`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e2090`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e23c0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e1dd8`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e1e25`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e1edd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e2070`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e2090`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e23c0`
- `win32kbase!EtwTraceBeginCallback` at `0x1400e20cb`
- `win32kbase!EtwTraceBeginCallback` at `0x1400e20cb`
- `win32kbase!EtwTraceEndCallback` at `0x1400e2107`
- `win32kbase!EtwTraceEndCallback` at `0x1400e2107`
- `win32kbase!EnterSharedCrit` at `0x1400e24a2`
- `win32kbase!EnterSharedCrit` at `0x1400e24a2`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1400e2456`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1400e24db`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1400e2456`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1400e24db`
- `win32kbase!EnterCrit` at `0x1400e2125`
- `win32kbase!EnterCrit` at `0x1400e2125`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400e20b6`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400e20b6`
- `win32kbase!Win32FreePool` at `0x1400e2567`
- `win32kbase!Win32FreePool` at `0x1400e1f43`
- `win32kbase!Win32FreePool` at `0x1400e2567`

## pseudocode

```c
SIZE_T __fastcall SfnOUTSTRING(
        __int64 *a1,
        ULONG a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char a7,
        __int64 a8)
{
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v13; // rcx
  __int64 v14; // r13
  __int64 v15; // r12
  unsigned int v16; // eax
  unsigned __int64 v17; // rsi
  _QWORD *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rcx
  ULONG_PTR v22; // rcx
  _DWORD *v23; // rdi
  __int64 v24; // rcx
  _DWORD *v25; // rax
  struct tagTHREADINFO *v26; // rax
  _QWORD *v27; // r8
  __int64 v28; // rcx
  __int64 v29; // rax
  __int128 v30; // xmm6
  __int64 v31; // xmm7_8
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  int v35; // esi
  BOOL v36; // r14d
  __int64 *v37; // rax
  __int64 v38; // rcx
  int v39; // edi
  __int64 v40; // rax
  SIZE_T v41; // rdi
  __int64 v42; // rcx
  int v43; // esi
  int v44; // r14d
  unsigned __int64 v45; // rax
  unsigned __int64 v46; // r8
  ULONG v47; // r8d
  _BYTE *v48; // rcx
  __int64 *v49; // rax
  _BYTE *v51; // rax
  __int64 v52; // rax
  _QWORD *v53; // r14
  ULONG BytesInMultiByteString[2]; // [rsp+30h] [rbp-388h] BYREF
  int v55; // [rsp+38h] [rbp-380h]
  int v56; // [rsp+3Ch] [rbp-37Ch] BYREF
  int v57; // [rsp+40h] [rbp-378h]
  unsigned int v58[2]; // [rsp+48h] [rbp-370h]
  struct _LARGE_STRING *v59; // [rsp+50h] [rbp-368h]
  SIZE_T Length[2]; // [rsp+58h] [rbp-360h] BYREF
  volatile void *Address; // [rsp+68h] [rbp-350h]
  void *Src; // [rsp+90h] [rbp-328h] BYREF
  ULONG BytesInUnicodeString[4]; // [rsp+98h] [rbp-320h] BYREF
  PCWCH UnicodeString; // [rsp+A8h] [rbp-310h]
  ULONG_PTR RegionSize; // [rsp+B0h] [rbp-308h] BYREF
  PVOID *v66; // [rsp+B8h] [rbp-300h]
  __int128 v67; // [rsp+C0h] [rbp-2F8h] BYREF
  void (*v68)(void *); // [rsp+D0h] [rbp-2E8h]
  _BYTE v69[96]; // [rsp+F0h] [rbp-2C8h] BYREF
  _BYTE v70[512]; // [rsp+150h] [rbp-268h] BYREF

  v59 = (struct _LARGE_STRING *)a4;
  *(_QWORD *)v58 = a3;
  BytesInMultiByteString[0] = a2;
  v10 = 0;
  v57 = 0;
  memset_0(v69, 0, sizeof(v69));
  v66 = (PVOID *)v69;
  Src = 0;
  v56 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v11);
  if ( CurrentThreadWin32Thread )
    v14 = *CurrentThreadWin32Thread;
  else
    v14 = 0;
  if ( a1 )
    v15 = a1[5] - *(_QWORD *)(v14 + 504);
  else
    v15 = 0;
  v16 = *(_DWORD *)(a4 + 4) & 0x7FFFFFFF;
  v17 = v16 + 2;
  if ( (unsigned int)v17 >= v16 )
  {
    v55 = a7 & 1;
    v18 = (_QWORD *)PsGetCurrentThreadWin32Thread(v13);
    v21 = v18 ? *v18 : 0LL;
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v21 + 520), 0, 0) & 0x8000000) != 0
      || *(int *)(a4 + 4) >= 0
      || (a7 & 1) != 0
      || (v17 *= 2LL, v17 <= 0xFFFFFFFF) )
    {
      Length[0] = (unsigned int)v17;
      v22 = ((unsigned int)v17 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
      RegionSize = v22;
      if ( v22 > 0x800 )
      {
        v52 = Win32AllocPoolWithQuotaZInit(104, 1667461973, v19, v20);
        v23 = (_DWORD *)v52;
        if ( v52 )
        {
          v53 = (_QWORD *)(v52 + 32);
          *(_QWORD *)(v52 + 32) = 0;
          if ( ZwAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, (PVOID *)(v52 + 32), 0, &RegionSize, 0x1000u, 4u) >= 0 )
          {
            v25 = (_DWORD *)*v53;
            goto LABEL_14;
          }
          Win32FreePool(v23);
        }
      }
      else
      {
        if ( v22 + 104 <= 0x200 )
        {
          v23 = v70;
          memset_0(v70, 0, sizeof(v70));
LABEL_13:
          v25 = v23 + 26;
          *((_QWORD *)v23 + 4) = 0;
LABEL_14:
          *v23 = 104;
          *((_QWORD *)v23 + 2) = v25;
          v23[1] = RegionSize;
          v23[2] = 0;
          v23[6] = 96;
          goto LABEL_15;
        }
        v23 = (_DWORD *)Win32AllocPoolWithQuotaZInit((unsigned int)(v22 + 104), 1667461973, 512, v20);
        if ( v23 )
          goto LABEL_13;
      }
      v23 = 0;
LABEL_15:
      v66 = (PVOID *)v23;
      if ( !v23 )
        return 0;
      PsGetCurrentThreadWin32Thread(v24);
      v67 = 0;
      v68 = 0;
      if ( v23 != (_DWORD *)v69 && v23 != (_DWORD *)v70 )
      {
        v26 = PtiCurrent();
        *(_QWORD *)&v67 = *((_QWORD *)v26 + 47);
        *((_QWORD *)v26 + 47) = &v67;
        *((_QWORD *)&v67 + 1) = v23;
        v68 = Win32FreePool;
      }
      *((_QWORD *)v23 + 5) = v15;
      v23[12] = BytesInMultiByteString[0];
      if ( v55 )
      {
        if ( *((int *)v59 + 1) >= 0 )
        {
          *((_QWORD *)v23 + 7) = 2LL * *(_QWORD *)v58;
          _InterlockedOr((volatile signed __int32 *)PtiCurrent() + 130, 0x8000000u);
          v57 = 1;
          goto LABEL_22;
        }
      }
      else if ( (_InterlockedCompareExchange((volatile signed __int32 *)PtiCurrent() + 130, 0, 0) & 0x8000000) != 0 )
      {
        *((_QWORD *)v23 + 7) = *(_QWORD *)v58 >> 1;
        _InterlockedAnd((volatile signed __int32 *)PtiCurrent() + 130, 0xF7FFFFFF);
LABEL_22:
        *((_QWORD *)v23 + 8) = a5;
        *((_QWORD *)v23 + 9) = a6;
        v27 = v23 + 20;
        if ( (unsigned int)v17 > v23[1] )
          goto LABEL_65;
        v28 = *((_QWORD *)v23 + 2);
        *((_QWORD *)v23 + 2) = v28 + ((Length[0] + 7) & 0xFFFFFFFFFFFFFFF8uLL);
        if ( *((_QWORD *)v23 + 4) )
        {
          *v27 = v28;
        }
        else
        {
          *v27 = v28 - (_QWORD)v23;
          *(_DWORD *)((char *)&v23[v23[2]++] + (unsigned int)v23[6]) = 80;
        }
        v23[22] = v17;
        Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(Length);
        v29 = *(_QWORD *)(v14 + 512);
        v30 = *(_OWORD *)(v29 + 64);
        v31 = *(_QWORD *)(v29 + 80);
        *(_QWORD *)(v29 + 72) = v15;
        v32 = 0;
        if ( a1 )
          v32 = *a1;
        *(_QWORD *)(*(_QWORD *)(v14 + 512) + 64LL) = v32;
        if ( a1 )
          v33 = *(_QWORD *)(a1[5] + 224);
        else
          v33 = 0;
        *(_QWORD *)(*(_QWORD *)(v14 + 512) + 80LL) = v33;
        v35 = (*(_DWORD *)(PsGetCurrentThreadWin32Thread(v33) + 24) >> 2) & 3;
        v36 = 1;
        if ( v35 )
        {
          v37 = (__int64 *)PsGetCurrentThreadWin32Thread(v34);
          if ( v37 )
            v38 = *v37;
          else
            v38 = 0;
          v36 = *(_BYTE *)(v38 + 1708) != 1;
          UserSessionSwitchLeaveCrit();
        }
        EtwTraceBeginCallback(35);
        *((_QWORD *)v23 + 2) = 0;
        v39 = KeUserModeCallback(35, v23, (unsigned int)*v23, &Src, &v56);
        EtwTraceEndCallback(35);
        if ( v35 )
        {
          if ( v35 == 1 )
            EnterSharedCrit(0, v36);
          else
            EnterCrit(0, v36);
        }
        Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)Length);
        v40 = *(_QWORD *)(v14 + 512);
        *(_OWORD *)(v40 + 64) = v30;
        *(_QWORD *)(v40 + 80) = v31;
        if ( v39 < 0 || v56 != 24 )
          goto LABEL_65;
        *(_QWORD *)BytesInMultiByteString = 0;
        RtlCopyFromUser(BytesInMultiByteString, Src, 8u);
        v41 = *(_QWORD *)BytesInMultiByteString;
        Length[0] = *(_QWORD *)BytesInMultiByteString;
        if ( a8 && (*(_DWORD *)(a8 + 84) & 5) != 0 || (a7 & 2) != 0 )
          goto LABEL_66;
        if ( !*(_QWORD *)BytesInMultiByteString )
        {
          if ( *(_QWORD *)v58 )
          {
            v51 = (_BYTE *)*((_QWORD *)v59 + 1);
            if ( *((int *)v59 + 1) < 0 )
              *v51 = 0;
            else
              *(_WORD *)v51 = 0;
          }
          goto LABEL_66;
        }
        *(_OWORD *)Length = 0;
        Address = 0;
        RtlCopyFromUser(Length, Src, 0x18u);
        *(_OWORD *)BytesInUnicodeString = *(_OWORD *)Length;
        UnicodeString = (PCWCH)Address;
        v42 = *((_QWORD *)PtiCurrent() + 68);
        if ( v42 )
        {
          if ( (*(_DWORD *)(v42 + 84) & 1) != 0 && *(struct _LARGE_STRING **)(v42 + 96) == v59 )
            goto LABEL_65;
        }
        v43 = *((_DWORD *)v59 + 1);
        BytesInMultiByteString[0] = 0;
        v44 = v55;
        if ( LODWORD(Length[1]) )
          ProbeForRead(Address, LODWORD(Length[1]), (v55 ^ 1) + 1);
        else
          *(_BYTE *)MmUserProbeAddress = 0;
        if ( v43 < 0 )
        {
          if ( !v44 )
          {
            v46 = 2LL * (unsigned int)v41;
            if ( v46 >= BytesInUnicodeString[2] )
              LODWORD(v46) = BytesInUnicodeString[2];
            RtlUnicodeToMultiByteSize(BytesInMultiByteString, UnicodeString, v46);
            LODWORD(v45) = BytesInMultiByteString[0];
            goto LABEL_64;
          }
          LODWORD(v45) = BytesInUnicodeString[2];
          if ( (unsigned int)v41 < BytesInUnicodeString[2] )
            LODWORD(v45) = v41;
        }
        else if ( v44 )
        {
          v47 = BytesInUnicodeString[2];
          if ( (unsigned int)v41 < BytesInUnicodeString[2] )
            v47 = v41;
          RtlMultiByteToUnicodeSize(BytesInMultiByteString, (const CHAR *)UnicodeString, v47);
          LODWORD(v45) = BytesInMultiByteString[0] >> 1;
        }
        else if ( (unsigned int)v41 >= BytesInUnicodeString[2] >> 1 )
        {
          v45 = (unsigned __int64)BytesInUnicodeString[2] >> 1;
        }
        else
        {
          LODWORD(v45) = v41;
        }
        BytesInMultiByteString[0] = v45;
LABEL_64:
        v41 = (unsigned int)v45;
        Length[0] = (unsigned int)v45;
        CopyOutputString((struct _CALLBACKSTATUS *)BytesInUnicodeString, v59, v58[0], v44);
        goto LABEL_66;
      }
      *((_QWORD *)v23 + 7) = *(_QWORD *)v58;
      goto LABEL_22;
    }
  }
LABEL_65:
  v41 = 0;
LABEL_66:
  v48 = v69;
  if ( v66 != (PVOID *)v69 )
  {
    v48 = v70;
    if ( v66 != (PVOID *)v70 )
    {
      if ( v66[4] )
      {
        Length[0] = 0;
        ZwFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, v66 + 4, Length, 0x8000u);
      }
      *((_QWORD *)PtiCurrent() + 47) = v67;
      ((void (__fastcall *)(_QWORD))v68)(*((_QWORD *)&v67 + 1));
    }
  }
  if ( v57 )
  {
    v49 = (__int64 *)PsGetCurrentThreadWin32Thread(v48);
    if ( v49 )
      v10 = *v49;
    _InterlockedAnd((volatile signed __int32 *)(v10 + 520), 0xF7FFFFFF);
  }
  return v41;
}

```

## disassembly

```asm
0x1400e1d60  mov     rax, rsp
0x1400e1d63  push    rbx
0x1400e1d64  push    rsi
0x1400e1d65  push    rdi
0x1400e1d66  push    r12
0x1400e1d68  push    r13
0x1400e1d6a  push    r14
0x1400e1d6c  push    r15
0x1400e1d6e  sub     rsp, 380h
0x1400e1d75  movaps  xmmword ptr [rax-48h], xmm6
0x1400e1d79  movaps  xmmword ptr [rax-58h], xmm7
0x1400e1d7d  mov     rax, cs:__security_cookie
0x1400e1d84  xor     rax, rsp
0x1400e1d87  mov     [rsp+3B8h+var_68], rax
0x1400e1d8f  mov     r14, r9
0x1400e1d92  mov     [rsp+3B8h+var_368], r9
0x1400e1d97  mov     qword ptr [rsp+3B8h+var_370], r8
0x1400e1d9c  mov     [rsp+3B8h+BytesInMultiByteString], edx
0x1400e1da0  mov     r15, rcx
0x1400e1da3  xor     ebx, ebx
0x1400e1da5  mov     [rsp+3B8h+var_378], ebx
0x1400e1da9  xor     edx, edx; Val
0x1400e1dab  lea     r8d, [rbx+60h]; Size
0x1400e1daf  lea     rcx, [rsp+3B8h+var_2C8]; void *
0x1400e1db7  call    memset_0
0x1400e1dbc  lea     rax, [rsp+3B8h+var_2C8]
0x1400e1dc4  mov     [rsp+3B8h+var_300], rax
0x1400e1dcc  mov     [rsp+3B8h+Src], rbx
0x1400e1dd4  mov     [rsp+3B8h+var_37C], ebx
0x1400e1dd8  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400e1ddf  nop     dword ptr [rax+rax+00h]
0x1400e1de4  test    rax, rax
0x1400e1de7  jz      loc_1400E2580
0x1400e1ded  mov     r13, [rax]
0x1400e1df0  test    r15, r15
0x1400e1df3  jz      loc_1400E2578
0x1400e1df9  mov     r12, [r15+28h]
0x1400e1dfd  sub     r12, [r13+1F8h]
0x1400e1e04  mov     eax, [r14+4]
0x1400e1e08  btr     eax, 1Fh
0x1400e1e0c  lea     esi, [rax+2]
0x1400e1e0f  cmp     esi, eax
0x1400e1e11  jb      loc_1400E2343
0x1400e1e17  mov     edi, dword ptr [rsp+3B8h+arg_30]
0x1400e1e1e  and     edi, 1
0x1400e1e21  mov     [rsp+3B8h+var_380], edi
0x1400e1e25  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400e1e2c  nop     dword ptr [rax+rax+00h]
0x1400e1e31  test    rax, rax
0x1400e1e34  jz      loc_1400E2588
0x1400e1e3a  mov     rcx, [rax]
0x1400e1e3d  xor     eax, eax
0x1400e1e3f  lock cmpxchg [rcx+208h], ebx
0x1400e1e47  bt      eax, 1Bh
0x1400e1e4b  jb      short loc_1400E1E57
0x1400e1e4d  cmp     [r14+4], ebx
0x1400e1e51  jl      loc_1400E24B3
0x1400e1e57  mov     eax, esi
0x1400e1e59  mov     [rsp+3B8h+Length], rax
0x1400e1e5e  lea     rcx, [rax+7]
0x1400e1e62  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1400e1e66  mov     [rsp+3B8h+RegionSize], rcx
0x1400e1e6e  cmp     rcx, 800h
0x1400e1e75  ja      loc_1400E24D1
0x1400e1e7b  lea     rax, [rcx+68h]
0x1400e1e7f  mov     r8d, 200h; Size
0x1400e1e85  cmp     rax, r8
0x1400e1e88  ja      loc_1400E244E
0x1400e1e8e  lea     rdi, [rsp+3B8h+var_268]
0x1400e1e96  xor     edx, edx; Val
0x1400e1e98  lea     rcx, [rsp+3B8h+var_268]; void *
0x1400e1ea0  call    memset_0
0x1400e1ea5  lea     rax, [rdi+68h]
0x1400e1ea9  mov     [rdi+20h], rbx
0x1400e1ead  mov     dword ptr [rdi], 68h ; 'h'
0x1400e1eb3  mov     [rdi+10h], rax
0x1400e1eb7  mov     rax, [rsp+3B8h+RegionSize]
0x1400e1ebf  mov     [rdi+4], eax
0x1400e1ec2  mov     [rdi+8], ebx
0x1400e1ec5  mov     dword ptr [rdi+18h], 60h ; '`'
0x1400e1ecc  mov     [rsp+3B8h+var_300], rdi
0x1400e1ed4  test    rdi, rdi
0x1400e1ed7  jz      loc_1400E253C
0x1400e1edd  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400e1ee4  nop     dword ptr [rax+rax+00h]
0x1400e1ee9  xorps   xmm0, xmm0
0x1400e1eec  xor     eax, eax
0x1400e1eee  movups  [rsp+3B8h+var_2F8], xmm0
0x1400e1ef6  mov     [rsp+3B8h+var_2E8], rax
0x1400e1efe  lea     rax, [rsp+3B8h+var_2C8]
0x1400e1f06  cmp     rdi, rax
0x1400e1f09  jz      short loc_1400E1F52
0x1400e1f0b  lea     rax, [rsp+3B8h+var_268]
0x1400e1f13  cmp     rdi, rax
0x1400e1f16  jz      short loc_1400E1F52
0x1400e1f18  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400e1f1d  mov     rcx, [rax+178h]
0x1400e1f24  mov     qword ptr [rsp+3B8h+var_2F8], rcx
0x1400e1f2c  lea     rcx, [rsp+3B8h+var_2F8]
0x1400e1f34  mov     [rax+178h], rcx
0x1400e1f3b  mov     qword ptr [rsp+3B8h+var_2F8+8], rdi
0x1400e1f43  mov     rax, cs:__imp_Win32FreePool
0x1400e1f4a  mov     [rsp+3B8h+var_2E8], rax
0x1400e1f52  mov     [rdi+28h], r12
0x1400e1f56  mov     eax, [rsp+3B8h+BytesInMultiByteString]
0x1400e1f5a  mov     [rdi+30h], eax
0x1400e1f5d  mov     eax, [rsp+3B8h+var_380]
0x1400e1f61  test    eax, eax
0x1400e1f63  jz      loc_1400E2414
0x1400e1f69  mov     rcx, [rsp+3B8h+var_368]
0x1400e1f6e  cmp     [rcx+4], ebx
0x1400e1f71  jl      loc_1400E2598
0x1400e1f77  mov     rax, qword ptr [rsp+3B8h+var_370]
0x1400e1f7c  add     rax, rax
0x1400e1f7f  mov     [rdi+38h], rax
0x1400e1f83  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400e1f88  lock or dword ptr [rax+208h], 8000000h
0x1400e1f93  mov     [rsp+3B8h+var_378], 1
0x1400e1f9b  mov     rax, [rsp+3B8h+arg_20]
0x1400e1fa3  mov     [rdi+40h], rax
0x1400e1fa7  mov     rax, [rsp+3B8h+arg_28]
0x1400e1faf  mov     [rdi+48h], rax
0x1400e1fb3  lea     r8, [rdi+50h]
0x1400e1fb7  cmp     esi, [rdi+4]
0x1400e1fba  ja      loc_1400E2343
0x1400e1fc0  mov     rcx, [rdi+10h]
0x1400e1fc4  mov     rax, [rsp+3B8h+Length]
0x1400e1fc9  add     rax, 7
0x1400e1fcd  and     rax, 0FFFFFFFFFFFFFFF8h
0x1400e1fd1  add     rax, rcx
0x1400e1fd4  mov     [rdi+10h], rax
0x1400e1fd8  cmp     [rdi+20h], rbx
0x1400e1fdc  jnz     loc_1400E2534
0x1400e1fe2  sub     rcx, rdi
0x1400e1fe5  mov     [r8], rcx
0x1400e1fe8  sub     r8d, edi
0x1400e1feb  mov     edx, [rdi+8]
0x1400e1fee  mov     ecx, [rdi+18h]
0x1400e1ff1  add     rcx, rdi
0x1400e1ff4  mov     [rcx+rdx*4], r8d
0x1400e1ff8  inc     dword ptr [rdi+8]
0x1400e1ffb  mov     [rdi+58h], esi
0x1400e1ffe  mov     rdx, r15
0x1400e2001  lea     rcx, [rsp+3B8h+Length]
0x1400e2006  call    ??0?$Win32HMThreadLockBase@UtagMENU@@$00$0A@@@QEAA@PEAUtagMENU@@@Z; Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(tagMENU *)
0x1400e200b  nop
0x1400e200c  mov     rax, [r13+200h]
0x1400e2013  movups  xmm6, xmmword ptr [rax+40h]
0x1400e2017  movsd   xmm7, qword ptr [rax+50h]
0x1400e201c  mov     rax, [r13+200h]
0x1400e2023  mov     [rax+48h], r12
0x1400e2027  test    r15, r15
0x1400e202a  mov     rcx, rbx
0x1400e202d  jz      short loc_1400E2032
0x1400e202f  mov     rcx, [r15]
0x1400e2032  mov     rax, [r13+200h]
0x1400e2039  mov     [rax+40h], rcx
0x1400e203d  test    r15, r15
0x1400e2040  jz      short loc_1400E204F
0x1400e2042  mov     rax, [r15+28h]
0x1400e2046  mov     rcx, [rax+0E0h]
0x1400e204d  jmp     short loc_1400E2052
0x1400e204f  mov     rcx, rbx
0x1400e2052  mov     rax, [r13+200h]
0x1400e2059  mov     [rax+50h], rcx
0x1400e205d  jmp     short loc_1400E2070
0x1400e205f  lea     rcx, [rsp+3B8h+Length]; BugCheckParameter3
0x1400e2064  call    ??1?$Win32HMThreadLock@UtagCURSOR@@@@QEAA@XZ; Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>(void)
0x1400e2069  xor     ebx, ebx
0x1400e206b  jmp     loc_1400E2343
0x1400e2070  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400e2077  nop     dword ptr [rax+rax+00h]
0x1400e207c  mov     esi, [rax+18h]
0x1400e207f  shr     esi, 2
0x1400e2082  and     esi, 3
0x1400e2085  mov     r12d, 1
0x1400e208b  mov     r14d, r12d
0x1400e208e  jz      short loc_1400E20C2
0x1400e2090  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400e2097  nop     dword ptr [rax+rax+00h]
0x1400e209c  test    rax, rax
0x1400e209f  jz      loc_1400E2590
0x1400e20a5  mov     rcx, [rax]
0x1400e20a8  mov     r14d, ebx
0x1400e20ab  cmp     [rcx+6ACh], r12b
0x1400e20b2  setnz   r14b
0x1400e20b6  call    cs:__imp_UserSessionSwitchLeaveCrit
0x1400e20bd  nop     dword ptr [rax+rax+00h]
0x1400e20c2  mov     r15d, 23h ; '#'
0x1400e20c8  mov     ecx, r15d
0x1400e20cb  call    cs:__imp_EtwTraceBeginCallback
0x1400e20d2  nop     dword ptr [rax+rax+00h]
0x1400e20d7  mov     [rdi+10h], rbx
0x1400e20db  lea     rax, [rsp+3B8h+var_37C]
0x1400e20e0  mov     qword ptr [rsp+3B8h+AllocationType], rax
0x1400e20e5  lea     r9, [rsp+3B8h+Src]
0x1400e20ed  mov     r8d, [rdi]
0x1400e20f0  mov     rdx, rdi
0x1400e20f3  mov     ecx, r15d
0x1400e20f6  call    cs:__imp_KeUserModeCallback
0x1400e20fd  nop     dword ptr [rax+rax+00h]
0x1400e2102  mov     edi, eax
0x1400e2104  mov     ecx, r15d
0x1400e2107  call    cs:__imp_EtwTraceEndCallback
0x1400e210e  nop     dword ptr [rax+rax+00h]
0x1400e2113  test    esi, esi
0x1400e2115  jz      short loc_1400E2131
0x1400e2117  mov     edx, r14d
0x1400e211a  xor     ecx, ecx
0x1400e211c  cmp     esi, r12d
0x1400e211f  jz      loc_1400E24A2
0x1400e2125  call    cs:__imp_EnterCrit
0x1400e212c  nop     dword ptr [rax+rax+00h]
0x1400e2131  lea     rcx, [rsp+3B8h+Length]; BugCheckParameter3
0x1400e2136  call    ??1?$Win32HMThreadLock@UtagCURSOR@@@@QEAA@XZ; Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>(void)
0x1400e213b  nop
0x1400e213c  mov     rax, [r13+200h]
0x1400e2143  movups  xmmword ptr [rax+40h], xmm6
0x1400e2147  movsd   qword ptr [rax+50h], xmm7
0x1400e214c  jmp     short loc_1400E2155
0x1400e214e  xor     ebx, ebx
0x1400e2150  jmp     loc_1400E2343
0x1400e2155  test    edi, edi
0x1400e2157  js      loc_1400E2343
0x1400e215d  cmp     [rsp+3B8h+var_37C], 18h
0x1400e2162  jnz     loc_1400E2343
0x1400e2168  mov     qword ptr [rsp+3B8h+BytesInMultiByteString], rbx
0x1400e216d  mov     r8d, 8; Size
0x1400e2173  mov     rdx, [rsp+3B8h+Src]; Src
0x1400e217b  lea     rcx, [rsp+3B8h+BytesInMultiByteString]; void *
0x1400e2180  call    RtlCopyFromUser
0x1400e2185  mov     rdi, qword ptr [rsp+3B8h+BytesInMultiByteString]
0x1400e218a  mov     [rsp+3B8h+Length], rdi
0x1400e218f  jmp     short loc_1400E2198
0x1400e2191  xor     ebx, ebx
0x1400e2193  jmp     loc_1400E2343
0x1400e2198  mov     rax, [rsp+3B8h+arg_38]
0x1400e21a0  test    rax, rax
0x1400e21a3  jnz     loc_1400E243E
0x1400e21a9  test    [rsp+3B8h+arg_30], 2
0x1400e21b1  jnz     loc_1400E2346
0x1400e21b7  test    rdi, rdi
0x1400e21ba  jz      loc_1400E2476
0x1400e21c0  xorps   xmm0, xmm0
0x1400e21c3  xor     eax, eax
0x1400e21c5  movups  xmmword ptr [rsp+3B8h+Length], xmm0
0x1400e21ca  mov     [rsp+3B8h+Address], rax
0x1400e21cf  lea     r8d, [rax+18h]; Size
0x1400e21d3  mov     rdx, [rsp+3B8h+Src]; Src
0x1400e21db  lea     rcx, [rsp+3B8h+Length]; void *
0x1400e21e0  call    RtlCopyFromUser
0x1400e21e5  movups  xmm0, xmmword ptr [rsp+3B8h+Length]
0x1400e21ea  movups  xmmword ptr [rsp+3B8h+BytesInUnicodeString], xmm0
0x1400e21f2  movsd   xmm1, [rsp+3B8h+Address]
0x1400e21f8  movsd   [rsp+3B8h+UnicodeString], xmm1
0x1400e2201  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400e2206  mov     rcx, [rax+220h]
0x1400e220d  test    rcx, rcx
0x1400e2210  jz      short loc_1400E221A
0x1400e2212  mov     eax, [rcx+54h]
0x1400e2215  test    r12b, al
0x1400e2218  jnz     short loc_1400E2293
0x1400e221a  mov     rcx, [rsp+3B8h+var_368]
0x1400e221f  mov     esi, [rcx+4]
0x1400e2222  mov     [rsp+3B8h+BytesInMultiByteString], ebx
0x1400e2226  mov     r14d, [rsp+3B8h+var_380]
0x1400e222b  cmp     dword ptr [rsp+3B8h+Length+8], ebx
0x1400e222f  jz      loc_1400E230D
0x1400e2235  mov     r8d, r14d
0x1400e2238  xor     r8d, r12d
0x1400e223b  add     r8d, r12d; Alignment
0x1400e223e  mov     edx, dword ptr [rsp+3B8h+Length+8]; Length
0x1400e2242  mov     rcx, [rsp+3B8h+Address]; Address
0x1400e2247  call    cs:__imp_ProbeForRead
0x1400e224e  nop     dword ptr [rax+rax+00h]
0x1400e2253  test    esi, esi
0x1400e2255  js      short loc_1400E226D
0x1400e2257  test    r14d, r14d
0x1400e225a  jnz     short loc_1400E22DA
0x1400e225c  mov     eax, [rsp+3B8h+BytesInUnicodeString+8]
0x1400e2263  shr     eax, 1
0x1400e2265  cmp     edi, eax
0x1400e2267  jnb     short loc_1400E2287
0x1400e2269  mov     eax, edi
0x1400e226b  jmp     short loc_1400E227E
0x1400e226d  test    r14d, r14d
0x1400e2270  jz      short loc_1400E22A7
0x1400e2272  mov     eax, [rsp+3B8h+BytesInUnicodeString+8]
0x1400e2279  cmp     edi, eax
0x1400e227b  cmovb   eax, edi
0x1400e227e  mov     [rsp+3B8h+BytesInMultiByteString], eax
0x1400e2282  jmp     loc_1400E231E
0x1400e2287  mov     eax, [rsp+3B8h+BytesInUnicodeString+8]
0x1400e228e  shr     rax, 1
0x1400e2291  jmp     short loc_1400E227E
0x1400e2293  mov     rax, [rsp+3B8h+var_368]
0x1400e2298  cmp     [rcx+60h], rax
0x1400e229c  jnz     loc_1400E221A
0x1400e22a2  jmp     loc_1400E2343
0x1400e22a7  mov     eax, [rsp+3B8h+BytesInUnicodeString+8]
  ... truncated ...
```

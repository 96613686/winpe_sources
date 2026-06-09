# SfnOUTSTRING

- ea: `0x1400bbb50`
- end: `0x1400bc395`
- name: `SfnOUTSTRING`
- size: `2117`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000b0f0`
- `0x140021d30`
- `0x1400bb574`
- `0x140109e30`
- `0x14014ec30`
- `0x140188ea0`

## callees

- `0x1400292ec`
- `0x1400381a8`
- `0x1400af078`
- `0x1400bbb50`
- `0x1400bcaa0`
- `0x1400d4c10`
- `0x1402a4d38`
- `0x140341ff0`
- `0x1403420d0`
- `0x140342540`

## import_xrefs

- `ntoskrnl!KeUserModeCallback` at `0x1400bbee6`
- `ntoskrnl!KeUserModeCallback` at `0x1400bbee6`
- `ntoskrnl!RtlMultiByteToUnicodeSize` at `0x1400bc0e6`
- `ntoskrnl!RtlMultiByteToUnicodeSize` at `0x1400bc0e6`
- `ntoskrnl!RtlUnicodeToMultiByteSize` at `0x1400bc0b8`
- `ntoskrnl!RtlUnicodeToMultiByteSize` at `0x1400bc0b8`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x1400bc175`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x1400bc175`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x1400bc30c`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x1400bc30c`
- `ntoskrnl!ProbeForRead` at `0x1400bc037`
- `ntoskrnl!ProbeForRead` at `0x1400bc037`
- `ntoskrnl!MmUserProbeAddress` at `0x1400bc0fd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400bbbc8`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400bbc15`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400bbccd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400bbe60`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400bbe80`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400bc1b0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400bbbc8`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400bbc15`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400bbccd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400bbe60`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400bbe80`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400bc1b0`
- `win32kbase!EtwTraceBeginCallback` at `0x1400bbebb`
- `win32kbase!EtwTraceBeginCallback` at `0x1400bbebb`
- `win32kbase!EtwTraceEndCallback` at `0x1400bbef7`
- `win32kbase!EtwTraceEndCallback` at `0x1400bbef7`
- `win32kbase!EnterSharedCrit` at `0x1400bc292`
- `win32kbase!EnterSharedCrit` at `0x1400bc292`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1400bc246`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1400bc2cb`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1400bc246`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1400bc2cb`
- `win32kbase!EnterCrit` at `0x1400bbf15`
- `win32kbase!EnterCrit` at `0x1400bbf15`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400bbea6`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400bbea6`
- `win32kbase!Win32FreePool` at `0x1400bc357`
- `win32kbase!Win32FreePool` at `0x1400bbd33`
- `win32kbase!Win32FreePool` at `0x1400bc357`

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
0x1400bbb50  mov     rax, rsp
0x1400bbb53  push    rbx
0x1400bbb54  push    rsi
0x1400bbb55  push    rdi
0x1400bbb56  push    r12
0x1400bbb58  push    r13
0x1400bbb5a  push    r14
0x1400bbb5c  push    r15
0x1400bbb5e  sub     rsp, 380h
0x1400bbb65  movaps  xmmword ptr [rax-48h], xmm6
0x1400bbb69  movaps  xmmword ptr [rax-58h], xmm7
0x1400bbb6d  mov     rax, cs:__security_cookie
0x1400bbb74  xor     rax, rsp
0x1400bbb77  mov     [rsp+3B8h+var_68], rax
0x1400bbb7f  mov     r14, r9
0x1400bbb82  mov     [rsp+3B8h+var_368], r9
0x1400bbb87  mov     qword ptr [rsp+3B8h+var_370], r8
0x1400bbb8c  mov     [rsp+3B8h+BytesInMultiByteString], edx
0x1400bbb90  mov     r15, rcx
0x1400bbb93  xor     ebx, ebx
0x1400bbb95  mov     [rsp+3B8h+var_378], ebx
0x1400bbb99  xor     edx, edx; Val
0x1400bbb9b  lea     r8d, [rbx+60h]; Size
0x1400bbb9f  lea     rcx, [rsp+3B8h+var_2C8]; void *
0x1400bbba7  call    memset_0
0x1400bbbac  lea     rax, [rsp+3B8h+var_2C8]
0x1400bbbb4  mov     [rsp+3B8h+var_300], rax
0x1400bbbbc  mov     [rsp+3B8h+Src], rbx
0x1400bbbc4  mov     [rsp+3B8h+var_37C], ebx
0x1400bbbc8  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400bbbcf  nop     dword ptr [rax+rax+00h]
0x1400bbbd4  test    rax, rax
0x1400bbbd7  jz      loc_1400BC370
0x1400bbbdd  mov     r13, [rax]
0x1400bbbe0  test    r15, r15
0x1400bbbe3  jz      loc_1400BC368
0x1400bbbe9  mov     r12, [r15+28h]
0x1400bbbed  sub     r12, [r13+1F8h]
0x1400bbbf4  mov     eax, [r14+4]
0x1400bbbf8  btr     eax, 1Fh
0x1400bbbfc  lea     esi, [rax+2]
0x1400bbbff  cmp     esi, eax
0x1400bbc01  jb      loc_1400BC133
0x1400bbc07  mov     edi, dword ptr [rsp+3B8h+arg_30]
0x1400bbc0e  and     edi, 1
0x1400bbc11  mov     [rsp+3B8h+var_380], edi
0x1400bbc15  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400bbc1c  nop     dword ptr [rax+rax+00h]
0x1400bbc21  test    rax, rax
0x1400bbc24  jz      loc_1400BC378
0x1400bbc2a  mov     rcx, [rax]
0x1400bbc2d  xor     eax, eax
0x1400bbc2f  lock cmpxchg [rcx+208h], ebx
0x1400bbc37  bt      eax, 1Bh
0x1400bbc3b  jb      short loc_1400BBC47
0x1400bbc3d  cmp     [r14+4], ebx
0x1400bbc41  jl      loc_1400BC2A3
0x1400bbc47  mov     eax, esi
0x1400bbc49  mov     [rsp+3B8h+Length], rax
0x1400bbc4e  lea     rcx, [rax+7]
0x1400bbc52  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1400bbc56  mov     [rsp+3B8h+RegionSize], rcx
0x1400bbc5e  cmp     rcx, 800h
0x1400bbc65  ja      loc_1400BC2C1
0x1400bbc6b  lea     rax, [rcx+68h]
0x1400bbc6f  mov     r8d, 200h; Size
0x1400bbc75  cmp     rax, r8
0x1400bbc78  ja      loc_1400BC23E
0x1400bbc7e  lea     rdi, [rsp+3B8h+var_268]
0x1400bbc86  xor     edx, edx; Val
0x1400bbc88  lea     rcx, [rsp+3B8h+var_268]; void *
0x1400bbc90  call    memset_0
0x1400bbc95  lea     rax, [rdi+68h]
0x1400bbc99  mov     [rdi+20h], rbx
0x1400bbc9d  mov     dword ptr [rdi], 68h ; 'h'
0x1400bbca3  mov     [rdi+10h], rax
0x1400bbca7  mov     rax, [rsp+3B8h+RegionSize]
0x1400bbcaf  mov     [rdi+4], eax
0x1400bbcb2  mov     [rdi+8], ebx
0x1400bbcb5  mov     dword ptr [rdi+18h], 60h ; '`'
0x1400bbcbc  mov     [rsp+3B8h+var_300], rdi
0x1400bbcc4  test    rdi, rdi
0x1400bbcc7  jz      loc_1400BC32C
0x1400bbccd  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400bbcd4  nop     dword ptr [rax+rax+00h]
0x1400bbcd9  xorps   xmm0, xmm0
0x1400bbcdc  xor     eax, eax
0x1400bbcde  movups  [rsp+3B8h+var_2F8], xmm0
0x1400bbce6  mov     [rsp+3B8h+var_2E8], rax
0x1400bbcee  lea     rax, [rsp+3B8h+var_2C8]
0x1400bbcf6  cmp     rdi, rax
0x1400bbcf9  jz      short loc_1400BBD42
0x1400bbcfb  lea     rax, [rsp+3B8h+var_268]
0x1400bbd03  cmp     rdi, rax
0x1400bbd06  jz      short loc_1400BBD42
0x1400bbd08  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400bbd0d  mov     rcx, [rax+178h]
0x1400bbd14  mov     qword ptr [rsp+3B8h+var_2F8], rcx
0x1400bbd1c  lea     rcx, [rsp+3B8h+var_2F8]
0x1400bbd24  mov     [rax+178h], rcx
0x1400bbd2b  mov     qword ptr [rsp+3B8h+var_2F8+8], rdi
0x1400bbd33  mov     rax, cs:__imp_Win32FreePool
0x1400bbd3a  mov     [rsp+3B8h+var_2E8], rax
0x1400bbd42  mov     [rdi+28h], r12
0x1400bbd46  mov     eax, [rsp+3B8h+BytesInMultiByteString]
0x1400bbd4a  mov     [rdi+30h], eax
0x1400bbd4d  mov     eax, [rsp+3B8h+var_380]
0x1400bbd51  test    eax, eax
0x1400bbd53  jz      loc_1400BC204
0x1400bbd59  mov     rcx, [rsp+3B8h+var_368]
0x1400bbd5e  cmp     [rcx+4], ebx
0x1400bbd61  jl      loc_1400BC388
0x1400bbd67  mov     rax, qword ptr [rsp+3B8h+var_370]
0x1400bbd6c  add     rax, rax
0x1400bbd6f  mov     [rdi+38h], rax
0x1400bbd73  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400bbd78  lock or dword ptr [rax+208h], 8000000h
0x1400bbd83  mov     [rsp+3B8h+var_378], 1
0x1400bbd8b  mov     rax, [rsp+3B8h+arg_20]
0x1400bbd93  mov     [rdi+40h], rax
0x1400bbd97  mov     rax, [rsp+3B8h+arg_28]
0x1400bbd9f  mov     [rdi+48h], rax
0x1400bbda3  lea     r8, [rdi+50h]
0x1400bbda7  cmp     esi, [rdi+4]
0x1400bbdaa  ja      loc_1400BC133
0x1400bbdb0  mov     rcx, [rdi+10h]
0x1400bbdb4  mov     rax, [rsp+3B8h+Length]
0x1400bbdb9  add     rax, 7
0x1400bbdbd  and     rax, 0FFFFFFFFFFFFFFF8h
0x1400bbdc1  add     rax, rcx
0x1400bbdc4  mov     [rdi+10h], rax
0x1400bbdc8  cmp     [rdi+20h], rbx
0x1400bbdcc  jnz     loc_1400BC324
0x1400bbdd2  sub     rcx, rdi
0x1400bbdd5  mov     [r8], rcx
0x1400bbdd8  sub     r8d, edi
0x1400bbddb  mov     edx, [rdi+8]
0x1400bbdde  mov     ecx, [rdi+18h]
0x1400bbde1  add     rcx, rdi
0x1400bbde4  mov     [rcx+rdx*4], r8d
0x1400bbde8  inc     dword ptr [rdi+8]
0x1400bbdeb  mov     [rdi+58h], esi
0x1400bbdee  mov     rdx, r15
0x1400bbdf1  lea     rcx, [rsp+3B8h+Length]
0x1400bbdf6  call    ??0?$Win32HMThreadLockBase@UtagMENU@@$00$0A@@@QEAA@PEAUtagMENU@@@Z; Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(tagMENU *)
0x1400bbdfb  nop
0x1400bbdfc  mov     rax, [r13+200h]
0x1400bbe03  movups  xmm6, xmmword ptr [rax+40h]
0x1400bbe07  movsd   xmm7, qword ptr [rax+50h]
0x1400bbe0c  mov     rax, [r13+200h]
0x1400bbe13  mov     [rax+48h], r12
0x1400bbe17  test    r15, r15
0x1400bbe1a  mov     rcx, rbx
0x1400bbe1d  jz      short loc_1400BBE22
0x1400bbe1f  mov     rcx, [r15]
0x1400bbe22  mov     rax, [r13+200h]
0x1400bbe29  mov     [rax+40h], rcx
0x1400bbe2d  test    r15, r15
0x1400bbe30  jz      short loc_1400BBE3F
0x1400bbe32  mov     rax, [r15+28h]
0x1400bbe36  mov     rcx, [rax+0E0h]
0x1400bbe3d  jmp     short loc_1400BBE42
0x1400bbe3f  mov     rcx, rbx
0x1400bbe42  mov     rax, [r13+200h]
0x1400bbe49  mov     [rax+50h], rcx
0x1400bbe4d  jmp     short loc_1400BBE60
0x1400bbe4f  lea     rcx, [rsp+3B8h+Length]; BugCheckParameter3
0x1400bbe54  call    ??1?$Win32HMThreadLock@UtagCURSOR@@@@QEAA@XZ; Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>(void)
0x1400bbe59  xor     ebx, ebx
0x1400bbe5b  jmp     loc_1400BC133
0x1400bbe60  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400bbe67  nop     dword ptr [rax+rax+00h]
0x1400bbe6c  mov     esi, [rax+18h]
0x1400bbe6f  shr     esi, 2
0x1400bbe72  and     esi, 3
0x1400bbe75  mov     r12d, 1
0x1400bbe7b  mov     r14d, r12d
0x1400bbe7e  jz      short loc_1400BBEB2
0x1400bbe80  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400bbe87  nop     dword ptr [rax+rax+00h]
0x1400bbe8c  test    rax, rax
0x1400bbe8f  jz      loc_1400BC380
0x1400bbe95  mov     rcx, [rax]
0x1400bbe98  mov     r14d, ebx
0x1400bbe9b  cmp     [rcx+6ACh], r12b
0x1400bbea2  setnz   r14b
0x1400bbea6  call    cs:__imp_UserSessionSwitchLeaveCrit
0x1400bbead  nop     dword ptr [rax+rax+00h]
0x1400bbeb2  mov     r15d, 23h ; '#'
0x1400bbeb8  mov     ecx, r15d
0x1400bbebb  call    cs:__imp_EtwTraceBeginCallback
0x1400bbec2  nop     dword ptr [rax+rax+00h]
0x1400bbec7  mov     [rdi+10h], rbx
0x1400bbecb  lea     rax, [rsp+3B8h+var_37C]
0x1400bbed0  mov     qword ptr [rsp+3B8h+AllocationType], rax
0x1400bbed5  lea     r9, [rsp+3B8h+Src]
0x1400bbedd  mov     r8d, [rdi]
0x1400bbee0  mov     rdx, rdi
0x1400bbee3  mov     ecx, r15d
0x1400bbee6  call    cs:__imp_KeUserModeCallback
0x1400bbeed  nop     dword ptr [rax+rax+00h]
0x1400bbef2  mov     edi, eax
0x1400bbef4  mov     ecx, r15d
0x1400bbef7  call    cs:__imp_EtwTraceEndCallback
0x1400bbefe  nop     dword ptr [rax+rax+00h]
0x1400bbf03  test    esi, esi
0x1400bbf05  jz      short loc_1400BBF21
0x1400bbf07  mov     edx, r14d
0x1400bbf0a  xor     ecx, ecx
0x1400bbf0c  cmp     esi, r12d
0x1400bbf0f  jz      loc_1400BC292
0x1400bbf15  call    cs:__imp_EnterCrit
0x1400bbf1c  nop     dword ptr [rax+rax+00h]
0x1400bbf21  lea     rcx, [rsp+3B8h+Length]; BugCheckParameter3
0x1400bbf26  call    ??1?$Win32HMThreadLock@UtagCURSOR@@@@QEAA@XZ; Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>(void)
0x1400bbf2b  nop
0x1400bbf2c  mov     rax, [r13+200h]
0x1400bbf33  movups  xmmword ptr [rax+40h], xmm6
0x1400bbf37  movsd   qword ptr [rax+50h], xmm7
0x1400bbf3c  jmp     short loc_1400BBF45
0x1400bbf3e  xor     ebx, ebx
0x1400bbf40  jmp     loc_1400BC133
0x1400bbf45  test    edi, edi
0x1400bbf47  js      loc_1400BC133
0x1400bbf4d  cmp     [rsp+3B8h+var_37C], 18h
0x1400bbf52  jnz     loc_1400BC133
0x1400bbf58  mov     qword ptr [rsp+3B8h+BytesInMultiByteString], rbx
0x1400bbf5d  mov     r8d, 8; Size
0x1400bbf63  mov     rdx, [rsp+3B8h+Src]; Src
0x1400bbf6b  lea     rcx, [rsp+3B8h+BytesInMultiByteString]; void *
0x1400bbf70  call    RtlCopyFromUser
0x1400bbf75  mov     rdi, qword ptr [rsp+3B8h+BytesInMultiByteString]
0x1400bbf7a  mov     [rsp+3B8h+Length], rdi
0x1400bbf7f  jmp     short loc_1400BBF88
0x1400bbf81  xor     ebx, ebx
0x1400bbf83  jmp     loc_1400BC133
0x1400bbf88  mov     rax, [rsp+3B8h+arg_38]
0x1400bbf90  test    rax, rax
0x1400bbf93  jnz     loc_1400BC22E
0x1400bbf99  test    [rsp+3B8h+arg_30], 2
0x1400bbfa1  jnz     loc_1400BC136
0x1400bbfa7  test    rdi, rdi
0x1400bbfaa  jz      loc_1400BC266
0x1400bbfb0  xorps   xmm0, xmm0
0x1400bbfb3  xor     eax, eax
0x1400bbfb5  movups  xmmword ptr [rsp+3B8h+Length], xmm0
0x1400bbfba  mov     [rsp+3B8h+Address], rax
0x1400bbfbf  lea     r8d, [rax+18h]; Size
0x1400bbfc3  mov     rdx, [rsp+3B8h+Src]; Src
0x1400bbfcb  lea     rcx, [rsp+3B8h+Length]; void *
0x1400bbfd0  call    RtlCopyFromUser
0x1400bbfd5  movups  xmm0, xmmword ptr [rsp+3B8h+Length]
0x1400bbfda  movups  xmmword ptr [rsp+3B8h+BytesInUnicodeString], xmm0
0x1400bbfe2  movsd   xmm1, [rsp+3B8h+Address]
0x1400bbfe8  movsd   [rsp+3B8h+UnicodeString], xmm1
0x1400bbff1  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400bbff6  mov     rcx, [rax+220h]
0x1400bbffd  test    rcx, rcx
0x1400bc000  jz      short loc_1400BC00A
0x1400bc002  mov     eax, [rcx+54h]
0x1400bc005  test    r12b, al
0x1400bc008  jnz     short loc_1400BC083
0x1400bc00a  mov     rcx, [rsp+3B8h+var_368]
0x1400bc00f  mov     esi, [rcx+4]
0x1400bc012  mov     [rsp+3B8h+BytesInMultiByteString], ebx
0x1400bc016  mov     r14d, [rsp+3B8h+var_380]
0x1400bc01b  cmp     dword ptr [rsp+3B8h+Length+8], ebx
0x1400bc01f  jz      loc_1400BC0FD
0x1400bc025  mov     r8d, r14d
0x1400bc028  xor     r8d, r12d
0x1400bc02b  add     r8d, r12d; Alignment
0x1400bc02e  mov     edx, dword ptr [rsp+3B8h+Length+8]; Length
0x1400bc032  mov     rcx, [rsp+3B8h+Address]; Address
0x1400bc037  call    cs:__imp_ProbeForRead
0x1400bc03e  nop     dword ptr [rax+rax+00h]
0x1400bc043  test    esi, esi
0x1400bc045  js      short loc_1400BC05D
0x1400bc047  test    r14d, r14d
0x1400bc04a  jnz     short loc_1400BC0CA
0x1400bc04c  mov     eax, [rsp+3B8h+BytesInUnicodeString+8]
0x1400bc053  shr     eax, 1
0x1400bc055  cmp     edi, eax
0x1400bc057  jnb     short loc_1400BC077
0x1400bc059  mov     eax, edi
0x1400bc05b  jmp     short loc_1400BC06E
0x1400bc05d  test    r14d, r14d
0x1400bc060  jz      short loc_1400BC097
0x1400bc062  mov     eax, [rsp+3B8h+BytesInUnicodeString+8]
0x1400bc069  cmp     edi, eax
0x1400bc06b  cmovb   eax, edi
0x1400bc06e  mov     [rsp+3B8h+BytesInMultiByteString], eax
0x1400bc072  jmp     loc_1400BC10E
0x1400bc077  mov     eax, [rsp+3B8h+BytesInUnicodeString+8]
0x1400bc07e  shr     rax, 1
0x1400bc081  jmp     short loc_1400BC06E
0x1400bc083  mov     rax, [rsp+3B8h+var_368]
0x1400bc088  cmp     [rcx+60h], rax
0x1400bc08c  jnz     loc_1400BC00A
0x1400bc092  jmp     loc_1400BC133
0x1400bc097  mov     eax, [rsp+3B8h+BytesInUnicodeString+8]
  ... truncated ...
```

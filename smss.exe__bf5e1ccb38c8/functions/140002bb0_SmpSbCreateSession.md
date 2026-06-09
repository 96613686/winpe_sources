# SmpSbCreateSession

- ea: `0x140002bb0`
- end: `0x1400030e9`
- name: `SmpSbCreateSession`
- size: `1337`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400027a0`
- `0x1400151e0`

## callees

- `0x140002bb0`
- `0x1400030f0`
- `0x140003114`
- `0x140008cd0`
- `0x14000aca0`
- `0x14000d4c0`
- `0x140017d5c`
- `0x140017ff0`
- `0x140018154`
- `0x14001cc29`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140002d99`
- `ntdll!RtlInitUnicodeString` at `0x140002d99`
- `ntdll!NtClose` at `0x140002cf0`
- `ntdll!NtClose` at `0x140002d05`
- `ntdll!NtClose` at `0x140002feb`
- `ntdll!NtClose` at `0x140002cf0`
- `ntdll!NtClose` at `0x140002d05`
- `ntdll!NtClose` at `0x140002feb`
- `ntdll!RtlFreeHeap` at `0x140002d1d`
- `ntdll!RtlFreeHeap` at `0x140002d1d`
- `ntdll!NtResumeThread` at `0x140002fdc`
- `ntdll!NtResumeThread` at `0x140002fdc`
- `ntdll!NtDuplicateObject` at `0x140002e79`
- `ntdll!NtDuplicateObject` at `0x140002eaa`
- `ntdll!NtDuplicateObject` at `0x140002fc5`
- `ntdll!NtDuplicateObject` at `0x1400030a7`
- `ntdll!NtDuplicateObject` at `0x1400030cd`
- `ntdll!NtDuplicateObject` at `0x140002e79`
- `ntdll!NtDuplicateObject` at `0x140002eaa`
- `ntdll!NtDuplicateObject` at `0x140002fc5`
- `ntdll!NtDuplicateObject` at `0x1400030a7`
- `ntdll!NtDuplicateObject` at `0x1400030cd`
- `ntdll!RtlAcquireSRWLockShared` at `0x140002c24`
- `ntdll!RtlAcquireSRWLockShared` at `0x140002c24`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x140002f12`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x140002f12`

## string_xrefs

- `0x140002caf`: `SmpSbCreateSession`
- `0x140002f41`: `SmpSbCreateSession`
- `0x140003047`: `SmpSbCreateSession`
- `0x14000306f`: `SmpSbCreateSession`

## pseudocode

```c
NTSTATUS __fastcall SmpSbCreateSession(int a1, void *a2, __int128 *a3, __int64 a4, __int128 *a5)
{
  int v8; // r13d
  _QWORD *v9; // rbx
  _QWORD **v10; // rdi
  _QWORD *i; // rax
  int v12; // eax
  int v13; // edi
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  NTSTATUS result; // eax
  __int64 v18; // rax
  _QWORD *v19; // rbx
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  NTSTATUS v26; // eax
  NTSTATUS v27; // eax
  signed __int32 v28; // eax
  int v29; // eax
  NTSTATUS v30; // ebx
  __int64 v31; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v34[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 Parameters[3]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v36[5]; // [rsp+80h] [rbp-80h] BYREF
  int v37; // [rsp+A8h] [rbp-58h]
  int v38; // [rsp+ACh] [rbp-54h]
  signed __int32 v39; // [rsp+B0h] [rbp-50h]
  void *TargetHandle[2]; // [rsp+B8h] [rbp-48h] BYREF
  HANDLE SourceHandle[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v42; // [rsp+D8h] [rbp-28h]
  __int128 v43; // [rsp+E8h] [rbp-18h]
  __int128 v44; // [rsp+F8h] [rbp-8h]
  __int128 v45; // [rsp+108h] [rbp+8h]
  __int64 v46; // [rsp+118h] [rbp+18h]
  __int64 v47; // [rsp+128h] [rbp+28h]
  __int128 v48; // [rsp+130h] [rbp+30h]
  __int128 v49; // [rsp+140h] [rbp+40h]
  __int128 v50; // [rsp+150h] [rbp+50h]
  __int128 v51; // [rsp+160h] [rbp+60h]
  __int128 v52; // [rsp+170h] [rbp+70h]
  __int128 v53; // [rsp+180h] [rbp+80h]
  __int128 v54; // [rsp+190h] [rbp+90h]
  HANDLE ThreadHandle; // [rsp+200h] [rbp+100h] BYREF

  memset_0(v36, 0, 0x120u);
  v8 = *((_DWORD *)a3 + 18);
  ThreadHandle = 0;
  v33 = 0;
  v9 = 0;
  v34[0] = 1;
  v10 = (_QWORD **)(SmpKnownSubSysTable + 24LL * (a1 & 0x1F));
  v34[1] = v10;
  RtlAcquireSRWLockShared(v10 + 2);
  for ( i = *v10; ; i = (_QWORD *)*i )
  {
    if ( i == v10 )
    {
      SmpUnlockKnownSubSysList(v34);
      if ( *((_DWORD *)a3 + 18) != 1 )
        return -1073741570;
      result = NtDuplicateObject(a2, *((HANDLE *)a3 + 2), (HANDLE)0xFFFFFFFFFFFFFFFFLL, &ThreadHandle, 2u, 0, 0);
      if ( result >= 0 )
      {
        v30 = NtResumeThread(ThreadHandle, 0);
        NtClose(ThreadHandle);
        return v30;
      }
      return result;
    }
    if ( *((_DWORD *)i - 2) == a1 )
    {
      if ( *((_DWORD *)i - 12) == v8 )
        v9 = i - 9;
      if ( v9 )
        break;
    }
  }
  _InterlockedIncrement((volatile signed __int32 *)v9);
  SmpUnlockKnownSubSysList(v34);
  LODWORD(DestinationString.Buffer) = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  v12 = *((_DWORD *)v9 + 2);
  if ( (v12 & 4) != 0 )
    goto LABEL_7;
  if ( (v12 & 1) == 0 )
  {
    if ( *((_DWORD *)v9 + 6) != -1 )
      goto LABEL_7;
LABEL_49:
    v13 = 0;
    SmpLockKnownSubSysList(*((unsigned int *)v9 + 16), 1, &DestinationString);
    if ( !(unsigned int)SmpCheckSubSysStatus(v9) )
      v13 = SmpWaitForStatusChange(v31, (v9[1] & 1) == 0, &DestinationString);
    SmpUnlockKnownSubSysList(&DestinationString);
    if ( v13 < 0 )
      goto LABEL_10;
    goto LABEL_7;
  }
  if ( !v9[6] )
    goto LABEL_49;
LABEL_7:
  if ( (v9[1] & 4) == 0 )
  {
    memset_0(v36, 0, 0xA8u);
    v20 = a3[1];
    v47 = 0;
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    v21 = *a3;
    *(_OWORD *)SourceHandle = v20;
    v22 = a3[3];
    *(_OWORD *)TargetHandle = v21;
    v23 = a3[2];
    v43 = v22;
    v24 = a3[5];
    v42 = v23;
    v25 = a3[4];
    v45 = v24;
    v44 = v25;
    v46 = *((_QWORD *)a3 + 12);
    if ( a5 )
      v48 = *a5;
    else
      v48 = 0;
    v26 = NtDuplicateObject(a2, *((HANDLE *)a3 + 1), (HANDLE)v9[4], &TargetHandle[1], 0x1FFFFFu, 0, 0);
    v13 = v26;
    if ( v26 < 0 )
    {
      SmLogFailureInt((unsigned int)"SmpSbCreateSession", 179, a1, 0, v26);
      goto LABEL_11;
    }
    v27 = NtDuplicateObject(a2, *((HANDLE *)a3 + 2), (HANDLE)v9[4], SourceHandle, 0x1FFFFFu, 0, 0);
    v13 = v27;
    if ( v27 < 0 )
    {
      SmLogFailureInt((unsigned int)"SmpSbCreateSession", 195, *((_DWORD *)v9 + 16), 0, v27);
    }
    else
    {
      v28 = _InterlockedIncrement((volatile signed __int32 *)v9 + 1);
      if ( !v28 )
        _InterlockedOr((volatile signed __int32 *)v9 + 2, 8u);
      v39 = v28;
      v37 = 0;
      v36[0] = 12583064;
      v33 = 288;
      v29 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD *, _QWORD, _QWORD *, __int64 *, _QWORD, _QWORD, _QWORD, _DWORD))NtAlpcSendWaitReceivePort)(
              v9[5],
              0x20000,
              v36,
              0,
              v36,
              &v33,
              0,
              0,
              *(_QWORD *)&DestinationString.Length,
              DestinationString.Buffer);
      v13 = v29;
      if ( v29 >= 0 )
      {
        v13 = v38;
        goto LABEL_11;
      }
      SmLogFailureInt((unsigned int)"SmpSbCreateSession", 232, *((_DWORD *)v9 + 16), 0, v29);
      NtDuplicateObject((HANDLE)v9[4], SourceHandle[0], 0, 0, 0, 0, 1u);
    }
    NtDuplicateObject((HANDLE)v9[4], TargetHandle[1], 0, 0, 0, 0, 1u);
    goto LABEL_11;
  }
  v13 = -1073741823;
  SmpLogFailure("SmpWaitForSingleSubSys", 1205, 3221225473LL);
LABEL_10:
  SmLogFailureInt((unsigned int)"SmpSbCreateSession", 148, a1, 0, v13);
LABEL_11:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9, 0xFFFFFFFF) == 1 )
  {
    if ( (v9[1] & 4) != 0 && *((_DWORD *)v9 + 6) == 2 && *((_DWORD *)v9 + 16) == *(_DWORD *)SmpCoreProcessIds )
    {
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"Core Windows subsystem terminated");
      Parameters[1] = -1073741823;
      Parameters[0] = (unsigned __int64)&DestinationString;
      SmpTerminate(Parameters, 1u, 2u);
    }
    v14 = (void *)v9[2];
    if ( v14 )
      SmpDisposeSubSysSynch(v14);
    v15 = (void *)v9[5];
    if ( v15 )
      NtClose(v15);
    if ( (v9[1] & 8) != 0 )
    {
      v18 = SmpOverflowSubSysList;
      if ( *(__int64 **)(SmpOverflowSubSysList + 8) != &SmpOverflowSubSysList )
        __fastfail(3u);
      v19 = v9 + 9;
      *v19 = SmpOverflowSubSysList;
      v19[1] = &SmpOverflowSubSysList;
      *(_QWORD *)(v18 + 8) = v19;
      SmpOverflowSubSysList = (__int64)v19;
    }
    else
    {
      v16 = (void *)v9[4];
      if ( v16 )
        NtClose(v16);
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v9);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x140002bb0  push    rbp
0x140002bb2  push    rbx
0x140002bb3  push    rsi
0x140002bb4  push    rdi
0x140002bb5  push    r12
0x140002bb7  push    r13
0x140002bb9  push    r14
0x140002bbb  push    r15
0x140002bbd  lea     rbp, [rsp-0A8h]
0x140002bc5  sub     rsp, 1A8h
0x140002bcc  mov     rsi, r8
0x140002bcf  mov     r12d, ecx
0x140002bd2  mov     r15, rdx
0x140002bd5  lea     rcx, [rbp+0E0h+var_160]; void *
0x140002bd9  xor     edx, edx; Val
0x140002bdb  mov     r8d, 120h; Size
0x140002be1  call    memset_0
0x140002be6  mov     r13d, [rsi+48h]
0x140002bea  xor     ecx, ecx
0x140002bec  mov     eax, r12d
0x140002bef  mov     [rbp+0E0h+ThreadHandle], rcx
0x140002bf6  and     eax, 1Fh
0x140002bf9  mov     [rsp+1E0h+var_190], rcx
0x140002bfe  mov     ebx, ecx
0x140002c00  mov     [rsp+1E0h+var_188], 1
0x140002c09  mov     r14d, r12d
0x140002c0c  lea     rcx, [rax+rax*2]
0x140002c10  mov     rax, cs:SmpKnownSubSysTable
0x140002c17  lea     rdi, [rax+rcx*8]
0x140002c1b  lea     rcx, [rdi+10h]
0x140002c1f  mov     [rsp+1E0h+var_180], rdi
0x140002c24  call    cs:__imp_RtlAcquireSRWLockShared
0x140002c2a  mov     rax, [rdi]
0x140002c2d  cmp     rax, rdi
0x140002c30  jnz     loc_140002F57
0x140002c36  lea     rcx, [rsp+1E0h+var_188]
0x140002c3b  call    SmpUnlockKnownSubSysList
0x140002c40  test    rbx, rbx
0x140002c43  jz      loc_140002F88
0x140002c49  xor     eax, eax
0x140002c4b  mov     qword ptr [rsp+1E0h+DestinationString+4], rax
0x140002c50  mov     [rsp+40h], rax
0x140002c55  mov     eax, [rbx+8]
0x140002c58  test    al, 4
0x140002c5a  jnz     short loc_140002C6F
0x140002c5c  test    al, 1
0x140002c5e  jz      loc_140002FF8
0x140002c64  cmp     qword ptr [rbx+30h], 0
0x140002c69  jz      loc_140003002
0x140002c6f  xor     r12d, r12d
0x140002c72  test    byte ptr [rbx+8], 4
0x140002c76  jz      loc_140002DC8
0x140002c7c  mov     edi, 0C0000001h
0x140002c81  lea     rcx, aSmpwaitforsing; "SmpWaitForSingleSubSys"
0x140002c88  mov     r8d, edi
0x140002c8b  mov     edx, 4B5h
0x140002c90  call    SmpLogFailure
0x140002c95  jmp     short loc_140002CA5
0x140002c97  lea     rcx, [rsp+1E0h+DestinationString]
0x140002c9c  call    SmpUnlockKnownSubSysList
0x140002ca1  test    edi, edi
0x140002ca3  jns     short loc_140002C72
0x140002ca5  xor     r9d, r9d
0x140002ca8  mov     [rsp+1E0h+DesiredAccess], edi
0x140002cac  mov     r8, r14
0x140002caf  lea     rcx, aSmpsbcreateses; "SmpSbCreateSession"
0x140002cb6  mov     edx, 94h
0x140002cbb  call    SmLogFailureInt
0x140002cc0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140002cc7  lock xadd [rbx], eax
0x140002ccb  cmp     eax, 1
0x140002cce  jnz     short loc_140002D23
0x140002cd0  test    byte ptr [rbx+8], 4
0x140002cd4  jnz     loc_140002D69
0x140002cda  mov     rcx, [rbx+10h]; BaseAddress
0x140002cde  test    rcx, rcx
0x140002ce1  jnz     loc_1400030D8
0x140002ce7  mov     rcx, [rbx+28h]; Handle
0x140002ceb  test    rcx, rcx
0x140002cee  jz      short loc_140002CF6
0x140002cf0  call    cs:__imp_NtClose
0x140002cf6  test    byte ptr [rbx+8], 8
0x140002cfa  jnz     short loc_140002D39
0x140002cfc  mov     rcx, [rbx+20h]; Handle
0x140002d00  test    rcx, rcx
0x140002d03  jz      short loc_140002D0B
0x140002d05  call    cs:__imp_NtClose
0x140002d0b  mov     rcx, gs:60h
0x140002d14  mov     r8, rbx; BaseAddress
0x140002d17  xor     edx, edx; Flags
0x140002d19  mov     rcx, [rcx+30h]; HeapHandle
0x140002d1d  call    cs:__imp_RtlFreeHeap
0x140002d23  mov     eax, edi
0x140002d25  add     rsp, 1A8h
0x140002d2c  pop     r15
0x140002d2e  pop     r14
0x140002d30  pop     r13
0x140002d32  pop     r12
0x140002d34  pop     rdi
0x140002d35  pop     rsi
0x140002d36  pop     rbx
0x140002d37  pop     rbp
0x140002d38  retn
0x140002d39  mov     rax, cs:SmpOverflowSubSysList
0x140002d40  lea     rcx, SmpOverflowSubSysList
0x140002d47  cmp     [rax+8], rcx
0x140002d4b  jnz     loc_1400030E2
0x140002d51  add     rbx, 48h ; 'H'
0x140002d55  mov     [rbx], rax
0x140002d58  mov     [rbx+8], rcx
0x140002d5c  mov     [rax+8], rbx
0x140002d60  mov     cs:SmpOverflowSubSysList, rbx
0x140002d67  jmp     short loc_140002D23
0x140002d69  cmp     dword ptr [rbx+18h], 2
0x140002d6d  jnz     loc_140002CDA
0x140002d73  mov     rax, cs:SmpCoreProcessIds
0x140002d7a  mov     ecx, [rax]
0x140002d7c  cmp     [rbx+40h], ecx
0x140002d7f  jnz     loc_140002CDA
0x140002d85  xorps   xmm0, xmm0
0x140002d88  lea     rdx, SourceString; "Core Windows subsystem terminated"
0x140002d8f  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x140002d94  movups  xmmword ptr [rsp+1E0h+DestinationString.Length], xmm0
0x140002d99  call    cs:__imp_RtlInitUnicodeString
0x140002d9f  lea     rax, [rsp+1E0h+DestinationString]
0x140002da4  mov     [rsp+1E0h+var_170], 0FFFFFFFFC0000001h
0x140002dad  mov     edx, 1; UnicodeStringParameterMask
0x140002db2  mov     [rsp+1E0h+Parameters], rax
0x140002db7  mov     r8d, 2; NumberOfParameters
0x140002dbd  lea     rcx, [rsp+1E0h+Parameters]; Parameters
0x140002dc2  call    SmpTerminate
0x140002dc8  xor     edx, edx; Val
0x140002dca  lea     rcx, [rbp+0E0h+var_160]; void *
0x140002dce  mov     r8d, 0A8h; Size
0x140002dd4  call    memset_0
0x140002dd9  movups  xmm1, xmmword ptr [rsi+10h]
0x140002ddd  mov     rcx, [rbp+0E0h+arg_20]
0x140002de4  xor     eax, eax
0x140002de6  xorps   xmm0, xmm0
0x140002de9  mov     [rbp+0E0h+var_B8], rax
0x140002ded  movaps  [rbp+0E0h+var_A0], xmm0
0x140002df1  movaps  [rbp+0E0h+var_90], xmm0
0x140002df5  movaps  [rbp+0E0h+var_80], xmm0
0x140002df9  movaps  [rbp+0E0h+var_70], xmm0
0x140002dfd  movaps  [rbp+0E0h+var_60], xmm0
0x140002e04  movaps  [rbp+0E0h+var_50], xmm0
0x140002e0b  movups  xmm0, xmmword ptr [rsi]
0x140002e0e  movups  xmmword ptr [rbp+0E0h+SourceHandle], xmm1
0x140002e12  movups  xmm1, xmmword ptr [rsi+30h]
0x140002e16  movups  xmmword ptr [rbp+0E0h+TargetHandle], xmm0
0x140002e1a  movups  xmm0, xmmword ptr [rsi+20h]
0x140002e1e  movups  [rbp+0E0h+var_F8], xmm1
0x140002e22  movups  xmm1, xmmword ptr [rsi+50h]
0x140002e26  movups  [rbp+0E0h+var_108], xmm0
0x140002e2a  movups  xmm0, xmmword ptr [rsi+40h]
0x140002e2e  movups  [rbp+0E0h+var_D8], xmm1
0x140002e32  movups  [rbp+0E0h+var_E8], xmm0
0x140002e36  movsd   xmm0, qword ptr [rsi+60h]
0x140002e3b  movsd   [rbp+0E0h+var_C8], xmm0
0x140002e40  test    rcx, rcx
0x140002e43  jz      loc_140002F2A
0x140002e49  mov     rax, [rcx]
0x140002e4c  mov     qword ptr [rbp+0E0h+var_B0], rax
0x140002e50  mov     rax, [rcx+8]
0x140002e54  mov     qword ptr [rbp+0E0h+var_B0+8], rax
0x140002e58  mov     r8, [rbx+20h]; TargetProcessHandle
0x140002e5c  lea     r9, [rbp+0E0h+TargetHandle+8]; TargetHandle
0x140002e60  mov     rdx, [rsi+8]; SourceHandle
0x140002e64  mov     rcx, r15; SourceProcessHandle
0x140002e67  mov     [rsp+1E0h+Options], r12d; Options
0x140002e6c  mov     [rsp+1E0h+HandleAttributes], r12d; HandleAttributes
0x140002e71  mov     [rsp+1E0h+DesiredAccess], 1FFFFFh; DesiredAccess
0x140002e79  call    cs:__imp_NtDuplicateObject
0x140002e7f  mov     edi, eax
0x140002e81  test    eax, eax
0x140002e83  js      loc_140002F37
0x140002e89  mov     r8, [rbx+20h]; TargetProcessHandle
0x140002e8d  lea     r9, [rbp+0E0h+SourceHandle]; TargetHandle
0x140002e91  mov     rdx, [rsi+10h]; SourceHandle
0x140002e95  mov     rcx, r15; SourceProcessHandle
0x140002e98  mov     [rsp+1E0h+Options], r12d; Options
0x140002e9d  mov     [rsp+1E0h+HandleAttributes], r12d; HandleAttributes
0x140002ea2  mov     [rsp+1E0h+DesiredAccess], 1FFFFFh; DesiredAccess
0x140002eaa  call    cs:__imp_NtDuplicateObject
0x140002eb0  mov     edi, eax
0x140002eb2  test    eax, eax
0x140002eb4  js      loc_140003043
0x140002eba  mov     eax, 1
0x140002ebf  lock xadd [rbx+4], eax
0x140002ec4  add     eax, 1
0x140002ec7  jz      loc_140003061
0x140002ecd  mov     [rbp+0E0h+var_130], eax
0x140002ed0  lea     r8, [rbp+0E0h+var_160]
0x140002ed4  mov     [rsp+1E0h+var_1A8], r12
0x140002ed9  lea     rax, [rsp+1E0h+var_190]
0x140002ede  mov     qword ptr [rsp+1E0h+Options], r12
0x140002ee3  xor     r9d, r9d
0x140002ee6  mov     qword ptr [rsp+1E0h+HandleAttributes], rax
0x140002eeb  mov     edx, 20000h
0x140002ef0  lea     rax, [rbp+0E0h+var_160]
0x140002ef4  mov     [rbp+0E0h+var_138], r12d
0x140002ef8  mov     [rbp+0E0h+var_160], 0C00098h
0x140002f00  mov     [rsp+1E0h+var_190], 120h
0x140002f09  mov     rcx, [rbx+28h]
0x140002f0d  mov     qword ptr [rsp+1E0h+DesiredAccess], rax
0x140002f12  call    cs:__imp_NtAlpcSendWaitReceivePort
0x140002f18  mov     edi, eax
0x140002f1a  test    eax, eax
0x140002f1c  js      loc_14000306B
0x140002f22  mov     edi, [rbp+0E0h+var_134]
0x140002f25  jmp     loc_140002CC0
0x140002f2a  xorps   xmm0, xmm0
0x140002f2d  movdqa  [rbp+0E0h+var_B0], xmm0
0x140002f32  jmp     loc_140002E58
0x140002f37  xor     r9d, r9d
0x140002f3a  mov     [rsp+1E0h+DesiredAccess], eax
0x140002f3e  mov     r8, r14
0x140002f41  lea     rcx, aSmpsbcreateses; "SmpSbCreateSession"
0x140002f48  mov     edx, 0B3h
0x140002f4d  call    SmLogFailureInt
0x140002f52  jmp     loc_140002CC0
0x140002f57  cmp     [rax-8], r12d
0x140002f5b  lea     rcx, [rax-48h]
0x140002f5f  jnz     short loc_140002F80
0x140002f61  cmp     [rcx+18h], r13d
0x140002f65  cmovz   rbx, rcx
0x140002f69  test    rbx, rbx
0x140002f6c  jz      short loc_140002F80
0x140002f6e  lock inc dword ptr [rbx]
0x140002f71  lea     rcx, [rsp+1E0h+var_188]
0x140002f76  call    SmpUnlockKnownSubSysList
0x140002f7b  jmp     loc_140002C49
0x140002f80  mov     rax, [rax]
0x140002f83  jmp     loc_140002C2D
0x140002f88  cmp     dword ptr [rsi+48h], 1
0x140002f8c  jz      short loc_140002F98
0x140002f8e  mov     eax, 0C00000FEh
0x140002f93  jmp     loc_140002D25
0x140002f98  mov     rdx, [rsi+10h]; SourceHandle
0x140002f9c  lea     r9, [rbp+0E0h+ThreadHandle]; TargetHandle
0x140002fa3  mov     [rsp+1E0h+Options], 0; Options
0x140002fab  mov     r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x140002fb2  mov     [rsp+1E0h+HandleAttributes], 0; HandleAttributes
0x140002fba  mov     rcx, r15; SourceProcessHandle
0x140002fbd  mov     [rsp+1E0h+DesiredAccess], 2; DesiredAccess
0x140002fc5  call    cs:__imp_NtDuplicateObject
0x140002fcb  test    eax, eax
0x140002fcd  js      loc_140002D25
0x140002fd3  mov     rcx, [rbp+0E0h+ThreadHandle]; ThreadHandle
0x140002fda  xor     edx, edx; SuspendCount
0x140002fdc  call    cs:__imp_NtResumeThread
0x140002fe2  mov     rcx, [rbp+0E0h+ThreadHandle]; Handle
0x140002fe9  mov     ebx, eax
0x140002feb  call    cs:__imp_NtClose
0x140002ff1  mov     eax, ebx
0x140002ff3  jmp     loc_140002D25
0x140002ff8  cmp     dword ptr [rbx+18h], 0FFFFFFFFh
0x140002ffc  jnz     loc_140002C6F
0x140003002  mov     ecx, [rbx+40h]
0x140003005  lea     r8, [rsp+1E0h+DestinationString]
0x14000300a  xor     r12d, r12d
0x14000300d  mov     edx, 1
0x140003012  mov     edi, r12d
0x140003015  call    SmpLockKnownSubSysList
0x14000301a  mov     rcx, rbx
0x14000301d  call    SmpCheckSubSysStatus
0x140003022  test    eax, eax
0x140003024  jnz     loc_140002C97
0x14000302a  mov     edx, [rbx+8]
0x14000302d  lea     r8, [rsp+1E0h+DestinationString]
0x140003032  not     edx
0x140003034  and     edx, 1
0x140003037  call    SmpWaitForStatusChange
0x14000303c  mov     edi, eax
0x14000303e  jmp     loc_140002C97
0x140003043  mov     r8d, [rbx+40h]
0x140003047  lea     rcx, aSmpsbcreateses; "SmpSbCreateSession"
0x14000304e  xor     r9d, r9d
0x140003051  mov     [rsp+1E0h+DesiredAccess], eax
0x140003055  mov     edx, 0C3h
0x14000305a  call    SmLogFailureInt
0x14000305f  jmp     short loc_1400030AD
0x140003061  lock or dword ptr [rbx+8], 8
0x140003066  jmp     loc_140002ECD
0x14000306b  mov     r8d, [rbx+40h]
0x14000306f  lea     rcx, aSmpsbcreateses; "SmpSbCreateSession"
0x140003076  xor     r9d, r9d
0x140003079  mov     [rsp+1E0h+DesiredAccess], eax
0x14000307d  mov     edx, 0E8h
0x140003082  call    SmLogFailureInt
0x140003087  mov     rdx, [rbp+0E0h+SourceHandle]; SourceHandle
0x14000308b  xor     r9d, r9d; TargetHandle
0x14000308e  mov     rcx, [rbx+20h]; SourceProcessHandle
0x140003092  xor     r8d, r8d; TargetProcessHandle
0x140003095  mov     [rsp+1E0h+Options], 1; Options
0x14000309d  mov     [rsp+1E0h+HandleAttributes], r12d; HandleAttributes
0x1400030a2  mov     [rsp+1E0h+DesiredAccess], r12d; DesiredAccess
0x1400030a7  call    cs:__imp_NtDuplicateObject
0x1400030ad  mov     rdx, [rbp+0E0h+TargetHandle+8]; SourceHandle
0x1400030b1  xor     r9d, r9d; TargetHandle
  ... truncated ...
```

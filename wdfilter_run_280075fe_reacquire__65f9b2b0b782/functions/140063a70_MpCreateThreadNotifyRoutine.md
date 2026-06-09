# MpCreateThreadNotifyRoutine

- ea: `0x140063a70`
- end: `0x140064160`
- name: `MpCreateThreadNotifyRoutine`
- size: `1776`
- prototype: `void __stdcall(HANDLE ProcessId, HANDLE ThreadId, BOOLEAN Create)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation`

## callees

- `0x140003950`
- `0x1400051bc`
- `0x140007030`
- `0x1400118d0`
- `0x140011900`
- `0x140030060`
- `0x140034b50`
- `0x140035080`
- `0x140035100`
- `0x140035e50`
- `0x140037820`
- `0x140056b50`
- `0x140063a70`
- `0x140064160`
- `0x140064770`
- `0x14006488c`
- `0x140065308`
- `0x14006e394`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140063b72`
- `ntoskrnl!PsGetProcessId` at `0x140063b72`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140063b3b`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140063b3b`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140063b60`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140063e1c`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140063b60`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140063e1c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140063c05`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140063c05`
- `ntoskrnl!ExReleaseResourceLite` at `0x140063bf9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140063bf9`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140063ba3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140063ba3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140063b91`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140063b91`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140063af6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140063af6`
- `ntoskrnl!IoGetCurrentProcess` at `0x140063e0d`
- `ntoskrnl!IoGetCurrentProcess` at `0x140063e0d`
- `ntoskrnl!PsIsSystemThread` at `0x140063acb`
- `ntoskrnl!PsIsSystemThread` at `0x140063acb`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140063c9b`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140063c9b`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140063ae7`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140063ae7`
- `ntoskrnl!KeBugCheck` at `0x140063cb3`
- `ntoskrnl!KeBugCheck` at `0x140063cb3`
- `ntoskrnl!ObfDereferenceObject` at `0x140063c1a`
- `ntoskrnl!ObfDereferenceObject` at `0x140063c1a`

## pseudocode

```c
void __fastcall MpCreateThreadNotifyRoutine(HANDLE ProcessId, HANDLE ThreadId, BOOLEAN Create)
{
  __int64 v3; // r13
  __int64 v5; // r14
  HANDLE CurrentProcessId; // r15
  NTSTATUS v7; // ecx
  struct _KPROCESS *v8; // rbx
  LONGLONG TimeQuadPart; // rsi
  unsigned __int64 v10; // rdi
  char *v11; // rbx
  volatile signed __int32 **v12; // r8
  volatile signed __int32 *i; // rax
  int v14; // edi
  int ProcessContextById; // eax
  bool v16; // si
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // ecx
  const void **v22; // r12
  int v23; // edi
  __int64 v24; // rax
  __int64 v25; // rsi
  struct _KPROCESS *CurrentProcess; // rax
  LONGLONG v27; // rax
  int v28; // eax
  unsigned __int16 *v29; // rax
  int v30; // eax
  __int64 v31; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v32; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE CurrentThreadId; // [rsp+48h] [rbp-B8h]
  HANDLE v34; // [rsp+50h] [rbp-B0h]
  __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+68h] [rbp-98h]
  __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  __int128 v39; // [rsp+80h] [rbp-80h] BYREF
  PEPROCESS Process; // [rsp+90h] [rbp-70h] BYREF
  __int64 v41; // [rsp+98h] [rbp-68h] BYREF
  int v42; // [rsp+A0h] [rbp-60h]
  _OWORD v43[3]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v44; // [rsp+D8h] [rbp-28h] BYREF

  v3 = 0;
  v34 = ThreadId;
  v35 = 0;
  v32 = 0;
  v5 = 0;
  LOBYTE(v31) = 0;
  if ( !Create )
  {
    MpDeleteThreadContext(KeGetCurrentThread());
    return;
  }
  if ( (_DWORD)ProcessId != 4 && !PsIsSystemThread(KeGetCurrentThread()) )
  {
    CurrentProcessId = PsGetCurrentProcessId();
    Process = 0;
    CurrentThreadId = PsGetCurrentThreadId();
    if ( CurrentProcessId )
    {
      v7 = PsLookupProcessByProcessId(CurrentProcessId, &Process);
      if ( v7 >= 0 )
      {
        _InterlockedIncrement64(&ObTotalReferences);
        v8 = Process;
        TimeQuadPart = PsGetProcessCreateTimeQuadPart(Process);
        v10 = (unsigned __int64)PsGetProcessId(v8);
        if ( v10 )
        {
          v11 = (char *)MpProcessTable;
          KeEnterCriticalRegion();
          ExAcquireResourceSharedLite((PERESOURCE)(v11 + 8), 1u);
          v12 = (volatile signed __int32 **)(*((_QWORD *)MpProcessTable + 48) + 16 * ((v10 >> 2) & 0x7F));
          for ( i = *v12; i != (volatile signed __int32 *)v12; i = *(volatile signed __int32 **)i )
          {
            if ( v10 == *((_QWORD *)i + 2) && TimeQuadPart == *((_QWORD *)i + 3) )
            {
              _InterlockedIncrement(i + 10);
              v3 = (__int64)(i - 2);
              break;
            }
          }
          ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
          KeLeaveCriticalRegion();
        }
        if ( Process )
        {
          ObfDereferenceObject(Process);
          if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
          {
            if ( KdRefreshDebuggerNotPresent() )
              KeBugCheck(1u);
            __debugbreak();
          }
        }
        if ( !v3 )
          goto LABEL_17;
        LOBYTE(v14) = v31;
        if ( CurrentProcessId == ProcessId )
        {
          v14 = (unsigned __int8)v31;
          if ( (*(_DWORD *)(v3 + 56) & 0x10000000) != 0 )
            v14 = 1;
          LODWORD(v31) = v14;
        }
        ProcessContextById = MpGetProcessContextById(ProcessId, &v32);
        v5 = v32;
        v16 = CurrentProcessId != ProcessId;
        if ( ProcessContextById >= 0
          && (v17 = *(_DWORD *)(v32 + 52), (v17 & 4) != 0)
          && (v16 = 0, *(_DWORD *)(v32 + 52) = v17 & 0xFFFFFFFB, (*(_DWORD *)(v5 + 56) & 0x10000000) != 0) )
        {
          LOBYTE(v31) = 1;
        }
        else if ( !(_BYTE)v14 && !v16 )
        {
LABEL_32:
          MpReleaseProcessContext(v3);
          goto LABEL_17;
        }
        v41 = 0;
        v42 = 0;
        GetMpUniquePidFromProcessId(ProcessId, &v41);
        v36 = 0;
        v37 = 0;
        GetMpUniquePidFromProcessId(CurrentProcessId, &v36);
        v39 = 0;
        MpGetPriorityInfo(0, 0, &v39);
        if ( (_BYTE)v31 )
        {
          v44 = 0;
          memset(v43, 0, sizeof(v43));
          if ( v5 )
          {
            if ( CurrentThreadId && v34 )
            {
              v31 = 0;
              if ( (int)MpGetThreadCreateTimeById(v34, &v31) >= 0 )
              {
                LODWORD(v43[0]) = (_DWORD)v34;
                *(_QWORD *)((char *)v43 + 4) = MpFileTimeToUlong64(v31);
              }
              v38 = 0;
              if ( (int)MpGetThreadCreateTimeById(CurrentThreadId, &v38) >= 0 )
              {
                LODWORD(v43[1]) = 0;
                HIDWORD(v43[0]) = (_DWORD)CurrentThreadId;
                *(_QWORD *)&v43[1] = MpFileTimeToUlong64(v38);
              }
              DWORD2(v43[1]) = *(_DWORD *)(v5 + 24);
              *(_QWORD *)((char *)&v43[1] + 12) = MpFileTimeToUlong64(*(_QWORD *)(v5 + 32));
              *((_QWORD *)&v43[2] + 1) = 0;
              MpGetThreadWin32StartAddressById(v34, &v44);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                WPP_SF_dd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  42,
                  WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
                  (unsigned int)CurrentProcessId,
                  (_DWORD)ProcessId);
              }
              v28 = MpSendSyncMonitorNotification(6, (unsigned int)&v36, (unsigned int)v43, (unsigned int)&v39, v3 + 56);
              if ( v28 < 0
                && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                _mm_lfence();
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  43,
                  WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
                  KeGetCurrentThread(),
                  v28);
                v5 = v32;
              }
            }
          }
        }
        if ( v16 )
        {
          if ( (*(_DWORD *)(v3 + 56) & 0x400000) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_dd(
                WPP_GLOBAL_Control->AttachedDevice,
                44,
                WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
                (unsigned int)CurrentProcessId,
                (_DWORD)ProcessId);
            }
            v30 = MpSendSyncMonitorNotification(3, (unsigned int)&v36, (unsigned int)&v41, (unsigned int)&v39, v3 + 56);
            if ( v30 < 0
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              _mm_lfence();
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                45,
                WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
                KeGetCurrentThread(),
                v30);
              v5 = v32;
            }
          }
          if ( (unsigned __int8)MpShouldSendBmMessage(v3, v18, v19, v20) && (*(_DWORD *)(v3 + 56) & 0x80u) == 0 )
          {
            if ( v5 && (v29 = *(unsigned __int16 **)(v5 + 128)) != 0 )
            {
              v21 = *v29;
              v22 = *(const void ***)(v5 + 128);
            }
            else
            {
              v21 = 0;
              v22 = 0;
            }
            v23 = v21 + 72;
            if ( (int)MpAsyncCreateNotification(&v35, (unsigned int)(v21 + 72)) >= 0 )
            {
              _mm_lfence();
              v24 = v35;
              *(_QWORD *)(v35 + 28) = 0;
              *(_QWORD *)(v24 + 36) = 0;
              *(_QWORD *)(v24 + 44) = 0;
              *(_QWORD *)(v24 + 52) = 0;
              *(_QWORD *)(v24 + 60) = 0;
              v25 = v35;
              *(_DWORD *)(v35 + 8) = v23;
              *(_DWORD *)(v25 + 16) = 6;
              *(_DWORD *)(v24 + 24) = (_DWORD)CurrentProcessId;
              CurrentProcess = IoGetCurrentProcess();
              v27 = PsGetProcessCreateTimeQuadPart(CurrentProcess);
              *(_QWORD *)(v25 + 28) = MpFileTimeToUlong64(v27);
              *(_DWORD *)(v25 + 36) = (_DWORD)CurrentThreadId;
              *(_QWORD *)(v25 + 40) = v41;
              *(_DWORD *)(v25 + 48) = v42;
              *(_DWORD *)(v25 + 52) = (_DWORD)v34;
              *(_QWORD *)(v25 + 56) = MpFileTimeToUlong64(0);
              if ( v22 && *(_WORD *)v22 )
              {
                memmove((void *)(v25 + 64), v22[1], *(unsigned __int16 *)v22);
                *(_WORD *)(v25 + 2 * ((unsigned __int64)*(unsigned __int16 *)v22 >> 1) + 64) = 0;
              }
              MpAsyncSendNotification(v25, v23, 0, 1, v3);
              MpAsyncDereferenceNotification(v25);
              v5 = v32;
            }
          }
        }
        goto LABEL_32;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          40,
          WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids,
          KeGetCurrentThread(),
          v7);
        v5 = v32;
LABEL_17:
        if ( v5 )
          MpReleaseProcessContext(v5);
      }
    }
  }
}

```

## disassembly

```asm
0x140063a70  push    rbp
0x140063a72  push    r12
0x140063a74  push    r13
0x140063a76  push    r14
0x140063a78  lea     rbp, [rsp-8]
0x140063a7d  sub     rsp, 108h
0x140063a84  mov     rax, cs:__security_cookie
0x140063a8b  xor     rax, rsp
0x140063a8e  mov     [rbp+20h+var_40], rax
0x140063a92  xor     r13d, r13d
0x140063a95  mov     [rsp+120h+var_D0], rdx
0x140063a9a  mov     [rsp+120h+var_C8], r13
0x140063a9f  mov     r12, rcx
0x140063aa2  mov     [rsp+120h+var_E0], r13
0x140063aa7  mov     r14d, r13d
0x140063aaa  mov     byte ptr [rsp+120h+var_E8], r13b
0x140063aaf  test    r8b, r8b
0x140063ab2  jz      loc_140064061
0x140063ab8  cmp     r12d, 4
0x140063abc  jz      loc_140063C6E
0x140063ac2  mov     rcx, gs:188h; Thread
0x140063acb  call    cs:__imp_PsIsSystemThread
0x140063ad2  nop     dword ptr [rax+rax+00h]
0x140063ad7  test    al, al
0x140063ad9  jnz     loc_140063C6E
0x140063adf  mov     [rsp+120h+var_30], r15
0x140063ae7  call    cs:__imp_PsGetCurrentProcessId
0x140063aee  nop     dword ptr [rax+rax+00h]
0x140063af3  mov     r15, rax
0x140063af6  call    cs:__imp_PsGetCurrentThreadId
0x140063afd  nop     dword ptr [rax+rax+00h]
0x140063b02  cmp     r15, r12
0x140063b05  mov     [rbp+20h+Process], r13
0x140063b09  mov     [rsp+120h+var_D8], rax
0x140063b0e  setnz   [rsp+120h+var_F0]
0x140063b13  test    r15, r15
0x140063b16  jz      loc_140063C66
0x140063b1c  mov     [rsp+120h+arg_10], rbx
0x140063b24  lea     rdx, [rbp+20h+Process]; Process
0x140063b28  mov     [rsp+120h+var_20], rsi
0x140063b30  mov     rcx, r15; ProcessId
0x140063b33  mov     [rsp+120h+var_28], rdi
0x140063b3b  call    cs:__imp_PsLookupProcessByProcessId
0x140063b42  nop     dword ptr [rax+rax+00h]
0x140063b47  mov     ecx, eax
0x140063b49  test    eax, eax
0x140063b4b  js      loc_140063FEC
0x140063b51  lock inc cs:ObTotalReferences
0x140063b59  mov     rbx, [rbp+20h+Process]
0x140063b5d  mov     rcx, rbx; Process
0x140063b60  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x140063b67  nop     dword ptr [rax+rax+00h]
0x140063b6c  mov     rcx, rbx; Process
0x140063b6f  mov     rsi, rax
0x140063b72  call    cs:__imp_PsGetProcessId
0x140063b79  nop     dword ptr [rax+rax+00h]
0x140063b7e  mov     rdi, rax
0x140063b81  test    rax, rax
0x140063b84  jz      loc_140063C11
0x140063b8a  mov     rbx, cs:MpProcessTable
0x140063b91  call    cs:__imp_KeEnterCriticalRegion
0x140063b98  nop     dword ptr [rax+rax+00h]
0x140063b9d  mov     dl, 1; Wait
0x140063b9f  lea     rcx, [rbx+8]; Resource
0x140063ba3  call    cs:__imp_ExAcquireResourceSharedLite
0x140063baa  nop     dword ptr [rax+rax+00h]
0x140063baf  mov     rax, cs:MpProcessTable
0x140063bb6  mov     r8, rdi
0x140063bb9  shr     r8, 2
0x140063bbd  and     r8d, 7Fh
0x140063bc1  shl     r8, 4
0x140063bc5  add     r8, [rax+180h]
0x140063bcc  mov     rax, [r8]
0x140063bcf  nop
0x140063bd0  cmp     rax, r8
0x140063bd3  jz      short loc_140063BEE
0x140063bd5  cmp     rdi, [rax+10h]
0x140063bd9  jz      short loc_140063BE0
0x140063bdb  mov     rax, [rax]
0x140063bde  jmp     short loc_140063BD0
0x140063be0  cmp     rsi, [rax+18h]
0x140063be4  jnz     short loc_140063BDB
0x140063be6  lock inc dword ptr [rax+28h]
0x140063bea  lea     r13, [rax-8]
0x140063bee  mov     rcx, cs:MpProcessTable
0x140063bf5  add     rcx, 8; Resource
0x140063bf9  call    cs:__imp_ExReleaseResourceLite
0x140063c00  nop     dword ptr [rax+rax+00h]
0x140063c05  call    cs:__imp_KeLeaveCriticalRegion
0x140063c0c  nop     dword ptr [rax+rax+00h]
0x140063c11  mov     rcx, [rbp+20h+Process]; Object
0x140063c15  test    rcx, rcx
0x140063c18  jz      short loc_140063C3C
0x140063c1a  call    cs:__imp_ObfDereferenceObject
0x140063c21  nop     dword ptr [rax+rax+00h]
0x140063c26  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140063c2d  lock xadd cs:ObTotalReferences, rax
0x140063c36  cmp     rax, 1
0x140063c3a  js      short loc_140063C8A
0x140063c3c  test    r13, r13
0x140063c3f  jnz     short loc_140063CC0
0x140063c41  test    r14, r14
0x140063c44  jz      short loc_140063C4E
0x140063c46  mov     rcx, r14
0x140063c49  call    MpReleaseProcessContext
0x140063c4e  mov     rdi, [rsp+120h+var_28]
0x140063c56  mov     rsi, [rsp+120h+var_20]
0x140063c5e  mov     rbx, [rsp+120h+arg_10]
0x140063c66  mov     r15, [rsp+120h+var_30]
0x140063c6e  mov     rcx, [rbp+20h+var_40]
0x140063c72  xor     rcx, rsp; StackCookie
0x140063c75  call    __security_check_cookie
0x140063c7a  add     rsp, 108h
0x140063c81  pop     r14
0x140063c83  pop     r13
0x140063c85  pop     r12
0x140063c87  pop     rbp
0x140063c88  retn
0x140063c8a  mov     rax, cs:MpData
0x140063c91  mov     ecx, [rax+364h]
0x140063c97  test    ecx, ecx
0x140063c99  jns     short loc_140063C3C
0x140063c9b  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140063ca2  nop     dword ptr [rax+rax+00h]
0x140063ca7  test    al, al
0x140063ca9  jnz     short loc_140063CAE
0x140063cab  int     3; Trap to Debugger
0x140063cac  jmp     short loc_140063C3C
0x140063cae  mov     ecx, 1; BugCheckCode
0x140063cb3  call    cs:__imp_KeBugCheck
0x140063cc0  mov     edi, dword ptr [rsp+120h+var_E8]
0x140063cc4  mov     ebx, 1
0x140063cc9  cmp     r15, r12
0x140063ccc  jnz     short loc_140063CE1
0x140063cce  test    dword ptr [r13+38h], 10000000h
0x140063cd6  movzx   edi, dil
0x140063cda  cmovnz  edi, ebx
0x140063cdd  mov     dword ptr [rsp+120h+var_E8], edi
0x140063ce1  lea     rdx, [rsp+120h+var_E0]
0x140063ce6  mov     rcx, r12
0x140063ce9  call    MpGetProcessContextById
0x140063cee  mov     r14, [rsp+120h+var_E0]
0x140063cf3  movzx   esi, [rsp+120h+var_F0]
0x140063cf8  test    eax, eax
0x140063cfa  js      short loc_140063D04
0x140063cfc  mov     eax, [r14+34h]
0x140063d00  test    al, 4
0x140063d02  jnz     short loc_140063D1B
0x140063d04  test    dil, dil
0x140063d07  jnz     short loc_140063D33
0x140063d09  test    sil, sil
0x140063d0c  jnz     short loc_140063D33
0x140063d0e  mov     rcx, r13
0x140063d11  call    MpReleaseProcessContext
0x140063d16  jmp     loc_140063C41
0x140063d1b  and     eax, 0FFFFFFFBh
0x140063d1e  xor     sil, sil
0x140063d21  mov     [r14+34h], eax
0x140063d25  test    dword ptr [r14+38h], 10000000h
0x140063d2d  jz      short loc_140063D04
0x140063d2f  mov     byte ptr [rsp+120h+var_E8], bl
0x140063d33  xor     eax, eax
0x140063d35  lea     rdx, [rbp+20h+var_88]
0x140063d39  mov     rcx, r12
0x140063d3c  mov     [rbp+20h+var_88], rax
0x140063d40  mov     [rbp+20h+var_80], eax
0x140063d43  call    GetMpUniquePidFromProcessId
0x140063d48  xor     eax, eax
0x140063d4a  lea     rdx, [rsp+120h+var_C0]
0x140063d4f  mov     rcx, r15
0x140063d52  mov     [rsp+120h+var_C0], rax
0x140063d57  mov     [rsp+120h+var_B8], eax
0x140063d5b  call    GetMpUniquePidFromProcessId
0x140063d60  xorps   xmm0, xmm0
0x140063d63  lea     r8, [rbp+20h+var_A0]
0x140063d67  xor     edx, edx
0x140063d69  xor     ecx, ecx
0x140063d6b  movups  [rbp+20h+var_A0], xmm0
0x140063d6f  call    MpGetPriorityInfo
0x140063d74  cmp     byte ptr [rsp+120h+var_E8], 0
0x140063d79  lea     rdi, WPP_GLOBAL_Control
0x140063d80  jnz     loc_140063E99
0x140063d86  test    sil, sil
0x140063d89  jz      short loc_140063D0E
0x140063d8b  test    dword ptr [r13+38h], 400000h
0x140063d93  lea     rsi, [r13+38h]
0x140063d97  jnz     loc_140064096
0x140063d9d  mov     rcx, r13
0x140063da0  call    MpShouldSendBmMessage
0x140063da5  test    al, al
0x140063da7  jz      loc_140063D0E
0x140063dad  mov     eax, [rsi]
0x140063daf  test    al, al
0x140063db1  js      loc_140063D0E
0x140063db7  test    r14, r14
0x140063dba  jnz     loc_140064044
0x140063dc0  xor     esi, esi
0x140063dc2  mov     ecx, esi
0x140063dc4  mov     r12d, ecx
0x140063dc7  lea     edi, [rcx+48h]
0x140063dca  mov     edx, edi
0x140063dcc  lea     rcx, [rsp+120h+var_C8]
0x140063dd1  call    MpAsyncCreateNotification
0x140063dd6  test    eax, eax
0x140063dd8  js      loc_140063D0E
0x140063dde  lfence
0x140063de1  mov     rax, [rsp+120h+var_C8]
0x140063de6  mov     [rax+1Ch], rsi
0x140063dea  mov     [rax+24h], rsi
0x140063dee  mov     [rax+2Ch], rsi
0x140063df2  mov     [rax+34h], rsi
0x140063df6  mov     [rax+3Ch], rsi
0x140063dfa  mov     rsi, [rsp+120h+var_C8]
0x140063dff  mov     [rsi+8], edi
0x140063e02  mov     dword ptr [rsi+10h], 6
0x140063e09  mov     [rax+18h], r15d
0x140063e0d  call    cs:__imp_IoGetCurrentProcess
0x140063e14  nop     dword ptr [rax+rax+00h]
0x140063e19  mov     rcx, rax; Process
0x140063e1c  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x140063e23  nop     dword ptr [rax+rax+00h]
0x140063e28  mov     rcx, rax
0x140063e2b  call    MpFileTimeToUlong64
0x140063e30  mov     [rsi+1Ch], rax
0x140063e34  xor     ecx, ecx
0x140063e36  mov     rax, [rsp+120h+var_D8]
0x140063e3b  mov     [rsi+24h], eax
0x140063e3e  movsd   xmm0, [rbp+20h+var_88]
0x140063e43  movsd   qword ptr [rsi+28h], xmm0
0x140063e48  mov     eax, [rbp+20h+var_80]
0x140063e4b  mov     [rsi+30h], eax
0x140063e4e  mov     rax, [rsp+120h+var_D0]
0x140063e53  mov     [rsi+34h], eax
0x140063e56  call    MpFileTimeToUlong64
0x140063e5b  mov     [rsi+38h], rax
0x140063e5f  test    r12, r12
0x140063e62  jz      short loc_140063E72
0x140063e64  movzx   eax, word ptr [r12]
0x140063e69  test    ax, ax
0x140063e6c  jnz     loc_14006413B
0x140063e72  mov     r9d, ebx
0x140063e75  mov     [rsp+120h+var_100], r13
0x140063e7a  xor     r8d, r8d
0x140063e7d  mov     edx, edi
0x140063e7f  mov     rcx, rsi
0x140063e82  call    MpAsyncSendNotification
0x140063e87  mov     rcx, rsi
0x140063e8a  call    MpAsyncDereferenceNotification
0x140063e8f  mov     r14, [rsp+120h+var_E0]
0x140063e94  jmp     loc_140063D0E
0x140063e99  xorps   xmm0, xmm0
0x140063e9c  xor     eax, eax
0x140063e9e  mov     [rbp+20h+var_48], rax
0x140063ea2  movups  [rbp+20h+var_78], xmm0
0x140063ea6  movups  [rbp+20h+var_68], xmm0
0x140063eaa  movups  [rbp+20h+var_58], xmm0
0x140063eae  test    r14, r14
0x140063eb1  jz      loc_140063D86
0x140063eb7  cmp     [rsp+120h+var_D8], rax
0x140063ebc  jz      loc_140063D86
0x140063ec2  mov     rax, [rsp+120h+var_D0]
0x140063ec7  test    rax, rax
0x140063eca  jz      loc_140063D86
0x140063ed0  xor     ecx, ecx
0x140063ed2  lea     rdx, [rsp+120h+var_E8]
0x140063ed7  mov     [rsp+120h+var_E8], rcx
0x140063edc  mov     rcx, rax
0x140063edf  call    MpGetThreadCreateTimeById
0x140063ee4  test    eax, eax
0x140063ee6  js      short loc_140063EFE
0x140063ee8  mov     rax, [rsp+120h+var_D0]
0x140063eed  mov     rcx, [rsp+120h+var_E8]
0x140063ef2  mov     dword ptr [rbp+20h+var_78], eax
0x140063ef5  call    MpFileTimeToUlong64
0x140063efa  mov     qword ptr [rbp+20h+var_78+4], rax
0x140063efe  mov     rcx, [rsp+120h+var_D8]
0x140063f03  lea     rdx, [rsp+120h+var_B0]
0x140063f08  xor     eax, eax
0x140063f0a  mov     [rsp+120h+var_B0], rax
0x140063f0f  call    MpGetThreadCreateTimeById
0x140063f14  test    eax, eax
0x140063f16  js      short loc_140063F34
0x140063f18  mov     rcx, [rsp+120h+var_B0]
0x140063f1d  xor     eax, eax
0x140063f1f  mov     qword ptr [rbp+20h+var_78+0Ch], rax
0x140063f23  mov     rax, [rsp+120h+var_D8]
0x140063f28  mov     dword ptr [rbp+20h+var_78+0Ch], eax
0x140063f2b  call    MpFileTimeToUlong64
0x140063f30  mov     qword ptr [rbp+20h+var_68], rax
0x140063f34  mov     eax, [r14+18h]
0x140063f38  mov     dword ptr [rbp+20h+var_68+8], eax
0x140063f3b  mov     rcx, [r14+20h]
0x140063f3f  call    MpFileTimeToUlong64
0x140063f44  mov     rcx, [rsp+120h+var_D0]
0x140063f49  lea     rdx, [rbp+20h+var_48]
0x140063f4d  mov     qword ptr [rbp+20h+var_68+0Ch], rax
0x140063f51  xor     eax, eax
0x140063f53  mov     qword ptr [rbp+20h+var_58+8], rax
0x140063f57  call    MpGetThreadWin32StartAddressById
0x140063f5c  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```

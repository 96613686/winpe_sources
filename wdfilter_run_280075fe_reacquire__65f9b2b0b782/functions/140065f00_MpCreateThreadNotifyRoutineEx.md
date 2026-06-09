# MpCreateThreadNotifyRoutineEx

- ea: `0x140065f00`
- end: `0x14006617f`
- name: `MpCreateThreadNotifyRoutineEx`
- size: `639`
- prototype: `void __stdcall(HANDLE ProcessId, HANDLE ThreadId, BOOLEAN Create)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400051bc`
- `0x1400118d0`
- `0x140030060`
- `0x140037820`
- `0x140056b50`
- `0x14006488c`
- `0x140065f00`
- `0x140066180`
- `0x14008bff8`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140065f7c`
- `ntoskrnl!PsGetProcessId` at `0x140065f7c`
- `ntoskrnl!PsInitialSystemProcess` at `0x140065f42`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140065f6a`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140065f6a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140066019`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140066019`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006600d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006600d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140065fb8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140065fb8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140065fa6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140065fa6`
- `ntoskrnl!IoGetCurrentProcess` at `0x140065f36`
- `ntoskrnl!IoGetCurrentProcess` at `0x140065f36`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400660b9`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400660b9`

## pseudocode

```c
void __fastcall MpCreateThreadNotifyRoutineEx(HANDLE ProcessId, HANDLE ThreadId, BOOLEAN Create)
{
  PCUNICODE_STRING v3; // r14
  struct _KPROCESS *CurrentProcess; // rax
  struct _KPROCESS *v6; // rsi
  LONGLONG TimeQuadPart; // r15
  unsigned __int64 v8; // rdi
  __int64 *v9; // rbp
  char *v10; // rbx
  volatile signed __int32 **v11; // r8
  volatile signed __int32 *i; // rax
  int v13; // eax
  bool v14; // zf
  int ProcessCommandLineByPointer; // eax
  int v16; // eax
  PCUNICODE_STRING String2; // [rsp+30h] [rbp-68h] BYREF
  int v18; // [rsp+38h] [rbp-60h]
  __int128 v19; // [rsp+40h] [rbp-58h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-48h] BYREF

  if ( Create )
  {
    v3 = 0;
    String2 = 0;
    CurrentProcess = IoGetCurrentProcess();
    v6 = CurrentProcess;
    if ( CurrentProcess != PsInitialSystemProcess )
    {
      TimeQuadPart = PsGetProcessCreateTimeQuadPart(CurrentProcess);
      v8 = (unsigned __int64)PsGetProcessId(v6);
      v9 = 0;
      if ( v8 )
      {
        v10 = (char *)MpProcessTable;
        KeEnterCriticalRegion();
        ExAcquireResourceSharedLite((PERESOURCE)(v10 + 8), 1u);
        v11 = (volatile signed __int32 **)(*((_QWORD *)MpProcessTable + 48) + 16 * ((v8 >> 2) & 0x7F));
        for ( i = *v11; i != (volatile signed __int32 *)v11; i = *(volatile signed __int32 **)i )
        {
          if ( v8 == *((_QWORD *)i + 2) && TimeQuadPart == *((_QWORD *)i + 3) )
          {
            _InterlockedIncrement(i + 10);
            v9 = (__int64 *)(i - 2);
            break;
          }
        }
        ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
        KeLeaveCriticalRegion();
        if ( v9 )
        {
          v13 = *((_DWORD *)v9 + 13);
          if ( (v13 & 0x400) != 0 )
          {
            v14 = (v9[7] & 0x20000000) == 0;
            *((_DWORD *)v9 + 13) = v13 & 0xFFFFFBFF;
            if ( !v14 )
            {
              ProcessCommandLineByPointer = MpGetProcessCommandLineByPointer(v6, &String2);
              v3 = String2;
              if ( ProcessCommandLineByPointer >= 0 )
              {
                if ( RtlCompareUnicodeString((PCUNICODE_STRING)v9[5], String2, 0) )
                {
                  v19 = 0;
                  MpGetPriorityInfo(0, 0, &v19);
                  String2 = 0;
                  v18 = 0;
                  GetMpUniquePidFromProcessId(ProcessId, &String2);
                  v20[0] = v9[5];
                  v20[1] = v3;
                  v16 = MpSendSyncMonitorNotification(
                          7,
                          (unsigned int)&String2,
                          (unsigned int)v20,
                          (unsigned int)&v19,
                          (__int64)(v9 + 7));
                  if ( v16 < 0
                    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                  {
                    _mm_lfence();
                    WPP_SF_qD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      41,
                      WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
                      KeGetCurrentThread(),
                      v16);
                  }
                }
              }
            }
          }
          MpReleaseProcessContext(v9);
          if ( v3 )
            MpFreeString(v3);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140065f00  test    r8b, r8b
0x140065f03  jz      locret_140066064
0x140065f09  push    r12
0x140065f0b  push    r14
0x140065f0d  sub     rsp, 88h
0x140065f14  mov     rax, cs:__security_cookie
0x140065f1b  xor     rax, rsp
0x140065f1e  mov     [rsp+98h+var_38], rax
0x140065f23  xor     r14d, r14d
0x140065f26  mov     [rsp+98h+var_18], rsi
0x140065f2e  mov     [rsp+98h+String2], r14
0x140065f33  mov     r12, rcx
0x140065f36  call    cs:__imp_IoGetCurrentProcess
0x140065f3d  nop     dword ptr [rax+rax+00h]
0x140065f42  mov     rcx, cs:__imp_PsInitialSystemProcess
0x140065f49  mov     rsi, rax
0x140065f4c  cmp     rax, [rcx]
0x140065f4f  jz      loc_140066044
0x140065f55  mov     [rsp+98h+arg_10], rbp
0x140065f5d  mov     rcx, rax; Process
0x140065f60  mov     [rsp+98h+var_20], rdi
0x140065f65  mov     [rsp+98h+var_28], r15
0x140065f6a  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x140065f71  nop     dword ptr [rax+rax+00h]
0x140065f76  mov     rcx, rsi; Process
0x140065f79  mov     r15, rax
0x140065f7c  call    cs:__imp_PsGetProcessId
0x140065f83  nop     dword ptr [rax+rax+00h]
0x140065f88  mov     rdi, rax
0x140065f8b  mov     ebp, r14d
0x140065f8e  test    rax, rax
0x140065f91  jz      loc_140066032
0x140065f97  mov     [rsp+98h+arg_8], rbx
0x140065f9f  mov     rbx, cs:MpProcessTable
0x140065fa6  call    cs:__imp_KeEnterCriticalRegion
0x140065fad  nop     dword ptr [rax+rax+00h]
0x140065fb2  mov     dl, 1; Wait
0x140065fb4  lea     rcx, [rbx+8]; Resource
0x140065fb8  call    cs:__imp_ExAcquireResourceSharedLite
0x140065fbf  nop     dword ptr [rax+rax+00h]
0x140065fc4  mov     rax, cs:MpProcessTable
0x140065fcb  mov     r8, rdi
0x140065fce  shr     r8, 2
0x140065fd2  and     r8d, 7Fh
0x140065fd6  shl     r8, 4
0x140065fda  add     r8, [rax+180h]
0x140065fe1  mov     rax, [r8]
0x140065fe4  cmp     rax, r8
0x140065fe7  jz      short loc_140066002
0x140065fe9  cmp     rdi, [rax+10h]
0x140065fed  jz      short loc_140065FF4
0x140065fef  mov     rax, [rax]
0x140065ff2  jmp     short loc_140065FE4
0x140065ff4  cmp     r15, [rax+18h]
0x140065ff8  jnz     short loc_140065FEF
0x140065ffa  lock inc dword ptr [rax+28h]
0x140065ffe  lea     rbp, [rax-8]
0x140066002  mov     rcx, cs:MpProcessTable
0x140066009  add     rcx, 8; Resource
0x14006600d  call    cs:__imp_ExReleaseResourceLite
0x140066014  nop     dword ptr [rax+rax+00h]
0x140066019  call    cs:__imp_KeLeaveCriticalRegion
0x140066020  nop     dword ptr [rax+rax+00h]
0x140066025  test    rbp, rbp
0x140066028  jnz     short loc_140066066
0x14006602a  mov     rbx, [rsp+98h+arg_8]
0x140066032  mov     rdi, [rsp+98h+var_20]
0x140066037  mov     rbp, [rsp+98h+arg_10]
0x14006603f  mov     r15, [rsp+98h+var_28]
0x140066044  mov     rsi, [rsp+98h+var_18]
0x14006604c  mov     rcx, [rsp+98h+var_38]
0x140066051  xor     rcx, rsp; StackCookie
0x140066054  call    __security_check_cookie
0x140066059  add     rsp, 88h
0x140066060  pop     r14
0x140066062  pop     r12
0x140066064  retn
0x140066066  mov     eax, [rbp+34h]
0x140066069  bt      eax, 0Ah
0x14006606d  jb      short loc_140066086
0x14006606f  mov     rcx, rbp
0x140066072  call    MpReleaseProcessContext
0x140066077  test    r14, r14
0x14006607a  jz      short loc_14006602A
0x14006607c  mov     rcx, r14
0x14006607f  call    MpFreeString
0x140066084  jmp     short loc_14006602A
0x140066086  btr     eax, 0Ah
0x14006608a  lea     rbx, [rbp+38h]
0x14006608e  test    dword ptr [rbx], 20000000h
0x140066094  mov     [rbp+34h], eax
0x140066097  jz      short loc_14006606F
0x140066099  lea     rdx, [rsp+98h+String2]
0x14006609e  mov     rcx, rsi
0x1400660a1  call    MpGetProcessCommandLineByPointer
0x1400660a6  mov     r14, [rsp+98h+String2]
0x1400660ab  test    eax, eax
0x1400660ad  js      short loc_14006606F
0x1400660af  mov     rcx, [rbp+28h]; String1
0x1400660b3  xor     r8d, r8d; CaseInSensitive
0x1400660b6  mov     rdx, r14; String2
0x1400660b9  call    cs:__imp_RtlCompareUnicodeString
0x1400660c0  nop     dword ptr [rax+rax+00h]
0x1400660c5  test    eax, eax
0x1400660c7  jz      short loc_14006606F
0x1400660c9  xorps   xmm0, xmm0
0x1400660cc  lea     r8, [rsp+98h+var_58]
0x1400660d1  xor     edx, edx
0x1400660d3  xor     ecx, ecx
0x1400660d5  movups  [rsp+98h+var_58], xmm0
0x1400660da  call    MpGetPriorityInfo
0x1400660df  xor     eax, eax
0x1400660e1  lea     rdx, [rsp+98h+String2]
0x1400660e6  mov     rcx, r12
0x1400660e9  mov     [rsp+98h+String2], rax
0x1400660ee  mov     [rsp+98h+var_60], eax
0x1400660f2  call    GetMpUniquePidFromProcessId
0x1400660f7  mov     rax, [rbp+28h]
0x1400660fb  lea     r9, [rsp+98h+var_58]
0x140066100  lea     r8, [rsp+98h+var_48]
0x140066105  mov     [rsp+98h+var_48], rax
0x14006610a  lea     rdx, [rsp+98h+String2]
0x14006610f  mov     [rsp+98h+var_40], r14
0x140066114  mov     ecx, 7
0x140066119  mov     [rsp+98h+var_78], rbx
0x14006611e  call    MpSendSyncMonitorNotification
0x140066123  test    eax, eax
0x140066125  jns     loc_14006606F
0x14006612b  mov     rcx, cs:WPP_GLOBAL_Control
0x140066132  lea     rdx, WPP_GLOBAL_Control
0x140066139  cmp     rcx, rdx
0x14006613c  jz      loc_14006606F
0x140066142  mov     ecx, [rcx+2Ch]
0x140066145  test    cl, 1
0x140066148  jz      loc_14006606F
0x14006614e  lfence
0x140066151  mov     r9, gs:188h
0x14006615a  lea     r8, WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids
0x140066161  mov     rcx, cs:WPP_GLOBAL_Control
0x140066168  mov     edx, 29h ; ')'
0x14006616d  mov     dword ptr [rsp+98h+var_78], eax
0x140066171  mov     rcx, [rcx+18h]
0x140066175  call    WPP_SF_qD
0x14006617a  jmp     loc_14006606F
```

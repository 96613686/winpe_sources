# SmpLoadSubSystem

- ea: `0x1400151e0`
- end: `0x1400153b5`
- name: `SmpLoadSubSystem`
- size: `469`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x140003450`
- `0x1400036d0`

## callees

- `0x1400010ec`
- `0x140001580`
- `0x140001e40`
- `0x140002bb0`
- `0x1400030f0`
- `0x140003114`
- `0x140003390`
- `0x1400053e0`
- `0x140008210`
- `0x140008f20`
- `0x14000d4c0`
- `0x1400151e0`
- `0x140017f58`
- `0x14001cc29`

## import_xrefs

- `ntdll!NtClose` at `0x140015354`
- `ntdll!NtClose` at `0x140015384`
- `ntdll!NtClose` at `0x140015354`
- `ntdll!NtClose` at `0x140015384`
- `ntdll!NtResumeThread` at `0x140015324`
- `ntdll!NtResumeThread` at `0x140015324`
- `ntdll!NtTerminateProcess` at `0x14001534a`
- `ntdll!NtTerminateProcess` at `0x14001534a`

## pseudocode

```c
__int64 __fastcall SmpLoadSubSystem(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, int a5, int a6)
{
  __int64 v10; // rbx
  unsigned int v11; // edi
  __int64 v12; // rdx
  __int64 KnownSubSys; // rax
  _QWORD *v14; // rsi
  __int64 v15; // r9
  int v16; // eax
  __int64 v17; // r9
  NTSTATUS v18; // eax
  int v20; // eax
  __int64 v21; // [rsp+40h] [rbp-79h] BYREF
  int v22; // [rsp+48h] [rbp-71h]
  __int128 v23; // [rsp+50h] [rbp-69h] BYREF
  HANDLE ThreadHandle; // [rsp+60h] [rbp-59h]
  __int64 v25; // [rsp+68h] [rbp-51h]
  __int64 v26; // [rsp+70h] [rbp-49h]
  int v27; // [rsp+98h] [rbp-21h]

  memset_0(&v23, 0, 0x68u);
  v22 = 0;
  v21 = 0;
  if ( (a6 & 0x10) == 0 )
  {
    KnownSubSys = SmpCreateKnownSubSys(0);
    v10 = 0;
    v14 = (_QWORD *)KnownSubSys;
    if ( !KnownSubSys )
    {
      if ( a1 )
        v10 = *(_QWORD *)(a1 + 8);
      v11 = -1073741801;
      v12 = 10498;
      goto LABEL_5;
    }
    *(_DWORD *)(KnownSubSys + 64) = a4;
    SmpWaitForSubSysStartup(a4, 0, 0, &v21);
    SmpAddKnownSubSys(&v21, v14);
    SmpUnlockKnownSubSysList(&v21);
    v16 = SmpExecuteImage(a1, a2, a3, v15, 0, a6 | 0x20u, &v23);
    v11 = v16;
    if ( v16 >= 0 )
    {
      v14[4] = *((_QWORD *)&v23 + 1);
      v14[6] = v25;
      v14[7] = v26;
      if ( v27 == 1
        || (v11 = SmpSbCreateSession(a4, (void *)0xFFFFFFFFFFFFFFFFLL, &v23, v17, 0), (v11 & 0x80000000) == 0) )
      {
        v18 = NtResumeThread(ThreadHandle, 0);
        v11 = v18;
        if ( v18 >= 0 )
        {
          NtClose(ThreadHandle);
          v20 = SmpWaitForSingleSubSys(v14);
          v11 = v20;
          if ( v20 < 0 )
          {
            SmLogFailureInt((unsigned int)"SmpLoadSubSystem", 10591, a4, 0, v20);
            goto LABEL_17;
          }
        }
        else
        {
          SmpLogFailure("SmpLoadSubSystem", 10570, (unsigned int)v18);
        }
      }
      NtTerminateProcess(*((HANDLE *)&v23 + 1), v11);
      NtClose(ThreadHandle);
    }
    else
    {
      SmpLogFailure("SmpLoadSubSystem", 10539, (unsigned int)v16);
    }
LABEL_17:
    SmpDeleteSubSys(v14);
    SmpDereferenceKnownSubSys(v14);
    return v11;
  }
  v10 = 0;
  if ( a1 )
    v10 = *(_QWORD *)(a1 + 8);
  v11 = -1073741772;
  v12 = 10482;
LABEL_5:
  SmpLogFailureString("SmpLoadSubSystem", v12, v10, v11);
  return v11;
}

```

## disassembly

```asm
0x1400151e0  push    rbp
0x1400151e2  push    rbx
0x1400151e3  push    rsi
0x1400151e4  push    rdi
0x1400151e5  push    r12
0x1400151e7  push    r13
0x1400151e9  push    r14
0x1400151eb  push    r15
0x1400151ed  lea     rbp, [rsp-0Fh]
0x1400151f2  sub     rsp, 0C8h
0x1400151f9  mov     r13, rdx
0x1400151fc  mov     r14d, r9d
0x1400151ff  xor     edx, edx; Val
0x140015201  mov     r12, r8
0x140015204  mov     rdi, rcx
0x140015207  lea     rcx, [rbp+47h+var_B0]; void *
0x14001520b  lea     r8d, [rdx+68h]; Size
0x14001520f  call    memset_0
0x140015214  mov     r15d, [rbp+47h+arg_28]
0x140015218  xor     eax, eax
0x14001521a  mov     [rbp+47h+var_BC], rax
0x14001521e  mov     [rbp-79h], rax
0x140015222  test    r15b, 10h
0x140015226  jz      short loc_140015254
0x140015228  xor     ebx, ebx
0x14001522a  test    rdi, rdi
0x14001522d  jz      short loc_140015233
0x14001522f  mov     rbx, [rdi+8]
0x140015233  mov     edi, 0C0000034h
0x140015238  mov     edx, 28F2h
0x14001523d  mov     r8, rbx
0x140015240  lea     rcx, aSmploadsubsyst; "SmpLoadSubSystem"
0x140015247  mov     r9d, edi
0x14001524a  call    SmpLogFailureString
0x14001524f  jmp     loc_14001536A
0x140015254  xor     ecx, ecx
0x140015256  call    SmpCreateKnownSubSys
0x14001525b  xor     ebx, ebx
0x14001525d  mov     rsi, rax
0x140015260  test    rax, rax
0x140015263  jnz     short loc_14001527A
0x140015265  test    rdi, rdi
0x140015268  jz      short loc_14001526E
0x14001526a  mov     rbx, [rdi+8]
0x14001526e  mov     edi, 0C0000017h
0x140015273  mov     edx, 2902h
0x140015278  jmp     short loc_14001523D
0x14001527a  lea     r9, [rbp+47h+var_C0]
0x14001527e  mov     [rax+40h], r14d
0x140015282  xor     r8d, r8d
0x140015285  xor     edx, edx
0x140015287  mov     ecx, r14d
0x14001528a  call    SmpWaitForSubSysStartup
0x14001528f  mov     rdx, rsi
0x140015292  lea     rcx, [rbp+47h+var_C0]
0x140015296  call    SmpAddKnownSubSys
0x14001529b  lea     rcx, [rbp+47h+var_C0]
0x14001529f  call    SmpUnlockKnownSubSysList
0x1400152a4  lea     rax, [rbp+47h+var_B0]
0x1400152a8  or      r15d, 20h
0x1400152ac  mov     [rsp+100h+var_D0], rax
0x1400152b1  mov     r8, r12
0x1400152b4  mov     [rsp+100h+var_D8], r15d
0x1400152b9  mov     rdx, r13
0x1400152bc  mov     rcx, rdi
0x1400152bf  mov     [rsp+100h+var_E0], rbx
0x1400152c4  call    SmpExecuteImage
0x1400152c9  mov     edi, eax
0x1400152cb  test    eax, eax
0x1400152cd  jns     short loc_1400152E5
0x1400152cf  mov     r8d, eax
0x1400152d2  lea     rcx, aSmploadsubsyst; "SmpLoadSubSystem"
0x1400152d9  mov     edx, 292Bh
0x1400152de  call    SmpLogFailure
0x1400152e3  jmp     short loc_14001535A
0x1400152e5  mov     rax, [rbp+47h+ProcessHandle]
0x1400152e9  mov     [rsi+20h], rax
0x1400152ed  mov     rax, [rbp+47h+var_98]
0x1400152f1  mov     [rsi+30h], rax
0x1400152f5  mov     rax, [rbp+47h+var_90]
0x1400152f9  mov     [rsi+38h], rax
0x1400152fd  cmp     [rbp+47h+var_68], 1
0x140015301  jz      short loc_14001531E
0x140015303  lea     r8, [rbp+47h+var_B0]
0x140015307  mov     [rsp+100h+var_E0], rbx
0x14001530c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140015310  mov     ecx, r14d
0x140015313  call    SmpSbCreateSession
0x140015318  mov     edi, eax
0x14001531a  test    eax, eax
0x14001531c  js      short loc_140015344
0x14001531e  mov     rcx, [rbp+47h+ThreadHandle]; ThreadHandle
0x140015322  xor     edx, edx; SuspendCount
0x140015324  call    cs:__imp_NtResumeThread
0x14001532a  mov     edi, eax
0x14001532c  test    eax, eax
0x14001532e  jns     short loc_140015380
0x140015330  mov     r8d, eax
0x140015333  lea     rcx, aSmploadsubsyst; "SmpLoadSubSystem"
0x14001533a  mov     edx, 294Ah
0x14001533f  call    SmpLogFailure
0x140015344  mov     rcx, [rbp+47h+ProcessHandle]; ProcessHandle
0x140015348  mov     edx, edi; ExitStatus
0x14001534a  call    cs:__imp_NtTerminateProcess
0x140015350  mov     rcx, [rbp+47h+ThreadHandle]; Handle
0x140015354  call    cs:__imp_NtClose
0x14001535a  mov     rcx, rsi; BaseAddress
0x14001535d  call    SmpDeleteSubSys
0x140015362  mov     rcx, rsi; BaseAddress
0x140015365  call    SmpDereferenceKnownSubSys
0x14001536a  mov     eax, edi
0x14001536c  add     rsp, 0C8h
0x140015373  pop     r15
0x140015375  pop     r14
0x140015377  pop     r13
0x140015379  pop     r12
0x14001537b  pop     rdi
0x14001537c  pop     rsi
0x14001537d  pop     rbx
0x14001537e  pop     rbp
0x14001537f  retn
0x140015380  mov     rcx, [rbp+47h+ThreadHandle]; Handle
0x140015384  call    cs:__imp_NtClose
0x14001538a  mov     rcx, rsi
0x14001538d  call    SmpWaitForSingleSubSys
0x140015392  mov     edi, eax
0x140015394  test    eax, eax
0x140015396  jns     short loc_140015344
0x140015398  mov     r8, r14
0x14001539b  mov     dword ptr [rsp+100h+var_E0], eax
0x14001539f  xor     r9d, r9d
0x1400153a2  lea     rcx, aSmploadsubsyst; "SmpLoadSubSystem"
0x1400153a9  mov     edx, 295Fh
0x1400153ae  call    SmLogFailureInt
0x1400153b3  jmp     short loc_14001535A
```

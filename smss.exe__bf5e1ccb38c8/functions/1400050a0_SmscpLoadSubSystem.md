# SmscpLoadSubSystem

- ea: `0x1400050a0`
- end: `0x1400053d5`
- name: `SmscpLoadSubSystem`
- size: `821`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140003450`
- `0x1400036d0`

## callees

- `0x1400010ec`
- `0x1400050a0`
- `0x1400053e0`
- `0x140008e60`
- `0x14000d4c0`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x140005253`
- `ntdll!EtwEventWrite` at `0x1400052b2`
- `ntdll!EtwEventWrite` at `0x140005253`
- `ntdll!EtwEventWrite` at `0x1400052b2`
- `ntdll!EtwEventEnabled` at `0x140005103`
- `ntdll!EtwEventEnabled` at `0x140005220`
- `ntdll!EtwEventEnabled` at `0x140005103`
- `ntdll!EtwEventEnabled` at `0x140005220`
- `ntdll!NtSetInformationProcess` at `0x1400051e2`
- `ntdll!NtSetInformationProcess` at `0x1400051e2`
- `ntdll!NtResumeThread` at `0x14000516e`
- `ntdll!NtResumeThread` at `0x14000516e`
- `ntdll!NtTerminateProcess` at `0x14000536f`
- `ntdll!NtTerminateProcess` at `0x14000536f`
- `ntdll!NtWaitForMultipleObjects` at `0x1400051ac`
- `ntdll!NtWaitForMultipleObjects` at `0x1400051ac`
- `ntdll!NtQueryEvent` at `0x140005398`
- `ntdll!NtQueryEvent` at `0x140005398`

## pseudocode

```c
__int64 __fastcall SmscpLoadSubSystem(unsigned __int16 *a1, __int64 a2, __int64 a3, int a4, int a5)
{
  __int64 v9; // r9
  int v10; // eax
  int v11; // ebx
  __int64 v12; // rcx
  NTSTATUS v13; // eax
  unsigned __int16 v15; // ax
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  __int16 v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 EventInformation; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Object[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v24; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE ThreadHandle; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+78h] [rbp-88h]
  int v27; // [rsp+A8h] [rbp-58h]
  _QWORD v28[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v29[5]; // [rsp+E0h] [rbp-20h] BYREF
  int v30; // [rsp+108h] [rbp+8h]
  int v31; // [rsp+10Ch] [rbp+Ch]

  memset_0(&v24, 0, 0x68u);
  LODWORD(EventInformation) = a4;
  *(_OWORD *)Object = 0;
  if ( SmpTraceHandle && EtwEventEnabled(SmpTraceHandle, &SmssEvt_LoadSubsystem_Start) )
  {
    v15 = *a1;
    v30 = *a1;
    v21 = v15 >> 1;
    v29[0] = &EventInformation;
    v29[2] = &v21;
    v29[4] = *((_QWORD *)a1 + 1);
    v29[1] = 4;
    v29[3] = 2;
    v31 = 0;
    EtwEventWrite(SmpTraceHandle, &SmssEvt_LoadSubsystem_Start, 3, v29);
  }
  if ( (a5 & 0x10) != 0 )
  {
    v11 = -1073741772;
    if ( a1 )
      v16 = *((_QWORD *)a1 + 1);
    else
      v16 = 0;
    SmpLogFailureString("SmscpLoadSubSystem", 1298, v16, 3221225524LL);
    goto LABEL_11;
  }
  v10 = SmpExecuteImage((__int64)a1, a2, a3, v9, 0, a5 | 0x20u, &v24);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v12 = v26;
    *((_QWORD *)SmscpSharedWindow + 1) = v26;
    if ( v27 == 1 )
    {
      v11 = NtResumeThread(ThreadHandle, 0);
      if ( v11 >= 0 )
      {
LABEL_8:
        Object[0] = SmscpSubsystemRegistered;
        Object[1] = *((HANDLE *)&v24 + 1);
        v13 = NtWaitForMultipleObjects(2u, Object, WaitAny, 0, 0);
        v11 = v13;
        if ( v13 >= 0 )
        {
          if ( v13 != 1
            || (EventInformation = 0,
                NtQueryEvent(SmscpSubsystemRegistered, EventBasicInformation, &EventInformation, 8u, 0),
                HIDWORD(EventInformation)) )
          {
            *((_QWORD *)SmscpSharedWindow + 1) = 0;
            NtSetInformationProcess(*((HANDLE *)&v24 + 1), (PROCESSINFOCLASS)68, 0, 0);
            v11 = 0;
          }
          else
          {
            v11 = -1073741823;
            if ( a3 )
              v20 = *(_QWORD *)(a3 + 8);
            else
              v20 = 0;
            SmpLogFailureString("SmscpLoadSubSystem", 1411, v20, 3221225473LL);
          }
          goto LABEL_11;
        }
        if ( a3 )
          v18 = *(_QWORD *)(a3 + 8);
        else
          v18 = 0;
        v19 = 1385;
        goto LABEL_31;
      }
      v17 = 1357;
    }
    else
    {
      v11 = SmExecPgmEx(v12, &v24);
      if ( v11 >= 0 )
        goto LABEL_8;
      v17 = 1348;
    }
    SmpLogFailure("SmscpLoadSubSystem", v17, (unsigned int)v11);
    if ( a3 )
      v18 = *(_QWORD *)(a3 + 8);
    else
      v18 = 0;
    v19 = 1363;
LABEL_31:
    SmpLogFailureString("SmscpLoadSubSystem", v19, v18, (unsigned int)v11);
    NtTerminateProcess(*((HANDLE *)&v24 + 1), v11);
    goto LABEL_11;
  }
  SmpLogFailure("SmscpLoadSubSystem", 1316, (unsigned int)v10);
LABEL_11:
  LODWORD(EventInformation) = v11;
  if ( SmpTraceHandle && EtwEventEnabled(SmpTraceHandle, &SmssEvt_LoadSubsystem_Stop) )
  {
    v28[0] = &EventInformation;
    v28[1] = 4;
    EtwEventWrite(SmpTraceHandle, &SmssEvt_LoadSubsystem_Stop, 1, v28);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400050a0  push    rbp
0x1400050a2  push    rbx
0x1400050a3  push    rsi
0x1400050a4  push    rdi
0x1400050a5  push    r14
0x1400050a7  push    r15
0x1400050a9  lea     rbp, [rsp-28h]
0x1400050ae  sub     rsp, 128h
0x1400050b5  mov     rax, cs:__security_cookie
0x1400050bc  xor     rax, rsp
0x1400050bf  mov     [rbp+50h+var_40], rax
0x1400050c3  mov     r14, r8
0x1400050c6  mov     rsi, rdx
0x1400050c9  mov     rdi, rcx
0x1400050cc  xor     edx, edx; Val
0x1400050ce  mov     r8d, 68h ; 'h'; Size
0x1400050d4  lea     rcx, [rsp+150h+var_F0]; void *
0x1400050d9  mov     ebx, r9d
0x1400050dc  call    memset_0
0x1400050e1  mov     rcx, cs:SmpTraceHandle; RegHandle
0x1400050e8  xor     r15d, r15d
0x1400050eb  mov     dword ptr [rsp+150h+EventInformation], ebx
0x1400050ef  xorps   xmm0, xmm0
0x1400050f2  movups  xmmword ptr [rsp+150h+Object], xmm0
0x1400050f7  test    rcx, rcx
0x1400050fa  jz      short loc_140005111
0x1400050fc  lea     rdx, SmssEvt_LoadSubsystem_Start; EventDescriptor
0x140005103  call    cs:__imp_EtwEventEnabled
0x140005109  test    al, al
0x14000510b  jnz     loc_14000525B
0x140005111  mov     eax, [rbp+50h+arg_20]
0x140005117  test    al, 10h
0x140005119  jnz     loc_1400052BD
0x14000511f  lea     rcx, [rsp+150h+var_F0]
0x140005124  or      eax, 20h
0x140005127  mov     [rsp+150h+var_120], rcx
0x14000512c  mov     r8, r14
0x14000512f  mov     [rsp+150h+var_128], eax
0x140005133  mov     rcx, rdi
0x140005136  mov     rdx, rsi
0x140005139  mov     [rsp+150h+Time], r15
0x14000513e  call    SmpExecuteImage
0x140005143  mov     ebx, eax
0x140005145  test    eax, eax
0x140005147  js      loc_1400052E9
0x14000514d  mov     rax, cs:SmscpSharedWindow
0x140005154  mov     rcx, [rsp+150h+var_D8]
0x140005159  mov     [rax+8], rcx
0x14000515d  cmp     [rbp+50h+var_A8], 1
0x140005161  jnz     loc_140005302
0x140005167  mov     rcx, [rsp+150h+ThreadHandle]; ThreadHandle
0x14000516c  xor     edx, edx; SuspendCount
0x14000516e  call    cs:__imp_NtResumeThread
0x140005174  mov     ebx, eax
0x140005176  test    eax, eax
0x140005178  js      loc_14000531D
0x14000517e  mov     rax, cs:SmscpSubsystemRegistered
0x140005185  lea     rdx, [rsp+150h+Object]; Object
0x14000518a  mov     [rsp+150h+Object], rax
0x14000518f  xor     r9d, r9d; Alertable
0x140005192  mov     rax, [rsp+150h+ProcessHandle]
0x140005197  mov     r8d, 1; WaitType
0x14000519d  mov     ecx, 2; Count
0x1400051a2  mov     [rsp+150h+Object+8], rax
0x1400051a7  mov     [rsp+150h+Time], r15; Time
0x1400051ac  call    cs:__imp_NtWaitForMultipleObjects
0x1400051b2  mov     ebx, eax
0x1400051b4  test    eax, eax
0x1400051b6  js      loc_140005346
0x1400051bc  cmp     eax, 1
0x1400051bf  jz      loc_14000537A
0x1400051c5  mov     rax, cs:SmscpSharedWindow
0x1400051cc  xor     ecx, ecx
0x1400051ce  xor     r9d, r9d; ProcessInformationLength
0x1400051d1  xor     r8d, r8d; ProcessInformation
0x1400051d4  mov     edx, 44h ; 'D'; ProcessInformationClass
0x1400051d9  mov     [rax+8], rcx
0x1400051dd  mov     rcx, [rsp+150h+ProcessHandle]; ProcessHandle
0x1400051e2  call    cs:__imp_NtSetInformationProcess
0x1400051e8  mov     ebx, r15d
0x1400051eb  mov     rcx, cs:SmpTraceHandle; RegHandle
0x1400051f2  mov     dword ptr [rsp+150h+EventInformation], ebx
0x1400051f6  test    rcx, rcx
0x1400051f9  jnz     short loc_140005219
0x1400051fb  mov     eax, ebx
0x1400051fd  mov     rcx, [rbp+50h+var_40]
0x140005201  xor     rcx, rsp; StackCookie
0x140005204  call    __security_check_cookie
0x140005209  add     rsp, 128h
0x140005210  pop     r15
0x140005212  pop     r14
0x140005214  pop     rdi
0x140005215  pop     rsi
0x140005216  pop     rbx
0x140005217  pop     rbp
0x140005218  retn
0x140005219  lea     rdx, SmssEvt_LoadSubsystem_Stop; EventDescriptor
0x140005220  call    cs:__imp_EtwEventEnabled
0x140005226  test    al, al
0x140005228  jz      short loc_1400051FB
0x14000522a  mov     rcx, cs:SmpTraceHandle
0x140005231  lea     rax, [rsp+150h+EventInformation]
0x140005236  lea     r9, [rbp+50h+var_80]
0x14000523a  mov     [rbp+50h+var_80], rax
0x14000523e  mov     r8d, 1
0x140005244  mov     [rbp+50h+var_78], 4
0x14000524c  lea     rdx, SmssEvt_LoadSubsystem_Stop
0x140005253  call    cs:__imp_EtwEventWrite
0x140005259  jmp     short loc_1400051FB
0x14000525b  movzx   ecx, word ptr [rdi]
0x14000525e  lea     r9, [rbp+50h+var_70]
0x140005262  movzx   eax, cx
0x140005265  mov     [rbp+50h+var_48], ecx
0x140005268  mov     rcx, cs:SmpTraceHandle
0x14000526f  lea     rdx, SmssEvt_LoadSubsystem_Start
0x140005276  shr     ax, 1
0x140005279  mov     r8d, 3
0x14000527f  mov     [rsp+150h+var_110], ax
0x140005284  lea     rax, [rsp+150h+EventInformation]
0x140005289  mov     [rbp+50h+var_70], rax
0x14000528d  lea     rax, [rsp+150h+var_110]
0x140005292  mov     [rbp+50h+var_60], rax
0x140005296  mov     rax, [rdi+8]
0x14000529a  mov     [rbp+50h+var_50], rax
0x14000529e  mov     [rbp+50h+var_68], 4
0x1400052a6  mov     [rbp+50h+var_58], 2
0x1400052ae  mov     [rbp+50h+var_44], r15d
0x1400052b2  call    cs:__imp_EtwEventWrite
0x1400052b8  jmp     loc_140005111
0x1400052bd  mov     ebx, 0C0000034h
0x1400052c2  test    rdi, rdi
0x1400052c5  jz      short loc_1400052CD
0x1400052c7  mov     r8, [rdi+8]
0x1400052cb  jmp     short loc_1400052D0
0x1400052cd  mov     r8, r15
0x1400052d0  mov     r9d, ebx
0x1400052d3  lea     rcx, aSmscploadsubsy; "SmscpLoadSubSystem"
0x1400052da  mov     edx, 512h
0x1400052df  call    SmpLogFailureString
0x1400052e4  jmp     loc_1400051EB
0x1400052e9  mov     r8d, eax
0x1400052ec  lea     rcx, aSmscploadsubsy; "SmscpLoadSubSystem"
0x1400052f3  mov     edx, 524h
0x1400052f8  call    SmpLogFailure
0x1400052fd  jmp     loc_1400051EB
0x140005302  lea     rdx, [rsp+150h+var_F0]
0x140005307  call    SmExecPgmEx
0x14000530c  mov     ebx, eax
0x14000530e  test    eax, eax
0x140005310  jns     loc_14000517E
0x140005316  mov     edx, 544h
0x14000531b  jmp     short loc_140005322
0x14000531d  mov     edx, 54Dh
0x140005322  mov     r8d, ebx
0x140005325  lea     rcx, aSmscploadsubsy; "SmscpLoadSubSystem"
0x14000532c  call    SmpLogFailure
0x140005331  test    r14, r14
0x140005334  jz      short loc_14000533C
0x140005336  mov     r8, [r14+8]
0x14000533a  jmp     short loc_14000533F
0x14000533c  mov     r8, r15
0x14000533f  mov     edx, 553h
0x140005344  jmp     short loc_140005359
0x140005346  test    r14, r14
0x140005349  jz      short loc_140005351
0x14000534b  mov     r8, [r14+8]
0x14000534f  jmp     short loc_140005354
0x140005351  mov     r8, r15
0x140005354  mov     edx, 569h
0x140005359  mov     r9d, ebx
0x14000535c  lea     rcx, aSmscploadsubsy; "SmscpLoadSubSystem"
0x140005363  call    SmpLogFailureString
0x140005368  mov     rcx, [rsp+150h+ProcessHandle]; ProcessHandle
0x14000536d  mov     edx, ebx; ExitStatus
0x14000536f  call    cs:__imp_NtTerminateProcess
0x140005375  jmp     loc_1400051EB
0x14000537a  mov     rcx, cs:SmscpSubsystemRegistered; EventHandle
0x140005381  lea     r8, [rsp+150h+EventInformation]; EventInformation
0x140005386  mov     r9d, 8; EventInformationLength
0x14000538c  mov     [rsp+150h+EventInformation], r15
0x140005391  xor     edx, edx; EventInformationClass
0x140005393  mov     [rsp+150h+Time], r15; ReturnLength
0x140005398  call    cs:__imp_NtQueryEvent
0x14000539e  cmp     dword ptr [rsp+150h+EventInformation+4], r15d
0x1400053a3  jnz     loc_1400051C5
0x1400053a9  mov     ebx, 0C0000001h
0x1400053ae  test    r14, r14
0x1400053b1  jz      short loc_1400053B9
0x1400053b3  mov     r8, [r14+8]
0x1400053b7  jmp     short loc_1400053BC
0x1400053b9  mov     r8, r15
0x1400053bc  mov     r9d, ebx
0x1400053bf  lea     rcx, aSmscploadsubsy; "SmscpLoadSubSystem"
0x1400053c6  mov     edx, 583h
0x1400053cb  call    SmpLogFailureString
0x1400053d0  jmp     loc_1400051EB
```

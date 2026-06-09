# KeyMgrIntfGroupKeyTimeoutWorker(void *)

- ea: `0x180065fb0`
- end: `0x18006623b`
- name: `?KeyMgrIntfGroupKeyTimeoutWorker@@YAKPEAX@Z`
- size: `651`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180011030`
- `0x180013bc0`
- `0x1800169c0`
- `0x18001b2b0`
- `0x18001df24`
- `0x18001df84`
- `0x180023554`
- `0x180040f84`
- `0x1800428e0`
- `0x180065fb0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18006610e`
- `MobileNetworking!ReleaseWriteLock` at `0x1800661d1`
- `MobileNetworking!ReleaseWriteLock` at `0x18006610e`
- `MobileNetworking!ReleaseWriteLock` at `0x1800661d1`
- `MobileNetworking!AcquireWriteLock` at `0x180066143`
- `MobileNetworking!AcquireWriteLock` at `0x180066143`

## pseudocode

```c
__int64 __fastcall KeyMgrIntfGroupKeyTimeoutWorker(char *Parameter, unsigned int a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  int v5; // ebp
  _DWORD *v6; // rsi
  _QWORD *v7; // rcx
  __int64 v8; // r9
  __int64 v9; // rdx
  unsigned int started; // eax
  unsigned int v11; // ecx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 276, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids);
  NetTraceBeginContextActivity(Parameter, a2);
  v3 = SecMgrLockAndCheckAdapterDeleted((struct MSMSEC_INTF_CONTEXT *)Parameter);
  v4 = v3;
  if ( v3 )
  {
    v5 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 277, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids, v3);
    v6 = Parameter + 3264;
    goto LABEL_26;
  }
  v6 = Parameter + 3264;
  v5 = 1;
  if ( *((_DWORD *)Parameter + 816) != 3 )
  {
    if ( *v6 != 4 )
    {
      v4 = 0;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
        goto LABEL_26;
      v8 = (unsigned int)*v6;
      v9 = 278;
LABEL_25:
      WPP_SF_d(v7[7], v9, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids, v8);
      goto LABEL_26;
    }
    InstallGroupKey((struct MSMSEC_INTF_CONTEXT *)Parameter);
    started = MSMSecStartTimer(
                *((void **)Parameter + 407),
                (void *)3,
                *((_DWORD *)Parameter + 830),
                "KeyMgrIntfGroupKeyTimeoutWorker");
    v4 = started;
    if ( !started )
      goto LABEL_26;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_26;
    v9 = 279;
LABEL_24:
    v8 = started;
    goto LABEL_25;
  }
  if ( !GenerateRsnGroupKeys((struct MSMSEC_INTF_CONTEXT *)Parameter, 1) )
  {
    TraceAdapterId(*((_DWORD *)Parameter + 624), "<<< Unlocking <<<");
    ReleaseWriteLock(Parameter, Parameter + 2512, "KeyMgrIntfGroupKeyTimeoutWorker", 3582);
    KeyMgrIntfUpdateGroupKey((struct MSMSEC_INTF_CONTEXT *)Parameter);
    TraceAdapterId(*((_DWORD *)Parameter + 624), ">>> Locking >>>");
    AcquireWriteLock(Parameter, Parameter + 2512, "KeyMgrIntfGroupKeyTimeoutWorker", 3584);
  }
  started = MSMSecStartTimer(*((void **)Parameter + 407), (void *)4, 0x2710u, "KeyMgrIntfGroupKeyTimeoutWorker");
  v4 = started;
  if ( started )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v9 = 280;
      goto LABEL_24;
    }
  }
LABEL_26:
  NetTraceEndContextActivity(Parameter, 0x10u);
  if ( v5 )
  {
    v11 = *((_DWORD *)Parameter + 624);
    *v6 = 0;
    TraceAdapterId(v11, "<<< Unlocking <<<");
    ReleaseWriteLock(Parameter, Parameter + 2512, "KeyMgrIntfGroupKeyTimeoutWorker", 3602);
  }
  TraceAdapterId(*((_DWORD *)Parameter + 624), "<<< Derefing <<<");
  SecMgrDerefAdapterEx((struct MSMSEC_INTF_CONTEXT *)Parameter, "KeyMgrIntfGroupKeyTimeoutWorker", 3608);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 281, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180065fb0  push    rbx
0x180065fb2  push    rbp
0x180065fb3  push    rsi
0x180065fb4  push    rdi
0x180065fb5  push    r12
0x180065fb7  push    r14
0x180065fb9  push    r15
0x180065fbb  sub     rsp, 20h
0x180065fbf  mov     rdi, rcx
0x180065fc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180065fc9  lea     r14, WPP_GLOBAL_Control
0x180065fd0  lea     r15, WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids
0x180065fd7  cmp     rcx, r14
0x180065fda  jz      short loc_180065FF6
0x180065fdc  test    dword ptr [rcx+44h], 100h
0x180065fe3  jz      short loc_180065FF6
0x180065fe5  mov     rcx, [rcx+38h]
0x180065fe9  mov     edx, 114h
0x180065fee  mov     r8, r15
0x180065ff1  call    WPP_SF_
0x180065ff6  mov     rcx, rdi; void *
0x180065ff9  call    ?NetTraceBeginContextActivity@@YAXPEAXI@Z; NetTraceBeginContextActivity(void *,uint)
0x180065ffe  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180066001  call    ?SecMgrLockAndCheckAdapterDeleted@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrLockAndCheckAdapterDeleted(MSMSEC_INTF_CONTEXT *)
0x180066006  lea     r12, aKeymgrintfgrou; "KeyMgrIntfGroupKeyTimeoutWorker"
0x18006600d  mov     ebx, eax
0x18006600f  test    eax, eax
0x180066011  jz      short loc_180066047
0x180066013  xor     ebp, ebp
0x180066015  mov     rcx, cs:WPP_GLOBAL_Control
0x18006601c  cmp     rcx, r14
0x18006601f  jz      short loc_18006603B
0x180066021  test    byte ptr [rcx+44h], 1
0x180066025  jz      short loc_18006603B
0x180066027  mov     rcx, [rcx+38h]
0x18006602b  mov     edx, 115h
0x180066030  mov     r9d, eax
0x180066033  mov     r8, r15
0x180066036  call    WPP_SF_d
0x18006603b  lea     rsi, [rdi+0CC0h]
0x180066042  jmp     loc_180066195
0x180066047  lea     rsi, [rdi+0CC0h]
0x18006604e  mov     ebp, 1
0x180066053  cmp     dword ptr [rsi], 3
0x180066056  jz      short loc_1800660D7
0x180066058  cmp     dword ptr [rsi], 4
0x18006605b  jz      short loc_180066086
0x18006605d  xor     ebx, ebx
0x18006605f  mov     rcx, cs:WPP_GLOBAL_Control
0x180066066  cmp     rcx, r14
0x180066069  jz      loc_180066195
0x18006606f  test    byte ptr [rcx+44h], 2
0x180066073  jz      loc_180066195
0x180066079  mov     r9d, [rsi]
0x18006607c  mov     edx, 116h
0x180066081  jmp     loc_180066189
0x180066086  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180066089  call    ?InstallGroupKey@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z; InstallGroupKey(MSMSEC_INTF_CONTEXT *)
0x18006608e  mov     r8d, [rdi+0CF8h]; unsigned int
0x180066095  mov     r9, r12; char *
0x180066098  mov     rcx, [rdi+0CB8h]; void *
0x18006609f  mov     edx, 3; void *
0x1800660a4  call    ?MSMSecStartTimer@@YAKPEAX0KPEBD@Z; MSMSecStartTimer(void *,void *,ulong,char const *)
0x1800660a9  mov     ebx, eax
0x1800660ab  test    eax, eax
0x1800660ad  jz      loc_180066195
0x1800660b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800660ba  cmp     rcx, r14
0x1800660bd  jz      loc_180066195
0x1800660c3  test    [rcx+44h], bpl
0x1800660c7  jz      loc_180066195
0x1800660cd  mov     edx, 117h
0x1800660d2  jmp     loc_180066186
0x1800660d7  mov     dl, bpl; bool
0x1800660da  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x1800660dd  call    ?GenerateRsnGroupKeys@@YAKPEAUMSMSEC_INTF_CONTEXT@@_N@Z; GenerateRsnGroupKeys(MSMSEC_INTF_CONTEXT *,bool)
0x1800660e2  test    eax, eax
0x1800660e4  jnz     short loc_18006614F
0x1800660e6  mov     ecx, [rdi+9C0h]; unsigned int
0x1800660ec  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800660f3  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800660f8  lea     rbx, [rdi+9D0h]
0x1800660ff  mov     r9d, 0DFEh
0x180066105  mov     rdx, rbx
0x180066108  mov     r8, r12
0x18006610b  mov     rcx, rdi
0x18006610e  call    cs:__imp_ReleaseWriteLock
0x180066115  nop     dword ptr [rax+rax+00h]
0x18006611a  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x18006611d  call    ?KeyMgrIntfUpdateGroupKey@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z; KeyMgrIntfUpdateGroupKey(MSMSEC_INTF_CONTEXT *)
0x180066122  mov     ecx, [rdi+9C0h]; unsigned int
0x180066128  lea     rdx, aLocking; ">>> Locking >>>"
0x18006612f  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180066134  mov     r9d, 0E00h
0x18006613a  mov     r8, r12
0x18006613d  mov     rdx, rbx
0x180066140  mov     rcx, rdi
0x180066143  call    cs:__imp_AcquireWriteLock
0x18006614a  nop     dword ptr [rax+rax+00h]
0x18006614f  mov     rcx, [rdi+0CB8h]; void *
0x180066156  mov     r9, r12; char *
0x180066159  mov     edx, 4; void *
0x18006615e  mov     r8d, 2710h; unsigned int
0x180066164  call    ?MSMSecStartTimer@@YAKPEAX0KPEBD@Z; MSMSecStartTimer(void *,void *,ulong,char const *)
0x180066169  mov     ebx, eax
0x18006616b  test    eax, eax
0x18006616d  jz      short loc_180066195
0x18006616f  mov     rcx, cs:WPP_GLOBAL_Control
0x180066176  cmp     rcx, r14
0x180066179  jz      short loc_180066195
0x18006617b  test    [rcx+44h], bpl
0x18006617f  jz      short loc_180066195
0x180066181  mov     edx, 118h
0x180066186  mov     r9d, eax
0x180066189  mov     rcx, [rcx+38h]
0x18006618d  mov     r8, r15
0x180066190  call    WPP_SF_d
0x180066195  mov     edx, 10h; unsigned int
0x18006619a  mov     rcx, rdi; void *
0x18006619d  call    ?NetTraceEndContextActivity@@YAXPEAXI@Z; NetTraceEndContextActivity(void *,uint)
0x1800661a2  test    ebp, ebp
0x1800661a4  jz      short loc_1800661DD
0x1800661a6  mov     ecx, [rdi+9C0h]; unsigned int
0x1800661ac  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800661b3  mov     dword ptr [rsi], 0
0x1800661b9  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800661be  lea     rdx, [rdi+9D0h]
0x1800661c5  mov     r9d, 0E12h
0x1800661cb  mov     r8, r12
0x1800661ce  mov     rcx, rdi
0x1800661d1  call    cs:__imp_ReleaseWriteLock
0x1800661d8  nop     dword ptr [rax+rax+00h]
0x1800661dd  mov     ecx, [rdi+9C0h]; unsigned int
0x1800661e3  lea     rdx, aDerefing; "<<< Derefing <<<"
0x1800661ea  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800661ef  mov     r8d, 0E18h; int
0x1800661f5  mov     rdx, r12; char *
0x1800661f8  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x1800661fb  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180066200  mov     rcx, cs:WPP_GLOBAL_Control
0x180066207  cmp     rcx, r14
0x18006620a  jz      short loc_180066229
0x18006620c  test    dword ptr [rcx+44h], 100h
0x180066213  jz      short loc_180066229
0x180066215  mov     rcx, [rcx+38h]
0x180066219  mov     edx, 119h
0x18006621e  mov     r9d, ebx
0x180066221  mov     r8, r15
0x180066224  call    WPP_SF_d
0x180066229  mov     eax, ebx
0x18006622b  add     rsp, 20h
0x18006622f  pop     r15
0x180066231  pop     r14
0x180066233  pop     r12
0x180066235  pop     rdi
0x180066236  pop     rsi
0x180066237  pop     rbp
0x180066238  pop     rbx
0x180066239  retn
```

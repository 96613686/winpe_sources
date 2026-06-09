# MSMSecStopSecurity

- ea: `0x180015300`
- end: `0x1800155f9`
- name: `MSMSecStopSecurity`
- size: `761`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1800058b8`
- `0x180006344`
- `0x18000892c`
- `0x180008998`
- `0x180012970`
- `0x180013bc0`
- `0x1800148d0`
- `0x180015300`
- `0x1800163e0`
- `0x1800169c0`
- `0x18002da24`
- `0x18003346c`
- `0x18003c528`
- `0x180055a38`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18001543d`
- `MobileNetworking!ReleaseWriteLock` at `0x18001543d`
- `MobileNetworking!AcquireWriteLock` at `0x1800153f8`
- `MobileNetworking!AcquireWriteLock` at `0x1800153f8`

## string_xrefs

- `0x180015349`: `MSMSecStopSecurity`

## pseudocode

```c
__int64 __fastcall MSMSecStopSecurity(void *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  struct MSMSEC_INTF_CONTEXT *v4; // rdi
  unsigned int v5; // eax
  int v6; // r8d
  PVOID v7; // rcx
  int v8; // ebp
  PVOID *v9; // rcx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  struct MSMSEC_INTF_CONTEXT *v13; // [rsp+68h] [rbp+10h] BYREF

  v13 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 73, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v2 = IncThreadCountAndCheckInitializedEx("MSMSecStopSecurity", 604);
  v3 = v2;
  if ( v2 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v12 = 74;
LABEL_30:
      WPP_SF_d(v11[7], v12, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v2);
    }
  }
  else if ( a1 )
  {
    v2 = SecMgrValidateAndRefAdapter(a1, &v13);
    v3 = v2;
    if ( !v2 )
    {
      v4 = v13;
      v5 = SecMgrStopSecurity(v13);
      v3 = v5;
      if ( v5 )
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        {
LABEL_19:
          SecMgrDerefAdapterEx(v4, "MSMSecStopSecurity", 653);
          goto LABEL_20;
        }
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        {
LABEL_16:
          if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x100) != 0 )
            WPP_SF_Ls((unsigned int)v9[7], 11, v6, *((_DWORD *)v4 + 624), (__int64)"<<< Derefing <<<");
          goto LABEL_19;
        }
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 77, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v5);
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        v8 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
          WPP_SF_Lq(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            78,
            &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
            *((unsigned int *)v4 + 624),
            a1);
        if ( (byte_1800AED45 & 1) != 0 )
          McTemplateU0qj_EventWriteTransfer(v7, "%R", *((unsigned int *)v4 + 624), (char *)v4 + 32);
        TraceAdapterId(*((_DWORD *)v4 + 624), ">>> Locking >>>");
        AcquireWriteLock(v4, (char *)v4 + 2512, "MSMSecStopSecurity", 632);
        if ( *((_DWORD *)v4 + 695) )
        {
          *((_DWORD *)v4 + 695) = 0;
          v8 = 1;
        }
        PmkCacheInvalidate((struct MSMSEC_INTF_CONTEXT *)((char *)v4 + 3000));
        TraceAdapterId(*((_DWORD *)v4 + 624), "<<< Unlocking <<<");
        ReleaseWriteLock(v4, (char *)v4 + 2512, "MSMSecStopSecurity", 642);
        if ( v8 )
          WpsAuthMgrDeinitializeWcnOneX();
      }
      v9 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_16;
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v12 = 76;
      goto LABEL_30;
    }
  }
  else
  {
    v3 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 75, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  }
LABEL_20:
  DecThreadCountEx("MSMSecStopSecurity", 655);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 79, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180015300  mov     [rsp+arg_0], rbx
0x180015305  mov     [rsp+arg_10], rbp
0x18001530a  push    rsi
0x18001530b  push    rdi
0x18001530c  push    r12
0x18001530e  push    r13
0x180015310  push    r15
0x180015312  sub     rsp, 30h
0x180015316  mov     rsi, rcx
0x180015319  mov     [rsp+58h+arg_8], 0
0x180015322  mov     rcx, cs:WPP_GLOBAL_Control
0x180015329  lea     r15, WPP_GLOBAL_Control
0x180015330  lea     r12, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180015337  cmp     rcx, r15
0x18001533a  jz      short loc_180015349
0x18001533c  test    dword ptr [rcx+44h], 100h
0x180015343  jnz     loc_180015570
0x180015349  lea     r13, aMsmsecstopsecu_0; "MSMSecStopSecurity"
0x180015350  mov     edx, 25Ch; int
0x180015355  mov     rcx, r13; char *
0x180015358  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x18001535d  mov     ebx, eax
0x18001535f  test    eax, eax
0x180015361  jnz     loc_1800154AE
0x180015367  test    rsi, rsi
0x18001536a  jz      loc_180015586
0x180015370  lea     rdx, [rsp+58h+arg_8]; struct MSMSEC_INTF_CONTEXT **
0x180015375  mov     rcx, rsi; void *
0x180015378  call    ?SecMgrValidateAndRefAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateAndRefAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x18001537d  mov     ebx, eax
0x18001537f  test    eax, eax
0x180015381  jnz     loc_1800154E6
0x180015387  mov     rdi, [rsp+58h+arg_8]
0x18001538c  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x18001538f  call    ?SecMgrStopSecurity@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrStopSecurity(MSMSEC_INTF_CONTEXT *)
0x180015394  mov     ebx, eax
0x180015396  test    eax, eax
0x180015398  jnz     loc_180015511
0x18001539e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800153a5  xor     ebp, ebp
0x1800153a7  cmp     rcx, r15
0x1800153aa  jnz     loc_180015544
0x1800153b0  test    cs:byte_1800AED45, 1
0x1800153b7  jz      short loc_1800153D0
0x1800153b9  mov     r8d, [rdi+9C0h]
0x1800153c0  lea     r9, [rdi+20h]
0x1800153c4  lea     rdx, MsmSecDisconnectNotification; "%R"
0x1800153cb  call    McTemplateU0qj_EventWriteTransfer
0x1800153d0  mov     ecx, [rdi+9C0h]; unsigned int
0x1800153d6  lea     rdx, aLocking; ">>> Locking >>>"
0x1800153dd  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800153e2  lea     rsi, [rdi+9D0h]
0x1800153e9  mov     r9d, 278h
0x1800153ef  mov     rdx, rsi
0x1800153f2  mov     r8, r13
0x1800153f5  mov     rcx, rdi
0x1800153f8  call    cs:__imp_AcquireWriteLock
0x1800153ff  nop     dword ptr [rax+rax+00h]
0x180015404  cmp     [rdi+0ADCh], ebp
0x18001540a  jnz     loc_1800155B9
0x180015410  lea     rcx, [rdi+0BB8h]; struct MSMSEC_PMKCACHE_CONTEXT *
0x180015417  call    ?PmkCacheInvalidate@@YAXPEAUMSMSEC_PMKCACHE_CONTEXT@@@Z; PmkCacheInvalidate(MSMSEC_PMKCACHE_CONTEXT *)
0x18001541c  mov     ecx, [rdi+9C0h]; unsigned int
0x180015422  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180015429  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18001542e  mov     r9d, 282h
0x180015434  mov     r8, r13
0x180015437  mov     rdx, rsi
0x18001543a  mov     rcx, rdi
0x18001543d  call    cs:__imp_ReleaseWriteLock
0x180015444  nop     dword ptr [rax+rax+00h]
0x180015449  test    ebp, ebp
0x18001544b  jnz     loc_1800155C9
0x180015451  mov     rcx, cs:WPP_GLOBAL_Control
0x180015458  cmp     rcx, r15
0x18001545b  jz      short loc_18001546A
0x18001545d  test    dword ptr [rcx+44h], 100h
0x180015464  jnz     loc_1800155D3
0x18001546a  mov     r8d, 28Dh; int
0x180015470  mov     rdx, r13; char *
0x180015473  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180015476  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x18001547b  mov     edx, 28Fh; int
0x180015480  mov     rcx, r13; char *
0x180015483  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x180015488  mov     rcx, cs:WPP_GLOBAL_Control
0x18001548f  cmp     rcx, r15
0x180015492  jnz     short loc_1800154C7
0x180015494  mov     rbp, [rsp+58h+arg_10]
0x180015499  mov     eax, ebx
0x18001549b  mov     rbx, [rsp+58h+arg_0]
0x1800154a0  add     rsp, 30h
0x1800154a4  pop     r15
0x1800154a6  pop     r13
0x1800154a8  pop     r12
0x1800154aa  pop     rdi
0x1800154ab  pop     rsi
0x1800154ac  retn
0x1800154ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800154b5  cmp     rcx, r15
0x1800154b8  jz      short loc_18001547B
0x1800154ba  test    byte ptr [rcx+44h], 1
0x1800154be  jz      short loc_18001547B
0x1800154c0  mov     edx, 4Ah ; 'J'
0x1800154c5  jmp     short loc_1800154FD
0x1800154c7  test    dword ptr [rcx+44h], 100h
0x1800154ce  jz      short loc_180015494
0x1800154d0  mov     rcx, [rcx+38h]
0x1800154d4  mov     edx, 4Fh ; 'O'
0x1800154d9  mov     r9d, ebx
0x1800154dc  mov     r8, r12
0x1800154df  call    WPP_SF_d
0x1800154e4  jmp     short loc_180015494
0x1800154e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800154ed  cmp     rcx, r15
0x1800154f0  jz      short loc_18001547B
0x1800154f2  test    byte ptr [rcx+44h], 1
0x1800154f6  jz      short loc_18001547B
0x1800154f8  mov     edx, 4Ch ; 'L'
0x1800154fd  mov     rcx, [rcx+38h]
0x180015501  mov     r9d, eax
0x180015504  mov     r8, r12
0x180015507  call    WPP_SF_d
0x18001550c  jmp     loc_18001547B
0x180015511  mov     rcx, cs:WPP_GLOBAL_Control
0x180015518  cmp     rcx, r15
0x18001551b  jz      loc_18001546A
0x180015521  test    byte ptr [rcx+44h], 1
0x180015525  jz      loc_180015458
0x18001552b  mov     rcx, [rcx+38h]
0x18001552f  mov     edx, 4Dh ; 'M'
0x180015534  mov     r9d, eax
0x180015537  mov     r8, r12
0x18001553a  call    WPP_SF_d
0x18001553f  jmp     loc_180015451
0x180015544  test    byte ptr [rcx+44h], 20h
0x180015548  jz      loc_1800153B0
0x18001554e  mov     r9d, [rdi+9C0h]
0x180015555  mov     edx, 4Eh ; 'N'
0x18001555a  mov     rcx, [rcx+38h]
0x18001555e  mov     r8, r12
0x180015561  mov     [rsp+58h+var_38], rsi
0x180015566  call    WPP_SF_Lq
0x18001556b  jmp     loc_1800153B0
0x180015570  mov     rcx, [rcx+38h]
0x180015574  mov     edx, 49h ; 'I'
0x180015579  mov     r8, r12
0x18001557c  call    WPP_SF_
0x180015581  jmp     loc_180015349
0x180015586  mov     ebx, 57h ; 'W'
0x18001558b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015592  cmp     rcx, r15
0x180015595  jz      loc_18001547B
0x18001559b  test    byte ptr [rcx+44h], 1
0x18001559f  jz      loc_18001547B
0x1800155a5  mov     rcx, [rcx+38h]
0x1800155a9  lea     edx, [rbx-0Ch]
0x1800155ac  mov     r8, r12
0x1800155af  call    WPP_SF_
0x1800155b4  jmp     loc_18001547B
0x1800155b9  mov     [rdi+0ADCh], ebp
0x1800155bf  mov     ebp, 1
0x1800155c4  jmp     loc_180015410
0x1800155c9  call    ?WpsAuthMgrDeinitializeWcnOneX@@YAXXZ; WpsAuthMgrDeinitializeWcnOneX(void)
0x1800155ce  jmp     loc_180015451
0x1800155d3  mov     r9d, [rdi+9C0h]
0x1800155da  lea     rax, aDerefing; "<<< Derefing <<<"
0x1800155e1  mov     rcx, [rcx+38h]
0x1800155e5  mov     edx, 0Bh
0x1800155ea  mov     [rsp+58h+var_38], rax
0x1800155ef  call    WPP_SF_Ls
0x1800155f4  jmp     loc_18001546A
```

# SecMgrReAuthWorker(void *)

- ea: `0x180057930`
- end: `0x180057b11`
- name: `?SecMgrReAuthWorker@@YAKPEAX@Z`
- size: `481`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000e620`
- `0x180013600`
- `0x18001df24`
- `0x18001df84`
- `0x18002b3f8`
- `0x18002bb08`
- `0x1800354e0`
- `0x180057874`
- `0x180057930`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180057a95`
- `MobileNetworking!ReleaseWriteLock` at `0x180057a95`

## pseudocode

```c
__int64 __fastcall SecMgrReAuthWorker(_QWORD *Parameter, unsigned int a2)
{
  __int64 v3; // rdx
  int v4; // r8d
  unsigned int v5; // eax
  unsigned int v6; // ebx
  int v7; // ebp
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  _QWORD *v11; // [rsp+90h] [rbp+8h] BYREF

  v11 = Parameter;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 159, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
  NetTraceBeginContextActivity(Parameter, a2);
  v5 = SecMgrLockAndCheckPortActive((struct MSMSEC_PORT_CONTEXT *)*Parameter, v3, v4);
  v6 = v5;
  if ( v5 )
  {
    v7 = 0;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v9 = 160;
LABEL_15:
      WPP_SF_d(v8[7], v9, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v5);
    }
  }
  else
  {
    v7 = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
      WPP_SF_DDDDDD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        161,
        &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids,
        *(unsigned __int8 *)(*Parameter + 302LL),
        *(unsigned __int8 *)(*Parameter + 303LL),
        *(unsigned __int8 *)(*Parameter + 304LL),
        *(unsigned __int8 *)(*Parameter + 305LL));
    v5 = SecMgrReAuthPort((struct MSMSEC_PORT_CONTEXT *)*Parameter);
    v6 = v5;
    if ( v5 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v9 = 162;
        goto LABEL_15;
      }
    }
  }
  NetTraceEndContextActivity(Parameter, 0x15u);
  if ( v7 )
  {
    TracePortId(*(_DWORD *)(*Parameter + 312LL), "<<< Unlocking <<<");
    ReleaseWriteLock(*Parameter, *Parameter + 320LL, "SecMgrReAuthWorker", 1964);
  }
  TracePortId(*(_DWORD *)(*Parameter + 312LL), "<<< Derefing <<<");
  SecMgrDerefPortEx((struct MSMSEC_PORT_CONTEXT *)*Parameter, "SecMgrReAuthWorker", 1967);
  FreeMSMSecMemory(&v11);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 163, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180057930  mov     [rsp+arg_0], rcx
0x180057935  push    rbx
0x180057936  push    rbp
0x180057937  push    rsi
0x180057938  push    rdi
0x180057939  push    r14
0x18005793b  push    r15
0x18005793d  sub     rsp, 58h
0x180057941  mov     rdi, rcx
0x180057944  mov     rcx, cs:WPP_GLOBAL_Control
0x18005794b  lea     r14, WPP_GLOBAL_Control
0x180057952  lea     r15, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180057959  cmp     rcx, r14
0x18005795c  jz      short loc_180057978
0x18005795e  test    dword ptr [rcx+44h], 100h
0x180057965  jz      short loc_180057978
0x180057967  mov     rcx, [rcx+38h]
0x18005796b  mov     edx, 9Fh
0x180057970  mov     r8, r15
0x180057973  call    WPP_SF_
0x180057978  mov     rcx, rdi; void *
0x18005797b  call    ?NetTraceBeginContextActivity@@YAXPEAXI@Z; NetTraceBeginContextActivity(void *,uint)
0x180057980  mov     rcx, [rdi]; struct MSMSEC_PORT_CONTEXT *
0x180057983  call    ?SecMgrLockAndCheckPortActive@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrLockAndCheckPortActive(MSMSEC_PORT_CONTEXT *)
0x180057988  mov     ebx, eax
0x18005798a  test    eax, eax
0x18005798c  jz      short loc_1800579B4
0x18005798e  xor     ebp, ebp
0x180057990  mov     rcx, cs:WPP_GLOBAL_Control
0x180057997  cmp     rcx, r14
0x18005799a  jz      loc_180057A58
0x1800579a0  test    byte ptr [rcx+44h], 1
0x1800579a4  jz      loc_180057A58
0x1800579aa  mov     edx, 0A0h
0x1800579af  jmp     loc_180057A49
0x1800579b4  mov     ebp, 1
0x1800579b9  mov     rsi, cs:WPP_GLOBAL_Control
0x1800579c0  cmp     rsi, r14
0x1800579c3  jz      short loc_180057A24
0x1800579c5  test    byte ptr [rsi+44h], 2
0x1800579c9  jz      short loc_180057A24
0x1800579cb  mov     rax, [rdi]
0x1800579ce  mov     edx, 0A1h
0x1800579d3  movzx   ecx, byte ptr [rax+133h]
0x1800579da  movzx   r8d, byte ptr [rax+132h]
0x1800579e2  movzx   r10d, byte ptr [rax+131h]
0x1800579ea  movzx   r11d, byte ptr [rax+130h]
0x1800579f2  movzx   ebx, byte ptr [rax+12Fh]
0x1800579f9  movzx   r9d, byte ptr [rax+12Eh]
0x180057a01  mov     [rsp+88h+var_48], ecx
0x180057a05  mov     rcx, [rsi+38h]
0x180057a09  mov     [rsp+88h+var_50], r8d
0x180057a0e  mov     r8, r15
0x180057a11  mov     [rsp+88h+var_58], r10d
0x180057a16  mov     [rsp+88h+var_60], r11d
0x180057a1b  mov     [rsp+88h+var_68], ebx
0x180057a1f  call    WPP_SF_DDDDDD
0x180057a24  mov     rcx, [rdi]; struct MSMSEC_PORT_CONTEXT *
0x180057a27  call    ?SecMgrReAuthPort@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrReAuthPort(MSMSEC_PORT_CONTEXT *)
0x180057a2c  mov     ebx, eax
0x180057a2e  test    eax, eax
0x180057a30  jz      short loc_180057A58
0x180057a32  mov     rcx, cs:WPP_GLOBAL_Control
0x180057a39  cmp     rcx, r14
0x180057a3c  jz      short loc_180057A58
0x180057a3e  test    [rcx+44h], bpl
0x180057a42  jz      short loc_180057A58
0x180057a44  mov     edx, 0A2h
0x180057a49  mov     rcx, [rcx+38h]
0x180057a4d  mov     r9d, eax
0x180057a50  mov     r8, r15
0x180057a53  call    WPP_SF_d
0x180057a58  mov     edx, 15h; unsigned int
0x180057a5d  mov     rcx, rdi; void *
0x180057a60  call    ?NetTraceEndContextActivity@@YAXPEAXI@Z; NetTraceEndContextActivity(void *,uint)
0x180057a65  test    ebp, ebp
0x180057a67  jz      short loc_180057AA1
0x180057a69  mov     rcx, [rdi]
0x180057a6c  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180057a73  mov     ecx, [rcx+138h]; unsigned int
0x180057a79  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180057a7e  mov     rcx, [rdi]
0x180057a81  lea     r8, aSecmgrreauthwo; "SecMgrReAuthWorker"
0x180057a88  mov     r9d, 7ACh
0x180057a8e  lea     rdx, [rcx+140h]
0x180057a95  call    cs:__imp_ReleaseWriteLock
0x180057a9c  nop     dword ptr [rax+rax+00h]
0x180057aa1  mov     rcx, [rdi]
0x180057aa4  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180057aab  mov     ecx, [rcx+138h]; unsigned int
0x180057ab1  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180057ab6  mov     rcx, [rdi]; struct MSMSEC_PORT_CONTEXT *
0x180057ab9  lea     rdx, aSecmgrreauthwo; "SecMgrReAuthWorker"
0x180057ac0  mov     r8d, 7AFh; int
0x180057ac6  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x180057acb  lea     rcx, [rsp+88h+arg_0]
0x180057ad3  call    FreeMSMSecMemory
0x180057ad8  mov     rcx, cs:WPP_GLOBAL_Control
0x180057adf  cmp     rcx, r14
0x180057ae2  jz      short loc_180057B01
0x180057ae4  test    dword ptr [rcx+44h], 100h
0x180057aeb  jz      short loc_180057B01
0x180057aed  mov     rcx, [rcx+38h]
0x180057af1  mov     edx, 0A3h
0x180057af6  mov     r9d, ebx
0x180057af9  mov     r8, r15
0x180057afc  call    WPP_SF_d
0x180057b01  mov     eax, ebx
0x180057b03  add     rsp, 58h
0x180057b07  pop     r15
0x180057b09  pop     r14
0x180057b0b  pop     rdi
0x180057b0c  pop     rsi
0x180057b0d  pop     rbp
0x180057b0e  pop     rbx
0x180057b0f  retn
```

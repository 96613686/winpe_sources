# SecMgrHandleOneXUIResp(MSMSEC_INTF_CONTEXT *,ulong,_WLAN_UI_SECURITY_RESPONSE *,MSMSEC_UI_REQUEST *,int,ulong)

- ea: `0x180056ea4`
- end: `0x18005722c`
- name: `?SecMgrHandleOneXUIResp@@YAKPEAUMSMSEC_INTF_CONTEXT@@KPEAU_WLAN_UI_SECURITY_RESPONSE@@PEAUMSMSEC_UI_REQUEST@@HK@Z`
- size: `904`
- prototype: `unsigned int __usercall@<eax>(struct MSMSEC_INTF_CONTEXT *@<rcx>, unsigned int@<edx>, struct _WLAN_UI_SECURITY_RESPONSE *@<r8>, struct MSMSEC_UI_REQUEST *@<r9>, int, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180032910`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000a26c`
- `0x180011030`
- `0x180013600`
- `0x180014998`
- `0x1800169c0`
- `0x180016a08`
- `0x18002abec`
- `0x18002b3f8`
- `0x18002bb08`
- `0x1800354e0`
- `0x180038ea8`
- `0x1800558c0`
- `0x180056ea4`
- `0x180063e94`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180057098`
- `MobileNetworking!ReleaseWriteLock` at `0x1800570d2`
- `MobileNetworking!ReleaseWriteLock` at `0x1800571bc`
- `MobileNetworking!ReleaseWriteLock` at `0x180057098`
- `MobileNetworking!ReleaseWriteLock` at `0x1800570d2`
- `MobileNetworking!ReleaseWriteLock` at `0x1800571bc`

## pseudocode

```c
__int64 __fastcall SecMgrHandleOneXUIResp(
        struct MSMSEC_INTF_CONTEXT *a1,
        unsigned int a2,
        struct _WLAN_UI_SECURITY_RESPONSE *a3,
        struct MSMSEC_UI_REQUEST *a4,
        int a5)
{
  unsigned int v9; // eax
  unsigned int v10; // ebx
  PVOID *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rax
  unsigned int v16; // r10d
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // r11
  __int64 v20; // r8
  char v21; // r10
  struct MSMSEC_PORT_CONTEXT *v22; // rdi
  unsigned int v23; // eax
  unsigned int v24; // ecx
  unsigned int v25; // eax
  unsigned int v27; // [rsp+38h] [rbp-70h]
  struct MSMSEC_PORT_CONTEXT *v28[11]; // [rsp+50h] [rbp-58h] BYREF

  v28[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 141, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
  v9 = SecMgrLockAndCheckAdapterDeleted(a1);
  v10 = v9;
  if ( !v9 )
  {
    if ( !(unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)a1 + 681), 9) )
    {
      v10 = 5023;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v15 = IntfActionStr(9, v12, v13, v14);
        v18 = IntfSecStateStr(v16, v17, v15);
        WPP_SF_SLSL(
          *(_QWORD *)(v19 + 56),
          143,
          (unsigned int)&WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids,
          v18,
          v21,
          v20,
          9);
      }
LABEL_22:
      TraceAdapterId(*((_DWORD *)a1 + 624), "<<< Unlocking <<<");
      ReleaseWriteLock(a1, (char *)a1 + 2512, "SecMgrHandleOneXUIResp", 1831);
      goto LABEL_36;
    }
    v10 = SecMgrValidateAndRefPort(a1, (unsigned __int8 (*)[6])((unsigned __int8 *)a4 + 2), v28);
    if ( v10 == 1168 )
    {
      if ( !*(_DWORD *)(*((_QWORD *)a1 + 348) + 32LL) )
      {
LABEL_19:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 145, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v10);
        goto LABEL_22;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
      {
        v27 = *((unsigned __int8 *)a4 + 16);
        WPP_SF_DDDDDD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          144,
          &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids,
          *((unsigned __int8 *)a4 + 12),
          *((unsigned __int8 *)a4 + 13),
          *((unsigned __int8 *)a4 + 14),
          *((unsigned __int8 *)a4 + 15));
      }
      v10 = SecMgrFindAndRefInfraPort(a1, v28);
    }
    if ( !v10 )
    {
      TraceAdapterId(*((_DWORD *)a1 + 624), "<<< Unlocking <<<");
      ReleaseWriteLock(a1, (char *)a1 + 2512, "SecMgrHandleOneXUIResp", 1810);
      v22 = v28[0];
      v23 = SecMgrLockAndCheckPortActive(v28[0]);
      v10 = v23;
      if ( v23 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 146, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v23);
      }
      else
      {
        if ( a3 )
          v24 = *((_DWORD *)a3 + 1);
        else
          v24 = 0;
        v25 = AuthMgrHandleUIResponse(
                v22,
                a2,
                *((_DWORD *)a4 + 5),
                (char *)a4 + 32,
                v24,
                (void *)(((unsigned __int64)a3 + 16) & ((unsigned __int128)-(__int128)(unsigned __int64)a3 >> 64)),
                a5,
                v27);
        v10 = v25;
        if ( v25 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 147, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v25);
        TracePortId(*((_DWORD *)v22 + 78), "<<< Unlocking <<<");
        ReleaseWriteLock(v22, (char *)v22 + 320, "SecMgrHandleOneXUIResp", 1835);
      }
      TracePortId(*((_DWORD *)v22 + 78), "<<< Derefing <<<");
      SecMgrDerefPortEx(v22, "SecMgrHandleOneXUIResp", 1839);
      goto LABEL_36;
    }
    goto LABEL_19;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v10;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 142, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v9);
LABEL_36:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x100) != 0 )
    WPP_SF_d(v11[7], 148, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180056ea4  push    rbx
0x180056ea6  push    rbp
0x180056ea7  push    rsi
0x180056ea8  push    rdi
0x180056ea9  push    r12
0x180056eab  push    r13
0x180056ead  push    r14
0x180056eaf  push    r15
0x180056eb1  sub     rsp, 68h
0x180056eb5  mov     rsi, r9
0x180056eb8  mov     [rsp+0A8h+var_58], 0
0x180056ec1  mov     rbp, r8
0x180056ec4  mov     r15d, edx
0x180056ec7  mov     rdi, rcx
0x180056eca  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ed1  lea     r12, WPP_GLOBAL_Control
0x180056ed8  lea     r13, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180056edf  cmp     rcx, r12
0x180056ee2  jz      short loc_180056EFE
0x180056ee4  test    dword ptr [rcx+44h], 100h
0x180056eeb  jz      short loc_180056EFE
0x180056eed  mov     rcx, [rcx+38h]
0x180056ef1  mov     edx, 8Dh
0x180056ef6  mov     r8, r13
0x180056ef9  call    WPP_SF_
0x180056efe  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180056f01  call    ?SecMgrLockAndCheckAdapterDeleted@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrLockAndCheckAdapterDeleted(MSMSEC_INTF_CONTEXT *)
0x180056f06  mov     ebx, eax
0x180056f08  test    eax, eax
0x180056f0a  jz      short loc_180056F3F
0x180056f0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180056f13  cmp     rcx, r12
0x180056f16  jz      loc_180057218
0x180056f1c  test    byte ptr [rcx+44h], 1
0x180056f20  jz      loc_1800571F6
0x180056f26  mov     rcx, [rcx+38h]
0x180056f2a  mov     edx, 8Eh
0x180056f2f  mov     r9d, eax
0x180056f32  mov     r8, r13
0x180056f35  call    WPP_SF_d
0x180056f3a  jmp     loc_1800571EF
0x180056f3f  mov     ecx, [rdi+0AA4h]
0x180056f45  mov     r14d, 9
0x180056f4b  mov     edx, r14d
0x180056f4e  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x180056f53  test    eax, eax
0x180056f55  jnz     short loc_180056FB9
0x180056f57  mov     ebx, 139Fh
0x180056f5c  mov     r11, cs:WPP_GLOBAL_Control
0x180056f63  cmp     r11, r12
0x180056f66  jz      loc_18005706F
0x180056f6c  test    byte ptr [r11+44h], 1
0x180056f71  jz      loc_18005706F
0x180056f77  mov     r10d, [rdi+0AA4h]
0x180056f7e  mov     ecx, r14d
0x180056f81  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x180056f86  mov     ecx, r10d
0x180056f89  mov     r8, rax
0x180056f8c  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x180056f91  mov     rcx, [r11+38h]
0x180056f95  mov     r9, rax
0x180056f98  mov     [rsp+0A8h+var_78], r14d
0x180056f9d  mov     edx, 8Fh
0x180056fa2  mov     [rsp+0A8h+var_80], r8
0x180056fa7  mov     r8, r13
0x180056faa  mov     [rsp+0A8h+var_88], r10d
0x180056faf  call    WPP_SF_SLSL
0x180056fb4  jmp     loc_18005706F
0x180056fb9  lea     r8, [rsp+0A8h+var_58]; struct MSMSEC_PORT_CONTEXT **
0x180056fbe  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180056fc1  lea     rdx, [rsi+0Ch]; unsigned __int8 (*)[6]
0x180056fc5  call    ?SecMgrValidateAndRefPort@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAY05EPEAPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrValidateAndRefPort(MSMSEC_INTF_CONTEXT *,uchar (*)[6],MSMSEC_PORT_CONTEXT * *)
0x180056fca  mov     ebx, eax
0x180056fcc  cmp     eax, 490h
0x180056fd1  jnz     short loc_180057045
0x180056fd3  mov     rax, [rdi+0AE0h]
0x180056fda  cmp     dword ptr [rax+20h], 0
0x180056fde  jz      short loc_180057049
0x180056fe0  mov     rcx, cs:WPP_GLOBAL_Control
0x180056fe7  cmp     rcx, r12
0x180056fea  jz      short loc_180057036
0x180056fec  test    byte ptr [rcx+44h], 2
0x180056ff0  jz      short loc_180057036
0x180056ff2  movzx   r8d, byte ptr [rsi+10h]
0x180056ff7  mov     edx, 90h
0x180056ffc  movzx   eax, byte ptr [rsi+11h]
0x180057000  movzx   r10d, byte ptr [rsi+0Fh]
0x180057005  movzx   r11d, byte ptr [rsi+0Eh]
0x18005700a  movzx   ebx, byte ptr [rsi+0Dh]
0x18005700e  movzx   r9d, byte ptr [rsi+0Ch]
0x180057013  mov     rcx, [rcx+38h]
0x180057017  mov     [rsp+0A8h+var_68], eax
0x18005701b  mov     [rsp+0A8h+var_70], r8d; unsigned int
0x180057020  mov     r8, r13
0x180057023  mov     [rsp+0A8h+var_78], r10d
0x180057028  mov     dword ptr [rsp+0A8h+var_80], r11d
0x18005702d  mov     [rsp+0A8h+var_88], ebx
0x180057031  call    WPP_SF_DDDDDD
0x180057036  lea     rdx, [rsp+0A8h+var_58]; struct MSMSEC_PORT_CONTEXT **
0x18005703b  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x18005703e  call    ?SecMgrFindAndRefInfraPort@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrFindAndRefInfraPort(MSMSEC_INTF_CONTEXT *,MSMSEC_PORT_CONTEXT * *)
0x180057043  mov     ebx, eax
0x180057045  test    ebx, ebx
0x180057047  jz      short loc_1800570A9
0x180057049  mov     rcx, cs:WPP_GLOBAL_Control
0x180057050  cmp     rcx, r12
0x180057053  jz      short loc_18005706F
0x180057055  test    byte ptr [rcx+44h], 1
0x180057059  jz      short loc_18005706F
0x18005705b  mov     rcx, [rcx+38h]
0x18005705f  mov     edx, 91h
0x180057064  mov     r9d, ebx
0x180057067  mov     r8, r13
0x18005706a  call    WPP_SF_d
0x18005706f  mov     ecx, [rdi+9C0h]; unsigned int
0x180057075  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18005707c  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180057081  lea     rdx, [rdi+9D0h]
0x180057088  mov     r9d, 727h
0x18005708e  lea     r8, aSecmgrhandleon; "SecMgrHandleOneXUIResp"
0x180057095  mov     rcx, rdi
0x180057098  call    cs:__imp_ReleaseWriteLock
0x18005709f  nop     dword ptr [rax+rax+00h]
0x1800570a4  jmp     loc_1800571EF
0x1800570a9  mov     ecx, [rdi+9C0h]; unsigned int
0x1800570af  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800570b6  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800570bb  lea     rdx, [rdi+9D0h]
0x1800570c2  mov     r9d, 712h
0x1800570c8  lea     r8, aSecmgrhandleon; "SecMgrHandleOneXUIResp"
0x1800570cf  mov     rcx, rdi
0x1800570d2  call    cs:__imp_ReleaseWriteLock
0x1800570d9  nop     dword ptr [rax+rax+00h]
0x1800570de  mov     rdi, [rsp+0A8h+var_58]
0x1800570e3  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x1800570e6  call    ?SecMgrLockAndCheckPortActive@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrLockAndCheckPortActive(MSMSEC_PORT_CONTEXT *)
0x1800570eb  mov     ebx, eax
0x1800570ed  test    eax, eax
0x1800570ef  jz      short loc_180057124
0x1800570f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800570f8  cmp     rcx, r12
0x1800570fb  jz      loc_1800571C8
0x180057101  test    byte ptr [rcx+44h], 1
0x180057105  jz      loc_1800571C8
0x18005710b  mov     rcx, [rcx+38h]
0x18005710f  mov     edx, 92h
0x180057114  mov     r9d, eax
0x180057117  mov     r8, r13
0x18005711a  call    WPP_SF_d
0x18005711f  jmp     loc_1800571C8
0x180057124  mov     rax, rbp
0x180057127  lea     rcx, [rbp+10h]
0x18005712b  neg     rax
0x18005712e  sbb     rdx, rdx
0x180057131  and     rdx, rcx
0x180057134  test    rbp, rbp
0x180057137  jz      short loc_18005713E
0x180057139  mov     ecx, [rbp+4]
0x18005713c  jmp     short loc_180057140
0x18005713e  xor     ecx, ecx
0x180057140  mov     eax, [rsp+0A8h+arg_20]
0x180057147  lea     r9, [rsi+20h]; void *
0x18005714b  mov     r8d, [rsi+14h]; unsigned int
0x18005714f  mov     [rsp+0A8h+var_78], eax; int
0x180057153  mov     [rsp+0A8h+var_80], rdx; void *
0x180057158  mov     edx, r15d; unsigned int
0x18005715b  mov     [rsp+0A8h+var_88], ecx; unsigned int
0x18005715f  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180057162  call    ?AuthMgrHandleUIResponse@@YAKPEAUMSMSEC_PORT_CONTEXT@@KKPEAXK1HK@Z; AuthMgrHandleUIResponse(MSMSEC_PORT_CONTEXT *,ulong,ulong,void *,ulong,void *,int,ulong)
0x180057167  mov     ebx, eax
0x180057169  test    eax, eax
0x18005716b  jz      short loc_180057193
0x18005716d  mov     rcx, cs:WPP_GLOBAL_Control
0x180057174  cmp     rcx, r12
0x180057177  jz      short loc_180057193
0x180057179  test    byte ptr [rcx+44h], 1
0x18005717d  jz      short loc_180057193
0x18005717f  mov     rcx, [rcx+38h]
0x180057183  mov     edx, 93h
0x180057188  mov     r9d, eax
0x18005718b  mov     r8, r13
0x18005718e  call    WPP_SF_d
0x180057193  mov     ecx, [rdi+138h]; unsigned int
0x180057199  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800571a0  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x1800571a5  lea     rdx, [rdi+140h]
0x1800571ac  mov     r9d, 72Bh
0x1800571b2  lea     r8, aSecmgrhandleon; "SecMgrHandleOneXUIResp"
0x1800571b9  mov     rcx, rdi
0x1800571bc  call    cs:__imp_ReleaseWriteLock
0x1800571c3  nop     dword ptr [rax+rax+00h]
0x1800571c8  mov     ecx, [rdi+138h]; unsigned int
0x1800571ce  lea     rdx, aDerefing; "<<< Derefing <<<"
0x1800571d5  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x1800571da  mov     r8d, 72Fh; int
0x1800571e0  lea     rdx, aSecmgrhandleon; "SecMgrHandleOneXUIResp"
0x1800571e7  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x1800571ea  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x1800571ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800571f6  cmp     rcx, r12
0x1800571f9  jz      short loc_180057218
0x1800571fb  test    dword ptr [rcx+44h], 100h
0x180057202  jz      short loc_180057218
0x180057204  mov     rcx, [rcx+38h]
0x180057208  mov     edx, 94h
0x18005720d  mov     r9d, ebx
0x180057210  mov     r8, r13
0x180057213  call    WPP_SF_d
0x180057218  mov     eax, ebx
0x18005721a  add     rsp, 68h
0x18005721e  pop     r15
0x180057220  pop     r14
0x180057222  pop     r13
0x180057224  pop     r12
0x180057226  pop     rdi
0x180057227  pop     rsi
0x180057228  pop     rbp
0x180057229  pop     rbx
0x18005722a  retn
```

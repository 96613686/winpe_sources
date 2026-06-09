# SecMgrIsOneXUIRequestPending(ulong,MSMSEC_UI_REQUEST *,MSMSEC_INTF_CONTEXT *,int *)

- ea: `0x180057390`
- end: `0x180057680`
- name: `?SecMgrIsOneXUIRequestPending@@YAKKPEAUMSMSEC_UI_REQUEST@@PEAUMSMSEC_INTF_CONTEXT@@PEAH@Z`
- size: `752`
- prototype: `unsigned int __fastcall(unsigned int, struct MSMSEC_UI_REQUEST *, struct MSMSEC_INTF_CONTEXT *, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1800533f0`

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
- `0x1800558c0`
- `0x180057390`
- `0x1800640d0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180057508`
- `MobileNetworking!ReleaseWriteLock` at `0x180057542`
- `MobileNetworking!ReleaseWriteLock` at `0x180057612`
- `MobileNetworking!ReleaseWriteLock` at `0x180057508`
- `MobileNetworking!ReleaseWriteLock` at `0x180057542`
- `MobileNetworking!ReleaseWriteLock` at `0x180057612`

## pseudocode

```c
__int64 __fastcall SecMgrIsOneXUIRequestPending(
        unsigned int a1,
        struct MSMSEC_UI_REQUEST *a2,
        struct MSMSEC_INTF_CONTEXT *a3,
        int *a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rax
  unsigned int v15; // r10d
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // r11
  __int64 v19; // r8
  char v20; // r10
  unsigned int v21; // eax
  struct MSMSEC_PORT_CONTEXT *v22; // rdi
  unsigned int v23; // eax
  unsigned int IsOneXRequestPending; // eax
  int v26; // [rsp+40h] [rbp-48h] BYREF
  struct MSMSEC_PORT_CONTEXT *v27; // [rsp+48h] [rbp-40h] BYREF

  v27 = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 149, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
  v8 = SecMgrLockAndCheckAdapterDeleted(a3);
  v9 = v8;
  if ( !v8 )
  {
    if ( (unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)a3 + 681), 9) )
    {
      v21 = SecMgrValidateAndRefPort(a3, (unsigned __int8 (*)[6])((unsigned __int8 *)a2 + 2), &v27);
      v9 = v21;
      if ( !v21 )
      {
        TraceAdapterId(*((_DWORD *)a3 + 624), "<<< Unlocking <<<");
        ReleaseWriteLock(a3, (char *)a3 + 2512, "SecMgrIsOneXUIRequestPending", 1886);
        v22 = v27;
        v23 = SecMgrLockAndCheckPortActive(v27);
        v9 = v23;
        if ( v23 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 153, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v23);
        }
        else
        {
          IsOneXRequestPending = AuthMgrIsOneXRequestPending(
                                   (struct MSMSEC_PORT_CONTEXT *)((char *)v22 + 920),
                                   a1,
                                   *((_DWORD *)a2 + 5),
                                   (char *)a2 + 32,
                                   &v26);
          v9 = IsOneXRequestPending;
          if ( IsOneXRequestPending )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                154,
                &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids,
                IsOneXRequestPending);
          }
          else
          {
            *a4 = v26;
          }
          TracePortId(*((_DWORD *)v22 + 78), "<<< Unlocking <<<");
          ReleaseWriteLock(v22, (char *)v22 + 320, "SecMgrIsOneXUIRequestPending", 1905);
        }
        TracePortId(*((_DWORD *)v22 + 78), "<<< Derefing <<<");
        SecMgrDerefPortEx(v22, "SecMgrIsOneXUIRequestPending", 1909);
        goto LABEL_28;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 152, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v21);
    }
    else
    {
      v9 = 5023;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v14 = IntfActionStr(9, v11, v12, v13);
        v17 = IntfSecStateStr(v15, v16, v14);
        WPP_SF_SLSL(
          *(_QWORD *)(v18 + 56),
          151,
          (unsigned int)&WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids,
          v17,
          v20,
          v19,
          9);
      }
    }
    TraceAdapterId(*((_DWORD *)a3 + 624), "<<< Unlocking <<<");
    ReleaseWriteLock(a3, (char *)a3 + 2512, "SecMgrIsOneXUIRequestPending", 1901);
LABEL_28:
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_29;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 150, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v8);
    goto LABEL_28;
  }
LABEL_29:
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x100) != 0 )
    WPP_SF_d(v10[7], 155, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180057390  push    rbx
0x180057392  push    rbp
0x180057393  push    rsi
0x180057394  push    rdi
0x180057395  push    r12
0x180057397  push    r14
0x180057399  push    r15
0x18005739b  sub     rsp, 50h
0x18005739f  mov     r14, r9
0x1800573a2  mov     [rsp+88h+var_40], 0
0x1800573ab  mov     rdi, r8
0x1800573ae  mov     [rsp+88h+var_48], 0
0x1800573b6  mov     rsi, rdx
0x1800573b9  mov     ebp, ecx
0x1800573bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800573c2  lea     r15, WPP_GLOBAL_Control
0x1800573c9  lea     r12, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x1800573d0  cmp     rcx, r15
0x1800573d3  jz      short loc_1800573EF
0x1800573d5  test    dword ptr [rcx+44h], 100h
0x1800573dc  jz      short loc_1800573EF
0x1800573de  mov     rcx, [rcx+38h]
0x1800573e2  mov     edx, 95h
0x1800573e7  mov     r8, r12
0x1800573ea  call    WPP_SF_
0x1800573ef  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x1800573f2  call    ?SecMgrLockAndCheckAdapterDeleted@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrLockAndCheckAdapterDeleted(MSMSEC_INTF_CONTEXT *)
0x1800573f7  mov     ebx, eax
0x1800573f9  test    eax, eax
0x1800573fb  jz      short loc_180057430
0x1800573fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180057404  cmp     rcx, r15
0x180057407  jz      loc_18005766E
0x18005740d  test    byte ptr [rcx+44h], 1
0x180057411  jz      loc_18005764C
0x180057417  mov     rcx, [rcx+38h]
0x18005741b  mov     edx, 96h
0x180057420  mov     r9d, eax
0x180057423  mov     r8, r12
0x180057426  call    WPP_SF_d
0x18005742b  jmp     loc_180057645
0x180057430  mov     ecx, [rdi+0AA4h]
0x180057436  mov     edx, 9
0x18005743b  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x180057440  test    eax, eax
0x180057442  jnz     short loc_1800574A2
0x180057444  mov     ebx, 139Fh
0x180057449  mov     r11, cs:WPP_GLOBAL_Control
0x180057450  cmp     r11, r15
0x180057453  jz      loc_1800574DF
0x180057459  test    byte ptr [r11+44h], 1
0x18005745e  jz      short loc_1800574DF
0x180057460  mov     r10d, [rdi+0AA4h]
0x180057467  lea     ecx, [rax+9]
0x18005746a  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x18005746f  mov     ecx, r10d
0x180057472  mov     r8, rax
0x180057475  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x18005747a  mov     rcx, [r11+38h]
0x18005747e  mov     r9, rax
0x180057481  mov     [rsp+88h+var_58], 9
0x180057489  mov     edx, 97h
0x18005748e  mov     [rsp+88h+var_60], r8
0x180057493  mov     r8, r12
0x180057496  mov     dword ptr [rsp+88h+var_68], r10d
0x18005749b  call    WPP_SF_SLSL
0x1800574a0  jmp     short loc_1800574DF
0x1800574a2  lea     rdx, [rsi+0Ch]; unsigned __int8 (*)[6]
0x1800574a6  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x1800574a9  lea     r8, [rsp+88h+var_40]; struct MSMSEC_PORT_CONTEXT **
0x1800574ae  call    ?SecMgrValidateAndRefPort@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAY05EPEAPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrValidateAndRefPort(MSMSEC_INTF_CONTEXT *,uchar (*)[6],MSMSEC_PORT_CONTEXT * *)
0x1800574b3  mov     ebx, eax
0x1800574b5  test    eax, eax
0x1800574b7  jz      short loc_180057519
0x1800574b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800574c0  cmp     rcx, r15
0x1800574c3  jz      short loc_1800574DF
0x1800574c5  test    byte ptr [rcx+44h], 1
0x1800574c9  jz      short loc_1800574DF
0x1800574cb  mov     rcx, [rcx+38h]
0x1800574cf  mov     edx, 98h
0x1800574d4  mov     r9d, eax
0x1800574d7  mov     r8, r12
0x1800574da  call    WPP_SF_d
0x1800574df  mov     ecx, [rdi+9C0h]; unsigned int
0x1800574e5  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800574ec  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800574f1  lea     rdx, [rdi+9D0h]
0x1800574f8  mov     r9d, 76Dh
0x1800574fe  lea     r8, aSecmgrisonexui; "SecMgrIsOneXUIRequestPending"
0x180057505  mov     rcx, rdi
0x180057508  call    cs:__imp_ReleaseWriteLock
0x18005750f  nop     dword ptr [rax+rax+00h]
0x180057514  jmp     loc_180057645
0x180057519  mov     ecx, [rdi+9C0h]; unsigned int
0x18005751f  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180057526  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18005752b  lea     rdx, [rdi+9D0h]
0x180057532  mov     r9d, 75Eh
0x180057538  lea     r8, aSecmgrisonexui; "SecMgrIsOneXUIRequestPending"
0x18005753f  mov     rcx, rdi
0x180057542  call    cs:__imp_ReleaseWriteLock
0x180057549  nop     dword ptr [rax+rax+00h]
0x18005754e  mov     rdi, [rsp+88h+var_40]
0x180057553  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180057556  call    ?SecMgrLockAndCheckPortActive@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrLockAndCheckPortActive(MSMSEC_PORT_CONTEXT *)
0x18005755b  mov     ebx, eax
0x18005755d  test    eax, eax
0x18005755f  jz      short loc_180057594
0x180057561  mov     rcx, cs:WPP_GLOBAL_Control
0x180057568  cmp     rcx, r15
0x18005756b  jz      loc_18005761E
0x180057571  test    byte ptr [rcx+44h], 1
0x180057575  jz      loc_18005761E
0x18005757b  mov     rcx, [rcx+38h]
0x18005757f  mov     edx, 99h
0x180057584  mov     r9d, eax
0x180057587  mov     r8, r12
0x18005758a  call    WPP_SF_d
0x18005758f  jmp     loc_18005761E
0x180057594  mov     r8d, [rsi+14h]; unsigned int
0x180057598  lea     rax, [rsp+88h+var_48]
0x18005759d  lea     r9, [rsi+20h]; void *
0x1800575a1  mov     [rsp+88h+var_68], rax; int *
0x1800575a6  lea     rcx, [rdi+398h]; struct MSMSEC_PORT_AUTH_CONTEXT *
0x1800575ad  mov     edx, ebp; unsigned int
0x1800575af  call    ?AuthMgrIsOneXRequestPending@@YAKPEAUMSMSEC_PORT_AUTH_CONTEXT@@KKPEAXPEAH@Z; AuthMgrIsOneXRequestPending(MSMSEC_PORT_AUTH_CONTEXT *,ulong,ulong,void *,int *)
0x1800575b4  mov     ebx, eax
0x1800575b6  test    eax, eax
0x1800575b8  jz      short loc_1800575E2
0x1800575ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800575c1  cmp     rcx, r15
0x1800575c4  jz      short loc_1800575E9
0x1800575c6  test    byte ptr [rcx+44h], 1
0x1800575ca  jz      short loc_1800575E9
0x1800575cc  mov     rcx, [rcx+38h]
0x1800575d0  mov     edx, 9Ah
0x1800575d5  mov     r9d, eax
0x1800575d8  mov     r8, r12
0x1800575db  call    WPP_SF_d
0x1800575e0  jmp     short loc_1800575E9
0x1800575e2  mov     eax, [rsp+88h+var_48]
0x1800575e6  mov     [r14], eax
0x1800575e9  mov     ecx, [rdi+138h]; unsigned int
0x1800575ef  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800575f6  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x1800575fb  lea     rdx, [rdi+140h]
0x180057602  mov     r9d, 771h
0x180057608  lea     r8, aSecmgrisonexui; "SecMgrIsOneXUIRequestPending"
0x18005760f  mov     rcx, rdi
0x180057612  call    cs:__imp_ReleaseWriteLock
0x180057619  nop     dword ptr [rax+rax+00h]
0x18005761e  mov     ecx, [rdi+138h]; unsigned int
0x180057624  lea     rdx, aDerefing; "<<< Derefing <<<"
0x18005762b  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180057630  mov     r8d, 775h; int
0x180057636  lea     rdx, aSecmgrisonexui; "SecMgrIsOneXUIRequestPending"
0x18005763d  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180057640  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x180057645  mov     rcx, cs:WPP_GLOBAL_Control
0x18005764c  cmp     rcx, r15
0x18005764f  jz      short loc_18005766E
0x180057651  test    dword ptr [rcx+44h], 100h
0x180057658  jz      short loc_18005766E
0x18005765a  mov     rcx, [rcx+38h]
0x18005765e  mov     edx, 9Bh
0x180057663  mov     r9d, ebx
0x180057666  mov     r8, r12
0x180057669  call    WPP_SF_d
0x18005766e  mov     eax, ebx
0x180057670  add     rsp, 50h
0x180057674  pop     r15
0x180057676  pop     r14
0x180057678  pop     r12
0x18005767a  pop     rdi
0x18005767b  pop     rsi
0x18005767c  pop     rbp
0x18005767d  pop     rbx
0x18005767e  retn
```

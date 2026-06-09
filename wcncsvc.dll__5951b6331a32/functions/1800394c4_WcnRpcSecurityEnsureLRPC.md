# WcnRpcSecurityEnsureLRPC

- ea: `0x1800394c4`
- end: `0x180039687`
- name: `WcnRpcSecurityEnsureLRPC`
- size: `451`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE Binding)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180039090`
- `0x180039690`

## callees

- `0x180004fb8`
- `0x180005014`
- `0x180026ab4`
- `0x1800394c4`
- `0x180053004`
- `0x180056dfe`

## import_xrefs

- `RPCRT4!RpcStringBindingParseW` at `0x180039599`
- `RPCRT4!RpcStringBindingParseW` at `0x180039599`
- `RPCRT4!RpcStringFreeW` at `0x180039628`
- `RPCRT4!RpcStringFreeW` at `0x180039642`
- `RPCRT4!RpcStringFreeW` at `0x180039628`
- `RPCRT4!RpcStringFreeW` at `0x180039642`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18003952d`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18003952d`

## pseudocode

```c
__int64 __fastcall WcnRpcSecurityEnsureLRPC(RPC_BINDING_HANDLE Binding)
{
  const char *Indent; // rax
  __int64 v3; // r10
  unsigned int v4; // ebx
  _BYTE *v5; // r10
  unsigned int v6; // eax
  __int64 v7; // r10
  int v8; // edx
  RPC_WSTR v9; // rdi
  unsigned int v10; // eax
  __int64 v11; // r10
  const char *v12; // rax
  __int64 v13; // r10
  RPC_WSTR StringBinding; // [rsp+58h] [rbp+10h] BYREF
  RPC_WSTR Protseq; // [rsp+60h] [rbp+18h] BYREF

  StringBinding = 0;
  Protseq = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 50, WPP_3caf818283943d0c809de850cf5bb0ac_Traceguids, Indent);
  }
  v4 = RpcBindingToStringBindingW(Binding, &StringBinding);
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = (unsigned int)GetIndent(0);
      v8 = 51;
LABEL_8:
      WPP_SF_sd(*(_QWORD *)(v7 + 16), v8, (unsigned int)WPP_3caf818283943d0c809de850cf5bb0ac_Traceguids, v6, v4);
LABEL_17:
      v5 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v4 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
    if ( v4 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = (unsigned int)GetIndent(0);
        v8 = 52;
        goto LABEL_8;
      }
    }
    else
    {
      v9 = Protseq;
      if ( !wcscmp_0(Protseq, L"ncalrpc") )
        goto LABEL_17;
      v4 = 5;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v10 = (unsigned int)GetIndent(0);
        WPP_SF_sS(
          *(_QWORD *)(v11 + 16),
          53,
          (unsigned int)WPP_3caf818283943d0c809de850cf5bb0ac_Traceguids,
          v10,
          (__int64)v9);
        goto LABEL_17;
      }
    }
  }
  if ( StringBinding )
  {
    RpcStringFreeW(&StringBinding);
    v5 = WPP_GLOBAL_Control;
  }
  if ( Protseq )
  {
    RpcStringFreeW(&Protseq);
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 6u )
  {
    v12 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v13 + 16), 54, WPP_3caf818283943d0c809de850cf5bb0ac_Traceguids, v12);
  }
  return v4;
}

```

## disassembly

```asm
0x1800394c4  mov     [rsp+arg_0], rbx
0x1800394c9  push    rbp
0x1800394ca  push    rdi
0x1800394cb  push    r14
0x1800394cd  sub     rsp, 30h
0x1800394d1  mov     rbx, rcx
0x1800394d4  mov     [rsp+48h+StringBinding], 0
0x1800394dd  mov     [rsp+48h+Protseq], 0
0x1800394e6  mov     r10, cs:WPP_GLOBAL_Control
0x1800394ed  lea     rbp, WPP_GLOBAL_Control
0x1800394f4  lea     r14, WPP_3caf818283943d0c809de850cf5bb0ac_Traceguids
0x1800394fb  cmp     r10, rbp
0x1800394fe  jz      short loc_180039525
0x180039500  cmp     byte ptr [r10+19h], 6
0x180039505  jb      short loc_180039525
0x180039507  mov     ecx, 1; int
0x18003950c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180039511  mov     rcx, [r10+10h]
0x180039515  mov     edx, 32h ; '2'
0x18003951a  mov     r9, rax
0x18003951d  mov     r8, r14
0x180039520  call    WPP_SF_s
0x180039525  lea     rdx, [rsp+48h+StringBinding]; StringBinding
0x18003952a  mov     rcx, rbx; Binding
0x18003952d  call    cs:__imp_RpcBindingToStringBindingW
0x180039533  mov     ebx, eax
0x180039535  test    eax, eax
0x180039537  jz      short loc_180039578
0x180039539  mov     r10, cs:WPP_GLOBAL_Control
0x180039540  cmp     r10, rbp
0x180039543  jz      loc_18003961B
0x180039549  cmp     byte ptr [r10+19h], 2
0x18003954e  jb      loc_18003961B
0x180039554  xor     ecx, ecx; int
0x180039556  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003955b  mov     edx, 33h ; '3'
0x180039560  mov     rcx, [r10+10h]
0x180039564  mov     r9, rax
0x180039567  mov     r8, r14
0x18003956a  mov     dword ptr [rsp+48h+Endpoint], ebx
0x18003956e  call    WPP_SF_sd
0x180039573  jmp     loc_180039614
0x180039578  mov     rcx, [rsp+48h+StringBinding]; StringBinding
0x18003957d  lea     r8, [rsp+48h+Protseq]; Protseq
0x180039582  mov     [rsp+48h+NetworkOptions], 0; NetworkOptions
0x18003958b  xor     r9d, r9d; NetworkAddr
0x18003958e  xor     edx, edx; ObjUuid
0x180039590  mov     [rsp+48h+Endpoint], 0; Endpoint
0x180039599  call    cs:__imp_RpcStringBindingParseW
0x18003959f  mov     ebx, eax
0x1800395a1  test    eax, eax
0x1800395a3  jz      short loc_1800395C6
0x1800395a5  mov     r10, cs:WPP_GLOBAL_Control
0x1800395ac  cmp     r10, rbp
0x1800395af  jz      short loc_18003961B
0x1800395b1  cmp     byte ptr [r10+19h], 2
0x1800395b6  jb      short loc_18003961B
0x1800395b8  xor     ecx, ecx; int
0x1800395ba  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800395bf  mov     edx, 34h ; '4'
0x1800395c4  jmp     short loc_180039560
0x1800395c6  mov     rdi, [rsp+48h+Protseq]
0x1800395cb  lea     rdx, aNcalrpc; "ncalrpc"
0x1800395d2  mov     rcx, rdi; String1
0x1800395d5  call    wcscmp_0
0x1800395da  test    eax, eax
0x1800395dc  jz      short loc_180039614
0x1800395de  mov     ebx, 5
0x1800395e3  mov     r10, cs:WPP_GLOBAL_Control
0x1800395ea  cmp     r10, rbp
0x1800395ed  jz      short loc_18003961B
0x1800395ef  cmp     byte ptr [r10+19h], 3
0x1800395f4  jb      short loc_18003961B
0x1800395f6  xor     ecx, ecx; int
0x1800395f8  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800395fd  mov     rcx, [r10+10h]
0x180039601  lea     edx, [rbx+30h]
0x180039604  mov     r9, rax
0x180039607  mov     [rsp+48h+Endpoint], rdi
0x18003960c  mov     r8, r14
0x18003960f  call    WPP_SF_sS
0x180039614  mov     r10, cs:WPP_GLOBAL_Control
0x18003961b  cmp     [rsp+48h+StringBinding], 0
0x180039621  jz      short loc_180039635
0x180039623  lea     rcx, [rsp+48h+StringBinding]; String
0x180039628  call    cs:__imp_RpcStringFreeW
0x18003962e  mov     r10, cs:WPP_GLOBAL_Control
0x180039635  cmp     [rsp+48h+Protseq], 0
0x18003963b  jz      short loc_18003964F
0x18003963d  lea     rcx, [rsp+48h+Protseq]; String
0x180039642  call    cs:__imp_RpcStringFreeW
0x180039648  mov     r10, cs:WPP_GLOBAL_Control
0x18003964f  cmp     r10, rbp
0x180039652  jz      short loc_180039677
0x180039654  cmp     byte ptr [r10+19h], 6
0x180039659  jb      short loc_180039677
0x18003965b  or      ecx, 0FFFFFFFFh; int
0x18003965e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180039663  mov     rcx, [r10+10h]
0x180039667  mov     edx, 36h ; '6'
0x18003966c  mov     r9, rax
0x18003966f  mov     r8, r14
0x180039672  call    WPP_SF_s
0x180039677  mov     eax, ebx
0x180039679  mov     rbx, [rsp+48h+arg_0]
0x18003967e  add     rsp, 30h
0x180039682  pop     r14
0x180039684  pop     rdi
0x180039685  pop     rbp
0x180039686  retn
```

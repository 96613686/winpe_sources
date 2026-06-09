# PNP_Local_ExportPnpState

- ea: `0x180015550`
- end: `0x1800156b9`
- name: `PNP_Local_ExportPnpState`
- size: `361`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, __int64, int, int, __int64, int, _WORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000be30`
- `0x1800117d4`
- `0x180013d90`
- `0x180015550`
- `0x1800156c0`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18001567b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001567b`

## pseudocode

```c
RPC_STATUS __fastcall PNP_Local_ExportPnpState(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        int a6,
        _WORD *a7,
        _DWORD *a8)
{
  __int128 v11; // xmm0
  int v12; // eax
  RPC_STATUS result; // eax
  int Reply[4]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v15; // [rsp+40h] [rbp-48h]

  Reply[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e8d02699756f3b086e4657f0935e50be_Traceguids);
  if ( (PnpServiceInstallOptions & 0x100) != 0 )
  {
    if ( a7 && a8 )
    {
      if ( (unsigned int)VerifyClientAccessToObject(2) )
      {
        *a7 = 0;
        *a8 = 0;
        LODWORD(v11) = 0;
        if ( *(_DWORD *)a5 == 1 )
        {
          v11 = *(_OWORD *)*(_QWORD *)(a5 + 8);
          v15 = v11;
          v12 = Reply[0];
        }
        else
        {
          v12 = 59;
          Reply[0] = 59;
        }
        if ( !v12 )
          *a8 = PnpExportState(a3, (_DWORD)a7, a6, v11, a4);
      }
      else
      {
        Reply[0] = 51;
      }
    }
    else
    {
      Reply[0] = 3;
    }
  }
  else
  {
    Reply[0] = 50;
  }
  result = RpcAsyncCompleteCall(pAsync, Reply);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e8d02699756f3b086e4657f0935e50be_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180015550  mov     [rsp+arg_0], rcx
0x180015555  push    rbx
0x180015556  push    rsi
0x180015557  push    rdi
0x180015558  push    r12
0x18001555a  push    r14
0x18001555c  push    r15
0x18001555e  sub     rsp, 58h
0x180015562  mov     r15d, r9d
0x180015565  mov     r12, r8
0x180015568  mov     rsi, rcx
0x18001556b  mov     [rsp+88h+Reply], 0
0x180015573  lea     r14, WPP_GLOBAL_Control
0x18001557a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015581  cmp     rcx, r14
0x180015584  jz      short loc_1800155A4
0x180015586  test    dword ptr [rcx+1Ch], 10000000h
0x18001558d  jz      short loc_1800155A4
0x18001558f  mov     edx, 0Ah
0x180015594  lea     r8, WPP_e8d02699756f3b086e4657f0935e50be_Traceguids
0x18001559b  mov     rcx, [rcx+10h]
0x18001559f  call    WPP_SF_
0x1800155a4  test    cs:PnpServiceInstallOptions, 100h
0x1800155ae  jnz     short loc_1800155BD
0x1800155b0  mov     [rsp+88h+Reply], 32h ; '2'
0x1800155b8  jmp     loc_180015673
0x1800155bd  mov     rbx, [rsp+88h+arg_30]
0x1800155c5  test    rbx, rbx
0x1800155c8  jz      loc_18001566B
0x1800155ce  mov     rdi, [rsp+88h+arg_38]
0x1800155d6  test    rdi, rdi
0x1800155d9  jz      loc_18001566B
0x1800155df  mov     ecx, 2
0x1800155e4  call    VerifyClientAccessToObject
0x1800155e9  test    eax, eax
0x1800155eb  jnz     short loc_1800155F7
0x1800155ed  mov     [rsp+88h+Reply], 33h ; '3'
0x1800155f5  jmp     short loc_180015673
0x1800155f7  xor     eax, eax
0x1800155f9  mov     [rbx], ax
0x1800155fc  mov     [rdi], eax
0x1800155fe  xorps   xmm0, xmm0
0x180015601  mov     rdx, [rsp+88h+arg_20]
0x180015609  cmp     dword ptr [rdx], 1
0x18001560c  jz      short loc_180015619
0x18001560e  mov     eax, 3Bh ; ';'
0x180015613  mov     [rsp+88h+Reply], eax
0x180015617  jmp     short loc_180015629
0x180015619  mov     rax, [rdx+8]
0x18001561d  movups  xmm0, xmmword ptr [rax]
0x180015620  movups  [rsp+88h+var_48], xmm0
0x180015625  mov     eax, [rsp+88h+Reply]
0x180015629  test    eax, eax
0x18001562b  jnz     short loc_180015673
0x18001562d  mov     [rsp+88h+var_68], r15d
0x180015632  movq    r9, xmm0
0x180015637  mov     r8d, [rsp+88h+arg_28]
0x18001563f  mov     rdx, rbx
0x180015642  mov     rcx, r12
0x180015645  call    PnpExportState
0x18001564a  mov     [rdi], eax
0x18001564c  jmp     short loc_180015673
0x18001564e  mov     ecx, eax
0x180015650  lea     r8, [rsp+88h+Reply]
0x180015655  call    PnPExceptionHandler
0x18001565a  lea     r14, WPP_GLOBAL_Control
0x180015661  mov     rsi, [rsp+88h+arg_0]
0x180015669  jmp     short loc_180015673
0x18001566b  mov     [rsp+88h+Reply], 3
0x180015673  lea     rdx, [rsp+88h+Reply]; Reply
0x180015678  mov     rcx, rsi; pAsync
0x18001567b  call    cs:__imp_RpcAsyncCompleteCall
0x180015681  mov     rcx, cs:WPP_GLOBAL_Control
0x180015688  cmp     rcx, r14
0x18001568b  jz      short loc_1800156AB
0x18001568d  test    dword ptr [rcx+1Ch], 10000000h
0x180015694  jz      short loc_1800156AB
0x180015696  mov     edx, 0Bh
0x18001569b  lea     r8, WPP_e8d02699756f3b086e4657f0935e50be_Traceguids
0x1800156a2  mov     rcx, [rcx+10h]
0x1800156a6  call    WPP_SF_
0x1800156ab  add     rsp, 58h
0x1800156af  pop     r15
0x1800156b1  pop     r14
0x1800156b3  pop     r12
0x1800156b5  pop     rdi
0x1800156b6  pop     rsi
0x1800156b7  pop     rbx
0x1800156b8  retn
0x18001924a  push    rbp
0x18001924c  sub     rsp, 30h
0x180019250  mov     rbp, rdx
0x180019253  mov     eax, 1
0x180019258  add     rsp, 30h
0x18001925c  pop     rbp
0x18001925d  retn
```

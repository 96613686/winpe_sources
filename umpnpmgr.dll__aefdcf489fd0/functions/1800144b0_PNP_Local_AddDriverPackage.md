# PNP_Local_AddDriverPackage

- ea: `0x1800144b0`
- end: `0x1800146c5`
- name: `PNP_Local_AddDriverPackage`
- size: `533`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, __int64, __int64, __int64, unsigned int, int *, _DWORD *, __int64, _DWORD *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180001190`
- `0x18000be30`
- `0x18000bf60`
- `0x18000f110`
- `0x18001091c`
- `0x1800117d4`
- `0x180013d90`
- `0x1800144b0`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180014684`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180014684`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014676`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014676`

## pseudocode

```c
RPC_STATUS __fastcall PNP_Local_AddDriverPackage(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        int *a6,
        _DWORD *a7,
        __int64 a8,
        _DWORD *a9,
        int a10)
{
  int v13; // eax
  __int128 *v14; // rdx
  int v15; // eax
  const wchar_t *v16; // rcx
  RPC_STATUS result; // eax
  int Reply; // [rsp+50h] [rbp-68h] BYREF
  HANDLE hObject[2]; // [rsp+58h] [rbp-60h] BYREF
  __int128 v20; // [rsp+68h] [rbp-50h]

  Reply = 0;
  hObject[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
  if ( (PnpServiceInstallOptions & 0x10) == 0 )
  {
    Reply = 50;
    goto LABEL_25;
  }
  if ( !(unsigned int)IsClientLocal()
    || !(unsigned int)UserDriverInstallAllowed() && !(unsigned int)VerifyClientAccessToObject(2) )
  {
    goto LABEL_7;
  }
  if ( *a7 < 0x104u )
  {
    Reply = 26;
    goto LABEL_25;
  }
  if ( a5 > 0xFFFF )
    goto LABEL_13;
  if ( !(unsigned int)GetClientUserToken(hObject) )
  {
LABEL_7:
    Reply = 51;
    goto LABEL_25;
  }
  v13 = *a6;
  if ( (unsigned int)*a6 <= 1 )
  {
    v14 = (__int128 *)*((_QWORD *)a6 + 1);
    if ( !v14 )
    {
LABEL_13:
      Reply = 31;
      goto LABEL_25;
    }
    v20 = 0;
    if ( v13 == 1 )
    {
      v20 = *v14;
      v15 = Reply;
    }
    else
    {
      v15 = 59;
      Reply = 59;
    }
    if ( !v15 )
    {
      v16 = L"WinSta0\\Default";
      if ( *((_QWORD *)&v20 + 1) )
        v16 = (const wchar_t *)*((_QWORD *)&v20 + 1);
      *((_QWORD *)&v20 + 1) = v16;
      *a9 = 0;
      *a9 = PnpAddDriverPackage(hObject[0], a3, a4, (unsigned __int16)a5, a8, a7, v20, v16, a10);
    }
  }
  else
  {
    Reply = 52;
  }
LABEL_25:
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  result = RpcAsyncCompleteCall(pAsync, &Reply);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1800144b0  mov     [rsp+arg_0], rcx
0x1800144b5  push    rbx
0x1800144b6  push    rsi
0x1800144b7  push    rdi
0x1800144b8  push    r12
0x1800144ba  push    r14
0x1800144bc  push    r15
0x1800144be  sub     rsp, 88h
0x1800144c5  mov     r15, r9
0x1800144c8  mov     r12, r8
0x1800144cb  mov     rdi, rcx
0x1800144ce  mov     [rsp+0B8h+Reply], 0
0x1800144d6  mov     [rsp+0B8h+hObject], 0
0x1800144df  lea     rsi, WPP_GLOBAL_Control
0x1800144e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144ed  cmp     rcx, rsi
0x1800144f0  jz      short loc_180014511
0x1800144f2  test    dword ptr [rcx+1Ch], 10000000h
0x1800144f9  jz      short loc_180014511
0x1800144fb  mov     edx, 16h
0x180014500  lea     r8, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids
0x180014507  mov     rcx, [rcx+10h]
0x18001450b  call    WPP_SF_
0x180014510  nop
0x180014511  test    byte ptr cs:PnpServiceInstallOptions, 10h
0x180014518  jnz     short loc_180014527
0x18001451a  mov     [rsp+0B8h+Reply], 32h ; '2'
0x180014522  jmp     loc_18001464F
0x180014527  call    IsClientLocal
0x18001452c  test    eax, eax
0x18001452e  jnz     short loc_18001453D
0x180014530  mov     [rsp+0B8h+Reply], 33h ; '3'
0x180014538  jmp     loc_18001464F
0x18001453d  call    UserDriverInstallAllowed
0x180014542  test    eax, eax
0x180014544  jnz     short loc_180014552
0x180014546  lea     ecx, [rax+2]
0x180014549  call    VerifyClientAccessToObject
0x18001454e  test    eax, eax
0x180014550  jz      short loc_180014530
0x180014552  mov     r14, [rsp+0B8h+arg_30]
0x18001455a  cmp     dword ptr [r14], 104h
0x180014561  jnb     short loc_180014570
0x180014563  mov     [rsp+0B8h+Reply], 1Ah
0x18001456b  jmp     loc_18001464F
0x180014570  cmp     [rsp+0B8h+arg_20], 0FFFFh
0x18001457b  jbe     short loc_18001458A
0x18001457d  mov     [rsp+0B8h+Reply], 1Fh
0x180014585  jmp     loc_18001464F
0x18001458a  lea     rcx, [rsp+0B8h+hObject]
0x18001458f  call    GetClientUserToken
0x180014594  test    eax, eax
0x180014596  jz      short loc_180014530
0x180014598  mov     rcx, [rsp+0B8h+arg_28]
0x1800145a0  mov     eax, [rcx]
0x1800145a2  cmp     eax, 1
0x1800145a5  jbe     short loc_1800145B4
0x1800145a7  mov     [rsp+0B8h+Reply], 34h ; '4'
0x1800145af  jmp     loc_18001464F
0x1800145b4  mov     rdx, [rcx+8]
0x1800145b8  test    rdx, rdx
0x1800145bb  jz      short loc_18001457D
0x1800145bd  xorps   xmm0, xmm0
0x1800145c0  movups  [rsp+0B8h+var_50], xmm0
0x1800145c5  cmp     eax, 1
0x1800145c8  jz      short loc_1800145D5
0x1800145ca  mov     eax, 3Bh ; ';'
0x1800145cf  mov     [rsp+0B8h+Reply], eax
0x1800145d3  jmp     short loc_1800145E2
0x1800145d5  movups  xmm0, xmmword ptr [rdx]
0x1800145d8  movdqu  [rsp+0B8h+var_50], xmm0
0x1800145de  mov     eax, [rsp+0B8h+Reply]
0x1800145e2  test    eax, eax
0x1800145e4  jnz     short loc_18001464F
0x1800145e6  lea     rcx, aWinsta0Default; "WinSta0\\Default"
0x1800145ed  cmp     qword ptr [rsp+0B8h+var_50+8], 0
0x1800145f3  cmovnz  rcx, qword ptr [rsp+0B8h+var_50+8]
0x1800145f9  mov     qword ptr [rsp+0B8h+var_50+8], rcx
0x1800145fe  mov     rbx, [rsp+0B8h+arg_40]
0x180014606  mov     [rbx], eax
0x180014608  mov     eax, [rsp+0B8h+arg_48]
0x18001460f  mov     [rsp+0B8h+var_78], eax
0x180014613  mov     [rsp+0B8h+var_80], rcx
0x180014618  mov     rax, qword ptr [rsp+0B8h+var_50]
0x18001461d  mov     [rsp+0B8h+var_88], rax
0x180014622  mov     [rsp+0B8h+var_90], r14
0x180014627  mov     rax, [rsp+0B8h+arg_38]
0x18001462f  mov     [rsp+0B8h+var_98], rax
0x180014634  movzx   r9d, word ptr [rsp+0B8h+arg_20]
0x18001463d  mov     r8, r15
0x180014640  mov     rdx, r12
0x180014643  mov     rcx, [rsp+0B8h+hObject]
0x180014648  call    PnpAddDriverPackage
0x18001464d  mov     [rbx], eax
0x18001464f  jmp     short loc_18001466C
0x180014651  mov     ecx, eax
0x180014653  lea     r8, [rsp+0B8h+Reply]
0x180014658  call    PnPExceptionHandler
0x18001465d  lea     rsi, WPP_GLOBAL_Control
0x180014664  mov     rdi, [rsp+0B8h+arg_0]
0x18001466c  mov     rcx, [rsp+0B8h+hObject]; hObject
0x180014671  test    rcx, rcx
0x180014674  jz      short loc_18001467C
0x180014676  call    cs:__imp_CloseHandle
0x18001467c  lea     rdx, [rsp+0B8h+Reply]; Reply
0x180014681  mov     rcx, rdi; pAsync
0x180014684  call    cs:__imp_RpcAsyncCompleteCall
0x18001468a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014691  cmp     rcx, rsi
0x180014694  jz      short loc_1800146B4
0x180014696  test    dword ptr [rcx+1Ch], 10000000h
0x18001469d  jz      short loc_1800146B4
0x18001469f  mov     edx, 17h
0x1800146a4  lea     r8, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids
0x1800146ab  mov     rcx, [rcx+10h]
0x1800146af  call    WPP_SF_
0x1800146b4  add     rsp, 88h
0x1800146bb  pop     r15
0x1800146bd  pop     r14
0x1800146bf  pop     r12
0x1800146c1  pop     rdi
0x1800146c2  pop     rsi
0x1800146c3  pop     rbx
0x1800146c4  retn
0x1800191cf  push    rbp
0x1800191d1  sub     rsp, 50h
0x1800191d5  mov     rbp, rdx
0x1800191d8  mov     eax, 1
0x1800191dd  add     rsp, 50h
0x1800191e1  pop     rbp
0x1800191e2  retn
```

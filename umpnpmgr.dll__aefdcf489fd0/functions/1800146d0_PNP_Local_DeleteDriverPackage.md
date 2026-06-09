# PNP_Local_DeleteDriverPackage

- ea: `0x1800146d0`
- end: `0x18001489a`
- name: `PNP_Local_DeleteDriverPackage`
- size: `458`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, __int64, __int64, int *, _DWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180004180`
- `0x18000be30`
- `0x18000f110`
- `0x18001091c`
- `0x1800117d4`
- `0x180013d90`
- `0x1800146d0`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18001485f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001485f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014851`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014851`

## pseudocode

```c
RPC_STATUS __fastcall PNP_Local_DeleteDriverPackage(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        __int64 a3,
        int *a4,
        _DWORD *a5)
{
  int v8; // eax
  __int128 *v9; // rcx
  int v10; // eax
  const wchar_t *v11; // r9
  int v12; // eax
  RPC_STATUS result; // eax
  int Reply; // [rsp+30h] [rbp-58h] BYREF
  int v15; // [rsp+34h] [rbp-54h]
  HANDLE hObject[2]; // [rsp+38h] [rbp-50h] BYREF
  __int128 v17; // [rsp+48h] [rbp-40h]

  Reply = 0;
  hObject[0] = 0;
  v15 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
  if ( (PnpServiceInstallOptions & 0x10) != 0 )
  {
    if ( (unsigned int)IsClientLocal()
      && (unsigned int)VerifyClientAccessToObject(2)
      && (unsigned int)GetClientUserToken(hObject) )
    {
      v8 = *a4;
      if ( (unsigned int)*a4 <= 1 )
      {
        v9 = (__int128 *)*((_QWORD *)a4 + 1);
        if ( v9 )
        {
          v17 = 0;
          if ( v8 == 1 )
          {
            v17 = *v9;
            v10 = Reply;
          }
          else
          {
            v10 = 59;
            Reply = 59;
          }
          if ( !v10 )
          {
            v11 = L"WinSta0\\Default";
            if ( *((_QWORD *)&v17 + 1) )
              v11 = (const wchar_t *)*((_QWORD *)&v17 + 1);
            *((_QWORD *)&v17 + 1) = v11;
            *a5 = 0;
            v12 = PnpDeleteDriverPackage(hObject[0], a3, v17);
            *a5 = v12;
            if ( !v12 && v15 )
              Reply = 34;
          }
        }
        else
        {
          Reply = 31;
        }
      }
      else
      {
        Reply = 52;
      }
    }
    else
    {
      Reply = 51;
    }
  }
  else
  {
    Reply = 50;
  }
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  result = RpcAsyncCompleteCall(pAsync, &Reply);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1800146d0  mov     rax, rsp
0x1800146d3  mov     [rax+8], rcx
0x1800146d7  push    rbx
0x1800146d8  push    rsi
0x1800146d9  push    r14
0x1800146db  push    r15
0x1800146dd  sub     rsp, 68h
0x1800146e1  mov     rbx, r9
0x1800146e4  mov     r15, r8
0x1800146e7  mov     rsi, rcx
0x1800146ea  mov     dword ptr [rax-58h], 0
0x1800146f1  mov     qword ptr [rax-50h], 0
0x1800146f9  mov     dword ptr [rax-54h], 0
0x180014700  lea     r14, WPP_GLOBAL_Control
0x180014707  mov     rcx, cs:WPP_GLOBAL_Control
0x18001470e  cmp     rcx, r14
0x180014711  jz      short loc_180014732
0x180014713  test    dword ptr [rcx+1Ch], 10000000h
0x18001471a  jz      short loc_180014732
0x18001471c  mov     edx, 24h ; '$'
0x180014721  lea     r8, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids
0x180014728  mov     rcx, [rcx+10h]
0x18001472c  call    WPP_SF_
0x180014731  nop
0x180014732  test    byte ptr cs:PnpServiceInstallOptions, 10h
0x180014739  jnz     short loc_180014748
0x18001473b  mov     [rsp+88h+Reply], 32h ; '2'
0x180014743  jmp     loc_18001482A
0x180014748  call    IsClientLocal
0x18001474d  test    eax, eax
0x18001474f  jnz     short loc_18001475E
0x180014751  mov     [rsp+88h+Reply], 33h ; '3'
0x180014759  jmp     loc_18001482A
0x18001475e  mov     ecx, 2
0x180014763  call    VerifyClientAccessToObject
0x180014768  test    eax, eax
0x18001476a  jz      short loc_180014751
0x18001476c  lea     rcx, [rsp+88h+hObject]
0x180014771  call    GetClientUserToken
0x180014776  test    eax, eax
0x180014778  jz      short loc_180014751
0x18001477a  mov     eax, [rbx]
0x18001477c  cmp     eax, 1
0x18001477f  jbe     short loc_18001478E
0x180014781  mov     [rsp+88h+Reply], 34h ; '4'
0x180014789  jmp     loc_18001482A
0x18001478e  mov     rcx, [rbx+8]
0x180014792  test    rcx, rcx
0x180014795  jnz     short loc_1800147A4
0x180014797  mov     [rsp+88h+Reply], 1Fh
0x18001479f  jmp     loc_18001482A
0x1800147a4  xorps   xmm0, xmm0
0x1800147a7  movups  [rsp+88h+var_40], xmm0
0x1800147ac  cmp     eax, 1
0x1800147af  jz      short loc_1800147BC
0x1800147b1  mov     eax, 3Bh ; ';'
0x1800147b6  mov     [rsp+88h+Reply], eax
0x1800147ba  jmp     short loc_1800147C9
0x1800147bc  movups  xmm0, xmmword ptr [rcx]
0x1800147bf  movdqu  [rsp+88h+var_40], xmm0
0x1800147c5  mov     eax, [rsp+88h+Reply]
0x1800147c9  test    eax, eax
0x1800147cb  jnz     short loc_18001482A
0x1800147cd  lea     r9, aWinsta0Default; "WinSta0\\Default"
0x1800147d4  cmp     qword ptr [rsp+88h+var_40+8], 0
0x1800147da  cmovnz  r9, qword ptr [rsp+88h+var_40+8]
0x1800147e0  mov     qword ptr [rsp+88h+var_40+8], r9
0x1800147e5  mov     rbx, [rsp+88h+arg_20]
0x1800147ed  mov     [rbx], eax
0x1800147ef  lea     rax, [rsp+88h+var_54]
0x1800147f4  mov     [rsp+88h+var_60], rax
0x1800147f9  mov     eax, [rsp+88h+arg_28]
0x180014800  mov     [rsp+88h+var_68], eax
0x180014804  mov     r8, qword ptr [rsp+88h+var_40]
0x180014809  mov     rdx, r15
0x18001480c  mov     rcx, [rsp+88h+hObject]
0x180014811  call    PnpDeleteDriverPackage
0x180014816  mov     [rbx], eax
0x180014818  test    eax, eax
0x18001481a  jnz     short loc_18001482A
0x18001481c  cmp     [rsp+88h+var_54], eax
0x180014820  jz      short loc_18001482A
0x180014822  mov     [rsp+88h+Reply], 22h ; '"'
0x18001482a  jmp     short loc_180014847
0x18001482c  mov     ecx, eax
0x18001482e  lea     r8, [rsp+88h+Reply]
0x180014833  call    PnPExceptionHandler
0x180014838  lea     r14, WPP_GLOBAL_Control
0x18001483f  mov     rsi, [rsp+88h+arg_0]
0x180014847  mov     rcx, [rsp+88h+hObject]; hObject
0x18001484c  test    rcx, rcx
0x18001484f  jz      short loc_180014857
0x180014851  call    cs:__imp_CloseHandle
0x180014857  lea     rdx, [rsp+88h+Reply]; Reply
0x18001485c  mov     rcx, rsi; pAsync
0x18001485f  call    cs:__imp_RpcAsyncCompleteCall
0x180014865  mov     rcx, cs:WPP_GLOBAL_Control
0x18001486c  cmp     rcx, r14
0x18001486f  jz      short loc_18001488F
0x180014871  test    dword ptr [rcx+1Ch], 10000000h
0x180014878  jz      short loc_18001488F
0x18001487a  mov     edx, 25h ; '%'
0x18001487f  lea     r8, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids
0x180014886  mov     rcx, [rcx+10h]
0x18001488a  call    WPP_SF_
0x18001488f  add     rsp, 68h
0x180014893  pop     r15
0x180014895  pop     r14
0x180014897  pop     rsi
0x180014898  pop     rbx
0x180014899  retn
0x18001924a  push    rbp
0x18001924c  sub     rsp, 30h
0x180019250  mov     rbp, rdx
0x180019253  mov     eax, 1
0x180019258  add     rsp, 30h
0x18001925c  pop     rbp
0x18001925d  retn
```

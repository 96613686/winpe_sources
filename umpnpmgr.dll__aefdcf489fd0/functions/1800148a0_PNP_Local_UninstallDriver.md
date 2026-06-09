# PNP_Local_UninstallDriver

- ea: `0x1800148a0`
- end: `0x180014a7d`
- name: `PNP_Local_UninstallDriver`
- size: `477`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, __int64, __int64, __int64, int *, _DWORD *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000f110`
- `0x18001091c`
- `0x1800117d4`
- `0x180013d90`
- `0x1800148a0`
- `0x180014a84`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180014a36`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180014a36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014a28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014a28`

## pseudocode

```c
RPC_STATUS __fastcall PNP_Local_UninstallDriver(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int *a5,
        _DWORD *a6,
        int a7)
{
  int v10; // eax
  __int128 *v11; // rdx
  int v12; // eax
  const wchar_t *v13; // rcx
  RPC_STATUS result; // eax
  int Reply; // [rsp+40h] [rbp-48h] BYREF
  int v16; // [rsp+44h] [rbp-44h] BYREF
  HANDLE hObject[2]; // [rsp+48h] [rbp-40h] BYREF
  __int128 v18; // [rsp+58h] [rbp-30h]

  Reply = 0;
  hObject[0] = 0;
  v16 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
  if ( (PnpServiceInstallOptions & 0x20) != 0 )
  {
    if ( (unsigned int)IsClientLocal() && (unsigned int)GetClientUserToken(hObject) )
    {
      v10 = *a5;
      if ( (unsigned int)*a5 <= 1 )
      {
        v11 = (__int128 *)*((_QWORD *)a5 + 1);
        if ( v11 )
        {
          v18 = 0;
          if ( v10 == 1 )
          {
            v18 = *v11;
            v12 = Reply;
          }
          else
          {
            v12 = 59;
            Reply = 59;
          }
          if ( !v12 )
          {
            v13 = L"WinSta0\\Default";
            if ( *((_QWORD *)&v18 + 1) )
              v13 = (const wchar_t *)*((_QWORD *)&v18 + 1);
            *((_QWORD *)&v18 + 1) = v13;
            *a6 = 0;
            *a6 = PnpUninstallDriver(hObject[0], a3, a4, v18, v13, a7, &v16);
            if ( v16 )
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
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1800148a0  mov     rax, rsp
0x1800148a3  mov     [rax+10h], rbx
0x1800148a7  mov     [rax+18h], rsi
0x1800148ab  mov     [rax+8], rcx
0x1800148af  push    r12
0x1800148b1  push    r14
0x1800148b3  push    r15
0x1800148b5  sub     rsp, 70h
0x1800148b9  mov     r15, r9
0x1800148bc  mov     r12, r8
0x1800148bf  mov     rsi, rcx
0x1800148c2  mov     dword ptr [rax-48h], 0
0x1800148c9  mov     qword ptr [rax-40h], 0
0x1800148d1  mov     dword ptr [rax-44h], 0
0x1800148d8  lea     r14, WPP_GLOBAL_Control
0x1800148df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800148e6  cmp     rcx, r14
0x1800148e9  jz      short loc_18001490A
0x1800148eb  test    dword ptr [rcx+1Ch], 10000000h
0x1800148f2  jz      short loc_18001490A
0x1800148f4  mov     edx, 40h ; '@'
0x1800148f9  lea     r8, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids
0x180014900  mov     rcx, [rcx+10h]
0x180014904  call    WPP_SF_
0x180014909  nop
0x18001490a  test    byte ptr cs:PnpServiceInstallOptions, 20h
0x180014911  jnz     short loc_180014920
0x180014913  mov     [rsp+88h+Reply], 32h ; '2'
0x18001491b  jmp     loc_180014A01
0x180014920  call    IsClientLocal
0x180014925  test    eax, eax
0x180014927  jnz     short loc_180014936
0x180014929  mov     [rsp+88h+Reply], 33h ; '3'
0x180014931  jmp     loc_180014A01
0x180014936  lea     rcx, [rsp+88h+hObject]
0x18001493b  call    GetClientUserToken
0x180014940  test    eax, eax
0x180014942  jz      short loc_180014929
0x180014944  mov     rcx, [rsp+88h+arg_20]
0x18001494c  mov     eax, [rcx]
0x18001494e  cmp     eax, 1
0x180014951  jbe     short loc_180014960
0x180014953  mov     [rsp+88h+Reply], 34h ; '4'
0x18001495b  jmp     loc_180014A01
0x180014960  mov     rdx, [rcx+8]
0x180014964  test    rdx, rdx
0x180014967  jnz     short loc_180014976
0x180014969  mov     [rsp+88h+Reply], 1Fh
0x180014971  jmp     loc_180014A01
0x180014976  xorps   xmm0, xmm0
0x180014979  movups  [rsp+88h+var_30], xmm0
0x18001497e  cmp     eax, 1
0x180014981  jz      short loc_18001498E
0x180014983  mov     eax, 3Bh ; ';'
0x180014988  mov     [rsp+88h+Reply], eax
0x18001498c  jmp     short loc_18001499B
0x18001498e  movups  xmm0, xmmword ptr [rdx]
0x180014991  movdqu  [rsp+88h+var_30], xmm0
0x180014997  mov     eax, [rsp+88h+Reply]
0x18001499b  test    eax, eax
0x18001499d  jnz     short loc_180014A01
0x18001499f  lea     rcx, aWinsta0Default; "WinSta0\\Default"
0x1800149a6  cmp     qword ptr [rsp+88h+var_30+8], 0
0x1800149ac  cmovnz  rcx, qword ptr [rsp+88h+var_30+8]
0x1800149b2  mov     qword ptr [rsp+88h+var_30+8], rcx
0x1800149b7  mov     rbx, [rsp+88h+arg_28]
0x1800149bf  mov     [rbx], eax
0x1800149c1  lea     rax, [rsp+88h+var_44]
0x1800149c6  mov     [rsp+88h+var_58], rax
0x1800149cb  mov     eax, [rsp+88h+arg_30]
0x1800149d2  mov     [rsp+88h+var_60], eax
0x1800149d6  mov     [rsp+88h+var_68], rcx
0x1800149db  mov     r9, qword ptr [rsp+88h+var_30]
0x1800149e0  mov     r8, r15
0x1800149e3  mov     rdx, r12
0x1800149e6  mov     rcx, [rsp+88h+hObject]
0x1800149eb  call    PnpUninstallDriver
0x1800149f0  mov     [rbx], eax
0x1800149f2  cmp     [rsp+88h+var_44], 0
0x1800149f7  jz      short loc_180014A01
0x1800149f9  mov     [rsp+88h+Reply], 22h ; '"'
0x180014a01  jmp     short loc_180014A1E
0x180014a03  mov     ecx, eax
0x180014a05  lea     r8, [rsp+88h+Reply]
0x180014a0a  call    PnPExceptionHandler
0x180014a0f  lea     r14, WPP_GLOBAL_Control
0x180014a16  mov     rsi, [rsp+88h+arg_0]
0x180014a1e  mov     rcx, [rsp+88h+hObject]; hObject
0x180014a23  test    rcx, rcx
0x180014a26  jz      short loc_180014A2E
0x180014a28  call    cs:__imp_CloseHandle
0x180014a2e  lea     rdx, [rsp+88h+Reply]; Reply
0x180014a33  mov     rcx, rsi; pAsync
0x180014a36  call    cs:__imp_RpcAsyncCompleteCall
0x180014a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a43  cmp     rcx, r14
0x180014a46  jz      short loc_180014A66
0x180014a48  test    dword ptr [rcx+1Ch], 10000000h
0x180014a4f  jz      short loc_180014A66
0x180014a51  mov     edx, 41h ; 'A'
0x180014a56  lea     r8, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids
0x180014a5d  mov     rcx, [rcx+10h]
0x180014a61  call    WPP_SF_
0x180014a66  lea     r11, [rsp+88h+var_18]
0x180014a6b  mov     rbx, [r11+28h]
0x180014a6f  mov     rsi, [r11+30h]
0x180014a73  mov     rsp, r11
0x180014a76  pop     r15
0x180014a78  pop     r14
0x180014a7a  pop     r12
0x180014a7c  retn
0x18001929c  push    rbp
0x18001929e  sub     rsp, 40h
0x1800192a2  mov     rbp, rdx
0x1800192a5  mov     eax, 1
0x1800192aa  add     rsp, 40h
0x1800192ae  pop     rbp
0x1800192af  retn
```

# PNP_Local_InstallDriver

- ea: `0x18000bc30`
- end: `0x18000be2a`
- name: `PNP_Local_InstallDriver`
- size: `506`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, __int64, __int64, __int64, int *, _DWORD *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800027a0`
- `0x18000bc30`
- `0x18000be30`
- `0x18000bf60`
- `0x18000f110`
- `0x18001091c`
- `0x1800117d4`
- `0x180013d90`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18000bdec`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000bdec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bdde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bdde`

## pseudocode

```c
RPC_STATUS __fastcall PNP_Local_InstallDriver(
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
  int Reply; // [rsp+40h] [rbp-68h] BYREF
  int v16; // [rsp+44h] [rbp-64h] BYREF
  HANDLE hObject[2]; // [rsp+48h] [rbp-60h] BYREF
  __int128 v18; // [rsp+58h] [rbp-50h]

  Reply = 0;
  hObject[0] = 0;
  v16 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
  if ( (PnpServiceInstallOptions & 0x20) != 0 )
  {
    if ( (unsigned int)IsClientLocal() )
    {
      if ( (unsigned int)UserDriverInstallAllowed() || (unsigned int)VerifyClientAccessToObject(2) )
      {
        if ( (unsigned int)GetClientUserToken(hObject) )
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
                *a6 = PnpInstallDriver(hObject[0], a3, a4, v18, v13, a7, &v16);
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
        Reply = 51;
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
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
  return result;
}

```

## disassembly

```asm
0x18000bc30  mov     [rsp+arg_0], rcx
0x18000bc35  push    rbx
0x18000bc36  push    rsi
0x18000bc37  push    rdi
0x18000bc38  push    r12
0x18000bc3a  push    r14
0x18000bc3c  push    r15
0x18000bc3e  sub     rsp, 78h
0x18000bc42  mov     r14, r9
0x18000bc45  mov     r15, r8
0x18000bc48  mov     rdi, rcx
0x18000bc4b  xor     r12d, r12d
0x18000bc4e  mov     [rsp+0A8h+Reply], r12d
0x18000bc53  mov     [rsp+0A8h+hObject], r12
0x18000bc58  mov     [rsp+0A8h+var_64], r12d
0x18000bc5d  lea     rsi, WPP_GLOBAL_Control
0x18000bc64  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc6b  cmp     rcx, rsi
0x18000bc6e  jz      short loc_18000BC8F
0x18000bc70  test    dword ptr [rcx+1Ch], 10000000h
0x18000bc77  jz      short loc_18000BC8F
0x18000bc79  mov     edx, 32h ; '2'
0x18000bc7e  lea     r8, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids
0x18000bc85  mov     rcx, [rcx+10h]
0x18000bc89  call    WPP_SF_
0x18000bc8e  nop
0x18000bc8f  test    byte ptr cs:PnpServiceInstallOptions, 20h
0x18000bc96  jnz     short loc_18000BCA5
0x18000bc98  mov     [rsp+0A8h+Reply], 32h ; '2'
0x18000bca0  jmp     loc_18000BDB7
0x18000bca5  call    IsClientLocal
0x18000bcaa  test    eax, eax
0x18000bcac  jnz     short loc_18000BCBB
0x18000bcae  mov     [rsp+0A8h+Reply], 33h ; '3'
0x18000bcb6  jmp     loc_18000BDB7
0x18000bcbb  call    UserDriverInstallAllowed
0x18000bcc0  test    eax, eax
0x18000bcc2  jnz     short loc_18000BCDF
0x18000bcc4  mov     ecx, 2
0x18000bcc9  call    VerifyClientAccessToObject
0x18000bcce  test    eax, eax
0x18000bcd0  jnz     short loc_18000BCDF
0x18000bcd2  mov     [rsp+0A8h+Reply], 33h ; '3'
0x18000bcda  jmp     loc_18000BDB7
0x18000bcdf  lea     rcx, [rsp+0A8h+hObject]
0x18000bce4  call    GetClientUserToken
0x18000bce9  test    eax, eax
0x18000bceb  jnz     short loc_18000BCFA
0x18000bced  mov     [rsp+0A8h+Reply], 33h ; '3'
0x18000bcf5  jmp     loc_18000BDB7
0x18000bcfa  mov     rcx, [rsp+0A8h+arg_20]
0x18000bd02  mov     eax, [rcx]
0x18000bd04  cmp     eax, 1
0x18000bd07  jbe     short loc_18000BD16
0x18000bd09  mov     [rsp+0A8h+Reply], 34h ; '4'
0x18000bd11  jmp     loc_18000BDB7
0x18000bd16  mov     rdx, [rcx+8]
0x18000bd1a  test    rdx, rdx
0x18000bd1d  jnz     short loc_18000BD2C
0x18000bd1f  mov     [rsp+0A8h+Reply], 1Fh
0x18000bd27  jmp     loc_18000BDB7
0x18000bd2c  xorps   xmm0, xmm0
0x18000bd2f  movups  [rsp+0A8h+var_50], xmm0
0x18000bd34  cmp     eax, 1
0x18000bd37  jz      short loc_18000BD44
0x18000bd39  mov     eax, 3Bh ; ';'
0x18000bd3e  mov     [rsp+0A8h+Reply], eax
0x18000bd42  jmp     short loc_18000BD50
0x18000bd44  movups  xmm0, xmmword ptr [rdx]
0x18000bd47  movups  [rsp+0A8h+var_50], xmm0
0x18000bd4c  mov     eax, [rsp+0A8h+Reply]
0x18000bd50  test    eax, eax
0x18000bd52  jnz     short loc_18000BDB7
0x18000bd54  lea     rcx, aWinsta0Default; "WinSta0\\Default"
0x18000bd5b  mov     rax, qword ptr [rsp+0A8h+var_50+8]
0x18000bd60  test    rax, rax
0x18000bd63  cmovnz  rcx, rax
0x18000bd67  mov     qword ptr [rsp+0A8h+var_50+8], rcx
0x18000bd6c  mov     rbx, [rsp+0A8h+arg_28]
0x18000bd74  mov     [rbx], r12d
0x18000bd77  lea     rax, [rsp+0A8h+var_64]
0x18000bd7c  mov     [rsp+0A8h+var_78], rax
0x18000bd81  mov     eax, [rsp+0A8h+arg_30]
0x18000bd88  mov     [rsp+0A8h+var_80], eax
0x18000bd8c  mov     [rsp+0A8h+var_88], rcx
0x18000bd91  mov     r9, qword ptr [rsp+0A8h+var_50]
0x18000bd96  mov     r8, r14
0x18000bd99  mov     rdx, r15
0x18000bd9c  mov     rcx, [rsp+0A8h+hObject]
0x18000bda1  call    PnpInstallDriver
0x18000bda6  mov     [rbx], eax
0x18000bda8  cmp     [rsp+0A8h+var_64], 0
0x18000bdad  jz      short loc_18000BDB7
0x18000bdaf  mov     [rsp+0A8h+Reply], 22h ; '"'
0x18000bdb7  jmp     short loc_18000BDD4
0x18000bdb9  mov     ecx, eax
0x18000bdbb  lea     r8, [rsp+0A8h+Reply]
0x18000bdc0  call    PnPExceptionHandler
0x18000bdc5  lea     rsi, WPP_GLOBAL_Control
0x18000bdcc  mov     rdi, [rsp+0A8h+arg_0]
0x18000bdd4  mov     rcx, [rsp+0A8h+hObject]; hObject
0x18000bdd9  test    rcx, rcx
0x18000bddc  jz      short loc_18000BDE4
0x18000bdde  call    cs:__imp_CloseHandle
0x18000bde4  lea     rdx, [rsp+0A8h+Reply]; Reply
0x18000bde9  mov     rcx, rdi; pAsync
0x18000bdec  call    cs:__imp_RpcAsyncCompleteCall
0x18000bdf2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdf9  cmp     rcx, rsi
0x18000bdfc  jz      short loc_18000BE1C
0x18000bdfe  test    dword ptr [rcx+1Ch], 10000000h
0x18000be05  jz      short loc_18000BE1C
0x18000be07  mov     edx, 33h ; '3'
0x18000be0c  lea     r8, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids
0x18000be13  mov     rcx, [rcx+10h]
0x18000be17  call    WPP_SF_
0x18000be1c  add     rsp, 78h
0x18000be20  pop     r15
0x18000be22  pop     r14
0x18000be24  pop     r12
0x18000be26  pop     rdi
0x18000be27  pop     rsi
0x18000be28  pop     rbx
0x18000be29  retn
0x180018df0  push    rbp
0x180018df2  sub     rsp, 40h
0x180018df6  mov     rbp, rdx
0x180018df9  mov     eax, 1
0x180018dfe  add     rsp, 40h
0x180018e02  pop     rbp
0x180018e03  retn
```

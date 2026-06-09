# WsDeleteSymbolicLink

- ea: `0x180009370`
- end: `0x1800094ec`
- name: `WsDeleteSymbolicLink`
- size: `380`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180001750`
- `0x18002bd5c`
- `0x18002cac8`
- `0x18002cbf4`

## callees

- `0x180008950`
- `0x180009370`
- `0x180031878`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800094c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800094c2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800093d3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800093d3`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800093c1`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800093c1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800093a6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800093a6`
- `RPCRT4!RpcImpersonateClient` at `0x18000945a`
- `RPCRT4!RpcImpersonateClient` at `0x18000945a`
- `RPCRT4!RpcRevertToSelf` at `0x1800093f7`
- `RPCRT4!RpcRevertToSelf` at `0x1800093f7`

## pseudocode

```c
void __fastcall WsDeleteSymbolicLink(__int64 a1, const WCHAR *a2, WCHAR *a3, void *a4)
{
  WCHAR *v5; // rbx
  char v7; // si
  RPC_STATUS v8; // eax
  int v9; // r8d
  RPC_STATUS v10; // eax
  int v11; // r8d

  v5 = a3;
  if ( !a1 && !a3 )
    return;
  v7 = 0;
  if ( !a3 )
  {
    v5 = (WCHAR *)WsReturnSessionPath();
    if ( !v5 )
      return;
    v7 = 1;
  }
  if ( a4 == (void *)-1LL )
  {
    v10 = RpcImpersonateClient(0);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v11, (unsigned int)"unknown", 0, v10);
      }
      goto LABEL_7;
    }
    goto LABEL_5;
  }
  if ( SetThreadToken(0, a4) )
  {
LABEL_5:
    DefineDosDeviceW(0xFu, v5, a2);
    if ( a4 == (void *)-1LL )
    {
      v8 = RpcRevertToSelf();
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v9, (unsigned int)"unknown", 0, v8);
        }
        __fastfail(7u);
      }
    }
    else
    {
      RevertToSelf();
    }
  }
LABEL_7:
  if ( v5 )
  {
    if ( v7 )
      LocalFree(v5);
  }
}

```

## disassembly

```asm
0x180009370  push    rbx
0x180009372  push    rbp
0x180009373  push    rsi
0x180009374  push    rdi
0x180009375  sub     rsp, 38h
0x180009379  mov     rdi, r9
0x18000937c  mov     rbx, r8
0x18000937f  mov     rbp, rdx
0x180009382  test    rcx, rcx
0x180009385  jz      loc_180009450
0x18000938b  xor     sil, sil
0x18000938e  test    rbx, rbx
0x180009391  jz      loc_1800094D3
0x180009397  xor     ecx, ecx; BindingHandle
0x180009399  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000939d  jz      loc_18000945A
0x1800093a3  mov     rdx, rdi; Token
0x1800093a6  call    cs:__imp_SetThreadToken
0x1800093ad  nop     dword ptr [rax+rax+00h]
0x1800093b2  test    eax, eax
0x1800093b4  jz      short loc_1800093DF
0x1800093b6  mov     r8, rbp; lpTargetPath
0x1800093b9  mov     rdx, rbx; lpDeviceName
0x1800093bc  mov     ecx, 0Fh; dwFlags
0x1800093c1  call    cs:__imp_DefineDosDeviceW
0x1800093c8  nop     dword ptr [rax+rax+00h]
0x1800093cd  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800093d1  jz      short loc_1800093F7
0x1800093d3  call    cs:__imp_RevertToSelf
0x1800093da  nop     dword ptr [rax+rax+00h]
0x1800093df  test    rbx, rbx
0x1800093e2  jz      short loc_1800093ED
0x1800093e4  test    sil, sil
0x1800093e7  jnz     loc_1800094BF
0x1800093ed  add     rsp, 38h
0x1800093f1  pop     rdi
0x1800093f2  pop     rsi
0x1800093f3  pop     rbp
0x1800093f4  pop     rbx
0x1800093f5  retn
0x1800093f7  call    cs:__imp_RpcRevertToSelf
0x1800093fe  nop     dword ptr [rax+rax+00h]
0x180009403  test    eax, eax
0x180009405  jz      short loc_1800093DF
0x180009407  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000940e  lea     rdx, WPP_GLOBAL_Control
0x180009415  cmp     rcx, rdx
0x180009418  jz      short loc_180009447
0x18000941a  test    byte ptr [rcx+1Ch], 4
0x18000941e  jz      short loc_180009447
0x180009420  cmp     byte ptr [rcx+19h], 1
0x180009424  jb      short loc_180009447
0x180009426  mov     rcx, [rcx+10h]
0x18000942a  lea     r9, aUnknown; "unknown"
0x180009431  mov     [rsp+58h+var_30], eax
0x180009435  mov     edx, 0Bh
0x18000943a  mov     [rsp+58h+var_38], 0
0x180009442  call    WPP_SF_sdL
0x180009447  mov     ecx, 7
0x18000944c  int     29h; Win8: RtlFailFast(ecx)
0x18000944e  jmp     short loc_1800093DF
0x180009450  test    rbx, rbx
0x180009453  jz      short loc_1800093ED
0x180009455  jmp     loc_18000938B
0x18000945a  call    cs:__imp_RpcImpersonateClient
0x180009461  nop     dword ptr [rax+rax+00h]
0x180009466  test    eax, eax
0x180009468  jz      loc_1800093B6
0x18000946e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180009475  lea     rdx, WPP_GLOBAL_Control
0x18000947c  cmp     rcx, rdx
0x18000947f  jz      loc_1800093DF
0x180009485  test    byte ptr [rcx+1Ch], 4
0x180009489  jz      loc_1800093DF
0x18000948f  cmp     byte ptr [rcx+19h], 1
0x180009493  jb      loc_1800093DF
0x180009499  mov     rcx, [rcx+10h]
0x18000949d  lea     r9, aUnknown; "unknown"
0x1800094a4  mov     [rsp+58h+var_30], eax
0x1800094a8  mov     edx, 0Ah
0x1800094ad  mov     [rsp+58h+var_38], 0
0x1800094b5  call    WPP_SF_sdL
0x1800094ba  jmp     loc_1800093DF
0x1800094bf  mov     rcx, rbx; hMem
0x1800094c2  call    cs:__imp_LocalFree
0x1800094c9  nop     dword ptr [rax+rax+00h]
0x1800094ce  jmp     loc_1800093ED
0x1800094d3  call    WsReturnSessionPath
0x1800094d8  mov     rbx, rax
0x1800094db  test    rax, rax
0x1800094de  jz      loc_1800093ED
0x1800094e4  mov     sil, 1
0x1800094e7  jmp     loc_180009397
```

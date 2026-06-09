# VerifyRpcAccess

- ea: `0x18006c6bc`
- end: `0x18006ca3f`
- name: `VerifyRpcAccess`
- size: `899`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE ClientBinding)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006c180`
- `0x18006c320`

## callees

- `0x18006c6bc`
- `0x180092008`
- `0x180092ee4`
- `0x18009aee0`
- `0x18009bb88`

## import_xrefs

- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18006c765`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18006c765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c9a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c9a7`
- `RPCRT4!RpcImpersonateClient` at `0x18006c6e5`
- `RPCRT4!RpcImpersonateClient` at `0x18006c6e5`
- `RPCRT4!RpcRevertToSelf` at `0x18006c780`
- `RPCRT4!RpcRevertToSelf` at `0x18006c780`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18006c72e`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18006c72e`

## pseudocode

```c
__int64 __fastcall VerifyRpcAccess(RPC_BINDING_HANDLE ClientBinding)
{
  unsigned int v2; // eax
  PSRWLOCK v3; // rbx
  unsigned int v4; // edi
  unsigned int v5; // eax
  __int64 *v6; // rdx
  PVOID *v8; // rcx
  __int64 v9; // rdx
  PVOID *v10; // rcx
  DWORD LastError; // eax
  _DWORD v12[4]; // [rsp+20h] [rbp-A8h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v14[52]; // [rsp+38h] [rbp-90h] BYREF
  int v15; // [rsp+6Ch] [rbp-5Ch]

  v2 = RpcImpersonateClient(0);
  if ( !v2 )
  {
    v3 = g_service;
    v4 = 5;
    if ( g_service )
    {
      memset_0(v14, 0, 0x70u);
      RpcCallAttributes[0] = 3;
      RpcCallAttributes[1] = 96;
      v5 = RpcServerInqCallAttributesW(ClientBinding, RpcCallAttributes);
      if ( v5 )
      {
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_8;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, v5);
          v8 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 8) == 0 || *((_BYTE *)v8 + 25) < 2u )
          goto LABEL_8;
        v9 = 22;
      }
      else
      {
        v6 = *(__int64 **)(qword_180111728 + 72);
        if ( v15 != 1 && LOBYTE(v3[28].Ptr) )
        {
          if ( LOBYTE(v3[28].Ptr) == 1 )
          {
            v6 = qword_1800EF288;
          }
          else
          {
            if ( LOBYTE(v3[28].Ptr) != 2 )
            {
              v8 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                goto LABEL_8;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  23,
                  WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids,
                  LOBYTE(v3[28].Ptr));
                v8 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 8) == 0 || *((_BYTE *)v8 + 25) < 2u )
                goto LABEL_8;
              v9 = 24;
              goto LABEL_59;
            }
            v6 = *(__int64 **)(qword_180111728 + 88);
          }
        }
        v12[0] = 0;
        if ( (unsigned int)CheckTokenMembershipEx(0, v6, 2, v12) )
        {
          if ( v12[0] )
          {
            v4 = 0;
LABEL_8:
            RpcRevertToSelf();
            return v4;
          }
          v8 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_8;
          }
          v9 = 27;
        }
        else
        {
          v8 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            goto LABEL_8;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            LastError = GetLastError();
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              25,
              WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids,
              LastError);
            v8 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 8) == 0 || *((_BYTE *)v8 + 25) < 2u )
            goto LABEL_8;
          v9 = 26;
        }
      }
    }
    else
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_8;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 8) == 0 || *((_BYTE *)v8 + 25) < 2u )
        goto LABEL_8;
      v9 = 20;
    }
LABEL_59:
    WPP_SF_d(v8[2], v9, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, 5);
    goto LABEL_8;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  v4 = 5;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, v2);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 && *((_BYTE *)v10 + 25) >= 2u )
      WPP_SF_d(v10[2], 18, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, 5);
  }
  return v4;
}

```

## disassembly

```asm
0x18006c6bc  mov     [rsp+arg_8], rbx
0x18006c6c1  mov     [rsp+arg_10], rsi
0x18006c6c6  push    rdi
0x18006c6c7  sub     rsp, 0C0h
0x18006c6ce  mov     rax, cs:__security_cookie
0x18006c6d5  xor     rax, rsp
0x18006c6d8  mov     [rsp+0C8h+var_18], rax
0x18006c6e0  mov     rsi, rcx
0x18006c6e3  xor     ecx, ecx; BindingHandle
0x18006c6e5  call    cs:__imp_RpcImpersonateClient
0x18006c6eb  test    eax, eax
0x18006c6ed  jnz     loc_18006C803
0x18006c6f3  mov     rbx, cs:?g_service@@3PEAVEventService@@EA; EventService * g_service
0x18006c6fa  lea     edi, [rax+5]
0x18006c6fd  test    rbx, rbx
0x18006c700  jz      loc_18006C7AD
0x18006c706  xor     edx, edx; Val
0x18006c708  lea     r8d, [rax+70h]; Size
0x18006c70c  lea     rcx, [rsp+0C8h+var_90]; void *
0x18006c711  call    memset_0
0x18006c716  lea     rdx, [rsp+0C8h+RpcCallAttributes]; RpcCallAttributes
0x18006c71b  mov     [rsp+0C8h+RpcCallAttributes], 3
0x18006c723  mov     rcx, rsi; ClientBinding
0x18006c726  mov     [rsp+0C8h+var_94], 60h ; '`'
0x18006c72e  call    cs:__imp_RpcServerInqCallAttributesW
0x18006c734  test    eax, eax
0x18006c736  jnz     loc_18006C882
0x18006c73c  cmp     [rsp+0C8h+var_5C], 1
0x18006c741  mov     r8, cs:qword_180111728
0x18006c748  mov     rdx, [r8+48h]
0x18006c74c  jnz     loc_18006C8EB
0x18006c752  xor     ecx, ecx
0x18006c754  mov     [rsp+0C8h+var_A8], 0
0x18006c75c  lea     r9, [rsp+0C8h+var_A8]
0x18006c761  lea     r8d, [rcx+2]
0x18006c765  call    cs:__imp_CheckTokenMembershipEx
0x18006c76b  test    eax, eax
0x18006c76d  jz      loc_18006C984
0x18006c773  cmp     [rsp+0C8h+var_A8], 0
0x18006c778  jz      loc_18006C9F7
0x18006c77e  xor     edi, edi
0x18006c780  call    cs:__imp_RpcRevertToSelf
0x18006c786  mov     eax, edi
0x18006c788  mov     rcx, [rsp+0C8h+var_18]
0x18006c790  xor     rcx, rsp; StackCookie
0x18006c793  call    __security_check_cookie
0x18006c798  lea     r11, [rsp+0C8h+var_8]
0x18006c7a0  mov     rbx, [r11+18h]
0x18006c7a4  mov     rsi, [r11+20h]
0x18006c7a8  mov     rsp, r11
0x18006c7ab  pop     rdi
0x18006c7ac  retn
0x18006c7ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c7b4  lea     rbx, WPP_GLOBAL_Control
0x18006c7bb  cmp     rcx, rbx
0x18006c7be  jz      short loc_18006C780
0x18006c7c0  test    byte ptr [rcx+1Ch], 8
0x18006c7c4  jz      short loc_18006C7E8
0x18006c7c6  cmp     byte ptr [rcx+19h], 1
0x18006c7ca  jb      short loc_18006C7E8
0x18006c7cc  mov     rcx, [rcx+10h]
0x18006c7d0  lea     r8, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x18006c7d7  mov     edx, 13h
0x18006c7dc  call    WPP_SF_
0x18006c7e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c7e8  cmp     rcx, rbx
0x18006c7eb  jz      short loc_18006C780
0x18006c7ed  test    byte ptr [rcx+1Ch], 8
0x18006c7f1  jz      short loc_18006C780
0x18006c7f3  cmp     byte ptr [rcx+19h], 2
0x18006c7f7  jb      short loc_18006C780
0x18006c7f9  mov     edx, 14h
0x18006c7fe  jmp     loc_18006CA27
0x18006c803  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c80a  lea     rbx, WPP_GLOBAL_Control
0x18006c811  mov     edi, 5
0x18006c816  cmp     rcx, rbx
0x18006c819  jz      loc_18006C786
0x18006c81f  test    byte ptr [rcx+1Ch], 8
0x18006c823  jz      short loc_18006C848
0x18006c825  cmp     byte ptr [rcx+19h], 2
0x18006c829  jb      short loc_18006C848
0x18006c82b  mov     rcx, [rcx+10h]
0x18006c82f  lea     edx, [rdi+0Ch]
0x18006c832  mov     r9d, eax
0x18006c835  lea     r8, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x18006c83c  call    WPP_SF_d
0x18006c841  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c848  cmp     rcx, rbx
0x18006c84b  jz      loc_18006C786
0x18006c851  test    byte ptr [rcx+1Ch], 8
0x18006c855  jz      loc_18006C786
0x18006c85b  cmp     byte ptr [rcx+19h], 2
0x18006c85f  jb      loc_18006C786
0x18006c865  mov     rcx, [rcx+10h]
0x18006c869  lea     r8, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x18006c870  mov     edx, 12h
0x18006c875  mov     r9d, edi
0x18006c878  call    WPP_SF_d
0x18006c87d  jmp     loc_18006C786
0x18006c882  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c889  lea     rbx, WPP_GLOBAL_Control
0x18006c890  cmp     rcx, rbx
0x18006c893  jz      loc_18006C780
0x18006c899  test    byte ptr [rcx+1Ch], 8
0x18006c89d  jz      short loc_18006C8C4
0x18006c89f  cmp     byte ptr [rcx+19h], 2
0x18006c8a3  jb      short loc_18006C8C4
0x18006c8a5  mov     rcx, [rcx+10h]
0x18006c8a9  lea     r8, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x18006c8b0  mov     edx, 15h
0x18006c8b5  mov     r9d, eax
0x18006c8b8  call    WPP_SF_d
0x18006c8bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c8c4  cmp     rcx, rbx
0x18006c8c7  jz      loc_18006C780
0x18006c8cd  test    byte ptr [rcx+1Ch], 8
0x18006c8d1  jz      loc_18006C780
0x18006c8d7  cmp     byte ptr [rcx+19h], 2
0x18006c8db  jb      loc_18006C780
0x18006c8e1  mov     edx, 16h
0x18006c8e6  jmp     loc_18006CA27
0x18006c8eb  movzx   r9d, byte ptr [rbx+0E0h]
0x18006c8f3  mov     ecx, r9d
0x18006c8f6  test    r9d, r9d
0x18006c8f9  jz      loc_18006C752
0x18006c8ff  sub     ecx, 1
0x18006c902  jz      short loc_18006C978
0x18006c904  cmp     ecx, 1
0x18006c907  jz      short loc_18006C96F
0x18006c909  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c910  lea     rbx, WPP_GLOBAL_Control
0x18006c917  cmp     rcx, rbx
0x18006c91a  jz      loc_18006C780
0x18006c920  test    byte ptr [rcx+1Ch], 8
0x18006c924  jz      short loc_18006C948
0x18006c926  cmp     byte ptr [rcx+19h], 1
0x18006c92a  jb      short loc_18006C948
0x18006c92c  mov     rcx, [rcx+10h]
0x18006c930  lea     r8, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x18006c937  mov     edx, 17h
0x18006c93c  call    WPP_SF_d
0x18006c941  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c948  cmp     rcx, rbx
0x18006c94b  jz      loc_18006C780
0x18006c951  test    byte ptr [rcx+1Ch], 8
0x18006c955  jz      loc_18006C780
0x18006c95b  cmp     byte ptr [rcx+19h], 2
0x18006c95f  jb      loc_18006C780
0x18006c965  mov     edx, 18h
0x18006c96a  jmp     loc_18006CA27
0x18006c96f  mov     rdx, [r8+58h]
0x18006c973  jmp     loc_18006C752
0x18006c978  lea     rdx, qword_1800EF288
0x18006c97f  jmp     loc_18006C752
0x18006c984  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c98b  lea     rbx, WPP_GLOBAL_Control
0x18006c992  cmp     rcx, rbx
0x18006c995  jz      loc_18006C780
0x18006c99b  test    byte ptr [rcx+1Ch], 8
0x18006c99f  jz      short loc_18006C9D3
0x18006c9a1  cmp     byte ptr [rcx+19h], 2
0x18006c9a5  jb      short loc_18006C9D3
0x18006c9a7  call    cs:__imp_GetLastError
0x18006c9ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c9b4  lea     r8, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x18006c9bb  mov     edx, 19h
0x18006c9c0  mov     r9d, eax
0x18006c9c3  mov     rcx, [rcx+10h]
0x18006c9c7  call    WPP_SF_d
0x18006c9cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c9d3  cmp     rcx, rbx
0x18006c9d6  jz      loc_18006C780
0x18006c9dc  test    byte ptr [rcx+1Ch], 8
0x18006c9e0  jz      loc_18006C780
0x18006c9e6  cmp     byte ptr [rcx+19h], 2
0x18006c9ea  jb      loc_18006C780
0x18006c9f0  mov     edx, 1Ah
0x18006c9f5  jmp     short loc_18006CA27
0x18006c9f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c9fe  lea     rbx, WPP_GLOBAL_Control
0x18006ca05  cmp     rcx, rbx
0x18006ca08  jz      loc_18006C780
0x18006ca0e  test    byte ptr [rcx+1Ch], 8
0x18006ca12  jz      loc_18006C780
0x18006ca18  cmp     byte ptr [rcx+19h], 2
0x18006ca1c  jb      loc_18006C780
0x18006ca22  mov     edx, 1Bh
0x18006ca27  mov     rcx, [rcx+10h]
0x18006ca2b  lea     r8, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x18006ca32  mov     r9d, edi
0x18006ca35  call    WPP_SF_d
0x18006ca3a  jmp     loc_18006C780
```

# RpcStartOnDemandRequestCompletion

- ea: `0x1800ab850`
- end: `0x1800aba2a`
- name: `RpcStartOnDemandRequestCompletion`
- size: `474`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180064120`
- `0x1800aba30`

## callees

- `0x180011bb0`
- `0x180011c20`
- `0x1800137a0`
- `0x180084f50`
- `0x1800ab850`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x1800ab980`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800ab980`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1800ab9cd`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1800ab9cd`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x1800ab8fc`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x1800ab8fc`

## string_xrefs

- `0x1800ab8ac`: `RpcStartOnDemandRequestCompletion`
- `0x1800ab9ef`: `RpcStartOnDemandRequestCompletion`

## pseudocode

```c
void __fastcall RpcStartOnDemandRequestCompletion(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v4; // rcx
  char v5; // bl
  unsigned int v6; // eax
  unsigned int v7; // eax
  char v8; // di
  PRPC_ASYNC_STATE *v9; // [rsp+30h] [rbp-38h] BYREF
  unsigned int Reply; // [rsp+38h] [rbp-30h] BYREF

  Reply = a3;
  v9 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      165,
      WPP_59cb1c30c417333f98d499625c161da5_Traceguids,
      "RpcStartOnDemandRequestCompletion");
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    v5 = 6;
    goto LABEL_24;
  }
  v6 = HtReferenceHandleWithTag(g_hHandleTable, a2, 1229870150, 1448036676, 0, &v9);
  v5 = v6;
  if ( !v6 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 167, WPP_59cb1c30c417333f98d499625c161da5_Traceguids, Reply);
    }
    v7 = RpcAsyncCompleteCall(*v9, &Reply);
    v8 = v7;
    if ( v7 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 168, WPP_59cb1c30c417333f98d499625c161da5_Traceguids, v7);
      }
      v5 = v8;
    }
    HtDereferenceHandleWithTag(g_hHandleTable, a2, 0, 1);
    goto LABEL_23;
  }
  v4 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return;
  if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 166, WPP_59cb1c30c417333f98d499625c161da5_Traceguids, v6);
LABEL_23:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_24:
  if ( (_UNKNOWN *)v4 != &WPP_GLOBAL_Control && *(_BYTE *)(v4 + 25) >= 5u && (*(_BYTE *)(v4 + 28) & 1) != 0 )
    WPP_SF_sL(
      *(_QWORD *)(v4 + 16),
      169,
      (unsigned int)WPP_59cb1c30c417333f98d499625c161da5_Traceguids,
      (unsigned int)"RpcStartOnDemandRequestCompletion",
      v5);
}

```

## disassembly

```asm
0x1800ab850  mov     r11, rsp
0x1800ab853  mov     [r11+8], rbx
0x1800ab857  mov     [r11+20h], rsi
0x1800ab85b  push    rdi
0x1800ab85c  push    r14
0x1800ab85e  push    r15
0x1800ab860  sub     rsp, 50h
0x1800ab864  mov     rax, cs:__security_cookie
0x1800ab86b  xor     rax, rsp
0x1800ab86e  mov     [rsp+68h+var_28], rax
0x1800ab873  mov     [r11-30h], r8d
0x1800ab877  mov     rsi, rdx
0x1800ab87a  mov     qword ptr [r11-38h], 0
0x1800ab882  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab889  lea     r14, WPP_GLOBAL_Control
0x1800ab890  lea     r15, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800ab897  cmp     rcx, r14
0x1800ab89a  jz      short loc_1800AB8C7
0x1800ab89c  cmp     byte ptr [rcx+19h], 5
0x1800ab8a0  jb      short loc_1800AB8C7
0x1800ab8a2  test    byte ptr [rcx+1Ch], 1
0x1800ab8a6  jz      short loc_1800AB8C7
0x1800ab8a8  mov     rcx, [rcx+10h]
0x1800ab8ac  lea     r9, aRpcstartondema; "RpcStartOnDemandRequestCompletion"
0x1800ab8b3  mov     edx, 0A5h
0x1800ab8b8  mov     r8, r15
0x1800ab8bb  call    WPP_SF_s
0x1800ab8c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab8c7  test    rsi, rsi
0x1800ab8ca  jnz     short loc_1800AB8D4
0x1800ab8cc  lea     ebx, [rsi+6]
0x1800ab8cf  jmp     loc_1800AB9DA
0x1800ab8d4  mov     rcx, cs:g_hHandleTable
0x1800ab8db  lea     rax, [rsp+68h+var_38]
0x1800ab8e0  mov     [rsp+68h+var_40], rax
0x1800ab8e5  mov     r9d, 564F4944h
0x1800ab8eb  mov     r8d, 494E5446h
0x1800ab8f1  mov     [rsp+68h+var_48], 0
0x1800ab8f9  mov     rdx, rsi
0x1800ab8fc  call    cs:__imp_HtReferenceHandleWithTag
0x1800ab902  mov     ebx, eax
0x1800ab904  test    eax, eax
0x1800ab906  jz      short loc_1800AB945
0x1800ab908  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab90f  cmp     rcx, r14
0x1800ab912  jz      loc_1800ABA07
0x1800ab918  cmp     byte ptr [rcx+19h], 1
0x1800ab91c  jb      loc_1800AB9DA
0x1800ab922  test    byte ptr [rcx+1Ch], 1
0x1800ab926  jz      loc_1800AB9DA
0x1800ab92c  mov     rcx, [rcx+10h]
0x1800ab930  mov     edx, 0A6h
0x1800ab935  mov     r9d, eax
0x1800ab938  mov     r8, r15
0x1800ab93b  call    WPP_SF_d
0x1800ab940  jmp     loc_1800AB9D3
0x1800ab945  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab94c  cmp     rcx, r14
0x1800ab94f  jz      short loc_1800AB973
0x1800ab951  cmp     byte ptr [rcx+19h], 4
0x1800ab955  jb      short loc_1800AB973
0x1800ab957  test    byte ptr [rcx+1Ch], 1
0x1800ab95b  jz      short loc_1800AB973
0x1800ab95d  mov     r9d, [rsp+68h+Reply]
0x1800ab962  mov     edx, 0A7h
0x1800ab967  mov     rcx, [rcx+10h]
0x1800ab96b  mov     r8, r15
0x1800ab96e  call    WPP_SF_d
0x1800ab973  mov     rcx, [rsp+68h+var_38]
0x1800ab978  lea     rdx, [rsp+68h+Reply]; Reply
0x1800ab97d  mov     rcx, [rcx]; pAsync
0x1800ab980  call    cs:__imp_RpcAsyncCompleteCall
0x1800ab986  mov     edi, eax
0x1800ab988  test    eax, eax
0x1800ab98a  jz      short loc_1800AB9BA
0x1800ab98c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab993  cmp     rcx, r14
0x1800ab996  jz      short loc_1800AB9B8
0x1800ab998  cmp     byte ptr [rcx+19h], 1
0x1800ab99c  jb      short loc_1800AB9B8
0x1800ab99e  test    byte ptr [rcx+1Ch], 1
0x1800ab9a2  jz      short loc_1800AB9B8
0x1800ab9a4  mov     rcx, [rcx+10h]
0x1800ab9a8  mov     edx, 0A8h
0x1800ab9ad  mov     r9d, eax
0x1800ab9b0  mov     r8, r15
0x1800ab9b3  call    WPP_SF_d
0x1800ab9b8  mov     ebx, edi
0x1800ab9ba  mov     rcx, cs:g_hHandleTable
0x1800ab9c1  mov     r9d, 1
0x1800ab9c7  xor     r8d, r8d
0x1800ab9ca  mov     rdx, rsi
0x1800ab9cd  call    cs:__imp_HtDereferenceHandleWithTag
0x1800ab9d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab9da  cmp     rcx, r14
0x1800ab9dd  jz      short loc_1800ABA07
0x1800ab9df  cmp     byte ptr [rcx+19h], 5
0x1800ab9e3  jb      short loc_1800ABA07
0x1800ab9e5  test    byte ptr [rcx+1Ch], 1
0x1800ab9e9  jz      short loc_1800ABA07
0x1800ab9eb  mov     rcx, [rcx+10h]
0x1800ab9ef  lea     r9, aRpcstartondema; "RpcStartOnDemandRequestCompletion"
0x1800ab9f6  mov     edx, 0A9h
0x1800ab9fb  mov     [rsp+68h+var_48], ebx
0x1800ab9ff  mov     r8, r15
0x1800aba02  call    WPP_SF_sL
0x1800aba07  mov     rcx, [rsp+68h+var_28]
0x1800aba0c  xor     rcx, rsp; StackCookie
0x1800aba0f  call    __security_check_cookie
0x1800aba14  lea     r11, [rsp+68h+var_18]
0x1800aba19  mov     rbx, [r11+20h]
0x1800aba1d  mov     rsi, [r11+38h]
0x1800aba21  mov     rsp, r11
0x1800aba24  pop     r15
0x1800aba26  pop     r14
0x1800aba28  pop     rdi
0x1800aba29  retn
```

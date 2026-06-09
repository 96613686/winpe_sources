# LocalFtmAsyncCompletionCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180023f40`
- end: `0x180024139`
- name: `?LocalFtmAsyncCompletionCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `505`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800063a0`
- `0x180006934`
- `0x180023f40`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180024046`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180024046`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180023fcc`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180023fcc`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18002403d`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18002403d`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180023fba`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180023fba`

## pseudocode

```c
void __fastcall LocalFtmAsyncCompletionCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  _QWORD v9[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int Reply; // [rsp+78h] [rbp+30h] BYREF

  Reply = 0;
  v9[0] = 0;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 154, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids);
  }
  HtReferenceHandleWithTag(g_hHandleTable, Context, 0, 1448036676, 0, v9);
  v6 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)(v9[0] + 16LL), &Reply);
  v7 = v6;
  switch ( v6 )
  {
    case 0x77Au:
    case 0x3E5u:
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 156, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids, v6);
      }
      break;
    case 0x71Au:
      v8 = Reply;
      if ( !Reply )
      {
        v8 = 1223;
        Reply = 1223;
      }
      goto LABEL_10;
    case 0u:
      v8 = Reply;
      goto LABEL_29;
    default:
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 157, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids, v6);
      }
      break;
  }
  v8 = v7;
  Reply = v7;
LABEL_29:
  if ( (_DWORD)v8 )
  {
LABEL_10:
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(v9[0] + 136LL))(*(_QWORD *)(v9[0] + 144LL), v8, 0, 0);
    goto LABEL_11;
  }
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(v9[0] + 136LL))(
    *(_QWORD *)(v9[0] + 144LL),
    0,
    *(_DWORD *)(v9[0] + 152LL) / 0x68u,
    *(_QWORD *)(v9[0] + 160LL));
LABEL_11:
  if ( v9[0] )
    HtDereferenceHandleWithTag(g_hHandleTable, *(_QWORD *)v9[0], 0, 1);
  CloseThreadpoolWait(Wait);
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 158, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids, v7);
  }
}

```

## disassembly

```asm
0x180023f40  push    rbp
0x180023f42  push    rbx
0x180023f43  push    rdi
0x180023f44  push    r15
0x180023f46  mov     rbp, rsp
0x180023f49  sub     rsp, 48h
0x180023f4d  mov     rdi, r8
0x180023f50  mov     [rbp+Reply], 0
0x180023f57  mov     rbx, rdx
0x180023f5a  mov     [rbp+var_18], 0
0x180023f62  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f69  lea     r15, WPP_GLOBAL_Control
0x180023f70  cmp     rcx, r15
0x180023f73  jz      short loc_180023F96
0x180023f75  cmp     byte ptr [rcx+69h], 4
0x180023f79  jb      short loc_180023F96
0x180023f7b  test    byte ptr [rcx+6Ch], 2
0x180023f7f  jz      short loc_180023F96
0x180023f81  mov     rcx, [rcx+60h]
0x180023f85  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x180023f8c  mov     edx, 9Ah
0x180023f91  call    WPP_SF_
0x180023f96  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180023f9d  lea     rax, [rbp+var_18]
0x180023fa1  mov     [rsp+48h+var_20], rax
0x180023fa6  mov     r9d, 564F4944h
0x180023fac  xor     r8d, r8d
0x180023faf  mov     [rsp+48h+var_28], 0
0x180023fb7  mov     rdx, rbx
0x180023fba  call    cs:__imp_HtReferenceHandleWithTag
0x180023fc0  mov     rcx, [rbp+var_18]
0x180023fc4  lea     rdx, [rbp+Reply]; Reply
0x180023fc8  add     rcx, 10h; pAsync
0x180023fcc  call    cs:__imp_RpcAsyncCompleteCall
0x180023fd2  mov     ebx, eax
0x180023fd4  cmp     eax, 77Ah
0x180023fd9  jz      loc_1800240C1
0x180023fdf  cmp     eax, 3E5h
0x180023fe4  jz      loc_1800240C1
0x180023fea  cmp     eax, 71Ah
0x180023fef  jnz     loc_180024086
0x180023ff5  mov     edx, [rbp+Reply]
0x180023ff8  test    edx, edx
0x180023ffa  jnz     short loc_180024004
0x180023ffc  mov     edx, 4C7h
0x180024001  mov     [rbp+Reply], edx
0x180024004  mov     rcx, [rbp+var_18]
0x180024008  xor     r9d, r9d
0x18002400b  xor     r8d, r8d
0x18002400e  mov     rax, [rcx+88h]
0x180024015  mov     rcx, [rcx+90h]
0x18002401c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024021  mov     rdx, [rbp+var_18]
0x180024025  test    rdx, rdx
0x180024028  jz      short loc_180024043
0x18002402a  mov     rdx, [rdx]
0x18002402d  mov     r9d, 1
0x180024033  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18002403a  xor     r8d, r8d
0x18002403d  call    cs:__imp_HtDereferenceHandleWithTag
0x180024043  mov     rcx, rdi; pwa
0x180024046  call    cs:__imp_CloseThreadpoolWait
0x18002404c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024053  cmp     rcx, r15
0x180024056  jz      short loc_18002407C
0x180024058  cmp     byte ptr [rcx+69h], 4
0x18002405c  jb      short loc_18002407C
0x18002405e  test    byte ptr [rcx+6Ch], 2
0x180024062  jz      short loc_18002407C
0x180024064  mov     rcx, [rcx+60h]
0x180024068  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x18002406f  mov     edx, 9Eh
0x180024074  mov     r9d, ebx
0x180024077  call    WPP_SF_d
0x18002407c  add     rsp, 48h
0x180024080  pop     r15
0x180024082  pop     rdi
0x180024083  pop     rbx
0x180024084  pop     rbp
0x180024085  retn
0x180024086  test    ebx, ebx
0x180024088  jz      short loc_1800240BC
0x18002408a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024091  cmp     rcx, r15
0x180024094  jz      short loc_1800240F1
0x180024096  cmp     byte ptr [rcx+69h], 1
0x18002409a  jb      short loc_1800240F1
0x18002409c  test    byte ptr [rcx+6Ch], 2
0x1800240a0  jz      short loc_1800240F1
0x1800240a2  mov     rcx, [rcx+60h]
0x1800240a6  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x1800240ad  mov     edx, 9Dh
0x1800240b2  mov     r9d, ebx
0x1800240b5  call    WPP_SF_d
0x1800240ba  jmp     short loc_1800240F1
0x1800240bc  mov     edx, [rbp+Reply]
0x1800240bf  jmp     short loc_1800240F6
0x1800240c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800240c8  cmp     rcx, r15
0x1800240cb  jz      short loc_1800240F1
0x1800240cd  cmp     byte ptr [rcx+69h], 1
0x1800240d1  jb      short loc_1800240F1
0x1800240d3  test    byte ptr [rcx+6Ch], 2
0x1800240d7  jz      short loc_1800240F1
0x1800240d9  mov     rcx, [rcx+60h]
0x1800240dd  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x1800240e4  mov     edx, 9Ch
0x1800240e9  mov     r9d, ebx
0x1800240ec  call    WPP_SF_d
0x1800240f1  mov     edx, ebx
0x1800240f3  mov     [rbp+Reply], ebx
0x1800240f6  test    edx, edx
0x1800240f8  jnz     loc_180024004
0x1800240fe  mov     r10, [rbp+var_18]
0x180024102  mov     rax, 4EC4EC4EC4EC4EC5h
0x18002410c  mov     edx, [r10+98h]
0x180024113  mov     r9, [r10+0A0h]
0x18002411a  mov     rcx, [r10+90h]
0x180024121  mul     rdx
0x180024124  mov     rax, [r10+88h]
0x18002412b  shr     rdx, 5
0x18002412f  mov     r8d, edx
0x180024132  xor     edx, edx
0x180024134  jmp     loc_18002401C
```

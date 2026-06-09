# wfdAsyncCompletionCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18005a4b0`
- end: `0x18005a7c3`
- name: `?wfdAsyncCompletionCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `787`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800063a0`
- `0x180006934`
- `0x18004fe34`
- `0x18004ffb8`
- `0x180050040`
- `0x180050148`
- `0x18005a4b0`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005a774`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005a774`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18005a5f2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18005a5f2`

## pseudocode

```c
void __fastcall wfdAsyncCompletionCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  int v4; // esi
  int v5; // edi
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  union DOT11_OUI_HEADER *v12; // rcx
  unsigned int v13; // r8d
  struct _WFD_API_ASYNC_CONTEXT *v14; // r10
  __int64 v15; // rcx
  void (__fastcall *v16)(__int64, __int64, __int128 *, char *, unsigned int, int); // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  void (__fastcall *v19)(__int64, __int64, __int128 *, _QWORD, int); // rax
  __int64 v20; // rcx
  int v21; // [rsp+20h] [rbp-40h]
  int v22; // [rsp+28h] [rbp-38h]
  struct _WFD_API_ASYNC_CONTEXT *v23[2]; // [rsp+40h] [rbp-20h] BYREF
  __int128 v24; // [rsp+50h] [rbp-10h] BYREF
  int Reply; // [rsp+98h] [rbp+38h] BYREF

  v4 = 0;
  Reply = 0;
  v5 = 0;
  v23[0] = 0;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 51, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
  }
  v8 = LocalWfdAsyncContextRefPending(Context, v23, 0);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 52, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v8);
    }
    v9 = LocalWfdAsyncContextRefCancelled(Context, v23);
    v10 = v9;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 53, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v9);
      }
      goto LABEL_45;
    }
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 54, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
    }
    v5 = 1;
  }
  v11 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)((char *)v23[0] + 32), &Reply);
  v10 = v11;
  if ( v11 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 55, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v11);
      v12 = WPP_GLOBAL_Control;
    }
    v13 = v10;
    Reply = v10;
  }
  else
  {
    v13 = Reply;
    v12 = WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    v13 = 1223;
    Reply = 1223;
  }
  if ( !v13 )
  {
    LocalWfdAsyncContextPendingMarkIdle(v23[0]);
    goto LABEL_35;
  }
  v4 = 1;
  if ( v12 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v12 + 105) >= 3u
    && (*((_DWORD *)v12 + 27) & 0x1000) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v12 + 12), 56, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v13);
LABEL_35:
    v12 = WPP_GLOBAL_Control;
    v13 = Reply;
  }
  v14 = v23[0];
  if ( *(_DWORD *)v23[0] == 1 )
  {
    v18 = *((_QWORD *)v23[0] + 3);
    v19 = (void (__fastcall *)(__int64, __int64, __int128 *, _QWORD, int))*((_QWORD *)v23[0] + 21);
    v21 = *((_DWORD *)v23[0] + 48);
    v20 = *((_QWORD *)v23[0] + 2);
    v24 = *((_OWORD *)v23[0] + 11);
    v19(v20, v18, &v24, v13, v21);
    goto LABEL_45;
  }
  if ( *(_DWORD *)v23[0] == 2 )
  {
    v15 = *((_QWORD *)v23[0] + 2);
    v16 = (void (__fastcall *)(__int64, __int64, __int128 *, char *, unsigned int, int))*((_QWORD *)v23[0] + 21);
    v22 = *((_DWORD *)v23[0] + 50);
    v17 = *((_QWORD *)v23[0] + 3);
    v24 = *((_OWORD *)v23[0] + 11);
    v16(v15, v17, &v24, (char *)v23[0] + 192, v13, v22);
LABEL_45:
    v14 = v23[0];
    goto LABEL_46;
  }
  if ( v12 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v12 + 105)
    && (*((_DWORD *)v12 + 27) & 0x1000) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v12 + 12), 57, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, *(unsigned int *)v23[0]);
    v14 = v23[0];
  }
  v10 = 87;
LABEL_46:
  if ( v14 )
  {
    LocalWfdAsyncContextDeref(v14);
    if ( v4 )
      LocalWfdAsyncContextDeref(v23[0]);
  }
  CloseThreadpoolWait(Wait);
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 58, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v10);
  }
}

```

## disassembly

```asm
0x18005a4b0  mov     [rsp-28h+arg_0], rbx
0x18005a4b5  mov     [rsp-28h+arg_10], rsi
0x18005a4ba  push    rbp
0x18005a4bb  push    rdi
0x18005a4bc  push    r12
0x18005a4be  push    r13
0x18005a4c0  push    r14
0x18005a4c2  mov     rbp, rsp
0x18005a4c5  sub     rsp, 60h
0x18005a4c9  xor     esi, esi
0x18005a4cb  mov     [rbp+Reply], 0
0x18005a4d2  xor     edi, edi
0x18005a4d4  mov     [rbp+var_20], 0
0x18005a4dc  mov     r14, r8
0x18005a4df  mov     rbx, rdx
0x18005a4e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a4e9  lea     r12, WPP_GLOBAL_Control
0x18005a4f0  cmp     rcx, r12
0x18005a4f3  jz      short loc_18005A514
0x18005a4f5  cmp     byte ptr [rcx+69h], 4
0x18005a4f9  jb      short loc_18005A514
0x18005a4fb  test    byte ptr [rcx+6Ch], 2
0x18005a4ff  jz      short loc_18005A514
0x18005a501  mov     rcx, [rcx+60h]
0x18005a505  lea     edx, [rsi+33h]
0x18005a508  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18005a50f  call    WPP_SF_
0x18005a514  xor     r8d, r8d; int
0x18005a517  lea     rdx, [rbp+var_20]; struct _WFD_API_ASYNC_CONTEXT **
0x18005a51b  mov     rcx, rbx; void *
0x18005a51e  call    ?LocalWfdAsyncContextRefPending@@YAKPEAXPEAPEAU_WFD_API_ASYNC_CONTEXT@@H@Z; LocalWfdAsyncContextRefPending(void *,_WFD_API_ASYNC_CONTEXT * *,int)
0x18005a523  mov     r13d, 1000h
0x18005a529  test    eax, eax
0x18005a52b  jz      loc_18005A5E6
0x18005a531  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a538  cmp     rcx, r12
0x18005a53b  jz      short loc_18005A561
0x18005a53d  cmp     byte ptr [rcx+69h], 1
0x18005a541  jb      short loc_18005A561
0x18005a543  test    [rcx+6Ch], r13d
0x18005a547  jz      short loc_18005A561
0x18005a549  mov     rcx, [rcx+60h]
0x18005a54d  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18005a554  mov     edx, 34h ; '4'
0x18005a559  mov     r9d, eax
0x18005a55c  call    WPP_SF_d
0x18005a561  lea     rdx, [rbp+var_20]; struct _WFD_API_ASYNC_CONTEXT **
0x18005a565  mov     rcx, rbx; void *
0x18005a568  call    ?LocalWfdAsyncContextRefCancelled@@YAKPEAXPEAPEAU_WFD_API_ASYNC_CONTEXT@@@Z; LocalWfdAsyncContextRefCancelled(void *,_WFD_API_ASYNC_CONTEXT * *)
0x18005a56d  mov     ebx, eax
0x18005a56f  test    eax, eax
0x18005a571  jz      short loc_18005A5B4
0x18005a573  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a57a  cmp     rcx, r12
0x18005a57d  jz      loc_18005A753
0x18005a583  cmp     byte ptr [rcx+69h], 1
0x18005a587  jb      loc_18005A753
0x18005a58d  test    [rcx+6Ch], r13d
0x18005a591  jz      loc_18005A753
0x18005a597  mov     rcx, [rcx+60h]
0x18005a59b  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18005a5a2  mov     edx, 35h ; '5'
0x18005a5a7  mov     r9d, eax
0x18005a5aa  call    WPP_SF_d
0x18005a5af  jmp     loc_18005A753
0x18005a5b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a5bb  cmp     rcx, r12
0x18005a5be  jz      short loc_18005A5E1
0x18005a5c0  cmp     byte ptr [rcx+69h], 3
0x18005a5c4  jb      short loc_18005A5E1
0x18005a5c6  test    [rcx+6Ch], r13d
0x18005a5ca  jz      short loc_18005A5E1
0x18005a5cc  mov     rcx, [rcx+60h]
0x18005a5d0  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18005a5d7  mov     edx, 36h ; '6'
0x18005a5dc  call    WPP_SF_
0x18005a5e1  mov     edi, 1
0x18005a5e6  mov     rcx, [rbp+var_20]
0x18005a5ea  lea     rdx, [rbp+Reply]; Reply
0x18005a5ee  add     rcx, 20h ; ' '; pAsync
0x18005a5f2  call    cs:__imp_RpcAsyncCompleteCall
0x18005a5f8  mov     ebx, eax
0x18005a5fa  test    eax, eax
0x18005a5fc  jz      short loc_18005A63D
0x18005a5fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a605  cmp     rcx, r12
0x18005a608  jz      short loc_18005A635
0x18005a60a  cmp     byte ptr [rcx+69h], 1
0x18005a60e  jb      short loc_18005A635
0x18005a610  test    [rcx+6Ch], r13d
0x18005a614  jz      short loc_18005A635
0x18005a616  mov     rcx, [rcx+60h]
0x18005a61a  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18005a621  mov     edx, 37h ; '7'
0x18005a626  mov     r9d, eax
0x18005a629  call    WPP_SF_d
0x18005a62e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a635  mov     r8d, ebx
0x18005a638  mov     [rbp+Reply], ebx
0x18005a63b  jmp     short loc_18005A648
0x18005a63d  mov     r8d, [rbp+Reply]
0x18005a641  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a648  test    edi, edi
0x18005a64a  jz      short loc_18005A656
0x18005a64c  mov     r8d, 4C7h
0x18005a652  mov     [rbp+Reply], r8d
0x18005a656  test    r8d, r8d
0x18005a659  jz      short loc_18005A689
0x18005a65b  mov     esi, 1
0x18005a660  cmp     rcx, r12
0x18005a663  jz      short loc_18005A69D
0x18005a665  cmp     byte ptr [rcx+69h], 3
0x18005a669  jb      short loc_18005A69D
0x18005a66b  test    [rcx+6Ch], r13d
0x18005a66f  jz      short loc_18005A69D
0x18005a671  mov     rcx, [rcx+60h]
0x18005a675  lea     edx, [rsi+37h]
0x18005a678  mov     r9d, r8d
0x18005a67b  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18005a682  call    WPP_SF_d
0x18005a687  jmp     short loc_18005A692
0x18005a689  mov     rcx, [rbp+var_20]; struct _WFD_API_ASYNC_CONTEXT *
0x18005a68d  call    ?LocalWfdAsyncContextPendingMarkIdle@@YAKPEAU_WFD_API_ASYNC_CONTEXT@@@Z; LocalWfdAsyncContextPendingMarkIdle(_WFD_API_ASYNC_CONTEXT *)
0x18005a692  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a699  mov     r8d, [rbp+Reply]
0x18005a69d  mov     r10, [rbp+var_20]
0x18005a6a1  mov     r9d, [r10]
0x18005a6a4  mov     edx, r9d
0x18005a6a7  sub     edx, 1
0x18005a6aa  jz      short loc_18005A720
0x18005a6ac  cmp     edx, 1
0x18005a6af  jz      short loc_18005A6E2
0x18005a6b1  cmp     rcx, r12
0x18005a6b4  jz      short loc_18005A6DB
0x18005a6b6  cmp     byte ptr [rcx+69h], 1
0x18005a6ba  jb      short loc_18005A6DB
0x18005a6bc  test    [rcx+6Ch], r13d
0x18005a6c0  jz      short loc_18005A6DB
0x18005a6c2  mov     rcx, [rcx+60h]
0x18005a6c6  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18005a6cd  mov     edx, 39h ; '9'
0x18005a6d2  call    WPP_SF_d
0x18005a6d7  mov     r10, [rbp+var_20]
0x18005a6db  mov     ebx, 57h ; 'W'
0x18005a6e0  jmp     short loc_18005A757
0x18005a6e2  mov     edx, [r10+0C8h]
0x18005a6e9  lea     r9, [r10+0C0h]
0x18005a6f0  movups  xmm0, xmmword ptr [r10+0B0h]
0x18005a6f8  mov     rcx, [r10+10h]
0x18005a6fc  mov     rax, [r10+0A8h]
0x18005a703  mov     [rsp+60h+var_38], edx
0x18005a707  mov     rdx, [r10+18h]
0x18005a70b  mov     [rsp+60h+var_40], r8d
0x18005a710  lea     r8, [rbp+var_10]
0x18005a714  movdqu  [rbp+var_10], xmm0
0x18005a719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a71e  jmp     short loc_18005A753
0x18005a720  mov     ecx, [r10+0C0h]
0x18005a727  mov     r9d, r8d
0x18005a72a  movups  xmm0, xmmword ptr [r10+0B0h]
0x18005a732  mov     rdx, [r10+18h]
0x18005a736  lea     r8, [rbp+var_10]
0x18005a73a  mov     rax, [r10+0A8h]
0x18005a741  mov     [rsp+60h+var_40], ecx
0x18005a745  mov     rcx, [r10+10h]
0x18005a749  movdqu  [rbp+var_10], xmm0
0x18005a74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a753  mov     r10, [rbp+var_20]
0x18005a757  test    r10, r10
0x18005a75a  jz      short loc_18005A771
0x18005a75c  mov     rcx, r10; struct _WFD_API_ASYNC_CONTEXT *
0x18005a75f  call    ?LocalWfdAsyncContextDeref@@YAKPEAU_WFD_API_ASYNC_CONTEXT@@@Z; LocalWfdAsyncContextDeref(_WFD_API_ASYNC_CONTEXT *)
0x18005a764  test    esi, esi
0x18005a766  jz      short loc_18005A771
0x18005a768  mov     rcx, [rbp+var_20]; struct _WFD_API_ASYNC_CONTEXT *
0x18005a76c  call    ?LocalWfdAsyncContextDeref@@YAKPEAU_WFD_API_ASYNC_CONTEXT@@@Z; LocalWfdAsyncContextDeref(_WFD_API_ASYNC_CONTEXT *)
0x18005a771  mov     rcx, r14; pwa
0x18005a774  call    cs:__imp_CloseThreadpoolWait
0x18005a77a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a781  cmp     rcx, r12
0x18005a784  jz      short loc_18005A7AA
0x18005a786  cmp     byte ptr [rcx+69h], 4
0x18005a78a  jb      short loc_18005A7AA
0x18005a78c  test    byte ptr [rcx+6Ch], 2
0x18005a790  jz      short loc_18005A7AA
0x18005a792  mov     rcx, [rcx+60h]
0x18005a796  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18005a79d  mov     edx, 3Ah ; ':'
0x18005a7a2  mov     r9d, ebx
0x18005a7a5  call    WPP_SF_d
0x18005a7aa  lea     r11, [rsp+60h+var_s0]
0x18005a7af  mov     rbx, [r11+30h]
0x18005a7b3  mov     rsi, [r11+40h]
0x18005a7b7  mov     rsp, r11
0x18005a7ba  pop     r14
0x18005a7bc  pop     r13
0x18005a7be  pop     r12
0x18005a7c0  pop     rdi
0x18005a7c1  pop     rbp
0x18005a7c2  retn
```

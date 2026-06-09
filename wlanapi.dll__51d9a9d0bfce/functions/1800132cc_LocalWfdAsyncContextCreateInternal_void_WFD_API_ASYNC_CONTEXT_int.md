# LocalWfdAsyncContextCreateInternal(void *,_WFD_API_ASYNC_CONTEXT * *,int)

- ea: `0x1800132cc`
- end: `0x1800135cf`
- name: `?LocalWfdAsyncContextCreateInternal@@YAKPEAXPEAPEAU_WFD_API_ASYNC_CONTEXT@@H@Z`
- size: `771`
- prototype: `unsigned int __fastcall(void *, struct _WFD_API_ASYNC_CONTEXT **, int)`
- caller_count: `9`
- callee_count: `8`
- tags: ``

## callers

- `0x180012e84`
- `0x180050370`
- `0x180050710`
- `0x180055438`
- `0x180055bb8`
- `0x180055d20`
- `0x1800572d4`
- `0x180059278`
- `0x180059558`

## callees

- `0x1800053c0`
- `0x1800063a0`
- `0x180006934`
- `0x1800132cc`
- `0x18001a5bc`
- `0x1800281e8`
- `0x18004fe34`
- `0x18005a7d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800134b4`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800134b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001340b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001340b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134c6`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800134d9`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800134d9`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180013584`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180013584`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18001337f`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18001337f`
- `MobileNetworking!HtNewHandle` at `0x18001344a`
- `MobileNetworking!HtNewHandle` at `0x18001344a`

## pseudocode

```c
__int64 __fastcall LocalWfdAsyncContextCreateInternal(void *a1, struct _WFD_API_ASYNC_CONTEXT **a2, int a3)
{
  union DOT11_OUI_HEADER *v6; // rcx
  DWORD v7; // eax
  DWORD LastError; // ebx
  char *v9; // rax
  char *v10; // rdi
  HANDLE EventA; // rax
  unsigned int v12; // eax
  __int64 v14; // [rsp+60h] [rbp+8h] BYREF
  __int64 v15; // [rsp+78h] [rbp+20h] BYREF

  v15 = 0;
  v14 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 59, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a1 && a2 )
  {
    v7 = HtReferenceHandleWithTag(g_hHandleTable, a1, a3 != 0 ? 1280333636 : 1466525252, 0, 1, &v14);
    LastError = v7;
    if ( !v7 )
    {
      v9 = (char *)AllocWLMem(0xD0u);
      v10 = v9;
      if ( !v9 )
      {
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 62, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
        }
        LastError = GetLastError();
        goto LABEL_32;
      }
      memset_0(v9, 0, 0xD0u);
      LastError = HtNewHandle(g_hHandleTable, v10, 1466525250, wfdAsyncContextDestroy, 1, &v15);
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 63, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
        }
        wfdAsyncContextDestroy(v10);
        goto LABEL_32;
      }
      *((_QWORD *)v10 + 2) = v15;
      *((_QWORD *)v10 + 1) = v14;
      v14 = 0;
      EventA = CreateEventA(0, 1, 0, 0);
      *((_QWORD *)v10 + 18) = EventA;
      if ( EventA )
      {
        v12 = RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)(v10 + 32), 0x70u);
        LastError = v12;
        if ( !v12 )
        {
          *((_QWORD *)v10 + 10) = *((_QWORD *)v10 + 18);
          *((_DWORD *)v10 + 19) = 1;
          *a2 = (struct _WFD_API_ASYNC_CONTEXT *)v10;
          goto LABEL_32;
        }
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 64, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v12);
        }
      }
      else
      {
        LastError = GetLastError();
      }
      LocalWfdAsyncContextDeref((struct _WFD_API_ASYNC_CONTEXT *)v10);
LABEL_32:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_39;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 12), 61, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, a1, v7);
      goto LABEL_32;
    }
  }
  else
  {
    if ( v6 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v6 + 105)
      && (*((_DWORD *)v6 + 27) & 0x1000) != 0 )
    {
      WPP_SF_(*((_QWORD *)v6 + 12), 60, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    LastError = 87;
  }
LABEL_39:
  if ( v14 )
  {
    HtDereferenceHandleWithTag(g_hHandleTable, a1, 0, 1);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v6 + 105) >= 4u
    && (*((_BYTE *)v6 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v6 + 12), 65, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800132cc  mov     rax, rsp
0x1800132cf  mov     [rax+10h], rbx
0x1800132d3  mov     [rax+18h], rbp
0x1800132d7  push    rsi
0x1800132d8  push    rdi
0x1800132d9  push    r12
0x1800132db  push    r13
0x1800132dd  push    r14
0x1800132df  sub     rsp, 30h
0x1800132e3  mov     ebx, r8d
0x1800132e6  mov     qword ptr [rax+20h], 0
0x1800132ee  mov     r14, rdx
0x1800132f1  mov     qword ptr [rax+8], 0
0x1800132f9  mov     rbp, rcx
0x1800132fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180013303  lea     r12, WPP_GLOBAL_Control
0x18001330a  lea     r13, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180013311  cmp     rcx, r12
0x180013314  jz      short loc_18001333A
0x180013316  cmp     byte ptr [rcx+69h], 4
0x18001331a  jb      short loc_18001333A
0x18001331c  test    byte ptr [rcx+6Ch], 2
0x180013320  jz      short loc_18001333A
0x180013322  mov     rcx, [rcx+60h]
0x180013326  mov     edx, 3Bh ; ';'
0x18001332b  mov     r8, r13
0x18001332e  call    WPP_SF_
0x180013333  mov     rcx, cs:WPP_GLOBAL_Control
0x18001333a  test    rbp, rbp
0x18001333d  jz      loc_180013538
0x180013343  test    r14, r14
0x180013346  jz      loc_180013538
0x18001334c  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180013353  lea     rax, [rsp+58h+arg_0]
0x180013358  mov     [rsp+58h+var_30], rax
0x18001335d  neg     ebx
0x18001335f  mov     esi, 1
0x180013364  mov     rdx, rbp
0x180013367  sbb     r8d, r8d
0x18001336a  mov     [rsp+58h+var_38], esi
0x18001336e  and     r8d, 0F4E6F100h
0x180013375  xor     r9d, r9d
0x180013378  add     r8d, 57696644h
0x18001337f  call    cs:__imp_HtReferenceHandleWithTag
0x180013385  mov     ebx, eax
0x180013387  test    eax, eax
0x180013389  jz      short loc_1800133CD
0x18001338b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013392  cmp     rcx, r12
0x180013395  jz      loc_18001356C
0x18001339b  cmp     [rcx+69h], sil
0x18001339f  jb      loc_18001356C
0x1800133a5  test    dword ptr [rcx+6Ch], 1000h
0x1800133ac  jz      loc_18001356C
0x1800133b2  mov     rcx, [rcx+60h]
0x1800133b6  lea     edx, [rsi+3Ch]
0x1800133b9  mov     r9, rbp
0x1800133bc  mov     [rsp+58h+var_38], eax
0x1800133c0  mov     r8, r13
0x1800133c3  call    WPP_SF_qD
0x1800133c8  jmp     loc_18001351C
0x1800133cd  mov     ebx, 0D0h
0x1800133d2  mov     ecx, ebx; dwBytes
0x1800133d4  call    AllocWLMem
0x1800133d9  mov     rdi, rax
0x1800133dc  test    rax, rax
0x1800133df  jnz     short loc_180013418
0x1800133e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800133e8  cmp     rcx, r12
0x1800133eb  jz      short loc_18001340B
0x1800133ed  cmp     [rcx+69h], sil
0x1800133f1  jb      short loc_18001340B
0x1800133f3  test    dword ptr [rcx+6Ch], 1000h
0x1800133fa  jz      short loc_18001340B
0x1800133fc  mov     rcx, [rcx+60h]
0x180013400  lea     edx, [rax+3Eh]
0x180013403  mov     r8, r13
0x180013406  call    WPP_SF_
0x18001340b  call    cs:__imp_GetLastError
0x180013411  mov     ebx, eax
0x180013413  jmp     loc_18001351C
0x180013418  mov     r8, rbx; Size
0x18001341b  xor     edx, edx; Val
0x18001341d  mov     rcx, rdi; void *
0x180013420  call    memset_0
0x180013425  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18001342c  lea     rax, [rsp+58h+arg_18]
0x180013431  mov     [rsp+58h+var_30], rax
0x180013436  lea     r9, ?wfdAsyncContextDestroy@@YAXPEAX@Z; wfdAsyncContextDestroy(void *)
0x18001343d  mov     r8d, 57696642h
0x180013443  mov     [rsp+58h+var_38], esi
0x180013447  mov     rdx, rdi
0x18001344a  call    cs:__imp_HtNewHandle
0x180013450  mov     ebx, eax
0x180013452  test    eax, eax
0x180013454  jz      short loc_18001348F
0x180013456  mov     rcx, cs:WPP_GLOBAL_Control
0x18001345d  cmp     rcx, r12
0x180013460  jz      short loc_180013482
0x180013462  cmp     [rcx+69h], sil
0x180013466  jb      short loc_180013482
0x180013468  test    dword ptr [rcx+6Ch], 1000h
0x18001346f  jz      short loc_180013482
0x180013471  mov     rcx, [rcx+60h]
0x180013475  mov     edx, 3Fh ; '?'
0x18001347a  mov     r8, r13
0x18001347d  call    WPP_SF_
0x180013482  mov     rcx, rdi; void *
0x180013485  call    ?wfdAsyncContextDestroy@@YAXPEAX@Z; wfdAsyncContextDestroy(void *)
0x18001348a  jmp     loc_18001351C
0x18001348f  mov     rax, [rsp+58h+arg_18]
0x180013494  xor     r9d, r9d; lpName
0x180013497  mov     [rdi+10h], rax
0x18001349b  xor     r8d, r8d; bInitialState
0x18001349e  mov     rax, [rsp+58h+arg_0]
0x1800134a3  mov     edx, esi; bManualReset
0x1800134a5  mov     [rdi+8], rax
0x1800134a9  xor     ecx, ecx; lpEventAttributes
0x1800134ab  mov     [rsp+58h+arg_0], 0
0x1800134b4  call    cs:__imp_CreateEventA
0x1800134ba  mov     [rdi+90h], rax
0x1800134c1  test    rax, rax
0x1800134c4  jnz     short loc_1800134D0
0x1800134c6  call    cs:__imp_GetLastError
0x1800134cc  mov     ebx, eax
0x1800134ce  jmp     short loc_180013514
0x1800134d0  lea     rcx, [rdi+20h]; pAsync
0x1800134d4  mov     edx, 70h ; 'p'; Size
0x1800134d9  call    cs:__imp_RpcAsyncInitializeHandle
0x1800134df  mov     ebx, eax
0x1800134e1  test    eax, eax
0x1800134e3  jz      short loc_180013525
0x1800134e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134ec  cmp     rcx, r12
0x1800134ef  jz      short loc_180013514
0x1800134f1  cmp     [rcx+69h], sil
0x1800134f5  jb      short loc_180013514
0x1800134f7  test    dword ptr [rcx+6Ch], 1000h
0x1800134fe  jz      short loc_180013514
0x180013500  mov     rcx, [rcx+60h]
0x180013504  mov     edx, 40h ; '@'
0x180013509  mov     r9d, eax
0x18001350c  mov     r8, r13
0x18001350f  call    WPP_SF_d
0x180013514  mov     rcx, rdi; struct _WFD_API_ASYNC_CONTEXT *
0x180013517  call    ?LocalWfdAsyncContextDeref@@YAKPEAU_WFD_API_ASYNC_CONTEXT@@@Z; LocalWfdAsyncContextDeref(_WFD_API_ASYNC_CONTEXT *)
0x18001351c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013523  jmp     short loc_18001356C
0x180013525  mov     rax, [rdi+90h]
0x18001352c  mov     [rdi+50h], rax
0x180013530  mov     [rdi+4Ch], esi
0x180013533  mov     [r14], rdi
0x180013536  jmp     short loc_18001351C
0x180013538  mov     esi, 1
0x18001353d  cmp     rcx, r12
0x180013540  jz      short loc_180013567
0x180013542  cmp     [rcx+69h], sil
0x180013546  jb      short loc_180013567
0x180013548  test    dword ptr [rcx+6Ch], 1000h
0x18001354f  jz      short loc_180013567
0x180013551  mov     rcx, [rcx+60h]
0x180013555  lea     edx, [rsi+3Bh]
0x180013558  mov     r8, r13
0x18001355b  call    WPP_SF_
0x180013560  mov     rcx, cs:WPP_GLOBAL_Control
0x180013567  mov     ebx, 57h ; 'W'
0x18001356c  cmp     [rsp+58h+arg_0], 0
0x180013572  jz      short loc_180013591
0x180013574  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18001357b  mov     r9d, esi
0x18001357e  xor     r8d, r8d
0x180013581  mov     rdx, rbp
0x180013584  call    cs:__imp_HtDereferenceHandleWithTag
0x18001358a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013591  cmp     rcx, r12
0x180013594  jz      short loc_1800135B6
0x180013596  cmp     byte ptr [rcx+69h], 4
0x18001359a  jb      short loc_1800135B6
0x18001359c  test    byte ptr [rcx+6Ch], 2
0x1800135a0  jz      short loc_1800135B6
0x1800135a2  mov     rcx, [rcx+60h]
0x1800135a6  mov     edx, 41h ; 'A'
0x1800135ab  mov     r9d, ebx
0x1800135ae  mov     r8, r13
0x1800135b1  call    WPP_SF_d
0x1800135b6  mov     rbp, [rsp+58h+arg_10]
0x1800135bb  mov     eax, ebx
0x1800135bd  mov     rbx, [rsp+58h+arg_8]
0x1800135c2  add     rsp, 30h
0x1800135c6  pop     r14
0x1800135c8  pop     r13
0x1800135ca  pop     r12
0x1800135cc  pop     rdi
0x1800135cd  pop     rsi
0x1800135ce  retn
```

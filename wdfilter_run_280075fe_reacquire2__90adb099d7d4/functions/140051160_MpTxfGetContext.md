# MpTxfGetContext

- ea: `0x140051160`
- end: `0x1400516f1`
- name: `MpTxfGetContext`
- size: `1425`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: ``

## callers

- `0x140030380`
- `0x1400393f0`
- `0x14003a660`
- `0x140050cf0`
- `0x140051af0`
- `0x14007d2bc`

## callees

- `0x1400018a4`
- `0x1400026c0`
- `0x1400049dc`
- `0x1400118d0`
- `0x140011bc0`
- `0x140050b88`
- `0x140051160`

## import_xrefs

- `ntoskrnl!RtlStringFromGUID` at `0x140051513`
- `ntoskrnl!RtlStringFromGUID` at `0x140051513`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005133f`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005133f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400513f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400513f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400513ea`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400513ea`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400513a3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400513a3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005138e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005138e`
- `FLTMGR!FltReleaseContext` at `0x1400515c8`
- `FLTMGR!FltReleaseContext` at `0x14005166e`
- `FLTMGR!FltReleaseContext` at `0x140051687`
- `FLTMGR!FltReleaseContext` at `0x1400515c8`
- `FLTMGR!FltReleaseContext` at `0x14005166e`
- `FLTMGR!FltReleaseContext` at `0x140051687`
- `FLTMGR!FltSetTransactionContext` at `0x140051573`
- `FLTMGR!FltSetTransactionContext` at `0x140051573`
- `FLTMGR!FltGetTransactionContext` at `0x1400511d9`
- `FLTMGR!FltGetTransactionContext` at `0x1400511d9`
- `FLTMGR!FltEnlistInTransaction` at `0x1400515ef`
- `FLTMGR!FltEnlistInTransaction` at `0x1400515ef`
- `FLTMGR!FltDeleteContext` at `0x140051646`
- `FLTMGR!FltDeleteContext` at `0x140051646`
- `FLTMGR!FltReferenceContext` at `0x14005136f`
- `FLTMGR!FltReferenceContext` at `0x14005136f`
- `FLTMGR!FltAllocateContext` at `0x1400512da`
- `FLTMGR!FltAllocateContext` at `0x1400512da`
- `FLTMGR!FltGetInstanceContext` at `0x14005125d`
- `FLTMGR!FltGetInstanceContext` at `0x14005125d`

## pseudocode

```c
__int64 __fastcall MpTxfGetContext(__int64 a1, char a2, struct _KTRANSACTION *a3, PFLT_CONTEXT *a4)
{
  __int64 result; // rax
  NTSTATUS TransactionContext; // ebx
  NTSTATUS InstanceContext; // eax
  __int64 v11; // rdx
  __int64 v12; // r9
  PDEVICE_OBJECT v13; // rcx
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  char *v16; // rbx
  char *v17; // rax
  _QWORD *v18; // rcx
  PFLT_CONTEXT *v19; // rdx
  _QWORD *v20; // rbx
  __int64 v21; // rdx
  _QWORD *v22; // rbx
  __int64 v23; // rcx
  NTSTATUS v24; // eax
  PFLT_CONTEXT v25; // r8
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-20h] BYREF
  PFLT_CONTEXT v27; // [rsp+38h] [rbp-18h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+40h] [rbp-10h] BYREF

  Context = 0;
  OldContext = 0;
  v27 = 0;
  if ( !MpTxfData )
    return 3221225659LL;
  if ( a1 && a4 && a3 )
  {
    TransactionContext = FltGetTransactionContext(*(PFLT_INSTANCE *)(a1 + 24), a3, &Context);
    if ( TransactionContext >= 0 )
    {
      *a4 = Context;
      return 0;
    }
    result = 3221226021LL;
    if ( TransactionContext != -1073741275 )
    {
      _mm_lfence();
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          WPP_7b03be39b4a33db2ed204d39738df527_Traceguids,
          (unsigned int)TransactionContext);
      }
      return (unsigned int)TransactionContext;
    }
    if ( !a2 )
    {
      _mm_lfence();
      return result;
    }
    InstanceContext = FltGetInstanceContext(*(PFLT_INSTANCE *)(a1 + 24), &v27);
    TransactionContext = InstanceContext;
    if ( InstanceContext >= 0 )
    {
      TransactionContext = FltAllocateContext(
                             *(PFLT_FILTER *)(a1 + 8),
                             0x20u,
                             0xB0u,
                             ExDefaultNonPagedPoolType,
                             &Context);
      if ( TransactionContext >= 0 )
      {
        memset(Context, 0, 0xB0u);
        *(_WORD *)Context = -9723;
        *((_WORD *)Context + 1) = 176;
        ExInitializeResourceLite((PERESOURCE)((char *)Context + 8));
        v14 = (char *)Context + 112;
        *((_QWORD *)Context + 15) = (char *)Context + 112;
        *v14 = v14;
        v15 = (char *)Context + 136;
        *((_QWORD *)Context + 18) = (char *)Context + 136;
        *v15 = v15;
        FltReferenceContext(v27);
        *((_QWORD *)Context + 16) = v27;
        v16 = (char *)v27;
        KeEnterCriticalRegion();
        ExAcquireResourceExclusiveLite((PERESOURCE)(v16 + 288), 1u);
        v17 = (char *)v27 + 392;
        v18 = (char *)Context + 112;
        v19 = (PFLT_CONTEXT *)*((_QWORD *)v27 + 50);
        if ( *v19 != (char *)v27 + 392 )
          __fastfail(3u);
        *v18 = v17;
        v18[1] = v19;
        *v19 = v18;
        *((_QWORD *)v17 + 1) = v18;
        ExReleaseResourceLite((PERESOURCE)((char *)v27 + 288));
        KeLeaveCriticalRegion();
        v20 = Context;
        v20[20] = MpAllocatePoolWithTag(1, 16, 1735675981);
        v21 = *((_QWORD *)Context + 20);
        if ( !v21 )
        {
          TransactionContext = -1073741670;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_56;
          }
          v11 = 15;
          v12 = 3221225626LL;
          goto LABEL_20;
        }
        _mm_lfence();
        TransactionContext = MpQueryTransactionId(a3, v21);
        if ( TransactionContext >= 0 )
        {
          _mm_lfence();
          v22 = Context;
          v22[19] = MpAllocatePoolWithTag(1, 16, 1853116493);
          v23 = *((_QWORD *)Context + 19);
          if ( v23 )
          {
            *(_QWORD *)(v23 + 8) = 0;
            **((_WORD **)Context + 19) = 0;
            *(_WORD *)(*((_QWORD *)Context + 19) + 2LL) = 0;
            v24 = RtlStringFromGUID(*((const GUID *const *)Context + 20), *((PUNICODE_STRING *)Context + 19));
            if ( v24 < 0
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              _mm_lfence();
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                17,
                WPP_7b03be39b4a33db2ed204d39738df527_Traceguids,
                (unsigned int)v24);
            }
          }
          TransactionContext = FltSetTransactionContext(
                                 *(PFLT_INSTANCE *)(a1 + 24),
                                 a3,
                                 FLT_SET_CONTEXT_KEEP_IF_EXISTS,
                                 Context,
                                 &OldContext);
          if ( (int)(TransactionContext + 0x80000000) < 0 || TransactionContext == -1071906814 )
          {
            _mm_lfence();
            if ( TransactionContext == -1071906814 )
            {
              FltReleaseContext(Context);
              v25 = OldContext;
              Context = OldContext;
            }
            else
            {
              v25 = Context;
            }
            TransactionContext = FltEnlistInTransaction(*(PFLT_INSTANCE *)(a1 + 24), a3, v25, 0xCu);
            if ( ((TransactionContext + 0x80000000) & 0x80000000) != 0 || TransactionContext == -1071906789 )
            {
              TransactionContext = 0;
              *a4 = Context;
              Context = 0;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                _mm_lfence();
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  19,
                  WPP_7b03be39b4a33db2ed204d39738df527_Traceguids,
                  (unsigned int)TransactionContext);
              }
              FltDeleteContext(Context);
            }
            goto LABEL_56;
          }
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
LABEL_56:
            _mm_lfence();
            if ( v27 )
              FltReleaseContext(v27);
            if ( Context )
              FltReleaseContext(Context);
            return (unsigned int)TransactionContext;
          }
          v11 = 18;
        }
        else
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_56;
          }
          v11 = 16;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_56;
        v11 = 14;
      }
      v12 = (unsigned int)TransactionContext;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_56;
      v11 = 13;
      v12 = (unsigned int)InstanceContext;
    }
    _mm_lfence();
    v13 = WPP_GLOBAL_Control;
LABEL_20:
    WPP_SF_d(v13->AttachedDevice, v11, WPP_7b03be39b4a33db2ed204d39738df527_Traceguids, v12);
    goto LABEL_56;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_7b03be39b4a33db2ed204d39738df527_Traceguids);
  return 3221225485LL;
}

```

## disassembly

```asm
0x140051160  mov     [rsp-38h+arg_8], rbx
0x140051165  push    rbp
0x140051166  push    rsi
0x140051167  push    rdi
0x140051168  push    r12
0x14005116a  push    r13
0x14005116c  push    r14
0x14005116e  push    r15
0x140051170  mov     rbp, rsp
0x140051173  sub     rsp, 50h
0x140051177  mov     rax, cs:__security_cookie
0x14005117e  xor     rax, rsp
0x140051181  mov     [rbp+var_8], rax
0x140051185  xor     r12d, r12d
0x140051188  mov     r15, r9
0x14005118b  cmp     cs:MpTxfData, r12
0x140051192  mov     r14, r8
0x140051195  mov     dil, dl
0x140051198  mov     [rbp+Context], r12
0x14005119c  mov     rsi, rcx
0x14005119f  mov     [rbp+OldContext], r12
0x1400511a3  mov     [rbp+var_18], r12
0x1400511a7  jnz     short loc_1400511B3
0x1400511a9  mov     eax, 0C00000BBh
0x1400511ae  jmp     loc_1400516CC
0x1400511b3  test    rsi, rsi
0x1400511b6  jz      loc_140051698
0x1400511bc  test    r15, r15
0x1400511bf  jz      loc_140051698
0x1400511c5  test    r14, r14
0x1400511c8  jz      loc_140051698
0x1400511ce  mov     rcx, [rcx+18h]; Instance
0x1400511d2  lea     r8, [rbp+Context]; Context
0x1400511d6  mov     rdx, r14; Transaction
0x1400511d9  call    cs:__imp_FltGetTransactionContext
0x1400511e0  nop     dword ptr [rax+rax+00h]
0x1400511e5  mov     ebx, eax
0x1400511e7  test    eax, eax
0x1400511e9  js      short loc_1400511F9
0x1400511eb  mov     rax, [rbp+Context]
0x1400511ef  mov     [r15], rax
0x1400511f2  xor     eax, eax
0x1400511f4  jmp     loc_1400516CC
0x1400511f9  mov     eax, 0C0000225h
0x1400511fe  cmp     ebx, eax
0x140051200  jz      short loc_140051248
0x140051202  lfence
0x140051205  mov     rax, cs:WPP_GLOBAL_Control
0x14005120c  lea     rdi, WPP_GLOBAL_Control
0x140051213  cmp     rax, rdi
0x140051216  jz      short loc_140051241
0x140051218  mov     eax, [rax+2Ch]
0x14005121b  test    al, 1
0x14005121d  jz      short loc_140051241
0x14005121f  lfence
0x140051222  mov     rcx, cs:WPP_GLOBAL_Control
0x140051229  lea     r8, WPP_7b03be39b4a33db2ed204d39738df527_Traceguids
0x140051230  mov     edx, 0Ch
0x140051235  mov     r9d, ebx
0x140051238  mov     rcx, [rcx+18h]
0x14005123c  call    WPP_SF_d
0x140051241  mov     eax, ebx
0x140051243  jmp     loc_1400516CC
0x140051248  test    dil, dil
0x14005124b  jnz     short loc_140051255
0x14005124d  lfence
0x140051250  jmp     loc_1400516CC
0x140051255  mov     rcx, [rsi+18h]; Instance
0x140051259  lea     rdx, [rbp+var_18]; Context
0x14005125d  call    cs:__imp_FltGetInstanceContext
0x140051264  nop     dword ptr [rax+rax+00h]
0x140051269  mov     ebx, eax
0x14005126b  test    eax, eax
0x14005126d  jns     short loc_1400512B9
0x14005126f  mov     rcx, cs:WPP_GLOBAL_Control
0x140051276  lea     rdi, WPP_GLOBAL_Control
0x14005127d  cmp     rcx, rdi
0x140051280  jz      loc_140051662
0x140051286  mov     ecx, [rcx+2Ch]
0x140051289  test    cl, 1
0x14005128c  jz      loc_140051662
0x140051292  mov     edx, 0Dh
0x140051297  mov     r9d, eax
0x14005129a  lfence
0x14005129d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400512a4  mov     rcx, [rcx+18h]
0x1400512a8  lea     r8, WPP_7b03be39b4a33db2ed204d39738df527_Traceguids
0x1400512af  call    WPP_SF_d
0x1400512b4  jmp     loc_140051662
0x1400512b9  mov     r9d, cs:ExDefaultNonPagedPoolType; PoolType
0x1400512c0  lea     rax, [rbp+Context]
0x1400512c4  mov     rcx, [rsi+8]; Filter
0x1400512c8  mov     edi, 0B0h
0x1400512cd  mov     r8d, edi; ContextSize
0x1400512d0  mov     [rsp+50h+ReturnedContext], rax; ReturnedContext
0x1400512d5  mov     edx, 20h ; ' '; ContextType
0x1400512da  call    cs:__imp_FltAllocateContext
0x1400512e1  nop     dword ptr [rax+rax+00h]
0x1400512e6  mov     ebx, eax
0x1400512e8  test    eax, eax
0x1400512ea  jns     short loc_140051318
0x1400512ec  mov     rax, cs:WPP_GLOBAL_Control
0x1400512f3  lea     rdi, WPP_GLOBAL_Control
0x1400512fa  cmp     rax, rdi
0x1400512fd  jz      loc_140051662
0x140051303  mov     eax, [rax+2Ch]
0x140051306  test    al, 1
0x140051308  jz      loc_140051662
0x14005130e  mov     edx, 0Eh
0x140051313  mov     r9d, ebx
0x140051316  jmp     short loc_14005129A
0x140051318  mov     rcx, [rbp+Context]; void *
0x14005131c  mov     r8, rdi; Size
0x14005131f  xor     edx, edx; Val
0x140051321  call    memset
0x140051326  mov     rax, [rbp+Context]
0x14005132a  mov     word ptr [rax], 0DA05h
0x14005132f  mov     rax, [rbp+Context]
0x140051333  mov     [rax+2], di
0x140051337  mov     rcx, [rbp+Context]
0x14005133b  add     rcx, 8; Resource
0x14005133f  call    cs:__imp_ExInitializeResourceLite
0x140051346  nop     dword ptr [rax+rax+00h]
0x14005134b  mov     rax, [rbp+Context]
0x14005134f  add     rax, 70h ; 'p'
0x140051353  mov     [rax+8], rax
0x140051357  mov     [rax], rax
0x14005135a  mov     rax, [rbp+Context]
0x14005135e  add     rax, 88h
0x140051364  mov     [rax+8], rax
0x140051368  mov     [rax], rax
0x14005136b  mov     rcx, [rbp+var_18]; Context
0x14005136f  call    cs:__imp_FltReferenceContext
0x140051376  nop     dword ptr [rax+rax+00h]
0x14005137b  mov     rcx, [rbp+Context]
0x14005137f  mov     rax, [rbp+var_18]
0x140051383  mov     [rcx+80h], rax
0x14005138a  mov     rbx, [rbp+var_18]
0x14005138e  call    cs:__imp_KeEnterCriticalRegion
0x140051395  nop     dword ptr [rax+rax+00h]
0x14005139a  mov     dl, 1; Wait
0x14005139c  lea     rcx, [rbx+120h]; Resource
0x1400513a3  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400513aa  nop     dword ptr [rax+rax+00h]
0x1400513af  mov     rax, [rbp+var_18]
0x1400513b3  mov     rcx, [rbp+Context]
0x1400513b7  add     rax, 188h
0x1400513bd  add     rcx, 70h ; 'p'
0x1400513c1  mov     rdx, [rax+8]
0x1400513c5  cmp     [rdx], rax
0x1400513c8  jz      short loc_1400513D1
0x1400513ca  mov     ecx, 3
0x1400513cf  int     29h; Win8: RtlFailFast(ecx)
0x1400513d1  mov     [rcx], rax
0x1400513d4  mov     [rcx+8], rdx
0x1400513d8  mov     [rdx], rcx
0x1400513db  mov     [rax+8], rcx
0x1400513df  mov     rcx, [rbp+var_18]
0x1400513e3  add     rcx, 120h; Resource
0x1400513ea  call    cs:__imp_ExReleaseResourceLite
0x1400513f1  nop     dword ptr [rax+rax+00h]
0x1400513f6  call    cs:__imp_KeLeaveCriticalRegion
0x1400513fd  nop     dword ptr [rax+rax+00h]
0x140051402  mov     rbx, [rbp+Context]
0x140051406  mov     r13d, 10h
0x14005140c  mov     r8d, 6774504Dh
0x140051412  mov     edx, r13d
0x140051415  lea     ecx, [r13-0Fh]
0x140051419  call    MpAllocatePoolWithTag
0x14005141e  mov     [rbx+0A0h], rax
0x140051425  mov     rax, [rbp+Context]
0x140051429  mov     rdx, [rax+0A0h]
0x140051430  test    rdx, rdx
0x140051433  jnz     short loc_14005146B
0x140051435  mov     ebx, 0C000009Ah
0x14005143a  mov     rcx, cs:WPP_GLOBAL_Control
0x140051441  lea     rdi, WPP_GLOBAL_Control
0x140051448  cmp     rcx, rdi
0x14005144b  jz      loc_140051662
0x140051451  mov     eax, [rcx+2Ch]
0x140051454  test    al, 1
0x140051456  jz      loc_140051662
0x14005145c  lea     edx, [r13-1]
0x140051460  mov     r9d, 0C000009Ah
0x140051466  jmp     loc_1400512A4
0x14005146b  lfence
0x14005146e  mov     rcx, r14
0x140051471  call    MpQueryTransactionId
0x140051476  mov     ebx, eax
0x140051478  test    eax, eax
0x14005147a  jns     short loc_1400514A6
0x14005147c  mov     rax, cs:WPP_GLOBAL_Control
0x140051483  lea     rdi, WPP_GLOBAL_Control
0x14005148a  cmp     rax, rdi
0x14005148d  jz      loc_140051662
0x140051493  mov     eax, [rax+2Ch]
0x140051496  test    al, 1
0x140051498  jz      loc_140051662
0x14005149e  mov     edx, r13d
0x1400514a1  jmp     loc_140051313
0x1400514a6  lfence
0x1400514a9  mov     rbx, [rbp+Context]
0x1400514ad  mov     r8d, 6E74504Dh
0x1400514b3  mov     rdx, r13
0x1400514b6  mov     ecx, 1
0x1400514bb  call    MpAllocatePoolWithTag
0x1400514c0  mov     [rbx+98h], rax
0x1400514c7  lea     rdi, WPP_GLOBAL_Control
0x1400514ce  mov     rax, [rbp+Context]
0x1400514d2  mov     rcx, [rax+98h]
0x1400514d9  test    rcx, rcx
0x1400514dc  jz      short loc_140051559
0x1400514de  mov     [rcx+8], r12
0x1400514e2  mov     rax, [rbp+Context]
0x1400514e6  mov     rcx, [rax+98h]
0x1400514ed  mov     [rcx], r12w
0x1400514f1  mov     rax, [rbp+Context]
0x1400514f5  mov     rcx, [rax+98h]
0x1400514fc  mov     [rcx+2], r12w
0x140051501  mov     rcx, [rbp+Context]
0x140051505  mov     rdx, [rcx+98h]; GuidString
0x14005150c  mov     rcx, [rcx+0A0h]; Guid
0x140051513  call    cs:__imp_RtlStringFromGUID
0x14005151a  nop     dword ptr [rax+rax+00h]
0x14005151f  test    eax, eax
0x140051521  jns     short loc_140051559
0x140051523  mov     rcx, cs:WPP_GLOBAL_Control
0x14005152a  cmp     rcx, rdi
0x14005152d  jz      short loc_140051559
0x14005152f  mov     ecx, [rcx+2Ch]
0x140051532  test    cl, 1
0x140051535  jz      short loc_140051559
0x140051537  lfence
0x14005153a  mov     rcx, cs:WPP_GLOBAL_Control
0x140051541  lea     r8, WPP_7b03be39b4a33db2ed204d39738df527_Traceguids
0x140051548  mov     edx, 11h
0x14005154d  mov     r9d, eax
0x140051550  mov     rcx, [rcx+18h]
0x140051554  call    WPP_SF_d
0x140051559  mov     r9, [rbp+Context]; NewContext
0x14005155d  lea     rax, [rbp+OldContext]
0x140051561  mov     rcx, [rsi+18h]; Instance
0x140051565  mov     r8d, 1; Operation
0x14005156b  mov     rdx, r14; Transaction
0x14005156e  mov     [rsp+50h+ReturnedContext], rax; OldContext
0x140051573  call    cs:__imp_FltSetTransactionContext
0x14005157a  nop     dword ptr [rax+rax+00h]
0x14005157f  mov     r13d, 80000000h
0x140051585  mov     ecx, 0C01C0002h
0x14005158a  mov     ebx, eax
0x14005158c  add     eax, r13d
0x14005158f  test    r13d, eax
0x140051592  jnz     short loc_1400515BD
0x140051594  cmp     ebx, ecx
0x140051596  jz      short loc_1400515BD
0x140051598  mov     rax, cs:WPP_GLOBAL_Control
0x14005159f  cmp     rax, rdi
0x1400515a2  jz      loc_140051662
0x1400515a8  mov     eax, [rax+2Ch]
0x1400515ab  test    al, 1
0x1400515ad  jz      loc_140051662
0x1400515b3  mov     edx, 12h
0x1400515b8  jmp     loc_140051313
0x1400515bd  lfence
0x1400515c0  cmp     ebx, ecx
0x1400515c2  jnz     short loc_1400515DE
0x1400515c4  mov     rcx, [rbp+Context]; Context
0x1400515c8  call    cs:__imp_FltReleaseContext
0x1400515cf  nop     dword ptr [rax+rax+00h]
0x1400515d4  mov     r8, [rbp+OldContext]
0x1400515d8  mov     [rbp+Context], r8
0x1400515dc  jmp     short loc_1400515E2
0x1400515de  mov     r8, [rbp+Context]; TransactionContext
0x1400515e2  mov     rcx, [rsi+18h]; Instance
0x1400515e6  mov     r9d, 0Ch; NotificationMask
0x1400515ec  mov     rdx, r14; Transaction
0x1400515ef  call    cs:__imp_FltEnlistInTransaction
0x1400515f6  nop     dword ptr [rax+rax+00h]
0x1400515fb  mov     ebx, eax
0x1400515fd  add     eax, r13d
0x140051600  test    r13d, eax
0x140051603  jnz     short loc_140051654
0x140051605  cmp     ebx, 0C01C001Bh
0x14005160b  jz      short loc_140051654
0x14005160d  mov     rax, cs:WPP_GLOBAL_Control
0x140051614  cmp     rax, rdi
0x140051617  jz      short loc_140051642
0x140051619  mov     eax, [rax+2Ch]
0x14005161c  test    al, 1
0x14005161e  jz      short loc_140051642
0x140051620  lfence
0x140051623  mov     rcx, cs:WPP_GLOBAL_Control
0x14005162a  lea     r8, WPP_7b03be39b4a33db2ed204d39738df527_Traceguids
0x140051631  mov     edx, 13h
0x140051636  mov     r9d, ebx
0x140051639  mov     rcx, [rcx+18h]
0x14005163d  call    WPP_SF_d
0x140051642  mov     rcx, [rbp+Context]; Context
0x140051646  call    cs:__imp_FltDeleteContext
0x14005164d  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```

# TmRollbackEnlistmentExt

- ea: `0x140020250`
- end: `0x140020447`
- name: `TmRollbackEnlistmentExt`
- size: `503`
- prototype: `NTSTATUS __stdcall(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14000c718`
- `0x140013b80`
- `0x14001c4a0`

## callees

- `0x140001e10`
- `0x140011ab4`
- `0x14001b338`
- `0x140020250`
- `0x1400209fc`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400202f8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400202f8`
- `ntoskrnl!KeReleaseMutex` at `0x1400203ef`
- `ntoskrnl!KeReleaseMutex` at `0x14002041e`
- `ntoskrnl!KeReleaseMutex` at `0x140020434`
- `ntoskrnl!KeReleaseMutex` at `0x140021a17`
- `ntoskrnl!KeReleaseMutex` at `0x140021a32`
- `ntoskrnl!KeReleaseMutex` at `0x1400203ef`
- `ntoskrnl!KeReleaseMutex` at `0x14002041e`
- `ntoskrnl!KeReleaseMutex` at `0x140020434`
- `ntoskrnl!KeReleaseMutex` at `0x140021a17`
- `ntoskrnl!KeReleaseMutex` at `0x140021a32`
- `ntoskrnl!DbgPrintEx` at `0x140020290`
- `ntoskrnl!DbgPrintEx` at `0x140020290`

## string_xrefs

- `0x14002027f`: `KTM:  TmRollbackEnlistmentExt for tx %lx\n`

## pseudocode

```c
NTSTATUS __stdcall TmRollbackEnlistmentExt(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)
{
  __int64 v4; // rbx
  __int64 v5; // r14
  _QWORD *v6; // rcx
  struct _KMUTANT *v8; // r15
  char v9; // di
  char v10; // cl
  unsigned int v11; // eax
  int v12; // edx
  int v13; // eax
  int v14; // r8d
  NTSTATUS v15; // esi

  v4 = *((_QWORD *)Enlistment + 20);
  v5 = *((_QWORD *)Enlistment + 19);
  DbgPrintEx(0x6Cu, 0x80000020, "KTM:  TmRollbackEnlistmentExt for tx %lx\n", v4);
  v6 = (_QWORD *)(v5 + 360);
  if ( TmVirtualClock && !*v6 )
    return -1072103342;
  TmpAdjustVirtualClock(*v6, TmVirtualClock);
  TmpAcquireTransactionMutex(v4);
  v8 = (struct _KMUTANT *)((char *)Enlistment + 64);
  KeWaitForSingleObject((char *)Enlistment + 64, Executive, 0, 0, 0);
  v9 = 1;
  v10 = 0;
  if ( (*((_DWORD *)Enlistment + 43) & 1) != 0 )
  {
    v11 = *(_DWORD *)(v4 + 192);
    if ( v11 <= 0xB )
    {
      v12 = 2334;
      if ( _bittest(&v12, v11) )
      {
        v10 = 1;
        if ( (*(_DWORD *)(v4 + 196) & 0x80u) == 0 )
          _InterlockedOr((volatile signed __int32 *)(v4 + 196), 0x40u);
      }
    }
  }
  else
  {
    v13 = *((_DWORD *)Enlistment + 42);
    if ( (unsigned int)(v13 - 256) <= 0x11 && (v14 = 132355, _bittest(&v14, v13 - 256)) )
    {
      v10 = 1;
    }
    else if ( v13 == 258 || v13 == 261 )
    {
      _InterlockedOr((volatile signed __int32 *)(v4 + 196), 0x8000000u);
    }
  }
  if ( v10 )
  {
    if ( *(__int64 (__fastcall **)(PKENLISTMENT *, PVOID, PVOID, ULONG, PLARGE_INTEGER))(v5 + 296) != TmpInternalCrmNotification
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
    {
      WPP_SF_q_guid__guid_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        10,
        *((_DWORD *)Enlistment + 40) + 176,
        v4,
        *((_QWORD *)Enlistment + 20) + 176LL,
        v5 + 136);
    }
    KeReleaseMutex((PRKMUTEX)((char *)Enlistment + 64), 0);
    v9 = 0;
    v15 = TmpTxActionDoRollback(v4);
  }
  else
  {
    v15 = -1072103405;
  }
  if ( v9 )
    KeReleaseMutex(v8, 0);
  KeReleaseMutex((PRKMUTEX)(*(_QWORD *)(v4 + 88) + 32LL), 0);
  return v15;
}

```

## disassembly

```asm
0x140020250  mov     [rsp+arg_10], rbx
0x140020255  mov     [rsp+arg_18], rsi
0x14002025a  mov     [rsp+arg_0], rcx
0x14002025f  push    rdi
0x140020260  push    r14
0x140020262  push    r15
0x140020264  sub     rsp, 40h
0x140020268  mov     rdi, rdx
0x14002026b  mov     rsi, rcx
0x14002026e  mov     rbx, [rcx+0A0h]
0x140020275  mov     r14, [rcx+98h]
0x14002027c  mov     r9, rbx
0x14002027f  lea     r8, aKtmTmrollbacke; "KTM:  TmRollbackEnlistmentExt for tx %l"...
0x140020286  mov     edx, 80000020h; Level
0x14002028b  mov     ecx, 6Ch ; 'l'; ComponentId
0x140020290  call    cs:__imp_DbgPrintEx
0x140020297  nop     dword ptr [rax+rax+00h]
0x14002029c  lea     rcx, [r14+168h]
0x1400202a3  test    rdi, rdi
0x1400202a6  jz      short loc_1400202C8
0x1400202a8  cmp     qword ptr [rcx], 0
0x1400202ac  jnz     short loc_1400202C8
0x1400202ae  mov     eax, 0C0190052h
0x1400202b3  mov     rbx, [rsp+58h+arg_10]
0x1400202b8  mov     rsi, [rsp+58h+arg_18]
0x1400202bd  add     rsp, 40h
0x1400202c1  pop     r15
0x1400202c3  pop     r14
0x1400202c5  pop     rdi
0x1400202c6  retn
0x1400202c8  mov     [rsp+58h+arg_8], rbx
0x1400202cd  mov     rdx, rdi
0x1400202d0  mov     rcx, [rcx]
0x1400202d3  call    TmpAdjustVirtualClock
0x1400202d8  mov     rcx, rbx
0x1400202db  call    TmpAcquireTransactionMutex
0x1400202e0  lea     r15, [rsi+40h]
0x1400202e4  mov     [rsp+58h+Timeout], 0; Timeout
0x1400202ed  xor     r9d, r9d; Alertable
0x1400202f0  xor     r8d, r8d; WaitMode
0x1400202f3  xor     edx, edx; WaitReason
0x1400202f5  mov     rcx, r15; Object
0x1400202f8  call    cs:__imp_KeWaitForSingleObject
0x1400202ff  nop     dword ptr [rax+rax+00h]
0x140020304  mov     dil, 1
0x140020307  mov     [rsp+58h+var_27], dil
0x14002030c  xor     cl, cl
0x14002030e  mov     [rsp+58h+var_28], cl
0x140020312  mov     eax, [rsi+0ACh]
0x140020318  test    dil, al
0x14002031b  jz      short loc_14002034D
0x14002031d  mov     eax, [rbx+0C0h]
0x140020323  cmp     eax, 0Bh
0x140020326  ja      short loc_14002038C
0x140020328  mov     edx, 91Eh
0x14002032d  bt      edx, eax
0x140020330  jnb     short loc_14002038C
0x140020332  mov     cl, dil
0x140020335  mov     [rsp+58h+var_28], cl
0x140020339  mov     eax, [rbx+0C4h]
0x14002033f  test    al, al
0x140020341  js      short loc_14002038C
0x140020343  lock or dword ptr [rbx+0C4h], 40h
0x14002034b  jmp     short loc_14002038C
0x14002034d  mov     eax, [rsi+0A8h]
0x140020353  lea     edx, [rax-100h]
0x140020359  cmp     edx, 11h
0x14002035c  ja      short loc_140020373
0x14002035e  mov     r8d, 20503h
0x140020364  bt      r8d, edx
0x140020368  jnb     short loc_140020373
0x14002036a  mov     cl, dil
0x14002036d  mov     [rsp+58h+var_28], cl
0x140020371  jmp     short loc_14002038C
0x140020373  cmp     eax, 102h
0x140020378  jz      short loc_140020381
0x14002037a  cmp     eax, 105h
0x14002037f  jnz     short loc_14002038C
0x140020381  lock or dword ptr [rbx+0C4h], 8000000h
0x14002038c  test    cl, cl
0x14002038e  jz      short loc_14002040F
0x140020390  lea     rax, TmpInternalCrmNotification
0x140020397  cmp     [r14+128h], rax
0x14002039e  jz      short loc_1400203EA
0x1400203a0  lea     rax, WPP_GLOBAL_Control
0x1400203a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400203ae  cmp     rcx, rax
0x1400203b1  jz      short loc_1400203EA
0x1400203b3  mov     eax, [rcx+2Ch]
0x1400203b6  test    al, 8
0x1400203b8  jz      short loc_1400203EA
0x1400203ba  lea     rax, [r14+88h]
0x1400203c1  mov     r8, [rsi+0A0h]
0x1400203c8  add     r8, 0B0h
0x1400203cf  mov     edx, 0Ah
0x1400203d4  mov     [rsp+58h+var_30], rax
0x1400203d9  mov     [rsp+58h+Timeout], r8
0x1400203de  mov     r9, rbx
0x1400203e1  mov     rcx, [rcx+18h]
0x1400203e5  call    WPP_SF_q_guid__guid_
0x1400203ea  xor     edx, edx; Wait
0x1400203ec  mov     rcx, r15; Mutex
0x1400203ef  call    cs:__imp_KeReleaseMutex
0x1400203f6  nop     dword ptr [rax+rax+00h]
0x1400203fb  xor     dil, dil
0x1400203fe  mov     [rsp+58h+var_27], dil
0x140020403  mov     rcx, rbx
0x140020406  call    TmpTxActionDoRollback
0x14002040b  mov     esi, eax
0x14002040d  jmp     short loc_140020414
0x14002040f  mov     esi, 0C0190013h
0x140020414  test    dil, dil
0x140020417  jz      short loc_14002042A
0x140020419  xor     edx, edx; Wait
0x14002041b  mov     rcx, r15; Mutex
0x14002041e  call    cs:__imp_KeReleaseMutex
0x140020425  nop     dword ptr [rax+rax+00h]
0x14002042a  mov     rcx, [rbx+58h]
0x14002042e  add     rcx, 20h ; ' '; Mutex
0x140020432  xor     edx, edx; Wait
0x140020434  call    cs:__imp_KeReleaseMutex
0x14002043b  nop     dword ptr [rax+rax+00h]
0x140020440  mov     eax, esi
0x140020442  jmp     loc_1400202B3
0x1400219fe  push    rbp
0x140021a00  sub     rsp, 30h
0x140021a04  mov     rbp, rdx
0x140021a07  cmp     byte ptr [rbp+31h], 0
0x140021a0b  jz      short loc_140021A24
0x140021a0d  mov     rcx, [rbp+60h]
0x140021a11  add     rcx, 40h ; '@'; Mutex
0x140021a15  xor     edx, edx; Wait
0x140021a17  call    cs:__imp_KeReleaseMutex
0x140021a1e  nop     dword ptr [rax+rax+00h]
0x140021a23  nop
0x140021a24  mov     rax, [rbp+68h]
0x140021a28  mov     rcx, [rax+58h]
0x140021a2c  add     rcx, 20h ; ' '; Mutex
0x140021a30  xor     edx, edx; Wait
0x140021a32  call    cs:__imp_KeReleaseMutex
0x140021a39  nop     dword ptr [rax+rax+00h]
0x140021a3e  nop
0x140021a3f  add     rsp, 30h
0x140021a43  pop     rbp
0x140021a44  retn
```

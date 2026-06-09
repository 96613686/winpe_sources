# CompleteAllFunctionIdleIrps

- ea: `0x140008230`
- end: `0x1400083c0`
- name: `CompleteAllFunctionIdleIrps`
- size: `400`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005eb0`
- `0x140007170`
- `0x1400145e0`

## callees

- `0x1400054a0`
- `0x140008230`
- `0x1400083c8`
- `0x14000b4bc`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140008359`
- `ntoskrnl!IofCompleteRequest` at `0x140008359`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140008380`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140008380`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1400082b8`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1400082b8`

## pseudocode

```c
__int64 __fastcall CompleteAllFunctionIdleIrps(__int64 a1, int a2)
{
  int v2; // esi
  _DWORD *v4; // rcx
  __int64 v5; // rdi
  PIRP v6; // rax
  _LIST_ENTRY *v7; // rcx
  _LIST_ENTRY *p_ListEntry; // rax
  __int64 result; // rax
  __int64 v10; // rcx
  __int128 *v11; // rdx
  IRP *v12; // rdi
  __int128 v13; // [rsp+40h] [rbp-18h] BYREF

  v2 = a2;
  v13 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_q(
      *(_QWORD *)(a1 + 1368),
      a2,
      7,
      34,
      (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids,
      *(_QWORD *)(a1 + 32));
  }
  v4 = *(_DWORD **)(a1 + 128);
  *((_QWORD *)&v13 + 1) = &v13;
  *(_QWORD *)&v13 = &v13;
  if ( *v4 )
  {
    v5 = 0;
    do
    {
      v6 = IoCsqRemoveNextIrp(
             (PIO_CSQ)(*(_QWORD *)(*(_QWORD *)&v4[2 * v5 + 2] + 64LL) + 128LL),
             (PVOID)(*(_QWORD *)(*(_QWORD *)&v4[2 * v5 + 2] + 64LL) + 8LL));
      if ( v6 )
      {
        v7 = (_LIST_ENTRY *)*((_QWORD *)&v13 + 1);
        if ( **((__int128 ***)&v13 + 1) != &v13 )
          goto LABEL_15;
        p_ListEntry = &v6->Tail.Overlay.ListEntry;
        p_ListEntry->Flink = (_LIST_ENTRY *)&v13;
        p_ListEntry->Blink = v7;
        v7->Flink = p_ListEntry;
        *((_QWORD *)&v13 + 1) = p_ListEntry;
      }
      v4 = *(_DWORD **)(a1 + 128);
      v5 = (unsigned int)(v5 + 1);
    }
    while ( (unsigned int)v5 < *v4 );
  }
  while ( 1 )
  {
    result = v13;
    if ( (__int128 *)v13 == &v13 )
      break;
    if ( *(__int128 **)(v13 + 8) != &v13 || (v10 = *(_QWORD *)v13, *(_QWORD *)(*(_QWORD *)v13 + 8LL) != (_QWORD)v13) )
LABEL_15:
      __fastfail(3u);
    *(_QWORD *)&v13 = *(_QWORD *)v13;
    v11 = &v13;
    v12 = (IRP *)(result - 168);
    *(_QWORD *)(v10 + 8) = &v13;
    *(_DWORD *)(result - 168 + 48) = v2;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 4;
      WPP_RECORDER_SF_qD(
        *(_QWORD *)(a1 + 1368),
        (_DWORD)v11,
        7,
        35,
        (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids,
        result + 88,
        v2);
    }
    IofCompleteRequest(v12, 0);
    UsbcReleaseRemoveLock(a1, v12);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 200), v12, 0x20u);
  }
  return result;
}

```

## disassembly

```asm
0x140008230  push    rbp
0x140008232  push    rbx
0x140008233  push    rsi
0x140008234  push    rdi
0x140008235  push    r12
0x140008237  push    r14
0x140008239  mov     rbp, rsp
0x14000823c  sub     rsp, 58h
0x140008240  xorps   xmm0, xmm0
0x140008243  mov     esi, edx
0x140008245  movups  [rbp+var_18], xmm0
0x140008249  mov     rbx, rcx
0x14000824c  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140008253  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000825a  lea     r12, WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids
0x140008261  jz      short loc_140008289
0x140008263  mov     rax, [rcx+20h]
0x140008267  mov     r9d, 22h ; '"'
0x14000826d  mov     rcx, [rcx+558h]
0x140008274  mov     dl, 4
0x140008276  mov     [rsp+58h+var_30], rax
0x14000827b  mov     [rsp+58h+var_38], r12
0x140008280  lea     r8d, [r9-1Bh]
0x140008284  call    WPP_RECORDER_SF_q
0x140008289  mov     rcx, [rbx+80h]
0x140008290  lea     rax, [rbp+var_18]
0x140008294  mov     qword ptr [rbp+var_18+8], rax
0x140008298  lea     rax, [rbp+var_18]
0x14000829c  mov     qword ptr [rbp+var_18], rax
0x1400082a0  cmp     dword ptr [rcx], 0
0x1400082a3  jbe     short loc_1400082FF
0x1400082a5  xor     edi, edi
0x1400082a7  mov     rcx, [rcx+rdi*8+8]
0x1400082ac  mov     rdx, [rcx+40h]
0x1400082b0  add     rdx, 8; PeekContext
0x1400082b4  lea     rcx, [rdx+78h]; Csq
0x1400082b8  call    cs:__imp_IoCsqRemoveNextIrp
0x1400082bf  nop     dword ptr [rax+rax+00h]
0x1400082c4  test    rax, rax
0x1400082c7  jz      short loc_1400082F2
0x1400082c9  mov     rcx, qword ptr [rbp+var_18+8]
0x1400082cd  lea     rdx, [rbp+var_18]
0x1400082d1  cmp     [rcx], rdx
0x1400082d4  jnz     loc_1400083B9
0x1400082da  add     rax, 0A8h
0x1400082e0  lea     rdx, [rbp+var_18]
0x1400082e4  mov     [rax], rdx
0x1400082e7  mov     [rax+8], rcx
0x1400082eb  mov     [rcx], rax
0x1400082ee  mov     qword ptr [rbp+var_18+8], rax
0x1400082f2  mov     rcx, [rbx+80h]
0x1400082f9  inc     edi
0x1400082fb  cmp     edi, [rcx]
0x1400082fd  jb      short loc_1400082A7
0x1400082ff  mov     rax, qword ptr [rbp+var_18]
0x140008303  lea     rcx, [rbp+var_18]
0x140008307  cmp     rax, rcx
0x14000830a  jnz     short loc_14000831A
0x14000830c  add     rsp, 58h
0x140008310  pop     r14
0x140008312  pop     r12
0x140008314  pop     rdi
0x140008315  pop     rsi
0x140008316  pop     rbx
0x140008317  pop     rbp
0x140008318  retn
0x14000831a  lea     rcx, [rbp+var_18]
0x14000831e  cmp     [rax+8], rcx
0x140008322  jnz     loc_1400083B9
0x140008328  mov     rcx, [rax]
0x14000832b  cmp     [rcx+8], rax
0x14000832f  jnz     loc_1400083B9
0x140008335  mov     qword ptr [rbp+var_18], rcx
0x140008339  lea     rdx, [rbp+var_18]
0x14000833d  lea     rdi, [rax-0A8h]
0x140008344  mov     [rcx+8], rdx
0x140008348  mov     [rdi+30h], esi
0x14000834b  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140008352  jnz     short loc_140008391
0x140008354  xor     edx, edx; PriorityBoost
0x140008356  mov     rcx, rdi; Irp
0x140008359  call    cs:__imp_IofCompleteRequest
0x140008360  nop     dword ptr [rax+rax+00h]
0x140008365  mov     rdx, rdi
0x140008368  mov     rcx, rbx
0x14000836b  call    UsbcReleaseRemoveLock
0x140008370  lea     rcx, [rbx+0C8h]; RemoveLock
0x140008377  mov     r8d, 20h ; ' '; RemlockSize
0x14000837d  mov     rdx, rdi; Tag
0x140008380  call    cs:__imp_IoReleaseRemoveLockEx
0x140008387  nop     dword ptr [rax+rax+00h]
0x14000838c  jmp     loc_1400082FF
0x140008391  mov     rcx, [rbx+558h]
0x140008398  mov     r9d, 23h ; '#'
0x14000839e  mov     [rsp+58h+var_28], esi
0x1400083a2  mov     dl, 4
0x1400083a4  mov     [rsp+58h+var_30], rdi
0x1400083a9  mov     [rsp+58h+var_38], r12
0x1400083ae  lea     r8d, [r9-1Ch]
0x1400083b2  call    WPP_RECORDER_SF_qD
0x1400083b7  jmp     short loc_140008354
0x1400083b9  mov     ecx, 3
0x1400083be  int     29h; Win8: RtlFailFast(ecx)
```

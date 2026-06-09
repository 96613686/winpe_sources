# SecMgrSuccessEntryAction(PORT_EVENT *,ulong *)

- ea: `0x180025390`
- end: `0x180025695`
- name: `?SecMgrSuccessEntryAction@@YAKPEAUPORT_EVENT@@PEAK@Z`
- size: `773`
- prototype: `unsigned int __fastcall(struct PORT_EVENT *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000892c`
- `0x180008998`
- `0x1800169c0`
- `0x180025390`
- `0x18002569c`
- `0x180055a38`
- `0x180096010`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800254e6`
- `MobileNetworking!ReleaseWriteLock` at `0x180025524`
- `MobileNetworking!ReleaseWriteLock` at `0x1800254e6`
- `MobileNetworking!ReleaseWriteLock` at `0x180025524`
- `MobileNetworking!AcquireWriteLock` at `0x180025416`
- `MobileNetworking!AcquireWriteLock` at `0x1800254a2`
- `MobileNetworking!AcquireWriteLock` at `0x180025416`
- `MobileNetworking!AcquireWriteLock` at `0x1800254a2`

## pseudocode

```c
__int64 __fastcall SecMgrSuccessEntryAction(struct PORT_EVENT *a1, unsigned int *a2, int a3)
{
  __int64 v4; // rbx
  void *v5; // rdi
  void *v6; // rsi
  unsigned int (*v7)(void *, void *, unsigned __int8 (*)[6], unsigned int, unsigned int); // rbp
  unsigned int v8; // edi
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d
  __int64 v12; // r9

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 60, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids);
  v4 = *((_QWORD *)a1 + 3);
  v5 = *(void **)(v4 + 32);
  v6 = *(void **)(v4 + 424);
  v7 = *(unsigned int (**)(void *, void *, unsigned __int8 (*)[6], unsigned int, unsigned int))(v4 + 96);
  *(_DWORD *)(v4 + 500) = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_Ls(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      11,
      a3,
      *(_DWORD *)(*(_QWORD *)(v4 + 24) + 2496LL),
      (__int64)">>> Locking >>>");
  AcquireWriteLock(*(_QWORD *)(v4 + 24), *(_QWORD *)(v4 + 24) + 2512LL, "SecMgrSuccessEntryAction", 663);
  v8 = MSMIndicateSecurityResult(
         *(_DWORD *)(v4 + 312),
         v5,
         v6,
         (unsigned __int8 (*)[6])(v4 + 302),
         0,
         0,
         *(_DWORD *)(*(_QWORD *)(v4 + 24) + 2800LL),
         *(void **)(v4 + 24),
         *(void **)(*(_QWORD *)(v4 + 24) + 2624LL),
         *(void **)(v4 + 424),
         v7);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, v9, *(_DWORD *)(v4 + 312), (__int64)">>> Locking >>>");
  AcquireWriteLock(v4, v4 + 320, "SecMgrSuccessEntryAction", 681);
  if ( *(_DWORD *)(v4 + 2024)
    && !(*(unsigned int (__fastcall **)(__int64, _QWORD, __int64))(v4 + 288))(*(_QWORD *)(v4 + 24) + 32LL, 0, 1000) )
  {
    *(_DWORD *)(v4 + 2024) = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, v10, *(_DWORD *)(v4 + 312), (__int64)"<<< Unlocking <<<");
  ReleaseWriteLock(v4, v4 + 320, "SecMgrSuccessEntryAction", 696);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 61, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids, v8);
    TraceAdapterId(*(_DWORD *)(*(_QWORD *)(v4 + 24) + 2496LL), "<<< Unlocking <<<");
    v12 = 717;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
      WPP_SF_Ls(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        11,
        v11,
        *(_DWORD *)(*(_QWORD *)(v4 + 24) + 2496LL),
        (__int64)"<<< Unlocking <<<");
    v12 = 711;
  }
  ReleaseWriteLock(*(_QWORD *)(v4 + 24), *(_QWORD *)(v4 + 24) + 2512LL, "SecMgrSuccessEntryAction", v12);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 62, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180025390  push    rbx
0x180025392  push    rbp
0x180025393  push    rsi
0x180025394  push    rdi
0x180025395  push    r12
0x180025397  push    r13
0x180025399  push    r14
0x18002539b  push    r15
0x18002539d  sub     rsp, 68h
0x1800253a1  mov     rbx, rcx
0x1800253a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800253ab  lea     r14, WPP_GLOBAL_Control
0x1800253b2  mov     r15d, 100h
0x1800253b8  cmp     rcx, r14
0x1800253bb  jnz     loc_18002555A
0x1800253c1  mov     rbx, [rbx+18h]
0x1800253c5  mov     rdi, [rbx+20h]
0x1800253c9  mov     rsi, [rbx+1A8h]
0x1800253d0  mov     rbp, [rbx+60h]
0x1800253d4  mov     dword ptr [rbx+1F4h], 1
0x1800253de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800253e5  lea     r12, aLocking; ">>> Locking >>>"
0x1800253ec  cmp     rcx, r14
0x1800253ef  jz      short loc_1800253FB
0x1800253f1  test    [rcx+44h], r15d
0x1800253f5  jnz     loc_18002557E
0x1800253fb  mov     rcx, [rbx+18h]
0x1800253ff  lea     r13, aSecmgrsuccesse_0; "SecMgrSuccessEntryAction"
0x180025406  mov     r9d, 297h
0x18002540c  mov     r8, r13
0x18002540f  lea     rdx, [rcx+9D0h]
0x180025416  call    cs:__imp_AcquireWriteLock
0x18002541d  nop     dword ptr [rax+rax+00h]
0x180025422  mov     rcx, [rbx+18h]
0x180025426  lea     r9, [rbx+12Eh]; unsigned __int8 (*)[6]
0x18002542d  mov     rax, [rbx+1A8h]
0x180025434  mov     r8, rsi; void *
0x180025437  mov     [rsp+0A8h+var_58], rbp; unsigned int (*)(void *, void *, unsigned __int8 (*)[6], unsigned int, unsigned int)
0x18002543c  mov     rdx, rdi; void *
0x18002543f  mov     [rsp+0A8h+var_60], rax; void *
0x180025444  xor     ebp, ebp
0x180025446  mov     rax, [rcx+0A40h]
0x18002544d  mov     [rsp+0A8h+var_68], rax; void *
0x180025452  mov     eax, [rcx+0AF0h]
0x180025458  mov     [rsp+0A8h+var_70], rcx; void *
0x18002545d  mov     ecx, [rbx+138h]; unsigned int
0x180025463  mov     [rsp+0A8h+var_78], eax; int
0x180025467  mov     [rsp+0A8h+var_80], ebp; unsigned int
0x18002546b  mov     [rsp+0A8h+var_88], ebp; unsigned int
0x18002546f  call    ?MSMIndicateSecurityResult@@YAKKPEAX0PEAY05EKKH000P6AK001KK@Z@Z; MSMIndicateSecurityResult(ulong,void *,void *,uchar (*)[6],ulong,ulong,int,void *,void *,void *,ulong (*)(void *,void *,uchar (*)[6],ulong,ulong))
0x180025474  mov     edi, eax
0x180025476  mov     rcx, cs:WPP_GLOBAL_Control
0x18002547d  cmp     rcx, r14
0x180025480  jz      short loc_18002548C
0x180025482  test    [rcx+44h], r15d
0x180025486  jnz     loc_1800255A1
0x18002548c  lea     rsi, [rbx+140h]
0x180025493  mov     r9d, 2A9h
0x180025499  mov     rdx, rsi
0x18002549c  mov     r8, r13
0x18002549f  mov     rcx, rbx
0x1800254a2  call    cs:__imp_AcquireWriteLock
0x1800254a9  nop     dword ptr [rax+rax+00h]
0x1800254ae  cmp     [rbx+7E8h], ebp
0x1800254b4  jnz     loc_1800255C0
0x1800254ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254c1  lea     r12, aUnlocking; "<<< Unlocking <<<"
0x1800254c8  cmp     rcx, r14
0x1800254cb  jz      short loc_1800254D7
0x1800254cd  test    [rcx+44h], r15d
0x1800254d1  jnz     loc_1800255EF
0x1800254d7  mov     r9d, 2B8h
0x1800254dd  mov     r8, r13
0x1800254e0  mov     rdx, rsi
0x1800254e3  mov     rcx, rbx
0x1800254e6  call    cs:__imp_ReleaseWriteLock
0x1800254ed  nop     dword ptr [rax+rax+00h]
0x1800254f2  test    edi, edi
0x1800254f4  jnz     loc_18002560E
0x1800254fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180025501  cmp     rcx, r14
0x180025504  jz      short loc_180025510
0x180025506  test    [rcx+44h], r15d
0x18002550a  jnz     loc_180025655
0x180025510  mov     r9d, 2C7h
0x180025516  mov     rcx, [rbx+18h]
0x18002551a  mov     r8, r13
0x18002551d  lea     rdx, [rcx+9D0h]
0x180025524  call    cs:__imp_ReleaseWriteLock
0x18002552b  nop     dword ptr [rax+rax+00h]
0x180025530  mov     rcx, cs:WPP_GLOBAL_Control
0x180025537  cmp     rcx, r14
0x18002553a  jz      short loc_180025546
0x18002553c  test    [rcx+44h], r15d
0x180025540  jnz     loc_180025678
0x180025546  mov     eax, edi
0x180025548  add     rsp, 68h
0x18002554c  pop     r15
0x18002554e  pop     r14
0x180025550  pop     r13
0x180025552  pop     r12
0x180025554  pop     rdi
0x180025555  pop     rsi
0x180025556  pop     rbp
0x180025557  pop     rbx
0x180025558  retn
0x18002555a  test    [rcx+44h], r15d
0x18002555e  jz      loc_1800253C1
0x180025564  mov     rcx, [rcx+38h]
0x180025568  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x18002556f  mov     edx, 3Ch ; '<'
0x180025574  call    WPP_SF_
0x180025579  jmp     loc_1800253C1
0x18002557e  mov     r9, [rbx+18h]
0x180025582  mov     edx, 0Bh
0x180025587  mov     rcx, [rcx+38h]
0x18002558b  mov     qword ptr [rsp+0A8h+var_88], r12
0x180025590  mov     r9d, [r9+9C0h]
0x180025597  call    WPP_SF_Ls
0x18002559c  jmp     loc_1800253FB
0x1800255a1  mov     r9d, [rbx+138h]
0x1800255a8  mov     edx, 0Ch
0x1800255ad  mov     rcx, [rcx+38h]
0x1800255b1  mov     qword ptr [rsp+0A8h+var_88], r12
0x1800255b6  call    WPP_SF_Ls
0x1800255bb  jmp     loc_18002548C
0x1800255c0  mov     rcx, [rbx+18h]
0x1800255c4  xor     edx, edx
0x1800255c6  mov     rax, [rbx+120h]
0x1800255cd  add     rcx, 20h ; ' '
0x1800255d1  mov     r8d, 3E8h
0x1800255d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255dc  test    eax, eax
0x1800255de  jnz     loc_1800254BA
0x1800255e4  mov     [rbx+7E8h], ebp
0x1800255ea  jmp     loc_1800254BA
0x1800255ef  mov     r9d, [rbx+138h]
0x1800255f6  mov     edx, 0Ch
0x1800255fb  mov     rcx, [rcx+38h]
0x1800255ff  mov     qword ptr [rsp+0A8h+var_88], r12
0x180025604  call    WPP_SF_Ls
0x180025609  jmp     loc_1800254D7
0x18002560e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025615  cmp     rcx, r14
0x180025618  jz      short loc_180025638
0x18002561a  test    byte ptr [rcx+44h], 1
0x18002561e  jz      short loc_180025638
0x180025620  mov     rcx, [rcx+38h]
0x180025624  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x18002562b  mov     edx, 3Dh ; '='
0x180025630  mov     r9d, edi
0x180025633  call    WPP_SF_d
0x180025638  mov     rcx, [rbx+18h]
0x18002563c  mov     rdx, r12; char *
0x18002563f  mov     ecx, [rcx+9C0h]; unsigned int
0x180025645  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18002564a  mov     r9d, 2CDh
0x180025650  jmp     loc_180025516
0x180025655  mov     r9, [rbx+18h]
0x180025659  mov     edx, 0Bh
0x18002565e  mov     rcx, [rcx+38h]
0x180025662  mov     qword ptr [rsp+0A8h+var_88], r12
0x180025667  mov     r9d, [r9+9C0h]
0x18002566e  call    WPP_SF_Ls
0x180025673  jmp     loc_180025510
0x180025678  mov     rcx, [rcx+38h]
0x18002567c  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x180025683  mov     edx, 3Eh ; '>'
0x180025688  mov     r9d, edi
0x18002568b  call    WPP_SF_d
0x180025690  jmp     loc_180025546
```

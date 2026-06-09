# SecMgrFailureEntryAction(PORT_EVENT *,ulong *)

- ea: `0x180062970`
- end: `0x180062c2c`
- name: `?SecMgrFailureEntryAction@@YAKPEAUPORT_EVENT@@PEAK@Z`
- size: `700`
- prototype: `unsigned int __fastcall(struct PORT_EVENT *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000892c`
- `0x180008998`
- `0x1800169c0`
- `0x18001f2dc`
- `0x18002569c`
- `0x18002bb08`
- `0x180062970`
- `0x180096010`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180062b6d`
- `MobileNetworking!ReleaseWriteLock` at `0x180062be1`
- `MobileNetworking!ReleaseWriteLock` at `0x180062b6d`
- `MobileNetworking!ReleaseWriteLock` at `0x180062be1`
- `MobileNetworking!AcquireWriteLock` at `0x180062a86`
- `MobileNetworking!AcquireWriteLock` at `0x180062b11`
- `MobileNetworking!AcquireWriteLock` at `0x180062a86`
- `MobileNetworking!AcquireWriteLock` at `0x180062b11`

## pseudocode

```c
__int64 __fastcall SecMgrFailureEntryAction(struct PORT_EVENT *a1, unsigned int *a2)
{
  unsigned int v3; // ebp
  __int64 v4; // rbx
  void *v5; // r14
  void *v6; // r15
  unsigned int (*v7)(void *, void *, unsigned __int8 (*)[6], unsigned int, unsigned int); // r12
  int v8; // ecx
  unsigned int v9; // esi
  __int64 v10; // rcx
  unsigned int v11; // edi

  v3 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 65, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids);
  v4 = *((_QWORD *)a1 + 3);
  v5 = *(void **)(v4 + 32);
  v6 = *(void **)(v4 + 424);
  v7 = *(unsigned int (**)(void *, void *, unsigned __int8 (*)[6], unsigned int, unsigned int))(v4 + 96);
  *(_DWORD *)(v4 + 500) = 0;
  switch ( *((_DWORD *)a1 + 4) )
  {
    case 0x1E:
      v3 = *((_DWORD *)a1 + 16);
      goto LABEL_14;
    case 0x1F:
      v9 = 294916;
      goto LABEL_15;
    case 0x22:
LABEL_14:
      v9 = *((_DWORD *)a1 + 12);
      goto LABEL_15;
  }
  v8 = (int)WPP_GLOBAL_Control;
  v9 = 327679;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      66,
      WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids,
      *((unsigned int *)a1 + 4));
  if ( (byte_1800AED45 & 2) != 0 )
    McTemplateU0qqq_EventWriteTransfer(v8, (unsigned int)MsmSecUnknownFailureTransition, 5023, 807, *((_DWORD *)a1 + 4));
LABEL_15:
  v10 = *(_QWORD *)(v4 + 24);
  *(_DWORD *)(v4 + 480) = v9;
  *(_DWORD *)(v4 + 484) = v3;
  TraceAdapterId(*(_DWORD *)(v10 + 2496), ">>> Locking >>>");
  AcquireWriteLock(*(_QWORD *)(v4 + 24), *(_QWORD *)(v4 + 24) + 2512LL, "SecMgrFailureEntryAction", 814);
  v11 = MSMIndicateSecurityResult(
          *(_DWORD *)(v4 + 312),
          v5,
          v6,
          (unsigned __int8 (*)[6])(v4 + 302),
          v9,
          v3,
          0,
          *(void **)(v4 + 24),
          *(void **)(*(_QWORD *)(v4 + 24) + 2624LL),
          *(void **)(v4 + 424),
          v7);
  TracePortId(*(_DWORD *)(v4 + 312), ">>> Locking >>>");
  AcquireWriteLock(v4, v4 + 320, "SecMgrFailureEntryAction", 834);
  if ( *(_DWORD *)(v4 + 2024)
    && !(*(unsigned int (__fastcall **)(__int64, _QWORD, __int64))(v4 + 288))(*(_QWORD *)(v4 + 24) + 32LL, 0, 5000) )
  {
    *(_DWORD *)(v4 + 2024) = 0;
  }
  TracePortId(*(_DWORD *)(v4 + 312), "<<< Unlocking <<<");
  ReleaseWriteLock(v4, v4 + 320, "SecMgrFailureEntryAction", 849);
  if ( v11 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 67, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids, v11);
  TraceAdapterId(*(_DWORD *)(*(_QWORD *)(v4 + 24) + 2496LL), "<<< Unlocking <<<");
  ReleaseWriteLock(*(_QWORD *)(v4 + 24), *(_QWORD *)(v4 + 24) + 2512LL, "SecMgrFailureEntryAction", 863);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 68, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180062970  push    rbx
0x180062972  push    rbp
0x180062973  push    rsi
0x180062974  push    rdi
0x180062975  push    r12
0x180062977  push    r14
0x180062979  push    r15
0x18006297b  sub     rsp, 60h
0x18006297f  mov     rdi, rcx
0x180062982  xor     ebp, ebp
0x180062984  mov     rcx, cs:WPP_GLOBAL_Control
0x18006298b  lea     rdx, WPP_GLOBAL_Control
0x180062992  cmp     rcx, rdx
0x180062995  jz      short loc_1800629BA
0x180062997  test    dword ptr [rcx+44h], 100h
0x18006299e  jz      short loc_1800629BA
0x1800629a0  mov     rcx, [rcx+38h]
0x1800629a4  lea     edx, [rbp+41h]
0x1800629a7  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x1800629ae  call    WPP_SF_
0x1800629b3  lea     rdx, WPP_GLOBAL_Control
0x1800629ba  mov     rbx, [rdi+18h]
0x1800629be  mov     r14, [rbx+20h]
0x1800629c2  mov     r15, [rbx+1A8h]
0x1800629c9  mov     r12, [rbx+60h]
0x1800629cd  mov     [rbx+1F4h], ebp
0x1800629d3  mov     r9d, [rdi+10h]
0x1800629d7  mov     ecx, r9d
0x1800629da  sub     ecx, 1Eh
0x1800629dd  jz      short loc_180062A46
0x1800629df  sub     ecx, 1
0x1800629e2  jz      short loc_180062A3F
0x1800629e4  cmp     ecx, 3
0x1800629e7  jz      short loc_180062A49
0x1800629e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800629f0  mov     esi, 4FFFFh
0x1800629f5  cmp     rcx, rdx
0x1800629f8  jz      short loc_180062A15
0x1800629fa  test    byte ptr [rcx+44h], 1
0x1800629fe  jz      short loc_180062A15
0x180062a00  mov     rcx, [rcx+38h]
0x180062a04  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x180062a0b  mov     edx, 42h ; 'B'
0x180062a10  call    WPP_SF_d
0x180062a15  test    cs:byte_1800AED45, 2
0x180062a1c  jz      short loc_180062A4C
0x180062a1e  mov     eax, [rdi+10h]
0x180062a21  lea     rdx, MsmSecUnknownFailureTransition
0x180062a28  mov     r9d, 327h
0x180062a2e  mov     [rsp+98h+var_78], eax
0x180062a32  mov     r8d, 139Fh
0x180062a38  call    McTemplateU0qqq_EventWriteTransfer
0x180062a3d  jmp     short loc_180062A4C
0x180062a3f  mov     esi, 48004h
0x180062a44  jmp     short loc_180062A4C
0x180062a46  mov     ebp, [rdi+40h]
0x180062a49  mov     esi, [rdi+30h]
0x180062a4c  mov     rcx, [rbx+18h]
0x180062a50  lea     rdx, aLocking; ">>> Locking >>>"
0x180062a57  mov     [rbx+1E0h], esi
0x180062a5d  mov     [rbx+1E4h], ebp
0x180062a63  mov     ecx, [rcx+9C0h]; unsigned int
0x180062a69  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180062a6e  mov     rcx, [rbx+18h]
0x180062a72  lea     r8, aSecmgrfailuree; "SecMgrFailureEntryAction"
0x180062a79  mov     r9d, 32Eh
0x180062a7f  lea     rdx, [rcx+9D0h]
0x180062a86  call    cs:__imp_AcquireWriteLock
0x180062a8d  nop     dword ptr [rax+rax+00h]
0x180062a92  mov     rcx, [rbx+18h]
0x180062a96  lea     r9, [rbx+12Eh]; unsigned __int8 (*)[6]
0x180062a9d  mov     rax, [rbx+1A8h]
0x180062aa4  mov     r8, r15; void *
0x180062aa7  mov     [rsp+98h+var_48], r12; unsigned int (*)(void *, void *, unsigned __int8 (*)[6], unsigned int, unsigned int)
0x180062aac  mov     rdx, r14; void *
0x180062aaf  mov     [rsp+98h+var_50], rax; void *
0x180062ab4  mov     rax, [rcx+0A40h]
0x180062abb  mov     [rsp+98h+var_58], rax; void *
0x180062ac0  mov     [rsp+98h+var_60], rcx; void *
0x180062ac5  mov     ecx, [rbx+138h]; unsigned int
0x180062acb  mov     [rsp+98h+var_68], 0; int
0x180062ad3  mov     [rsp+98h+var_70], ebp; unsigned int
0x180062ad7  mov     [rsp+98h+var_78], esi; unsigned int
0x180062adb  call    ?MSMIndicateSecurityResult@@YAKKPEAX0PEAY05EKKH000P6AK001KK@Z@Z; MSMIndicateSecurityResult(ulong,void *,void *,uchar (*)[6],ulong,ulong,int,void *,void *,void *,ulong (*)(void *,void *,uchar (*)[6],ulong,ulong))
0x180062ae0  mov     ecx, [rbx+138h]; unsigned int
0x180062ae6  lea     rdx, aLocking; ">>> Locking >>>"
0x180062aed  mov     edi, eax
0x180062aef  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180062af4  lea     rsi, [rbx+140h]
0x180062afb  mov     r9d, 342h
0x180062b01  lea     rbp, aSecmgrfailuree; "SecMgrFailureEntryAction"
0x180062b08  mov     rdx, rsi
0x180062b0b  mov     r8, rbp
0x180062b0e  mov     rcx, rbx
0x180062b11  call    cs:__imp_AcquireWriteLock
0x180062b18  nop     dword ptr [rax+rax+00h]
0x180062b1d  cmp     dword ptr [rbx+7E8h], 0
0x180062b24  jz      short loc_180062B4C
0x180062b26  mov     rcx, [rbx+18h]
0x180062b2a  xor     edx, edx
0x180062b2c  mov     rax, [rbx+120h]
0x180062b33  add     rcx, 20h ; ' '
0x180062b37  mov     r8d, 1388h
0x180062b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b42  test    eax, eax
0x180062b44  jnz     short loc_180062B4C
0x180062b46  mov     [rbx+7E8h], eax
0x180062b4c  mov     ecx, [rbx+138h]; unsigned int
0x180062b52  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180062b59  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180062b5e  mov     r9d, 351h
0x180062b64  mov     r8, rbp
0x180062b67  mov     rdx, rsi
0x180062b6a  mov     rcx, rbx
0x180062b6d  call    cs:__imp_ReleaseWriteLock
0x180062b74  nop     dword ptr [rax+rax+00h]
0x180062b79  test    edi, edi
0x180062b7b  jz      short loc_180062BB0
0x180062b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180062b84  lea     rsi, WPP_GLOBAL_Control
0x180062b8b  cmp     rcx, rsi
0x180062b8e  jz      short loc_180062BB7
0x180062b90  test    byte ptr [rcx+44h], 1
0x180062b94  jz      short loc_180062BB7
0x180062b96  mov     rcx, [rcx+38h]
0x180062b9a  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x180062ba1  mov     edx, 43h ; 'C'
0x180062ba6  mov     r9d, edi
0x180062ba9  call    WPP_SF_d
0x180062bae  jmp     short loc_180062BB7
0x180062bb0  lea     rsi, WPP_GLOBAL_Control
0x180062bb7  mov     rcx, [rbx+18h]
0x180062bbb  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180062bc2  mov     ecx, [rcx+9C0h]; unsigned int
0x180062bc8  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180062bcd  mov     rcx, [rbx+18h]
0x180062bd1  mov     r9d, 35Fh
0x180062bd7  mov     r8, rbp
0x180062bda  lea     rdx, [rcx+9D0h]
0x180062be1  call    cs:__imp_ReleaseWriteLock
0x180062be8  nop     dword ptr [rax+rax+00h]
0x180062bed  mov     rcx, cs:WPP_GLOBAL_Control
0x180062bf4  cmp     rcx, rsi
0x180062bf7  jz      short loc_180062C1A
0x180062bf9  test    dword ptr [rcx+44h], 100h
0x180062c00  jz      short loc_180062C1A
0x180062c02  mov     rcx, [rcx+38h]
0x180062c06  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x180062c0d  mov     edx, 44h ; 'D'
0x180062c12  mov     r9d, edi
0x180062c15  call    WPP_SF_d
0x180062c1a  mov     eax, edi
0x180062c1c  add     rsp, 60h
0x180062c20  pop     r15
0x180062c22  pop     r14
0x180062c24  pop     r12
0x180062c26  pop     rdi
0x180062c27  pop     rsi
0x180062c28  pop     rbp
0x180062c29  pop     rbx
0x180062c2a  retn
```

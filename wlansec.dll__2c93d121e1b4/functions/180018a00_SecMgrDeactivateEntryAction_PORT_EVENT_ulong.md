# SecMgrDeactivateEntryAction(PORT_EVENT *,ulong *)

- ea: `0x180018a00`
- end: `0x180018c76`
- name: `?SecMgrDeactivateEntryAction@@YAKPEAUPORT_EVENT@@PEAK@Z`
- size: `630`
- prototype: `unsigned int __fastcall(struct PORT_EVENT *, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000c444`
- `0x180016e28`
- `0x180018a00`
- `0x180018c7c`
- `0x18001a23c`
- `0x180034398`
- `0x1800418c0`
- `0x180055a38`
- `0x180096010`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180018aa1`
- `MobileNetworking!ReleaseWriteLock` at `0x180018aa1`
- `MobileNetworking!AcquireWriteLock` at `0x180018a5f`
- `MobileNetworking!AcquireWriteLock` at `0x180018a5f`

## pseudocode

```c
__int64 __fastcall SecMgrDeactivateEntryAction(struct PORT_EVENT *a1, unsigned int *a2, int a3)
{
  PVOID *v4; // rcx
  __int64 v5; // rbx
  int v6; // r8d
  PVOID *v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  PVOID *v10; // rcx

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 71, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = *((_QWORD *)a1 + 3);
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x100) != 0 )
    WPP_SF_Ls((unsigned int)v4[7], 12, a3, *(_DWORD *)(v5 + 312), (__int64)">>> Locking >>>");
  AcquireWriteLock(v5, v5 + 320, "SecMgrDeactivateEntryAction", 907);
  if ( !*(_DWORD *)(v5 + 2024) )
    goto LABEL_6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 72, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids);
  if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, __int64))(v5 + 288))(*(_QWORD *)(v5 + 24) + 32LL, 0, 100) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        73,
        WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids,
        *(unsigned int *)(v5 + 2024));
    --*(_DWORD *)(v5 + 2024);
    goto LABEL_6;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_10;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 74, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids);
LABEL_6:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x100) != 0 )
    WPP_SF_Ls((unsigned int)v7[7], 12, v6, *(_DWORD *)(v5 + 312), (__int64)"<<< Unlocking <<<");
LABEL_10:
  ReleaseWriteLock(v5, v5 + 320, "SecMgrDeactivateEntryAction", 928);
  if ( (unsigned int)IntfIsInAPMode(*(struct MSMSEC_INTF_CONTEXT **)(v5 + 24)) )
    WpsAuthMgrDeactivate((struct MSMSEC_PORT_CONTEXT *)v5);
  else
    AuthMgrDeactivate((struct MSMSEC_PORT_CONTEXT *)v5);
  KeyMgrDeactivate((struct MSMSEC_PORT_CONTEXT *)v5);
  FlushKeyCache((struct MSMSEC_EAPOL_KEY_CACHE *)(v5 + 776));
  v8 = CreateAndQueuePortEvent(v5, 24, 0);
  v9 = v8;
  if ( !v8 )
    goto LABEL_13;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 75, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids, v8);
LABEL_13:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x100) != 0 )
    WPP_SF_d(v10[7], 76, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180018a00  push    rbx
0x180018a02  push    rbp
0x180018a03  push    rsi
0x180018a04  push    rdi
0x180018a05  push    r14
0x180018a07  sub     rsp, 30h
0x180018a0b  mov     rbx, rcx
0x180018a0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a15  lea     rsi, WPP_GLOBAL_Control
0x180018a1c  lea     rbp, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x180018a23  mov     r14d, 100h
0x180018a29  cmp     rcx, rsi
0x180018a2c  jnz     loc_180018B10
0x180018a32  mov     rbx, [rbx+18h]
0x180018a36  cmp     rcx, rsi
0x180018a39  jz      short loc_180018A45
0x180018a3b  test    [rcx+44h], r14d
0x180018a3f  jnz     loc_180018B53
0x180018a45  lea     rdi, [rbx+140h]
0x180018a4c  mov     r9d, 38Bh
0x180018a52  mov     rdx, rdi
0x180018a55  lea     r8, aSecmgrdeactiva; "SecMgrDeactivateEntryAction"
0x180018a5c  mov     rcx, rbx
0x180018a5f  call    cs:__imp_AcquireWriteLock
0x180018a66  nop     dword ptr [rax+rax+00h]
0x180018a6b  cmp     dword ptr [rbx+7E8h], 0
0x180018a72  jnz     loc_180018B79
0x180018a78  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a7f  cmp     rcx, rsi
0x180018a82  jz      short loc_180018A8E
0x180018a84  test    [rcx+44h], r14d
0x180018a88  jnz     loc_180018C1D
0x180018a8e  mov     r9d, 3A0h
0x180018a94  lea     r8, aSecmgrdeactiva; "SecMgrDeactivateEntryAction"
0x180018a9b  mov     rdx, rdi
0x180018a9e  mov     rcx, rbx
0x180018aa1  call    cs:__imp_ReleaseWriteLock
0x180018aa8  nop     dword ptr [rax+rax+00h]
0x180018aad  mov     rcx, [rbx+18h]; struct MSMSEC_INTF_CONTEXT *
0x180018ab1  call    ?IntfIsInAPMode@@YAHPEAUMSMSEC_INTF_CONTEXT@@@Z; IntfIsInAPMode(MSMSEC_INTF_CONTEXT *)
0x180018ab6  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x180018ab9  test    eax, eax
0x180018abb  jnz     short loc_180018B09
0x180018abd  call    ?AuthMgrDeactivate@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; AuthMgrDeactivate(MSMSEC_PORT_CONTEXT *)
0x180018ac2  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x180018ac5  call    ?KeyMgrDeactivate@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; KeyMgrDeactivate(MSMSEC_PORT_CONTEXT *)
0x180018aca  lea     rcx, [rbx+308h]; struct MSMSEC_EAPOL_KEY_CACHE *
0x180018ad1  call    ?FlushKeyCache@@YAXPEAUMSMSEC_EAPOL_KEY_CACHE@@@Z; FlushKeyCache(MSMSEC_EAPOL_KEY_CACHE *)
0x180018ad6  xor     r8d, r8d
0x180018ad9  mov     rcx, rbx
0x180018adc  lea     edx, [r8+18h]
0x180018ae0  call    ?CreateAndQueuePortEvent@@YAKPEAUMSMSEC_PORT_CONTEXT@@W4MSMSEC_PORT_EVENT_TYPE@@H@Z; CreateAndQueuePortEvent(MSMSEC_PORT_CONTEXT *,MSMSEC_PORT_EVENT_TYPE,int)
0x180018ae5  mov     ebx, eax
0x180018ae7  test    eax, eax
0x180018ae9  jnz     loc_180018C43
0x180018aef  mov     rcx, cs:WPP_GLOBAL_Control
0x180018af6  cmp     rcx, rsi
0x180018af9  jnz     short loc_180018B37
0x180018afb  mov     eax, ebx
0x180018afd  add     rsp, 30h
0x180018b01  pop     r14
0x180018b03  pop     rdi
0x180018b04  pop     rsi
0x180018b05  pop     rbp
0x180018b06  pop     rbx
0x180018b07  retn
0x180018b09  call    ?WpsAuthMgrDeactivate@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; WpsAuthMgrDeactivate(MSMSEC_PORT_CONTEXT *)
0x180018b0e  jmp     short loc_180018AC2
0x180018b10  test    [rcx+44h], r14d
0x180018b14  jz      loc_180018A32
0x180018b1a  mov     rcx, [rcx+38h]
0x180018b1e  mov     edx, 47h ; 'G'
0x180018b23  mov     r8, rbp
0x180018b26  call    WPP_SF_
0x180018b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b32  jmp     loc_180018A32
0x180018b37  test    [rcx+44h], r14d
0x180018b3b  jz      short loc_180018AFB
0x180018b3d  mov     rcx, [rcx+38h]
0x180018b41  mov     edx, 4Ch ; 'L'
0x180018b46  mov     r9d, ebx
0x180018b49  mov     r8, rbp
0x180018b4c  call    WPP_SF_d
0x180018b51  jmp     short loc_180018AFB
0x180018b53  mov     r9d, [rbx+138h]
0x180018b5a  lea     rax, aLocking; ">>> Locking >>>"
0x180018b61  mov     rcx, [rcx+38h]
0x180018b65  mov     edx, 0Ch
0x180018b6a  mov     [rsp+58h+var_38], rax
0x180018b6f  call    WPP_SF_Ls
0x180018b74  jmp     loc_180018A45
0x180018b79  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b80  cmp     rcx, rsi
0x180018b83  jz      short loc_180018B9C
0x180018b85  test    byte ptr [rcx+44h], 2
0x180018b89  jz      short loc_180018B9C
0x180018b8b  mov     rcx, [rcx+38h]
0x180018b8f  mov     edx, 48h ; 'H'
0x180018b94  mov     r8, rbp
0x180018b97  call    WPP_SF_
0x180018b9c  mov     rcx, [rbx+18h]
0x180018ba0  xor     edx, edx
0x180018ba2  mov     rax, [rbx+120h]
0x180018ba9  add     rcx, 20h ; ' '
0x180018bad  lea     r8d, [rdx+64h]
0x180018bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bb6  test    eax, eax
0x180018bb8  jnz     short loc_180018BED
0x180018bba  mov     rcx, cs:WPP_GLOBAL_Control
0x180018bc1  cmp     rcx, rsi
0x180018bc4  jz      short loc_180018BE2
0x180018bc6  test    byte ptr [rcx+44h], 2
0x180018bca  jz      short loc_180018BE2
0x180018bcc  mov     r9d, [rbx+7E8h]
0x180018bd3  lea     edx, [rax+49h]
0x180018bd6  mov     rcx, [rcx+38h]
0x180018bda  mov     r8, rbp
0x180018bdd  call    WPP_SF_d
0x180018be2  dec     dword ptr [rbx+7E8h]
0x180018be8  jmp     loc_180018A78
0x180018bed  mov     rcx, cs:WPP_GLOBAL_Control
0x180018bf4  cmp     rcx, rsi
0x180018bf7  jz      loc_180018A8E
0x180018bfd  test    byte ptr [rcx+44h], 1
0x180018c01  jz      loc_180018A7F
0x180018c07  mov     rcx, [rcx+38h]
0x180018c0b  mov     edx, 4Ah ; 'J'
0x180018c10  mov     r8, rbp
0x180018c13  call    WPP_SF_
0x180018c18  jmp     loc_180018A78
0x180018c1d  mov     r9d, [rbx+138h]
0x180018c24  lea     rax, aUnlocking; "<<< Unlocking <<<"
0x180018c2b  mov     rcx, [rcx+38h]
0x180018c2f  mov     edx, 0Ch
0x180018c34  mov     [rsp+58h+var_38], rax
0x180018c39  call    WPP_SF_Ls
0x180018c3e  jmp     loc_180018A8E
0x180018c43  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c4a  cmp     rcx, rsi
0x180018c4d  jz      loc_180018AFB
0x180018c53  test    byte ptr [rcx+44h], 1
0x180018c57  jz      loc_180018AF6
0x180018c5d  mov     rcx, [rcx+38h]
0x180018c61  mov     edx, 4Bh ; 'K'
0x180018c66  mov     r9d, ebx
0x180018c69  mov     r8, rbp
0x180018c6c  call    WPP_SF_d
0x180018c71  jmp     loc_180018AEF
```

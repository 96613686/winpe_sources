# _BoundSubscription::ReceiveCompleteCallback_::_1_::catch$1

- ea: `0x180021a22`
- end: `0x180021bb6`
- name: `_BoundSubscription::ReceiveCompleteCallback_::_1_::catch$1`
- size: `404`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000dda4`
- `0x180011938`
- `0x180021a22`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall BoundSubscription::ReceiveCompleteCallback_::_1_::catch_1(__int64 a1, __int64 a2)
{
  __int64 (__fastcall ***v3)(_QWORD); // rdi
  int v4; // eax
  __int64 v5; // rbx
  const wchar_t *v6; // rax
  const wchar_t *v7; // rcx
  __int64 v8; // rax
  const wchar_t *v9; // rax
  const wchar_t *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  char v13; // al
  int v14; // r8d
  _QWORD *v15; // rcx
  _QWORD *v16; // r9

  v3 = *(__int64 (__fastcall ****)(_QWORD))(a2 + 96);
  v4 = (**v3)(v3);
  v5 = *(_QWORD *)(a2 + 72);
  *(_DWORD *)(v5 + 180) = v4;
  BoundSubscription::InternalDeactivate((BoundSubscription *)v5, 0);
  *(_DWORD *)(a2 + 64) = (**v3)(v3);
  v6 = (const wchar_t *)(*(_QWORD *)(v5 + 64) + 56LL);
  if ( *(_QWORD *)(*(_QWORD *)(v5 + 64) + 80LL) >= 8u )
    v6 = *(const wchar_t **)v6;
  v7 = &word_180026AD8;
  if ( v6 )
    v7 = v6;
  v8 = -1;
  do
    ++v8;
  while ( v7[v8] );
  *(_QWORD *)(a2 + 104) = v7;
  *(_DWORD *)(a2 + 112) = 2 * v8 + 2;
  *(_DWORD *)(a2 + 116) = 0;
  v9 = (const wchar_t *)(v5 + 72);
  if ( *(_QWORD *)(v5 + 96) >= 8u )
    v9 = *(const wchar_t **)v9;
  v10 = &word_180026AD8;
  if ( v9 )
    v10 = v9;
  v11 = -1;
  do
    ++v11;
  while ( v10[v11] );
  *(_QWORD *)(a2 + 120) = v10;
  *(_DWORD *)(a2 + 128) = 2 * v11 + 2;
  *(_DWORD *)(a2 + 132) = 0;
  *(_QWORD *)(a2 + 136) = a2 + 64;
  *(_QWORD *)(a2 + 144) = 4;
  v12 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 64) + 104LL) + 136LL);
  (*(void (__fastcall **)(__int64, __int64 *, __int64, __int64))(*(_QWORD *)v12 + 8LL))(
    v12,
    EVTCOLL_SUBSCRIPTION_ACTIVATION_ERROR,
    3,
    a2 + 104);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = (**v3)(v3);
    v15 = (_QWORD *)(v5 + 72);
    if ( *(_QWORD *)(v5 + 96) >= 8u )
      v15 = (_QWORD *)*v15;
    v16 = (_QWORD *)(*(_QWORD *)(v5 + 64) + 56LL);
    if ( *(_QWORD *)(*(_QWORD *)(v5 + 64) + 80LL) >= 8u )
      v16 = (_QWORD *)*v16;
    WPP_SF_SSqD(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, v14, (_DWORD)v16, (__int64)v15, v5, v13);
  }
  return 0;
}

```

## disassembly

```asm
0x180021a22  mov     [rsp+arg_8], rdx
0x180021a27  push    rbx
0x180021a28  push    rbp
0x180021a29  push    rdi
0x180021a2a  sub     rsp, 40h
0x180021a2e  mov     rbp, rdx
0x180021a31  mov     rdi, [rbp+60h]
0x180021a35  mov     rax, [rdi]
0x180021a38  mov     rcx, rdi
0x180021a3b  mov     rax, [rax]
0x180021a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a43  mov     rbx, [rbp+48h]
0x180021a47  mov     [rbx+0B4h], eax
0x180021a4d  xor     edx, edx; bool
0x180021a4f  mov     rcx, rbx; this
0x180021a52  call    ?InternalDeactivate@BoundSubscription@@QEAAX_N@Z; BoundSubscription::InternalDeactivate(bool)
0x180021a57  mov     rax, [rdi]
0x180021a5a  mov     rcx, rdi
0x180021a5d  mov     rax, [rax]
0x180021a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a65  mov     [rbp+40h], eax
0x180021a68  mov     rax, [rbx+40h]
0x180021a6c  add     rax, 38h ; '8'
0x180021a70  cmp     qword ptr [rax+18h], 8
0x180021a75  jb      short loc_180021A7A
0x180021a77  mov     rax, [rax]
0x180021a7a  lea     rcx, word_180026AD8
0x180021a81  test    rax, rax
0x180021a84  cmovnz  rcx, rax
0x180021a88  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021a8c  inc     rax
0x180021a8f  cmp     word ptr [rcx+rax*2], 0
0x180021a94  jnz     short loc_180021A8C
0x180021a96  mov     [rbp+68h], rcx
0x180021a9a  lea     eax, ds:2[rax*2]
0x180021aa1  mov     [rbp+70h], eax
0x180021aa4  mov     dword ptr [rbp+74h], 0
0x180021aab  lea     rax, [rbx+48h]
0x180021aaf  cmp     qword ptr [rax+18h], 8
0x180021ab4  jb      short loc_180021AB9
0x180021ab6  mov     rax, [rax]
0x180021ab9  lea     rcx, word_180026AD8
0x180021ac0  test    rax, rax
0x180021ac3  cmovnz  rcx, rax
0x180021ac7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021acb  inc     rax
0x180021ace  cmp     word ptr [rcx+rax*2], 0
0x180021ad3  jnz     short loc_180021ACB
0x180021ad5  mov     [rbp+78h], rcx
0x180021ad9  lea     eax, ds:2[rax*2]
0x180021ae0  mov     [rbp+80h], eax
0x180021ae6  mov     dword ptr [rbp+84h], 0
0x180021af0  lea     rax, [rbp+40h]
0x180021af4  mov     [rbp+88h], rax
0x180021afb  mov     qword ptr [rbp+90h], 4
0x180021b06  mov     rax, [rbx+40h]
0x180021b0a  mov     rcx, [rax+68h]
0x180021b0e  mov     rcx, [rcx+88h]
0x180021b15  mov     rax, [rcx]
0x180021b18  lea     r9, [rbp+68h]
0x180021b1c  mov     r8d, 3
0x180021b22  lea     rdx, EVTCOLL_SUBSCRIPTION_ACTIVATION_ERROR
0x180021b29  mov     rax, [rax+8]
0x180021b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b32  lea     rcx, WPP_GLOBAL_Control
0x180021b39  mov     rax, cs:WPP_GLOBAL_Control
0x180021b40  cmp     rax, rcx
0x180021b43  jz      short loc_180021BA3
0x180021b45  test    byte ptr [rax+1Ch], 10h
0x180021b49  jz      short loc_180021BA3
0x180021b4b  cmp     byte ptr [rax+19h], 2
0x180021b4f  jb      short loc_180021BA3
0x180021b51  mov     rax, [rdi]
0x180021b54  mov     rcx, rdi
0x180021b57  mov     rax, [rax]
0x180021b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b5f  lea     rcx, [rbx+48h]
0x180021b63  cmp     qword ptr [rcx+18h], 8
0x180021b68  jb      short loc_180021B6D
0x180021b6a  mov     rcx, [rcx]
0x180021b6d  mov     r9, [rbx+40h]
0x180021b71  add     r9, 38h ; '8'
0x180021b75  cmp     qword ptr [r9+18h], 8
0x180021b7a  jb      short loc_180021B7F
0x180021b7c  mov     r9, [r9]
0x180021b7f  mov     edx, 39h ; '9'
0x180021b84  mov     [rsp+58h+var_28], eax
0x180021b88  mov     [rsp+58h+var_30], rbx
0x180021b8d  mov     [rsp+58h+var_38], rcx
0x180021b92  mov     rcx, cs:WPP_GLOBAL_Control
0x180021b99  mov     rcx, [rcx+10h]
0x180021b9d  call    WPP_SF_SSqD
0x180021ba2  nop
0x180021ba3  mov     rax, 0
0x180021bad  add     rsp, 40h
0x180021bb1  pop     rdi
0x180021bb2  pop     rbp
0x180021bb3  pop     rbx
0x180021bb4  retn
```

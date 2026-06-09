# _BoundSubscription::SubscribeCompleteCallback_::_1_::catch$1

- ea: `0x180021e97`
- end: `0x18002202b`
- name: `_BoundSubscription::SubscribeCompleteCallback_::_1_::catch$1`
- size: `404`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000dda4`
- `0x180011938`
- `0x180021e97`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall BoundSubscription::SubscribeCompleteCallback_::_1_::catch_1(__int64 a1, __int64 a2)
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
    WPP_SF_SSqD(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, v14, (_DWORD)v16, (__int64)v15, v5, v13);
  }
  return 0;
}

```

## disassembly

```asm
0x180021e97  mov     [rsp+arg_8], rdx
0x180021e9c  push    rbx
0x180021e9d  push    rbp
0x180021e9e  push    rdi
0x180021e9f  sub     rsp, 40h
0x180021ea3  mov     rbp, rdx
0x180021ea6  mov     rdi, [rbp+60h]
0x180021eaa  mov     rax, [rdi]
0x180021ead  mov     rcx, rdi
0x180021eb0  mov     rax, [rax]
0x180021eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021eb8  mov     rbx, [rbp+48h]
0x180021ebc  mov     [rbx+0B4h], eax
0x180021ec2  xor     edx, edx; bool
0x180021ec4  mov     rcx, rbx; this
0x180021ec7  call    ?InternalDeactivate@BoundSubscription@@QEAAX_N@Z; BoundSubscription::InternalDeactivate(bool)
0x180021ecc  mov     rax, [rdi]
0x180021ecf  mov     rcx, rdi
0x180021ed2  mov     rax, [rax]
0x180021ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021eda  mov     [rbp+40h], eax
0x180021edd  mov     rax, [rbx+40h]
0x180021ee1  add     rax, 38h ; '8'
0x180021ee5  cmp     qword ptr [rax+18h], 8
0x180021eea  jb      short loc_180021EEF
0x180021eec  mov     rax, [rax]
0x180021eef  lea     rcx, word_180026AD8
0x180021ef6  test    rax, rax
0x180021ef9  cmovnz  rcx, rax
0x180021efd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021f01  inc     rax
0x180021f04  cmp     word ptr [rcx+rax*2], 0
0x180021f09  jnz     short loc_180021F01
0x180021f0b  mov     [rbp+68h], rcx
0x180021f0f  lea     eax, ds:2[rax*2]
0x180021f16  mov     [rbp+70h], eax
0x180021f19  mov     dword ptr [rbp+74h], 0
0x180021f20  lea     rax, [rbx+48h]
0x180021f24  cmp     qword ptr [rax+18h], 8
0x180021f29  jb      short loc_180021F2E
0x180021f2b  mov     rax, [rax]
0x180021f2e  lea     rcx, word_180026AD8
0x180021f35  test    rax, rax
0x180021f38  cmovnz  rcx, rax
0x180021f3c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021f40  inc     rax
0x180021f43  cmp     word ptr [rcx+rax*2], 0
0x180021f48  jnz     short loc_180021F40
0x180021f4a  mov     [rbp+78h], rcx
0x180021f4e  lea     eax, ds:2[rax*2]
0x180021f55  mov     [rbp+80h], eax
0x180021f5b  mov     dword ptr [rbp+84h], 0
0x180021f65  lea     rax, [rbp+40h]
0x180021f69  mov     [rbp+88h], rax
0x180021f70  mov     qword ptr [rbp+90h], 4
0x180021f7b  mov     rax, [rbx+40h]
0x180021f7f  mov     rcx, [rax+68h]
0x180021f83  mov     rcx, [rcx+88h]
0x180021f8a  mov     rax, [rcx]
0x180021f8d  lea     r9, [rbp+68h]
0x180021f91  mov     r8d, 3
0x180021f97  lea     rdx, EVTCOLL_SUBSCRIPTION_ACTIVATION_ERROR
0x180021f9e  mov     rax, [rax+8]
0x180021fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fa7  lea     rcx, WPP_GLOBAL_Control
0x180021fae  mov     rax, cs:WPP_GLOBAL_Control
0x180021fb5  cmp     rax, rcx
0x180021fb8  jz      short loc_180022018
0x180021fba  test    byte ptr [rax+1Ch], 10h
0x180021fbe  jz      short loc_180022018
0x180021fc0  cmp     byte ptr [rax+19h], 2
0x180021fc4  jb      short loc_180022018
0x180021fc6  mov     rax, [rdi]
0x180021fc9  mov     rcx, rdi
0x180021fcc  mov     rax, [rax]
0x180021fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fd4  lea     rcx, [rbx+48h]
0x180021fd8  cmp     qword ptr [rcx+18h], 8
0x180021fdd  jb      short loc_180021FE2
0x180021fdf  mov     rcx, [rcx]
0x180021fe2  mov     r9, [rbx+40h]
0x180021fe6  add     r9, 38h ; '8'
0x180021fea  cmp     qword ptr [r9+18h], 8
0x180021fef  jb      short loc_180021FF4
0x180021ff1  mov     r9, [r9]
0x180021ff4  mov     edx, 35h ; '5'
0x180021ff9  mov     [rsp+58h+var_28], eax
0x180021ffd  mov     [rsp+58h+var_30], rbx
0x180022002  mov     [rsp+58h+var_38], rcx
0x180022007  mov     rcx, cs:WPP_GLOBAL_Control
0x18002200e  mov     rcx, [rcx+10h]
0x180022012  call    WPP_SF_SSqD
0x180022017  nop
0x180022018  mov     rax, 0
0x180022022  add     rsp, 40h
0x180022026  pop     rdi
0x180022027  pop     rbp
0x180022028  pop     rbx
0x180022029  retn
```

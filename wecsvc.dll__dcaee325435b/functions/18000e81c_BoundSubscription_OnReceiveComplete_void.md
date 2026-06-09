# BoundSubscription::OnReceiveComplete(void)

- ea: `0x18000e81c`
- end: `0x18000ea1f`
- name: `?OnReceiveComplete@BoundSubscription@@AEAAXXZ`
- size: `515`
- prototype: `void __fastcall(BoundSubscription *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000f5f0`

## callees

- `0x18000c2d8`
- `0x18000cef8`
- `0x18000e81c`
- `0x18000f670`
- `0x18000f7b0`
- `0x180011938`
- `0x18001fe50`
- `0x180023010`

## pseudocode

```c
void __fastcall BoundSubscription::OnReceiveComplete(BoundSubscription *this)
{
  _QWORD *v2; // r8
  _QWORD *v3; // r9
  _QWORD *v4; // r9
  const wchar_t *v5; // rax
  const wchar_t *v6; // rdx
  const wchar_t *v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rax
  const wchar_t *v10; // rax
  bool v11; // cf
  _QWORD *v12; // rcx
  _QWORD *v13; // r9
  const wchar_t *v14; // [rsp+40h] [rbp-38h] BYREF
  int v15; // [rsp+48h] [rbp-30h]
  int v16; // [rsp+4Ch] [rbp-2Ch]
  const wchar_t *v17; // [rsp+50h] [rbp-28h]
  int v18; // [rsp+58h] [rbp-20h]
  int v19; // [rsp+5Ch] [rbp-1Ch]

  if ( *((_DWORD *)this + 14) && *((_DWORD *)this + 14) != 3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v2 = (_QWORD *)((char *)this + 72);
      if ( *((_QWORD *)this + 12) >= 8u )
        v2 = (_QWORD *)*v2;
      v3 = (_QWORD *)(*((_QWORD *)this + 8) + 56LL);
      if ( *(_QWORD *)(*((_QWORD *)this + 8) + 80LL) >= 8u )
        v3 = (_QWORD *)*v3;
      WPP_SF_SSqD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        (_DWORD)v2,
        (_DWORD)v3,
        (__int64)v2,
        (char)this,
        *((_DWORD *)this + 84));
    }
    BoundSubscription::RecordLastError(
      (struct _FILETIME *)this,
      *((_DWORD *)this + 84),
      *((struct WSMAN_OBJECT **)this + 43));
    if ( *((_DWORD *)this + 84) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = (_QWORD *)((char *)this + 72);
        if ( *((_QWORD *)this + 12) >= 8u )
          v12 = (_QWORD *)*v12;
        v13 = (_QWORD *)(*((_QWORD *)this + 8) + 56LL);
        if ( *(_QWORD *)(*((_QWORD *)this + 8) + 80LL) >= 8u )
          v13 = (_QWORD *)*v13;
        WPP_SF_SSqD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          63,
          (_DWORD)WPP_GLOBAL_Control,
          (_DWORD)v13,
          (__int64)v12,
          (char)this,
          *((_DWORD *)this + 84));
      }
      BoundSubscription::ExitReceivingState(this);
      BoundSubscription::EnterRetryingState(this);
    }
    else
    {
      if ( *((_DWORD *)this + 62) )
      {
        v4 = (_QWORD *)*((_QWORD *)this + 8);
        v5 = (const wchar_t *)(v4 + 7);
        if ( v4[10] >= 8u )
          v5 = *(const wchar_t **)v5;
        v6 = &word_180026AD8;
        v7 = &word_180026AD8;
        if ( v5 )
          v7 = v5;
        v8 = -1;
        v9 = -1;
        do
          ++v9;
        while ( v7[v9] );
        v14 = v7;
        v15 = 2 * v9 + 2;
        v10 = (const wchar_t *)((char *)this + 72);
        v11 = *((_QWORD *)this + 12) < 8u;
        v16 = 0;
        if ( !v11 )
          v10 = *(const wchar_t **)v10;
        if ( v10 )
          v6 = v10;
        do
          ++v8;
        while ( v6[v8] );
        v17 = v6;
        v18 = 2 * v8 + 2;
        v19 = 0;
        (*(void (__fastcall **)(_QWORD, __int64 *, __int64, const wchar_t **))(**(_QWORD **)(v4[13] + 136LL) + 8LL))(
          *(_QWORD *)(v4[13] + 136LL),
          EVTCOLL_SUBSCRIPTION_ACTIVE,
          2,
          &v14);
      }
      *((_DWORD *)this + 62) = 0;
      BoundSubscription::ReceiveEvents(this);
    }
  }
}

```

## disassembly

```asm
0x18000e81c  mov     [rsp+arg_8], rbx
0x18000e821  mov     [rsp+arg_10], rsi
0x18000e826  push    rdi
0x18000e827  sub     rsp, 70h
0x18000e82b  mov     rax, cs:__security_cookie
0x18000e832  xor     rax, rsp
0x18000e835  mov     [rsp+78h+var_18], rax
0x18000e83a  xor     edi, edi
0x18000e83c  mov     rbx, rcx
0x18000e83f  cmp     [rcx+38h], edi
0x18000e842  jz      loc_18000EA00
0x18000e848  cmp     dword ptr [rcx+38h], 3
0x18000e84c  jz      loc_18000EA00
0x18000e852  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e859  lea     rsi, WPP_GLOBAL_Control
0x18000e860  cmp     rcx, rsi
0x18000e863  jz      short loc_18000E8B5
0x18000e865  test    byte ptr [rcx+1Ch], 10h
0x18000e869  jz      short loc_18000E8B5
0x18000e86b  cmp     byte ptr [rcx+19h], 5
0x18000e86f  jb      short loc_18000E8B5
0x18000e871  mov     r10d, [rbx+150h]
0x18000e878  lea     r8, [rbx+48h]
0x18000e87c  cmp     qword ptr [r8+18h], 8
0x18000e881  jb      short loc_18000E886
0x18000e883  mov     r8, [r8]
0x18000e886  mov     r9, [rbx+40h]
0x18000e88a  add     r9, 38h ; '8'
0x18000e88e  cmp     qword ptr [r9+18h], 8
0x18000e893  jb      short loc_18000E898
0x18000e895  mov     r9, [r9]
0x18000e898  mov     rcx, [rcx+10h]
0x18000e89c  mov     edx, 3Eh ; '>'
0x18000e8a1  mov     [rsp+78h+var_48], r10d
0x18000e8a6  mov     [rsp+78h+var_50], rbx
0x18000e8ab  mov     [rsp+78h+var_58], r8
0x18000e8b0  call    WPP_SF_SSqD
0x18000e8b5  mov     r8, [rbx+158h]; struct WSMAN_OBJECT *
0x18000e8bc  mov     rcx, rbx; this
0x18000e8bf  mov     edx, [rbx+150h]; unsigned int
0x18000e8c5  call    ?RecordLastError@BoundSubscription@@AEAAXKPEAUWSMAN_OBJECT@@@Z; BoundSubscription::RecordLastError(ulong,WSMAN_OBJECT *)
0x18000e8ca  mov     r10d, [rbx+150h]
0x18000e8d1  test    r10d, r10d
0x18000e8d4  jnz     loc_18000E999
0x18000e8da  cmp     [rbx+0F8h], edi
0x18000e8e0  jbe     loc_18000E989
0x18000e8e6  mov     r9, [rbx+40h]
0x18000e8ea  lea     rax, [r9+38h]
0x18000e8ee  cmp     qword ptr [rax+18h], 8
0x18000e8f3  jb      short loc_18000E8F8
0x18000e8f5  mov     rax, [rax]
0x18000e8f8  test    rax, rax
0x18000e8fb  lea     rdx, word_180026AD8
0x18000e902  mov     r8, rdx
0x18000e905  cmovnz  r8, rax
0x18000e909  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000e90d  mov     rax, rcx
0x18000e910  inc     rax
0x18000e913  cmp     [r8+rax*2], di
0x18000e918  jnz     short loc_18000E910
0x18000e91a  lea     eax, ds:2[rax*2]
0x18000e921  mov     [rsp+78h+var_38], r8
0x18000e926  mov     [rsp+78h+var_30], eax
0x18000e92a  lea     rax, [rbx+48h]
0x18000e92e  cmp     qword ptr [rax+18h], 8
0x18000e933  mov     [rsp+78h+var_2C], edi
0x18000e937  jb      short loc_18000E93C
0x18000e939  mov     rax, [rax]
0x18000e93c  test    rax, rax
0x18000e93f  cmovnz  rdx, rax
0x18000e943  inc     rcx
0x18000e946  cmp     [rdx+rcx*2], di
0x18000e94a  jnz     short loc_18000E943
0x18000e94c  mov     [rsp+78h+var_28], rdx
0x18000e951  lea     eax, ds:2[rcx*2]
0x18000e958  mov     [rsp+78h+var_20], eax
0x18000e95c  lea     rdx, EVTCOLL_SUBSCRIPTION_ACTIVE
0x18000e963  mov     [rsp+78h+var_1C], edi
0x18000e967  mov     r8d, 2
0x18000e96d  mov     rax, [r9+68h]
0x18000e971  lea     r9, [rsp+78h+var_38]
0x18000e976  mov     rcx, [rax+88h]
0x18000e97d  mov     rax, [rcx]
0x18000e980  mov     rax, [rax+8]
0x18000e984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e989  mov     rcx, rbx; this
0x18000e98c  mov     [rbx+0F8h], edi
0x18000e992  call    ?ReceiveEvents@BoundSubscription@@AEAAXXZ; BoundSubscription::ReceiveEvents(void)
0x18000e997  jmp     short loc_18000EA00
0x18000e999  mov     r8, cs:WPP_GLOBAL_Control
0x18000e9a0  cmp     r8, rsi
0x18000e9a3  jz      short loc_18000E9F0
0x18000e9a5  test    byte ptr [r8+1Ch], 10h
0x18000e9aa  jz      short loc_18000E9F0
0x18000e9ac  cmp     byte ptr [r8+19h], 2
0x18000e9b1  jb      short loc_18000E9F0
0x18000e9b3  lea     rcx, [rbx+48h]
0x18000e9b7  cmp     qword ptr [rcx+18h], 8
0x18000e9bc  jb      short loc_18000E9C1
0x18000e9be  mov     rcx, [rcx]
0x18000e9c1  mov     r9, [rbx+40h]
0x18000e9c5  add     r9, 38h ; '8'
0x18000e9c9  cmp     qword ptr [r9+18h], 8
0x18000e9ce  jb      short loc_18000E9D3
0x18000e9d0  mov     r9, [r9]
0x18000e9d3  mov     [rsp+78h+var_48], r10d
0x18000e9d8  mov     edx, 3Fh ; '?'
0x18000e9dd  mov     [rsp+78h+var_50], rbx
0x18000e9e2  mov     [rsp+78h+var_58], rcx
0x18000e9e7  mov     rcx, [r8+10h]
0x18000e9eb  call    WPP_SF_SSqD
0x18000e9f0  mov     rcx, rbx; this
0x18000e9f3  call    ?ExitReceivingState@BoundSubscription@@AEAAXXZ; BoundSubscription::ExitReceivingState(void)
0x18000e9f8  mov     rcx, rbx; this
0x18000e9fb  call    ?EnterRetryingState@BoundSubscription@@AEAAXXZ; BoundSubscription::EnterRetryingState(void)
0x18000ea00  mov     rcx, [rsp+78h+var_18]
0x18000ea05  xor     rcx, rsp; StackCookie
0x18000ea08  call    __security_check_cookie
0x18000ea0d  lea     r11, [rsp+78h+var_8]
0x18000ea12  mov     rbx, [r11+18h]
0x18000ea16  mov     rsi, [r11+20h]
0x18000ea1a  mov     rsp, r11
0x18000ea1d  pop     rdi
0x18000ea1e  retn
```

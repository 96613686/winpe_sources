# CShareWithListItemBase::UpdateUI(int)

- ea: `0x18000e1f4`
- end: `0x18000e393`
- name: `?UpdateUI@CShareWithListItemBase@@QEAAJH@Z`
- size: `415`
- prototype: `__int64 __fastcall(CShareWithListItemBase *__hidden this, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000d674`
- `0x18000df2c`
- `0x18000e10c`

## callees

- `0x180003860`
- `0x180003888`
- `0x18000e1f4`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CShareWithListItemBase::UpdateUI(CShareWithListItemBase *this, int a2)
{
  _QWORD *v4; // rcx
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !*((_DWORD *)this + 60) )
    goto LABEL_21;
  v5 = (*(__int64 (__fastcall **)(CShareWithListItemBase *))(*(_QWORD *)this + 416LL))(this);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 191, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v5);
  if ( a2 )
  {
    v6 = (*(__int64 (__fastcall **)(CShareWithListItemBase *))(*(_QWORD *)this + 384LL))(this);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 192, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v6);
  }
  v7 = (*(__int64 (__fastcall **)(CShareWithListItemBase *))(*(_QWORD *)this + 400LL))(this);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v7);
  v8 = (*(__int64 (__fastcall **)(CShareWithListItemBase *))(*(_QWORD *)this + 408LL))(this);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 194, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v8);
  v9 = (*(__int64 (__fastcall **)(CShareWithListItemBase *))(*(_QWORD *)this + 432LL))(this);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v9);
      v4 = WPP_GLOBAL_Control;
    }
LABEL_21:
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
      WPP_SF_(v4[2], 196, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e1f4  push    rbx
0x18000e1f6  push    rsi
0x18000e1f7  push    rdi
0x18000e1f8  push    r14
0x18000e1fa  sub     rsp, 28h
0x18000e1fe  mov     edi, edx
0x18000e200  mov     rbx, rcx
0x18000e203  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e20a  lea     r14, WPP_GLOBAL_Control
0x18000e211  lea     rsi, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000e218  cmp     rcx, r14
0x18000e21b  jz      short loc_18000E23B
0x18000e21d  test    byte ptr [rcx+1Ch], 20h
0x18000e221  jz      short loc_18000E23B
0x18000e223  mov     rcx, [rcx+10h]
0x18000e227  mov     edx, 0BEh
0x18000e22c  mov     r8, rsi
0x18000e22f  call    WPP_SF_
0x18000e234  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e23b  cmp     dword ptr [rbx+0F0h], 0
0x18000e242  jz      loc_18000E36B
0x18000e248  mov     rax, [rbx]
0x18000e24b  mov     rcx, rbx
0x18000e24e  mov     rax, [rax+1A0h]
0x18000e255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e25a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e261  cmp     rcx, r14
0x18000e264  jz      short loc_18000E280
0x18000e266  test    byte ptr [rcx+1Ch], 8
0x18000e26a  jz      short loc_18000E280
0x18000e26c  mov     rcx, [rcx+10h]
0x18000e270  mov     edx, 0BFh
0x18000e275  mov     r9d, eax
0x18000e278  mov     r8, rsi
0x18000e27b  call    WPP_SF_d
0x18000e280  test    edi, edi
0x18000e282  jz      short loc_18000E2BC
0x18000e284  mov     rax, [rbx]
0x18000e287  mov     rcx, rbx
0x18000e28a  mov     rax, [rax+180h]
0x18000e291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e296  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e29d  cmp     rcx, r14
0x18000e2a0  jz      short loc_18000E2BC
0x18000e2a2  test    byte ptr [rcx+1Ch], 8
0x18000e2a6  jz      short loc_18000E2BC
0x18000e2a8  mov     rcx, [rcx+10h]
0x18000e2ac  mov     edx, 0C0h
0x18000e2b1  mov     r9d, eax
0x18000e2b4  mov     r8, rsi
0x18000e2b7  call    WPP_SF_d
0x18000e2bc  mov     rax, [rbx]
0x18000e2bf  mov     rcx, rbx
0x18000e2c2  mov     rax, [rax+190h]
0x18000e2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2d5  cmp     rcx, r14
0x18000e2d8  jz      short loc_18000E2F4
0x18000e2da  test    byte ptr [rcx+1Ch], 8
0x18000e2de  jz      short loc_18000E2F4
0x18000e2e0  mov     rcx, [rcx+10h]
0x18000e2e4  mov     edx, 0C1h
0x18000e2e9  mov     r9d, eax
0x18000e2ec  mov     r8, rsi
0x18000e2ef  call    WPP_SF_d
0x18000e2f4  mov     rax, [rbx]
0x18000e2f7  mov     rcx, rbx
0x18000e2fa  mov     rax, [rax+198h]
0x18000e301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e306  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e30d  cmp     rcx, r14
0x18000e310  jz      short loc_18000E32C
0x18000e312  test    byte ptr [rcx+1Ch], 8
0x18000e316  jz      short loc_18000E32C
0x18000e318  mov     rcx, [rcx+10h]
0x18000e31c  mov     edx, 0C2h
0x18000e321  mov     r9d, eax
0x18000e324  mov     r8, rsi
0x18000e327  call    WPP_SF_d
0x18000e32c  mov     rax, [rbx]
0x18000e32f  mov     rcx, rbx
0x18000e332  mov     rax, [rax+1B0h]
0x18000e339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e33e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e345  cmp     rcx, r14
0x18000e348  jz      short loc_18000E387
0x18000e34a  test    byte ptr [rcx+1Ch], 8
0x18000e34e  jz      short loc_18000E36B
0x18000e350  mov     rcx, [rcx+10h]
0x18000e354  mov     edx, 0C3h
0x18000e359  mov     r9d, eax
0x18000e35c  mov     r8, rsi
0x18000e35f  call    WPP_SF_d
0x18000e364  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e36b  cmp     rcx, r14
0x18000e36e  jz      short loc_18000E387
0x18000e370  test    byte ptr [rcx+1Ch], 20h
0x18000e374  jz      short loc_18000E387
0x18000e376  mov     rcx, [rcx+10h]
0x18000e37a  mov     edx, 0C4h
0x18000e37f  mov     r8, rsi
0x18000e382  call    WPP_SF_
0x18000e387  xor     eax, eax
0x18000e389  add     rsp, 28h
0x18000e38d  pop     r14
0x18000e38f  pop     rdi
0x18000e390  pop     rsi
0x18000e391  pop     rbx
0x18000e392  retn
```

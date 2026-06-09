# CheckIndicatePendedData

- ea: `0x14000d210`
- end: `0x14000d40c`
- name: `CheckIndicatePendedData`
- size: `508`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x140011904`
- `0x1400120b4`
- `0x140012efc`

## callees

- `0x140005038`
- `0x140005068`
- `0x14000bc98`
- `0x14000cdfc`
- `0x14000cf04`
- `0x14000d210`
- `0x14000e810`
- `0x14000f0a0`
- `0x14000fe74`

## pseudocode

```c
__int64 __fastcall CheckIndicatePendedData(__int64 a1, __int64 a2, KIRQL *a3, KIRQL *a4)
{
  int v4; // eax
  _DWORD *v8; // rbp
  int v9; // esi
  __int64 *v10; // r15
  _BYTE *v11; // rdi
  PDEVICE_OBJECT *v12; // rdx
  int v13; // eax
  int v14; // eax
  int v15; // r8d
  int v16; // eax
  int v17; // r8d
  __int64 v18; // rcx
  _QWORD *v19; // rax
  unsigned int v20; // r9d

  v4 = *(_DWORD *)(a2 + 32);
  if ( (v4 & 0xC00) == 0 )
  {
    v8 = *(_DWORD **)(a2 + 48);
    v9 = 0;
    *(_DWORD *)(a2 + 32) = v4 | 0x400;
    v10 = (__int64 *)(v8 + 30);
    while ( 1 )
    {
      v11 = (_BYTE *)*v10;
      v12 = &WPP_GLOBAL_Control;
      if ( (__int64 *)*v10 == v10 )
        goto LABEL_19;
      v13 = (unsigned __int8)v11[59];
      if ( (_BYTE)v13 )
      {
        if ( v13 + (unsigned __int8)v11[58] != (unsigned __int8)v11[57] )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_(
              (__int64)WPP_GLOBAL_Control->AttachedDevice,
              0x67u,
              (__int64)WPP_9481eaf791d131fecb736b68b85870ad_Traceguids);
          }
          *(_DWORD *)(a2 + 32) |= 0x100u;
          goto LABEL_19;
        }
        v9 = DecodeParityPackets(a2, *v10);
        if ( v9 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_d(
              (__int64)WPP_GLOBAL_Control->AttachedDevice,
              0x68u,
              (__int64)WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
              v9);
          }
          goto LABEL_14;
        }
      }
      v14 = PgmIndicateGroup(a1, a2, (_DWORD)a3, (_DWORD)a4, (__int64)v11);
      v9 = v14;
      if ( v14 < 0 )
        break;
      v8[13] += (unsigned __int8)v11[62];
      v15 = (unsigned __int8)v11[59];
      v16 = (unsigned __int8)v11[58];
      --v8[68];
      v17 = v16 + v15;
      v8[65] -= v17;
      v8[66] -= v17;
      v18 = *(_QWORD *)v11;
      if ( *(_BYTE **)(*(_QWORD *)v11 + 8LL) != v11 || (v19 = (_QWORD *)*((_QWORD *)v11 + 1), (_BYTE *)*v19 != v11) )
        __fastfail(3u);
      *v19 = v18;
      *(_QWORD *)(v18 + 8) = v19;
      FreeNakContext(a2, v11);
    }
    if ( v14 != -1073741285 )
LABEL_14:
      *(_DWORD *)(a2 + 32) |= 0x100u;
LABEL_19:
    v20 = *(_DWORD *)(a2 + 32) & 0xFFFFFBFF;
    *(_DWORD *)(a2 + 32) = v20;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_DqD(
        WPP_GLOBAL_Control->AttachedDevice,
        106,
        WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
        (unsigned int)v9,
        a2,
        v20);
    CheckDeferredCleanup(a2, v12, a3);
    CheckIndicateDisconnect(a1, a2, a3, a4, 1);
  }
  return 0;
}

```

## disassembly

```asm
0x14000d210  mov     [rsp+arg_0], rcx
0x14000d215  push    rbx
0x14000d216  push    rbp
0x14000d217  push    rsi
0x14000d218  push    rdi
0x14000d219  push    r12
0x14000d21b  push    r13
0x14000d21d  push    r14
0x14000d21f  push    r15
0x14000d221  sub     rsp, 38h
0x14000d225  mov     eax, [rdx+20h]
0x14000d228  mov     r12, r9
0x14000d22b  mov     r13, r8
0x14000d22e  mov     rbx, rdx
0x14000d231  test    eax, 0C00h
0x14000d236  jnz     loc_14000D3DA
0x14000d23c  mov     rbp, [rdx+30h]
0x14000d240  xor     esi, esi
0x14000d242  bts     eax, 0Ah
0x14000d246  mov     [rdx+20h], eax
0x14000d249  lea     r15, [rbp+78h]
0x14000d24d  mov     rdi, [r15]
0x14000d250  lea     rdx, WPP_GLOBAL_Control
0x14000d257  cmp     rdi, r15
0x14000d25a  jz      loc_14000D36E
0x14000d260  movzx   eax, byte ptr [rdi+3Bh]
0x14000d264  test    al, al
0x14000d266  jz      short loc_14000D28B
0x14000d268  movzx   ecx, byte ptr [rdi+3Ah]
0x14000d26c  add     ecx, eax
0x14000d26e  movzx   eax, byte ptr [rdi+39h]
0x14000d272  cmp     ecx, eax
0x14000d274  jnz     loc_14000D341
0x14000d27a  mov     rdx, rdi
0x14000d27d  mov     rcx, rbx
0x14000d280  call    DecodeParityPackets
0x14000d285  mov     esi, eax
0x14000d287  test    eax, eax
0x14000d289  js      short loc_14000D308
0x14000d28b  mov     rcx, [rsp+78h+arg_0]
0x14000d293  mov     r9, r12
0x14000d296  mov     r8, r13
0x14000d299  mov     [rsp+78h+var_58], rdi
0x14000d29e  mov     rdx, rbx
0x14000d2a1  call    PgmIndicateGroup
0x14000d2a6  mov     esi, eax
0x14000d2a8  test    eax, eax
0x14000d2aa  js      loc_14000D3F5
0x14000d2b0  movzx   eax, byte ptr [rdi+3Eh]
0x14000d2b4  add     [rbp+34h], eax
0x14000d2b7  movzx   r8d, byte ptr [rdi+3Bh]
0x14000d2bc  movzx   eax, byte ptr [rdi+3Ah]
0x14000d2c0  dec     dword ptr [rbp+110h]
0x14000d2c6  add     r8d, eax
0x14000d2c9  sub     [rbp+104h], r8d
0x14000d2d0  sub     [rbp+108h], r8d
0x14000d2d7  mov     rcx, [rdi]
0x14000d2da  cmp     [rcx+8], rdi
0x14000d2de  jnz     loc_14000D3EE
0x14000d2e4  mov     rax, [rdi+8]
0x14000d2e8  cmp     [rax], rdi
0x14000d2eb  jnz     loc_14000D3EE
0x14000d2f1  mov     [rax], rcx
0x14000d2f4  mov     rdx, rdi
0x14000d2f7  mov     [rcx+8], rax
0x14000d2fb  mov     rcx, rbx
0x14000d2fe  call    FreeNakContext
0x14000d303  jmp     loc_14000D24D
0x14000d308  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d30f  lea     rdi, WPP_GLOBAL_Control
0x14000d316  cmp     rcx, rdi
0x14000d319  jz      short loc_14000D33A
0x14000d31b  mov     eax, [rcx+2Ch]
0x14000d31e  test    al, 2
0x14000d320  jz      short loc_14000D33A
0x14000d322  mov     rcx, [rcx+18h]
0x14000d326  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x14000d32d  mov     edx, 68h ; 'h'
0x14000d332  mov     r9d, esi
0x14000d335  call    WPP_SF_d
0x14000d33a  bts     dword ptr [rbx+20h], 8
0x14000d33f  jmp     short loc_14000D375
0x14000d341  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d348  cmp     rcx, rdx
0x14000d34b  jz      short loc_14000D369
0x14000d34d  mov     eax, [rcx+2Ch]
0x14000d350  test    al, 2
0x14000d352  jz      short loc_14000D369
0x14000d354  mov     rcx, [rcx+18h]
0x14000d358  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x14000d35f  mov     edx, 67h ; 'g'
0x14000d364  call    WPP_SF_
0x14000d369  bts     dword ptr [rbx+20h], 8
0x14000d36e  lea     rdi, WPP_GLOBAL_Control
0x14000d375  mov     r9d, [rbx+20h]
0x14000d379  btr     r9d, 0Ah
0x14000d37e  mov     [rbx+20h], r9d
0x14000d382  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d389  cmp     rcx, rdi
0x14000d38c  jz      short loc_14000D3B7
0x14000d38e  mov     eax, [rcx+2Ch]
0x14000d391  test    al, 10h
0x14000d393  jz      short loc_14000D3B7
0x14000d395  mov     rcx, [rcx+18h]
0x14000d399  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x14000d3a0  mov     [rsp+78h+var_50], r9d
0x14000d3a5  mov     edx, 6Ah ; 'j'
0x14000d3aa  mov     r9d, esi
0x14000d3ad  mov     [rsp+78h+var_58], rbx
0x14000d3b2  call    WPP_SF_DqD
0x14000d3b7  mov     rcx, rbx
0x14000d3ba  call    CheckDeferredCleanup
0x14000d3bf  mov     rcx, [rsp+78h+arg_0]
0x14000d3c7  mov     r9, r12
0x14000d3ca  mov     r8, r13
0x14000d3cd  mov     byte ptr [rsp+78h+var_58], 1
0x14000d3d2  mov     rdx, rbx
0x14000d3d5  call    CheckIndicateDisconnect
0x14000d3da  xor     eax, eax
0x14000d3dc  add     rsp, 38h
0x14000d3e0  pop     r15
0x14000d3e2  pop     r14
0x14000d3e4  pop     r13
0x14000d3e6  pop     r12
0x14000d3e8  pop     rdi
0x14000d3e9  pop     rsi
0x14000d3ea  pop     rbp
0x14000d3eb  pop     rbx
0x14000d3ec  retn
0x14000d3ee  mov     ecx, 3
0x14000d3f3  int     29h; Win8: RtlFailFast(ecx)
0x14000d3f5  lea     rdi, WPP_GLOBAL_Control
0x14000d3fc  cmp     eax, 0C000021Bh
0x14000d401  jz      loc_14000D375
0x14000d407  jmp     loc_14000D33A
```

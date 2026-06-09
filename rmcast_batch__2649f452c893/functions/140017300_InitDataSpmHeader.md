# InitDataSpmHeader

- ea: `0x140017300`
- end: `0x140017650`
- name: `InitDataSpmHeader`
- size: `848`
- prototype: `__int64 __fastcall(__int64, int, __int64, _WORD *, unsigned int, __int64, unsigned __int8)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x140016a74`
- `0x140017a30`
- `0x140019f70`

## callees

- `0x140005068`
- `0x1400050ac`
- `0x1400052e4`
- `0x14000bef8`
- `0x140017300`
- `0x140017658`
- `0x14001ae90`

## pseudocode

```c
__int64 __fastcall InitDataSpmHeader(
        __int64 a1,
        int a2,
        __int64 a3,
        _WORD *a4,
        unsigned int a5,
        __int64 a6,
        unsigned __int8 a7)
{
  int v10; // eax
  __int64 v11; // r8
  __int64 v13; // rdx
  unsigned int v14; // r11d
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned __int16 v18; // bx
  bool v19; // zf
  unsigned __int16 v20; // si
  int inited; // esi
  unsigned __int16 v22; // [rsp+70h] [rbp+8h] BYREF

  if ( !a1 || (v10 = *(_DWORD *)(a1 + 16), v10 != 1397966163) && v10 != 844318035 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids, a1);
    return 3221225473LL;
  }
  v11 = (unsigned __int16)*a4;
  if ( (unsigned __int16)v11 < 0x10u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
        (unsigned __int16)*a4,
        16);
    return 3221225990LL;
  }
  v13 = a7;
  v14 = a7;
  *(_WORD *)a3 = __ROR2__(*(_WORD *)(a1 + 70), 8);
  *(_DWORD *)(a3 + 8) = *(_DWORD *)(a1 + 64);
  *(_WORD *)(a3 + 12) = *(_WORD *)(a1 + 68);
  *(_WORD *)(a3 + 4) = (unsigned __int8)v13;
  *(_WORD *)(a3 + 2) = __ROR2__(*(_WORD *)(*(_QWORD *)(a1 + 40) + 48LL), 8);
  if ( (_BYTE)v13 )
  {
    if ( (_DWORD)v13 == 4 )
    {
      v17 = a5;
      if ( a5 != (a5 & 0xC69) )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
          return 3221225485LL;
        v16 = 22;
        goto LABEL_29;
      }
      v18 = 24;
      goto LABEL_34;
    }
    if ( (_DWORD)v13 != 5 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
        return 3221225485LL;
      v16 = 24;
      v17 = v14;
LABEL_29:
      WPP_SF_d(v15->AttachedDevice, v16, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids, v17);
      return 3221225485LL;
    }
    v17 = a5;
    if ( a5 != (a5 & 0xC69) )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
        return 3221225485LL;
      v16 = 23;
      goto LABEL_29;
    }
    v18 = 24;
    v19 = (a5 & 0x800) == 0;
  }
  else
  {
    v17 = a5;
    if ( a5 != (a5 & 0x1EBC8) )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
        return 3221225485LL;
      v16 = 21;
      goto LABEL_29;
    }
    v18 = 36;
    v19 = (a5 & 0x12A00) == 0;
  }
  if ( !v19 )
    *(_BYTE *)(a3 + 5) = 2;
LABEL_34:
  if ( (unsigned __int16)v11 < v18 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_DdD(WPP_GLOBAL_Control->AttachedDevice, v13, v11, (unsigned int)v11, v18, v14);
    return 3221225843LL;
  }
  v20 = 0;
  if ( (_DWORD)v17 )
  {
    v22 = v11 - v18;
    inited = InitDataSpmOptions(a1, a2, (unsigned int)a3 + v18, (unsigned int)&v22, v17, a6);
    if ( inited < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          26,
          WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
          (unsigned int)inited);
      return (unsigned int)inited;
    }
    *(_BYTE *)(a3 + 5) |= 1u;
    v20 = v22;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids, a3, v18, v20);
  *a4 = v18 + v20;
  return 0;
}

```

## disassembly

```asm
0x140017300  push    rbx
0x140017302  push    rbp
0x140017303  push    rsi
0x140017304  push    rdi
0x140017305  push    r14
0x140017307  push    r15
0x140017309  sub     rsp, 38h
0x14001730d  mov     r14, r9
0x140017310  mov     rdi, r8
0x140017313  mov     rbp, rdx
0x140017316  mov     r10, rcx
0x140017319  test    rcx, rcx
0x14001731c  jz      loc_14001760B
0x140017322  mov     eax, [rcx+10h]
0x140017325  cmp     eax, 53534553h
0x14001732a  jz      short loc_140017337
0x14001732c  cmp     eax, 32534553h
0x140017331  jnz     loc_14001760B
0x140017337  movzx   r8d, word ptr [r9]
0x14001733b  mov     r15d, 10h
0x140017341  cmp     r8w, r15w
0x140017345  jnb     short loc_140017387
0x140017347  mov     rcx, cs:WPP_GLOBAL_Control
0x14001734e  lea     rax, WPP_GLOBAL_Control
0x140017355  cmp     rcx, rax
0x140017358  jz      short loc_14001737D
0x14001735a  mov     eax, [rcx+2Ch]
0x14001735d  test    al, 2
0x14001735f  jz      short loc_14001737D
0x140017361  mov     rcx, [rcx+18h]
0x140017365  lea     edx, [r15+4]
0x140017369  mov     r9d, r8d
0x14001736c  mov     [rsp+68h+var_48], r15d
0x140017371  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140017378  call    WPP_SF_Dd
0x14001737d  mov     eax, 0C0000206h
0x140017382  jmp     loc_140017642
0x140017387  movzx   eax, word ptr [rcx+46h]
0x14001738b  movzx   edx, [rsp+68h+arg_30]
0x140017393  ror     ax, 8
0x140017397  mov     r11d, edx
0x14001739a  mov     [rdi], ax
0x14001739d  mov     eax, [rcx+40h]
0x1400173a0  mov     [rdi+8], eax
0x1400173a3  movzx   eax, word ptr [rcx+44h]
0x1400173a7  mov     [rdi+0Ch], ax
0x1400173ab  mov     [rdi+4], dl
0x1400173ae  mov     byte ptr [rdi+5], 0
0x1400173b2  mov     rax, [rcx+28h]
0x1400173b6  movzx   ecx, word ptr [rax+30h]
0x1400173ba  ror     cx, 8
0x1400173be  mov     [rdi+2], cx
0x1400173c2  mov     ecx, edx
0x1400173c4  test    dl, dl
0x1400173c6  jz      loc_140017498
0x1400173cc  sub     ecx, 4
0x1400173cf  jz      loc_14001745B
0x1400173d5  cmp     ecx, 1
0x1400173d8  jz      short loc_140017409
0x1400173da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400173e1  lea     rax, WPP_GLOBAL_Control
0x1400173e8  cmp     rcx, rax
0x1400173eb  jz      loc_1400174DC
0x1400173f1  mov     eax, [rcx+2Ch]
0x1400173f4  test    al, 2
0x1400173f6  jz      loc_1400174DC
0x1400173fc  mov     edx, 18h
0x140017401  mov     r9d, r11d
0x140017404  jmp     loc_1400174CC
0x140017409  mov     r9d, [rsp+68h+arg_20]
0x140017411  mov     eax, r9d
0x140017414  and     eax, 0C69h
0x140017419  cmp     r9d, eax
0x14001741c  jz      short loc_14001744A
0x14001741e  mov     rcx, cs:WPP_GLOBAL_Control
0x140017425  lea     rax, WPP_GLOBAL_Control
0x14001742c  cmp     rcx, rax
0x14001742f  jz      loc_1400174DC
0x140017435  mov     eax, [rcx+2Ch]
0x140017438  test    al, 2
0x14001743a  jz      loc_1400174DC
0x140017440  mov     edx, 17h
0x140017445  jmp     loc_1400174CC
0x14001744a  mov     ebx, 18h
0x14001744f  test    r9d, 800h
0x140017456  jmp     loc_1400174F2
0x14001745b  mov     r9d, [rsp+68h+arg_20]
0x140017463  mov     eax, r9d
0x140017466  and     eax, 0C69h
0x14001746b  cmp     r9d, eax
0x14001746e  jz      short loc_140017491
0x140017470  mov     rcx, cs:WPP_GLOBAL_Control
0x140017477  lea     rax, WPP_GLOBAL_Control
0x14001747e  cmp     rcx, rax
0x140017481  jz      short loc_1400174DC
0x140017483  mov     eax, [rcx+2Ch]
0x140017486  test    al, 2
0x140017488  jz      short loc_1400174DC
0x14001748a  mov     edx, 16h
0x14001748f  jmp     short loc_1400174CC
0x140017491  mov     ebx, 18h
0x140017496  jmp     short loc_1400174F8
0x140017498  mov     r9d, [rsp+68h+arg_20]
0x1400174a0  mov     eax, r9d
0x1400174a3  and     eax, 1EBC8h
0x1400174a8  cmp     r9d, eax
0x1400174ab  jz      short loc_1400174E6
0x1400174ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400174b4  lea     rax, WPP_GLOBAL_Control
0x1400174bb  cmp     rcx, rax
0x1400174be  jz      short loc_1400174DC
0x1400174c0  mov     eax, [rcx+2Ch]
0x1400174c3  test    al, 2
0x1400174c5  jz      short loc_1400174DC
0x1400174c7  mov     edx, 15h
0x1400174cc  mov     rcx, [rcx+18h]
0x1400174d0  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x1400174d7  call    WPP_SF_d
0x1400174dc  mov     eax, 0C000000Dh
0x1400174e1  jmp     loc_140017642
0x1400174e6  mov     ebx, 24h ; '$'
0x1400174eb  test    r9d, 12A00h
0x1400174f2  jz      short loc_1400174F8
0x1400174f4  mov     byte ptr [rdi+5], 2
0x1400174f8  cmp     r8w, bx
0x1400174fc  jnb     short loc_14001753A
0x1400174fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140017505  lea     rax, WPP_GLOBAL_Control
0x14001750c  cmp     rcx, rax
0x14001750f  jz      short loc_140017530
0x140017511  mov     eax, [rcx+2Ch]
0x140017514  test    al, 2
0x140017516  jz      short loc_140017530
0x140017518  mov     rcx, [rcx+18h]
0x14001751c  mov     r9d, r8d
0x14001751f  movzx   eax, bx
0x140017522  mov     dword ptr [rsp+68h+var_40], r11d
0x140017527  mov     [rsp+68h+var_48], eax
0x14001752b  call    WPP_SF_DdD
0x140017530  mov     eax, 0C0000173h
0x140017535  jmp     loc_140017642
0x14001753a  xor     esi, esi
0x14001753c  test    r9d, r9d
0x14001753f  jz      short loc_1400175BD
0x140017541  mov     rax, [rsp+68h+arg_28]
0x140017549  sub     r8w, bx
0x14001754d  mov     [rsp+68h+arg_0], r8w
0x140017553  mov     rdx, rbp
0x140017556  mov     [rsp+68h+var_40], rax
0x14001755b  mov     rcx, r10
0x14001755e  mov     [rsp+68h+var_48], r9d
0x140017563  lea     r9, [rsp+68h+arg_0]
0x140017568  movzx   r8d, bx
0x14001756c  add     r8, rdi
0x14001756f  call    InitDataSpmOptions
0x140017574  mov     esi, eax
0x140017576  test    eax, eax
0x140017578  jns     short loc_1400175B4
0x14001757a  mov     rcx, cs:WPP_GLOBAL_Control
0x140017581  lea     rax, WPP_GLOBAL_Control
0x140017588  cmp     rcx, rax
0x14001758b  jz      short loc_1400175AD
0x14001758d  mov     edx, [rcx+2Ch]
0x140017590  test    dl, 2
0x140017593  jz      short loc_1400175AD
0x140017595  mov     rcx, [rcx+18h]
0x140017599  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x1400175a0  mov     edx, 1Ah
0x1400175a5  mov     r9d, esi
0x1400175a8  call    WPP_SF_d
0x1400175ad  mov     eax, esi
0x1400175af  jmp     loc_140017642
0x1400175b4  or      byte ptr [rdi+5], 1
0x1400175b8  movzx   esi, [rsp+68h+arg_0]
0x1400175bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400175c4  lea     rax, WPP_GLOBAL_Control
0x1400175cb  cmp     rcx, rax
0x1400175ce  jz      short loc_140017600
0x1400175d0  mov     eax, [rcx+2Ch]
0x1400175d3  test    r15b, al
0x1400175d6  jz      short loc_140017600
0x1400175d8  mov     rcx, [rcx+18h]
0x1400175dc  mov     edx, 1Bh
0x1400175e1  movzx   eax, si
0x1400175e4  mov     r9, rdi
0x1400175e7  movzx   r8d, bx
0x1400175eb  mov     dword ptr [rsp+68h+var_40], eax
0x1400175ef  mov     [rsp+68h+var_48], r8d
0x1400175f4  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x1400175fb  call    WPP_SF_qDD
0x140017600  add     si, bx
0x140017603  mov     [r14], si
0x140017607  xor     eax, eax
0x140017609  jmp     short loc_140017642
0x14001760b  mov     rcx, cs:WPP_GLOBAL_Control
0x140017612  lea     rax, WPP_GLOBAL_Control
0x140017619  cmp     rcx, rax
0x14001761c  jz      short loc_14001763D
0x14001761e  mov     eax, [rcx+2Ch]
0x140017621  test    al, 2
0x140017623  jz      short loc_14001763D
0x140017625  mov     rcx, [rcx+18h]
0x140017629  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140017630  mov     edx, 13h
0x140017635  mov     r9, r10
0x140017638  call    WPP_SF_q
0x14001763d  mov     eax, 0C0000001h
0x140017642  add     rsp, 38h
0x140017646  pop     r15
0x140017648  pop     r14
0x14001764a  pop     rdi
0x14001764b  pop     rsi
0x14001764c  pop     rbp
0x14001764d  pop     rbx
0x14001764e  retn
```

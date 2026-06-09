# UdfFindLogicalVolumeIntegrityDescriptor

- ea: `0x1400491d0`
- end: `0x1400494f9`
- name: `UdfFindLogicalVolumeIntegrityDescriptor`
- size: `809`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140003148`
- `0x140049f80`

## callees

- `0x140004340`
- `0x14000ca10`
- `0x14000cad4`
- `0x14001093c`
- `0x1400134f8`
- `0x14001c080`
- `0x140049020`
- `0x1400491d0`
- `0x140049bb0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004945a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004945a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400492a7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400492a7`

## pseudocode

```c
__int64 __fastcall UdfFindLogicalVolumeIntegrityDescriptor(__int64 a1, __int64 a2, _DWORD *a3, unsigned int **a4)
{
  unsigned int *v7; // rbx
  int v8; // edi
  int v9; // esi
  int v10; // ecx
  unsigned int i; // r14d
  SIZE_T v12; // rsi
  unsigned int *PoolWithTag; // rax
  __int16 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // ecx
  int v17; // r8d
  int v18; // edx
  unsigned int *v19; // rax
  int v22; // [rsp+A0h] [rbp+18h]

  v7 = 0;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
  {
    WPP_SF_qqDD(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), &WPP_GLOBAL_Control, a3, a2, a3, a3[1], *a3);
  }
  v8 = *a3;
  if ( !*a3 || (v22 = 64, v9 = 0, v10 = *(_DWORD *)(a2 + 68), ((v10 - 1) & v8) != 0) )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
    {
      WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 60, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
    }
    return 3221225522LL;
  }
  else
  {
    for ( i = a3[1]; v8; ++i )
    {
      if ( !v7 )
      {
        v12 = ((-v10 & (v10 + 511)) + 4095) & 0xFFFFF000;
        PoolWithTag = (unsigned int *)ExAllocatePoolWithTag((POOL_TYPE)1552, v12, 0x34666455u);
        v7 = PoolWithTag;
        if ( !ExPoolZeroingNativelySupported )
        {
          if ( PoolWithTag )
            memset(PoolWithTag, 0, v12);
        }
      }
      v9 = UdfReadWriteSectors(
             a1,
             (union _LARGE_INTEGER)((unsigned __int64)i << *(_DWORD *)(a2 + 72)),
             -*(_DWORD *)(a2 + 68) & (unsigned int)(*(_DWORD *)(a2 + 68) + 511),
             1,
             v7,
             *(PDEVICE_OBJECT *)(a2 + 24),
             0);
      if ( v9 < 0 )
        break;
      v14 = *(_WORD *)v7;
      if ( !*(_WORD *)v7 )
        break;
      if ( (unsigned __int16)(v14 - 8) > 1u || !UdfVerifyDescriptor(a1, (__int64)v7, v14, 0x200u, i, 1) )
        goto LABEL_20;
      if ( *(_WORD *)v7 == 8 )
        break;
      v15 = v7[7];
      if ( ((_DWORD)v15 || v7[18] != *(unsigned __int16 *)(*(_QWORD *)(a2 + 16) + 4LL)) && (_DWORD)v15 != 1 )
      {
LABEL_20:
        v9 = -1073741774;
        break;
      }
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
      {
        WPP_SF_dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          61,
          WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
          v15,
          i);
      }
      v16 = v7[8];
      if ( v16 )
      {
        v17 = --v22;
        v18 = *(_DWORD *)(a2 + 68);
        if ( ((v18 - 1) & v16) != 0 || !v17 )
          goto LABEL_20;
        v8 = v16 + v18;
        i = v7[9] - 1;
      }
      v19 = *a4;
      *a4 = v7;
      v7 = v19;
      v10 = *(_DWORD *)(a2 + 68);
      v8 -= v10;
    }
    if ( v7 )
      ExFreePoolWithTag(v7, 0);
    if ( !*a4 )
      v9 = -1073741774;
    if ( v9 < 0 )
      UdfFreePool(a4);
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 62, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
    }
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x1400491d0  mov     r11, rsp
0x1400491d3  mov     [r11+10h], rbx
0x1400491d7  mov     [r11+8], rcx
0x1400491db  push    rsi
0x1400491dc  push    rdi
0x1400491dd  push    r12
0x1400491df  push    r13
0x1400491e1  push    r14
0x1400491e3  sub     rsp, 60h
0x1400491e7  mov     r12, r9
0x1400491ea  mov     r14, r8
0x1400491ed  mov     r13, rdx
0x1400491f0  xor     r10d, r10d
0x1400491f3  mov     ebx, r10d
0x1400491f6  mov     [r11-38h], rbx
0x1400491fa  lea     rdx, WPP_GLOBAL_Control
0x140049201  mov     rcx, cs:WPP_GLOBAL_Control
0x140049208  cmp     rcx, rdx
0x14004920b  jz      short loc_14004923F
0x14004920d  test    dword ptr [rcx+2Ch], 800h
0x140049214  jz      short loc_14004923F
0x140049216  mov     eax, [r8]
0x140049219  mov     [rsp+88h+var_58], eax
0x14004921d  mov     eax, [r8+4]
0x140049221  mov     dword ptr [rsp+88h+var_60], eax
0x140049225  mov     [r11-68h], r8
0x140049229  mov     r9, r13
0x14004922c  mov     rcx, [rcx+18h]
0x140049230  call    WPP_SF_qqDD
0x140049235  xor     r10d, r10d
0x140049238  lea     rdx, WPP_GLOBAL_Control
0x14004923f  mov     edi, [r14]
0x140049242  test    edi, edi
0x140049244  jz      loc_1400494B4
0x14004924a  mov     [rsp+88h+arg_10], 40h ; '@'
0x140049255  mov     esi, r10d
0x140049258  mov     ecx, [r13+44h]
0x14004925c  lea     eax, [rcx-1]
0x14004925f  test    edi, eax
0x140049261  jnz     loc_1400494B4
0x140049267  mov     [rsp+88h+var_48], edi
0x14004926b  mov     r14d, [r14+4]
0x14004926f  mov     [rsp+88h+var_44], r14d
0x140049274  test    edi, edi
0x140049276  jz      loc_14004944B
0x14004927c  test    rbx, rbx
0x14004927f  jnz     short loc_1400492DC
0x140049281  lea     esi, [rcx+1FFh]
0x140049287  neg     ecx
0x140049289  and     esi, ecx
0x14004928b  add     esi, 0FFFh
0x140049291  mov     eax, 0FFFFF000h
0x140049296  and     rsi, rax
0x140049299  mov     r8d, 34666455h; Tag
0x14004929f  mov     rdx, rsi; NumberOfBytes
0x1400492a2  mov     ecx, 610h; PoolType
0x1400492a7  call    cs:__imp_ExAllocatePoolWithTag
0x1400492ae  nop     dword ptr [rax+rax+00h]
0x1400492b3  mov     rbx, rax
0x1400492b6  xor     r10d, r10d
0x1400492b9  cmp     cs:ExPoolZeroingNativelySupported, r10b
0x1400492c0  jnz     short loc_1400492D7
0x1400492c2  test    rax, rax
0x1400492c5  jz      short loc_1400492D7
0x1400492c7  mov     r8, rsi; Size
0x1400492ca  xor     edx, edx; Val
0x1400492cc  mov     rcx, rax; void *
0x1400492cf  call    memset
0x1400492d4  xor     r10d, r10d
0x1400492d7  mov     [rsp+88h+var_38], rbx
0x1400492dc  mov     eax, [r13+44h]
0x1400492e0  lea     r8d, [rax+1FFh]
0x1400492e7  neg     eax
0x1400492e9  and     r8d, eax
0x1400492ec  mov     edx, r14d
0x1400492ef  mov     ecx, [r13+48h]
0x1400492f3  shl     rdx, cl
0x1400492f6  mov     byte ptr [rsp+88h+var_58], r10b
0x1400492fb  mov     rax, [r13+18h]
0x1400492ff  mov     [rsp+88h+var_60], rax
0x140049304  mov     [rsp+88h+var_68], rbx
0x140049309  mov     r9b, 1
0x14004930c  mov     rcx, [rsp+88h+arg_0]
0x140049314  call    UdfReadWriteSectors
0x140049319  mov     esi, eax
0x14004931b  mov     [rsp+88h+var_40], eax
0x14004931f  xor     r10d, r10d
0x140049322  test    eax, eax
0x140049324  js      loc_14004944B
0x14004932a  movzx   r8d, word ptr [rbx]
0x14004932e  test    r8w, r8w
0x140049332  jz      loc_14004944B
0x140049338  lea     eax, [r8-8]
0x14004933c  lea     ecx, [r10+1]
0x140049340  cmp     ax, cx
0x140049343  ja      short loc_140049391
0x140049345  mov     dword ptr [rsp+88h+var_60], ecx
0x140049349  mov     dword ptr [rsp+88h+var_68], r14d
0x14004934e  mov     r9d, 200h
0x140049354  mov     rdx, rbx
0x140049357  mov     rcx, [rsp+88h+arg_0]
0x14004935f  call    UdfVerifyDescriptor
0x140049364  xor     r10d, r10d
0x140049367  test    al, al
0x140049369  jz      short loc_140049391
0x14004936b  cmp     word ptr [rbx], 8
0x14004936f  jz      loc_14004944B
0x140049375  mov     r9d, [rbx+1Ch]
0x140049379  test    r9d, r9d
0x14004937c  jnz     short loc_14004938B
0x14004937e  mov     rax, [r13+10h]
0x140049382  movzx   ecx, word ptr [rax+4]
0x140049386  cmp     [rbx+48h], ecx
0x140049389  jz      short loc_1400493A1
0x14004938b  cmp     r9d, 1
0x14004938f  jz      short loc_1400493A1
0x140049391  mov     edi, 0C0000032h
0x140049396  mov     esi, edi
0x140049398  mov     [rsp+88h+var_40], edi
0x14004939c  jmp     loc_140049450
0x1400493a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400493a8  lea     rax, WPP_GLOBAL_Control
0x1400493af  cmp     rcx, rax
0x1400493b2  jz      short loc_1400493DA
0x1400493b4  test    dword ptr [rcx+2Ch], 800h
0x1400493bb  jz      short loc_1400493DA
0x1400493bd  mov     edx, 3Dh ; '='
0x1400493c2  mov     dword ptr [rsp+88h+var_68], r14d
0x1400493c7  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x1400493ce  mov     rcx, [rcx+18h]
0x1400493d2  call    WPP_SF_dd
0x1400493d7  xor     r10d, r10d
0x1400493da  mov     ecx, [rbx+20h]
0x1400493dd  test    ecx, ecx
0x1400493df  jz      short loc_140049429
0x1400493e1  mov     [rsp+88h+var_48], ecx
0x1400493e5  mov     r14d, [rbx+24h]
0x1400493e9  mov     [rsp+88h+var_44], r14d
0x1400493ee  mov     r8d, [rsp+88h+arg_10]
0x1400493f6  dec     r8d
0x1400493f9  mov     [rsp+88h+arg_10], r8d
0x140049401  mov     [rsp+88h+var_3C], r8d
0x140049406  mov     edx, [r13+44h]
0x14004940a  lea     eax, [rdx-1]
0x14004940d  test    ecx, eax
0x14004940f  jnz     short loc_140049391
0x140049411  test    r8d, r8d
0x140049414  jz      loc_140049391
0x14004941a  lea     edi, [rcx+rdx]
0x14004941d  mov     [rsp+88h+var_48], edi
0x140049421  dec     r14d
0x140049424  mov     [rsp+88h+var_44], r14d
0x140049429  mov     rax, [r12]
0x14004942d  mov     [r12], rbx
0x140049431  mov     rbx, rax
0x140049434  mov     [rsp+88h+var_38], rax
0x140049439  mov     ecx, [r13+44h]
0x14004943d  sub     edi, ecx
0x14004943f  mov     [rsp+88h+var_48], edi
0x140049443  inc     r14d
0x140049446  jmp     loc_14004926F
0x14004944b  mov     edi, 0C0000032h
0x140049450  test    rbx, rbx
0x140049453  jz      short loc_140049469
0x140049455  xor     edx, edx; Tag
0x140049457  mov     rcx, rbx; P
0x14004945a  call    cs:__imp_ExFreePoolWithTag
0x140049461  nop     dword ptr [rax+rax+00h]
0x140049466  xor     r10d, r10d
0x140049469  cmp     [r12], r10
0x14004946d  cmovz   esi, edi
0x140049470  test    esi, esi
0x140049472  jns     short loc_14004947C
0x140049474  mov     rcx, r12
0x140049477  call    UdfFreePool
0x14004947c  mov     rcx, cs:WPP_GLOBAL_Control
0x140049483  lea     rax, WPP_GLOBAL_Control
0x14004948a  cmp     rcx, rax
0x14004948d  jz      short loc_1400494B0
0x14004948f  test    dword ptr [rcx+2Ch], 800h
0x140049496  jz      short loc_1400494B0
0x140049498  mov     edx, 3Eh ; '>'
0x14004949d  mov     r9d, esi
0x1400494a0  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x1400494a7  mov     rcx, [rcx+18h]
0x1400494ab  call    WPP_SF_d
0x1400494b0  mov     eax, esi
0x1400494b2  jmp     short loc_1400494E3
0x1400494b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400494bb  cmp     rcx, rdx
0x1400494be  jz      short loc_1400494DE
0x1400494c0  test    dword ptr [rcx+2Ch], 800h
0x1400494c7  jz      short loc_1400494DE
0x1400494c9  mov     edx, 3Ch ; '<'
0x1400494ce  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x1400494d5  mov     rcx, [rcx+18h]
0x1400494d9  call    WPP_SF_
0x1400494de  mov     eax, 0C0000032h
0x1400494e3  mov     rbx, [rsp+88h+arg_8]
0x1400494eb  add     rsp, 60h
0x1400494ef  pop     r14
0x1400494f1  pop     r13
0x1400494f3  pop     r12
0x1400494f5  pop     rdi
0x1400494f6  pop     rsi
0x1400494f7  retn
0x14005a26d  push    rbp
0x14005a26f  sub     rsp, 40h
0x14005a273  mov     rbp, rdx
0x14005a276  lea     rcx, [rbp+50h]
0x14005a27a  call    UdfFreePool
0x14005a27f  nop
0x14005a280  add     rsp, 40h
0x14005a284  pop     rbp
0x14005a285  retn
```

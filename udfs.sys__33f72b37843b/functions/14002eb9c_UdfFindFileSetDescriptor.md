# UdfFindFileSetDescriptor

- ea: `0x14002eb9c`
- end: `0x14002f005`
- name: `UdfFindFileSetDescriptor`
- size: `1129`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140003148`
- `0x140049f80`

## callees

- `0x140004340`
- `0x14000b128`
- `0x14000ca10`
- `0x14000cad4`
- `0x14001356c`
- `0x14001c080`
- `0x14002eb9c`
- `0x14003d810`
- `0x140049020`
- `0x140049bb0`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002ecad`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002ecad`

## pseudocode

```c
__int64 __fastcall UdfFindFileSetDescriptor(__int64 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  __int64 v5; // r10
  __int64 v6; // rdi
  unsigned int v7; // edx
  int v8; // r14d
  int v9; // ebx
  int v10; // ecx
  int i; // r12d
  SIZE_T v12; // rbx
  PVOID PoolWithTag; // rax
  unsigned int v14; // eax
  __int64 v15; // r9
  __int16 v16; // r8
  int v17; // ecx
  unsigned int v18; // edx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v23; // [rsp+30h] [rbp-78h]
  __int64 v24[9]; // [rsp+60h] [rbp-48h] BYREF
  unsigned __int16 v27; // [rsp+C0h] [rbp+18h]

  v5 = a2;
  v6 = 0;
  v24[0] = 0;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
  {
    WPP_SF_qqDDDD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      *(unsigned __int16 *)(a3 + 8),
      *(_DWORD *)a3 & 0x3FFFFFFF,
      a2,
      a3,
      *(unsigned __int16 *)(a3 + 8),
      *(_DWORD *)(a3 + 4),
      *(_DWORD *)a3 & 0x3FFFFFFF,
      *(_DWORD *)a3 >> 30);
    v5 = a2;
  }
  v7 = *(_DWORD *)a3;
  v8 = *(_DWORD *)a3 & 0x3FFFFFFF;
  if ( !v8 || v7 >= 0x40000000 || (v9 = 0, v10 = *(_DWORD *)(v5 + 68), (v7 & (v10 - 1) & 0x3FFFFFFF) != 0) )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
    {
      WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 64, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
    }
    return 3221225522LL;
  }
  else
  {
    v27 = *(_WORD *)(a3 + 8);
    for ( i = *(_DWORD *)(a3 + 4); v8; ++i )
    {
      if ( !v6 )
      {
        v12 = ((-v10 & (v10 + 511)) + 4095) & 0xFFFFF000;
        PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1552, v12, 0x31666455u);
        v6 = (__int64)PoolWithTag;
        if ( !ExPoolZeroingNativelySupported && PoolWithTag )
          memset(PoolWithTag, 0, v12);
        v24[0] = v6;
        v5 = a2;
      }
      v14 = UdfLookupPsnOfExtent(a1, v5, v27, i, *(_DWORD *)(v5 + 68));
      v15 = a2;
      LOBYTE(v23) = 0;
      LOBYTE(v15) = 1;
      v9 = UdfReadWriteSectors(
             a1,
             (unsigned __int64)v14 << *(_DWORD *)(a2 + 72),
             -*(_DWORD *)(a2 + 68) & (unsigned int)(*(_DWORD *)(a2 + 68) + 511),
             v15,
             v6,
             *(_QWORD *)(a2 + 24),
             v23);
      if ( v9 < 0 )
        break;
      v16 = *(_WORD *)v6;
      if ( !*(_WORD *)v6 )
        break;
      if ( v16 != 256 && v16 != 8 || !UdfVerifyDescriptor(a1, v6, v16, 0x200u, i, 1) )
        goto LABEL_19;
      if ( *(_WORD *)v6 == 8 )
        break;
      v17 = *(_DWORD *)(v6 + 448) & 0x3FFFFFFF;
      if ( v17 )
      {
        if ( *(_DWORD *)(v6 + 448) >= 0x40000000u )
          break;
        v5 = a2;
        v18 = *(_DWORD *)(a2 + 68);
        if ( ((v18 - 1) & v17) != 0 )
        {
          v19 = *(_QWORD *)&WPP_GLOBAL_Control;
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
          {
            v20 = 65;
            goto LABEL_27;
          }
          goto LABEL_19;
        }
        if ( *(_WORD *)(v6 + 456) != v27 )
        {
          v19 = *(_QWORD *)&WPP_GLOBAL_Control;
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
          {
            v20 = 66;
            goto LABEL_27;
          }
          goto LABEL_19;
        }
        v8 = v17 + v18;
        if ( v17 + v18 < v18 )
        {
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40000) != 0 )
          {
            WPP_SF_d(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
              67,
              WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
          }
          goto LABEL_19;
        }
        i = *(_DWORD *)(v6 + 452) - 1;
        if ( !*(_DWORD *)(v6 + 452) )
        {
          v19 = *(_QWORD *)&WPP_GLOBAL_Control;
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40000) != 0 )
          {
            v20 = 68;
LABEL_27:
            WPP_SF_(*(_QWORD *)(v19 + 24), v20, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
          }
LABEL_19:
          v9 = -1073741774;
          break;
        }
      }
      else
      {
        v5 = a2;
      }
      v21 = *a4;
      if ( !*a4 || *(_DWORD *)(v21 + 40) < *(_DWORD *)(v6 + 40) )
      {
        *a4 = v6;
        v6 = v21;
        v24[0] = v21;
      }
      v10 = *(_DWORD *)(v5 + 68);
      v8 -= v10;
    }
    UdfFreePool(v24);
    if ( !*a4 )
      v9 = -1073741489;
    if ( v9 < 0 )
      UdfFreePool(a4);
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 70, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
    }
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x14002eb9c  mov     r11, rsp
0x14002eb9f  mov     [r11+20h], r9
0x14002eba3  mov     [r11+10h], rdx
0x14002eba7  mov     [r11+8], rcx
0x14002ebab  push    rbx
0x14002ebac  push    rsi
0x14002ebad  push    rdi
0x14002ebae  push    r12
0x14002ebb0  push    r14
0x14002ebb2  push    r15
0x14002ebb4  sub     rsp, 78h
0x14002ebb8  mov     r12, r8
0x14002ebbb  mov     r10, rdx
0x14002ebbe  xor     esi, esi
0x14002ebc0  mov     edi, esi
0x14002ebc2  mov     [r11-48h], rsi
0x14002ebc6  lea     r15, WPP_GLOBAL_Control
0x14002ebcd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ebd4  cmp     rcx, r15
0x14002ebd7  jz      short loc_14002EC26
0x14002ebd9  test    dword ptr [rcx+2Ch], 800h
0x14002ebe0  jz      short loc_14002EC26
0x14002ebe2  mov     r8d, [r8]
0x14002ebe5  mov     eax, r8d
0x14002ebe8  shr     eax, 1Eh
0x14002ebeb  and     r8d, 3FFFFFFFh
0x14002ebf2  movzx   edx, word ptr [r12+8]
0x14002ebf8  mov     [rsp+0A8h+var_68], eax
0x14002ebfc  mov     [r11-70h], r8d
0x14002ec00  mov     eax, [r12+4]
0x14002ec05  mov     [rsp+0A8h+var_78], eax
0x14002ec09  mov     dword ptr [rsp+0A8h+var_80], edx
0x14002ec0d  mov     [rsp+0A8h+var_88], r12
0x14002ec12  mov     r9, r10
0x14002ec15  mov     rcx, [rcx+18h]
0x14002ec19  call    WPP_SF_qqDDDD
0x14002ec1e  mov     r10, [rsp+0A8h+arg_8]
0x14002ec26  mov     edx, [r12]
0x14002ec2a  mov     r14d, edx
0x14002ec2d  and     r14d, 3FFFFFFFh
0x14002ec34  jz      loc_14002EFC7
0x14002ec3a  cmp     edx, 40000000h
0x14002ec40  jnb     loc_14002EFC7
0x14002ec46  mov     ebx, esi
0x14002ec48  mov     ecx, [r10+44h]
0x14002ec4c  lea     eax, [rcx-1]
0x14002ec4f  and     eax, edx
0x14002ec51  test    eax, 3FFFFFFFh
0x14002ec56  jnz     loc_14002EFC7
0x14002ec5c  movzx   eax, word ptr [r12+8]
0x14002ec62  mov     [rsp+0A8h+arg_10], ax
0x14002ec6a  mov     [rsp+0A8h+var_54], r14d
0x14002ec6f  mov     r12d, [r12+4]
0x14002ec74  mov     [rsp+0A8h+var_50], r12d
0x14002ec79  test    r14d, r14d
0x14002ec7c  jz      loc_14002EF18
0x14002ec82  test    rdi, rdi
0x14002ec85  jnz     short loc_14002ECE4
0x14002ec87  lea     ebx, [rcx+1FFh]
0x14002ec8d  neg     ecx
0x14002ec8f  and     ebx, ecx
0x14002ec91  add     ebx, 0FFFh
0x14002ec97  mov     eax, 0FFFFF000h
0x14002ec9c  and     rbx, rax
0x14002ec9f  mov     r8d, 31666455h; Tag
0x14002eca5  mov     rdx, rbx; NumberOfBytes
0x14002eca8  mov     ecx, 610h; PoolType
0x14002ecad  call    cs:__imp_ExAllocatePoolWithTag
0x14002ecb4  nop     dword ptr [rax+rax+00h]
0x14002ecb9  mov     rdi, rax
0x14002ecbc  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14002ecc3  jnz     short loc_14002ECD7
0x14002ecc5  test    rax, rax
0x14002ecc8  jz      short loc_14002ECD7
0x14002ecca  mov     r8, rbx; Size
0x14002eccd  xor     edx, edx; Val
0x14002eccf  mov     rcx, rax; void *
0x14002ecd2  call    memset
0x14002ecd7  mov     [rsp+0A8h+var_48], rdi
0x14002ecdc  mov     r10, [rsp+0A8h+arg_8]
0x14002ece4  mov     eax, [r10+44h]
0x14002ece8  mov     dword ptr [rsp+0A8h+var_88], eax
0x14002ecec  mov     r9d, r12d
0x14002ecef  movzx   r8d, [rsp+0A8h+arg_10]
0x14002ecf8  mov     rdx, r10
0x14002ecfb  mov     rcx, [rsp+0A8h+arg_0]
0x14002ed03  call    UdfLookupPsnOfExtent
0x14002ed08  mov     edx, eax
0x14002ed0a  mov     r9, [rsp+0A8h+arg_8]
0x14002ed12  mov     eax, [r9+44h]
0x14002ed16  lea     r8d, [rax+1FFh]
0x14002ed1d  neg     eax
0x14002ed1f  and     r8d, eax
0x14002ed22  mov     ecx, [r9+48h]
0x14002ed26  shl     rdx, cl
0x14002ed29  mov     byte ptr [rsp+0A8h+var_78], sil
0x14002ed2e  mov     rax, [r9+18h]
0x14002ed32  mov     [rsp+0A8h+var_80], rax
0x14002ed37  mov     [rsp+0A8h+var_88], rdi
0x14002ed3c  mov     r9b, 1
0x14002ed3f  mov     rcx, [rsp+0A8h+arg_0]
0x14002ed47  call    UdfReadWriteSectors
0x14002ed4c  mov     ebx, eax
0x14002ed4e  mov     [rsp+0A8h+var_58], eax
0x14002ed52  test    eax, eax
0x14002ed54  js      loc_14002EF18
0x14002ed5a  movzx   r8d, word ptr [rdi]
0x14002ed5e  test    r8w, r8w
0x14002ed62  jz      loc_14002EF18
0x14002ed68  mov     eax, 100h
0x14002ed6d  cmp     r8w, ax
0x14002ed71  jz      short loc_14002ED7A
0x14002ed73  cmp     r8w, 8
0x14002ed78  jnz     short loc_14002EDA1
0x14002ed7a  mov     dword ptr [rsp+0A8h+var_80], 1
0x14002ed82  mov     dword ptr [rsp+0A8h+var_88], r12d
0x14002ed87  mov     r9d, 200h
0x14002ed8d  mov     rdx, rdi
0x14002ed90  mov     rcx, [rsp+0A8h+arg_0]
0x14002ed98  call    UdfVerifyDescriptor
0x14002ed9d  test    al, al
0x14002ed9f  jnz     short loc_14002EDAF
0x14002eda1  mov     ebx, 0C0000032h
0x14002eda6  mov     [rsp+0A8h+var_58], ebx
0x14002edaa  jmp     loc_14002EF18
0x14002edaf  cmp     word ptr [rdi], 8
0x14002edb3  jz      loc_14002EF18
0x14002edb9  mov     eax, [rdi+1C0h]
0x14002edbf  mov     ecx, eax
0x14002edc1  and     ecx, 3FFFFFFFh
0x14002edc7  jz      loc_14002EED9
0x14002edcd  cmp     eax, 40000000h
0x14002edd2  jnb     loc_14002EF18
0x14002edd8  mov     [rsp+0A8h+var_54], ecx
0x14002eddc  mov     r10, [rsp+0A8h+arg_8]
0x14002ede4  mov     edx, [r10+44h]
0x14002ede8  lea     eax, [rdx-1]
0x14002edeb  test    ecx, eax
0x14002eded  jz      short loc_14002EE1B
0x14002edef  mov     rcx, cs:WPP_GLOBAL_Control
0x14002edf6  cmp     rcx, r15
0x14002edf9  jz      short loc_14002EDA1
0x14002edfb  mov     eax, [rcx+2Ch]
0x14002edfe  bt      eax, 0Bh
0x14002ee02  jnb     short loc_14002EDA1
0x14002ee04  mov     edx, 41h ; 'A'
0x14002ee09  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14002ee10  mov     rcx, [rcx+18h]
0x14002ee14  call    WPP_SF_
0x14002ee19  jmp     short loc_14002EDA1
0x14002ee1b  movzx   eax, [rsp+0A8h+arg_10]
0x14002ee23  cmp     [rdi+1C8h], ax
0x14002ee2a  jz      short loc_14002EE50
0x14002ee2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ee33  cmp     rcx, r15
0x14002ee36  jz      loc_14002EDA1
0x14002ee3c  mov     eax, [rcx+2Ch]
0x14002ee3f  bt      eax, 0Bh
0x14002ee43  jnb     loc_14002EDA1
0x14002ee49  mov     edx, 42h ; 'B'
0x14002ee4e  jmp     short loc_14002EE09
0x14002ee50  mov     r12d, [rdi+1C4h]
0x14002ee57  mov     [rsp+0A8h+var_50], r12d
0x14002ee5c  lea     r14d, [rcx+rdx]
0x14002ee60  mov     [rsp+0A8h+var_54], r14d
0x14002ee65  cmp     r14d, edx
0x14002ee68  jnb     short loc_14002EEA4
0x14002ee6a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ee71  cmp     rcx, r15
0x14002ee74  jz      loc_14002EDA1
0x14002ee7a  mov     eax, [rcx+2Ch]
0x14002ee7d  bt      eax, 12h
0x14002ee81  jnb     loc_14002EDA1
0x14002ee87  mov     edx, 43h ; 'C'
0x14002ee8c  mov     r9d, r14d
0x14002ee8f  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14002ee96  mov     rcx, [rcx+18h]
0x14002ee9a  call    WPP_SF_d
0x14002ee9f  jmp     loc_14002EDA1
0x14002eea4  dec     r12d
0x14002eea7  mov     [rsp+0A8h+var_50], r12d
0x14002eeac  cmp     r12d, 0FFFFFFFFh
0x14002eeb0  jnz     short loc_14002EEE1
0x14002eeb2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002eeb9  cmp     rcx, r15
0x14002eebc  jz      loc_14002EDA1
0x14002eec2  mov     eax, [rcx+2Ch]
0x14002eec5  bt      eax, 12h
0x14002eec9  jnb     loc_14002EDA1
0x14002eecf  mov     edx, 44h ; 'D'
0x14002eed4  jmp     loc_14002EE09
0x14002eed9  mov     r10, [rsp+0A8h+arg_8]
0x14002eee1  mov     r9, [rsp+0A8h+arg_18]
0x14002eee9  mov     rcx, [r9]
0x14002eeec  test    rcx, rcx
0x14002eeef  jz      short loc_14002EEF9
0x14002eef1  mov     eax, [rdi+28h]
0x14002eef4  cmp     [rcx+28h], eax
0x14002eef7  jnb     short loc_14002EF04
0x14002eef9  mov     [r9], rdi
0x14002eefc  mov     rdi, rcx
0x14002eeff  mov     [rsp+0A8h+var_48], rcx
0x14002ef04  mov     ecx, [r10+44h]
0x14002ef08  sub     r14d, ecx
0x14002ef0b  mov     [rsp+0A8h+var_54], r14d
0x14002ef10  inc     r12d
0x14002ef13  jmp     loc_14002EC74
0x14002ef18  lea     rcx, [rsp+0A8h+var_48]
0x14002ef1d  call    UdfFreePool
0x14002ef22  jmp     short loc_14002EF7A
0x14002ef24  mov     rax, [rsp+0A8h+arg_0]
0x14002ef2c  mov     ebx, [rax+18h]
0x14002ef2f  lea     rax, WPP_GLOBAL_Control
0x14002ef36  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ef3d  cmp     rcx, rax
0x14002ef40  jz      short loc_14002EF63
0x14002ef42  test    dword ptr [rcx+2Ch], 800h
0x14002ef49  jz      short loc_14002EF63
0x14002ef4b  mov     edx, 45h ; 'E'
0x14002ef50  mov     r9d, ebx
0x14002ef53  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14002ef5a  mov     rcx, [rcx+18h]
0x14002ef5e  call    WPP_SF_d
0x14002ef63  mov     eax, 0C0000032h
0x14002ef68  cmp     ebx, 0C0000102h
0x14002ef6e  cmovz   ebx, eax
0x14002ef71  xor     esi, esi
0x14002ef73  lea     r15, WPP_GLOBAL_Control
0x14002ef7a  mov     eax, 0C000014Fh
0x14002ef7f  mov     rcx, [rsp+0A8h+arg_18]
0x14002ef87  cmp     [rcx], rsi
0x14002ef8a  cmovz   ebx, eax
0x14002ef8d  test    ebx, ebx
0x14002ef8f  jns     short loc_14002EF96
0x14002ef91  call    UdfFreePool
0x14002ef96  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ef9d  cmp     rcx, r15
0x14002efa0  jz      short loc_14002EFC3
0x14002efa2  test    dword ptr [rcx+2Ch], 800h
0x14002efa9  jz      short loc_14002EFC3
0x14002efab  mov     edx, 46h ; 'F'
0x14002efb0  mov     r9d, ebx
0x14002efb3  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14002efba  mov     rcx, [rcx+18h]
0x14002efbe  call    WPP_SF_d
0x14002efc3  mov     eax, ebx
0x14002efc5  jmp     short loc_14002EFF6
0x14002efc7  mov     rcx, cs:WPP_GLOBAL_Control
0x14002efce  cmp     rcx, r15
0x14002efd1  jz      short loc_14002EFF1
0x14002efd3  test    dword ptr [rcx+2Ch], 800h
0x14002efda  jz      short loc_14002EFF1
0x14002efdc  mov     edx, 40h ; '@'
0x14002efe1  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14002efe8  mov     rcx, [rcx+18h]
0x14002efec  call    WPP_SF_
0x14002eff1  mov     eax, 0C0000032h
0x14002eff6  add     rsp, 78h
0x14002effa  pop     r15
0x14002effc  pop     r14
0x14002effe  pop     r12
0x14002f000  pop     rdi
0x14002f001  pop     rsi
0x14002f002  pop     rbx
0x14002f003  retn
0x14005b335  push    rbp
0x14005b337  sub     rsp, 50h
0x14005b33b  mov     rbp, rdx
0x14005b33e  lea     rcx, [rbp+60h]
0x14005b342  call    UdfFreePool
0x14005b347  nop
0x14005b348  add     rsp, 50h
0x14005b34c  pop     rbp
0x14005b34d  retn
0x14005b34f  push    rbp
0x14005b351  sub     rsp, 50h
0x14005b355  mov     rbp, rdx
0x14005b358  mov     rdx, rcx
0x14005b35b  mov     rcx, [rbp+0B0h]
0x14005b362  call    UdfExceptionFilter
0x14005b367  nop
0x14005b368  add     rsp, 50h
0x14005b36c  pop     rbp
0x14005b36d  retn
```

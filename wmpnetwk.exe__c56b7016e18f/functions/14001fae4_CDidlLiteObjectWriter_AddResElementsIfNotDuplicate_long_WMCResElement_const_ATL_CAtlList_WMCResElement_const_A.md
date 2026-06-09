# CDidlLiteObjectWriter::AddResElementsIfNotDuplicate(long,_WMCResElement const *,ATL::CAtlList<_WMCResElement const *,ATL::CElementTraits<_WMCResElement const *>> &)

- ea: `0x14001fae4`
- end: `0x14001fe71`
- name: `?AddResElementsIfNotDuplicate@CDidlLiteObjectWriter@@KAXJPEBU_WMCResElement@@AEAV?$CAtlList@PEBU_WMCResElement@@V?$CElementTraits@PEBU_WMCResElement@@@ATL@@@ATL@@@Z`
- size: `909`
- prototype: `void __fastcall(int, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001efac`
- `0x14001f110`

## callees

- `0x140018144`
- `0x14001fae4`
- `0x14003e4e0`
- `0x14003f17c`
- `0x14003f1bc`
- `0x140059f38`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14001fb7e`
- `KERNEL32!CompareStringW` at `0x14001fbc7`
- `KERNEL32!CompareStringW` at `0x14001fcca`
- `KERNEL32!CompareStringW` at `0x14001fb7e`
- `KERNEL32!CompareStringW` at `0x14001fbc7`
- `KERNEL32!CompareStringW` at `0x14001fcca`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall CDidlLiteObjectWriter::AddResElementsIfNotDuplicate(int a1, __int64 a2, __int64 a3)
{
  __int64 v5; // r8
  PVOID *v6; // r10
  __int64 i; // r12
  __int64 v8; // rsi
  _QWORD *v9; // r14
  unsigned int v10; // r15d
  __int64 v11; // rbx
  _QWORD *v12; // rbp
  BOOL v13; // ebp
  __int64 v14; // rbx
  __int64 *v15; // rcx
  __int64 v16; // rax
  __int64 **v17; // rax

  v5 = a2;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      80,
      &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids,
      (unsigned int)a1,
      a2,
      a3);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v5 = a2;
  }
  for ( i = 0; (int)i < a1; i = (unsigned int)(i + 1) )
  {
    v8 = v5 + 96 * i;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    {
      WPP_SF_qq(v6[2], 76, &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids, v8, a3);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v9 = *(_QWORD **)a3;
    v10 = 0;
    while ( v9 )
    {
      v11 = v9[2];
      v12 = (_QWORD *)*v9;
      if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)v11, -1, *(PCNZWCH *)v8, -1) == 2 )
      {
        v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_17:
        v10 = 1;
        break;
      }
      v9 = v12;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids, v11, v8);
      }
      v13 = 0;
      if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v11 + 40), -1, *(PCNZWCH *)(v8 + 40), -1) == 2
        && CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v11 + 48), -1, *(PCNZWCH *)(v8 + 48), -1) == 2
        && *(_DWORD *)(v11 + 24) == *(_DWORD *)(v8 + 24)
        && *(_DWORD *)(v11 + 28) == *(_DWORD *)(v8 + 28)
        && *(_DWORD *)(v11 + 32) == *(_DWORD *)(v8 + 32)
        && *(_DWORD *)(v11 + 56) == *(_DWORD *)(v8 + 56)
        && *(_DWORD *)(v11 + 60) == *(_DWORD *)(v8 + 60)
        && *(_DWORD *)(v11 + 64) == *(_DWORD *)(v8 + 64) )
      {
        v13 = *(_DWORD *)(v11 + 68) == *(_DWORD *)(v8 + 68);
      }
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids, v13);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v13 )
        goto LABEL_17;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    {
      WPP_SF_d(v6[2], 77, &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids, v10);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !v10 )
    {
      v14 = *(_QWORD *)(a3 + 8);
      ATL::CAtlList<_WMCResElement const *,ATL::CElementTraits<_WMCResElement const *>>::GetFreeNode(a3);
      v15 = *(__int64 **)(a3 + 32);
      v16 = *v15;
      v15[2] = v8;
      *(_QWORD *)(a3 + 32) = v16;
      v15[1] = v14;
      *v15 = 0;
      ++*(_QWORD *)(a3 + 16);
      v17 = *(__int64 ***)(a3 + 8);
      if ( v17 )
        *v17 = v15;
      else
        *(_QWORD *)a3 = v15;
      *(_QWORD *)(a3 + 8) = v15;
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v5 = a2;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_q(v6[2], 81, &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids, *(_QWORD *)(a3 + 16));
}

```

## disassembly

```asm
0x14001fae4  mov     [rsp+arg_8], rdx
0x14001fae9  push    rbx
0x14001faea  push    rbp
0x14001faeb  push    rsi
0x14001faec  push    rdi
0x14001faed  push    r12
0x14001faef  push    r13
0x14001faf1  push    r14
0x14001faf3  push    r15
0x14001faf5  sub     rsp, 38h
0x14001faf9  mov     rdi, r8
0x14001fafc  mov     r13d, ecx
0x14001faff  mov     r8, rdx
0x14001fb02  mov     r10, cs:WPP_GLOBAL_Control
0x14001fb09  lea     rbx, WPP_GLOBAL_Control
0x14001fb10  cmp     r10, rbx
0x14001fb13  jz      short loc_14001FB20
0x14001fb15  test    byte ptr [r10+1Ch], 2
0x14001fb1a  jnz     loc_14001FD8F
0x14001fb20  xor     r12d, r12d
0x14001fb23  test    r13d, r13d
0x14001fb26  jle     loc_14001FC8E
0x14001fb2c  lea     edx, [r12+1]; dwCmpFlags
0x14001fb31  lea     rsi, [r12+r12*2]
0x14001fb35  shl     rsi, 5
0x14001fb39  add     rsi, r8
0x14001fb3c  cmp     r10, rbx
0x14001fb3f  jz      short loc_14001FB4C
0x14001fb41  test    byte ptr [r10+1Ch], 2
0x14001fb46  jnz     loc_14001FDD0
0x14001fb4c  mov     r14, [rdi]
0x14001fb4f  xor     r15d, r15d
0x14001fb52  test    r14, r14
0x14001fb55  jz      loc_14001FC19
0x14001fb5b  mov     rbx, [r14+10h]
0x14001fb5f  or      r9d, 0FFFFFFFFh; cchCount1
0x14001fb63  mov     rax, [rsi]
0x14001fb66  mov     ecx, 7Fh; Locale
0x14001fb6b  mov     rbp, [r14]
0x14001fb6e  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x14001fb76  mov     r8, [rbx]; lpString1
0x14001fb79  mov     [rsp+78h+lpString2], rax; lpString2
0x14001fb7e  call    cs:__imp_CompareStringW
0x14001fb84  cmp     eax, 2
0x14001fb87  jz      short loc_14001FC03
0x14001fb89  mov     r14, rbp
0x14001fb8c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fb93  lea     rax, WPP_GLOBAL_Control
0x14001fb9a  cmp     rcx, rax
0x14001fb9d  jz      short loc_14001FBA9
0x14001fb9f  test    byte ptr [rcx+1Ch], 2
0x14001fba3  jnz     loc_14001FD34
0x14001fba9  mov     rax, [rsi+28h]
0x14001fbad  xor     ebp, ebp
0x14001fbaf  mov     r8, [rbx+28h]; lpString1
0x14001fbb3  or      r9d, 0FFFFFFFFh; cchCount1
0x14001fbb7  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x14001fbbc  mov     [rsp+78h+lpString2], rax; lpString2
0x14001fbc1  lea     edx, [rbp+1]; dwCmpFlags
0x14001fbc4  lea     ecx, [rbp+7Fh]; Locale
0x14001fbc7  call    cs:__imp_CompareStringW
0x14001fbcd  cmp     eax, 2
0x14001fbd0  jz      loc_14001FCAD
0x14001fbd6  mov     r10, cs:WPP_GLOBAL_Control
0x14001fbdd  lea     rbx, WPP_GLOBAL_Control
0x14001fbe4  cmp     r10, rbx
0x14001fbe7  jz      short loc_14001FBF4
0x14001fbe9  test    byte ptr [r10+1Ch], 2
0x14001fbee  jnz     loc_14001FD60
0x14001fbf4  mov     edx, 1
0x14001fbf9  test    ebp, ebp
0x14001fbfb  jz      loc_14001FB52
0x14001fc01  jmp     short loc_14001FC11
0x14001fc03  mov     r10, cs:WPP_GLOBAL_Control
0x14001fc0a  lea     rbx, WPP_GLOBAL_Control
0x14001fc11  mov     edx, 1
0x14001fc16  mov     r15d, edx
0x14001fc19  cmp     r10, rbx
0x14001fc1c  jz      short loc_14001FC29
0x14001fc1e  test    byte ptr [r10+1Ch], 2
0x14001fc23  jnz     loc_14001FE09
0x14001fc29  test    r15d, r15d
0x14001fc2c  jnz     short loc_14001FC7A
0x14001fc2e  mov     rbx, [rdi+8]
0x14001fc32  mov     rcx, rdi
0x14001fc35  call    ?GetFreeNode@?$CAtlList@PEBU_WMCResElement@@V?$CElementTraits@PEBU_WMCResElement@@@ATL@@@ATL@@AEAAXXZ; ATL::CAtlList<_WMCResElement const *,ATL::CElementTraits<_WMCResElement const *>>::GetFreeNode(void)
0x14001fc3a  mov     rcx, [rdi+20h]
0x14001fc3e  lea     edx, [r15+1]
0x14001fc42  mov     rax, [rcx]
0x14001fc45  mov     [rcx+10h], rsi
0x14001fc49  mov     [rdi+20h], rax
0x14001fc4d  mov     [rcx+8], rbx
0x14001fc51  mov     qword ptr [rcx], 0
0x14001fc58  add     [rdi+10h], rdx
0x14001fc5c  mov     rax, [rdi+8]
0x14001fc60  test    rax, rax
0x14001fc63  jz      short loc_14001FCA8
0x14001fc65  mov     [rax], rcx
0x14001fc68  mov     [rdi+8], rcx
0x14001fc6c  lea     rbx, WPP_GLOBAL_Control
0x14001fc73  mov     r10, cs:WPP_GLOBAL_Control
0x14001fc7a  mov     r8, [rsp+78h+arg_8]
0x14001fc82  add     r12d, edx
0x14001fc85  cmp     r12d, r13d
0x14001fc88  jl      loc_14001FB31
0x14001fc8e  cmp     r10, rbx
0x14001fc91  jnz     loc_14001FE3D
0x14001fc97  add     rsp, 38h
0x14001fc9b  pop     r15
0x14001fc9d  pop     r14
0x14001fc9f  pop     r13
0x14001fca1  pop     r12
0x14001fca3  pop     rdi
0x14001fca4  pop     rsi
0x14001fca5  pop     rbp
0x14001fca6  pop     rbx
0x14001fca7  retn
0x14001fca8  mov     [rdi], rcx
0x14001fcab  jmp     short loc_14001FC68
0x14001fcad  mov     rax, [rsi+30h]
0x14001fcb1  or      ecx, 0FFFFFFFFh
0x14001fcb4  mov     r8, [rbx+30h]; lpString1
0x14001fcb8  mov     r9d, ecx; cchCount1
0x14001fcbb  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x14001fcbf  mov     [rsp+78h+lpString2], rax; lpString2
0x14001fcc4  lea     edx, [rcx+2]; dwCmpFlags
0x14001fcc7  lea     ecx, [rdx+7Eh]; Locale
0x14001fcca  call    cs:__imp_CompareStringW
0x14001fcd0  cmp     eax, 2
0x14001fcd3  jnz     loc_14001FBD6
0x14001fcd9  mov     eax, [rsi+18h]
0x14001fcdc  cmp     [rbx+18h], eax
0x14001fcdf  jnz     loc_14001FBD6
0x14001fce5  mov     eax, [rsi+1Ch]
0x14001fce8  cmp     [rbx+1Ch], eax
0x14001fceb  jnz     loc_14001FBD6
0x14001fcf1  mov     eax, [rsi+20h]
0x14001fcf4  cmp     [rbx+20h], eax
0x14001fcf7  jnz     loc_14001FBD6
0x14001fcfd  mov     eax, [rsi+38h]
0x14001fd00  cmp     [rbx+38h], eax
0x14001fd03  jnz     loc_14001FBD6
0x14001fd09  mov     eax, [rsi+3Ch]
0x14001fd0c  cmp     [rbx+3Ch], eax
0x14001fd0f  jnz     loc_14001FBD6
0x14001fd15  mov     eax, [rsi+40h]
0x14001fd18  cmp     [rbx+40h], eax
0x14001fd1b  jnz     loc_14001FBD6
0x14001fd21  mov     eax, [rsi+44h]
0x14001fd24  cmp     [rbx+44h], eax
0x14001fd27  mov     eax, 1
0x14001fd2c  cmovz   ebp, eax
0x14001fd2f  jmp     loc_14001FBD6
0x14001fd34  cmp     byte ptr [rcx+19h], 5
0x14001fd38  jb      loc_14001FBA9
0x14001fd3e  mov     rcx, [rcx+10h]
0x14001fd42  lea     r8, WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids
0x14001fd49  mov     edx, 4Ah ; 'J'
0x14001fd4e  mov     [rsp+78h+lpString2], rsi
0x14001fd53  mov     r9, rbx
0x14001fd56  call    WPP_SF_qq
0x14001fd5b  jmp     loc_14001FBA9
0x14001fd60  cmp     byte ptr [r10+19h], 5
0x14001fd65  jb      loc_14001FBF4
0x14001fd6b  mov     rcx, [r10+10h]
0x14001fd6f  lea     r8, WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids
0x14001fd76  mov     edx, 4Bh ; 'K'
0x14001fd7b  mov     r9d, ebp
0x14001fd7e  call    WPP_SF_d
0x14001fd83  mov     r10, cs:WPP_GLOBAL_Control
0x14001fd8a  jmp     loc_14001FBF4
0x14001fd8f  cmp     byte ptr [r10+19h], 5
0x14001fd94  jb      loc_14001FB20
0x14001fd9a  mov     rcx, [r10+10h]
0x14001fd9e  mov     edx, 50h ; 'P'
0x14001fda3  mov     qword ptr [rsp+78h+cchCount2], rdi
0x14001fda8  mov     r9d, r13d
0x14001fdab  mov     [rsp+78h+lpString2], r8
0x14001fdb0  lea     r8, WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids
0x14001fdb7  call    WPP_SF_dqq
0x14001fdbc  mov     r10, cs:WPP_GLOBAL_Control
0x14001fdc3  mov     r8, [rsp+78h+arg_8]
0x14001fdcb  jmp     loc_14001FB20
0x14001fdd0  cmp     byte ptr [r10+19h], 5
0x14001fdd5  jb      loc_14001FB4C
0x14001fddb  mov     rcx, [r10+10h]
0x14001fddf  lea     r8, WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids
0x14001fde6  mov     edx, 4Ch ; 'L'
0x14001fdeb  mov     [rsp+78h+lpString2], rdi
0x14001fdf0  mov     r9, rsi
0x14001fdf3  call    WPP_SF_qq
0x14001fdf8  mov     r10, cs:WPP_GLOBAL_Control
0x14001fdff  mov     edx, 1
0x14001fe04  jmp     loc_14001FB4C
0x14001fe09  cmp     byte ptr [r10+19h], 5
0x14001fe0e  jb      loc_14001FC29
0x14001fe14  mov     rcx, [r10+10h]
0x14001fe18  lea     r8, WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids
0x14001fe1f  mov     edx, 4Dh ; 'M'
0x14001fe24  mov     r9d, r15d
0x14001fe27  call    WPP_SF_d
0x14001fe2c  mov     r10, cs:WPP_GLOBAL_Control
0x14001fe33  mov     edx, 1
0x14001fe38  jmp     loc_14001FC29
0x14001fe3d  test    byte ptr [r10+1Ch], 2
0x14001fe42  jz      loc_14001FC97
0x14001fe48  cmp     byte ptr [r10+19h], 5
0x14001fe4d  jb      loc_14001FC97
0x14001fe53  mov     r9, [rdi+10h]
0x14001fe57  lea     r8, WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids
0x14001fe5e  mov     rcx, [r10+10h]
0x14001fe62  mov     edx, 51h ; 'Q'
0x14001fe67  call    WPP_SF_q
0x14001fe6c  jmp     loc_14001FC97
```

# IteratePathSubNodesWithName(IteratePathSubNodesType,ushort const *,unsigned __int64,ushort const *,Unattend &,UnattendNode,IPathIterator *)

- ea: `0x1800424a0`
- end: `0x18004269c`
- name: `?IteratePathSubNodesWithName@@YAJW4IteratePathSubNodesType@@PEBG_K1AEAVUnattend@@VUnattendNode@@PEAVIPathIterator@@@Z`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800433b0`

## callees

- `0x1800423b0`
- `0x1800424a0`
- `0x180044f8c`
- `0x180044ff0`
- `0x180045074`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180042641`
- `KERNEL32!HeapFree` at `0x180042641`
- `KERNEL32!GetProcessHeap` at `0x18004262d`
- `KERNEL32!GetProcessHeap` at `0x18004262d`
- `KERNEL32!CompareStringW` at `0x1800425af`
- `KERNEL32!CompareStringW` at `0x1800425af`

## pseudocode

```c
__int64 __fastcall IteratePathSubNodesWithName(
        unsigned int a1,
        const WCHAR *a2,
        unsigned __int64 a3,
        __int64 a4,
        Unattend *a5,
        struct UnattendNode *a6,
        __int64 a7)
{
  const struct UnattendNode *v7; // rsi
  char v9; // r12
  int Child; // ebx
  unsigned __int64 v11; // rdi
  __int64 v12; // r13
  WCHAR *v13; // rsi
  int v14; // eax
  HANDLE ProcessHeap; // rax
  unsigned __int64 v17; // [rsp+30h] [rbp-41h] BYREF
  unsigned int v18; // [rsp+38h] [rbp-39h]
  __int64 v19; // [rsp+40h] [rbp-31h]
  __int64 v20; // [rsp+48h] [rbp-29h]
  PCNZWCH lpString2; // [rsp+50h] [rbp-21h] BYREF
  struct UnattendNode *v22; // [rsp+58h] [rbp-19h]
  __int128 v23; // [rsp+60h] [rbp-11h] BYREF
  __int128 v24; // [rsp+70h] [rbp-1h] BYREF
  PCNZWCH lpString1; // [rsp+80h] [rbp+Fh]
  unsigned __int64 v26; // [rsp+88h] [rbp+17h]

  v7 = a6;
  v26 = a3;
  lpString1 = a2;
  v18 = a1;
  v9 = 0;
  v19 = a7;
  v20 = a4;
  v22 = a6;
  v17 = 0;
  if ( a1 > 2 || !a2 || !a4 || !a7 )
    return 2147942487LL;
  Child = Unattend::CountChildren(a5, a6, &v17);
  if ( Child < 0 )
    return (unsigned int)Child;
  if ( a3 > v17 )
    return 2147942487LL;
  v11 = 0;
  v12 = -1;
  while ( v11 < v17 )
  {
    Child = Unattend::GetChild(a5, v7, v11, (struct UnattendNode *)&v24);
    if ( Child >= 0 )
    {
      Child = Unattend::GetName(a5, (const struct UnattendNode *)&v24, (unsigned __int16 **)&lpString2);
      if ( Child >= 0 )
      {
        v13 = (WCHAR *)lpString2;
        if ( lpString2 && CompareStringW(0x409u, 1u, lpString1, -1, lpString2, -1) == 2 )
        {
          if ( !v18 )
            goto LABEL_17;
          if ( v18 == 1 )
          {
            v9 = 1;
            v23 = v24;
            Child = IteratePath(v20, a5, &v23, v19);
          }
          else if ( v18 == 2 && v26 == ++v12 )
          {
LABEL_17:
            v9 = 1;
            v23 = v24;
            v14 = IteratePath(v20, a5, &v23, v19);
            v11 = v17;
            Child = v14;
          }
        }
        else
        {
          Child = 0;
        }
        if ( v13 )
        {
          ProcessHeap = GetProcessHeap();
          if ( HeapFree(ProcessHeap, 0, v13) )
            v13 = 0;
          lpString2 = v13;
        }
        v7 = v22;
      }
    }
    ++v11;
    if ( Child < 0 )
      break;
  }
  if ( !v9 && Child >= 0 )
    return 1;
  return (unsigned int)Child;
}

```

## disassembly

```asm
0x1800424a0  mov     [rsp-8+arg_0], rbx
0x1800424a5  mov     [rsp-8+arg_10], rsi
0x1800424aa  push    rbp
0x1800424ab  push    rdi
0x1800424ac  push    r12
0x1800424ae  push    r13
0x1800424b0  push    r14
0x1800424b2  lea     rbp, [rsp-1Fh]
0x1800424b7  sub     rsp, 90h
0x1800424be  mov     rsi, [rbp+3Fh+arg_28]
0x1800424c2  xor     r13d, r13d
0x1800424c5  mov     r14, [rbp+3Fh+arg_20]
0x1800424c9  mov     rdi, r8
0x1800424cc  mov     [rbp+3Fh+var_28], r8
0x1800424d0  mov     rax, r9
0x1800424d3  mov     r8, rdx
0x1800424d6  mov     [rbp+3Fh+lpString1], rdx
0x1800424da  mov     edx, ecx
0x1800424dc  mov     [rbp+3Fh+var_78], ecx
0x1800424df  mov     rcx, [rbp+3Fh+arg_30]
0x1800424e3  mov     r12b, r13b
0x1800424e6  mov     [rbp+3Fh+var_70], rcx
0x1800424ea  mov     [rbp+3Fh+var_68], rax
0x1800424ee  mov     [rbp+3Fh+var_58], rsi
0x1800424f2  mov     [rbp+3Fh+var_80], r13
0x1800424f6  cmp     edx, 2
0x1800424f9  ja      loc_18004267B
0x1800424ff  test    r8, r8
0x180042502  jz      loc_18004267B
0x180042508  test    rax, rax
0x18004250b  jz      loc_18004267B
0x180042511  test    rcx, rcx
0x180042514  jz      loc_18004267B
0x18004251a  lea     r8, [rbp+3Fh+var_80]; unsigned __int64 *
0x18004251e  mov     rdx, rsi; struct UnattendNode *
0x180042521  mov     rcx, r14; this
0x180042524  call    ?CountChildren@Unattend@@QEAAJAEBVUnattendNode@@AEA_K@Z; Unattend::CountChildren(UnattendNode const &,unsigned __int64 &)
0x180042529  mov     ebx, eax
0x18004252b  test    eax, eax
0x18004252d  js      loc_180042677
0x180042533  cmp     rdi, [rbp+3Fh+var_80]
0x180042537  ja      loc_18004267B
0x18004253d  mov     edi, r13d
0x180042540  or      r13, 0FFFFFFFFFFFFFFFFh
0x180042544  lea     eax, [rdi+1]
0x180042547  cmp     rdi, [rbp+3Fh+var_80]
0x18004254b  jnb     loc_18004266D
0x180042551  lea     r9, [rbp+3Fh+var_40]; struct UnattendNode *
0x180042555  mov     r8, rdi; unsigned __int64
0x180042558  mov     rdx, rsi; struct UnattendNode *
0x18004255b  mov     rcx, r14; this
0x18004255e  call    ?GetChild@Unattend@@QEAAJAEBVUnattendNode@@_KAEAV2@@Z; Unattend::GetChild(UnattendNode const &,unsigned __int64,UnattendNode &)
0x180042563  mov     ebx, eax
0x180042565  test    eax, eax
0x180042567  js      loc_18004265D
0x18004256d  lea     r8, [rbp+3Fh+var_60]; unsigned __int16 **
0x180042571  mov     rcx, r14; this
0x180042574  lea     rdx, [rbp+3Fh+var_40]; struct UnattendNode *
0x180042578  call    ?GetName@Unattend@@QEAAJAEBVUnattendNode@@PEAPEAG@Z; Unattend::GetName(UnattendNode const &,ushort * *)
0x18004257d  mov     ebx, eax
0x18004257f  test    eax, eax
0x180042581  js      loc_18004265D
0x180042587  mov     rsi, [rbp+3Fh+var_60]
0x18004258b  test    rsi, rsi
0x18004258e  jz      loc_180042626
0x180042594  or      [rsp+0B0h+var_88], 0FFFFFFFFh
0x180042599  or      r9d, 0FFFFFFFFh; cchCount1
0x18004259d  mov     r8, [rbp+3Fh+lpString1]; lpString1
0x1800425a1  mov     ecx, 409h; Locale
0x1800425a6  mov     [rsp+0B0h+lpString2], rsi; lpString2
0x1800425ab  lea     edx, [r9+2]; dwCmpFlags
0x1800425af  call    cs:__imp_CompareStringW
0x1800425b6  nop     dword ptr [rax+rax+00h]
0x1800425bb  cmp     eax, 2
0x1800425be  jnz     short loc_180042626
0x1800425c0  mov     ecx, [rbp+3Fh+var_78]
0x1800425c3  test    ecx, ecx
0x1800425c5  jz      short loc_1800425DA
0x1800425c7  sub     ecx, 1
0x1800425ca  jz      short loc_180042602
0x1800425cc  cmp     ecx, 1
0x1800425cf  jnz     short loc_180042628
0x1800425d1  inc     r13
0x1800425d4  cmp     [rbp+3Fh+var_28], r13
0x1800425d8  jnz     short loc_180042628
0x1800425da  movaps  xmm0, [rbp+3Fh+var_40]
0x1800425de  lea     r8, [rbp+3Fh+var_50]
0x1800425e2  mov     r9, [rbp+3Fh+var_70]
0x1800425e6  mov     rdx, r14
0x1800425e9  mov     rcx, [rbp+3Fh+var_68]
0x1800425ed  mov     r12b, 1
0x1800425f0  movdqa  [rbp+3Fh+var_50], xmm0
0x1800425f5  call    ?IteratePath@@YAJPEBGAEAVUnattend@@VUnattendNode@@PEAVIPathIterator@@@Z; IteratePath(ushort const *,Unattend &,UnattendNode,IPathIterator *)
0x1800425fa  mov     rdi, [rbp+3Fh+var_80]
0x1800425fe  mov     ebx, eax
0x180042600  jmp     short loc_180042628
0x180042602  movaps  xmm0, [rbp+3Fh+var_40]
0x180042606  lea     r8, [rbp+3Fh+var_50]
0x18004260a  mov     r9, [rbp+3Fh+var_70]
0x18004260e  mov     rdx, r14
0x180042611  mov     rcx, [rbp+3Fh+var_68]
0x180042615  mov     r12b, 1
0x180042618  movdqa  [rbp+3Fh+var_50], xmm0
0x18004261d  call    ?IteratePath@@YAJPEBGAEAVUnattend@@VUnattendNode@@PEAVIPathIterator@@@Z; IteratePath(ushort const *,Unattend &,UnattendNode,IPathIterator *)
0x180042622  mov     ebx, eax
0x180042624  jmp     short loc_180042628
0x180042626  xor     ebx, ebx
0x180042628  test    rsi, rsi
0x18004262b  jz      short loc_180042659
0x18004262d  call    cs:__imp_GetProcessHeap
0x180042634  nop     dword ptr [rax+rax+00h]
0x180042639  mov     r8, rsi; lpMem
0x18004263c  xor     edx, edx; dwFlags
0x18004263e  mov     rcx, rax; hHeap
0x180042641  call    cs:__imp_HeapFree
0x180042648  nop     dword ptr [rax+rax+00h]
0x18004264d  xor     ecx, ecx
0x18004264f  test    eax, eax
0x180042651  cmovnz  rsi, rcx
0x180042655  mov     [rbp+3Fh+var_60], rsi
0x180042659  mov     rsi, [rbp+3Fh+var_58]
0x18004265d  mov     eax, 1
0x180042662  add     rdi, rax
0x180042665  test    ebx, ebx
0x180042667  jns     loc_180042547
0x18004266d  test    r12b, r12b
0x180042670  jnz     short loc_180042677
0x180042672  test    ebx, ebx
0x180042674  cmovns  ebx, eax
0x180042677  mov     eax, ebx
0x180042679  jmp     short loc_180042680
0x18004267b  mov     eax, 80070057h
0x180042680  lea     r11, [rsp+0B0h+var_20]
0x180042688  mov     rbx, [r11+30h]
0x18004268c  mov     rsi, [r11+40h]
0x180042690  mov     rsp, r11
0x180042693  pop     r14
0x180042695  pop     r13
0x180042697  pop     r12
0x180042699  pop     rdi
0x18004269a  pop     rbp
0x18004269b  retn
```

# IteratePathFirstSubNodeWithAttrValue(ushort const *,ushort * *,ushort * *,ulong,ushort const *,Unattend &,UnattendNode,IPathIterator *)

- ea: `0x1800426a4`
- end: `0x180042acc`
- name: `?IteratePathFirstSubNodeWithAttrValue@@YAJPEBGPEAPEAG1K0AEAVUnattend@@VUnattendNode@@PEAVIPathIterator@@@Z`
- size: `1064`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800433b0`

## callees

- `0x1800423b0`
- `0x1800426a4`
- `0x180044f8c`
- `0x180044ff0`
- `0x180045074`
- `0x18004537c`
- `0x180045448`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800428e9`
- `KERNEL32!HeapFree` at `0x18004291b`
- `KERNEL32!HeapFree` at `0x1800429d6`
- `KERNEL32!HeapFree` at `0x180042a63`
- `KERNEL32!HeapFree` at `0x1800428e9`
- `KERNEL32!HeapFree` at `0x18004291b`
- `KERNEL32!HeapFree` at `0x1800429d6`
- `KERNEL32!HeapFree` at `0x180042a63`
- `KERNEL32!GetProcessHeap` at `0x1800428d5`
- `KERNEL32!GetProcessHeap` at `0x180042907`
- `KERNEL32!GetProcessHeap` at `0x1800429c2`
- `KERNEL32!GetProcessHeap` at `0x180042a4f`
- `KERNEL32!GetProcessHeap` at `0x1800428d5`
- `KERNEL32!GetProcessHeap` at `0x180042907`
- `KERNEL32!GetProcessHeap` at `0x1800429c2`
- `KERNEL32!GetProcessHeap` at `0x180042a4f`
- `KERNEL32!CompareStringW` at `0x1800427bc`
- `KERNEL32!CompareStringW` at `0x1800428a0`
- `KERNEL32!CompareStringW` at `0x180042996`
- `KERNEL32!CompareStringW` at `0x1800427bc`
- `KERNEL32!CompareStringW` at `0x1800428a0`
- `KERNEL32!CompareStringW` at `0x180042996`

## pseudocode

```c
__int64 __fastcall IteratePathFirstSubNodeWithAttrValue(
        const WCHAR *a1,
        __int64 a2,
        const WCHAR **a3,
        unsigned int a4,
        __int64 a5,
        Unattend *a6,
        struct UnattendNode *a7,
        __int64 a8)
{
  Unattend *v8; // rdi
  const WCHAR **v9; // r14
  const struct UnattendNode *v10; // r12
  int Child; // ebx
  unsigned __int64 v12; // r13
  unsigned __int16 *v13; // r15
  int v14; // esi
  WCHAR *v15; // r12
  __int64 v16; // rax
  const WCHAR *v17; // rcx
  char v18; // r12
  unsigned __int64 v19; // rsi
  const WCHAR *v20; // r13
  WCHAR *v21; // r14
  unsigned __int16 *v22; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v24; // rax
  HANDLE v25; // rax
  bool v26; // cf
  int v27; // eax
  HANDLE v28; // rax
  char v30; // [rsp+30h] [rbp-B9h]
  int v31; // [rsp+34h] [rbp-B5h]
  int v32; // [rsp+38h] [rbp-B1h]
  unsigned __int16 *v34; // [rsp+40h] [rbp-A9h] BYREF
  const WCHAR **v35; // [rsp+48h] [rbp-A1h]
  unsigned __int64 v36; // [rsp+50h] [rbp-99h] BYREF
  PCNZWCH lpString2; // [rsp+58h] [rbp-91h] BYREF
  unsigned __int64 v38; // [rsp+60h] [rbp-89h] BYREF
  PCNZWCH v39; // [rsp+68h] [rbp-81h] BYREF
  Unattend *v40; // [rsp+70h] [rbp-79h]
  const WCHAR **v41; // [rsp+78h] [rbp-71h]
  struct UnattendNode *v42; // [rsp+80h] [rbp-69h]
  unsigned __int64 v43; // [rsp+88h] [rbp-61h]
  __int128 v44; // [rsp+90h] [rbp-59h] BYREF
  PCNZWCH lpString1; // [rsp+A0h] [rbp-49h]
  __int64 v46; // [rsp+A8h] [rbp-41h]
  PCNZWCH v47; // [rsp+B0h] [rbp-39h]
  PCNZWCH v48; // [rsp+B8h] [rbp-31h]
  __int128 v49; // [rsp+C0h] [rbp-29h] BYREF
  __int64 v50; // [rsp+D0h] [rbp-19h]
  __int64 v51; // [rsp+D8h] [rbp-11h]
  _BYTE v52[64]; // [rsp+E0h] [rbp-9h] BYREF

  v8 = a6;
  v9 = a3;
  v10 = a7;
  lpString1 = a1;
  v50 = a8;
  v41 = a3;
  v46 = a2;
  v51 = a5;
  v40 = a6;
  v42 = a7;
  v36 = 0;
  v30 = 0;
  if ( !a2 || !a3 || !a5 || !a8 )
    return 2147942487LL;
  Child = Unattend::CountChildren(a6, a7, &v36);
  if ( Child >= 0 )
  {
    v12 = 0;
    v43 = 0;
    do
    {
      if ( v12 >= v36 )
        break;
      v13 = 0;
      v31 = 1;
      v14 = 1;
      Child = Unattend::GetChild(v8, v10, v12, (struct UnattendNode *)&v44);
      if ( Child >= 0 )
      {
        Child = Unattend::GetName(v8, (const struct UnattendNode *)&v44, (unsigned __int16 **)&lpString2);
        if ( Child >= 0 )
        {
          v15 = (WCHAR *)lpString2;
          if ( lpString2 )
          {
            if ( CompareStringW(0x409u, 1u, lpString1, -1, lpString2, -1) == 2 )
            {
              v32 = 0;
              if ( a4 )
              {
                v16 = v46 - (_QWORD)v41;
                *(_QWORD *)&v49 = v46 - (_QWORD)v41;
                v35 = v9;
                do
                {
                  if ( v14 != 1 )
                    break;
                  v17 = *v9;
                  v47 = *(const WCHAR **)((char *)v9 + v16);
                  v48 = v17;
                  if ( v47 )
                  {
                    Child = Unattend::CountAttributes(v8, (const struct UnattendNode *)&v44, &v38);
                    if ( Child >= 0 )
                    {
                      v18 = 0;
                      v19 = 0;
                      v20 = v47;
                      do
                      {
                        if ( v19 >= v38 )
                          break;
                        Child = Unattend::GetAttributeInfo(
                                  v8,
                                  (const struct UnattendNode *)&v44,
                                  v19,
                                  (unsigned __int16 **)&v39,
                                  &v34,
                                  (struct UnattendNode *)v52);
                        if ( Child >= 0 )
                        {
                          v21 = (WCHAR *)v39;
                          if ( CompareStringW(0x409u, 1u, v20, -1, v39, -1) == 2 )
                          {
                            v13 = v34;
                            v18 = 1;
                            v19 = v38;
                            v22 = 0;
                            v34 = 0;
                            Child = 0;
                          }
                          else
                          {
                            v22 = v34;
                          }
                          if ( v21 )
                          {
                            ProcessHeap = GetProcessHeap();
                            if ( HeapFree(ProcessHeap, 0, v21) )
                              v21 = 0;
                            v39 = v21;
                          }
                          if ( v22 )
                          {
                            v24 = GetProcessHeap();
                            if ( HeapFree(v24, 0, v22) )
                              v22 = 0;
                            v34 = v22;
                          }
                          v8 = v40;
                        }
                        ++v19;
                      }
                      while ( Child >= 0 );
                      v14 = v31;
                      v9 = v35;
                      if ( !v18 && Child >= 0 )
                      {
                        Child = 1;
                        v13 = 0;
                      }
                    }
                    v17 = v48;
                  }
                  else
                  {
                    Child = -2147024809;
                  }
                  if ( Child >= 0 )
                  {
                    if ( Child == 1 || v17 && CompareStringW(0x409u, 1u, v17, -1, v13, -1) != 2 )
                    {
                      v14 = 0;
                      v31 = 0;
                    }
                    else
                    {
                      v14 = 1;
                      v31 = 1;
                    }
                  }
                  if ( v13 )
                  {
                    v25 = GetProcessHeap();
                    if ( HeapFree(v25, 0, v13) )
                      v13 = 0;
                  }
                  v35 = ++v9;
                  v26 = ++v32 < a4;
                  v16 = v49;
                }
                while ( v26 );
                v15 = (WCHAR *)lpString2;
                v12 = v43;
                v9 = v41;
              }
              if ( Child >= 0 && v14 == 1 )
              {
                v49 = v44;
                v30 = 1;
                v27 = IteratePath(v51, v8, &v49, v50);
                v12 = v36;
                Child = v27;
              }
            }
            v28 = GetProcessHeap();
            if ( HeapFree(v28, 0, v15) )
              v15 = 0;
            lpString2 = v15;
            v10 = v42;
          }
          else
          {
            v10 = v42;
          }
        }
      }
      v43 = ++v12;
    }
    while ( Child >= 0 );
    if ( Child >= 0 && !v30 )
      return 1;
  }
  return (unsigned int)Child;
}

```

## disassembly

```asm
0x1800426a4  mov     [rsp-8+arg_18], rbx
0x1800426a9  push    rbp
0x1800426aa  push    rsi
0x1800426ab  push    rdi
0x1800426ac  push    r12
0x1800426ae  push    r13
0x1800426b0  push    r14
0x1800426b2  push    r15
0x1800426b4  lea     rbp, [rsp-7]
0x1800426b9  sub     rsp, 0F0h
0x1800426c0  mov     rax, [rbp+37h+arg_20]
0x1800426c4  xor     esi, esi
0x1800426c6  mov     rdi, [rbp+37h+arg_28]
0x1800426ca  mov     r14, r8
0x1800426cd  mov     r12, [rbp+37h+arg_30]
0x1800426d1  mov     [rbp+37h+lpString1], rcx
0x1800426d5  mov     rcx, [rbp+37h+arg_38]
0x1800426d9  mov     [rbp+37h+var_50], rcx
0x1800426dd  mov     [rsp+120h+var_E4], r9d
0x1800426e2  mov     [rbp+37h+var_A8], r8
0x1800426e6  mov     [rbp+37h+var_78], rdx
0x1800426ea  mov     [rbp+37h+var_48], rax
0x1800426ee  mov     [rbp+37h+var_B0], rdi
0x1800426f2  mov     [rbp+37h+var_A0], r12
0x1800426f6  mov     [rsp+120h+var_D0], rsi
0x1800426fb  mov     [rsp+120h+var_F0], sil
0x180042700  test    rdx, rdx
0x180042703  jz      loc_180042AAC
0x180042709  test    r8, r8
0x18004270c  jz      loc_180042AAC
0x180042712  test    rax, rax
0x180042715  jz      loc_180042AAC
0x18004271b  test    rcx, rcx
0x18004271e  jz      loc_180042AAC
0x180042724  lea     r8, [rsp+120h+var_D0]; unsigned __int64 *
0x180042729  mov     rdx, r12; struct UnattendNode *
0x18004272c  mov     rcx, rdi; this
0x18004272f  call    ?CountChildren@Unattend@@QEAAJAEBVUnattendNode@@AEA_K@Z; Unattend::CountChildren(UnattendNode const &,unsigned __int64 &)
0x180042734  mov     ebx, eax
0x180042736  test    eax, eax
0x180042738  js      loc_180042AA8
0x18004273e  mov     r13d, esi
0x180042741  mov     [rbp+37h+var_98], rsi
0x180042745  lea     eax, [rsi+1]
0x180042748  cmp     r13, [rsp+120h+var_D0]
0x18004274d  jnb     loc_180042A9C
0x180042753  mov     r15, rsi
0x180042756  mov     [rsp+120h+var_EC], eax
0x18004275a  lea     r9, [rbp+37h+var_90]; struct UnattendNode *
0x18004275e  mov     r8, r13; unsigned __int64
0x180042761  mov     rdx, r12; struct UnattendNode *
0x180042764  mov     rcx, rdi; this
0x180042767  mov     esi, eax
0x180042769  call    ?GetChild@Unattend@@QEAAJAEBVUnattendNode@@_KAEAV2@@Z; Unattend::GetChild(UnattendNode const &,unsigned __int64,UnattendNode &)
0x18004276e  mov     ebx, eax
0x180042770  test    eax, eax
0x180042772  js      loc_180042A86
0x180042778  lea     r8, [rsp+120h+var_C8]; unsigned __int16 **
0x18004277d  mov     rcx, rdi; this
0x180042780  lea     rdx, [rbp+37h+var_90]; struct UnattendNode *
0x180042784  call    ?GetName@Unattend@@QEAAJAEBVUnattendNode@@PEAPEAG@Z; Unattend::GetName(UnattendNode const &,ushort * *)
0x180042789  mov     ebx, eax
0x18004278b  test    eax, eax
0x18004278d  js      loc_180042A86
0x180042793  mov     r12, [rsp+120h+var_C8]
0x180042798  test    r12, r12
0x18004279b  jz      loc_180042A82
0x1800427a1  mov     r8, [rbp+37h+lpString1]; lpString1
0x1800427a5  or      eax, 0FFFFFFFFh
0x1800427a8  mov     [rsp+120h+cchCount2], eax; cchCount2
0x1800427ac  mov     r9d, eax; cchCount1
0x1800427af  mov     ecx, 409h; Locale
0x1800427b4  mov     [rsp+120h+lpString2], r12; lpString2
0x1800427b9  lea     edx, [rax+2]; dwCmpFlags
0x1800427bc  call    cs:__imp_CompareStringW
0x1800427c3  nop     dword ptr [rax+rax+00h]
0x1800427c8  cmp     eax, 2
0x1800427cb  jnz     loc_180042A4F
0x1800427d1  xor     edx, edx
0x1800427d3  lea     r10d, [rax-1]
0x1800427d7  mov     [rsp+120h+var_E8], edx
0x1800427db  cmp     [rsp+120h+var_E4], edx
0x1800427df  jbe     loc_180042A1D
0x1800427e5  mov     rax, [rbp+37h+var_78]
0x1800427e9  sub     rax, [rbp+37h+var_A8]
0x1800427ed  mov     qword ptr [rbp+37h+var_60], rax
0x1800427f1  mov     [rsp+120h+var_D8], r14
0x1800427f6  cmp     esi, r10d
0x1800427f9  jnz     loc_180042A10
0x1800427ff  mov     rax, [rax+r14]
0x180042803  mov     rcx, [r14]
0x180042806  mov     [rbp+37h+var_70], rax
0x18004280a  mov     [rbp+37h+var_68], rcx
0x18004280e  mov     [rsp+120h+var_EF], dl
0x180042812  test    rax, rax
0x180042815  jz      loc_180042969
0x18004281b  lea     r8, [rsp+120h+var_C0]; unsigned __int64 *
0x180042820  mov     rcx, rdi; this
0x180042823  lea     rdx, [rbp+37h+var_90]; struct UnattendNode *
0x180042827  call    ?CountAttributes@Unattend@@QEAAJAEBVUnattendNode@@AEA_K@Z; Unattend::CountAttributes(UnattendNode const &,unsigned __int64 &)
0x18004282c  xor     edx, edx
0x18004282e  mov     ebx, eax
0x180042830  test    eax, eax
0x180042832  js      loc_18004295D
0x180042838  mov     r12b, [rsp+120h+var_EF]
0x18004283d  mov     esi, edx
0x18004283f  mov     r13, [rbp+37h+var_70]
0x180042843  cmp     rsi, [rsp+120h+var_C0]
0x180042848  jnb     loc_180042943
0x18004284e  lea     rax, [rbp+37h+var_40]
0x180042852  mov     r8, rsi; unsigned __int64
0x180042855  mov     qword ptr [rsp+120h+cchCount2], rax; struct UnattendNode *
0x18004285a  lea     r9, [rsp+120h+var_B8]; unsigned __int16 **
0x18004285f  lea     rax, [rsp+120h+var_E0]
0x180042864  mov     rcx, rdi; this
0x180042867  lea     rdx, [rbp+37h+var_90]; struct UnattendNode *
0x18004286b  mov     [rsp+120h+lpString2], rax; unsigned __int16 **
0x180042870  call    ?GetAttributeInfo@Unattend@@QEAAJAEBVUnattendNode@@_KPEAPEAG2PEAV2@@Z; Unattend::GetAttributeInfo(UnattendNode const &,unsigned __int64,ushort * *,ushort * *,UnattendNode *)
0x180042875  xor     edx, edx
0x180042877  mov     ebx, eax
0x180042879  test    eax, eax
0x18004287b  js      loc_180042938
0x180042881  mov     r14, [rsp+120h+var_B8]
0x180042886  or      eax, 0FFFFFFFFh
0x180042889  mov     [rsp+120h+cchCount2], eax; cchCount2
0x18004288d  mov     r9d, eax; cchCount1
0x180042890  mov     r8, r13; lpString1
0x180042893  mov     [rsp+120h+lpString2], r14; lpString2
0x180042898  mov     ecx, 409h; Locale
0x18004289d  lea     edx, [rax+2]; dwCmpFlags
0x1800428a0  call    cs:__imp_CompareStringW
0x1800428a7  nop     dword ptr [rax+rax+00h]
0x1800428ac  xor     edx, edx
0x1800428ae  cmp     eax, 2
0x1800428b1  jnz     short loc_1800428CB
0x1800428b3  mov     r15, [rsp+120h+var_E0]
0x1800428b8  mov     r12b, 1
0x1800428bb  mov     rsi, [rsp+120h+var_C0]
0x1800428c0  mov     edi, edx
0x1800428c2  mov     [rsp+120h+var_E0], rdx
0x1800428c7  mov     ebx, edx
0x1800428c9  jmp     short loc_1800428D0
0x1800428cb  mov     rdi, [rsp+120h+var_E0]
0x1800428d0  test    r14, r14
0x1800428d3  jz      short loc_180042902
0x1800428d5  call    cs:__imp_GetProcessHeap
0x1800428dc  nop     dword ptr [rax+rax+00h]
0x1800428e1  mov     r8, r14; lpMem
0x1800428e4  xor     edx, edx; dwFlags
0x1800428e6  mov     rcx, rax; hHeap
0x1800428e9  call    cs:__imp_HeapFree
0x1800428f0  nop     dword ptr [rax+rax+00h]
0x1800428f5  xor     edx, edx
0x1800428f7  test    eax, eax
0x1800428f9  cmovnz  r14, rdx
0x1800428fd  mov     [rsp+120h+var_B8], r14
0x180042902  test    rdi, rdi
0x180042905  jz      short loc_180042934
0x180042907  call    cs:__imp_GetProcessHeap
0x18004290e  nop     dword ptr [rax+rax+00h]
0x180042913  mov     r8, rdi; lpMem
0x180042916  xor     edx, edx; dwFlags
0x180042918  mov     rcx, rax; hHeap
0x18004291b  call    cs:__imp_HeapFree
0x180042922  nop     dword ptr [rax+rax+00h]
0x180042927  xor     edx, edx
0x180042929  test    eax, eax
0x18004292b  cmovnz  rdi, rdx
0x18004292f  mov     [rsp+120h+var_E0], rdi
0x180042934  mov     rdi, [rbp+37h+var_B0]
0x180042938  inc     rsi
0x18004293b  test    ebx, ebx
0x18004293d  jns     loc_180042843
0x180042943  mov     esi, [rsp+120h+var_EC]
0x180042947  mov     r14, [rsp+120h+var_D8]
0x18004294c  test    r12b, r12b
0x18004294f  jnz     short loc_18004295D
0x180042951  test    ebx, ebx
0x180042953  js      short loc_18004295D
0x180042955  mov     ebx, 1
0x18004295a  mov     r15, rdx
0x18004295d  mov     rcx, [rbp+37h+var_68]
0x180042961  mov     r10d, 1
0x180042967  jmp     short loc_18004296E
0x180042969  mov     ebx, 80070057h
0x18004296e  test    ebx, ebx
0x180042970  js      short loc_1800429BD
0x180042972  cmp     ebx, r10d
0x180042975  jz      short loc_1800429B7
0x180042977  test    rcx, rcx
0x18004297a  jz      short loc_1800429AD
0x18004297c  or      eax, 0FFFFFFFFh
0x18004297f  mov     r8, rcx; lpString1
0x180042982  mov     [rsp+120h+cchCount2], eax; cchCount2
0x180042986  mov     r9d, eax; cchCount1
0x180042989  mov     edx, r10d; dwCmpFlags
0x18004298c  mov     [rsp+120h+lpString2], r15; lpString2
0x180042991  mov     ecx, 409h; Locale
0x180042996  call    cs:__imp_CompareStringW
0x18004299d  nop     dword ptr [rax+rax+00h]
0x1800429a2  xor     edx, edx
0x1800429a4  lea     r10d, [rdx+1]
0x1800429a8  cmp     eax, 2
0x1800429ab  jnz     short loc_1800429B7
0x1800429ad  mov     esi, r10d
0x1800429b0  mov     [rsp+120h+var_EC], r10d
0x1800429b5  jmp     short loc_1800429BD
0x1800429b7  mov     esi, edx
0x1800429b9  mov     [rsp+120h+var_EC], edx
0x1800429bd  test    r15, r15
0x1800429c0  jz      short loc_1800429EE
0x1800429c2  call    cs:__imp_GetProcessHeap
0x1800429c9  nop     dword ptr [rax+rax+00h]
0x1800429ce  mov     r8, r15; lpMem
0x1800429d1  xor     edx, edx; dwFlags
0x1800429d3  mov     rcx, rax; hHeap
0x1800429d6  call    cs:__imp_HeapFree
0x1800429dd  nop     dword ptr [rax+rax+00h]
0x1800429e2  xor     edx, edx
0x1800429e4  test    eax, eax
0x1800429e6  cmovnz  r15, rdx
0x1800429ea  lea     r10d, [rdx+1]
0x1800429ee  mov     eax, [rsp+120h+var_E8]
0x1800429f2  add     r14, 8
0x1800429f6  add     eax, r10d
0x1800429f9  mov     [rsp+120h+var_D8], r14
0x1800429fe  cmp     eax, [rsp+120h+var_E4]
0x180042a02  mov     [rsp+120h+var_E8], eax
0x180042a06  mov     rax, qword ptr [rbp+37h+var_60]
0x180042a0a  jb      loc_1800427F6
0x180042a10  mov     r12, [rsp+120h+var_C8]
0x180042a15  mov     r13, [rbp+37h+var_98]
0x180042a19  mov     r14, [rbp+37h+var_A8]
0x180042a1d  test    ebx, ebx
0x180042a1f  js      short loc_180042A4F
0x180042a21  cmp     esi, r10d
0x180042a24  jnz     short loc_180042A4F
0x180042a26  movaps  xmm0, [rbp+37h+var_90]
0x180042a2a  lea     r8, [rbp+37h+var_60]
0x180042a2e  mov     r9, [rbp+37h+var_50]
0x180042a32  mov     rdx, rdi
0x180042a35  mov     rcx, [rbp+37h+var_48]
0x180042a39  movdqa  [rbp+37h+var_60], xmm0
0x180042a3e  mov     [rsp+120h+var_F0], r10b
0x180042a43  call    ?IteratePath@@YAJPEBGAEAVUnattend@@VUnattendNode@@PEAVIPathIterator@@@Z; IteratePath(ushort const *,Unattend &,UnattendNode,IPathIterator *)
0x180042a48  mov     r13, [rsp+120h+var_D0]
0x180042a4d  mov     ebx, eax
0x180042a4f  call    cs:__imp_GetProcessHeap
0x180042a56  nop     dword ptr [rax+rax+00h]
0x180042a5b  mov     r8, r12; lpMem
0x180042a5e  xor     edx, edx; dwFlags
0x180042a60  mov     rcx, rax; hHeap
0x180042a63  call    cs:__imp_HeapFree
0x180042a6a  nop     dword ptr [rax+rax+00h]
0x180042a6f  xor     esi, esi
0x180042a71  test    eax, eax
0x180042a73  cmovnz  r12, rsi
0x180042a77  mov     [rsp+120h+var_C8], r12
0x180042a7c  mov     r12, [rbp+37h+var_A0]
0x180042a80  jmp     short loc_180042A88
0x180042a82  mov     r12, [rbp+37h+var_A0]
0x180042a86  xor     esi, esi
0x180042a88  mov     eax, 1
0x180042a8d  add     r13, rax
0x180042a90  mov     [rbp+37h+var_98], r13
0x180042a94  test    ebx, ebx
0x180042a96  jns     loc_180042748
0x180042a9c  test    ebx, ebx
0x180042a9e  js      short loc_180042AA8
0x180042aa0  cmp     [rsp+120h+var_F0], sil
0x180042aa5  cmovz   ebx, eax
0x180042aa8  mov     eax, ebx
0x180042aaa  jmp     short loc_180042AB1
0x180042aac  mov     eax, 80070057h
0x180042ab1  mov     rbx, [rsp+120h+arg_18]
0x180042ab9  add     rsp, 0F0h
0x180042ac0  pop     r15
0x180042ac2  pop     r14
0x180042ac4  pop     r13
0x180042ac6  pop     r12
0x180042ac8  pop     rdi
0x180042ac9  pop     rsi
0x180042aca  pop     rbp
0x180042acb  retn
```

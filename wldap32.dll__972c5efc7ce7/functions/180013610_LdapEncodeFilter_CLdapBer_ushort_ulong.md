# LdapEncodeFilter(CLdapBer *,ushort *,ulong)

- ea: `0x180013610`
- end: `0x180013fe3`
- name: `?LdapEncodeFilter@@YAKPEAVCLdapBer@@PEAGK@Z`
- size: `2515`
- prototype: `unsigned int __fastcall(struct CLdapBer *, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x18000e0d0`
- `0x180013610`
- `0x18004af90`

## callees

- `0x1800037a8`
- `0x180010ef0`
- `0x180011c80`
- `0x180012400`
- `0x180013610`
- `0x180013ff0`
- `0x180032bd8`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800137e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800137e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800138bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800138bb`

## string_xrefs

- `0x180013ba3`: `Freeing memory at 0x%x which is already freed\n`

## pseudocode

```c
__int64 __fastcall LdapEncodeFilter(struct CLdapBer *a1, unsigned __int16 *a2, unsigned int a3)
{
  CLdapBer *v5; // r10
  unsigned __int16 v6; // ax
  int v7; // r13d
  char v8; // si
  unsigned int v9; // r12d
  unsigned int v10; // ebx
  unsigned __int16 *i; // r15
  unsigned __int16 v12; // ax
  unsigned __int16 v13; // ax
  unsigned __int16 *j; // r15
  int v15; // eax
  struct CLdapBer *v16; // r10
  int v17; // edi
  unsigned __int16 v18; // bp
  unsigned __int16 *v19; // r14
  unsigned int v20; // eax
  unsigned __int16 *v22; // rdx
  unsigned int v23; // ecx
  size_t v24; // rbx
  unsigned int v25; // esi
  _DWORD *v26; // rdi
  unsigned int v27; // eax
  int v28; // eax
  int v29; // r9d
  int v30; // r8d
  int v31; // eax
  HANDLE v32; // rcx
  unsigned int v33; // eax
  unsigned __int16 *v34; // rdi
  int RightParen; // eax
  int v36; // ebp
  unsigned __int16 v37; // r15
  unsigned __int16 *v38; // r14
  unsigned int v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // eax
  int v42; // eax
  unsigned __int16 v43; // r15
  unsigned __int16 *v44; // r14
  unsigned int v45; // eax
  unsigned int v46; // eax

  v5 = a1;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40000) != 0 )
  {
    LDAPClientPrint(0x40000, "LdapEncodeFilter : Filter is '%S'\n", a2);
    v5 = a1;
  }
  if ( a3 >= 0x64 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40000) != 0 )
      LDAPClientTraceEvent(0x40000, (__int64)"LdapEncodeFilter : too much recursion\n");
    return 87;
  }
  v6 = *a2;
  v7 = 0;
  v8 = 0;
  v9 = a3 + 1;
  v10 = 87;
  for ( i = a2; v6 == 32; ++i )
    v6 = i[1];
  if ( !v6 )
    return v10;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v8 )
        return v7 != 0 ? 0x57 : 0;
      v12 = *i;
      if ( !*i )
        return v7 != 0 ? 0x57 : 0;
      if ( v12 != 40 )
        break;
      v13 = i[1];
      for ( j = i + 1; v13 == 32; ++j )
        v13 = j[1];
      switch ( v13 )
      {
        case '|':
LABEL_43:
          v33 = CLdapBer::HrStartWriteSequence(v5, (v13 != 38) + 160);
          if ( v33 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40000) != 0 )
              LDAPClientPrint(0x40000, "LdapEncodeFilter : 1 Filter is '%S', error 0x%x\n", a2, v33);
            return 87;
          }
          v34 = j + 1;
          RightParen = FindRightParen(j + 1);
          v36 = RightParen;
          if ( RightParen == -1 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40000) != 0 )
              LDAPClientPrint(0x40000, "LdapEncodeFilter : 2 Filter is '%S', no right ')'\n", a2);
            return 87;
          }
          v37 = v34[RightParen];
          v38 = &v34[RightParen];
          *v38 = 0;
          v39 = LdapEncodeFilter(a1, v34, v9);
          v10 = v39;
          if ( v39 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40000) != 0 )
              LDAPClientPrint(0x40000, "LdapEncodeFilter : 3 Filter is '%S', error 0x%x\n", a2, v39);
            return v10;
          }
          *v38 = v37;
          v40 = CLdapBer::HrEndWriteSequence(a1);
          if ( v40 )
          {
            if ( g_fTracingOn != v10 && g_fProviderEnabled != v10 && (g_ulTraceFlags & 0x40000) != 0 )
              LDAPClientPrint(0x40000, "LdapEncodeFilter : 4 Filter is '%S', error 0x%x\n", a2, v40);
            return 87;
          }
          goto LABEL_57;
        case '!':
          v41 = CLdapBer::HrStartWriteSequence(v5, 0xA2u);
          if ( v41 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40000) != 0 )
              LDAPClientPrint(0x40000, "LdapEncodeFilter : 5 Filter is '%S', error 0x%x\n", a2, v41);
            return 87;
          }
          v34 = j + 1;
          v42 = FindRightParen(j + 1);
          v36 = v42;
          if ( v42 == -1 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40000) != 0 )
              LDAPClientPrint(0x40000, "LdapEncodeFilter : 6 Filter is '%S', no right ')'\n", a2);
            return 87;
          }
          v43 = v34[v42];
          v44 = &v34[v42];
          *v44 = 0;
          v45 = LdapEncodeFilter(a1, v34, v9);
          v10 = v45;
          if ( v45 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40000) != 0 )
              LDAPClientPrint(0x40000, "LdapEncodeFilter : 7 Filter is '%S', error 0x%x\n", a2, v45);
            return v10;
          }
          *v44 = v43;
          v46 = CLdapBer::HrEndWriteSequence(a1);
          if ( v46 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40000) != 0 )
              LDAPClientPrint(0x40000, "LdapEncodeFilter : 8 Filter is '%S', error 0x%x\n", a2, v46);
            return 87;
          }
LABEL_57:
          i = &v34[v36 + 1];
LABEL_42:
          v5 = a1;
          break;
        case '&':
          goto LABEL_43;
        case ')':
          v10 = 87;
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40000) != 0 )
            LDAPClientPrint(0x40000, "LdapEncodeFilter : Filter is '%S', () not allowed\n", a2);
          return v10;
        default:
          v15 = FindRightParen(j);
          v17 = v15;
          if ( v15 == -1 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40000) != 0 )
              LDAPClientPrint(0x40000, "LdapEncodeFilter : 9 Filter is '%S', no right ')'\n", a2);
            return 87;
          }
          v18 = j[v15];
          v19 = &j[v15];
          *v19 = 0;
          v20 = LdapEncodeFilter(v16, j, v9);
          v10 = v20;
          if ( v20 )
          {
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40000) != 0 )
              LDAPClientPrint(0x40000, "LdapEncodeFilter : 10 Filter is '%S', error 0x%x\n", a2, v20);
            return v10;
          }
          v5 = a1;
          *v19 = v18;
          i = &j[v17 + 1];
          break;
      }
    }
    if ( v12 != 41 )
      break;
    --v7;
LABEL_59:
    ++i;
  }
  if ( v12 == 32 )
    goto LABEL_59;
  if ( v12 == 38 || v12 == 124 )
  {
    v10 = 87;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40000) != 0 )
      LDAPClientPrint(0x40000, "LdapEncodeFilter : invalid filter is '%S'\n", a2);
  }
  else
  {
    v22 = i;
    v23 = 1;
    while ( v12 )
    {
      if ( v23 + 1 < v23 )
        goto LABEL_96;
      ++v22;
      ++v23;
      v12 = *v22;
    }
    v24 = 2LL * v23;
    if ( v24 > 0xFFFFFFFF )
      goto LABEL_96;
    v25 = v24 + 8;
    if ( (int)v24 + 8 < (unsigned int)v24 )
    {
      v26 = 0;
      v25 = -1;
    }
    else
    {
      v26 = HeapAlloc(LdapHeap, 8u, v25);
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(8, "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n", v25, (_DWORD)v26, 1920226124);
    v27 = LdapAllocatedHeap;
    if ( v26 )
    {
      *v26 = 1920226124;
      v26[1] = v24;
      v26 += 2;
      v27 += v24;
      LdapAllocatedHeap = v27;
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
        v24,
        (_DWORD)v26,
        1920226124,
        v27);
    if ( !v26 )
    {
LABEL_96:
      v10 = 90;
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40000) != 0 )
        LDAPClientPrint(0x40000, "LdapEncodeFilter : 11 Filter is '%S', error 0x%x\n", a2, 90);
      return v10;
    }
    memcpy_0(v26, i, v24);
    v10 = LdapEncodeSimpleFilter(a1, (unsigned __int16 *)v26);
    v28 = *(v26 - 2);
    if ( v28 != 1684095564 )
    {
      if ( v28 != 1701987916 )
        goto LABEL_36;
      if ( g_fTracingOn )
      {
        if ( g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(8, "Freeing memory at 0x%x which is already freed\n", (_DWORD)v26);
LABEL_36:
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(
            8,
            "ldapfree freed       0x%x bytes at address 0x%x of tag 0x%x.\n",
            *(v26 - 1),
            (_DWORD)v26 - 8,
            1920226124);
      }
      v29 = *(v26 - 2);
      if ( v29 != 1920226124 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(8, "Expected tag 0x%x but found tag 0x%x\n", 1920226124, v29);
      v30 = *(v26 - 1);
      v31 = LdapAllocatedHeap - v30;
      LdapAllocatedHeap -= v30;
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(
          8,
          "ldapFree   0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
          v30,
          (_DWORD)v26,
          1920226124,
          v31);
      v32 = LdapHeap;
      *(v26 - 2) = 1701987916;
      HeapFree(v32, 0, v26 - 2);
    }
    if ( !v10 )
    {
      v8 = 1;
      goto LABEL_42;
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40000) != 0 )
      LDAPClientPrint(0x40000, "LdapEncodeFilter : 12 Filter is '%S', error 0x%x\n", a2, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x180013610  mov     [rsp+arg_8], rdx
0x180013615  mov     [rsp+arg_0], rcx
0x18001361a  push    r12
0x18001361c  push    r14
0x18001361e  sub     rsp, 58h
0x180013622  cmp     cs:g_fTracingOn, 0
0x180013629  mov     r12d, r8d
0x18001362c  mov     r14, rdx
0x18001362f  mov     r10, rcx
0x180013632  jnz     loc_180013A66
0x180013638  mov     [rsp+68h+arg_10], rbx
0x180013640  mov     [rsp+68h+var_18], rbp
0x180013645  mov     [rsp+68h+var_20], rsi
0x18001364a  mov     [rsp+68h+var_28], rdi
0x18001364f  mov     [rsp+68h+var_30], r13
0x180013654  mov     [rsp+68h+var_38], r15
0x180013659  cmp     r12d, 64h ; 'd'
0x18001365d  jnb     loc_180013A25
0x180013663  movzx   eax, word ptr [r14]
0x180013667  xor     r13d, r13d
0x18001366a  xor     sil, sil
0x18001366d  inc     r12d
0x180013670  mov     ebx, 57h ; 'W'
0x180013675  mov     r15, r14
0x180013678  cmp     ax, 20h ; ' '
0x18001367c  jz      loc_180013B23
0x180013682  test    ax, ax
0x180013685  jz      loc_18001398D
0x18001368b  mov     r8d, 0FFFFFFFFh
0x180013691  test    sil, sil
0x180013694  jnz     loc_18001373F
0x18001369a  movzx   eax, word ptr [r15]
0x18001369e  test    ax, ax
0x1800136a1  jz      loc_18001373F
0x1800136a7  cmp     ax, 28h ; '('
0x1800136ab  jnz     loc_180013772
0x1800136b1  movzx   eax, word ptr [r15+2]
0x1800136b6  add     r15, 2
0x1800136ba  cmp     ax, 20h ; ' '
0x1800136be  jz      loc_180013C38
0x1800136c4  cmp     ax, 7Ch ; '|'
0x1800136c8  jz      loc_1800138DC
0x1800136ce  cmp     ax, 21h ; '!'
0x1800136d2  jz      loc_180013994
0x1800136d8  cmp     ax, 26h ; '&'
0x1800136dc  jz      loc_1800138DC
0x1800136e2  cmp     ax, 29h ; ')'
0x1800136e6  jz      loc_180013DBD
0x1800136ec  mov     rcx, r15; unsigned __int16 *
0x1800136ef  call    ?FindRightParen@@YAJPEAG@Z; FindRightParen(ushort *)
0x1800136f4  movsxd  rdi, eax
0x1800136f7  cmp     edi, 0FFFFFFFFh
0x1800136fa  jz      loc_180013D77
0x180013700  movzx   ebp, word ptr [r15+rdi*2]
0x180013705  lea     r14, [r15+rdi*2]
0x180013709  xor     ecx, ecx
0x18001370b  mov     r8d, r12d; unsigned int
0x18001370e  mov     [r14], cx
0x180013712  mov     rdx, r15; unsigned __int16 *
0x180013715  mov     rcx, r10; struct CLdapBer *
0x180013718  call    ?LdapEncodeFilter@@YAKPEAVCLdapBer@@PEAGK@Z; LdapEncodeFilter(CLdapBer *,ushort *,ulong)
0x18001371d  mov     ebx, eax
0x18001371f  test    eax, eax
0x180013721  jnz     loc_180013D2E
0x180013727  mov     r10, [rsp+68h+arg_0]
0x18001372c  lea     eax, [rdi+1]
0x18001372f  movsxd  rcx, eax
0x180013732  mov     [r14], bp
0x180013736  lea     r15, [r15+rcx*2]
0x18001373a  jmp     loc_18001368B
0x18001373f  neg     r13d
0x180013742  sbb     eax, eax
0x180013744  and     eax, 57h
0x180013747  mov     r15, [rsp+68h+var_38]
0x18001374c  mov     r13, [rsp+68h+var_30]
0x180013751  mov     rdi, [rsp+68h+var_28]
0x180013756  mov     rsi, [rsp+68h+var_20]
0x18001375b  mov     rbp, [rsp+68h+var_18]
0x180013760  mov     rbx, [rsp+68h+arg_10]
0x180013768  add     rsp, 58h
0x18001376c  pop     r14
0x18001376e  pop     r12
0x180013770  retn
0x180013772  cmp     ax, 29h ; ')'
0x180013776  jz      loc_180013A0F
0x18001377c  cmp     ax, 20h ; ' '
0x180013780  jz      loc_180013A12
0x180013786  cmp     ax, 26h ; '&'
0x18001378a  jz      loc_180013CE3
0x180013790  cmp     ax, 7Ch ; '|'
0x180013794  jz      loc_180013CE3
0x18001379a  mov     rdx, r15
0x18001379d  mov     ecx, 1
0x1800137a2  test    ax, ax
0x1800137a5  jz      short loc_1800137BD
0x1800137a7  lea     eax, [rcx+1]
0x1800137aa  cmp     eax, ecx
0x1800137ac  jb      loc_180013C95
0x1800137b2  add     rdx, 2
0x1800137b6  mov     ecx, eax
0x1800137b8  movzx   eax, word ptr [rdx]
0x1800137bb  jmp     short loc_1800137A2
0x1800137bd  mov     ebx, ecx
0x1800137bf  add     rbx, rbx
0x1800137c2  cmp     rbx, r8
0x1800137c5  ja      loc_180013C95
0x1800137cb  lea     esi, [rbx+8]
0x1800137ce  cmp     esi, ebx
0x1800137d0  jb      loc_180013A1B
0x1800137d6  mov     rcx, cs:LdapHeap; hHeap
0x1800137dd  mov     edx, 8; dwFlags
0x1800137e2  mov     r8d, esi; dwBytes
0x1800137e5  call    cs:__imp_HeapAlloc
0x1800137ec  nop     dword ptr [rax+rax+00h]
0x1800137f1  mov     rdi, rax
0x1800137f4  cmp     cs:g_fTracingOn, 0
0x1800137fb  jnz     loc_180013AE5
0x180013801  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x180013807  test    rdi, rdi
0x18001380a  jz      short loc_180013821
0x18001380c  mov     dword ptr [rdi], 7274534Ch
0x180013812  mov     [rdi+4], ebx
0x180013815  add     rdi, 8
0x180013819  add     eax, ebx
0x18001381b  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x180013821  cmp     cs:g_fTracingOn, 0
0x180013828  jnz     loc_180013B37
0x18001382e  test    rdi, rdi
0x180013831  jz      loc_180013C95
0x180013837  mov     r8, rbx; Size
0x18001383a  mov     rdx, r15; Src
0x18001383d  mov     rcx, rdi; void *
0x180013840  call    memcpy_0
0x180013845  mov     rcx, [rsp+68h+arg_0]; this
0x18001384a  mov     rdx, rdi; unsigned __int16 *
0x18001384d  call    ?LdapEncodeSimpleFilter@@YAKPEAVCLdapBer@@PEAG@Z; LdapEncodeSimpleFilter(CLdapBer *,ushort *)
0x180013852  mov     ebx, eax
0x180013854  mov     eax, [rdi-8]
0x180013857  cmp     eax, 6461424Ch
0x18001385c  jz      short loc_1800138C7
0x18001385e  cmp     eax, 6572464Ch
0x180013863  jz      loc_180013B79
0x180013869  cmp     cs:g_fTracingOn, 0
0x180013870  jnz     loc_180013BB9
0x180013876  mov     r9d, [rdi-8]
0x18001387a  cmp     r9d, 7274534Ch
0x180013881  jnz     loc_180013AA2
0x180013887  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x18001388d  mov     r8d, [rdi-4]
0x180013891  sub     eax, r8d
0x180013894  cmp     cs:g_fTracingOn, 0
0x18001389b  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x1800138a1  jnz     loc_180013BF9
0x1800138a7  mov     rcx, cs:LdapHeap; hHeap
0x1800138ae  lea     r8, [rdi-8]; lpMem
0x1800138b2  xor     edx, edx; dwFlags
0x1800138b4  mov     dword ptr [rdi-8], 6572464Ch
0x1800138bb  call    cs:__imp_HeapFree
0x1800138c2  nop     dword ptr [rax+rax+00h]
0x1800138c7  test    ebx, ebx
0x1800138c9  jnz     loc_180013C4C
0x1800138cf  mov     sil, 1
0x1800138d2  mov     r10, [rsp+68h+arg_0]
0x1800138d7  jmp     loc_18001368B
0x1800138dc  xor     edx, edx
0x1800138de  mov     rcx, r10; this
0x1800138e1  cmp     ax, 26h ; '&'
0x1800138e5  setnz   dl
0x1800138e8  add     edx, 0A0h; unsigned int
0x1800138ee  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x1800138f3  test    eax, eax
0x1800138f5  jnz     loc_180013E97
0x1800138fb  lea     rdi, [r15+2]
0x1800138ff  mov     rcx, rdi; unsigned __int16 *
0x180013902  call    ?FindRightParen@@YAJPEAG@Z; FindRightParen(ushort *)
0x180013907  movsxd  rbp, eax
0x18001390a  cmp     ebp, 0FFFFFFFFh
0x18001390d  jz      loc_180013E51
0x180013913  movzx   r15d, word ptr [rdi+rbp*2]
0x180013918  lea     r14, [rdi+rbp*2]
0x18001391c  xor     ecx, ecx
0x18001391e  mov     r8d, r12d; unsigned int
0x180013921  mov     [r14], cx
0x180013925  mov     rdx, rdi; unsigned __int16 *
0x180013928  mov     rcx, [rsp+68h+arg_0]; struct CLdapBer *
0x18001392d  call    ?LdapEncodeFilter@@YAKPEAVCLdapBer@@PEAGK@Z; LdapEncodeFilter(CLdapBer *,ushort *,ulong)
0x180013932  mov     ebx, eax
0x180013934  test    eax, eax
0x180013936  jnz     loc_180013E08
0x18001393c  mov     rcx, [rsp+68h+arg_0]; this
0x180013941  mov     [r14], r15w
0x180013945  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x18001394a  test    eax, eax
0x18001394c  jz      loc_180013A00
0x180013952  cmp     cs:g_fTracingOn, ebx
0x180013958  jz      short loc_180013988
0x18001395a  cmp     cs:g_fProviderEnabled, ebx
0x180013960  jz      short loc_180013988
0x180013962  test    cs:g_ulTraceFlags, 40000h
0x18001396d  jz      short loc_180013988
0x18001396f  mov     r8, [rsp+68h+arg_8]
0x180013974  lea     rdx, aLdapencodefilt_9; "LdapEncodeFilter : 4 Filter is '%S', er"...
0x18001397b  mov     r9d, eax
0x18001397e  mov     ecx, 40000h
0x180013983  call    LDAPClientPrint
0x180013988  mov     ebx, 57h ; 'W'
0x18001398d  mov     eax, ebx
0x18001398f  jmp     loc_180013747
0x180013994  mov     edx, 0A2h; unsigned int
0x180013999  mov     rcx, r10; this
0x18001399c  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x1800139a1  test    eax, eax
0x1800139a3  jnz     loc_180013FA4
0x1800139a9  lea     rdi, [r15+2]
0x1800139ad  mov     rcx, rdi; unsigned __int16 *
0x1800139b0  call    ?FindRightParen@@YAJPEAG@Z; FindRightParen(ushort *)
0x1800139b5  movsxd  rbp, eax
0x1800139b8  cmp     ebp, 0FFFFFFFFh
0x1800139bb  jz      loc_180013F5E
0x1800139c1  movzx   r15d, word ptr [rdi+rbp*2]
0x1800139c6  lea     r14, [rdi+rbp*2]
0x1800139ca  xor     ecx, ecx
0x1800139cc  mov     r8d, r12d; unsigned int
0x1800139cf  mov     [r14], cx
0x1800139d3  mov     rdx, rdi; unsigned __int16 *
0x1800139d6  mov     rcx, [rsp+68h+arg_0]; struct CLdapBer *
0x1800139db  call    ?LdapEncodeFilter@@YAKPEAVCLdapBer@@PEAGK@Z; LdapEncodeFilter(CLdapBer *,ushort *,ulong)
0x1800139e0  mov     ebx, eax
0x1800139e2  test    eax, eax
0x1800139e4  jnz     loc_180013F15
0x1800139ea  mov     rcx, [rsp+68h+arg_0]; this
0x1800139ef  mov     [r14], r15w
0x1800139f3  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x1800139f8  test    eax, eax
0x1800139fa  jnz     loc_180013ED6
0x180013a00  lea     eax, [rbp+1]
0x180013a03  movsxd  rcx, eax
0x180013a06  lea     r15, [rdi+rcx*2]
0x180013a0a  jmp     loc_1800138D2
0x180013a0f  add     r13d, r8d
0x180013a12  add     r15, 2
0x180013a16  jmp     loc_180013691
0x180013a1b  xor     edi, edi
0x180013a1d  mov     esi, r8d
0x180013a20  jmp     loc_1800137F4
0x180013a25  cmp     cs:g_fTracingOn, 0
0x180013a2c  jz      loc_180013988
0x180013a32  cmp     cs:g_fProviderEnabled, 0
0x180013a39  jz      loc_180013988
0x180013a3f  test    cs:g_ulTraceFlags, 40000h
0x180013a4a  jz      loc_180013988
0x180013a50  lea     rdx, aLdapencodefilt_0; "LdapEncodeFilter : too much recursion\n"
0x180013a57  mov     ecx, 40000h
0x180013a5c  call    LDAPClientTraceEvent
0x180013a61  jmp     loc_180013988
0x180013a66  cmp     cs:g_fProviderEnabled, 0
0x180013a6d  jz      loc_180013638
0x180013a73  test    cs:g_ulTraceFlags, 40000h
0x180013a7e  jz      loc_180013638
0x180013a84  mov     r8, r14
0x180013a87  lea     rdx, aLdapencodefilt_5; "LdapEncodeFilter : Filter is '%S'\n"
0x180013a8e  mov     ecx, 40000h
0x180013a93  call    LDAPClientPrint
0x180013a98  mov     r10, [rsp+68h+arg_0]
0x180013a9d  jmp     loc_180013638
0x180013aa2  cmp     cs:g_fTracingOn, 0
0x180013aa9  jz      loc_180013887
0x180013aaf  cmp     cs:g_fProviderEnabled, 0
0x180013ab6  jz      loc_180013887
0x180013abc  test    byte ptr cs:g_ulTraceFlags, 8
0x180013ac3  jz      loc_180013887
0x180013ac9  mov     r8d, 7274534Ch
0x180013acf  lea     rdx, aExpectedTag0xX; "Expected tag 0x%x but found tag 0x%x\n"
0x180013ad6  mov     ecx, 8
0x180013adb  call    LDAPClientPrint
0x180013ae0  jmp     loc_180013887
0x180013ae5  cmp     cs:g_fProviderEnabled, 0
0x180013aec  jz      loc_180013801
0x180013af2  test    byte ptr cs:g_ulTraceFlags, 8
0x180013af9  jz      loc_180013801
0x180013aff  mov     r9, rdi
0x180013b02  mov     [rsp+68h+var_48], 7274534Ch
0x180013b0a  mov     r8d, esi
0x180013b0d  lea     rdx, aLdapmallocAllo; "ldapMalloc allocated 0x%x bytes at addr"...
0x180013b14  mov     ecx, 8
0x180013b19  call    LDAPClientPrint
0x180013b1e  jmp     loc_180013801
0x180013b23  movzx   eax, word ptr [r15+2]
0x180013b28  add     r15, 2
0x180013b2c  cmp     ax, 20h ; ' '
0x180013b30  jz      short loc_180013B23
0x180013b32  jmp     loc_180013682
0x180013b37  cmp     cs:g_fProviderEnabled, 0
0x180013b3e  jz      loc_18001382E
0x180013b44  test    byte ptr cs:g_ulTraceFlags, 8
0x180013b4b  jz      loc_18001382E
0x180013b51  mov     [rsp+68h+var_40], eax
0x180013b55  lea     rdx, aLdapmalloc0x08; "ldapMalloc 0x%08x bytes at address 0x%x"...
0x180013b5c  mov     r9, rdi
0x180013b5f  mov     [rsp+68h+var_48], 7274534Ch
  ... truncated ...
```

# ScCacheEnumItems

- ea: `0x180037258`
- end: `0x1800374ee`
- name: `ScCacheEnumItems`
- size: `662`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180012d08`
- `0x180015728`
- `0x180030a84`

## callees

- `0x180009e76`
- `0x18000a408`
- `0x18000a590`
- `0x18000d9d0`
- `0x180013734`
- `0x180037258`
- `0x1800383f8`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall ScCacheEnumItems(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, unsigned int *a5)
{
  unsigned int *v7; // r13
  __int64 v8; // rcx
  unsigned int v9; // eax
  PVOID v10; // rcx
  __int64 v11; // r12
  unsigned int v12; // ebx
  __int64 v13; // rcx
  char *v14; // r15
  unsigned int i; // esi
  __int64 v16; // rdi
  __int64 v17; // r13
  void *v18; // rax
  __int64 v19; // rcx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  void *v22; // rax
  __int64 v23; // rcx
  unsigned int v25; // [rsp+78h] [rbp+10h] BYREF
  __int64 v26; // [rsp+80h] [rbp+18h] BYREF
  _QWORD *v27; // [rsp+88h] [rbp+20h]

  v27 = a4;
  v26 = 0;
  v25 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  v7 = a5;
  v8 = *(_QWORD *)(a1 + 40);
  *a4 = 0;
  *v7 = 0;
  v9 = CacheEnumItems(v8, &v26, &v25);
  v11 = v26;
  v12 = v9;
  if ( !v9 && v25 )
  {
    v14 = (char *)(*(__int64 (__fastcall **)(__int64))(a1 + 48))(16LL * v25);
    if ( v14 )
    {
      for ( i = 0; ; ++i )
      {
        v16 = 16LL * i;
        if ( i >= v25 )
          break;
        v17 = *(_QWORD *)(v16 + v11 + 8);
        v18 = (void *)(*(__int64 (__fastcall **)(_QWORD))(a1 + 48))(*(unsigned int *)(v17 + 8));
        *(_QWORD *)&v14[v16 + 8] = v18;
        if ( !v18 )
        {
          WppTraceIndent(v19, 2u);
          v12 = 8;
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v21 = 47;
LABEL_20:
            WPP_SF_s(v20[2], v21, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
            goto LABEL_27;
          }
          goto LABEL_27;
        }
        memcpy_0(v18, *(const void **)v17, *(unsigned int *)(v17 + 8));
      }
      *a5 = i;
      v22 = (void *)(*(__int64 (__fastcall **)(__int64))(a1 + 48))(16LL * i);
      v23 = (__int64)v27;
      *v27 = v22;
      if ( v22 )
      {
        memcpy_0(v22, v14, 16LL * i);
      }
      else
      {
        WppTraceIndent(v23, 2u);
        v12 = 8;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = 48;
          goto LABEL_20;
        }
      }
LABEL_27:
      (*(void (__fastcall **)(char *))(a1 + 56))(v14);
    }
    else
    {
      WppTraceIndent(v13, v12 + 2);
      v12 = 8;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
          WPP_pszIndent);
      }
    }
  }
  if ( v11 )
    CspFreeH(v11);
  WppTraceIndent((__int64)v10, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      49,
      (unsigned int)WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      v12);
  }
  return v12;
}

```

## disassembly

```asm
0x180037258  mov     rax, rsp
0x18003725b  mov     [rax+20h], r9
0x18003725f  mov     [rax+18h], r8
0x180037263  mov     [rax+10h], edx
0x180037266  push    rbx
0x180037267  push    rsi
0x180037268  push    rdi
0x180037269  push    r12
0x18003726b  push    r13
0x18003726d  push    r14
0x18003726f  push    r15
0x180037271  sub     rsp, 30h
0x180037275  xor     edx, edx
0x180037277  mov     qword ptr [rax+18h], 0
0x18003727f  mov     rbx, r9
0x180037282  mov     dword ptr [rax+10h], 0
0x180037289  mov     r14, rcx
0x18003728c  call    WppTraceIndent
0x180037291  mov     rcx, cs:WPP_GLOBAL_Control
0x180037298  lea     rdi, WPP_GLOBAL_Control
0x18003729f  cmp     rcx, rdi
0x1800372a2  jz      short loc_1800372CC
0x1800372a4  test    byte ptr [rcx+1Ch], 2
0x1800372a8  jz      short loc_1800372CC
0x1800372aa  cmp     byte ptr [rcx+19h], 5
0x1800372ae  jb      short loc_1800372CC
0x1800372b0  mov     r9, cs:WPP_pszIndent
0x1800372b7  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x1800372be  mov     rcx, [rcx+10h]
0x1800372c2  mov     edx, 2Dh ; '-'
0x1800372c7  call    WPP_SF_s
0x1800372cc  mov     r13, [rsp+68h+arg_20]
0x1800372d4  lea     r8, [rsp+68h+arg_8]
0x1800372d9  mov     rcx, [r14+28h]
0x1800372dd  lea     rdx, [rsp+68h+arg_10]
0x1800372e5  mov     qword ptr [rbx], 0
0x1800372ec  mov     dword ptr [r13+0], 0
0x1800372f4  call    CacheEnumItems
0x1800372f9  mov     r12, [rsp+68h+arg_10]
0x180037301  mov     ebx, eax
0x180037303  test    eax, eax
0x180037305  jnz     loc_18003748D
0x18003730b  cmp     [rsp+68h+arg_8], eax
0x18003730f  jz      loc_18003748D
0x180037315  mov     ecx, [rsp+68h+arg_8]
0x180037319  mov     rax, [r14+30h]
0x18003731d  shl     rcx, 4
0x180037321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037326  mov     r15, rax
0x180037329  test    rax, rax
0x18003732c  jnz     short loc_18003737D
0x18003732e  lea     edx, [rbx+2]
0x180037331  call    WppTraceIndent
0x180037336  lea     ebx, [r15+8]
0x18003733a  mov     rcx, cs:WPP_GLOBAL_Control
0x180037341  cmp     rcx, rdi
0x180037344  jz      loc_18003748D
0x18003734a  test    byte ptr [rcx+1Ch], 1
0x18003734e  jz      loc_18003748D
0x180037354  cmp     byte ptr [rcx+19h], 2
0x180037358  jb      loc_18003748D
0x18003735e  mov     r9, cs:WPP_pszIndent
0x180037365  lea     edx, [rbx+26h]
0x180037368  mov     rcx, [rcx+10h]
0x18003736c  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180037373  call    WPP_SF_s
0x180037378  jmp     loc_18003748D
0x18003737d  xor     esi, esi
0x18003737f  mov     edi, esi
0x180037381  shl     rdi, 4
0x180037385  cmp     esi, [rsp+68h+arg_8]
0x180037389  jnb     loc_180037415
0x18003738f  mov     r13, [rdi+r12+8]
0x180037394  mov     rax, [r14+30h]
0x180037398  mov     ecx, [r13+8]
0x18003739c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373a1  mov     [rdi+r15+8], rax
0x1800373a6  test    rax, rax
0x1800373a9  jz      short loc_1800373BF
0x1800373ab  mov     r8d, [r13+8]; Size
0x1800373af  mov     rcx, rax; void *
0x1800373b2  mov     rdx, [r13+0]; Src
0x1800373b6  call    memcpy_0
0x1800373bb  inc     esi
0x1800373bd  jmp     short loc_18003737F
0x1800373bf  mov     edx, 2
0x1800373c4  call    WppTraceIndent
0x1800373c9  mov     ebx, 8
0x1800373ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800373d5  lea     rdi, WPP_GLOBAL_Control
0x1800373dc  cmp     rcx, rdi
0x1800373df  jz      loc_180037481
0x1800373e5  test    byte ptr [rcx+1Ch], 1
0x1800373e9  jz      loc_180037481
0x1800373ef  cmp     byte ptr [rcx+19h], 2
0x1800373f3  jb      loc_180037481
0x1800373f9  lea     edx, [rbx+27h]
0x1800373fc  mov     r9, cs:WPP_pszIndent
0x180037403  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x18003740a  mov     rcx, [rcx+10h]
0x18003740e  call    WPP_SF_s
0x180037413  jmp     short loc_180037481
0x180037415  mov     rax, [rsp+68h+arg_20]
0x18003741d  mov     rcx, rdi
0x180037420  mov     [rax], esi
0x180037422  mov     rax, [r14+30h]
0x180037426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003742b  mov     rcx, [rsp+68h+arg_18]
0x180037433  mov     [rcx], rax
0x180037436  test    rax, rax
0x180037439  jnz     short loc_18003746C
0x18003743b  lea     edx, [rax+2]
0x18003743e  call    WppTraceIndent
0x180037443  mov     ebx, 8
0x180037448  mov     rcx, cs:WPP_GLOBAL_Control
0x18003744f  lea     rdi, WPP_GLOBAL_Control
0x180037456  cmp     rcx, rdi
0x180037459  jz      short loc_180037481
0x18003745b  test    byte ptr [rcx+1Ch], 1
0x18003745f  jz      short loc_180037481
0x180037461  cmp     byte ptr [rcx+19h], 2
0x180037465  jb      short loc_180037481
0x180037467  lea     edx, [rbx+28h]
0x18003746a  jmp     short loc_1800373FC
0x18003746c  mov     r8, rdi; Size
0x18003746f  mov     rdx, r15; Src
0x180037472  mov     rcx, rax; void *
0x180037475  call    memcpy_0
0x18003747a  lea     rdi, WPP_GLOBAL_Control
0x180037481  mov     rax, [r14+38h]
0x180037485  mov     rcx, r15
0x180037488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003748d  test    r12, r12
0x180037490  jz      short loc_18003749A
0x180037492  mov     rcx, r12
0x180037495  call    CspFreeH
0x18003749a  mov     edx, 1
0x18003749f  call    WppTraceIndent
0x1800374a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800374ab  cmp     rcx, rdi
0x1800374ae  jz      short loc_1800374DC
0x1800374b0  test    byte ptr [rcx+1Ch], 2
0x1800374b4  jz      short loc_1800374DC
0x1800374b6  cmp     byte ptr [rcx+19h], 5
0x1800374ba  jb      short loc_1800374DC
0x1800374bc  mov     r9, cs:WPP_pszIndent
0x1800374c3  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x1800374ca  mov     rcx, [rcx+10h]
0x1800374ce  mov     edx, 31h ; '1'
0x1800374d3  mov     [rsp+68h+var_48], ebx
0x1800374d7  call    WPP_SF_sd
0x1800374dc  mov     eax, ebx
0x1800374de  add     rsp, 30h
0x1800374e2  pop     r15
0x1800374e4  pop     r14
0x1800374e6  pop     r13
0x1800374e8  pop     r12
0x1800374ea  pop     rdi
0x1800374eb  pop     rsi
0x1800374ec  pop     rbx
0x1800374ed  retn
```

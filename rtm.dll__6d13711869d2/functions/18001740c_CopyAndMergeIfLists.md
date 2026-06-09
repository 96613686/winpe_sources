# CopyAndMergeIfLists

- ea: `0x18001740c`
- end: `0x180017654`
- name: `CopyAndMergeIfLists`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180018070`

## callees

- `0x1800172b4`
- `0x18001740c`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180017515`
- `KERNEL32!HeapAlloc` at `0x180017515`
- `rtutils!RouterLogEventA` at `0x180017622`
- `rtutils!RouterLogEventA` at `0x180017622`

## string_xrefs

- `0x1800175cc`: `CreateOutInterfaceEntry : Could not allocateout interface entry %x`

## pseudocode

```c
void __fastcall CopyAndMergeIfLists(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v4; // rdi
  _QWORD *v5; // rbx
  unsigned int v6; // r9d
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // edx
  unsigned int v10; // r8d
  int v11; // ecx
  _OWORD *v12; // rax
  _QWORD *v13; // rcx
  int v14; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v15[2044]; // [rsp+34h] [rbp-834h] BYREF

  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  v4 = (_QWORD *)*a2;
  if ( (_QWORD *)*a2 != a2 )
  {
    v5 = (_QWORD *)*a1;
    if ( (_QWORD *)*a1 == a1 )
    {
LABEL_3:
      CopyAndAppendIfList(a1, v4, a2);
    }
    else
    {
      while ( v4 != a2 )
      {
        if ( v5 == a1 )
          goto LABEL_19;
        v6 = *((_DWORD *)v4 + 6);
        while ( 1 )
        {
          if ( *((_DWORD *)v5 + 6) >= v6 )
          {
            if ( *((_DWORD *)v5 + 6) > v6 )
              goto LABEL_19;
            v7 = *((_DWORD *)v5 + 7);
            if ( v7 >= *((_DWORD *)v4 + 7) )
            {
              if ( v7 > *((_DWORD *)v4 + 7) )
                goto LABEL_19;
              v8 = *((_DWORD *)v5 + 4);
              if ( v8 >= *((_DWORD *)v4 + 4) )
              {
                if ( v8 > *((_DWORD *)v4 + 4) )
                  goto LABEL_19;
                v9 = *((_DWORD *)v4 + 5);
                v10 = *((_DWORD *)v5 + 5);
                v11 = (unsigned __int8)v10 - (unsigned __int8)v9;
                if ( (unsigned __int8)v10 == (unsigned __int8)v9 )
                {
                  v11 = (*((_DWORD *)v5 + 5) & 0xFF00) - (*((_DWORD *)v4 + 5) & 0xFF00);
                  if ( !v11 )
                  {
                    v11 = (v10 & 0xFF0000) - (v9 & 0xFF0000);
                    if ( (v10 & 0xFF0000) == (v9 & 0xFF0000) )
                      v11 = ((v10 >> 8) & 0xFF0000) - ((v9 >> 8) & 0xFF0000);
                  }
                }
                if ( v11 >= 0 )
                  break;
              }
            }
          }
          v5 = (_QWORD *)*v5;
          if ( v5 == a1 )
            goto LABEL_19;
        }
        if ( v11 > 0 )
        {
LABEL_19:
          v12 = HeapAlloc(hHeap, 0, 0x48u);
          if ( !v12 )
          {
            if ( qword_18002B8A8 )
            {
              LOWORD(v14) = 0;
              FormatRRASErrorString(&v14, L"CreateOutInterfaceEntry : Could not allocateout interface entry %x", 8);
              ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v14);
            }
            if ( dword_18002BA54 )
              RouterLogEventA(qword_18002BA58, 1u, 0xC353u, 0, 0, 8u);
            return;
          }
          *v12 = *(_OWORD *)v4;
          v12[1] = *((_OWORD *)v4 + 1);
          v12[2] = *((_OWORD *)v4 + 2);
          v12[3] = *((_OWORD *)v4 + 3);
          *((_QWORD *)v12 + 8) = v4[8];
          v13 = (_QWORD *)v5[1];
          if ( (_QWORD *)*v13 != v5 )
            __fastfail(3u);
          *(_QWORD *)v12 = v5;
          *((_QWORD *)v12 + 1) = v13;
          *v13 = v12;
          v5[1] = v12;
        }
        else
        {
          if ( *((__int16 *)v4 + 17) < 0 )
          {
            *((_WORD *)v5 + 17) |= 0x8000u;
            *((_WORD *)v5 + 18) += *((_WORD *)v4 + 18);
          }
          if ( (*((_WORD *)v4 + 17) & 0x4000) != 0 )
          {
            *((_WORD *)v5 + 17) |= 0x4000u;
            *((_WORD *)v5 + 19) += *((_WORD *)v4 + 19);
          }
          v5 = (_QWORD *)*v5;
        }
        v4 = (_QWORD *)*v4;
        if ( v5 == a1 )
        {
          if ( v4 == a2 )
            return;
          goto LABEL_3;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18001740c  mov     [rsp+arg_8], rbx
0x180017411  mov     [rsp+arg_10], rbp
0x180017416  push    rsi
0x180017417  push    rdi
0x180017418  push    r12
0x18001741a  push    r14
0x18001741c  push    r15
0x18001741e  sub     rsp, 840h
0x180017425  mov     rax, cs:__security_cookie
0x18001742c  xor     rax, rsp
0x18001742f  mov     [rsp+868h+var_38], rax
0x180017437  mov     r14, rdx
0x18001743a  mov     rsi, rcx
0x18001743d  xor     ebp, ebp
0x18001743f  lea     rcx, [rsp+868h+var_834]; void *
0x180017444  xor     edx, edx; Val
0x180017446  mov     [rsp+868h+var_838], ebp
0x18001744a  mov     r8d, 7FCh; Size
0x180017450  call    memset_0
0x180017455  mov     rdi, [r14]
0x180017458  cmp     rdi, r14
0x18001745b  jz      loc_180017628
0x180017461  mov     rbx, [rsi]
0x180017464  cmp     rbx, rsi
0x180017467  jnz     short loc_18001747C
0x180017469  mov     r8, r14
0x18001746c  mov     rdx, rdi
0x18001746f  mov     rcx, rsi
0x180017472  call    CopyAndAppendIfList
0x180017477  jmp     loc_180017628
0x18001747c  mov     r12d, 0FF0000h
0x180017482  mov     r15d, 4000h
0x180017488  cmp     rdi, r14
0x18001748b  jz      loc_180017628
0x180017491  cmp     rbx, rsi
0x180017494  jz      short loc_180017508
0x180017496  mov     r9d, [rdi+18h]
0x18001749a  cmp     [rbx+18h], r9d
0x18001749e  jb      short loc_180017500
0x1800174a0  ja      short loc_180017508
0x1800174a2  mov     eax, [rbx+1Ch]
0x1800174a5  cmp     eax, [rdi+1Ch]
0x1800174a8  jb      short loc_180017500
0x1800174aa  ja      short loc_180017508
0x1800174ac  mov     eax, [rbx+10h]
0x1800174af  cmp     eax, [rdi+10h]
0x1800174b2  jb      short loc_180017500
0x1800174b4  ja      short loc_180017508
0x1800174b6  mov     edx, [rdi+14h]
0x1800174b9  mov     r8d, [rbx+14h]
0x1800174bd  movzx   eax, dl
0x1800174c0  movzx   ecx, r8b
0x1800174c4  sub     ecx, eax
0x1800174c6  jnz     short loc_1800174FC
0x1800174c8  mov     eax, edx
0x1800174ca  mov     ecx, r8d
0x1800174cd  and     eax, 0FF00h
0x1800174d2  and     ecx, 0FF00h
0x1800174d8  sub     ecx, eax
0x1800174da  jnz     short loc_1800174FC
0x1800174dc  mov     eax, edx
0x1800174de  mov     ecx, r8d
0x1800174e1  and     eax, r12d
0x1800174e4  and     ecx, r12d
0x1800174e7  sub     ecx, eax
0x1800174e9  jnz     short loc_1800174FC
0x1800174eb  shr     edx, 8
0x1800174ee  mov     ecx, r8d
0x1800174f1  shr     ecx, 8
0x1800174f4  and     edx, r12d
0x1800174f7  and     ecx, r12d
0x1800174fa  sub     ecx, edx
0x1800174fc  test    ecx, ecx
0x1800174fe  jns     short loc_18001757D
0x180017500  mov     rbx, [rbx]
0x180017503  cmp     rbx, rsi
0x180017506  jnz     short loc_18001749A
0x180017508  mov     rcx, cs:hHeap; hHeap
0x18001750f  xor     edx, edx; dwFlags
0x180017511  lea     r8d, [rdx+48h]; dwBytes
0x180017515  call    cs:__imp_HeapAlloc
0x18001751b  test    rax, rax
0x18001751e  jz      loc_1800175B6
0x180017524  movups  xmm0, xmmword ptr [rdi]
0x180017527  movups  xmmword ptr [rax], xmm0
0x18001752a  movups  xmm1, xmmword ptr [rdi+10h]
0x18001752e  movups  xmmword ptr [rax+10h], xmm1
0x180017532  movups  xmm0, xmmword ptr [rdi+20h]
0x180017536  movups  xmmword ptr [rax+20h], xmm0
0x18001753a  movups  xmm1, xmmword ptr [rdi+30h]
0x18001753e  movups  xmmword ptr [rax+30h], xmm1
0x180017542  movsd   xmm0, qword ptr [rdi+40h]
0x180017547  movsd   qword ptr [rax+40h], xmm0
0x18001754c  mov     rcx, [rbx+8]
0x180017550  cmp     [rcx], rbx
0x180017553  jnz     short loc_1800175AF
0x180017555  mov     [rax], rbx
0x180017558  mov     [rax+8], rcx
0x18001755c  mov     [rcx], rax
0x18001755f  mov     [rbx+8], rax
0x180017563  mov     rdi, [rdi]
0x180017566  cmp     rbx, rsi
0x180017569  jnz     loc_180017488
0x18001756f  cmp     rdi, r14
0x180017572  jz      loc_180017628
0x180017578  jmp     loc_180017469
0x18001757d  jg      short loc_180017508
0x18001757f  cmp     [rdi+22h], bp
0x180017583  jge     short loc_180017596
0x180017585  mov     eax, 8000h
0x18001758a  or      [rbx+22h], ax
0x18001758e  movzx   eax, word ptr [rdi+24h]
0x180017592  add     [rbx+24h], ax
0x180017596  test    [rdi+22h], r15w
0x18001759b  jz      short loc_1800175AA
0x18001759d  or      [rbx+22h], r15w
0x1800175a2  movzx   eax, word ptr [rdi+26h]
0x1800175a6  add     [rbx+26h], ax
0x1800175aa  mov     rbx, [rbx]
0x1800175ad  jmp     short loc_180017563
0x1800175af  mov     ecx, 3
0x1800175b4  int     29h; Win8: RtlFailFast(ecx)
0x1800175b6  cmp     cs:qword_18002B8A8, rbp
0x1800175bd  mov     ebx, 8
0x1800175c2  jz      short loc_1800175FC
0x1800175c4  mov     r8d, ebx
0x1800175c7  mov     word ptr [rsp+868h+var_838], bp
0x1800175cc  lea     rdx, aCreateoutinter; "CreateOutInterfaceEntry : Could not all"...
0x1800175d3  lea     rcx, [rsp+868h+var_838]
0x1800175d8  call    FormatRRASErrorString
0x1800175dd  mov     rdx, cs:qword_18002B8A8
0x1800175e4  lea     r8, [rsp+868h+var_838]
0x1800175e9  mov     rcx, cs:gMgmEtwContext
0x1800175f0  mov     rax, cs:gMgmTemplateFunc
0x1800175f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175fc  mov     edx, 1; dwEventType
0x180017601  cmp     cs:dword_18002BA54, edx
0x180017607  jb      short loc_180017628
0x180017609  mov     rcx, cs:qword_18002BA58; hLogHandle
0x180017610  xor     r9d, r9d; dwSubStringCount
0x180017613  mov     [rsp+868h+dwErrorCode], ebx; dwErrorCode
0x180017617  mov     r8d, 0C353h; dwMessageId
0x18001761d  mov     [rsp+868h+plpszSubStringArray], rbp; plpszSubStringArray
0x180017622  call    cs:__imp_RouterLogEventA
0x180017628  mov     rcx, [rsp+868h+var_38]
0x180017630  xor     rcx, rsp; StackCookie
0x180017633  call    __security_check_cookie
0x180017638  lea     r11, [rsp+868h+var_28]
0x180017640  mov     rbx, [r11+38h]
0x180017644  mov     rbp, [r11+40h]
0x180017648  mov     rsp, r11
0x18001764b  pop     r15
0x18001764d  pop     r14
0x18001764f  pop     r12
0x180017651  pop     rdi
0x180017652  pop     rsi
0x180017653  retn
```

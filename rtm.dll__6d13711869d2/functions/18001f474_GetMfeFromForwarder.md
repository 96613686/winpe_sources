# GetMfeFromForwarder

- ea: `0x18001f474`
- end: `0x18001f72c`
- name: `GetMfeFromForwarder`
- size: `696`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001e77c`
- `0x18001ed64`

## callees

- `0x18001f474`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001f4e9`
- `KERNEL32!HeapAlloc` at `0x18001f4e9`
- `KERNEL32!HeapFree` at `0x18001f699`
- `KERNEL32!HeapFree` at `0x18001f699`
- `rtutils!RouterLogEventA` at `0x18001f70a`
- `rtutils!RouterLogEventA` at `0x18001f70a`

## string_xrefs

- `0x18001f6c2`: `GetMfeFromForwarder : Failed to create MFE, error in multiplication`
- `0x18001f6ad`: `GetMfeFromForwarder : Failed to create MFE, error in addition`
- `0x18001f508`: `GetMfeFromForwarder : Failed to create MFE of size : %x`

## pseudocode

```c
void __fastcall GetMfeFromForwarder(__int64 a1, __int64 a2)
{
  unsigned __int64 v4; // rcx
  unsigned int v5; // esi
  _DWORD *v6; // rax
  _DWORD *v7; // rbx
  unsigned int v8; // eax
  __int64 v9; // r8
  _QWORD *v10; // rdi
  _QWORD *v11; // rdx
  __int64 v12; // r9
  int v13; // ecx
  int v14; // eax
  bool v15; // zf
  __int64 v16; // rdx
  const wchar_t *v17; // r8
  int v18; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v19[2044]; // [rsp+34h] [rbp-834h] BYREF

  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  if ( !*(_DWORD *)(a2 + 144) )
    return;
  v4 = 28LL * *(unsigned int *)(a2 + 80);
  if ( v4 > 0xFFFFFFFF )
  {
    v16 = qword_18002B8A8;
    if ( !qword_18002B8A8 )
      goto LABEL_31;
    v17 = L"GetMfeFromForwarder : Failed to create MFE, error in multiplication";
    goto LABEL_30;
  }
  v5 = v4 + 56;
  if ( (int)v4 + 56 >= (unsigned int)v4 )
  {
    v6 = HeapAlloc(hHeap, 0, v5);
    v7 = v6;
    if ( !v6 )
    {
      if ( qword_18002B8A8 )
      {
        LOWORD(v18) = 0;
        FormatRRASErrorString(&v18, L"GetMfeFromForwarder : Failed to create MFE of size : %x", v5);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v18);
      }
      if ( dword_18002BA54 )
        RouterLogEventA(qword_18002BA58, 1u, 0xC353u, 0, 0, 8u);
      return;
    }
    memset_0(v6, 0, 28 * (*(unsigned int *)(a2 + 80) + 2LL));
    *v7 = *(_DWORD *)(a1 + 32);
    v7[1] = *(_DWORD *)(a2 + 104);
    v7[2] = *(_DWORD *)(a2 + 108);
    v7[4] = *(_DWORD *)(a2 + 80);
    v8 = ((__int64 (__fastcall *)(_DWORD *))qword_18002B948)(v7);
    if ( v8 )
    {
      if ( qword_18002B8A8 )
      {
        LOWORD(v18) = 0;
        FormatRRASErrorString(&v18, L"GetMfeFromForwarder : Failed to get MFE from forwarder: %x", v8);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v18);
      }
      goto LABEL_25;
    }
    *(_OWORD *)(a2 + 184) = *(_OWORD *)v7;
    *(_OWORD *)(a2 + 200) = *((_OWORD *)v7 + 1);
    *(_OWORD *)(a2 + 216) = *((_OWORD *)v7 + 2);
    *(_QWORD *)(a2 + 232) = *((_QWORD *)v7 + 6);
    if ( !v7[4] )
      goto LABEL_25;
    v9 = 0;
    v10 = (_QWORD *)(a2 + 88);
LABEL_14:
    v11 = (_QWORD *)*v10;
    if ( (_QWORD *)*v10 == v10 )
      goto LABEL_24;
    v12 = 7LL * (unsigned int)v9;
    v13 = v7[v12 + 14];
    while ( 1 )
    {
      v14 = *((_DWORD *)v11 + 5);
      if ( v14 )
      {
        if ( *((_DWORD *)v11 + 4) != v13 )
          goto LABEL_21;
        v15 = v14 == v7[v12 + 15];
      }
      else
      {
        v15 = *((_DWORD *)v11 + 4) == v13;
      }
      if ( v15 )
      {
        *((_DWORD *)v11 + 10) = v7[7 * v9 + 14];
        *((_DWORD *)v11 + 11) = v7[v12 + 15];
        *((_DWORD *)v11 + 13) = v7[v12 + 17];
        *((_DWORD *)v11 + 14) = v7[v12 + 18];
        *((_DWORD *)v11 + 15) = v7[v12 + 19];
        *((_DWORD *)v11 + 16) = v7[v12 + 20];
LABEL_24:
        v9 = (unsigned int)(v9 + 1);
        if ( (unsigned int)v9 >= v7[4] )
        {
LABEL_25:
          HeapFree(hHeap, 0, v7);
          return;
        }
        goto LABEL_14;
      }
LABEL_21:
      v11 = (_QWORD *)*v11;
      if ( v11 == v10 )
        goto LABEL_24;
    }
  }
  v16 = qword_18002B8A8;
  if ( qword_18002B8A8 )
  {
    v17 = L"GetMfeFromForwarder : Failed to create MFE, error in addition";
LABEL_30:
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(gMgmEtwContext, v16, v17);
  }
LABEL_31:
  if ( dword_18002BA54 )
    RouterLogEventA(qword_18002BA58, 1u, 0xC353u, 0, 0, 0xDu);
}

```

## disassembly

```asm
0x18001f474  push    rbx
0x18001f476  push    rbp
0x18001f477  push    rsi
0x18001f478  push    rdi
0x18001f479  sub     rsp, 848h
0x18001f480  mov     rax, cs:__security_cookie
0x18001f487  xor     rax, rsp
0x18001f48a  mov     [rsp+868h+var_38], rax
0x18001f492  mov     rdi, rdx
0x18001f495  mov     rbp, rcx
0x18001f498  xor     eax, eax
0x18001f49a  lea     rcx, [rsp+868h+var_834]; void *
0x18001f49f  xor     edx, edx; Val
0x18001f4a1  mov     [rsp+868h+var_838], eax
0x18001f4a5  mov     r8d, 7FCh; Size
0x18001f4ab  call    memset_0
0x18001f4b0  cmp     dword ptr [rdi+90h], 0
0x18001f4b7  jz      loc_18001F710
0x18001f4bd  mov     eax, [rdi+50h]
0x18001f4c0  imul    rcx, rax, 1Ch
0x18001f4c4  mov     eax, 0FFFFFFFFh
0x18001f4c9  cmp     rcx, rax
0x18001f4cc  ja      loc_18001F6B6
0x18001f4d2  lea     esi, [rcx+38h]
0x18001f4d5  cmp     esi, ecx
0x18001f4d7  jb      loc_18001F6A1
0x18001f4dd  mov     rcx, cs:hHeap; hHeap
0x18001f4e4  xor     edx, edx; dwFlags
0x18001f4e6  mov     r8d, esi; dwBytes
0x18001f4e9  call    cs:__imp_HeapAlloc
0x18001f4ef  mov     rbx, rax
0x18001f4f2  test    rax, rax
0x18001f4f5  jnz     short loc_18001F552
0x18001f4f7  cmp     cs:qword_18002B8A8, rax
0x18001f4fe  jz      short loc_18001F538
0x18001f500  mov     r8d, esi
0x18001f503  mov     word ptr [rsp+868h+var_838], ax
0x18001f508  lea     rdx, aGetmfefromforw_0; "GetMfeFromForwarder : Failed to create "...
0x18001f50f  lea     rcx, [rsp+868h+var_838]
0x18001f514  call    FormatRRASErrorString
0x18001f519  mov     rdx, cs:qword_18002B8A8
0x18001f520  lea     r8, [rsp+868h+var_838]
0x18001f525  mov     rcx, cs:gMgmEtwContext
0x18001f52c  mov     rax, cs:gMgmTemplateFunc
0x18001f533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f538  cmp     cs:dword_18002BA54, 1
0x18001f53f  jb      loc_18001F710
0x18001f545  mov     [rsp+868h+dwErrorCode], 8
0x18001f54d  jmp     loc_18001F6ED
0x18001f552  mov     eax, [rdi+50h]
0x18001f555  xor     edx, edx; Val
0x18001f557  add     rax, 2
0x18001f55b  mov     rcx, rbx; void *
0x18001f55e  imul    r8, rax, 1Ch; Size
0x18001f562  call    memset_0
0x18001f567  mov     eax, [rbp+20h]
0x18001f56a  mov     rcx, rbx
0x18001f56d  mov     [rbx], eax
0x18001f56f  mov     eax, [rdi+68h]
0x18001f572  mov     [rbx+4], eax
0x18001f575  mov     eax, [rdi+6Ch]
0x18001f578  mov     [rbx+8], eax
0x18001f57b  mov     eax, [rdi+50h]
0x18001f57e  mov     [rbx+10h], eax
0x18001f581  mov     rax, cs:qword_18002B948
0x18001f588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f58d  test    eax, eax
0x18001f58f  jz      short loc_18001F5DE
0x18001f591  cmp     cs:qword_18002B8A8, 0
0x18001f599  jz      loc_18001F68D
0x18001f59f  xor     ecx, ecx
0x18001f5a1  lea     rdx, aGetmfefromforw_2; "GetMfeFromForwarder : Failed to get MFE"...
0x18001f5a8  mov     word ptr [rsp+868h+var_838], cx
0x18001f5ad  mov     r8d, eax
0x18001f5b0  lea     rcx, [rsp+868h+var_838]
0x18001f5b5  call    FormatRRASErrorString
0x18001f5ba  mov     rdx, cs:qword_18002B8A8
0x18001f5c1  lea     r8, [rsp+868h+var_838]
0x18001f5c6  mov     rcx, cs:gMgmEtwContext
0x18001f5cd  mov     rax, cs:gMgmTemplateFunc
0x18001f5d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5d9  jmp     loc_18001F68D
0x18001f5de  movups  xmm0, xmmword ptr [rbx]
0x18001f5e1  movups  xmmword ptr [rdi+0B8h], xmm0
0x18001f5e8  movups  xmm1, xmmword ptr [rbx+10h]
0x18001f5ec  movups  xmmword ptr [rdi+0C8h], xmm1
0x18001f5f3  movups  xmm0, xmmword ptr [rbx+20h]
0x18001f5f7  movups  xmmword ptr [rdi+0D8h], xmm0
0x18001f5fe  movsd   xmm1, qword ptr [rbx+30h]
0x18001f603  movsd   qword ptr [rdi+0E8h], xmm1
0x18001f60b  cmp     dword ptr [rbx+10h], 0
0x18001f60f  jbe     short loc_18001F68D
0x18001f611  xor     r8d, r8d
0x18001f614  add     rdi, 58h ; 'X'
0x18001f618  mov     rdx, [rdi]
0x18001f61b  cmp     rdx, rdi
0x18001f61e  jz      short loc_18001F684
0x18001f620  mov     r10d, r8d
0x18001f623  imul    r9, r10, 1Ch
0x18001f627  mov     ecx, [r9+rbx+38h]
0x18001f62c  mov     eax, [rdx+14h]
0x18001f62f  test    eax, eax
0x18001f631  jz      short loc_18001F63F
0x18001f633  cmp     [rdx+10h], ecx
0x18001f636  jnz     short loc_18001F644
0x18001f638  cmp     eax, [r9+rbx+3Ch]
0x18001f63d  jmp     short loc_18001F642
0x18001f63f  cmp     [rdx+10h], ecx
0x18001f642  jz      short loc_18001F64E
0x18001f644  mov     rdx, [rdx]
0x18001f647  cmp     rdx, rdi
0x18001f64a  jnz     short loc_18001F62C
0x18001f64c  jmp     short loc_18001F684
0x18001f64e  lea     rax, [r8+2]
0x18001f652  imul    rcx, rax, 1Ch
0x18001f656  mov     eax, [rcx+rbx]
0x18001f659  mov     [rdx+28h], eax
0x18001f65c  mov     eax, [r9+rbx+3Ch]
0x18001f661  mov     [rdx+2Ch], eax
0x18001f664  mov     eax, [r9+rbx+44h]
0x18001f669  mov     [rdx+34h], eax
0x18001f66c  mov     eax, [r9+rbx+48h]
0x18001f671  mov     [rdx+38h], eax
0x18001f674  mov     eax, [r9+rbx+4Ch]
0x18001f679  mov     [rdx+3Ch], eax
0x18001f67c  mov     eax, [r9+rbx+50h]
0x18001f681  mov     [rdx+40h], eax
0x18001f684  inc     r8d
0x18001f687  cmp     r8d, [rbx+10h]
0x18001f68b  jb      short loc_18001F618
0x18001f68d  mov     rcx, cs:hHeap; hHeap
0x18001f694  mov     r8, rbx; lpMem
0x18001f697  xor     edx, edx; dwFlags
0x18001f699  call    cs:__imp_HeapFree
0x18001f69f  jmp     short loc_18001F710
0x18001f6a1  mov     rdx, cs:qword_18002B8A8
0x18001f6a8  test    rdx, rdx
0x18001f6ab  jz      short loc_18001F6DC
0x18001f6ad  lea     r8, aGetmfefromforw_1; "GetMfeFromForwarder : Failed to create "...
0x18001f6b4  jmp     short loc_18001F6C9
0x18001f6b6  mov     rdx, cs:qword_18002B8A8
0x18001f6bd  test    rdx, rdx
0x18001f6c0  jz      short loc_18001F6DC
0x18001f6c2  lea     r8, aGetmfefromforw; "GetMfeFromForwarder : Failed to create "...
0x18001f6c9  mov     rcx, cs:gMgmEtwContext
0x18001f6d0  mov     rax, cs:gMgmTemplateFunc
0x18001f6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6dc  cmp     cs:dword_18002BA54, 1
0x18001f6e3  jb      short loc_18001F710
0x18001f6e5  mov     [rsp+868h+dwErrorCode], 0Dh; dwErrorCode
0x18001f6ed  mov     rcx, cs:qword_18002BA58; hLogHandle
0x18001f6f4  xor     r9d, r9d; dwSubStringCount
0x18001f6f7  mov     r8d, 0C353h; dwMessageId
0x18001f6fd  mov     [rsp+868h+plpszSubStringArray], 0; plpszSubStringArray
0x18001f706  lea     edx, [r9+1]; dwEventType
0x18001f70a  call    cs:__imp_RouterLogEventA
0x18001f710  mov     rcx, [rsp+868h+var_38]
0x18001f718  xor     rcx, rsp; StackCookie
0x18001f71b  call    __security_check_cookie
0x18001f720  add     rsp, 848h
0x18001f727  pop     rdi
0x18001f728  pop     rsi
0x18001f729  pop     rbp
0x18001f72a  pop     rbx
0x18001f72b  retn
```

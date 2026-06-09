# MungeAclForPrinter(_ACL *,_ACL * *)

- ea: `0x1800085c0`
- end: `0x180008836`
- name: `?MungeAclForPrinter@@YAHPEAU_ACL@@PEAPEAU1@@Z`
- size: `630`
- prototype: `__int64 __fastcall(struct _ACL *Src, struct _ACL **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008950`

## callees

- `0x1800083f0`
- `0x1800085c0`
- `0x18001d322`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008652`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008765`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008652`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008765`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180008724`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180008724`
- `KERNEL32!LocalSize` at `0x180008678`
- `KERNEL32!LocalSize` at `0x18000878b`
- `KERNEL32!LocalSize` at `0x180008678`
- `KERNEL32!LocalSize` at `0x18000878b`

## pseudocode

```c
__int64 __fastcall MungeAclForPrinter(struct _ACL *Src, struct _ACL **a2)
{
  struct _ACE_HEADER *v4; // rdi
  char *v5; // rbx
  WORD v6; // r13
  char *v7; // rsi
  __int64 v8; // rbx
  unsigned int v9; // ecx
  unsigned int v10; // eax
  struct _ACL *v11; // rax
  struct _ACL *v12; // rsi
  __int16 v13; // ax
  size_t AceSize; // r8
  __int64 v15; // rax
  __int64 v16; // r9
  struct _ACE_HEADER *AceSid; // r12
  unsigned int v18; // r15d
  __int64 v19; // rsi
  struct _ACE_HEADER *v20; // rax
  char *v21; // rsi
  __int64 v22; // rbx
  struct _ACL *v23; // rax
  struct _ACL *v24; // rsi
  __int16 v25; // ax
  __int64 v26; // rax

  if ( !a2 )
    return 0;
  *a2 = 0;
  if ( Src )
  {
    v4 = (struct _ACE_HEADER *)&Src[1];
    if ( Src->AceCount )
    {
      v5 = 0;
      v6 = 0;
      v7 = 0;
      do
      {
        if ( (v4[1].AceType & 0x10) != 0 && (v4->AceFlags & 9) == 1 )
        {
          if ( !v7 )
          {
            v8 = (unsigned int)((_DWORD)v4 - (_DWORD)Src);
            v9 = 3 * (Src->AclSize - (_DWORD)v8);
            v10 = v9 + v8;
            if ( v9 + (unsigned int)v8 < (unsigned int)v8 )
              return 0;
            if ( v10 < v9 )
              return 0;
            v11 = (struct _ACL *)LocalAlloc(0x40u, v10);
            *a2 = v11;
            v12 = v11;
            if ( !v11 )
              return 0;
            memcpy_0(v11, Src, (unsigned int)v8);
            v13 = LocalSize(v12);
            v7 = (char *)*a2;
            v5 = (char *)*a2 + v8;
            *((_WORD *)v7 + 1) = v13;
            *((_WORD *)v7 + 2) = v6;
          }
          AceSize = v4->AceSize;
          v4->AceFlags &= ~1u;
          memcpy_0(v5, v4, AceSize);
          v15 = *((unsigned __int16 *)v5 + 1);
          ++*((_WORD *)v7 + 2);
          v5 += v15;
          v4->AceFlags |= 9u;
        }
        if ( !v4->AceType && (*(_DWORD *)&v4[1] & 0xF0030) == 0xF0030 && (v4->AceFlags & 9) == 9 )
        {
          AceSid = GetAceSid(v4);
          if ( AceSid && (v18 = 0, v19 = v16, Src->AceCount) )
          {
            while ( 1 )
            {
              if ( !*(_BYTE *)v19 && (*(_DWORD *)(v19 + 4) & 0xF000C) == 0xF000C && (*(_BYTE *)(v19 + 1) & 8) == 0 )
              {
                v20 = GetAceSid((struct _ACE_HEADER *)v19);
                if ( EqualSid(AceSid, v20) )
                  break;
              }
              ++v18;
              v19 += *(unsigned __int16 *)(v19 + 2);
              if ( v18 >= Src->AceCount )
                goto LABEL_23;
            }
          }
          else
          {
LABEL_23:
            v21 = (char *)*a2;
            if ( !*a2 )
            {
              v22 = (unsigned int)((_DWORD)v4 - (_DWORD)Src);
              v23 = (struct _ACL *)LocalAlloc(0x40u, Src->AclSize + 2 * (Src->AclSize - (unsigned int)v22));
              *a2 = v23;
              v24 = v23;
              if ( !v23 )
                return 0;
              memcpy_0(v23, Src, (unsigned int)v22);
              v25 = LocalSize(v24);
              v21 = (char *)*a2;
              v5 = (char *)*a2 + v22;
              *((_WORD *)v21 + 1) = v25;
              *((_WORD *)v21 + 2) = v6;
            }
            memcpy_0(v5, v4, v4->AceSize);
            v5[1] &= ~1u;
            v26 = *((unsigned __int16 *)v5 + 1);
            v5[1] |= 0xAu;
            *((_DWORD *)v5 + 1) = 0x20000;
            v5 += v26;
            ++*((_WORD *)v21 + 2);
          }
        }
        v7 = (char *)*a2;
        if ( *a2 )
        {
          memcpy_0(v5, v4, v4->AceSize);
          v5 += *((unsigned __int16 *)v5 + 1);
          ++*((_WORD *)v7 + 2);
        }
        v4 = (struct _ACE_HEADER *)((char *)v4 + v4->AceSize);
        ++v6;
      }
      while ( v6 < Src->AceCount );
      if ( v7 )
        *((_WORD *)v7 + 1) = (_WORD)v5 - *(_WORD *)a2;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800085c0  push    rbx
0x1800085c2  push    rbp
0x1800085c3  push    rsi
0x1800085c4  push    rdi
0x1800085c5  push    r12
0x1800085c7  push    r13
0x1800085c9  push    r14
0x1800085cb  push    r15
0x1800085cd  sub     rsp, 28h
0x1800085d1  mov     r14, rdx
0x1800085d4  mov     rbp, rcx
0x1800085d7  test    rdx, rdx
0x1800085da  jz      loc_180008823
0x1800085e0  mov     qword ptr [rdx], 0
0x1800085e7  mov     r15d, 1
0x1800085ed  test    rcx, rcx
0x1800085f0  jz      loc_18000881E
0x1800085f6  xor     eax, eax
0x1800085f8  lea     r9, [rcx+8]
0x1800085fc  mov     rdi, r9
0x1800085ff  cmp     ax, [rcx+4]
0x180008603  jnb     loc_18000881E
0x180008609  xor     ebx, ebx
0x18000860b  xor     r13d, r13d
0x18000860e  xor     esi, esi
0x180008610  test    byte ptr [rdi+4], 10h
0x180008614  jz      loc_1800086B5
0x18000861a  mov     al, [rdi+1]
0x18000861d  and     al, 9
0x18000861f  cmp     al, r15b
0x180008622  jnz     loc_1800086B5
0x180008628  test    rsi, rsi
0x18000862b  jnz     short loc_18000868D
0x18000862d  movzx   eax, word ptr [rbp+2]
0x180008631  mov     ebx, edi
0x180008633  sub     ebx, ebp
0x180008635  sub     eax, ebx
0x180008637  lea     ecx, [rax+rax*2]
0x18000863a  lea     eax, [rcx+rbx]
0x18000863d  cmp     eax, ebx
0x18000863f  jb      loc_180008823
0x180008645  cmp     eax, ecx
0x180008647  jb      loc_180008823
0x18000864d  mov     edx, eax; uBytes
0x18000864f  lea     ecx, [rsi+40h]; uFlags
0x180008652  call    cs:__imp_LocalAlloc
0x180008658  mov     [r14], rax
0x18000865b  mov     rsi, rax
0x18000865e  test    rax, rax
0x180008661  jz      loc_180008823
0x180008667  mov     r8d, ebx; Size
0x18000866a  mov     rdx, rbp; Src
0x18000866d  mov     rcx, rax; void *
0x180008670  call    memcpy_0
0x180008675  mov     rcx, rsi; hMem
0x180008678  call    cs:__imp_LocalSize
0x18000867e  mov     rsi, [r14]
0x180008681  add     rbx, rsi
0x180008684  mov     [rsi+2], ax
0x180008688  mov     [rsi+4], r13w
0x18000868d  movzx   r8d, word ptr [rdi+2]; Size
0x180008692  mov     rdx, rdi; Src
0x180008695  and     byte ptr [rdi+1], 0FEh
0x180008699  mov     rcx, rbx; void *
0x18000869c  call    memcpy_0
0x1800086a1  movzx   eax, word ptr [rbx+2]
0x1800086a5  lea     r9, [rbp+8]
0x1800086a9  add     [rsi+4], r15w
0x1800086ae  add     rbx, rax
0x1800086b1  or      byte ptr [rdi+1], 9
0x1800086b5  cmp     byte ptr [rdi], 0
0x1800086b8  jnz     loc_1800087D3
0x1800086be  mov     eax, [rdi+4]
0x1800086c1  and     eax, 0F0030h
0x1800086c6  cmp     eax, 0F0030h
0x1800086cb  jnz     loc_1800087D3
0x1800086d1  mov     al, [rdi+1]
0x1800086d4  and     al, 9
0x1800086d6  cmp     al, 9
0x1800086d8  jnz     loc_1800087D3
0x1800086de  mov     rcx, rdi; struct _ACE_HEADER *
0x1800086e1  call    ?GetAceSid@@YAPEAXPEAU_ACE_HEADER@@@Z; GetAceSid(_ACE_HEADER *)
0x1800086e6  mov     r12, rax
0x1800086e9  test    rax, rax
0x1800086ec  jz      short loc_18000874B
0x1800086ee  xor     r15d, r15d
0x1800086f1  xor     eax, eax
0x1800086f3  mov     rsi, r9
0x1800086f6  cmp     ax, [rbp+4]
0x1800086fa  jnb     short loc_180008745
0x1800086fc  cmp     byte ptr [rsi], 0
0x1800086ff  jnz     short loc_180008732
0x180008701  mov     eax, [rsi+4]
0x180008704  and     eax, 0F000Ch
0x180008709  cmp     eax, 0F000Ch
0x18000870e  jnz     short loc_180008732
0x180008710  test    byte ptr [rsi+1], 8
0x180008714  jnz     short loc_180008732
0x180008716  mov     rcx, rsi; struct _ACE_HEADER *
0x180008719  call    ?GetAceSid@@YAPEAXPEAU_ACE_HEADER@@@Z; GetAceSid(_ACE_HEADER *)
0x18000871e  mov     rdx, rax; pSid2
0x180008721  mov     rcx, r12; pSid1
0x180008724  call    cs:__imp_EqualSid
0x18000872a  test    eax, eax
0x18000872c  jnz     loc_1800087CD
0x180008732  movzx   eax, word ptr [rsi+2]
0x180008736  inc     r15d
0x180008739  add     rsi, rax
0x18000873c  movzx   eax, word ptr [rbp+4]
0x180008740  cmp     r15d, eax
0x180008743  jb      short loc_1800086FC
0x180008745  mov     r15d, 1
0x18000874b  mov     rsi, [r14]
0x18000874e  test    rsi, rsi
0x180008751  jnz     short loc_1800087A0
0x180008753  movzx   ecx, word ptr [rbp+2]
0x180008757  mov     ebx, edi
0x180008759  sub     ebx, ebp
0x18000875b  sub     ecx, ebx
0x18000875d  lea     edx, [rbx+rcx*2]
0x180008760  add     edx, ecx; uBytes
0x180008762  lea     ecx, [rsi+40h]; uFlags
0x180008765  call    cs:__imp_LocalAlloc
0x18000876b  mov     [r14], rax
0x18000876e  mov     rsi, rax
0x180008771  test    rax, rax
0x180008774  jz      loc_180008823
0x18000877a  mov     r8d, ebx; Size
0x18000877d  mov     rdx, rbp; Src
0x180008780  mov     rcx, rax; void *
0x180008783  call    memcpy_0
0x180008788  mov     rcx, rsi; hMem
0x18000878b  call    cs:__imp_LocalSize
0x180008791  mov     rsi, [r14]
0x180008794  add     rbx, rsi
0x180008797  mov     [rsi+2], ax
0x18000879b  mov     [rsi+4], r13w
0x1800087a0  movzx   r8d, word ptr [rdi+2]; Size
0x1800087a5  mov     rdx, rdi; Src
0x1800087a8  mov     rcx, rbx; void *
0x1800087ab  call    memcpy_0
0x1800087b0  and     byte ptr [rbx+1], 0FEh
0x1800087b4  movzx   eax, word ptr [rbx+2]
0x1800087b8  or      byte ptr [rbx+1], 0Ah
0x1800087bc  mov     dword ptr [rbx+4], 20000h
0x1800087c3  add     rbx, rax
0x1800087c6  add     [rsi+4], r15w
0x1800087cb  jmp     short loc_1800087D3
0x1800087cd  mov     r15d, 1
0x1800087d3  mov     rsi, [r14]
0x1800087d6  test    rsi, rsi
0x1800087d9  jz      short loc_1800087F7
0x1800087db  movzx   r8d, word ptr [rdi+2]; Size
0x1800087e0  mov     rdx, rdi; Src
0x1800087e3  mov     rcx, rbx; void *
0x1800087e6  call    memcpy_0
0x1800087eb  movzx   eax, word ptr [rbx+2]
0x1800087ef  add     rbx, rax
0x1800087f2  add     [rsi+4], r15w
0x1800087f7  movzx   ecx, word ptr [rdi+2]
0x1800087fb  lea     r9, [rbp+8]
0x1800087ff  add     rdi, rcx
0x180008802  add     r13w, r15w
0x180008806  cmp     r13w, [rbp+4]
0x18000880b  jb      loc_180008610
0x180008811  test    rsi, rsi
0x180008814  jz      short loc_18000881E
0x180008816  sub     bx, [r14]
0x18000881a  mov     [rsi+2], bx
0x18000881e  mov     eax, r15d
0x180008821  jmp     short loc_180008825
0x180008823  xor     eax, eax
0x180008825  add     rsp, 28h
0x180008829  pop     r15
0x18000882b  pop     r14
0x18000882d  pop     r13
0x18000882f  pop     r12
0x180008831  pop     rdi
0x180008832  pop     rsi
0x180008833  pop     rbp
0x180008834  pop     rbx
0x180008835  retn
```

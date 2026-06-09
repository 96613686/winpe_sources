# YReader::GraftNsAttDefsN(_stack<DeclAttDef *,4> *)

- ea: `0x10040b4c0`
- end: `0x10040b873`
- name: `?GraftNsAttDefsN@YReader@@AEAAXPEAV?$_stack@PEAVDeclAttDef@@$03@@@Z`
- size: `947`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x1004079d0`

## callees

- `0x100401780`
- `0x10040b4c0`
- `0x10040bfc0`
- `0x10040c7b0`
- `0x100415950`
- `0x100415c10`
- `0x1004236e0`
- `0x1004394f0`

## pseudocode

```c
void __fastcall YReader::GraftNsAttDefsN(__int64 a1, __int64 a2)
{
  __int64 *v2; // r13
  __int64 v4; // rbx
  __int64 v5; // r15
  unsigned int v6; // eax
  __int64 v7; // rax
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rbp
  __int64 v10; // rsi
  YReader *v11; // rcx
  struct StringPtr *v12; // rdx
  int v13; // r8d
  unsigned int v14; // eax
  __int64 v15; // rax
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // rbp
  __int64 v18; // rsi
  YReader *v19; // rcx
  int v20; // eax
  unsigned int v21; // ecx
  __int64 v22; // rcx
  __int64 v23; // rax
  int v24; // r8d
  unsigned __int64 v25; // r12
  __int64 v26; // rcx
  unsigned int v27; // edi
  __int64 v28; // r15
  __int64 v29; // rax
  __int64 v30; // rbx
  __int64 v31; // rsi
  int v32; // ebp
  __int64 v33; // [rsp+20h] [rbp-38h] BYREF
  int v34; // [rsp+28h] [rbp-30h]
  unsigned __int64 i; // [rsp+68h] [rbp+10h]

  v2 = *(__int64 **)(a2 + 16);
  for ( i = (unsigned __int64)&v2[*(unsigned int *)(a2 + 24)]; (unsigned __int64)v2 < i; ++v2 )
  {
    v4 = *v2;
    v5 = *(unsigned int *)(*v2 + 56);
    if ( (_DWORD)v5 )
    {
      v14 = *(_DWORD *)(v4 + 56);
      if ( v14 == dword_100450B48 && !memcmp(*(const void **)(v4 + 48), CodeStringPtr::xmlns, 2LL * v14) )
      {
        *(_DWORD *)(v4 + 132) = 1;
        v15 = *(unsigned int *)(a1 + 5304);
        if ( (_DWORD)v15 )
        {
          v16 = *(_QWORD *)(a1 + 5296);
          v17 = v16 + 152 * v15;
          if ( v16 < v17 )
          {
            v18 = *(unsigned int *)(v4 + 40);
            while ( (_DWORD)v18 != *(_DWORD *)(v16 + 8)
                 || memcmp(*(const void **)(v4 + 32), *(const void **)v16, 2 * v18) )
            {
              v16 += 152LL;
              if ( v16 >= v17 )
                goto LABEL_23;
            }
            *(_OWORD *)(v16 + 64) = *(_OWORD *)(v4 + 96);
            v24 = *(_DWORD *)(v4 + 172);
            if ( v24 )
            {
              v25 = v16 + 80;
              YReader::NormalizeTypedAttributeValue(v19, (struct StringPtr *)(v16 + 80), v24);
              v26 = *(unsigned int *)(v4 + 56);
              v27 = *(_DWORD *)(v4 + 40) - v26 - 1;
              v28 = *(_QWORD *)(v4 + 32) + 2 * v26;
              if ( *(_DWORD *)(a1 + 560) )
              {
                v29 = *(_QWORD *)(a1 + 552);
                v30 = v29 + 40LL * (unsigned int)(*(_DWORD *)(a1 + 560) - 1);
                v31 = v29 + 40;
                if ( v30 != v29 + 40 )
                {
                  v32 = *(_DWORD *)(a1 + 528);
                  while ( *(_DWORD *)(v30 + 32) == v32 )
                  {
                    if ( v27 == *(_DWORD *)(v30 + 8) && !memcmp((const void *)(v28 + 2), *(const void **)v30, 2LL * v27) )
                    {
                      if ( !*(_DWORD *)(v25 + 8) && v27 )
                      {
                        MXRRaiseException(-1072894362);
                        JUMPOUT(0x10040B872LL);
                      }
                      CloneStringPtr::Assign(
                        (CloneStringPtr *)(v30 + 16),
                        *(struct IMalloc **)(a1 + 520),
                        (struct StringPtr *)v25);
                      goto LABEL_28;
                    }
                    v30 -= 40;
                    if ( v30 == v31 )
                      goto LABEL_28;
                  }
                }
              }
            }
            continue;
          }
        }
LABEL_23:
        if ( *(_DWORD *)(v4 + 128) )
        {
          v12 = (struct StringPtr *)&v33;
          v20 = *(_DWORD *)(v4 + 40) - v5;
          v33 = *(_QWORD *)(v4 + 32) + 2 * (v5 + 1);
          v34 = v20 - 1;
          goto LABEL_25;
        }
      }
    }
    else
    {
      v6 = *(_DWORD *)(v4 + 40);
      if ( v6 == dword_100450B48 && !memcmp(*(const void **)(v4 + 32), CodeStringPtr::xmlns, 2LL * v6) )
      {
        *(_DWORD *)(v4 + 132) = 1;
        v7 = *(unsigned int *)(a1 + 5304);
        if ( (_DWORD)v7 )
        {
          v8 = *(_QWORD *)(a1 + 5296);
          v9 = v8 + 152 * v7;
          if ( v8 < v9 )
          {
            v10 = *(unsigned int *)(v4 + 40);
            while ( (_DWORD)v10 != *(_DWORD *)(v8 + 8) || memcmp(*(const void **)(v4 + 32), *(const void **)v8, 2 * v10) )
            {
              v8 += 152LL;
              if ( v8 >= v9 )
                goto LABEL_11;
            }
            *(_OWORD *)(v8 + 64) = *(_OWORD *)(v4 + 96);
            v13 = *(_DWORD *)(v4 + 172);
            if ( v13 )
            {
              YReader::NormalizeTypedAttributeValue(v11, (struct StringPtr *)(v8 + 80), v13);
              NamespaceSupport::PatchPrefix(
                (NamespaceSupport *)(a1 + 512),
                (struct StringPtr *)&CodeStringPtr::empty,
                (struct StringPtr *)(v8 + 80));
            }
            continue;
          }
        }
LABEL_11:
        if ( *(_DWORD *)(v4 + 128) )
        {
          v12 = (struct StringPtr *)&CodeStringPtr::empty;
LABEL_25:
          NamespaceSupport::PushPrefix((NamespaceSupport *)(a1 + 512), v12, (struct StringPtr *)(v4 + 112));
          *(_OWORD *)(v4 + 64) = *(_OWORD *)&CodeStringPtr::xmlnsUri;
          *(_OWORD *)(v4 + 80) = CodeStringPtr::empty;
          v21 = *(_DWORD *)(a1 + 5304);
          if ( *(_DWORD *)(a1 + 5308) == v21 )
          {
            _stack<Attribute,16>::grow(a1 + 5280);
            v21 = *(_DWORD *)(a1 + 5304);
          }
          *(_DWORD *)(a1 + 5304) = v21 + 1;
          v22 = 152LL * v21;
          v23 = *(_QWORD *)(a1 + 5296);
          *(_OWORD *)(v22 + v23) = *(_OWORD *)(v4 + 32);
          *(_OWORD *)(v22 + v23 + 16) = *(_OWORD *)(v4 + 48);
          *(_OWORD *)(v22 + v23 + 32) = *(_OWORD *)(v4 + 64);
          *(_OWORD *)(v22 + v23 + 48) = *(_OWORD *)(v4 + 80);
          *(_OWORD *)(v22 + v23 + 64) = *(_OWORD *)(v4 + 96);
          *(_OWORD *)(v22 + v23 + 80) = *(_OWORD *)(v4 + 112);
          *(_OWORD *)(v22 + v23 + 96) = *(_OWORD *)(v4 + 128);
          *(_OWORD *)(v22 + v23 + 112) = *(_OWORD *)(v4 + 144);
          *(_OWORD *)(v22 + v23 + 128) = *(_OWORD *)(v4 + 160);
          *(_QWORD *)(v22 + v23 + 144) = *(_QWORD *)(v4 + 176);
        }
      }
    }
LABEL_28:
    ;
  }
}

```

## disassembly

```asm
0x10040b4c0  push    r13
0x10040b4c2  push    r14
0x10040b4c4  sub     rsp, 48h
0x10040b4c8  mov     r13, [rdx+10h]
0x10040b4cc  mov     r14, rcx
0x10040b4cf  mov     eax, [rdx+18h]
0x10040b4d2  lea     rax, ds:0[rax*8]
0x10040b4da  add     rax, r13
0x10040b4dd  mov     [rsp+58h+arg_8], rax
0x10040b4e2  cmp     r13, rax
0x10040b4e5  jnb     loc_10040B7A1
0x10040b4eb  mov     [rsp+58h+arg_0], rbx
0x10040b4f0  mov     [rsp+58h+arg_10], rbp
0x10040b4f5  mov     [rsp+58h+arg_18], rsi
0x10040b4fa  mov     [rsp+58h+var_18], rdi
0x10040b4ff  mov     [rsp+58h+var_20], r12
0x10040b504  mov     [rsp+58h+var_28], r15
0x10040b509  nop     dword ptr [rax+00000000h]
0x10040b510  mov     rbx, [r13+0]
0x10040b514  mov     r15d, [rbx+38h]
0x10040b518  test    r15d, r15d
0x10040b51b  jnz     loc_10040B5FD
0x10040b521  mov     eax, [rbx+28h]
0x10040b524  cmp     eax, cs:dword_100450B48
0x10040b52a  jnz     loc_10040B774
0x10040b530  mov     rdx, cs:?xmlns@CodeStringPtr@@2UStringPtr@@A; Buf2
0x10040b537  mov     r8d, eax
0x10040b53a  mov     rcx, [rbx+20h]; Buf1
0x10040b53e  add     r8, r8; Size
0x10040b541  call    memcmp
0x10040b546  test    eax, eax
0x10040b548  jnz     loc_10040B774
0x10040b54e  mov     dword ptr [rbx+84h], 1
0x10040b558  mov     eax, [r14+14B8h]
0x10040b55f  test    eax, eax
0x10040b561  jz      short loc_10040B5A7
0x10040b563  mov     rdi, [r14+14B0h]
0x10040b56a  imul    rbp, rax, 98h
0x10040b571  add     rbp, rdi
0x10040b574  cmp     rdi, rbp
0x10040b577  jnb     short loc_10040B5A7
0x10040b579  mov     esi, [rbx+28h]
0x10040b57c  nop     dword ptr [rax+00h]
0x10040b580  cmp     esi, [rdi+8]
0x10040b583  jnz     short loc_10040B59B
0x10040b585  mov     rdx, [rdi]; Buf2
0x10040b588  mov     r8, rsi
0x10040b58b  mov     rcx, [rbx+20h]; Buf1
0x10040b58f  add     r8, r8; Size
0x10040b592  call    memcmp
0x10040b597  test    eax, eax
0x10040b599  jz      short loc_10040B5C0
0x10040b59b  add     rdi, 98h
0x10040b5a2  cmp     rdi, rbp
0x10040b5a5  jb      short loc_10040B580
0x10040b5a7  cmp     dword ptr [rbx+80h], 0
0x10040b5ae  jz      loc_10040B774
0x10040b5b4  lea     rdx, ?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x10040b5bb  jmp     loc_10040B6B2
0x10040b5c0  movups  xmm0, xmmword ptr [rbx+60h]
0x10040b5c4  movups  xmmword ptr [rdi+40h], xmm0
0x10040b5c8  mov     r8d, [rbx+0ACh]; int
0x10040b5cf  test    r8d, r8d
0x10040b5d2  jz      loc_10040B774
0x10040b5d8  lea     rdx, [rdi+50h]; struct StringPtr *
0x10040b5dc  call    ?NormalizeTypedAttributeValue@YReader@@AEAAXPEAUStringPtr@@H@Z; YReader::NormalizeTypedAttributeValue(StringPtr *,int)
0x10040b5e1  lea     rcx, [r14+200h]; this
0x10040b5e8  lea     r8, [rdi+50h]; struct StringPtr *
0x10040b5ec  lea     rdx, ?empty@CodeStringPtr@@2UStringPtr@@A; struct StringPtr *
0x10040b5f3  call    ?PatchPrefix@NamespaceSupport@@QEAAXPEAUStringPtr@@0@Z; NamespaceSupport::PatchPrefix(StringPtr *,StringPtr *)
0x10040b5f8  jmp     loc_10040B774
0x10040b5fd  mov     eax, [rbx+38h]
0x10040b600  cmp     eax, cs:dword_100450B48
0x10040b606  jnz     loc_10040B774
0x10040b60c  mov     rdx, cs:?xmlns@CodeStringPtr@@2UStringPtr@@A; Buf2
0x10040b613  mov     r8d, eax
0x10040b616  mov     rcx, [rbx+30h]; Buf1
0x10040b61a  add     r8, r8; Size
0x10040b61d  call    memcmp
0x10040b622  test    eax, eax
0x10040b624  jnz     loc_10040B774
0x10040b62a  mov     dword ptr [rbx+84h], 1
0x10040b634  mov     eax, [r14+14B8h]
0x10040b63b  test    eax, eax
0x10040b63d  jz      short loc_10040B683
0x10040b63f  mov     rdi, [r14+14B0h]
0x10040b646  imul    rbp, rax, 98h
0x10040b64d  add     rbp, rdi
0x10040b650  cmp     rdi, rbp
0x10040b653  jnb     short loc_10040B683
0x10040b655  mov     esi, [rbx+28h]
0x10040b658  cmp     esi, [rdi+8]
0x10040b65b  jnz     short loc_10040B677
0x10040b65d  mov     rdx, [rdi]; Buf2
0x10040b660  mov     r8, rsi
0x10040b663  mov     rcx, [rbx+20h]; Buf1
0x10040b667  add     r8, r8; Size
0x10040b66a  call    memcmp
0x10040b66f  test    eax, eax
0x10040b671  jz      loc_10040B7AA
0x10040b677  add     rdi, 98h
0x10040b67e  cmp     rdi, rbp
0x10040b681  jb      short loc_10040B658
0x10040b683  cmp     dword ptr [rbx+80h], 0
0x10040b68a  jz      loc_10040B774
0x10040b690  mov     rax, [rbx+20h]
0x10040b694  lea     rcx, [r15+1]
0x10040b698  lea     rdx, [rsp+58h+var_38]; struct StringPtr *
0x10040b69d  lea     rcx, [rax+rcx*2]
0x10040b6a1  mov     eax, [rbx+28h]
0x10040b6a4  sub     eax, r15d
0x10040b6a7  mov     [rsp+58h+var_38], rcx
0x10040b6ac  dec     eax
0x10040b6ae  mov     [rsp+58h+var_30], eax
0x10040b6b2  lea     r8, [rbx+70h]; struct StringPtr *
0x10040b6b6  lea     rcx, [r14+200h]; this
0x10040b6bd  call    ?PushPrefix@NamespaceSupport@@QEAAXPEAUStringPtr@@0@Z; NamespaceSupport::PushPrefix(StringPtr *,StringPtr *)
0x10040b6c2  movups  xmm0, xmmword ptr cs:?xmlnsUri@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::xmlnsUri
0x10040b6c9  lea     rdi, [r14+14A0h]
0x10040b6d0  movups  xmmword ptr [rbx+40h], xmm0
0x10040b6d4  movups  xmm1, xmmword ptr cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x10040b6db  movups  xmmword ptr [rbx+50h], xmm1
0x10040b6df  mov     ecx, [rdi+18h]
0x10040b6e2  cmp     [rdi+1Ch], ecx
0x10040b6e5  jnz     short loc_10040B6F4
0x10040b6e7  xor     edx, edx
0x10040b6e9  mov     rcx, rdi
0x10040b6ec  call    ?grow@?$_stack@UAttribute@@$0BA@@@AEAAXI@Z; _stack<Attribute,16>::grow(uint)
0x10040b6f1  mov     ecx, [rdi+18h]
0x10040b6f4  lea     eax, [rcx+1]
0x10040b6f7  mov     [rdi+18h], eax
0x10040b6fa  movups  xmm0, xmmword ptr [rbx+20h]
0x10040b6fe  mov     eax, ecx
0x10040b700  imul    rcx, rax, 98h
0x10040b707  mov     rax, [rdi+10h]
0x10040b70b  movups  xmmword ptr [rcx+rax], xmm0
0x10040b70f  movups  xmm1, xmmword ptr [rbx+30h]
0x10040b713  movups  xmmword ptr [rcx+rax+10h], xmm1
0x10040b718  movups  xmm0, xmmword ptr [rbx+40h]
0x10040b71c  movups  xmmword ptr [rcx+rax+20h], xmm0
0x10040b721  movups  xmm1, xmmword ptr [rbx+50h]
0x10040b725  movups  xmmword ptr [rcx+rax+30h], xmm1
0x10040b72a  movups  xmm0, xmmword ptr [rbx+60h]
0x10040b72e  movups  xmmword ptr [rcx+rax+40h], xmm0
0x10040b733  movups  xmm1, xmmword ptr [rbx+70h]
0x10040b737  movups  xmmword ptr [rcx+rax+50h], xmm1
0x10040b73c  movups  xmm0, xmmword ptr [rbx+80h]
0x10040b743  movups  xmmword ptr [rcx+rax+60h], xmm0
0x10040b748  movups  xmm1, xmmword ptr [rbx+90h]
0x10040b74f  movups  xmmword ptr [rcx+rax+70h], xmm1
0x10040b754  movups  xmm0, xmmword ptr [rbx+0A0h]
0x10040b75b  movups  xmmword ptr [rcx+rax+80h], xmm0
0x10040b763  movsd   xmm1, qword ptr [rbx+0B0h]
0x10040b76b  movsd   qword ptr [rcx+rax+90h], xmm1
0x10040b774  add     r13, 8
0x10040b778  cmp     r13, [rsp+58h+arg_8]
0x10040b77d  jb      loc_10040B510
0x10040b783  mov     r12, [rsp+58h+var_20]
0x10040b788  mov     rdi, [rsp+58h+var_18]
0x10040b78d  mov     rsi, [rsp+58h+arg_18]
0x10040b792  mov     rbp, [rsp+58h+arg_10]
0x10040b797  mov     rbx, [rsp+58h+arg_0]
0x10040b79c  mov     r15, [rsp+58h+var_28]
0x10040b7a1  add     rsp, 48h
0x10040b7a5  pop     r14
0x10040b7a7  pop     r13
0x10040b7a9  retn
0x10040b7aa  movups  xmm0, xmmword ptr [rbx+60h]
0x10040b7ae  movups  xmmword ptr [rdi+40h], xmm0
0x10040b7b2  mov     r8d, [rbx+0ACh]; int
0x10040b7b9  test    r8d, r8d
0x10040b7bc  jz      short loc_10040B774
0x10040b7be  lea     r12, [rdi+50h]
0x10040b7c2  mov     rdx, r12; struct StringPtr *
0x10040b7c5  call    ?NormalizeTypedAttributeValue@YReader@@AEAAXPEAUStringPtr@@H@Z; YReader::NormalizeTypedAttributeValue(StringPtr *,int)
0x10040b7ca  mov     ecx, [rbx+38h]
0x10040b7cd  mov     edi, [rbx+28h]
0x10040b7d0  mov     rax, [rbx+20h]
0x10040b7d4  sub     edi, ecx
0x10040b7d6  dec     edi
0x10040b7d8  cmp     dword ptr [r14+230h], 0
0x10040b7e0  lea     r15, [rax+rcx*2]
0x10040b7e4  jz      short loc_10040B774
0x10040b7e6  mov     eax, [r14+230h]
0x10040b7ed  dec     eax
0x10040b7ef  lea     rcx, [rax+rax*4]
0x10040b7f3  mov     rax, [r14+228h]
0x10040b7fa  lea     rbx, [rax+rcx*8]
0x10040b7fe  lea     rsi, [rax+28h]
0x10040b802  cmp     rbx, rsi
0x10040b805  jz      loc_10040B774
0x10040b80b  mov     ebp, [r14+210h]
0x10040b812  cmp     [rbx+20h], ebp
0x10040b815  jnz     loc_10040B774
0x10040b81b  cmp     edi, [rbx+8]
0x10040b81e  jnz     short loc_10040B836
0x10040b820  mov     rdx, [rbx]; Buf2
0x10040b823  lea     rcx, [r15+2]; Buf1
0x10040b827  mov     r8d, edi
0x10040b82a  add     r8, r8; Size
0x10040b82d  call    memcmp
0x10040b832  test    eax, eax
0x10040b834  jz      short loc_10040B844
0x10040b836  sub     rbx, 28h ; '('
0x10040b83a  cmp     rbx, rsi
0x10040b83d  jnz     short loc_10040B812
0x10040b83f  jmp     loc_10040B774
0x10040b844  cmp     dword ptr [r12+8], 0
0x10040b84a  jnz     short loc_10040B850
0x10040b84c  test    edi, edi
0x10040b84e  jnz     short loc_10040B868
0x10040b850  mov     rdx, [r14+208h]; struct IMalloc *
0x10040b857  lea     rcx, [rbx+10h]; this
0x10040b85b  mov     r8, r12; struct StringPtr *
0x10040b85e  call    ?Assign@CloneStringPtr@@QEAAXPEAUIMalloc@@PEAUStringPtr@@@Z; CloneStringPtr::Assign(IMalloc *,StringPtr *)
0x10040b863  jmp     loc_10040B774
0x10040b868  mov     ecx, 0C00CEE66h; int
0x10040b86d  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```

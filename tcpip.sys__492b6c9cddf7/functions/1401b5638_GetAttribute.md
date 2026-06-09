# GetAttribute

- ea: `0x1401b5638`
- end: `0x1401b5a18`
- name: `GetAttribute`
- size: `992`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1401b5bf4`

## callees

- `0x1400d7e1c`
- `0x1401b53f0`
- `0x1401b5638`
- `0x1401b5a20`
- `0x1401b5cd4`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1401b5824`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401b5824`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x1401b5720`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x1401b5720`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x1401b570e`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x1401b570e`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1401b56ed`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1401b56ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b574c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b59cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b59e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b574c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b59cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b59e3`
- `ntoskrnl!ExAllocatePool2` at `0x1401b56ac`
- `ntoskrnl!ExAllocatePool2` at `0x1401b57d0`
- `ntoskrnl!ExAllocatePool2` at `0x1401b58fd`
- `ntoskrnl!ExAllocatePool2` at `0x1401b56ac`
- `ntoskrnl!ExAllocatePool2` at `0x1401b57d0`
- `ntoskrnl!ExAllocatePool2` at `0x1401b58fd`

## pseudocode

```c
__int64 __fastcall GetAttribute(
        _QWORD *a1,
        __int64 a2,
        unsigned __int16 a3,
        struct _UNICODE_STRING **a4,
        unsigned int i)
{
  struct _UNICODE_STRING **v5; // r14
  unsigned int v9; // ecx
  PVOID v10; // r15
  int v11; // eax
  __int64 v12; // rcx
  NTSTATUS FqbnString; // esi
  __int64 v14; // rax
  unsigned __int16 *v15; // r12
  __int64 v16; // rax
  struct _UNICODE_STRING *v17; // r15
  WCHAR *v18; // rdi
  USHORT v19; // bx
  unsigned int v20; // eax
  unsigned int v21; // ecx
  __int64 v22; // rax
  __int64 v23; // rbx
  unsigned int v24; // ecx
  wchar_t *v25; // rdi
  size_t v26; // r13
  bool v27; // zf
  unsigned int v28; // r15d
  __int64 v30; // [rsp+30h] [rbp-30h]
  NTSTRSAFE_PWSTR ppszDestEnd; // [rsp+40h] [rbp-20h] BYREF
  _QWORD *Pool2; // [rsp+48h] [rbp-18h]
  size_t pcbRemaining[2]; // [rsp+50h] [rbp-10h] BYREF
  unsigned int pusResult; // [rsp+A8h] [rbp+48h] BYREF
  struct _UNICODE_STRING **v35; // [rsp+B8h] [rbp+58h]

  v35 = a4;
  v5 = a4;
  LODWORD(ppszDestEnd) = 0;
  if ( !a2 || a3 >= 5u )
    return 3221225485LL;
  if ( a4 )
    *a4 = 0;
  v9 = 128;
  if ( (unsigned __int16)(a3 - 3) > 1u )
    v9 = 256;
  for ( i = v9; ; v9 = i )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(66, v9, 1097884741);
    v10 = Pool2;
    if ( !Pool2 )
      break;
    if ( *a1 )
    {
      v11 = SeQuerySecurityAttributesToken(*a1, a2, 1, Pool2, i, &i);
    }
    else
    {
      v12 = a1[2];
      if ( v12 )
        v11 = SeQuerySecurityAttributesTokenAccessInformation(v12, a2, 1, Pool2, i, &i);
      else
        v11 = ZwQuerySecurityAttributesToken(a1[3], a2, 1, Pool2, i, &i);
    }
    FqbnString = v11;
    if ( v11 >= 0 )
    {
      if ( *((_DWORD *)Pool2 + 1) )
      {
        v14 = Pool2[1];
        if ( *(_DWORD *)(v14 + 24) )
        {
          v15 = *(unsigned __int16 **)(v14 + 32);
          if ( v15 )
          {
            if ( a3 )
            {
              switch ( a3 )
              {
                case 1u:
                  if ( !v5 || *(_WORD *)(v14 + 16) != 4 )
                    goto LABEL_52;
                  FqbnString = CreateFqbnString(*(_QWORD *)(v14 + 32), v5);
                  break;
                case 3u:
                case 4u:
                  goto LABEL_52;
                case 2u:
                  if ( *(_WORD *)(v14 + 16) == 16 && v5 )
                  {
                    v20 = *((_DWORD *)v15 + 2);
                    if ( v20 > 0xFFFF || (v21 = 4 * (unsigned __int16)v20, v21 > 0xFFFF) )
                    {
                      FqbnString = -1073741675;
                    }
                    else
                    {
                      LOWORD(pusResult) = 4 * v20;
                      FqbnString = RtlUShortAdd(v21, 2u, (USHORT *)&pusResult);
                      if ( FqbnString >= 0 )
                      {
                        FqbnString = CalcStringContiguousBufferSizeFromLength((unsigned __int16)pusResult, &ppszDestEnd);
                        if ( FqbnString >= 0 )
                        {
                          v22 = ExAllocatePool2(66, (unsigned int)ppszDestEnd, 1097884741);
                          v23 = v22;
                          if ( v22 )
                          {
                            v24 = (unsigned __int16)pusResult;
                            v25 = (wchar_t *)(v22 + 16);
                            *(_QWORD *)(v22 + 8) = v22 + 16;
                            *(_WORD *)(v22 + 2) = v24;
                            ppszDestEnd = (NTSTRSAFE_PWSTR)(v22 + 16);
                            v26 = v24;
                            *(_WORD *)v22 = v24 - 2;
                            memset((void *)(v22 + 16), 0, v24);
                            v27 = *((_DWORD *)v15 + 2) == 0;
                            pcbRemaining[0] = v26;
                            pusResult = 0;
                            if ( !v27 )
                            {
                              v28 = pusResult;
                              while ( 1 )
                              {
                                LODWORD(v30) = *(unsigned __int8 *)(v28 + *(_QWORD *)v15);
                                RtlStringCbPrintfExW(v25, v26, &ppszDestEnd, pcbRemaining, 0, L"%02x", v30);
                                if ( ++v28 >= *((_DWORD *)v15 + 2) )
                                  break;
                                v25 = ppszDestEnd;
                                v26 = pcbRemaining[0];
                              }
                              v5 = v35;
                              v10 = Pool2;
                            }
                            *v5 = (struct _UNICODE_STRING *)v23;
                          }
                          else
                          {
                            FqbnString = -1073741801;
                          }
                        }
                      }
                    }
                    break;
                  }
                  goto LABEL_52;
              }
            }
            else
            {
              if ( v5 && *(_WORD *)(v14 + 16) == 3 )
              {
                FqbnString = CalcStringContiguousBufferSizeFromLength(*v15, &ppszDestEnd);
                if ( FqbnString >= 0 )
                {
                  v16 = ExAllocatePool2(66, (unsigned int)ppszDestEnd, 1097884741);
                  v17 = (struct _UNICODE_STRING *)v16;
                  if ( v16 )
                  {
                    v18 = (WCHAR *)(v16 + 16);
                    v19 = *v15 + 2;
                    memset((void *)(v16 + 16), 0, v19);
                    v17->MaximumLength = v19;
                    v17->Length = 0;
                    v17->Buffer = v18;
                    RtlCopyUnicodeString(v17, (PCUNICODE_STRING)v15);
                    *v5 = v17;
                  }
                  else
                  {
                    FqbnString = -1073741801;
                  }
                  v10 = Pool2;
                }
                goto LABEL_53;
              }
LABEL_52:
              FqbnString = -1073741811;
            }
          }
        }
      }
LABEL_53:
      ExFreePoolWithTag(v10, 0);
      return (unsigned int)FqbnString;
    }
    if ( v11 == -1073741275 )
    {
      FqbnString = 0;
      goto LABEL_53;
    }
    if ( v11 != -1073741789 )
      goto LABEL_53;
    ExFreePoolWithTag(Pool2, 0);
  }
  return (unsigned int)-1073741801;
}

```

## disassembly

```asm
0x1401b5638  mov     [rsp-38h+arg_0], rbx
0x1401b563d  mov     [rsp-38h+arg_18], r9
0x1401b5642  push    rbp
0x1401b5643  push    rsi
0x1401b5644  push    rdi
0x1401b5645  push    r12
0x1401b5647  push    r13
0x1401b5649  push    r14
0x1401b564b  push    r15
0x1401b564d  mov     rbp, rsp
0x1401b5650  sub     rsp, 60h
0x1401b5654  xor     esi, esi
0x1401b5656  mov     r14, r9
0x1401b5659  mov     dword ptr [rbp+ppszDestEnd], esi
0x1401b565c  movzx   edi, r8w
0x1401b5660  mov     r12, rdx
0x1401b5663  mov     r13, rcx
0x1401b5666  test    rdx, rdx
0x1401b5669  jz      loc_1401B59FA
0x1401b566f  cmp     r8w, 5
0x1401b5674  jnb     loc_1401B59FA
0x1401b567a  mov     ebx, esi
0x1401b567c  test    r9, r9
0x1401b567f  jz      short loc_1401B5684
0x1401b5681  mov     [r9], rsi
0x1401b5684  mov     ecx, 80h
0x1401b5689  lea     eax, [rdi-3]
0x1401b568c  mov     edx, 100h
0x1401b5691  lea     r8d, [rcx-7Fh]
0x1401b5695  cmp     ax, r8w
0x1401b5699  cmova   ecx, edx
0x1401b569c  mov     [rbp+arg_20], ecx
0x1401b569f  mov     edx, ecx
0x1401b56a1  mov     r8d, 41706445h
0x1401b56a7  mov     ecx, 42h ; 'B'
0x1401b56ac  call    cs:__imp_ExAllocatePool2
0x1401b56b3  nop     dword ptr [rax+rax+00h]
0x1401b56b8  mov     [rbp+var_18], rax
0x1401b56bc  mov     r15, rax
0x1401b56bf  test    rax, rax
0x1401b56c2  jz      loc_1401B59F1
0x1401b56c8  mov     rcx, [r13+0]
0x1401b56cc  lea     rax, [rbp+arg_20]
0x1401b56d0  mov     [rsp+60h+pszFormat], rax
0x1401b56d5  mov     r9, r15
0x1401b56d8  mov     r8d, 1
0x1401b56de  test    rcx, rcx
0x1401b56e1  jz      short loc_1401B56FB
0x1401b56e3  mov     edx, [rbp+arg_20]
0x1401b56e6  mov     [rsp+60h+dwFlags], edx
0x1401b56ea  mov     rdx, r12
0x1401b56ed  call    cs:__imp_SeQuerySecurityAttributesToken
0x1401b56f4  nop     dword ptr [rax+rax+00h]
0x1401b56f9  jmp     short loc_1401B572C
0x1401b56fb  mov     rcx, [r13+10h]
0x1401b56ff  mov     rdx, r12
0x1401b5702  mov     eax, [rbp+arg_20]
0x1401b5705  mov     [rsp+60h+dwFlags], eax
0x1401b5709  test    rcx, rcx
0x1401b570c  jz      short loc_1401B571C
0x1401b570e  call    cs:__imp_SeQuerySecurityAttributesTokenAccessInformation
0x1401b5715  nop     dword ptr [rax+rax+00h]
0x1401b571a  jmp     short loc_1401B572C
0x1401b571c  mov     rcx, [r13+18h]
0x1401b5720  call    cs:__imp_ZwQuerySecurityAttributesToken
0x1401b5727  nop     dword ptr [rax+rax+00h]
0x1401b572c  xor     r10d, r10d
0x1401b572f  mov     esi, eax
0x1401b5731  test    eax, eax
0x1401b5733  jns     short loc_1401B5768
0x1401b5735  cmp     eax, 0C0000225h
0x1401b573a  jz      short loc_1401B5760
0x1401b573c  cmp     eax, 0C0000023h
0x1401b5741  jnz     loc_1401B59C8
0x1401b5747  xor     edx, edx; Tag
0x1401b5749  mov     rcx, r15; P
0x1401b574c  call    cs:__imp_ExFreePoolWithTag
0x1401b5753  nop     dword ptr [rax+rax+00h]
0x1401b5758  mov     ecx, [rbp+arg_20]
0x1401b575b  jmp     loc_1401B569F
0x1401b5760  mov     esi, r10d
0x1401b5763  jmp     loc_1401B59C8
0x1401b5768  cmp     [r15+4], r10d
0x1401b576c  jz      loc_1401B59C8
0x1401b5772  mov     rax, [r15+8]
0x1401b5776  cmp     [rax+18h], r10d
0x1401b577a  jz      loc_1401B59C8
0x1401b5780  mov     r12, [rax+20h]
0x1401b5784  test    r12, r12
0x1401b5787  jz      loc_1401B59C8
0x1401b578d  test    di, di
0x1401b5790  jnz     loc_1401B5837
0x1401b5796  test    r14, r14
0x1401b5799  jz      loc_1401B59C3
0x1401b579f  cmp     word ptr [rax+10h], 3
0x1401b57a4  jnz     loc_1401B59C3
0x1401b57aa  movzx   ecx, word ptr [r12]
0x1401b57af  lea     rdx, [rbp+ppszDestEnd]
0x1401b57b3  call    CalcStringContiguousBufferSizeFromLength
0x1401b57b8  mov     esi, eax
0x1401b57ba  test    eax, eax
0x1401b57bc  js      loc_1401B59C8
0x1401b57c2  mov     edx, dword ptr [rbp+ppszDestEnd]
0x1401b57c5  mov     ecx, 42h ; 'B'
0x1401b57ca  mov     r8d, 41706445h
0x1401b57d0  call    cs:__imp_ExAllocatePool2
0x1401b57d7  nop     dword ptr [rax+rax+00h]
0x1401b57dc  mov     r15, rax
0x1401b57df  test    rax, rax
0x1401b57e2  jnz     short loc_1401B57F2
0x1401b57e4  mov     esi, 0C0000017h
0x1401b57e9  mov     r15, [rbp+var_18]
0x1401b57ed  jmp     loc_1401B59C8
0x1401b57f2  lea     rdi, [rax+10h]
0x1401b57f6  xor     edx, edx; Val
0x1401b57f8  movzx   eax, word ptr [r12]
0x1401b57fd  mov     rcx, rdi; void *
0x1401b5800  add     ax, 2
0x1401b5804  movzx   ebx, ax
0x1401b5807  mov     r8d, ebx; Size
0x1401b580a  call    memset
0x1401b580f  xor     eax, eax
0x1401b5811  mov     [r15+2], bx
0x1401b5816  mov     rdx, r12; SourceString
0x1401b5819  mov     [r15], ax
0x1401b581d  mov     rcx, r15; DestinationString
0x1401b5820  mov     [r15+8], rdi
0x1401b5824  call    cs:__imp_RtlCopyUnicodeString
0x1401b582b  nop     dword ptr [rax+rax+00h]
0x1401b5830  xor     ebx, ebx
0x1401b5832  mov     [r14], r15
0x1401b5835  jmp     short loc_1401B57E9
0x1401b5837  mov     ecx, 1
0x1401b583c  cmp     di, cx
0x1401b583f  jnz     short loc_1401B5867
0x1401b5841  test    r14, r14
0x1401b5844  jz      loc_1401B59C3
0x1401b584a  cmp     word ptr [rax+10h], 4
0x1401b584f  jnz     loc_1401B59C3
0x1401b5855  mov     rdx, r14
0x1401b5858  mov     rcx, r12
0x1401b585b  call    CreateFqbnString
0x1401b5860  mov     esi, eax
0x1401b5862  jmp     loc_1401B59C8
0x1401b5867  cmp     di, 3
0x1401b586b  jz      loc_1401B59C3
0x1401b5871  cmp     di, 4
0x1401b5875  jz      loc_1401B59C3
0x1401b587b  mov     r13d, 2
0x1401b5881  cmp     di, r13w
0x1401b5885  jnz     loc_1401B59C8
0x1401b588b  cmp     word ptr [rax+10h], 10h
0x1401b5890  jnz     loc_1401B59C3
0x1401b5896  test    r14, r14
0x1401b5899  jz      loc_1401B59C3
0x1401b589f  mov     eax, [r12+8]
0x1401b58a4  mov     edx, 0FFFFh
0x1401b58a9  cmp     eax, edx
0x1401b58ab  ja      loc_1401B59BC
0x1401b58b1  movzx   ecx, ax
0x1401b58b4  shl     ecx, 2; usAugend
0x1401b58b7  cmp     ecx, edx
0x1401b58b9  ja      loc_1401B59BC
0x1401b58bf  mov     edx, r13d; usAddend
0x1401b58c2  mov     word ptr [rbp+pusResult], cx
0x1401b58c6  lea     r8, [rbp+pusResult]; pusResult
0x1401b58ca  call    RtlUShortAdd
0x1401b58cf  mov     esi, eax
0x1401b58d1  test    eax, eax
0x1401b58d3  js      loc_1401B59C8
0x1401b58d9  movzx   ecx, word ptr [rbp+pusResult]
0x1401b58dd  lea     rdx, [rbp+ppszDestEnd]
0x1401b58e1  call    CalcStringContiguousBufferSizeFromLength
0x1401b58e6  mov     esi, eax
0x1401b58e8  test    eax, eax
0x1401b58ea  js      loc_1401B59C8
0x1401b58f0  mov     edx, dword ptr [rbp+ppszDestEnd]
0x1401b58f3  lea     ecx, [r13+40h]
0x1401b58f7  mov     r8d, 41706445h
0x1401b58fd  call    cs:__imp_ExAllocatePool2
0x1401b5904  nop     dword ptr [rax+rax+00h]
0x1401b5909  mov     rbx, rax
0x1401b590c  test    rax, rax
0x1401b590f  jnz     short loc_1401B591B
0x1401b5911  mov     esi, 0C0000017h
0x1401b5916  jmp     loc_1401B59C8
0x1401b591b  movzx   ecx, word ptr [rbp+pusResult]
0x1401b591f  lea     rdi, [rax+10h]
0x1401b5923  mov     [rax+8], rdi
0x1401b5927  mov     r8d, ecx; Size
0x1401b592a  movzx   eax, cx
0x1401b592d  mov     [rbx+2], cx
0x1401b5931  sub     ax, r13w
0x1401b5935  mov     [rbp+ppszDestEnd], rdi
0x1401b5939  mov     r13d, ecx
0x1401b593c  mov     [rbx], ax
0x1401b593f  mov     rcx, rdi; void *
0x1401b5942  xor     edx, edx; Val
0x1401b5944  call    memset
0x1401b5949  cmp     dword ptr [r12+8], 0
0x1401b594f  mov     [rbp+pcbRemaining], r13
0x1401b5953  mov     [rbp+pusResult], 0
0x1401b595a  jbe     short loc_1401B59B5
0x1401b595c  mov     r15d, [rbp+pusResult]
0x1401b5960  mov     rax, [r12]
0x1401b5964  lea     r9, [rbp+pcbRemaining]; pcbRemaining
0x1401b5968  mov     r8d, r15d
0x1401b596b  mov     rdx, r13; cbDest
0x1401b596e  mov     rcx, rdi; pszDest
0x1401b5971  movzx   r8d, byte ptr [r8+rax]
0x1401b5976  lea     rax, a02x; "%02x"
0x1401b597d  mov     [rsp+60h+var_30], r8d
0x1401b5982  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x1401b5986  mov     [rsp+60h+pszFormat], rax; pszFormat
0x1401b598b  mov     qword ptr [rsp+60h+dwFlags], 0; dwFlags
0x1401b5994  call    RtlStringCbPrintfExW
0x1401b5999  inc     r15d
0x1401b599c  cmp     r15d, [r12+8]
0x1401b59a1  jnb     short loc_1401B59AD
0x1401b59a3  mov     rdi, [rbp+ppszDestEnd]
0x1401b59a7  mov     r13, [rbp+pcbRemaining]
0x1401b59ab  jmp     short loc_1401B5960
0x1401b59ad  mov     r14, [rbp+arg_18]
0x1401b59b1  mov     r15, [rbp+var_18]
0x1401b59b5  mov     [r14], rbx
0x1401b59b8  xor     ebx, ebx
0x1401b59ba  jmp     short loc_1401B59C8
0x1401b59bc  mov     esi, 0C0000095h
0x1401b59c1  jmp     short loc_1401B59C8
0x1401b59c3  mov     esi, 0C000000Dh
0x1401b59c8  xor     edx, edx; Tag
0x1401b59ca  mov     rcx, r15; P
0x1401b59cd  call    cs:__imp_ExFreePoolWithTag
0x1401b59d4  nop     dword ptr [rax+rax+00h]
0x1401b59d9  test    rbx, rbx
0x1401b59dc  jz      short loc_1401B59F6
0x1401b59de  xor     edx, edx; Tag
0x1401b59e0  mov     rcx, rbx; P
0x1401b59e3  call    cs:__imp_ExFreePoolWithTag
0x1401b59ea  nop     dword ptr [rax+rax+00h]
0x1401b59ef  jmp     short loc_1401B59F6
0x1401b59f1  mov     esi, 0C0000017h
0x1401b59f6  mov     eax, esi
0x1401b59f8  jmp     short loc_1401B59FF
0x1401b59fa  mov     eax, 0C000000Dh
0x1401b59ff  mov     rbx, [rsp+60h+arg_0]
0x1401b5a07  add     rsp, 60h
0x1401b5a0b  pop     r15
0x1401b5a0d  pop     r14
0x1401b5a0f  pop     r13
0x1401b5a11  pop     r12
0x1401b5a13  pop     rdi
0x1401b5a14  pop     rsi
0x1401b5a15  pop     rbp
0x1401b5a16  retn
```

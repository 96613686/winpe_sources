# GetAttribute

- ea: `0x1401b7338`
- end: `0x1401b7718`
- name: `GetAttribute`
- size: `992`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1401b78f4`

## callees

- `0x1400663fc`
- `0x1401b70f0`
- `0x1401b7338`
- `0x1401b7720`
- `0x1401b79d4`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1401b7524`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401b7524`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x1401b7420`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x1401b7420`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x1401b740e`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x1401b740e`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1401b73ed`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1401b73ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b744c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b76cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b76e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b744c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b76cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b76e3`
- `ntoskrnl!ExAllocatePool2` at `0x1401b73ac`
- `ntoskrnl!ExAllocatePool2` at `0x1401b74d0`
- `ntoskrnl!ExAllocatePool2` at `0x1401b75fd`
- `ntoskrnl!ExAllocatePool2` at `0x1401b73ac`
- `ntoskrnl!ExAllocatePool2` at `0x1401b74d0`
- `ntoskrnl!ExAllocatePool2` at `0x1401b75fd`

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
0x1401b7338  mov     [rsp-38h+arg_0], rbx
0x1401b733d  mov     [rsp-38h+arg_18], r9
0x1401b7342  push    rbp
0x1401b7343  push    rsi
0x1401b7344  push    rdi
0x1401b7345  push    r12
0x1401b7347  push    r13
0x1401b7349  push    r14
0x1401b734b  push    r15
0x1401b734d  mov     rbp, rsp
0x1401b7350  sub     rsp, 60h
0x1401b7354  xor     esi, esi
0x1401b7356  mov     r14, r9
0x1401b7359  mov     dword ptr [rbp+ppszDestEnd], esi
0x1401b735c  movzx   edi, r8w
0x1401b7360  mov     r12, rdx
0x1401b7363  mov     r13, rcx
0x1401b7366  test    rdx, rdx
0x1401b7369  jz      loc_1401B76FA
0x1401b736f  cmp     r8w, 5
0x1401b7374  jnb     loc_1401B76FA
0x1401b737a  mov     ebx, esi
0x1401b737c  test    r9, r9
0x1401b737f  jz      short loc_1401B7384
0x1401b7381  mov     [r9], rsi
0x1401b7384  mov     ecx, 80h
0x1401b7389  lea     eax, [rdi-3]
0x1401b738c  mov     edx, 100h
0x1401b7391  lea     r8d, [rcx-7Fh]
0x1401b7395  cmp     ax, r8w
0x1401b7399  cmova   ecx, edx
0x1401b739c  mov     [rbp+arg_20], ecx
0x1401b739f  mov     edx, ecx
0x1401b73a1  mov     r8d, 41706445h
0x1401b73a7  mov     ecx, 42h ; 'B'
0x1401b73ac  call    cs:__imp_ExAllocatePool2
0x1401b73b3  nop     dword ptr [rax+rax+00h]
0x1401b73b8  mov     [rbp+var_18], rax
0x1401b73bc  mov     r15, rax
0x1401b73bf  test    rax, rax
0x1401b73c2  jz      loc_1401B76F1
0x1401b73c8  mov     rcx, [r13+0]
0x1401b73cc  lea     rax, [rbp+arg_20]
0x1401b73d0  mov     [rsp+60h+pszFormat], rax
0x1401b73d5  mov     r9, r15
0x1401b73d8  mov     r8d, 1
0x1401b73de  test    rcx, rcx
0x1401b73e1  jz      short loc_1401B73FB
0x1401b73e3  mov     edx, [rbp+arg_20]
0x1401b73e6  mov     [rsp+60h+dwFlags], edx
0x1401b73ea  mov     rdx, r12
0x1401b73ed  call    cs:__imp_SeQuerySecurityAttributesToken
0x1401b73f4  nop     dword ptr [rax+rax+00h]
0x1401b73f9  jmp     short loc_1401B742C
0x1401b73fb  mov     rcx, [r13+10h]
0x1401b73ff  mov     rdx, r12
0x1401b7402  mov     eax, [rbp+arg_20]
0x1401b7405  mov     [rsp+60h+dwFlags], eax
0x1401b7409  test    rcx, rcx
0x1401b740c  jz      short loc_1401B741C
0x1401b740e  call    cs:__imp_SeQuerySecurityAttributesTokenAccessInformation
0x1401b7415  nop     dword ptr [rax+rax+00h]
0x1401b741a  jmp     short loc_1401B742C
0x1401b741c  mov     rcx, [r13+18h]
0x1401b7420  call    cs:__imp_ZwQuerySecurityAttributesToken
0x1401b7427  nop     dword ptr [rax+rax+00h]
0x1401b742c  xor     r10d, r10d
0x1401b742f  mov     esi, eax
0x1401b7431  test    eax, eax
0x1401b7433  jns     short loc_1401B7468
0x1401b7435  cmp     eax, 0C0000225h
0x1401b743a  jz      short loc_1401B7460
0x1401b743c  cmp     eax, 0C0000023h
0x1401b7441  jnz     loc_1401B76C8
0x1401b7447  xor     edx, edx; Tag
0x1401b7449  mov     rcx, r15; P
0x1401b744c  call    cs:__imp_ExFreePoolWithTag
0x1401b7453  nop     dword ptr [rax+rax+00h]
0x1401b7458  mov     ecx, [rbp+arg_20]
0x1401b745b  jmp     loc_1401B739F
0x1401b7460  mov     esi, r10d
0x1401b7463  jmp     loc_1401B76C8
0x1401b7468  cmp     [r15+4], r10d
0x1401b746c  jz      loc_1401B76C8
0x1401b7472  mov     rax, [r15+8]
0x1401b7476  cmp     [rax+18h], r10d
0x1401b747a  jz      loc_1401B76C8
0x1401b7480  mov     r12, [rax+20h]
0x1401b7484  test    r12, r12
0x1401b7487  jz      loc_1401B76C8
0x1401b748d  test    di, di
0x1401b7490  jnz     loc_1401B7537
0x1401b7496  test    r14, r14
0x1401b7499  jz      loc_1401B76C3
0x1401b749f  cmp     word ptr [rax+10h], 3
0x1401b74a4  jnz     loc_1401B76C3
0x1401b74aa  movzx   ecx, word ptr [r12]
0x1401b74af  lea     rdx, [rbp+ppszDestEnd]
0x1401b74b3  call    CalcStringContiguousBufferSizeFromLength
0x1401b74b8  mov     esi, eax
0x1401b74ba  test    eax, eax
0x1401b74bc  js      loc_1401B76C8
0x1401b74c2  mov     edx, dword ptr [rbp+ppszDestEnd]
0x1401b74c5  mov     ecx, 42h ; 'B'
0x1401b74ca  mov     r8d, 41706445h
0x1401b74d0  call    cs:__imp_ExAllocatePool2
0x1401b74d7  nop     dword ptr [rax+rax+00h]
0x1401b74dc  mov     r15, rax
0x1401b74df  test    rax, rax
0x1401b74e2  jnz     short loc_1401B74F2
0x1401b74e4  mov     esi, 0C0000017h
0x1401b74e9  mov     r15, [rbp+var_18]
0x1401b74ed  jmp     loc_1401B76C8
0x1401b74f2  lea     rdi, [rax+10h]
0x1401b74f6  xor     edx, edx; Val
0x1401b74f8  movzx   eax, word ptr [r12]
0x1401b74fd  mov     rcx, rdi; void *
0x1401b7500  add     ax, 2
0x1401b7504  movzx   ebx, ax
0x1401b7507  mov     r8d, ebx; Size
0x1401b750a  call    memset
0x1401b750f  xor     eax, eax
0x1401b7511  mov     [r15+2], bx
0x1401b7516  mov     rdx, r12; SourceString
0x1401b7519  mov     [r15], ax
0x1401b751d  mov     rcx, r15; DestinationString
0x1401b7520  mov     [r15+8], rdi
0x1401b7524  call    cs:__imp_RtlCopyUnicodeString
0x1401b752b  nop     dword ptr [rax+rax+00h]
0x1401b7530  xor     ebx, ebx
0x1401b7532  mov     [r14], r15
0x1401b7535  jmp     short loc_1401B74E9
0x1401b7537  mov     ecx, 1
0x1401b753c  cmp     di, cx
0x1401b753f  jnz     short loc_1401B7567
0x1401b7541  test    r14, r14
0x1401b7544  jz      loc_1401B76C3
0x1401b754a  cmp     word ptr [rax+10h], 4
0x1401b754f  jnz     loc_1401B76C3
0x1401b7555  mov     rdx, r14
0x1401b7558  mov     rcx, r12
0x1401b755b  call    CreateFqbnString
0x1401b7560  mov     esi, eax
0x1401b7562  jmp     loc_1401B76C8
0x1401b7567  cmp     di, 3
0x1401b756b  jz      loc_1401B76C3
0x1401b7571  cmp     di, 4
0x1401b7575  jz      loc_1401B76C3
0x1401b757b  mov     r13d, 2
0x1401b7581  cmp     di, r13w
0x1401b7585  jnz     loc_1401B76C8
0x1401b758b  cmp     word ptr [rax+10h], 10h
0x1401b7590  jnz     loc_1401B76C3
0x1401b7596  test    r14, r14
0x1401b7599  jz      loc_1401B76C3
0x1401b759f  mov     eax, [r12+8]
0x1401b75a4  mov     edx, 0FFFFh
0x1401b75a9  cmp     eax, edx
0x1401b75ab  ja      loc_1401B76BC
0x1401b75b1  movzx   ecx, ax
0x1401b75b4  shl     ecx, 2; usAugend
0x1401b75b7  cmp     ecx, edx
0x1401b75b9  ja      loc_1401B76BC
0x1401b75bf  mov     edx, r13d; usAddend
0x1401b75c2  mov     word ptr [rbp+pusResult], cx
0x1401b75c6  lea     r8, [rbp+pusResult]; pusResult
0x1401b75ca  call    RtlUShortAdd
0x1401b75cf  mov     esi, eax
0x1401b75d1  test    eax, eax
0x1401b75d3  js      loc_1401B76C8
0x1401b75d9  movzx   ecx, word ptr [rbp+pusResult]
0x1401b75dd  lea     rdx, [rbp+ppszDestEnd]
0x1401b75e1  call    CalcStringContiguousBufferSizeFromLength
0x1401b75e6  mov     esi, eax
0x1401b75e8  test    eax, eax
0x1401b75ea  js      loc_1401B76C8
0x1401b75f0  mov     edx, dword ptr [rbp+ppszDestEnd]
0x1401b75f3  lea     ecx, [r13+40h]
0x1401b75f7  mov     r8d, 41706445h
0x1401b75fd  call    cs:__imp_ExAllocatePool2
0x1401b7604  nop     dword ptr [rax+rax+00h]
0x1401b7609  mov     rbx, rax
0x1401b760c  test    rax, rax
0x1401b760f  jnz     short loc_1401B761B
0x1401b7611  mov     esi, 0C0000017h
0x1401b7616  jmp     loc_1401B76C8
0x1401b761b  movzx   ecx, word ptr [rbp+pusResult]
0x1401b761f  lea     rdi, [rax+10h]
0x1401b7623  mov     [rax+8], rdi
0x1401b7627  mov     r8d, ecx; Size
0x1401b762a  movzx   eax, cx
0x1401b762d  mov     [rbx+2], cx
0x1401b7631  sub     ax, r13w
0x1401b7635  mov     [rbp+ppszDestEnd], rdi
0x1401b7639  mov     r13d, ecx
0x1401b763c  mov     [rbx], ax
0x1401b763f  mov     rcx, rdi; void *
0x1401b7642  xor     edx, edx; Val
0x1401b7644  call    memset
0x1401b7649  cmp     dword ptr [r12+8], 0
0x1401b764f  mov     [rbp+pcbRemaining], r13
0x1401b7653  mov     [rbp+pusResult], 0
0x1401b765a  jbe     short loc_1401B76B5
0x1401b765c  mov     r15d, [rbp+pusResult]
0x1401b7660  mov     rax, [r12]
0x1401b7664  lea     r9, [rbp+pcbRemaining]; pcbRemaining
0x1401b7668  mov     r8d, r15d
0x1401b766b  mov     rdx, r13; cbDest
0x1401b766e  mov     rcx, rdi; pszDest
0x1401b7671  movzx   r8d, byte ptr [r8+rax]
0x1401b7676  lea     rax, a02x; "%02x"
0x1401b767d  mov     [rsp+60h+var_30], r8d
0x1401b7682  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x1401b7686  mov     [rsp+60h+pszFormat], rax; pszFormat
0x1401b768b  mov     qword ptr [rsp+60h+dwFlags], 0; dwFlags
0x1401b7694  call    RtlStringCbPrintfExW
0x1401b7699  inc     r15d
0x1401b769c  cmp     r15d, [r12+8]
0x1401b76a1  jnb     short loc_1401B76AD
0x1401b76a3  mov     rdi, [rbp+ppszDestEnd]
0x1401b76a7  mov     r13, [rbp+pcbRemaining]
0x1401b76ab  jmp     short loc_1401B7660
0x1401b76ad  mov     r14, [rbp+arg_18]
0x1401b76b1  mov     r15, [rbp+var_18]
0x1401b76b5  mov     [r14], rbx
0x1401b76b8  xor     ebx, ebx
0x1401b76ba  jmp     short loc_1401B76C8
0x1401b76bc  mov     esi, 0C0000095h
0x1401b76c1  jmp     short loc_1401B76C8
0x1401b76c3  mov     esi, 0C000000Dh
0x1401b76c8  xor     edx, edx; Tag
0x1401b76ca  mov     rcx, r15; P
0x1401b76cd  call    cs:__imp_ExFreePoolWithTag
0x1401b76d4  nop     dword ptr [rax+rax+00h]
0x1401b76d9  test    rbx, rbx
0x1401b76dc  jz      short loc_1401B76F6
0x1401b76de  xor     edx, edx; Tag
0x1401b76e0  mov     rcx, rbx; P
0x1401b76e3  call    cs:__imp_ExFreePoolWithTag
0x1401b76ea  nop     dword ptr [rax+rax+00h]
0x1401b76ef  jmp     short loc_1401B76F6
0x1401b76f1  mov     esi, 0C0000017h
0x1401b76f6  mov     eax, esi
0x1401b76f8  jmp     short loc_1401B76FF
0x1401b76fa  mov     eax, 0C000000Dh
0x1401b76ff  mov     rbx, [rsp+60h+arg_0]
0x1401b7707  add     rsp, 60h
0x1401b770b  pop     r15
0x1401b770d  pop     r14
0x1401b770f  pop     r13
0x1401b7711  pop     r12
0x1401b7713  pop     rdi
0x1401b7714  pop     rsi
0x1401b7715  pop     rbp
0x1401b7716  retn
```

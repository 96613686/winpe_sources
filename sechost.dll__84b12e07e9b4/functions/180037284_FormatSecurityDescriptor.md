# FormatSecurityDescriptor

- ea: `0x180037284`
- end: `0x18003743b`
- name: `FormatSecurityDescriptor`
- size: `439`
- prototype: `__int64 __usercall@<rax>(__int64@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800237d8`
- `0x1800238ec`

## callees

- `0x180012290`
- `0x1800125c8`
- `0x180016edc`
- `0x1800195b8`
- `0x180019ab8`
- `0x180037284`
- `0x180037444`
- `0x1800376c0`
- `0x18004f91a`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!wcsstr` at `0x1800372ff`
- `api-ms-win-core-crt-l1-1-0!wcsstr` at `0x18003738e`
- `api-ms-win-core-crt-l1-1-0!wcsstr` at `0x1800372ff`
- `api-ms-win-core-crt-l1-1-0!wcsstr` at `0x18003738e`

## pseudocode

```c
__int64 __fastcall FormatSecurityDescriptor(const wchar_t *a1, __int64 a2, const wchar_t *a3, __int64 a4, wchar_t **a5)
{
  unsigned __int64 v6; // r12
  wchar_t *v7; // rdi
  __int64 v8; // rdx
  int v9; // ebx
  __int64 v10; // r11
  __int64 v11; // r13
  const wchar_t *v12; // rcx
  unsigned __int64 i; // rsi
  wchar_t *v14; // rax
  __int64 v15; // r14
  size_t v16; // rbx
  wchar_t *v17; // rax
  wchar_t *v18; // r14
  wchar_t *v19; // r13
  wchar_t v21; // [rsp+40h] [rbp-20h]
  size_t v22; // [rsp+48h] [rbp-18h] BYREF
  __int64 v23; // [rsp+50h] [rbp-10h] BYREF
  wchar_t *v24; // [rsp+58h] [rbp-8h] BYREF
  char Args; // [rsp+B8h] [rbp+58h]

  Args = a4;
  v6 = 0;
  v24 = 0;
  v7 = 0;
  v9 = RtlStringCbLengthW(a4, 4294967294LL, &v24);
  if ( v9 >= 0 )
  {
    v23 = 0;
    v9 = RtlStringCchLengthW(v10, v8, &v23);
    if ( v9 >= 0 )
    {
      v11 = v23;
      v12 = a1;
      for ( i = 0; ; ++i )
      {
        v14 = wcsstr(v12, a3);
        if ( !v14 )
          break;
        v12 = &v14[v11];
      }
      v22 = 0;
      v9 = RtlULongLongMult(v24, i, &v22);
      if ( v9 >= 0 )
      {
        v15 = a2 - v11 * i;
        v16 = v22 + 2 * v15;
        if ( v16 < v22 )
        {
          v9 = -1073741675;
        }
        else
        {
          v22 += 2 * v15;
          v17 = (wchar_t *)AccessHlprAlloc(v22);
          v7 = v17;
          if ( v17 )
          {
            memset_0(v17, 0, v16);
            v18 = v7;
            v24 = v7;
            while ( v6 < i )
            {
              v19 = &wcsstr(a1, a3)[v11];
              v21 = *v19;
              *v19 = 0;
              v9 = RtlStringCbPrintfExW(v18, 0, (__int64)a1, Args);
              if ( v9 < 0 )
                goto LABEL_17;
              a1 = v19;
              v16 = v22;
              ++v6;
              v18 = v24;
              *v19 = v21;
              v11 = v23;
            }
            v9 = RtlStringCbCatW(v18, v16, a1);
            if ( v9 >= 0 )
            {
              *a5 = v7;
              v7 = 0;
            }
          }
          else
          {
            v9 = -1073741801;
          }
        }
      }
    }
  }
LABEL_17:
  FreeTransientObjectSecurityDescriptor(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180037284  mov     rax, rsp
0x180037287  mov     [rax+8], rbx
0x18003728b  mov     [rax+20h], r9
0x18003728f  mov     [rax+18h], r8
0x180037293  mov     [rax+10h], rdx
0x180037297  push    rbp
0x180037298  push    rsi
0x180037299  push    rdi
0x18003729a  push    r12
0x18003729c  push    r13
0x18003729e  push    r14
0x1800372a0  push    r15
0x1800372a2  mov     rbp, rsp
0x1800372a5  sub     rsp, 60h
0x1800372a9  mov     r15, rcx
0x1800372ac  xor     r12d, r12d
0x1800372af  mov     r11, r8
0x1800372b2  mov     [rbp+var_8], r12
0x1800372b6  lea     r8, [rbp+var_8]
0x1800372ba  mov     rcx, r9
0x1800372bd  mov     edx, 0FFFFFFFEh
0x1800372c2  mov     edi, r12d
0x1800372c5  call    RtlStringCbLengthW
0x1800372ca  mov     ebx, eax
0x1800372cc  test    eax, eax
0x1800372ce  js      loc_180037419
0x1800372d4  lea     r8, [rbp+var_10]
0x1800372d8  mov     [rbp+var_10], r12
0x1800372dc  mov     rcx, r11
0x1800372df  call    RtlStringCchLengthW
0x1800372e4  mov     ebx, eax
0x1800372e6  test    eax, eax
0x1800372e8  js      loc_180037419
0x1800372ee  mov     r13, [rbp+var_10]
0x1800372f2  mov     rcx, r15; Str
0x1800372f5  mov     r14, [rbp+SubStr]
0x1800372f9  mov     esi, r12d
0x1800372fc  mov     rdx, r14; SubStr
0x1800372ff  call    cs:__imp_wcsstr
0x180037305  test    rax, rax
0x180037308  jz      short loc_180037313
0x18003730a  lea     rcx, [rax+r13*2]
0x18003730e  inc     rsi
0x180037311  jmp     short loc_1800372FC
0x180037313  mov     rcx, [rbp+var_8]
0x180037317  lea     r8, [rbp+var_18]
0x18003731b  mov     rdx, rsi
0x18003731e  mov     [rbp+var_18], r12
0x180037322  call    RtlULongLongMult
0x180037327  mov     r14, [rbp+arg_8]
0x18003732b  mov     ebx, eax
0x18003732d  test    eax, eax
0x18003732f  js      loc_180037419
0x180037335  mov     rcx, [rbp+var_18]
0x180037339  mov     rax, rsi
0x18003733c  imul    rax, r13
0x180037340  sub     r14, rax
0x180037343  lea     rbx, [rcx+r14*2]
0x180037347  cmp     rbx, rcx
0x18003734a  jb      loc_180037414
0x180037350  mov     rcx, rbx
0x180037353  mov     [rbp+var_18], rbx
0x180037357  call    AccessHlprAlloc
0x18003735c  mov     rdi, rax
0x18003735f  test    rax, rax
0x180037362  jnz     short loc_18003736E
0x180037364  mov     ebx, 0C0000017h
0x180037369  jmp     loc_180037419
0x18003736e  mov     r8, rbx; Size
0x180037371  xor     edx, edx; Val
0x180037373  mov     rcx, rdi; void *
0x180037376  call    memset_0
0x18003737b  mov     r14, rdi
0x18003737e  mov     [rbp+var_8], rdi
0x180037382  cmp     r12, rsi
0x180037385  jnb     short loc_1800373F5
0x180037387  mov     rdx, [rbp+SubStr]; SubStr
0x18003738b  mov     rcx, r15; Str
0x18003738e  call    cs:__imp_wcsstr
0x180037394  lea     r9, [rbp+var_18]
0x180037398  mov     rdx, rbx
0x18003739b  lea     r8, [rbp+var_8]
0x18003739f  mov     rcx, r14; Buffer
0x1800373a2  lea     r13, [rax+r13*2]
0x1800373a6  movzx   eax, word ptr [r13+0]
0x1800373ab  mov     [rbp+var_20], ax
0x1800373af  xor     eax, eax
0x1800373b1  mov     [r13+0], ax
0x1800373b6  mov     rax, qword ptr [rbp+arg_18]
0x1800373ba  mov     qword ptr [rsp+60h+Args], rax; Args
0x1800373bf  mov     [rsp+60h+var_38], r15; __int64
0x1800373c4  mov     qword ptr [rsp+60h+var_40], 0; int
0x1800373cd  call    RtlStringCbPrintfExW
0x1800373d2  mov     ebx, eax
0x1800373d4  test    eax, eax
0x1800373d6  js      short loc_180037419
0x1800373d8  movzx   eax, [rbp+var_20]
0x1800373dc  mov     r15, r13
0x1800373df  mov     rbx, [rbp+var_18]
0x1800373e3  inc     r12
0x1800373e6  mov     r14, [rbp+var_8]
0x1800373ea  mov     [r13+0], ax
0x1800373ef  mov     r13, [rbp+var_10]
0x1800373f3  jmp     short loc_180037382
0x1800373f5  mov     r8, r15
0x1800373f8  mov     rdx, rbx
0x1800373fb  mov     rcx, r14
0x1800373fe  call    RtlStringCbCatW
0x180037403  mov     ebx, eax
0x180037405  test    eax, eax
0x180037407  js      short loc_180037419
0x180037409  mov     rax, [rbp+arg_20]
0x18003740d  mov     [rax], rdi
0x180037410  xor     edi, edi
0x180037412  jmp     short loc_180037419
0x180037414  mov     ebx, 0C0000095h
0x180037419  mov     rcx, rdi
0x18003741c  call    FreeTransientObjectSecurityDescriptor
0x180037421  mov     eax, ebx
0x180037423  mov     rbx, [rsp+60h+arg_0]
0x18003742b  add     rsp, 60h
0x18003742f  pop     r15
0x180037431  pop     r14
0x180037433  pop     r13
0x180037435  pop     r12
0x180037437  pop     rdi
0x180037438  pop     rsi
0x180037439  pop     rbp
0x18003743a  retn
```

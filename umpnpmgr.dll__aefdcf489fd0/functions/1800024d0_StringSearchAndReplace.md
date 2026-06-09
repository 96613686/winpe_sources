# StringSearchAndReplace

- ea: `0x1800024d0`
- end: `0x18000273c`
- name: `StringSearchAndReplace`
- size: `620`
- prototype: `void *__fastcall(const wchar_t *Src)`
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180001190`
- `0x1800027a0`
- `0x180004180`
- `0x1800056d0`
- `0x180014a84`
- `0x1800156c0`

## callees

- `0x1800010e0`
- `0x1800024d0`
- `0x180013370`
- `0x180013df8`
- `0x180013e20`
- `0x180018926`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800025b2`
- `msvcrt!wcsstr` at `0x1800025cb`
- `msvcrt!wcsstr` at `0x18000266a`
- `msvcrt!wcsstr` at `0x1800026c1`
- `msvcrt!wcsstr` at `0x1800025b2`
- `msvcrt!wcsstr` at `0x1800025cb`
- `msvcrt!wcsstr` at `0x18000266a`
- `msvcrt!wcsstr` at `0x1800026c1`
- `ntdll!RtlFreeHeap` at `0x180002723`
- `ntdll!RtlFreeHeap` at `0x180002723`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002558`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002558`

## pseudocode

```c
void *__fastcall StringSearchAndReplace(const wchar_t *Src)
{
  const wchar_t *v1; // rbp
  void *v2; // r12
  const wchar_t *v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rsi
  __int64 v6; // rcx
  const wchar_t *v7; // rax
  DWORD v8; // r14d
  __int64 v10; // rdi
  __int64 v11; // rcx
  const wchar_t *v12; // rax
  unsigned int v13; // r15d
  size_t v14; // rbx
  wchar_t *v15; // rax
  unsigned int v16; // r10d
  __int64 v17; // r13
  __int64 v18; // rax
  char *v19; // rsi
  wchar_t *i; // r15
  unsigned __int64 v21; // [rsp+60h] [rbp+8h] BYREF
  signed __int64 v22; // [rsp+68h] [rbp+10h] BYREF
  __int64 v23; // [rsp+70h] [rbp+18h] BYREF

  v1 = Src;
  v21 = 0;
  v2 = 0;
  v22 = 0;
  v23 = 0;
  if ( !Src )
    goto LABEL_11;
  v3 = Src;
  v4 = 0x7FFF;
  while ( *v3 )
  {
    ++v3;
    if ( !--v4 )
    {
      v5 = 0;
      goto LABEL_7;
    }
  }
  v5 = 2 * (0x7FFF - v4);
LABEL_7:
  if ( !v4 )
    goto LABEL_11;
  v6 = 0x7FFF;
  v7 = L"\"";
  while ( *v7 )
  {
    ++v7;
    if ( !--v6 )
      goto LABEL_11;
  }
  v10 = 0x7FFF - v6;
  if ( v10 * 2 )
  {
    v11 = 0x7FFF;
    v12 = L"\\\"";
    while ( *v12 )
    {
      ++v12;
      if ( !--v11 )
        goto LABEL_11;
    }
    v8 = 0;
    v13 = 0;
    v14 = 2 * (0x7FFF - v11);
    v15 = wcsstr(v1, L"\"");
    if ( v15 )
    {
      do
      {
        ++v13;
        v15 = wcsstr(&v15[v10], L"\"");
      }
      while ( v15 );
      if ( v13 )
      {
        if ( (int)RtlULongLongMult(v13, v10 * 2, &v23) < 0
          || (int)RtlSizeTSub(v5 + 2, v23, &v21) < 0
          || (int)RtlULongLongMult(v16, v14, &v23) < 0
          || (v17 = v21 + v23, v21 + v23 < v21) )
        {
          v8 = 534;
        }
        else
        {
          v18 = PnpHeapAlloc(v21 + v23);
          v2 = (void *)v18;
          if ( v18 )
          {
            v19 = (char *)v18;
            for ( i = wcsstr(v1, L"\""); i; i = wcsstr(&i[v10], L"\"") )
            {
              v22 = (char *)i - (char *)v1;
              if ( i != v1 )
              {
                memcpy_0(v19, v1, (char *)i - (char *)v1);
                v19 += (char *)i - (char *)v1;
              }
              if ( v14 )
              {
                memcpy_0(v19, L"\\\"", v14);
                v19 += v14;
              }
              v1 = &i[v10];
            }
            if ( (int)RtlSizeTSub(v19, v2, &v23) < 0
              || (int)RtlSizeTSub(v17, v23, &v22) < 0
              || (int)RtlStringCbCopyW(v19, v22, v1) < 0 )
            {
              v8 = 13;
              RtlFreeHeap(PnpHeapHandle, 0, v2);
              v2 = 0;
            }
          }
          else
          {
            v8 = 8;
          }
        }
      }
    }
  }
  else
  {
LABEL_11:
    v8 = 13;
  }
  SetLastError(v8);
  return v2;
}

```

## disassembly

```asm
0x1800024d0  mov     [rsp+arg_18], rbx
0x1800024d5  mov     [rsp+arg_10], r8
0x1800024da  mov     [rsp+arg_8], rdx
0x1800024df  push    rbp
0x1800024e0  push    rsi
0x1800024e1  push    rdi
0x1800024e2  push    r12
0x1800024e4  push    r13
0x1800024e6  push    r14
0x1800024e8  push    r15
0x1800024ea  sub     rsp, 20h
0x1800024ee  xor     edx, edx
0x1800024f0  mov     rbp, rcx
0x1800024f3  mov     [rsp+58h+arg_0], rdx
0x1800024f8  mov     r12d, edx
0x1800024fb  mov     [rsp+58h+arg_8], rdx
0x180002500  mov     [rsp+58h+arg_10], rdx
0x180002505  test    rcx, rcx
0x180002508  jz      short loc_18000254F
0x18000250a  mov     ebx, 7FFFh
0x18000250f  mov     rax, rbp
0x180002512  mov     ecx, ebx
0x180002514  cmp     [rax], dx
0x180002517  jz      short loc_180002528
0x180002519  add     rax, 2
0x18000251d  sub     rcx, 1
0x180002521  jnz     short loc_180002514
0x180002523  mov     rsi, rdx
0x180002526  jmp     short loc_180002531
0x180002528  mov     rsi, rbx
0x18000252b  sub     rsi, rcx
0x18000252e  add     rsi, rsi
0x180002531  test    rcx, rcx
0x180002534  jz      short loc_18000254F
0x180002536  mov     rcx, rbx
0x180002539  lea     rax, SubStr; "\""
0x180002540  cmp     [rax], dx
0x180002543  jz      short loc_180002576
0x180002545  add     rax, 2
0x180002549  sub     rcx, 1
0x18000254d  jnz     short loc_180002540
0x18000254f  mov     r14d, 0Dh
0x180002555  mov     ecx, r14d; dwErrCode
0x180002558  call    cs:__imp_SetLastError
0x18000255e  mov     rbx, [rsp+58h+arg_18]
0x180002563  mov     rax, r12
0x180002566  add     rsp, 20h
0x18000256a  pop     r15
0x18000256c  pop     r14
0x18000256e  pop     r13
0x180002570  pop     r12
0x180002572  pop     rdi
0x180002573  pop     rsi
0x180002574  pop     rbp
0x180002575  retn
0x180002576  mov     rdi, rbx
0x180002579  sub     rdi, rcx
0x18000257c  add     rdi, rdi
0x18000257f  jz      short loc_18000254F
0x180002581  mov     rcx, rbx
0x180002584  lea     rax, asc_18001C488; "\\\""
0x18000258b  cmp     [rax], dx
0x18000258e  jz      short loc_18000259C
0x180002590  add     rax, 2
0x180002594  sub     rcx, 1
0x180002598  jnz     short loc_18000258B
0x18000259a  jmp     short loc_18000254F
0x18000259c  sub     rbx, rcx
0x18000259f  mov     r14d, edx
0x1800025a2  mov     r15d, edx
0x1800025a5  mov     rcx, rbp; Str
0x1800025a8  lea     rdx, SubStr; "\""
0x1800025af  add     rbx, rbx
0x1800025b2  call    cs:__imp_wcsstr
0x1800025b8  test    rax, rax
0x1800025bb  jz      short loc_180002555
0x1800025bd  lea     rcx, [rdi+rax]; Str
0x1800025c1  inc     r15d
0x1800025c4  lea     rdx, SubStr; "\""
0x1800025cb  call    cs:__imp_wcsstr
0x1800025d1  test    rax, rax
0x1800025d4  jnz     short loc_1800025BD
0x1800025d6  test    r15d, r15d
0x1800025d9  jz      loc_180002555
0x1800025df  lea     r8, [rsp+58h+arg_10]
0x1800025e4  mov     ecx, r15d
0x1800025e7  mov     rdx, rdi
0x1800025ea  mov     r10d, r15d
0x1800025ed  call    RtlULongLongMult
0x1800025f2  test    eax, eax
0x1800025f4  js      loc_180002731
0x1800025fa  mov     rdx, [rsp+58h+arg_10]
0x1800025ff  lea     rcx, [rsi+2]
0x180002603  lea     r8, [rsp+58h+arg_0]
0x180002608  call    RtlSizeTSub
0x18000260d  test    eax, eax
0x18000260f  js      loc_180002731
0x180002615  lea     r8, [rsp+58h+arg_10]
0x18000261a  mov     rdx, rbx
0x18000261d  mov     ecx, r10d
0x180002620  call    RtlULongLongMult
0x180002625  test    eax, eax
0x180002627  js      loc_180002731
0x18000262d  mov     r13, [rsp+58h+arg_10]
0x180002632  add     r13, [rsp+58h+arg_0]
0x180002637  cmp     r13, [rsp+58h+arg_0]
0x18000263c  jb      loc_180002731
0x180002642  mov     rcx, r13
0x180002645  call    PnpHeapAlloc
0x18000264a  mov     r12, rax
0x18000264d  test    rax, rax
0x180002650  jnz     short loc_18000265D
0x180002652  mov     r14d, 8
0x180002658  jmp     loc_180002555
0x18000265d  lea     rdx, SubStr; "\""
0x180002664  mov     rcx, rbp; Str
0x180002667  mov     rsi, r12
0x18000266a  call    cs:__imp_wcsstr
0x180002670  mov     r15, rax
0x180002673  test    rax, rax
0x180002676  jz      short loc_1800026CF
0x180002678  mov     r8, r15
0x18000267b  sub     r8, rbp; Size
0x18000267e  mov     [rsp+58h+arg_8], r8
0x180002683  jz      short loc_180002699
0x180002685  mov     rdx, rbp; Src
0x180002688  mov     rcx, rsi; void *
0x18000268b  call    memcpy_0
0x180002690  mov     rax, r15
0x180002693  sub     rax, rbp
0x180002696  add     rsi, rax
0x180002699  test    rbx, rbx
0x18000269c  jz      short loc_1800026B3
0x18000269e  mov     r8, rbx; Size
0x1800026a1  lea     rdx, asc_18001C488; "\\\""
0x1800026a8  mov     rcx, rsi; void *
0x1800026ab  call    memcpy_0
0x1800026b0  add     rsi, rbx
0x1800026b3  lea     rbp, [rdi+r15]
0x1800026b7  mov     rcx, rbp; Str
0x1800026ba  lea     rdx, SubStr; "\""
0x1800026c1  call    cs:__imp_wcsstr
0x1800026c7  mov     r15, rax
0x1800026ca  test    rax, rax
0x1800026cd  jnz     short loc_180002678
0x1800026cf  lea     r8, [rsp+58h+arg_10]
0x1800026d4  mov     rdx, r12
0x1800026d7  mov     rcx, rsi
0x1800026da  call    RtlSizeTSub
0x1800026df  test    eax, eax
0x1800026e1  js      short loc_180002711
0x1800026e3  mov     rdx, [rsp+58h+arg_10]
0x1800026e8  lea     r8, [rsp+58h+arg_8]
0x1800026ed  mov     rcx, r13
0x1800026f0  call    RtlSizeTSub
0x1800026f5  test    eax, eax
0x1800026f7  js      short loc_180002711
0x1800026f9  mov     rdx, [rsp+58h+arg_8]
0x1800026fe  mov     r8, rbp
0x180002701  mov     rcx, rsi
0x180002704  call    RtlStringCbCopyW
0x180002709  test    eax, eax
0x18000270b  jns     loc_180002555
0x180002711  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x180002718  mov     r8, r12; P
0x18000271b  xor     edx, edx; Flags
0x18000271d  mov     r14d, 0Dh
0x180002723  call    cs:__imp_RtlFreeHeap
0x180002729  xor     r12d, r12d
0x18000272c  jmp     loc_180002555
0x180002731  mov     r14d, 216h
0x180002737  jmp     loc_180002555
```

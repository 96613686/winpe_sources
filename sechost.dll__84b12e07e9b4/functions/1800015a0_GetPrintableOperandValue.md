# GetPrintableOperandValue

- ea: `0x1800015a0`
- end: `0x180001b92`
- name: `GetPrintableOperandValue`
- size: `1522`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1800015a0`
- `0x180001ef0`

## callees

- `0x1800015a0`
- `0x180001e58`
- `0x180002fa0`
- `0x180017be0`
- `0x180021d84`
- `0x180023174`
- `0x18004f902`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001709`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000178a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000195e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001a17`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001a83`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001709`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000178a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000195e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001a17`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001a83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800018aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001b63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800018aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001b63`

## string_xrefs

- `0x180001720`: `SID(%ls)`

## pseudocode

```c
__int64 __fastcall GetPrintableOperandValue(
        unsigned __int8 *a1,
        int a2,
        __int64 a3,
        int *a4,
        _BYTE *a5,
        _BYTE *a6,
        __int64 a7,
        char a8)
{
  unsigned int StringForSid; // edi
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  unsigned int v20; // r12d
  __int64 v21; // rax
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rbx
  HLOCAL v24; // rax
  unsigned int v25; // r12d
  __int64 v26; // r13
  _WORD *v27; // rax
  unsigned int v28; // r8d
  int v29; // r9d
  unsigned __int8 *v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rax
  unsigned __int64 v33; // rdx
  unsigned int v34; // r12d
  unsigned __int64 v35; // rax
  unsigned __int64 v36; // rax
  unsigned __int64 v37; // rbx
  _WORD *v38; // rax
  __int64 v39; // r11
  int v40; // r9d
  unsigned int v41; // r10d
  unsigned int v42; // r13d
  _WORD *v43; // rax
  unsigned __int64 v44; // rbx
  __int64 v45; // r13
  unsigned __int8 v46; // r12
  unsigned __int8 v47; // bl
  _WORD *v48; // rax
  _WORD *v49; // r11
  __int64 v50; // r11
  __int64 v51; // r11
  __int64 v52; // r11
  __int64 v53; // r9
  HLOCAL hMem; // [rsp+40h] [rbp-B1h] BYREF
  unsigned int v56; // [rsp+48h] [rbp-A9h] BYREF
  unsigned int v57; // [rsp+4Ch] [rbp-A5h]
  int v58; // [rsp+50h] [rbp-A1h]
  int v59; // [rsp+54h] [rbp-9Dh]
  __int64 v60; // [rsp+58h] [rbp-99h]
  _BYTE *v61; // [rsp+60h] [rbp-91h]
  __int64 v62; // [rsp+68h] [rbp-89h]
  _BYTE *v63; // [rsp+70h] [rbp-81h]
  _BYTE v64[24]; // [rsp+78h] [rbp-79h] BYREF
  _BYTE Sid[80]; // [rsp+90h] [rbp-61h] BYREF

  v61 = a6;
  v60 = a7;
  v63 = a5;
  hMem = 0;
  v56 = 0;
  if ( a1 && a3 && a2 )
  {
    *a4 = 1;
    StringForSid = 0;
    v13 = *a1 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( v16 )
          {
            v17 = v16 - 12;
            if ( v17 )
            {
              v18 = v17 - 8;
              if ( v18 )
              {
                v19 = v18 - 56;
                if ( v19 )
                {
                  if ( v19 == 1 && (unsigned int)(a2 - 1) >= 4 )
                  {
                    v20 = *(_DWORD *)(a1 + 1);
                    *a4 = 5;
                    if ( v20 <= 0x44 && a2 - 5 >= v20 )
                    {
                      memcpy_0(Sid, a1 + 5, v20);
                      StringForSid = LocalGetStringForSid(Sid, (wchar_t **)&hMem, a5, v61, v60, a8);
                      if ( StringForSid )
                        goto LABEL_78;
                      *a4 += v20;
                      v21 = -1;
                      do
                        ++v21;
                      while ( *((_WORD *)hMem + v21) );
                      if ( (int)v21 + 6 < (unsigned int)v21 || (v22 = 2LL * (unsigned int)(v21 + 6), v22 > 0xFFFFFFFF) )
                      {
LABEL_24:
                        StringForSid = 534;
                        goto LABEL_78;
                      }
                      v23 = (unsigned int)v22;
                      v24 = LocalAlloc(0x40u, (unsigned int)v22);
                      *(_QWORD *)a3 = v24;
                      if ( v24 )
                      {
                        if ( (int)RtlStringCchPrintfW(v24, v23 >> 1, L"SID(%ls)", hMem) >= 0 )
                        {
LABEL_78:
                          if ( hMem )
                            LocalFree(hMem);
                          return StringForSid;
                        }
                        goto LABEL_66;
                      }
LABEL_58:
                      StringForSid = 8;
                      goto LABEL_78;
                    }
                  }
                }
                else if ( (unsigned int)(a2 - 1) >= 4 )
                {
                  v25 = *(_DWORD *)(a1 + 1);
                  *a4 = 5;
                  if ( v25 )
                  {
                    if ( a2 - 5 >= v25 )
                    {
                      LODWORD(v26) = 6;
                      v62 = 6;
                      v27 = LocalAlloc(0x40u, 6u);
                      *(_QWORD *)a3 = v27;
                      if ( v27 )
                      {
                        v28 = 0;
                        *v27 = 123;
                        v29 = *a4;
                        v59 = *a4;
                        v57 = 0;
                        while ( v25 > v28 )
                        {
                          v30 = &a1[v28 + v29];
                          if ( *v30 == 80 )
                          {
                            StringForSid = 1336;
                            goto LABEL_78;
                          }
                          StringForSid = GetPrintableOperandValue(
                                           (_DWORD)v30,
                                           a2 - v28 - v29,
                                           (unsigned int)&hMem,
                                           (_DWORD)a4,
                                           (__int64)v63,
                                           (__int64)v61,
                                           v60,
                                           a8);
                          if ( StringForSid )
                            goto LABEL_78;
                          if ( (int)ULongAddStringSize((unsigned int)v26, hMem, &v56) < 0 )
                            goto LABEL_24;
                          v26 = v56 + 4;
                          if ( (unsigned int)v26 < v56 )
                            goto LABEL_24;
                          v58 = *a4;
                          v56 += 4;
                          v32 = SddlpReAlloc(v31, (unsigned int)v26);
                          *(_QWORD *)a3 = v32;
                          if ( !v32 )
                            goto LABEL_58;
                          if ( (int)RtlStringCchPrintfW(
                                      v32 + 2 * (((unsigned __int64)(unsigned int)v62 >> 1) - 2),
                                      (unsigned __int64)(unsigned int)(v26 - v62 + 4) >> 1,
                                      L"%ls, ",
                                      hMem) < 0 )
                            goto LABEL_66;
                          v57 += v58;
                          LocalFree(hMem);
                          v28 = v57;
                          v29 = v59;
                          hMem = 0;
                          v62 = v26;
                        }
                        v33 = (unsigned __int64)(unsigned int)v26 >> 1;
                        *(_WORD *)(*(_QWORD *)a3 + 2 * v33 - 8) = 125;
                        *(_WORD *)(*(_QWORD *)a3 + 2 * v33 - 6) = 0;
                        *a4 = v29 + v25;
                        goto LABEL_78;
                      }
                      goto LABEL_58;
                    }
                  }
                }
                return 1336;
              }
              if ( (unsigned int)(a2 - 1) >= 4 )
              {
                v34 = *(_DWORD *)(a1 + 1);
                *a4 = 5;
                if ( a2 - 5 >= v34 )
                {
                  if ( v34 )
                  {
                    v35 = 2LL * v34;
                    if ( v35 <= 0xFFFFFFFF && (int)v35 + 2 >= (unsigned int)v35 )
                    {
                      v36 = 2LL * (unsigned int)(v35 + 2);
                      if ( v36 <= 0xFFFFFFFF )
                      {
                        v37 = (unsigned int)v36;
                        v38 = LocalAlloc(0x40u, (unsigned int)v36);
                        *(_QWORD *)a3 = v38;
                        if ( v38 )
                        {
                          *v38 = 35;
                          v39 = 0;
                          do
                          {
                            v40 = 2 * v39;
                            v41 = a1[(unsigned int)*a4 + v39];
                            v39 = (unsigned int)(v39 + 1);
                            *(_WORD *)(*(_QWORD *)a3 + 2LL * (unsigned int)(v40 + 1)) = a0123456789abcd[(unsigned __int64)v41 >> 4];
                            *(_WORD *)(*(_QWORD *)a3 + 2LL * (unsigned int)(v40 + 2)) = a0123456789abcd[v41 & 0xF];
                          }
                          while ( (unsigned int)v39 < v34 );
                          *(_WORD *)(*(_QWORD *)a3 + 2 * (v37 >> 1) - 2) = 0;
                          *a4 += v34;
                          goto LABEL_78;
                        }
                        goto LABEL_58;
                      }
                    }
                    return 534;
                  }
                }
              }
            }
            else if ( (unsigned int)(a2 - 1) >= 4 )
            {
              v42 = *(_DWORD *)(a1 + 1);
              *a4 = 5;
              if ( a2 - 5 >= v42 )
              {
                if ( v42 + 6 >= v42 )
                {
                  v43 = LocalAlloc(0x40u, v42 + 6);
                  *(_QWORD *)a3 = v43;
                  if ( v43 )
                  {
                    *v43 = 34;
                    memcpy_0((void *)(*(_QWORD *)a3 + 2LL), &a1[*a4], v42);
                    v44 = (unsigned __int64)v42 >> 1;
                    *(_WORD *)(*(_QWORD *)a3 + 2 * v44 + 2) = 34;
                    *(_WORD *)(*(_QWORD *)a3 + 2 * v44 + 4) = 0;
                    *a4 += v42;
                    goto LABEL_78;
                  }
                  goto LABEL_58;
                }
                return 534;
              }
            }
            return 1336;
          }
        }
      }
    }
    if ( (unsigned int)(a2 - 1) < 0xA )
      return 1336;
    v45 = *(_QWORD *)(a1 + 1);
    v46 = a1[9];
    v47 = a1[10];
    v48 = LocalAlloc(0x40u, 0x40u);
    *(_QWORD *)a3 = v48;
    v49 = v48;
    if ( !v48 )
      goto LABEL_58;
    if ( v46 == 1 )
    {
      *v48 = 43;
    }
    else
    {
      if ( v46 != 2 )
      {
LABEL_64:
        if ( v47 == 1 )
        {
          *v49 = 48;
          if ( (int)RtlStringCchCopyW(v64, 8, L"%I64o") < 0 )
            goto LABEL_66;
          v51 = v50 + 2;
        }
        else if ( v47 == 3 )
        {
          *(_DWORD *)v49 = 7864368;
          if ( (int)RtlStringCchCopyW(v64, 8, L"%I64x") < 0 )
            goto LABEL_66;
          v51 = v52 + 4;
        }
        else if ( (int)RtlStringCchCopyW(v64, 8, L"%I64u") < 0 )
        {
          goto LABEL_66;
        }
        if ( !v45 && v47 == 1 )
          goto LABEL_77;
        v53 = -v45;
        if ( v46 != 2 )
          v53 = v45;
        if ( (int)RtlStringCchPrintfW(v51, 32 - ((v51 - *(_QWORD *)a3) >> 1), v64, v53) >= 0 )
        {
LABEL_77:
          *a4 += 10;
          goto LABEL_78;
        }
LABEL_66:
        StringForSid = 50;
        goto LABEL_78;
      }
      *v48 = 45;
    }
    v49 = v48 + 1;
    goto LABEL_64;
  }
  return 87;
}

```

## disassembly

```asm
0x1800015a0  push    rbp
0x1800015a2  push    rbx
0x1800015a3  push    rsi
0x1800015a4  push    rdi
0x1800015a5  push    r12
0x1800015a7  push    r13
0x1800015a9  push    r14
0x1800015ab  push    r15
0x1800015ad  lea     rbp, [rsp-7]
0x1800015b2  sub     rsp, 0F8h
0x1800015b9  mov     rax, cs:__security_cookie
0x1800015c0  xor     rax, rsp
0x1800015c3  mov     [rbp+3Fh+var_50], rax
0x1800015c7  mov     rax, [rbp+3Fh+arg_28]
0x1800015cb  mov     ebx, edx
0x1800015cd  mov     r13, [rbp+3Fh+arg_20]
0x1800015d1  xor     edx, edx
0x1800015d3  mov     [rsp+130h+var_D0], rax
0x1800015d8  mov     rsi, r9
0x1800015db  mov     rax, [rbp+3Fh+arg_30]
0x1800015df  mov     r14, r8
0x1800015e2  mov     [rsp+130h+var_D8], rax
0x1800015e7  mov     r15, rcx
0x1800015ea  mov     [rsp+130h+var_C0], r13
0x1800015ef  mov     [rsp+130h+hMem], rdx
0x1800015f4  mov     [rsp+130h+var_E8], edx
0x1800015f8  test    rcx, rcx
0x1800015fb  jz      loc_180001B6D
0x180001601  test    r8, r8
0x180001604  jz      loc_180001B6D
0x18000160a  test    ebx, ebx
0x18000160c  jz      loc_180001B6D
0x180001612  mov     dword ptr [r9], 1
0x180001619  mov     edi, edx
0x18000161b  movzx   ecx, byte ptr [rcx]
0x18000161e  sub     ecx, 1
0x180001621  jz      loc_180001A64
0x180001627  sub     ecx, 1
0x18000162a  jz      loc_180001A64
0x180001630  sub     ecx, 1
0x180001633  jz      loc_180001A64
0x180001639  sub     ecx, 1
0x18000163c  jz      loc_180001A64
0x180001642  sub     ecx, 0Ch
0x180001645  jz      loc_1800019E4
0x18000164b  sub     ecx, 8
0x18000164e  jz      loc_1800018FC
0x180001654  sub     ecx, 38h ; '8'
0x180001657  jz      loc_18000174C
0x18000165d  cmp     ecx, 1
0x180001660  jz      short loc_18000166C
0x180001662  mov     edi, 538h
0x180001667  jmp     loc_180001B69
0x18000166c  lea     eax, [rbx-1]
0x18000166f  cmp     eax, 4
0x180001672  jb      short loc_180001662
0x180001674  mov     r12d, [r15+1]
0x180001678  mov     dword ptr [r9], 5
0x18000167f  cmp     r12d, 44h ; 'D'
0x180001683  ja      short loc_180001662
0x180001685  lea     eax, [rbx-5]
0x180001688  cmp     eax, r12d
0x18000168b  jb      short loc_180001662
0x18000168d  mov     r8d, r12d; Size
0x180001690  lea     rdx, [r15+5]; Src
0x180001694  lea     rcx, [rbp+3Fh+Sid]; void *
0x180001698  call    memcpy_0
0x18000169d  mov     al, [rbp+3Fh+arg_38]
0x1800016a3  lea     rdx, [rsp+130h+hMem]
0x1800016a8  mov     r9, [rsp+130h+var_D0]
0x1800016ad  lea     rcx, [rbp+3Fh+Sid]; Sid
0x1800016b1  mov     [rsp+130h+var_108], al; char
0x1800016b5  mov     r8, r13
0x1800016b8  mov     rax, [rsp+130h+var_D8]
0x1800016bd  mov     [rsp+130h+var_110], rax; __int64
0x1800016c2  call    LocalGetStringForSid
0x1800016c7  xor     r15d, r15d
0x1800016ca  mov     edi, eax
0x1800016cc  test    eax, eax
0x1800016ce  jnz     loc_180001B59
0x1800016d4  add     [rsi], r12d
0x1800016d7  mov     rcx, [rsp+130h+hMem]
0x1800016dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800016e0  inc     rax
0x1800016e3  cmp     [rcx+rax*2], r15w
0x1800016e8  jnz     short loc_1800016E0
0x1800016ea  lea     ecx, [rax+6]
0x1800016ed  cmp     ecx, eax
0x1800016ef  jb      short loc_180001742
0x1800016f1  mov     eax, ecx
0x1800016f3  mov     ecx, 0FFFFFFFFh
0x1800016f8  add     rax, rax
0x1800016fb  cmp     rax, rcx
0x1800016fe  ja      short loc_180001742
0x180001700  mov     edx, eax; uBytes
0x180001702  mov     ecx, 40h ; '@'; uFlags
0x180001707  mov     ebx, eax
0x180001709  call    cs:__imp_LocalAlloc
0x18000170f  mov     [r14], rax
0x180001712  test    rax, rax
0x180001715  jz      loc_180001A94
0x18000171b  mov     r9, [rsp+130h+hMem]
0x180001720  lea     r8, aSidLs; "SID(%ls)"
0x180001727  shr     rbx, 1
0x18000172a  mov     rcx, rax
0x18000172d  mov     rdx, rbx
0x180001730  call    RtlStringCchPrintfW
0x180001735  test    eax, eax
0x180001737  js      loc_180001ADE
0x18000173d  jmp     loc_180001B59
0x180001742  mov     edi, 216h
0x180001747  jmp     loc_180001B59
0x18000174c  lea     eax, [rbx-1]
0x18000174f  cmp     eax, 4
0x180001752  jb      loc_180001662
0x180001758  mov     r12d, [r15+1]
0x18000175c  mov     dword ptr [r9], 5
0x180001763  test    r12d, r12d
0x180001766  jz      loc_180001662
0x18000176c  lea     eax, [rbx-5]
0x18000176f  cmp     eax, r12d
0x180001772  jb      loc_180001662
0x180001778  mov     r13d, 6
0x18000177e  mov     edx, r13d; uBytes
0x180001781  mov     [rsp+130h+var_C8], r13
0x180001786  lea     ecx, [r13+3Ah]; uFlags
0x18000178a  call    cs:__imp_LocalAlloc
0x180001790  mov     [r14], rax
0x180001793  test    rax, rax
0x180001796  jz      loc_180001A94
0x18000179c  lea     ecx, [r13+75h]
0x1800017a0  xor     r8d, r8d
0x1800017a3  mov     [rax], cx
0x1800017a6  mov     r9d, [rsi]
0x1800017a9  mov     [rsp+130h+var_DC], r9d
0x1800017ae  mov     [rsp+130h+var_E4], r8d
0x1800017b3  cmp     r12d, r8d
0x1800017b6  jbe     loc_1800018D7
0x1800017bc  mov     eax, r8d
0x1800017bf  add     rax, r15
0x1800017c2  mov     ecx, r9d
0x1800017c5  add     rcx, rax
0x1800017c8  cmp     byte ptr [rcx], 50h ; 'P'
0x1800017cb  jz      loc_1800018CD
0x1800017d1  mov     al, [rbp+3Fh+arg_38]
0x1800017d7  mov     edx, ebx
0x1800017d9  mov     [rsp+130h+var_F8], al
0x1800017dd  sub     edx, r8d
0x1800017e0  mov     rax, [rsp+130h+var_D8]
0x1800017e5  lea     r8, [rsp+130h+hMem]
0x1800017ea  mov     [rsp+130h+var_100], rax
0x1800017ef  sub     edx, r9d
0x1800017f2  mov     rax, [rsp+130h+var_D0]
0x1800017f7  mov     r9, rsi
0x1800017fa  mov     qword ptr [rsp+130h+var_108], rax
0x1800017ff  mov     rax, [rsp+130h+var_C0]
0x180001804  mov     [rsp+130h+var_110], rax
0x180001809  call    GetPrintableOperandValue
0x18000180e  mov     edi, eax
0x180001810  test    eax, eax
0x180001812  jnz     loc_180001B59
0x180001818  mov     rdx, [rsp+130h+hMem]
0x18000181d  lea     r8, [rsp+130h+var_E8]
0x180001822  mov     ecx, r13d
0x180001825  call    ULongAddStringSize
0x18000182a  test    eax, eax
0x18000182c  js      loc_180001742
0x180001832  mov     eax, [rsp+130h+var_E8]
0x180001836  lea     r13d, [rax+4]
0x18000183a  cmp     r13d, eax
0x18000183d  jb      loc_180001742
0x180001843  mov     eax, [rsi]
0x180001845  mov     r8, [r14]
0x180001848  mov     edx, r13d
0x18000184b  mov     [rsp+130h+var_E0], eax
0x18000184f  mov     [rsp+130h+var_E8], r13d
0x180001854  call    SddlpReAlloc
0x180001859  mov     [r14], rax
0x18000185c  test    rax, rax
0x18000185f  jz      loc_180001A94
0x180001865  mov     r8, [rsp+130h+var_C8]
0x18000186a  mov     edx, r13d
0x18000186d  mov     r9, [rsp+130h+hMem]
0x180001872  sub     edx, r8d
0x180001875  mov     ecx, r8d
0x180001878  add     edx, 4
0x18000187b  shr     rcx, 1
0x18000187e  lea     r8, aLs_0; "%ls, "
0x180001885  add     rcx, 0FFFFFFFFFFFFFFFEh
0x180001889  shr     rdx, 1
0x18000188c  lea     rcx, [rax+rcx*2]
0x180001890  call    RtlStringCchPrintfW
0x180001895  test    eax, eax
0x180001897  js      loc_180001ADE
0x18000189d  mov     eax, [rsp+130h+var_E0]
0x1800018a1  add     [rsp+130h+var_E4], eax
0x1800018a5  mov     rcx, [rsp+130h+hMem]; hMem
0x1800018aa  call    cs:__imp_LocalFree
0x1800018b0  mov     r8d, [rsp+130h+var_E4]
0x1800018b5  mov     r9d, [rsp+130h+var_DC]
0x1800018ba  mov     [rsp+130h+hMem], 0
0x1800018c3  mov     [rsp+130h+var_C8], r13
0x1800018c8  jmp     loc_1800017B3
0x1800018cd  mov     edi, 538h
0x1800018d2  jmp     loc_180001B59
0x1800018d7  mov     rax, [r14]
0x1800018da  mov     edx, r13d
0x1800018dd  shr     rdx, 1
0x1800018e0  mov     word ptr [rax+rdx*2-8], 7Dh ; '}'
0x1800018e7  xor     eax, eax
0x1800018e9  mov     rcx, [r14]
0x1800018ec  mov     [rcx+rdx*2-6], ax
0x1800018f1  lea     eax, [r9+r12]
0x1800018f5  mov     [rsi], eax
0x1800018f7  jmp     loc_180001B59
0x1800018fc  lea     eax, [rbx-1]
0x1800018ff  cmp     eax, 4
0x180001902  jb      loc_180001662
0x180001908  mov     r12d, [r15+1]
0x18000190c  lea     eax, [rbx-5]
0x18000190f  mov     dword ptr [r9], 5
0x180001916  cmp     eax, r12d
0x180001919  jb      loc_180001662
0x18000191f  test    r12d, r12d
0x180001922  jz      loc_180001662
0x180001928  mov     eax, r12d
0x18000192b  mov     ecx, 0FFFFFFFFh
0x180001930  add     rax, rax
0x180001933  cmp     rax, rcx
0x180001936  ja      loc_1800019DA
0x18000193c  lea     edx, [rax+2]
0x18000193f  cmp     edx, eax
0x180001941  jb      loc_1800019DA
0x180001947  mov     eax, edx
0x180001949  add     rax, rax
0x18000194c  cmp     rax, rcx
0x18000194f  ja      loc_1800019DA
0x180001955  mov     edx, eax; uBytes
0x180001957  mov     ecx, 40h ; '@'; uFlags
0x18000195c  mov     ebx, eax
0x18000195e  call    cs:__imp_LocalAlloc
0x180001964  mov     [r14], rax
0x180001967  test    rax, rax
0x18000196a  jz      loc_180001A94
0x180001970  mov     ecx, 23h ; '#'
0x180001975  lea     r13, a0123456789abcd; "0123456789abcdef"
0x18000197c  mov     [rax], cx
0x18000197f  xor     r11d, r11d
0x180001982  mov     eax, [rsi]
0x180001984  lea     r9d, [r11+r11]
0x180001988  mov     rcx, [r14]
0x18000198b  lea     edx, [r9+1]
0x18000198f  add     rax, r15
0x180001992  movzx   r10d, byte ptr [r11+rax]
0x180001997  inc     r11d
0x18000199a  mov     r8d, r10d
0x18000199d  and     r10d, 0Fh
0x1800019a1  shr     r8, 4
0x1800019a5  movzx   eax, word ptr [r13+r8*2+0]
0x1800019ab  mov     [rcx+rdx*2], ax
0x1800019af  lea     edx, [r9+2]
0x1800019b3  mov     rcx, [r14]
0x1800019b6  movzx   eax, word ptr [r13+r10*2+0]
0x1800019bc  mov     [rcx+rdx*2], ax
0x1800019c0  cmp     r11d, r12d
0x1800019c3  jb      short loc_180001982
0x1800019c5  mov     rcx, [r14]
0x1800019c8  xor     eax, eax
0x1800019ca  shr     rbx, 1
0x1800019cd  mov     [rcx+rbx*2-2], ax
0x1800019d2  add     [rsi], r12d
0x1800019d5  jmp     loc_180001B59
0x1800019da  mov     edi, 216h
0x1800019df  jmp     loc_180001B69
0x1800019e4  lea     eax, [rbx-1]
0x1800019e7  cmp     eax, 4
0x1800019ea  jb      loc_180001662
0x1800019f0  mov     r13d, [r15+1]
0x1800019f4  lea     eax, [rbx-5]
0x1800019f7  mov     dword ptr [r9], 5
0x1800019fe  cmp     eax, r13d
0x180001a01  jb      loc_180001662
0x180001a07  lea     eax, [r13+6]
0x180001a0b  cmp     eax, r13d
0x180001a0e  jb      short loc_1800019DA
0x180001a10  mov     edx, eax; uBytes
0x180001a12  mov     ecx, 40h ; '@'; uFlags
0x180001a17  call    cs:__imp_LocalAlloc
0x180001a1d  mov     [r14], rax
0x180001a20  test    rax, rax
0x180001a23  jz      short loc_180001A94
0x180001a25  mov     r12d, 22h ; '"'
0x180001a2b  mov     r8d, r13d; Size
0x180001a2e  mov     [rax], r12w
0x180001a32  mov     ebx, r13d
0x180001a35  mov     edx, [rsi]
0x180001a37  mov     rcx, [r14]
0x180001a3a  add     rdx, r15; Src
0x180001a3d  add     rcx, 2; void *
0x180001a41  call    memcpy_0
  ... truncated ...
```

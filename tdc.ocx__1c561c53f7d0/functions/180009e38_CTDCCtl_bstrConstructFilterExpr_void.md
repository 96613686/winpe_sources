# CTDCCtl::bstrConstructFilterExpr(void)

- ea: `0x180009e38`
- end: `0x18000a074`
- name: `?bstrConstructFilterExpr@CTDCCtl@@AEAAPEAGXZ`
- size: `572`
- prototype: `unsigned __int16 *__fastcall(CTDCCtl *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006c40`
- `0x1800089d0`

## callees

- `0x180009e38`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180009e57`
- `OLEAUT32!__imp_SysAllocString` at `0x180009e57`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180009ef7`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180009ef7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a062`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a062`
- `OLEAUT32!__imp_SysStringLen` at `0x180009ed0`
- `OLEAUT32!__imp_SysStringLen` at `0x180009edb`
- `OLEAUT32!__imp_SysStringLen` at `0x180009ee8`
- `OLEAUT32!__imp_SysStringLen` at `0x180009ed0`
- `OLEAUT32!__imp_SysStringLen` at `0x180009edb`
- `OLEAUT32!__imp_SysStringLen` at `0x180009ee8`

## pseudocode

```c
BSTR __fastcall CTDCCtl::bstrConstructFilterExpr(CTDCCtl *this)
{
  const OLECHAR *v2; // rcx
  BSTR v3; // rbx
  _WORD *v4; // rax
  _WORD *v5; // rax
  OLECHAR *v6; // rbx
  UINT v7; // edi
  UINT v8; // edi
  UINT v9; // edi
  BSTR v10; // rax
  __int64 v11; // r11
  OLECHAR *v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rdx
  BSTR v15; // rcx
  BSTR v16; // rcx
  __int64 v18; // rcx
  unsigned __int64 v19; // rax
  OLECHAR *v20; // rdx
  BSTR v21; // r9
  __int64 v22; // rcx
  OLECHAR *v23; // rcx
  BSTR v24; // rcx
  __int64 v26; // rcx
  unsigned __int64 v27; // r8
  OLECHAR *v28; // rdx
  OLECHAR *v29; // rax
  OLECHAR *v30; // rcx
  BSTR v31; // rcx
  int v33; // ecx
  BSTR pbstr; // [rsp+50h] [rbp+8h] BYREF

  v2 = (const OLECHAR *)*((_QWORD *)this + 60);
  if ( v2 && *v2 )
    return SysAllocString(v2);
  v4 = (_WORD *)*((_QWORD *)this + 54);
  v3 = 0;
  if ( v4 )
  {
    if ( *v4 )
    {
      v5 = (_WORD *)*((_QWORD *)this + 52);
      if ( v5 )
      {
        if ( *v5 )
        {
          pbstr = 0;
          if ( (*(int (__fastcall **)(char *, BSTR *))(*((_QWORD *)this + 22) + 184LL))((char *)this + 176, &pbstr) >= 0 )
          {
            v6 = (OLECHAR *)*((_QWORD *)this + 54);
            v7 = SysStringLen(*((BSTR *)this + 52));
            v8 = SysStringLen(v6) + v7;
            v9 = SysStringLen(pbstr) + 2 + v8;
            v10 = SysAllocStringLen(0, v9);
            v3 = v10;
            if ( v10 )
            {
              v11 = 2147483646;
              if ( v9 )
              {
                if ( v9 <= 0x7FFFFFFFuLL )
                {
                  v12 = (OLECHAR *)*((_QWORD *)this + 54);
                  v13 = 2147483646;
                  v14 = v9;
                  do
                  {
                    if ( !v13 )
                      break;
                    if ( !*v12 )
                      break;
                    *v10++ = *v12++;
                    --v13;
                    --v14;
                  }
                  while ( v14 );
                  v15 = v10 - 1;
                  if ( v14 )
                    v15 = v10;
                  *v15 = 0;
                }
                else
                {
                  *v10 = 0;
                }
              }
              v16 = v3;
              while ( *v16++ )
                ;
              v18 = (unsigned int)(v16 - v3) - 1;
              v19 = v9 - v18;
              if ( v9 != v18 )
              {
                v20 = &v3[v18];
                if ( v19 <= 0x7FFFFFFF )
                {
                  v21 = pbstr;
                  v22 = 2147483646;
                  do
                  {
                    if ( !v22 )
                      break;
                    if ( !*v21 )
                      break;
                    *v20++ = *v21++;
                    --v22;
                    --v19;
                  }
                  while ( v19 );
                  v23 = v20 - 1;
                  if ( v19 )
                    v23 = v20;
                  *v23 = 0;
                }
                else
                {
                  *v20 = 0;
                }
              }
              v24 = v3;
              while ( *v24++ )
                ;
              v26 = (unsigned int)(v24 - v3) - 1;
              v3[v26] = 34;
              v27 = v9 - (unsigned __int64)(unsigned int)(v26 + 1);
              if ( v27 )
              {
                v28 = &v3[(unsigned int)(v26 + 1)];
                if ( v27 <= 0x7FFFFFFF )
                {
                  v29 = (OLECHAR *)*((_QWORD *)this + 52);
                  do
                  {
                    if ( !v11 )
                      break;
                    if ( !*v29 )
                      break;
                    *v28++ = *v29++;
                    --v11;
                    --v27;
                  }
                  while ( v27 );
                  v30 = v28 - 1;
                  if ( v27 )
                    v30 = v28;
                  *v30 = 0;
                }
                else
                {
                  *v28 = 0;
                }
              }
              v31 = v3;
              while ( *v31++ )
                ;
              v33 = v31 - v3 - 1;
              v3[v33] = 34;
              v3[v33 + 1] = 0;
            }
            SysFreeString(pbstr);
          }
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180009e38  push    rbx
0x180009e3a  push    rbp
0x180009e3b  push    rsi
0x180009e3c  push    rdi
0x180009e3d  sub     rsp, 28h
0x180009e41  mov     rsi, rcx
0x180009e44  xor     ebp, ebp
0x180009e46  mov     rcx, [rcx+1E0h]; psz
0x180009e4d  test    rcx, rcx
0x180009e50  jz      short loc_180009E65
0x180009e52  cmp     [rcx], bp
0x180009e55  jz      short loc_180009E65
0x180009e57  call    cs:__imp_SysAllocString
0x180009e5d  mov     rbx, rax
0x180009e60  jmp     loc_18000A068
0x180009e65  mov     rax, [rsi+1B0h]
0x180009e6c  mov     rbx, rbp
0x180009e6f  test    rax, rax
0x180009e72  jz      loc_18000A068
0x180009e78  cmp     [rax], bp
0x180009e7b  jz      loc_18000A068
0x180009e81  mov     rax, [rsi+1A0h]
0x180009e88  test    rax, rax
0x180009e8b  jz      loc_18000A068
0x180009e91  cmp     [rax], bp
0x180009e94  jz      loc_18000A068
0x180009e9a  lea     rcx, [rsi+0B0h]
0x180009ea1  mov     [rsp+48h+pbstr], rbp
0x180009ea6  mov     rax, [rcx]
0x180009ea9  lea     rdx, [rsp+48h+pbstr]
0x180009eae  mov     rax, [rax+0B8h]
0x180009eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eba  test    eax, eax
0x180009ebc  js      loc_18000A068
0x180009ec2  mov     rcx, [rsi+1A0h]; pbstr
0x180009ec9  mov     rbx, [rsi+1B0h]
0x180009ed0  call    cs:__imp_SysStringLen
0x180009ed6  mov     rcx, rbx; pbstr
0x180009ed9  mov     edi, eax
0x180009edb  call    cs:__imp_SysStringLen
0x180009ee1  mov     rcx, [rsp+48h+pbstr]; pbstr
0x180009ee6  add     edi, eax
0x180009ee8  call    cs:__imp_SysStringLen
0x180009eee  add     eax, 2
0x180009ef1  xor     ecx, ecx; strIn
0x180009ef3  add     edi, eax
0x180009ef5  mov     edx, edi; ui
0x180009ef7  call    cs:__imp_SysAllocStringLen
0x180009efd  mov     rbx, rax
0x180009f00  test    rax, rax
0x180009f03  jz      loc_18000A05D
0x180009f09  mov     r8d, edi
0x180009f0c  mov     edi, 7FFFFFFFh
0x180009f11  lea     r11d, [rdi-1]
0x180009f15  test    r8, r8
0x180009f18  jz      short loc_180009F63
0x180009f1a  cmp     r8, rdi
0x180009f1d  jbe     short loc_180009F24
0x180009f1f  mov     [rax], bp
0x180009f22  jmp     short loc_180009F63
0x180009f24  mov     r9, [rsi+1B0h]
0x180009f2b  mov     rcx, r11
0x180009f2e  mov     rdx, r8
0x180009f31  test    rcx, rcx
0x180009f34  jz      short loc_180009F55
0x180009f36  movzx   r10d, word ptr [r9]
0x180009f3a  test    r10w, r10w
0x180009f3e  jz      short loc_180009F55
0x180009f40  mov     [rax], r10w
0x180009f44  add     r9, 2
0x180009f48  add     rax, 2
0x180009f4c  dec     rcx
0x180009f4f  sub     rdx, 1
0x180009f53  jnz     short loc_180009F31
0x180009f55  test    rdx, rdx
0x180009f58  lea     rcx, [rax-2]
0x180009f5c  cmovnz  rcx, rax
0x180009f60  mov     [rcx], bp
0x180009f63  mov     rcx, rbx
0x180009f66  movzx   eax, word ptr [rcx]
0x180009f69  add     rcx, 2
0x180009f6d  test    ax, ax
0x180009f70  jnz     short loc_180009F66
0x180009f72  sub     rcx, rbx
0x180009f75  mov     rax, r8
0x180009f78  sar     rcx, 1
0x180009f7b  dec     ecx
0x180009f7d  sub     rax, rcx
0x180009f80  jz      short loc_180009FCA
0x180009f82  lea     rdx, [rbx+rcx*2]
0x180009f86  cmp     rax, rdi
0x180009f89  jbe     short loc_180009F90
0x180009f8b  mov     [rdx], bp
0x180009f8e  jmp     short loc_180009FCA
0x180009f90  mov     r9, [rsp+48h+pbstr]
0x180009f95  mov     rcx, r11
0x180009f98  test    rcx, rcx
0x180009f9b  jz      short loc_180009FBC
0x180009f9d  movzx   r10d, word ptr [r9]
0x180009fa1  test    r10w, r10w
0x180009fa5  jz      short loc_180009FBC
0x180009fa7  mov     [rdx], r10w
0x180009fab  add     r9, 2
0x180009faf  add     rdx, 2
0x180009fb3  dec     rcx
0x180009fb6  sub     rax, 1
0x180009fba  jnz     short loc_180009F98
0x180009fbc  test    rax, rax
0x180009fbf  lea     rcx, [rdx-2]
0x180009fc3  cmovnz  rcx, rdx
0x180009fc7  mov     [rcx], bp
0x180009fca  mov     rcx, rbx
0x180009fcd  movzx   eax, word ptr [rcx]
0x180009fd0  add     rcx, 2
0x180009fd4  test    ax, ax
0x180009fd7  jnz     short loc_180009FCD
0x180009fd9  sub     rcx, rbx
0x180009fdc  mov     r9d, 22h ; '"'
0x180009fe2  sar     rcx, 1
0x180009fe5  dec     ecx
0x180009fe7  lea     eax, [rcx+1]
0x180009fea  mov     [rbx+rcx*2], r9w
0x180009fef  mov     ecx, eax
0x180009ff1  sub     r8, rcx
0x180009ff4  jz      short loc_18000A03A
0x180009ff6  lea     rdx, [rbx+rax*2]
0x180009ffa  cmp     r8, rdi
0x180009ffd  jbe     short loc_18000A004
0x180009fff  mov     [rdx], bp
0x18000a002  jmp     short loc_18000A03A
0x18000a004  mov     rax, [rsi+1A0h]
0x18000a00b  test    r11, r11
0x18000a00e  jz      short loc_18000A02C
0x18000a010  movzx   ecx, word ptr [rax]
0x18000a013  test    cx, cx
0x18000a016  jz      short loc_18000A02C
0x18000a018  mov     [rdx], cx
0x18000a01b  add     rax, 2
0x18000a01f  add     rdx, 2
0x18000a023  dec     r11
0x18000a026  sub     r8, 1
0x18000a02a  jnz     short loc_18000A00B
0x18000a02c  test    r8, r8
0x18000a02f  lea     rcx, [rdx-2]
0x18000a033  cmovnz  rcx, rdx
0x18000a037  mov     [rcx], bp
0x18000a03a  mov     rcx, rbx
0x18000a03d  movzx   eax, word ptr [rcx]
0x18000a040  add     rcx, 2
0x18000a044  test    ax, ax
0x18000a047  jnz     short loc_18000A03D
0x18000a049  sub     rcx, rbx
0x18000a04c  sar     rcx, 1
0x18000a04f  dec     ecx
0x18000a051  lea     eax, [rcx+1]
0x18000a054  mov     [rbx+rcx*2], r9w
0x18000a059  mov     [rbx+rax*2], bp
0x18000a05d  mov     rcx, [rsp+48h+pbstr]; bstrString
0x18000a062  call    cs:__imp_SysFreeString
0x18000a068  mov     rax, rbx
0x18000a06b  add     rsp, 28h
0x18000a06f  pop     rdi
0x18000a070  pop     rsi
0x18000a071  pop     rbp
0x18000a072  pop     rbx
0x18000a073  retn
```

# GetEnumNameFromGuidList

- ea: `0x180046a24`
- end: `0x180046bee`
- name: `GetEnumNameFromGuidList`
- size: `458`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180043390`

## callees

- `0x1800113a8`
- `0x180046a24`
- `0x180046bf4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046a98`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180046a98`

## pseudocode

```c
__int64 *__fastcall GetEnumNameFromGuidList(
        __int64 *a1,
        _QWORD *a2,
        _QWORD *a3,
        const WCHAR *a4,
        unsigned int a5,
        char a6,
        unsigned __int16 *a7,
        unsigned int a8)
{
  _QWORD *i; // rax
  __int64 v11; // rcx
  __int64 **v12; // rbx
  __int64 **j; // rdi
  __int64 *v14; // rbx
  unsigned int v15; // ebp
  int v16; // r12d
  unsigned __int16 *v17; // r14
  __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  __int64 v20; // rcx
  const unsigned __int16 *v21; // r8
  __int64 v22; // rax
  __int64 v23; // rcx

  *a1 = 0;
  a1[1] = 0;
  for ( i = (_QWORD *)*a2; i != a2; i = (_QWORD *)*i )
  {
    v11 = i[5] - *a3;
    if ( !v11 )
      v11 = i[6] - a3[1];
    if ( !v11 )
    {
      v12 = (__int64 **)(i + 2);
      for ( j = (__int64 **)i[2]; j != v12; j = (__int64 **)*j )
      {
        if ( CompareStringOrdinal((LPCWCH)j[5], -1, a4, -1, 1) == 2 )
        {
          v14 = j[2];
          v15 = a8;
          v16 = 0;
          v17 = a7;
          while ( v14 != j[3] )
          {
            if ( a6 )
            {
              if ( (a5 & (_DWORD)v14[4]) == *((_DWORD *)v14 + 8) )
              {
                v20 = *v14;
                v21 = L"%.*s";
                v22 = v14[1] - *v14;
                *a1 = *v14;
                a1[1] = v22 >> 1;
                if ( v16 )
                  v21 = L" | %.*s";
                if ( StringCbPrintfW(v17, v15, v21, *((unsigned int *)a1 + 2), v20) < 0 )
                  goto LABEL_28;
                v23 = -1;
                do
                  ++v23;
                while ( v17[v23] );
                v17 += (unsigned int)v23;
                v15 += -2 - 2 * v23;
                ++v16;
              }
            }
            else if ( *((_DWORD *)v14 + 8) == a5 )
            {
              v18 = v14[1] - *v14;
              *a1 = *v14;
              a1[1] = v18 >> 1;
              goto LABEL_16;
            }
            v14 += 5;
          }
          goto LABEL_27;
        }
      }
      break;
    }
  }
  v15 = a8;
  v17 = a7;
LABEL_27:
  if ( a6 )
  {
LABEL_28:
    StringCchPrintfW(v17, (unsigned __int64)v15 >> 1, L"(0x%X)", a5);
  }
  else
  {
LABEL_16:
    v19 = (unsigned __int64)v15 >> 1;
    if ( a1[1] )
      StringCchPrintfW(v17, v19, L"%.*s", *((unsigned int *)a1 + 2), *a1);
    else
      StringCchPrintfW(v17, v19, L"0x%X", a5);
  }
  return a1;
}

```

## disassembly

```asm
0x180046a24  push    rbx
0x180046a26  push    rbp
0x180046a27  push    rsi
0x180046a28  push    rdi
0x180046a29  push    r12
0x180046a2b  push    r14
0x180046a2d  push    r15
0x180046a2f  sub     rsp, 30h
0x180046a33  mov     rbp, r9
0x180046a36  mov     rsi, rcx
0x180046a39  xor     r9d, r9d
0x180046a3c  mov     [rcx], r9
0x180046a3f  mov     [rcx+8], r9
0x180046a43  mov     rax, [rdx]
0x180046a46  mov     r15d, [rsp+68h+arg_20]
0x180046a4e  cmp     rax, rdx
0x180046a51  jz      loc_180046B9F
0x180046a57  mov     rcx, [rax+28h]
0x180046a5b  sub     rcx, [r8]
0x180046a5e  jnz     short loc_180046A68
0x180046a60  mov     rcx, [rax+30h]
0x180046a64  sub     rcx, [r8+8]
0x180046a68  test    rcx, rcx
0x180046a6b  jz      short loc_180046A72
0x180046a6d  mov     rax, [rax]
0x180046a70  jmp     short loc_180046A46
0x180046a72  lea     rbx, [rax+10h]
0x180046a76  mov     rdi, [rbx]
0x180046a79  cmp     rdi, rbx
0x180046a7c  jz      loc_180046B9C
0x180046a82  mov     rcx, [rdi+28h]; lpString1
0x180046a86  or      r9d, 0FFFFFFFFh; cchCount2
0x180046a8a  or      edx, r9d; cchCount1
0x180046a8d  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180046a95  mov     r8, rbp; lpString2
0x180046a98  call    cs:__imp_CompareStringOrdinal
0x180046a9e  cmp     eax, 2
0x180046aa1  jz      short loc_180046AA8
0x180046aa3  mov     rdi, [rdi]
0x180046aa6  jmp     short loc_180046A79
0x180046aa8  mov     rbx, [rdi+10h]
0x180046aac  xor     r9d, r9d
0x180046aaf  mov     ebp, dword ptr [rsp+68h+arg_38]
0x180046ab6  mov     r12d, r9d
0x180046ab9  mov     r14, [rsp+68h+arg_30]
0x180046ac1  cmp     rbx, [rdi+18h]
0x180046ac5  jz      loc_180046BAE
0x180046acb  cmp     [rsp+68h+arg_28], r9b
0x180046ad3  jnz     short loc_180046B22
0x180046ad5  cmp     [rbx+20h], r15d
0x180046ad9  jnz     loc_180046B93
0x180046adf  mov     rax, [rbx]
0x180046ae2  mov     rcx, [rbx+8]
0x180046ae6  sub     rcx, rax
0x180046ae9  mov     [rsi], rax
0x180046aec  sar     rcx, 1
0x180046aef  mov     [rsi+8], rcx
0x180046af3  mov     edx, ebp
0x180046af5  shr     rdx, 1; unsigned __int64
0x180046af8  cmp     [rsi+8], r9
0x180046afc  jz      loc_180046BCA
0x180046b02  mov     rax, [rsi]
0x180046b05  lea     r8, aS_6; "%.*s"
0x180046b0c  mov     r9d, [rsi+8]
0x180046b10  mov     rcx, r14; unsigned __int16 *
0x180046b13  mov     qword ptr [rsp+68h+bIgnoreCase], rax
0x180046b18  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046b1d  jmp     loc_180046BDC
0x180046b22  mov     eax, [rbx+20h]
0x180046b25  and     eax, r15d
0x180046b28  cmp     eax, [rbx+20h]
0x180046b2b  jnz     short loc_180046B93
0x180046b2d  mov     rcx, [rbx]
0x180046b30  lea     r8, aS_6; "%.*s"
0x180046b37  mov     rax, [rbx+8]
0x180046b3b  sub     rax, rcx
0x180046b3e  mov     [rsi], rcx
0x180046b41  sar     rax, 1
0x180046b44  mov     [rsi+8], rax
0x180046b48  test    r12d, r12d
0x180046b4b  mov     r9d, [rsi+8]
0x180046b4f  lea     rax, aS_4; " | %.*s"
0x180046b56  mov     qword ptr [rsp+68h+bIgnoreCase], rcx
0x180046b5b  cmovnz  r8, rax; unsigned __int16 *
0x180046b5f  mov     edx, ebp; unsigned __int64
0x180046b61  mov     rcx, r14; unsigned __int16 *
0x180046b64  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046b69  xor     r9d, r9d
0x180046b6c  test    eax, eax
0x180046b6e  js      short loc_180046BBC
0x180046b70  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180046b74  inc     rcx
0x180046b77  cmp     [r14+rcx*2], r9w
0x180046b7c  jnz     short loc_180046B74
0x180046b7e  mov     eax, ecx
0x180046b80  lea     r14, [r14+rax*2]
0x180046b84  lea     eax, [rcx+rcx]
0x180046b87  mov     ecx, 0FFFFFFFEh
0x180046b8c  sub     ecx, eax
0x180046b8e  add     ebp, ecx
0x180046b90  inc     r12d
0x180046b93  add     rbx, 28h ; '('
0x180046b97  jmp     loc_180046AC1
0x180046b9c  xor     r9d, r9d
0x180046b9f  mov     ebp, dword ptr [rsp+68h+arg_38]
0x180046ba6  mov     r14, [rsp+68h+arg_30]
0x180046bae  cmp     [rsp+68h+arg_28], r9b
0x180046bb6  jz      loc_180046AF3
0x180046bbc  mov     edx, ebp
0x180046bbe  lea     r8, a0xX; "(0x%X)"
0x180046bc5  shr     rdx, 1
0x180046bc8  jmp     short loc_180046BD1
0x180046bca  lea     r8, a0xX_0; "0x%X"
0x180046bd1  mov     r9d, r15d
0x180046bd4  mov     rcx, r14; unsigned __int16 *
0x180046bd7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046bdc  mov     rax, rsi
0x180046bdf  add     rsp, 30h
0x180046be3  pop     r15
0x180046be5  pop     r14
0x180046be7  pop     r12
0x180046be9  pop     rdi
0x180046bea  pop     rsi
0x180046beb  pop     rbp
0x180046bec  pop     rbx
0x180046bed  retn
```

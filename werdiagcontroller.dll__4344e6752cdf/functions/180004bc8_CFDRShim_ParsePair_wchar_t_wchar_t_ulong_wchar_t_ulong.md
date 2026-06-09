# CFDRShim::ParsePair(wchar_t *,wchar_t *,ulong,wchar_t *,ulong)

- ea: `0x180004bc8`
- end: `0x180004e13`
- name: `?ParsePair@CFDRShim@@AEAAJPEA_W0K0K@Z`
- size: `587`
- prototype: `__int64 __fastcall(CFDRShim *this, wchar_t *, wchar_t *, __int64, wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004e1c`

## callees

- `0x180004bc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180004c6b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180004c6b`
- `ntdll!DbgPrintEx` at `0x180004c58`
- `ntdll!DbgPrintEx` at `0x180004dc2`
- `ntdll!DbgPrintEx` at `0x180004ddd`
- `ntdll!DbgPrintEx` at `0x180004df7`
- `ntdll!DbgPrintEx` at `0x180004c58`
- `ntdll!DbgPrintEx` at `0x180004dc2`
- `ntdll!DbgPrintEx` at `0x180004ddd`
- `ntdll!DbgPrintEx` at `0x180004df7`

## string_xrefs

- `0x180004d4a`: `WERDIAG: Failed copying string. HRESULT: %08X\n`

## pseudocode

```c
__int64 __fastcall CFDRShim::ParsePair(CFDRShim *this, wchar_t *a2, wchar_t *a3, __int64 a4, wchar_t *a5)
{
  wchar_t *v5; // rsi
  const wchar_t *v6; // r14
  wchar_t *v7; // r15
  wchar_t *v8; // rax
  __int64 v9; // rdx
  unsigned int v10; // ebx
  __int64 v11; // r12
  wchar_t *v12; // rax
  __int64 v13; // r10
  wchar_t *v14; // r8
  __int64 v15; // rdx
  _WORD *v16; // rax
  unsigned int v17; // r9d
  unsigned __int64 v18; // rcx
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdx
  wchar_t *v23; // rcx

  v5 = a3;
  v6 = a2;
  if ( a2 )
  {
    if ( a3 )
    {
      v7 = a5;
      if ( a5 )
      {
        v8 = a2;
        v9 = 0x7FFFFFFF;
        do
        {
          if ( !*v8 )
            break;
          ++v8;
          --v9;
        }
        while ( v9 );
        v10 = v9 == 0 ? 0x80070057 : 0;
        v11 = (0x7FFFFFFF - v9) & -(__int64)(v9 != 0);
        if ( !v9 )
        {
          DbgPrintEx(0x96u, 0, "WERDIAG: Failed obtaining string length. HRESULT: %08X\n", v10);
          return v10;
        }
        v12 = wcschr(v6, 0x3Du);
        if ( !v12 )
        {
          DbgPrintEx(0x96u, 0, "WERDIAG: Invalid format: expected '='.\n");
          return (unsigned int)-2147024809;
        }
        v13 = v12 - v6 + 1;
        if ( !(v12 - v6) || v11 == v13 )
        {
          DbgPrintEx(0x96u, 0, "WERDIAG: Invalid args\n");
          return (unsigned int)-2147024809;
        }
        v14 = v12 + 1;
        if ( v12 == (wchar_t *)-2LL )
        {
          v17 = -2147024809;
        }
        else
        {
          v15 = 0x7FFFFFFF;
          v16 = v12 + 1;
          do
          {
            if ( !*v16 )
              break;
            ++v16;
            --v15;
          }
          while ( v15 );
          v17 = v15 == 0 ? 0x80070057 : 0;
          v18 = (0x7FFFFFFF - v15) & -(__int64)(v15 != 0);
          if ( v15 )
          {
            if ( v18 <= 0x7FFFFFFE )
            {
              v19 = 512;
              do
              {
                if ( !v18 )
                  break;
                if ( !*v14 )
                  break;
                *v7++ = *v14++;
                --v18;
                --v19;
              }
              while ( v19 );
              v20 = v7 - 1;
              v10 = v19 == 0 ? 0x8007007A : 0;
              if ( v19 )
                v20 = v7;
              *v20 = 0;
              if ( v19 )
              {
                v21 = v13 - 1;
                if ( (unsigned __int64)(v13 - 1) <= 0x7FFFFFFE )
                {
                  v22 = 128;
                  do
                  {
                    if ( !v21 )
                      break;
                    if ( !*v6 )
                      break;
                    *v5++ = *v6++;
                    --v21;
                    --v22;
                  }
                  while ( v22 );
                  v23 = v5 - 1;
                  v10 = v22 == 0 ? 0x8007007A : 0;
                  if ( v22 )
                    v23 = v5;
                  *v23 = 0;
                  if ( v22 )
                    return 0;
                }
                else
                {
                  v10 = -2147024809;
                  *v5 = 0;
                }
              }
            }
            else
            {
              v10 = -2147024809;
              *a5 = 0;
            }
            DbgPrintEx(0x96u, 0, "WERDIAG: Failed copying string. HRESULT: %08X\n", v10);
            return v10;
          }
        }
        DbgPrintEx(0x96u, 0, "WERDIAG: Failed getting string length. HRESULT: %08X\n", v17);
        return (unsigned int)-2147467259;
      }
    }
  }
  DbgPrintEx(0x96u, 0, "WERDIAG: Invalid args: The pair string cannot be null\n");
  return 2147942487LL;
}

```

## disassembly

```asm
0x180004bc8  push    rbx
0x180004bca  push    rbp
0x180004bcb  push    rsi
0x180004bcc  push    rdi
0x180004bcd  push    r12
0x180004bcf  push    r13
0x180004bd1  push    r14
0x180004bd3  push    r15
0x180004bd5  sub     rsp, 28h
0x180004bd9  xor     r13d, r13d
0x180004bdc  mov     rsi, r8
0x180004bdf  mov     r14, rdx
0x180004be2  test    rdx, rdx
0x180004be5  jz      loc_180004DE9
0x180004beb  test    r8, r8
0x180004bee  jz      loc_180004DE9
0x180004bf4  mov     r15, [rsp+68h+arg_20]
0x180004bfc  test    r15, r15
0x180004bff  jz      loc_180004DE9
0x180004c05  mov     ebp, 7FFFFFFFh
0x180004c0a  mov     rax, r14
0x180004c0d  mov     edx, ebp
0x180004c0f  cmp     [rax], r13w
0x180004c13  jz      short loc_180004C1F
0x180004c15  add     rax, 2
0x180004c19  sub     rdx, 1
0x180004c1d  jnz     short loc_180004C0F
0x180004c1f  mov     rax, rdx
0x180004c22  mov     edi, 80070057h
0x180004c27  neg     rax
0x180004c2a  mov     rcx, rbp
0x180004c2d  mov     rax, rdx
0x180004c30  sbb     ebx, ebx
0x180004c32  sub     rcx, rdx
0x180004c35  not     ebx
0x180004c37  and     ebx, edi
0x180004c39  neg     rax
0x180004c3c  sbb     r12, r12
0x180004c3f  and     r12, rcx
0x180004c42  test    rdx, rdx
0x180004c45  jnz     short loc_180004C63
0x180004c47  lea     r8, aWerdiagFailedO_3; "WERDIAG: Failed obtaining string length"...
0x180004c4e  mov     r9d, ebx
0x180004c51  xor     edx, edx; Level
0x180004c53  mov     ecx, 96h; ComponentId
0x180004c58  call    cs:__imp_DbgPrintEx
0x180004c5e  jmp     loc_180004DE5
0x180004c63  mov     edx, 3Dh ; '='; Ch
0x180004c68  mov     rcx, r14; Str
0x180004c6b  call    cs:__imp_wcschr
0x180004c71  mov     r8, rax
0x180004c74  test    rax, rax
0x180004c77  jnz     short loc_180004C85
0x180004c79  lea     r8, aWerdiagInvalid_0; "WERDIAG: Invalid format: expected '='."...
0x180004c80  jmp     loc_180004DD6
0x180004c85  mov     r10, r8
0x180004c88  sub     r10, r14
0x180004c8b  sar     r10, 1
0x180004c8e  inc     r10
0x180004c91  cmp     r10, 1
0x180004c95  jz      loc_180004DCF
0x180004c9b  cmp     r12, r10
0x180004c9e  jz      loc_180004DCF
0x180004ca4  add     r8, 2
0x180004ca8  jz      loc_180004DB1
0x180004cae  mov     rdx, rbp
0x180004cb1  mov     rax, r8
0x180004cb4  cmp     [rax], r13w
0x180004cb8  jz      short loc_180004CC4
0x180004cba  add     rax, 2
0x180004cbe  sub     rdx, 1
0x180004cc2  jnz     short loc_180004CB4
0x180004cc4  mov     rax, rdx
0x180004cc7  neg     rax
0x180004cca  mov     rax, rdx
0x180004ccd  sbb     r9d, r9d
0x180004cd0  sub     rbp, rdx
0x180004cd3  not     r9d
0x180004cd6  and     r9d, edi
0x180004cd9  neg     rax
0x180004cdc  sbb     rcx, rcx
0x180004cdf  and     rcx, rbp
0x180004ce2  test    rdx, rdx
0x180004ce5  jz      loc_180004DB4
0x180004ceb  mov     r9d, 7FFFFFFEh
0x180004cf1  cmp     rcx, r9
0x180004cf4  jbe     short loc_180004CFE
0x180004cf6  mov     ebx, edi
0x180004cf8  mov     [r15], r13w
0x180004cfc  jmp     short loc_180004D4A
0x180004cfe  mov     edx, 200h
0x180004d03  test    rcx, rcx
0x180004d06  jz      short loc_180004D26
0x180004d08  movzx   eax, word ptr [r8]
0x180004d0c  test    ax, ax
0x180004d0f  jz      short loc_180004D26
0x180004d11  mov     [r15], ax
0x180004d15  add     r8, 2
0x180004d19  add     r15, 2
0x180004d1d  dec     rcx
0x180004d20  sub     rdx, 1
0x180004d24  jnz     short loc_180004D03
0x180004d26  mov     rax, rdx
0x180004d29  lea     rcx, [r15-2]
0x180004d2d  neg     rax
0x180004d30  mov     r8d, 8007007Ah
0x180004d36  sbb     ebx, ebx
0x180004d38  not     ebx
0x180004d3a  and     ebx, r8d
0x180004d3d  test    rdx, rdx
0x180004d40  cmovnz  rcx, r15
0x180004d44  mov     [rcx], r13w
0x180004d48  jnz     short loc_180004D56
0x180004d4a  lea     r8, aWerdiagFailedC_3; "WERDIAG: Failed copying string. HRESULT"...
0x180004d51  jmp     loc_180004C4E
0x180004d56  lea     rax, [r10-1]
0x180004d5a  cmp     rax, r9
0x180004d5d  jbe     short loc_180004D67
0x180004d5f  mov     ebx, edi
0x180004d61  mov     [rsi], r13w
0x180004d65  jmp     short loc_180004D4A
0x180004d67  mov     edx, 80h
0x180004d6c  test    rax, rax
0x180004d6f  jz      short loc_180004D8E
0x180004d71  movzx   ecx, word ptr [r14]
0x180004d75  test    cx, cx
0x180004d78  jz      short loc_180004D8E
0x180004d7a  mov     [rsi], cx
0x180004d7d  add     r14, 2
0x180004d81  add     rsi, 2
0x180004d85  dec     rax
0x180004d88  sub     rdx, 1
0x180004d8c  jnz     short loc_180004D6C
0x180004d8e  mov     rax, rdx
0x180004d91  lea     rcx, [rsi-2]
0x180004d95  neg     rax
0x180004d98  sbb     ebx, ebx
0x180004d9a  not     ebx
0x180004d9c  and     ebx, r8d
0x180004d9f  test    rdx, rdx
0x180004da2  cmovnz  rcx, rsi
0x180004da6  mov     [rcx], r13w
0x180004daa  jz      short loc_180004D4A
0x180004dac  mov     ebx, r13d
0x180004daf  jmp     short loc_180004DE5
0x180004db1  mov     r9d, edi
0x180004db4  lea     r8, aWerdiagFailedG_1; "WERDIAG: Failed getting string length. "...
0x180004dbb  xor     edx, edx; Level
0x180004dbd  mov     ecx, 96h; ComponentId
0x180004dc2  call    cs:__imp_DbgPrintEx
0x180004dc8  mov     ebx, 80004005h
0x180004dcd  jmp     short loc_180004DE5
0x180004dcf  lea     r8, aWerdiagInvalid_10; "WERDIAG: Invalid args\n"
0x180004dd6  xor     edx, edx; Level
0x180004dd8  mov     ecx, 96h; ComponentId
0x180004ddd  call    cs:__imp_DbgPrintEx
0x180004de3  mov     ebx, edi
0x180004de5  mov     eax, ebx
0x180004de7  jmp     short loc_180004E02
0x180004de9  lea     r8, aWerdiagInvalid_7; "WERDIAG: Invalid args: The pair string "...
0x180004df0  xor     edx, edx; Level
0x180004df2  mov     ecx, 96h; ComponentId
0x180004df7  call    cs:__imp_DbgPrintEx
0x180004dfd  mov     eax, 80070057h
0x180004e02  add     rsp, 28h
0x180004e06  pop     r15
0x180004e08  pop     r14
0x180004e0a  pop     r13
0x180004e0c  pop     r12
0x180004e0e  pop     rdi
0x180004e0f  pop     rsi
0x180004e10  pop     rbp
0x180004e11  pop     rbx
0x180004e12  retn
```

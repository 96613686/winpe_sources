# CompressChunk

- ea: `0x18001dfe0`
- end: `0x18001e3f5`
- name: `CompressChunk`
- size: `1045`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180010938`
- `0x180016c54`
- `0x18001b6a0`
- `0x18001b770`
- `0x18001b870`
- `0x18001dfe0`
- `0x1800219c4`
- `0x1800607b0`
- `0x180060e5a`
- `0x180060e70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001e07c`
- `KERNEL32!GetLastError` at `0x18001e09d`
- `KERNEL32!GetLastError` at `0x18001e0e7`
- `KERNEL32!GetLastError` at `0x18001e108`
- `KERNEL32!GetLastError` at `0x18001e17d`
- `KERNEL32!GetLastError` at `0x18001e199`
- `KERNEL32!GetLastError` at `0x18001e24b`
- `KERNEL32!GetLastError` at `0x18001e267`
- `KERNEL32!GetLastError` at `0x18001e2e4`
- `KERNEL32!GetLastError` at `0x18001e300`
- `KERNEL32!GetLastError` at `0x18001e37c`
- `KERNEL32!GetLastError` at `0x18001e398`
- `KERNEL32!GetLastError` at `0x18001e07c`
- `KERNEL32!GetLastError` at `0x18001e09d`
- `KERNEL32!GetLastError` at `0x18001e0e7`
- `KERNEL32!GetLastError` at `0x18001e108`
- `KERNEL32!GetLastError` at `0x18001e17d`
- `KERNEL32!GetLastError` at `0x18001e199`
- `KERNEL32!GetLastError` at `0x18001e24b`
- `KERNEL32!GetLastError` at `0x18001e267`
- `KERNEL32!GetLastError` at `0x18001e2e4`
- `KERNEL32!GetLastError` at `0x18001e300`
- `KERNEL32!GetLastError` at `0x18001e37c`
- `KERNEL32!GetLastError` at `0x18001e398`

## string_xrefs

- `0x18001e289`: `CompressChunk`
- `0x18001e322`: `CompressChunk`
- `0x18001e3c0`: `CompressChunk`

## pseudocode

```c
__int64 __fastcall CompressChunk(__int64 a1, __int64 a2)
{
  __int64 v2; // r13
  signed int v3; // ebx
  __int64 v4; // r14
  UCHAR *v7; // rax
  int v8; // r15d
  __int64 v9; // rax
  __int64 v10; // rdx
  signed int LastError; // ecx
  signed int v12; // eax
  signed int v13; // eax
  unsigned int v14; // r8d
  __int64 v15; // rax
  signed int v16; // ecx
  signed int v17; // eax
  signed int v18; // eax
  signed int v19; // ecx
  signed int v20; // eax
  signed int v21; // eax
  ULONG v22; // eax
  ULONG v23; // edx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 inited; // rax
  UCHAR *v27; // r13
  void *v28; // r15
  __int64 v29; // rdx
  signed int v30; // ecx
  signed int v31; // eax
  signed int v32; // eax
  __int64 v33; // r8
  __int64 v34; // rdx
  signed int v35; // ecx
  signed int v36; // eax
  signed int v37; // eax
  signed int v38; // ecx
  signed int v39; // eax
  signed int v40; // eax
  ULONG cbInput; // [rsp+40h] [rbp-29h] BYREF
  int v43; // [rsp+44h] [rbp-25h] BYREF
  PUCHAR pbInput; // [rsp+48h] [rbp-21h]
  _BYTE v45[32]; // [rsp+50h] [rbp-19h] BYREF
  UCHAR pbOutput[8]; // [rsp+70h] [rbp+7h] BYREF
  __int64 v47; // [rsp+78h] [rbp+Fh]
  int v48; // [rsp+80h] [rbp+17h]

  v2 = *(_QWORD *)(a2 + 32);
  v3 = 0;
  v4 = 0;
  if ( a1 )
    v4 = *(_QWORD *)(a1 + 288);
  v7 = *(UCHAR **)(a2 + 64);
  cbInput = 0;
  pbInput = v7;
  memset_0(v45, 0, sizeof(v45));
  v8 = 0;
  if ( a1 )
  {
    v9 = a1;
    if ( *(_QWORD *)(a1 + 64) )
      v9 = *(_QWORD *)(a1 + 64);
    if ( (*(_BYTE *)(v9 + 36) & 2) != 0 )
      v8 = 1;
  }
  if ( v8 && !GenerateHashFromBuffer((PUCHAR)(a2 + 72), *(_DWORD *)(a2 + 48), (_QWORD *)(*(_QWORD *)(a2 + 40) + 12LL)) )
  {
    LastError = GetLastError();
    v12 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v12 = LastError;
    if ( v12 >= 0 )
    {
      v3 = -2147467259;
    }
    else
    {
      v13 = GetLastError();
      v3 = (unsigned __int16)v13 | 0x80070000;
      if ( v13 <= 0 )
        v3 = v13;
    }
    if ( v3 < 0 )
    {
      v14 = 789;
LABEL_89:
      UtilReportError((__int64)L"CompressChunk", v10, v14, v3);
      return (unsigned int)v3;
    }
    return (unsigned int)v3;
  }
  if ( v4 )
  {
LABEL_32:
    if ( !(*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD, ULONG *))(v4 + 16))(
            v4,
            a2 + 72,
            *(unsigned int *)(a2 + 48),
            *(_QWORD *)(a2 + 64),
            *(_DWORD *)(a2 + 48),
            &cbInput) )
    {
      v19 = GetLastError();
      v20 = (unsigned __int16)v19 | 0x80070000;
      if ( v19 <= 0 )
        v20 = v19;
      if ( v20 >= 0 )
      {
        v3 = -2147467259;
      }
      else
      {
        v21 = GetLastError();
        v3 = (unsigned __int16)v21 | 0x80070000;
        if ( v21 <= 0 )
          v3 = v21;
      }
      if ( v3 == -2147024785 )
      {
        v22 = *(_DWORD *)(a2 + 48);
        v3 = 0;
LABEL_42:
        cbInput = v22;
        v23 = v22;
LABEL_79:
        *(_DWORD *)(*(_QWORD *)(a2 + 40) + 8LL) = v23;
        if ( !(unsigned int)ReadWriteData(**(HANDLE **)(a2 + 40), 1u) )
        {
          v38 = GetLastError();
          v39 = (unsigned __int16)v38 | 0x80070000;
          if ( v38 <= 0 )
            v39 = v38;
          if ( v39 >= 0 )
          {
            v3 = -2147467259;
          }
          else
          {
            v40 = GetLastError();
            v3 = (unsigned __int16)v40 | 0x80070000;
            if ( v40 <= 0 )
              v3 = v40;
          }
          if ( v3 < 0 )
          {
            v14 = 909;
            goto LABEL_89;
          }
        }
        return (unsigned int)v3;
      }
      if ( v3 < 0 )
      {
        v14 = 826;
        goto LABEL_89;
      }
    }
    v22 = *(_DWORD *)(a2 + 48);
    v23 = cbInput;
    if ( cbInput == v22 )
      goto LABEL_42;
    if ( !v8 )
      goto LABEL_79;
    v24 = *(unsigned int *)(v2 + 28);
    v25 = *(unsigned int *)(v2 + 24);
    v43 = 0;
    inited = InitDecompressionContext(v25, v24);
    v27 = pbInput;
    v28 = (void *)inited;
    if ( !inited
      || !(*(unsigned int (__fastcall **)(__int64, PUCHAR, _QWORD, __int64, _DWORD, int *))(inited + 16))(
            inited,
            pbInput,
            cbInput,
            a2 + 72,
            *(_DWORD *)(a2 + 48),
            &v43)
      || !GenerateHashFromBuffer((PUCHAR)(a2 + 72), *(_DWORD *)(a2 + 48), pbOutput) )
    {
      v30 = GetLastError();
      v31 = (unsigned __int16)v30 | 0x80070000;
      if ( v30 <= 0 )
        v31 = v30;
      if ( v31 >= 0 )
      {
        v3 = -2147467259;
      }
      else
      {
        v32 = GetLastError();
        v3 = (unsigned __int16)v32 | 0x80070000;
        if ( v32 <= 0 )
          v3 = v32;
      }
      if ( v3 >= 0 )
        goto LABEL_60;
      UtilReportError((__int64)L"CompressChunk", v29, 0x362u, v3);
    }
    if ( v3 < 0 )
    {
LABEL_75:
      if ( v28 )
        FreeCompressionContext(v28);
      if ( v3 < 0 )
        return (unsigned int)v3;
      v23 = cbInput;
      goto LABEL_79;
    }
LABEL_60:
    v33 = *(_QWORD *)(a2 + 40);
    if ( *(_DWORD *)(a2 + 48) != v43
      || *(_QWORD *)(v33 + 12) != *(_QWORD *)pbOutput
      || *(_QWORD *)(v33 + 20) != v47
      || *(_DWORD *)(v33 + 28) != v48 )
    {
      v3 = 1392;
    }
    if ( !GenerateHashFromBuffer(v27, cbInput, (_QWORD *)(v33 + 12)) )
    {
      v35 = GetLastError();
      v36 = (unsigned __int16)v35 | 0x80070000;
      if ( v35 <= 0 )
        v36 = v35;
      if ( v36 >= 0 )
      {
        v3 = -2147467259;
      }
      else
      {
        v37 = GetLastError();
        v3 = (unsigned __int16)v37 | 0x80070000;
        if ( v37 <= 0 )
          v3 = v37;
      }
      if ( v3 < 0 )
        UtilReportError((__int64)L"CompressChunk", v34, 0x377u, v3);
    }
    goto LABEL_75;
  }
  v15 = InitCompressionContext(*(unsigned int *)(v2 + 24), *(unsigned int *)(v2 + 28));
  v4 = v15;
  if ( v15 )
  {
    if ( a1 )
      *(_QWORD *)(a1 + 288) = v15;
    goto LABEL_32;
  }
  v16 = GetLastError();
  v17 = (unsigned __int16)v16 | 0x80070000;
  if ( v16 <= 0 )
    v17 = v16;
  if ( v17 >= 0 )
  {
    v3 = -2147467259;
  }
  else
  {
    v18 = GetLastError();
    v3 = (unsigned __int16)v18 | 0x80070000;
    if ( v18 <= 0 )
      v3 = v18;
  }
  if ( v3 < 0 )
  {
    v14 = 801;
    goto LABEL_89;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001dfe0  mov     [rsp-8+arg_10], rbx
0x18001dfe5  push    rbp
0x18001dfe6  push    rsi
0x18001dfe7  push    rdi
0x18001dfe8  push    r12
0x18001dfea  push    r13
0x18001dfec  push    r14
0x18001dfee  push    r15
0x18001dff0  lea     rbp, [rsp-27h]
0x18001dff5  sub     rsp, 90h
0x18001dffc  mov     rax, cs:__security_cookie
0x18001e003  xor     rax, rsp
0x18001e006  mov     [rbp+57h+var_38], rax
0x18001e00a  mov     r13, [rdx+20h]
0x18001e00e  xor     ebx, ebx
0x18001e010  xor     r14d, r14d
0x18001e013  mov     rsi, rdx
0x18001e016  mov     rdi, rcx
0x18001e019  test    rcx, rcx
0x18001e01c  jz      short loc_18001E025
0x18001e01e  mov     r14, [rcx+120h]
0x18001e025  mov     rax, [rdx+40h]
0x18001e029  lea     rcx, [rbp+57h+var_70]; void *
0x18001e02d  and     [rbp+57h+cbInput], ebx
0x18001e030  xor     edx, edx; Val
0x18001e032  mov     [rbp+57h+pbInput], rax
0x18001e036  lea     r8d, [rdx+20h]; Size
0x18001e03a  call    memset_0
0x18001e03f  xor     r15d, r15d
0x18001e042  lea     ecx, [r15+1]
0x18001e046  test    rdi, rdi
0x18001e049  jz      short loc_18001E05F
0x18001e04b  cmp     [rdi+40h], rbx
0x18001e04f  mov     rax, rdi
0x18001e052  cmovnz  rax, [rdi+40h]
0x18001e057  test    byte ptr [rax+24h], 2
0x18001e05b  cmovnz  r15d, ecx
0x18001e05f  test    r15d, r15d
0x18001e062  jz      short loc_18001E0CD
0x18001e064  mov     r8, [rsi+28h]
0x18001e068  lea     rcx, [rsi+48h]; pbInput
0x18001e06c  mov     edx, [rsi+30h]; cbInput
0x18001e06f  add     r8, 0Ch; pbOutput
0x18001e073  call    GenerateHashFromBuffer
0x18001e078  test    eax, eax
0x18001e07a  jnz     short loc_18001E0CD
0x18001e07c  call    cs:__imp_GetLastError
0x18001e083  nop     dword ptr [rax+rax+00h]
0x18001e088  mov     ecx, eax
0x18001e08a  mov     edi, 80070000h
0x18001e08f  movzx   eax, ax
0x18001e092  or      eax, edi
0x18001e094  test    ecx, ecx
0x18001e096  cmovle  eax, ecx
0x18001e099  test    eax, eax
0x18001e09b  jns     short loc_18001E0B5
0x18001e09d  call    cs:__imp_GetLastError
0x18001e0a4  nop     dword ptr [rax+rax+00h]
0x18001e0a9  movzx   ebx, ax
0x18001e0ac  or      ebx, edi
0x18001e0ae  test    eax, eax
0x18001e0b0  cmovle  ebx, eax
0x18001e0b3  jmp     short loc_18001E0BA
0x18001e0b5  mov     ebx, 80004005h
0x18001e0ba  test    ebx, ebx
0x18001e0bc  jns     loc_18001E3CC
0x18001e0c2  mov     r8d, 315h
0x18001e0c8  jmp     loc_18001E3BD
0x18001e0cd  test    r14, r14
0x18001e0d0  jnz     short loc_18001E144
0x18001e0d2  mov     edx, [r13+1Ch]
0x18001e0d6  mov     ecx, [r13+18h]
0x18001e0da  call    InitCompressionContext
0x18001e0df  mov     r14, rax
0x18001e0e2  test    rax, rax
0x18001e0e5  jnz     short loc_18001E138
0x18001e0e7  call    cs:__imp_GetLastError
0x18001e0ee  nop     dword ptr [rax+rax+00h]
0x18001e0f3  mov     ecx, eax
0x18001e0f5  mov     edi, 80070000h
0x18001e0fa  movzx   eax, ax
0x18001e0fd  or      eax, edi
0x18001e0ff  test    ecx, ecx
0x18001e101  cmovle  eax, ecx
0x18001e104  test    eax, eax
0x18001e106  jns     short loc_18001E120
0x18001e108  call    cs:__imp_GetLastError
0x18001e10f  nop     dword ptr [rax+rax+00h]
0x18001e114  movzx   ebx, ax
0x18001e117  or      ebx, edi
0x18001e119  test    eax, eax
0x18001e11b  cmovle  ebx, eax
0x18001e11e  jmp     short loc_18001E125
0x18001e120  mov     ebx, 80004005h
0x18001e125  test    ebx, ebx
0x18001e127  jns     loc_18001E3CC
0x18001e12d  mov     r8d, 321h
0x18001e133  jmp     loc_18001E3BD
0x18001e138  test    rdi, rdi
0x18001e13b  jz      short loc_18001E144
0x18001e13d  mov     [rdi+120h], rax
0x18001e144  mov     r8d, [rsi+30h]
0x18001e148  lea     rax, [rbp+57h+cbInput]
0x18001e14c  mov     r9, [rsi+40h]
0x18001e150  lea     r12, [rsi+48h]
0x18001e154  mov     [rsp+0C0h+var_98], rax
0x18001e159  mov     rdx, r12
0x18001e15c  mov     rax, [r14+10h]
0x18001e160  mov     rcx, r14
0x18001e163  mov     [rsp+0C0h+var_A0], r8d
0x18001e168  call    cs:__guard_dispatch_icall_fptr
0x18001e16e  mov     edi, 80070000h
0x18001e173  mov     r14d, 80004005h
0x18001e179  test    eax, eax
0x18001e17b  jnz     short loc_18001E1DD
0x18001e17d  call    cs:__imp_GetLastError
0x18001e184  nop     dword ptr [rax+rax+00h]
0x18001e189  mov     ecx, eax
0x18001e18b  movzx   eax, ax
0x18001e18e  or      eax, edi
0x18001e190  test    ecx, ecx
0x18001e192  cmovle  eax, ecx
0x18001e195  test    eax, eax
0x18001e197  jns     short loc_18001E1B1
0x18001e199  call    cs:__imp_GetLastError
0x18001e1a0  nop     dword ptr [rax+rax+00h]
0x18001e1a5  movzx   ebx, ax
0x18001e1a8  or      ebx, edi
0x18001e1aa  test    eax, eax
0x18001e1ac  cmovle  ebx, eax
0x18001e1af  jmp     short loc_18001E1B4
0x18001e1b1  mov     ebx, r14d
0x18001e1b4  cmp     ebx, 8007006Fh
0x18001e1ba  jnz     short loc_18001E1CE
0x18001e1bc  mov     eax, [rsi+30h]
0x18001e1bf  xor     ebx, ebx
0x18001e1c1  mov     r13, r12
0x18001e1c4  mov     [rbp+57h+cbInput], eax
0x18001e1c7  mov     edx, eax
0x18001e1c9  jmp     loc_18001E352
0x18001e1ce  test    ebx, ebx
0x18001e1d0  jns     short loc_18001E1DD
0x18001e1d2  mov     r8d, 33Ah
0x18001e1d8  jmp     loc_18001E3BD
0x18001e1dd  mov     eax, [rsi+30h]
0x18001e1e0  mov     edx, [rbp+57h+cbInput]
0x18001e1e3  cmp     edx, eax
0x18001e1e5  jz      short loc_18001E1C1
0x18001e1e7  test    r15d, r15d
0x18001e1ea  jz      loc_18001E34E
0x18001e1f0  mov     edx, [r13+1Ch]
0x18001e1f4  mov     ecx, [r13+18h]
0x18001e1f8  and     [rbp+57h+var_7C], 0
0x18001e1fc  call    InitDecompressionContext
0x18001e201  mov     r13, [rbp+57h+pbInput]
0x18001e205  mov     r15, rax
0x18001e208  test    rax, rax
0x18001e20b  jz      short loc_18001E24B
0x18001e20d  mov     r8d, [rbp+57h+cbInput]
0x18001e211  lea     rax, [rbp+57h+var_7C]
0x18001e215  mov     [rsp+0C0h+var_98], rax
0x18001e21a  mov     r9, r12
0x18001e21d  mov     eax, [rsi+30h]
0x18001e220  mov     rdx, r13
0x18001e223  mov     [rsp+0C0h+var_A0], eax
0x18001e227  mov     rcx, r15
0x18001e22a  mov     rax, [r15+10h]
0x18001e22e  call    cs:__guard_dispatch_icall_fptr
0x18001e234  test    eax, eax
0x18001e236  jz      short loc_18001E24B
0x18001e238  mov     edx, [rsi+30h]; cbInput
0x18001e23b  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x18001e23f  mov     rcx, r12; pbInput
0x18001e242  call    GenerateHashFromBuffer
0x18001e247  test    eax, eax
0x18001e249  jnz     short loc_18001E29B
0x18001e24b  call    cs:__imp_GetLastError
0x18001e252  nop     dword ptr [rax+rax+00h]
0x18001e257  mov     ecx, eax
0x18001e259  movzx   eax, ax
0x18001e25c  or      eax, edi
0x18001e25e  test    ecx, ecx
0x18001e260  cmovle  eax, ecx
0x18001e263  test    eax, eax
0x18001e265  jns     short loc_18001E27F
0x18001e267  call    cs:__imp_GetLastError
0x18001e26e  nop     dword ptr [rax+rax+00h]
0x18001e273  movzx   ebx, ax
0x18001e276  or      ebx, edi
0x18001e278  test    eax, eax
0x18001e27a  cmovle  ebx, eax
0x18001e27d  jmp     short loc_18001E282
0x18001e27f  mov     ebx, r14d
0x18001e282  test    ebx, ebx
0x18001e284  jns     short loc_18001E2A3
0x18001e286  mov     r9d, ebx
0x18001e289  lea     rcx, aCompresschunk; "CompressChunk"
0x18001e290  mov     r8d, 362h
0x18001e296  call    UtilReportError
0x18001e29b  test    ebx, ebx
0x18001e29d  js      loc_18001E334
0x18001e2a3  mov     eax, [rbp+57h+var_7C]
0x18001e2a6  mov     r8, [rsi+28h]
0x18001e2aa  cmp     [rsi+30h], eax
0x18001e2ad  jnz     short loc_18001E2CC
0x18001e2af  mov     rax, [r8+0Ch]
0x18001e2b3  cmp     rax, qword ptr [rbp+57h+pbOutput]
0x18001e2b7  jnz     short loc_18001E2CC
0x18001e2b9  mov     rax, [r8+14h]
0x18001e2bd  cmp     rax, [rbp+57h+var_48]
0x18001e2c1  jnz     short loc_18001E2CC
0x18001e2c3  mov     eax, [r8+1Ch]
0x18001e2c7  cmp     eax, [rbp+57h+var_40]
0x18001e2ca  jz      short loc_18001E2D1
0x18001e2cc  mov     ebx, 570h
0x18001e2d1  mov     edx, [rbp+57h+cbInput]; cbInput
0x18001e2d4  add     r8, 0Ch; pbOutput
0x18001e2d8  mov     rcx, r13; pbInput
0x18001e2db  call    GenerateHashFromBuffer
0x18001e2e0  test    eax, eax
0x18001e2e2  jnz     short loc_18001E334
0x18001e2e4  call    cs:__imp_GetLastError
0x18001e2eb  nop     dword ptr [rax+rax+00h]
0x18001e2f0  mov     ecx, eax
0x18001e2f2  movzx   eax, ax
0x18001e2f5  or      eax, edi
0x18001e2f7  test    ecx, ecx
0x18001e2f9  cmovle  eax, ecx
0x18001e2fc  test    eax, eax
0x18001e2fe  jns     short loc_18001E318
0x18001e300  call    cs:__imp_GetLastError
0x18001e307  nop     dword ptr [rax+rax+00h]
0x18001e30c  movzx   ebx, ax
0x18001e30f  or      ebx, edi
0x18001e311  test    eax, eax
0x18001e313  cmovle  ebx, eax
0x18001e316  jmp     short loc_18001E31B
0x18001e318  mov     ebx, r14d
0x18001e31b  test    ebx, ebx
0x18001e31d  jns     short loc_18001E334
0x18001e31f  mov     r9d, ebx
0x18001e322  lea     rcx, aCompresschunk; "CompressChunk"
0x18001e329  mov     r8d, 377h
0x18001e32f  call    UtilReportError
0x18001e334  test    r15, r15
0x18001e337  jz      short loc_18001E341
0x18001e339  mov     rcx, r15; lpMem
0x18001e33c  call    FreeCompressionContext
0x18001e341  test    ebx, ebx
0x18001e343  js      loc_18001E3CC
0x18001e349  mov     edx, [rbp+57h+cbInput]
0x18001e34c  jmp     short loc_18001E352
0x18001e34e  mov     r13, [rbp+57h+pbInput]
0x18001e352  mov     rax, [rsi+28h]
0x18001e356  lea     r9, [rbp+57h+var_70]
0x18001e35a  mov     [rsp+0C0h+var_A0], 1; DWORD
0x18001e362  mov     [rax+8], edx
0x18001e365  mov     rdx, r13
0x18001e368  mov     rax, [rsi+28h]
0x18001e36c  mov     r8d, [rbp+57h+cbInput]
0x18001e370  mov     rcx, [rax]; hFile
0x18001e373  call    ReadWriteData
0x18001e378  test    eax, eax
0x18001e37a  jnz     short loc_18001E3CC
0x18001e37c  call    cs:__imp_GetLastError
0x18001e383  nop     dword ptr [rax+rax+00h]
0x18001e388  mov     ecx, eax
0x18001e38a  movzx   eax, ax
0x18001e38d  or      eax, edi
0x18001e38f  test    ecx, ecx
0x18001e391  cmovle  eax, ecx
0x18001e394  test    eax, eax
0x18001e396  jns     short loc_18001E3B0
0x18001e398  call    cs:__imp_GetLastError
0x18001e39f  nop     dword ptr [rax+rax+00h]
0x18001e3a4  movzx   ebx, ax
0x18001e3a7  or      ebx, edi
0x18001e3a9  test    eax, eax
0x18001e3ab  cmovle  ebx, eax
0x18001e3ae  jmp     short loc_18001E3B3
0x18001e3b0  mov     ebx, r14d
0x18001e3b3  test    ebx, ebx
0x18001e3b5  jns     short loc_18001E3CC
0x18001e3b7  mov     r8d, 38Dh
0x18001e3bd  mov     r9d, ebx
0x18001e3c0  lea     rcx, aCompresschunk; "CompressChunk"
0x18001e3c7  call    UtilReportError
0x18001e3cc  mov     eax, ebx
0x18001e3ce  mov     rcx, [rbp+57h+var_38]
0x18001e3d2  xor     rcx, rsp; StackCookie
0x18001e3d5  call    __security_check_cookie
0x18001e3da  mov     rbx, [rsp+0C0h+arg_10]
0x18001e3e2  add     rsp, 90h
0x18001e3e9  pop     r15
0x18001e3eb  pop     r14
0x18001e3ed  pop     r13
0x18001e3ef  pop     r12
0x18001e3f1  pop     rdi
0x18001e3f2  pop     rsi
0x18001e3f3  pop     rbp
  ... truncated ...
```

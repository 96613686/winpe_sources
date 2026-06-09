# SxspAddPrivateProbingPathParts(CGenericBaseStringBuffer<CUnicodeCharTraits> const &,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,CFusionArray<CGenericStringBuffer<260,CUnicodeCharTraits>,CGenericStringBuffer<260,CUnicodeCharTraits>,0,32> *)

- ea: `0x180059f28`
- end: `0x18005a2e6`
- name: `?SxspAddPrivateProbingPathParts@@YAHAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@0PEAV?$CFusionArray@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@V1@$0A@$0CA@@@@Z`
- size: `958`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180065f30`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180014260`
- `0x18001c270`
- `0x18001d6f0`
- `0x180029380`
- `0x180032350`
- `0x1800324c4`
- `0x180033b50`
- `0x180059f28`
- `0x1800605d4`
- `0x180060af8`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a006`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a02b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a059`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a07c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a098`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a167`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a1b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a1e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a20d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a237`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a27a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a298`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a006`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a02b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a059`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a07c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a098`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a167`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a1b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a1e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a20d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a237`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a27a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a298`

## pseudocode

```c
__int64 __fastcall SxspAddPrivateProbingPathParts(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rcx
  const unsigned __int16 *v7; // rbx
  const unsigned __int16 *v8; // rdi
  char **v9; // rcx
  _BYTE *v10; // rcx
  char **v11; // rcx
  unsigned int v12; // ebx
  int v14; // [rsp+20h] [rbp-E0h] BYREF
  int v15; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v16; // [rsp+30h] [rbp-D0h]
  __int64 *v17; // [rsp+38h] [rbp-C8h]
  __int64 v18; // [rsp+40h] [rbp-C0h]
  int v19; // [rsp+48h] [rbp-B8h]
  unsigned int *v20; // [rsp+50h] [rbp-B0h]
  _BYTE v21[16]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR v22; // [rsp+70h] [rbp-90h]
  _BYTE v23[16]; // [rsp+290h] [rbp+190h] BYREF
  LPCWSTR lpFileName; // [rsp+2A0h] [rbp+1A0h]

  v15 = 1;
  v17 = &qword_180072E40;
  v18 = 544438355;
  v20 = (unsigned int *)&v14;
  v14 = 0;
  v16 = 0;
  v19 = 4776;
  CFrame::BaseEnter((CFrame *)&v15);
  v6 = *(_QWORD *)(a2 + 32);
  if ( !v6 || *(_WORD *)(*(_QWORD *)(a2 + 16) + 2 * v6 - 2) != 92 )
    goto LABEL_36;
  v7 = *(const unsigned __int16 **)(a1 + 16);
  v8 = v7;
  while ( *v7 )
  {
    if ( *v7 == 59 )
    {
      if ( !SxspValidatePrivateProbingPathSegment(v8, v7) )
        goto LABEL_36;
      CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v23);
      CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v21);
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(v23, a2) )
      {
        v9 = off_180074BF0;
LABEL_18:
        *v20 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v9);
        CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(v21);
        v10 = v23;
LABEL_19:
        CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(v10);
        goto LABEL_37;
      }
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(v23, v8, v7 - v8) )
      {
        v9 = off_180074BD0;
        goto LABEL_18;
      }
      SetLastError(0);
      if ( !(unsigned int)SxspGetFullPathName(lpFileName, (__int64)v21) )
      {
        v9 = off_180074BB0;
        goto LABEL_18;
      }
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator((__int64)v21) )
      {
        v9 = off_180074B90;
        goto LABEL_18;
      }
      SetLastError(0);
      if ( !(unsigned int)CFusionArray<CGenericStringBuffer<260,CUnicodeCharTraits>,CGenericStringBuffer<260,CUnicodeCharTraits>,0,32>::Win32Append(
                            a3,
                            v21) )
      {
        v9 = off_180074B70;
        goto LABEL_18;
      }
      v8 = ++v7;
      CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(v21);
      CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(v23);
    }
    else
    {
      ++v7;
    }
  }
  if ( v8 != v7 )
  {
    if ( SxspValidatePrivateProbingPathSegment(v8, v7) )
    {
      CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v21);
      CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v23);
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(v21, a2) )
      {
        v11 = off_180074B50;
LABEL_25:
        *v20 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v11);
        CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(v23);
        v10 = v21;
        goto LABEL_19;
      }
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(v21, v8, v7 - v8) )
      {
        v11 = off_180074B30;
        goto LABEL_25;
      }
      SetLastError(0);
      if ( !(unsigned int)SxspGetFullPathName(v22, (__int64)v23) )
      {
        v11 = off_180074B10;
        goto LABEL_25;
      }
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator((__int64)v23) )
      {
        v11 = off_180074AF0;
        goto LABEL_25;
      }
      SetLastError(0);
      if ( !(unsigned int)CFusionArray<CGenericStringBuffer<260,CUnicodeCharTraits>,CGenericStringBuffer<260,CUnicodeCharTraits>,0,32>::Win32Append(
                            a3,
                            v23) )
      {
        v11 = off_180074AD0;
        goto LABEL_25;
      }
      CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(v23);
      CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(v21);
      goto LABEL_35;
    }
LABEL_36:
    SetLastError(0x54Fu);
    *v20 = 0;
    goto LABEL_37;
  }
LABEL_35:
  SetLastError(0);
  *v20 = 1;
LABEL_37:
  v12 = *v20;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v15);
  return v12;
}

```

## disassembly

```asm
0x180059f28  mov     [rsp-8+arg_18], rbx
0x180059f2d  push    rbp
0x180059f2e  push    rsi
0x180059f2f  push    rdi
0x180059f30  push    r14
0x180059f32  push    r15
0x180059f34  lea     rbp, [rsp-3D0h]
0x180059f3c  sub     rsp, 4D0h
0x180059f43  mov     rax, cs:__security_cookie
0x180059f4a  xor     rax, rsp
0x180059f4d  mov     [rbp+3F0h+var_30], rax
0x180059f54  lea     rax, qword_180072E40
0x180059f5b  mov     [rsp+4F0h+var_4C8], 1
0x180059f63  mov     [rsp+4F0h+var_4B8], rax
0x180059f68  mov     rbx, rcx
0x180059f6b  lea     rax, [rsp+4F0h+var_4D0]
0x180059f70  mov     [rsp+4F0h+var_4B0], 20737853h
0x180059f79  xor     r15d, r15d
0x180059f7c  mov     [rsp+4F0h+var_4A0], rax
0x180059f81  lea     rcx, [rsp+4F0h+var_4C8]; this
0x180059f86  mov     [rsp+4F0h+var_4D0], r15d
0x180059f8b  mov     r14, r8
0x180059f8e  mov     [rsp+4F0h+var_4C0], r15
0x180059f93  mov     rsi, rdx
0x180059f96  mov     [rsp+4F0h+var_4A8], 12A8h
0x180059f9e  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180059fa3  mov     rcx, [rsi+20h]
0x180059fa7  test    rcx, rcx
0x180059faa  jz      loc_18005A293
0x180059fb0  mov     rax, [rsi+10h]
0x180059fb4  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180059fba  jnz     loc_18005A293
0x180059fc0  mov     rbx, [rbx+10h]
0x180059fc4  mov     rdi, rbx
0x180059fc7  cmp     [rbx], r15w
0x180059fcb  jz      loc_18005A133
0x180059fd1  cmp     word ptr [rbx], 3Bh ; ';'
0x180059fd5  jnz     loc_18005A0D7
0x180059fdb  mov     rdx, rbx; unsigned __int16 *
0x180059fde  mov     rcx, rdi; unsigned __int16 *
0x180059fe1  call    ?SxspValidatePrivateProbingPathSegment@@YA_NPEBG0@Z; SxspValidatePrivateProbingPathSegment(ushort const *,ushort const *)
0x180059fe6  test    al, al
0x180059fe8  jz      loc_18005A293
0x180059fee  lea     rcx, [rbp+3F0h+var_260]; void *
0x180059ff5  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x180059ffa  lea     rcx, [rsp+4F0h+var_490]; void *
0x180059fff  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18005a004  xor     ecx, ecx; dwErrCode
0x18005a006  call    cs:__imp_SetLastError
0x18005a00d  nop     dword ptr [rax+rax+00h]
0x18005a012  mov     rdx, rsi
0x18005a015  lea     rcx, [rbp+3F0h+var_260]
0x18005a01c  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHAEBV1@@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(CGenericBaseStringBuffer<CUnicodeCharTraits> const &)
0x18005a021  test    eax, eax
0x18005a023  jz      loc_18005A12A
0x18005a029  xor     ecx, ecx; dwErrCode
0x18005a02b  call    cs:__imp_SetLastError
0x18005a032  nop     dword ptr [rax+rax+00h]
0x18005a037  mov     r8, rbx
0x18005a03a  lea     rcx, [rbp+3F0h+var_260]
0x18005a041  sub     r8, rdi
0x18005a044  mov     rdx, rdi
0x18005a047  sar     r8, 1
0x18005a04a  call    ?Win32Append@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(ushort const *,unsigned __int64)
0x18005a04f  test    eax, eax
0x18005a051  jz      loc_18005A0FB
0x18005a057  xor     ecx, ecx; dwErrCode
0x18005a059  call    cs:__imp_SetLastError
0x18005a060  nop     dword ptr [rax+rax+00h]
0x18005a065  mov     rcx, [rbp+3F0h+lpFileName]; lpFileName
0x18005a06c  lea     rdx, [rsp+4F0h+var_490]
0x18005a071  call    ?SxspGetFullPathName@@YAHPEBGAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@PEAV1@@Z; SxspGetFullPathName(ushort const *,CGenericBaseStringBuffer<CUnicodeCharTraits> &,CGenericBaseStringBuffer<CUnicodeCharTraits> *)
0x18005a076  test    eax, eax
0x18005a078  jz      short loc_18005A0F2
0x18005a07a  xor     ecx, ecx; dwErrCode
0x18005a07c  call    cs:__imp_SetLastError
0x18005a083  nop     dword ptr [rax+rax+00h]
0x18005a088  lea     rcx, [rsp+4F0h+var_490]
0x18005a08d  call    ?Win32EnsureTrailingPathSeparator@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator(void)
0x18005a092  test    eax, eax
0x18005a094  jz      short loc_18005A0E9
0x18005a096  xor     ecx, ecx; dwErrCode
0x18005a098  call    cs:__imp_SetLastError
0x18005a09f  nop     dword ptr [rax+rax+00h]
0x18005a0a4  lea     rdx, [rsp+4F0h+var_490]
0x18005a0a9  mov     rcx, r14
0x18005a0ac  call    ?Win32Append@?$CFusionArray@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@V1@$0A@$0CA@@@QEAAHAEBV?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@W4AppendMode@1@@Z; CFusionArray<CGenericStringBuffer<260,CUnicodeCharTraits>,CGenericStringBuffer<260,CUnicodeCharTraits>,0,32>::Win32Append(CGenericStringBuffer<260,CUnicodeCharTraits> const &,CFusionArray<CGenericStringBuffer<260,CUnicodeCharTraits>,CGenericStringBuffer<260,CUnicodeCharTraits>,0,32>::AppendMode)
0x18005a0b1  test    eax, eax
0x18005a0b3  jz      short loc_18005A0E0
0x18005a0b5  add     rbx, 2
0x18005a0b9  lea     rcx, [rsp+4F0h+var_490]; void *
0x18005a0be  mov     rdi, rbx
0x18005a0c1  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18005a0c6  lea     rcx, [rbp+3F0h+var_260]; void *
0x18005a0cd  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18005a0d2  jmp     loc_180059FC7
0x18005a0d7  add     rbx, 2
0x18005a0db  jmp     loc_180059FC7
0x18005a0e0  lea     rcx, off_180074B70; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005a0e7  jmp     short loc_18005A102
0x18005a0e9  lea     rcx, off_180074B90; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005a0f0  jmp     short loc_18005A102
0x18005a0f2  lea     rcx, off_180074BB0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005a0f9  jmp     short loc_18005A102
0x18005a0fb  lea     rcx, off_180074BD0; struct _CALL_SITE_INFO *
0x18005a102  mov     rax, [rsp+4F0h+var_4A0]
0x18005a107  mov     [rax], r15d
0x18005a10a  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18005a10f  lea     rcx, [rsp+4F0h+var_490]; void *
0x18005a114  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18005a119  lea     rcx, [rbp+3F0h+var_260]; void *
0x18005a120  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18005a125  jmp     loc_18005A2AC
0x18005a12a  lea     rcx, off_180074BF0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005a131  jmp     short loc_18005A102
0x18005a133  cmp     rdi, rbx
0x18005a136  jz      loc_18005A278
0x18005a13c  mov     rdx, rbx; unsigned __int16 *
0x18005a13f  mov     rcx, rdi; unsigned __int16 *
0x18005a142  call    ?SxspValidatePrivateProbingPathSegment@@YA_NPEBG0@Z; SxspValidatePrivateProbingPathSegment(ushort const *,ushort const *)
0x18005a147  test    al, al
0x18005a149  jz      loc_18005A293
0x18005a14f  lea     rcx, [rsp+4F0h+var_490]; void *
0x18005a154  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18005a159  lea     rcx, [rbp+3F0h+var_260]; void *
0x18005a160  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18005a165  xor     ecx, ecx; dwErrCode
0x18005a167  call    cs:__imp_SetLastError
0x18005a16e  nop     dword ptr [rax+rax+00h]
0x18005a173  mov     rdx, rsi
0x18005a176  lea     rcx, [rsp+4F0h+var_490]
0x18005a17b  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHAEBV1@@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(CGenericBaseStringBuffer<CUnicodeCharTraits> const &)
0x18005a180  test    eax, eax
0x18005a182  jnz     short loc_18005A1AE
0x18005a184  lea     rcx, off_180074B50; struct _CALL_SITE_INFO *
0x18005a18b  mov     rax, [rsp+4F0h+var_4A0]
0x18005a190  mov     [rax], r15d
0x18005a193  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18005a198  lea     rcx, [rbp+3F0h+var_260]; void *
0x18005a19f  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18005a1a4  lea     rcx, [rsp+4F0h+var_490]
0x18005a1a9  jmp     loc_18005A120
0x18005a1ae  xor     ecx, ecx; dwErrCode
0x18005a1b0  call    cs:__imp_SetLastError
0x18005a1b7  nop     dword ptr [rax+rax+00h]
0x18005a1bc  sub     rbx, rdi
0x18005a1bf  lea     rcx, [rsp+4F0h+var_490]
0x18005a1c4  sar     rbx, 1
0x18005a1c7  mov     rdx, rdi
0x18005a1ca  mov     r8, rbx
0x18005a1cd  call    ?Win32Append@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(ushort const *,unsigned __int64)
0x18005a1d2  test    eax, eax
0x18005a1d4  jnz     short loc_18005A1DF
0x18005a1d6  lea     rcx, off_180074B30; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005a1dd  jmp     short loc_18005A18B
0x18005a1df  xor     ecx, ecx; dwErrCode
0x18005a1e1  call    cs:__imp_SetLastError
0x18005a1e8  nop     dword ptr [rax+rax+00h]
0x18005a1ed  mov     rcx, [rsp+4F0h+var_480]; lpFileName
0x18005a1f2  lea     rdx, [rbp+3F0h+var_260]
0x18005a1f9  call    ?SxspGetFullPathName@@YAHPEBGAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@PEAV1@@Z; SxspGetFullPathName(ushort const *,CGenericBaseStringBuffer<CUnicodeCharTraits> &,CGenericBaseStringBuffer<CUnicodeCharTraits> *)
0x18005a1fe  test    eax, eax
0x18005a200  jnz     short loc_18005A20B
0x18005a202  lea     rcx, off_180074B10; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005a209  jmp     short loc_18005A18B
0x18005a20b  xor     ecx, ecx; dwErrCode
0x18005a20d  call    cs:__imp_SetLastError
0x18005a214  nop     dword ptr [rax+rax+00h]
0x18005a219  lea     rcx, [rbp+3F0h+var_260]
0x18005a220  call    ?Win32EnsureTrailingPathSeparator@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator(void)
0x18005a225  test    eax, eax
0x18005a227  jnz     short loc_18005A235
0x18005a229  lea     rcx, off_180074AF0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005a230  jmp     loc_18005A18B
0x18005a235  xor     ecx, ecx; dwErrCode
0x18005a237  call    cs:__imp_SetLastError
0x18005a23e  nop     dword ptr [rax+rax+00h]
0x18005a243  lea     rdx, [rbp+3F0h+var_260]
0x18005a24a  mov     rcx, r14
0x18005a24d  call    ?Win32Append@?$CFusionArray@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@V1@$0A@$0CA@@@QEAAHAEBV?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@W4AppendMode@1@@Z; CFusionArray<CGenericStringBuffer<260,CUnicodeCharTraits>,CGenericStringBuffer<260,CUnicodeCharTraits>,0,32>::Win32Append(CGenericStringBuffer<260,CUnicodeCharTraits> const &,CFusionArray<CGenericStringBuffer<260,CUnicodeCharTraits>,CGenericStringBuffer<260,CUnicodeCharTraits>,0,32>::AppendMode)
0x18005a252  test    eax, eax
0x18005a254  jnz     short loc_18005A262
0x18005a256  lea     rcx, off_180074AD0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005a25d  jmp     loc_18005A18B
0x18005a262  lea     rcx, [rbp+3F0h+var_260]; void *
0x18005a269  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18005a26e  lea     rcx, [rsp+4F0h+var_490]; void *
0x18005a273  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18005a278  xor     ecx, ecx; dwErrCode
0x18005a27a  call    cs:__imp_SetLastError
0x18005a281  nop     dword ptr [rax+rax+00h]
0x18005a286  mov     rax, [rsp+4F0h+var_4A0]
0x18005a28b  mov     dword ptr [rax], 1
0x18005a291  jmp     short loc_18005A2AC
0x18005a293  mov     ecx, 54Fh; dwErrCode
0x18005a298  call    cs:__imp_SetLastError
0x18005a29f  nop     dword ptr [rax+rax+00h]
0x18005a2a4  mov     rax, [rsp+4F0h+var_4A0]
0x18005a2a9  mov     [rax], r15d
0x18005a2ac  mov     rax, [rsp+4F0h+var_4A0]
0x18005a2b1  lea     rcx, [rsp+4F0h+var_4C8]; this
0x18005a2b6  mov     ebx, [rax]
0x18005a2b8  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18005a2bd  mov     eax, ebx
0x18005a2bf  mov     rcx, [rbp+3F0h+var_30]
0x18005a2c6  xor     rcx, rsp; StackCookie
0x18005a2c9  call    __security_check_cookie
0x18005a2ce  mov     rbx, [rsp+4F0h+arg_18]
0x18005a2d6  add     rsp, 4D0h
0x18005a2dd  pop     r15
0x18005a2df  pop     r14
0x18005a2e1  pop     rdi
0x18005a2e2  pop     rsi
0x18005a2e3  pop     rbp
0x18005a2e4  retn
```

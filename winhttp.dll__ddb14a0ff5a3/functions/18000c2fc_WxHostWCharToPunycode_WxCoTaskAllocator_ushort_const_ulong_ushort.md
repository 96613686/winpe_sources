# WxHostWCharToPunycode<WxCoTaskAllocator>(ushort const *,ulong,ushort * *)

- ea: `0x18000c2fc`
- end: `0x18000c4c8`
- name: `??$WxHostWCharToPunycode@VWxCoTaskAllocator@@@@YAJPEBGKPEAPEAG@Z`
- size: `460`
- prototype: `__int64 __fastcall(LPCWSTR lpUnicodeCharStr, int cchUnicodeChar, LPWSTR *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c17c`
- `0x180067010`

## callees

- `0x18000bfd0`
- `0x18000c2fc`
- `0x1800566d0`
- `0x18007a8fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4a1`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x18000c377`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x18000c471`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x18000c493`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x18000c377`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x18000c471`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x18000c493`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c34e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c34e`

## pseudocode

```c
__int64 __fastcall WxHostWCharToPunycode<WxCoTaskAllocator>(LPCWSTR lpUnicodeCharStr, int cchUnicodeChar, LPWSTR *a3)
{
  __int64 v4; // rsi
  int cchASCIIChar; // r15d
  LPWSTR v7; // rbx
  WCHAR *v8; // rax
  unsigned int v9; // edi
  unsigned int v10; // eax
  int v12; // eax
  int v13; // eax
  DWORD LastError; // eax
  int v15; // r15d
  LPWSTR lpASCIICharStr; // [rsp+30h] [rbp-10h] BYREF
  int v17; // [rsp+3Ch] [rbp-4h]

  v17 = 0;
  LODWORD(v4) = cchUnicodeChar;
  if ( cchUnicodeChar == -1 )
  {
    v4 = -1;
    do
      ++v4;
    while ( lpUnicodeCharStr[v4] );
  }
  v17 = 0;
  cchASCIIChar = 2 * v4;
  v7 = 0;
  lpASCIICharStr = 0;
  if ( (unsigned int)(2 * v4) < 0x100 )
    cchASCIIChar = 256;
  v8 = (WCHAR *)CoTaskMemAlloc((unsigned int)(2 * cchASCIIChar + 2));
  if ( v8 )
  {
    v7 = v8;
    lpASCIICharStr = v8;
    v9 = 0;
    v10 = IdnToAscii(0, lpUnicodeCharStr, v4, v8, cchASCIIChar);
    if ( v10 )
    {
LABEL_6:
      v7[v10] = 0;
      *a3 = v7;
      v7 = 0;
      lpASCIICharStr = 0;
      goto LABEL_7;
    }
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      v15 = IdnToAscii(0, lpUnicodeCharStr, v4, 0, 0);
      if ( v15 )
      {
        WxCoTaskAllocator::Free((void **)&lpASCIICharStr);
        v12 = WxAlloc<unsigned short,WxCoTaskAllocator>((unsigned int)(2 * v15 + 2), &lpASCIICharStr);
        v7 = lpASCIICharStr;
        v9 = v12;
        if ( v12 < 0 )
        {
          v17 = 659;
          goto LABEL_7;
        }
        v10 = IdnToAscii(0, lpUnicodeCharStr, v4, lpASCIICharStr, v15);
        if ( v10 )
          goto LABEL_6;
      }
      LastError = GetLastError();
    }
    if ( LastError == 8 )
    {
      v9 = -2147024882;
      v17 = 672;
    }
    else
    {
      if ( v7 )
        WxCoTaskAllocator::Free((void **)&lpASCIICharStr);
      v13 = WxNewStringWCch<WxCoTaskAllocator>(lpUnicodeCharStr, (unsigned int)v4, &lpASCIICharStr);
      v7 = lpASCIICharStr;
      v9 = v13;
      if ( v13 >= 0 )
      {
        v10 = v4;
        goto LABEL_6;
      }
      v17 = 679;
    }
  }
  else
  {
    v9 = -2147024882;
    v17 = 636;
  }
LABEL_7:
  if ( v7 )
    WxCoTaskAllocator::Free((void **)&lpASCIICharStr);
  return v9;
}

```

## disassembly

```asm
0x18000c2fc  mov     [rsp-38h+arg_18], rbx
0x18000c301  push    rbp
0x18000c302  push    rsi
0x18000c303  push    rdi
0x18000c304  push    r12
0x18000c306  push    r13
0x18000c308  push    r14
0x18000c30a  push    r15
0x18000c30c  mov     rbp, rsp
0x18000c30f  sub     rsp, 40h
0x18000c313  xor     r13d, r13d
0x18000c316  mov     r12, r8
0x18000c319  mov     [rbp+var_4], r13d
0x18000c31d  mov     esi, edx
0x18000c31f  mov     r14, rcx
0x18000c322  cmp     edx, 0FFFFFFFFh
0x18000c325  jz      loc_18000C42B
0x18000c32b  mov     eax, 100h
0x18000c330  mov     [rbp+var_4], r13d
0x18000c334  lea     r15d, [rsi+rsi]
0x18000c338  mov     rbx, r13
0x18000c33b  cmp     r15d, eax
0x18000c33e  mov     [rbp+lpASCIICharStr], rbx
0x18000c342  cmovb   r15d, eax
0x18000c346  lea     ecx, ds:2[r15*2]; cb
0x18000c34e  call    cs:__imp_CoTaskMemAlloc
0x18000c354  test    rax, rax
0x18000c357  jz      loc_18000C43E
0x18000c35d  mov     rbx, rax
0x18000c360  mov     [rbp+lpASCIICharStr], rax
0x18000c364  mov     r9, rax; lpASCIICharStr
0x18000c367  mov     [rsp+40h+cchASCIIChar], r15d; cchASCIIChar
0x18000c36c  mov     r8d, esi; cchUnicodeChar
0x18000c36f  mov     rdx, r14; lpUnicodeCharStr
0x18000c372  xor     ecx, ecx; dwFlags
0x18000c374  mov     edi, r13d
0x18000c377  call    cs:__imp_IdnToAscii
0x18000c37d  test    eax, eax
0x18000c37f  jz      loc_18000C456
0x18000c385  mov     edx, eax
0x18000c387  mov     [rbx+rdx*2], r13w
0x18000c38c  mov     [r12], rbx
0x18000c390  mov     rbx, r13
0x18000c393  mov     [rbp+lpASCIICharStr], rbx
0x18000c397  test    rbx, rbx
0x18000c39a  jz      short loc_18000C3A5
0x18000c39c  lea     rcx, [rbp+lpASCIICharStr]; void **
0x18000c3a0  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x18000c3a5  mov     rbx, [rsp+40h+arg_18]
0x18000c3ad  mov     eax, edi
0x18000c3af  add     rsp, 40h
0x18000c3b3  pop     r15
0x18000c3b5  pop     r14
0x18000c3b7  pop     r13
0x18000c3b9  pop     r12
0x18000c3bb  pop     rdi
0x18000c3bc  pop     rsi
0x18000c3bd  pop     rbp
0x18000c3be  retn
0x18000c3bf  test    rbx, rbx
0x18000c3c2  jz      short loc_18000C3CD
0x18000c3c4  lea     rcx, [rbp+lpASCIICharStr]; void **
0x18000c3c8  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x18000c3cd  lea     ecx, ds:2[r15*2]; cb
0x18000c3d5  lea     rdx, [rbp+lpASCIICharStr]
0x18000c3d9  call    ??$WxAlloc@GVWxCoTaskAllocator@@@@YAJKPEAPEAG@Z; WxAlloc<ushort,WxCoTaskAllocator>(ulong,ushort * *)
0x18000c3de  mov     rbx, [rbp+lpASCIICharStr]
0x18000c3e2  mov     edi, eax
0x18000c3e4  test    eax, eax
0x18000c3e6  jns     loc_18000C483
0x18000c3ec  mov     [rbp+var_4], 293h
0x18000c3f3  jmp     short loc_18000C397
0x18000c3f5  test    rbx, rbx
0x18000c3f8  jz      short loc_18000C403
0x18000c3fa  lea     rcx, [rbp+lpASCIICharStr]; void **
0x18000c3fe  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x18000c403  lea     r8, [rbp+lpASCIICharStr]
0x18000c407  mov     edx, esi
0x18000c409  mov     rcx, r14
0x18000c40c  call    ??$WxNewStringWCch@VWxCoTaskAllocator@@@@YAJPEBGKPEAPEAG@Z; WxNewStringWCch<WxCoTaskAllocator>(ushort const *,ulong,ushort * *)
0x18000c411  mov     rbx, [rbp+lpASCIICharStr]
0x18000c415  mov     edi, eax
0x18000c417  test    eax, eax
0x18000c419  jns     loc_18000C4C1
0x18000c41f  mov     [rbp+var_4], 2A7h
0x18000c426  jmp     loc_18000C397
0x18000c42b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000c42f  inc     rsi
0x18000c432  cmp     [rcx+rsi*2], r13w
0x18000c437  jnz     short loc_18000C42F
0x18000c439  jmp     loc_18000C32B
0x18000c43e  mov     [rbp+var_4], 34h ; '4'
0x18000c445  mov     edi, 8007000Eh
0x18000c44a  mov     [rbp+var_4], 27Ch
0x18000c451  jmp     loc_18000C397
0x18000c456  call    cs:__imp_GetLastError
0x18000c45c  cmp     eax, 7Ah ; 'z'
0x18000c45f  jnz     short loc_18000C4A7
0x18000c461  xor     r9d, r9d; lpASCIICharStr
0x18000c464  mov     [rsp+40h+cchASCIIChar], r13d; cchASCIIChar
0x18000c469  mov     r8d, esi; cchUnicodeChar
0x18000c46c  mov     rdx, r14; lpUnicodeCharStr
0x18000c46f  xor     ecx, ecx; dwFlags
0x18000c471  call    cs:__imp_IdnToAscii
0x18000c477  mov     r15d, eax
0x18000c47a  test    eax, eax
0x18000c47c  jz      short loc_18000C4A1
0x18000c47e  jmp     loc_18000C3BF
0x18000c483  mov     r9, rbx; lpASCIICharStr
0x18000c486  mov     [rsp+40h+cchASCIIChar], r15d; cchASCIIChar
0x18000c48b  mov     r8d, esi; cchUnicodeChar
0x18000c48e  mov     rdx, r14; lpUnicodeCharStr
0x18000c491  xor     ecx, ecx; dwFlags
0x18000c493  call    cs:__imp_IdnToAscii
0x18000c499  test    eax, eax
0x18000c49b  jnz     loc_18000C385
0x18000c4a1  call    cs:__imp_GetLastError
0x18000c4a7  cmp     eax, 8
0x18000c4aa  jnz     loc_18000C3F5
0x18000c4b0  mov     edi, 8007000Eh
0x18000c4b5  mov     [rbp+var_4], 2A0h
0x18000c4bc  jmp     loc_18000C397
0x18000c4c1  mov     eax, esi
0x18000c4c3  jmp     loc_18000C385
```

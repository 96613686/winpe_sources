# CTextString::Unicode(void)

- ea: `0x18000e680`
- end: `0x18000e85c`
- name: `?Unicode@CTextString@@IEAAPEBGXZ`
- size: `476`
- prototype: `const unsigned __int16 *__fastcall(CTextString *__hidden this)`
- caller_count: `36`
- callee_count: `4`
- tags: ``

## callers

- `0x180001ab0`
- `0x18000dbf0`
- `0x18000e110`
- `0x18000e980`
- `0x180011880`
- `0x180011b70`
- `0x180012000`
- `0x18001a860`
- `0x18001a9a0`
- `0x18001ad70`
- `0x18001aee0`
- `0x18001b230`
- `0x18001b340`
- `0x18001b500`
- `0x180022f20`
- `0x180024f70`
- `0x180025170`
- `0x180025300`
- `0x180025490`
- `0x180025610`
- `0x1800257b0`
- `0x180025980`
- `0x180025b30`
- `0x180025d30`
- `0x180025fe0`
- `0x1800262f0`
- `0x180026640`
- `0x180026d80`
- `0x1800272a0`
- `0x1800274a0`
- `0x180027630`
- `0x1800277c0`
- `0x180027ad0`
- `0x180027c50`
- `0x180027e50`
- `0x180028790`

## callees

- `0x180003ee0`
- `0x18000e680`
- `0x180012650`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e80d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e80d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e829`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18000e727`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18000e793`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18000e727`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18000e793`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000e748`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000e7b2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000e748`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000e7b2`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
const unsigned __int16 *__fastcall CTextString::Unicode(CTextString *this)
{
  const WCHAR *v2; // rbp
  int v3; // ecx
  unsigned int v4; // edi
  const CHAR *v6; // rsi
  UINT ACP; // eax
  int v8; // eax
  int cchWideChar; // r12d
  unsigned int v10; // edi
  WCHAR *lpWideCharStr; // r13
  const CHAR *v12; // rsi
  UINT v13; // eax
  int v14; // eax
  __int64 v15; // rax
  ulong pExceptionObject; // [rsp+60h] [rbp+8h] BYREF

  v2 = &WideCharStr;
  v3 = *((_DWORD *)this + 2);
  if ( v3 == 1 )
  {
    v4 = *((_DWORD *)this + 14);
    if ( v4 > 1 )
    {
      if ( *((_DWORD *)this + 15) )
        v6 = (const CHAR *)*((_QWORD *)this + 6);
      else
        v6 = (const CHAR *)&WideCharStr;
      ACP = GetACP();
      v8 = MultiByteToWideChar(ACP, 1u, v6, v4 - 1, 0, 0);
      cchWideChar = v8;
      if ( !v8 )
      {
        pExceptionObject = GetLastError();
        throw &pExceptionObject;
      }
      v10 = 2 * v8 + 2;
      CBuffer::Presize((CTextString *)((char *)this + 16), v10, 0);
      *((_DWORD *)this + 8) = v10;
      if ( *((_DWORD *)this + 9) )
        lpWideCharStr = (WCHAR *)*((_QWORD *)this + 3);
      else
        lpWideCharStr = (WCHAR *)&WideCharStr;
      pExceptionObject = *((_DWORD *)this + 14) - 1;
      if ( *((_DWORD *)this + 15) )
        v12 = (const CHAR *)*((_QWORD *)this + 6);
      else
        v12 = (const CHAR *)&WideCharStr;
      v13 = GetACP();
      v14 = MultiByteToWideChar(v13, 1u, v12, pExceptionObject, lpWideCharStr, cchWideChar);
      if ( !v14 )
      {
        pExceptionObject = GetLastError();
        throw &pExceptionObject;
      }
      v15 = (unsigned int)(2 * v14);
      if ( *((_DWORD *)this + 9) <= (unsigned int)v15 )
        WideCharStr = 0;
      else
        *(_WORD *)(*((_QWORD *)this + 3) + v15) = 0;
    }
    else if ( v4 == 1 )
    {
      CBuffer::Set((CTextString *)((char *)this + 16), (const unsigned __int8 *const)&WideCharStr, 2u);
    }
    else
    {
      *((_DWORD *)this + 8) = 0;
    }
    *((_DWORD *)this + 2) = 3;
  }
  else
  {
    if ( !v3 )
    {
      pExceptionObject = 1359;
      throw &pExceptionObject;
    }
    if ( (unsigned int)(v3 - 2) >= 2 )
    {
      pExceptionObject = 1359;
      throw &pExceptionObject;
    }
  }
  if ( *((_DWORD *)this + 8) && *((_DWORD *)this + 9) )
    return (const unsigned __int16 *)*((_QWORD *)this + 3);
  return v2;
}

```

## disassembly

```asm
0x18000e680  mov     [rsp+arg_10], rbx
0x18000e685  mov     [rsp+arg_18], rbp
0x18000e68a  push    rsi
0x18000e68b  push    rdi
0x18000e68c  push    r12
0x18000e68e  push    r14
0x18000e690  push    r15
0x18000e692  sub     rsp, 30h
0x18000e696  mov     rbx, rcx
0x18000e699  lea     rbp, WideCharStr
0x18000e6a0  mov     ecx, [rcx+8]
0x18000e6a3  cmp     ecx, 1
0x18000e6a6  jnz     short loc_18000E6ED
0x18000e6a8  mov     edi, [rbx+38h]
0x18000e6ab  cmp     edi, ecx
0x18000e6ad  ja      short loc_18000E719
0x18000e6af  jz      loc_18000E845
0x18000e6b5  xor     r14d, r14d
0x18000e6b8  mov     [rbx+20h], r14d
0x18000e6bc  mov     dword ptr [rbx+8], 3
0x18000e6c3  cmp     dword ptr [rbx+20h], 0
0x18000e6c7  jz      short loc_18000E6D3
0x18000e6c9  cmp     dword ptr [rbx+24h], 0
0x18000e6cd  jbe     short loc_18000E6D3
0x18000e6cf  mov     rbp, [rbx+18h]
0x18000e6d3  mov     rbx, [rsp+58h+arg_10]
0x18000e6d8  mov     rax, rbp
0x18000e6db  mov     rbp, [rsp+58h+arg_18]
0x18000e6e0  add     rsp, 30h
0x18000e6e4  pop     r15
0x18000e6e6  pop     r14
0x18000e6e8  pop     r12
0x18000e6ea  pop     rdi
0x18000e6eb  pop     rsi
0x18000e6ec  retn
0x18000e6ed  test    ecx, ecx
0x18000e6ef  jz      loc_18000E7F3
0x18000e6f5  sub     ecx, 2
0x18000e6f8  jz      short loc_18000E6C3
0x18000e6fa  cmp     ecx, 1
0x18000e6fd  jz      short loc_18000E6C3
0x18000e6ff  lea     rdx, _TI1K; pThrowInfo
0x18000e706  mov     [rsp+58h+pExceptionObject], 54Fh
0x18000e70e  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000e713  call    _CxxThrowException_0
0x18000e719  cmp     dword ptr [rbx+3Ch], 0
0x18000e71d  jbe     loc_18000E7D5
0x18000e723  mov     rsi, [rbx+30h]
0x18000e727  call    cs:__imp_GetACP
0x18000e72d  xor     r14d, r14d
0x18000e730  lea     r9d, [rdi-1]; cbMultiByte
0x18000e734  mov     [rsp+58h+cchWideChar], r14d; cchWideChar
0x18000e739  mov     ecx, eax; CodePage
0x18000e73b  mov     r8, rsi; lpMultiByteStr
0x18000e73e  mov     [rsp+58h+lpWideCharStr], r14; lpWideCharStr
0x18000e743  mov     edx, 1; dwFlags
0x18000e748  call    cs:__imp_MultiByteToWideChar
0x18000e74e  mov     r12d, eax
0x18000e751  test    eax, eax
0x18000e753  jz      loc_18000E80D
0x18000e759  lea     edi, ds:2[rax*2]
0x18000e760  mov     [rsp+58h+arg_8], r13
0x18000e765  mov     edx, edi; unsigned int
0x18000e767  lea     rcx, [rbx+10h]; this
0x18000e76b  xor     r8d, r8d; int
0x18000e76e  call    ?Presize@CBuffer@@QEAAPEAEKH@Z; CBuffer::Presize(ulong,int)
0x18000e773  mov     [rbx+20h], edi
0x18000e776  cmp     [rbx+24h], r14d
0x18000e77a  jbe     short loc_18000E7DD
0x18000e77c  mov     r13, [rbx+18h]
0x18000e780  mov     eax, [rbx+38h]
0x18000e783  dec     eax
0x18000e785  mov     [rsp+58h+pExceptionObject], eax
0x18000e789  cmp     [rbx+3Ch], r14d
0x18000e78d  jbe     short loc_18000E7E2
0x18000e78f  mov     rsi, [rbx+30h]
0x18000e793  call    cs:__imp_GetACP
0x18000e799  mov     r9d, [rsp+58h+pExceptionObject]; cbMultiByte
0x18000e79e  mov     r8, rsi; lpMultiByteStr
0x18000e7a1  mov     ecx, eax; CodePage
0x18000e7a3  mov     [rsp+58h+cchWideChar], r12d; cchWideChar
0x18000e7a8  mov     edx, 1; dwFlags
0x18000e7ad  mov     [rsp+58h+lpWideCharStr], r13; lpWideCharStr
0x18000e7b2  call    cs:__imp_MultiByteToWideChar
0x18000e7b8  mov     r13, [rsp+58h+arg_8]
0x18000e7bd  test    eax, eax
0x18000e7bf  jz      short loc_18000E829
0x18000e7c1  add     eax, eax
0x18000e7c3  cmp     [rbx+24h], eax
0x18000e7c6  jbe     short loc_18000E7E7
0x18000e7c8  add     rax, [rbx+18h]
0x18000e7cc  mov     [rax], r14w
0x18000e7d0  jmp     loc_18000E6BC
0x18000e7d5  mov     rsi, rbp
0x18000e7d8  jmp     loc_18000E727
0x18000e7dd  mov     r13, rbp
0x18000e7e0  jmp     short loc_18000E780
0x18000e7e2  mov     rsi, rbp
0x18000e7e5  jmp     short loc_18000E793
0x18000e7e7  mov     rax, rbp
0x18000e7ea  mov     [rax], r14w
0x18000e7ee  jmp     loc_18000E6BC
0x18000e7f3  lea     rdx, _TI1K; pThrowInfo
0x18000e7fa  mov     [rsp+58h+pExceptionObject], 54Fh
0x18000e802  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000e807  call    _CxxThrowException_0
0x18000e80d  call    cs:__imp_GetLastError
0x18000e813  lea     rdx, _TI1K; pThrowInfo
0x18000e81a  mov     [rsp+58h+pExceptionObject], eax
0x18000e81e  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000e823  call    _CxxThrowException_0
0x18000e829  call    cs:__imp_GetLastError
0x18000e82f  lea     rdx, _TI1K; pThrowInfo
0x18000e836  mov     [rsp+58h+pExceptionObject], eax
0x18000e83a  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000e83f  call    _CxxThrowException_0
0x18000e845  mov     r8d, 2; unsigned int
0x18000e84b  lea     rcx, [rbx+10h]; this
0x18000e84f  mov     rdx, rbp; unsigned __int8 *
0x18000e852  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x18000e857  jmp     loc_18000E6BC
```

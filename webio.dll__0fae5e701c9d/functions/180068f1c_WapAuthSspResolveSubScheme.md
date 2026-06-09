# WapAuthSspResolveSubScheme

- ea: `0x180068f1c`
- end: `0x180069045`
- name: `WapAuthSspResolveSubScheme`
- size: `297`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800687a0`

## callees

- `0x180068f1c`
- `0x1800722f0`
- `0x1800971ec`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068fc5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068fff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068fc5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068fff`
- `SspiCli!QueryContextAttributesExW` at `0x180068f53`
- `SspiCli!QueryContextAttributesExW` at `0x180068f53`
- `SspiCli!FreeContextBuffer` at `0x180069020`
- `SspiCli!FreeContextBuffer` at `0x180069020`

## pseudocode

```c
__int64 __fastcall WapAuthSspResolveSubScheme(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdi
  const WCHAR *v5; // rcx
  PVOID pBuffer; // [rsp+30h] [rbp-48h] BYREF
  __int64 v8; // [rsp+38h] [rbp-40h]

  v8 = 0;
  pBuffer = 0;
  v2 = QueryContextAttributesExW((PCtxtHandle)(a1 + 48), 0xCu, &pBuffer, 0x10u);
  v3 = v2;
  if ( v2 )
  {
    if ( (xmmword_1800AD710 & 8) != 0 )
      WPP_SF_d(515, 17, WPP_05612d2d46af3ad8812821a8d7ec1cab_Traceguids, v2);
  }
  else
  {
    v3 = 0;
    if ( (unsigned int)v8 <= 1 )
    {
      v4 = -1;
      v5 = (const WCHAR *)*((_QWORD *)pBuffer + 2);
      do
        ++v4;
      while ( v5[v4] );
      if ( CompareStringOrdinal(v5, v4, lpString2, cchCount2, 1) == 2 )
      {
        *(_DWORD *)a1 = 3;
      }
      else if ( CompareStringOrdinal(*((LPCWCH *)pBuffer + 2), v4, off_1800AC1D0, dword_1800AC1D8, 1) == 2 )
      {
        *(_DWORD *)a1 = 4;
      }
    }
  }
  if ( pBuffer )
    FreeContextBuffer(pBuffer);
  return v3;
}

```

## disassembly

```asm
0x180068f1c  push    rbx
0x180068f1e  push    rbp
0x180068f1f  push    rsi
0x180068f20  push    rdi
0x180068f21  sub     rsp, 58h
0x180068f25  mov     rax, cs:__security_cookie
0x180068f2c  xor     rax, rsp
0x180068f2f  mov     [rsp+78h+var_38], rax
0x180068f34  xor     ebp, ebp
0x180068f36  lea     r8, [rsp+78h+pBuffer]; pBuffer
0x180068f3b  mov     rsi, rcx
0x180068f3e  mov     [rsp+78h+var_40], rbp
0x180068f43  add     rcx, 30h ; '0'; phContext
0x180068f47  mov     [rsp+78h+pBuffer], rbp
0x180068f4c  lea     r9d, [rbp+10h]; cbBuffer
0x180068f50  lea     edx, [rbp+0Ch]; ulAttribute
0x180068f53  call    cs:__imp_QueryContextAttributesExW
0x180068f5a  nop     dword ptr [rax+rax+00h]
0x180068f5f  mov     ebx, eax
0x180068f61  test    eax, eax
0x180068f63  jz      short loc_180068F8E
0x180068f65  test    byte ptr cs:xmmword_1800AD710, 8
0x180068f6c  jz      loc_180069016
0x180068f72  lea     edx, [rbp+11h]
0x180068f75  mov     ecx, 203h
0x180068f7a  mov     r9d, eax
0x180068f7d  lea     r8, WPP_05612d2d46af3ad8812821a8d7ec1cab_Traceguids
0x180068f84  call    WPP_SF_d
0x180068f89  jmp     loc_180069016
0x180068f8e  cmp     dword ptr [rsp+78h+var_40], 1
0x180068f93  mov     ebx, ebp
0x180068f95  ja      short loc_180069016
0x180068f97  mov     rax, [rsp+78h+pBuffer]
0x180068f9c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180068fa0  mov     rcx, [rax+10h]; lpString1
0x180068fa4  inc     rdi
0x180068fa7  cmp     [rcx+rdi*2], bp
0x180068fab  jnz     short loc_180068FA4
0x180068fad  mov     r9d, cs:cchCount2; cchCount2
0x180068fb4  mov     edx, edi; cchCount1
0x180068fb6  mov     r8, cs:lpString2; lpString2
0x180068fbd  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x180068fc5  call    cs:__imp_CompareStringOrdinal
0x180068fcc  nop     dword ptr [rax+rax+00h]
0x180068fd1  cmp     eax, 2
0x180068fd4  jnz     short loc_180068FDE
0x180068fd6  mov     dword ptr [rsi], 3
0x180068fdc  jmp     short loc_180069016
0x180068fde  mov     rcx, [rsp+78h+pBuffer]
0x180068fe3  mov     edx, edi; cchCount1
0x180068fe5  mov     r9d, cs:dword_1800AC1D8; cchCount2
0x180068fec  mov     r8, cs:off_1800AC1D0; lpString2
0x180068ff3  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x180068ffb  mov     rcx, [rcx+10h]; lpString1
0x180068fff  call    cs:__imp_CompareStringOrdinal
0x180069006  nop     dword ptr [rax+rax+00h]
0x18006900b  cmp     eax, 2
0x18006900e  jnz     short loc_180069016
0x180069010  mov     dword ptr [rsi], 4
0x180069016  mov     rcx, [rsp+78h+pBuffer]; pvContextBuffer
0x18006901b  test    rcx, rcx
0x18006901e  jz      short loc_18006902C
0x180069020  call    cs:__imp_FreeContextBuffer
0x180069027  nop     dword ptr [rax+rax+00h]
0x18006902c  mov     eax, ebx
0x18006902e  mov     rcx, [rsp+78h+var_38]
0x180069033  xor     rcx, rsp; StackCookie
0x180069036  call    __security_check_cookie
0x18006903b  add     rsp, 58h
0x18006903f  pop     rdi
0x180069040  pop     rsi
0x180069041  pop     rbp
0x180069042  pop     rbx
0x180069043  retn
```

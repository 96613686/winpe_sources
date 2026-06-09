# CFETextStreamDecoder::Process(void)

- ea: `0x180048840`
- end: `0x180048abc`
- name: `?Process@CFETextStreamDecoder@@UEAAJXZ`
- size: `636`
- prototype: `__int64 __fastcall(CFETextStreamDecoder *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800034b0`
- `0x1800172c8`
- `0x18002ad50`
- `0x18002ae98`
- `0x18002b178`
- `0x180048688`
- `0x180048840`
- `0x1800ff4f0`
- `0x1800ff520`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strtod` at `0x180048989`
- `api-ms-win-crt-private-l1-1-0!_o_strtod` at `0x180048989`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180048899`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180048899`
- `OLEAUT32!__imp_SysFreeString` at `0x18004891c`
- `OLEAUT32!__imp_SysFreeString` at `0x18004892a`
- `OLEAUT32!__imp_SysFreeString` at `0x18004891c`
- `OLEAUT32!__imp_SysFreeString` at `0x18004892a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800488ba`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800488ba`

## pseudocode

```c
__int64 __fastcall CFETextStreamDecoder::Process(CFETextStreamDecoder *this)
{
  const CHAR *v2; // rcx
  const OLECHAR *v3; // rax
  OLECHAR *v4; // rbx
  _QWORD *v5; // rcx
  char *v6; // rsi
  unsigned int v8; // ebx
  __int64 v9; // rsi
  const char *v10; // r10
  __int64 v11; // rax
  __int64 v12; // rcx
  float *v13; // rbp
  const char *v14; // r10
  int v15; // ebx
  double v16; // xmm0_8
  _BYTE *v17; // r10
  float v18; // xmm1_4
  const void *v19; // rbp
  __int64 v20; // rsi
  void *v21; // rcx
  __int64 i; // rdx
  int v23; // edx
  unsigned int v24; // [rsp+20h] [rbp-38h] BYREF
  CLSID pclsid; // [rsp+28h] [rbp-30h] BYREF

  *(_BYTE *)(*((unsigned int *)this + 21) + *((_QWORD *)this + 9)) = 0;
  if ( *((_BYTE *)this + 97) && *((_DWORD *)this + 21) > 0x28u )
  {
    v2 = (const CHAR *)*((_QWORD *)this + 9);
    pclsid = 0;
    if ( v2 )
      v3 = A2WBSTR(v2, 38);
    else
      v3 = SysAllocStringLen(0, 0x26u);
    v4 = (OLECHAR *)v3;
    if ( !v3 )
      ATL::AtlThrowImpl(-2147024882);
    if ( !CLSIDFromString(v3, &pclsid) )
    {
      v5 = (_QWORD *)**((_QWORD **)this + 5);
      if ( *(_QWORD *)&pclsid.Data1 == *v5 && *(_QWORD *)pclsid.Data4 == v5[1] )
      {
        v6 = (char *)*((_QWORD *)this + 9);
        *((_BYTE *)this + 97) = 0;
        if ( !strncmp_0(v6 + 38, "\n", 2u) )
        {
          *((_DWORD *)this + 21) -= 40;
          memmove_0(v6, v6 + 40, (unsigned int)(*((_DWORD *)this + 21) + 1));
          SysFreeString(v4);
          goto LABEL_28;
        }
      }
    }
    SysFreeString(v4);
    return 2147811350LL;
  }
  else
  {
LABEL_28:
    while ( *((_DWORD *)this + 21) )
    {
      v8 = *((_DWORD *)this + 12);
      v9 = 0;
      v10 = (const char *)*((_QWORD *)this + 9);
      if ( v8 )
      {
        while ( 1 )
        {
          v11 = *((_QWORD *)this + 7);
          v24 = 0;
          v13 = (float *)CFEWindowedBuffer::GetWritePointer(*(CFEWindowedBuffer **)(v11 + 8 * v9), &v24);
          if ( !v13 )
            return 327698;
          v15 = 0;
          if ( *(_DWORD *)(v12 + 4) )
            break;
LABEL_20:
          if ( !*v14 )
            return 327696;
          if ( *v14 != 9 )
            return 2147811350LL;
          v8 = *((_DWORD *)this + 12);
          v10 = v14 + 1;
          v9 = (unsigned int)(v9 + 1);
          if ( (unsigned int)v9 >= v8 )
            goto LABEL_23;
        }
        while ( 1 )
        {
          *(_QWORD *)&pclsid.Data1 = 0;
          v16 = strtod(v14, (char **)&pclsid);
          v17 = *(_BYTE **)&pclsid.Data1;
          v18 = v16;
          *v13 = v18;
          if ( !*v17 )
            return 327696;
          if ( *v17 != 9 )
            return 2147811350LL;
          ++v13;
          v14 = v17 + 1;
          if ( (unsigned int)++v15 >= *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 8 * v9) + 4LL) )
            goto LABEL_20;
        }
      }
LABEL_23:
      v19 = v10 + 2;
      if ( *((_QWORD *)this + 9) + (unsigned __int64)*((unsigned int *)this + 20) < (unsigned __int64)(v10 + 2) )
        return 327696;
      if ( strncmp_0(v10, "\n", 2u) )
        return 2147811350LL;
      v20 = 0;
      if ( v8 )
      {
        do
        {
          CFEWindowedBuffer::AdvanceWritePointer(*(CFEWindowedBuffer **)(*((_QWORD *)this + 7) + 8 * v20), 1u);
          v20 = (unsigned int)(v20 + 1);
        }
        while ( (unsigned int)v20 < *((_DWORD *)this + 12) );
      }
      v21 = (void *)*((_QWORD *)this + 9);
      *((_DWORD *)this + 21) += *((_DWORD *)this + 18) - (_DWORD)v19;
      memmove_0(v21, v19, (unsigned int)(*((_DWORD *)this + 21) + 1));
    }
    if ( !*((_BYTE *)this + 64) )
      return 327696;
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 12); i = (unsigned int)(v23 + 1) )
      CFEWindowedBuffer::EndOfStream(*(CFEWindowedBuffer **)(*((_QWORD *)this + 7) + 8 * i));
    return 327697;
  }
}

```

## disassembly

```asm
0x180048840  mov     [rsp+arg_8], rbx
0x180048845  mov     [rsp+arg_10], rbp
0x18004884a  push    rsi
0x18004884b  push    rdi
0x18004884c  push    r14
0x18004884e  sub     rsp, 40h
0x180048852  mov     rax, cs:__security_cookie
0x180048859  xor     rax, rsp
0x18004885c  mov     [rsp+58h+var_20], rax
0x180048861  mov     edx, [rcx+54h]
0x180048864  mov     rdi, rcx
0x180048867  mov     rax, [rcx+48h]
0x18004886b  mov     byte ptr [rdx+rax], 0
0x18004886f  cmp     byte ptr [rcx+61h], 0
0x180048873  jz      loc_180048A53
0x180048879  cmp     dword ptr [rcx+54h], 28h ; '('
0x18004887d  jbe     loc_180048A53
0x180048883  mov     rcx, [rcx+48h]; lpMultiByteStr
0x180048887  xorps   xmm0, xmm0
0x18004888a  mov     edx, 26h ; '&'; cbMultiByte
0x18004888f  movups  xmmword ptr [rsp+58h+pclsid.Data1], xmm0
0x180048894  test    rcx, rcx
0x180048897  jnz     short loc_1800488A1
0x180048899  call    cs:__imp_SysAllocStringLen
0x18004889f  jmp     short loc_1800488A6
0x1800488a1  call    ?A2WBSTR@@YAPEAGPEBDH@Z; A2WBSTR(char const *,int)
0x1800488a6  mov     rbx, rax
0x1800488a9  test    rax, rax
0x1800488ac  jz      loc_180048AB1
0x1800488b2  lea     rdx, [rsp+58h+pclsid]; pclsid
0x1800488b7  mov     rcx, rax; lpsz
0x1800488ba  call    cs:__imp_CLSIDFromString
0x1800488c0  test    eax, eax
0x1800488c2  jnz     short loc_180048927
0x1800488c4  mov     rax, [rdi+28h]
0x1800488c8  mov     rcx, [rax]
0x1800488cb  mov     rax, qword ptr [rsp+58h+pclsid.Data1]
0x1800488d0  cmp     rax, [rcx]
0x1800488d3  jnz     short loc_180048927
0x1800488d5  mov     rax, qword ptr [rsp+58h+pclsid.Data4]
0x1800488da  cmp     rax, [rcx+8]
0x1800488de  jnz     short loc_180048927
0x1800488e0  mov     rsi, [rdi+48h]
0x1800488e4  lea     rdx, asc_180111994; "\n"
0x1800488eb  mov     r8d, 2; MaxCount
0x1800488f1  mov     byte ptr [rdi+61h], 0
0x1800488f5  lea     rcx, [rsi+26h]; Str1
0x1800488f9  call    strncmp_0
0x1800488fe  test    eax, eax
0x180048900  jnz     short loc_180048927
0x180048902  add     dword ptr [rdi+54h], 0FFFFFFD8h
0x180048906  lea     rdx, [rsi+28h]; Src
0x18004890a  mov     r8d, [rdi+54h]
0x18004890e  mov     rcx, rsi; void *
0x180048911  inc     r8d; Size
0x180048914  call    memmove_0
0x180048919  mov     rcx, rbx; bstrString
0x18004891c  call    cs:__imp_SysFreeString
0x180048922  jmp     loc_180048A53
0x180048927  mov     rcx, rbx; bstrString
0x18004892a  call    cs:__imp_SysFreeString
0x180048930  mov     eax, 80050016h
0x180048935  jmp     loc_180048A91
0x18004893a  mov     ebx, [rdi+30h]
0x18004893d  xor     esi, esi
0x18004893f  mov     r10, [rdi+48h]
0x180048943  test    ebx, ebx
0x180048945  jz      loc_1800489E8
0x18004894b  mov     rax, [rdi+38h]
0x18004894f  lea     rdx, [rsp+58h+var_38]; unsigned int *
0x180048954  mov     [rsp+58h+var_38], 0
0x18004895c  mov     rcx, [rax+rsi*8]; this
0x180048960  call    ?GetWritePointer@CFEWindowedBuffer@@QEAAPEAXPEAI@Z; CFEWindowedBuffer::GetWritePointer(uint *)
0x180048965  mov     rbp, rax
0x180048968  test    rax, rax
0x18004896b  jz      loc_180048A85
0x180048971  xor     ebx, ebx
0x180048973  cmp     [rcx+4], ebx
0x180048976  jbe     short loc_1800489C5
0x180048978  lea     rdx, [rsp+58h+pclsid]; EndPtr
0x18004897d  mov     qword ptr [rsp+58h+pclsid.Data1], 0
0x180048986  mov     rcx, r10; String
0x180048989  call    cs:__imp_strtod
0x18004898f  mov     r10, qword ptr [rsp+58h+pclsid.Data1]
0x180048994  xorps   xmm1, xmm1
0x180048997  cvtsd2ss xmm1, xmm0
0x18004899b  movss   dword ptr [rbp+0], xmm1
0x1800489a0  mov     al, [r10]
0x1800489a3  test    al, al
0x1800489a5  jz      loc_180048A8C
0x1800489ab  cmp     al, 9
0x1800489ad  jnz     short loc_180048930
0x1800489af  mov     rax, [rdi+38h]
0x1800489b3  add     rbp, 4
0x1800489b7  inc     r10
0x1800489ba  inc     ebx
0x1800489bc  mov     rcx, [rax+rsi*8]
0x1800489c0  cmp     ebx, [rcx+4]
0x1800489c3  jb      short loc_180048978
0x1800489c5  mov     al, [r10]
0x1800489c8  test    al, al
0x1800489ca  jz      loc_180048A8C
0x1800489d0  cmp     al, 9
0x1800489d2  jnz     loc_180048930
0x1800489d8  mov     ebx, [rdi+30h]
0x1800489db  inc     r10
0x1800489de  inc     esi
0x1800489e0  cmp     esi, ebx
0x1800489e2  jb      loc_18004894B
0x1800489e8  mov     eax, [rdi+50h]
0x1800489eb  lea     rbp, [r10+2]
0x1800489ef  add     rax, [rdi+48h]
0x1800489f3  cmp     rax, rbp
0x1800489f6  jb      loc_180048A8C
0x1800489fc  mov     r8d, 2; MaxCount
0x180048a02  lea     rdx, asc_180111994; "\n"
0x180048a09  mov     rcx, r10; Str1
0x180048a0c  call    strncmp_0
0x180048a11  test    eax, eax
0x180048a13  jnz     loc_180048930
0x180048a19  xor     esi, esi
0x180048a1b  test    ebx, ebx
0x180048a1d  jz      short loc_180048A38
0x180048a1f  mov     rcx, [rdi+38h]
0x180048a23  mov     edx, 1; unsigned int
0x180048a28  mov     rcx, [rcx+rsi*8]; this
0x180048a2c  call    ?AdvanceWritePointer@CFEWindowedBuffer@@QEAAXI@Z; CFEWindowedBuffer::AdvanceWritePointer(uint)
0x180048a31  inc     esi
0x180048a33  cmp     esi, [rdi+30h]
0x180048a36  jb      short loc_180048A1F
0x180048a38  mov     eax, [rdi+48h]
0x180048a3b  mov     rdx, rbp; Src
0x180048a3e  mov     rcx, [rdi+48h]; void *
0x180048a42  sub     eax, ebp
0x180048a44  add     [rdi+54h], eax
0x180048a47  mov     r8d, [rdi+54h]
0x180048a4b  inc     r8d; Size
0x180048a4e  call    memmove_0
0x180048a53  cmp     dword ptr [rdi+54h], 0
0x180048a57  ja      loc_18004893A
0x180048a5d  cmp     byte ptr [rdi+40h], 0
0x180048a61  jz      short loc_180048A8C
0x180048a63  xor     edx, edx
0x180048a65  cmp     [rdi+30h], edx
0x180048a68  jbe     short loc_180048A7E
0x180048a6a  mov     rcx, [rdi+38h]
0x180048a6e  mov     rcx, [rcx+rdx*8]; this
0x180048a72  call    ?EndOfStream@CFEWindowedBuffer@@QEAAXXZ; CFEWindowedBuffer::EndOfStream(void)
0x180048a77  inc     edx
0x180048a79  cmp     edx, [rdi+30h]
0x180048a7c  jb      short loc_180048A6A
0x180048a7e  mov     eax, 50011h
0x180048a83  jmp     short loc_180048A91
0x180048a85  mov     eax, 50012h
0x180048a8a  jmp     short loc_180048A91
0x180048a8c  mov     eax, 50010h
0x180048a91  mov     rcx, [rsp+58h+var_20]
0x180048a96  xor     rcx, rsp; StackCookie
0x180048a99  call    __security_check_cookie
0x180048a9e  mov     rbx, [rsp+58h+arg_8]
0x180048aa3  mov     rbp, [rsp+58h+arg_10]
0x180048aa8  add     rsp, 40h
0x180048aac  pop     r14
0x180048aae  pop     rdi
0x180048aaf  pop     rsi
0x180048ab0  retn
0x180048ab1  mov     ecx, 8007000Eh; int
0x180048ab6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

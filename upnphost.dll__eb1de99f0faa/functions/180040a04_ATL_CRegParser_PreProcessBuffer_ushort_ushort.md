# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180040a04`
- end: `0x180040c16`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `530`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041690`

## callees

- `0x18003a560`
- `0x18003c5c8`
- `0x18003de00`
- `0x18003df34`
- `0x180040a04`
- `0x180042fdc`
- `0x180043034`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180040b1f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180040b1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040a97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040a97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040a85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040bca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040a85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040bca`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180040acf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180040b77`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180040ba0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180040acf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180040b77`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180040ba0`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  void *v9; // rcx
  _WORD *v11; // rax
  WCHAR v12; // ax
  LPWSTR v13; // rax
  const unsigned __int16 *v14; // rdx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rsi
  __int64 v17; // rcx
  int v18; // eax
  const unsigned __int16 *v19; // rax
  __int64 v20; // r8
  int v21; // ebx
  const WCHAR *i; // rax
  unsigned int v23; // ebx
  __int64 v24; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v26; // [rsp+30h] [rbp-29h] BYREF
  unsigned __int16 v27[32]; // [rsp+40h] [rbp-19h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  LODWORD(v24) = 0;
  if ( v7 < 100 )
    v7 = 1000;
  HIDWORD(v24) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v11 = CoTaskMemAlloc((unsigned int)v8);
  pv = v11;
  v9 = v11;
  if ( !v11 )
    goto LABEL_9;
  *v11 = 0;
  *(_QWORD *)this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_29:
    v23 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_30;
  }
  while ( v12 != 37 )
  {
    v14 = v4;
LABEL_26:
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v24, v14, 1) )
      goto LABEL_33;
LABEL_27:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v9 = pv;
      goto LABEL_29;
    }
  }
  v13 = CharNextW(v4);
  *(_QWORD *)this = v13;
  if ( *v13 == 37 )
  {
    v14 = v13;
    goto LABEL_26;
  }
  v15 = ATL::CRegParser::StrChrW(v13, 0x25u);
  v16 = v15;
  if ( !v15 )
    goto LABEL_32;
  v17 = ((__int64)v15 - *(_QWORD *)this) >> 1;
  if ( v17 > 31 )
  {
    v23 = -2147467259;
    goto LABEL_30;
  }
  v18 = _o_wcsncpy_s(v27, 32, *(_QWORD *)this, (int)v17, v24);
  ATL::AtlCrtErrorCheck(v18);
  v19 = ATL::CRegObject::StrFromMap(*((ATL::CRegObject **)this + 1), v27);
  if ( !v19 )
  {
LABEL_32:
    v23 = -2147352567;
    goto LABEL_30;
  }
  v26 = 0;
  v20 = -1;
  do
    ++v20;
  while ( v19[v20] );
  v21 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v24, v19, v20);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v26);
  if ( v21 )
  {
    for ( i = *(const WCHAR **)this; i != v16; *(_QWORD *)this = i )
      i = CharNextW(i);
    goto LABEL_27;
  }
LABEL_33:
  v23 = -2147024882;
LABEL_30:
  CoTaskMemFree(pv);
  return v23;
}

```

## disassembly

```asm
0x180040a04  mov     [rsp-8+arg_8], rbx
0x180040a09  mov     [rsp-8+arg_18], rsi
0x180040a0e  push    rbp
0x180040a0f  push    rdi
0x180040a10  push    r12
0x180040a12  push    r14
0x180040a14  push    r15
0x180040a16  lea     rbp, [rsp-37h]
0x180040a1b  sub     rsp, 90h
0x180040a22  mov     rax, cs:__security_cookie
0x180040a29  xor     rax, rsp
0x180040a2c  mov     [rbp+57h+var_30], rax
0x180040a30  xor     r15d, r15d
0x180040a33  mov     r14, r8
0x180040a36  mov     rbx, rdx
0x180040a39  mov     rdi, rcx
0x180040a3c  test    rdx, rdx
0x180040a3f  jz      loc_180040BE9
0x180040a45  test    r8, r8
0x180040a48  jz      loc_180040BE9
0x180040a4e  mov     [r8], r15
0x180040a51  or      rax, 0FFFFFFFFFFFFFFFFh
0x180040a55  inc     rax
0x180040a58  cmp     [rdx+rax*2], r15w
0x180040a5d  jnz     short loc_180040A55
0x180040a5f  add     eax, eax
0x180040a61  mov     [rbp+57h+var_90], r15d
0x180040a65  cmp     eax, 64h ; 'd'
0x180040a68  mov     ecx, 3E8h
0x180040a6d  cmovl   eax, ecx
0x180040a70  mov     ecx, eax
0x180040a72  mov     [rbp+57h+var_8C], eax
0x180040a75  add     rcx, rcx
0x180040a78  mov     eax, 0FFFFFFFFh
0x180040a7d  cmp     rcx, rax
0x180040a80  jbe     short loc_180040A95
0x180040a82  mov     rcx, r15; pv
0x180040a85  call    cs:__imp_CoTaskMemFree
0x180040a8b  mov     eax, 8007000Eh
0x180040a90  jmp     loc_180040BEE
0x180040a95  mov     ecx, ecx; cb
0x180040a97  call    cs:__imp_CoTaskMemAlloc
0x180040a9d  mov     [rbp+57h+pv], rax
0x180040aa1  mov     rcx, rax
0x180040aa4  test    rax, rax
0x180040aa7  jz      short loc_180040A85
0x180040aa9  mov     [rax], r15w
0x180040aad  mov     [rdi], rbx
0x180040ab0  movzx   eax, word ptr [rbx]
0x180040ab3  test    ax, ax
0x180040ab6  jz      loc_180040BBC
0x180040abc  mov     r12d, 25h ; '%'
0x180040ac2  cmp     ax, r12w
0x180040ac6  jnz     loc_180040B87
0x180040acc  mov     rcx, rbx; lpsz
0x180040acf  call    cs:__imp_CharNextW
0x180040ad5  mov     [rdi], rax
0x180040ad8  cmp     [rax], r12w
0x180040adc  jnz     short loc_180040AE6
0x180040ade  mov     rdx, rax
0x180040ae1  jmp     loc_180040B8A
0x180040ae6  mov     edx, r12d; unsigned __int16
0x180040ae9  mov     rcx, rax; lpsz
0x180040aec  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180040af1  mov     rsi, rax
0x180040af4  test    rax, rax
0x180040af7  jz      loc_180040BDB
0x180040afd  mov     rcx, rax
0x180040b00  sub     rcx, [rdi]
0x180040b03  sar     rcx, 1
0x180040b06  cmp     rcx, 1Fh
0x180040b0a  jg      loc_180040BD4
0x180040b10  mov     r8, [rdi]
0x180040b13  mov     edx, 20h ; ' '
0x180040b18  movsxd  r9, ecx
0x180040b1b  lea     rcx, [rbp+57h+var_70]
0x180040b1f  call    cs:__imp__o_wcsncpy_s
0x180040b25  mov     ecx, eax; int
0x180040b27  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180040b2c  mov     rcx, [rdi+8]; this
0x180040b30  lea     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x180040b34  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x180040b39  test    rax, rax
0x180040b3c  jz      loc_180040BDB
0x180040b42  mov     [rbp+57h+var_80], r15
0x180040b46  or      r8, 0FFFFFFFFFFFFFFFFh
0x180040b4a  inc     r8; int
0x180040b4d  cmp     [rax+r8*2], r15w
0x180040b52  jnz     short loc_180040B4A
0x180040b54  mov     rdx, rax; unsigned __int16 *
0x180040b57  lea     rcx, [rbp+57h+var_90]; this
0x180040b5b  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180040b60  lea     rcx, [rbp+57h+var_80]
0x180040b64  mov     ebx, eax
0x180040b66  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180040b6b  test    ebx, ebx
0x180040b6d  jz      short loc_180040BE2
0x180040b6f  mov     rax, [rdi]
0x180040b72  jmp     short loc_180040B80
0x180040b74  mov     rcx, rax; lpsz
0x180040b77  call    cs:__imp_CharNextW
0x180040b7d  mov     [rdi], rax
0x180040b80  cmp     rax, rsi
0x180040b83  jnz     short loc_180040B74
0x180040b85  jmp     short loc_180040B9D
0x180040b87  mov     rdx, rbx; unsigned __int16 *
0x180040b8a  mov     r8d, 1; int
0x180040b90  lea     rcx, [rbp+57h+var_90]; this
0x180040b94  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180040b99  test    eax, eax
0x180040b9b  jz      short loc_180040BE2
0x180040b9d  mov     rcx, [rdi]; lpsz
0x180040ba0  call    cs:__imp_CharNextW
0x180040ba6  mov     rbx, rax
0x180040ba9  mov     [rdi], rax
0x180040bac  movzx   eax, word ptr [rax]
0x180040baf  test    ax, ax
0x180040bb2  jnz     loc_180040AC2
0x180040bb8  mov     rcx, [rbp+57h+pv]
0x180040bbc  mov     ebx, r15d
0x180040bbf  mov     [rbp+57h+pv], r15
0x180040bc3  mov     [r14], rcx
0x180040bc6  mov     rcx, [rbp+57h+pv]; pv
0x180040bca  call    cs:__imp_CoTaskMemFree
0x180040bd0  mov     eax, ebx
0x180040bd2  jmp     short loc_180040BEE
0x180040bd4  mov     ebx, 80004005h
0x180040bd9  jmp     short loc_180040BC6
0x180040bdb  mov     ebx, 80020009h
0x180040be0  jmp     short loc_180040BC6
0x180040be2  mov     ebx, 8007000Eh
0x180040be7  jmp     short loc_180040BC6
0x180040be9  mov     eax, 80004003h
0x180040bee  mov     rcx, [rbp+57h+var_30]
0x180040bf2  xor     rcx, rsp; StackCookie
0x180040bf5  call    __security_check_cookie
0x180040bfa  lea     r11, [rsp+0B0h+var_20]
0x180040c02  mov     rbx, [r11+38h]
0x180040c06  mov     rsi, [r11+48h]
0x180040c0a  mov     rsp, r11
0x180040c0d  pop     r15
0x180040c0f  pop     r14
0x180040c11  pop     r12
0x180040c13  pop     rdi
0x180040c14  pop     rbp
0x180040c15  retn
```

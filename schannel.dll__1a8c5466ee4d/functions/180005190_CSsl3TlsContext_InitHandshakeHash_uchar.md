# CSsl3TlsContext::InitHandshakeHash(uchar)

- ea: `0x180005190`
- end: `0x180005487`
- name: `?InitHandshakeHash@CSsl3TlsContext@@UEAAKE@Z`
- size: `759`
- prototype: `unsigned int __fastcall(CSsl3TlsContext *__hidden this, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004950`

## callees

- `0x180005190`
- `0x180005e30`
- `0x1800597b0`
- `0x18005a10c`
- `0x18005a160`

## import_xrefs

- `ncrypt!SslCreateClientAuthHash` at `0x180005425`
- `ncrypt!SslCreateClientAuthHash` at `0x180005425`
- `ncrypt!SslCreateHandshakeHash` at `0x18000525b`
- `ncrypt!SslCreateHandshakeHash` at `0x18000525b`
- `ncrypt!SslFreeObject` at `0x18000521e`
- `ncrypt!SslFreeObject` at `0x18000521e`
- `ncrypt!SslGetCipherSuitePRFHashAlgorithm` at `0x1800052e3`
- `ncrypt!SslGetCipherSuitePRFHashAlgorithm` at `0x1800052e3`

## pseudocode

```c
__int64 __fastcall CSsl3TlsContext::InitHandshakeHash(CSsl3TlsContext *this, char a2)
{
  __int64 *v2; // rax
  __int64 v5; // r12
  unsigned int v6; // r13d
  unsigned int v7; // r15d
  unsigned int v8; // edi
  char *v9; // rsi
  __int64 v10; // rcx
  __int64 result; // rax
  unsigned int v12; // ebp
  unsigned int CipherSuitePRFHashAlgorithm; // edi
  int v14; // ecx
  unsigned int v15; // r15d
  int v16; // r14d
  int v17; // esi
  __int64 v18; // rdx
  const wchar_t *v19; // r12
  int v20; // r13d
  unsigned __int16 v21; // r10
  __int64 *v22; // rax
  unsigned __int8 v23; // r8
  int v24; // ecx
  unsigned int v25; // r9d
  int v26; // ecx
  __int64 v27; // rdx
  unsigned int i; // [rsp+30h] [rbp-148h]
  unsigned int v29; // [rsp+34h] [rbp-144h]
  __int64 v30; // [rsp+38h] [rbp-140h]
  _QWORD v31[16]; // [rsp+40h] [rbp-138h] BYREF
  wchar_t String1[64]; // [rsp+C0h] [rbp-B8h] BYREF

  v2 = (__int64 *)*((_QWORD *)this + 1);
  if ( v2 )
    v5 = *v2;
  else
    v5 = 0;
  v6 = *((unsigned __int16 *)this + 17);
  v29 = v6;
  v30 = v5;
  if ( (*((_BYTE *)this + 32) & 1) != 0 && v2 )
    v7 = *((_DWORD *)v2 + 7);
  else
    v7 = 0;
  v8 = 0;
  for ( i = v7; v8 < *((_DWORD *)this + 567); ++v8 )
  {
    v9 = (char *)this + 8 * v8;
    v10 = *((_QWORD *)v9 + 289);
    if ( v10 )
    {
      SslFreeObject(v10, 0);
      *((_QWORD *)v9 + 289) = 0;
    }
  }
  *((_DWORD *)this + 610) = 0;
  *((_DWORD *)this + 567) = 0;
  result = SslCreateHandshakeHash(v5, (char *)this + 2312, v6, v7, 0);
  if ( (_DWORD)result )
    return result;
  v12 = 1;
  *((_DWORD *)this + 567) = 1;
  if ( !a2 )
    return 0;
  memset_0(v31, 0, sizeof(v31));
  CipherSuitePRFHashAlgorithm = SslGetCipherSuitePRFHashAlgorithm(v5, v6, v7, 0, String1, 0);
  if ( CipherSuitePRFHashAlgorithm
    || (v14 = g_dwHashInfoTotalCount,
        v15 = 0,
        v16 = *((_DWORD *)this + 22),
        CipherSuitePRFHashAlgorithm = -2146893007,
        String1[63] = 0,
        v17 = 4,
        g_dwHashInfoTotalCount <= 4) )
  {
LABEL_16:
    CSsl3TlsContext::FreeHandshakeHash(this);
    return CipherSuitePRFHashAlgorithm;
  }
  while ( 1 )
  {
    if ( v17 >= (unsigned int)v14 || (v18 = g_pHashInfo[v17]) == 0 )
    {
      CipherSuitePRFHashAlgorithm = 1168;
      goto LABEL_35;
    }
    v19 = *(const wchar_t **)v18;
    v20 = *(_DWORD *)(v18 + 20);
    CipherSuitePRFHashAlgorithm = 0;
    if ( !wcsnicmp(String1, *(const wchar_t **)v18, 0x40u) )
      break;
    v14 = g_dwHashInfoTotalCount;
LABEL_35:
    if ( ++v17 >= v14 )
    {
      if ( !CipherSuitePRFHashAlgorithm )
        goto LABEL_31;
      goto LABEL_16;
    }
  }
  if ( v17 < g_dwHashInfoTotalCount && v19 )
  {
    *((_DWORD *)this + 610) = v20;
    v31[0] = v19;
    v21 = 1 << v20;
    v22 = qword_1800931C0;
    v23 = 0;
    v15 = 1;
    do
    {
      if ( v23 < 0xCu )
      {
        v24 = *((unsigned __int16 *)this + 1114);
        if ( _bittest(&v24, v23) )
        {
          if ( (v16 & (_DWORD)v22[3]) != 0 )
          {
            v25 = *((_DWORD *)v22 + 10);
            v26 = v21;
            if ( !_bittest(&v26, v25) )
            {
              v27 = v15;
              v21 |= 1 << v25;
              ++v15;
              *((_DWORD *)this + v27 + 610) = v25;
              v31[v27] = v22[6];
            }
          }
        }
      }
      v22 += 10;
      ++v23;
    }
    while ( v22 < (__int64 *)&off_180093580 );
  }
LABEL_31:
  while ( v12 < v15 )
  {
    CipherSuitePRFHashAlgorithm = SslCreateClientAuthHash(v30, (char *)this + 8 * v12 + 2312, v29, i, v31[v12], 0);
    if ( CipherSuitePRFHashAlgorithm )
      goto LABEL_16;
    *((_DWORD *)this + 567) = ++v12;
  }
  return 0;
}

```

## disassembly

```asm
0x180005190  mov     [rsp+arg_10], rbx
0x180005195  mov     [rsp+arg_18], rsi
0x18000519a  push    rdi
0x18000519b  push    r12
0x18000519d  push    r13
0x18000519f  push    r14
0x1800051a1  push    r15
0x1800051a3  sub     rsp, 150h
0x1800051aa  mov     rax, cs:__security_cookie
0x1800051b1  xor     rax, rsp
0x1800051b4  mov     [rsp+178h+var_38], rax
0x1800051bc  mov     rax, [rcx+8]
0x1800051c0  xor     esi, esi
0x1800051c2  movzx   r14d, dl
0x1800051c6  mov     rbx, rcx
0x1800051c9  test    rax, rax
0x1800051cc  jz      loc_180005329
0x1800051d2  mov     r12, [rax]
0x1800051d5  test    byte ptr [rcx+20h], 1
0x1800051d9  movzx   r13d, word ptr [rcx+22h]
0x1800051de  mov     [rsp+178h+var_144], r13d
0x1800051e3  mov     [rsp+178h+var_140], r12
0x1800051e8  jz      loc_180005321
0x1800051ee  test    rax, rax
0x1800051f1  jz      loc_180005321
0x1800051f7  mov     r15d, [rax+1Ch]
0x1800051fb  mov     edi, esi
0x1800051fd  mov     [rsp+178h+var_148], r15d
0x180005202  cmp     [rcx+8DCh], esi
0x180005208  jbe     short loc_18000523B
0x18000520a  mov     eax, edi
0x18000520c  lea     rsi, [rbx+rax*8]
0x180005210  mov     rcx, [rsi+908h]
0x180005217  test    rcx, rcx
0x18000521a  jz      short loc_18000522F
0x18000521c  xor     edx, edx
0x18000521e  call    cs:__imp_SslFreeObject
0x180005224  mov     qword ptr [rsi+908h], 0
0x18000522f  inc     edi
0x180005231  cmp     edi, [rbx+8DCh]
0x180005237  jb      short loc_18000520A
0x180005239  xor     esi, esi
0x18000523b  mov     [rbx+988h], esi
0x180005241  lea     rdx, [rbx+908h]
0x180005248  mov     r9d, r15d
0x18000524b  mov     [rbx+8DCh], esi
0x180005251  mov     r8d, r13d
0x180005254  mov     dword ptr [rsp+178h+var_158], esi
0x180005258  mov     rcx, r12
0x18000525b  call    cs:__imp_SslCreateHandshakeHash
0x180005261  test    eax, eax
0x180005263  jnz     short loc_180005287
0x180005265  mov     [rsp+178h+arg_8], rbp
0x18000526d  mov     ebp, 1
0x180005272  mov     [rbx+8DCh], ebp
0x180005278  test    r14b, r14b
0x18000527b  jnz     short loc_1800052B4
0x18000527d  xor     eax, eax
0x18000527f  mov     rbp, [rsp+178h+arg_8]
0x180005287  mov     rcx, [rsp+178h+var_38]
0x18000528f  xor     rcx, rsp; StackCookie
0x180005292  call    __security_check_cookie
0x180005297  lea     r11, [rsp+178h+var_28]
0x18000529f  mov     rbx, [r11+40h]
0x1800052a3  mov     rsi, [r11+48h]
0x1800052a7  mov     rsp, r11
0x1800052aa  pop     r15
0x1800052ac  pop     r14
0x1800052ae  pop     r13
0x1800052b0  pop     r12
0x1800052b2  pop     rdi
0x1800052b3  retn
0x1800052b4  xor     edx, edx; Val
0x1800052b6  lea     rcx, [rsp+178h+var_138]; void *
0x1800052bb  mov     r8d, 80h; Size
0x1800052c1  call    memset_0
0x1800052c6  lea     rax, [rsp+178h+String1]
0x1800052ce  mov     [rsp+178h+var_150], esi
0x1800052d2  xor     r9d, r9d
0x1800052d5  mov     [rsp+178h+var_158], rax
0x1800052da  mov     r8d, r15d
0x1800052dd  mov     edx, r13d
0x1800052e0  mov     rcx, r12
0x1800052e3  call    cs:__imp_SslGetCipherSuitePRFHashAlgorithm
0x1800052e9  mov     edi, eax
0x1800052eb  test    eax, eax
0x1800052ed  jnz     short loc_180005312
0x1800052ef  mov     ecx, cs:g_dwHashInfoTotalCount
0x1800052f5  mov     r15d, esi
0x1800052f8  mov     r14d, [rbx+58h]
0x1800052fc  mov     edi, 80090331h
0x180005301  mov     [rsp+178h+var_3A], si
0x180005309  mov     esi, 4
0x18000530e  cmp     ecx, esi
0x180005310  jg      short loc_180005331
0x180005312  mov     rcx, rbx; this
0x180005315  call    ?FreeHandshakeHash@CSsl3TlsContext@@IEAAXXZ; CSsl3TlsContext::FreeHandshakeHash(void)
0x18000531a  mov     eax, edi
0x18000531c  jmp     loc_18000527F
0x180005321  mov     r15d, esi
0x180005324  jmp     loc_1800051FB
0x180005329  mov     r12, rsi
0x18000532c  jmp     loc_1800051D5
0x180005331  lea     rdx, g_pHashInfo
0x180005338  cmp     esi, ecx
0x18000533a  jnb     loc_180005480
0x180005340  mov     eax, esi
0x180005342  mov     rdx, [rdx+rax*8]
0x180005346  test    rdx, rdx
0x180005349  jz      loc_180005480
0x18000534f  mov     r12, [rdx]
0x180005352  lea     rcx, [rsp+178h+String1]; String1
0x18000535a  mov     r13d, [rdx+14h]
0x18000535e  mov     r8d, 40h ; '@'; MaxCount
0x180005364  mov     rdx, r12; String2
0x180005367  xor     edi, edi
0x180005369  call    _wcsnicmp
0x18000536e  test    eax, eax
0x180005370  jnz     loc_180005463
0x180005376  cmp     esi, cs:g_dwHashInfoTotalCount
0x18000537c  jge     short loc_1800053E6
0x18000537e  test    r12, r12
0x180005381  jz      short loc_1800053E6
0x180005383  mov     r10d, ebp
0x180005386  mov     [rbx+988h], r13d
0x18000538d  mov     ecx, r13d
0x180005390  mov     [rsp+178h+var_138], r12
0x180005395  shl     r10w, cl
0x180005399  lea     rax, qword_1800931C0
0x1800053a0  xor     r8b, r8b
0x1800053a3  lea     r11, off_180093580
0x1800053aa  mov     r15d, ebp
0x1800053ad  nop     dword ptr [rax]
0x1800053b0  cmp     r8b, 0Ch
0x1800053b4  jnb     short loc_1800053DA
0x1800053b6  movzx   ecx, word ptr [rbx+8B4h]
0x1800053bd  movzx   edx, r8b
0x1800053c1  bt      ecx, edx
0x1800053c4  jnb     short loc_1800053DA
0x1800053c6  test    [rax+18h], r14d
0x1800053ca  jz      short loc_1800053DA
0x1800053cc  mov     r9d, [rax+28h]
0x1800053d0  movzx   ecx, r10w
0x1800053d4  bt      ecx, r9d
0x1800053d8  jnb     short loc_18000543F
0x1800053da  add     rax, 50h ; 'P'
0x1800053de  inc     r8b
0x1800053e1  cmp     rax, r11
0x1800053e4  jb      short loc_1800053B0
0x1800053e6  mov     esi, [rsp+178h+var_148]
0x1800053ea  mov     r14, [rsp+178h+var_140]
0x1800053ef  mov     r12d, [rsp+178h+var_144]
0x1800053f4  cmp     ebp, r15d
0x1800053f7  jnb     loc_18000527D
0x1800053fd  mov     eax, ebp
0x1800053ff  lea     rdx, [rbx+908h]
0x180005406  mov     [rsp+178h+var_150], 0
0x18000540e  mov     r9d, esi
0x180005411  mov     r8d, r12d
0x180005414  mov     rcx, r14
0x180005417  lea     rdx, [rdx+rax*8]
0x18000541b  mov     rax, [rsp+rax*8+178h+var_138]
0x180005420  mov     [rsp+178h+var_158], rax
0x180005425  call    cs:__imp_SslCreateClientAuthHash
0x18000542b  mov     edi, eax
0x18000542d  test    eax, eax
0x18000542f  jnz     loc_180005312
0x180005435  inc     ebp
0x180005437  mov     [rbx+8DCh], ebp
0x18000543d  jmp     short loc_1800053F4
0x18000543f  mov     edx, r15d
0x180005442  bts     ecx, r9d
0x180005446  movzx   r10d, cx
0x18000544a  inc     r15d
0x18000544d  mov     [rbx+rdx*4+988h], r9d
0x180005455  mov     rcx, [rax+30h]
0x180005459  mov     [rsp+rdx*8+178h+var_138], rcx
0x18000545e  jmp     loc_1800053DA
0x180005463  mov     ecx, cs:g_dwHashInfoTotalCount
0x180005469  inc     esi
0x18000546b  cmp     esi, ecx
0x18000546d  jl      loc_180005331
0x180005473  test    edi, edi
0x180005475  jz      loc_1800053E6
0x18000547b  jmp     loc_180005312
0x180005480  mov     edi, 490h
0x180005485  jmp     short loc_180005469
```

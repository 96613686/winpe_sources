# CStringNormalizer::NormalizeString(ulong,uint,wchar_t const * const,uint *,uchar * const)

- ea: `0x180056a80`
- end: `0x180056c70`
- name: `?NormalizeString@CStringNormalizer@@AEBAIKIQEB_WPEAIQEAE@Z`
- size: `496`
- prototype: `unsigned int(CStringNormalizer *__hidden this, unsigned int, unsigned int, const wchar_t *const, unsigned int *, unsigned __int8 *const)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180056c78`

## callees

- `0x1800555f4`
- `0x180056a80`
- `0x180056dc8`
- `0x1800b89a0`
- `0x1800bd1bc`
- `0x18018e8cb`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056ad6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056ad6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056b8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056b8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056bb9`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180056af8`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180056af8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056ba0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056c2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056ba0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056c2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CStringNormalizer::NormalizeString(
        CStringNormalizer *this,
        unsigned int a2,
        int a3,
        const wchar_t *a4,
        unsigned int *a5,
        unsigned __int8 *const a6)
{
  __int64 v7; // rsi
  LCID SystemPreferredLocale; // edi
  DWORD v10; // r12d
  const wchar_t *v11; // r9
  unsigned __int16 *v12; // r14
  int v13; // r8d
  char *v14; // rdx
  int i; // ecx
  char v16; // r9
  int v17; // eax
  int v18; // edx
  unsigned int *v19; // rax
  signed int v20; // edi
  int v21; // eax
  int v22; // edx
  unsigned int j; // edi
  void *v24; // rcx
  bool v26; // bl
  void *v27; // rcx
  LPVOID pv; // [rsp+30h] [rbp-28h] BYREF
  LPVOID *p_pv; // [rsp+38h] [rbp-20h]
  wchar_t *v30; // [rsp+40h] [rbp-18h] BYREF
  char v31; // [rsp+48h] [rbp-10h]

  LODWORD(v7) = a3;
  SystemPreferredLocale = a2;
  v10 = ~(unsigned __int8)*(_DWORD *)this & 2 | 0x8030401;
  if ( !IsValidOrFallbackLocale(a2) )
  {
    SystemPreferredLocale = CStringNormalizer::m_lcidSystemLocale;
    if ( !CStringNormalizer::m_lcidSystemLocale )
    {
      SystemPreferredLocale = GetSystemPreferredLocale();
      CStringNormalizer::m_lcidSystemLocale = SystemPreferredLocale;
    }
  }
  pv = 0;
  if ( SystemPreferredLocale == 1042
    && !(unsigned int)CScriptAutoDetection::HasScript(&g_scriptAutoDetection, a4, v7, v11) )
  {
    p_pv = &pv;
    v30 = 0;
    v31 = 1;
    v26 = (int)CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
                 (PMAPPING_SERVICE_INFO *)g_koreanDecomposition,
                 a4,
                 v7,
                 &v30) >= 0;
    if ( v31 )
    {
      v27 = *p_pv;
      *p_pv = v30;
      if ( v27 )
        CoTaskMemFree(v27);
    }
    if ( v26 )
    {
      a4 = (const wchar_t *)pv;
      v7 = -1;
      do
        ++v7;
      while ( *((_WORD *)pv + v7) );
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v12 = (unsigned __int16 *)((char *)this + 56);
  v13 = LCMapStringW(SystemPreferredLocale, v10, a4, v7, (LPWSTR)this + 28, 1024);
  if ( v13 <= 0 )
  {
    GetLastError();
    v19 = a5;
LABEL_20:
    j = 0;
    *v19 = 0;
    goto LABEL_16;
  }
  v14 = (char *)this + 56;
  for ( i = (*(_DWORD *)this >> 1) & 1; ; i = v17 )
  {
    v16 = *v14;
    if ( *v14 == 1 && i <= 0 )
      break;
    if ( v13 < 0 )
      break;
    ++v14;
    --v13;
    v17 = i - 1;
    if ( v16 != 1 )
      v17 = i;
  }
  v18 = (_DWORD)v14 - (_DWORD)this - 56;
  v19 = a5;
  if ( v18 <= 0 )
    goto LABEL_20;
  v20 = *a5;
  if ( v18 <= (int)*a5 )
  {
    v20 = v18;
    *a5 = v18;
  }
  memcpy_0(a6, (char *)this + 56, v20);
  v21 = v20 / 2;
  v22 = 0;
  for ( j = 0; v22 < v21; ++v22 )
    j = *v12++ + 4 * j;
LABEL_16:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v24 = pv;
  pv = 0;
  if ( v24 )
    CoTaskMemFree(v24);
  return j;
}

```

## disassembly

```asm
0x180056a80  push    rbp
0x180056a82  push    rbx
0x180056a83  push    rsi
0x180056a84  push    rdi
0x180056a85  push    r12
0x180056a87  push    r13
0x180056a89  push    r14
0x180056a8b  push    r15
0x180056a8d  mov     rbp, rsp
0x180056a90  sub     rsp, 58h
0x180056a94  mov     r15, r9
0x180056a97  mov     esi, r8d
0x180056a9a  mov     edi, edx
0x180056a9c  mov     r13, rcx
0x180056a9f  xor     r14d, r14d
0x180056aa2  mov     r12d, [rcx]
0x180056aa5  not     r12d
0x180056aa8  and     r12d, 2
0x180056aac  or      r12d, 8030401h
0x180056ab3  mov     ecx, edx; unsigned int
0x180056ab5  call    ?IsValidOrFallbackLocale@@YA_NK@Z; IsValidOrFallbackLocale(ulong)
0x180056aba  test    al, al
0x180056abc  jz      loc_180056C50
0x180056ac2  mov     [rbp+pv], r14
0x180056ac6  cmp     edi, 412h
0x180056acc  jz      loc_180056BCA
0x180056ad2  lea     rcx, [r13+8]; lpCriticalSection
0x180056ad6  call    cs:__imp_EnterCriticalSection
0x180056adc  lea     r14, [r13+38h]
0x180056ae0  mov     [rsp+58h+cchDest], 400h; cchDest
0x180056ae8  mov     [rsp+58h+lpDestStr], r14; lpDestStr
0x180056aed  mov     r9d, esi; cchSrc
0x180056af0  mov     r8, r15; lpSrcStr
0x180056af3  mov     edx, r12d; dwMapFlags
0x180056af6  mov     ecx, edi; Locale
0x180056af8  call    cs:__imp_LCMapStringW
0x180056afe  mov     r8d, eax
0x180056b01  xor     esi, esi
0x180056b03  test    eax, eax
0x180056b05  jle     loc_180056BB9
0x180056b0b  mov     rdx, r14
0x180056b0e  mov     ecx, [r13+0]
0x180056b12  shr     ecx, 1
0x180056b14  and     ecx, 1
0x180056b17  mov     r9b, [rdx]
0x180056b1a  cmp     r9b, 1
0x180056b1e  jz      short loc_180056B39
0x180056b20  test    r8d, r8d
0x180056b23  js      short loc_180056B3D
0x180056b25  inc     rdx
0x180056b28  dec     r8d
0x180056b2b  lea     eax, [rcx-1]
0x180056b2e  cmp     r9b, 1
0x180056b32  cmovnz  eax, ecx
0x180056b35  mov     ecx, eax
0x180056b37  jmp     short loc_180056B17
0x180056b39  test    ecx, ecx
0x180056b3b  jg      short loc_180056B20
0x180056b3d  sub     edx, r13d
0x180056b40  add     edx, 0FFFFFFC8h
0x180056b43  mov     rax, [rbp+arg_20]
0x180056b47  test    edx, edx
0x180056b49  jle     short loc_180056BC4
0x180056b4b  mov     edi, [rax]
0x180056b4d  cmp     edx, edi
0x180056b4f  jg      short loc_180056B55
0x180056b51  mov     edi, edx
0x180056b53  mov     [rax], edx
0x180056b55  movsxd  r8, edi; Size
0x180056b58  mov     rdx, r14; Src
0x180056b5b  mov     rcx, [rbp+arg_28]; void *
0x180056b5f  call    memcpy_0
0x180056b64  mov     eax, edi
0x180056b66  cdq
0x180056b67  mov     r8d, 2
0x180056b6d  idiv    r8d
0x180056b70  mov     edx, esi
0x180056b72  mov     edi, edx
0x180056b74  test    eax, eax
0x180056b76  jle     short loc_180056B88
0x180056b78  movzx   ecx, word ptr [r14]
0x180056b7c  lea     edi, [rcx+rdi*4]
0x180056b7f  add     r14, r8
0x180056b82  inc     edx
0x180056b84  cmp     edx, eax
0x180056b86  jl      short loc_180056B78
0x180056b88  lea     rcx, [r13+8]; lpCriticalSection
0x180056b8c  call    cs:__imp_LeaveCriticalSection
0x180056b92  nop
0x180056b93  mov     rcx, [rbp+pv]; pv
0x180056b97  mov     [rbp+pv], rsi
0x180056b9b  test    rcx, rcx
0x180056b9e  jz      short loc_180056BA6
0x180056ba0  call    cs:__imp_CoTaskMemFree
0x180056ba6  mov     eax, edi
0x180056ba8  add     rsp, 58h
0x180056bac  pop     r15
0x180056bae  pop     r14
0x180056bb0  pop     r13
0x180056bb2  pop     r12
0x180056bb4  pop     rdi
0x180056bb5  pop     rsi
0x180056bb6  pop     rbx
0x180056bb7  pop     rbp
0x180056bb8  retn
0x180056bb9  call    cs:__imp_GetLastError
0x180056bbf  nop
0x180056bc0  mov     rax, [rbp+arg_20]
0x180056bc4  mov     edi, esi
0x180056bc6  mov     [rax], esi
0x180056bc8  jmp     short loc_180056B88
0x180056bca  mov     r8d, esi; unsigned int
0x180056bcd  mov     rdx, r15; wchar_t *
0x180056bd0  lea     rcx, ?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; prgServices
0x180056bd7  call    ?HasScript@CScriptAutoDetection@@QEAAJPEB_WK0@Z; CScriptAutoDetection::HasScript(wchar_t const *,ulong,wchar_t const *)
0x180056bdc  test    eax, eax
0x180056bde  jnz     loc_180056AD2
0x180056be4  lea     rax, [rbp+pv]
0x180056be8  mov     [rbp+var_20], rax
0x180056bec  mov     [rbp+var_18], r14
0x180056bf0  mov     [rbp+var_10], 1
0x180056bf4  lea     r9, [rbp+var_18]; wchar_t **
0x180056bf8  mov     r8d, esi; unsigned int
0x180056bfb  mov     rdx, r15; wchar_t *
0x180056bfe  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; prgServices
0x180056c05  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEB_WKPEAPEA_W@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(wchar_t const *,ulong,wchar_t * *)
0x180056c0a  mov     ebx, eax
0x180056c0c  shr     ebx, 1Fh
0x180056c0f  xor     bl, 1
0x180056c12  cmp     [rbp+var_10], r14b
0x180056c16  jz      short loc_180056C31
0x180056c18  mov     r8, [rbp+var_20]
0x180056c1c  mov     rcx, [r8]; pv
0x180056c1f  mov     rdx, [rbp+var_18]
0x180056c23  mov     [r8], rdx
0x180056c26  test    rcx, rcx
0x180056c29  jz      short loc_180056C31
0x180056c2b  call    cs:__imp_CoTaskMemFree
0x180056c31  test    bl, bl
0x180056c33  jz      loc_180056AD2
0x180056c39  mov     r15, [rbp+pv]
0x180056c3d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180056c41  inc     rsi
0x180056c44  cmp     [r15+rsi*2], r14w
0x180056c49  jnz     short loc_180056C41
0x180056c4b  jmp     loc_180056AD2
0x180056c50  mov     edi, cs:?m_lcidSystemLocale@CStringNormalizer@@0KA; ulong CStringNormalizer::m_lcidSystemLocale
0x180056c56  test    edi, edi
0x180056c58  jnz     loc_180056AC2
0x180056c5e  call    ?GetSystemPreferredLocale@@YAKXZ; GetSystemPreferredLocale(void)
0x180056c63  mov     edi, eax
0x180056c65  mov     cs:?m_lcidSystemLocale@CStringNormalizer@@0KA, eax; ulong CStringNormalizer::m_lcidSystemLocale
0x180056c6b  jmp     loc_180056AC2
```

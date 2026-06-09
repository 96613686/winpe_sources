# CVariant::GetArrayData(void * *,ulong *)

- ea: `0x18000d330`
- end: `0x18000d51f`
- name: `?GetArrayData@CVariant@@AEAAJPEAPEAXPEAK@Z`
- size: `495`
- prototype: `HRESULT __fastcall(CVariant *this, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d528`

## callees

- `0x1800088f0`
- `0x1800096f0`
- `0x18000d330`
- `0x18000d610`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d404`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d4c1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d4c1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d3d7`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d3d7`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18000d3c5`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18000d45a`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18000d4d6`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18000d3c5`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18000d45a`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18000d4d6`

## pseudocode

```c
HRESULT __fastcall CVariant::GetArrayData(CVariant *this, void **a2, unsigned int *a3)
{
  int v3; // eax
  int v7; // r12d
  int NumElements; // r15d
  int v9; // eax
  __int64 v10; // r13
  HRESULT result; // eax
  SAFEARRAY *v12; // rcx
  int i; // eax
  UINT v14; // eax
  OLECHAR *v15; // rcx
  _WORD *v16; // rax
  char *v17; // rbx
  unsigned __int16 *v18; // r14
  HRESULT Element; // edi
  int v20; // r10d
  __int16 v21; // r11
  __int64 v22; // rax
  HRESULT v23; // eax
  BSTR bstrString; // [rsp+20h] [rbp-10h] BYREF
  SAFEARRAY *psa; // [rsp+28h] [rbp-8h]
  BSTR pv; // [rsp+70h] [rbp+40h] BYREF
  void **v27; // [rsp+78h] [rbp+48h]
  __int64 rgIndices; // [rsp+88h] [rbp+58h] BYREF

  v27 = a2;
  v3 = *((_WORD *)this + 4) & 0xDFFF;
  rgIndices = 0;
  if ( v3 == 31 || (v7 = 0, v3 == 8) )
    v7 = 1;
  NumElements = CVariant::GetNumElements(this);
  v9 = iTypeSize(*((_WORD *)this + 4));
  v10 = v9;
  if ( v9 < 1 )
    return -2147217407;
  v12 = (SAFEARRAY *)*((_QWORD *)this + 2);
  psa = v12;
  if ( v7 )
  {
    *a3 = 2;
    for ( i = 0; ; i = rgIndices + 1 )
    {
      LODWORD(rgIndices) = i;
      if ( i >= NumElements )
        break;
      pv = 0;
      result = SafeArrayGetElement(v12, (LONG *)&rgIndices, &pv);
      if ( result < 0 )
        return result;
      v14 = SysStringLen(pv);
      v15 = pv;
      *a3 += 2 * v14 + 2;
      SysFreeString(v15);
      v12 = psa;
    }
  }
  else
  {
    *a3 = NumElements * v9;
  }
  v16 = CoTaskMemAlloc(*a3);
  *a2 = v16;
  v17 = (char *)v16;
  if ( !v16 )
    return -2147217402;
  LODWORD(pv) = 0;
  *v16 = 0;
  v18 = v16;
  LODWORD(rgIndices) = 0;
  Element = 0;
  if ( NumElements > 0 )
  {
    while ( !Element )
    {
      if ( v7 )
      {
        bstrString = 0;
        Element = SafeArrayGetElement(psa, (LONG *)&rgIndices, &bstrString);
        if ( Element )
          break;
        StringCchCopyNW(
          v18,
          ((unsigned __int64)*a3 >> 1) - (((char *)v18 - (_BYTE *)*v27) >> 1),
          bstrString,
          (unsigned __int64)(*a3 - (unsigned int)pv) >> 1);
        v22 = -1;
        do
          ++v22;
        while ( v18[v22] != v21 );
        LODWORD(pv) = v20 + 2 * v22 + 2;
        v18 += v22 + 1;
        SysFreeString(bstrString);
        *v18 = 0;
      }
      else
      {
        v23 = SafeArrayGetElement(psa, (LONG *)&rgIndices, v17);
        v17 += v10;
        Element = v23;
      }
      LODWORD(rgIndices) = rgIndices + 1;
      if ( (int)rgIndices >= NumElements )
      {
        if ( !Element )
          return 0;
        break;
      }
    }
    CoTaskMemFree(*v27);
  }
  return 0;
}

```

## disassembly

```asm
0x18000d330  mov     [rsp-38h+arg_10], rbx
0x18000d335  mov     [rsp-38h+arg_8], rdx
0x18000d33a  push    rbp
0x18000d33b  push    rsi
0x18000d33c  push    rdi
0x18000d33d  push    r12
0x18000d33f  push    r13
0x18000d341  push    r14
0x18000d343  push    r15
0x18000d345  mov     rbp, rsp
0x18000d348  sub     rsp, 30h
0x18000d34c  movzx   eax, word ptr [rcx+8]
0x18000d350  xor     r14d, r14d
0x18000d353  btr     eax, 0Dh
0x18000d357  mov     [rbp+rgIndices], r14
0x18000d35b  mov     rsi, r8
0x18000d35e  mov     rdi, rdx
0x18000d361  mov     rbx, rcx
0x18000d364  cmp     eax, 1Fh
0x18000d367  jz      short loc_18000D371
0x18000d369  mov     r12d, r14d
0x18000d36c  cmp     eax, 8
0x18000d36f  jnz     short loc_18000D377
0x18000d371  mov     r12d, 1
0x18000d377  call    ?GetNumElements@CVariant@@QEAAKXZ; CVariant::GetNumElements(void)
0x18000d37c  movzx   ecx, word ptr [rbx+8]; unsigned __int16
0x18000d380  mov     r15d, eax
0x18000d383  call    ?iTypeSize@@YAHG@Z; iTypeSize(ushort)
0x18000d388  movsxd  r13, eax
0x18000d38b  cmp     r13d, 1
0x18000d38f  jge     short loc_18000D39B
0x18000d391  mov     eax, 80041001h
0x18000d396  jmp     loc_18000D507
0x18000d39b  mov     rcx, [rbx+10h]; psa
0x18000d39f  mov     [rbp+psa], rcx
0x18000d3a3  test    r12d, r12d
0x18000d3a6  jz      short loc_18000D3F9
0x18000d3a8  mov     dword ptr [rsi], 2
0x18000d3ae  mov     eax, r14d
0x18000d3b1  mov     dword ptr [rbp+rgIndices], eax
0x18000d3b4  cmp     eax, r15d
0x18000d3b7  jge     short loc_18000D402
0x18000d3b9  lea     r8, [rbp+pv]; pv
0x18000d3bd  mov     [rbp+pv], r14
0x18000d3c1  lea     rdx, [rbp+rgIndices]; rgIndices
0x18000d3c5  call    cs:__imp_SafeArrayGetElement
0x18000d3cb  test    eax, eax
0x18000d3cd  js      loc_18000D507
0x18000d3d3  mov     rcx, [rbp+pv]; pbstr
0x18000d3d7  call    cs:__imp_SysStringLen
0x18000d3dd  mov     rcx, [rbp+pv]; bstrString
0x18000d3e1  add     eax, eax
0x18000d3e3  add     eax, 2
0x18000d3e6  add     [rsi], eax
0x18000d3e8  call    cs:__imp_SysFreeString
0x18000d3ee  mov     eax, dword ptr [rbp+rgIndices]
0x18000d3f1  mov     rcx, [rbp+psa]
0x18000d3f5  inc     eax
0x18000d3f7  jmp     short loc_18000D3B1
0x18000d3f9  mov     eax, r13d
0x18000d3fc  imul    eax, r15d
0x18000d400  mov     [rsi], eax
0x18000d402  mov     ecx, [rsi]; cb
0x18000d404  call    cs:__imp_CoTaskMemAlloc
0x18000d40a  mov     [rdi], rax
0x18000d40d  mov     rbx, rax
0x18000d410  test    rax, rax
0x18000d413  jnz     short loc_18000D41F
0x18000d415  mov     eax, 80041006h
0x18000d41a  jmp     loc_18000D507
0x18000d41f  xor     ecx, ecx
0x18000d421  mov     dword ptr [rbp+pv], r14d
0x18000d425  mov     [rax], cx
0x18000d428  mov     r14, rax
0x18000d42b  mov     dword ptr [rbp+rgIndices], ecx
0x18000d42e  mov     edi, ecx
0x18000d430  test    r15d, r15d
0x18000d433  jle     loc_18000D505
0x18000d439  test    edi, edi
0x18000d43b  jnz     loc_18000D4F8
0x18000d441  lea     rdx, [rbp+rgIndices]; rgIndices
0x18000d445  test    r12d, r12d
0x18000d448  jz      loc_18000D4CF
0x18000d44e  mov     [rbp+bstrString], rcx
0x18000d452  lea     r8, [rbp+bstrString]; pv
0x18000d456  mov     rcx, [rbp+psa]; psa
0x18000d45a  call    cs:__imp_SafeArrayGetElement
0x18000d460  xor     r11d, r11d
0x18000d463  mov     edi, eax
0x18000d465  test    eax, eax
0x18000d467  jnz     loc_18000D4F8
0x18000d46d  mov     edx, [rsi]
0x18000d46f  mov     rcx, r14
0x18000d472  mov     rax, [rbp+arg_8]
0x18000d476  mov     r9d, edx
0x18000d479  mov     r10d, dword ptr [rbp+pv]
0x18000d47d  sub     r9d, r10d
0x18000d480  mov     r8, [rbp+bstrString]; unsigned __int16 *
0x18000d484  shr     rdx, 1
0x18000d487  sub     rcx, [rax]
0x18000d48a  sar     rcx, 1
0x18000d48d  sub     rdx, rcx; unsigned __int64
0x18000d490  shr     r9, 1; unsigned __int64
0x18000d493  mov     rcx, r14; unsigned __int16 *
0x18000d496  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000d49b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d49f  inc     rax
0x18000d4a2  cmp     [r14+rax*2], r11w
0x18000d4a7  jnz     short loc_18000D49F
0x18000d4a9  mov     rcx, [rbp+bstrString]; bstrString
0x18000d4ad  lea     r10d, [r10+rax*2]
0x18000d4b1  add     r10d, 2
0x18000d4b5  lea     r14, [r14+rax*2]
0x18000d4b9  mov     dword ptr [rbp+pv], r10d
0x18000d4bd  add     r14, 2
0x18000d4c1  call    cs:__imp_SysFreeString
0x18000d4c7  xor     ecx, ecx
0x18000d4c9  mov     [r14], cx
0x18000d4cd  jmp     short loc_18000D4E3
0x18000d4cf  mov     rcx, [rbp+psa]; psa
0x18000d4d3  mov     r8, rbx; pv
0x18000d4d6  call    cs:__imp_SafeArrayGetElement
0x18000d4dc  add     rbx, r13
0x18000d4df  mov     edi, eax
0x18000d4e1  xor     ecx, ecx
0x18000d4e3  mov     eax, dword ptr [rbp+rgIndices]
0x18000d4e6  inc     eax
0x18000d4e8  mov     dword ptr [rbp+rgIndices], eax
0x18000d4eb  cmp     eax, r15d
0x18000d4ee  jl      loc_18000D439
0x18000d4f4  test    edi, edi
0x18000d4f6  jz      short loc_18000D505
0x18000d4f8  mov     rax, [rbp+arg_8]
0x18000d4fc  mov     rcx, [rax]; pv
0x18000d4ff  call    cs:__imp_CoTaskMemFree
0x18000d505  xor     eax, eax
0x18000d507  mov     rbx, [rsp+30h+arg_10]
0x18000d50f  add     rsp, 30h
0x18000d513  pop     r15
0x18000d515  pop     r14
0x18000d517  pop     r13
0x18000d519  pop     r12
0x18000d51b  pop     rdi
0x18000d51c  pop     rsi
0x18000d51d  pop     rbp
0x18000d51e  retn
```

# CVssRegistryValueIterator::GetCurrentValueContent(ulong &)

- ea: `0x1800389c0`
- end: `0x180038d39`
- name: `?GetCurrentValueContent@CVssRegistryValueIterator@@QEAAXAEAK@Z`
- size: `889`
- prototype: `void __fastcall(CVssRegistryValueIterator *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18003ced0`

## callees

- `0x18000212c`
- `0x180033a8c`
- `0x180033c78`
- `0x180037080`
- `0x1800389c0`
- `0x18003a2b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180038b80`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180038b80`

## string_xrefs

- `0x1800389dd`: `base\stor\vss\modules\registry\registry.cxx`
- `0x1800389e9`: `CVssRegistryValueIterator::GetCurrentValueContent`
- `0x180038bbe`: `CVssRegistryValueIterator::GetCurrentValueContent`
- `0x180038a94`: `Unexpected error: attempting to read a value of the wrong type`

## pseudocode

```c
void __fastcall CVssRegistryValueIterator::GetCurrentValueContent(CVssRegistryValueIterator *this, unsigned int *a2)
{
  int v4; // edi
  LSTATUS v5; // eax
  unsigned int v6; // edi
  DWORD v7; // esi
  __int64 v8; // r14
  int v9; // r15d
  __int64 v10; // rbx
  int v11; // ebx
  DWORD v12; // edi
  LPDWORD lpReserved; // [rsp+20h] [rbp-E0h]
  LPDWORD lpType; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcbData; // [rsp+38h] [rbp-C8h]
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v17; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v18; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v19; // [rsp+60h] [rbp-A0h]
  int v20; // [rsp+68h] [rbp-98h]
  int v21; // [rsp+6Ch] [rbp-94h]
  int v22; // [rsp+70h] [rbp-90h]
  _BYTE v23[120]; // [rsp+78h] [rbp-88h] BYREF
  int v24; // [rsp+F0h] [rbp-10h]
  LPVOID v25[20]; // [rsp+100h] [rbp+0h] BYREF
  DWORD cchValueName; // [rsp+1B0h] [rbp+B0h] BYREF
  DWORD Type; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned int Data; // [rsp+1C8h] [rbp+C8h] BYREF

  v17 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v18 = L"CVssRegistryValueIterator::GetCurrentValueContent";
  v19 = L"REGREGSC";
  v20 = 955;
  v21 = 11;
  v22 = 255;
  v24 = 0x1000000;
  memset_0(v23, 0, sizeof(v23));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v25, (__int64)&v17, 0);
  CVssRegistryValueIterator::ReadCurrentValueDetails(this);
  if ( *((_DWORD *)this + 4) != 4 )
  {
    v17 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v18 = L"CVssRegistryValueIterator::GetCurrentValueContent";
    v19 = L"REGREGSC";
    v20 = 961;
    v21 = 11;
    v22 = 255;
    v24 = 0x1000000;
    memset_0(v23, 0, sizeof(v23));
    CVssFunctionTracer::TranslateGenericError(
      v25,
      &v17,
      2147549183LL,
      L"Unexpected error: attempting to read a value of the wrong type");
  }
  v4 = *((_DWORD *)this + 11);
  if ( v4 != 4 )
  {
    v17 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v18 = L"CVssRegistryValueIterator::GetCurrentValueContent";
    v19 = L"REGREGSC";
    v20 = 966;
    v21 = 11;
    v22 = 255;
    v24 = 0x1000000;
    memset_0(v23, 0, sizeof(v23));
    CVssFunctionTracer::TranslateGenericError(
      v25,
      &v17,
      2147549183LL,
      L"Unexpected error: unexpected DWORD size [%ld, %ld]",
      v4,
      4);
  }
  Data = 0;
  cchValueName = *((_DWORD *)this + 10);
  Type = 0;
  cbData = 4;
  v5 = RegEnumValueW(
         *(HKEY *)this,
         *((_DWORD *)this + 3),
         *((LPWSTR *)this + 4),
         &cchValueName,
         0,
         &Type,
         (LPBYTE)&Data,
         &cbData);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 != 259 )
    {
      v7 = cchValueName;
      v8 = *((_QWORD *)this + 4);
      v9 = *((_DWORD *)this + 3);
      v10 = *(_QWORD *)this;
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      v17 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v18 = L"CVssRegistryValueIterator::GetCurrentValueContent";
      v19 = L"REGREGSC";
      v20 = 997;
      v21 = 11;
      v22 = 255;
      v24 = 0x1000000;
      memset_0(v23, 0, sizeof(v23));
      LODWORD(lpcbData) = v7;
      LODWORD(lpType) = v9;
      CVssFunctionTracer::TranslateGenericError(
        v25,
        &v17,
        v6,
        L"RegEnumValue(%p,%lu,%p,%lu ...)",
        v10,
        lpType,
        v8,
        lpcbData);
    }
    v17 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v18 = L"CVssRegistryValueIterator::GetCurrentValueContent";
    v19 = L"REGREGSC";
    v20 = 995;
    v21 = 11;
    v22 = 255;
    v24 = 0x1000000;
    memset_0(v23, 0, sizeof(v23));
    LODWORD(lpType) = *((_DWORD *)this + 2);
    LODWORD(lpReserved) = *((_DWORD *)this + 3);
    CVssFunctionTracer::TranslateGenericError(
      v25,
      &v17,
      2147549183LL,
      L"Unexpected error: dwIndex out of scope %lu %lu",
      lpReserved,
      lpType);
  }
  v11 = *((_DWORD *)this + 4);
  v12 = Type;
  if ( Type != v11 )
  {
    v17 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v18 = L"CVssRegistryValueIterator::GetCurrentValueContent";
    v19 = L"REGREGSC";
    v20 = 989;
    v21 = 11;
    v22 = 255;
    v24 = 0x1000000;
    memset_0(v23, 0, sizeof(v23));
    LODWORD(lpType) = v11;
    LODWORD(lpReserved) = v12;
    CVssFunctionTracer::TranslateGenericError(
      v25,
      &v17,
      2147549183LL,
      L"Unexpected error: current value type changed in the meantime %lu %lu",
      lpReserved,
      lpType);
  }
  *a2 = Data;
  CVssFunctionTracer::~CVssFunctionTracer(v25);
}

```

## disassembly

```asm
0x1800389c0  push    rbp
0x1800389c2  push    rbx
0x1800389c3  push    rsi
0x1800389c4  push    rdi
0x1800389c5  push    r13
0x1800389c7  push    r14
0x1800389c9  push    r15
0x1800389cb  lea     rbp, [rsp-70h]
0x1800389d0  sub     rsp, 170h
0x1800389d7  mov     rsi, rdx
0x1800389da  mov     rbx, rcx
0x1800389dd  lea     r13, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x1800389e4  mov     [rsp+1A0h+var_150], r13
0x1800389e9  lea     r15, aCvssregistryva_4; "CVssRegistryValueIterator::GetCurrentVa"...
0x1800389f0  mov     [rsp+1A0h+var_148], r15
0x1800389f5  lea     rdi, aRegregsc; "REGREGSC"
0x1800389fc  mov     [rsp+1A0h+var_140], rdi
0x180038a01  mov     [rsp+1A0h+var_138], 3BBh
0x180038a09  mov     [rsp+1A0h+var_134], 0Bh
0x180038a11  mov     [rsp+1A0h+var_130], 0FFh
0x180038a19  mov     [rbp+0A0h+var_B0], 1000000h
0x180038a20  xor     edx, edx; Val
0x180038a22  lea     r8d, [rdx+78h]; Size
0x180038a26  lea     rcx, [rsp+1A0h+var_128]; void *
0x180038a2b  call    memset_0
0x180038a30  xor     r8d, r8d
0x180038a33  lea     rdx, [rsp+1A0h+var_150]
0x180038a38  lea     rcx, [rbp+0A0h+var_A0]
0x180038a3c  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180038a41  nop
0x180038a42  mov     rcx, rbx; this
0x180038a45  call    ?ReadCurrentValueDetails@CVssRegistryValueIterator@@AEAAXXZ; CVssRegistryValueIterator::ReadCurrentValueDetails(void)
0x180038a4a  mov     r14d, 4
0x180038a50  cmp     [rbx+10h], r14d
0x180038a54  jz      short loc_180038AB0
0x180038a56  mov     [rsp+1A0h+var_150], r13
0x180038a5b  mov     [rsp+1A0h+var_148], r15
0x180038a60  mov     [rsp+1A0h+var_140], rdi
0x180038a65  mov     [rsp+1A0h+var_138], 3C1h
0x180038a6d  mov     [rsp+1A0h+var_134], 0Bh
0x180038a75  mov     [rsp+1A0h+var_130], 0FFh
0x180038a7d  mov     [rbp+0A0h+var_B0], 1000000h
0x180038a84  xor     edx, edx; Val
0x180038a86  lea     r8d, [r14+74h]; Size
0x180038a8a  lea     rcx, [rsp+1A0h+var_128]; void *
0x180038a8f  call    memset_0
0x180038a94  lea     r9, aUnexpectedErro_3; "Unexpected error: attempting to read a "...
0x180038a9b  mov     r8d, 8000FFFFh
0x180038aa1  lea     rdx, [rsp+1A0h+var_150]
0x180038aa6  lea     rcx, [rbp+0A0h+var_A0]
0x180038aaa  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180038ab0  mov     edi, [rbx+2Ch]
0x180038ab3  cmp     edi, r14d
0x180038ab6  jz      short loc_180038B22
0x180038ab8  mov     [rsp+1A0h+var_150], r13
0x180038abd  mov     [rsp+1A0h+var_148], r15
0x180038ac2  lea     rax, aRegregsc; "REGREGSC"
0x180038ac9  mov     [rsp+1A0h+var_140], rax
0x180038ace  mov     [rsp+1A0h+var_138], 3C6h
0x180038ad6  mov     [rsp+1A0h+var_134], 0Bh
0x180038ade  mov     [rsp+1A0h+var_130], 0FFh
0x180038ae6  mov     [rbp+0A0h+var_B0], 1000000h
0x180038aed  xor     edx, edx; Val
0x180038aef  lea     r8d, [rdx+78h]; Size
0x180038af3  lea     rcx, [rsp+1A0h+var_128]; void *
0x180038af8  call    memset_0
0x180038afd  mov     [rsp+1A0h+lpType], r14
0x180038b02  mov     dword ptr [rsp+1A0h+lpReserved], edi
0x180038b06  lea     r9, aUnexpectedErro; "Unexpected error: unexpected DWORD size"...
0x180038b0d  mov     r8d, 8000FFFFh
0x180038b13  lea     rdx, [rsp+1A0h+var_150]
0x180038b18  lea     rcx, [rbp+0A0h+var_A0]
0x180038b1c  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180038b22  mov     [rbp+0A0h+Data], 0
0x180038b2c  mov     eax, [rbx+28h]
0x180038b2f  mov     [rbp+0A0h+cchValueName], eax
0x180038b35  mov     [rbp+0A0h+Type], 0
0x180038b3f  mov     [rsp+1A0h+cbData], r14d
0x180038b44  lea     rax, [rsp+1A0h+cbData]
0x180038b49  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x180038b4e  lea     rax, [rbp+0A0h+Data]
0x180038b55  mov     [rsp+1A0h+lpData], rax; lpData
0x180038b5a  lea     rax, [rbp+0A0h+Type]
0x180038b61  mov     [rsp+1A0h+lpType], rax; lpType
0x180038b66  mov     [rsp+1A0h+lpReserved], 0; lpReserved
0x180038b6f  lea     r9, [rbp+0A0h+cchValueName]; lpcchValueName
0x180038b76  mov     r8, [rbx+20h]; lpValueName
0x180038b7a  mov     edx, [rbx+0Ch]; dwIndex
0x180038b7d  mov     rcx, [rbx]; hKey
0x180038b80  call    cs:__imp_RegEnumValueW
0x180038b86  mov     edi, eax
0x180038b88  test    eax, eax
0x180038b8a  jz      loc_180038CA0
0x180038b90  cmp     eax, 103h
0x180038b95  jz      loc_180038C31
0x180038b9b  mov     esi, [rbp+0A0h+cchValueName]
0x180038ba1  mov     r14, [rbx+20h]
0x180038ba5  mov     r15d, [rbx+0Ch]
0x180038ba9  mov     rbx, [rbx]
0x180038bac  test    eax, eax
0x180038bae  jle     short loc_180038BB9
0x180038bb0  movzx   edi, ax
0x180038bb3  or      edi, 80070000h
0x180038bb9  mov     [rsp+1A0h+var_150], r13
0x180038bbe  lea     rax, aCvssregistryva_4; "CVssRegistryValueIterator::GetCurrentVa"...
0x180038bc5  mov     [rsp+1A0h+var_148], rax
0x180038bca  lea     rax, aRegregsc; "REGREGSC"
0x180038bd1  mov     [rsp+1A0h+var_140], rax
0x180038bd6  mov     [rsp+1A0h+var_138], 3E5h
0x180038bde  mov     [rsp+1A0h+var_134], 0Bh
0x180038be6  mov     [rsp+1A0h+var_130], 0FFh
0x180038bee  mov     [rbp+0A0h+var_B0], 1000000h
0x180038bf5  xor     edx, edx; Val
0x180038bf7  lea     r8d, [rdx+78h]; Size
0x180038bfb  lea     rcx, [rsp+1A0h+var_128]; void *
0x180038c00  call    memset_0
0x180038c05  mov     dword ptr [rsp+1A0h+lpcbData], esi
0x180038c09  mov     [rsp+1A0h+lpData], r14
0x180038c0e  mov     dword ptr [rsp+1A0h+lpType], r15d
0x180038c13  mov     [rsp+1A0h+lpReserved], rbx
0x180038c18  lea     r9, aRegenumvaluePL; "RegEnumValue(%p,%lu,%p,%lu ...)"
0x180038c1f  mov     r8d, edi
0x180038c22  lea     rdx, [rsp+1A0h+var_150]
0x180038c27  lea     rcx, [rbp+0A0h+var_A0]
0x180038c2b  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180038c31  mov     [rsp+1A0h+var_150], r13
0x180038c36  mov     [rsp+1A0h+var_148], r15
0x180038c3b  lea     rax, aRegregsc; "REGREGSC"
0x180038c42  mov     [rsp+1A0h+var_140], rax
0x180038c47  mov     [rsp+1A0h+var_138], 3E3h
0x180038c4f  mov     [rsp+1A0h+var_134], 0Bh
0x180038c57  mov     [rsp+1A0h+var_130], 0FFh
0x180038c5f  mov     [rbp+0A0h+var_B0], 1000000h
0x180038c66  xor     edx, edx; Val
0x180038c68  lea     r8d, [rdx+78h]; Size
0x180038c6c  lea     rcx, [rsp+1A0h+var_128]; void *
0x180038c71  call    memset_0
0x180038c76  mov     eax, [rbx+8]
0x180038c79  mov     dword ptr [rsp+1A0h+lpType], eax
0x180038c7d  mov     eax, [rbx+0Ch]
0x180038c80  mov     dword ptr [rsp+1A0h+lpReserved], eax
0x180038c84  lea     r9, aUnexpectedErro_8; "Unexpected error: dwIndex out of scope "...
0x180038c8b  mov     r8d, 8000FFFFh
0x180038c91  lea     rdx, [rsp+1A0h+var_150]
0x180038c96  lea     rcx, [rbp+0A0h+var_A0]
0x180038c9a  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180038ca0  mov     ebx, [rbx+10h]
0x180038ca3  mov     edi, [rbp+0A0h+Type]
0x180038ca9  cmp     edi, ebx
0x180038cab  jz      short loc_180038D16
0x180038cad  mov     [rsp+1A0h+var_150], r13
0x180038cb2  mov     [rsp+1A0h+var_148], r15
0x180038cb7  lea     rax, aRegregsc; "REGREGSC"
0x180038cbe  mov     [rsp+1A0h+var_140], rax
0x180038cc3  mov     [rsp+1A0h+var_138], 3DDh
0x180038ccb  mov     [rsp+1A0h+var_134], 0Bh
0x180038cd3  mov     [rsp+1A0h+var_130], 0FFh
0x180038cdb  mov     [rbp+0A0h+var_B0], 1000000h
0x180038ce2  xor     edx, edx; Val
0x180038ce4  lea     r8d, [rdx+78h]; Size
0x180038ce8  lea     rcx, [rsp+1A0h+var_128]; void *
0x180038ced  call    memset_0
0x180038cf2  mov     dword ptr [rsp+1A0h+lpType], ebx
0x180038cf6  mov     dword ptr [rsp+1A0h+lpReserved], edi
0x180038cfa  lea     r9, aUnexpectedErro_0; "Unexpected error: current value type ch"...
0x180038d01  mov     r8d, 8000FFFFh
0x180038d07  lea     rdx, [rsp+1A0h+var_150]
0x180038d0c  lea     rcx, [rbp+0A0h+var_A0]
0x180038d10  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180038d16  mov     eax, [rbp+0A0h+Data]
0x180038d1c  mov     [rsi], eax
0x180038d1e  lea     rcx, [rbp+0A0h+var_A0]; this
0x180038d22  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180038d27  add     rsp, 170h
0x180038d2e  pop     r15
0x180038d30  pop     r14
0x180038d32  pop     r13
0x180038d34  pop     rdi
0x180038d35  pop     rsi
0x180038d36  pop     rbx
0x180038d37  pop     rbp
0x180038d38  retn
```

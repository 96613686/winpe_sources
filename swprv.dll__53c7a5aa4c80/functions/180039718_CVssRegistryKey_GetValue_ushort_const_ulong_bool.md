# CVssRegistryKey::GetValue(ushort const *,ulong &,bool)

- ea: `0x180039718`
- end: `0x180039ac2`
- name: `?GetValue@CVssRegistryKey@@QEAA_NPEBGAEAK_N@Z`
- size: `938`
- prototype: `char __fastcall(HKEY *this, const unsigned __int16 *, unsigned int *, char)`
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000aa5c`
- `0x18000d968`
- `0x18000ffe0`
- `0x18001a0d0`
- `0x18001f898`
- `0x18003f1f4`

## callees

- `0x18000212c`
- `0x18001febc`
- `0x180033a8c`
- `0x180033c78`
- `0x180035f44`
- `0x180037080`
- `0x180039718`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800397e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800399df`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800397e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800399df`

## string_xrefs

- `0x18003973c`: `base\stor\vss\modules\registry\registry.cxx`
- `0x180039827`: `base\stor\vss\modules\registry\registry.cxx`
- `0x180039a0e`: `base\stor\vss\modules\registry\registry.cxx`
- `0x180039748`: `CVssRegistryKey::GetValue`
- `0x180039833`: `CVssRegistryKey::GetValue`
- `0x180039a1a`: `CVssRegistryKey::GetValue`
- `0x1800398ff`: `Expected REG_DWORD type for registry key %s value name %s. The present value has been ignored`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CVssRegistryKey::GetValue(HKEY *this, const unsigned __int16 *a2, unsigned int *a3, char a4)
{
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  DWORD v9; // r14d
  DWORD v10; // r15d
  HKEY v11; // r12
  HKEY v12; // rdi
  char v13; // dl
  DWORD v14; // ebx
  LSTATUS v15; // eax
  unsigned int v16; // ebx
  DWORD v17; // r14d
  DWORD v18; // r15d
  HKEY v19; // r12
  HKEY v20; // rdi
  char v21; // bl
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  DWORD v24; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[12]; // [rsp+54h] [rbp-ACh] BYREF
  const unsigned __int16 *v26; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v27; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v28; // [rsp+70h] [rbp-90h]
  int v29; // [rsp+78h] [rbp-88h]
  int v30; // [rsp+7Ch] [rbp-84h]
  int v31; // [rsp+80h] [rbp-80h]
  _BYTE v32[120]; // [rsp+88h] [rbp-78h] BYREF
  int v33; // [rsp+100h] [rbp+0h]
  LPVOID v34[20]; // [rsp+110h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+1C0h] [rbp+C0h] BYREF
  DWORD lpcbData; // [rsp+1D0h] [rbp+D0h] BYREF
  DWORD Type; // [rsp+1D8h] [rbp+D8h] BYREF

  LOBYTE(Type) = a4;
  v26 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v27 = L"CVssRegistryKey::GetValue";
  v28 = L"REGREGSC";
  v29 = 504;
  v30 = 11;
  v31 = 255;
  v33 = 0x1000000;
  memset_0(v32, 0, sizeof(v32));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v34, (__int64)&v26, 0);
  *a3 = 0;
  Type = 0;
  cbData = 0;
  v7 = RegQueryValueExW(this[1], a2, 0, &Type, 0, &cbData);
  v8 = v7;
  if ( v7 == 2 )
    goto LABEL_9;
  if ( v7 && v7 != 234 )
  {
    v9 = cbData;
    v10 = Type;
    v11 = this[3];
    v12 = this[1];
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    v26 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v27 = L"CVssRegistryKey::GetValue";
    v28 = L"REGREGSC";
    v29 = 535;
    v30 = 11;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(v32, 0, sizeof(v32));
    CVssFunctionTracer::TranslateGenericError(
      v34,
      &v26,
      v8,
      L"RegQueryValueExW(0x%08lx(%s),%s,0,[%lx],0,[%lu])",
      v12,
      v11,
      a2,
      v10,
      v9);
  }
  if ( Type != 4 )
  {
    v26 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v27 = L"CVssRegistryKey::GetValue";
    v28 = L"REGREGSC";
    v29 = 542;
    v30 = 11;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(v32, 0, sizeof(v32));
    CVssFunctionTracer::LogGenericWarning(
      v34,
      &v26,
      L"Expected REG_DWORD type for registry key %s value name %s. The present value has been ignored",
      this[3],
      a2);
LABEL_9:
    v13 = 0;
    goto LABEL_17;
  }
  v14 = cbData;
  if ( cbData != 4 )
  {
    v26 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v27 = L"CVssRegistryKey::GetValue";
    v28 = L"REGREGSC";
    v29 = 555;
    v30 = 11;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(v32, 0, sizeof(v32));
    LODWORD(lpData) = v14;
    CVssFunctionTracer::TranslateGenericError(
      v34,
      &v26,
      2147549183LL,
      L"Unexpected size %lu for a DWORD value 0x%08lx(%s),%s",
      lpData,
      this[1],
      this[3],
      a2);
  }
  v24 = 0;
  lpcbData = 4;
  *(_DWORD *)Data = 0;
  v15 = RegQueryValueExW(this[1], a2, 0, &v24, Data, &lpcbData);
  v16 = v15;
  if ( v15 )
  {
    v17 = lpcbData;
    v18 = v24;
    v19 = this[3];
    v20 = this[1];
    if ( v15 > 0 )
      v16 = (unsigned __int16)v15 | 0x80070000;
    v26 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v27 = L"CVssRegistryKey::GetValue";
    v28 = L"REGREGSC";
    v29 = 570;
    v30 = 11;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(v32, 0, sizeof(v32));
    CVssFunctionTracer::TranslateGenericError(
      v34,
      &v26,
      v16,
      L"RegQueryValueExW(0x%08lx(%s),%s,0,[%lx],0,[%lu])",
      v20,
      v19,
      a2,
      v18,
      v17);
  }
  *a3 = *(_DWORD *)Data;
  v13 = 1;
LABEL_17:
  v21 = CVssFunctionTracer::Exit((CVssFunctionTracer *)v34, v13);
  CVssFunctionTracer::~CVssFunctionTracer(v34);
  return v21;
}

```

## disassembly

```asm
0x180039718  mov     byte ptr [rsp-8+Type], r9b
0x18003971d  push    rbp
0x18003971e  push    rbx
0x18003971f  push    rsi
0x180039720  push    rdi
0x180039721  push    r12
0x180039723  push    r14
0x180039725  push    r15
0x180039727  lea     rbp, [rsp-80h]
0x18003972c  sub     rsp, 180h
0x180039733  mov     r14, r8
0x180039736  mov     rsi, rdx
0x180039739  mov     rdi, rcx
0x18003973c  lea     r15, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x180039743  mov     [rsp+1B0h+var_150], r15
0x180039748  lea     r12, aCvssregistryke_3; "CVssRegistryKey::GetValue"
0x18003974f  mov     [rsp+1B0h+var_148], r12
0x180039754  lea     rax, aRegregsc; "REGREGSC"
0x18003975b  mov     [rsp+1B0h+var_140], rax
0x180039760  mov     [rsp+1B0h+var_138], 1F8h
0x180039768  mov     [rsp+1B0h+var_134], 0Bh
0x180039770  mov     [rbp+0B0h+var_130], 0FFh
0x180039777  mov     [rbp+0B0h+var_B0], 1000000h
0x18003977e  xor     edx, edx; Val
0x180039780  lea     r8d, [rdx+78h]; Size
0x180039784  lea     rcx, [rbp+0B0h+var_128]; void *
0x180039788  call    memset_0
0x18003978d  xor     r8d, r8d
0x180039790  lea     rdx, [rsp+1B0h+var_150]
0x180039795  lea     rcx, [rbp+0B0h+var_A0]
0x180039799  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003979e  nop
0x18003979f  mov     dword ptr [r14], 0
0x1800397a6  mov     [rbp+0B0h+Type], 0
0x1800397b0  mov     [rbp+0B0h+cbData], 0
0x1800397ba  lea     rax, [rbp+0B0h+cbData]
0x1800397c1  mov     [rsp+1B0h+lpcbData], rax; lpcbData
0x1800397c6  mov     [rsp+1B0h+lpData], 0; lpData
0x1800397cf  lea     r9, [rbp+0B0h+Type]; lpType
0x1800397d6  xor     r8d, r8d; lpReserved
0x1800397d9  mov     rdx, rsi; lpValueName
0x1800397dc  mov     rcx, [rdi+8]; hKey
0x1800397e0  call    cs:__imp_RegQueryValueExW
0x1800397e6  mov     ebx, eax
0x1800397e8  cmp     eax, 2
0x1800397eb  jz      loc_180039914
0x1800397f1  test    eax, eax
0x1800397f3  jz      loc_1800398AA
0x1800397f9  cmp     eax, 0EAh
0x1800397fe  jz      loc_1800398AA
0x180039804  mov     r14d, [rbp+0B0h+cbData]
0x18003980b  mov     r15d, [rbp+0B0h+Type]
0x180039812  mov     r12, [rdi+18h]
0x180039816  mov     rdi, [rdi+8]
0x18003981a  test    eax, eax
0x18003981c  jle     short loc_180039827
0x18003981e  movzx   ebx, ax
0x180039821  or      ebx, 80070000h
0x180039827  lea     rax, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x18003982e  mov     [rsp+1B0h+var_150], rax
0x180039833  lea     rax, aCvssregistryke_3; "CVssRegistryKey::GetValue"
0x18003983a  mov     [rsp+1B0h+var_148], rax
0x18003983f  lea     rax, aRegregsc; "REGREGSC"
0x180039846  mov     [rsp+1B0h+var_140], rax
0x18003984b  mov     [rsp+1B0h+var_138], 217h
0x180039853  mov     [rsp+1B0h+var_134], 0Bh
0x18003985b  mov     [rbp+0B0h+var_130], 0FFh
0x180039862  mov     [rbp+0B0h+var_B0], 1000000h
0x180039869  xor     edx, edx; Val
0x18003986b  lea     r8d, [rdx+78h]; Size
0x18003986f  lea     rcx, [rbp+0B0h+var_128]; void *
0x180039873  call    memset_0
0x180039878  mov     [rsp+1B0h+var_170], r14d
0x18003987d  mov     dword ptr [rsp+1B0h+var_178], r15d
0x180039882  mov     [rsp+1B0h+var_180], rsi
0x180039887  mov     [rsp+1B0h+lpcbData], r12
0x18003988c  mov     [rsp+1B0h+lpData], rdi
0x180039891  lea     r9, aRegqueryvaluee_0; "RegQueryValueExW(0x%08lx(%s),%s,0,[%lx]"...
0x180039898  mov     r8d, ebx
0x18003989b  lea     rdx, [rsp+1B0h+var_150]
0x1800398a0  lea     rcx, [rbp+0B0h+var_A0]
0x1800398a4  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x1800398aa  cmp     [rbp+0B0h+Type], 4
0x1800398b1  jz      short loc_18003991B
0x1800398b3  mov     [rsp+1B0h+var_150], r15
0x1800398b8  mov     [rsp+1B0h+var_148], r12
0x1800398bd  lea     rax, aRegregsc; "REGREGSC"
0x1800398c4  mov     [rsp+1B0h+var_140], rax
0x1800398c9  mov     [rsp+1B0h+var_138], 21Eh
0x1800398d1  mov     [rsp+1B0h+var_134], 0Bh
0x1800398d9  mov     [rbp+0B0h+var_130], 0FFh
0x1800398e0  mov     [rbp+0B0h+var_B0], 1000000h
0x1800398e7  xor     edx, edx; Val
0x1800398e9  lea     r8d, [rdx+78h]; Size
0x1800398ed  lea     rcx, [rbp+0B0h+var_128]; void *
0x1800398f1  call    memset_0
0x1800398f6  mov     [rsp+1B0h+lpData], rsi
0x1800398fb  mov     r9, [rdi+18h]
0x1800398ff  lea     r8, aExpectedRegDwo; "Expected REG_DWORD type for registry ke"...
0x180039906  lea     rdx, [rsp+1B0h+var_150]
0x18003990b  lea     rcx, [rbp+0B0h+var_A0]
0x18003990f  call    ?LogGenericWarning@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::LogGenericWarning(CVssDebugInfo,ushort const *,...)
0x180039914  xor     edx, edx
0x180039916  jmp     loc_180039A9A
0x18003991b  mov     ebx, [rbp+0B0h+cbData]
0x180039921  cmp     ebx, 4
0x180039924  jz      short loc_1800399A0
0x180039926  mov     [rsp+1B0h+var_150], r15
0x18003992b  mov     [rsp+1B0h+var_148], r12
0x180039930  lea     rax, aRegregsc; "REGREGSC"
0x180039937  mov     [rsp+1B0h+var_140], rax
0x18003993c  mov     [rsp+1B0h+var_138], 22Bh
0x180039944  mov     [rsp+1B0h+var_134], 0Bh
0x18003994c  mov     [rbp+0B0h+var_130], 0FFh
0x180039953  mov     [rbp+0B0h+var_B0], 1000000h
0x18003995a  xor     edx, edx; Val
0x18003995c  lea     r8d, [rdx+78h]; Size
0x180039960  lea     rcx, [rbp+0B0h+var_128]; void *
0x180039964  call    memset_0
0x180039969  mov     [rsp+1B0h+var_178], rsi
0x18003996e  mov     rax, [rdi+18h]
0x180039972  mov     [rsp+1B0h+var_180], rax
0x180039977  mov     rax, [rdi+8]
0x18003997b  mov     [rsp+1B0h+lpcbData], rax
0x180039980  mov     dword ptr [rsp+1B0h+lpData], ebx
0x180039984  lea     r9, aUnexpectedSize; "Unexpected size %lu for a DWORD value 0"...
0x18003998b  mov     r8d, 8000FFFFh
0x180039991  lea     rdx, [rsp+1B0h+var_150]
0x180039996  lea     rcx, [rbp+0B0h+var_A0]
0x18003999a  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x1800399a0  mov     [rsp+1B0h+var_160], 0
0x1800399a8  mov     [rbp+0B0h+arg_10], 4
0x1800399b2  mov     dword ptr [rsp+1B0h+Data], 0
0x1800399ba  lea     rax, [rbp+0B0h+arg_10]
0x1800399c1  mov     [rsp+1B0h+lpcbData], rax; lpcbData
0x1800399c6  lea     rax, [rsp+1B0h+Data]
0x1800399cb  mov     [rsp+1B0h+lpData], rax; lpData
0x1800399d0  lea     r9, [rsp+1B0h+var_160]; lpType
0x1800399d5  xor     r8d, r8d; lpReserved
0x1800399d8  mov     rdx, rsi; lpValueName
0x1800399db  mov     rcx, [rdi+8]; hKey
0x1800399df  call    cs:__imp_RegQueryValueExW
0x1800399e5  mov     ebx, eax
0x1800399e7  test    eax, eax
0x1800399e9  jz      loc_180039A91
0x1800399ef  mov     r14d, [rbp+0B0h+arg_10]
0x1800399f6  mov     r15d, [rsp+1B0h+var_160]
0x1800399fb  mov     r12, [rdi+18h]
0x1800399ff  mov     rdi, [rdi+8]
0x180039a03  jle     short loc_180039A0E
0x180039a05  movzx   ebx, ax
0x180039a08  or      ebx, 80070000h
0x180039a0e  lea     rax, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x180039a15  mov     [rsp+1B0h+var_150], rax
0x180039a1a  lea     rax, aCvssregistryke_3; "CVssRegistryKey::GetValue"
0x180039a21  mov     [rsp+1B0h+var_148], rax
0x180039a26  lea     rax, aRegregsc; "REGREGSC"
0x180039a2d  mov     [rsp+1B0h+var_140], rax
0x180039a32  mov     [rsp+1B0h+var_138], 23Ah
0x180039a3a  mov     [rsp+1B0h+var_134], 0Bh
0x180039a42  mov     [rbp+0B0h+var_130], 0FFh
0x180039a49  mov     [rbp+0B0h+var_B0], 1000000h
0x180039a50  xor     edx, edx; Val
0x180039a52  lea     r8d, [rdx+78h]; Size
0x180039a56  lea     rcx, [rbp+0B0h+var_128]; void *
0x180039a5a  call    memset_0
0x180039a5f  mov     [rsp+1B0h+var_170], r14d
0x180039a64  mov     dword ptr [rsp+1B0h+var_178], r15d
0x180039a69  mov     [rsp+1B0h+var_180], rsi
0x180039a6e  mov     [rsp+1B0h+lpcbData], r12
0x180039a73  mov     [rsp+1B0h+lpData], rdi
0x180039a78  lea     r9, aRegqueryvaluee_0; "RegQueryValueExW(0x%08lx(%s),%s,0,[%lx]"...
0x180039a7f  mov     r8d, ebx
0x180039a82  lea     rdx, [rsp+1B0h+var_150]
0x180039a87  lea     rcx, [rbp+0B0h+var_A0]
0x180039a8b  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180039a91  mov     eax, dword ptr [rsp+1B0h+Data]
0x180039a95  mov     [r14], eax
0x180039a98  mov     dl, 1; bool
0x180039a9a  lea     rcx, [rbp+0B0h+var_A0]; this
0x180039a9e  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x180039aa3  mov     bl, al
0x180039aa5  lea     rcx, [rbp+0B0h+var_A0]; this
0x180039aa9  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180039aae  mov     al, bl
0x180039ab0  add     rsp, 180h
0x180039ab7  pop     r15
0x180039ab9  pop     r14
0x180039abb  pop     r12
0x180039abd  pop     rdi
0x180039abe  pop     rsi
0x180039abf  pop     rbx
0x180039ac0  pop     rbp
0x180039ac1  retn
```

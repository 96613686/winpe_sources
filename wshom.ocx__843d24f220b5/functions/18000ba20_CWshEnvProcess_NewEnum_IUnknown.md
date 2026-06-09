# CWshEnvProcess::_NewEnum(IUnknown * *)

- ea: `0x18000ba20`
- end: `0x18000bc4c`
- name: `?_NewEnum@CWshEnvProcess@@UEAAJPEAPEAUIUnknown@@@Z`
- size: `556`
- prototype: `__int64 __fastcall(CWshEnvProcess *__hidden this, struct IUnknown **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180009b40`
- `0x18000ba20`
- `0x18000df6c`
- `0x180011010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000bb23`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bb23`
- `OLEAUT32!__imp_VariantClear` at `0x18000bba1`
- `OLEAUT32!__imp_VariantClear` at `0x18000bba1`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000bc10`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000bc10`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000bb95`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000bb95`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000bae3`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000bae3`
- `KERNEL32!FreeEnvironmentStringsW` at `0x18000bc2c`
- `KERNEL32!FreeEnvironmentStringsW` at `0x18000bc2c`
- `KERNEL32!GetEnvironmentStrings` at `0x18000baae`
- `KERNEL32!GetEnvironmentStrings` at `0x18000baae`
- `KERNEL32!GetEnvironmentStringsW` at `0x18000ba73`
- `KERNEL32!GetEnvironmentStringsW` at `0x18000ba73`
- `KERNEL32!FreeEnvironmentStringsA` at `0x18000bc1e`
- `KERNEL32!FreeEnvironmentStringsA` at `0x18000bc1e`

## pseudocode

```c
__int64 __fastcall CWshEnvProcess::_NewEnum(CWshEnvProcess *this, struct IUnknown **a2)
{
  signed int v3; // r12d
  LPWCH EnvironmentStringsW; // rax
  WCHAR *v5; // rsi
  HRESULT v6; // ebx
  CHAR *v7; // r14
  __int64 v8; // rcx
  LPCH EnvironmentStrings; // rax
  __int64 v10; // rcx
  SAFEARRAY *Vector; // r13
  const CHAR *v12; // r15
  const OLECHAR *v13; // rdi
  LONG i; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  int v17; // eax
  struct CEnumVARIANT *v18; // rdi
  VARIANTARG pv; // [rsp+20h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+90h] [rbp+50h] BYREF
  struct CEnumVARIANT *v22; // [rsp+98h] [rbp+58h] BYREF

  rgIndices = 0;
  v22 = 0;
  memset(&pv, 0, sizeof(pv));
  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v3 = 0;
  if ( !Global::g_fWindowsNT )
  {
    EnvironmentStrings = GetEnvironmentStrings();
    v7 = EnvironmentStrings;
    if ( !EnvironmentStrings )
      return (unsigned int)-2147467259;
    v5 = 0;
    while ( *EnvironmentStrings )
    {
      ++v3;
      v10 = -1;
      do
        ++v10;
      while ( EnvironmentStrings[v10] );
      EnvironmentStrings += v10 + 1;
    }
LABEL_18:
    Vector = SafeArrayCreateVector(0xCu, 0, v3);
    if ( Vector )
    {
      v12 = v7;
      rgIndices = 0;
      v13 = v5;
      for ( i = 0; i < v3; i = ++rgIndices )
      {
        pv.vt = 8;
        if ( Global::g_fWindowsNT )
        {
          pv.llVal = (LONGLONG)SysAllocString(v13);
          if ( !pv.llVal )
          {
            v6 = -2147024882;
            goto LABEL_45;
          }
          if ( v13 )
          {
            v15 = -1;
            do
              ++v15;
            while ( v13[v15] );
          }
          else
          {
            v15 = 0;
          }
          v13 += v15 + 1;
        }
        else
        {
          v6 = PSZToBSTR(v12, &pv.bstrVal);
          if ( v6 < 0 )
            goto LABEL_45;
          if ( v12 )
          {
            v16 = -1;
            do
              ++v16;
            while ( v12[v16] );
          }
          else
          {
            v16 = 0;
          }
          v12 += v16 + 1;
        }
        v6 = SafeArrayPutElement(Vector, &rgIndices, &pv);
        VariantClear(&pv);
        if ( v6 < 0 )
          goto LABEL_45;
      }
      v17 = CEnumVARIANT::Create(Vector, &v22);
      v18 = v22;
      v6 = v17;
      if ( v17 >= 0 )
      {
        v6 = (**(__int64 (__fastcall ***)(struct CEnumVARIANT *, GUID *, struct IUnknown **))v22)(
               v22,
               &IID_IUnknown,
               a2);
        if ( v6 >= 0 )
          v6 = 0;
      }
      if ( v18 )
        (*(void (__fastcall **)(struct CEnumVARIANT *))(*(_QWORD *)v18 + 16LL))(v18);
LABEL_45:
      SafeArrayDestroy(Vector);
    }
    else
    {
      v6 = -2147024882;
    }
    if ( v7 )
      FreeEnvironmentStringsA(v7);
    if ( v5 )
      FreeEnvironmentStringsW(v5);
    return (unsigned int)v6;
  }
  EnvironmentStringsW = GetEnvironmentStringsW();
  v5 = EnvironmentStringsW;
  if ( EnvironmentStringsW )
  {
    v7 = 0;
    while ( *EnvironmentStringsW )
    {
      ++v3;
      v8 = -1;
      do
        ++v8;
      while ( EnvironmentStringsW[v8] );
      EnvironmentStringsW += v8 + 1;
    }
    goto LABEL_18;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x18000ba20  mov     [rsp-38h+arg_0], rbx
0x18000ba25  mov     [rsp-38h+arg_8], rdx
0x18000ba2a  push    rbp
0x18000ba2b  push    rsi
0x18000ba2c  push    rdi
0x18000ba2d  push    r12
0x18000ba2f  push    r13
0x18000ba31  push    r14
0x18000ba33  push    r15
0x18000ba35  mov     rbp, rsp
0x18000ba38  sub     rsp, 40h
0x18000ba3c  xor     ebx, ebx
0x18000ba3e  xor     ecx, ecx
0x18000ba40  mov     [rbp+var_10], rcx
0x18000ba44  xorps   xmm0, xmm0
0x18000ba47  mov     [rbp+rgIndices], ebx
0x18000ba4a  mov     [rbp+arg_18], rbx
0x18000ba4e  movups  [rbp+pv], xmm0
0x18000ba52  test    rdx, rdx
0x18000ba55  jnz     short loc_18000BA61
0x18000ba57  mov     eax, 80004003h
0x18000ba5c  jmp     loc_18000BC34
0x18000ba61  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000ba65  mov     [rdx], rbx
0x18000ba68  cmp     cs:?g_fWindowsNT@Global@@2_NA, bl; bool Global::g_fWindowsNT
0x18000ba6e  mov     r12d, ebx
0x18000ba71  jz      short loc_18000BAAE
0x18000ba73  call    cs:__imp_GetEnvironmentStringsW
0x18000ba79  mov     rsi, rax
0x18000ba7c  test    rax, rax
0x18000ba7f  jnz     short loc_18000BA8B
0x18000ba81  mov     ebx, 80004005h
0x18000ba86  jmp     loc_18000BC32
0x18000ba8b  mov     r14, rbx
0x18000ba8e  jmp     short loc_18000BAA7
0x18000ba90  inc     r12d
0x18000ba93  mov     rcx, rdi
0x18000ba96  inc     rcx
0x18000ba99  cmp     [rax+rcx*2], bx
0x18000ba9d  jnz     short loc_18000BA96
0x18000ba9f  lea     rax, [rax+rcx*2]
0x18000baa3  add     rax, 2
0x18000baa7  cmp     [rax], bx
0x18000baaa  jnz     short loc_18000BA90
0x18000baac  jmp     short loc_18000BAD9
0x18000baae  call    cs:__imp_GetEnvironmentStrings
0x18000bab4  mov     r14, rax
0x18000bab7  test    rax, rax
0x18000baba  jz      short loc_18000BA81
0x18000babc  mov     rsi, rbx
0x18000babf  jmp     short loc_18000BAD5
0x18000bac1  inc     r12d
0x18000bac4  mov     rcx, rdi
0x18000bac7  inc     rcx
0x18000baca  cmp     [rax+rcx], bl
0x18000bacd  jnz     short loc_18000BAC7
0x18000bacf  inc     rax
0x18000bad2  add     rax, rcx
0x18000bad5  cmp     [rax], bl
0x18000bad7  jnz     short loc_18000BAC1
0x18000bad9  mov     ecx, 0Ch; vt
0x18000bade  mov     r8d, r12d; cElements
0x18000bae1  xor     edx, edx; lLbound
0x18000bae3  call    cs:__imp_SafeArrayCreateVector
0x18000bae9  mov     r13, rax
0x18000baec  test    rax, rax
0x18000baef  jnz     short loc_18000BAFB
0x18000baf1  mov     ebx, 8007000Eh
0x18000baf6  jmp     loc_18000BC16
0x18000bafb  mov     r15, r14
0x18000bafe  mov     [rbp+rgIndices], ebx
0x18000bb01  mov     rdi, rsi
0x18000bb04  mov     eax, ebx
0x18000bb06  cmp     eax, r12d
0x18000bb09  jge     loc_18000BBC1
0x18000bb0f  cmp     cs:?g_fWindowsNT@Global@@2_NA, bl; bool Global::g_fWindowsNT
0x18000bb15  mov     eax, 8
0x18000bb1a  mov     word ptr [rbp+pv], ax
0x18000bb1e  jz      short loc_18000BB57
0x18000bb20  mov     rcx, rdi; psz
0x18000bb23  call    cs:__imp_SysAllocString
0x18000bb29  mov     qword ptr [rbp+pv+8], rax
0x18000bb2d  test    rax, rax
0x18000bb30  jz      loc_18000BBBA
0x18000bb36  test    rdi, rdi
0x18000bb39  jz      short loc_18000BB4A
0x18000bb3b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bb3f  inc     rax
0x18000bb42  cmp     [rdi+rax*2], bx
0x18000bb46  jnz     short loc_18000BB3F
0x18000bb48  jmp     short loc_18000BB4D
0x18000bb4a  mov     rax, rbx
0x18000bb4d  lea     rdi, [rdi+rax*2]
0x18000bb51  add     rdi, 2
0x18000bb55  jmp     short loc_18000BB8A
0x18000bb57  lea     rdx, [rbp+pv+8]; unsigned __int16 **
0x18000bb5b  mov     rcx, r15; lpMultiByteStr
0x18000bb5e  call    ?PSZToBSTR@@YAJPEBDPEAPEAG@Z; PSZToBSTR(char const *,ushort * *)
0x18000bb63  mov     ebx, eax
0x18000bb65  test    eax, eax
0x18000bb67  js      loc_18000BC0D
0x18000bb6d  test    r15, r15
0x18000bb70  jz      short loc_18000BB82
0x18000bb72  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bb76  inc     rax
0x18000bb79  cmp     byte ptr [r15+rax], 0
0x18000bb7e  jnz     short loc_18000BB76
0x18000bb80  jmp     short loc_18000BB84
0x18000bb82  xor     eax, eax
0x18000bb84  inc     r15
0x18000bb87  add     r15, rax
0x18000bb8a  lea     r8, [rbp+pv]; pv
0x18000bb8e  mov     rcx, r13; psa
0x18000bb91  lea     rdx, [rbp+rgIndices]; rgIndices
0x18000bb95  call    cs:__imp_SafeArrayPutElement
0x18000bb9b  lea     rcx, [rbp+pv]; pvarg
0x18000bb9f  mov     ebx, eax
0x18000bba1  call    cs:__imp_VariantClear
0x18000bba7  test    ebx, ebx
0x18000bba9  js      short loc_18000BC0D
0x18000bbab  mov     eax, [rbp+rgIndices]
0x18000bbae  inc     eax
0x18000bbb0  mov     [rbp+rgIndices], eax
0x18000bbb3  xor     ebx, ebx
0x18000bbb5  jmp     loc_18000BB06
0x18000bbba  mov     ebx, 8007000Eh
0x18000bbbf  jmp     short loc_18000BC0D
0x18000bbc1  lea     rdx, [rbp+arg_18]; struct CEnumVARIANT **
0x18000bbc5  mov     rcx, r13; psa
0x18000bbc8  call    ?Create@CEnumVARIANT@@SAJPEAUtagSAFEARRAY@@PEAPEAV1@@Z; CEnumVARIANT::Create(tagSAFEARRAY *,CEnumVARIANT * *)
0x18000bbcd  mov     rdi, [rbp+arg_18]
0x18000bbd1  mov     ebx, eax
0x18000bbd3  test    eax, eax
0x18000bbd5  js      short loc_18000BBF9
0x18000bbd7  mov     rax, [rdi]
0x18000bbda  lea     rdx, IID_IUnknown
0x18000bbe1  mov     r8, [rbp+arg_8]
0x18000bbe5  mov     rcx, rdi
0x18000bbe8  mov     rax, [rax]
0x18000bbeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbf0  mov     ebx, eax
0x18000bbf2  xor     eax, eax
0x18000bbf4  test    ebx, ebx
0x18000bbf6  cmovns  ebx, eax
0x18000bbf9  test    rdi, rdi
0x18000bbfc  jz      short loc_18000BC0D
0x18000bbfe  mov     rax, [rdi]
0x18000bc01  mov     rcx, rdi
0x18000bc04  mov     rax, [rax+10h]
0x18000bc08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc0d  mov     rcx, r13; psa
0x18000bc10  call    cs:__imp_SafeArrayDestroy
0x18000bc16  test    r14, r14
0x18000bc19  jz      short loc_18000BC24
0x18000bc1b  mov     rcx, r14; penv
0x18000bc1e  call    cs:__imp_FreeEnvironmentStringsA
0x18000bc24  test    rsi, rsi
0x18000bc27  jz      short loc_18000BC32
0x18000bc29  mov     rcx, rsi; penv
0x18000bc2c  call    cs:__imp_FreeEnvironmentStringsW
0x18000bc32  mov     eax, ebx
0x18000bc34  mov     rbx, [rsp+40h+arg_0]
0x18000bc3c  add     rsp, 40h
0x18000bc40  pop     r15
0x18000bc42  pop     r14
0x18000bc44  pop     r13
0x18000bc46  pop     r12
0x18000bc48  pop     rdi
0x18000bc49  pop     rsi
0x18000bc4a  pop     rbp
0x18000bc4b  retn
```

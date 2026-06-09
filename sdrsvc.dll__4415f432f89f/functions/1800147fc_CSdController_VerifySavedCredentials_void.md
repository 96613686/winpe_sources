# CSdController::_VerifySavedCredentials(void)

- ea: `0x1800147fc`
- end: `0x1800148d6`
- name: `?_VerifySavedCredentials@CSdController@@AEAAJXZ`
- size: `218`
- prototype: `__int64 __fastcall(CSdController *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011b84`

## callees

- `0x180014184`
- `0x1800147fc`
- `0x18001586c`
- `0x180015974`
- `0x18001b0e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001487d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800148b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001487d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800148b0`

## pseudocode

```c
__int64 __fastcall CSdController::_VerifySavedCredentials(CSdController *this)
{
  int CredsFromRegistry; // eax
  WCHAR *v2; // rbx
  bool v3; // sf
  __int16 v4; // ax
  __int64 v5; // rax
  __int64 v6; // rcx
  WCHAR *i; // rax
  unsigned int v8; // ebx
  int v10; // [rsp+20h] [rbp-40h] BYREF
  __int16 v11; // [rsp+24h] [rbp-3Ch]
  __int16 v12; // [rsp+26h] [rbp-3Ah]
  LPVOID pv; // [rsp+70h] [rbp+10h] BYREF
  LPCWSTR lpszPassword; // [rsp+78h] [rbp+18h] BYREF

  pv = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "CSdController::_VerifySavedCredentials", 2540, 0);
  pv = 0;
  lpszPassword = 0;
  CredsFromRegistry = ReadCredsFromRegistry((unsigned __int16 **)&pv, (unsigned __int16 **)&lpszPassword);
  v2 = (WCHAR *)lpszPassword;
  v3 = CredsFromRegistry < 0;
  v10 = CredsFromRegistry;
  v4 = 2549;
  if ( v3 || (v11 = 2549, v10 = CSdController::_VerifyCreds((wchar_t *)pv, lpszPassword), v4 = 2550, v10 < 0) )
    v12 = v4;
  else
    v11 = 2550;
  CoTaskMemFree(pv);
  if ( v2 )
  {
    v5 = -1;
    do
      ++v5;
    while ( v2[v5] );
    v6 = 2 * v5;
    for ( i = v2; v6; --v6 )
    {
      *(_BYTE *)i = 0;
      i = (WCHAR *)((char *)i + 1);
    }
    CoTaskMemFree(v2);
  }
  v8 = v10;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10);
  return v8;
}

```

## disassembly

```asm
0x1800147fc  mov     [rsp-8+arg_10], rbx
0x180014801  mov     [rsp-8+arg_18], rdi
0x180014806  mov     [rsp-8+pv], rcx
0x18001480b  push    rbp
0x18001480c  mov     rbp, rsp
0x18001480f  sub     rsp, 60h
0x180014813  xor     r9d, r9d; unsigned __int16
0x180014816  lea     rdx, aCsdcontrollerV_2; "CSdController::_VerifySavedCredentials"
0x18001481d  mov     r8d, 9ECh; unsigned __int16
0x180014823  lea     rcx, [rbp+var_40]; this
0x180014827  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001482c  xor     edi, edi
0x18001482e  lea     rdx, [rbp+lpszPassword]; unsigned __int16 **
0x180014832  lea     rcx, [rbp+pv]; unsigned __int16 **
0x180014836  mov     [rbp+pv], rdi
0x18001483a  mov     [rbp+lpszPassword], rdi
0x18001483e  call    ?ReadCredsFromRegistry@@YAJPEAPEAG0@Z; ReadCredsFromRegistry(ushort * *,ushort * *)
0x180014843  mov     rbx, [rbp+lpszPassword]
0x180014847  test    eax, eax
0x180014849  mov     [rbp+var_40], eax
0x18001484c  mov     eax, 9F5h
0x180014851  jns     short loc_180014859
0x180014853  mov     [rbp+var_3A], ax
0x180014857  jmp     short loc_180014879
0x180014859  mov     rcx, [rbp+pv]; Str
0x18001485d  mov     rdx, rbx; lpszPassword
0x180014860  mov     [rbp+var_3C], ax
0x180014864  call    ?_VerifyCreds@CSdController@@CAJPEBG0@Z; CSdController::_VerifyCreds(ushort const *,ushort const *)
0x180014869  mov     [rbp+var_40], eax
0x18001486c  test    eax, eax
0x18001486e  mov     eax, 9F6h
0x180014873  js      short loc_180014853
0x180014875  mov     [rbp+var_3C], ax
0x180014879  mov     rcx, [rbp+pv]; pv
0x18001487d  call    cs:__imp_CoTaskMemFree
0x180014883  test    rbx, rbx
0x180014886  jz      short loc_1800148B6
0x180014888  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001488c  inc     rax
0x18001488f  cmp     [rbx+rax*2], di
0x180014893  jnz     short loc_18001488C
0x180014895  lea     rcx, [rax+rax]
0x180014899  mov     rax, rbx
0x18001489c  test    rcx, rcx
0x18001489f  jz      short loc_1800148AD
0x1800148a1  mov     [rax], dil
0x1800148a4  inc     rax
0x1800148a7  sub     rcx, 1
0x1800148ab  jnz     short loc_1800148A1
0x1800148ad  mov     rcx, rbx; pv
0x1800148b0  call    cs:__imp_CoTaskMemFree
0x1800148b6  mov     ebx, [rbp+var_40]
0x1800148b9  lea     rcx, [rbp+var_40]; this
0x1800148bd  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800148c2  lea     r11, [rsp+60h+var_s0]
0x1800148c7  mov     eax, ebx
0x1800148c9  mov     rbx, [r11+20h]
0x1800148cd  mov     rdi, [r11+28h]
0x1800148d1  mov     rsp, r11
0x1800148d4  pop     rbp
0x1800148d5  retn
```

# CSdBackupImpl::_PopulateCompressionExtensionsFromRegistry(void)

- ea: `0x18001c078`
- end: `0x18001c1bf`
- name: `?_PopulateCompressionExtensionsFromRegistry@CSdBackupImpl@@AEAAJXZ`
- size: `327`
- prototype: `__int64 __fastcall(CSdBackupImpl *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800189ac`

## callees

- `0x18000b654`
- `0x180012998`
- `0x18001c078`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180088228`
- `0x180094190`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001c14b`
- `ole32!CoTaskMemFree` at `0x18001c197`
- `ole32!CoTaskMemFree` at `0x18001c1a2`
- `ole32!CoTaskMemFree` at `0x18001c14b`
- `ole32!CoTaskMemFree` at `0x18001c197`
- `ole32!CoTaskMemFree` at `0x18001c1a2`

## string_xrefs

- `0x18001c119`: `IncludeExtensionAsCompressed`
- `0x18001c15d`: `ExcludeExtensionAsCompressed`
- `0x18001c093`: `CSdBackupImpl::_PopulateCompressionExtensionsFromRegistry`

## pseudocode

```c
__int64 __fastcall CSdBackupImpl::_PopulateCompressionExtensionsFromRegistry(CSdBackupImpl *this)
{
  void *v2; // rbx
  struct CSxStringMap **v3; // rsi
  CSxStringMap *v4; // rcx
  __int16 v5; // ax
  CSxStringMap *v6; // rcx
  int ExtensionsListFromReg; // eax
  unsigned int v8; // ebx
  int Instance; // [rsp+20h] [rbp-48h] BYREF
  __int16 v11; // [rsp+24h] [rbp-44h]
  __int16 v12; // [rsp+26h] [rbp-42h]
  LPVOID pv; // [rsp+90h] [rbp+28h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&Instance,
    "CSdBackupImpl::_PopulateCompressionExtensionsFromRegistry",
    1362,
    1);
  v2 = 0;
  pv = 0;
  v3 = (struct CSxStringMap **)((char *)this + 712);
  v4 = (CSxStringMap *)*((_QWORD *)this + 89);
  if ( v4 )
  {
    *v3 = 0;
    CSxStringMap::Release(v4);
  }
  Instance = CSxStringMap::CreateInstance((struct CSxStringMap **)this + 89);
  v5 = 1370;
  if ( Instance < 0 )
    goto LABEL_4;
  v11 = 1370;
  v6 = (CSxStringMap *)*((_QWORD *)this + 90);
  if ( v6 )
  {
    *((_QWORD *)this + 90) = 0;
    CSxStringMap::Release(v6);
  }
  Instance = CSxStringMap::CreateInstance((struct CSxStringMap **)this + 90);
  v5 = 1371;
  if ( Instance < 0 )
    goto LABEL_4;
  v11 = 1371;
  if ( (int)ReadExtensionsListFromReg(L"IncludeExtensionAsCompressed", (unsigned __int16 **)&pv) >= 0 )
  {
    v2 = pv;
    Instance = SxConvertMultiStringToMap((const unsigned __int16 *)pv, *v3);
    v5 = 1381;
    if ( Instance < 0 )
      goto LABEL_4;
    v11 = 1381;
    CoTaskMemFree(v2);
    pv = 0;
  }
  ExtensionsListFromReg = ReadExtensionsListFromReg(L"ExcludeExtensionAsCompressed", (unsigned __int16 **)&pv);
  v2 = pv;
  if ( ExtensionsListFromReg < 0 )
    goto LABEL_14;
  Instance = SxConvertMultiStringToMap((const unsigned __int16 *)pv, *((struct CSxStringMap **)this + 90));
  v5 = 1398;
  if ( Instance >= 0 )
  {
    v11 = 1398;
    CoTaskMemFree(v2);
    v2 = 0;
    goto LABEL_14;
  }
LABEL_4:
  v12 = v5;
LABEL_14:
  CoTaskMemFree(v2);
  v8 = Instance;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&Instance);
  return v8;
}

```

## disassembly

```asm
0x18001c078  push    rbp
0x18001c07a  push    rbx
0x18001c07b  push    rsi
0x18001c07c  push    rdi
0x18001c07d  mov     rbp, rsp
0x18001c080  sub     rsp, 68h
0x18001c084  mov     rdi, rcx
0x18001c087  mov     r9d, 1; unsigned __int16
0x18001c08d  mov     r8d, 552h; unsigned __int16
0x18001c093  lea     rdx, aCsdbackupimplP_0; "CSdBackupImpl::_PopulateCompressionExte"...
0x18001c09a  lea     rcx, [rbp+var_48]; this
0x18001c09e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001c0a3  xor     ebx, ebx
0x18001c0a5  mov     [rbp+pv], rbx
0x18001c0a9  lea     rsi, [rdi+2C8h]
0x18001c0b0  mov     rcx, [rsi]; this
0x18001c0b3  test    rcx, rcx
0x18001c0b6  jz      short loc_18001C0C0
0x18001c0b8  mov     [rsi], rbx
0x18001c0bb  call    ?Release@CSxStringMap@@QEAAKXZ; CSxStringMap::Release(void)
0x18001c0c0  mov     rcx, rsi; struct CSxStringMap **
0x18001c0c3  call    ?CreateInstance@CSxStringMap@@SAJPEAPEAV1@@Z; CSxStringMap::CreateInstance(CSxStringMap * *)
0x18001c0c8  mov     [rbp+var_48], eax
0x18001c0cb  test    eax, eax
0x18001c0cd  mov     eax, 55Ah
0x18001c0d2  jns     short loc_18001C0DD
0x18001c0d4  mov     [rbp+var_42], ax
0x18001c0d8  jmp     loc_18001C19F
0x18001c0dd  mov     [rbp+var_44], ax
0x18001c0e1  mov     rcx, [rdi+2D0h]; this
0x18001c0e8  test    rcx, rcx
0x18001c0eb  jz      short loc_18001C0F9
0x18001c0ed  mov     [rdi+2D0h], rbx
0x18001c0f4  call    ?Release@CSxStringMap@@QEAAKXZ; CSxStringMap::Release(void)
0x18001c0f9  lea     rcx, [rdi+2D0h]; struct CSxStringMap **
0x18001c100  call    ?CreateInstance@CSxStringMap@@SAJPEAPEAV1@@Z; CSxStringMap::CreateInstance(CSxStringMap * *)
0x18001c105  mov     [rbp+var_48], eax
0x18001c108  test    eax, eax
0x18001c10a  mov     eax, 55Bh
0x18001c10f  js      short loc_18001C0D4
0x18001c111  mov     [rbp+var_44], ax
0x18001c115  lea     rdx, [rbp+pv]; unsigned __int16 **
0x18001c119  lea     rcx, c_wszIncludeExtensionAsCompressed; "IncludeExtensionAsCompressed"
0x18001c120  call    ?ReadExtensionsListFromReg@@YAJPEBGPEAPEAG@Z; ReadExtensionsListFromReg(ushort const *,ushort * *)
0x18001c125  test    eax, eax
0x18001c127  js      short loc_18001C159
0x18001c129  mov     rdx, [rsi]; struct CSxStringMap *
0x18001c12c  mov     rbx, [rbp+pv]
0x18001c130  mov     rcx, rbx; unsigned __int16 *
0x18001c133  call    ?SxConvertMultiStringToMap@@YAJPEBGPEAVCSxStringMap@@@Z; SxConvertMultiStringToMap(ushort const *,CSxStringMap *)
0x18001c138  mov     [rbp+var_48], eax
0x18001c13b  test    eax, eax
0x18001c13d  mov     eax, 565h
0x18001c142  js      short loc_18001C0D4
0x18001c144  mov     [rbp+var_44], ax
0x18001c148  mov     rcx, rbx; pv
0x18001c14b  call    cs:__imp_CoTaskMemFree
0x18001c151  mov     [rbp+pv], 0
0x18001c159  lea     rdx, [rbp+pv]; unsigned __int16 **
0x18001c15d  lea     rcx, c_wszExcludeExtensionAsCompressed; "ExcludeExtensionAsCompressed"
0x18001c164  call    ?ReadExtensionsListFromReg@@YAJPEBGPEAPEAG@Z; ReadExtensionsListFromReg(ushort const *,ushort * *)
0x18001c169  mov     rbx, [rbp+pv]
0x18001c16d  test    eax, eax
0x18001c16f  js      short loc_18001C19F
0x18001c171  mov     rdx, [rdi+2D0h]; struct CSxStringMap *
0x18001c178  mov     rcx, rbx; unsigned __int16 *
0x18001c17b  call    ?SxConvertMultiStringToMap@@YAJPEBGPEAVCSxStringMap@@@Z; SxConvertMultiStringToMap(ushort const *,CSxStringMap *)
0x18001c180  mov     [rbp+var_48], eax
0x18001c183  test    eax, eax
0x18001c185  mov     eax, 576h
0x18001c18a  js      loc_18001C0D4
0x18001c190  mov     [rbp+var_44], ax
0x18001c194  mov     rcx, rbx; pv
0x18001c197  call    cs:__imp_CoTaskMemFree
0x18001c19d  xor     ebx, ebx
0x18001c19f  mov     rcx, rbx; pv
0x18001c1a2  call    cs:__imp_CoTaskMemFree
0x18001c1a8  mov     ebx, [rbp+var_48]
0x18001c1ab  lea     rcx, [rbp+var_48]; this
0x18001c1af  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001c1b4  mov     eax, ebx
0x18001c1b6  add     rsp, 68h
0x18001c1ba  pop     rdi
0x18001c1bb  pop     rsi
0x18001c1bc  pop     rbx
0x18001c1bd  pop     rbp
0x18001c1be  retn
```

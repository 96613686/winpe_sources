# CSdBackupImpl::_PopulateCompressionExtensionsFromRegistry(void)

- ea: `0x18001cb40`
- end: `0x18001cc9a`
- name: `?_PopulateCompressionExtensionsFromRegistry@CSdBackupImpl@@AEAAJXZ`
- size: `346`
- prototype: `__int64 __fastcall(CSdBackupImpl *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800193c0`

## callees

- `0x18000b97c`
- `0x1800131f0`
- `0x18001cb40`
- `0x180072e08`
- `0x180072f14`
- `0x18008bc8c`
- `0x18009846c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001cc13`
- `ole32!CoTaskMemFree` at `0x18001cc65`
- `ole32!CoTaskMemFree` at `0x18001cc76`
- `ole32!CoTaskMemFree` at `0x18001cc13`
- `ole32!CoTaskMemFree` at `0x18001cc65`
- `ole32!CoTaskMemFree` at `0x18001cc76`

## string_xrefs

- `0x18001cbe1`: `IncludeExtensionAsCompressed`
- `0x18001cc2b`: `ExcludeExtensionAsCompressed`
- `0x18001cb5b`: `CSdBackupImpl::_PopulateCompressionExtensionsFromRegistry`

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
    0x552u,
    1u);
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
0x18001cb40  push    rbp
0x18001cb42  push    rbx
0x18001cb43  push    rsi
0x18001cb44  push    rdi
0x18001cb45  mov     rbp, rsp
0x18001cb48  sub     rsp, 68h
0x18001cb4c  mov     rdi, rcx
0x18001cb4f  mov     r9d, 1; unsigned __int16
0x18001cb55  mov     r8d, 552h; unsigned __int16
0x18001cb5b  lea     rdx, aCsdbackupimplP_0; "CSdBackupImpl::_PopulateCompressionExte"...
0x18001cb62  lea     rcx, [rbp+var_48]; this
0x18001cb66  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001cb6b  xor     ebx, ebx
0x18001cb6d  mov     [rbp+pv], rbx
0x18001cb71  lea     rsi, [rdi+2C8h]
0x18001cb78  mov     rcx, [rsi]; this
0x18001cb7b  test    rcx, rcx
0x18001cb7e  jz      short loc_18001CB88
0x18001cb80  mov     [rsi], rbx
0x18001cb83  call    ?Release@CSxStringMap@@QEAAKXZ; CSxStringMap::Release(void)
0x18001cb88  mov     rcx, rsi; struct CSxStringMap **
0x18001cb8b  call    ?CreateInstance@CSxStringMap@@SAJPEAPEAV1@@Z; CSxStringMap::CreateInstance(CSxStringMap * *)
0x18001cb90  mov     [rbp+var_48], eax
0x18001cb93  test    eax, eax
0x18001cb95  mov     eax, 55Ah
0x18001cb9a  jns     short loc_18001CBA5
0x18001cb9c  mov     [rbp+var_42], ax
0x18001cba0  jmp     loc_18001CC73
0x18001cba5  mov     [rbp+var_44], ax
0x18001cba9  mov     rcx, [rdi+2D0h]; this
0x18001cbb0  test    rcx, rcx
0x18001cbb3  jz      short loc_18001CBC1
0x18001cbb5  mov     [rdi+2D0h], rbx
0x18001cbbc  call    ?Release@CSxStringMap@@QEAAKXZ; CSxStringMap::Release(void)
0x18001cbc1  lea     rcx, [rdi+2D0h]; struct CSxStringMap **
0x18001cbc8  call    ?CreateInstance@CSxStringMap@@SAJPEAPEAV1@@Z; CSxStringMap::CreateInstance(CSxStringMap * *)
0x18001cbcd  mov     [rbp+var_48], eax
0x18001cbd0  test    eax, eax
0x18001cbd2  mov     eax, 55Bh
0x18001cbd7  js      short loc_18001CB9C
0x18001cbd9  mov     [rbp+var_44], ax
0x18001cbdd  lea     rdx, [rbp+pv]; unsigned __int16 **
0x18001cbe1  lea     rcx, c_wszIncludeExtensionAsCompressed; "IncludeExtensionAsCompressed"
0x18001cbe8  call    ?ReadExtensionsListFromReg@@YAJPEBGPEAPEAG@Z; ReadExtensionsListFromReg(ushort const *,ushort * *)
0x18001cbed  test    eax, eax
0x18001cbef  js      short loc_18001CC27
0x18001cbf1  mov     rdx, [rsi]; struct CSxStringMap *
0x18001cbf4  mov     rbx, [rbp+pv]
0x18001cbf8  mov     rcx, rbx; unsigned __int16 *
0x18001cbfb  call    ?SxConvertMultiStringToMap@@YAJPEBGPEAVCSxStringMap@@@Z; SxConvertMultiStringToMap(ushort const *,CSxStringMap *)
0x18001cc00  mov     [rbp+var_48], eax
0x18001cc03  test    eax, eax
0x18001cc05  mov     eax, 565h
0x18001cc0a  js      short loc_18001CB9C
0x18001cc0c  mov     [rbp+var_44], ax
0x18001cc10  mov     rcx, rbx; pv
0x18001cc13  call    cs:__imp_CoTaskMemFree
0x18001cc1a  nop     dword ptr [rax+rax+00h]
0x18001cc1f  mov     [rbp+pv], 0
0x18001cc27  lea     rdx, [rbp+pv]; unsigned __int16 **
0x18001cc2b  lea     rcx, c_wszExcludeExtensionAsCompressed; "ExcludeExtensionAsCompressed"
0x18001cc32  call    ?ReadExtensionsListFromReg@@YAJPEBGPEAPEAG@Z; ReadExtensionsListFromReg(ushort const *,ushort * *)
0x18001cc37  mov     rbx, [rbp+pv]
0x18001cc3b  test    eax, eax
0x18001cc3d  js      short loc_18001CC73
0x18001cc3f  mov     rdx, [rdi+2D0h]; struct CSxStringMap *
0x18001cc46  mov     rcx, rbx; unsigned __int16 *
0x18001cc49  call    ?SxConvertMultiStringToMap@@YAJPEBGPEAVCSxStringMap@@@Z; SxConvertMultiStringToMap(ushort const *,CSxStringMap *)
0x18001cc4e  mov     [rbp+var_48], eax
0x18001cc51  test    eax, eax
0x18001cc53  mov     eax, 576h
0x18001cc58  js      loc_18001CB9C
0x18001cc5e  mov     [rbp+var_44], ax
0x18001cc62  mov     rcx, rbx; pv
0x18001cc65  call    cs:__imp_CoTaskMemFree
0x18001cc6c  nop     dword ptr [rax+rax+00h]
0x18001cc71  xor     ebx, ebx
0x18001cc73  mov     rcx, rbx; pv
0x18001cc76  call    cs:__imp_CoTaskMemFree
0x18001cc7d  nop     dword ptr [rax+rax+00h]
0x18001cc82  mov     ebx, [rbp+var_48]
0x18001cc85  lea     rcx, [rbp+var_48]; this
0x18001cc89  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001cc8e  mov     eax, ebx
0x18001cc90  add     rsp, 68h
0x18001cc94  pop     rdi
0x18001cc95  pop     rsi
0x18001cc96  pop     rbx
0x18001cc97  pop     rbp
0x18001cc98  retn
```

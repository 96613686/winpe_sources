# CVssRegistryValueIterator::Attach(CVssRegistryKey &)

- ea: `0x180038118`
- end: `0x1800382fc`
- name: `?Attach@CVssRegistryValueIterator@@QEAAXAEAVCVssRegistryKey@@@Z`
- size: `484`
- prototype: `void __fastcall(CVssRegistryValueIterator *__hidden this, struct CVssRegistryKey *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003ced0`

## callees

- `0x18000212c`
- `0x180002138`
- `0x1800049e0`
- `0x180033a8c`
- `0x180033c78`
- `0x180037080`
- `0x180038118`
- `0x180038704`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180038211`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180038211`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003829c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003829c`

## string_xrefs

- `0x180038135`: `base\stor\vss\modules\registry\registry.cxx`
- `0x180038141`: `CVssRegistryValueIterator::Attach`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssRegistryValueIterator::Attach(CVssRegistryValueIterator *this, struct CVssRegistryKey *a2)
{
  HKEY v4; // rcx
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 v8; // rbx
  LPVOID v9; // rax
  const unsigned __int16 *v10; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v11; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v12; // [rsp+70h] [rbp-90h]
  int v13; // [rsp+78h] [rbp-88h]
  int v14; // [rsp+7Ch] [rbp-84h]
  int v15; // [rsp+80h] [rbp-80h]
  _BYTE v16[120]; // [rsp+88h] [rbp-78h] BYREF
  int v17; // [rsp+100h] [rbp+0h]
  LPVOID v18[20]; // [rsp+110h] [rbp+10h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+1C0h] [rbp+C0h] BYREF
  DWORD cValues; // [rsp+1C8h] [rbp+C8h] BYREF
  int pExceptionObject; // [rsp+1D0h] [rbp+D0h] BYREF

  v10 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v11 = L"CVssRegistryValueIterator::Attach";
  v12 = L"REGREGSC";
  v13 = 1162;
  v14 = 11;
  v15 = 255;
  v17 = 0x1000000;
  memset_0(v16, 0, sizeof(v16));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v18, (__int64)&v10, 0);
  CVssRegistryValueIterator::Detach(this);
  v4 = (HKEY)*((_QWORD *)a2 + 1);
  *(_QWORD *)this = v4;
  cValues = 0;
  cbMaxValueNameLen = 0;
  v5 = RegQueryInfoKeyW(v4, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  v6 = v5;
  if ( v5 )
  {
    v7 = *(_QWORD *)this;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    v10 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v11 = L"CVssRegistryValueIterator::Attach";
    v12 = L"REGREGSC";
    v13 = 1186;
    v14 = 11;
    v15 = 255;
    v17 = 0x1000000;
    memset_0(v16, 0, sizeof(v16));
    CVssFunctionTracer::TranslateGenericError(v18, &v10, v6, L"RegQueryInfoKeyW(%p, ...)", v7);
  }
  v8 = cbMaxValueNameLen;
  CVssAutoGenericValue_Storage<unsigned short *,0,void (*)(void *),&void CoTaskMemFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close((char *)this + 24);
  v9 = CoTaskMemAlloc(2 * v8 + 2);
  *((_QWORD *)this + 4) = v9;
  if ( !v9 )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  *((_DWORD *)this + 2) = cValues;
  *((_DWORD *)this + 10) = cbMaxValueNameLen + 1;
  *((_BYTE *)this + 49) = 1;
  CVssFunctionTracer::~CVssFunctionTracer(v18);
}

```

## disassembly

```asm
0x180038118  push    rbp
0x18003811a  push    rbx
0x18003811b  push    rsi
0x18003811c  push    rdi
0x18003811d  push    r12
0x18003811f  push    r13
0x180038121  push    r15
0x180038123  lea     rbp, [rsp-80h]
0x180038128  sub     rsp, 180h
0x18003812f  mov     rbx, rdx
0x180038132  mov     rsi, rcx
0x180038135  lea     r15, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x18003813c  mov     [rsp+1B0h+var_150], r15
0x180038141  lea     r12, aCvssregistryva_3; "CVssRegistryValueIterator::Attach"
0x180038148  mov     [rsp+1B0h+var_148], r12
0x18003814d  lea     r13, aRegregsc; "REGREGSC"
0x180038154  mov     [rsp+1B0h+var_140], r13
0x180038159  mov     [rsp+1B0h+var_138], 48Ah
0x180038161  mov     [rsp+1B0h+var_134], 0Bh
0x180038169  mov     [rbp+0B0h+var_130], 0FFh
0x180038170  mov     [rbp+0B0h+var_B0], 1000000h
0x180038177  xor     edx, edx; Val
0x180038179  lea     r8d, [rdx+78h]; Size
0x18003817d  lea     rcx, [rbp+0B0h+var_128]; void *
0x180038181  call    memset_0
0x180038186  xor     r8d, r8d
0x180038189  lea     rdx, [rsp+1B0h+var_150]
0x18003818e  lea     rcx, [rbp+0B0h+var_A0]
0x180038192  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180038197  nop
0x180038198  mov     rcx, rsi; this
0x18003819b  call    ?Detach@CVssRegistryValueIterator@@QEAAXXZ; CVssRegistryValueIterator::Detach(void)
0x1800381a0  mov     rcx, [rbx+8]; hKey
0x1800381a4  mov     [rsi], rcx
0x1800381a7  mov     [rbp+0B0h+cValues], 0
0x1800381b1  mov     [rbp+0B0h+cbMaxValueNameLen], 0
0x1800381bb  mov     [rsp+1B0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800381c4  mov     [rsp+1B0h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x1800381cd  mov     [rsp+1B0h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x1800381d6  lea     rax, [rbp+0B0h+cbMaxValueNameLen]
0x1800381dd  mov     [rsp+1B0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800381e2  lea     rax, [rbp+0B0h+cValues]
0x1800381e9  mov     [rsp+1B0h+lpcValues], rax; lpcValues
0x1800381ee  mov     [rsp+1B0h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x1800381f7  mov     [rsp+1B0h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x180038200  mov     [rsp+1B0h+lpcSubKeys], 0; lpcSubKeys
0x180038209  xor     r9d, r9d; lpReserved
0x18003820c  xor     r8d, r8d; lpcchClass
0x18003820f  xor     edx, edx; lpClass
0x180038211  call    cs:__imp_RegQueryInfoKeyW
0x180038217  mov     ebx, eax
0x180038219  test    eax, eax
0x18003821b  jz      short loc_180038285
0x18003821d  mov     rdi, [rsi]
0x180038220  jle     short loc_18003822B
0x180038222  movzx   ebx, ax
0x180038225  or      ebx, 80070000h
0x18003822b  mov     [rsp+1B0h+var_150], r15
0x180038230  mov     [rsp+1B0h+var_148], r12
0x180038235  mov     [rsp+1B0h+var_140], r13
0x18003823a  mov     [rsp+1B0h+var_138], 4A2h
0x180038242  mov     [rsp+1B0h+var_134], 0Bh
0x18003824a  mov     [rbp+0B0h+var_130], 0FFh
0x180038251  mov     [rbp+0B0h+var_B0], 1000000h
0x180038258  xor     edx, edx; Val
0x18003825a  lea     r8d, [rdx+78h]; Size
0x18003825e  lea     rcx, [rbp+0B0h+var_128]; void *
0x180038262  call    memset_0
0x180038267  mov     [rsp+1B0h+lpcSubKeys], rdi
0x18003826c  lea     r9, aRegqueryinfoke; "RegQueryInfoKeyW(%p, ...)"
0x180038273  mov     r8d, ebx
0x180038276  lea     rdx, [rsp+1B0h+var_150]
0x18003827b  lea     rcx, [rbp+0B0h+var_A0]
0x18003827f  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180038285  mov     ebx, [rbp+0B0h+cbMaxValueNameLen]
0x18003828b  lea     rcx, [rsi+18h]
0x18003828f  call    ?Close@?$CVssAutoGenericValue_Storage@PEAG$0A@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6AAEAPEAGAEAPEAG@Z$1?Identity@?$DTyper@PEAG@@SAAEAPEAG1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<ushort *,0,void (*)(void *),&CoTaskMemFree(void *),ushort * & (*)(ushort * &),&DTyper<ushort *>::Identity(ushort * &)>::Close(void)
0x180038294  lea     rcx, ds:2[rbx*2]; cb
0x18003829c  call    cs:__imp_CoTaskMemAlloc
0x1800382a2  mov     [rsi+20h], rax
0x1800382a6  test    rax, rax
0x1800382a9  jnz     short loc_1800382C9
0x1800382ab  mov     [rbp+0B0h+pExceptionObject], 8007000Eh
0x1800382b5  lea     rdx, _TI1J; pThrowInfo
0x1800382bc  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x1800382c3  call    _CxxThrowException_0
0x1800382c9  mov     eax, [rbp+0B0h+cValues]
0x1800382cf  mov     [rsi+8], eax
0x1800382d2  mov     eax, [rbp+0B0h+cbMaxValueNameLen]
0x1800382d8  inc     eax
0x1800382da  mov     [rsi+28h], eax
0x1800382dd  mov     byte ptr [rsi+31h], 1
0x1800382e1  lea     rcx, [rbp+0B0h+var_A0]; this
0x1800382e5  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1800382ea  add     rsp, 180h
0x1800382f1  pop     r15
0x1800382f3  pop     r13
0x1800382f5  pop     r12
0x1800382f7  pop     rdi
0x1800382f8  pop     rsi
0x1800382f9  pop     rbx
0x1800382fa  pop     rbp
0x1800382fb  retn
```

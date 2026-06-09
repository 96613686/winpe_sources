# CVssRegistryKeyIterator::Attach(CVssRegistryKey &)

- ea: `0x180037f24`
- end: `0x18003810f`
- name: `?Attach@CVssRegistryKeyIterator@@QEAAXAEAVCVssRegistryKey@@@Z`
- size: `491`
- prototype: `void __fastcall(CVssRegistryKeyIterator *__hidden this, struct CVssRegistryKey *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002e7ec`

## callees

- `0x18000212c`
- `0x180002138`
- `0x1800049e0`
- `0x180033a8c`
- `0x180033c78`
- `0x180037080`
- `0x180037f24`
- `0x1800386cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003801d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003801d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800380ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800380ae`

## string_xrefs

- `0x180037f41`: `base\stor\vss\modules\registry\registry.cxx`
- `0x180037f4d`: `CVssRegistryKeyIterator::Attach`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssRegistryKeyIterator::Attach(CVssRegistryKeyIterator *this, struct CVssRegistryKey *a2)
{
  HKEY v4; // rcx
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  DWORD v8; // ecx
  __int64 v9; // rbx
  LPVOID v10; // rax
  const unsigned __int16 *v11; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v12; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v13; // [rsp+70h] [rbp-90h]
  int v14; // [rsp+78h] [rbp-88h]
  int v15; // [rsp+7Ch] [rbp-84h]
  int v16; // [rsp+80h] [rbp-80h]
  _BYTE v17[120]; // [rsp+88h] [rbp-78h] BYREF
  int v18; // [rsp+100h] [rbp+0h]
  LPVOID v19[20]; // [rsp+110h] [rbp+10h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+1C0h] [rbp+C0h] BYREF
  DWORD cSubKeys; // [rsp+1C8h] [rbp+C8h] BYREF
  int pExceptionObject; // [rsp+1D0h] [rbp+D0h] BYREF

  v11 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v12 = L"CVssRegistryKeyIterator::Attach";
  v13 = L"REGREGSC";
  v14 = 760;
  v15 = 11;
  v16 = 255;
  v18 = 0x1000000;
  memset_0(v17, 0, sizeof(v17));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v19, (__int64)&v11, 0);
  CVssRegistryKeyIterator::Detach(this);
  v4 = (HKEY)*((_QWORD *)a2 + 1);
  *(_QWORD *)this = v4;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v5 = RegQueryInfoKeyW(v4, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v6 = v5;
  if ( v5 )
  {
    v7 = *(_QWORD *)this;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    v11 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v12 = L"CVssRegistryKeyIterator::Attach";
    v13 = L"REGREGSC";
    v14 = 784;
    v15 = 11;
    v16 = 255;
    v18 = 0x1000000;
    memset_0(v17, 0, sizeof(v17));
    CVssFunctionTracer::TranslateGenericError(v19, &v11, v6, L"RegQueryInfoKeyW(%p, ...)", v7);
  }
  v8 = cbMaxSubKeyLen;
  if ( cbMaxSubKeyLen )
  {
    v9 = cbMaxSubKeyLen;
    CVssAutoGenericValue_Storage<unsigned short *,0,void (*)(void *),&void CoTaskMemFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close((char *)this + 24);
    v10 = CoTaskMemAlloc(2 * v9 + 2);
    *((_QWORD *)this + 4) = v10;
    if ( !v10 )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
    v8 = cbMaxSubKeyLen;
  }
  *((_DWORD *)this + 2) = cSubKeys;
  *((_DWORD *)this + 4) = v8 + 1;
  *((_BYTE *)this + 40) = 1;
  CVssFunctionTracer::~CVssFunctionTracer(v19);
}

```

## disassembly

```asm
0x180037f24  push    rbp
0x180037f26  push    rbx
0x180037f27  push    rsi
0x180037f28  push    rdi
0x180037f29  push    r12
0x180037f2b  push    r13
0x180037f2d  push    r15
0x180037f2f  lea     rbp, [rsp-80h]
0x180037f34  sub     rsp, 180h
0x180037f3b  mov     rbx, rdx
0x180037f3e  mov     rsi, rcx
0x180037f41  lea     r15, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x180037f48  mov     [rsp+1B0h+var_150], r15
0x180037f4d  lea     r12, aCvssregistryke_1; "CVssRegistryKeyIterator::Attach"
0x180037f54  mov     [rsp+1B0h+var_148], r12
0x180037f59  lea     r13, aRegregsc; "REGREGSC"
0x180037f60  mov     [rsp+1B0h+var_140], r13
0x180037f65  mov     [rsp+1B0h+var_138], 2F8h
0x180037f6d  mov     [rsp+1B0h+var_134], 0Bh
0x180037f75  mov     [rbp+0B0h+var_130], 0FFh
0x180037f7c  mov     [rbp+0B0h+var_B0], 1000000h
0x180037f83  xor     edx, edx; Val
0x180037f85  lea     r8d, [rdx+78h]; Size
0x180037f89  lea     rcx, [rbp+0B0h+var_128]; void *
0x180037f8d  call    memset_0
0x180037f92  xor     r8d, r8d
0x180037f95  lea     rdx, [rsp+1B0h+var_150]
0x180037f9a  lea     rcx, [rbp+0B0h+var_A0]
0x180037f9e  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180037fa3  nop
0x180037fa4  mov     rcx, rsi; this
0x180037fa7  call    ?Detach@CVssRegistryKeyIterator@@QEAAXXZ; CVssRegistryKeyIterator::Detach(void)
0x180037fac  mov     rcx, [rbx+8]; hKey
0x180037fb0  mov     [rsi], rcx
0x180037fb3  mov     [rbp+0B0h+cSubKeys], 0
0x180037fbd  mov     [rbp+0B0h+cbMaxSubKeyLen], 0
0x180037fc7  mov     [rsp+1B0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180037fd0  mov     [rsp+1B0h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x180037fd9  mov     [rsp+1B0h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x180037fe2  mov     [rsp+1B0h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x180037feb  mov     [rsp+1B0h+lpcValues], 0; lpcValues
0x180037ff4  mov     [rsp+1B0h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180037ffd  lea     rax, [rbp+0B0h+cbMaxSubKeyLen]
0x180038004  mov     [rsp+1B0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180038009  lea     rax, [rbp+0B0h+cSubKeys]
0x180038010  mov     [rsp+1B0h+lpcSubKeys], rax; lpcSubKeys
0x180038015  xor     r9d, r9d; lpReserved
0x180038018  xor     r8d, r8d; lpcchClass
0x18003801b  xor     edx, edx; lpClass
0x18003801d  call    cs:__imp_RegQueryInfoKeyW
0x180038023  mov     ebx, eax
0x180038025  test    eax, eax
0x180038027  jz      short loc_180038091
0x180038029  mov     rdi, [rsi]
0x18003802c  jle     short loc_180038037
0x18003802e  movzx   ebx, ax
0x180038031  or      ebx, 80070000h
0x180038037  mov     [rsp+1B0h+var_150], r15
0x18003803c  mov     [rsp+1B0h+var_148], r12
0x180038041  mov     [rsp+1B0h+var_140], r13
0x180038046  mov     [rsp+1B0h+var_138], 310h
0x18003804e  mov     [rsp+1B0h+var_134], 0Bh
0x180038056  mov     [rbp+0B0h+var_130], 0FFh
0x18003805d  mov     [rbp+0B0h+var_B0], 1000000h
0x180038064  xor     edx, edx; Val
0x180038066  lea     r8d, [rdx+78h]; Size
0x18003806a  lea     rcx, [rbp+0B0h+var_128]; void *
0x18003806e  call    memset_0
0x180038073  mov     [rsp+1B0h+lpcSubKeys], rdi
0x180038078  lea     r9, aRegqueryinfoke; "RegQueryInfoKeyW(%p, ...)"
0x18003807f  mov     r8d, ebx
0x180038082  lea     rdx, [rsp+1B0h+var_150]
0x180038087  lea     rcx, [rbp+0B0h+var_A0]
0x18003808b  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180038091  mov     ecx, [rbp+0B0h+cbMaxSubKeyLen]
0x180038097  test    ecx, ecx
0x180038099  jz      short loc_1800380E1
0x18003809b  mov     ebx, ecx
0x18003809d  lea     rcx, [rsi+18h]
0x1800380a1  call    ?Close@?$CVssAutoGenericValue_Storage@PEAG$0A@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6AAEAPEAGAEAPEAG@Z$1?Identity@?$DTyper@PEAG@@SAAEAPEAG1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<ushort *,0,void (*)(void *),&CoTaskMemFree(void *),ushort * & (*)(ushort * &),&DTyper<ushort *>::Identity(ushort * &)>::Close(void)
0x1800380a6  lea     rcx, ds:2[rbx*2]; cb
0x1800380ae  call    cs:__imp_CoTaskMemAlloc
0x1800380b4  mov     [rsi+20h], rax
0x1800380b8  test    rax, rax
0x1800380bb  jnz     short loc_1800380DB
0x1800380bd  mov     [rbp+0B0h+pExceptionObject], 8007000Eh
0x1800380c7  lea     rdx, _TI1J; pThrowInfo
0x1800380ce  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x1800380d5  call    _CxxThrowException_0
0x1800380db  mov     ecx, [rbp+0B0h+cbMaxSubKeyLen]
0x1800380e1  mov     eax, [rbp+0B0h+cSubKeys]
0x1800380e7  mov     [rsi+8], eax
0x1800380ea  lea     eax, [rcx+1]
0x1800380ed  mov     [rsi+10h], eax
0x1800380f0  mov     byte ptr [rsi+28h], 1
0x1800380f4  lea     rcx, [rbp+0B0h+var_A0]; this
0x1800380f8  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1800380fd  add     rsp, 180h
0x180038104  pop     r15
0x180038106  pop     r13
0x180038108  pop     r12
0x18003810a  pop     rdi
0x18003810b  pop     rsi
0x18003810c  pop     rbx
0x18003810d  pop     rbp
0x18003810e  retn
```

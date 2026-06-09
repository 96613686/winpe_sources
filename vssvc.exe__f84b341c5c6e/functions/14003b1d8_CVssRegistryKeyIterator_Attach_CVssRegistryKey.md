# CVssRegistryKeyIterator::Attach(CVssRegistryKey &)

- ea: `0x14003b1d8`
- end: `0x14003b49d`
- name: `?Attach@CVssRegistryKeyIterator@@QEAAXAEAVCVssRegistryKey@@@Z`
- size: `709`
- prototype: `void __fastcall(CVssRegistryKeyIterator *__hidden this, struct CVssRegistryKey *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140015fb0`

## callees

- `0x140006020`
- `0x1400137c0`
- `0x140013cb0`
- `0x14003b1d8`
- `0x14003b4a4`
- `0x14003b4ec`
- `0x140049ec4`
- `0x1400921dc`
- `0x1400921e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14003b3a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14003b3a8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003b26f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003b26f`
- `VssTrace!__imp_VssTraceMessage` at `0x14003b33d`
- `VssTrace!__imp_VssTraceMessage` at `0x14003b33d`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003b2b7`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003b2b7`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003b2a8`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003b2a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003b43b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003b43b`

## string_xrefs

- `0x14003b1f5`: `base\stor\vss\modules\registry\registry.cxx`
- `0x14003b200`: `CVssRegistryKeyIterator::Attach`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssRegistryKeyIterator::Attach(CVssRegistryKeyIterator *this, struct CVssRegistryKey *a2)
{
  int v4; // eax
  __int64 v5; // rcx
  int v6; // ebx
  HKEY v7; // rcx
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdi
  DWORD v11; // ecx
  __int64 v12; // rbx
  LPVOID v13; // rax
  unsigned __int64 v14; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v16; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v17; // [rsp+78h] [rbp-88h]
  unsigned int v18; // [rsp+80h] [rbp-80h]
  int v19; // [rsp+84h] [rbp-7Ch]
  const wchar_t *v20; // [rsp+88h] [rbp-78h]
  unsigned int v21; // [rsp+90h] [rbp-70h]
  DWORD TickCount; // [rsp+94h] [rbp-6Ch]
  int v23; // [rsp+98h] [rbp-68h]
  __int128 v24; // [rsp+A0h] [rbp-60h]
  __int128 v25; // [rsp+B0h] [rbp-50h]
  __int64 v26; // [rsp+C0h] [rbp-40h]
  const unsigned __int16 *v27; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v28; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v29; // [rsp+E0h] [rbp-20h]
  int v30; // [rsp+E8h] [rbp-18h]
  int v31; // [rsp+ECh] [rbp-14h]
  int v32; // [rsp+F0h] [rbp-10h]
  _BYTE v33[120]; // [rsp+F8h] [rbp-8h] BYREF
  int v34; // [rsp+170h] [rbp+70h]
  DWORD cbMaxSubKeyLen; // [rsp+1C0h] [rbp+C0h] BYREF
  DWORD cSubKeys; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 pExceptionObject; // [rsp+1D0h] [rbp+D0h] BYREF

  v27 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v28 = L"CVssRegistryKeyIterator::Attach";
  v29 = L"REGREGSC";
  v30 = 760;
  v31 = 11;
  v32 = 255;
  v34 = 0x1000000;
  memset_0(v33, 0, sizeof(v33));
  v15 = 0;
  v20 = L"CVssRegistryKeyIterator::Attach";
  v16 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v17 = L"REGREGSC";
  v18 = 760;
  v19 = 11;
  TickCount = GetTickCount();
  v23 = 255;
  v14 = 0xFFFFFFFF00000000uLL;
  v26 = 0;
  v24 = 0;
  v25 = 0;
  pExceptionObject = 0;
  if ( (int)VssGetTracingContextPerThread(&pExceptionObject) < 0 )
  {
    v5 = v26;
  }
  else
  {
    v4 = VssSetTracingContextPerThread(&v14);
    v5 = v26;
    if ( v4 >= 0 )
      v5 = pExceptionObject;
    v26 = v5;
  }
  if ( v5 )
    v21 = *(_DWORD *)(v5 + 48) + 1;
  else
    v21 = 0;
  v6 = 160;
  if ( v23 != 255 )
    v6 = v23;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v14) )
    VssTraceMessage(v16, v17, v18, v21, v19, v20, L"ENTER", v6, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v27);
  CVssRegistryKeyIterator::Detach(this);
  v7 = (HKEY)*((_QWORD *)a2 + 1);
  *(_QWORD *)this = v7;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v8 = RegQueryInfoKeyW(v7, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v9 = v8;
  if ( v8 )
  {
    v10 = *(_QWORD *)this;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    v27 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v28 = L"CVssRegistryKeyIterator::Attach";
    v29 = L"REGREGSC";
    v30 = 784;
    v31 = 11;
    v32 = 255;
    v34 = 0x1000000;
    memset_0(v33, 0, sizeof(v33));
    CVssFunctionTracer::TranslateGenericError(&v14, &v27, v9, L"RegQueryInfoKeyW(%p, ...)", v10);
  }
  v11 = cbMaxSubKeyLen;
  if ( cbMaxSubKeyLen )
  {
    v12 = cbMaxSubKeyLen;
    CVssAutoGenericValue_Storage<unsigned short *,0,void (*)(void *),&void CoTaskMemFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close((char *)this + 24);
    v13 = CoTaskMemAlloc(2 * v12 + 2);
    *((_QWORD *)this + 4) = v13;
    if ( !v13 )
    {
      LODWORD(pExceptionObject) = -2147024882;
      throw (long *)&pExceptionObject;
    }
    v11 = cbMaxSubKeyLen;
  }
  *((_DWORD *)this + 2) = cSubKeys;
  *((_DWORD *)this + 4) = v11 + 1;
  *((_BYTE *)this + 40) = 1;
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v14);
}

```

## disassembly

```asm
0x14003b1d8  push    rbp
0x14003b1da  push    rbx
0x14003b1db  push    rsi
0x14003b1dc  push    rdi
0x14003b1dd  push    r12
0x14003b1df  push    r13
0x14003b1e1  push    r14
0x14003b1e3  lea     rbp, [rsp-80h]
0x14003b1e8  sub     rsp, 180h
0x14003b1ef  mov     rdi, rdx
0x14003b1f2  mov     rsi, rcx
0x14003b1f5  lea     r12, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x14003b1fc  mov     [rbp+0B0h+var_E0], r12
0x14003b200  lea     r13, aCvssregistryke_2; "CVssRegistryKeyIterator::Attach"
0x14003b207  mov     [rbp+0B0h+var_D8], r13
0x14003b20b  lea     rax, aRegregsc; "REGREGSC"
0x14003b212  mov     [rbp+0B0h+var_D0], rax
0x14003b216  mov     [rbp+0B0h+var_C8], 2F8h
0x14003b21d  mov     [rbp+0B0h+var_C4], 0Bh
0x14003b224  mov     [rbp+0B0h+var_C0], 0FFh
0x14003b22b  xor     r14d, r14d
0x14003b22e  mov     [rbp+0B0h+var_40], 1000000h
0x14003b235  xor     edx, edx; Val
0x14003b237  lea     r8d, [r14+78h]; Size
0x14003b23b  lea     rcx, [rbp+0B0h+var_B8]; void *
0x14003b23f  call    memset_0
0x14003b244  mov     [rsp+1B0h+var_148], r14d
0x14003b249  mov     rax, [rbp+0B0h+var_D8]
0x14003b24d  mov     [rbp+0B0h+var_128], rax
0x14003b251  mov     rax, [rbp+0B0h+var_E0]
0x14003b255  mov     [rsp+1B0h+var_140], rax
0x14003b25a  mov     rax, [rbp+0B0h+var_D0]
0x14003b25e  mov     [rsp+1B0h+var_138], rax
0x14003b263  mov     eax, [rbp+0B0h+var_C8]
0x14003b266  mov     [rbp+0B0h+var_130], eax
0x14003b269  mov     eax, [rbp+0B0h+var_C4]
0x14003b26c  mov     [rbp+0B0h+var_12C], eax
0x14003b26f  call    cs:__imp_GetTickCount
0x14003b275  mov     [rbp+0B0h+var_11C], eax
0x14003b278  mov     [rsp+1B0h+var_14C], 0FFFFFFFFh
0x14003b280  mov     eax, [rbp+0B0h+var_C0]
0x14003b283  mov     [rbp+0B0h+var_118], eax
0x14003b286  mov     [rsp+1B0h+var_150], r14d
0x14003b28b  mov     [rbp+0B0h+var_F0], r14
0x14003b28f  xorps   xmm0, xmm0
0x14003b292  movups  [rbp+0B0h+var_110], xmm0
0x14003b296  movups  [rbp+0B0h+var_100], xmm0
0x14003b29a  mov     [rbp+0B0h+pExceptionObject], r14
0x14003b2a1  lea     rcx, [rbp+0B0h+pExceptionObject]
0x14003b2a8  call    cs:__imp_VssGetTracingContextPerThread
0x14003b2ae  test    eax, eax
0x14003b2b0  js      short loc_14003B2D1
0x14003b2b2  lea     rcx, [rsp+1B0h+var_150]
0x14003b2b7  call    cs:__imp_VssSetTracingContextPerThread
0x14003b2bd  mov     rcx, [rbp+0B0h+var_F0]
0x14003b2c1  test    eax, eax
0x14003b2c3  cmovns  rcx, [rbp+0B0h+pExceptionObject]
0x14003b2cb  mov     [rbp+0B0h+var_F0], rcx
0x14003b2cf  jmp     short loc_14003B2D5
0x14003b2d1  mov     rcx, [rbp+0B0h+var_F0]
0x14003b2d5  test    rcx, rcx
0x14003b2d8  jz      short loc_14003B2E4
0x14003b2da  mov     eax, [rcx+30h]
0x14003b2dd  inc     eax
0x14003b2df  mov     [rbp+0B0h+var_120], eax
0x14003b2e2  jmp     short loc_14003B2E8
0x14003b2e4  mov     [rbp+0B0h+var_120], r14d
0x14003b2e8  mov     ebx, 0A0h
0x14003b2ed  cmp     [rbp+0B0h+var_118], 0FFh
0x14003b2f4  cmovnz  ebx, [rbp+0B0h+var_118]
0x14003b2f8  lea     rcx, [rsp+1B0h+var_150]; this
0x14003b2fd  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14003b302  test    eax, eax
0x14003b304  jz      short loc_14003B343
0x14003b306  mov     [rsp+1B0h+lpcbMaxValueNameLen], r14
0x14003b30b  mov     dword ptr [rsp+1B0h+lpcValues], ebx
0x14003b30f  lea     rax, aEnter; "ENTER"
0x14003b316  mov     [rsp+1B0h+lpcbMaxClassLen], rax
0x14003b31b  mov     rax, [rbp+0B0h+var_128]
0x14003b31f  mov     [rsp+1B0h+lpcbMaxSubKeyLen], rax
0x14003b324  mov     eax, [rbp+0B0h+var_12C]
0x14003b327  mov     dword ptr [rsp+1B0h+lpcSubKeys], eax
0x14003b32b  mov     r9d, [rbp+0B0h+var_120]
0x14003b32f  mov     r8d, [rbp+0B0h+var_130]
0x14003b333  mov     rdx, [rsp+1B0h+var_138]
0x14003b338  mov     rcx, [rsp+1B0h+var_140]
0x14003b33d  call    cs:__imp_VssTraceMessage
0x14003b343  lea     rcx, [rbp+0B0h+var_E0]; this
0x14003b347  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14003b34c  nop
0x14003b34d  mov     rcx, rsi; this
0x14003b350  call    ?Detach@CVssRegistryKeyIterator@@QEAAXXZ; CVssRegistryKeyIterator::Detach(void)
0x14003b355  mov     rcx, [rdi+8]; hKey
0x14003b359  mov     [rsi], rcx
0x14003b35c  mov     [rbp+0B0h+cSubKeys], r14d
0x14003b363  mov     [rbp+0B0h+cbMaxSubKeyLen], r14d
0x14003b36a  mov     [rsp+1B0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x14003b36f  mov     [rsp+1B0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x14003b374  mov     [rsp+1B0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x14003b379  mov     [rsp+1B0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x14003b37e  mov     [rsp+1B0h+lpcValues], r14; lpcValues
0x14003b383  mov     [rsp+1B0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x14003b388  lea     rax, [rbp+0B0h+cbMaxSubKeyLen]
0x14003b38f  mov     [rsp+1B0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x14003b394  lea     rax, [rbp+0B0h+cSubKeys]
0x14003b39b  mov     [rsp+1B0h+lpcSubKeys], rax; lpcSubKeys
0x14003b3a0  xor     r9d, r9d; lpReserved
0x14003b3a3  xor     r8d, r8d; lpcchClass
0x14003b3a6  xor     edx, edx; lpClass
0x14003b3a8  call    cs:__imp_RegQueryInfoKeyW
0x14003b3ae  mov     ebx, eax
0x14003b3b0  test    eax, eax
0x14003b3b2  jz      short loc_14003B41E
0x14003b3b4  mov     rdi, [rsi]
0x14003b3b7  jle     short loc_14003B3C2
0x14003b3b9  movzx   ebx, ax
0x14003b3bc  or      ebx, 80070000h
0x14003b3c2  mov     [rbp+0B0h+var_E0], r12
0x14003b3c6  mov     [rbp+0B0h+var_D8], r13
0x14003b3ca  lea     rax, aRegregsc; "REGREGSC"
0x14003b3d1  mov     [rbp+0B0h+var_D0], rax
0x14003b3d5  mov     [rbp+0B0h+var_C8], 310h
0x14003b3dc  mov     [rbp+0B0h+var_C4], 0Bh
0x14003b3e3  mov     [rbp+0B0h+var_C0], 0FFh
0x14003b3ea  mov     [rbp+0B0h+var_40], 1000000h
0x14003b3f1  xor     edx, edx; Val
0x14003b3f3  lea     r8d, [rdx+78h]; Size
0x14003b3f7  lea     rcx, [rbp+0B0h+var_B8]; void *
0x14003b3fb  call    memset_0
0x14003b400  mov     [rsp+1B0h+lpcSubKeys], rdi
0x14003b405  lea     r9, aRegqueryinfoke; "RegQueryInfoKeyW(%p, ...)"
0x14003b40c  mov     r8d, ebx
0x14003b40f  lea     rdx, [rbp+0B0h+var_E0]
0x14003b413  lea     rcx, [rsp+1B0h+var_150]
0x14003b418  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14003b41e  mov     ecx, [rbp+0B0h+cbMaxSubKeyLen]
0x14003b424  test    ecx, ecx
0x14003b426  jz      short loc_14003B46E
0x14003b428  mov     ebx, ecx
0x14003b42a  lea     rcx, [rsi+18h]
0x14003b42e  call    ?Close@?$CVssAutoGenericValue_Storage@PEAG$0A@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6AAEAPEAGAEAPEAG@Z$1?Identity@?$DTyper@PEAG@@SAAEAPEAG1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<ushort *,0,void (*)(void *),&CoTaskMemFree(void *),ushort * & (*)(ushort * &),&DTyper<ushort *>::Identity(ushort * &)>::Close(void)
0x14003b433  lea     rcx, ds:2[rbx*2]; cb
0x14003b43b  call    cs:__imp_CoTaskMemAlloc
0x14003b441  mov     [rsi+20h], rax
0x14003b445  test    rax, rax
0x14003b448  jnz     short loc_14003B468
0x14003b44a  mov     dword ptr [rbp+0B0h+pExceptionObject], 8007000Eh
0x14003b454  lea     rdx, _TI1J; pThrowInfo
0x14003b45b  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x14003b462  call    _CxxThrowException_0
0x14003b468  mov     ecx, [rbp+0B0h+cbMaxSubKeyLen]
0x14003b46e  mov     eax, [rbp+0B0h+cSubKeys]
0x14003b474  mov     [rsi+8], eax
0x14003b477  lea     eax, [rcx+1]
0x14003b47a  mov     [rsi+10h], eax
0x14003b47d  mov     byte ptr [rsi+28h], 1
0x14003b481  lea     rcx, [rsp+1B0h+var_150]; this
0x14003b486  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14003b48b  add     rsp, 180h
0x14003b492  pop     r14
0x14003b494  pop     r13
0x14003b496  pop     r12
0x14003b498  pop     rdi
0x14003b499  pop     rsi
0x14003b49a  pop     rbx
0x14003b49b  pop     rbp
0x14003b49c  retn
```

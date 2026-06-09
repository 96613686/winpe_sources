# CVssRegistryKey::Close(void)

- ea: `0x18003835c`
- end: `0x180038474`
- name: `?Close@CVssRegistryKey@@QEAAXXZ`
- size: `280`
- prototype: `void __fastcall(CVssRegistryKey *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180037e24`
- `0x18003a05c`

## callees

- `0x18000212c`
- `0x1800049e0`
- `0x180033a8c`
- `0x180033c78`
- `0x1800367b8`
- `0x18003835c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800383e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800383e2`

## string_xrefs

- `0x180038387`: `base\stor\vss\modules\registry\registry.cxx`
- `0x180038396`: `CVssRegistryKey::Close`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVssRegistryKey::Close(CVssRegistryKey *this)
{
  HKEY v2; // rcx
  LSTATUS v3; // edi
  LSTATUS v4; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v5; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v6; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v7; // [rsp+40h] [rbp-C0h]
  int v8; // [rsp+48h] [rbp-B8h]
  int v9; // [rsp+4Ch] [rbp-B4h]
  int v10; // [rsp+50h] [rbp-B0h]
  _BYTE v11[120]; // [rsp+58h] [rbp-A8h] BYREF
  int v12; // [rsp+D0h] [rbp-30h]
  LPVOID v13[20]; // [rsp+E0h] [rbp-20h] BYREF

  v8 = 668;
  v9 = 11;
  v10 = 255;
  v5 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v6 = L"CVssRegistryKey::Close";
  v7 = L"REGREGSC";
  v12 = 0x1000000;
  memset_0(v11, 0, sizeof(v11));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v13, (__int64)&v5, 0);
  v2 = (HKEY)*((_QWORD *)this + 1);
  if ( v2 )
  {
    v3 = RegCloseKey(v2);
    if ( v3 )
    {
      v5 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v6 = L"CVssRegistryKey::Close";
      v7 = L"REGREGSC";
      v8 = 675;
      v9 = 11;
      v10 = 255;
      v12 = 0x1000000;
      memset_0(v11, 0, sizeof(v11));
      v4 = v3;
      CVssFunctionTracer::Trace(
        v13,
        &v5,
        L"Error on closing key with name %s. lRes == 0x%08lx",
        *((_QWORD *)this + 3),
        v4);
    }
    *((_QWORD *)this + 1) = 0;
  }
  CVssAutoGenericValue_Storage<unsigned short *,0,void (*)(void *),&void CoTaskMemFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close((__int64)this + 16);
  CVssFunctionTracer::~CVssFunctionTracer(v13);
}

```

## disassembly

```asm
0x18003835c  push    rbp
0x18003835e  push    rbx
0x18003835f  push    rdi
0x180038360  push    r12
0x180038362  push    r14
0x180038364  push    r15
0x180038366  lea     rbp, [rsp-58h]
0x18003836b  sub     rsp, 158h
0x180038372  xor     edx, edx; Val
0x180038374  mov     [rsp+180h+var_138], 29Ch
0x18003837c  mov     rbx, rcx
0x18003837f  mov     [rsp+180h+var_134], 0Bh
0x180038387  lea     r14, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x18003838e  mov     [rsp+180h+var_130], 0FFh
0x180038396  lea     r15, aCvssregistryke_0; "CVssRegistryKey::Close"
0x18003839d  mov     [rsp+180h+var_150], r14
0x1800383a2  lea     r12, aRegregsc; "REGREGSC"
0x1800383a9  mov     [rsp+180h+var_148], r15
0x1800383ae  lea     r8d, [rdx+78h]; Size
0x1800383b2  mov     [rsp+180h+var_140], r12
0x1800383b7  lea     rcx, [rsp+180h+var_128]; void *
0x1800383bc  mov     [rbp+80h+var_B0], 1000000h
0x1800383c3  call    memset_0
0x1800383c8  xor     r8d, r8d
0x1800383cb  lea     rdx, [rsp+180h+var_150]
0x1800383d0  lea     rcx, [rbp+80h+var_A0]
0x1800383d4  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1800383d9  mov     rcx, [rbx+8]; hKey
0x1800383dd  test    rcx, rcx
0x1800383e0  jz      short loc_180038451
0x1800383e2  call    cs:__imp_RegCloseKey
0x1800383e8  mov     edi, eax
0x1800383ea  test    eax, eax
0x1800383ec  jz      short loc_180038449
0x1800383ee  xor     edx, edx; Val
0x1800383f0  mov     [rsp+180h+var_150], r14
0x1800383f5  lea     rcx, [rsp+180h+var_128]; void *
0x1800383fa  mov     [rsp+180h+var_148], r15
0x1800383ff  mov     [rsp+180h+var_140], r12
0x180038404  mov     [rsp+180h+var_138], 2A3h
0x18003840c  lea     r8d, [rdx+78h]; Size
0x180038410  mov     [rsp+180h+var_134], 0Bh
0x180038418  mov     [rsp+180h+var_130], 0FFh
0x180038420  mov     [rbp+80h+var_B0], 1000000h
0x180038427  call    memset_0
0x18003842c  mov     r9, [rbx+18h]
0x180038430  lea     r8, aErrorOnClosing; "Error on closing key with name %s. lRes"...
0x180038437  lea     rdx, [rsp+180h+var_150]
0x18003843c  mov     [rsp+180h+var_160], edi
0x180038440  lea     rcx, [rbp+80h+var_A0]
0x180038444  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180038449  mov     qword ptr [rbx+8], 0
0x180038451  lea     rcx, [rbx+10h]
0x180038455  call    ?Close@?$CVssAutoGenericValue_Storage@PEAG$0A@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6AAEAPEAGAEAPEAG@Z$1?Identity@?$DTyper@PEAG@@SAAEAPEAG1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<ushort *,0,void (*)(void *),&CoTaskMemFree(void *),ushort * & (*)(ushort * &),&DTyper<ushort *>::Identity(ushort * &)>::Close(void)
0x18003845a  lea     rcx, [rbp+80h+var_A0]; this
0x18003845e  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180038463  add     rsp, 158h
0x18003846a  pop     r15
0x18003846c  pop     r14
0x18003846e  pop     r12
0x180038470  pop     rdi
0x180038471  pop     rbx
0x180038472  pop     rbp
0x180038473  retn
```

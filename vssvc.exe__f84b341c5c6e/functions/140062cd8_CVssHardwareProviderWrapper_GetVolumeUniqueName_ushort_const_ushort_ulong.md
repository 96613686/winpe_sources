# CVssHardwareProviderWrapper::GetVolumeUniqueName(ushort const *,ushort *,ulong)

- ea: `0x140062cd8`
- end: `0x140062f4e`
- name: `?GetVolumeUniqueName@CVssHardwareProviderWrapper@@AEAA_NPEBGPEAGK@Z`
- size: `630`
- prototype: `bool(CVssHardwareProviderWrapper *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x1400c7dc8`

## callees

- `0x140011a90`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140024ef8`
- `0x140025110`
- `0x14003a8f0`
- `0x140062cd8`
- `0x140091560`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140062dea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140062e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140062dea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140062e7e`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x140062de0`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x140062e74`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x140062de0`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x140062e74`

## string_xrefs

- `0x140062edc`: `GetVolumeNameForVolumeMountPoint(%s) fail on second time. with 0x%08lx.`
- `0x140062e47`: `GetVolumeNameForVolumeMountPoint(%s) fails with 0x%08lx.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall CVssHardwareProviderWrapper::GetVolumeUniqueName(
        CVssHardwareProviderWrapper *this,
        WCHAR *a2,
        unsigned __int16 *a3)
{
  __int64 v5; // rbx
  __int64 v6; // rax
  signed int LastError; // eax
  unsigned int v8; // ebx
  WCHAR *v9; // r9
  const wchar_t *v10; // r8
  bool v11; // dl
  signed int v12; // eax
  bool v13; // bl
  unsigned int v15; // [rsp+20h] [rbp-E0h]
  void **v16; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpszVolumeMountPoint; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v18; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v19; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v20; // [rsp+58h] [rbp-A8h]
  int v21; // [rsp+60h] [rbp-A0h]
  int v22; // [rsp+64h] [rbp-9Ch]
  int v23; // [rsp+68h] [rbp-98h]
  _BYTE v24[120]; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+E8h] [rbp-18h]
  LPVOID v26[14]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR szVolumeName[264]; // [rsp+160h] [rbp+60h] BYREF

  v18 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
  v19 = L"CVssHardwareProviderWrapper::GetVolumeUniqueName";
  v20 = L"CORHWUTC";
  v21 = 1799;
  v22 = 1;
  v23 = 255;
  v25 = 0x1000000;
  memset_0(v24, 0, sizeof(v24));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v26, (__int64)&v18, 0);
  memset_0(szVolumeName, 0, 0x208u);
  lpszVolumeMountPoint = 0;
  v16 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::CopyFrom(&v16, a2);
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( a2[v6 - 1] != 92 )
    CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::Append(&v16, L"\\");
  if ( !GetVolumeNameForVolumeMountPointW(lpszVolumeMountPoint, szVolumeName, 0x104u) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v18 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
    v19 = L"CVssHardwareProviderWrapper::GetVolumeUniqueName";
    v20 = L"CORHWUTC";
    v21 = 1813;
    v22 = 6;
    v23 = 255;
    v25 = 0x1000000;
    memset_0(v24, 0, sizeof(v24));
    v9 = a2;
    v10 = L"GetVolumeNameForVolumeMountPoint(%s) fails with 0x%08lx.";
LABEL_9:
    v15 = v8;
    CVssFunctionTracer::Trace(v26, &v18, v10, v9, v15);
    v11 = 0;
    goto LABEL_18;
  }
  if ( !GetVolumeNameForVolumeMountPointW(szVolumeName, a3, 0x104u) )
  {
    v12 = GetLastError();
    v8 = v12;
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    v18 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
    v19 = L"CVssHardwareProviderWrapper::GetVolumeUniqueName";
    v20 = L"CORHWUTC";
    v21 = 1817;
    v22 = 6;
    v23 = 255;
    v25 = 0x1000000;
    memset_0(v24, 0, sizeof(v24));
    v9 = szVolumeName;
    v10 = L"GetVolumeNameForVolumeMountPoint(%s) fail on second time. with 0x%08lx.";
    goto LABEL_9;
  }
  do
    ++v5;
  while ( a3[v5] );
  if ( a3[v5 - 1] == 92 )
    a3[v5 - 1] = 0;
  v11 = 1;
LABEL_18:
  v13 = CVssFunctionTracer::Exit((CVssFunctionTracer *)v26, v11);
  CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v16);
  CVssFunctionTracer::~CVssFunctionTracer(v26);
  return v13;
}

```

## disassembly

```asm
0x140062cd8  mov     [rsp-8+arg_0], rbx
0x140062cdd  mov     [rsp-8+arg_18], rsi
0x140062ce2  push    rbp
0x140062ce3  push    rdi
0x140062ce4  push    r12
0x140062ce6  push    r13
0x140062ce8  push    r14
0x140062cea  lea     rbp, [rsp-280h]
0x140062cf2  sub     rsp, 380h
0x140062cf9  mov     rax, cs:__security_cookie
0x140062d00  xor     rax, rsp
0x140062d03  mov     [rbp+2A0h+var_30], rax
0x140062d0a  mov     rdi, r8
0x140062d0d  mov     rsi, rdx
0x140062d10  lea     r12, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x140062d17  mov     [rsp+3A0h+var_358], r12
0x140062d1c  lea     r13, aCvsshardwarepr_133; "CVssHardwareProviderWrapper::GetVolumeU"...
0x140062d23  mov     [rsp+3A0h+var_350], r13
0x140062d28  lea     rax, aCorhwutc; "CORHWUTC"
0x140062d2f  mov     [rsp+3A0h+var_348], rax
0x140062d34  mov     [rsp+3A0h+var_340], 707h
0x140062d3c  mov     [rsp+3A0h+var_33C], 1
0x140062d44  mov     [rsp+3A0h+var_338], 0FFh
0x140062d4c  xor     r14d, r14d
0x140062d4f  mov     [rbp+2A0h+var_2B8], 1000000h
0x140062d56  xor     edx, edx; Val
0x140062d58  lea     r8d, [r14+78h]; Size
0x140062d5c  lea     rcx, [rsp+3A0h+var_330]; void *
0x140062d61  call    memset_0
0x140062d66  xor     r8d, r8d
0x140062d69  lea     rdx, [rsp+3A0h+var_358]
0x140062d6e  lea     rcx, [rbp+2A0h+var_2B0]
0x140062d72  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x140062d77  nop
0x140062d78  xor     edx, edx; Val
0x140062d7a  mov     r8d, 208h; Size
0x140062d80  lea     rcx, [rbp+2A0h+szVolumeName]; void *
0x140062d84  call    memset_0
0x140062d89  mov     [rsp+3A0h+lpszVolumeMountPoint], r14
0x140062d8e  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x140062d95  mov     [rsp+3A0h+var_368], rax
0x140062d9a  mov     rdx, rsi
0x140062d9d  lea     rcx, [rsp+3A0h+var_368]
0x140062da2  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::CopyFrom(ushort const *)
0x140062da7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140062dab  mov     rax, rbx
0x140062dae  inc     rax
0x140062db1  cmp     [rsi+rax*2], r14w
0x140062db6  jnz     short loc_140062DAE
0x140062db8  cmp     word ptr [rsi+rax*2-2], 5Ch ; '\'
0x140062dbe  jz      short loc_140062DD1
0x140062dc0  lea     rdx, pszSrc; "\\"
0x140062dc7  lea     rcx, [rsp+3A0h+var_368]
0x140062dcc  call    ?Append@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::Append(ushort const *)
0x140062dd1  mov     r8d, 104h; cchBufferLength
0x140062dd7  lea     rdx, [rbp+2A0h+szVolumeName]; lpszVolumeName
0x140062ddb  mov     rcx, [rsp+3A0h+lpszVolumeMountPoint]; lpszVolumeMountPoint
0x140062de0  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x140062de6  test    eax, eax
0x140062de8  jnz     short loc_140062E67
0x140062dea  call    cs:__imp_GetLastError
0x140062df0  mov     ebx, eax
0x140062df2  test    eax, eax
0x140062df4  jle     short loc_140062DFF
0x140062df6  movzx   ebx, ax
0x140062df9  or      ebx, 80070000h
0x140062dff  mov     [rsp+3A0h+var_358], r12
0x140062e04  mov     [rsp+3A0h+var_350], r13
0x140062e09  lea     rax, aCorhwutc; "CORHWUTC"
0x140062e10  mov     [rsp+3A0h+var_348], rax
0x140062e15  mov     [rsp+3A0h+var_340], 715h
0x140062e1d  mov     [rsp+3A0h+var_33C], 6
0x140062e25  mov     [rsp+3A0h+var_338], 0FFh
0x140062e2d  mov     [rbp+2A0h+var_2B8], 1000000h
0x140062e34  xor     edx, edx; Val
0x140062e36  lea     r8d, [rdx+78h]; Size
0x140062e3a  lea     rcx, [rsp+3A0h+var_330]; void *
0x140062e3f  call    memset_0
0x140062e44  mov     r9, rsi
0x140062e47  lea     r8, aGetvolumenamef; "GetVolumeNameForVolumeMountPoint(%s) fa"...
0x140062e4e  mov     [rsp+3A0h+var_380], ebx
0x140062e52  lea     rdx, [rsp+3A0h+var_358]
0x140062e57  lea     rcx, [rbp+2A0h+var_2B0]
0x140062e5b  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140062e60  xor     edx, edx
0x140062e62  jmp     loc_140062F02
0x140062e67  mov     r8d, 104h; cchBufferLength
0x140062e6d  mov     rdx, rdi; lpszVolumeName
0x140062e70  lea     rcx, [rbp+2A0h+szVolumeName]; lpszVolumeMountPoint
0x140062e74  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x140062e7a  test    eax, eax
0x140062e7c  jnz     short loc_140062EE8
0x140062e7e  call    cs:__imp_GetLastError
0x140062e84  mov     ebx, eax
0x140062e86  test    eax, eax
0x140062e88  jle     short loc_140062E93
0x140062e8a  movzx   ebx, ax
0x140062e8d  or      ebx, 80070000h
0x140062e93  mov     [rsp+3A0h+var_358], r12
0x140062e98  mov     [rsp+3A0h+var_350], r13
0x140062e9d  lea     rax, aCorhwutc; "CORHWUTC"
0x140062ea4  mov     [rsp+3A0h+var_348], rax
0x140062ea9  mov     [rsp+3A0h+var_340], 719h
0x140062eb1  mov     [rsp+3A0h+var_33C], 6
0x140062eb9  mov     [rsp+3A0h+var_338], 0FFh
0x140062ec1  mov     [rbp+2A0h+var_2B8], 1000000h
0x140062ec8  xor     edx, edx; Val
0x140062eca  lea     r8d, [rdx+78h]; Size
0x140062ece  lea     rcx, [rsp+3A0h+var_330]; void *
0x140062ed3  call    memset_0
0x140062ed8  lea     r9, [rbp+2A0h+szVolumeName]
0x140062edc  lea     r8, aGetvolumenamef_8; "GetVolumeNameForVolumeMountPoint(%s) fa"...
0x140062ee3  jmp     loc_140062E4E
0x140062ee8  inc     rbx
0x140062eeb  cmp     [rdi+rbx*2], r14w
0x140062ef0  jnz     short loc_140062EE8
0x140062ef2  cmp     word ptr [rdi+rbx*2-2], 5Ch ; '\'
0x140062ef8  jnz     short loc_140062F00
0x140062efa  mov     [rdi+rbx*2-2], r14w
0x140062f00  mov     dl, 1; bool
0x140062f02  lea     rcx, [rbp+2A0h+var_2B0]; this
0x140062f06  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x140062f0b  mov     bl, al
0x140062f0d  lea     rcx, [rsp+3A0h+var_368]
0x140062f12  call    ??1?$CVssAutoLocalPtr@PEAX@@UEAA@XZ; CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(void)
0x140062f17  nop
0x140062f18  lea     rcx, [rbp+2A0h+var_2B0]; this
0x140062f1c  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140062f21  mov     al, bl
0x140062f23  mov     rcx, [rbp+2A0h+var_30]
0x140062f2a  xor     rcx, rsp; StackCookie
0x140062f2d  call    __security_check_cookie
0x140062f32  lea     r11, [rsp+3A0h+var_20]
0x140062f3a  mov     rbx, [r11+30h]
0x140062f3e  mov     rsi, [r11+48h]
0x140062f42  mov     rsp, r11
0x140062f45  pop     r14
0x140062f47  pop     r13
0x140062f49  pop     r12
0x140062f4b  pop     rdi
0x140062f4c  pop     rbp
0x140062f4d  retn
```

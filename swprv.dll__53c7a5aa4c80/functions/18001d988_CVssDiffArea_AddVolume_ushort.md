# CVssDiffArea::AddVolume(ushort *)

- ea: `0x18001d988`
- end: `0x18001dc36`
- name: `?AddVolume@CVssDiffArea@@QEAAXPEAG@Z`
- size: `686`
- prototype: `void __fastcall(CVssDiffArea *__hidden this, LPCWSTR lpszVolumeMountPoint)`
- caller_count: `4`
- callee_count: `12`
- tags: `reparse_path`

## callers

- `0x18001f6f0`
- `0x180020c6c`
- `0x180027ca0`
- `0x18002edd8`

## callees

- `0x180001580`
- `0x18000212c`
- `0x1800034cc`
- `0x180003888`
- `0x180003de8`
- `0x1800066fc`
- `0x180012254`
- `0x18001d988`
- `0x180033a8c`
- `0x180033c78`
- `0x18003649c`
- `0x18003750c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001daaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001daaa`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18001daa0`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18001daa0`

## string_xrefs

- `0x18001daff`: `GetVolumeNameForVolumeMountPointW( %s, ...)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssDiffArea::AddVolume(CVssDiffArea *this, LPCWSTR lpszVolumeMountPoint)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  __int64 v6; // r9
  const wchar_t *v7; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v8; // [rsp+50h] [rbp-B0h]
  const wchar_t *v9; // [rsp+58h] [rbp-A8h]
  int v10; // [rsp+60h] [rbp-A0h]
  int v11; // [rsp+64h] [rbp-9Ch]
  int v12; // [rsp+68h] [rbp-98h]
  _BYTE v13[120]; // [rsp+70h] [rbp-90h] BYREF
  int v14; // [rsp+E8h] [rbp-18h]
  LPCRITICAL_SECTION v15[2]; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID v16[14]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR szVolumeName[264]; // [rsp+170h] [rbp+70h] BYREF

  v7 = L"base\\stor\\vss\\modules\\softprv\\src\\diff.cxx";
  v8 = L"CVssDiffArea::AddVolume";
  v9 = L"SPRDIFFC";
  v10 = 212;
  v11 = 2;
  v12 = 255;
  v14 = 0x1000000;
  memset_0(v13, 0, sizeof(v13));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v16, (__int64)&v7, 0);
  if ( !lpszVolumeMountPoint )
  {
    v7 = L"base\\stor\\vss\\modules\\softprv\\src\\diff.cxx";
    v8 = L"CVssDiffArea::AddVolume";
    v9 = L"SPRDIFFC";
    v10 = 216;
    v11 = 2;
    v12 = 255;
    v14 = 0x1000000;
    memset_0(v13, 0, sizeof(v13));
    CVssFunctionTracer::Throw(v16, &v7, 2147942487LL, L"NULL pwszVolumeName");
  }
  CVssAutomaticLock2::CVssAutomaticLock2((CVssAutomaticLock2 *)v15, (CVssDiffArea *)((char *)this + 120));
  if ( !GetVolumeNameForVolumeMountPointW(lpszVolumeMountPoint, szVolumeName, 0x104u) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v7 = L"base\\stor\\vss\\modules\\softprv\\src\\diff.cxx";
    v8 = L"CVssDiffArea::AddVolume";
    v9 = L"SPRDIFFC";
    v10 = 228;
    v11 = 2;
    v12 = 255;
    v14 = 0x1000000;
    memset_0(v13, 0, sizeof(v13));
    CVssFunctionTracer::TranslateInternalProviderError(
      v16,
      &v7,
      v5,
      2147754758LL,
      L"GetVolumeNameForVolumeMountPointW( %s, ...)",
      lpszVolumeMountPoint);
  }
  if ( !IsVolMgmtVolumeName(szVolumeName) )
  {
    v7 = L"base\\stor\\vss\\modules\\softprv\\src\\diff.cxx";
    v8 = L"CVssDiffArea::AddVolume";
    v9 = L"SPRDIFFC";
    v10 = 234;
    v11 = 2;
    v12 = 255;
    v14 = 0x1000000;
    memset_0(v13, 0, sizeof(v13));
    CVssFunctionTracer::TranslateInternalProviderError(
      v16,
      &v7,
      2147549183LL,
      2147754758LL,
      L"ConvertVolMgmtVolumeNameIntoKernelObject( %s, ...)",
      szVolumeName);
  }
  szVolumeName[48] = 0;
  szVolumeName[1] = 63;
  CVssIOCTLChannel::PackSmallString(this, (struct CVssFunctionTracer *)v16, szVolumeName);
  LOBYTE(v6) = 1;
  CVssIOCTLChannel::Call(this, v16, 5488672, v6, 2, 0, 0);
  *((_DWORD *)this + 11) = 0;
  *((_DWORD *)this + 16) = 0;
  CVssAutomaticLock2::~CVssAutomaticLock2(v15);
  CVssFunctionTracer::~CVssFunctionTracer(v16);
}

```

## disassembly

```asm
0x18001d988  mov     [rsp-8+arg_10], rbx
0x18001d98d  mov     [rsp-8+arg_18], rdi
0x18001d992  push    rbp
0x18001d993  push    r12
0x18001d995  push    r13
0x18001d997  push    r14
0x18001d999  push    r15
0x18001d99b  lea     rbp, [rsp-290h]
0x18001d9a3  sub     rsp, 390h
0x18001d9aa  mov     rax, cs:__security_cookie
0x18001d9b1  xor     rax, rsp
0x18001d9b4  mov     [rbp+2B0h+var_30], rax
0x18001d9bb  mov     rdi, rdx
0x18001d9be  mov     rbx, rcx
0x18001d9c1  lea     r15, aBaseStorVssMod_4; "base\\stor\\vss\\modules\\softprv\\src"...
0x18001d9c8  mov     [rsp+3B0h+var_368], r15
0x18001d9cd  lea     r12, aCvssdiffareaAd; "CVssDiffArea::AddVolume"
0x18001d9d4  mov     [rsp+3B0h+var_360], r12
0x18001d9d9  lea     r13, aSprdiffc; "SPRDIFFC"
0x18001d9e0  mov     [rsp+3B0h+var_358], r13
0x18001d9e5  mov     [rsp+3B0h+var_350], 0D4h
0x18001d9ed  mov     r14d, 2
0x18001d9f3  mov     [rsp+3B0h+var_34C], r14d
0x18001d9f8  mov     [rsp+3B0h+var_348], 0FFh
0x18001da00  mov     [rbp+2B0h+var_2C8], 1000000h
0x18001da07  xor     edx, edx; Val
0x18001da09  lea     r8d, [r14+76h]; Size
0x18001da0d  lea     rcx, [rsp+3B0h+var_340]; void *
0x18001da12  call    memset_0
0x18001da17  xor     r8d, r8d
0x18001da1a  lea     rdx, [rsp+3B0h+var_368]
0x18001da1f  lea     rcx, [rbp+2B0h+var_2B0]
0x18001da23  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18001da28  nop
0x18001da29  test    rdi, rdi
0x18001da2c  jnz     short loc_18001DA85
0x18001da2e  mov     [rsp+3B0h+var_368], r15
0x18001da33  mov     [rsp+3B0h+var_360], r12
0x18001da38  mov     [rsp+3B0h+var_358], r13
0x18001da3d  mov     [rsp+3B0h+var_350], 0D8h
0x18001da45  mov     [rsp+3B0h+var_34C], r14d
0x18001da4a  mov     [rsp+3B0h+var_348], 0FFh
0x18001da52  mov     [rbp+2B0h+var_2C8], 1000000h
0x18001da59  xor     edx, edx; Val
0x18001da5b  lea     r8d, [r14+76h]; Size
0x18001da5f  lea     rcx, [rsp+3B0h+var_340]; void *
0x18001da64  call    memset_0
0x18001da69  lea     r9, aNullPwszvolume; "NULL pwszVolumeName"
0x18001da70  mov     r8d, 80070057h
0x18001da76  lea     rdx, [rsp+3B0h+var_368]
0x18001da7b  lea     rcx, [rbp+2B0h+var_2B0]
0x18001da7f  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18001da85  lea     rdx, [rbx+78h]; struct CVssCriticalSection *
0x18001da89  lea     rcx, [rbp+2B0h+var_2C0]; this
0x18001da8d  call    ??0CVssAutomaticLock2@@QEAA@AEAVCVssCriticalSection@@@Z; CVssAutomaticLock2::CVssAutomaticLock2(CVssCriticalSection &)
0x18001da92  nop
0x18001da93  mov     r8d, 104h; cchBufferLength
0x18001da99  lea     rdx, [rbp+2B0h+szVolumeName]; lpszVolumeName
0x18001da9d  mov     rcx, rdi; lpszVolumeMountPoint
0x18001daa0  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18001daa6  test    eax, eax
0x18001daa8  jnz     short loc_18001DB23
0x18001daaa  call    cs:__imp_GetLastError
0x18001dab0  mov     ebx, eax
0x18001dab2  test    eax, eax
0x18001dab4  jle     short loc_18001DABF
0x18001dab6  movzx   ebx, ax
0x18001dab9  or      ebx, 80070000h
0x18001dabf  mov     [rsp+3B0h+var_368], r15
0x18001dac4  mov     [rsp+3B0h+var_360], r12
0x18001dac9  mov     [rsp+3B0h+var_358], r13
0x18001dace  mov     [rsp+3B0h+var_350], 0E4h
0x18001dad6  mov     [rsp+3B0h+var_34C], r14d
0x18001dadb  mov     [rsp+3B0h+var_348], 0FFh
0x18001dae3  mov     [rbp+2B0h+var_2C8], 1000000h
0x18001daea  xor     edx, edx; Val
0x18001daec  lea     r8d, [rdx+78h]; Size
0x18001daf0  lea     rcx, [rsp+3B0h+var_340]; void *
0x18001daf5  call    memset_0
0x18001dafa  mov     [rsp+3B0h+var_388], rdi
0x18001daff  lea     rax, aGetvolumenamef_0; "GetVolumeNameForVolumeMountPointW( %s, "...
0x18001db06  mov     [rsp+3B0h+var_390], rax
0x18001db0b  mov     r9d, 80042306h
0x18001db11  mov     r8d, ebx
0x18001db14  lea     rdx, [rsp+3B0h+var_368]
0x18001db19  lea     rcx, [rbp+2B0h+var_2B0]
0x18001db1d  call    ?TranslateInternalProviderError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JJPEBGZZ; CVssFunctionTracer::TranslateInternalProviderError(CVssDebugInfo,long,long,ushort const *,...)
0x18001db23  lea     rcx, [rbp+2B0h+szVolumeName]; unsigned __int16 *
0x18001db27  call    ?IsVolMgmtVolumeName@@YA_NPEBG@Z; IsVolMgmtVolumeName(ushort const *)
0x18001db2c  test    al, al
0x18001db2e  jz      loc_18001DBCB
0x18001db34  xor     eax, eax
0x18001db36  mov     [rbp+2B0h+var_1E0], ax
0x18001db3d  mov     eax, 3Fh ; '?'
0x18001db42  mov     [rbp+2B0h+var_23E], ax
0x18001db46  lea     r8, [rbp+2B0h+szVolumeName]; unsigned __int16 *
0x18001db4a  lea     rdx, [rbp+2B0h+var_2B0]; struct CVssFunctionTracer *
0x18001db4e  mov     rcx, rbx; this
0x18001db51  call    ?PackSmallString@CVssIOCTLChannel@@QEAAPEAXAEAVCVssFunctionTracer@@PEBG@Z; CVssIOCTLChannel::PackSmallString(CVssFunctionTracer &,ushort const *)
0x18001db56  mov     [rsp+3B0h+var_380], 0
0x18001db5f  mov     byte ptr [rsp+3B0h+var_388], 0
0x18001db64  mov     dword ptr [rsp+3B0h+var_390], r14d
0x18001db69  mov     r9b, 1
0x18001db6c  mov     r8d, 53C020h
0x18001db72  lea     rdx, [rbp+2B0h+var_2B0]
0x18001db76  mov     rcx, rbx
0x18001db79  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x18001db7e  mov     dword ptr [rbx+2Ch], 0
0x18001db85  mov     dword ptr [rbx+40h], 0
0x18001db8c  lea     rcx, [rbp+2B0h+var_2C0]; this
0x18001db90  call    ??1CVssAutomaticLock2@@QEAA@XZ; CVssAutomaticLock2::~CVssAutomaticLock2(void)
0x18001db95  nop
0x18001db96  lea     rcx, [rbp+2B0h+var_2B0]; this
0x18001db9a  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18001db9f  mov     rcx, [rbp+2B0h+var_30]
0x18001dba6  xor     rcx, rsp; StackCookie
0x18001dba9  call    __security_check_cookie
0x18001dbae  lea     r11, [rsp+3B0h+var_20]
0x18001dbb6  mov     rbx, [r11+40h]
0x18001dbba  mov     rdi, [r11+48h]
0x18001dbbe  mov     rsp, r11
0x18001dbc1  pop     r15
0x18001dbc3  pop     r14
0x18001dbc5  pop     r13
0x18001dbc7  pop     r12
0x18001dbc9  pop     rbp
0x18001dbca  retn
0x18001dbcb  mov     [rsp+3B0h+var_368], r15
0x18001dbd0  mov     [rsp+3B0h+var_360], r12
0x18001dbd5  mov     [rsp+3B0h+var_358], r13
0x18001dbda  mov     [rsp+3B0h+var_350], 0EAh
0x18001dbe2  mov     [rsp+3B0h+var_34C], r14d
0x18001dbe7  mov     [rsp+3B0h+var_348], 0FFh
0x18001dbef  mov     [rbp+2B0h+var_2C8], 1000000h
0x18001dbf6  xor     edx, edx; Val
0x18001dbf8  lea     r8d, [rdx+78h]; Size
0x18001dbfc  lea     rcx, [rsp+3B0h+var_340]; void *
0x18001dc01  call    memset_0
0x18001dc06  lea     rax, [rbp+2B0h+szVolumeName]
0x18001dc0a  mov     [rsp+3B0h+var_388], rax
0x18001dc0f  lea     rax, aConvertvolmgmt; "ConvertVolMgmtVolumeNameIntoKernelObjec"...
0x18001dc16  mov     [rsp+3B0h+var_390], rax
0x18001dc1b  mov     r9d, 80042306h
0x18001dc21  mov     r8d, 8000FFFFh
0x18001dc27  lea     rdx, [rsp+3B0h+var_368]
0x18001dc2c  lea     rcx, [rbp+2B0h+var_2B0]
0x18001dc30  call    ?TranslateInternalProviderError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JJPEBGZZ; CVssFunctionTracer::TranslateInternalProviderError(CVssDebugInfo,long,long,ushort const *,...)
```

# GetVolumeNameWithCheck(CVssDebugInfo,long,ushort const *,ushort *,ulong)

- ea: `0x18002a774`
- end: `0x18002a942`
- name: `?GetVolumeNameWithCheck@@YAXUCVssDebugInfo@@JPEBGPEAGK@Z`
- size: `462`
- prototype: `void __fastcall(const struct CVssDebugInfo *, unsigned int, const WCHAR *, WCHAR *)`
- caller_count: `11`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x180027ca0`
- `0x180028aa0`
- `0x1800294e0`
- `0x180029e60`
- `0x18002a950`
- `0x18002c080`
- `0x18002c830`
- `0x18002d1f0`
- `0x18002e010`
- `0x180039394`
- `0x180040cb0`

## callees

- `0x18000212c`
- `0x18002a774`
- `0x1800339c0`
- `0x180033a8c`
- `0x180033c2c`
- `0x180033c78`
- `0x18003649c`
- `0x1800367b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a87f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a87f`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18002a875`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18002a875`

## string_xrefs

- `0x18002a854`: `GetVolumeNameForVolumeMountPointW will be called on %s`
- `0x18002a89f`: `GetVolumeNameForVolumeMountPoint(%s,...) failed with error code 0x%08lx`
- `0x18002a8fe`: `GetVolumeNameForVolumeMountPointW succeeded and the output is %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GetVolumeNameWithCheck(const struct CVssDebugInfo *a1, unsigned int a2, const WCHAR *a3, WCHAR *a4)
{
  CVssDebugInfo *v8; // rax
  int v9; // r9d
  int v10; // [rsp+30h] [rbp-D8h]
  const unsigned __int16 *v11; // [rsp+38h] [rbp-D0h] BYREF
  const wchar_t *v12; // [rsp+40h] [rbp-C8h]
  const unsigned __int16 *v13; // [rsp+48h] [rbp-C0h]
  int v14; // [rsp+50h] [rbp-B8h]
  int v15; // [rsp+54h] [rbp-B4h]
  int v16; // [rsp+58h] [rbp-B0h]
  _BYTE v17[120]; // [rsp+60h] [rbp-A8h] BYREF
  int v18; // [rsp+D8h] [rbp-30h]
  LPVOID v19[14]; // [rsp+E8h] [rbp-20h] BYREF

  v11 = L"base\\stor\\vss\\inc\\vs_vol.hxx";
  v12 = L"GetVolumeNameWithCheck";
  v13 = L"INCVOLH";
  v14 = 347;
  v15 = 11;
  v16 = 255;
  v18 = 0x1000000;
  memset_0(v17, 0, sizeof(v17));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v19, (__int64)&v11, 0);
  *a4 = 0;
  v11 = L"base\\stor\\vss\\inc\\vs_vol.hxx";
  v12 = L"GetVolumeNameWithCheck";
  v13 = L"INCVOLH";
  v14 = 355;
  v15 = 11;
  v16 = 255;
  v18 = 0x1000000;
  memset_0(v17, 0, sizeof(v17));
  CVssFunctionTracer::Trace(v19, &v11, L"GetVolumeNameForVolumeMountPointW will be called on %s", a3);
  if ( !GetVolumeNameForVolumeMountPointW(a3, a4, 0x32u) )
  {
    GetLastError();
    v8 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)&v11, a1);
    v10 = v9;
    CVssFunctionTracer::Throw(
      v19,
      v8,
      a2,
      L"GetVolumeNameForVolumeMountPoint(%s,...) failed with error code 0x%08lx",
      a3,
      v10);
  }
  v11 = L"base\\stor\\vss\\inc\\vs_vol.hxx";
  v12 = L"GetVolumeNameWithCheck";
  v13 = L"INCVOLH";
  v14 = 363;
  v15 = 11;
  v16 = 255;
  v18 = 0x1000000;
  memset_0(v17, 0, sizeof(v17));
  CVssFunctionTracer::Trace(v19, &v11, L"GetVolumeNameForVolumeMountPointW succeeded and the output is %s", a4);
  CVssFunctionTracer::~CVssFunctionTracer(v19);
  CVssDebugInfo::~CVssDebugInfo(a1);
}

```

## disassembly

```asm
0x18002a774  mov     rax, rsp
0x18002a777  mov     [rax+10h], rbx
0x18002a77b  mov     [rax+18h], rsi
0x18002a77f  mov     [rax+8], rcx
0x18002a783  push    rbp
0x18002a784  push    rdi
0x18002a785  push    r12
0x18002a787  push    r13
0x18002a789  push    r14
0x18002a78b  lea     rbp, [rax-78h]
0x18002a78f  sub     rsp, 150h
0x18002a796  mov     rsi, r9
0x18002a799  mov     rdi, r8
0x18002a79c  mov     r14d, edx
0x18002a79f  mov     rbx, rcx
0x18002a7a2  lea     r12, aBaseStorVssInc; "base\\stor\\vss\\inc\\vs_vol.hxx"
0x18002a7a9  mov     [rsp+170h+var_140], r12
0x18002a7ae  lea     r13, aGetvolumenamew; "GetVolumeNameWithCheck"
0x18002a7b5  mov     [rsp+170h+var_138], r13
0x18002a7ba  lea     rax, aIncvolh; "INCVOLH"
0x18002a7c1  mov     [rsp+170h+var_130], rax
0x18002a7c6  mov     [rsp+170h+var_128], 15Bh
0x18002a7ce  mov     [rsp+170h+var_124], 0Bh
0x18002a7d6  mov     [rsp+170h+var_120], 0FFh
0x18002a7de  mov     [rbp+70h+var_A0], 1000000h
0x18002a7e5  xor     edx, edx; Val
0x18002a7e7  lea     r8d, [rdx+78h]; Size
0x18002a7eb  lea     rcx, [rsp+170h+var_118]; void *
0x18002a7f0  call    memset_0
0x18002a7f5  xor     r8d, r8d
0x18002a7f8  lea     rdx, [rsp+170h+var_140]
0x18002a7fd  lea     rcx, [rbp+70h+var_90]
0x18002a801  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18002a806  nop
0x18002a807  xor     eax, eax
0x18002a809  mov     [rsi], ax
0x18002a80c  mov     [rsp+170h+var_140], r12
0x18002a811  mov     [rsp+170h+var_138], r13
0x18002a816  lea     rax, aIncvolh; "INCVOLH"
0x18002a81d  mov     [rsp+170h+var_130], rax
0x18002a822  mov     [rsp+170h+var_128], 163h
0x18002a82a  mov     [rsp+170h+var_124], 0Bh
0x18002a832  mov     [rsp+170h+var_120], 0FFh
0x18002a83a  mov     [rbp+70h+var_A0], 1000000h
0x18002a841  xor     edx, edx; Val
0x18002a843  lea     r8d, [rdx+78h]; Size
0x18002a847  lea     rcx, [rsp+170h+var_118]; void *
0x18002a84c  call    memset_0
0x18002a851  mov     r9, rdi
0x18002a854  lea     r8, aGetvolumenamef_2; "GetVolumeNameForVolumeMountPointW will "...
0x18002a85b  lea     rdx, [rsp+170h+var_140]
0x18002a860  lea     rcx, [rbp+70h+var_90]
0x18002a864  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18002a869  mov     r8d, 32h ; '2'; cchBufferLength
0x18002a86f  mov     rdx, rsi; lpszVolumeName
0x18002a872  mov     rcx, rdi; lpszVolumeMountPoint
0x18002a875  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18002a87b  test    eax, eax
0x18002a87d  jnz     short loc_18002A8B6
0x18002a87f  call    cs:__imp_GetLastError
0x18002a885  mov     r9d, eax
0x18002a888  mov     rdx, rbx; struct CVssDebugInfo *
0x18002a88b  lea     rcx, [rsp+170h+var_140]; this
0x18002a890  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x18002a895  mov     dword ptr [rsp+170h+var_148], r9d
0x18002a89a  mov     qword ptr [rsp+170h+var_150], rdi
0x18002a89f  lea     r9, aGetvolumenamef_3; "GetVolumeNameForVolumeMountPoint(%s,..."...
0x18002a8a6  mov     r8d, r14d
0x18002a8a9  mov     rdx, rax
0x18002a8ac  lea     rcx, [rbp+70h+var_90]
0x18002a8b0  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18002a8b6  mov     [rsp+170h+var_140], r12
0x18002a8bb  mov     [rsp+170h+var_138], r13
0x18002a8c0  lea     rax, aIncvolh; "INCVOLH"
0x18002a8c7  mov     [rsp+170h+var_130], rax
0x18002a8cc  mov     [rsp+170h+var_128], 16Bh
0x18002a8d4  mov     [rsp+170h+var_124], 0Bh
0x18002a8dc  mov     [rsp+170h+var_120], 0FFh
0x18002a8e4  mov     [rbp+70h+var_A0], 1000000h
0x18002a8eb  xor     edx, edx; Val
0x18002a8ed  lea     r8d, [rdx+78h]; Size
0x18002a8f1  lea     rcx, [rsp+170h+var_118]; void *
0x18002a8f6  call    memset_0
0x18002a8fb  mov     r9, rsi
0x18002a8fe  lea     r8, aGetvolumenamef_1; "GetVolumeNameForVolumeMountPointW succe"...
0x18002a905  lea     rdx, [rsp+170h+var_140]
0x18002a90a  lea     rcx, [rbp+70h+var_90]
0x18002a90e  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18002a913  nop
0x18002a914  lea     rcx, [rbp+70h+var_90]; this
0x18002a918  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18002a91d  nop
0x18002a91e  mov     rcx, rbx; this
0x18002a921  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x18002a926  lea     r11, [rsp+170h+var_20]
0x18002a92e  mov     rbx, [r11+38h]
0x18002a932  mov     rsi, [r11+40h]
0x18002a936  mov     rsp, r11
0x18002a939  pop     r14
0x18002a93b  pop     r13
0x18002a93d  pop     r12
0x18002a93f  pop     rdi
0x18002a940  pop     rbp
0x18002a941  retn
```

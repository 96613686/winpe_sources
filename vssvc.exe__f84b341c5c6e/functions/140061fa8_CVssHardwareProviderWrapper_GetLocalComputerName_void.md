# CVssHardwareProviderWrapper::GetLocalComputerName(void)

- ea: `0x140061fa8`
- end: `0x14006220a`
- name: `?GetLocalComputerName@CVssHardwareProviderWrapper@@AEAAPEAGXZ`
- size: `610`
- prototype: `unsigned __int16 *__fastcall(CVssHardwareProviderWrapper *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14004fd80`
- `0x1400883a0`

## callees

- `0x1400137c0`
- `0x1400138e0`
- `0x140013b00`
- `0x140015e38`
- `0x140028b48`
- `0x14003fcac`
- `0x140061fa8`
- `0x140091584`
- `0x1400919a0`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140062046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140062151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140062046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140062151`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x140062040`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x140062147`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x140062040`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x140062147`

## string_xrefs

- `0x14006209f`: `GetComputerName`
- `0x1400621ac`: `GetComputerName`
- `0x140061fd3`: `CVssHardwareProviderWrapper::GetLocalComputerName`
- `0x14006211f`: `Cannot allocate space for computer name`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int16 *__fastcall CVssHardwareProviderWrapper::GetLocalComputerName(CVssHardwareProviderWrapper *this)
{
  signed int LastError; // eax
  unsigned __int64 v2; // rax
  WCHAR *v3; // rax
  WCHAR *v4; // rbx
  signed int v5; // eax
  const unsigned __int16 *v7; // [rsp+38h] [rbp-D0h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-C8h]
  const unsigned __int16 *v9; // [rsp+48h] [rbp-C0h]
  int v10; // [rsp+50h] [rbp-B8h]
  int v11; // [rsp+54h] [rbp-B4h]
  int v12; // [rsp+58h] [rbp-B0h]
  _BYTE v13[120]; // [rsp+60h] [rbp-A8h] BYREF
  int v14; // [rsp+D8h] [rbp-30h]
  LPVOID v15; // [rsp+E8h] [rbp-20h] BYREF
  signed int v16; // [rsp+F0h] [rbp-18h]
  CVssHardwareProviderWrapper *nSize; // [rsp+178h] [rbp+70h] BYREF

  nSize = this;
  v7 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
  v8 = L"CVssHardwareProviderWrapper::GetLocalComputerName";
  v9 = L"CORHWUTC";
  v10 = 2307;
  v11 = 1;
  v12 = 255;
  v14 = 0x1000000;
  memset_0(v13, 0, sizeof(v13));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v15, (__int64)&v7, 0);
  LODWORD(nSize) = 0;
  GetComputerNameExW(ComputerNameDnsFullyQualified, 0, (LPDWORD)&nSize);
  LastError = GetLastError();
  if ( LastError != 234 )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v16 = LastError;
    v7 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
    v8 = L"CVssHardwareProviderWrapper::GetLocalComputerName";
    v9 = L"CORHWUTC";
    v10 = 2318;
    v11 = 1;
    v12 = 255;
    v14 = 0x1000000;
    memset_0(v13, 0, sizeof(v13));
    CVssFunctionTracer::CheckForError(&v15, &v7, L"GetComputerName");
  }
  v2 = 2LL * (unsigned int)nSize;
  if ( !is_mul_ok((unsigned int)nSize, 2u) )
    v2 = -1;
  v3 = (WCHAR *)operator new[](v2, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v3;
  if ( !v3 )
  {
    v7 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
    v8 = L"CVssHardwareProviderWrapper::GetLocalComputerName";
    v9 = L"CORHWUTC";
    v10 = 2324;
    v11 = 1;
    v12 = 255;
    v14 = 0x1000000;
    memset_0(v13, 0, sizeof(v13));
    CVssFunctionTracer::Throw(&v15, &v7, 2147942414LL, L"Cannot allocate space for computer name");
  }
  if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, v3, (LPDWORD)&nSize) )
  {
    v5 = GetLastError();
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    v16 = v5;
    operator delete(v4);
    v7 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
    v8 = L"CVssHardwareProviderWrapper::GetLocalComputerName";
    v9 = L"CORHWUTC";
    v10 = 2331;
    v11 = 1;
    v12 = 255;
    v14 = 0x1000000;
    memset_0(v13, 0, sizeof(v13));
    CVssFunctionTracer::TranslateWin32Error(&v15, &v7, L"GetComputerName");
  }
  CVssFunctionTracer::TraceInternalWithFormat((CVssFunctionTracer *)&v15, L"RETURN", 0xAAu, L"Returning string: %s", v4);
  CVssFunctionTracer::~CVssFunctionTracer(&v15);
  return v4;
}

```

## disassembly

```asm
0x140061fa8  mov     rax, rsp
0x140061fab  mov     [rax+18h], rbx
0x140061faf  mov     [rax+20h], r12
0x140061fb3  mov     [rax+8], rcx
0x140061fb7  push    rbp
0x140061fb8  push    r14
0x140061fba  push    r15
0x140061fbc  lea     rbp, [rax-68h]
0x140061fc0  sub     rsp, 150h
0x140061fc7  lea     r14, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x140061fce  mov     [rsp+160h+var_130], r14
0x140061fd3  lea     r15, aCvsshardwarepr_149; "CVssHardwareProviderWrapper::GetLocalCo"...
0x140061fda  mov     [rsp+160h+var_128], r15
0x140061fdf  lea     r12, aCorhwutc; "CORHWUTC"
0x140061fe6  mov     [rsp+160h+var_120], r12
0x140061feb  mov     [rsp+160h+var_118], 903h
0x140061ff3  mov     [rsp+160h+var_114], 1
0x140061ffb  mov     [rsp+160h+var_110], 0FFh
0x140062003  mov     [rbp+60h+var_90], 1000000h
0x14006200a  mov     ebx, 78h ; 'x'
0x14006200f  mov     r8d, ebx; Size
0x140062012  xor     edx, edx; Val
0x140062014  lea     rcx, [rsp+160h+var_108]; void *
0x140062019  call    memset_0
0x14006201e  xor     r8d, r8d
0x140062021  lea     rdx, [rsp+160h+var_130]
0x140062026  lea     rcx, [rbp+60h+var_80]
0x14006202a  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x14006202f  nop
0x140062030  mov     dword ptr [rbp+60h+nSize], 0
0x140062037  lea     r8, [rbp+60h+nSize]; nSize
0x14006203b  xor     edx, edx; lpBuffer
0x14006203d  lea     ecx, [rbx-75h]; NameType
0x140062040  call    cs:__imp_GetComputerNameExW
0x140062046  call    cs:__imp_GetLastError
0x14006204c  cmp     eax, 0EAh
0x140062051  jz      short loc_1400620B4
0x140062053  test    eax, eax
0x140062055  jle     short loc_14006205F
0x140062057  movzx   eax, ax
0x14006205a  or      eax, 80070000h
0x14006205f  mov     [rbp+60h+var_78], eax
0x140062062  mov     [rsp+160h+var_130], r14
0x140062067  mov     [rsp+160h+var_128], r15
0x14006206c  mov     [rsp+160h+var_120], r12
0x140062071  mov     [rsp+160h+var_118], 90Eh
0x140062079  mov     [rsp+160h+var_114], 1
0x140062081  mov     [rsp+160h+var_110], 0FFh
0x140062089  mov     [rbp+60h+var_90], 1000000h
0x140062090  mov     r8, rbx; Size
0x140062093  xor     edx, edx; Val
0x140062095  lea     rcx, [rsp+160h+var_108]; void *
0x14006209a  call    memset_0
0x14006209f  lea     r8, aGetcomputernam; "GetComputerName"
0x1400620a6  lea     rdx, [rsp+160h+var_130]
0x1400620ab  lea     rcx, [rbp+60h+var_80]
0x1400620af  call    ?CheckForError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForError(CVssDebugInfo,ushort const *)
0x1400620b4  mov     ecx, dword ptr [rbp+60h+nSize]
0x1400620b7  mov     eax, 2
0x1400620bc  mul     rcx
0x1400620bf  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400620c6  cmovb   rax, rcx
0x1400620ca  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400620d1  mov     rcx, rax; unsigned __int64
0x1400620d4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400620d9  mov     rbx, rax
0x1400620dc  test    rax, rax
0x1400620df  jnz     short loc_14006213B
0x1400620e1  mov     [rsp+160h+var_130], r14
0x1400620e6  mov     [rsp+160h+var_128], r15
0x1400620eb  mov     [rsp+160h+var_120], r12
0x1400620f0  mov     [rsp+160h+var_118], 914h
0x1400620f8  mov     [rsp+160h+var_114], 1
0x140062100  mov     [rsp+160h+var_110], 0FFh
0x140062108  mov     [rbp+60h+var_90], 1000000h
0x14006210f  xor     edx, edx; Val
0x140062111  lea     r8d, [rax+78h]; Size
0x140062115  lea     rcx, [rsp+160h+var_108]; void *
0x14006211a  call    memset_0
0x14006211f  lea     r9, aCannotAllocate_8; "Cannot allocate space for computer name"
0x140062126  mov     r8d, 8007000Eh
0x14006212c  lea     rdx, [rsp+160h+var_130]
0x140062131  lea     rcx, [rbp+60h+var_80]
0x140062135  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14006213b  lea     r8, [rbp+60h+nSize]; nSize
0x14006213f  mov     rdx, rbx; lpBuffer
0x140062142  mov     ecx, 3; NameType
0x140062147  call    cs:__imp_GetComputerNameExW
0x14006214d  test    eax, eax
0x14006214f  jnz     short loc_1400621C2
0x140062151  call    cs:__imp_GetLastError
0x140062157  test    eax, eax
0x140062159  jle     short loc_140062163
0x14006215b  movzx   eax, ax
0x14006215e  or      eax, 80070000h
0x140062163  mov     [rbp+60h+var_78], eax
0x140062166  mov     rcx, rbx; Block
0x140062169  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14006216e  mov     [rsp+160h+var_130], r14
0x140062173  mov     [rsp+160h+var_128], r15
0x140062178  mov     [rsp+160h+var_120], r12
0x14006217d  mov     [rsp+160h+var_118], 91Bh
0x140062185  mov     [rsp+160h+var_114], 1
0x14006218d  mov     [rsp+160h+var_110], 0FFh
0x140062195  mov     [rbp+60h+var_90], 1000000h
0x14006219c  xor     edx, edx; Val
0x14006219e  lea     r8d, [rdx+78h]; Size
0x1400621a2  lea     rcx, [rsp+160h+var_108]; void *
0x1400621a7  call    memset_0
0x1400621ac  lea     r8, aGetcomputernam; "GetComputerName"
0x1400621b3  lea     rdx, [rsp+160h+var_130]
0x1400621b8  lea     rcx, [rbp+60h+var_80]
0x1400621bc  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1400621c2  mov     [rsp+160h+var_140], rbx
0x1400621c7  lea     r9, aReturningStrin; "Returning string: %s"
0x1400621ce  mov     r8d, 0AAh; unsigned int
0x1400621d4  lea     rdx, aReturn; "RETURN"
0x1400621db  lea     rcx, [rbp+60h+var_80]; this
0x1400621df  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1400621e4  nop
0x1400621e5  lea     rcx, [rbp+60h+var_80]; this
0x1400621e9  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1400621ee  mov     rax, rbx
0x1400621f1  lea     r11, [rsp+160h+var_10]
0x1400621f9  mov     rbx, [r11+30h]
0x1400621fd  mov     r12, [r11+38h]
0x140062201  mov     rsp, r11
0x140062204  pop     r15
0x140062206  pop     r14
0x140062208  pop     rbp
0x140062209  retn
```

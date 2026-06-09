# CSrmRegistryKey::Open(HKEY__ *,ushort const *,...)

- ea: `0x18007691c`
- end: `0x180076c05`
- name: `?Open@CSrmRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ`
- size: `745`
- prototype: `bool(CSrmRegistryKey *__hidden this, HKEY hKey, const unsigned __int16 *, ...)`
- caller_count: `13`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18000d8ec`
- `0x180014c40`
- `0x1800176f4`
- `0x180018064`
- `0x180026bc0`
- `0x180053574`
- `0x18005d7f4`
- `0x18008b790`
- `0x18009f134`
- `0x1800a1950`
- `0x1800a53a4`
- `0x1800a6f90`
- `0x1800b0298`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18000af40`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180074a04`
- `0x180075614`
- `0x18007691c`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800769f0`
- `msvcrt!_vsnwprintf` at `0x1800769f0`
- `ADVAPI32!RegCloseKey` at `0x180076a82`
- `ADVAPI32!RegCloseKey` at `0x180076a82`
- `ADVAPI32!RegOpenKeyExW` at `0x180076a68`
- `ADVAPI32!RegOpenKeyExW` at `0x180076a68`

## string_xrefs

- `0x180076961`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x18007696d`: `CSrmRegistryKey::Open`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char CSrmRegistryKey::Open(CSrmRegistryKey *this, HKEY hKey, const unsigned __int16 *a3, ...)
{
  unsigned int v5; // eax
  int v6; // eax
  int v8; // eax
  char v9; // al
  unsigned int Hr; // ebx
  __int64 v11; // rax
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE *v13; // [rsp+50h] [rbp-B0h]
  _QWORD v14[3]; // [rsp+58h] [rbp-A8h] BYREF
  int v15; // [rsp+70h] [rbp-90h]
  int v16; // [rsp+74h] [rbp-8Ch]
  int v17; // [rsp+78h] [rbp-88h]
  _BYTE v18[96]; // [rsp+80h] [rbp-80h] BYREF
  int v19; // [rsp+E0h] [rbp-20h]
  _BYTE v20[152]; // [rsp+E8h] [rbp-18h] BYREF
  void **v21; // [rsp+180h] [rbp+80h] BYREF
  int v22; // [rsp+188h] [rbp+88h]
  wchar_t Buffer[259]; // [rsp+230h] [rbp+130h] BYREF
  __int16 v24; // [rsp+436h] [rbp+336h]
  va_list Args; // [rsp+4A8h] [rbp+3A8h] BYREF

  va_start(Args, a3);
  v14[0] = L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp";
  v14[1] = L"CSrmRegistryKey::Open";
  v14[2] = L"SRMREGSC";
  v15 = 109;
  v16 = 17;
  v17 = 255;
  v19 = 0x1000000;
  memset_0(v18, 0, sizeof(v18));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v21, (const struct CSrmDebugInfo *)v14, 0);
  v13 = 0;
  v5 = _vsnwprintf(Buffer, 0x103u, a3, Args);
  if ( v5 >= 0x104 )
  {
    v24 = 0;
    v22 = -2147024774;
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v21);
    v13 = v20;
    v11 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v20,
            (__int64)L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
            (__int64)L"SRMREGSC",
            (__int64)L"CSrmRegistryKey::Open",
            121,
            17);
    CSrmFunctionTracer::TranslateGenericError(&v21, v11, Hr, L"StringCchVPrintfW()");
  }
  if ( v5 == 259 )
    v24 = 0;
  v22 = 0;
  hKeya = 0;
  v6 = RegOpenKeyExW(hKey, Buffer, 0, *(_DWORD *)this, &hKeya);
  if ( v6 == 2 )
  {
    if ( hKeya )
      RegCloseKey(hKeya);
    hKeya = 0;
    v21 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v21);
    return 0;
  }
  else
  {
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    v22 = v6;
    if ( v6 < 0 )
    {
      v8 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v21);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v21, v8);
      v9 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v21);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v21, 0x87u, v9, 0);
    }
    v22 = v6;
    CSrmRegistryKey::Close(this);
    CSrmAutoPWSZ::CopyFrom((LPVOID *)this + 2, Buffer);
    *((_QWORD *)this + 1) = hKeya;
    hKeya = 0;
    v21 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v21);
    return 1;
  }
}

```

## disassembly

```asm
0x18007691c  mov     [rsp-8+Format], r8
0x180076921  mov     qword ptr [rsp-8+Args], r9
0x180076926  push    rbp
0x180076927  push    rbx
0x180076928  push    rdi
0x180076929  push    r12
0x18007692b  push    r13
0x18007692d  push    r14
0x18007692f  push    r15
0x180076931  lea     rbp, [rsp-350h]
0x180076939  sub     rsp, 450h
0x180076940  mov     rax, cs:__security_cookie
0x180076947  xor     rax, rsp
0x18007694a  mov     [rbp+380h+var_40], rax
0x180076951  mov     rdi, rdx
0x180076954  mov     rbx, rcx
0x180076957  lea     rax, [rsp+480h+var_428]
0x18007695c  mov     [rsp+480h+var_430], rax
0x180076961  lea     r15, aBaseFsFsrmUtil_16; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x180076968  mov     [rsp+480h+var_428], r15
0x18007696d  lea     r12, aCsrmregistryke_2; "CSrmRegistryKey::Open"
0x180076974  mov     [rsp+480h+var_420], r12
0x180076979  lea     r13, aSrmregsc; "SRMREGSC"
0x180076980  mov     [rsp+480h+var_418], r13
0x180076985  mov     [rsp+480h+var_410], 6Dh ; 'm'
0x18007698d  mov     [rsp+480h+var_40C], 11h
0x180076995  mov     [rsp+480h+var_408], 0FFh
0x18007699d  mov     [rbp+380h+var_3A0], 1000000h
0x1800769a4  xor     edx, edx; Val
0x1800769a6  lea     r8d, [rdx+60h]; Size
0x1800769aa  lea     rcx, [rbp+380h+var_400]; void *
0x1800769ae  call    memset_0
0x1800769b3  nop
0x1800769b4  xor     r8d, r8d
0x1800769b7  lea     rdx, [rsp+480h+var_428]
0x1800769bc  lea     rcx, [rbp+380h+var_300]
0x1800769c3  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800769c8  nop
0x1800769c9  mov     [rsp+480h+var_430], 0
0x1800769d2  lea     r9, [rbp+380h+Args]; Args
0x1800769d9  mov     r8, [rbp+380h+Format]; Format
0x1800769e0  mov     r14d, 103h
0x1800769e6  mov     edx, r14d; BufferCount
0x1800769e9  lea     rcx, [rbp+380h+Buffer]; Buffer
0x1800769f0  call    cs:__imp__vsnwprintf
0x1800769f6  test    eax, eax
0x1800769f8  js      loc_180076B9E
0x1800769fe  cmp     eax, r14d
0x180076a01  ja      loc_180076B9E
0x180076a07  jnz     short loc_180076A1A
0x180076a09  xor     eax, eax
0x180076a0b  mov     [rbp+380h+var_4A], ax
0x180076a12  mov     [rbp+380h+var_2F8], eax
0x180076a18  jmp     short loc_180076A24
0x180076a1a  mov     [rbp+380h+var_2F8], 0
0x180076a24  lea     r15, ??_7?$CSrmAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>::`vftable'
0x180076a2b  mov     [rsp+480h+var_440], r15
0x180076a30  mov     [rsp+480h+hKey], 0
0x180076a39  lea     r14, ??_7?$CSrmAuto@PEAUHKEY__@@V?$CSrmAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<HKEY__ *,CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::`vftable'
0x180076a40  mov     [rsp+480h+var_440], r14
0x180076a45  mov     [rsp+480h+hKey], 0
0x180076a4e  lea     rax, [rsp+480h+hKey]
0x180076a53  mov     [rsp+480h+phkResult], rax; phkResult
0x180076a58  mov     r9d, [rbx]; samDesired
0x180076a5b  xor     r8d, r8d; ulOptions
0x180076a5e  lea     rdx, [rbp+380h+Buffer]; lpSubKey
0x180076a65  mov     rcx, rdi; hKey
0x180076a68  call    cs:__imp_RegOpenKeyExW
0x180076a6e  cmp     eax, 2
0x180076a71  jnz     short loc_180076ADD
0x180076a73  mov     [rsp+480h+var_440], r14
0x180076a78  mov     rcx, [rsp+480h+hKey]; hKey
0x180076a7d  test    rcx, rcx
0x180076a80  jz      short loc_180076A88
0x180076a82  call    cs:__imp_RegCloseKey
0x180076a88  mov     [rsp+480h+hKey], 0
0x180076a91  mov     [rsp+480h+var_440], r15
0x180076a96  mov     [rsp+480h+hKey], 0
0x180076a9f  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180076aa6  mov     [rbp+380h+var_300], rax
0x180076aad  lea     rcx, [rbp+380h+var_300]; this
0x180076ab4  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180076ab9  xor     al, al
0x180076abb  mov     rcx, [rbp+380h+var_40]
0x180076ac2  xor     rcx, rsp; StackCookie
0x180076ac5  call    __security_check_cookie
0x180076aca  add     rsp, 450h
0x180076ad1  pop     r15
0x180076ad3  pop     r14
0x180076ad5  pop     r13
0x180076ad7  pop     r12
0x180076ad9  pop     rdi
0x180076ada  pop     rbx
0x180076adb  pop     rbp
0x180076adc  retn
0x180076add  test    eax, eax
0x180076adf  jle     short loc_180076AE9
0x180076ae1  movzx   eax, ax
0x180076ae4  or      eax, 80070000h
0x180076ae9  mov     [rbp+380h+var_2F8], eax
0x180076aef  test    eax, eax
0x180076af1  js      short loc_180076B60
0x180076af3  mov     [rbp+380h+var_2F8], eax
0x180076af9  mov     rcx, rbx; this
0x180076afc  call    ?Close@CSrmRegistryKey@@QEAAXXZ; CSrmRegistryKey::Close(void)
0x180076b01  lea     rcx, [rbx+10h]; this
0x180076b05  lea     rdx, [rbp+380h+Buffer]; unsigned __int16 *
0x180076b0c  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180076b11  mov     rax, [rsp+480h+hKey]
0x180076b16  mov     [rsp+480h+hKey], 0
0x180076b1f  mov     [rbx+8], rax
0x180076b23  mov     [rsp+480h+var_440], r14
0x180076b28  mov     [rsp+480h+hKey], 0
0x180076b31  mov     [rsp+480h+var_440], r15
0x180076b36  mov     [rsp+480h+hKey], 0
0x180076b3f  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180076b46  mov     [rbp+380h+var_300], rax
0x180076b4d  lea     rcx, [rbp+380h+var_300]; this
0x180076b54  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180076b59  mov     al, 1
0x180076b5b  jmp     loc_180076ABB
0x180076b60  lea     rcx, [rbp+380h+var_300]; this
0x180076b67  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180076b6c  mov     edx, eax; int
0x180076b6e  lea     rcx, [rbp+380h+var_300]; this
0x180076b75  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180076b7a  lea     rcx, [rbp+380h+var_300]; this
0x180076b81  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180076b86  mov     r8d, eax; char
0x180076b89  xor     r9d, r9d; unsigned __int16 *
0x180076b8c  mov     edx, 87h; unsigned int
0x180076b91  lea     rcx, [rbp+380h+var_300]; this
0x180076b98  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180076b9e  xor     eax, eax
0x180076ba0  mov     [rbp+380h+var_4A], ax
0x180076ba7  mov     [rbp+380h+var_2F8], 8007007Ah
0x180076bb1  lea     rcx, [rbp+380h+var_300]; this
0x180076bb8  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180076bbd  mov     ebx, eax
0x180076bbf  lea     rax, [rbp+380h+var_398]
0x180076bc3  mov     [rsp+480h+var_430], rax
0x180076bc8  mov     [rsp+480h+var_458], 11h
0x180076bd0  mov     dword ptr [rsp+480h+phkResult], 79h ; 'y'
0x180076bd8  mov     r9, r12
0x180076bdb  mov     r8, r13
0x180076bde  mov     rdx, r15
0x180076be1  lea     rcx, [rbp+380h+var_398]
0x180076be5  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180076bea  nop
0x180076beb  lea     r9, aStringcchvprin; "StringCchVPrintfW()"
0x180076bf2  mov     r8d, ebx
0x180076bf5  mov     rdx, rax
0x180076bf8  lea     rcx, [rbp+380h+var_300]
0x180076bff  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
```

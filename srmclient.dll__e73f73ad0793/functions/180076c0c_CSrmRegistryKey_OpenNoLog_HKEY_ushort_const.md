# CSrmRegistryKey::OpenNoLog(HKEY__ *,ushort const *,...)

- ea: `0x180076c0c`
- end: `0x180076ef5`
- name: `?OpenNoLog@CSrmRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ`
- size: `745`
- prototype: `bool(CSrmRegistryKey *__hidden this, HKEY hKey, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18000e290`
- `0x180069414`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18000af40`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180073d04`
- `0x180075614`
- `0x180076c0c`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180076ce0`
- `msvcrt!_vsnwprintf` at `0x180076ce0`
- `ADVAPI32!RegCloseKey` at `0x180076d72`
- `ADVAPI32!RegCloseKey` at `0x180076d72`
- `ADVAPI32!RegOpenKeyExW` at `0x180076d58`
- `ADVAPI32!RegOpenKeyExW` at `0x180076d58`

## string_xrefs

- `0x180076c51`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x180076c5d`: `CSrmRegistryKey::OpenNoLog`

## pseudocode

```c
char CSrmRegistryKey::OpenNoLog(CSrmRegistryKey *this, HKEY hKey, const unsigned __int16 *a3, ...)
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
  v14[1] = L"CSrmRegistryKey::OpenNoLog";
  v14[2] = L"SRMREGSC";
  v15 = 151;
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
            (__int64)L"CSrmRegistryKey::OpenNoLog",
            163,
            17);
    CSrmFunctionTracer::Throw(&v21, v11, Hr, L"StringCchVPrintfW()");
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
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v21, 0xB2u, v9, 0);
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
0x180076c0c  mov     [rsp-8+Format], r8
0x180076c11  mov     qword ptr [rsp-8+Args], r9
0x180076c16  push    rbp
0x180076c17  push    rbx
0x180076c18  push    rdi
0x180076c19  push    r12
0x180076c1b  push    r13
0x180076c1d  push    r14
0x180076c1f  push    r15
0x180076c21  lea     rbp, [rsp-350h]
0x180076c29  sub     rsp, 450h
0x180076c30  mov     rax, cs:__security_cookie
0x180076c37  xor     rax, rsp
0x180076c3a  mov     [rbp+380h+var_40], rax
0x180076c41  mov     rdi, rdx
0x180076c44  mov     rbx, rcx
0x180076c47  lea     rax, [rsp+480h+var_428]
0x180076c4c  mov     [rsp+480h+var_430], rax
0x180076c51  lea     r15, aBaseFsFsrmUtil_16; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x180076c58  mov     [rsp+480h+var_428], r15
0x180076c5d  lea     r12, aCsrmregistryke_0; "CSrmRegistryKey::OpenNoLog"
0x180076c64  mov     [rsp+480h+var_420], r12
0x180076c69  lea     r13, aSrmregsc; "SRMREGSC"
0x180076c70  mov     [rsp+480h+var_418], r13
0x180076c75  mov     [rsp+480h+var_410], 97h
0x180076c7d  mov     [rsp+480h+var_40C], 11h
0x180076c85  mov     [rsp+480h+var_408], 0FFh
0x180076c8d  mov     [rbp+380h+var_3A0], 1000000h
0x180076c94  xor     edx, edx; Val
0x180076c96  lea     r8d, [rdx+60h]; Size
0x180076c9a  lea     rcx, [rbp+380h+var_400]; void *
0x180076c9e  call    memset_0
0x180076ca3  nop
0x180076ca4  xor     r8d, r8d
0x180076ca7  lea     rdx, [rsp+480h+var_428]
0x180076cac  lea     rcx, [rbp+380h+var_300]
0x180076cb3  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180076cb8  nop
0x180076cb9  mov     [rsp+480h+var_430], 0
0x180076cc2  lea     r9, [rbp+380h+Args]; Args
0x180076cc9  mov     r8, [rbp+380h+Format]; Format
0x180076cd0  mov     r14d, 103h
0x180076cd6  mov     edx, r14d; BufferCount
0x180076cd9  lea     rcx, [rbp+380h+Buffer]; Buffer
0x180076ce0  call    cs:__imp__vsnwprintf
0x180076ce6  test    eax, eax
0x180076ce8  js      loc_180076E8E
0x180076cee  cmp     eax, r14d
0x180076cf1  ja      loc_180076E8E
0x180076cf7  jnz     short loc_180076D0A
0x180076cf9  xor     eax, eax
0x180076cfb  mov     [rbp+380h+var_4A], ax
0x180076d02  mov     [rbp+380h+var_2F8], eax
0x180076d08  jmp     short loc_180076D14
0x180076d0a  mov     [rbp+380h+var_2F8], 0
0x180076d14  lea     r15, ??_7?$CSrmAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>::`vftable'
0x180076d1b  mov     [rsp+480h+var_440], r15
0x180076d20  mov     [rsp+480h+hKey], 0
0x180076d29  lea     r14, ??_7?$CSrmAuto@PEAUHKEY__@@V?$CSrmAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<HKEY__ *,CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::`vftable'
0x180076d30  mov     [rsp+480h+var_440], r14
0x180076d35  mov     [rsp+480h+hKey], 0
0x180076d3e  lea     rax, [rsp+480h+hKey]
0x180076d43  mov     [rsp+480h+phkResult], rax; phkResult
0x180076d48  mov     r9d, [rbx]; samDesired
0x180076d4b  xor     r8d, r8d; ulOptions
0x180076d4e  lea     rdx, [rbp+380h+Buffer]; lpSubKey
0x180076d55  mov     rcx, rdi; hKey
0x180076d58  call    cs:__imp_RegOpenKeyExW
0x180076d5e  cmp     eax, 2
0x180076d61  jnz     short loc_180076DCD
0x180076d63  mov     [rsp+480h+var_440], r14
0x180076d68  mov     rcx, [rsp+480h+hKey]; hKey
0x180076d6d  test    rcx, rcx
0x180076d70  jz      short loc_180076D78
0x180076d72  call    cs:__imp_RegCloseKey
0x180076d78  mov     [rsp+480h+hKey], 0
0x180076d81  mov     [rsp+480h+var_440], r15
0x180076d86  mov     [rsp+480h+hKey], 0
0x180076d8f  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180076d96  mov     [rbp+380h+var_300], rax
0x180076d9d  lea     rcx, [rbp+380h+var_300]; this
0x180076da4  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180076da9  xor     al, al
0x180076dab  mov     rcx, [rbp+380h+var_40]
0x180076db2  xor     rcx, rsp; StackCookie
0x180076db5  call    __security_check_cookie
0x180076dba  add     rsp, 450h
0x180076dc1  pop     r15
0x180076dc3  pop     r14
0x180076dc5  pop     r13
0x180076dc7  pop     r12
0x180076dc9  pop     rdi
0x180076dca  pop     rbx
0x180076dcb  pop     rbp
0x180076dcc  retn
0x180076dcd  test    eax, eax
0x180076dcf  jle     short loc_180076DD9
0x180076dd1  movzx   eax, ax
0x180076dd4  or      eax, 80070000h
0x180076dd9  mov     [rbp+380h+var_2F8], eax
0x180076ddf  test    eax, eax
0x180076de1  js      short loc_180076E50
0x180076de3  mov     [rbp+380h+var_2F8], eax
0x180076de9  mov     rcx, rbx; this
0x180076dec  call    ?Close@CSrmRegistryKey@@QEAAXXZ; CSrmRegistryKey::Close(void)
0x180076df1  lea     rcx, [rbx+10h]; this
0x180076df5  lea     rdx, [rbp+380h+Buffer]; unsigned __int16 *
0x180076dfc  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180076e01  mov     rax, [rsp+480h+hKey]
0x180076e06  mov     [rsp+480h+hKey], 0
0x180076e0f  mov     [rbx+8], rax
0x180076e13  mov     [rsp+480h+var_440], r14
0x180076e18  mov     [rsp+480h+hKey], 0
0x180076e21  mov     [rsp+480h+var_440], r15
0x180076e26  mov     [rsp+480h+hKey], 0
0x180076e2f  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180076e36  mov     [rbp+380h+var_300], rax
0x180076e3d  lea     rcx, [rbp+380h+var_300]; this
0x180076e44  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180076e49  mov     al, 1
0x180076e4b  jmp     loc_180076DAB
0x180076e50  lea     rcx, [rbp+380h+var_300]; this
0x180076e57  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180076e5c  mov     edx, eax; int
0x180076e5e  lea     rcx, [rbp+380h+var_300]; this
0x180076e65  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180076e6a  lea     rcx, [rbp+380h+var_300]; this
0x180076e71  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180076e76  mov     r8d, eax; char
0x180076e79  xor     r9d, r9d; unsigned __int16 *
0x180076e7c  mov     edx, 0B2h; unsigned int
0x180076e81  lea     rcx, [rbp+380h+var_300]; this
0x180076e88  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x180076e8e  xor     eax, eax
0x180076e90  mov     [rbp+380h+var_4A], ax
0x180076e97  mov     [rbp+380h+var_2F8], 8007007Ah
0x180076ea1  lea     rcx, [rbp+380h+var_300]; this
0x180076ea8  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180076ead  mov     ebx, eax
0x180076eaf  lea     rax, [rbp+380h+var_398]
0x180076eb3  mov     [rsp+480h+var_430], rax
0x180076eb8  mov     [rsp+480h+var_458], 11h
0x180076ec0  mov     dword ptr [rsp+480h+phkResult], 0A3h
0x180076ec8  mov     r9, r12
0x180076ecb  mov     r8, r13
0x180076ece  mov     rdx, r15
0x180076ed1  lea     rcx, [rbp+380h+var_398]
0x180076ed5  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180076eda  nop
0x180076edb  lea     r9, aStringcchvprin; "StringCchVPrintfW()"
0x180076ee2  mov     r8d, ebx
0x180076ee5  mov     rdx, rax
0x180076ee8  lea     rcx, [rbp+380h+var_300]
0x180076eef  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```

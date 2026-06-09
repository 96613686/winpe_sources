# WinSAT::CompressionWorkload::SetupWorkSpace(ulong)

- ea: `0x140078b6c`
- end: `0x140078e8a`
- name: `?SetupWorkSpace@CompressionWorkload@WinSAT@@AEAAKK@Z`
- size: `798`
- prototype: `unsigned int __fastcall(WinSAT::CompressionWorkload *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140078e90`

## callees

- `0x140004170`
- `0x140004348`
- `0x140007f14`
- `0x140008178`
- `0x140017af0`
- `0x14004fce4`
- `0x1400530a8`
- `0x140078b6c`
- `0x140113220`
- `0x140118218`
- `0x140118674`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140078c41`
- `KERNEL32!EnterCriticalSection` at `0x140078d92`
- `KERNEL32!EnterCriticalSection` at `0x140078e4b`
- `KERNEL32!EnterCriticalSection` at `0x140078c41`
- `KERNEL32!EnterCriticalSection` at `0x140078d92`
- `KERNEL32!EnterCriticalSection` at `0x140078e4b`
- `KERNEL32!LeaveCriticalSection` at `0x140078d15`
- `KERNEL32!LeaveCriticalSection` at `0x140078de7`
- `KERNEL32!LeaveCriticalSection` at `0x140078d15`
- `KERNEL32!LeaveCriticalSection` at `0x140078de7`
- `KERNEL32!GetLastError` at `0x140078d5f`
- `KERNEL32!GetLastError` at `0x140078e18`
- `KERNEL32!GetLastError` at `0x140078d5f`
- `KERNEL32!GetLastError` at `0x140078e18`
- `KERNEL32!VirtualLock` at `0x140078e0a`
- `KERNEL32!VirtualLock` at `0x140078e0a`
- `KERNEL32!VirtualAlloc` at `0x140078d49`
- `KERNEL32!VirtualAlloc` at `0x140078d49`
- `KERNEL32!SetLastError` at `0x140078df3`
- `KERNEL32!SetLastError` at `0x140078df3`
- `ntdll!RtlGetCompressionWorkSpaceSize` at `0x140078c09`
- `ntdll!RtlGetCompressionWorkSpaceSize` at `0x140078c09`
- `ntdll!RtlNtStatusToDosError` at `0x140078c15`
- `ntdll!RtlNtStatusToDosError` at `0x140078c15`

## string_xrefs

- `0x140078da7`: `base\winsat\cpu\compression.cpp`
- `0x140078c98`: `> Compression buffer workspace size (CPU `
- `0x140078cd7`: `> Decompression fragment size (CPU `

## pseudocode

```c
DWORD __fastcall WinSAT::CompressionWorkload::SetupWorkSpace(WinSAT::CompressionWorkload *this, unsigned int a2)
{
  int v2; // eax
  __int64 v4; // rax
  __int64 v5; // rax
  NTSTATUS CompressionWorkSpaceSize; // eax
  SIZE_T v8; // rdx
  bool v9; // zf
  __int64 *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 *v14; // rax
  __int64 *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 *v19; // rax
  __int64 *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  void *v24; // rax
  DWORD v25; // eax
  int v26; // r8d
  __int64 v27; // rdx
  __int64 v28; // rbx
  const unsigned __int16 *v29; // rax
  __int64 *v30; // rax
  __int64 *v31; // rax
  __int64 *v32; // rax
  DWORD LastError; // eax
  ULONG CompressBufferWorkSpaceSize[4]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD Buffer[64]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwErrCode; // [rsp+230h] [rbp+130h]
  char v37; // [rsp+234h] [rbp+134h]
  __int64 v38; // [rsp+238h] [rbp+138h]

  v2 = *((_DWORD *)this + 214);
  CompressBufferWorkSpaceSize[0] = 0;
  CompressBufferWorkSpaceSize[1] = 0;
  if ( v2 == 1 )
  {
    v4 = XpressEncodeCreate(a2);
    *((_QWORD *)this + 108) = v4;
    if ( v4 )
    {
      v5 = XpressDecodeCreate();
      *((_QWORD *)this + 109) = v5;
      if ( v5 )
      {
        *((_DWORD *)this + 254) = 0;
        return 0;
      }
    }
    return 31;
  }
  else if ( v2 )
  {
    return 87;
  }
  else
  {
    CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(
                                 2u,
                                 CompressBufferWorkSpaceSize,
                                 &CompressBufferWorkSpaceSize[1]);
    if ( CompressionWorkSpaceSize )
    {
      return RtlNtStatusToDosError(CompressionWorkSpaceSize);
    }
    else
    {
      v8 = CompressBufferWorkSpaceSize[1];
      if ( CompressBufferWorkSpaceSize[0] > CompressBufferWorkSpaceSize[1] )
        v8 = CompressBufferWorkSpaceSize[0];
      v9 = *((_BYTE *)this + 24) == 0;
      *((_DWORD *)this + 254) = v8;
      if ( !v9 )
      {
        EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
        v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                (__int64)L"> Workspace size (CPU ");
        v11 = std::basic_ostream<unsigned short>::operator<<((__int64)v10, *((_DWORD *)this + 22));
        v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, "): ");
        v13 = std::basic_ostream<unsigned short>::operator<<(v12, *((_DWORD *)this + 254));
        v14 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v13, 10);
        v15 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                v14,
                (__int64)L"> Compression buffer workspace size (CPU ");
        v16 = std::basic_ostream<unsigned short>::operator<<((__int64)v15, *((_DWORD *)this + 22));
        v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v16, "): ");
        v18 = std::basic_ostream<unsigned short>::operator<<(v17, CompressBufferWorkSpaceSize[0]);
        v19 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v18, 10);
        v20 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                v19,
                (__int64)L"> Decompression fragment size (CPU ");
        v21 = std::basic_ostream<unsigned short>::operator<<((__int64)v20, *((_DWORD *)this + 22));
        v22 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v21, "): ");
        v23 = std::basic_ostream<unsigned short>::operator<<(v22, CompressBufferWorkSpaceSize[1]);
        std::endl(v23);
        LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
        v8 = *((unsigned int *)this + 254);
      }
      v24 = VirtualAlloc(0, v8, 0x1000u, *(_BYTE *)(*((_QWORD *)this + 106) + 8377LL) != 0 ? 4 : 516);
      *((_QWORD *)this + 125) = v24;
      if ( v24 )
      {
        if ( VirtualLock(v24, *((unsigned int *)this + 254)) )
          return 0;
        LastError = GetLastError();
        v37 = 1;
        dwErrCode = LastError;
        v38 = 0;
        mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
        _InterlockedIncrement(*((volatile signed __int32 **)this + 4));
        EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
        v26 = 513;
        v27 = 992;
      }
      else
      {
        v25 = GetLastError();
        v37 = 1;
        dwErrCode = v25;
        v38 = 0;
        mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
        _InterlockedIncrement(*((volatile signed __int32 **)this + 4));
        EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
        v26 = 512;
        v27 = 972;
      }
      v28 = *((_QWORD *)this + 2);
      v29 = mlib::MUISpf_(
              (mlib *)"base\\winsat\\cpu\\compression.cpp",
              (const char *)v27,
              v26,
              *((_DWORD *)this + 22),
              *(_QWORD *)CompressBufferWorkSpaceSize);
      v30 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)(v28 + 240), (__int64)v29);
      v31 = (__int64 *)std::endl(v30);
      v32 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v31, (__int64)Buffer);
      std::endl(v32);
      LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
      SetLastError(dwErrCode);
      return dwErrCode;
    }
  }
}

```

## disassembly

```asm
0x140078b6c  mov     [rsp-8+arg_10], rbx
0x140078b71  mov     [rsp-8+arg_18], rdi
0x140078b76  push    rbp
0x140078b77  lea     rbp, [rsp-150h]
0x140078b7f  sub     rsp, 250h
0x140078b86  mov     rax, cs:__security_cookie
0x140078b8d  xor     rax, rsp
0x140078b90  mov     [rbp+150h+var_10], rax
0x140078b97  mov     eax, [rcx+358h]
0x140078b9d  mov     rdi, rcx
0x140078ba0  mov     [rsp+250h+CompressBufferWorkSpaceSize], 0
0x140078ba8  mov     [rsp+250h+CompressFragmentWorkSpaceSize], 0
0x140078bb0  cmp     eax, 1
0x140078bb3  jnz     short loc_140078BF4
0x140078bb5  mov     ecx, edx
0x140078bb7  call    XpressEncodeCreate
0x140078bbc  mov     [rdi+360h], rax
0x140078bc3  test    rax, rax
0x140078bc6  jz      short loc_140078BEA
0x140078bc8  call    XpressDecodeCreate
0x140078bcd  mov     [rdi+368h], rax
0x140078bd4  test    rax, rax
0x140078bd7  jz      short loc_140078BEA
0x140078bd9  mov     dword ptr [rdi+3F8h], 0
0x140078be3  xor     eax, eax
0x140078be5  jmp     loc_140078E66
0x140078bea  mov     eax, 1Fh
0x140078bef  jmp     loc_140078E66
0x140078bf4  test    eax, eax
0x140078bf6  jnz     loc_140078E61
0x140078bfc  lea     ecx, [rax+2]; CompressionFormatAndEngine
0x140078bff  lea     r8, [rsp+250h+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x140078c04  lea     rdx, [rsp+250h+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x140078c09  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x140078c0f  test    eax, eax
0x140078c11  jz      short loc_140078C20
0x140078c13  mov     ecx, eax; Status
0x140078c15  call    cs:__imp_RtlNtStatusToDosError
0x140078c1b  jmp     loc_140078E66
0x140078c20  mov     edx, [rsp+250h+CompressFragmentWorkSpaceSize]
0x140078c24  cmp     [rsp+250h+CompressBufferWorkSpaceSize], edx
0x140078c28  cmova   edx, [rsp+250h+CompressBufferWorkSpaceSize]
0x140078c2d  cmp     byte ptr [rdi+18h], 0
0x140078c31  mov     [rdi+3F8h], edx
0x140078c37  jz      loc_140078D21
0x140078c3d  mov     rcx, [rdi+50h]; lpCriticalSection
0x140078c41  call    cs:__imp_EnterCriticalSection
0x140078c47  mov     rcx, [rdi+8]
0x140078c4b  lea     rdx, aWorkspaceSizeC; "> Workspace size (CPU "
0x140078c52  add     rcx, 0F0h
0x140078c59  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140078c5e  mov     edx, [rdi+58h]
0x140078c61  mov     rcx, rax
0x140078c64  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140078c69  mov     rcx, rax
0x140078c6c  lea     rdx, asc_1401417DC; "): "
0x140078c73  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x140078c78  mov     edx, [rdi+3F8h]
0x140078c7e  mov     rcx, rax
0x140078c81  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140078c86  mov     ebx, 0Ah
0x140078c8b  mov     rcx, rax
0x140078c8e  mov     edx, ebx
0x140078c90  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x140078c95  mov     rcx, rax
0x140078c98  lea     rdx, aCompressionBuf; "> Compression buffer workspace size (CP"...
0x140078c9f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140078ca4  mov     edx, [rdi+58h]
0x140078ca7  mov     rcx, rax
0x140078caa  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140078caf  mov     rcx, rax
0x140078cb2  lea     rdx, asc_1401417DC; "): "
0x140078cb9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x140078cbe  mov     edx, [rsp+250h+CompressBufferWorkSpaceSize]
0x140078cc2  mov     rcx, rax
0x140078cc5  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140078cca  mov     edx, ebx
0x140078ccc  mov     rcx, rax
0x140078ccf  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x140078cd4  mov     rcx, rax
0x140078cd7  lea     rdx, aDecompressionF; "> Decompression fragment size (CPU "
0x140078cde  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140078ce3  mov     edx, [rdi+58h]
0x140078ce6  mov     rcx, rax
0x140078ce9  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140078cee  mov     rcx, rax
0x140078cf1  lea     rdx, asc_1401417DC; "): "
0x140078cf8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x140078cfd  mov     edx, [rsp+250h+CompressFragmentWorkSpaceSize]
0x140078d01  mov     rcx, rax
0x140078d04  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140078d09  mov     rcx, rax
0x140078d0c  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140078d11  mov     rcx, [rdi+50h]; lpCriticalSection
0x140078d15  call    cs:__imp_LeaveCriticalSection
0x140078d1b  mov     edx, [rdi+3F8h]; dwSize
0x140078d21  mov     rax, [rdi+350h]
0x140078d28  mov     r8d, 1000h; flAllocationType
0x140078d2e  mov     cl, [rax+20B9h]
0x140078d34  neg     cl
0x140078d36  sbb     r9d, r9d
0x140078d39  xor     ecx, ecx; lpAddress
0x140078d3b  and     r9d, 0FFFFFE00h
0x140078d42  add     r9d, 204h; flProtect
0x140078d49  call    cs:__imp_VirtualAlloc
0x140078d4f  mov     [rdi+3E8h], rax
0x140078d56  test    rax, rax
0x140078d59  jnz     loc_140078E01
0x140078d5f  call    cs:__imp_GetLastError
0x140078d65  lea     rcx, [rsp+250h+Buffer]; lpBuffer
0x140078d6a  mov     [rbp+150h+var_1C], 1
0x140078d71  mov     [rbp+150h+dwErrCode], eax
0x140078d77  mov     [rbp+150h+var_18], 0
0x140078d82  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x140078d87  mov     rax, [rdi+20h]
0x140078d8b  lock inc dword ptr [rax]
0x140078d8e  mov     rcx, [rdi+50h]; lpCriticalSection
0x140078d92  call    cs:__imp_EnterCriticalSection
0x140078d98  mov     r8d, 200h; int
0x140078d9e  mov     edx, 3CCh; char *
0x140078da3  mov     r9d, [rdi+58h]; unsigned __int16
0x140078da7  lea     rcx, aBaseWinsatCpuC_0; "base\\winsat\\cpu\\compression.cpp"
0x140078dae  mov     rbx, [rdi+10h]
0x140078db2  call    ?MUISpf_@mlib@@YAPEBGPEBDHGZZ; mlib::MUISpf_(char const *,int,ushort,...)
0x140078db7  mov     rdx, rax
0x140078dba  lea     rcx, [rbx+0F0h]
0x140078dc1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140078dc6  mov     rcx, rax
0x140078dc9  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140078dce  lea     rdx, [rsp+250h+Buffer]
0x140078dd3  mov     rcx, rax
0x140078dd6  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140078ddb  mov     rcx, rax
0x140078dde  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140078de3  mov     rcx, [rdi+50h]; lpCriticalSection
0x140078de7  call    cs:__imp_LeaveCriticalSection
0x140078ded  mov     ecx, [rbp+150h+dwErrCode]; dwErrCode
0x140078df3  call    cs:__imp_SetLastError
0x140078df9  mov     eax, [rbp+150h+dwErrCode]
0x140078dff  jmp     short loc_140078E66
0x140078e01  mov     edx, [rdi+3F8h]; dwSize
0x140078e07  mov     rcx, rax; lpAddress
0x140078e0a  call    cs:__imp_VirtualLock
0x140078e10  test    eax, eax
0x140078e12  jnz     loc_140078BE3
0x140078e18  call    cs:__imp_GetLastError
0x140078e1e  lea     rcx, [rsp+250h+Buffer]; lpBuffer
0x140078e23  mov     [rbp+150h+var_1C], 1
0x140078e2a  mov     [rbp+150h+dwErrCode], eax
0x140078e30  mov     [rbp+150h+var_18], 0
0x140078e3b  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x140078e40  mov     rax, [rdi+20h]
0x140078e44  lock inc dword ptr [rax]
0x140078e47  mov     rcx, [rdi+50h]; lpCriticalSection
0x140078e4b  call    cs:__imp_EnterCriticalSection
0x140078e51  mov     r8d, 201h
0x140078e57  mov     edx, 3E0h
0x140078e5c  jmp     loc_140078DA3
0x140078e61  mov     eax, 57h ; 'W'
0x140078e66  mov     rcx, [rbp+150h+var_10]
0x140078e6d  xor     rcx, rsp; StackCookie
0x140078e70  call    __security_check_cookie
0x140078e75  lea     r11, [rsp+250h+var_s0]
0x140078e7d  mov     rbx, [r11+20h]
0x140078e81  mov     rdi, [r11+28h]
0x140078e85  mov     rsp, r11
0x140078e88  pop     rbp
0x140078e89  retn
```

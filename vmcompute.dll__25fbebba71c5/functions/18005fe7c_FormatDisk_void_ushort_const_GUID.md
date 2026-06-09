# FormatDisk(void *,ushort const *,_GUID)

- ea: `0x18005fe7c`
- end: `0x180060338`
- name: `?FormatDisk@@YA?AUPartitionInfo@@PEAXPEBGU_GUID@@@Z`
- size: `1212`
- prototype: `struct PartitionInfo __high(void *, const unsigned __int16 *, struct _GUID)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800369c0`
- `0x18005ca68`

## callees

- `0x180002f50`
- `0x180003c78`
- `0x18000481d`
- `0x180006158`
- `0x180006660`
- `0x18000d0ec`
- `0x18000d108`
- `0x180018bd4`
- `0x18005fe7c`
- `0x180060490`
- `0x180060c10`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005fec8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005fec8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fef6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fef6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006027e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006027e`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180060153`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180060153`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180060163`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180060163`
- `RPCRT4!UuidCreate` at `0x180060016`
- `RPCRT4!UuidCreate` at `0x180060016`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005ff5c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005ffb9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800600f6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005ff5c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005ffb9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800600f6`
- `KERNELBASE!Sleep` at `0x18006020b`
- `KERNELBASE!Sleep` at `0x18006020b`

## string_xrefs

- `0x1800602b1`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x1800602d8`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x1800602ea`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x1800602fc`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x18006030e`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x180060323`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x18005fec1`: `fmifs.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_OWORD *__fastcall FormatDisk(_OWORD *a1, void *a2, __int64 a3, UUID *a4)
{
  HMODULE Library; // rax
  const char *v9; // r9
  HMODULE v10; // rbx
  const char *v11; // r9
  FARPROC ProcAddress; // r12
  const char *v13; // r9
  const char *v14; // r9
  UUID v15; // xmm1
  const char *v16; // r9
  __int64 DiskVolumePath; // rax
  int v18; // esi
  __int64 v19; // r15
  __int128 *v20; // rcx
  signed int Data1; // r14d
  unsigned int v23; // eax
  _QWORD v24[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+60h] [rbp-A0h]
  __int128 v26; // [rsp+70h] [rbp-90h]
  __int64 v27; // [rsp+80h] [rbp-80h]
  DWORD BytesReturned[4]; // [rsp+90h] [rbp-70h] BYREF
  UUID Uuid; // [rsp+A0h] [rbp-60h] BYREF
  int v30; // [rsp+B0h] [rbp-50h]
  RTL_CONDITION_VARIABLE ConditionVariable; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v32; // [rsp+C0h] [rbp-40h]
  __int128 v33; // [rsp+D0h] [rbp-30h] BYREF
  __m128i si128; // [rsp+E0h] [rbp-20h]
  __int128 v35; // [rsp+F0h] [rbp-10h]
  UUID v36; // [rsp+100h] [rbp+0h]
  __int128 InBuffer; // [rsp+110h] [rbp+10h] BYREF
  __int64 v38; // [rsp+120h] [rbp+20h]
  _BYTE OutBuffer[4]; // [rsp+130h] [rbp+30h] BYREF
  int v40; // [rsp+134h] [rbp+34h]
  __int128 v41; // [rsp+138h] [rbp+38h]
  __int64 v42; // [rsp+148h] [rbp+48h]
  __int64 v43; // [rsp+150h] [rbp+50h]
  int v44; // [rsp+160h] [rbp+60h]
  __int64 v45; // [rsp+168h] [rbp+68h]
  __int64 v46; // [rsp+170h] [rbp+70h]
  int v47; // [rsp+178h] [rbp+78h]
  char v48; // [rsp+17Ch] [rbp+7Ch]
  GUID v49; // [rsp+180h] [rbp+80h]
  int v50; // [rsp+1F0h] [rbp+F0h]
  __int64 v51; // [rsp+1F8h] [rbp+F8h]
  __int64 v52; // [rsp+200h] [rbp+100h]
  int v53; // [rsp+208h] [rbp+108h]
  char v54; // [rsp+20Ch] [rbp+10Ch]
  GUID v55; // [rsp+210h] [rbp+110h]
  UUID v56; // [rsp+220h] [rbp+120h]
  unsigned __int64 v57; // [rsp+230h] [rbp+130h]
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  *(_QWORD *)BytesReturned = a1;
  Library = LoadLibraryExW(L"fmifs.dll", 0, 0x800u);
  v10 = Library;
  if ( !Library )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1DE,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      v9);
  ProcAddress = GetProcAddress(Library, "FormatEx2");
  if ( !ProcAddress )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1E1,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      v11);
  InBuffer = 0;
  v38 = 0;
  LODWORD(InBuffer) = 1;
  BytesReturned[0] = 0;
  if ( !DeviceIoControl(a2, 0x7C058u, &InBuffer, 0x18u, 0, 0, BytesReturned, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      v13);
  memset_0(OutBuffer, 0, 0x150u);
  if ( !DeviceIoControl(a2, 0x70050u, 0, 0, OutBuffer, 0x150u, BytesReturned, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1FE,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      v14);
  v33 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v33) = 0;
  v36 = 0;
  v35 = v41;
  if ( !memcmp_0(&GUID_00000000_0000_0000_0000_000000000000, a4, 0x10u) )
  {
    Uuid = 0;
    UuidCreate(&Uuid);
    v15 = Uuid;
  }
  else
  {
    v15 = *a4;
  }
  v36 = v15;
  v40 = 2;
  v44 = 1;
  v45 = 0x100000;
  v46 = 0x8000000;
  v47 = 0;
  v48 = 1;
  v49 = PARTITION_MSFT_RESERVED_GUID;
  v50 = 1;
  v51 = 135266304;
  v52 = v42 - 135266304 + v43;
  v53 = 1;
  v54 = 1;
  v55 = PARTITION_BASIC_DATA_GUID;
  v56 = v15;
  v57 = 0x8000000000000000uLL;
  if ( !DeviceIoControl(a2, 0x7C054u, OutBuffer, 0x150u, 0, 0, BytesReturned, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x228,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      v16);
  DiskVolumePath = GetDiskVolumePath(&Uuid, a2);
  std::wstring::operator=(&v33, DiskVolumePath);
  std::wstring::~wstring(&Uuid);
  v18 = 0;
  v19 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  while ( 1 )
  {
    Uuid.Data1 = -2147418113;
    v30 = 0;
    InitializeSRWLock((PSRWLOCK)Uuid.Data4);
    InitializeConditionVariable(&ConditionVariable);
    v32 = 1;
    *(_QWORD *)(v19 + 6992) = &Uuid;
    v24[0] = 0x204500000002LL;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v24[1] = &qword_18008E1B0;
    v20 = &v33;
    if ( si128.m128i_i64[1] > 7uLL )
      v20 = (__int128 *)v33;
    ((void (__fastcall *)(__int128 *, __int64, __int64, _QWORD *))ProcAddress)(v20, 12, a3, v24);
    Vml::VmSlimEvent::Wait((PSRWLOCK)Uuid.Data4, 0xFFFFFFFF);
    Data1 = Uuid.Data1;
    *(_QWORD *)(v19 + 6992) = 0;
    if ( Data1 >= 0 )
      break;
    Sleep(0x3E8u);
    if ( ++v18 >= 3 )
    {
      v23 = wil::verify_hresult<long>((unsigned int)Data1);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x283,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
        (const char *)v23,
        (int)lambda_84911dc0c7d45ac9e8b2066b124b16a3_::_lambda_invoker_cdecl_);
    }
  }
  *a1 = 0;
  *a1 = v33;
  a1[1] = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v33) = 0;
  a1[2] = v35;
  a1[3] = v36;
  std::wstring::~wstring(&v33);
  FreeLibrary(v10);
  return a1;
}

```

## disassembly

```asm
0x18005fe7c  push    rbp
0x18005fe7e  push    rbx
0x18005fe7f  push    rsi
0x18005fe80  push    rdi
0x18005fe81  push    r12
0x18005fe83  push    r13
0x18005fe85  push    r14
0x18005fe87  push    r15
0x18005fe89  lea     rbp, [rsp-198h]
0x18005fe91  sub     rsp, 298h
0x18005fe98  mov     rax, cs:__security_cookie
0x18005fe9f  xor     rax, rsp
0x18005fea2  mov     [rbp+1D0h+var_50], rax
0x18005fea9  mov     r15, r9
0x18005feac  mov     r13, r8
0x18005feaf  mov     rsi, rdx
0x18005feb2  mov     rdi, rcx
0x18005feb5  mov     qword ptr [rbp+1D0h+BytesReturned], rcx
0x18005feb9  xor     edx, edx; hFile
0x18005febb  mov     r8d, 800h; dwFlags
0x18005fec1  lea     rcx, LibFileName; "fmifs.dll"
0x18005fec8  call    cs:__imp_LoadLibraryExW
0x18005fecf  nop     dword ptr [rax+rax+00h]
0x18005fed4  mov     rbx, rax
0x18005fed7  mov     [rsp+2D0h+var_288], rax
0x18005fedc  mov     rcx, [rbp+1D8h]; this
0x18005fee3  test    rax, rax
0x18005fee6  jz      loc_1800602EA
0x18005feec  lea     rdx, aFormatex2; "FormatEx2"
0x18005fef3  mov     rcx, rax; hModule
0x18005fef6  call    cs:__imp_GetProcAddress
0x18005fefd  nop     dword ptr [rax+rax+00h]
0x18005ff02  mov     r12, rax
0x18005ff05  mov     rcx, [rbp+1D8h]; this
0x18005ff0c  test    rax, rax
0x18005ff0f  jz      loc_1800602FC
0x18005ff15  xorps   xmm0, xmm0
0x18005ff18  xor     eax, eax
0x18005ff1a  movups  [rbp+1D0h+InBuffer], xmm0
0x18005ff1e  mov     [rbp+1D0h+var_1B0], rax
0x18005ff22  mov     dword ptr [rbp+1D0h+InBuffer], 1
0x18005ff29  mov     [rbp+1D0h+BytesReturned], eax
0x18005ff2c  mov     r14, [rbp+1D8h]
0x18005ff33  xor     ecx, ecx
0x18005ff35  mov     [rsp+2D0h+lpOverlapped], rcx; lpOverlapped
0x18005ff3a  lea     rax, [rbp+1D0h+BytesReturned]
0x18005ff3e  mov     [rsp+2D0h+lpBytesReturned], rax; lpBytesReturned
0x18005ff43  mov     [rsp+2D0h+nOutBufferSize], ecx; nOutBufferSize
0x18005ff47  mov     [rsp+2D0h+lpOutBuffer], rcx; lpOutBuffer
0x18005ff4c  lea     r9d, [rcx+18h]; nInBufferSize
0x18005ff50  lea     r8, [rbp+1D0h+InBuffer]; lpInBuffer
0x18005ff54  mov     edx, 7C058h; dwIoControlCode
0x18005ff59  mov     rcx, rsi; hDevice
0x18005ff5c  call    cs:__imp_DeviceIoControl
0x18005ff63  nop     dword ptr [rax+rax+00h]
0x18005ff68  test    eax, eax
0x18005ff6a  jz      loc_18006030E
0x18005ff70  xor     edx, edx; Val
0x18005ff72  mov     r8d, 150h; Size
0x18005ff78  lea     rcx, [rbp+1D0h+OutBuffer]; void *
0x18005ff7c  call    memset_0
0x18005ff81  mov     r14, [rbp+1D8h]
0x18005ff88  mov     [rsp+2D0h+lpOverlapped], 0; lpOverlapped
0x18005ff91  lea     rax, [rbp+1D0h+BytesReturned]
0x18005ff95  mov     [rsp+2D0h+lpBytesReturned], rax; lpBytesReturned
0x18005ff9a  mov     [rsp+2D0h+nOutBufferSize], 150h; nOutBufferSize
0x18005ffa2  lea     rax, [rbp+1D0h+OutBuffer]
0x18005ffa6  mov     [rsp+2D0h+lpOutBuffer], rax; lpOutBuffer
0x18005ffab  xor     r9d, r9d; nInBufferSize
0x18005ffae  xor     r8d, r8d; lpInBuffer
0x18005ffb1  mov     edx, 70050h; dwIoControlCode
0x18005ffb6  mov     rcx, rsi; hDevice
0x18005ffb9  call    cs:__imp_DeviceIoControl
0x18005ffc0  nop     dword ptr [rax+rax+00h]
0x18005ffc5  test    eax, eax
0x18005ffc7  jz      loc_180060323
0x18005ffcd  xorps   xmm0, xmm0
0x18005ffd0  movups  [rbp+1D0h+var_200], xmm0
0x18005ffd4  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18005ffdc  movdqa  [rbp+1D0h+var_1F0], xmm1
0x18005ffe1  xor     eax, eax
0x18005ffe3  mov     word ptr [rbp+1D0h+var_200], ax
0x18005ffe7  movups  [rbp+1D0h+var_1D0], xmm0
0x18005ffeb  movups  xmm0, [rbp+1D0h+var_198]
0x18005ffef  movdqu  [rbp+1D0h+var_1E0], xmm0
0x18005fff4  lea     r8d, [rax+10h]; Size
0x18005fff8  mov     rdx, r15; Buf2
0x18005fffb  lea     rcx, _GUID_00000000_0000_0000_0000_000000000000; Buf1
0x180060002  call    memcmp_0
0x180060007  test    eax, eax
0x180060009  jnz     short loc_180060028
0x18006000b  xorps   xmm0, xmm0
0x18006000e  movups  xmmword ptr [rbp+1D0h+Uuid.Data1], xmm0
0x180060012  lea     rcx, [rbp+1D0h+Uuid]; Uuid
0x180060016  call    cs:__imp_UuidCreate
0x18006001d  nop     dword ptr [rax+rax+00h]
0x180060022  movups  xmm1, xmmword ptr [rbp+1D0h+Uuid.Data1]
0x180060026  jmp     short loc_18006002C
0x180060028  movups  xmm1, xmmword ptr [r15]
0x18006002c  movaps  [rbp+1D0h+var_1D0], xmm1
0x180060030  mov     [rbp+1D0h+var_19C], 2
0x180060037  mov     edx, 1
0x18006003c  mov     [rbp+1D0h+var_170], edx
0x18006003f  mov     [rbp+1D0h+var_168], 100000h
0x180060047  mov     [rbp+1D0h+var_160], 8000000h
0x18006004f  xor     r15d, r15d
0x180060052  mov     [rbp+1D0h+var_158], r15d
0x180060056  mov     [rbp+1D0h+var_154], dl
0x180060059  movups  xmm0, xmmword ptr cs:PARTITION_MSFT_RESERVED_GUID.Data1
0x180060060  movdqu  [rbp+1D0h+var_150], xmm0
0x180060068  mov     [rbp+1D0h+var_E0], edx
0x18006006e  mov     [rbp+1D0h+var_D8], 8100000h
0x180060079  mov     rcx, [rbp+1D0h+var_180]
0x18006007d  mov     rax, [rbp+1D0h+var_188]
0x180060081  add     rax, 0FFFFFFFFF7F00000h
0x180060087  add     rcx, rax
0x18006008a  mov     [rbp+1D0h+var_D0], rcx
0x180060091  mov     [rbp+1D0h+var_C8], edx
0x180060097  mov     [rbp+1D0h+var_C4], dl
0x18006009d  movups  xmm0, xmmword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x1800600a4  movdqu  [rbp+1D0h+var_C0], xmm0
0x1800600ac  movdqu  [rbp+1D0h+var_B0], xmm1
0x1800600b4  mov     rax, 8000000000000000h
0x1800600be  mov     [rbp+1D0h+var_A0], rax
0x1800600c5  mov     r14, [rbp+1D8h]
0x1800600cc  mov     [rsp+2D0h+lpOverlapped], r15; lpOverlapped
0x1800600d1  lea     rax, [rbp+1D0h+BytesReturned]
0x1800600d5  mov     [rsp+2D0h+lpBytesReturned], rax; lpBytesReturned
0x1800600da  mov     [rsp+2D0h+nOutBufferSize], r15d; nOutBufferSize
0x1800600df  mov     [rsp+2D0h+lpOutBuffer], r15; lpOutBuffer
0x1800600e4  mov     r9d, 150h; nInBufferSize
0x1800600ea  lea     r8, [rbp+1D0h+OutBuffer]; lpInBuffer
0x1800600ee  mov     edx, 7C054h; dwIoControlCode
0x1800600f3  mov     rcx, rsi; hDevice
0x1800600f6  call    cs:__imp_DeviceIoControl
0x1800600fd  nop     dword ptr [rax+rax+00h]
0x180060102  test    eax, eax
0x180060104  jz      loc_1800602B1
0x18006010a  mov     rdx, rsi
0x18006010d  lea     rcx, [rbp+1D0h+Uuid]
0x180060111  call    ?GetDiskVolumePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetDiskVolumePath(void *)
0x180060116  mov     rdx, rax
0x180060119  lea     rcx, [rbp+1D0h+var_200]
0x18006011d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180060122  lea     rcx, [rbp+1D0h+Uuid]
0x180060126  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006012b  mov     esi, r15d
0x18006012e  mov     ecx, cs:_tls_index
0x180060134  mov     rax, gs:58h
0x18006013d  mov     r15, [rax+rcx*8]
0x180060141  mov     [rbp+1D0h+Uuid.Data1], 8000FFFFh
0x180060148  mov     [rbp+1D0h+var_220], 0
0x18006014f  lea     rcx, [rbp+1D0h+Uuid.Data4]; SRWLock
0x180060153  call    cs:__imp_InitializeSRWLock
0x18006015a  nop     dword ptr [rax+rax+00h]
0x18006015f  lea     rcx, [rbp+1D0h+ConditionVariable]; ConditionVariable
0x180060163  call    cs:__imp_InitializeConditionVariable
0x18006016a  nop     dword ptr [rax+rax+00h]
0x18006016f  mov     [rbp+1D0h+var_210], 1
0x180060177  lea     rax, [rbp+1D0h+Uuid]
0x18006017b  mov     ecx, 1B50h
0x180060180  mov     [r15+rcx], rax
0x180060184  xorps   xmm0, xmm0
0x180060187  xor     eax, eax
0x180060189  movups  [rsp+2D0h+var_280], xmm0
0x18006018e  movups  [rsp+2D0h+var_270], xmm0
0x180060193  movups  [rsp+2D0h+var_260], xmm0
0x180060198  mov     [rbp+1D0h+var_250], rax
0x18006019c  mov     byte ptr [rsp+2D0h+var_280], 2
0x1800601a1  lea     rax, qword_18008E1B0
0x1800601a8  mov     qword ptr [rsp+2D0h+var_280+8], rax
0x1800601ad  mov     dword ptr [rsp+2D0h+var_280+4], 2045h
0x1800601b5  lea     rcx, [rbp+1D0h+var_200]
0x1800601b9  cmp     qword ptr [rbp+1D0h+var_1F0+8], 7
0x1800601be  cmova   rcx, qword ptr [rbp+1D0h+var_200]
0x1800601c3  lea     rax, _lambda_84911dc0c7d45ac9e8b2066b124b16a3____lambda_invoker_cdecl_
0x1800601ca  mov     [rsp+2D0h+lpOutBuffer], rax; int
0x1800601cf  lea     r9, [rsp+2D0h+var_280]
0x1800601d4  mov     r8, r13
0x1800601d7  mov     edx, 0Ch
0x1800601dc  mov     rax, r12
0x1800601df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800601e4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800601e7  lea     rcx, [rbp+1D0h+Uuid.Data4]; SRWLock
0x1800601eb  call    ?Wait@VmSlimEvent@Vml@@QEAAHK@Z; Vml::VmSlimEvent::Wait(ulong)
0x1800601f0  mov     r14d, [rbp+1D0h+Uuid.Data1]
0x1800601f4  mov     eax, 1B50h
0x1800601f9  mov     qword ptr [r15+rax], 0
0x180060201  test    r14d, r14d
0x180060204  jns     short loc_180060227
0x180060206  mov     ecx, 3E8h; dwMilliseconds
0x18006020b  call    cs:__imp_Sleep
0x180060212  nop     dword ptr [rax+rax+00h]
0x180060217  inc     esi
0x180060219  cmp     esi, 3
0x18006021c  jge     loc_1800602C6
0x180060222  jmp     loc_180060141
0x180060227  xorps   xmm0, xmm0
0x18006022a  movups  xmmword ptr [rdi], xmm0
0x18006022d  mov     rax, qword ptr [rbp+1D0h+var_200]
0x180060231  mov     [rdi], rax
0x180060234  mov     rax, qword ptr [rbp+1D0h+var_200+8]
0x180060238  mov     [rdi+8], rax
0x18006023c  mov     rax, qword ptr [rbp+1D0h+var_1F0]
0x180060240  mov     [rdi+10h], rax
0x180060244  mov     rax, qword ptr [rbp+1D0h+var_1F0+8]
0x180060248  mov     [rdi+18h], rax
0x18006024c  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180060254  movdqa  [rbp+1D0h+var_1F0], xmm0
0x180060259  xor     ecx, ecx
0x18006025b  mov     word ptr [rbp+1D0h+var_200], cx
0x18006025f  movaps  xmm0, [rbp+1D0h+var_1E0]
0x180060263  movdqu  xmmword ptr [rdi+20h], xmm0
0x180060268  movaps  xmm1, [rbp+1D0h+var_1D0]
0x18006026c  movdqu  xmmword ptr [rdi+30h], xmm1
0x180060271  lea     rcx, [rbp+1D0h+var_200]
0x180060275  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006027a  nop
0x18006027b  mov     rcx, rbx; hLibModule
0x18006027e  call    cs:__imp_FreeLibrary
0x180060285  nop     dword ptr [rax+rax+00h]
0x18006028a  mov     rax, rdi
0x18006028d  mov     rcx, [rbp+1D0h+var_50]
0x180060294  xor     rcx, rsp; StackCookie
0x180060297  call    __security_check_cookie
0x18006029c  add     rsp, 298h
0x1800602a3  pop     r15
0x1800602a5  pop     r14
0x1800602a7  pop     r13
0x1800602a9  pop     r12
0x1800602ab  pop     rdi
0x1800602ac  pop     rsi
0x1800602ad  pop     rbx
0x1800602ae  pop     rbp
0x1800602af  retn
0x1800602b1  lea     r8, aOnecoreVmCompu_15; "onecore\\vm\\compute\\shared\\storage\\"...
0x1800602b8  mov     edx, 228h; void *
0x1800602bd  mov     rcx, r14; this
0x1800602c0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800602c6  mov     ecx, r14d
0x1800602c9  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800602ce  mov     r9d, eax; char *
0x1800602d1  mov     rcx, [rbp+1D8h]; this
0x1800602d8  lea     r8, aOnecoreVmCompu_15; "onecore\\vm\\compute\\shared\\storage\\"...
0x1800602df  mov     edx, 283h; void *
0x1800602e4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800602ea  lea     r8, aOnecoreVmCompu_15; "onecore\\vm\\compute\\shared\\storage\\"...
0x1800602f1  mov     edx, 1DEh; void *
0x1800602f6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800602fc  lea     r8, aOnecoreVmCompu_15; "onecore\\vm\\compute\\shared\\storage\\"...
0x180060303  mov     edx, 1E1h; void *
0x180060308  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18006030e  lea     r8, aOnecoreVmCompu_15; "onecore\\vm\\compute\\shared\\storage\\"...
0x180060315  mov     edx, 1EFh; void *
0x18006031a  mov     rcx, r14; this
0x18006031d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180060323  lea     r8, aOnecoreVmCompu_15; "onecore\\vm\\compute\\shared\\storage\\"...
0x18006032a  mov     edx, 1FEh; void *
0x18006032f  mov     rcx, r14; this
0x180060332  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

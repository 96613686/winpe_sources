# Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(void)

- ea: `0x1800198f0`
- end: `0x180019d08`
- name: `?Initialize@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@AEAAXXZ`
- size: `1048`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180016698`
- `0x18001a9f8`
- `0x180020b40`

## callees

- `0x180002188`
- `0x1800085b8`
- `0x1800085e0`
- `0x180012cbc`
- `0x1800157d4`
- `0x180017f68`
- `0x1800180a4`
- `0x1800198f0`
- `0x1800319f0`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x180019958`
- `KERNEL32!GetSystemDirectoryW` at `0x180019958`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180019a0e`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180019a0e`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180019b25`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180019b25`
- `KERNEL32!QueryDosDeviceW` at `0x180019bc9`
- `KERNEL32!QueryDosDeviceW` at `0x180019bc9`
- `KERNEL32!FindFirstVolumeW` at `0x180019adc`
- `KERNEL32!FindFirstVolumeW` at `0x180019adc`
- `KERNEL32!FindVolumeClose` at `0x180019c21`
- `KERNEL32!FindVolumeClose` at `0x180019c21`
- `KERNEL32!FindNextVolumeW` at `0x180019c0a`
- `KERNEL32!FindNextVolumeW` at `0x180019c0a`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(
        Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *this)
{
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *v2; // rsi
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *i; // rdi
  __int64 v4; // r8
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rcx
  __int64 v7; // r8
  const unsigned __int16 *v8; // rdi
  HANDLE FirstVolumeW; // r14
  int v10; // edi
  __int64 v11; // rax
  unsigned __int64 v12; // rcx
  WCHAR *v13; // rcx
  bool v14; // r8
  DWORD cchReturnLength; // [rsp+20h] [rbp-C98h] BYREF
  HANDLE v16; // [rsp+28h] [rbp-C90h]
  __int64 v17; // [rsp+30h] [rbp-C88h]
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C78h] BYREF
  WCHAR szVolumeName[4]; // [rsp+250h] [rbp-A68h] BYREF
  char v21; // [rsp+258h] [rbp-A60h] BYREF
  __int16 v22; // [rsp+456h] [rbp-862h]
  WCHAR szVolumePathNames[1040]; // [rsp+460h] [rbp-858h] BYREF

  v17 = -2;
  v2 = (Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)*((_QWORD *)this + 1);
  for ( i = *(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping **)this;
        i != v2;
        i = (Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)((char *)i + 64) )
  {
    Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping(i);
  }
  *((_QWORD *)this + 1) = *(_QWORD *)this;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    ATL::AtlThrowLastWin32();
  if ( Buffer[0] )
  {
    v4 = -1;
    do
      ++v4;
    while ( Buffer[v4] );
  }
  std::wstring::assign((char *)this + 48, Buffer);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\??\\\\", &Src, 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\??\\", &Src, 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    this,
    L"\\DriverStores\\BSPDRIVERS",
    L"\\\\?\\GLOBALROOT\\DriverStores\\BSPDRIVERS",
    1);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    this,
    L"\\DriverStore\\Nodes",
    L"\\\\?\\GLOBALROOT\\DriverStore\\Nodes",
    1);
  if ( !GetSystemWindowsDirectoryW(Buffer, 0x105u) )
    ATL::AtlThrowLastWin32();
  v5 = -1;
  do
    ++v5;
  while ( Buffer[v5] );
  if ( v5 < 2 || Buffer[1] != 58 )
    ATL::AtlThrowImpl(-2147418113);
  if ( Buffer[v5 - 1] != 92 )
  {
    if ( v5 >= 0x104 )
      ATL::AtlThrowImpl(-2147024774);
    Buffer[v5] = 92;
    v6 = 2 * v5 + 2;
    if ( v6 >= 0x20A )
      ((void (__noreturn *)(void))_report_rangecheckfailure)();
    *(WCHAR *)((char *)Buffer + v6) = 0;
  }
  if ( Buffer[0] )
  {
    v7 = -1;
    do
      ++v7;
    while ( Buffer[v7] );
  }
  v8 = (const unsigned __int16 *)((char *)this + 80);
  std::wstring::assign((char *)this + 80, Buffer);
  if ( *((_QWORD *)this + 13) >= 8u )
    v8 = *(const unsigned __int16 **)v8;
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\SystemRoot\\", v8, 1);
  FirstVolumeW = FindFirstVolumeW(szVolumeName, 0x104u);
  v16 = FirstVolumeW;
  if ( FirstVolumeW == (HANDLE)-1LL )
    ATL::AtlThrowLastWin32();
  try
  {
    cchReturnLength = 0;
    do
    {
      v22 = 0;
      v10 = 0;
      if ( GetVolumePathNamesForVolumeNameW(szVolumeName, szVolumePathNames, 0x410u, &cchReturnLength) )
        LOBYTE(v10) = szVolumePathNames[0] != 0;
      v11 = -1;
      do
        ++v11;
      while ( szVolumeName[v11] );
      if ( v11 && Buffer[v11 + 263] == 92 )
      {
        v12 = 2 * v11 - 2;
        if ( v12 >= 0x208 )
          _report_rangecheckfailure(v12);
        *(WCHAR *)((char *)szVolumeName + v12) = 0;
      }
      if ( szVolumeName[0] != 92
        || szVolumeName[1] != 92
        || szVolumeName[2] != 63
        || (v13 = (WCHAR *)&v21, szVolumeName[3] != 92) )
      {
        v13 = szVolumeName;
      }
      if ( QueryDosDeviceW(v13, Buffer, 0x104u) )
      {
        if ( v10 )
          Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, Buffer, szVolumePathNames, 1);
        else
          Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(this, Buffer, v14);
      }
    }
    while ( FindNextVolumeW(FirstVolumeW, szVolumeName, 0x104u) );
  }
  catch ( ... )
  {
    FindVolumeClose(v16);
    throw;
  }
  FindVolumeClose(FirstVolumeW);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    this,
    L"\\Device\\LanmanRedirector\\",
    L"\\\\",
    0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\Device\\Mup\\", L"\\\\", 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\Device\\vmsmb\\", L"\\\\?\\VMSMB\\", 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\GLOBAL??\\", L"\\\\?\\", 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\\\", L"\\\\", 0);
  *((_BYTE *)this + 112) = 1;
}

```

## disassembly

```asm
0x1800198f0  mov     rax, rsp
0x1800198f3  push    rdi
0x1800198f4  push    r12
0x1800198f6  push    r13
0x1800198f8  push    r14
0x1800198fa  push    r15
0x1800198fc  sub     rsp, 0C90h
0x180019903  mov     [rsp+0CB8h+var_C88], 0FFFFFFFFFFFFFFFEh
0x18001990c  mov     [rax+10h], rbx
0x180019910  mov     [rax+18h], rsi
0x180019914  mov     rax, cs:__security_cookie
0x18001991b  xor     rax, rsp
0x18001991e  mov     [rsp+0CB8h+var_38], rax
0x180019926  mov     rbx, rcx
0x180019929  mov     rsi, [rcx+8]
0x18001992d  mov     rdi, [rcx]
0x180019930  jmp     short loc_18001993E
0x180019932  mov     rcx, rdi; this
0x180019935  call    ??1CMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping(void)
0x18001993a  add     rdi, 40h ; '@'
0x18001993e  cmp     rdi, rsi
0x180019941  jnz     short loc_180019932
0x180019943  mov     rax, [rbx]
0x180019946  mov     [rbx+8], rax
0x18001994a  mov     r13d, 104h
0x180019950  mov     edx, r13d; uSize
0x180019953  lea     rcx, [rsp+0CB8h+Buffer]; lpBuffer
0x180019958  call    cs:__imp_GetSystemDirectoryW
0x18001995f  nop     dword ptr [rax+rax+00h]
0x180019964  xor     r15d, r15d
0x180019967  test    eax, eax
0x180019969  jz      loc_180019CDE
0x18001996f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180019973  cmp     [rsp+0CB8h+Buffer], r15w
0x180019979  jnz     short loc_180019980
0x18001997b  mov     r8, r15
0x18001997e  jmp     short loc_180019992
0x180019980  lea     rax, [rsp+0CB8h+Buffer]
0x180019985  mov     r8, rsi
0x180019988  inc     r8
0x18001998b  cmp     [rax+r8*2], r15w
0x180019990  jnz     short loc_180019988
0x180019992  lea     rcx, [rbx+30h]; void *
0x180019996  lea     rdx, [rsp+0CB8h+Buffer]; Src
0x18001999b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800199a0  xor     r9d, r9d; bool
0x1800199a3  lea     r8, Src; unsigned __int16 *
0x1800199aa  lea     rdx, asc_18003B0F8; "\\??\\\\"
0x1800199b1  mov     rcx, rbx; this
0x1800199b4  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800199b9  xor     r9d, r9d; bool
0x1800199bc  lea     r8, Src; unsigned __int16 *
0x1800199c3  lea     rdx, asc_18003A2C8; "\\??\\"
0x1800199ca  mov     rcx, rbx; this
0x1800199cd  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800199d2  mov     r9b, 1; bool
0x1800199d5  lea     r8, aGlobalrootDriv_1; "\\\\?\\GLOBALROOT\\DriverStores\\BSPDRI"...
0x1800199dc  lea     rdx, aDriverstoresBs; "\\DriverStores\\BSPDRIVERS"
0x1800199e3  mov     rcx, rbx; this
0x1800199e6  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800199eb  mov     r9b, 1; bool
0x1800199ee  lea     r8, aGlobalrootDriv_0; "\\\\?\\GLOBALROOT\\DriverStore\\Nodes"
0x1800199f5  lea     rdx, aDriverstoreNod; "\\DriverStore\\Nodes"
0x1800199fc  mov     rcx, rbx; this
0x1800199ff  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180019a04  mov     edx, 105h; uSize
0x180019a09  lea     rcx, [rsp+0CB8h+Buffer]; lpBuffer
0x180019a0e  call    cs:__imp_GetSystemWindowsDirectoryW
0x180019a15  nop     dword ptr [rax+rax+00h]
0x180019a1a  test    eax, eax
0x180019a1c  jz      loc_180019CE4
0x180019a22  lea     rcx, [rsp+0CB8h+Buffer]
0x180019a27  mov     rax, rsi
0x180019a2a  inc     rax
0x180019a2d  cmp     [rcx+rax*2], r15w
0x180019a32  jnz     short loc_180019A2A
0x180019a34  cmp     rax, 2
0x180019a38  jb      loc_180019CD3
0x180019a3e  cmp     [rsp+0CB8h+var_C76], 3Ah ; ':'
0x180019a44  jnz     loc_180019CD3
0x180019a4a  mov     r12d, 5Ch ; '\'
0x180019a50  cmp     [rsp+rax*2+0CB8h+var_C7A], r12w
0x180019a56  jz      short loc_180019A82
0x180019a58  cmp     rax, r13
0x180019a5b  jnb     loc_180019CF0
0x180019a61  mov     [rsp+rax*2+0CB8h+Buffer], r12w
0x180019a67  lea     rcx, ds:2[rax*2]
0x180019a6f  cmp     rcx, 20Ah
0x180019a76  jnb     loc_180019CEA
0x180019a7c  mov     [rsp+rcx+0CB8h+Buffer], r15w
0x180019a82  cmp     [rsp+0CB8h+Buffer], r15w
0x180019a88  jnz     short loc_180019A8F
0x180019a8a  mov     r8, r15
0x180019a8d  jmp     short loc_180019AA1
0x180019a8f  lea     rax, [rsp+0CB8h+Buffer]
0x180019a94  mov     r8, rsi
0x180019a97  inc     r8
0x180019a9a  cmp     [rax+r8*2], r15w
0x180019a9f  jnz     short loc_180019A97
0x180019aa1  lea     rdi, [rbx+50h]
0x180019aa5  lea     rdx, [rsp+0CB8h+Buffer]; Src
0x180019aaa  mov     rcx, rdi; void *
0x180019aad  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180019ab2  cmp     qword ptr [rdi+18h], 8
0x180019ab7  jb      short loc_180019ABC
0x180019ab9  mov     rdi, [rdi]
0x180019abc  mov     r9b, 1; bool
0x180019abf  mov     r8, rdi; unsigned __int16 *
0x180019ac2  lea     rdx, aSystemroot; "\\SystemRoot\\"
0x180019ac9  mov     rcx, rbx; this
0x180019acc  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180019ad1  mov     edx, r13d; cchBufferLength
0x180019ad4  lea     rcx, [rsp+0CB8h+szVolumeName]; lpszVolumeName
0x180019adc  call    cs:__imp_FindFirstVolumeW
0x180019ae3  nop     dword ptr [rax+rax+00h]
0x180019ae8  mov     r14, rax
0x180019aeb  mov     [rsp+0CB8h+var_C90], rax
0x180019af0  cmp     rax, rsi
0x180019af3  jz      loc_180019CFB
0x180019af9  mov     [rsp+0CB8h+cchReturnLength], r15d
0x180019afe  mov     [rsp+0CB8h+var_862], r15w
0x180019b07  mov     edi, r15d
0x180019b0a  lea     r9, [rsp+0CB8h+cchReturnLength]; lpcchReturnLength
0x180019b0f  mov     r8d, 410h; cchBufferLength
0x180019b15  lea     rdx, [rsp+0CB8h+szVolumePathNames]; lpszVolumePathNames
0x180019b1d  lea     rcx, [rsp+0CB8h+szVolumeName]; lpszVolumeName
0x180019b25  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180019b2c  nop     dword ptr [rax+rax+00h]
0x180019b31  test    eax, eax
0x180019b33  jz      short loc_180019B42
0x180019b35  cmp     [rsp+0CB8h+szVolumePathNames], r15w
0x180019b3e  setnz   dil
0x180019b42  lea     rcx, [rsp+0CB8h+szVolumeName]
0x180019b4a  mov     rax, rsi
0x180019b4d  inc     rax
0x180019b50  cmp     [rcx+rax*2], r15w
0x180019b55  jnz     short loc_180019B4D
0x180019b57  test    rax, rax
0x180019b5a  jz      short loc_180019B85
0x180019b5c  cmp     [rsp+rax*2+0CB8h+var_A6A], r12w
0x180019b65  jnz     short loc_180019B85
0x180019b67  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180019b6f  cmp     rcx, 208h
0x180019b76  jnb     loc_180019D01
0x180019b7c  mov     [rsp+rcx+0CB8h+szVolumeName], r15w
0x180019b85  cmp     [rsp+0CB8h+szVolumeName], r12w
0x180019b8e  jnz     short loc_180019BB9
0x180019b90  cmp     [rsp+0CB8h+var_A66], r12w
0x180019b99  jnz     short loc_180019BB9
0x180019b9b  cmp     [rsp+0CB8h+var_A64], 3Fh ; '?'
0x180019ba4  jnz     short loc_180019BB9
0x180019ba6  cmp     [rsp+0CB8h+var_A62], r12w
0x180019baf  lea     rcx, [rsp+0CB8h+var_A60]
0x180019bb7  jz      short loc_180019BC1
0x180019bb9  lea     rcx, [rsp+0CB8h+szVolumeName]; lpDeviceName
0x180019bc1  mov     r8d, r13d; ucchMax
0x180019bc4  lea     rdx, [rsp+0CB8h+Buffer]; lpTargetPath
0x180019bc9  call    cs:__imp_QueryDosDeviceW
0x180019bd0  nop     dword ptr [rax+rax+00h]
0x180019bd5  test    eax, eax
0x180019bd7  jz      short loc_180019BFC
0x180019bd9  lea     rdx, [rsp+0CB8h+Buffer]; unsigned __int16 *
0x180019bde  mov     rcx, rbx; this
0x180019be1  test    edi, edi
0x180019be3  jz      short loc_180019BF7
0x180019be5  mov     r9b, 1; bool
0x180019be8  lea     r8, [rsp+0CB8h+szVolumePathNames]; unsigned __int16 *
0x180019bf0  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180019bf5  jmp     short loc_180019BFC
0x180019bf7  call    ?AddSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(ushort const *,bool)
0x180019bfc  mov     r8d, r13d; cchBufferLength
0x180019bff  lea     rdx, [rsp+0CB8h+szVolumeName]; lpszVolumeName
0x180019c07  mov     rcx, r14; hFindVolume
0x180019c0a  call    cs:__imp_FindNextVolumeW
0x180019c11  nop     dword ptr [rax+rax+00h]
0x180019c16  test    eax, eax
0x180019c18  jnz     loc_180019AFE
0x180019c1e  mov     rcx, r14; hFindVolume
0x180019c21  call    cs:__imp_FindVolumeClose
0x180019c28  nop     dword ptr [rax+rax+00h]
0x180019c2d  xor     r9d, r9d; bool
0x180019c30  lea     rdi, String2; "\\\\"
0x180019c37  mov     r8, rdi; unsigned __int16 *
0x180019c3a  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector\\"
0x180019c41  mov     rcx, rbx; this
0x180019c44  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180019c49  xor     r9d, r9d; bool
0x180019c4c  mov     r8, rdi; unsigned __int16 *
0x180019c4f  lea     rdx, aDeviceMup; "\\Device\\Mup\\"
0x180019c56  mov     rcx, rbx; this
0x180019c59  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180019c5e  xor     r9d, r9d; bool
0x180019c61  lea     r8, aVmsmb; "\\\\?\\VMSMB\\"
0x180019c68  lea     rdx, aDeviceVmsmb; "\\Device\\vmsmb\\"
0x180019c6f  mov     rcx, rbx; this
0x180019c72  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180019c77  xor     r9d, r9d; bool
0x180019c7a  lea     r8, asc_18003A2D8; "\\\\?\\"
0x180019c81  lea     rdx, aGlobal; "\\GLOBAL??\\"
0x180019c88  mov     rcx, rbx; this
0x180019c8b  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180019c90  xor     r9d, r9d; bool
0x180019c93  mov     r8, rdi; unsigned __int16 *
0x180019c96  mov     rdx, rdi; unsigned __int16 *
0x180019c99  mov     rcx, rbx; this
0x180019c9c  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180019ca1  mov     byte ptr [rbx+70h], 1
0x180019ca5  mov     rcx, [rsp+0CB8h+var_38]
0x180019cad  xor     rcx, rsp; StackCookie
0x180019cb0  call    __security_check_cookie
0x180019cb5  lea     r11, [rsp+0CB8h+var_28]
0x180019cbd  mov     rbx, [r11+38h]
0x180019cc1  mov     rsi, [r11+40h]
0x180019cc5  mov     rsp, r11
0x180019cc8  pop     r15
0x180019cca  pop     r14
0x180019ccc  pop     r13
0x180019cce  pop     r12
0x180019cd0  pop     rdi
0x180019cd1  retn
0x180019cd3  mov     ecx, 8000FFFFh; int
0x180019cd8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180019cde  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180019ce4  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180019cea  call    __report_rangecheckfailure
0x180019cf0  mov     ecx, 8007007Ah; int
0x180019cf5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180019cfb  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180019d01  call    __report_rangecheckfailure
```

# CImpPerf::EliminateRanges(void)

- ea: `0x18000fe68`
- end: `0x1800101cd`
- name: `?EliminateRanges@CImpPerf@@QEAAXXZ`
- size: `869`
- prototype: `void __fastcall(CImpPerf *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010ae0`

## callees

- `0x180002e10`
- `0x1800086b0`
- `0x18000bb8c`
- `0x18000f904`
- `0x18000fa80`
- `0x18000fe68`
- `0x1800119a8`

## import_xrefs

- `msvcrt!_wtoi` at `0x18000fe9d`
- `msvcrt!_wtoi` at `0x18000fe9d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000ffaf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000ffaf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ff08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010043`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ff08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010043`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010129`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800101a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010129`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800101a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001009d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800100d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001009d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800100d8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ff23`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ff48`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ffe3`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001015f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ff23`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ff48`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ffe3`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001015f`

## string_xrefs

- `0x18000fefa`: `SYSTEM\CurrentControlSet\Services`

## pseudocode

```c
void __fastcall CImpPerf::EliminateRanges(CImpPerf *this)
{
  __int64 v2; // rcx
  unsigned int v3; // eax
  __int64 i; // r8
  unsigned int v5; // ecx
  __int64 v6; // r9
  __int64 v7; // rcx
  HKEY v8; // rbx
  void *v9; // rax
  WCHAR *v10; // rdi
  void *v11; // rax
  unsigned __int16 *v12; // rsi
  DWORD v13; // r13d
  unsigned int v14; // r14d
  DWORD v15; // r12d
  LSTATUS v16; // eax
  void *v17; // rax
  HKEY v18; // r14
  unsigned int v19; // edx
  unsigned int v20; // eax
  unsigned int v21; // ecx
  __int64 v22; // r9
  __int64 v23; // rdx
  void *v24; // rax
  DWORD Type; // [rsp+40h] [rbp-39h] BYREF
  LPWSTR lpName; // [rsp+48h] [rbp-31h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-29h] BYREF
  BYTE v28[4]; // [rsp+54h] [rbp-25h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-21h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-11h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-9h] BYREF
  CImpPerf *v33; // [rsp+78h] [rbp-1h] BYREF
  char v34; // [rsp+80h] [rbp+7h]
  DWORD cchName; // [rsp+88h] [rbp+Fh] BYREF
  HKEY v36; // [rsp+90h] [rbp+17h]
  int v37; // [rsp+E0h] [rbp+67h]

  v2 = *(_QWORD *)(*((_QWORD *)this + 73) + 8LL);
  v3 = 0;
  if ( v2 )
    v3 = _wtoi((const wchar_t *)(v2 & 0xFFFFFFFFFFFFFFFEuLL)) + 1;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v5 = v3;
    if ( v3 >= *((_DWORD *)this + 144) )
      v5 = *((_DWORD *)this + 144);
    if ( (unsigned int)i >= v5 )
      break;
    v6 = *((_QWORD *)this + 73);
    v7 = *(_QWORD *)(v6 + 8 * i);
    if ( v7 )
      *(_QWORD *)(v6 + 8 * i) = v7 & 0xFFFFFFFFFFFFFFFEuLL;
  }
  v33 = this;
  v34 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services", 0, 8u, &hKey) )
  {
    v8 = hKey;
    v9 = CWin32DefaultArena::WbemMemAlloc(0x200u);
    std::unique_ptr<unsigned short [0]>::unique_ptr<unsigned short [0]>(&lpName, (__int64)v9);
    v10 = lpName;
    if ( lpName )
    {
      v11 = CWin32DefaultArena::WbemMemAlloc(0x21Au);
      std::unique_ptr<unsigned short [0]>::unique_ptr<unsigned short [0]>(&lpSubKey, (__int64)v11);
      v12 = (unsigned __int16 *)lpSubKey;
      if ( lpSubKey )
      {
        v13 = 256;
        v14 = 269;
        v37 = 269;
        v15 = 0;
        while ( 1 )
        {
          while ( 1 )
          {
            cchName = v13;
            v16 = RegEnumKeyExW(hKey, v15, v10, &cchName, 0, 0, 0, 0);
            if ( v16 )
              break;
            if ( v13 > v14 )
            {
              v14 = v13 + 13;
              v37 = v13 + 13;
              v17 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v13 + 13, 2u));
              std::unique_ptr<unsigned short [0]>::reset(&lpSubKey, v17);
              v12 = (unsigned __int16 *)lpSubKey;
              if ( !lpSubKey )
                goto LABEL_36;
            }
            StringCchCopyW(v12, v14, v10);
            StringCchCatW(v12, v14, L"\\Performance");
            phkResult = 0;
            if ( RegOpenKeyExW(hKey, v12, 0, 0x20019u, &phkResult) )
            {
              ++v15;
            }
            else
            {
              v18 = phkResult;
              v36 = phkResult;
              *(_DWORD *)Data = 0;
              *(_DWORD *)v28 = 0;
              cbData = 4;
              Type = 0;
              if ( !RegQueryValueExW(phkResult, L"First Counter", 0, &Type, Data, &cbData) && Type == 4 )
              {
                cbData = 4;
                if ( !RegQueryValueExW(phkResult, L"Last Counter", 0, &Type, v28, &cbData) && Type == 4 )
                {
                  v19 = *((_DWORD *)this + 144);
                  v20 = *(_DWORD *)Data;
                  if ( *(_DWORD *)Data <= v19 )
                  {
                    v21 = *(_DWORD *)v28;
                    if ( *(_DWORD *)v28 <= v19 )
                    {
                      while ( v20 <= v21 )
                      {
                        v22 = *((_QWORD *)this + 73);
                        v23 = *(_QWORD *)(v22 + 8LL * v20);
                        if ( v23 )
                        {
                          *(_QWORD *)(v22 + 8LL * v20) = v23 & 0xFFFFFFFFFFFFFFFEuLL;
                          v21 = *(_DWORD *)v28;
                        }
                        ++v20;
                      }
                    }
                  }
                }
              }
              ++v15;
              RegCloseKey(v18);
              v14 = v37;
            }
          }
          if ( v16 != 234 )
            break;
          v13 += 256;
          v24 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v13, 2u));
          std::unique_ptr<unsigned short [0]>::reset(&lpName, v24);
          v10 = lpName;
          if ( !lpName )
            goto LABEL_36;
        }
        if ( v16 == 259 )
          v34 = 1;
      }
LABEL_36:
      CDeleteMe<unsigned short>::~CDeleteMe<unsigned short>((void **)&lpSubKey);
    }
    CDeleteMe<unsigned short>::~CDeleteMe<unsigned short>((void **)&lpName);
    RegCloseKey(v8);
  }
  OnDeleteObjIf0<CImpPerf,void (CImpPerf::*)(void),{public: void CImpPerf::MakeAllValid(void),0}>::~OnDeleteObjIf0<CImpPerf,void (CImpPerf::*)(void),{public: void CImpPerf::MakeAllValid(void),0}>((__int64)&v33);
}

```

## disassembly

```asm
0x18000fe68  mov     [rsp-8+arg_10], rbx
0x18000fe6d  push    rbp
0x18000fe6e  push    rsi
0x18000fe6f  push    rdi
0x18000fe70  push    r12
0x18000fe72  push    r13
0x18000fe74  push    r14
0x18000fe76  push    r15
0x18000fe78  lea     rbp, [rsp-27h]
0x18000fe7d  sub     rsp, 0A0h
0x18000fe84  mov     r15, rcx
0x18000fe87  mov     rax, [rcx+248h]
0x18000fe8e  mov     rcx, [rax+8]
0x18000fe92  xor     eax, eax
0x18000fe94  test    rcx, rcx
0x18000fe97  jz      short loc_18000FEA5
0x18000fe99  and     rcx, 0FFFFFFFFFFFFFFFEh; String
0x18000fe9d  call    cs:__imp__wtoi
0x18000fea3  inc     eax
0x18000fea5  xor     r8d, r8d
0x18000fea8  mov     edx, [r15+240h]
0x18000feaf  mov     ecx, eax
0x18000feb1  cmp     eax, edx
0x18000feb3  cmovnb  ecx, edx
0x18000feb6  cmp     r8d, ecx
0x18000feb9  jnb     short loc_18000FED8
0x18000febb  mov     r9, [r15+248h]
0x18000fec2  mov     rcx, [r9+r8*8]
0x18000fec6  test    rcx, rcx
0x18000fec9  jz      short loc_18000FED3
0x18000fecb  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000fecf  mov     [r9+r8*8], rcx
0x18000fed3  inc     r8d
0x18000fed6  jmp     short loc_18000FEA8
0x18000fed8  mov     [rbp+57h+var_58], r15
0x18000fedc  mov     [rbp+57h+var_50], 0
0x18000fee0  mov     [rbp+57h+hKey], 0
0x18000fee8  lea     rax, [rbp+57h+hKey]
0x18000feec  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18000fef1  mov     r9d, 8; samDesired
0x18000fef7  xor     r8d, r8d; ulOptions
0x18000fefa  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services"
0x18000ff01  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ff08  call    cs:__imp_RegOpenKeyExW
0x18000ff0e  test    eax, eax
0x18000ff10  jnz     loc_1800101A9
0x18000ff16  mov     rbx, [rbp+57h+hKey]
0x18000ff1a  mov     [rbp+57h+arg_8], rbx
0x18000ff1e  mov     ecx, 200h
0x18000ff23  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000ff29  mov     rdx, rax
0x18000ff2c  lea     rcx, [rbp+57h+lpName]
0x18000ff30  call    ??0?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@PEAG@Z; std::unique_ptr<ushort [0]>::unique_ptr<ushort [0]>(ushort *)
0x18000ff35  nop
0x18000ff36  mov     rdi, [rbp+57h+lpName]
0x18000ff3a  test    rdi, rdi
0x18000ff3d  jz      loc_180010195
0x18000ff43  mov     ecx, 21Ah
0x18000ff48  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000ff4e  mov     rdx, rax
0x18000ff51  lea     rcx, [rbp+57h+lpSubKey]
0x18000ff55  call    ??0?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@PEAG@Z; std::unique_ptr<ushort [0]>::unique_ptr<ushort [0]>(ushort *)
0x18000ff5a  nop
0x18000ff5b  mov     rsi, [rbp+57h+lpSubKey]
0x18000ff5f  test    rsi, rsi
0x18000ff62  jz      loc_18001018B
0x18000ff68  mov     r13d, 100h
0x18000ff6e  lea     r14d, [r13+0Dh]
0x18000ff72  mov     [rbp+57h+arg_0], r14d
0x18000ff76  xor     r12d, r12d
0x18000ff79  mov     [rbp+57h+cchName], r13d
0x18000ff7d  mov     [rsp+0D0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18000ff86  mov     [rsp+0D0h+lpcchClass], 0; lpcchClass
0x18000ff8f  mov     [rsp+0D0h+lpClass], 0; lpClass
0x18000ff98  mov     [rsp+0D0h+phkResult], 0; lpReserved
0x18000ffa1  lea     r9, [rbp+57h+cchName]; lpcchName
0x18000ffa5  mov     r8, rdi; lpName
0x18000ffa8  mov     edx, r12d; dwIndex
0x18000ffab  mov     rcx, [rbp+57h+hKey]; hKey
0x18000ffaf  call    cs:__imp_RegEnumKeyExW
0x18000ffb5  test    eax, eax
0x18000ffb7  jnz     loc_180010138
0x18000ffbd  cmp     r13d, r14d
0x18000ffc0  jbe     short loc_180010002
0x18000ffc2  lea     r14d, [r13+0Dh]
0x18000ffc6  mov     [rbp+57h+arg_0], r14d
0x18000ffca  mov     ecx, r14d
0x18000ffcd  mov     eax, 2
0x18000ffd2  mul     rcx
0x18000ffd5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ffdc  cmovb   rax, rcx
0x18000ffe0  mov     rcx, rax
0x18000ffe3  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000ffe9  mov     rdx, rax
0x18000ffec  lea     rcx, [rbp+57h+lpSubKey]
0x18000fff0  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort [0]>::reset(ushort *)
0x18000fff5  mov     rsi, [rbp+57h+lpSubKey]
0x18000fff9  test    rsi, rsi
0x18000fffc  jz      loc_18001018B
0x180010002  mov     r8, rdi; unsigned __int16 *
0x180010005  mov     edx, r14d; unsigned __int64
0x180010008  mov     rcx, rsi; unsigned __int16 *
0x18001000b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010010  lea     r8, aPerformance; "\\Performance"
0x180010017  mov     edx, r14d; unsigned __int64
0x18001001a  mov     rcx, rsi; unsigned __int16 *
0x18001001d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010022  mov     [rbp+57h+var_60], 0
0x18001002a  lea     rax, [rbp+57h+var_60]
0x18001002e  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180010033  mov     r9d, 20019h; samDesired
0x180010039  xor     r8d, r8d; ulOptions
0x18001003c  mov     rdx, rsi; lpSubKey
0x18001003f  mov     rcx, [rbp+57h+hKey]; hKey
0x180010043  call    cs:__imp_RegOpenKeyExW
0x180010049  test    eax, eax
0x18001004b  jz      short loc_180010055
0x18001004d  inc     r12d
0x180010050  jmp     loc_18000FF79
0x180010055  mov     r14, [rbp+57h+var_60]
0x180010059  mov     [rbp+57h+var_40], r14
0x18001005d  mov     dword ptr [rbp+57h+Data], 0
0x180010064  mov     dword ptr [rbp+57h+var_7C], 0
0x18001006b  mov     [rbp+57h+cbData], 4
0x180010072  mov     [rbp+57h+Type], 0
0x180010079  lea     rax, [rbp+57h+cbData]
0x18001007d  mov     [rsp+0D0h+lpClass], rax; lpcbData
0x180010082  lea     rax, [rbp+57h+Data]
0x180010086  mov     [rsp+0D0h+phkResult], rax; lpData
0x18001008b  lea     r9, [rbp+57h+Type]; lpType
0x18001008f  xor     r8d, r8d; lpReserved
0x180010092  lea     rdx, ValueName; "First Counter"
0x180010099  mov     rcx, [rbp+57h+var_60]; hKey
0x18001009d  call    cs:__imp_RegQueryValueExW
0x1800100a3  test    eax, eax
0x1800100a5  jnz     short loc_180010123
0x1800100a7  cmp     [rbp+57h+Type], 4
0x1800100ab  jnz     short loc_180010123
0x1800100ad  mov     [rbp+57h+cbData], 4
0x1800100b4  lea     rax, [rbp+57h+cbData]
0x1800100b8  mov     [rsp+0D0h+lpClass], rax; lpcbData
0x1800100bd  lea     rax, [rbp+57h+var_7C]
0x1800100c1  mov     [rsp+0D0h+phkResult], rax; lpData
0x1800100c6  lea     r9, [rbp+57h+Type]; lpType
0x1800100ca  xor     r8d, r8d; lpReserved
0x1800100cd  lea     rdx, aLastCounter; "Last Counter"
0x1800100d4  mov     rcx, [rbp+57h+var_60]; hKey
0x1800100d8  call    cs:__imp_RegQueryValueExW
0x1800100de  test    eax, eax
0x1800100e0  jnz     short loc_180010123
0x1800100e2  cmp     [rbp+57h+Type], 4
0x1800100e6  jnz     short loc_180010123
0x1800100e8  mov     edx, [r15+240h]
0x1800100ef  mov     eax, dword ptr [rbp+57h+Data]
0x1800100f2  cmp     eax, edx
0x1800100f4  ja      short loc_180010123
0x1800100f6  mov     ecx, dword ptr [rbp+57h+var_7C]
0x1800100f9  cmp     ecx, edx
0x1800100fb  ja      short loc_180010123
0x1800100fd  jmp     short loc_18001011F
0x1800100ff  mov     r8d, eax
0x180010102  mov     r9, [r15+248h]
0x180010109  mov     rdx, [r9+r8*8]
0x18001010d  test    rdx, rdx
0x180010110  jz      short loc_18001011D
0x180010112  and     rdx, 0FFFFFFFFFFFFFFFEh
0x180010116  mov     [r9+r8*8], rdx
0x18001011a  mov     ecx, dword ptr [rbp+57h+var_7C]
0x18001011d  inc     eax
0x18001011f  cmp     eax, ecx
0x180010121  jbe     short loc_1800100FF
0x180010123  inc     r12d
0x180010126  mov     rcx, r14; hKey
0x180010129  call    cs:__imp_RegCloseKey
0x18001012f  mov     r14d, [rbp+57h+arg_0]
0x180010133  jmp     loc_18000FF79
0x180010138  cmp     eax, 0EAh
0x18001013d  jnz     short loc_180010180
0x18001013f  add     r13d, 100h
0x180010146  mov     ecx, r13d
0x180010149  mov     eax, 2
0x18001014e  mul     rcx
0x180010151  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180010158  cmovb   rax, rcx
0x18001015c  mov     rcx, rax
0x18001015f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180010165  mov     rdx, rax
0x180010168  lea     rcx, [rbp+57h+lpName]
0x18001016c  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort [0]>::reset(ushort *)
0x180010171  mov     rdi, [rbp+57h+lpName]
0x180010175  test    rdi, rdi
0x180010178  jnz     loc_18000FF79
0x18001017e  jmp     short loc_18001018B
0x180010180  cmp     eax, 103h
0x180010185  jnz     short loc_18001018B
0x180010187  mov     [rbp+57h+var_50], 1
0x18001018b  lea     rcx, [rbp+57h+lpSubKey]
0x18001018f  call    ??1?$CDeleteMe@G@@QEAA@XZ; CDeleteMe<ushort>::~CDeleteMe<ushort>(void)
0x180010194  nop
0x180010195  lea     rcx, [rbp+57h+lpName]
0x180010199  call    ??1?$CDeleteMe@G@@QEAA@XZ; CDeleteMe<ushort>::~CDeleteMe<ushort>(void)
0x18001019e  nop
0x18001019f  mov     rcx, rbx; hKey
0x1800101a2  call    cs:__imp_RegCloseKey
0x1800101a8  nop
0x1800101a9  lea     rcx, [rbp+57h+var_58]
0x1800101ad  call    ??1?$OnDeleteObjIf0@VCImpPerf@@P81@EAAXXZ$H?MakeAllValid@1@QEAAXXZA@@@QEAA@XZ; OnDeleteObjIf0<CImpPerf,void (CImpPerf::*)(void),{CImpPerf::MakeAllValid(void),0}>::~OnDeleteObjIf0<CImpPerf,void (CImpPerf::*)(void),{CImpPerf::MakeAllValid(void),0}>(void)
0x1800101b2  mov     rbx, [rsp+0D0h+arg_10]
0x1800101ba  add     rsp, 0A0h
0x1800101c1  pop     r15
0x1800101c3  pop     r14
0x1800101c5  pop     r13
0x1800101c7  pop     r12
0x1800101c9  pop     rdi
0x1800101ca  pop     rsi
0x1800101cb  pop     rbp
0x1800101cc  retn
```

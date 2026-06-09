# EnumProcessedSearchRoots(CAutoDSA<PROCESSED_SEARCH_ROOT> *,CAutoDSA<PROCESSED_SEARCH_ROOT> *)

- ea: `0x180021cd0`
- end: `0x180021f7c`
- name: `?EnumProcessedSearchRoots@@YAJPEAV?$CAutoDSA@UPROCESSED_SEARCH_ROOT@@@@0@Z`
- size: `684`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022840`
- `0x180022aa0`

## callees

- `0x180003840`
- `0x180005cc0`
- `0x18000687c`
- `0x18001a220`
- `0x1800218c4`
- `0x18002192c`
- `0x180021c80`
- `0x180021cd0`
- `0x1800227dc`
- `0x180022efc`
- `0x18002ffdc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021dbe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021dbe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021efa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021f4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021efa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021f4e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021e5e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021e5e`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180021d7f`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180021d7f`

## pseudocode

```c
__int64 __fastcall EnumProcessedSearchRoots(HDSA *a1, HDSA *a2, __int64 a3)
{
  int v5; // ebx
  DWORD v6; // ebx
  LSTATUS v7; // eax
  signed int StringValue; // edi
  LSTATUS v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r9
  int v16; // eax
  HDSA *v17; // rcx
  BOOL v18; // eax
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  __int128 p; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h]
  WCHAR Name; // [rsp+70h] [rbp-90h] BYREF
  char v26[526]; // [rsp+72h] [rbp-8Eh] BYREF
  unsigned __int16 v27; // [rsp+280h] [rbp+180h] BYREF
  char v28[526]; // [rsp+282h] [rbp+182h] BYREF

  hKey = 0;
  v5 = RegOpenKeyOpt(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\Windows Search\\ProcessedSearchRoots", a3, &hKey);
  if ( !v5 )
  {
    if ( (unsigned int)CDSA_Base<PROCESSED_SEARCH_ROOT>::Create(a1, 4)
      && (unsigned int)CDSA_Base<PROCESSED_SEARCH_ROOT>::Create(a2, 1) )
    {
      Name = 0;
      memset_0(v26, 0, 0x206u);
      v6 = 0;
      do
      {
        v7 = RegEnumKeyW(hKey, v6, &Name, 0x104u);
        StringValue = v7;
        if ( v7 > 0 )
          StringValue = (unsigned __int16)v7 | 0x80070000;
        if ( StringValue < 0 )
          break;
        hkey = 0;
        v9 = RegOpenKeyExW(hKey, &Name, 0, 0x20019u, &hkey);
        StringValue = v9;
        if ( v9 > 0 )
          StringValue = (unsigned __int16)v9 | 0x80070000;
        if ( StringValue < 0 )
          break;
        v27 = 0;
        memset_0(v28, 0, 0x206u);
        StringValue = RegGetStringValue(hkey, 0, &v27, 0x104u);
        if ( StringValue >= 0 )
        {
          pcbData = 4;
          v24 = 0;
          p = 0;
          RegGetValueW(hkey, 0, L"Version", 0x10u, 0, &p, &pcbData);
          v12 = -1;
          do
            ++v12;
          while ( *(_WORD *)&v28[2 * v12 - 2] );
          StringValue = _AllocStringWorker<CTCoAllocPolicy>(v11, v10, &v27, v12);
          if ( StringValue >= 0 )
          {
            v15 = -1;
            do
              ++v15;
            while ( *(_WORD *)&v26[2 * v15 - 2] );
            StringValue = _AllocStringWorker<CTCoAllocPolicy>(v14, v13, &Name, v15);
            if ( StringValue >= 0 )
            {
              v16 = IsFlagNotSet(hkey, L"Removing");
              v17 = a1;
              if ( !v16 )
                v17 = a2;
              StringValue = CAutoDSA<PROCESSED_SEARCH_ROOT>::AppendAndClearItem(v17, &p);
            }
          }
          PROCESSED_SEARCH_ROOT::DSADestroy((LPVOID *)&p, 0);
        }
        RegCloseKey(hkey);
        ++v6;
      }
      while ( StringValue >= 0 );
      v5 = 0;
      if ( StringValue != -2147024637 )
        v5 = StringValue;
      if ( v5 >= 0 )
      {
        if ( *a1 )
          v18 = DSA_Sort(*a1, SEARCH_ROOT::DSACompare, 0);
        else
          v18 = 0;
        v5 = !v18 ? 0x80004005 : 0;
      }
    }
    else
    {
      v5 = -2147024882;
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180021cd0  mov     [rsp-8+arg_10], rbx
0x180021cd5  push    rbp
0x180021cd6  push    rsi
0x180021cd7  push    rdi
0x180021cd8  push    r14
0x180021cda  push    r15
0x180021cdc  lea     rbp, [rsp-3A0h]
0x180021ce4  sub     rsp, 4A0h
0x180021ceb  mov     rax, cs:__security_cookie
0x180021cf2  xor     rax, rsp
0x180021cf5  mov     [rbp+3C0h+var_30], rax
0x180021cfc  mov     r14, rdx
0x180021cff  lea     r9, [rsp+4C0h+hKey]; HKEY *
0x180021d04  mov     rsi, rcx
0x180021d07  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows Search\\Pr"...
0x180021d0e  xor     r15d, r15d
0x180021d11  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180021d18  mov     [rsp+4C0h+hKey], r15
0x180021d1d  call    ?RegOpenKeyOpt@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; RegOpenKeyOpt(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x180021d22  mov     ebx, eax
0x180021d24  test    eax, eax
0x180021d26  jnz     loc_180021F54
0x180021d2c  lea     edx, [rax+4]
0x180021d2f  mov     rcx, rsi
0x180021d32  call    ?Create@?$CDSA_Base@UPROCESSED_SEARCH_ROOT@@@@QEAAHH@Z; CDSA_Base<PROCESSED_SEARCH_ROOT>::Create(int)
0x180021d37  test    eax, eax
0x180021d39  jz      loc_180021F44
0x180021d3f  lea     edx, [rbx+1]
0x180021d42  mov     rcx, r14
0x180021d45  call    ?Create@?$CDSA_Base@UPROCESSED_SEARCH_ROOT@@@@QEAAHH@Z; CDSA_Base<PROCESSED_SEARCH_ROOT>::Create(int)
0x180021d4a  test    eax, eax
0x180021d4c  jz      loc_180021F44
0x180021d52  xor     edx, edx; Val
0x180021d54  mov     [rsp+4C0h+Name], r15w
0x180021d5a  mov     r8d, 206h; Size
0x180021d60  lea     rcx, [rsp+4C0h+var_44E]; void *
0x180021d65  call    memset_0
0x180021d6a  mov     ebx, r15d
0x180021d6d  mov     rcx, [rsp+4C0h+hKey]; hKey
0x180021d72  lea     r8, [rsp+4C0h+Name]; lpName
0x180021d77  mov     r9d, 104h; cchName
0x180021d7d  mov     edx, ebx; dwIndex
0x180021d7f  call    cs:__imp_RegEnumKeyW
0x180021d85  mov     edi, eax
0x180021d87  test    eax, eax
0x180021d89  jle     short loc_180021D94
0x180021d8b  movzx   edi, ax
0x180021d8e  or      edi, 80070000h
0x180021d94  test    edi, edi
0x180021d96  js      loc_180021F0A
0x180021d9c  mov     rcx, [rsp+4C0h+hKey]; hKey
0x180021da1  lea     rax, [rsp+4C0h+hkey]
0x180021da6  mov     r9d, 20019h; samDesired
0x180021dac  mov     [rsp+4C0h+phkResult], rax; phkResult
0x180021db1  xor     r8d, r8d; ulOptions
0x180021db4  mov     [rsp+4C0h+hkey], r15
0x180021db9  lea     rdx, [rsp+4C0h+Name]; lpSubKey
0x180021dbe  call    cs:__imp_RegOpenKeyExW
0x180021dc4  mov     edi, eax
0x180021dc6  test    eax, eax
0x180021dc8  jle     short loc_180021DD3
0x180021dca  movzx   edi, ax
0x180021dcd  or      edi, 80070000h
0x180021dd3  test    edi, edi
0x180021dd5  js      loc_180021F0A
0x180021ddb  xor     edx, edx; Val
0x180021ddd  mov     [rbp+3C0h+var_240], r15w
0x180021de5  mov     r8d, 206h; Size
0x180021deb  lea     rcx, [rbp+3C0h+var_23E]; void *
0x180021df2  call    memset_0
0x180021df7  mov     rcx, [rsp+4C0h+hkey]; HKEY
0x180021dfc  lea     r8, [rbp+3C0h+var_240]; unsigned __int16 *
0x180021e03  mov     r9d, 104h; unsigned int
0x180021e09  xor     edx, edx; unsigned __int16 *
0x180021e0b  call    ?RegGetStringValue@@YAJPEAUHKEY__@@PEBGPEAGK@Z; RegGetStringValue(HKEY__ *,ushort const *,ushort *,ulong)
0x180021e10  mov     edi, eax
0x180021e12  test    eax, eax
0x180021e14  js      loc_180021EF5
0x180021e1a  mov     rcx, [rsp+4C0h+hkey]; hkey
0x180021e1f  lea     r8, Value; "Version"
0x180021e26  xor     eax, eax
0x180021e28  mov     [rsp+4C0h+var_470], 4
0x180021e30  mov     [rsp+4C0h+var_458], rax
0x180021e35  xorps   xmm0, xmm0
0x180021e38  lea     rax, [rsp+4C0h+var_470]
0x180021e3d  mov     r9d, 10h; dwFlags
0x180021e43  mov     [rsp+4C0h+pcbData], rax; pcbData
0x180021e48  xor     edx, edx; lpSubKey
0x180021e4a  lea     rax, [rsp+4C0h+p]
0x180021e4f  mov     [rsp+4C0h+pvData], rax; pvData
0x180021e54  mov     [rsp+4C0h+phkResult], r15; pdwType
0x180021e59  movups  [rsp+4C0h+p], xmm0
0x180021e5e  call    cs:__imp_RegGetValueW
0x180021e64  lea     rax, [rbp+3C0h+var_240]
0x180021e6b  or      r9, 0FFFFFFFFFFFFFFFFh
0x180021e6f  inc     r9
0x180021e72  cmp     [rax+r9*2], r15w
0x180021e77  jnz     short loc_180021E6F
0x180021e79  lea     rax, [rsp+4C0h+p+8]
0x180021e7e  lea     r8, [rbp+3C0h+var_240]
0x180021e85  mov     [rsp+4C0h+pvData], rax
0x180021e8a  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180021e8f  mov     edi, eax
0x180021e91  test    eax, eax
0x180021e93  js      short loc_180021EE9
0x180021e95  lea     rax, [rsp+4C0h+Name]
0x180021e9a  or      r9, 0FFFFFFFFFFFFFFFFh
0x180021e9e  inc     r9
0x180021ea1  cmp     [rax+r9*2], r15w
0x180021ea6  jnz     short loc_180021E9E
0x180021ea8  lea     rax, [rsp+4C0h+var_458]
0x180021ead  lea     r8, [rsp+4C0h+Name]
0x180021eb2  mov     [rsp+4C0h+pvData], rax
0x180021eb7  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180021ebc  mov     edi, eax
0x180021ebe  test    eax, eax
0x180021ec0  js      short loc_180021EE9
0x180021ec2  mov     rcx, [rsp+4C0h+hkey]; HKEY
0x180021ec7  lea     rdx, aRemoving; "Removing"
0x180021ece  call    ?IsFlagNotSet@@YAHPEAUHKEY__@@PEBG@Z; IsFlagNotSet(HKEY__ *,ushort const *)
0x180021ed3  lea     rdx, [rsp+4C0h+p]
0x180021ed8  mov     rcx, rsi
0x180021edb  test    eax, eax
0x180021edd  jnz     short loc_180021EE2
0x180021edf  mov     rcx, r14
0x180021ee2  call    ?AppendAndClearItem@?$CAutoDSA@UPROCESSED_SEARCH_ROOT@@@@QEAAJPEAUPROCESSED_SEARCH_ROOT@@@Z; CAutoDSA<PROCESSED_SEARCH_ROOT>::AppendAndClearItem(PROCESSED_SEARCH_ROOT *)
0x180021ee7  mov     edi, eax
0x180021ee9  xor     edx, edx; pData
0x180021eeb  lea     rcx, [rsp+4C0h+p]; p
0x180021ef0  call    ?DSADestroy@PROCESSED_SEARCH_ROOT@@SAHPEAU1@PEAX@Z; PROCESSED_SEARCH_ROOT::DSADestroy(PROCESSED_SEARCH_ROOT *,void *)
0x180021ef5  mov     rcx, [rsp+4C0h+hkey]; hKey
0x180021efa  call    cs:__imp_RegCloseKey
0x180021f00  inc     ebx
0x180021f02  test    edi, edi
0x180021f04  jns     loc_180021D6D
0x180021f0a  cmp     edi, 80070103h
0x180021f10  mov     ebx, r15d
0x180021f13  cmovnz  ebx, edi
0x180021f16  test    ebx, ebx
0x180021f18  js      short loc_180021F49
0x180021f1a  mov     rcx, [rsi]; pdsa
0x180021f1d  test    rcx, rcx
0x180021f20  jz      short loc_180021F33
0x180021f22  xor     r8d, r8d; lParam
0x180021f25  lea     rdx, ?DSACompare@SEARCH_ROOT@@SAHPEBU1@0_J@Z; pfnCompare
0x180021f2c  call    DSA_Sort
0x180021f31  jmp     short loc_180021F36
0x180021f33  mov     eax, r15d
0x180021f36  neg     eax
0x180021f38  sbb     ebx, ebx
0x180021f3a  not     ebx
0x180021f3c  and     ebx, 80004005h
0x180021f42  jmp     short loc_180021F49
0x180021f44  mov     ebx, 8007000Eh
0x180021f49  mov     rcx, [rsp+4C0h+hKey]; hKey
0x180021f4e  call    cs:__imp_RegCloseKey
0x180021f54  mov     eax, ebx
0x180021f56  mov     rcx, [rbp+3C0h+var_30]
0x180021f5d  xor     rcx, rsp; StackCookie
0x180021f60  call    __security_check_cookie
0x180021f65  mov     rbx, [rsp+4C0h+arg_10]
0x180021f6d  add     rsp, 4A0h
0x180021f74  pop     r15
0x180021f76  pop     r14
0x180021f78  pop     rdi
0x180021f79  pop     rsi
0x180021f7a  pop     rbp
0x180021f7b  retn
```

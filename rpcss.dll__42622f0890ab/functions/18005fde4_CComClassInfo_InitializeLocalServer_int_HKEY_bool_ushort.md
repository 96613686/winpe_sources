# CComClassInfo::InitializeLocalServer(int,HKEY__ *,bool,ushort)

- ea: `0x18005fde4`
- end: `0x180060326`
- name: `?InitializeLocalServer@CComClassInfo@@AEAAJHPEAUHKEY__@@_NG@Z`
- size: `1346`
- prototype: `__int64 __fastcall(CComClassInfo *this, int, HKEY hKey, char, unsigned __int16)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005e598`

## callees

- `0x18000acac`
- `0x180034540`
- `0x1800566cc`
- `0x18005fde4`
- `0x180070740`
- `0x18007ced0`
- `0x18009ffc0`
- `0x1800cb480`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005fec7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800602f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005fec7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800602f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006030d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006030d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005fe27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005fe27`

## string_xrefs

- `0x18005ffde`: `onecore\com\combase\catalog\class.cxx`
- `0x180060029`: `onecore\com\combase\catalog\class.cxx`
- `0x1800600aa`: `onecore\com\combase\catalog\class.cxx`
- `0x180060113`: `onecore\com\combase\catalog\class.cxx`
- `0x180060203`: `onecore\com\combase\catalog\class.cxx`
- `0x1800602c4`: `onecore\com\combase\catalog\class.cxx`
- `0x18005ffcb`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x180060030`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x1800600a3`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x18005ff73`: `CLSID:%ws %!HRESULT!`
- `0x1800600fd`: `CLSID:%ws Value:%!HRESULT!`
- `0x18005ffd2`: `CComClassInfo::InitializeLocalServer`
- `0x18006001d`: `CComClassInfo::InitializeLocalServer`
- `0x18006009c`: `CComClassInfo::InitializeLocalServer`
- `0x18006010c`: `CComClassInfo::InitializeLocalServer`
- `0x1800601e8`: `CComClassInfo::InitializeLocalServer`
- `0x1800602a9`: `CComClassInfo::InitializeLocalServer`
- `0x1800602bd`: `CLSID:%ws FileNotFound on server architecture query, continuing on%ws %!HRESULT!`
- `0x1800601fc`: `CLSID:%ws Binary architecture doesn't match registry view architecture. Server:%ws %!HRESULT!`
- `0x180060279`: `CLSID:%ws Unable to determine server architecture, treating as fatal%ws %!HRESULT!`

## pseudocode

```c
__int64 __fastcall CComClassInfo::InitializeLocalServer(
        CComClassInfo *this,
        int a2,
        HKEY hKey,
        char a4,
        unsigned __int16 a5)
{
  LSTATUS v8; // eax
  signed int RegistryStringValue; // ebx
  int v10; // r14d
  int v11; // r9d
  const unsigned __int16 near **v12; // rsi
  const unsigned __int16 **v13; // rsi
  signed int v14; // eax
  CComClassInfo *v15; // rcx
  int v16; // r9d
  int ExeArchitectureFromRegString; // eax
  unsigned __int16 *v18; // r8
  __int64 v20; // [rsp+30h] [rbp-38h]
  __int64 v21; // [rsp+38h] [rbp-30h]
  HKEY hKeya; // [rsp+40h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int16 *v24; // [rsp+50h] [rbp-18h] BYREF

  hKeya = 0;
  v8 = RegOpenKeyExW(hKey, L"LocalServer32", 0, 0x20019u, &hKeya);
  RegistryStringValue = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      RegistryStringValue = (unsigned __int16)v8 | 0x80070000;
    if ( RegistryStringValue < 0 )
    {
LABEL_17:
      if ( RegistryStringValue != -2147024894 )
      {
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          LODWORD(v20) = RegistryStringValue;
          ComTraceMessageT<unsigned short *,long>(
            (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
            (unsigned int)"CComClassInfo::InitializeLocalServer",
            920,
            0,
            (__int64)L"CLSID:%ws %!HRESULT!",
            (char *)this + 112,
            v20);
        }
        goto LABEL_71;
      }
LABEL_70:
      RegistryStringValue = 0;
      goto LABEL_71;
    }
  }
  v10 = 0;
  if ( a4 )
  {
    lpMem = 0;
    v24 = 0;
    RegistryStringValue = GetRegistryStringValue(hKeya, 0, L"LocalServer32", 1u, (unsigned __int16 **)&lpMem);
    if ( RegistryStringValue < 0 )
    {
      if ( RegistryStringValue != -2147024894 )
      {
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          ComTraceMessageT<unsigned short *,unsigned short const *,long>(
            (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
            (unsigned int)"CComClassInfo::InitializeLocalServer",
            824,
            v11,
            (__int64)L"CLSID:%ws Value:%ws %!HRESULT!",
            (char *)this + 112,
            L"LocalServer32",
            RegistryStringValue);
        goto LABEL_71;
      }
    }
    else
    {
      v12 = (const unsigned __int16 near **)lpMem;
      RegistryStringValue = CComClassInfo::GetPathFromDarwinDescriptor(this, a2, (unsigned __int16 *)lpMem, &v24);
      if ( v12 && v12 != &g_wszEmptyString )
        HeapFree(g_hHeap, 0, v12);
      if ( RegistryStringValue < 0 )
      {
        v10 = -2147467229;
        if ( RegistryStringValue != -2147467229 )
        {
          if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
            ComTraceMessageT<unsigned short *,unsigned short *,long>(
              (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
              (unsigned int)"CComClassInfo::InitializeLocalServer",
              805,
              0,
              (__int64)L"CLSID:%ws Value:%ws %!HRESULT!",
              (char *)this + 112,
              0,
              RegistryStringValue);
          goto LABEL_71;
        }
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          ComTraceMessageT<unsigned short *,unsigned short *,long>(
            (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
            (unsigned int)"CComClassInfo::InitializeLocalServer",
            811,
            0,
            (__int64)L"CLSID:%ws Value:%ws %!HRESULT!",
            (char *)this + 112,
            0,
            -2147467229);
      }
      else
      {
        *((_QWORD *)this + 33) = v24;
      }
    }
  }
  v13 = (const unsigned __int16 **)((char *)this + 264);
  if ( !*((_QWORD *)this + 33) )
  {
    RegistryStringValue = GetRegistryStringValue(hKeya, 0, 0, 0, (unsigned __int16 **)this + 33);
    if ( RegistryStringValue == -2147024894 )
    {
      RegistryStringValue = v10;
      if ( v10 >= 0 )
        RegistryStringValue = -2147024894;
      if ( RegistryStringValue < 0 )
        goto LABEL_17;
    }
    else if ( RegistryStringValue < 0 )
    {
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        LODWORD(v20) = RegistryStringValue;
        ComTraceMessageT<unsigned short *,long>(
          (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
          (unsigned int)"CComClassInfo::InitializeLocalServer",
          844,
          0,
          (__int64)L"CLSID:%ws Value:%!HRESULT!",
          (char *)this + 112,
          v20);
      }
      goto LABEL_71;
    }
  }
  v14 = GetRegistryStringValue(hKeya, 0, L"ServerExecutable", 0, (unsigned __int16 **)this + 37);
  RegistryStringValue = 0;
  if ( v14 != -2147024894 )
    RegistryStringValue = v14;
  if ( RegistryStringValue >= 0 )
  {
    if ( !*v13 )
      goto LABEL_71;
    ExeArchitectureFromRegString = CComClassInfo::GetExeArchitectureFromRegString(v15, *v13, (unsigned int *)this + 76);
    RegistryStringValue = ExeArchitectureFromRegString;
    if ( ExeArchitectureFromRegString >= 0 )
    {
      if ( a5
        && *((_DWORD *)this + 76) != a5
        && (dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1)) )
      {
        LODWORD(v21) = RegistryStringValue;
        ComTraceMessageT<unsigned short *,unsigned short *,long>(
          (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
          (unsigned int)"CComClassInfo::InitializeLocalServer",
          883,
          1,
          (__int64)L"CLSID:%ws Binary architecture doesn't match registry view architecture. Server:%ws %!HRESULT!",
          (char *)this + 112,
          *v13,
          v21);
      }
      *((_DWORD *)this + 56) |= 4u;
      *((_DWORD *)this + 24) = 1;
      goto LABEL_70;
    }
    if ( (unsigned int)(ExeArchitectureFromRegString + 2147024894) <= 1 )
    {
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
      {
        LODWORD(v21) = RegistryStringValue;
        ComTraceMessageT<unsigned short *,unsigned short *,long>(
          (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
          (unsigned int)"CComClassInfo::InitializeLocalServer",
          890,
          1,
          (__int64)L"CLSID:%ws FileNotFound on server architecture query, continuing on%ws %!HRESULT!",
          (char *)this + 112,
          *v13,
          v21);
      }
      v18 = (unsigned __int16 *)*v13;
      if ( *v13 && v18 != (unsigned __int16 *)&g_wszEmptyString )
        HeapFree(g_hHeap, 0, v18);
      *v13 = 0;
      goto LABEL_70;
    }
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
    {
      LODWORD(v21) = RegistryStringValue;
      ComTraceMessageT<unsigned short *,unsigned short *,long>(
        (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
        (unsigned int)"CComClassInfo::InitializeLocalServer",
        900,
        1,
        (__int64)L"CLSID:%ws Unable to determine server architecture, treating as fatal%ws %!HRESULT!",
        (char *)this + 112,
        *v13,
        v21);
    }
  }
  else if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
  {
    LODWORD(v21) = RegistryStringValue;
    ComTraceMessageT<unsigned short *,unsigned short const *,long>(
      (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
      (unsigned int)"CComClassInfo::InitializeLocalServer",
      863,
      v16,
      (__int64)L"CLSID:%ws Value:%ws %!HRESULT!",
      (char *)this + 112,
      L"ServerExecutable",
      v21);
  }
LABEL_71:
  if ( hKeya )
    RegCloseKey(hKeya);
  return (unsigned int)RegistryStringValue;
}

```

## disassembly

```asm
0x18005fde4  push    rbp
0x18005fde6  push    rbx
0x18005fde7  push    rsi
0x18005fde8  push    rdi
0x18005fde9  push    r12
0x18005fdeb  push    r13
0x18005fded  push    r14
0x18005fdef  push    r15
0x18005fdf1  mov     rbp, rsp
0x18005fdf4  sub     rsp, 68h
0x18005fdf8  mov     rdi, rcx
0x18005fdfb  mov     rax, r8
0x18005fdfe  lea     rcx, [rbp+hKey]
0x18005fe02  mov     sil, r9b
0x18005fe05  mov     [rsp+68h+phkResult], rcx; phkResult
0x18005fe0a  mov     r15d, edx
0x18005fe0d  xor     r12d, r12d
0x18005fe10  lea     rdx, ?LocalServer32@Constants@Catalog@Com@@3QBGB; "LocalServer32"
0x18005fe17  mov     rcx, rax; hKey
0x18005fe1a  mov     [rbp+hKey], r12
0x18005fe1e  mov     r9d, 20019h; samDesired
0x18005fe24  xor     r8d, r8d; ulOptions
0x18005fe27  call    cs:__imp_RegOpenKeyExW
0x18005fe2d  mov     ebx, eax
0x18005fe2f  test    eax, eax
0x18005fe31  jz      short loc_18005FE4D
0x18005fe33  jle     short loc_18005FE3E
0x18005fe35  movzx   ebx, ax
0x18005fe38  or      ebx, 80070000h
0x18005fe3e  test    ebx, ebx
0x18005fe40  jns     short loc_18005FE4D
0x18005fe42  mov     r15d, 80070002h
0x18005fe48  jmp     loc_18005FF29
0x18005fe4d  mov     r14d, r12d
0x18005fe50  mov     r13d, 1
0x18005fe56  test    sil, sil
0x18005fe59  jz      loc_18005FEE0
0x18005fe5f  mov     rcx, [rbp+hKey]; hkey
0x18005fe63  lea     rax, [rbp+lpMem]
0x18005fe67  lea     rsi, ?LocalServer32@Constants@Catalog@Com@@3QBGB; "LocalServer32"
0x18005fe6e  mov     [rbp+lpMem], r12
0x18005fe72  mov     r8, rsi; lpValue
0x18005fe75  mov     [rbp+var_18], r12
0x18005fe79  mov     r9d, r13d; unsigned int
0x18005fe7c  mov     [rsp+68h+phkResult], rax; unsigned __int16 **
0x18005fe81  xor     edx, edx; lpSubKey
0x18005fe83  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x18005fe88  mov     ebx, eax
0x18005fe8a  test    eax, eax
0x18005fe8c  js      loc_18006004F
0x18005fe92  mov     rsi, [rbp+lpMem]
0x18005fe96  lea     r9, [rbp+var_18]; unsigned __int16 **
0x18005fe9a  mov     r8, rsi; unsigned __int16 *
0x18005fe9d  mov     edx, r15d; int
0x18005fea0  mov     rcx, rdi; this
0x18005fea3  call    ?GetPathFromDarwinDescriptor@CComClassInfo@@AEAAJHPEAGPEAPEAG@Z; CComClassInfo::GetPathFromDarwinDescriptor(int,ushort *,ushort * *)
0x18005fea8  mov     ebx, eax
0x18005feaa  test    rsi, rsi
0x18005fead  jz      short loc_18005FECD
0x18005feaf  lea     rax, ?g_wszEmptyString@@3QBGB; ushort const near * const g_wszEmptyString
0x18005feb6  cmp     rsi, rax
0x18005feb9  jz      short loc_18005FECD
0x18005febb  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18005fec2  mov     r8, rsi; lpMem
0x18005fec5  xor     edx, edx; dwFlags
0x18005fec7  call    cs:__imp_HeapFree
0x18005fecd  test    ebx, ebx
0x18005fecf  js      loc_18005FF7F
0x18005fed5  mov     rax, [rbp+var_18]
0x18005fed9  mov     [rdi+108h], rax
0x18005fee0  mov     r15d, 80070002h
0x18005fee6  lea     rsi, [rdi+108h]
0x18005feed  cmp     [rsi], r12
0x18005fef0  jnz     loc_180060124
0x18005fef6  mov     rcx, [rbp+hKey]; hkey
0x18005fefa  xor     r9d, r9d; unsigned int
0x18005fefd  xor     r8d, r8d; lpValue
0x18005ff00  mov     [rsp+68h+phkResult], rsi; unsigned __int16 **
0x18005ff05  xor     edx, edx; lpSubKey
0x18005ff07  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x18005ff0c  mov     ebx, eax
0x18005ff0e  cmp     eax, r15d
0x18005ff11  jnz     loc_1800600C0
0x18005ff17  test    r14d, r14d
0x18005ff1a  mov     ebx, r14d
0x18005ff1d  cmovns  ebx, r15d
0x18005ff21  test    ebx, ebx
0x18005ff23  jns     loc_180060124
0x18005ff29  cmp     ebx, r15d
0x18005ff2c  jz      loc_180060301
0x18005ff32  test    ebx, ebx
0x18005ff34  jns     loc_180060304
0x18005ff3a  mov     eax, cs:dword_18014E4B8
0x18005ff40  test    eax, eax
0x18005ff42  jnz     short loc_18005FF60
0x18005ff44  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18005ff4b  jz      loc_180060304
0x18005ff51  xor     ecx, ecx
0x18005ff53  call    IsWppLevelEnabled
0x18005ff58  test    al, al
0x18005ff5a  jz      loc_180060304
0x18005ff60  lea     rax, [rdi+70h]
0x18005ff64  mov     dword ptr [rsp+68h+var_38], ebx
0x18005ff68  mov     [rsp+68h+var_40], rax
0x18005ff6d  mov     r8d, 398h
0x18005ff73  lea     rax, aClsidWsHresult; "CLSID:%ws %!HRESULT!"
0x18005ff7a  jmp     loc_180060104
0x18005ff7f  mov     eax, cs:dword_18014E4B8
0x18005ff85  mov     r14d, 80004023h
0x18005ff8b  cmp     ebx, r14d
0x18005ff8e  jz      short loc_18005FFEF
0x18005ff90  test    eax, eax
0x18005ff92  jnz     short loc_18005FFB0
0x18005ff94  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18005ff9b  jz      loc_180060304
0x18005ffa1  xor     ecx, ecx
0x18005ffa3  call    IsWppLevelEnabled
0x18005ffa8  test    al, al
0x18005ffaa  jz      loc_180060304
0x18005ffb0  lea     rax, [rdi+70h]
0x18005ffb4  mov     dword ptr [rsp+68h+var_30], ebx
0x18005ffb8  mov     [rsp+68h+var_38], r12
0x18005ffbd  xor     r9d, r9d
0x18005ffc0  mov     [rsp+68h+var_40], rax
0x18005ffc5  mov     r8d, 325h
0x18005ffcb  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x18005ffd2  lea     rdx, aCcomclassinfoI_4; "CComClassInfo::InitializeLocalServer"
0x18005ffd9  mov     [rsp+68h+phkResult], rax
0x18005ffde  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x18005ffe5  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x18005ffea  jmp     loc_180060304
0x18005ffef  test    eax, eax
0x18005fff1  jnz     short loc_18006000F
0x18005fff3  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18005fffa  jz      loc_18005FEE0
0x180060000  xor     ecx, ecx
0x180060002  call    IsWppLevelEnabled
0x180060007  test    al, al
0x180060009  jz      loc_18005FEE0
0x18006000f  mov     dword ptr [rsp+68h+var_30], r14d
0x180060014  lea     rax, [rdi+70h]
0x180060018  mov     [rsp+68h+var_38], r12
0x18006001d  lea     rdx, aCcomclassinfoI_4; "CComClassInfo::InitializeLocalServer"
0x180060024  mov     [rsp+68h+var_40], rax
0x180060029  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x180060030  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x180060037  xor     r9d, r9d
0x18006003a  mov     r8d, 32Bh
0x180060040  mov     [rsp+68h+phkResult], rax
0x180060045  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x18006004a  jmp     loc_18005FEE0
0x18006004f  mov     r15d, 80070002h
0x180060055  cmp     ebx, r15d
0x180060058  jz      loc_18005FEE6
0x18006005e  mov     eax, cs:dword_18014E4B8
0x180060064  test    eax, eax
0x180060066  jnz     short loc_180060084
0x180060068  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18006006f  jz      loc_180060304
0x180060075  xor     ecx, ecx
0x180060077  call    IsWppLevelEnabled
0x18006007c  test    al, al
0x18006007e  jz      loc_180060304
0x180060084  mov     dword ptr [rsp+68h+var_30], ebx
0x180060088  mov     r8d, 338h
0x18006008e  mov     [rsp+68h+var_38], rsi
0x180060093  lea     rax, [rdi+70h]
0x180060097  mov     [rsp+68h+var_40], rax
0x18006009c  lea     rdx, aCcomclassinfoI_4; "CComClassInfo::InitializeLocalServer"
0x1800600a3  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x1800600aa  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x1800600b1  mov     [rsp+68h+phkResult], rax
0x1800600b6  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x1800600bb  jmp     loc_180060304
0x1800600c0  test    ebx, ebx
0x1800600c2  jns     short loc_180060124
0x1800600c4  mov     eax, cs:dword_18014E4B8
0x1800600ca  test    eax, eax
0x1800600cc  jnz     short loc_1800600EA
0x1800600ce  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800600d5  jz      loc_180060304
0x1800600db  xor     ecx, ecx
0x1800600dd  call    IsWppLevelEnabled
0x1800600e2  test    al, al
0x1800600e4  jz      loc_180060304
0x1800600ea  lea     rax, [rdi+70h]
0x1800600ee  mov     dword ptr [rsp+68h+var_38], ebx
0x1800600f2  mov     [rsp+68h+var_40], rax
0x1800600f7  mov     r8d, 34Ch
0x1800600fd  lea     rax, aClsidWsValueHr; "CLSID:%ws Value:%!HRESULT!"
0x180060104  xor     r9d, r9d
0x180060107  mov     [rsp+68h+phkResult], rax
0x18006010c  lea     rdx, aCcomclassinfoI_4; "CComClassInfo::InitializeLocalServer"
0x180060113  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x18006011a  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x18006011f  jmp     loc_180060304
0x180060124  mov     rcx, [rbp+hKey]; hkey
0x180060128  lea     rax, [rdi+128h]
0x18006012f  lea     r14, ?ServerExecutable@Constants@Catalog@Com@@3QBGB; "ServerExecutable"
0x180060136  mov     [rsp+68h+phkResult], rax; unsigned __int16 **
0x18006013b  mov     r8, r14; lpValue
0x18006013e  xor     r9d, r9d; unsigned int
0x180060141  xor     edx, edx; lpSubKey
0x180060143  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x180060148  cmp     eax, r15d
0x18006014b  mov     ebx, r12d
0x18006014e  cmovnz  ebx, eax
0x180060151  test    ebx, ebx
0x180060153  jns     short loc_18006018F
0x180060155  mov     eax, cs:dword_18014E4B8
0x18006015b  test    eax, eax
0x18006015d  jnz     short loc_18006017B
0x18006015f  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x180060166  jz      loc_180060304
0x18006016c  xor     ecx, ecx
0x18006016e  call    IsWppLevelEnabled
0x180060173  test    al, al
0x180060175  jz      loc_180060304
0x18006017b  mov     dword ptr [rsp+68h+var_30], ebx
0x18006017f  mov     r8d, 35Fh
0x180060185  mov     [rsp+68h+var_38], r14
0x18006018a  jmp     loc_180060093
0x18006018f  mov     rdx, [rsi]; unsigned __int16 *
0x180060192  test    rdx, rdx
0x180060195  jz      loc_180060304
0x18006019b  lea     r14, [rdi+130h]
0x1800601a2  mov     r8, r14; unsigned int *
0x1800601a5  call    ?GetExeArchitectureFromRegString@CComClassInfo@@AEAAJPEBGPEAK@Z; CComClassInfo::GetExeArchitectureFromRegString(ushort const *,ulong *)
0x1800601aa  mov     ebx, eax
0x1800601ac  test    eax, eax
0x1800601ae  js      short loc_18006022A
0x1800601b0  movzx   eax, [rbp+arg_20]
0x1800601b4  test    ax, ax
0x1800601b7  jz      short loc_18006021A
0x1800601b9  cmp     [r14], eax
0x1800601bc  jz      short loc_18006021A
0x1800601be  mov     eax, cs:dword_18014E4B8
0x1800601c4  test    eax, eax
0x1800601c6  jnz     short loc_1800601DD
0x1800601c8  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800601cf  jz      short loc_18006021A
0x1800601d1  mov     ecx, r13d
0x1800601d4  call    IsWppLevelEnabled
0x1800601d9  test    al, al
0x1800601db  jz      short loc_18006021A
0x1800601dd  mov     rax, [rsi]
0x1800601e0  lea     rcx, [rdi+70h]
0x1800601e4  mov     dword ptr [rsp+68h+var_30], ebx
0x1800601e8  lea     rdx, aCcomclassinfoI_4; "CComClassInfo::InitializeLocalServer"
0x1800601ef  mov     [rsp+68h+var_38], rax
0x1800601f4  mov     r9d, r13d
0x1800601f7  mov     [rsp+68h+var_40], rcx
0x1800601fc  lea     rax, aClsidWsBinaryA_0; "CLSID:%ws Binary architecture doesn't m"...
0x180060203  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x18006020a  mov     [rsp+68h+phkResult], rax
0x18006020f  mov     r8d, 373h
0x180060215  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x18006021a  or      dword ptr [rdi+0E0h], 4
0x180060221  mov     [rdi+60h], r13d
0x180060225  jmp     loc_180060301
0x18006022a  add     eax, 7FF8FFFEh
0x18006022f  cmp     eax, r13d
0x180060232  mov     eax, cs:dword_18014E4B8
0x180060238  jbe     short loc_180060285
0x18006023a  test    eax, eax
0x18006023c  jnz     short loc_18006025B
0x18006023e  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x180060245  jz      loc_180060304
0x18006024b  mov     ecx, r13d
0x18006024e  call    IsWppLevelEnabled
0x180060253  test    al, al
0x180060255  jz      loc_180060304
0x18006025b  mov     rax, [rsi]
0x18006025e  lea     rcx, [rdi+70h]
0x180060262  mov     dword ptr [rsp+68h+var_30], ebx
0x180060266  mov     r9d, r13d
0x180060269  mov     [rsp+68h+var_38], rax
0x18006026e  mov     r8d, 384h
0x180060274  mov     [rsp+68h+var_40], rcx
0x180060279  lea     rax, aClsidWsUnableT; "CLSID:%ws Unable to determine server ar"...
0x180060280  jmp     loc_18005FFD2
0x180060285  test    eax, eax
0x180060287  jnz     short loc_18006029E
0x180060289  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x180060290  jz      short loc_1800602DB
0x180060292  mov     ecx, r13d
0x180060295  call    IsWppLevelEnabled
0x18006029a  test    al, al
0x18006029c  jz      short loc_1800602DB
0x18006029e  mov     rax, [rsi]
0x1800602a1  lea     rcx, [rdi+70h]
0x1800602a5  mov     dword ptr [rsp+68h+var_30], ebx
0x1800602a9  lea     rdx, aCcomclassinfoI_4; "CComClassInfo::InitializeLocalServer"
0x1800602b0  mov     [rsp+68h+var_38], rax
0x1800602b5  mov     r9d, r13d
0x1800602b8  mov     [rsp+68h+var_40], rcx
0x1800602bd  lea     rax, aClsidWsFilenot; "CLSID:%ws FileNotFound on server archit"...
0x1800602c4  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x1800602cb  mov     [rsp+68h+phkResult], rax
0x1800602d0  mov     r8d, 37Ah
  ... truncated ...
```

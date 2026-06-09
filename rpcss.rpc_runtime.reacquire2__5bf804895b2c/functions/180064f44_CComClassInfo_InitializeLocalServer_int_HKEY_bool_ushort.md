# CComClassInfo::InitializeLocalServer(int,HKEY__ *,bool,ushort)

- ea: `0x180064f44`
- end: `0x18006549e`
- name: `?InitializeLocalServer@CComClassInfo@@AEAAJHPEAUHKEY__@@_NG@Z`
- size: `1370`
- prototype: `__int64 __usercall@<rax>(CComClassInfo *__hidden this@<rcx>, int@<edx>, HKEY hKey@<r8>, bool@<r9b>, unsigned __int16)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180063694`

## callees

- `0x1800116bc`
- `0x180034260`
- `0x18005bcb0`
- `0x180064f44`
- `0x180074d98`
- `0x18007ac30`
- `0x180081158`
- `0x1800a543c`
- `0x1800d15d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006502d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065463`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006502d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065463`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006547e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006547e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180064f87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180064f87`

## string_xrefs

- `0x18006514a`: `onecore\com\combase\catalog\class.cxx`
- `0x180065195`: `onecore\com\combase\catalog\class.cxx`
- `0x180065216`: `onecore\com\combase\catalog\class.cxx`
- `0x18006527f`: `onecore\com\combase\catalog\class.cxx`
- `0x18006536e`: `onecore\com\combase\catalog\class.cxx`
- `0x18006542f`: `onecore\com\combase\catalog\class.cxx`
- `0x180065137`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x18006519c`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x18006520f`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x1800650df`: `CLSID:%ws %!HRESULT!`
- `0x18006513e`: `CComClassInfo::InitializeLocalServer`
- `0x180065189`: `CComClassInfo::InitializeLocalServer`
- `0x180065208`: `CComClassInfo::InitializeLocalServer`
- `0x180065278`: `CComClassInfo::InitializeLocalServer`
- `0x180065353`: `CComClassInfo::InitializeLocalServer`
- `0x180065414`: `CComClassInfo::InitializeLocalServer`
- `0x180065367`: `CLSID:%ws Binary architecture doesn't match registry view architecture. Server:%ws %!HRESULT!`
- `0x180065269`: `CLSID:%ws Value:%!HRESULT!`
- `0x1800653e4`: `CLSID:%ws Unable to determine server architecture, treating as fatal%ws %!HRESULT!`
- `0x180065428`: `CLSID:%ws FileNotFound on server architecture query, continuing on%ws %!HRESULT!`

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
  int RegistryStringValue; // ebx
  int v10; // r14d
  int v11; // r9d
  const unsigned __int16 near **v12; // rsi
  const unsigned __int16 **v13; // rsi
  int v14; // eax
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
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
        goto LABEL_70;
      }
LABEL_69:
      RegistryStringValue = 0;
      goto LABEL_70;
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
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          ComTraceMessageT<unsigned short *,unsigned short const *,long>(
            (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
            (unsigned int)"CComClassInfo::InitializeLocalServer",
            824,
            v11,
            (__int64)L"CLSID:%ws Value:%ws %!HRESULT!",
            (char *)this + 112,
            L"LocalServer32",
            RegistryStringValue);
        goto LABEL_70;
      }
    }
    else
    {
      v12 = (const unsigned __int16 near **)lpMem;
      RegistryStringValue = CComClassInfo::GetPathFromDarwinDescriptor(
                              this,
                              a2,
                              (unsigned __int16 *)lpMem,
                              (LPVOID *)&v24);
      if ( v12 && v12 != &g_wszEmptyString )
        HeapFree(g_hHeap, 0, v12);
      if ( RegistryStringValue < 0 )
      {
        v10 = -2147467229;
        if ( RegistryStringValue != -2147467229 )
        {
          if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
            ComTraceMessageT<unsigned short *,unsigned short *,long>(
              (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
              (unsigned int)"CComClassInfo::InitializeLocalServer",
              805,
              0,
              (__int64)L"CLSID:%ws Value:%ws %!HRESULT!",
              (char *)this + 112,
              0,
              RegistryStringValue);
          goto LABEL_70;
        }
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
      goto LABEL_70;
    }
  }
  v14 = GetRegistryStringValue(hKeya, 0, L"ServerExecutable", 0, (unsigned __int16 **)this + 37);
  RegistryStringValue = 0;
  if ( v14 != -2147024894 )
    RegistryStringValue = v14;
  if ( RegistryStringValue >= 0 )
  {
    if ( !*v13 )
      goto LABEL_70;
    ExeArchitectureFromRegString = CComClassInfo::GetExeArchitectureFromRegString(v15, *v13, (unsigned int *)this + 76);
    RegistryStringValue = ExeArchitectureFromRegString;
    if ( ExeArchitectureFromRegString >= 0 )
    {
      if ( !CComClassInfo::IsBinaryArchitectureExpectedForView(this, a5)
        && (dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1)) )
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
      goto LABEL_69;
    }
    if ( (unsigned int)(ExeArchitectureFromRegString + 2147024894) <= 1 )
    {
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
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
      goto LABEL_69;
    }
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
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
  else if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
LABEL_70:
  if ( hKeya )
    RegCloseKey(hKeya);
  return (unsigned int)RegistryStringValue;
}

```

## disassembly

```asm
0x180064f44  push    rbp
0x180064f46  push    rbx
0x180064f47  push    rsi
0x180064f48  push    rdi
0x180064f49  push    r12
0x180064f4b  push    r13
0x180064f4d  push    r14
0x180064f4f  push    r15
0x180064f51  mov     rbp, rsp
0x180064f54  sub     rsp, 68h
0x180064f58  mov     rdi, rcx
0x180064f5b  mov     rax, r8
0x180064f5e  lea     rcx, [rbp+hKey]
0x180064f62  mov     sil, r9b
0x180064f65  mov     [rsp+68h+phkResult], rcx; phkResult
0x180064f6a  mov     r15d, edx
0x180064f6d  xor     r12d, r12d
0x180064f70  lea     rdx, ?LocalServer32@Constants@Catalog@Com@@3QBGB; "LocalServer32"
0x180064f77  mov     rcx, rax; hKey
0x180064f7a  mov     [rbp+hKey], r12
0x180064f7e  mov     r9d, 20019h; samDesired
0x180064f84  xor     r8d, r8d; ulOptions
0x180064f87  call    cs:__imp_RegOpenKeyExW
0x180064f8e  nop     dword ptr [rax+rax+00h]
0x180064f93  mov     ebx, eax
0x180064f95  test    eax, eax
0x180064f97  jz      short loc_180064FB3
0x180064f99  jle     short loc_180064FA4
0x180064f9b  movzx   ebx, ax
0x180064f9e  or      ebx, 80070000h
0x180064fa4  test    ebx, ebx
0x180064fa6  jns     short loc_180064FB3
0x180064fa8  mov     r15d, 80070002h
0x180064fae  jmp     loc_180065095
0x180064fb3  mov     r14d, r12d
0x180064fb6  mov     r13d, 1
0x180064fbc  test    sil, sil
0x180064fbf  jz      loc_18006504C
0x180064fc5  mov     rcx, [rbp+hKey]; hkey
0x180064fc9  lea     rax, [rbp+lpMem]
0x180064fcd  lea     rsi, ?LocalServer32@Constants@Catalog@Com@@3QBGB; "LocalServer32"
0x180064fd4  mov     [rbp+lpMem], r12
0x180064fd8  mov     r8, rsi; lpValue
0x180064fdb  mov     [rbp+var_18], r12
0x180064fdf  mov     r9d, r13d; unsigned int
0x180064fe2  mov     [rsp+68h+phkResult], rax; unsigned __int16 **
0x180064fe7  xor     edx, edx; lpSubKey
0x180064fe9  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x180064fee  mov     ebx, eax
0x180064ff0  test    eax, eax
0x180064ff2  js      loc_1800651BB
0x180064ff8  mov     rsi, [rbp+lpMem]
0x180064ffc  lea     r9, [rbp+var_18]; unsigned __int16 **
0x180065000  mov     r8, rsi; unsigned __int16 *
0x180065003  mov     edx, r15d; int
0x180065006  mov     rcx, rdi; this
0x180065009  call    ?GetPathFromDarwinDescriptor@CComClassInfo@@AEAAJHPEAGPEAPEAG@Z; CComClassInfo::GetPathFromDarwinDescriptor(int,ushort *,ushort * *)
0x18006500e  mov     ebx, eax
0x180065010  test    rsi, rsi
0x180065013  jz      short loc_180065039
0x180065015  lea     rax, ?g_wszEmptyString@@3QBGB; ushort const near * const g_wszEmptyString
0x18006501c  cmp     rsi, rax
0x18006501f  jz      short loc_180065039
0x180065021  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180065028  mov     r8, rsi; lpMem
0x18006502b  xor     edx, edx; dwFlags
0x18006502d  call    cs:__imp_HeapFree
0x180065034  nop     dword ptr [rax+rax+00h]
0x180065039  test    ebx, ebx
0x18006503b  js      loc_1800650EB
0x180065041  mov     rax, [rbp+var_18]
0x180065045  mov     [rdi+108h], rax
0x18006504c  mov     r15d, 80070002h
0x180065052  lea     rsi, [rdi+108h]
0x180065059  cmp     [rsi], r12
0x18006505c  jnz     loc_180065290
0x180065062  mov     rcx, [rbp+hKey]; hkey
0x180065066  xor     r9d, r9d; unsigned int
0x180065069  xor     r8d, r8d; lpValue
0x18006506c  mov     [rsp+68h+phkResult], rsi; unsigned __int16 **
0x180065071  xor     edx, edx; lpSubKey
0x180065073  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x180065078  mov     ebx, eax
0x18006507a  cmp     eax, r15d
0x18006507d  jnz     loc_18006522C
0x180065083  test    r14d, r14d
0x180065086  mov     ebx, r14d
0x180065089  cmovns  ebx, r15d
0x18006508d  test    ebx, ebx
0x18006508f  jns     loc_180065290
0x180065095  cmp     ebx, r15d
0x180065098  jz      loc_180065472
0x18006509e  test    ebx, ebx
0x1800650a0  jns     loc_180065475
0x1800650a6  mov     eax, cs:dword_1801574B8
0x1800650ac  test    eax, eax
0x1800650ae  jnz     short loc_1800650CC
0x1800650b0  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800650b7  jz      loc_180065475
0x1800650bd  xor     ecx, ecx
0x1800650bf  call    IsWppLevelEnabled
0x1800650c4  test    al, al
0x1800650c6  jz      loc_180065475
0x1800650cc  lea     rax, [rdi+70h]
0x1800650d0  mov     dword ptr [rsp+68h+var_38], ebx
0x1800650d4  mov     [rsp+68h+var_40], rax
0x1800650d9  mov     r8d, 398h
0x1800650df  lea     rax, aClsidWsHresult; "CLSID:%ws %!HRESULT!"
0x1800650e6  jmp     loc_180065270
0x1800650eb  mov     eax, cs:dword_1801574B8
0x1800650f1  mov     r14d, 80004023h
0x1800650f7  cmp     ebx, r14d
0x1800650fa  jz      short loc_18006515B
0x1800650fc  test    eax, eax
0x1800650fe  jnz     short loc_18006511C
0x180065100  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x180065107  jz      loc_180065475
0x18006510d  xor     ecx, ecx
0x18006510f  call    IsWppLevelEnabled
0x180065114  test    al, al
0x180065116  jz      loc_180065475
0x18006511c  lea     rax, [rdi+70h]
0x180065120  mov     dword ptr [rsp+68h+var_30], ebx
0x180065124  mov     [rsp+68h+var_38], r12
0x180065129  xor     r9d, r9d
0x18006512c  mov     [rsp+68h+var_40], rax
0x180065131  mov     r8d, 325h
0x180065137  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x18006513e  lea     rdx, aCcomclassinfoI_4; "CComClassInfo::InitializeLocalServer"
0x180065145  mov     [rsp+68h+phkResult], rax
0x18006514a  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x180065151  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x180065156  jmp     loc_180065475
0x18006515b  test    eax, eax
0x18006515d  jnz     short loc_18006517B
0x18006515f  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x180065166  jz      loc_18006504C
0x18006516c  xor     ecx, ecx
0x18006516e  call    IsWppLevelEnabled
0x180065173  test    al, al
0x180065175  jz      loc_18006504C
0x18006517b  mov     dword ptr [rsp+68h+var_30], r14d
0x180065180  lea     rax, [rdi+70h]
0x180065184  mov     [rsp+68h+var_38], r12
0x180065189  lea     rdx, aCcomclassinfoI_4; "CComClassInfo::InitializeLocalServer"
0x180065190  mov     [rsp+68h+var_40], rax
0x180065195  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x18006519c  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x1800651a3  xor     r9d, r9d
0x1800651a6  mov     r8d, 32Bh
0x1800651ac  mov     [rsp+68h+phkResult], rax
0x1800651b1  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x1800651b6  jmp     loc_18006504C
0x1800651bb  mov     r15d, 80070002h
0x1800651c1  cmp     ebx, r15d
0x1800651c4  jz      loc_180065052
0x1800651ca  mov     eax, cs:dword_1801574B8
0x1800651d0  test    eax, eax
0x1800651d2  jnz     short loc_1800651F0
0x1800651d4  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800651db  jz      loc_180065475
0x1800651e1  xor     ecx, ecx
0x1800651e3  call    IsWppLevelEnabled
0x1800651e8  test    al, al
0x1800651ea  jz      loc_180065475
0x1800651f0  mov     dword ptr [rsp+68h+var_30], ebx
0x1800651f4  mov     r8d, 338h
0x1800651fa  mov     [rsp+68h+var_38], rsi
0x1800651ff  lea     rax, [rdi+70h]
0x180065203  mov     [rsp+68h+var_40], rax
0x180065208  lea     rdx, aCcomclassinfoI_4; "CComClassInfo::InitializeLocalServer"
0x18006520f  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x180065216  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x18006521d  mov     [rsp+68h+phkResult], rax
0x180065222  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x180065227  jmp     loc_180065475
0x18006522c  test    ebx, ebx
0x18006522e  jns     short loc_180065290
0x180065230  mov     eax, cs:dword_1801574B8
0x180065236  test    eax, eax
0x180065238  jnz     short loc_180065256
0x18006523a  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x180065241  jz      loc_180065475
0x180065247  xor     ecx, ecx
0x180065249  call    IsWppLevelEnabled
0x18006524e  test    al, al
0x180065250  jz      loc_180065475
0x180065256  lea     rax, [rdi+70h]
0x18006525a  mov     dword ptr [rsp+68h+var_38], ebx
0x18006525e  mov     [rsp+68h+var_40], rax
0x180065263  mov     r8d, 34Ch
0x180065269  lea     rax, aClsidWsValueHr; "CLSID:%ws Value:%!HRESULT!"
0x180065270  xor     r9d, r9d
0x180065273  mov     [rsp+68h+phkResult], rax
0x180065278  lea     rdx, aCcomclassinfoI_4; "CComClassInfo::InitializeLocalServer"
0x18006527f  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x180065286  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x18006528b  jmp     loc_180065475
0x180065290  mov     rcx, [rbp+hKey]; hkey
0x180065294  lea     rax, [rdi+128h]
0x18006529b  lea     r14, ?ServerExecutable@Constants@Catalog@Com@@3QBGB; "ServerExecutable"
0x1800652a2  mov     [rsp+68h+phkResult], rax; unsigned __int16 **
0x1800652a7  mov     r8, r14; lpValue
0x1800652aa  xor     r9d, r9d; unsigned int
0x1800652ad  xor     edx, edx; lpSubKey
0x1800652af  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x1800652b4  cmp     eax, r15d
0x1800652b7  mov     ebx, r12d
0x1800652ba  cmovnz  ebx, eax
0x1800652bd  test    ebx, ebx
0x1800652bf  jns     short loc_1800652FB
0x1800652c1  mov     eax, cs:dword_1801574B8
0x1800652c7  test    eax, eax
0x1800652c9  jnz     short loc_1800652E7
0x1800652cb  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800652d2  jz      loc_180065475
0x1800652d8  xor     ecx, ecx
0x1800652da  call    IsWppLevelEnabled
0x1800652df  test    al, al
0x1800652e1  jz      loc_180065475
0x1800652e7  mov     dword ptr [rsp+68h+var_30], ebx
0x1800652eb  mov     r8d, 35Fh
0x1800652f1  mov     [rsp+68h+var_38], r14
0x1800652f6  jmp     loc_1800651FF
0x1800652fb  mov     rdx, [rsi]; unsigned __int16 *
0x1800652fe  test    rdx, rdx
0x180065301  jz      loc_180065475
0x180065307  lea     r8, [rdi+130h]; unsigned int *
0x18006530e  call    ?GetExeArchitectureFromRegString@CComClassInfo@@AEAAJPEBGPEAK@Z; CComClassInfo::GetExeArchitectureFromRegString(ushort const *,ulong *)
0x180065313  mov     ebx, eax
0x180065315  test    eax, eax
0x180065317  js      short loc_180065395
0x180065319  movzx   edx, [rbp+arg_20]; unsigned int
0x18006531d  mov     rcx, rdi; this
0x180065320  call    ?IsBinaryArchitectureExpectedForView@CComClassInfo@@AEBA_NK@Z; CComClassInfo::IsBinaryArchitectureExpectedForView(ulong)
0x180065325  test    al, al
0x180065327  jnz     short loc_180065385
0x180065329  mov     eax, cs:dword_1801574B8
0x18006532f  test    eax, eax
0x180065331  jnz     short loc_180065348
0x180065333  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x18006533a  jz      short loc_180065385
0x18006533c  mov     ecx, r13d
0x18006533f  call    IsWppLevelEnabled
0x180065344  test    al, al
0x180065346  jz      short loc_180065385
0x180065348  mov     rax, [rsi]
0x18006534b  lea     rcx, [rdi+70h]
0x18006534f  mov     dword ptr [rsp+68h+var_30], ebx
0x180065353  lea     rdx, aCcomclassinfoI_4; "CComClassInfo::InitializeLocalServer"
0x18006535a  mov     [rsp+68h+var_38], rax
0x18006535f  mov     r9d, r13d
0x180065362  mov     [rsp+68h+var_40], rcx
0x180065367  lea     rax, aClsidWsBinaryA_0; "CLSID:%ws Binary architecture doesn't m"...
0x18006536e  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x180065375  mov     [rsp+68h+phkResult], rax
0x18006537a  mov     r8d, 373h
0x180065380  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x180065385  or      dword ptr [rdi+0E0h], 4
0x18006538c  mov     [rdi+60h], r13d
0x180065390  jmp     loc_180065472
0x180065395  add     eax, 7FF8FFFEh
0x18006539a  cmp     eax, r13d
0x18006539d  mov     eax, cs:dword_1801574B8
0x1800653a3  jbe     short loc_1800653F0
0x1800653a5  test    eax, eax
0x1800653a7  jnz     short loc_1800653C6
0x1800653a9  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800653b0  jz      loc_180065475
0x1800653b6  mov     ecx, r13d
0x1800653b9  call    IsWppLevelEnabled
0x1800653be  test    al, al
0x1800653c0  jz      loc_180065475
0x1800653c6  mov     rax, [rsi]
0x1800653c9  lea     rcx, [rdi+70h]
0x1800653cd  mov     dword ptr [rsp+68h+var_30], ebx
0x1800653d1  mov     r9d, r13d
0x1800653d4  mov     [rsp+68h+var_38], rax
0x1800653d9  mov     r8d, 384h
0x1800653df  mov     [rsp+68h+var_40], rcx
0x1800653e4  lea     rax, aClsidWsUnableT; "CLSID:%ws Unable to determine server ar"...
0x1800653eb  jmp     loc_18006513E
0x1800653f0  test    eax, eax
0x1800653f2  jnz     short loc_180065409
0x1800653f4  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800653fb  jz      short loc_180065446
0x1800653fd  mov     ecx, r13d
0x180065400  call    IsWppLevelEnabled
0x180065405  test    al, al
0x180065407  jz      short loc_180065446
0x180065409  mov     rax, [rsi]
0x18006540c  lea     rcx, [rdi+70h]
0x180065410  mov     dword ptr [rsp+68h+var_30], ebx
0x180065414  lea     rdx, aCcomclassinfoI_4; "CComClassInfo::InitializeLocalServer"
0x18006541b  mov     [rsp+68h+var_38], rax
0x180065420  mov     r9d, r13d
0x180065423  mov     [rsp+68h+var_40], rcx
0x180065428  lea     rax, aClsidWsFilenot; "CLSID:%ws FileNotFound on server archit"...
0x18006542f  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x180065436  mov     [rsp+68h+phkResult], rax
  ... truncated ...
```

# CPerfCounterServer::CleanupNames(void)

- ea: `0x18001aad8`
- end: `0x18001af59`
- name: `?CleanupNames@CPerfCounterServer@@AEAAJXZ`
- size: `1153`
- prototype: `__int64 __fastcall(CPerfCounterServer *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x18001b4d0`

## callees

- `0x18001aad8`
- `0x18001c104`
- `0x18004d030`
- `0x18004d350`
- `0x18004d690`
- `0x18004d6c8`
- `0x18004d754`
- `0x18004e638`
- `0x18004e650`
- `0x18004f330`
- `0x18004f62c`
- `0x180065b60`

## import_xrefs

- `KERNEL32!FindClose` at `0x18001aecd`
- `KERNEL32!FindClose` at `0x18001aecd`
- `KERNEL32!FindFirstFileExW` at `0x18001ab7f`
- `KERNEL32!FindFirstFileExW` at `0x18001ab7f`
- `KERNEL32!FindNextFileW` at `0x18001ac3e`
- `KERNEL32!FindNextFileW` at `0x18001ac3e`
- `ADVAPI32!RegCloseKey` at `0x18001aebb`
- `ADVAPI32!RegCloseKey` at `0x18001aebb`
- `ADVAPI32!RegOpenKeyExW` at `0x18001ac6d`
- `ADVAPI32!RegOpenKeyExW` at `0x18001ac6d`
- `ADVAPI32!RegDeleteValueW` at `0x18001ae77`
- `ADVAPI32!RegDeleteValueW` at `0x18001ae77`
- `ADVAPI32!RegEnumValueW` at `0x18001acbc`
- `ADVAPI32!RegEnumValueW` at `0x18001ae40`
- `ADVAPI32!RegEnumValueW` at `0x18001acbc`
- `ADVAPI32!RegEnumValueW` at `0x18001ae40`

## string_xrefs

- `0x18001ac5f`: `SYSTEM\CurrentControlSet\Services\ASP.NET_4.0.30319\Names`

## pseudocode

```c
__int64 __fastcall CPerfCounterServer::CleanupNames(CPerfCounterServer *this)
{
  __int64 FirstFile; // r15
  Hashtable *v2; // rax
  Hashtable *v3; // rdi
  unsigned int LastWin32Error; // ebx
  int v5; // r8d
  int v6; // r9d
  __int64 v7; // rdx
  char v8; // cl
  LSTATUS i; // eax
  DWORD v10; // r14d
  int v11; // r9d
  __int64 v12; // rdx
  int v13; // r8d
  char v14; // cl
  _WORD *v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r9
  _WORD *v18; // rcx
  __int16 v19; // ax
  _WORD *v20; // rax
  signed int v21; // esi
  __int64 v22; // r14
  LSTATUS v23; // eax
  signed int v24; // r14d
  __int64 v25; // rsi
  DWORD cchValueName[2]; // [rsp+48h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B8h] BYREF
  HKEY phkResult_8[2]; // [rsp+58h] [rbp-B0h] BYREF
  void *v30; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v31; // [rsp+70h] [rbp-98h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+78h] [rbp-90h] BYREF
  WCHAR ValueName[264]; // [rsp+2C8h] [rbp+1C0h] BYREF
  unsigned __int16 v34[264]; // [rsp+4D8h] [rbp+3D0h] BYREF

  FirstFile = -1;
  phkResult = 0;
  *(_OWORD *)phkResult_8 = 0;
  v2 = (Hashtable *)MemAllocClear(0x38u);
  v3 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &HashtableGeneric::`vftable';
    *((_QWORD *)v2 + 6) = HashtableGeneric::EnumerateCallback;
    LastWin32Error = Hashtable::Init(v2, 13);
    if ( LastWin32Error )
      goto LABEL_48;
    FirstFile = (__int64)FindFirstFileExW(
                           L"\\\\.\\pipe\\*",
                           FindExInfoStandard,
                           &FindFileData,
                           FindExSearchNameMatch,
                           0,
                           0);
    if ( FirstFile == -1 )
    {
      LastWin32Error = GetLastWin32Error();
      goto LABEL_48;
    }
    while ( 1 )
    {
      LastWin32Error = StringCchCopyNExW(v34, 0x104u, FindFileData.cFileName, 0x103u, 0, &v31, 0);
      if ( LastWin32Error )
        break;
      v5 = 2 * (261 - v31);
      if ( v5 <= 0 )
      {
        LastWin32Error = -2147024809;
        break;
      }
      v6 = 0;
      v7 = 0;
      do
      {
        v8 = *((_BYTE *)v34 + v7++);
        v6 = (v8 & 0xDF) + 37 * v6;
      }
      while ( v7 < v5 );
      LastWin32Error = Hashtable::DoAction(v3, (unsigned __int8 *)v34, v5, v6, v3, 0, 0);
      if ( LastWin32Error )
        break;
      if ( !FindNextFileW((HANDLE)FirstFile, &FindFileData) )
      {
        i = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"SYSTEM\\CurrentControlSet\\Services\\ASP.NET_4.0.30319\\Names",
              0,
              0x2001Fu,
              &phkResult);
        if ( i )
        {
LABEL_12:
          LastWin32Error = (unsigned __int16)i | 0x80070000;
          if ( i <= 0 )
            LastWin32Error = i;
          break;
        }
        v10 = 0;
        cchValueName[0] = 259;
        for ( i = RegEnumValueW(phkResult, 0, ValueName, cchValueName, 0, 0, 0, 0);
              ;
              i = RegEnumValueW(phkResult, v10, ValueName, cchValueName, 0, 0, 0, 0) )
        {
          ValueName[259] = 0;
          if ( i )
          {
            if ( i == 259 )
            {
              v21 = 0;
              if ( ((__int64)phkResult_8[0] & 0xFFFFFFFC) != 0 )
              {
                v22 = 0;
                do
                {
                  v23 = RegDeleteValueW(phkResult, *(LPCWSTR *)((char *)phkResult_8[1] + v22));
                  if ( v23 )
                  {
                    LastWin32Error = (unsigned __int16)v23 | 0x80070000;
                    if ( v23 <= 0 )
                      LastWin32Error = v23;
                  }
                  ++v21;
                  v22 += 8;
                }
                while ( v21 < (signed int)(LODWORD(phkResult_8[0]) >> 2) );
              }
              goto LABEL_48;
            }
            if ( i != 234 )
              goto LABEL_12;
          }
          else
          {
            v11 = 0;
            v30 = 0;
            v12 = 0;
            v13 = 2 * cchValueName[0] + 2;
            if ( v13 > 0 )
            {
              do
              {
                v14 = *((_BYTE *)ValueName + v12++);
                v11 = (v14 & 0xDF) + 37 * v11;
              }
              while ( v12 < v13 );
            }
            Hashtable::DoAction(v3, (unsigned __int8 *)ValueName, v13, v11, 0, 0, &v30);
            if ( !v30 )
            {
              v15 = MemAlloc(saturated_mul(cchValueName[0] + 1, 2u));
              if ( !v15 )
                goto LABEL_47;
              v16 = cchValueName[0] + 1;
              if ( (unsigned __int64)(v16 - 1) > 0x7FFFFFFE )
              {
                LastWin32Error = -2147024809;
                if ( cchValueName[0] != -1 )
                {
                  *v15 = 0;
                  goto LABEL_48;
                }
              }
              else
              {
                if ( cchValueName[0] > 0x7FFFFFFEuLL )
                {
                  *v15 = 0;
                  LastWin32Error = -2147024809;
                  goto LABEL_48;
                }
                v17 = cchValueName[0] - v16;
                v18 = v15;
                do
                {
                  if ( !(v17 + v16) )
                    break;
                  v19 = *(_WORD *)((char *)v18 + (char *)ValueName - (char *)v15);
                  if ( !v19 )
                    break;
                  *v18++ = v19;
                  --v16;
                }
                while ( v16 );
                v20 = v18 - 1;
                if ( v16 )
                  v20 = v18;
                LastWin32Error = v16 == 0 ? 0x8007007A : 0;
                *v20 = 0;
              }
              if ( LastWin32Error )
                goto LABEL_48;
              CImplPtrAry::Append((CImplPtrAry *)phkResult_8, v15);
            }
          }
          ++v10;
          cchValueName[0] = 259;
        }
      }
    }
  }
  else
  {
    v3 = 0;
LABEL_47:
    LastWin32Error = -2147024882;
  }
LABEL_48:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( FirstFile != -1 )
    FindClose((HANDLE)FirstFile);
  v24 = 0;
  if ( ((__int64)phkResult_8[0] & 0xFFFFFFFC) != 0 )
  {
    v25 = 0;
    do
    {
      MemFree(*(void **)((char *)phkResult_8[1] + v25));
      v25 += 8;
      ++v24;
    }
    while ( v24 < (signed int)(LODWORD(phkResult_8[0]) >> 2) );
  }
  if ( v3 )
    (**(void (__fastcall ***)(Hashtable *, __int64))v3)(v3, 1);
  CImplAry::~CImplAry((CImplAry *)phkResult_8);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18001aad8  mov     rax, rsp
0x18001aadb  mov     [rax+8], rbx
0x18001aadf  mov     [rax+10h], rsi
0x18001aae3  mov     [rax+18h], rdi
0x18001aae7  mov     [rax+20h], r12
0x18001aaeb  push    rbp
0x18001aaec  push    r14
0x18001aaee  push    r15
0x18001aaf0  lea     rbp, [rax-608h]
0x18001aaf7  sub     rsp, 6F0h
0x18001aafe  mov     rax, cs:__security_cookie
0x18001ab05  xor     rax, rsp
0x18001ab08  mov     [rbp+600h+var_20], rax
0x18001ab0f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001ab13  xorps   xmm0, xmm0
0x18001ab16  xor     r12d, r12d
0x18001ab19  mov     r15, rsi
0x18001ab1c  mov     [rsp+700h+phkResult], r12
0x18001ab21  movups  xmmword ptr [rsp+700h+phkResult+8], xmm0
0x18001ab26  lea     ecx, [rsi+39h]; unsigned __int64
0x18001ab29  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x18001ab2e  mov     rdi, rax
0x18001ab31  test    rax, rax
0x18001ab34  jz      loc_18001AEA9
0x18001ab3a  lea     rax, ??_7HashtableGeneric@@6B@; const HashtableGeneric::`vftable'
0x18001ab41  mov     rcx, rdi; this
0x18001ab44  mov     [rdi], rax
0x18001ab47  lea     edx, [rsi+0Eh]; int
0x18001ab4a  lea     rax, ?EnumerateCallback@HashtableGeneric@@CAXPEAX00@Z; HashtableGeneric::EnumerateCallback(void *,void *,void *)
0x18001ab51  mov     [rdi+30h], rax
0x18001ab55  call    ?Init@Hashtable@@QEAAJH@Z; Hashtable::Init(int)
0x18001ab5a  mov     ebx, eax
0x18001ab5c  test    eax, eax
0x18001ab5e  jnz     loc_18001AEB1
0x18001ab64  mov     [rsp+700h+dwAdditionalFlags], r12d; dwAdditionalFlags
0x18001ab69  lea     r8, [rsp+700h+FindFileData]; lpFindFileData
0x18001ab6e  xor     r9d, r9d; fSearchOp
0x18001ab71  mov     [rsp+700h+lpSearchFilter], r12; lpSearchFilter
0x18001ab76  xor     edx, edx; fInfoLevelId
0x18001ab78  lea     rcx, FileName; "\\\\.\\pipe\\*"
0x18001ab7f  call    cs:__imp_FindFirstFileExW
0x18001ab85  mov     r15, rax
0x18001ab88  cmp     rax, rsi
0x18001ab8b  jnz     short loc_18001AB99
0x18001ab8d  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001ab92  mov     ebx, eax
0x18001ab94  jmp     loc_18001AEB1
0x18001ab99  mov     r9d, 103h; unsigned __int64
0x18001ab9f  mov     dword ptr [rsp+700h+lpData], r12d; unsigned int
0x18001aba4  lea     rax, [rsp+700h+var_698]
0x18001aba9  mov     qword ptr [rsp+700h+dwAdditionalFlags], rax; unsigned __int64 *
0x18001abae  lea     r8, [rbp+600h+var_664]; unsigned __int16 *
0x18001abb2  lea     rcx, [rbp+600h+var_230]; unsigned __int16 *
0x18001abb9  mov     [rsp+700h+lpSearchFilter], r12; unsigned __int16 **
0x18001abbe  lea     edx, [r9+1]; unsigned __int64
0x18001abc2  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18001abc7  mov     ebx, eax
0x18001abc9  test    eax, eax
0x18001abcb  jnz     loc_18001AEB1
0x18001abd1  mov     r8d, 105h
0x18001abd7  sub     r8d, dword ptr [rsp+700h+var_698]
0x18001abdc  add     r8d, r8d; int
0x18001abdf  test    r8d, r8d
0x18001abe2  jle     loc_18001AEA2
0x18001abe8  mov     r9d, r12d
0x18001abeb  movsxd  r10, r8d
0x18001abee  mov     rdx, r12
0x18001abf1  movzx   ecx, byte ptr [rbp+rdx+600h+var_230]
0x18001abf9  inc     rdx
0x18001abfc  imul    r9d, 25h ; '%'
0x18001ac00  and     ecx, 0DFh
0x18001ac06  add     r9d, ecx; int
0x18001ac09  cmp     rdx, r10
0x18001ac0c  jl      short loc_18001ABF1
0x18001ac0e  mov     [rsp+700h+lpData], r12; void **
0x18001ac13  lea     rdx, [rbp+600h+var_230]; unsigned __int8 *
0x18001ac1a  mov     [rsp+700h+dwAdditionalFlags], r12d; int
0x18001ac1f  mov     rcx, rdi; this
0x18001ac22  mov     [rsp+700h+lpSearchFilter], rdi; void *
0x18001ac27  call    ?DoAction@Hashtable@@IEAAJPEAEHJPEAXHPEAPEAX@Z; Hashtable::DoAction(uchar *,int,long,void *,int,void * *)
0x18001ac2c  mov     ebx, eax
0x18001ac2e  test    eax, eax
0x18001ac30  jnz     loc_18001AEB1
0x18001ac36  lea     rdx, [rsp+700h+FindFileData]; lpFindFileData
0x18001ac3b  mov     rcx, r15; hFindFile
0x18001ac3e  call    cs:__imp_FindNextFileW
0x18001ac44  test    eax, eax
0x18001ac46  jnz     loc_18001AB99
0x18001ac4c  lea     rax, [rsp+700h+phkResult]
0x18001ac51  mov     r9d, 2001Fh; samDesired
0x18001ac57  xor     r8d, r8d; ulOptions
0x18001ac5a  mov     [rsp+700h+lpSearchFilter], rax; phkResult
0x18001ac5f  lea     rdx, aSystemCurrentc_8; "SYSTEM\\CurrentControlSet\\Services\\AS"...
0x18001ac66  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ac6d  call    cs:__imp_RegOpenKeyExW
0x18001ac73  test    eax, eax
0x18001ac75  jz      short loc_18001AC8A
0x18001ac77  movzx   ebx, ax
0x18001ac7a  or      ebx, 80070000h
0x18001ac80  test    eax, eax
0x18001ac82  cmovle  ebx, eax
0x18001ac85  jmp     loc_18001AEB1
0x18001ac8a  mov     rcx, [rsp+700h+phkResult]; hKey
0x18001ac8f  lea     r9, [rsp+700h+cchValueName]; lpcchValueName
0x18001ac94  mov     [rsp+700h+lpcbData], r12; lpcbData
0x18001ac99  lea     r8, [rbp+600h+ValueName]; lpValueName
0x18001aca0  mov     [rsp+700h+lpData], r12; lpData
0x18001aca5  xor     edx, edx; dwIndex
0x18001aca7  mov     qword ptr [rsp+700h+dwAdditionalFlags], r12; lpType
0x18001acac  mov     r14d, r12d
0x18001acaf  mov     [rsp+700h+lpSearchFilter], r12; lpReserved
0x18001acb4  mov     [rsp+700h+cchValueName], 103h
0x18001acbc  call    cs:__imp_RegEnumValueW
0x18001acc2  mov     esi, 80070057h
0x18001acc7  mov     [rbp+600h+var_23A], r12w
0x18001accf  test    eax, eax
0x18001acd1  jnz     loc_18001ADFB
0x18001acd7  mov     eax, [rsp+700h+cchValueName]
0x18001acdb  mov     r9d, r12d
0x18001acde  mov     [rsp+700h+var_6A0], r12
0x18001ace3  mov     rdx, r12
0x18001ace6  lea     r8d, ds:2[rax*2]; int
0x18001acee  movsxd  r10, r8d
0x18001acf1  test    r8d, r8d
0x18001acf4  jle     short loc_18001AD13
0x18001acf6  movzx   ecx, byte ptr [rbp+rdx+600h+ValueName]
0x18001acfe  inc     rdx
0x18001ad01  imul    r9d, 25h ; '%'
0x18001ad05  and     ecx, 0DFh
0x18001ad0b  add     r9d, ecx; int
0x18001ad0e  cmp     rdx, r10
0x18001ad11  jl      short loc_18001ACF6
0x18001ad13  lea     rax, [rsp+700h+var_6A0]
0x18001ad18  mov     rcx, rdi; this
0x18001ad1b  mov     [rsp+700h+lpData], rax; void **
0x18001ad20  lea     rdx, [rbp+600h+ValueName]; unsigned __int8 *
0x18001ad27  mov     [rsp+700h+dwAdditionalFlags], r12d; int
0x18001ad2c  mov     [rsp+700h+lpSearchFilter], r12; void *
0x18001ad31  call    ?DoAction@Hashtable@@IEAAJPEAEHJPEAXHPEAPEAX@Z; Hashtable::DoAction(uchar *,int,long,void *,int,void * *)
0x18001ad36  cmp     [rsp+700h+var_6A0], r12
0x18001ad3b  jnz     loc_18001AE0D
0x18001ad41  mov     ecx, [rsp+700h+cchValueName]
0x18001ad45  mov     eax, 2
0x18001ad4a  inc     ecx
0x18001ad4c  mul     rcx
0x18001ad4f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001ad56  cmovo   rax, rcx
0x18001ad5a  mov     rcx, rax; unsigned __int64
0x18001ad5d  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18001ad62  mov     r8, rax
0x18001ad65  test    rax, rax
0x18001ad68  jz      loc_18001AEAC
0x18001ad6e  mov     ecx, [rsp+700h+cchValueName]
0x18001ad72  mov     eax, 7FFFFFFEh
0x18001ad77  mov     r9d, ecx
0x18001ad7a  inc     ecx
0x18001ad7c  mov     edx, ecx
0x18001ad7e  dec     rcx
0x18001ad81  cmp     rcx, rax
0x18001ad84  ja      short loc_18001ADDD
0x18001ad86  cmp     r9, rax
0x18001ad89  ja      loc_18001AE4B
0x18001ad8f  sub     r9, rdx
0x18001ad92  lea     r10, [rbp+600h+ValueName]
0x18001ad99  sub     r10, r8
0x18001ad9c  mov     rcx, r8
0x18001ad9f  lea     rax, [r9+rdx]
0x18001ada3  test    rax, rax
0x18001ada6  jz      short loc_18001ADBF
0x18001ada8  movzx   eax, word ptr [r10+rcx]
0x18001adad  test    ax, ax
0x18001adb0  jz      short loc_18001ADBF
0x18001adb2  mov     [rcx], ax
0x18001adb5  add     rcx, 2
0x18001adb9  sub     rdx, 1
0x18001adbd  jnz     short loc_18001AD9F
0x18001adbf  test    rdx, rdx
0x18001adc2  lea     rax, [rcx-2]
0x18001adc6  cmovnz  rax, rcx
0x18001adca  neg     rdx
0x18001adcd  sbb     ebx, ebx
0x18001adcf  not     ebx
0x18001add1  and     ebx, 8007007Ah
0x18001add7  mov     [rax], r12w
0x18001addb  jmp     short loc_18001ADE4
0x18001addd  mov     ebx, esi
0x18001addf  test    rdx, rdx
0x18001ade2  jnz     short loc_18001AE53
0x18001ade4  test    ebx, ebx
0x18001ade6  jnz     loc_18001AEB1
0x18001adec  mov     rdx, r8; void *
0x18001adef  lea     rcx, [rsp+700h+phkResult+8]; this
0x18001adf4  call    ?Append@CImplPtrAry@@IEAAJPEAX@Z; CImplPtrAry::Append(void *)
0x18001adf9  jmp     short loc_18001AE0D
0x18001adfb  cmp     eax, 103h
0x18001ae00  jz      short loc_18001AE59
0x18001ae02  cmp     eax, 0EAh
0x18001ae07  jnz     loc_18001AC77
0x18001ae0d  mov     rcx, [rsp+700h+phkResult]; hKey
0x18001ae12  lea     r9, [rsp+700h+cchValueName]; lpcchValueName
0x18001ae17  mov     [rsp+700h+lpcbData], r12; lpcbData
0x18001ae1c  lea     r8, [rbp+600h+ValueName]; lpValueName
0x18001ae23  inc     r14d
0x18001ae26  mov     [rsp+700h+lpData], r12; lpData
0x18001ae2b  mov     qword ptr [rsp+700h+dwAdditionalFlags], r12; lpType
0x18001ae30  mov     edx, r14d; dwIndex
0x18001ae33  mov     [rsp+700h+lpSearchFilter], r12; lpReserved
0x18001ae38  mov     [rsp+700h+cchValueName], 103h
0x18001ae40  call    cs:__imp_RegEnumValueW
0x18001ae46  jmp     loc_18001ACC7
0x18001ae4b  mov     [r8], r12w
0x18001ae4f  mov     ebx, esi
0x18001ae51  jmp     short loc_18001AEB1
0x18001ae53  mov     [r8], r12w
0x18001ae57  jmp     short loc_18001AEB1
0x18001ae59  test    dword ptr [rsp+700h+phkResult+8], 0FFFFFFFCh
0x18001ae61  mov     esi, r12d
0x18001ae64  jbe     short loc_18001AEB1
0x18001ae66  mov     r14, r12
0x18001ae69  mov     rdx, [rsp+700h+var_6A8]
0x18001ae6e  mov     rcx, [rsp+700h+phkResult]; hKey
0x18001ae73  mov     rdx, [r14+rdx]; lpValueName
0x18001ae77  call    cs:__imp_RegDeleteValueW
0x18001ae7d  test    eax, eax
0x18001ae7f  jz      short loc_18001AE8F
0x18001ae81  movzx   ebx, ax
0x18001ae84  or      ebx, 80070000h
0x18001ae8a  test    eax, eax
0x18001ae8c  cmovle  ebx, eax
0x18001ae8f  mov     eax, dword ptr [rsp+700h+phkResult+8]
0x18001ae93  inc     esi
0x18001ae95  shr     eax, 2
0x18001ae98  add     r14, 8
0x18001ae9c  cmp     esi, eax
0x18001ae9e  jl      short loc_18001AE69
0x18001aea0  jmp     short loc_18001AEB1
0x18001aea2  mov     ebx, 80070057h
0x18001aea7  jmp     short loc_18001AEB1
0x18001aea9  mov     rdi, r12
0x18001aeac  mov     ebx, 8007000Eh
0x18001aeb1  mov     rcx, [rsp+700h+phkResult]; hKey
0x18001aeb6  test    rcx, rcx
0x18001aeb9  jz      short loc_18001AEC1
0x18001aebb  call    cs:__imp_RegCloseKey
0x18001aec1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001aec5  cmp     r15, rax
0x18001aec8  jz      short loc_18001AED3
0x18001aeca  mov     rcx, r15; hFindFile
0x18001aecd  call    cs:__imp_FindClose
0x18001aed3  test    dword ptr [rsp+700h+phkResult+8], 0FFFFFFFCh
0x18001aedb  mov     r14d, r12d
0x18001aede  jbe     short loc_18001AF04
0x18001aee0  mov     rsi, r12
0x18001aee3  mov     rcx, [rsp+700h+var_6A8]
0x18001aee8  mov     rcx, [rsi+rcx]; lpMem
0x18001aeec  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001aef1  mov     eax, dword ptr [rsp+700h+phkResult+8]
0x18001aef5  lea     rsi, [rsi+8]
0x18001aef9  shr     eax, 2
0x18001aefc  inc     r14d
0x18001aeff  cmp     r14d, eax
0x18001af02  jl      short loc_18001AEE3
0x18001af04  test    rdi, rdi
0x18001af07  jz      short loc_18001AF1D
0x18001af09  mov     rax, [rdi]
0x18001af0c  mov     edx, 1
0x18001af11  mov     rcx, rdi
0x18001af14  mov     rax, [rax]
0x18001af17  call    cs:__guard_dispatch_icall_fptr
0x18001af1d  lea     rcx, [rsp+700h+phkResult+8]; this
0x18001af22  call    ??1CImplAry@@QEAA@XZ; CImplAry::~CImplAry(void)
0x18001af27  mov     eax, ebx
0x18001af29  mov     rcx, [rbp+600h+var_20]
0x18001af30  xor     rcx, rsp; StackCookie
0x18001af33  call    __security_check_cookie
0x18001af38  lea     r11, [rsp+700h+var_10]
0x18001af40  mov     rbx, [r11+20h]
0x18001af44  mov     rsi, [r11+28h]
0x18001af48  mov     rdi, [r11+30h]
0x18001af4c  mov     r12, [r11+38h]
0x18001af50  mov     rsp, r11
0x18001af53  pop     r15
0x18001af55  pop     r14
0x18001af57  pop     rbp
0x18001af58  retn
```

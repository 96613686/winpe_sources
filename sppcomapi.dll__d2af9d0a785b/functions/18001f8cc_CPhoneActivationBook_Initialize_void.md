# CPhoneActivationBook::Initialize(void)

- ea: `0x18001f8cc`
- end: `0x18001fa6a`
- name: `?Initialize@CPhoneActivationBook@@QEAAJXZ`
- size: `414`
- prototype: `__int64 __fastcall(CPhoneActivationBook *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18001b864`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001d860`
- `0x18001f2a0`
- `0x18001f8cc`
- `0x180020620`
- `0x18002085c`
- `0x18003c560`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fa23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fa23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fa38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fa38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f919`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f919`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001f909`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001f909`

## pseudocode

```c
__int64 __fastcall CPhoneActivationBook::Initialize(CPhoneActivationBook *this)
{
  unsigned __int16 *v2; // rbx
  unsigned __int64 v3; // rdx
  signed int LastError; // eax
  unsigned int v5; // edi
  __int64 v6; // rcx
  int v7; // eax
  unsigned __int64 v8; // rdx
  __int64 v9; // rcx
  int PhoneList; // eax
  __int64 v11; // rcx
  CPhoneActivationBook *v12; // rcx
  int DefaultTapiCountryCode; // eax
  int v14; // r8d
  int v15; // edx
  char *v16; // rax
  char *v17; // r10
  int v18; // r9d
  int v19; // ecx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v22; // [rsp+20h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-248h] BYREF

  v2 = 0;
  v22 = 0;
  CArray<SLUX_PhoneLocation,SLUX_PhoneLocation,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 8, 0);
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    v7 = StringCchCatW(Buffer, v3, L"\\SPPUI");
    v5 = v7;
    if ( v7 >= 0 )
      goto LABEL_10;
    v6 = (unsigned int)v7;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    v6 = v5;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
LABEL_10:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( (v5 & 0x80000000) != 0 )
  {
    v9 = v5;
LABEL_12:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
    goto LABEL_28;
  }
  PhoneList = StringCchCatW(Buffer, v8, L"\\Phone.inf");
  v5 = PhoneList;
  if ( PhoneList < 0
    || (PhoneList = CPhoneActivationBook::SetupReadPhoneList(v11, Buffer, (__int64)this + 8),
        v5 = PhoneList,
        PhoneList < 0) )
  {
    v9 = (unsigned int)PhoneList;
    goto LABEL_12;
  }
  *((_DWORD *)this + 6) = 0;
  DefaultTapiCountryCode = CPhoneActivationBook::GetDefaultTapiCountryCode(v12, Buffer, &v22);
  v2 = v22;
  if ( DefaultTapiCountryCode >= 0 )
  {
    v14 = 0;
    if ( *((_DWORD *)this + 3) )
    {
      v15 = 0;
      while ( 1 )
      {
        v16 = *(char **)(*((_QWORD *)this + 2) + 40LL * v15 + 32);
        if ( v16 )
        {
          v17 = (char *)((char *)v22 - v16);
          do
          {
            v18 = *(unsigned __int16 *)&v17[(_QWORD)v16];
            v19 = *(unsigned __int16 *)v16 - v18;
            if ( v19 )
              break;
            v16 += 2;
          }
          while ( v18 );
          if ( !v19 )
            break;
        }
        if ( (unsigned int)++v15 >= *((_DWORD *)this + 3) )
          goto LABEL_27;
      }
      v14 = v15;
    }
LABEL_27:
    *((_DWORD *)this + 6) = v14;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
LABEL_28:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v5;
}

```

## disassembly

```asm
0x18001f8cc  push    rbx
0x18001f8ce  push    rbp
0x18001f8cf  push    rsi
0x18001f8d0  push    rdi
0x18001f8d1  sub     rsp, 258h
0x18001f8d8  mov     rax, cs:__security_cookie
0x18001f8df  xor     rax, rsp
0x18001f8e2  mov     [rsp+278h+var_38], rax
0x18001f8ea  mov     rsi, rcx
0x18001f8ed  xor     ebx, ebx
0x18001f8ef  add     rcx, 8
0x18001f8f3  mov     [rsp+278h+var_258], rbx
0x18001f8f8  xor     edx, edx
0x18001f8fa  call    ?SetSize@?$CArray@USLUX_PhoneLocation@@U1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<SLUX_PhoneLocation,SLUX_PhoneLocation,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18001f8ff  mov     edx, 104h; uSize
0x18001f904  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x18001f909  call    cs:__imp_GetSystemDirectoryW
0x18001f910  nop     dword ptr [rax+rax+00h]
0x18001f915  test    eax, eax
0x18001f917  jnz     short loc_18001F941
0x18001f919  call    cs:__imp_GetLastError
0x18001f920  nop     dword ptr [rax+rax+00h]
0x18001f925  mov     edi, eax
0x18001f927  test    eax, eax
0x18001f929  jnz     short loc_18001F932
0x18001f92b  mov     edi, 80004005h
0x18001f930  jmp     short loc_18001F93D
0x18001f932  jle     short loc_18001F93D
0x18001f934  movzx   edi, ax
0x18001f937  or      edi, 80070000h
0x18001f93d  mov     ecx, edi
0x18001f93f  jmp     short loc_18001F95A
0x18001f941  lea     r8, aSppui; "\\SPPUI"
0x18001f948  lea     rcx, [rsp+278h+Buffer]; unsigned __int16 *
0x18001f94d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f952  mov     edi, eax
0x18001f954  test    eax, eax
0x18001f956  jns     short loc_18001F95F
0x18001f958  mov     ecx, eax
0x18001f95a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001f95f  mov     ecx, edi
0x18001f961  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001f966  test    edi, edi
0x18001f968  jns     short loc_18001F976
0x18001f96a  mov     ecx, edi
0x18001f96c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001f971  jmp     loc_18001FA17
0x18001f976  lea     r8, aPhoneInf; "\\Phone.inf"
0x18001f97d  lea     rcx, [rsp+278h+Buffer]; unsigned __int16 *
0x18001f982  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f987  mov     edi, eax
0x18001f989  test    eax, eax
0x18001f98b  jns     short loc_18001F991
0x18001f98d  mov     ecx, eax
0x18001f98f  jmp     short loc_18001F96C
0x18001f991  lea     r8, [rsi+8]
0x18001f995  lea     rdx, [rsp+278h+Buffer]
0x18001f99a  call    ?SetupReadPhoneList@CPhoneActivationBook@@AEAAJPEBGPEAV?$CArray@USLUX_PhoneLocation@@U1@VCAdaptorDefault@@VCPoliciesDefault@@@@@Z; CPhoneActivationBook::SetupReadPhoneList(ushort const *,CArray<SLUX_PhoneLocation,SLUX_PhoneLocation,CAdaptorDefault,CPoliciesDefault> *)
0x18001f99f  mov     edi, eax
0x18001f9a1  test    eax, eax
0x18001f9a3  js      short loc_18001F98D
0x18001f9a5  lea     r8, [rsp+278h+var_258]; unsigned __int16 **
0x18001f9aa  mov     [rsi+18h], ebx
0x18001f9ad  lea     rdx, [rsp+278h+Buffer]; unsigned __int16 *
0x18001f9b2  call    ?GetDefaultTapiCountryCode@CPhoneActivationBook@@AEAAJPEBGPEAPEAG@Z; CPhoneActivationBook::GetDefaultTapiCountryCode(ushort const *,ushort * *)
0x18001f9b7  mov     rbx, [rsp+278h+var_258]
0x18001f9bc  test    eax, eax
0x18001f9be  js      short loc_18001FA17
0x18001f9c0  xor     r8d, r8d
0x18001f9c3  cmp     [rsi+0Ch], r8d
0x18001f9c7  jbe     short loc_18001FA0C
0x18001f9c9  mov     r11, [rsi+10h]
0x18001f9cd  xor     edx, edx
0x18001f9cf  movsxd  rax, edx
0x18001f9d2  lea     rcx, [rax+rax*4]
0x18001f9d6  mov     rax, [r11+rcx*8+20h]
0x18001f9db  test    rax, rax
0x18001f9de  jz      short loc_18001FA00
0x18001f9e0  mov     r10, rbx
0x18001f9e3  sub     r10, rax
0x18001f9e6  movzx   ecx, word ptr [rax]
0x18001f9e9  movzx   r9d, word ptr [rax+r10]
0x18001f9ee  sub     ecx, r9d
0x18001f9f1  jnz     short loc_18001F9FC
0x18001f9f3  add     rax, 2
0x18001f9f7  test    r9d, r9d
0x18001f9fa  jnz     short loc_18001F9E6
0x18001f9fc  test    ecx, ecx
0x18001f9fe  jz      short loc_18001FA09
0x18001fa00  inc     edx
0x18001fa02  cmp     edx, [rsi+0Ch]
0x18001fa05  jb      short loc_18001F9CF
0x18001fa07  jmp     short loc_18001FA0C
0x18001fa09  mov     r8d, edx
0x18001fa0c  mov     [rsi+18h], r8d
0x18001fa10  xor     ecx, ecx
0x18001fa12  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001fa17  mov     ecx, edi
0x18001fa19  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001fa1e  test    rbx, rbx
0x18001fa21  jz      short loc_18001FA4B
0x18001fa23  call    cs:__imp_GetProcessHeap
0x18001fa2a  nop     dword ptr [rax+rax+00h]
0x18001fa2f  lea     r8, [rbx-4]; lpMem
0x18001fa33  xor     edx, edx; dwFlags
0x18001fa35  mov     rcx, rax; hHeap
0x18001fa38  call    cs:__imp_HeapFree
0x18001fa3f  nop     dword ptr [rax+rax+00h]
0x18001fa44  xor     ecx, ecx
0x18001fa46  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001fa4b  mov     eax, edi
0x18001fa4d  mov     rcx, [rsp+278h+var_38]
0x18001fa55  xor     rcx, rsp; StackCookie
0x18001fa58  call    __security_check_cookie
0x18001fa5d  add     rsp, 258h
0x18001fa64  pop     rdi
0x18001fa65  pop     rsi
0x18001fa66  pop     rbp
0x18001fa67  pop     rbx
0x18001fa68  retn
```

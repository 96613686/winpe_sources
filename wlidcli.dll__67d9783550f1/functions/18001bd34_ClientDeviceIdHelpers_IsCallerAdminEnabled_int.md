# ClientDeviceIdHelpers::IsCallerAdminEnabled(int &)

- ea: `0x18001bd34`
- end: `0x18001be71`
- name: `?IsCallerAdminEnabled@ClientDeviceIdHelpers@@SAJAEAH@Z`
- size: `317`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031b40`

## callees

- `0x18000cc9c`
- `0x18000e870`
- `0x18001ba5c`
- `0x18001bc30`
- `0x18001bd34`
- `0x18001be78`
- `0x1800530e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdc7`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001bdbd`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001bdbd`

## string_xrefs

- `0x18001bdd9`: `DuplicateToken failed with hr = 0x%x`

## pseudocode

```c
__int64 __fastcall ClientDeviceIdHelpers::IsCallerAdminEnabled(int *a1)
{
  __int64 v2; // rcx
  unsigned int IsLoggedInUserMatchSID; // ebx
  signed int LastError; // eax
  const unsigned __int16 *v6; // [rsp+20h] [rbp-60h]
  const unsigned __int16 *v7; // [rsp+20h] [rbp-60h]
  unsigned int v8; // [rsp+20h] [rbp-60h]
  unsigned int v9; // [rsp+28h] [rbp-58h]
  unsigned int v10; // [rsp+28h] [rbp-58h]
  unsigned int v11; // [rsp+30h] [rbp-50h]
  unsigned int v12; // [rsp+30h] [rbp-50h]
  unsigned int v13; // [rsp+38h] [rbp-48h]
  unsigned int v14; // [rsp+38h] [rbp-48h]
  unsigned int v15; // [rsp+40h] [rbp-40h]
  unsigned int v16; // [rsp+40h] [rbp-40h]
  unsigned int v17; // [rsp+48h] [rbp-38h]
  unsigned int v18; // [rsp+48h] [rbp-38h]
  _QWORD v19[4]; // [rsp+60h] [rbp-20h] BYREF
  int CurrentUserToken; // [rsp+A0h] [rbp+20h] BYREF
  HANDLE DuplicateTokenHandle; // [rsp+A8h] [rbp+28h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+B0h] [rbp+30h] BYREF

  CurrentUserToken = 0;
  v19[2] = 0;
  v19[0] = "ClientDeviceIdHelpers::IsCallerAdminEnabled";
  v19[1] = &CurrentUserToken;
  v19[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrldevicehelpers.cpp",
    "ClientDeviceIdHelpers::IsCallerAdminEnabled",
    (const char *)0x89,
    0,
    v6);
  ExistingTokenHandle = 0;
  DuplicateTokenHandle = 0;
  *a1 = 0;
  CurrentUserToken = ClientDeviceIdHelpers::GetCurrentUserToken(v2, &ExistingTokenHandle);
  IsLoggedInUserMatchSID = CurrentUserToken;
  if ( CurrentUserToken >= 0 )
  {
    if ( DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
    {
      CurrentUserToken = ClientDeviceIdHelpers::IsLoggedInUserMatchSID(
                           &DuplicateTokenHandle,
                           1u,
                           0x12u,
                           0,
                           (unsigned int)v7,
                           v9,
                           v11,
                           v13,
                           v15,
                           v17,
                           a1);
      IsLoggedInUserMatchSID = CurrentUserToken;
      if ( CurrentUserToken >= 0 && *a1 != 1 )
      {
        IsLoggedInUserMatchSID = ClientDeviceIdHelpers::IsLoggedInUserMatchSID(
                                   &DuplicateTokenHandle,
                                   2u,
                                   0x20u,
                                   0x220u,
                                   v8,
                                   v10,
                                   v12,
                                   v14,
                                   v16,
                                   v18,
                                   a1);
        CurrentUserToken = IsLoggedInUserMatchSID;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      CurrentUserToken = LastError;
      LODWORD(v7) = LastError;
      TracePrintW(
        2u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrldevicehelpers.cpp",
        0xA3u,
        L"DuplicateToken failed with hr = 0x%x",
        v7);
      IsLoggedInUserMatchSID = CurrentUserToken;
    }
  }
  ATL::CHandle::~CHandle((ATL::CHandle *)&DuplicateTokenHandle);
  ATL::CHandle::~CHandle((ATL::CHandle *)&ExistingTokenHandle);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v19);
  return IsLoggedInUserMatchSID;
}

```

## disassembly

```asm
0x18001bd34  push    rbp
0x18001bd36  push    rbx
0x18001bd37  push    rdi
0x18001bd38  mov     rbp, rsp
0x18001bd3b  sub     rsp, 80h
0x18001bd42  mov     rdi, rcx
0x18001bd45  mov     [rbp+arg_0], 0
0x18001bd4c  lea     rdx, aClientdeviceid_0; "ClientDeviceIdHelpers::IsCallerAdminEna"...
0x18001bd53  mov     [rbp+var_10], 0
0x18001bd5b  lea     rax, [rbp+arg_0]
0x18001bd5f  mov     [rbp+var_20], rdx
0x18001bd63  lea     rcx, aClientcoreDsEx_9; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001bd6a  mov     [rbp+var_18], rax
0x18001bd6e  xor     r9d, r9d; unsigned int
0x18001bd71  mov     [rbp+var_8], 0
0x18001bd79  mov     r8d, 89h; char *
0x18001bd7f  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18001bd84  lea     rdx, [rbp+ExistingTokenHandle]; struct ATL::CHandle *
0x18001bd88  mov     [rbp+ExistingTokenHandle], 0
0x18001bd90  mov     [rbp+DuplicateTokenHandle], 0
0x18001bd98  mov     dword ptr [rdi], 0
0x18001bd9e  call    ?GetCurrentUserToken@ClientDeviceIdHelpers@@SAJKAEAVCHandle@ATL@@@Z; ClientDeviceIdHelpers::GetCurrentUserToken(ulong,ATL::CHandle &)
0x18001bda3  mov     [rbp+arg_0], eax
0x18001bda6  mov     ebx, eax
0x18001bda8  test    eax, eax
0x18001bdaa  js      loc_18001BE49
0x18001bdb0  mov     rcx, [rbp+ExistingTokenHandle]; ExistingTokenHandle
0x18001bdb4  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x18001bdb8  mov     edx, 2; ImpersonationLevel
0x18001bdbd  call    cs:__imp_DuplicateToken
0x18001bdc3  test    eax, eax
0x18001bdc5  jnz     short loc_18001BE03
0x18001bdc7  call    cs:__imp_GetLastError
0x18001bdcd  test    eax, eax
0x18001bdcf  jle     short loc_18001BDD9
0x18001bdd1  movzx   eax, ax
0x18001bdd4  or      eax, 80070000h
0x18001bdd9  lea     r9, aDuplicatetoken; "DuplicateToken failed with hr = 0x%x"
0x18001bde0  mov     [rbp+arg_0], eax
0x18001bde3  mov     r8d, 0A3h; unsigned int
0x18001bde9  mov     dword ptr [rsp+80h+var_60], eax
0x18001bded  lea     rdx, aClientcoreDsEx_9; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001bdf4  mov     ecx, 2; unsigned __int8
0x18001bdf9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001bdfe  mov     ebx, [rbp+arg_0]
0x18001be01  jmp     short loc_18001BE49
0x18001be03  xor     r9d, r9d; unsigned int
0x18001be06  mov     [rsp+80h+var_30], rdi; int *
0x18001be0b  mov     dl, 1; unsigned __int8
0x18001be0d  lea     rcx, [rbp+DuplicateTokenHandle]; struct ATL::CHandle *
0x18001be11  lea     r8d, [r9+12h]; unsigned int
0x18001be15  call    ?IsLoggedInUserMatchSID@ClientDeviceIdHelpers@@CAJAEAVCHandle@ATL@@EKKKKKKKKAEAH@Z; ClientDeviceIdHelpers::IsLoggedInUserMatchSID(ATL::CHandle &,uchar,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int &)
0x18001be1a  mov     [rbp+arg_0], eax
0x18001be1d  mov     ebx, eax
0x18001be1f  test    eax, eax
0x18001be21  js      short loc_18001BE49
0x18001be23  cmp     dword ptr [rdi], 1
0x18001be26  jz      short loc_18001BE49
0x18001be28  mov     r9d, 220h; unsigned int
0x18001be2e  mov     [rsp+80h+var_30], rdi; int *
0x18001be33  mov     r8d, 20h ; ' '; unsigned int
0x18001be39  lea     rcx, [rbp+DuplicateTokenHandle]; struct ATL::CHandle *
0x18001be3d  mov     dl, 2; unsigned __int8
0x18001be3f  call    ?IsLoggedInUserMatchSID@ClientDeviceIdHelpers@@CAJAEAVCHandle@ATL@@EKKKKKKKKAEAH@Z; ClientDeviceIdHelpers::IsLoggedInUserMatchSID(ATL::CHandle &,uchar,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int &)
0x18001be44  mov     ebx, eax
0x18001be46  mov     [rbp+arg_0], eax
0x18001be49  lea     rcx, [rbp+DuplicateTokenHandle]; this
0x18001be4d  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x18001be52  lea     rcx, [rbp+ExistingTokenHandle]; this
0x18001be56  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x18001be5b  lea     rcx, [rbp+var_20]
0x18001be5f  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18001be64  mov     eax, ebx
0x18001be66  add     rsp, 80h
0x18001be6d  pop     rdi
0x18001be6e  pop     rbx
0x18001be6f  pop     rbp
0x18001be70  retn
```

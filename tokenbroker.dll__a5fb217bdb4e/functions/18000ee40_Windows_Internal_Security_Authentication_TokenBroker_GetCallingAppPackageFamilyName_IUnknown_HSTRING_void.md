# Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppPackageFamilyName(IUnknown *,HSTRING__ * *,void *)

- ea: `0x18000ee40`
- end: `0x18000f0a0`
- name: `?GetCallingAppPackageFamilyName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAPEAUHSTRING__@@PEAX@Z`
- size: `608`
- prototype: `int(Windows::Internal::Security::Authentication::TokenBroker *__hidden this, struct IUnknown *, HSTRING *, void *)`
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000d2b0`
- `0x18000e390`
- `0x1800afd50`
- `0x1800f03a4`
- `0x1800f0ad4`
- `0x1800f9760`

## callees

- `0x18000bd40`
- `0x18000ee40`
- `0x18000f0b0`
- `0x180024000`
- `0x18008e690`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ef7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ef7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ef6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ef6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f00f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f095`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f00f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f095`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18000eec1`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18000efd8`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18000eec1`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18000efd8`

## string_xrefs

- `0x18000ef52`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000ef93`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000f01e`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000f04d`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000f073`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppPackageFamilyName(
        Windows::Internal::Security::Authentication::TokenBroker *this,
        struct IUnknown *a2,
        HSTRING *a3,
        void *a4)
{
  LONG PackageFamilyNameFromToken; // eax
  int v6; // ebx
  __int64 result; // rax
  unsigned __int64 v8; // rdx
  __int64 v9; // rdx
  struct IUnknownVtbl *v10; // rbx
  int ImpersonationTokenForClientOfObject_nothrow; // eax
  LONG v12; // eax
  HSTRING string; // [rsp+20h] [rbp-69h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+28h] [rbp-61h] BYREF
  WCHAR packageFamilyName[8]; // [rsp+30h] [rbp-59h] BYREF
  __int128 v16; // [rsp+40h] [rbp-49h]
  __int128 v17; // [rsp+50h] [rbp-39h]
  __int128 v18; // [rsp+60h] [rbp-29h]
  __int128 v19; // [rsp+70h] [rbp-19h]
  __int128 v20; // [rsp+80h] [rbp-9h]
  __int128 v21; // [rsp+90h] [rbp+7h]
  __int128 v22; // [rsp+A0h] [rbp+17h]
  __int16 v23; // [rsp+B0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  if ( this )
  {
    if ( a2 )
    {
      packageFamilyNameLength = 65;
      v23 = 0;
      *(_OWORD *)packageFamilyName = 0;
      v16 = 0;
      v17 = 0;
      v18 = 0;
      v19 = 0;
      v20 = 0;
      v21 = 0;
      v22 = 0;
      if ( a3 )
      {
        PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(a3, &packageFamilyNameLength, packageFamilyName);
        v6 = PackageFamilyNameFromToken;
        if ( PackageFamilyNameFromToken > 0 )
          v6 = (unsigned __int16)PackageFamilyNameFromToken | 0x80070000;
        if ( v6 < 0 )
        {
          if ( v6 == -2147009196 )
            return 2147958100LL;
          v9 = 1920;
          goto LABEL_16;
        }
      }
      else
      {
        string = 0;
        ImpersonationTokenForClientOfObject_nothrow = wil::GetImpersonationTokenForClientOfObject_nothrow(
                                                        this,
                                                        131080,
                                                        &string);
        v6 = ImpersonationTokenForClientOfObject_nothrow;
        if ( ImpersonationTokenForClientOfObject_nothrow < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x785,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
            (const char *)(unsigned int)ImpersonationTokenForClientOfObject_nothrow,
            (int)string);
          Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&string);
          return (unsigned int)v6;
        }
        v12 = GetPackageFamilyNameFromToken(string, &packageFamilyNameLength, packageFamilyName);
        v6 = v12;
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
        if ( v6 < 0 )
        {
          if ( v6 == -2147009196 )
          {
            if ( (unsigned __int64)string - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(string);
            return 2147958100LL;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x789,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
            (const char *)(unsigned int)v6,
            (int)string);
          Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&string);
          return (unsigned int)v6;
        }
        if ( (unsigned __int64)string - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(string);
      }
      string = 0;
      v8 = -1;
      do
        ++v8;
      while ( packageFamilyName[v8] );
      if ( v8 > 0xFFFFFFFF )
      {
        v6 = -2147024362;
LABEL_15:
        v9 = 1932;
LABEL_16:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v9,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
          (const char *)(unsigned int)v6,
          (int)string);
        return (unsigned int)v6;
      }
      v6 = WindowsCreateString(packageFamilyName, v8, &string);
      if ( v6 < 0 )
        goto LABEL_15;
      v10 = (struct IUnknownVtbl *)string;
      WindowsDeleteString(0);
      result = 0;
      a2->lpVtbl = v10;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x776,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)0x80070057LL,
        (int)string);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x775,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)0x80070057LL,
      (int)string);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000ee40  push    rbp
0x18000ee42  push    rdi
0x18000ee43  lea     rbp, [rsp-4Fh]
0x18000ee48  sub     rsp, 0D8h
0x18000ee4f  mov     rax, cs:__security_cookie
0x18000ee56  xor     rax, rsp
0x18000ee59  mov     [rbp+57h+var_20], rax
0x18000ee5d  mov     rax, r8
0x18000ee60  mov     rdi, rdx
0x18000ee63  test    rcx, rcx
0x18000ee66  jz      loc_18000EF8F
0x18000ee6c  test    rdx, rdx
0x18000ee6f  jz      loc_18000F01A
0x18000ee75  xorps   xmm0, xmm0
0x18000ee78  mov     [rsp+0E0h+var_10], rbx
0x18000ee80  xor     edx, edx
0x18000ee82  mov     [rbp+57h+packageFamilyNameLength], 41h ; 'A'
0x18000ee89  mov     [rbp+57h+var_30], dx
0x18000ee8d  movups  xmmword ptr [rbp+57h+packageFamilyName], xmm0
0x18000ee91  movups  [rbp+57h+var_A0], xmm0
0x18000ee95  movups  [rbp+57h+var_90], xmm0
0x18000ee99  movups  [rbp+57h+var_80], xmm0
0x18000ee9d  movups  [rbp+57h+var_70], xmm0
0x18000eea1  movups  [rbp+57h+var_60], xmm0
0x18000eea5  movups  [rbp+57h+var_50], xmm0
0x18000eea9  movups  [rbp+57h+var_40], xmm0
0x18000eead  test    rax, rax
0x18000eeb0  jz      loc_18000EFB4
0x18000eeb6  lea     r8, [rbp+57h+packageFamilyName]; packageFamilyName
0x18000eeba  mov     rcx, rax; token
0x18000eebd  lea     rdx, [rbp+57h+packageFamilyNameLength]; packageFamilyNameLength
0x18000eec1  call    cs:__imp_GetPackageFamilyNameFromToken
0x18000eec7  mov     ebx, eax
0x18000eec9  test    eax, eax
0x18000eecb  jle     short loc_18000EED6
0x18000eecd  movzx   ebx, ax
0x18000eed0  or      ebx, 80070000h
0x18000eed6  test    ebx, ebx
0x18000eed8  jns     short loc_18000EF1B
0x18000eeda  cmp     ebx, 80073D54h
0x18000eee0  jnz     loc_18000F03F
0x18000eee6  mov     eax, 80073D54h
0x18000eeeb  mov     rbx, [rsp+0E0h+var_10]
0x18000eef3  mov     rcx, [rbp+57h+var_20]
0x18000eef7  xor     rcx, rsp; StackCookie
0x18000eefa  call    __security_check_cookie
0x18000eeff  add     rsp, 0D8h
0x18000ef06  pop     rdi
0x18000ef07  pop     rbp
0x18000ef08  retn
0x18000ef09  mov     rcx, [rbp+57h+string]; hObject
0x18000ef0d  lea     rax, [rcx-1]
0x18000ef11  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ef15  jbe     loc_18000F095
0x18000ef1b  mov     [rbp+57h+string], 0
0x18000ef23  lea     rax, [rbp+57h+packageFamilyName]
0x18000ef27  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000ef2e  xchg    ax, ax
0x18000ef30  inc     rdx; length
0x18000ef33  cmp     word ptr [rax+rdx*2], 0
0x18000ef38  jnz     short loc_18000EF30
0x18000ef3a  mov     eax, 0FFFFFFFFh
0x18000ef3f  cmp     rdx, rax
0x18000ef42  jbe     short loc_18000EF65
0x18000ef44  mov     ebx, 80070216h
0x18000ef49  mov     edx, 78Ch; void *
0x18000ef4e  mov     rcx, [rbp+5Fh]; this
0x18000ef52  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000ef59  mov     r9d, ebx; char *
0x18000ef5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ef61  mov     eax, ebx
0x18000ef63  jmp     short loc_18000EEEB
0x18000ef65  lea     r8, [rbp+57h+string]; string
0x18000ef69  lea     rcx, [rbp+57h+packageFamilyName]; sourceString
0x18000ef6d  call    cs:__imp_WindowsCreateString
0x18000ef73  mov     ebx, eax
0x18000ef75  test    eax, eax
0x18000ef77  js      short loc_18000EF49
0x18000ef79  mov     rbx, [rbp+57h+string]
0x18000ef7d  xor     ecx, ecx; string
0x18000ef7f  call    cs:__imp_WindowsDeleteString
0x18000ef85  xor     eax, eax
0x18000ef87  mov     [rdi], rbx
0x18000ef8a  jmp     loc_18000EEEB
0x18000ef8f  mov     rcx, [rbp+5Fh]; this
0x18000ef93  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000ef9a  mov     r9d, 80070057h; char *
0x18000efa0  mov     edx, 775h; void *
0x18000efa5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000efaa  mov     eax, 80070057h
0x18000efaf  jmp     loc_18000EEF3
0x18000efb4  mov     [rbp+57h+string], rdx
0x18000efb8  lea     r8, [rbp+57h+string]
0x18000efbc  mov     edx, 20008h
0x18000efc1  call    ?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z; wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x18000efc6  mov     ebx, eax
0x18000efc8  test    eax, eax
0x18000efca  js      short loc_18000F049
0x18000efcc  mov     rcx, [rbp+57h+string]; token
0x18000efd0  lea     r8, [rbp+57h+packageFamilyName]; packageFamilyName
0x18000efd4  lea     rdx, [rbp+57h+packageFamilyNameLength]; packageFamilyNameLength
0x18000efd8  call    cs:__imp_GetPackageFamilyNameFromToken
0x18000efde  mov     ebx, eax
0x18000efe0  test    eax, eax
0x18000efe2  jle     short loc_18000EFED
0x18000efe4  movzx   ebx, ax
0x18000efe7  or      ebx, 80070000h
0x18000efed  test    ebx, ebx
0x18000efef  jns     loc_18000EF09
0x18000eff5  cmp     ebx, 80073D54h
0x18000effb  jnz     short loc_18000F06F
0x18000effd  mov     rcx, [rbp+57h+string]; hObject
0x18000f001  lea     rdx, [rcx-1]
0x18000f005  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000f009  ja      loc_18000EEE6
0x18000f00f  call    cs:__imp_CloseHandle
0x18000f015  jmp     loc_18000EEE6
0x18000f01a  mov     rcx, [rbp+5Fh]; this
0x18000f01e  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000f025  mov     r9d, 80070057h; char *
0x18000f02b  mov     edx, 776h; void *
0x18000f030  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f035  mov     eax, 80070057h
0x18000f03a  jmp     loc_18000EEF3
0x18000f03f  mov     edx, 780h
0x18000f044  jmp     loc_18000EF4E
0x18000f049  mov     rcx, [rbp+5Fh]; this
0x18000f04d  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000f054  mov     r9d, ebx; char *
0x18000f057  mov     edx, 785h; void *
0x18000f05c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f061  lea     rcx, [rbp+57h+string]; this
0x18000f065  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x18000f06a  jmp     loc_18000EF61
0x18000f06f  mov     rcx, [rbp+5Fh]; this
0x18000f073  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000f07a  mov     r9d, ebx; char *
0x18000f07d  mov     edx, 789h; void *
0x18000f082  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f087  lea     rcx, [rbp+57h+string]; this
0x18000f08b  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x18000f090  jmp     loc_18000EF61
0x18000f095  call    cs:__imp_CloseHandle
0x18000f09b  jmp     loc_18000EF1B
```

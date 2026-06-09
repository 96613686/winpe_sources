# WsiEnvironmentAccountManagerInternals::GetWsiEnvironmentSid(void * *)

- ea: `0x180013edc`
- end: `0x180014062`
- name: `?GetWsiEnvironmentSid@WsiEnvironmentAccountManagerInternals@@YAJPEAPEAX@Z`
- size: `390`
- prototype: `__int64 __fastcall(WsiEnvironmentAccountManagerInternals *__hidden this, void **)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013500`
- `0x180013b84`
- `0x180066c08`
- `0x1800d7da4`

## callees

- `0x180013edc`
- `0x180014e5c`
- `0x18004aa68`
- `0x1800534d0`
- `0x180061e1c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180014041`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180014041`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001401d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001401d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013f98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013f98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013fcb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013fcb`
- `samcli!NetUserGetInfo` at `0x180013f2e`
- `samcli!NetUserGetInfo` at `0x180013f2e`
- `netutils!NetApiBufferFree` at `0x180013f51`
- `netutils!NetApiBufferFree` at `0x180013f90`
- `netutils!NetApiBufferFree` at `0x180013f51`
- `netutils!NetApiBufferFree` at `0x180013f90`

## string_xrefs

- `0x180013fa7`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`
- `0x180014002`: `onecore\ds\security\umstartup\accountmanagerutils\accountmanagerutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WsiEnvironmentAccountManagerInternals::GetWsiEnvironmentSid(
        WsiEnvironmentAccountManagerInternals *this,
        void **a2)
{
  DWORD Info; // edi
  LPBYTE v5; // r12
  void *v6; // r14
  DWORD LastError; // ebx
  unsigned int v8; // ebx
  HLOCAL v9; // rcx
  DWORD LengthSid; // ebx
  HLOCAL v11; // rdi
  const char *v12; // r9
  char *v13; // [rsp+28h] [rbp-28h]
  LPBYTE bufptr; // [rsp+38h] [rbp-18h] BYREF
  char v15; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  LPVOID Buffer; // [rsp+80h] [rbp+30h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp+38h] BYREF

  *(_QWORD *)this = 0;
  Buffer = 0;
  bufptr = 0;
  v15 = 1;
  Info = NetUserGetInfo(0, L"WsiAccount", 0x17u, &bufptr);
  if ( v15 )
  {
    v5 = bufptr;
    v6 = Buffer;
    if ( Buffer )
    {
      LastError = GetLastError();
      NetApiBufferFree(v6);
      SetLastError(LastError);
    }
    Buffer = v5;
  }
  if ( Info == 2221 )
  {
    if ( Buffer )
      NetApiBufferFree(Buffer);
    return 2148073489LL;
  }
  else
  {
    if ( Info )
    {
      LODWORD(v13) = Info;
      v8 = -2147467259;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
        (const char *)0x80004005LL,
        (int)"status: %d",
        v13);
    }
    else
    {
      LengthSid = GetLengthSid(*((PSID *)Buffer + 4));
      wil::make_unique_hlocal<unsigned char [0]>(&hMem);
      v11 = hMem;
      if ( CopySid(LengthSid, hMem, *((PSID *)Buffer + 4)) )
      {
        *(_QWORD *)this = v11;
        hMem = 0;
        v8 = 0;
      }
      else
      {
        v8 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x1C6,
               (unsigned int)"onecore\\ds\\security\\umstartup\\accountmanagerutils\\accountmanagerutils.cpp",
               v12);
        v9 = hMem;
        hMem = 0;
        if ( v9 )
          LocalFree(v9);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned char *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&Buffer);
    return v8;
  }
}

```

## disassembly

```asm
0x180013edc  mov     [rsp-28h+arg_10], rbx
0x180013ee1  mov     [rsp-28h+arg_18], rsi
0x180013ee6  push    rbp
0x180013ee7  push    rdi
0x180013ee8  push    r12
0x180013eea  push    r14
0x180013eec  push    r15
0x180013eee  mov     rbp, rsp
0x180013ef1  sub     rsp, 50h
0x180013ef5  mov     r15, rcx
0x180013ef8  mov     qword ptr [rcx], 0
0x180013eff  mov     [rbp+Buffer], 0
0x180013f07  lea     rax, [rbp+Buffer]
0x180013f0b  mov     [rbp+var_20], rax
0x180013f0f  mov     [rbp+bufptr], 0
0x180013f17  mov     [rbp+var_10], 1
0x180013f1b  lea     r9, [rbp+bufptr]; bufptr
0x180013f1f  mov     r8d, 17h; level
0x180013f25  lea     rdx, username; "WsiAccount"
0x180013f2c  xor     ecx, ecx; servername
0x180013f2e  call    cs:__imp_NetUserGetInfo
0x180013f34  mov     edi, eax
0x180013f36  cmp     [rbp+var_10], 0
0x180013f3a  jnz     short loc_180013F75
0x180013f3c  cmp     edi, 8ADh
0x180013f42  jnz     loc_180013FE2
0x180013f48  mov     rcx, [rbp+Buffer]; Buffer
0x180013f4c  test    rcx, rcx
0x180013f4f  jz      short loc_180013F57
0x180013f51  call    cs:__imp_NetApiBufferFree
0x180013f57  mov     eax, 80090011h
0x180013f5c  lea     r11, [rsp+50h+var_s0]
0x180013f61  mov     rbx, [r11+40h]
0x180013f65  mov     rsi, [r11+48h]
0x180013f69  mov     rsp, r11
0x180013f6c  pop     r15
0x180013f6e  pop     r14
0x180013f70  pop     r12
0x180013f72  pop     rdi
0x180013f73  pop     rbp
0x180013f74  retn
0x180013f75  mov     r12, [rbp+bufptr]
0x180013f79  mov     rsi, [rbp+var_20]
0x180013f7d  mov     r14, [rsi]
0x180013f80  test    r14, r14
0x180013f83  jz      short loc_180013F9E
0x180013f85  call    cs:__imp_GetLastError
0x180013f8b  mov     ebx, eax
0x180013f8d  mov     rcx, r14; Buffer
0x180013f90  call    cs:__imp_NetApiBufferFree
0x180013f96  mov     ecx, ebx; dwErrCode
0x180013f98  call    cs:__imp_SetLastError
0x180013f9e  mov     [rsi], r12
0x180013fa1  jmp     short loc_180013F3C
0x180013fa3  mov     rcx, [rbp+28h]; this
0x180013fa7  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x180013fae  mov     edx, 1C6h; void *
0x180013fb3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013fb8  mov     ebx, eax
0x180013fba  mov     rcx, [rbp+hMem]; hMem
0x180013fbe  mov     [rbp+hMem], 0
0x180013fc6  test    rcx, rcx
0x180013fc9  jz      short loc_180013FD2
0x180013fcb  call    cs:__imp_LocalFree
0x180013fd1  nop
0x180013fd2  lea     rcx, [rbp+Buffer]
0x180013fd6  call    ??1?$unique_storage@U?$resource_policy@PEAEP6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<uchar *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<uchar *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>(void)
0x180013fdb  mov     eax, ebx
0x180013fdd  jmp     loc_180013F5C
0x180013fe2  test    edi, edi
0x180013fe4  jz      short loc_180014015
0x180013fe6  mov     rcx, [rbp+28h]; this
0x180013fea  mov     dword ptr [rsp+50h+var_28], edi; char *
0x180013fee  lea     rax, aStatusD; "status: %d"
0x180013ff5  mov     qword ptr [rsp+50h+var_30], rax; int
0x180013ffa  mov     ebx, 80004005h
0x180013fff  mov     r9d, ebx; char *
0x180014002  lea     r8, aOnecoreDsSecur_78; "onecore\\ds\\security\\umstartup\\accou"...
0x180014009  mov     edx, 1C1h; void *
0x18001400e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180014013  jmp     short loc_180013FD2
0x180014015  mov     rcx, [rbp+Buffer]
0x180014019  mov     rcx, [rcx+20h]; pSid
0x18001401d  call    cs:__imp_GetLengthSid
0x180014023  mov     ebx, eax
0x180014025  mov     edx, eax
0x180014027  lea     rcx, [rbp+hMem]
0x18001402b  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x180014030  mov     rdi, [rbp+hMem]
0x180014034  mov     r8, [rbp+Buffer]
0x180014038  mov     r8, [r8+20h]; pSourceSid
0x18001403c  mov     rdx, rdi; pDestinationSid
0x18001403f  mov     ecx, ebx; nDestinationSidLength
0x180014041  call    cs:__imp_CopySid
0x180014047  test    eax, eax
0x180014049  jz      loc_180013FA3
0x18001404f  mov     [r15], rdi
0x180014052  mov     [rbp+hMem], 0
0x18001405a  xor     ebx, ebx
0x18001405c  jmp     loc_180013FD2
```

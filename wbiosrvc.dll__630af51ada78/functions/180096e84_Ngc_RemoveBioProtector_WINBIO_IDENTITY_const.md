# Ngc::RemoveBioProtector(_WINBIO_IDENTITY const &)

- ea: `0x180096e84`
- end: `0x180096f4f`
- name: `?RemoveBioProtector@Ngc@@YAJAEBU_WINBIO_IDENTITY@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(Ngc *__hidden this, const struct _WINBIO_IDENTITY *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180028df4`
- `0x18009a6fc`

## callees

- `0x180043744`
- `0x18005388c`
- `0x180056358`
- `0x180096bc8`
- `0x180096e84`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180096edc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180096edc`
- `cryptngc!NgcRemoveBioProtector` at `0x180096f14`
- `cryptngc!NgcRemoveBioProtector` at `0x180096f14`

## string_xrefs

- `0x180096e94`: `onecore\ds\security\biometrics\service\server\ngc.cpp`
- `0x180096efa`: `onecore\ds\security\biometrics\service\server\ngc.cpp`
- `0x180096f25`: `onecore\ds\security\biometrics\service\server\ngc.cpp`

## pseudocode

```c
__int64 __fastcall Ngc::RemoveBioProtector(Ngc *this, const struct _WINBIO_IDENTITY *a2)
{
  unsigned int LastError; // ebx
  bool v3; // bl
  const char *v4; // r9
  int v5; // eax
  int v7[2]; // [rsp+20h] [rbp-28h] BYREF
  LPWSTR StringSid; // [rsp+28h] [rbp-20h] BYREF
  char v9; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)this == 3 )
  {
    v11 = 0;
    *(_QWORD *)v7 = &v11;
    StringSid = 0;
    v9 = 1;
    v3 = !ConvertSidToStringSidW((char *)this + 8, &StringSid);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v7);
    if ( v3 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x74,
                    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\ngc.cpp",
                    v4);
    }
    else
    {
      v5 = NgcRemoveBioProtector(v11);
      LastError = v5;
      if ( v5 >= 0 )
        LastError = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x76,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\ngc.cpp",
          (const char *)(unsigned int)v5,
          v7[0]);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
  }
  else
  {
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\ngc.cpp",
      (const char *)0x80070057LL,
      v7[0]);
  }
  return LastError;
}

```

## disassembly

```asm
0x180096e84  push    rbx
0x180096e86  sub     rsp, 40h
0x180096e8a  cmp     dword ptr [rcx], 3
0x180096e8d  jz      short loc_180096EB2
0x180096e8f  mov     rcx, [rsp+48h]; this
0x180096e94  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\biometrics\\serv"...
0x180096e9b  mov     ebx, 80070057h
0x180096ea0  mov     edx, 6Eh ; 'n'; void *
0x180096ea5  mov     r9d, ebx; char *
0x180096ea8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096ead  jmp     loc_180096F47
0x180096eb2  lea     rax, [rsp+48h+arg_0]
0x180096eb7  mov     [rsp+48h+arg_0], 0
0x180096ec0  add     rcx, 8; Sid
0x180096ec4  mov     qword ptr [rsp+48h+var_28], rax; int
0x180096ec9  lea     rdx, [rsp+48h+StringSid]; StringSid
0x180096ece  mov     [rsp+48h+StringSid], 0
0x180096ed7  mov     [rsp+48h+var_18], 1
0x180096edc  call    cs:__imp_ConvertSidToStringSidW
0x180096ee2  test    eax, eax
0x180096ee4  lea     rcx, [rsp+48h+var_28]
0x180096ee9  setz    bl
0x180096eec  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180096ef1  test    bl, bl
0x180096ef3  jz      short loc_180096F0F
0x180096ef5  mov     rcx, [rsp+48h]; this
0x180096efa  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\biometrics\\serv"...
0x180096f01  mov     edx, 74h ; 't'; void *
0x180096f06  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180096f0b  mov     ebx, eax
0x180096f0d  jmp     short loc_180096F3D
0x180096f0f  mov     rcx, [rsp+48h+arg_0]
0x180096f14  call    cs:__imp_NgcRemoveBioProtector
0x180096f1a  mov     ebx, eax
0x180096f1c  test    eax, eax
0x180096f1e  jns     short loc_180096F3B
0x180096f20  mov     rcx, [rsp+48h]; this
0x180096f25  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\biometrics\\serv"...
0x180096f2c  mov     r9d, eax; char *
0x180096f2f  mov     edx, 76h ; 'v'; void *
0x180096f34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096f39  jmp     short loc_180096F3D
0x180096f3b  xor     ebx, ebx
0x180096f3d  lea     rcx, [rsp+48h+arg_0]
0x180096f42  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180096f47  mov     eax, ebx
0x180096f49  add     rsp, 40h
0x180096f4d  pop     rbx
0x180096f4e  retn
```

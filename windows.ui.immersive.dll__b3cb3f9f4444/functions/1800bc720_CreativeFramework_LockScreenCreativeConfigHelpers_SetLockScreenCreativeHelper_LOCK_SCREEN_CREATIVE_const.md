# CreativeFramework::LockScreenCreativeConfigHelpers::SetLockScreenCreativeHelper(LOCK_SCREEN_CREATIVE const &)

- ea: `0x1800bc720`
- end: `0x1800bc888`
- name: `?SetLockScreenCreativeHelper@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJAEBULOCK_SCREEN_CREATIVE@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(CreativeFramework::LockScreenCreativeConfigHelpers *__hidden this, const struct LOCK_SCREEN_CREATIVE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800bc6e4`

## callees

- `0x18000a24c`
- `0x18000c1b8`
- `0x18000c410`
- `0x18003729c`
- `0x18003c554`
- `0x18003d244`
- `0x1800bc720`
- `0x1800bf3fc`
- `0x1800bf58c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bc81c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bc81c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800bc808`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800bc808`
- `ntdll!RtlPublishWnfStateData` at `0x1800bc841`
- `ntdll!RtlPublishWnfStateData` at `0x1800bc841`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800bc7c5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800bc7c5`

## string_xrefs

- `0x1800bc747`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x1800bc79d`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x1800bc7e8`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreativeFramework::LockScreenCreativeConfigHelpers::SetLockScreenCreativeHelper(
        CreativeFramework::LockScreenCreativeConfigHelpers *this,
        const struct LOCK_SCREEN_CREATIVE *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  unsigned __int16 **v5; // rdx
  int CurrentUserSidString; // eax
  const unsigned __int16 *v7; // r8
  __int64 v8; // rdx
  int Error; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  DWORD LengthSid; // eax
  int v13; // eax
  int v15; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  PSID Sid; // [rsp+48h] [rbp+18h] BYREF
  LPCWSTR StringSid; // [rsp+50h] [rbp+20h] BYREF

  v3 = CreativeFramework::LockScreenCreativeConfigHelpers::WriteCreativeToRegistry(this, a2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    CurrentUserSidString = CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(
                             (CreativeFramework::LockScreenCreativeConfigHelpers *)&StringSid,
                             v5);
    v4 = CurrentUserSidString;
    if ( CurrentUserSidString >= 0 )
    {
      CurrentUserSidString = CreativeFramework::LockScreenCreativeConfigHelpers::WriteCreativeToMachineRegistry(
                               this,
                               (const struct LOCK_SCREEN_CREATIVE *)StringSid,
                               v7);
      v4 = CurrentUserSidString;
      if ( CurrentUserSidString >= 0 )
      {
        Sid = 0;
        if ( ConvertStringSidToSidW(StringSid, &Sid) || (Error = ResultFromKnownLastError(), v4 = Error, Error >= 0) )
        {
          if ( !IsValidSid(Sid)
            || (LengthSid = GetLengthSid(Sid),
                v13 = RtlPublishWnfStateData(WNF_SHEL_LOCKSCREEN_IMAGE_CHANGED, 0, Sid, LengthSid, 0),
                v4 = v13 | 0x10000000,
                v13 >= 0) )
          {
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
            v4 = 0;
            goto LABEL_16;
          }
          v10 = v4;
          v11 = 268;
        }
        else
        {
          v10 = (unsigned int)Error;
          v11 = 260;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
          (const char *)v10,
          v15);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
LABEL_16:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
        return v4;
      }
      v8 = 257;
    }
    else
    {
      v8 = 256;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
      (const char *)(unsigned int)CurrentUserSidString,
      v15);
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xFD,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
    (const char *)(unsigned int)v3,
    v15);
  return v4;
}

```

## disassembly

```asm
0x1800bc720  mov     [rsp-8+arg_0], rbx
0x1800bc725  mov     [rsp-8+arg_18], rdi
0x1800bc72a  push    rbp
0x1800bc72b  mov     rbp, rsp
0x1800bc72e  sub     rsp, 30h
0x1800bc732  mov     rdi, rcx
0x1800bc735  call    ?WriteCreativeToRegistry@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEBULOCK_SCREEN_CREATIVE@@@Z; CreativeFramework::LockScreenCreativeConfigHelpers::WriteCreativeToRegistry(LOCK_SCREEN_CREATIVE const *)
0x1800bc73a  mov     ebx, eax
0x1800bc73c  test    eax, eax
0x1800bc73e  jns     short loc_1800BC75D
0x1800bc740  mov     rcx, [rbp+8]; this
0x1800bc744  mov     r9d, eax; char *
0x1800bc747  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x1800bc74e  mov     edx, 0FDh; void *
0x1800bc753  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc758  jmp     loc_1800BC875
0x1800bc75d  mov     [rbp+StringSid], 0
0x1800bc765  xor     edx, edx
0x1800bc767  lea     rcx, [rbp+StringSid]
0x1800bc76b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800bc770  lea     rcx, [rbp+StringSid]; this
0x1800bc774  call    ?GetCurrentUserSidString@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEAPEAG@Z; CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(ushort * *)
0x1800bc779  mov     ebx, eax
0x1800bc77b  test    eax, eax
0x1800bc77d  jns     short loc_1800BC786
0x1800bc77f  mov     edx, 100h
0x1800bc784  jmp     short loc_1800BC79D
0x1800bc786  mov     rdx, [rbp+StringSid]; struct LOCK_SCREEN_CREATIVE *
0x1800bc78a  mov     rcx, rdi; this
0x1800bc78d  call    ?WriteCreativeToMachineRegistry@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEBULOCK_SCREEN_CREATIVE@@PEBG@Z; CreativeFramework::LockScreenCreativeConfigHelpers::WriteCreativeToMachineRegistry(LOCK_SCREEN_CREATIVE const *,ushort const *)
0x1800bc792  mov     ebx, eax
0x1800bc794  test    eax, eax
0x1800bc796  jns     short loc_1800BC7B5
0x1800bc798  mov     edx, 101h; void *
0x1800bc79d  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x1800bc7a4  mov     r9d, eax; char *
0x1800bc7a7  mov     rcx, [rbp+8]; this
0x1800bc7ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc7b0  jmp     loc_1800BC86C
0x1800bc7b5  mov     [rbp+Sid], 0
0x1800bc7bd  lea     rdx, [rbp+Sid]; Sid
0x1800bc7c1  mov     rcx, [rbp+StringSid]; StringSid
0x1800bc7c5  call    cs:__imp_ConvertStringSidToSidW
0x1800bc7cc  nop     dword ptr [rax+rax+00h]
0x1800bc7d1  test    eax, eax
0x1800bc7d3  jnz     short loc_1800BC804
0x1800bc7d5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800bc7da  mov     ebx, eax
0x1800bc7dc  test    eax, eax
0x1800bc7de  jns     short loc_1800BC804
0x1800bc7e0  mov     r9d, eax; char *
0x1800bc7e3  mov     edx, 104h; void *
0x1800bc7e8  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x1800bc7ef  mov     rcx, [rbp+8]; this
0x1800bc7f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc7f8  nop
0x1800bc7f9  lea     rcx, [rbp+Sid]
0x1800bc7fd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800bc802  jmp     short loc_1800BC86C
0x1800bc804  mov     rcx, [rbp+Sid]; pSid
0x1800bc808  call    cs:__imp_IsValidSid
0x1800bc80f  nop     dword ptr [rax+rax+00h]
0x1800bc814  test    eax, eax
0x1800bc816  jz      short loc_1800BC861
0x1800bc818  mov     rcx, [rbp+Sid]; pSid
0x1800bc81c  call    cs:__imp_GetLengthSid
0x1800bc823  nop     dword ptr [rax+rax+00h]
0x1800bc828  mov     qword ptr [rsp+30h+var_10], 0
0x1800bc831  mov     r9d, eax
0x1800bc834  mov     r8, [rbp+Sid]
0x1800bc838  xor     edx, edx
0x1800bc83a  mov     rcx, cs:WNF_SHEL_LOCKSCREEN_IMAGE_CHANGED
0x1800bc841  call    cs:__imp_RtlPublishWnfStateData
0x1800bc848  nop     dword ptr [rax+rax+00h]
0x1800bc84d  mov     ebx, eax
0x1800bc84f  or      ebx, 10000000h
0x1800bc855  jge     short loc_1800BC861
0x1800bc857  mov     r9d, ebx
0x1800bc85a  mov     edx, 10Ch
0x1800bc85f  jmp     short loc_1800BC7E8
0x1800bc861  lea     rcx, [rbp+Sid]
0x1800bc865  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800bc86a  xor     ebx, ebx
0x1800bc86c  lea     rcx, [rbp+StringSid]
0x1800bc870  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800bc875  mov     eax, ebx
0x1800bc877  mov     rbx, [rsp+30h+arg_0]
0x1800bc87c  mov     rdi, [rsp+30h+arg_18]
0x1800bc881  add     rsp, 30h
0x1800bc885  pop     rbp
0x1800bc886  retn
```

# BioTrustlet::Start(bool)

- ea: `0x180056378`
- end: `0x18005676a`
- name: `?Start@BioTrustlet@@QEAAJ_N@Z`
- size: `1010`
- prototype: `__int64 __fastcall(BioTrustlet *this)`
- caller_count: `2`
- callee_count: `16`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180045044`
- `0x180071de8`

## callees

- `0x18001434c`
- `0x180014854`
- `0x180014894`
- `0x18003903c`
- `0x18003f2dc`
- `0x180051030`
- `0x18005388c`
- `0x1800538b0`
- `0x1800549a0`
- `0x180055fec`
- `0x180056358`
- `0x180056378`
- `0x180068f60`
- `0x180069cc8`
- `0x1800b4fac`
- `0x1800b532c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180056472`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180056472`
- `ntdll!RtlFreeUnicodeString` at `0x18005654f`
- `ntdll!RtlFreeUnicodeString` at `0x18005672e`
- `ntdll!RtlFreeUnicodeString` at `0x18005654f`
- `ntdll!RtlFreeUnicodeString` at `0x18005672e`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800564be`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800564be`
- `ntdll!RtlCreateProcessParametersEx` at `0x180056524`
- `ntdll!RtlCreateProcessParametersEx` at `0x180056524`
- `ntdll!NtCreateUserProcess` at `0x1800566bc`
- `ntdll!NtCreateUserProcess` at `0x1800566bc`

## string_xrefs

- `0x1800563c8`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`
- `0x18005644c`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`
- `0x18005648e`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`
- `0x1800564d2`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`
- `0x180056538`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`
- `0x1800566d0`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`
- `0x180056469`: `Global\BioIsoServiceReadyEvent_9AEB5736_E826_4EFE_ABD5_8BDED2257629`
- `0x1800563fa`: `%windir%\system32\BioIso.exe`

## pseudocode

```c
__int64 __fastcall BioTrustlet::Start(BioTrustlet *this)
{
  int IsSecureBioAvailable; // ebx
  __int64 v3; // rdx
  int v5; // eax
  const char *v6; // r9
  int LastError; // eax
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // [rsp+20h] [rbp-E0h]
  char v13; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v14; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v15; // [rsp+68h] [rbp-98h] BYREF
  __int64 v16; // [rsp+70h] [rbp-90h] BYREF
  __int64 v17; // [rsp+78h] [rbp-88h] BYREF
  _UNICODE_STRING UnicodeString; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v19[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v20; // [rsp+A0h] [rbp-60h] BYREF
  char v21; // [rsp+B0h] [rbp-50h]
  int v22; // [rsp+100h] [rbp+0h]
  _BYTE v23[20]; // [rsp+104h] [rbp+4h] BYREF
  char v24; // [rsp+118h] [rbp+18h] BYREF
  __int64 v25; // [rsp+170h] [rbp+70h]
  __int64 v26; // [rsp+178h] [rbp+78h]
  __int64 v27; // [rsp+180h] [rbp+80h]
  char *v28; // [rsp+188h] [rbp+88h]
  __int64 v29; // [rsp+190h] [rbp+90h]
  __int64 v30; // [rsp+198h] [rbp+98h]
  __int64 v31; // [rsp+1A0h] [rbp+A0h]
  char *v32; // [rsp+1A8h] [rbp+A8h]
  __int64 v33; // [rsp+1B0h] [rbp+B0h]
  __int64 v34; // [rsp+1B8h] [rbp+B8h]
  __int64 Length; // [rsp+1C0h] [rbp+C0h]
  PWSTR Buffer; // [rsp+1C8h] [rbp+C8h]
  __int64 v37; // [rsp+1D0h] [rbp+D0h]
  __int64 v38; // [rsp+1D8h] [rbp+D8h]
  __int64 v39; // [rsp+1E0h] [rbp+E0h]
  __int64 *v40; // [rsp+1E8h] [rbp+E8h]
  __int64 v41; // [rsp+1F0h] [rbp+F0h]
  _BYTE v42[32]; // [rsp+200h] [rbp+100h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v14 = 0;
  IsSecureBioAvailable = BioTrustlet::IsSecureBioAvailable(&v14);
  if ( IsSecureBioAvailable >= 0 )
  {
    if ( (v14 & 1) == 0 )
      return 2147942450LL;
    if ( !*((_QWORD *)this + 3) )
    {
      std::wstring::wstring(v42, L"%windir%\\system32\\BioIso.exe");
      IsSecureBioAvailable = BioTrustlet::SetPath(this, v42);
      std::wstring::_Tidy_deallocate(v42);
      if ( IsSecureBioAvailable < 0 )
      {
        v3 = 643;
        goto LABEL_3;
      }
    }
    v5 = BioTrustlet::TerminateRunningInstances(this);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x288,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\trustletcontrol.cpp",
        (const char *)(unsigned int)v5,
        v12);
    v19[0] = CreateEventExW(0, L"Global\\BioIsoServiceReadyEvent_9AEB5736_E826_4EFE_ABD5_8BDED2257629", 1u, 0x100001u);
    if ( ((v19[0] + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      UnicodeString = 0;
      v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 8);
      v9 = RtlDosPathNameToNtPathName_U_WithStatus(v8, &UnicodeString, 0, 0);
      if ( v9 >= 0 )
      {
        v17 = 0;
        v10 = RtlCreateProcessParametersEx(&v17, &UnicodeString, 0, 0);
        if ( v10 >= 0 )
        {
          *(_DWORD *)(v17 + 1032) = NtCurrentPeb()->ProcessParameters[1].Flags;
          memset_0(v23, 0, 0x64u);
          v22 = 104;
          v13 = 3;
          v26 = 131080;
          v27 = 1;
          v29 = 0;
          v28 = &v13;
          v30 = 65539;
          v31 = 16;
          v33 = 0;
          v32 = &v24;
          v34 = 131077;
          Length = UnicodeString.Length;
          v37 = 0;
          Buffer = UnicodeString.Buffer;
          v38 = 131090;
          v39 = 8;
          v41 = 0;
          v40 = &qword_1800E6628;
          v25 = 136;
          v15 = 0;
          v16 = 0;
          memset_0(&v20, 0, 0x58u);
          v20 = 88;
          v21 = 4;
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &v16,
            0);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &v15,
            0);
          v11 = NtCreateUserProcess(&v15, &v16, 0x2000000, 0x2000000);
          if ( v11 >= 0 )
          {
            wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
              (char *)this + 40,
              &v15);
            wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
              this,
              v19);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v15);
            RtlFreeUnicodeString(&UnicodeString);
            IsSecureBioAvailable = 0;
            goto LABEL_22;
          }
          IsSecureBioAvailable = wil::details::in1diag3::Return_NtStatus(
                                   retaddr,
                                   (void *)0x2F2,
                                   (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\trustletcontrol.cpp",
                                   (const char *)(unsigned int)v11,
                                   0);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v15);
        }
        else
        {
          IsSecureBioAvailable = wil::details::in1diag3::Return_NtStatus(
                                   retaddr,
                                   (void *)0x2AB,
                                   (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\trustletcontrol.cpp",
                                   (const char *)(unsigned int)v10,
                                   0);
        }
        RtlFreeUnicodeString(&UnicodeString);
LABEL_22:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v19);
        return (unsigned int)IsSecureBioAvailable;
      }
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x298,
                    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\trustletcontrol.cpp",
                    (const char *)(unsigned int)v9,
                    v12);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x290,
                    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\trustletcontrol.cpp",
                    v6);
    }
    IsSecureBioAvailable = LastError;
    goto LABEL_22;
  }
  v3 = 632;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\trustletcontrol.cpp",
    (const char *)(unsigned int)IsSecureBioAvailable,
    v12);
  return (unsigned int)IsSecureBioAvailable;
}

```

## disassembly

```asm
0x180056378  mov     [rsp-8+arg_8], rbx
0x18005637d  mov     [rsp-8+arg_10], rsi
0x180056382  push    rbp
0x180056383  push    r14
0x180056385  push    r15
0x180056387  lea     rbp, [rsp-130h]
0x18005638f  sub     rsp, 230h
0x180056396  mov     rax, cs:__security_cookie
0x18005639d  xor     rax, rsp
0x1800563a0  mov     [rbp+140h+var_20], rax
0x1800563a7  mov     rsi, rcx
0x1800563aa  xor     r15d, r15d
0x1800563ad  mov     [rsp+240h+var_1DC], r15w
0x1800563b3  lea     rcx, [rsp+240h+var_1DC]; unsigned __int16 *
0x1800563b8  call    ?IsSecureBioAvailable@BioTrustlet@@SAJAEAG@Z; BioTrustlet::IsSecureBioAvailable(ushort &)
0x1800563bd  mov     ebx, eax
0x1800563bf  test    eax, eax
0x1800563c1  jns     short loc_1800563E3
0x1800563c3  mov     edx, 278h; void *
0x1800563c8  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\biometrics\\serv"...
0x1800563cf  mov     r9d, ebx; char *
0x1800563d2  mov     rcx, [rbp+148h]; this
0x1800563d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800563de  jmp     loc_180056740
0x1800563e3  test    byte ptr [rsp+240h+var_1DC], 1
0x1800563e8  jnz     short loc_1800563F4
0x1800563ea  mov     eax, 80070032h
0x1800563ef  jmp     loc_180056742
0x1800563f4  cmp     [rsi+18h], r15
0x1800563f8  jnz     short loc_180056436
0x1800563fa  lea     rdx, aWindirSystem32; "%windir%\\system32\\BioIso.exe"
0x180056401  lea     rcx, [rbp+140h+var_40]
0x180056408  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005640d  nop
0x18005640e  lea     rdx, [rbp+140h+var_40]
0x180056415  mov     rcx, rsi
0x180056418  call    ?SetPath@BioTrustlet@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; BioTrustlet::SetPath(std::wstring const &)
0x18005641d  mov     ebx, eax
0x18005641f  lea     rcx, [rbp+140h+var_40]
0x180056426  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005642b  test    ebx, ebx
0x18005642d  jns     short loc_180056436
0x18005642f  mov     edx, 283h
0x180056434  jmp     short loc_1800563C8
0x180056436  mov     rcx, rsi; this
0x180056439  call    ?TerminateRunningInstances@BioTrustlet@@AEAAJXZ; BioTrustlet::TerminateRunningInstances(void)
0x18005643e  test    eax, eax
0x180056440  jns     short loc_18005645D
0x180056442  mov     rcx, [rbp+148h]; this
0x180056449  mov     r9d, eax; char *
0x18005644c  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\biometrics\\serv"...
0x180056453  mov     edx, 288h; void *
0x180056458  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005645d  mov     r9d, 100001h; dwDesiredAccess
0x180056463  mov     r8d, 1; dwFlags
0x180056469  lea     rdx, aGlobalBioisose; "Global\\BioIsoServiceReadyEvent_9AEB573"...
0x180056470  xor     ecx, ecx; lpEventAttributes
0x180056472  call    cs:__imp_CreateEventExW
0x180056478  mov     [rbp+140h+var_1B0], rax
0x18005647c  inc     rax
0x18005647f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180056485  jnz     short loc_1800564A1
0x180056487  mov     rcx, [rbp+148h]; this
0x18005648e  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\biometrics\\serv"...
0x180056495  mov     edx, 290h; void *
0x18005649a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005649f  jmp     short loc_1800564E3
0x1800564a1  xorps   xmm0, xmm0
0x1800564a4  movups  xmmword ptr [rbp+140h+UnicodeString.Length], xmm0
0x1800564a8  lea     rcx, [rsi+8]
0x1800564ac  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800564b1  xor     r9d, r9d
0x1800564b4  xor     r8d, r8d
0x1800564b7  lea     rdx, [rbp+140h+UnicodeString]
0x1800564bb  mov     rcx, rax
0x1800564be  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800564c4  test    eax, eax
0x1800564c6  jns     short loc_1800564EA
0x1800564c8  mov     rcx, [rbp+148h]; this
0x1800564cf  mov     r9d, eax; char *
0x1800564d2  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\biometrics\\serv"...
0x1800564d9  mov     edx, 298h; void *
0x1800564de  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800564e3  mov     ebx, eax
0x1800564e5  jmp     loc_180056737
0x1800564ea  mov     [rsp+240h+var_1C8], r15
0x1800564ef  mov     dword ptr [rsp+240h+var_1F0], 1
0x1800564f7  mov     [rsp+240h+var_1F8], r15
0x1800564fc  mov     [rsp+240h+var_200], r15
0x180056501  mov     [rsp+240h+var_208], r15
0x180056506  mov     [rsp+240h+var_210], r15
0x18005650b  mov     [rsp+240h+var_218], r15
0x180056510  mov     qword ptr [rsp+240h+var_220], r15; int
0x180056515  xor     r9d, r9d
0x180056518  xor     r8d, r8d
0x18005651b  lea     rdx, [rbp+140h+UnicodeString]
0x18005651f  lea     rcx, [rsp+240h+var_1C8]
0x180056524  call    cs:__imp_RtlCreateProcessParametersEx
0x18005652a  test    eax, eax
0x18005652c  jns     short loc_18005655A
0x18005652e  mov     rcx, [rbp+148h]; this
0x180056535  mov     r9d, eax; char *
0x180056538  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\biometrics\\serv"...
0x18005653f  mov     edx, 2ABh; void *
0x180056544  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180056549  mov     ebx, eax
0x18005654b  lea     rcx, [rbp+140h+UnicodeString]; UnicodeString
0x18005654f  call    cs:__imp_RtlFreeUnicodeString
0x180056555  jmp     loc_180056737
0x18005655a  mov     rax, gs:60h
0x180056563  mov     rcx, [rax+20h]
0x180056567  mov     edx, [rcx+408h]
0x18005656d  mov     rax, [rsp+240h+var_1C8]
0x180056572  mov     [rax+408h], edx
0x180056578  xor     edx, edx; Val
0x18005657a  lea     r8d, [rdx+64h]; Size
0x18005657e  lea     rcx, [rbp+140h+var_13C]; void *
0x180056582  call    memset_0
0x180056587  mov     [rbp+140h+var_140], 68h ; 'h'
0x18005658e  mov     [rsp+240h+var_1E0], 3
0x180056593  mov     [rbp+140h+var_C8], 20008h
0x18005659b  mov     [rbp+140h+var_C0], 1
0x1800565a6  mov     [rbp+140h+var_B0], r15
0x1800565ad  lea     rax, [rsp+240h+var_1E0]
0x1800565b2  mov     [rbp+140h+var_B8], rax
0x1800565b9  mov     [rbp+140h+var_A8], 10003h
0x1800565c4  mov     [rbp+140h+var_A0], 10h
0x1800565cf  mov     [rbp+140h+var_90], r15
0x1800565d6  lea     rax, [rbp+140h+var_128]
0x1800565da  mov     [rbp+140h+var_98], rax
0x1800565e1  mov     [rbp+140h+var_88], 20005h
0x1800565ec  movzx   eax, [rbp+140h+UnicodeString.Length]
0x1800565f0  mov     [rbp+140h+var_80], rax
0x1800565f7  mov     [rbp+140h+var_70], r15
0x1800565fe  mov     rax, [rbp+140h+UnicodeString.Buffer]
0x180056602  mov     [rbp+140h+var_78], rax
0x180056609  mov     [rbp+140h+var_68], 20012h
0x180056614  mov     [rbp+140h+var_60], 8
0x18005661f  mov     [rbp+140h+var_50], r15
0x180056626  lea     rax, qword_1800E6628
0x18005662d  mov     [rbp+140h+var_58], rax
0x180056634  mov     [rbp+140h+var_D0], 88h
0x18005663c  mov     [rsp+240h+var_1D8], r15
0x180056641  mov     [rsp+240h+var_1D0], r15
0x180056646  mov     ebx, 58h ; 'X'
0x18005664b  mov     r8d, ebx; Size
0x18005664e  xor     edx, edx; Val
0x180056650  lea     rcx, [rbp+140h+var_1A0]; void *
0x180056654  call    memset_0
0x180056659  mov     [rbp+140h+var_1A0], rbx
0x18005665d  mov     [rbp+140h+var_190], 4
0x180056661  mov     rbx, [rsp+240h+var_1C8]
0x180056666  xor     edx, edx
0x180056668  lea     rcx, [rsp+240h+var_1D0]
0x18005666d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180056672  xor     edx, edx
0x180056674  lea     rcx, [rsp+240h+var_1D8]
0x180056679  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18005667e  lea     rax, [rbp+140h+var_D0]
0x180056682  mov     [rsp+240h+var_1F0], rax
0x180056687  lea     rax, [rbp+140h+var_1A0]
0x18005668b  mov     [rsp+240h+var_1F8], rax
0x180056690  mov     [rsp+240h+var_200], rbx
0x180056695  mov     dword ptr [rsp+240h+var_208], r15d
0x18005669a  mov     dword ptr [rsp+240h+var_210], r15d
0x18005669f  mov     [rsp+240h+var_218], r15
0x1800566a4  mov     qword ptr [rsp+240h+var_220], r15; int
0x1800566a9  mov     r8d, 2000000h
0x1800566af  mov     r9d, r8d
0x1800566b2  lea     rdx, [rsp+240h+var_1D0]
0x1800566b7  lea     rcx, [rsp+240h+var_1D8]
0x1800566bc  call    cs:__imp_NtCreateUserProcess
0x1800566c2  test    eax, eax
0x1800566c4  jns     short loc_1800566FC
0x1800566c6  mov     rcx, [rbp+148h]; this
0x1800566cd  mov     r9d, eax; char *
0x1800566d0  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\biometrics\\serv"...
0x1800566d7  mov     edx, 2F2h; void *
0x1800566dc  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800566e1  mov     ebx, eax
0x1800566e3  lea     rcx, [rsp+240h+var_1D0]
0x1800566e8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800566ed  lea     rcx, [rsp+240h+var_1D8]
0x1800566f2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800566f7  jmp     loc_18005654B
0x1800566fc  lea     rcx, [rsi+28h]
0x180056700  lea     rdx, [rsp+240h+var_1D8]
0x180056705  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18005670a  lea     rdx, [rbp+140h+var_1B0]
0x18005670e  mov     rcx, rsi
0x180056711  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180056716  lea     rcx, [rsp+240h+var_1D0]
0x18005671b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180056720  lea     rcx, [rsp+240h+var_1D8]
0x180056725  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005672a  lea     rcx, [rbp+140h+UnicodeString]; UnicodeString
0x18005672e  call    cs:__imp_RtlFreeUnicodeString
0x180056734  mov     ebx, r15d
0x180056737  lea     rcx, [rbp+140h+var_1B0]
0x18005673b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180056740  mov     eax, ebx
0x180056742  mov     rcx, [rbp+140h+var_20]
0x180056749  xor     rcx, rsp; StackCookie
0x18005674c  call    __security_check_cookie
0x180056751  lea     r11, [rsp+240h+var_10]
0x180056759  mov     rbx, [r11+28h]
0x18005675d  mov     rsi, [r11+30h]
0x180056761  mov     rsp, r11
0x180056764  pop     r15
0x180056766  pop     r14
0x180056768  pop     rbp
0x180056769  retn
```

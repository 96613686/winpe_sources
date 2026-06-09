# ShellMRTHelper::Common::ConvertMsAppXUriToMsResourceUri(Windows::Foundation::IUriRuntimeClass *,ushort * *)

- ea: `0x18031ce10`
- end: `0x18031d113`
- name: `?ConvertMsAppXUriToMsResourceUri@Common@ShellMRTHelper@@YAJPEAUIUriRuntimeClass@Foundation@Windows@@PEAPEAG@Z`
- size: `771`
- prototype: `__int64 __fastcall(ShellMRTHelper::Common *__hidden this, struct Windows::Foundation::IUriRuntimeClass *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007abd0`

## callees

- `0x180027ee4`
- `0x180036250`
- `0x18003c5e4`
- `0x1800afabc`
- `0x18031ce10`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031ce3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031ce9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031ced6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031cf03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031cf3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d0db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d0e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d0fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031ce3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031ce9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031ced6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031cf03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031cf3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d0db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d0e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d0fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18031ce85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18031ceed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18031cf56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18031ce85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18031ceed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18031cf56`

## string_xrefs

- `0x18031ce63`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x18031cec1`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x18031cf29`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x18031cf97`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`

## pseudocode

```c
__int64 __fastcall ShellMRTHelper::Common::ConvertMsAppXUriToMsResourceUri(
        ShellMRTHelper::Common *this,
        struct Windows::Foundation::IUriRuntimeClass *a2,
        unsigned __int16 **a3)
{
  __int64 (__fastcall *v5)(ShellMRTHelper::Common *, HSTRING *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  PCWSTR StringRawBuffer; // r14
  __int64 (__fastcall *v9)(ShellMRTHelper::Common *, HSTRING *); // rbx
  int v10; // eax
  PCWSTR v11; // r15
  __int64 (__fastcall *v12)(ShellMRTHelper::Common *, HSTRING *); // rbx
  int v13; // eax
  PCWSTR v14; // rdi
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rax
  HSTRING v19; // [rsp+20h] [rbp-38h] BYREF
  HSTRING v20; // [rsp+28h] [rbp-30h] BYREF
  HSTRING string; // [rsp+30h] [rbp-28h] BYREF
  __int64 v22; // [rsp+38h] [rbp-20h] BYREF
  __int64 v23; // [rsp+40h] [rbp-18h]
  __int64 v24; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  UINT32 v26; // [rsp+A0h] [rbp+48h] BYREF
  UINT32 length; // [rsp+A8h] [rbp+50h] BYREF
  UINT32 v28; // [rsp+B0h] [rbp+58h] BYREF
  int v29; // [rsp+B8h] [rbp+60h] BYREF

  *(_QWORD *)a2 = 0;
  string = 0;
  v5 = *(__int64 (__fastcall **)(ShellMRTHelper::Common *, HSTRING *))(*(_QWORD *)this + 104LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = v5(this, &string);
  v7 = v6;
  if ( v6 >= 0 )
  {
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    v19 = 0;
    v9 = *(__int64 (__fastcall **)(ShellMRTHelper::Common *, HSTRING *))(*(_QWORD *)this + 112LL);
    WindowsDeleteString(0);
    v19 = 0;
    v10 = v9(this, &v19);
    v7 = v10;
    if ( v10 >= 0 )
    {
      v28 = 0;
      v11 = WindowsGetStringRawBuffer(v19, &v28);
      v20 = 0;
      v12 = *(__int64 (__fastcall **)(ShellMRTHelper::Common *, HSTRING *))(*(_QWORD *)this + 88LL);
      WindowsDeleteString(0);
      v20 = 0;
      v13 = v12(this, &v20);
      v7 = v13;
      if ( v13 >= 0 )
      {
        v26 = 0;
        v14 = WindowsGetStringRawBuffer(v20, &v26);
        v22 = 0;
        v23 = 0;
        v24 = 0;
        v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                &v22,
                L"ms-resource:",
                length + 20 + v28 + v26);
        v7 = v15;
        if ( v15 >= 0 )
        {
          v29 = 47;
          v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                  &v22,
                  &v29,
                  1);
          v7 = v15;
          if ( v15 >= 0 )
          {
            v29 = 47;
            v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                    &v22,
                    &v29,
                    1);
            v7 = v15;
            if ( v15 >= 0 )
            {
              if ( v26
                && (v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                            &v22,
                            v14,
                            v26),
                    v7 = v15,
                    v15 < 0) )
              {
                v16 = 131;
              }
              else
              {
                v29 = 47;
                v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                        &v22,
                        &v29,
                        1);
                v7 = v15;
                if ( v15 >= 0 )
                {
                  v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                          &v22,
                          L"files",
                          5);
                  v7 = v15;
                  if ( v15 >= 0 )
                  {
                    v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                            &v22,
                            StringRawBuffer,
                            length);
                    v7 = v15;
                    if ( v15 >= 0 )
                    {
                      if ( !v28
                        || (v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                                    &v22,
                                    v11,
                                    v28),
                            v7 = v15,
                            v15 >= 0) )
                      {
                        v17 = v22;
                        v22 = 0;
                        v24 = 0;
                        v23 = 0;
                        *(_QWORD *)a2 = v17;
                        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v22);
                        WindowsDeleteString(v20);
                        v20 = 0;
                        WindowsDeleteString(v19);
                        v7 = 0;
                        goto LABEL_29;
                      }
                      v16 = 143;
                    }
                    else
                    {
                      v16 = 138;
                    }
                  }
                  else
                  {
                    v16 = 135;
                  }
                }
                else
                {
                  v16 = 134;
                }
              }
            }
            else
            {
              v16 = 127;
            }
          }
          else
          {
            v16 = 126;
          }
        }
        else
        {
          v16 = 125;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
          (const char *)(unsigned int)v15,
          (int)v19);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v22);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
          (const char *)(unsigned int)v13,
          (int)v19);
      }
      WindowsDeleteString(v20);
      v20 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
        (const char *)(unsigned int)v10,
        (int)v19);
    }
    WindowsDeleteString(v19);
LABEL_29:
    v19 = 0;
    goto LABEL_30;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x68,
    (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
    (const char *)(unsigned int)v6,
    (int)v19);
LABEL_30:
  WindowsDeleteString(string);
  return v7;
}

```

## disassembly

```asm
0x18031ce10  push    rbp
0x18031ce12  push    rbx
0x18031ce13  push    rsi
0x18031ce14  push    rdi
0x18031ce15  push    r12
0x18031ce17  push    r13
0x18031ce19  push    r14
0x18031ce1b  push    r15
0x18031ce1d  mov     rbp, rsp
0x18031ce20  sub     rsp, 58h
0x18031ce24  mov     rsi, rdx
0x18031ce27  mov     rdi, rcx
0x18031ce2a  xor     r12d, r12d
0x18031ce2d  mov     [rdx], r12
0x18031ce30  mov     [rbp+string], r12
0x18031ce34  mov     rax, [rcx]
0x18031ce37  mov     rbx, [rax+68h]
0x18031ce3b  xor     ecx, ecx; string
0x18031ce3d  call    cs:__imp_WindowsDeleteString
0x18031ce43  mov     [rbp+string], r12
0x18031ce47  lea     rdx, [rbp+string]
0x18031ce4b  mov     rcx, rdi
0x18031ce4e  mov     rax, rbx
0x18031ce51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031ce56  mov     ebx, eax
0x18031ce58  test    eax, eax
0x18031ce5a  jns     short loc_18031CE79
0x18031ce5c  mov     rcx, [rbp+40h]; this
0x18031ce60  mov     r9d, eax; char *
0x18031ce63  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18031ce6a  lea     edx, [r12+68h]; void *
0x18031ce6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18031ce74  jmp     loc_18031D0F6
0x18031ce79  mov     [rbp+length], r12d
0x18031ce7d  lea     rdx, [rbp+length]; length
0x18031ce81  mov     rcx, [rbp+string]; string
0x18031ce85  call    cs:__imp_WindowsGetStringRawBuffer
0x18031ce8b  mov     r14, rax
0x18031ce8e  mov     [rbp+var_38], r12
0x18031ce92  mov     rcx, [rdi]
0x18031ce95  mov     rbx, [rcx+70h]
0x18031ce99  xor     ecx, ecx; string
0x18031ce9b  call    cs:__imp_WindowsDeleteString
0x18031cea1  mov     [rbp+var_38], r12
0x18031cea5  lea     rdx, [rbp+var_38]
0x18031cea9  mov     rcx, rdi
0x18031ceac  mov     rax, rbx
0x18031ceaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031ceb4  mov     ebx, eax
0x18031ceb6  test    eax, eax
0x18031ceb8  jns     short loc_18031CEE1
0x18031ceba  mov     rcx, [rbp+40h]; this
0x18031cebe  mov     r9d, eax; char *
0x18031cec1  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18031cec8  mov     edx, 6Eh ; 'n'; void *
0x18031cecd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18031ced2  mov     rcx, [rbp+var_38]; string
0x18031ced6  call    cs:__imp_WindowsDeleteString
0x18031cedc  jmp     loc_18031D0F2
0x18031cee1  mov     [rbp+arg_10], r12d
0x18031cee5  lea     rdx, [rbp+arg_10]; length
0x18031cee9  mov     rcx, [rbp+var_38]; string
0x18031ceed  call    cs:__imp_WindowsGetStringRawBuffer
0x18031cef3  mov     r15, rax
0x18031cef6  mov     [rbp+var_30], r12
0x18031cefa  mov     rcx, [rdi]
0x18031cefd  mov     rbx, [rcx+58h]
0x18031cf01  xor     ecx, ecx; string
0x18031cf03  call    cs:__imp_WindowsDeleteString
0x18031cf09  mov     [rbp+var_30], r12
0x18031cf0d  lea     rdx, [rbp+var_30]
0x18031cf11  mov     rcx, rdi
0x18031cf14  mov     rax, rbx
0x18031cf17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031cf1c  mov     ebx, eax
0x18031cf1e  test    eax, eax
0x18031cf20  jns     short loc_18031CF4A
0x18031cf22  mov     rcx, [rbp+40h]; this
0x18031cf26  mov     r9d, eax; char *
0x18031cf29  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18031cf30  mov     edx, 74h ; 't'; void *
0x18031cf35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18031cf3a  mov     rcx, [rbp+var_30]; string
0x18031cf3e  call    cs:__imp_WindowsDeleteString
0x18031cf44  mov     [rbp+var_30], r12
0x18031cf48  jmp     short loc_18031CED2
0x18031cf4a  mov     [rbp+arg_0], r12d
0x18031cf4e  lea     rdx, [rbp+arg_0]; length
0x18031cf52  mov     rcx, [rbp+var_30]; string
0x18031cf56  call    cs:__imp_WindowsGetStringRawBuffer
0x18031cf5c  mov     rdi, rax
0x18031cf5f  mov     [rbp+var_20], r12
0x18031cf63  mov     [rbp+var_18], r12
0x18031cf67  mov     [rbp+var_10], r12
0x18031cf6b  mov     r8d, [rbp+arg_0]
0x18031cf6f  add     r8d, [rbp+arg_10]
0x18031cf73  mov     ecx, [rbp+length]
0x18031cf76  add     ecx, 14h
0x18031cf79  add     r8d, ecx
0x18031cf7c  lea     rdx, ?c_msResourceUriScheme@Common@ShellMRTHelper@@3QBGB; "ms-resource:"
0x18031cf83  lea     rcx, [rbp+var_20]
0x18031cf87  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18031cf8c  mov     ebx, eax
0x18031cf8e  test    eax, eax
0x18031cf90  jns     short loc_18031CFB5
0x18031cf92  mov     edx, 7Dh ; '}'; void *
0x18031cf97  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18031cf9e  mov     r9d, eax; char *
0x18031cfa1  mov     rcx, [rbp+40h]; this
0x18031cfa5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18031cfaa  lea     rcx, [rbp+var_20]
0x18031cfae  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18031cfb3  jmp     short loc_18031CF3A
0x18031cfb5  mov     [rbp+arg_18], 2Fh ; '/'
0x18031cfbc  mov     r13d, 1
0x18031cfc2  mov     r8d, r13d
0x18031cfc5  lea     rdx, [rbp+arg_18]
0x18031cfc9  lea     rcx, [rbp+var_20]
0x18031cfcd  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18031cfd2  mov     ebx, eax
0x18031cfd4  test    eax, eax
0x18031cfd6  jns     short loc_18031CFDE
0x18031cfd8  lea     edx, [r13+7Dh]
0x18031cfdc  jmp     short loc_18031CF97
0x18031cfde  mov     [rbp+arg_18], 2Fh ; '/'
0x18031cfe5  mov     r8, r13
0x18031cfe8  lea     rdx, [rbp+arg_18]
0x18031cfec  lea     rcx, [rbp+var_20]
0x18031cff0  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18031cff5  mov     ebx, eax
0x18031cff7  test    eax, eax
0x18031cff9  jns     short loc_18031D002
0x18031cffb  mov     edx, 7Fh
0x18031d000  jmp     short loc_18031CF97
0x18031d002  mov     eax, [rbp+arg_0]
0x18031d005  test    eax, eax
0x18031d007  jz      short loc_18031D028
0x18031d009  mov     r8d, eax
0x18031d00c  mov     rdx, rdi
0x18031d00f  lea     rcx, [rbp+var_20]
0x18031d013  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18031d018  mov     ebx, eax
0x18031d01a  test    eax, eax
0x18031d01c  jns     short loc_18031D028
0x18031d01e  mov     edx, 83h
0x18031d023  jmp     loc_18031CF97
0x18031d028  mov     [rbp+arg_18], 2Fh ; '/'
0x18031d02f  mov     r8, r13
0x18031d032  lea     rdx, [rbp+arg_18]
0x18031d036  lea     rcx, [rbp+var_20]
0x18031d03a  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18031d03f  mov     ebx, eax
0x18031d041  test    eax, eax
0x18031d043  jns     short loc_18031D04F
0x18031d045  mov     edx, 86h
0x18031d04a  jmp     loc_18031CF97
0x18031d04f  mov     r8d, 5
0x18031d055  lea     rdx, ?c_msResourceUriFilesPathPrefix@Common@ShellMRTHelper@@3QBGB; "files"
0x18031d05c  lea     rcx, [rbp+var_20]
0x18031d060  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18031d065  mov     ebx, eax
0x18031d067  test    eax, eax
0x18031d069  jns     short loc_18031D075
0x18031d06b  mov     edx, 87h
0x18031d070  jmp     loc_18031CF97
0x18031d075  mov     r8d, [rbp+length]
0x18031d079  mov     rdx, r14
0x18031d07c  lea     rcx, [rbp+var_20]
0x18031d080  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18031d085  mov     ebx, eax
0x18031d087  test    eax, eax
0x18031d089  jns     short loc_18031D095
0x18031d08b  mov     edx, 8Ah
0x18031d090  jmp     loc_18031CF97
0x18031d095  mov     eax, [rbp+arg_10]
0x18031d098  test    eax, eax
0x18031d09a  jz      short loc_18031D0BB
0x18031d09c  mov     r8d, eax
0x18031d09f  mov     rdx, r15
0x18031d0a2  lea     rcx, [rbp+var_20]
0x18031d0a6  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18031d0ab  mov     ebx, eax
0x18031d0ad  test    eax, eax
0x18031d0af  jns     short loc_18031D0BB
0x18031d0b1  mov     edx, 8Fh
0x18031d0b6  jmp     loc_18031CF97
0x18031d0bb  mov     rax, [rbp+var_20]
0x18031d0bf  mov     [rbp+var_20], r12
0x18031d0c3  mov     [rbp+var_10], r12
0x18031d0c7  mov     [rbp+var_18], r12
0x18031d0cb  mov     [rsi], rax
0x18031d0ce  lea     rcx, [rbp+var_20]
0x18031d0d2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18031d0d7  mov     rcx, [rbp+var_30]; string
0x18031d0db  call    cs:__imp_WindowsDeleteString
0x18031d0e1  mov     [rbp+var_30], r12
0x18031d0e5  mov     rcx, [rbp+var_38]; string
0x18031d0e9  call    cs:__imp_WindowsDeleteString
0x18031d0ef  mov     ebx, r12d
0x18031d0f2  mov     [rbp+var_38], r12
0x18031d0f6  mov     rcx, [rbp+string]; string
0x18031d0fa  call    cs:__imp_WindowsDeleteString
0x18031d100  mov     eax, ebx
0x18031d102  add     rsp, 58h
0x18031d106  pop     r15
0x18031d108  pop     r14
0x18031d10a  pop     r13
0x18031d10c  pop     r12
0x18031d10e  pop     rdi
0x18031d10f  pop     rsi
0x18031d110  pop     rbx
0x18031d111  pop     rbp
0x18031d112  retn
```

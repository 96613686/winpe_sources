# ShellMRTHelper::Common::ConvertMsAppXUriToMsResourceUri(Windows::Foundation::IUriRuntimeClass *,ushort * *)

- ea: `0x18066d540`
- end: `0x18066d843`
- name: `?ConvertMsAppXUriToMsResourceUri@Common@ShellMRTHelper@@YAJPEAUIUriRuntimeClass@Foundation@Windows@@PEAPEAG@Z`
- size: `771`
- prototype: `__int64 __fastcall(ShellMRTHelper::Common *__hidden this, struct Windows::Foundation::IUriRuntimeClass *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ca8b0`

## callees

- `0x1800237c8`
- `0x180086ac0`
- `0x18008a6f0`
- `0x180140530`
- `0x18066d540`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066d56d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066d5cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066d606`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066d633`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066d66e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066d80b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066d819`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066d82a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066d56d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066d5cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066d606`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066d633`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066d66e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066d80b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066d819`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18066d82a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18066d5b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18066d61d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18066d686`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18066d5b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18066d61d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18066d686`

## string_xrefs

- `0x18066d590`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x18066d5ee`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x18066d656`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x18066d6cb`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`

## pseudocode

```c
__int64 __fastcall ShellMRTHelper::Common::ConvertMsAppXUriToMsResourceUri(
        ShellMRTHelper::Common *this,
        struct Windows::Foundation::IUriRuntimeClass *a2,
        unsigned __int16 **a3)
{
  __int64 v5; // rax
  __int64 (__fastcall *v6)(ShellMRTHelper::Common *, HSTRING *); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // rcx
  PCWSTR v11; // r14
  __int64 (__fastcall *v12)(ShellMRTHelper::Common *, HSTRING *); // rbx
  int v13; // eax
  PCWSTR v14; // rax
  __int64 v15; // rcx
  PCWSTR v16; // r15
  __int64 (__fastcall *v17)(ShellMRTHelper::Common *, HSTRING *); // rbx
  int v18; // eax
  PCWSTR v19; // rdi
  int v20; // eax
  __int64 v21; // rdx
  HSTRING v23; // [rsp+20h] [rbp-38h] BYREF
  HSTRING v24; // [rsp+28h] [rbp-30h] BYREF
  HSTRING string; // [rsp+30h] [rbp-28h] BYREF
  __int64 v26; // [rsp+38h] [rbp-20h] BYREF
  __int64 v27; // [rsp+40h] [rbp-18h]
  __int64 v28; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  UINT32 v30; // [rsp+A0h] [rbp+48h] BYREF
  UINT32 length; // [rsp+A8h] [rbp+50h] BYREF
  UINT32 v32; // [rsp+B0h] [rbp+58h] BYREF
  int v33; // [rsp+B8h] [rbp+60h] BYREF

  *(_QWORD *)a2 = 0;
  v5 = *(_QWORD *)this;
  string = 0;
  v6 = *(__int64 (__fastcall **)(ShellMRTHelper::Common *, HSTRING *))(v5 + 104);
  WindowsDeleteString(0);
  string = 0;
  v7 = v6(this, &string);
  v8 = v7;
  if ( v7 >= 0 )
  {
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    v10 = *(_QWORD *)this;
    v11 = StringRawBuffer;
    v23 = 0;
    v12 = *(__int64 (__fastcall **)(ShellMRTHelper::Common *, HSTRING *))(v10 + 112);
    WindowsDeleteString(0);
    v23 = 0;
    v13 = v12(this, &v23);
    v8 = v13;
    if ( v13 >= 0 )
    {
      v32 = 0;
      v14 = WindowsGetStringRawBuffer(v23, &v32);
      v15 = *(_QWORD *)this;
      v16 = v14;
      v24 = 0;
      v17 = *(__int64 (__fastcall **)(ShellMRTHelper::Common *, HSTRING *))(v15 + 88);
      WindowsDeleteString(0);
      v24 = 0;
      v18 = v17(this, &v24);
      v8 = v18;
      if ( v18 >= 0 )
      {
        v30 = 0;
        v19 = WindowsGetStringRawBuffer(v24, &v30);
        v26 = 0;
        v27 = 0;
        v28 = 0;
        v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                &v26,
                L"ms-resource:",
                length + 20 + v32 + v30);
        v8 = v20;
        if ( v20 >= 0 )
        {
          v33 = 47;
          v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                  &v26,
                  &v33,
                  1);
          v8 = v20;
          if ( v20 >= 0 )
          {
            v33 = 47;
            v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                    &v26,
                    &v33,
                    1);
            v8 = v20;
            if ( v20 >= 0 )
            {
              if ( v30
                && (v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                            &v26,
                            v19,
                            v30),
                    v8 = v20,
                    v20 < 0) )
              {
                v21 = 131;
              }
              else
              {
                v33 = 47;
                v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                        &v26,
                        &v33,
                        1);
                v8 = v20;
                if ( v20 >= 0 )
                {
                  v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                          &v26,
                          L"files",
                          5);
                  v8 = v20;
                  if ( v20 >= 0 )
                  {
                    v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                            &v26,
                            v11,
                            length);
                    v8 = v20;
                    if ( v20 >= 0 )
                    {
                      if ( !v32
                        || (v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                                    &v26,
                                    v16,
                                    v32),
                            v8 = v20,
                            v20 >= 0) )
                      {
                        *(_QWORD *)a2 = v26;
                        v26 = 0;
                        v28 = 0;
                        v27 = 0;
                        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v26);
                        WindowsDeleteString(v24);
                        v24 = 0;
                        WindowsDeleteString(v23);
                        v8 = 0;
                        goto LABEL_29;
                      }
                      v21 = 143;
                    }
                    else
                    {
                      v21 = 138;
                    }
                  }
                  else
                  {
                    v21 = 135;
                  }
                }
                else
                {
                  v21 = 134;
                }
              }
            }
            else
            {
              v21 = 127;
            }
          }
          else
          {
            v21 = 126;
          }
        }
        else
        {
          v21 = 125;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
          (const char *)(unsigned int)v20,
          (int)v23);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v26);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
          (const char *)(unsigned int)v18,
          (int)v23);
      }
      WindowsDeleteString(v24);
      v24 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
        (const char *)(unsigned int)v13,
        (int)v23);
    }
    WindowsDeleteString(v23);
LABEL_29:
    v23 = 0;
    goto LABEL_30;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x68,
    (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
    (const char *)(unsigned int)v7,
    (int)v23);
LABEL_30:
  WindowsDeleteString(string);
  return v8;
}

```

## disassembly

```asm
0x18066d540  push    rbp
0x18066d542  push    rbx
0x18066d543  push    rsi
0x18066d544  push    rdi
0x18066d545  push    r12
0x18066d547  push    r13
0x18066d549  push    r14
0x18066d54b  push    r15
0x18066d54d  mov     rbp, rsp
0x18066d550  sub     rsp, 58h
0x18066d554  xor     r12d, r12d
0x18066d557  mov     rdi, rcx
0x18066d55a  mov     [rdx], r12
0x18066d55d  mov     rsi, rdx
0x18066d560  mov     rax, [rcx]
0x18066d563  xor     ecx, ecx; string
0x18066d565  mov     [rbp+string], r12
0x18066d569  mov     rbx, [rax+68h]
0x18066d56d  call    cs:__imp_WindowsDeleteString
0x18066d573  lea     rdx, [rbp+string]
0x18066d577  mov     [rbp+string], r12
0x18066d57b  mov     rcx, rdi
0x18066d57e  mov     rax, rbx
0x18066d581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18066d586  mov     ebx, eax
0x18066d588  test    eax, eax
0x18066d58a  jns     short loc_18066D5A9
0x18066d58c  mov     rcx, [rbp+40h]; this
0x18066d590  lea     r8, aShellcommondes_7; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18066d597  mov     r9d, eax; char *
0x18066d59a  lea     edx, [r12+68h]; void *
0x18066d59f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18066d5a4  jmp     loc_18066D826
0x18066d5a9  mov     rcx, [rbp+string]; string
0x18066d5ad  lea     rdx, [rbp+length]; length
0x18066d5b1  mov     [rbp+length], r12d
0x18066d5b5  call    cs:__imp_WindowsGetStringRawBuffer
0x18066d5bb  mov     rcx, [rdi]
0x18066d5be  mov     r14, rax
0x18066d5c1  mov     [rbp+var_38], r12
0x18066d5c5  mov     rbx, [rcx+70h]
0x18066d5c9  xor     ecx, ecx; string
0x18066d5cb  call    cs:__imp_WindowsDeleteString
0x18066d5d1  lea     rdx, [rbp+var_38]
0x18066d5d5  mov     [rbp+var_38], r12
0x18066d5d9  mov     rcx, rdi
0x18066d5dc  mov     rax, rbx
0x18066d5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18066d5e4  mov     ebx, eax
0x18066d5e6  test    eax, eax
0x18066d5e8  jns     short loc_18066D611
0x18066d5ea  mov     rcx, [rbp+40h]; this
0x18066d5ee  lea     r8, aShellcommondes_7; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18066d5f5  mov     r9d, eax; char *
0x18066d5f8  mov     edx, 6Eh ; 'n'; void *
0x18066d5fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18066d602  mov     rcx, [rbp+var_38]; string
0x18066d606  call    cs:__imp_WindowsDeleteString
0x18066d60c  jmp     loc_18066D822
0x18066d611  mov     rcx, [rbp+var_38]; string
0x18066d615  lea     rdx, [rbp+arg_10]; length
0x18066d619  mov     [rbp+arg_10], r12d
0x18066d61d  call    cs:__imp_WindowsGetStringRawBuffer
0x18066d623  mov     rcx, [rdi]
0x18066d626  mov     r15, rax
0x18066d629  mov     [rbp+var_30], r12
0x18066d62d  mov     rbx, [rcx+58h]
0x18066d631  xor     ecx, ecx; string
0x18066d633  call    cs:__imp_WindowsDeleteString
0x18066d639  lea     rdx, [rbp+var_30]
0x18066d63d  mov     [rbp+var_30], r12
0x18066d641  mov     rcx, rdi
0x18066d644  mov     rax, rbx
0x18066d647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18066d64c  mov     ebx, eax
0x18066d64e  test    eax, eax
0x18066d650  jns     short loc_18066D67A
0x18066d652  mov     rcx, [rbp+40h]; this
0x18066d656  lea     r8, aShellcommondes_7; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18066d65d  mov     r9d, eax; char *
0x18066d660  mov     edx, 74h ; 't'; void *
0x18066d665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18066d66a  mov     rcx, [rbp+var_30]; string
0x18066d66e  call    cs:__imp_WindowsDeleteString
0x18066d674  mov     [rbp+var_30], r12
0x18066d678  jmp     short loc_18066D602
0x18066d67a  mov     rcx, [rbp+var_30]; string
0x18066d67e  lea     rdx, [rbp+arg_0]; length
0x18066d682  mov     [rbp+arg_0], r12d
0x18066d686  call    cs:__imp_WindowsGetStringRawBuffer
0x18066d68c  mov     ecx, [rbp+length]
0x18066d68f  lea     rdx, ?c_msResourceUriScheme@Common@ShellMRTHelper@@3QBGB; "ms-resource:"
0x18066d696  mov     r8d, [rbp+arg_0]
0x18066d69a  add     ecx, 14h
0x18066d69d  add     r8d, [rbp+arg_10]
0x18066d6a1  mov     rdi, rax
0x18066d6a4  add     r8d, ecx
0x18066d6a7  mov     [rbp+var_20], r12
0x18066d6ab  lea     rcx, [rbp+var_20]
0x18066d6af  mov     [rbp+var_18], r12
0x18066d6b3  mov     [rbp+var_10], r12
0x18066d6b7  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18066d6bc  mov     ebx, eax
0x18066d6be  test    eax, eax
0x18066d6c0  jns     short loc_18066D6E5
0x18066d6c2  mov     edx, 7Dh ; '}'; void *
0x18066d6c7  mov     rcx, [rbp+40h]; this
0x18066d6cb  lea     r8, aShellcommondes_7; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18066d6d2  mov     r9d, eax; char *
0x18066d6d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18066d6da  lea     rcx, [rbp+var_20]
0x18066d6de  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18066d6e3  jmp     short loc_18066D66A
0x18066d6e5  mov     r13d, 1
0x18066d6eb  mov     [rbp+arg_18], 2Fh ; '/'
0x18066d6f2  mov     r8d, r13d
0x18066d6f5  lea     rdx, [rbp+arg_18]
0x18066d6f9  lea     rcx, [rbp+var_20]
0x18066d6fd  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18066d702  mov     ebx, eax
0x18066d704  test    eax, eax
0x18066d706  jns     short loc_18066D70E
0x18066d708  lea     edx, [r13+7Dh]
0x18066d70c  jmp     short loc_18066D6C7
0x18066d70e  mov     r8, r13
0x18066d711  mov     [rbp+arg_18], 2Fh ; '/'
0x18066d718  lea     rdx, [rbp+arg_18]
0x18066d71c  lea     rcx, [rbp+var_20]
0x18066d720  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18066d725  mov     ebx, eax
0x18066d727  test    eax, eax
0x18066d729  jns     short loc_18066D732
0x18066d72b  mov     edx, 7Fh
0x18066d730  jmp     short loc_18066D6C7
0x18066d732  mov     eax, [rbp+arg_0]
0x18066d735  test    eax, eax
0x18066d737  jz      short loc_18066D758
0x18066d739  mov     r8d, eax
0x18066d73c  lea     rcx, [rbp+var_20]
0x18066d740  mov     rdx, rdi
0x18066d743  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18066d748  mov     ebx, eax
0x18066d74a  test    eax, eax
0x18066d74c  jns     short loc_18066D758
0x18066d74e  mov     edx, 83h
0x18066d753  jmp     loc_18066D6C7
0x18066d758  mov     r8, r13
0x18066d75b  mov     [rbp+arg_18], 2Fh ; '/'
0x18066d762  lea     rdx, [rbp+arg_18]
0x18066d766  lea     rcx, [rbp+var_20]
0x18066d76a  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18066d76f  mov     ebx, eax
0x18066d771  test    eax, eax
0x18066d773  jns     short loc_18066D77F
0x18066d775  mov     edx, 86h
0x18066d77a  jmp     loc_18066D6C7
0x18066d77f  mov     r8d, 5
0x18066d785  lea     rdx, ?c_msResourceUriFilesPathPrefix@Common@ShellMRTHelper@@3QBGB; "files"
0x18066d78c  lea     rcx, [rbp+var_20]
0x18066d790  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18066d795  mov     ebx, eax
0x18066d797  test    eax, eax
0x18066d799  jns     short loc_18066D7A5
0x18066d79b  mov     edx, 87h
0x18066d7a0  jmp     loc_18066D6C7
0x18066d7a5  mov     r8d, [rbp+length]
0x18066d7a9  lea     rcx, [rbp+var_20]
0x18066d7ad  mov     rdx, r14
0x18066d7b0  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18066d7b5  mov     ebx, eax
0x18066d7b7  test    eax, eax
0x18066d7b9  jns     short loc_18066D7C5
0x18066d7bb  mov     edx, 8Ah
0x18066d7c0  jmp     loc_18066D6C7
0x18066d7c5  mov     eax, [rbp+arg_10]
0x18066d7c8  test    eax, eax
0x18066d7ca  jz      short loc_18066D7EB
0x18066d7cc  mov     r8d, eax
0x18066d7cf  lea     rcx, [rbp+var_20]
0x18066d7d3  mov     rdx, r15
0x18066d7d6  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18066d7db  mov     ebx, eax
0x18066d7dd  test    eax, eax
0x18066d7df  jns     short loc_18066D7EB
0x18066d7e1  mov     edx, 8Fh
0x18066d7e6  jmp     loc_18066D6C7
0x18066d7eb  mov     rax, [rbp+var_20]
0x18066d7ef  lea     rcx, [rbp+var_20]
0x18066d7f3  mov     [rsi], rax
0x18066d7f6  mov     [rbp+var_20], r12
0x18066d7fa  mov     [rbp+var_10], r12
0x18066d7fe  mov     [rbp+var_18], r12
0x18066d802  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18066d807  mov     rcx, [rbp+var_30]; string
0x18066d80b  call    cs:__imp_WindowsDeleteString
0x18066d811  mov     rcx, [rbp+var_38]; string
0x18066d815  mov     [rbp+var_30], r12
0x18066d819  call    cs:__imp_WindowsDeleteString
0x18066d81f  mov     ebx, r12d
0x18066d822  mov     [rbp+var_38], r12
0x18066d826  mov     rcx, [rbp+string]; string
0x18066d82a  call    cs:__imp_WindowsDeleteString
0x18066d830  mov     eax, ebx
0x18066d832  add     rsp, 58h
0x18066d836  pop     r15
0x18066d838  pop     r14
0x18066d83a  pop     r13
0x18066d83c  pop     r12
0x18066d83e  pop     rdi
0x18066d83f  pop     rsi
0x18066d840  pop     rbx
0x18066d841  pop     rbp
0x18066d842  retn
```

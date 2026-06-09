# SsAddCertMappingToRegistry

- ea: `0x180024644`
- end: `0x180024db2`
- name: `SsAddCertMappingToRegistry`
- size: `1902`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180026524`
- `0x180031c8c`
- `0x180032f00`

## callees

- `0x180012ef0`
- `0x18001deb0`
- `0x1800214a4`
- `0x180024644`
- `0x1800268d8`

## import_xrefs

- `ntdll!RtlWriteRegistryValue` at `0x180024d2b`
- `ntdll!RtlWriteRegistryValue` at `0x180024d2b`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002474f`
- `ntdll!RtlSetEnvironmentVariable` at `0x180024812`
- `ntdll!RtlSetEnvironmentVariable` at `0x180024886`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800248fa`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002496e`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800249e2`
- `ntdll!RtlSetEnvironmentVariable` at `0x180024a56`
- `ntdll!RtlSetEnvironmentVariable` at `0x180024aca`
- `ntdll!RtlSetEnvironmentVariable` at `0x180024b3e`
- `ntdll!RtlSetEnvironmentVariable` at `0x180024c06`
- `ntdll!RtlSetEnvironmentVariable` at `0x180024ccd`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002474f`
- `ntdll!RtlSetEnvironmentVariable` at `0x180024812`
- `ntdll!RtlSetEnvironmentVariable` at `0x180024886`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800248fa`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002496e`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800249e2`
- `ntdll!RtlSetEnvironmentVariable` at `0x180024a56`
- `ntdll!RtlSetEnvironmentVariable` at `0x180024aca`
- `ntdll!RtlSetEnvironmentVariable` at `0x180024b3e`
- `ntdll!RtlSetEnvironmentVariable` at `0x180024c06`
- `ntdll!RtlSetEnvironmentVariable` at `0x180024ccd`
- `ntdll!RtlCreateEnvironment` at `0x1800246dc`
- `ntdll!RtlCreateEnvironment` at `0x1800246dc`
- `ntdll!RtlIntegerToUnicodeString` at `0x180024bb3`
- `ntdll!RtlIntegerToUnicodeString` at `0x180024c7a`
- `ntdll!RtlIntegerToUnicodeString` at `0x180024bb3`
- `ntdll!RtlIntegerToUnicodeString` at `0x180024c7a`
- `ntdll!RtlDestroyEnvironment` at `0x180024d80`
- `ntdll!RtlDestroyEnvironment` at `0x180024d80`
- `ntdll!RtlNtStatusToDosError` at `0x180024d88`
- `ntdll!RtlNtStatusToDosError` at `0x180024d88`
- `ntdll!RtlInitUnicodeString` at `0x18002472c`
- `ntdll!RtlInitUnicodeString` at `0x18002473a`
- `ntdll!RtlInitUnicodeString` at `0x1800247ee`
- `ntdll!RtlInitUnicodeString` at `0x1800247fd`
- `ntdll!RtlInitUnicodeString` at `0x180024862`
- `ntdll!RtlInitUnicodeString` at `0x180024871`
- `ntdll!RtlInitUnicodeString` at `0x1800248d6`
- `ntdll!RtlInitUnicodeString` at `0x1800248e5`
- `ntdll!RtlInitUnicodeString` at `0x18002494a`
- `ntdll!RtlInitUnicodeString` at `0x180024959`
- `ntdll!RtlInitUnicodeString` at `0x1800249be`
- `ntdll!RtlInitUnicodeString` at `0x1800249cd`
- `ntdll!RtlInitUnicodeString` at `0x180024a32`
- `ntdll!RtlInitUnicodeString` at `0x180024a41`
- `ntdll!RtlInitUnicodeString` at `0x180024aa6`
- `ntdll!RtlInitUnicodeString` at `0x180024ab5`
- `ntdll!RtlInitUnicodeString` at `0x180024b1a`
- `ntdll!RtlInitUnicodeString` at `0x180024b29`
- `ntdll!RtlInitUnicodeString` at `0x180024b8e`
- `ntdll!RtlInitUnicodeString` at `0x180024c56`
- `ntdll!RtlInitUnicodeString` at `0x18002472c`
- `ntdll!RtlInitUnicodeString` at `0x18002473a`
- `ntdll!RtlInitUnicodeString` at `0x1800247ee`
- `ntdll!RtlInitUnicodeString` at `0x1800247fd`
- `ntdll!RtlInitUnicodeString` at `0x180024862`
- `ntdll!RtlInitUnicodeString` at `0x180024871`
- `ntdll!RtlInitUnicodeString` at `0x1800248d6`
- `ntdll!RtlInitUnicodeString` at `0x1800248e5`
- `ntdll!RtlInitUnicodeString` at `0x18002494a`
- `ntdll!RtlInitUnicodeString` at `0x180024959`
- `ntdll!RtlInitUnicodeString` at `0x1800249be`
- `ntdll!RtlInitUnicodeString` at `0x1800249cd`
- `ntdll!RtlInitUnicodeString` at `0x180024a32`
- `ntdll!RtlInitUnicodeString` at `0x180024a41`
- `ntdll!RtlInitUnicodeString` at `0x180024aa6`
- `ntdll!RtlInitUnicodeString` at `0x180024ab5`
- `ntdll!RtlInitUnicodeString` at `0x180024b1a`
- `ntdll!RtlInitUnicodeString` at `0x180024b29`
- `ntdll!RtlInitUnicodeString` at `0x180024b8e`
- `ntdll!RtlInitUnicodeString` at `0x180024c56`

## string_xrefs

- `0x180024b0e`: `StoreName`

## pseudocode

```c
ULONG __fastcall SsAddCertMappingToRegistry(__int64 a1, const WCHAR *a2, int a3)
{
  int v6; // ebx
  _QWORD *v7; // rcx
  int v8; // edx
  int v9; // r9d
  ULONG v10; // ecx
  ULONG v11; // ecx
  ULONG ValueLength; // eax
  PVOID ValueData; // rcx
  PWSTR Environment; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING Value; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  char v18; // [rsp+60h] [rbp-A0h] BYREF
  char v19; // [rsp+B0h] [rbp-50h] BYREF

  Environment = 0;
  DestinationString = 0;
  Value = 0;
  if ( a2 )
  {
    v6 = RtlCreateEnvironment(0, &Environment);
    if ( v6 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"ServerName");
      RtlInitUnicodeString(&Value, a2);
      v6 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
      if ( v6 >= 0 )
      {
        if ( a3 )
        {
          v6 = -1073741637;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            goto LABEL_90;
          }
          v8 = 99;
          v9 = -1073741637;
LABEL_89:
          WPP_SF_dS(v7[2], v8, (unsigned int)WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids, v9, (__int64)a2);
          goto LABEL_90;
        }
        if ( *(_QWORD *)(a1 + 8)
          && (RtlInitUnicodeString(&DestinationString, L"Subject"),
              RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 8)),
              v6 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value),
              v6 < 0) )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            goto LABEL_90;
          }
          v8 = 100;
        }
        else
        {
          RtlInitUnicodeString(&DestinationString, L"Issuer");
          RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 16));
          v6 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
          if ( v6 >= 0 )
          {
            RtlInitUnicodeString(&DestinationString, L"ThumbPrint");
            RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 24));
            v6 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
            if ( v6 >= 0 )
            {
              RtlInitUnicodeString(&DestinationString, L"FriendlyName");
              RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 32));
              v6 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
              if ( v6 >= 0 )
              {
                RtlInitUnicodeString(&DestinationString, L"NotBefore");
                RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 40));
                v6 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
                if ( v6 >= 0 )
                {
                  RtlInitUnicodeString(&DestinationString, L"NotAfter");
                  RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 48));
                  v6 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
                  if ( v6 >= 0 )
                  {
                    RtlInitUnicodeString(&DestinationString, L"StoreLocation");
                    RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 56));
                    v6 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
                    if ( v6 >= 0 )
                    {
                      RtlInitUnicodeString(&DestinationString, L"StoreName");
                      RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 64));
                      v6 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
                      if ( v6 >= 0 )
                      {
                        RtlInitUnicodeString(&DestinationString, L"Type");
                        v10 = *(_DWORD *)(a1 + 80);
                        Value.Buffer = (PWSTR)&v18;
                        *(_DWORD *)&Value.Length = 4325442;
                        v6 = RtlIntegerToUnicodeString(v10, 0xAu, &Value);
                        if ( v6 >= 0 )
                        {
                          v6 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
                          if ( v6 >= 0 )
                          {
                            RtlInitUnicodeString(&DestinationString, L"Flags");
                            v11 = *(_DWORD *)(a1 + 84);
                            Value.Buffer = (PWSTR)&v19;
                            *(_DWORD *)&Value.Length = 4325442;
                            v6 = RtlIntegerToUnicodeString(v11, 0xAu, &Value);
                            if ( v6 >= 0 )
                            {
                              v6 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
                              if ( v6 >= 0 )
                              {
                                ValueLength = SsRtlQueryEnvironmentLength(Environment);
                                v6 = RtlWriteRegistryValue(0, &word_18005E1CC, a2, 7u, ValueData, ValueLength);
                                if ( v6 >= 0 )
                                  goto LABEL_90;
                                v7 = WPP_GLOBAL_Control;
                                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
                                  || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
                                {
                                  goto LABEL_90;
                                }
                                v8 = 112;
                              }
                              else
                              {
                                v7 = WPP_GLOBAL_Control;
                                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
                                  || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
                                {
                                  goto LABEL_90;
                                }
                                v8 = 111;
                              }
                            }
                            else
                            {
                              v7 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
                                || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
                              {
                                goto LABEL_90;
                              }
                              v8 = 110;
                            }
                          }
                          else
                          {
                            v7 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
                              || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
                            {
                              goto LABEL_90;
                            }
                            v8 = 109;
                          }
                        }
                        else
                        {
                          v7 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
                            || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
                          {
                            goto LABEL_90;
                          }
                          v8 = 108;
                        }
                      }
                      else
                      {
                        v7 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
                          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
                        {
                          goto LABEL_90;
                        }
                        v8 = 107;
                      }
                    }
                    else
                    {
                      v7 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
                        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
                      {
                        goto LABEL_90;
                      }
                      v8 = 106;
                    }
                  }
                  else
                  {
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
                      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
                    {
                      goto LABEL_90;
                    }
                    v8 = 105;
                  }
                }
                else
                {
                  v7 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                    || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
                    || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
                  {
                    goto LABEL_90;
                  }
                  v8 = 104;
                }
              }
              else
              {
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
                {
                  goto LABEL_90;
                }
                v8 = 103;
              }
            }
            else
            {
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
                || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
              {
                goto LABEL_90;
              }
              v8 = 102;
            }
          }
          else
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              goto LABEL_90;
            }
            v8 = 101;
          }
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_90;
        }
        v8 = 98;
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_90;
      }
      v8 = 97;
    }
    v9 = v6;
    goto LABEL_89;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids, 0);
  }
  v6 = -1073741811;
LABEL_90:
  if ( Environment )
    RtlDestroyEnvironment(Environment);
  return RtlNtStatusToDosError(v6);
}

```

## disassembly

```asm
0x180024644  mov     [rsp-8+arg_10], rbx
0x180024649  mov     [rsp-8+arg_18], rsi
0x18002464e  push    rbp
0x18002464f  push    rdi
0x180024650  push    r14
0x180024652  lea     rbp, [rsp-10h]
0x180024657  sub     rsp, 110h
0x18002465e  mov     rax, cs:__security_cookie
0x180024665  xor     rax, rsp
0x180024668  mov     [rbp+20h+var_20], rax
0x18002466c  mov     [rsp+120h+Environment], 0
0x180024675  xorps   xmm0, xmm0
0x180024678  xorps   xmm1, xmm1
0x18002467b  mov     r14d, r8d
0x18002467e  mov     rdi, rdx
0x180024681  mov     rsi, rcx
0x180024684  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x180024689  movups  xmmword ptr [rsp+120h+Value.Length], xmm1
0x18002468e  test    rdx, rdx
0x180024691  jnz     short loc_1800246D5
0x180024693  mov     rcx, cs:WPP_GLOBAL_Control
0x18002469a  lea     rax, WPP_GLOBAL_Control
0x1800246a1  cmp     rcx, rax
0x1800246a4  jz      short loc_1800246CB
0x1800246a6  test    dword ptr [rcx+1Ch], 100h
0x1800246ad  jz      short loc_1800246CB
0x1800246af  cmp     byte ptr [rcx+19h], 1
0x1800246b3  jb      short loc_1800246CB
0x1800246b5  mov     rcx, [rcx+10h]
0x1800246b9  lea     edx, [rdi+60h]
0x1800246bc  xor     r9d, r9d
0x1800246bf  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x1800246c6  call    WPP_SF_S
0x1800246cb  mov     ebx, 0C000000Dh
0x1800246d0  jmp     loc_180024D76
0x1800246d5  lea     rdx, [rsp+120h+Environment]; Environment
0x1800246da  xor     ecx, ecx; Inherit
0x1800246dc  call    cs:__imp_RtlCreateEnvironment
0x1800246e2  mov     ebx, eax
0x1800246e4  test    eax, eax
0x1800246e6  jns     short loc_180024720
0x1800246e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800246ef  lea     rax, WPP_GLOBAL_Control
0x1800246f6  cmp     rcx, rax
0x1800246f9  jz      loc_180024D76
0x1800246ff  test    dword ptr [rcx+1Ch], 100h
0x180024706  jz      loc_180024D76
0x18002470c  cmp     byte ptr [rcx+19h], 1
0x180024710  jb      loc_180024D76
0x180024716  mov     edx, 61h ; 'a'
0x18002471b  jmp     loc_180024D5E
0x180024720  lea     rdx, aServername; "ServerName"
0x180024727  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x18002472c  call    cs:__imp_RtlInitUnicodeString
0x180024732  mov     rdx, rdi; SourceString
0x180024735  lea     rcx, [rsp+120h+Value]; DestinationString
0x18002473a  call    cs:__imp_RtlInitUnicodeString
0x180024740  lea     r8, [rsp+120h+Value]; Value
0x180024745  lea     rdx, [rsp+120h+DestinationString]; Name
0x18002474a  lea     rcx, [rsp+120h+Environment]; Environment
0x18002474f  call    cs:__imp_RtlSetEnvironmentVariable
0x180024755  mov     ebx, eax
0x180024757  test    eax, eax
0x180024759  jns     short loc_180024793
0x18002475b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024762  lea     rax, WPP_GLOBAL_Control
0x180024769  cmp     rcx, rax
0x18002476c  jz      loc_180024D76
0x180024772  test    dword ptr [rcx+1Ch], 100h
0x180024779  jz      loc_180024D76
0x18002477f  cmp     byte ptr [rcx+19h], 1
0x180024783  jb      loc_180024D76
0x180024789  mov     edx, 62h ; 'b'
0x18002478e  jmp     loc_180024D5E
0x180024793  test    r14d, r14d
0x180024796  jz      short loc_1800247DB
0x180024798  mov     ebx, 0C00000BBh
0x18002479d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247a4  lea     rax, WPP_GLOBAL_Control
0x1800247ab  cmp     rcx, rax
0x1800247ae  jz      loc_180024D76
0x1800247b4  test    dword ptr [rcx+1Ch], 100h
0x1800247bb  jz      loc_180024D76
0x1800247c1  cmp     byte ptr [rcx+19h], 1
0x1800247c5  jb      loc_180024D76
0x1800247cb  mov     edx, 63h ; 'c'
0x1800247d0  mov     r9d, 0C00000BBh
0x1800247d6  jmp     loc_180024D61
0x1800247db  cmp     qword ptr [rsi+8], 0
0x1800247e0  jz      short loc_180024856
0x1800247e2  lea     rdx, aSubject; "Subject"
0x1800247e9  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x1800247ee  call    cs:__imp_RtlInitUnicodeString
0x1800247f4  mov     rdx, [rsi+8]; SourceString
0x1800247f8  lea     rcx, [rsp+120h+Value]; DestinationString
0x1800247fd  call    cs:__imp_RtlInitUnicodeString
0x180024803  lea     r8, [rsp+120h+Value]; Value
0x180024808  lea     rdx, [rsp+120h+DestinationString]; Name
0x18002480d  lea     rcx, [rsp+120h+Environment]; Environment
0x180024812  call    cs:__imp_RtlSetEnvironmentVariable
0x180024818  mov     ebx, eax
0x18002481a  test    eax, eax
0x18002481c  jns     short loc_180024856
0x18002481e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024825  lea     rax, WPP_GLOBAL_Control
0x18002482c  cmp     rcx, rax
0x18002482f  jz      loc_180024D76
0x180024835  test    dword ptr [rcx+1Ch], 100h
0x18002483c  jz      loc_180024D76
0x180024842  cmp     byte ptr [rcx+19h], 1
0x180024846  jb      loc_180024D76
0x18002484c  mov     edx, 64h ; 'd'
0x180024851  jmp     loc_180024D5E
0x180024856  lea     rdx, aIssuer; "Issuer"
0x18002485d  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x180024862  call    cs:__imp_RtlInitUnicodeString
0x180024868  mov     rdx, [rsi+10h]; SourceString
0x18002486c  lea     rcx, [rsp+120h+Value]; DestinationString
0x180024871  call    cs:__imp_RtlInitUnicodeString
0x180024877  lea     r8, [rsp+120h+Value]; Value
0x18002487c  lea     rdx, [rsp+120h+DestinationString]; Name
0x180024881  lea     rcx, [rsp+120h+Environment]; Environment
0x180024886  call    cs:__imp_RtlSetEnvironmentVariable
0x18002488c  mov     ebx, eax
0x18002488e  test    eax, eax
0x180024890  jns     short loc_1800248CA
0x180024892  mov     rcx, cs:WPP_GLOBAL_Control
0x180024899  lea     rax, WPP_GLOBAL_Control
0x1800248a0  cmp     rcx, rax
0x1800248a3  jz      loc_180024D76
0x1800248a9  test    dword ptr [rcx+1Ch], 100h
0x1800248b0  jz      loc_180024D76
0x1800248b6  cmp     byte ptr [rcx+19h], 1
0x1800248ba  jb      loc_180024D76
0x1800248c0  mov     edx, 65h ; 'e'
0x1800248c5  jmp     loc_180024D5E
0x1800248ca  lea     rdx, aThumbprint; "ThumbPrint"
0x1800248d1  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x1800248d6  call    cs:__imp_RtlInitUnicodeString
0x1800248dc  mov     rdx, [rsi+18h]; SourceString
0x1800248e0  lea     rcx, [rsp+120h+Value]; DestinationString
0x1800248e5  call    cs:__imp_RtlInitUnicodeString
0x1800248eb  lea     r8, [rsp+120h+Value]; Value
0x1800248f0  lea     rdx, [rsp+120h+DestinationString]; Name
0x1800248f5  lea     rcx, [rsp+120h+Environment]; Environment
0x1800248fa  call    cs:__imp_RtlSetEnvironmentVariable
0x180024900  mov     ebx, eax
0x180024902  test    eax, eax
0x180024904  jns     short loc_18002493E
0x180024906  mov     rcx, cs:WPP_GLOBAL_Control
0x18002490d  lea     rax, WPP_GLOBAL_Control
0x180024914  cmp     rcx, rax
0x180024917  jz      loc_180024D76
0x18002491d  test    dword ptr [rcx+1Ch], 100h
0x180024924  jz      loc_180024D76
0x18002492a  cmp     byte ptr [rcx+19h], 1
0x18002492e  jb      loc_180024D76
0x180024934  mov     edx, 66h ; 'f'
0x180024939  jmp     loc_180024D5E
0x18002493e  lea     rdx, aFriendlyname; "FriendlyName"
0x180024945  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x18002494a  call    cs:__imp_RtlInitUnicodeString
0x180024950  mov     rdx, [rsi+20h]; SourceString
0x180024954  lea     rcx, [rsp+120h+Value]; DestinationString
0x180024959  call    cs:__imp_RtlInitUnicodeString
0x18002495f  lea     r8, [rsp+120h+Value]; Value
0x180024964  lea     rdx, [rsp+120h+DestinationString]; Name
0x180024969  lea     rcx, [rsp+120h+Environment]; Environment
0x18002496e  call    cs:__imp_RtlSetEnvironmentVariable
0x180024974  mov     ebx, eax
0x180024976  test    eax, eax
0x180024978  jns     short loc_1800249B2
0x18002497a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024981  lea     rax, WPP_GLOBAL_Control
0x180024988  cmp     rcx, rax
0x18002498b  jz      loc_180024D76
0x180024991  test    dword ptr [rcx+1Ch], 100h
0x180024998  jz      loc_180024D76
0x18002499e  cmp     byte ptr [rcx+19h], 1
0x1800249a2  jb      loc_180024D76
0x1800249a8  mov     edx, 67h ; 'g'
0x1800249ad  jmp     loc_180024D5E
0x1800249b2  lea     rdx, aNotbefore; "NotBefore"
0x1800249b9  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x1800249be  call    cs:__imp_RtlInitUnicodeString
0x1800249c4  mov     rdx, [rsi+28h]; SourceString
0x1800249c8  lea     rcx, [rsp+120h+Value]; DestinationString
0x1800249cd  call    cs:__imp_RtlInitUnicodeString
0x1800249d3  lea     r8, [rsp+120h+Value]; Value
0x1800249d8  lea     rdx, [rsp+120h+DestinationString]; Name
0x1800249dd  lea     rcx, [rsp+120h+Environment]; Environment
0x1800249e2  call    cs:__imp_RtlSetEnvironmentVariable
0x1800249e8  mov     ebx, eax
0x1800249ea  test    eax, eax
0x1800249ec  jns     short loc_180024A26
0x1800249ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249f5  lea     rax, WPP_GLOBAL_Control
0x1800249fc  cmp     rcx, rax
0x1800249ff  jz      loc_180024D76
0x180024a05  test    dword ptr [rcx+1Ch], 100h
0x180024a0c  jz      loc_180024D76
0x180024a12  cmp     byte ptr [rcx+19h], 1
0x180024a16  jb      loc_180024D76
0x180024a1c  mov     edx, 68h ; 'h'
0x180024a21  jmp     loc_180024D5E
0x180024a26  lea     rdx, aNotafter; "NotAfter"
0x180024a2d  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x180024a32  call    cs:__imp_RtlInitUnicodeString
0x180024a38  mov     rdx, [rsi+30h]; SourceString
0x180024a3c  lea     rcx, [rsp+120h+Value]; DestinationString
0x180024a41  call    cs:__imp_RtlInitUnicodeString
0x180024a47  lea     r8, [rsp+120h+Value]; Value
0x180024a4c  lea     rdx, [rsp+120h+DestinationString]; Name
0x180024a51  lea     rcx, [rsp+120h+Environment]; Environment
0x180024a56  call    cs:__imp_RtlSetEnvironmentVariable
0x180024a5c  mov     ebx, eax
0x180024a5e  test    eax, eax
0x180024a60  jns     short loc_180024A9A
0x180024a62  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a69  lea     rax, WPP_GLOBAL_Control
0x180024a70  cmp     rcx, rax
0x180024a73  jz      loc_180024D76
0x180024a79  test    dword ptr [rcx+1Ch], 100h
0x180024a80  jz      loc_180024D76
0x180024a86  cmp     byte ptr [rcx+19h], 1
0x180024a8a  jb      loc_180024D76
0x180024a90  mov     edx, 69h ; 'i'
0x180024a95  jmp     loc_180024D5E
0x180024a9a  lea     rdx, aStorelocation; "StoreLocation"
0x180024aa1  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x180024aa6  call    cs:__imp_RtlInitUnicodeString
0x180024aac  mov     rdx, [rsi+38h]; SourceString
0x180024ab0  lea     rcx, [rsp+120h+Value]; DestinationString
0x180024ab5  call    cs:__imp_RtlInitUnicodeString
0x180024abb  lea     r8, [rsp+120h+Value]; Value
0x180024ac0  lea     rdx, [rsp+120h+DestinationString]; Name
0x180024ac5  lea     rcx, [rsp+120h+Environment]; Environment
0x180024aca  call    cs:__imp_RtlSetEnvironmentVariable
0x180024ad0  mov     ebx, eax
0x180024ad2  test    eax, eax
0x180024ad4  jns     short loc_180024B0E
0x180024ad6  mov     rcx, cs:WPP_GLOBAL_Control
0x180024add  lea     rax, WPP_GLOBAL_Control
0x180024ae4  cmp     rcx, rax
0x180024ae7  jz      loc_180024D76
0x180024aed  test    dword ptr [rcx+1Ch], 100h
0x180024af4  jz      loc_180024D76
0x180024afa  cmp     byte ptr [rcx+19h], 1
0x180024afe  jb      loc_180024D76
0x180024b04  mov     edx, 6Ah ; 'j'
0x180024b09  jmp     loc_180024D5E
0x180024b0e  lea     rdx, aStorename; "StoreName"
0x180024b15  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x180024b1a  call    cs:__imp_RtlInitUnicodeString
0x180024b20  mov     rdx, [rsi+40h]; SourceString
0x180024b24  lea     rcx, [rsp+120h+Value]; DestinationString
0x180024b29  call    cs:__imp_RtlInitUnicodeString
0x180024b2f  lea     r8, [rsp+120h+Value]; Value
0x180024b34  lea     rdx, [rsp+120h+DestinationString]; Name
0x180024b39  lea     rcx, [rsp+120h+Environment]; Environment
0x180024b3e  call    cs:__imp_RtlSetEnvironmentVariable
0x180024b44  mov     ebx, eax
0x180024b46  test    eax, eax
0x180024b48  jns     short loc_180024B82
0x180024b4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b51  lea     rax, WPP_GLOBAL_Control
0x180024b58  cmp     rcx, rax
0x180024b5b  jz      loc_180024D76
0x180024b61  test    dword ptr [rcx+1Ch], 100h
0x180024b68  jz      loc_180024D76
0x180024b6e  cmp     byte ptr [rcx+19h], 1
0x180024b72  jb      loc_180024D76
0x180024b78  mov     edx, 6Bh ; 'k'
0x180024b7d  jmp     loc_180024D5E
0x180024b82  lea     rdx, aType_0; "Type"
0x180024b89  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x180024b8e  call    cs:__imp_RtlInitUnicodeString
0x180024b94  mov     ecx, [rsi+50h]; Value
0x180024b97  lea     rax, [rsp+120h+var_C0]
0x180024b9c  lea     r8, [rsp+120h+Value]; String
0x180024ba1  mov     [rsp+120h+Value.Buffer], rax
0x180024ba6  mov     edx, 0Ah; Base
0x180024bab  mov     dword ptr [rsp+120h+Value.Length], 420042h
0x180024bb3  call    cs:__imp_RtlIntegerToUnicodeString
0x180024bb9  mov     ebx, eax
0x180024bbb  test    eax, eax
0x180024bbd  jns     short loc_180024BF7
0x180024bbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180024bc6  lea     rax, WPP_GLOBAL_Control
0x180024bcd  cmp     rcx, rax
0x180024bd0  jz      loc_180024D76
0x180024bd6  test    dword ptr [rcx+1Ch], 100h
0x180024bdd  jz      loc_180024D76
0x180024be3  cmp     byte ptr [rcx+19h], 1
0x180024be7  jb      loc_180024D76
0x180024bed  mov     edx, 6Ch ; 'l'
0x180024bf2  jmp     loc_180024D5E
0x180024bf7  lea     r8, [rsp+120h+Value]; Value
0x180024bfc  lea     rdx, [rsp+120h+DestinationString]; Name
0x180024c01  lea     rcx, [rsp+120h+Environment]; Environment
  ... truncated ...
```

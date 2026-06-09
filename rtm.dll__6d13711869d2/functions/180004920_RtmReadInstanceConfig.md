# RtmReadInstanceConfig

- ea: `0x180004920`
- end: `0x180004b44`
- name: `RtmReadInstanceConfig`
- size: `548`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007a34`
- `0x180009d14`

## callees

- `0x180002c5c`
- `0x180004920`
- `0x180005768`
- `0x180007a34`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x1800049fe`
- `ADVAPI32!RegOpenKeyExA` at `0x1800049fe`
- `ADVAPI32!RegCloseKey` at `0x180004ad7`
- `ADVAPI32!RegCloseKey` at `0x180004ad7`

## string_xrefs

- `0x180004986`: `Entered: RtmReadInstanceConfig`
- `0x180004a21`: `Instance Config: Error %d opening instance key`
- `0x180004a96`: `Leaving: RtmReadInstanceConfig`
- `0x180004ae6`: `Leaving: RtmReadInstanceConfig`

## pseudocode

```c
__int64 RtmReadInstanceConfig()
{
  __int64 v0; // r8
  __int64 result; // rax
  unsigned int v2; // eax
  __int64 v3; // r8
  unsigned int v4; // ebx
  char v5; // cl
  __int64 v6; // rax
  __int64 v7; // r8
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v9[16]; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v10; // [rsp+50h] [rbp-B0h]
  __int64 v11; // [rsp+58h] [rbp-A8h]
  int v12; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v13[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  hKey = 0;
  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  if ( (_DWORD)qword_18002BD00 || (result = RtmApiStartup(), !(_DWORD)result) )
  {
    if ( (byte_18002BD1A & 8) != 0 )
    {
      v11 = 62;
      v10 = L"Entered: RtmReadInstanceConfig";
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RRAS_RTM_TRACE_INFO, v0, 2, v9);
    }
    StringCchPrintfA((STRSAFE_LPSTR)lpSubKey + 66, 0xC2u, "\\Instance %05d", 0);
    v2 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
    v4 = v2;
    if ( v2 )
    {
      v5 = byte_18002BD1A;
      if ( (byte_18002BD1A & 4) != 0 )
      {
        LOWORD(v12) = 0;
        FormatRRASErrorString(&v12, L"Instance Config: Error %d opening instance key", v2);
        v5 = byte_18002BD1A;
        if ( (byte_18002BD1A & 4) != 0 )
        {
          v6 = -1;
          do
            ++v6;
          while ( *(_WORD *)&v13[2 * v6 - 4] );
          v11 = (unsigned int)(2 * v6 + 2);
          v10 = (const wchar_t *)&v12;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RRAS_RTM_TRACE_ERROR, v3, 2, v9);
          v5 = byte_18002BD1A;
        }
      }
      if ( (v5 & 8) != 0 )
      {
        v11 = 62;
        v10 = L"Leaving: RtmReadInstanceConfig";
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RRAS_RTM_TRACE_INFO, v3, 2, v9);
      }
      return v4;
    }
    else
    {
      RegCloseKey(hKey);
      if ( (byte_18002BD1A & 8) != 0 )
      {
        v11 = 62;
        v10 = L"Leaving: RtmReadInstanceConfig";
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RRAS_RTM_TRACE_INFO, v7, 2, v9);
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004920  mov     [rsp-8+arg_0], rbx
0x180004925  mov     [rsp-8+arg_8], rdi
0x18000492a  push    rbp
0x18000492b  lea     rbp, [rsp-770h]
0x180004933  sub     rsp, 870h
0x18000493a  mov     rax, cs:__security_cookie
0x180004941  xor     rax, rsp
0x180004944  mov     [rbp+770h+var_10], rax
0x18000494b  xor     edi, edi
0x18000494d  lea     rcx, [rsp+870h+var_80C]; void *
0x180004952  xor     edx, edx; Val
0x180004954  mov     [rsp+870h+hKey], rdi
0x180004959  mov     r8d, 7FCh; Size
0x18000495f  mov     [rsp+870h+var_810], edi
0x180004963  call    memset_0
0x180004968  cmp     dword ptr cs:qword_18002BD00, edi
0x18000496e  jnz     short loc_18000497D
0x180004970  call    RtmApiStartup
0x180004975  test    eax, eax
0x180004977  jnz     loc_180004B20
0x18000497d  test    cs:byte_18002BD1A, 8
0x180004984  jz      short loc_1800049BE
0x180004986  lea     rax, aEnteredRtmread_0; "Entered: RtmReadInstanceConfig"
0x18000498d  mov     [rsp+870h+var_818], 3Eh ; '>'
0x180004996  mov     [rsp+870h+var_820], rax
0x18000499b  lea     rdx, RRAS_RTM_TRACE_INFO
0x1800049a2  lea     rax, [rsp+870h+var_830]
0x1800049a7  mov     r9d, 2
0x1800049ad  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800049b4  mov     [rsp+870h+phkResult], rax
0x1800049b9  call    McGenEventWrite_EventWriteTransfer
0x1800049be  mov     rcx, cs:lpSubKey
0x1800049c5  lea     r8, aInstance05d; "\\Instance %05d"
0x1800049cc  add     rcx, 42h ; 'B'; pszDest
0x1800049d0  xor     r9d, r9d
0x1800049d3  mov     edx, 0C2h; cchDest
0x1800049d8  call    StringCchPrintfA
0x1800049dd  mov     rdx, cs:lpSubKey; lpSubKey
0x1800049e4  lea     rax, [rsp+870h+hKey]
0x1800049e9  mov     r9d, 20019h; samDesired
0x1800049ef  mov     [rsp+870h+phkResult], rax; phkResult
0x1800049f4  xor     r8d, r8d; ulOptions
0x1800049f7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800049fe  call    cs:__imp_RegOpenKeyExA
0x180004a04  mov     ebx, eax
0x180004a06  test    eax, eax
0x180004a08  jz      loc_180004AD2
0x180004a0e  mov     cl, cs:byte_18002BD1A
0x180004a14  test    cl, 4
0x180004a17  jz      short loc_180004A91
0x180004a19  mov     r8d, eax
0x180004a1c  mov     word ptr [rsp+870h+var_810], di
0x180004a21  lea     rdx, aInstanceConfig_0; "Instance Config: Error %d opening insta"...
0x180004a28  lea     rcx, [rsp+870h+var_810]
0x180004a2d  call    FormatRRASErrorString
0x180004a32  mov     cl, cs:byte_18002BD1A
0x180004a38  test    cl, 4
0x180004a3b  jz      short loc_180004A91
0x180004a3d  lea     rcx, [rsp+870h+var_810]
0x180004a42  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004a46  inc     rax
0x180004a49  cmp     [rcx+rax*2], di
0x180004a4d  jnz     short loc_180004A46
0x180004a4f  lea     eax, ds:2[rax*2]
0x180004a56  mov     dword ptr [rsp+870h+var_818+4], edi
0x180004a5a  lea     rcx, [rsp+870h+var_810]
0x180004a5f  mov     dword ptr [rsp+870h+var_818], eax
0x180004a63  lea     rax, [rsp+870h+var_830]
0x180004a68  mov     [rsp+870h+var_820], rcx
0x180004a6d  mov     r9d, 2
0x180004a73  mov     [rsp+870h+phkResult], rax
0x180004a78  lea     rdx, RRAS_RTM_TRACE_ERROR
0x180004a7f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004a86  call    McGenEventWrite_EventWriteTransfer
0x180004a8b  mov     cl, cs:byte_18002BD1A
0x180004a91  test    cl, 8
0x180004a94  jz      short loc_180004ACE
0x180004a96  lea     rax, aLeavingRtmread; "Leaving: RtmReadInstanceConfig"
0x180004a9d  mov     [rsp+870h+var_818], 3Eh ; '>'
0x180004aa6  mov     [rsp+870h+var_820], rax
0x180004aab  lea     rdx, RRAS_RTM_TRACE_INFO
0x180004ab2  lea     rax, [rsp+870h+var_830]
0x180004ab7  mov     r9d, 2
0x180004abd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004ac4  mov     [rsp+870h+phkResult], rax
0x180004ac9  call    McGenEventWrite_EventWriteTransfer
0x180004ace  mov     eax, ebx
0x180004ad0  jmp     short loc_180004B20
0x180004ad2  mov     rcx, [rsp+870h+hKey]; hKey
0x180004ad7  call    cs:__imp_RegCloseKey
0x180004add  test    cs:byte_18002BD1A, 8
0x180004ae4  jz      short loc_180004B1E
0x180004ae6  lea     rax, aLeavingRtmread; "Leaving: RtmReadInstanceConfig"
0x180004aed  mov     [rsp+870h+var_818], 3Eh ; '>'
0x180004af6  mov     [rsp+870h+var_820], rax
0x180004afb  lea     rdx, RRAS_RTM_TRACE_INFO
0x180004b02  lea     rax, [rsp+870h+var_830]
0x180004b07  mov     r9d, 2
0x180004b0d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004b14  mov     [rsp+870h+phkResult], rax
0x180004b19  call    McGenEventWrite_EventWriteTransfer
0x180004b1e  xor     eax, eax
0x180004b20  mov     rcx, [rbp+770h+var_10]
0x180004b27  xor     rcx, rsp; StackCookie
0x180004b2a  call    __security_check_cookie
0x180004b2f  lea     r11, [rsp+870h+var_s0]
0x180004b37  mov     rbx, [r11+10h]
0x180004b3b  mov     rdi, [r11+18h]
0x180004b3f  mov     rsp, r11
0x180004b42  pop     rbp
0x180004b43  retn
```

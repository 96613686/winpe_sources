# RtmWriteInstanceConfig

- ea: `0x180005530`
- end: `0x180005761`
- name: `RtmWriteInstanceConfig`
- size: `561`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800052d0`

## callees

- `0x180002c5c`
- `0x180005530`
- `0x180005768`
- `0x180007a34`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800056f4`
- `ADVAPI32!RegCloseKey` at `0x1800056f4`
- `ADVAPI32!RegCreateKeyExA` at `0x18000561f`
- `ADVAPI32!RegCreateKeyExA` at `0x18000561f`

## string_xrefs

- `0x180005594`: `Entered: RtmWriteInstanceConfig`
- `0x180005641`: `Instance Config: Error %d creating instance key`
- `0x1800056b3`: `Leaving: RtmWriteInstanceConfig`
- `0x180005703`: `Leaving: RtmWriteInstanceConfig`

## pseudocode

```c
__int64 RtmWriteInstanceConfig()
{
  __int64 v0; // r8
  __int64 result; // rax
  unsigned int v2; // eax
  __int64 v3; // r8
  unsigned int v4; // ebx
  char v5; // cl
  __int64 v6; // rax
  __int64 v7; // r8
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v9[16]; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v10; // [rsp+70h] [rbp-90h]
  __int64 v11; // [rsp+78h] [rbp-88h]
  int v12; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v13[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  hKey = 0;
  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  if ( (_DWORD)qword_18002BD00 || (result = RtmApiStartup(), !(_DWORD)result) )
  {
    if ( (byte_18002BD1A & 8) != 0 )
    {
      v11 = 64;
      v10 = L"Entered: RtmWriteInstanceConfig";
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RRAS_RTM_TRACE_INFO, v0, 2, v9);
    }
    StringCchPrintfA((STRSAFE_LPSTR)lpSubKey + 66, 0xC2u, "\\Instance %05d", 0);
    v2 = RegCreateKeyExA(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    v4 = v2;
    if ( v2 )
    {
      v5 = byte_18002BD1A;
      if ( (byte_18002BD1A & 4) != 0 )
      {
        LOWORD(v12) = 0;
        FormatRRASErrorString(&v12, L"Instance Config: Error %d creating instance key", v2);
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
        v11 = 64;
        v10 = L"Leaving: RtmWriteInstanceConfig";
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RRAS_RTM_TRACE_INFO, v3, 2, v9);
      }
      return v4;
    }
    else
    {
      RegCloseKey(hKey);
      if ( (byte_18002BD1A & 8) != 0 )
      {
        v11 = 64;
        v10 = L"Leaving: RtmWriteInstanceConfig";
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
0x180005530  mov     [rsp-8+arg_0], rbx
0x180005535  mov     [rsp-8+arg_8], rdi
0x18000553a  push    rbp
0x18000553b  lea     rbp, [rsp-790h]
0x180005543  sub     rsp, 890h
0x18000554a  mov     rax, cs:__security_cookie
0x180005551  xor     rax, rsp
0x180005554  mov     [rbp+790h+var_10], rax
0x18000555b  xor     edi, edi
0x18000555d  lea     rcx, [rbp+790h+var_80C]; void *
0x180005561  xor     edx, edx; Val
0x180005563  mov     [rsp+890h+hKey], rdi
0x180005568  mov     r8d, 7FCh; Size
0x18000556e  mov     [rbp+790h+var_810], edi
0x180005571  call    memset_0
0x180005576  cmp     dword ptr cs:qword_18002BD00, edi
0x18000557c  jnz     short loc_18000558B
0x18000557e  call    RtmApiStartup
0x180005583  test    eax, eax
0x180005585  jnz     loc_18000573D
0x18000558b  test    cs:byte_18002BD1A, 8
0x180005592  jz      short loc_1800055CC
0x180005594  lea     rax, aEnteredRtmwrit; "Entered: RtmWriteInstanceConfig"
0x18000559b  mov     [rsp+890h+var_818], 40h ; '@'
0x1800055a4  mov     [rsp+890h+var_820], rax
0x1800055a9  lea     rdx, RRAS_RTM_TRACE_INFO
0x1800055b0  lea     rax, [rsp+890h+var_830]
0x1800055b5  mov     r9d, 2
0x1800055bb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800055c2  mov     qword ptr [rsp+890h+dwOptions], rax
0x1800055c7  call    McGenEventWrite_EventWriteTransfer
0x1800055cc  mov     rcx, cs:lpSubKey
0x1800055d3  lea     r8, aInstance05d; "\\Instance %05d"
0x1800055da  add     rcx, 42h ; 'B'; pszDest
0x1800055de  xor     r9d, r9d
0x1800055e1  mov     edx, 0C2h; cchDest
0x1800055e6  call    StringCchPrintfA
0x1800055eb  mov     rdx, cs:lpSubKey; lpSubKey
0x1800055f2  lea     rax, [rsp+890h+hKey]
0x1800055f7  mov     [rsp+890h+lpdwDisposition], rdi; lpdwDisposition
0x1800055fc  xor     r9d, r9d; lpClass
0x1800055ff  mov     [rsp+890h+phkResult], rax; phkResult
0x180005604  xor     r8d, r8d; Reserved
0x180005607  mov     [rsp+890h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000560c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005613  mov     [rsp+890h+samDesired], 20006h; samDesired
0x18000561b  mov     [rsp+890h+dwOptions], edi; dwOptions
0x18000561f  call    cs:__imp_RegCreateKeyExA
0x180005625  mov     ebx, eax
0x180005627  test    eax, eax
0x180005629  jz      loc_1800056EF
0x18000562f  mov     cl, cs:byte_18002BD1A
0x180005635  test    cl, 4
0x180005638  jz      short loc_1800056AE
0x18000563a  mov     r8d, eax
0x18000563d  mov     word ptr [rbp+790h+var_810], di
0x180005641  lea     rdx, aInstanceConfig; "Instance Config: Error %d creating inst"...
0x180005648  lea     rcx, [rbp+790h+var_810]
0x18000564c  call    FormatRRASErrorString
0x180005651  mov     cl, cs:byte_18002BD1A
0x180005657  test    cl, 4
0x18000565a  jz      short loc_1800056AE
0x18000565c  lea     rcx, [rbp+790h+var_810]
0x180005660  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005664  inc     rax
0x180005667  cmp     [rcx+rax*2], di
0x18000566b  jnz     short loc_180005664
0x18000566d  lea     eax, ds:2[rax*2]
0x180005674  mov     dword ptr [rsp+890h+var_818+4], edi
0x180005678  lea     rcx, [rbp+790h+var_810]
0x18000567c  mov     dword ptr [rsp+890h+var_818], eax
0x180005680  lea     rax, [rsp+890h+var_830]
0x180005685  mov     [rsp+890h+var_820], rcx
0x18000568a  mov     r9d, 2
0x180005690  mov     qword ptr [rsp+890h+dwOptions], rax
0x180005695  lea     rdx, RRAS_RTM_TRACE_ERROR
0x18000569c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800056a3  call    McGenEventWrite_EventWriteTransfer
0x1800056a8  mov     cl, cs:byte_18002BD1A
0x1800056ae  test    cl, 8
0x1800056b1  jz      short loc_1800056EB
0x1800056b3  lea     rax, aLeavingRtmwrit_0; "Leaving: RtmWriteInstanceConfig"
0x1800056ba  mov     [rsp+890h+var_818], 40h ; '@'
0x1800056c3  mov     [rsp+890h+var_820], rax
0x1800056c8  lea     rdx, RRAS_RTM_TRACE_INFO
0x1800056cf  lea     rax, [rsp+890h+var_830]
0x1800056d4  mov     r9d, 2
0x1800056da  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800056e1  mov     qword ptr [rsp+890h+dwOptions], rax
0x1800056e6  call    McGenEventWrite_EventWriteTransfer
0x1800056eb  mov     eax, ebx
0x1800056ed  jmp     short loc_18000573D
0x1800056ef  mov     rcx, [rsp+890h+hKey]; hKey
0x1800056f4  call    cs:__imp_RegCloseKey
0x1800056fa  test    cs:byte_18002BD1A, 8
0x180005701  jz      short loc_18000573B
0x180005703  lea     rax, aLeavingRtmwrit_0; "Leaving: RtmWriteInstanceConfig"
0x18000570a  mov     [rsp+890h+var_818], 40h ; '@'
0x180005713  mov     [rsp+890h+var_820], rax
0x180005718  lea     rdx, RRAS_RTM_TRACE_INFO
0x18000571f  lea     rax, [rsp+890h+var_830]
0x180005724  mov     r9d, 2
0x18000572a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005731  mov     qword ptr [rsp+890h+dwOptions], rax
0x180005736  call    McGenEventWrite_EventWriteTransfer
0x18000573b  xor     eax, eax
0x18000573d  mov     rcx, [rbp+790h+var_10]
0x180005744  xor     rcx, rsp; StackCookie
0x180005747  call    __security_check_cookie
0x18000574c  lea     r11, [rsp+890h+var_s0]
0x180005754  mov     rbx, [r11+10h]
0x180005758  mov     rdi, [r11+18h]
0x18000575c  mov     rsp, r11
0x18000575f  pop     rbp
0x180005760  retn
```

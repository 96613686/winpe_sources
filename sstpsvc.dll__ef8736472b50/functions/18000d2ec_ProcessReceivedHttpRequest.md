# ProcessReceivedHttpRequest

- ea: `0x18000d2ec`
- end: `0x18000d43d`
- name: `ProcessReceivedHttpRequest`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000afb0`

## callees

- `0x1800089dc`
- `0x180008b90`
- `0x18000d2ec`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `msvcrt!_strcmpi` at `0x18000d3b5`
- `msvcrt!_strcmpi` at `0x18000d3b5`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000d34d`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000d34d`

## pseudocode

```c
__int64 __fastcall ProcessReceivedHttpRequest(__int64 a1, _WORD *a2)
{
  const wchar_t *v4; // r8
  const char *v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // r8
  int Source2[4]; // [rsp+20h] [rbp-828h] BYREF
  int v10; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v11[2044]; // [rsp+34h] [rbp-814h] BYREF

  Source2[0] = 65537;
  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  *a2 = 200;
  if ( RtlCompareMemory((const void *)(a1 + 32), Source2, 4u) != 4 )
  {
    if ( (byte_18002E903 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasSSTPSvcTraceError,
        L"Version mismatch in the request");
    *a2 = 505;
    return 50;
  }
  if ( *(_DWORD *)(a1 + 36) != 1 )
  {
    if ( (byte_18002E903 & 8) == 0 )
    {
LABEL_14:
      *a2 = 400;
      return 50;
    }
    v4 = L"Verb not accepted";
LABEL_13:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, v4);
    goto LABEL_14;
  }
  v5 = *(const char **)(a1 + 48);
  if ( !v5 || (v6 = 0, _strcmpi(v5, "SSTP_DUPLEX_POST")) )
  {
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_14;
    v7 = *(_QWORD *)(a1 + 48);
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"Received verb other than SSTP_POST - %hs", v7);
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_14;
    v4 = (const wchar_t *)&v10;
    goto LABEL_13;
  }
  return v6;
}

```

## disassembly

```asm
0x18000d2ec  mov     [rsp+arg_10], rbx
0x18000d2f1  mov     [rsp+arg_18], rsi
0x18000d2f6  push    rdi
0x18000d2f7  sub     rsp, 840h
0x18000d2fe  mov     rax, cs:__security_cookie
0x18000d305  xor     rax, rsp
0x18000d308  mov     [rsp+848h+var_18], rax
0x18000d310  mov     rsi, rdx
0x18000d313  mov     [rsp+848h+Source2], 10001h
0x18000d31b  mov     rdi, rcx
0x18000d31e  xor     eax, eax
0x18000d320  xor     edx, edx; Val
0x18000d322  mov     [rsp+848h+var_818], eax
0x18000d326  lea     rcx, [rsp+848h+var_814]; void *
0x18000d32b  mov     r8d, 7FCh; Size
0x18000d331  mov     ebx, 1
0x18000d336  call    memset_0
0x18000d33b  lea     rcx, [rdi+20h]; Source1
0x18000d33f  mov     word ptr [rsi], 0C8h
0x18000d344  lea     r8d, [rbx+3]; Length
0x18000d348  lea     rdx, [rsp+848h+Source2]; Source2
0x18000d34d  call    cs:__imp_RtlCompareMemory
0x18000d354  nop     dword ptr [rax+rax+00h]
0x18000d359  cmp     rax, 4
0x18000d35d  jz      short loc_18000D38C
0x18000d35f  test    cs:byte_18002E903, 8
0x18000d366  jz      short loc_18000D382
0x18000d368  lea     r8, aVersionMismatc; "Version mismatch in the request"
0x18000d36f  lea     rdx, RasSSTPSvcTraceError
0x18000d376  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d37d  call    McTemplateU0z_EventWriteTransfer
0x18000d382  mov     word ptr [rsi], 1F9h
0x18000d387  jmp     loc_18000D410
0x18000d38c  cmp     [rdi+24h], ebx
0x18000d38f  jz      short loc_18000D3A3
0x18000d391  test    cs:byte_18002E903, 8
0x18000d398  jz      short loc_18000D40B
0x18000d39a  lea     r8, aVerbNotAccepte; "Verb not accepted"
0x18000d3a1  jmp     short loc_18000D3F8
0x18000d3a3  mov     rcx, [rdi+30h]; String1
0x18000d3a7  test    rcx, rcx
0x18000d3aa  jz      short loc_18000D3C5
0x18000d3ac  lea     rdx, aSstpDuplexPost; "SSTP_DUPLEX_POST"
0x18000d3b3  xor     ebx, ebx
0x18000d3b5  call    cs:__imp__strcmpi
0x18000d3bc  nop     dword ptr [rax+rax+00h]
0x18000d3c1  test    eax, eax
0x18000d3c3  jz      short loc_18000D415
0x18000d3c5  test    cs:byte_18002E903, 8
0x18000d3cc  jz      short loc_18000D40B
0x18000d3ce  mov     r8, [rdi+30h]
0x18000d3d2  lea     rdx, aReceivedVerbOt; "Received verb other than SSTP_POST - %h"...
0x18000d3d9  xor     eax, eax
0x18000d3db  lea     rcx, [rsp+848h+var_818]
0x18000d3e0  mov     word ptr [rsp+848h+var_818], ax
0x18000d3e5  call    FormatRRASErrorString
0x18000d3ea  test    cs:byte_18002E903, 8
0x18000d3f1  jz      short loc_18000D40B
0x18000d3f3  lea     r8, [rsp+848h+var_818]
0x18000d3f8  lea     rdx, RasSSTPSvcTraceError
0x18000d3ff  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d406  call    McTemplateU0z_EventWriteTransfer
0x18000d40b  mov     word ptr [rsi], 190h
0x18000d410  mov     ebx, 32h ; '2'
0x18000d415  mov     eax, ebx
0x18000d417  mov     rcx, [rsp+848h+var_18]
0x18000d41f  xor     rcx, rsp; StackCookie
0x18000d422  call    __security_check_cookie
0x18000d427  lea     r11, [rsp+848h+var_8]
0x18000d42f  mov     rbx, [r11+20h]
0x18000d433  mov     rsi, [r11+28h]
0x18000d437  mov     rsp, r11
0x18000d43a  pop     rdi
0x18000d43b  retn
```

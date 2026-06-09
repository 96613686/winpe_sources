# HrComposeUpnpNotifyHeaders(ulong,ushort const *,ushort * *)

- ea: `0x180026bd4`
- end: `0x180026e8a`
- name: `?HrComposeUpnpNotifyHeaders@@YAJKPEBGPEAPEAG@Z`
- size: `694`
- prototype: `int(unsigned int, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180026630`

## callees

- `0x18000db4c`
- `0x180026bd4`
- `0x180026e90`
- `0x18003a560`
- `0x1800460d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180026df9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180026df9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180026c48`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180026c48`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026c27`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026c34`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026c27`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180026c34`

## string_xrefs

- `0x180026e4a`: `HrComposeUpnpNotifyHeaders`
- `0x180026dac`: `text/xml; charset="utf-8"`

## pseudocode

```c
__int64 __fastcall HrComposeUpnpNotifyHeaders(unsigned int a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 result; // rax
  __int64 v6; // rbx
  __int64 v7; // rbx
  wchar_t *v8; // rax
  wchar_t *v9; // rdi
  int v10; // ebx
  int v11; // eax
  STRSAFE_PCNZWCH v12; // rcx
  int v13; // edx
  unsigned __int64 v14; // [rsp+50h] [rbp-39h] BYREF
  wchar_t *Buffer; // [rsp+58h] [rbp-31h] BYREF
  WCHAR String[32]; // [rsp+60h] [rbp-29h] BYREF

  result = StringCchPrintfW(String, 0x20u, L"%d", a1);
  if ( (int)result >= 0 )
  {
    v6 = (unsigned int)(lstrlenW(a2) + 9);
    v7 = (unsigned int)(lstrlenW(String) + 9) + v6;
    v8 = (wchar_t *)malloc(2 * v7 + 178);
    v9 = v8;
    if ( v8 )
    {
      Buffer = v8;
      v14 = v7 + 89;
      v10 = StringCchPrintfExW(v8, v7 + 89, &Buffer, &v14, 0x800u, L"%s%s%s%s", L"NT", L":", L"upnp:event", L"\r\n");
      if ( v10 < 0
        || (v10 = StringCchPrintfExW(
                    Buffer,
                    v14,
                    &Buffer,
                    &v14,
                    0x800u,
                    L"%s%s%s%s",
                    L"NTS",
                    L":",
                    L"upnp:propchange",
                    L"\r\n"),
            v10 < 0)
        || (v10 = StringCchPrintfExW(Buffer, v14, &Buffer, &v14, 0x800u, L"%s%s%s%s", L"SID", L":", a2, L"\r\n"), v10 < 0)
        || (v10 = StringCchPrintfExW(Buffer, v14, &Buffer, &v14, 0x800u, L"%s%s%s%s", L"SEQ", L":", String, L"\r\n"),
            v10 < 0)
        || (v11 = StringCchPrintfExW(
                    Buffer,
                    v14,
                    &Buffer,
                    &v14,
                    0x800u,
                    L"%s%s%s%s",
                    L"Content-Type",
                    L":",
                    L"text/xml; charset=\"utf-8\"",
                    L"\r\n"),
            v10 = v11,
            v11 < 0) )
      {
        free(v9);
        if ( !v10 )
          return (unsigned int)v10;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          return (unsigned int)v10;
        v13 = 107;
LABEL_18:
        WPP_SF_sd(
          *((_QWORD *)v12 + 2),
          v13,
          (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
          (unsigned int)"HrComposeUpnpNotifyHeaders",
          v10);
        return (unsigned int)v10;
      }
      *a3 = v9;
      if ( !v11 )
        return (unsigned int)v10;
    }
    else
    {
      v10 = -2147024882;
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      return (unsigned int)v10;
    v13 = 106;
    goto LABEL_18;
  }
  return result;
}

```

## disassembly

```asm
0x180026bd4  mov     [rsp-8+arg_18], rbx
0x180026bd9  push    rbp
0x180026bda  push    rsi
0x180026bdb  push    rdi
0x180026bdc  push    r12
0x180026bde  push    r13
0x180026be0  push    r14
0x180026be2  push    r15
0x180026be4  lea     rbp, [rsp-27h]
0x180026be9  sub     rsp, 0B0h
0x180026bf0  mov     rax, cs:__security_cookie
0x180026bf7  xor     rax, rsp
0x180026bfa  mov     [rbp+57h+var_40], rax
0x180026bfe  mov     r14, r8
0x180026c01  mov     rsi, rdx
0x180026c04  mov     r9d, ecx
0x180026c07  lea     r8, aD; "%d"
0x180026c0e  mov     edx, 20h ; ' '; unsigned __int64
0x180026c13  lea     rcx, [rbp+57h+String]; unsigned __int16 *
0x180026c17  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026c1c  test    eax, eax
0x180026c1e  js      loc_180026E63
0x180026c24  mov     rcx, rsi; lpString
0x180026c27  call    cs:__imp_lstrlenW
0x180026c2d  lea     rcx, [rbp+57h+String]; lpString
0x180026c31  lea     ebx, [rax+9]
0x180026c34  call    cs:__imp_lstrlenW
0x180026c3a  add     eax, 9
0x180026c3d  add     rbx, rax
0x180026c40  lea     rcx, ds:0B2h[rbx*2]; Size
0x180026c48  call    cs:__imp_malloc
0x180026c4e  mov     rdi, rax
0x180026c51  test    rax, rax
0x180026c54  jz      loc_180026E23
0x180026c5a  mov     [rbp+57h+Buffer], rax
0x180026c5e  lea     rdx, [rbx+59h]; unsigned __int64
0x180026c62  lea     rax, aUpnpEvent; "upnp:event"
0x180026c69  mov     [rbp+57h+var_90], rdx
0x180026c6d  lea     r12, asc_180065574; "\r\n"
0x180026c74  mov     r15d, 800h
0x180026c7a  mov     [rsp+0E0h+var_98], r12
0x180026c7f  lea     r13, asc_1800655C8; ":"
0x180026c86  mov     [rsp+0E0h+var_A0], rax
0x180026c8b  lea     r9, [rbp+57h+var_90]; unsigned __int64 *
0x180026c8f  mov     [rsp+0E0h+var_A8], r13
0x180026c94  lea     rax, aNt; "NT"
0x180026c9b  mov     [rsp+0E0h+var_B0], rax
0x180026ca0  lea     r8, [rbp+57h+Buffer]; unsigned __int16 **
0x180026ca4  lea     rax, aSSSS; "%s%s%s%s"
0x180026cab  mov     rcx, rdi; Buffer
0x180026cae  mov     [rsp+0E0h+var_B8], rax; unsigned __int16 *
0x180026cb3  mov     [rsp+0E0h+var_C0], r15d; unsigned int
0x180026cb8  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180026cbd  mov     ebx, eax
0x180026cbf  test    eax, eax
0x180026cc1  js      loc_180026DF6
0x180026cc7  mov     rdx, [rbp+57h+var_90]; unsigned __int64
0x180026ccb  lea     rax, aUpnpPropchange; "upnp:propchange"
0x180026cd2  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180026cd6  lea     r9, [rbp+57h+var_90]; unsigned __int64 *
0x180026cda  mov     [rsp+0E0h+var_98], r12
0x180026cdf  lea     r8, [rbp+57h+Buffer]; unsigned __int16 **
0x180026ce3  mov     [rsp+0E0h+var_A0], rax
0x180026ce8  lea     rax, aNts; "NTS"
0x180026cef  mov     [rsp+0E0h+var_A8], r13
0x180026cf4  mov     [rsp+0E0h+var_B0], rax
0x180026cf9  lea     rax, aSSSS; "%s%s%s%s"
0x180026d00  mov     [rsp+0E0h+var_B8], rax; unsigned __int16 *
0x180026d05  mov     [rsp+0E0h+var_C0], r15d; unsigned int
0x180026d0a  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180026d0f  mov     ebx, eax
0x180026d11  test    eax, eax
0x180026d13  js      loc_180026DF6
0x180026d19  mov     rdx, [rbp+57h+var_90]; unsigned __int64
0x180026d1d  lea     rax, aSid; "SID"
0x180026d24  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180026d28  lea     r9, [rbp+57h+var_90]; unsigned __int64 *
0x180026d2c  mov     [rsp+0E0h+var_98], r12
0x180026d31  lea     r8, [rbp+57h+Buffer]; unsigned __int16 **
0x180026d35  mov     [rsp+0E0h+var_A0], rsi
0x180026d3a  lea     rsi, aSSSS; "%s%s%s%s"
0x180026d41  mov     [rsp+0E0h+var_A8], r13
0x180026d46  mov     [rsp+0E0h+var_B0], rax
0x180026d4b  mov     [rsp+0E0h+var_B8], rsi; unsigned __int16 *
0x180026d50  mov     [rsp+0E0h+var_C0], r15d; unsigned int
0x180026d55  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180026d5a  mov     ebx, eax
0x180026d5c  test    eax, eax
0x180026d5e  js      loc_180026DF6
0x180026d64  mov     rdx, [rbp+57h+var_90]; unsigned __int64
0x180026d68  lea     rax, [rbp+57h+String]
0x180026d6c  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180026d70  lea     r9, [rbp+57h+var_90]; unsigned __int64 *
0x180026d74  mov     [rsp+0E0h+var_98], r12
0x180026d79  lea     r8, [rbp+57h+Buffer]; unsigned __int16 **
0x180026d7d  mov     [rsp+0E0h+var_A0], rax
0x180026d82  lea     rax, aSeq; "SEQ"
0x180026d89  mov     [rsp+0E0h+var_A8], r13
0x180026d8e  mov     [rsp+0E0h+var_B0], rax
0x180026d93  mov     [rsp+0E0h+var_B8], rsi; unsigned __int16 *
0x180026d98  mov     [rsp+0E0h+var_C0], r15d; unsigned int
0x180026d9d  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180026da2  mov     ebx, eax
0x180026da4  test    eax, eax
0x180026da6  js      short loc_180026DF6
0x180026da8  mov     rdx, [rbp+57h+var_90]; unsigned __int64
0x180026dac  lea     rax, aTextXmlCharset_0; "text/xml; charset=\"utf-8\""
0x180026db3  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180026db7  lea     r9, [rbp+57h+var_90]; unsigned __int64 *
0x180026dbb  mov     [rsp+0E0h+var_98], r12
0x180026dc0  lea     r8, [rbp+57h+Buffer]; unsigned __int16 **
0x180026dc4  mov     [rsp+0E0h+var_A0], rax
0x180026dc9  lea     rax, aContentType_3; "Content-Type"
0x180026dd0  mov     [rsp+0E0h+var_A8], r13
0x180026dd5  mov     [rsp+0E0h+var_B0], rax
0x180026dda  mov     [rsp+0E0h+var_B8], rsi; unsigned __int16 *
0x180026ddf  mov     [rsp+0E0h+var_C0], r15d; unsigned int
0x180026de4  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180026de9  mov     ebx, eax
0x180026deb  test    eax, eax
0x180026ded  js      short loc_180026DF6
0x180026def  mov     [r14], rdi
0x180026df2  jnz     short loc_180026E28
0x180026df4  jmp     short loc_180026E61
0x180026df6  mov     rcx, rdi; Block
0x180026df9  call    cs:__imp_free
0x180026dff  test    ebx, ebx
0x180026e01  jz      short loc_180026E61
0x180026e03  mov     rcx, cs:WPP_GLOBAL_Control
0x180026e0a  lea     rax, WPP_GLOBAL_Control
0x180026e11  cmp     rcx, rax
0x180026e14  jz      short loc_180026E61
0x180026e16  test    byte ptr [rcx+1Ch], 1
0x180026e1a  jz      short loc_180026E61
0x180026e1c  mov     edx, 6Bh ; 'k'
0x180026e21  jmp     short loc_180026E46
0x180026e23  mov     ebx, 8007000Eh
0x180026e28  mov     rcx, cs:WPP_GLOBAL_Control
0x180026e2f  lea     rax, WPP_GLOBAL_Control
0x180026e36  cmp     rcx, rax
0x180026e39  jz      short loc_180026E61
0x180026e3b  test    byte ptr [rcx+1Ch], 1
0x180026e3f  jz      short loc_180026E61
0x180026e41  mov     edx, 6Ah ; 'j'
0x180026e46  mov     rcx, [rcx+10h]
0x180026e4a  lea     r9, aHrcomposeupnpn; "HrComposeUpnpNotifyHeaders"
0x180026e51  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180026e58  mov     [rsp+0E0h+var_C0], ebx
0x180026e5c  call    WPP_SF_sd
0x180026e61  mov     eax, ebx
0x180026e63  mov     rcx, [rbp+57h+var_40]
0x180026e67  xor     rcx, rsp; StackCookie
0x180026e6a  call    __security_check_cookie
0x180026e6f  mov     rbx, [rsp+0E0h+arg_18]
0x180026e77  add     rsp, 0B0h
0x180026e7e  pop     r15
0x180026e80  pop     r14
0x180026e82  pop     r13
0x180026e84  pop     r12
0x180026e86  pop     rdi
0x180026e87  pop     rsi
0x180026e88  pop     rbp
0x180026e89  retn
```

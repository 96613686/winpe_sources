# HrComposeUpnpNotifyHeaders(ulong,ushort const *,ushort * *)

- ea: `0x180027cf0`
- end: `0x180027fbf`
- name: `?HrComposeUpnpNotifyHeaders@@YAJKPEBGPEAPEAG@Z`
- size: `719`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027700`

## callees

- `0x1800200f4`
- `0x180027cf0`
- `0x180028014`
- `0x18003cb60`
- `0x180048da4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027f27`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027f27`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180027d70`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180027d70`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180027d43`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180027d56`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180027d43`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180027d56`

## string_xrefs

- `0x180027f7e`: `HrComposeUpnpNotifyHeaders`
- `0x180027eda`: `text/xml; charset="utf-8"`

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
0x180027cf0  mov     [rsp-8+arg_18], rbx
0x180027cf5  push    rbp
0x180027cf6  push    rsi
0x180027cf7  push    rdi
0x180027cf8  push    r12
0x180027cfa  push    r13
0x180027cfc  push    r14
0x180027cfe  push    r15
0x180027d00  lea     rbp, [rsp-27h]
0x180027d05  sub     rsp, 0B0h
0x180027d0c  mov     rax, cs:__security_cookie
0x180027d13  xor     rax, rsp
0x180027d16  mov     [rbp+57h+var_40], rax
0x180027d1a  mov     r14, r8
0x180027d1d  mov     rsi, rdx
0x180027d20  mov     r9d, ecx
0x180027d23  lea     r8, aD; "%d"
0x180027d2a  mov     edx, 20h ; ' '; unsigned __int64
0x180027d2f  lea     rcx, [rbp+57h+String]; unsigned __int16 *
0x180027d33  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027d38  test    eax, eax
0x180027d3a  js      loc_180027F97
0x180027d40  mov     rcx, rsi; lpString
0x180027d43  call    cs:__imp_lstrlenW
0x180027d4a  nop     dword ptr [rax+rax+00h]
0x180027d4f  lea     rcx, [rbp+57h+String]; lpString
0x180027d53  lea     ebx, [rax+9]
0x180027d56  call    cs:__imp_lstrlenW
0x180027d5d  nop     dword ptr [rax+rax+00h]
0x180027d62  add     eax, 9
0x180027d65  add     rbx, rax
0x180027d68  lea     rcx, ds:0B2h[rbx*2]; Size
0x180027d70  call    cs:__imp_malloc
0x180027d77  nop     dword ptr [rax+rax+00h]
0x180027d7c  mov     rdi, rax
0x180027d7f  test    rax, rax
0x180027d82  jz      loc_180027F57
0x180027d88  mov     [rbp+57h+Buffer], rax
0x180027d8c  lea     rdx, [rbx+59h]; unsigned __int64
0x180027d90  lea     rax, aUpnpEvent; "upnp:event"
0x180027d97  mov     [rbp+57h+var_90], rdx
0x180027d9b  lea     r12, asc_180069554; "\r\n"
0x180027da2  mov     r15d, 800h
0x180027da8  mov     [rsp+0E0h+var_98], r12
0x180027dad  lea     r13, asc_1800695A8; ":"
0x180027db4  mov     [rsp+0E0h+var_A0], rax
0x180027db9  lea     r9, [rbp+57h+var_90]; unsigned __int64 *
0x180027dbd  mov     [rsp+0E0h+var_A8], r13
0x180027dc2  lea     rax, aNt; "NT"
0x180027dc9  mov     [rsp+0E0h+var_B0], rax
0x180027dce  lea     r8, [rbp+57h+Buffer]; unsigned __int16 **
0x180027dd2  lea     rax, aSSSS; "%s%s%s%s"
0x180027dd9  mov     rcx, rdi; Buffer
0x180027ddc  mov     [rsp+0E0h+var_B8], rax; unsigned __int16 *
0x180027de1  mov     [rsp+0E0h+var_C0], r15d; unsigned int
0x180027de6  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180027deb  mov     ebx, eax
0x180027ded  test    eax, eax
0x180027def  js      loc_180027F24
0x180027df5  mov     rdx, [rbp+57h+var_90]; unsigned __int64
0x180027df9  lea     rax, aUpnpPropchange; "upnp:propchange"
0x180027e00  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180027e04  lea     r9, [rbp+57h+var_90]; unsigned __int64 *
0x180027e08  mov     [rsp+0E0h+var_98], r12
0x180027e0d  lea     r8, [rbp+57h+Buffer]; unsigned __int16 **
0x180027e11  mov     [rsp+0E0h+var_A0], rax
0x180027e16  lea     rax, aNts; "NTS"
0x180027e1d  mov     [rsp+0E0h+var_A8], r13
0x180027e22  mov     [rsp+0E0h+var_B0], rax
0x180027e27  lea     rax, aSSSS; "%s%s%s%s"
0x180027e2e  mov     [rsp+0E0h+var_B8], rax; unsigned __int16 *
0x180027e33  mov     [rsp+0E0h+var_C0], r15d; unsigned int
0x180027e38  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180027e3d  mov     ebx, eax
0x180027e3f  test    eax, eax
0x180027e41  js      loc_180027F24
0x180027e47  mov     rdx, [rbp+57h+var_90]; unsigned __int64
0x180027e4b  lea     rax, aSid; "SID"
0x180027e52  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180027e56  lea     r9, [rbp+57h+var_90]; unsigned __int64 *
0x180027e5a  mov     [rsp+0E0h+var_98], r12
0x180027e5f  lea     r8, [rbp+57h+Buffer]; unsigned __int16 **
0x180027e63  mov     [rsp+0E0h+var_A0], rsi
0x180027e68  lea     rsi, aSSSS; "%s%s%s%s"
0x180027e6f  mov     [rsp+0E0h+var_A8], r13
0x180027e74  mov     [rsp+0E0h+var_B0], rax
0x180027e79  mov     [rsp+0E0h+var_B8], rsi; unsigned __int16 *
0x180027e7e  mov     [rsp+0E0h+var_C0], r15d; unsigned int
0x180027e83  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180027e88  mov     ebx, eax
0x180027e8a  test    eax, eax
0x180027e8c  js      loc_180027F24
0x180027e92  mov     rdx, [rbp+57h+var_90]; unsigned __int64
0x180027e96  lea     rax, [rbp+57h+String]
0x180027e9a  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180027e9e  lea     r9, [rbp+57h+var_90]; unsigned __int64 *
0x180027ea2  mov     [rsp+0E0h+var_98], r12
0x180027ea7  lea     r8, [rbp+57h+Buffer]; unsigned __int16 **
0x180027eab  mov     [rsp+0E0h+var_A0], rax
0x180027eb0  lea     rax, aSeq; "SEQ"
0x180027eb7  mov     [rsp+0E0h+var_A8], r13
0x180027ebc  mov     [rsp+0E0h+var_B0], rax
0x180027ec1  mov     [rsp+0E0h+var_B8], rsi; unsigned __int16 *
0x180027ec6  mov     [rsp+0E0h+var_C0], r15d; unsigned int
0x180027ecb  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180027ed0  mov     ebx, eax
0x180027ed2  test    eax, eax
0x180027ed4  js      short loc_180027F24
0x180027ed6  mov     rdx, [rbp+57h+var_90]; unsigned __int64
0x180027eda  lea     rax, aTextXmlCharset_0; "text/xml; charset=\"utf-8\""
0x180027ee1  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180027ee5  lea     r9, [rbp+57h+var_90]; unsigned __int64 *
0x180027ee9  mov     [rsp+0E0h+var_98], r12
0x180027eee  lea     r8, [rbp+57h+Buffer]; unsigned __int16 **
0x180027ef2  mov     [rsp+0E0h+var_A0], rax
0x180027ef7  lea     rax, aContentType_3; "Content-Type"
0x180027efe  mov     [rsp+0E0h+var_A8], r13
0x180027f03  mov     [rsp+0E0h+var_B0], rax
0x180027f08  mov     [rsp+0E0h+var_B8], rsi; unsigned __int16 *
0x180027f0d  mov     [rsp+0E0h+var_C0], r15d; unsigned int
0x180027f12  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180027f17  mov     ebx, eax
0x180027f19  test    eax, eax
0x180027f1b  js      short loc_180027F24
0x180027f1d  mov     [r14], rdi
0x180027f20  jnz     short loc_180027F5C
0x180027f22  jmp     short loc_180027F95
0x180027f24  mov     rcx, rdi; Block
0x180027f27  call    cs:__imp_free
0x180027f2e  nop     dword ptr [rax+rax+00h]
0x180027f33  test    ebx, ebx
0x180027f35  jz      short loc_180027F95
0x180027f37  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f3e  lea     rax, WPP_GLOBAL_Control
0x180027f45  cmp     rcx, rax
0x180027f48  jz      short loc_180027F95
0x180027f4a  test    byte ptr [rcx+1Ch], 1
0x180027f4e  jz      short loc_180027F95
0x180027f50  mov     edx, 6Bh ; 'k'
0x180027f55  jmp     short loc_180027F7A
0x180027f57  mov     ebx, 8007000Eh
0x180027f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f63  lea     rax, WPP_GLOBAL_Control
0x180027f6a  cmp     rcx, rax
0x180027f6d  jz      short loc_180027F95
0x180027f6f  test    byte ptr [rcx+1Ch], 1
0x180027f73  jz      short loc_180027F95
0x180027f75  mov     edx, 6Ah ; 'j'
0x180027f7a  mov     rcx, [rcx+10h]
0x180027f7e  lea     r9, aHrcomposeupnpn; "HrComposeUpnpNotifyHeaders"
0x180027f85  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180027f8c  mov     [rsp+0E0h+var_C0], ebx
0x180027f90  call    WPP_SF_sd
0x180027f95  mov     eax, ebx
0x180027f97  mov     rcx, [rbp+57h+var_40]
0x180027f9b  xor     rcx, rsp; StackCookie
0x180027f9e  call    __security_check_cookie
0x180027fa3  mov     rbx, [rsp+0E0h+arg_18]
0x180027fab  add     rsp, 0B0h
0x180027fb2  pop     r15
0x180027fb4  pop     r14
0x180027fb6  pop     r13
0x180027fb8  pop     r12
0x180027fba  pop     rdi
0x180027fbb  pop     rsi
0x180027fbc  pop     rbp
0x180027fbd  retn
```

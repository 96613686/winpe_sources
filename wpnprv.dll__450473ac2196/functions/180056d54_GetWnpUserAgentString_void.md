# GetWnpUserAgentString(void)

- ea: `0x180056d54`
- end: `0x180056ef4`
- name: `?GetWnpUserAgentString@@YAPEBDXZ`
- size: `416`
- prototype: `CHAR *(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800527dc`

## callees

- `0x18000c97c`
- `0x18000fe2c`
- `0x18000fe54`
- `0x180044698`
- `0x180056d54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180056e52`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180056e52`
- `urlmon!ObtainUserAgentString` at `0x180056dbf`
- `urlmon!ObtainUserAgentString` at `0x180056dbf`

## string_xrefs

- `0x180056dfe`: `Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 7.0;)`

## pseudocode

```c
CHAR *GetWnpUserAgentString(void)
{
  PVOID *v0; // rcx
  HRESULT v1; // eax
  int v2; // eax
  char *v3; // rax
  int v4; // eax
  DWORD cbSize; // [rsp+40h] [rbp+8h] BYREF

  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids);
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( Str )
    goto LABEL_24;
  cbSize = 2048;
  v1 = ObtainUserAgentString(0, &Str, &cbSize);
  if ( v1 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
      (unsigned int)v1);
  }
  if ( !Str )
  {
    v2 = StringCchCopyA(&Str, 0x800u, "Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 7.0;)");
    if ( v2 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
        (unsigned int)v2);
    }
  }
  v3 = strrchr(&Str, 41);
  if ( !v3 )
    goto LABEL_23;
  v4 = StringCchPrintfA(v3, (char *)&CWnpConnector::s_pSSPI - v3, "; %hs %hs)", "WnpTrans", "10.0.10011.16384");
  if ( v4 >= 0 )
    goto LABEL_23;
  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return &Str;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
      (unsigned int)v4);
LABEL_23:
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_24:
  if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 4) != 0 && *((_BYTE *)v0 + 25) >= 6u )
    WPP_SF_(v0[2], 15, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids);
  return &Str;
}

```

## disassembly

```asm
0x180056d54  mov     [rsp+arg_8], rsi
0x180056d59  push    rdi
0x180056d5a  sub     rsp, 30h
0x180056d5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180056d65  lea     rdi, WPP_GLOBAL_Control
0x180056d6c  lea     rsi, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x180056d73  cmp     rcx, rdi
0x180056d76  jz      short loc_180056D9C
0x180056d78  test    byte ptr [rcx+1Ch], 4
0x180056d7c  jz      short loc_180056D9C
0x180056d7e  cmp     byte ptr [rcx+19h], 6
0x180056d82  jb      short loc_180056D9C
0x180056d84  mov     rcx, [rcx+10h]
0x180056d88  mov     edx, 0Ah
0x180056d8d  mov     r8, rsi
0x180056d90  call    WPP_SF_
0x180056d95  mov     rcx, cs:WPP_GLOBAL_Control
0x180056d9c  cmp     cs:Str, 0
0x180056da3  jnz     loc_180056EC0
0x180056da9  lea     r8, [rsp+38h+cbSize]; cbSize
0x180056dae  mov     [rsp+38h+cbSize], 800h
0x180056db6  lea     rdx, Str; pszUAOut
0x180056dbd  xor     ecx, ecx; dwOption
0x180056dbf  call    cs:__imp_ObtainUserAgentString
0x180056dc5  test    eax, eax
0x180056dc7  jns     short loc_180056DF5
0x180056dc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180056dd0  cmp     rcx, rdi
0x180056dd3  jz      short loc_180056DF5
0x180056dd5  test    byte ptr [rcx+1Ch], 4
0x180056dd9  jz      short loc_180056DF5
0x180056ddb  cmp     byte ptr [rcx+19h], 2
0x180056ddf  jb      short loc_180056DF5
0x180056de1  mov     rcx, [rcx+10h]
0x180056de5  mov     edx, 0Bh
0x180056dea  mov     r9d, eax
0x180056ded  mov     r8, rsi
0x180056df0  call    WPP_SF_d
0x180056df5  cmp     cs:Str, 0
0x180056dfc  jnz     short loc_180056E46
0x180056dfe  lea     r8, aMozilla40Compa; "Mozilla/4.0 (compatible; MSIE 7.0; Wind"...
0x180056e05  mov     edx, 800h; unsigned __int64
0x180056e0a  lea     rcx, Str; char *
0x180056e11  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180056e16  test    eax, eax
0x180056e18  jns     short loc_180056E46
0x180056e1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180056e21  cmp     rcx, rdi
0x180056e24  jz      short loc_180056E46
0x180056e26  test    byte ptr [rcx+1Ch], 4
0x180056e2a  jz      short loc_180056E46
0x180056e2c  cmp     byte ptr [rcx+19h], 2
0x180056e30  jb      short loc_180056E46
0x180056e32  mov     rcx, [rcx+10h]
0x180056e36  mov     edx, 0Dh
0x180056e3b  mov     r9d, eax
0x180056e3e  mov     r8, rsi
0x180056e41  call    WPP_SF_d
0x180056e46  mov     edx, 29h ; ')'; Ch
0x180056e4b  lea     rcx, Str; Str
0x180056e52  call    cs:__imp_strrchr
0x180056e58  test    rax, rax
0x180056e5b  jz      short loc_180056EB9
0x180056e5d  lea     rcx, a1001001116384; "10.0.10011.16384"
0x180056e64  mov     [rsp+38h+var_18], rcx
0x180056e69  lea     rdx, ?s_pSSPI@CWnpConnector@@0PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * CWnpConnector::s_pSSPI
0x180056e70  mov     rcx, rax; char *
0x180056e73  lea     r9, aWnptrans; "WnpTrans"
0x180056e7a  sub     rdx, rax; unsigned __int64
0x180056e7d  lea     r8, aHsHs_1; "; %hs %hs)"
0x180056e84  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180056e89  test    eax, eax
0x180056e8b  jns     short loc_180056EB9
0x180056e8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056e94  cmp     rcx, rdi
0x180056e97  jz      short loc_180056EE2
0x180056e99  test    byte ptr [rcx+1Ch], 4
0x180056e9d  jz      short loc_180056EC0
0x180056e9f  cmp     byte ptr [rcx+19h], 2
0x180056ea3  jb      short loc_180056EC0
0x180056ea5  mov     rcx, [rcx+10h]
0x180056ea9  mov     edx, 0Eh
0x180056eae  mov     r9d, eax
0x180056eb1  mov     r8, rsi
0x180056eb4  call    WPP_SF_d
0x180056eb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ec0  cmp     rcx, rdi
0x180056ec3  jz      short loc_180056EE2
0x180056ec5  test    byte ptr [rcx+1Ch], 4
0x180056ec9  jz      short loc_180056EE2
0x180056ecb  cmp     byte ptr [rcx+19h], 6
0x180056ecf  jb      short loc_180056EE2
0x180056ed1  mov     rcx, [rcx+10h]
0x180056ed5  mov     edx, 0Fh
0x180056eda  mov     r8, rsi
0x180056edd  call    WPP_SF_
0x180056ee2  mov     rsi, [rsp+38h+arg_8]
0x180056ee7  lea     rax, Str
0x180056eee  add     rsp, 30h
0x180056ef2  pop     rdi
0x180056ef3  retn
```

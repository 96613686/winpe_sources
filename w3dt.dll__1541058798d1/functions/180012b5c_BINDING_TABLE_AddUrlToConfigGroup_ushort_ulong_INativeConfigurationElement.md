# BINDING_TABLE::AddUrlToConfigGroup(ushort *,ulong,INativeConfigurationElement *)

- ea: `0x180012b5c`
- end: `0x180012d3c`
- name: `?AddUrlToConfigGroup@BINDING_TABLE@@AEAAJPEAGKPEAVINativeConfigurationElement@@@Z`
- size: `480`
- prototype: `int(BINDING_TABLE *__hidden this, unsigned __int16 *, unsigned int, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800108c0`

## callees

- `0x180012b5c`
- `0x1800134a8`
- `0x180013ed8`
- `0x180015e44`
- `0x1800160a0`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180012b8f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012b8f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012d18`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012d18`
- `iisutil!PuDbgPrintError` at `0x180012d02`
- `iisutil!PuDbgPrintError` at `0x180012d02`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012c1c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012c94`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012ca3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012c1c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012c94`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012ca3`

## string_xrefs

- `0x180012cd2`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x180012cc6`: `BINDING_TABLE::AddUrlToConfigGroup`
- `0x180012cf2`: `Failed to set w3c control channel logging info\n   LogPeriod = %d \n   LogFileTruncateSize = %d \n   LogFileDirectory = %S \n   LocalFiletimeRollover = %S \n`

## pseudocode

```c
__int64 __fastcall BINDING_TABLE::AddUrlToConfigGroup(
        BINDING_TABLE *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct INativeConfigurationElement *a4)
{
  int v8; // eax
  signed int SiteHttpLogInfo; // ebx
  int v10; // eax
  unsigned __int16 *Str; // rax
  signed int v12; // edi
  const wchar_t *v13; // rsi
  const wchar_t *v14; // rax
  unsigned int v16; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v17; // [rsp+54h] [rbp-35h]
  unsigned int v18; // [rsp+58h] [rbp-31h]
  enum _HTTP_LOGGING_TYPE v19; // [rsp+5Ch] [rbp-2Dh]
  int v20; // [rsp+60h] [rbp-29h]
  int v21; // [rsp+64h] [rbp-25h]
  _BYTE v22[56]; // [rsp+68h] [rbp-21h] BYREF

  STRU::STRU((STRU *)v22);
  v8 = HTTP_WRAPPER::AddUrlToConfigGroup(
         (BINDING_TABLE *)((char *)this + 352),
         *((_QWORD *)this + 48),
         a2,
         a3,
         *((_DWORD *)this + 100));
  SiteHttpLogInfo = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      SiteHttpLogInfo = (unsigned __int16)v8 | 0x80070000;
  }
  else
  {
    v10 = *((_DWORD *)this + 100);
    SiteHttpLogInfo = 0;
    if ( v10 == -1 )
    {
      *((_DWORD *)this + 100) = 0;
    }
    else if ( v10 )
    {
      *((_DWORD *)this + 100) = v10 + 1;
    }
    if ( !*((_DWORD *)this + 101) )
    {
      SiteHttpLogInfo = ReadSiteHttpLogInfo(a4, (struct SITE_HTTP_LOG_SETTINGS *)&v16);
      if ( SiteHttpLogInfo >= 0 )
      {
        Str = STRU::QueryStr((STRU *)v22);
        v12 = HTTP_WRAPPER::SetConfigGroupLogging(
                (BINDING_TABLE *)((char *)this + 352),
                *((_QWORD *)this + 48),
                v21,
                Str,
                v19,
                v16,
                v17,
                v18,
                v20,
                0);
        if ( v12 )
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            v13 = L"TRUE";
            if ( !v20 )
              v13 = L"FALSE";
            if ( STRU::QueryStr((STRU *)v22) )
              v14 = STRU::QueryStr((STRU *)v22);
            else
              v14 = L"<NULL>";
            if ( v12 > 0 )
              v12 = (unsigned __int16)v12 | 0x80070000;
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
              523,
              "BINDING_TABLE::AddUrlToConfigGroup",
              v12,
              "Failed to set w3c control channel logging info\n"
              "   LogPeriod = %d \n"
              "   LogFileTruncateSize = %d \n"
              "   LogFileDirectory = %S \n"
              "   LocalFiletimeRollover = %S \n",
              v16,
              v17,
              v14,
              v13);
          }
        }
        else
        {
          *((_DWORD *)this + 101) = 1;
        }
      }
    }
  }
  STRU::~STRU((STRU *)v22);
  return (unsigned int)SiteHttpLogInfo;
}

```

## disassembly

```asm
0x180012b5c  push    rbp
0x180012b5e  push    rbx
0x180012b5f  push    rsi
0x180012b60  push    rdi
0x180012b61  push    r14
0x180012b63  push    r15
0x180012b65  lea     rbp, [rsp-2Fh]
0x180012b6a  sub     rsp, 0B8h
0x180012b71  mov     rax, cs:__security_cookie
0x180012b78  xor     rax, rsp
0x180012b7b  mov     [rbp+57h+var_40], rax
0x180012b7f  mov     rsi, rcx
0x180012b82  mov     r14, r9
0x180012b85  lea     rcx, [rbp+57h+var_78]
0x180012b89  mov     edi, r8d
0x180012b8c  mov     rbx, rdx
0x180012b8f  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180012b95  mov     eax, [rsi+190h]
0x180012b9b  lea     r15, [rsi+160h]
0x180012ba2  mov     rdx, [rsi+180h]; unsigned __int64
0x180012ba9  mov     rcx, r15; this
0x180012bac  mov     r9d, edi; unsigned int
0x180012baf  mov     [rsp+0E0h+var_C0], eax; unsigned int
0x180012bb3  mov     r8, rbx; unsigned __int16 *
0x180012bb6  call    ?AddUrlToConfigGroup@HTTP_WRAPPER@@QEAAK_KPEBGKK@Z; HTTP_WRAPPER::AddUrlToConfigGroup(unsigned __int64,ushort const *,ulong,ulong)
0x180012bbb  mov     ebx, eax
0x180012bbd  test    eax, eax
0x180012bbf  jz      short loc_180012BD5
0x180012bc1  jle     loc_180012D14
0x180012bc7  movzx   ebx, ax
0x180012bca  or      ebx, 80070000h
0x180012bd0  jmp     loc_180012D14
0x180012bd5  mov     eax, [rsi+190h]
0x180012bdb  xor     ebx, ebx
0x180012bdd  cmp     eax, 0FFFFFFFFh
0x180012be0  jnz     short loc_180012BEA
0x180012be2  mov     [rsi+190h], ebx
0x180012be8  jmp     short loc_180012BF6
0x180012bea  test    eax, eax
0x180012bec  jz      short loc_180012BF6
0x180012bee  inc     eax
0x180012bf0  mov     [rsi+190h], eax
0x180012bf6  cmp     [rsi+194h], ebx
0x180012bfc  jnz     loc_180012D14
0x180012c02  lea     rdx, [rbp+57h+var_90]; struct SITE_HTTP_LOG_SETTINGS *
0x180012c06  mov     rcx, r14; struct INativeConfigurationElement *
0x180012c09  call    ?ReadSiteHttpLogInfo@@YAJPEAVINativeConfigurationElement@@PEAUSITE_HTTP_LOG_SETTINGS@@@Z; ReadSiteHttpLogInfo(INativeConfigurationElement *,SITE_HTTP_LOG_SETTINGS *)
0x180012c0e  mov     ebx, eax
0x180012c10  test    eax, eax
0x180012c12  js      loc_180012D14
0x180012c18  lea     rcx, [rbp+57h+var_78]
0x180012c1c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180012c22  mov     edx, [rbp+57h+var_80]
0x180012c25  mov     rcx, r15; this
0x180012c28  mov     r8d, [rbp+57h+var_7C]; int
0x180012c2c  mov     r9, rax; unsigned __int16 *
0x180012c2f  mov     [rsp+0E0h+var_98], 0; int
0x180012c37  mov     [rsp+0E0h+var_A0], edx; int
0x180012c3b  mov     edx, [rbp+57h+var_88]
0x180012c3e  mov     [rsp+0E0h+var_A8], edx; unsigned int
0x180012c42  mov     edx, [rbp+57h+var_8C]
0x180012c45  mov     [rsp+0E0h+var_B0], edx; unsigned int
0x180012c49  mov     edx, [rbp+57h+var_90]
0x180012c4c  mov     [rsp+0E0h+var_B8], edx; unsigned int
0x180012c50  mov     edx, [rbp+57h+var_84]
0x180012c53  mov     [rsp+0E0h+var_C0], edx; enum _HTTP_LOGGING_TYPE
0x180012c57  mov     rdx, [rsi+180h]; UrlGroupId
0x180012c5e  call    ?SetConfigGroupLogging@HTTP_WRAPPER@@QEAAK_KHPEAGW4_HTTP_LOGGING_TYPE@@KKKHH@Z; HTTP_WRAPPER::SetConfigGroupLogging(unsigned __int64,int,ushort *,_HTTP_LOGGING_TYPE,ulong,ulong,ulong,int,int)
0x180012c63  mov     edi, eax
0x180012c65  test    eax, eax
0x180012c67  jz      loc_180012D0A
0x180012c6d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180012c74  jz      loc_180012D14
0x180012c7a  cmp     [rbp+57h+var_80], 0
0x180012c7e  lea     rax, aFalse; "FALSE"
0x180012c85  lea     rsi, aTrue; "TRUE"
0x180012c8c  lea     rcx, [rbp+57h+var_78]
0x180012c90  cmovz   rsi, rax
0x180012c94  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180012c9a  test    rax, rax
0x180012c9d  jz      short loc_180012CAB
0x180012c9f  lea     rcx, [rbp+57h+var_78]
0x180012ca3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180012ca9  jmp     short loc_180012CB2
0x180012cab  lea     rax, aNull_0; "<NULL>"
0x180012cb2  test    edi, edi
0x180012cb4  jle     short loc_180012CBF
0x180012cb6  movzx   edi, di
0x180012cb9  or      edi, 80070000h
0x180012cbf  mov     rcx, cs:g_pDebug
0x180012cc6  lea     r9, aBindingTableAd; "BINDING_TABLE::AddUrlToConfigGroup"
0x180012ccd  mov     qword ptr [rsp+0E0h+var_98], rsi
0x180012cd2  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180012cd9  mov     qword ptr [rsp+0E0h+var_A0], rax
0x180012cde  mov     r8d, 20Bh
0x180012ce4  mov     eax, [rbp+57h+var_8C]
0x180012ce7  mov     [rsp+0E0h+var_A8], eax
0x180012ceb  mov     eax, [rbp+57h+var_90]
0x180012cee  mov     [rsp+0E0h+var_B0], eax
0x180012cf2  lea     rax, aFailedToSetW3c; "Failed to set w3c control channel loggi"...
0x180012cf9  mov     qword ptr [rsp+0E0h+var_B8], rax
0x180012cfe  mov     [rsp+0E0h+var_C0], edi
0x180012d02  call    cs:__imp_PuDbgPrintError
0x180012d08  jmp     short loc_180012D14
0x180012d0a  mov     dword ptr [rsi+194h], 1
0x180012d14  lea     rcx, [rbp+57h+var_78]
0x180012d18  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180012d1e  mov     eax, ebx
0x180012d20  mov     rcx, [rbp+57h+var_40]
0x180012d24  xor     rcx, rsp; StackCookie
0x180012d27  call    __security_check_cookie
0x180012d2c  add     rsp, 0B8h
0x180012d33  pop     r15
0x180012d35  pop     r14
0x180012d37  pop     rdi
0x180012d38  pop     rsi
0x180012d39  pop     rbx
0x180012d3a  pop     rbp
0x180012d3b  retn
```

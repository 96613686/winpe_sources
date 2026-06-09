# HTTP_LOG_FILE_CONFIG::Initialize(ulong,ushort const *,int,IAppHostElement *)

- ea: `0x180007744`
- end: `0x18000797b`
- name: `?Initialize@HTTP_LOG_FILE_CONFIG@@AEAAJKPEBGHPEAUIAppHostElement@@@Z`
- size: `567`
- prototype: `__int64 __fastcall(HTTP_LOG_FILE_CONFIG *this, unsigned int Value, const unsigned __int16 *, int, struct IAppHostElement *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x1800073e8`

## callees

- `0x180006df8`
- `0x180006f4c`
- `0x180007170`
- `0x180007294`
- `0x180007744`
- `0x180007a44`
- `0x18000e9a0`
- `0x180010010`

## import_xrefs

- `msvcrt!_ultow` at `0x180007929`
- `msvcrt!_ultow` at `0x180007929`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000795b`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000795b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007782`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007782`

## string_xrefs

- `0x180007898`: `directory`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_FILE_CONFIG::Initialize(
        HTTP_LOG_FILE_CONFIG *this,
        unsigned int Value,
        const unsigned __int16 *a3,
        int a4,
        struct IAppHostElement *a5)
{
  signed int BoolProperty; // ebx
  struct IAppHostElement *v10; // [rsp+30h] [rbp-58h] BYREF
  wchar_t *v11; // [rsp+38h] [rbp-50h] BYREF
  wchar_t Buffer[12]; // [rsp+40h] [rbp-48h] BYREF

  *((_DWORD *)this + 8) = Value;
  v10 = 0;
  BoolProperty = STRU::Copy((HTTP_LOG_FILE_CONFIG *)((char *)this + 48), a3);
  if ( BoolProperty >= 0 )
  {
    BoolProperty = Config_GetBoolProperty(a5, L"enabled", (int *)this);
    if ( BoolProperty >= 0 )
    {
      BoolProperty = Config_GetBoolProperty(a5, L"localTimeRollover", (int *)this + 1);
      if ( BoolProperty >= 0 )
      {
        BoolProperty = Config_GetBoolProperty(a5, L"logSiteId", (int *)this + 2);
        if ( BoolProperty >= 0 )
        {
          *((_DWORD *)this + 3) = a4;
          BoolProperty = Config_GetDWORDProperty(a5, L"logExtFileFlags", (unsigned int *)this + 4);
          if ( BoolProperty >= 0 )
          {
            BoolProperty = Config_GetDWORDProperty(a5, L"logFormat", (unsigned int *)this + 5);
            if ( BoolProperty >= 0 )
            {
              BoolProperty = Config_GetDWORDProperty(a5, L"period", (unsigned int *)this + 6);
              if ( BoolProperty >= 0 )
              {
                BoolProperty = Config_GetDWORDProperty(a5, L"truncateSize", (unsigned int *)this + 7);
                if ( BoolProperty >= 0 )
                {
                  BoolProperty = Config_GetDWORDProperty(a5, L"flushByEntryCountW3cLog", (unsigned int *)this + 9);
                  if ( BoolProperty >= 0 )
                  {
                    BoolProperty = Config_GetDWORDProperty(a5, L"logTargetW3C", (unsigned int *)this + 10);
                    if ( BoolProperty >= 0 )
                    {
                      BoolProperty = Config_GetStringProperty(
                                       a5,
                                       L"directory",
                                       (HTTP_LOG_FILE_CONFIG *)((char *)this + 104));
                      if ( BoolProperty >= 0 )
                      {
                        BoolProperty = Config_GetDWORDProperty(a5, L"maxLogLineLength", (unsigned int *)this + 55);
                        if ( BoolProperty >= 0 )
                        {
                          BoolProperty = Config_GetSubElement(a5, L"customFields", &v10);
                          if ( BoolProperty >= 0 )
                            BoolProperty = HTTP_LOG_FILE_CONFIG::PopulateCustomFieldsCollection(this, v10);
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v10 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v10->lpVtbl->Release)(v10);
    v10 = 0;
  }
  if ( BoolProperty < 0 )
  {
    v11 = 0;
    _ultow(Value, Buffer, 10);
    v11 = Buffer;
    EVENT_LOG::LogEvent(
      (EVENT_LOG *)((char *)g_pLogSvcAdmin + 1896),
      0xC000177A,
      1u,
      (const unsigned __int16 **const)&v11,
      BoolProperty);
  }
  return (unsigned int)BoolProperty;
}

```

## disassembly

```asm
0x180007744  push    rbx
0x180007746  push    rbp
0x180007747  push    rsi
0x180007748  push    rdi
0x180007749  push    r14
0x18000774b  sub     rsp, 60h
0x18000774f  mov     rax, cs:__security_cookie
0x180007756  xor     rax, rsp
0x180007759  mov     [rsp+88h+var_30], rax
0x18000775e  mov     rsi, [rsp+88h+arg_20]
0x180007766  mov     r14d, edx
0x180007769  mov     [rcx+20h], edx
0x18000776c  mov     rdi, rcx
0x18000776f  add     rcx, 30h ; '0'
0x180007773  mov     [rsp+88h+var_58], 0
0x18000777c  mov     rdx, r8
0x18000777f  mov     ebp, r9d
0x180007782  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180007788  mov     ebx, eax
0x18000778a  test    eax, eax
0x18000778c  js      loc_1800078EF
0x180007792  mov     r8, rdi; int *
0x180007795  lea     rdx, aEnabled; "enabled"
0x18000779c  mov     rcx, rsi; struct IAppHostElement *
0x18000779f  call    ?Config_GetBoolProperty@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; Config_GetBoolProperty(IAppHostElement *,ushort const *,int *)
0x1800077a4  mov     ebx, eax
0x1800077a6  test    eax, eax
0x1800077a8  js      loc_1800078EF
0x1800077ae  lea     r8, [rdi+4]; int *
0x1800077b2  mov     rcx, rsi; struct IAppHostElement *
0x1800077b5  lea     rdx, aLocaltimerollo; "localTimeRollover"
0x1800077bc  call    ?Config_GetBoolProperty@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; Config_GetBoolProperty(IAppHostElement *,ushort const *,int *)
0x1800077c1  mov     ebx, eax
0x1800077c3  test    eax, eax
0x1800077c5  js      loc_1800078EF
0x1800077cb  lea     r8, [rdi+8]; int *
0x1800077cf  mov     rcx, rsi; struct IAppHostElement *
0x1800077d2  lea     rdx, aLogsiteid; "logSiteId"
0x1800077d9  call    ?Config_GetBoolProperty@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; Config_GetBoolProperty(IAppHostElement *,ushort const *,int *)
0x1800077de  mov     ebx, eax
0x1800077e0  test    eax, eax
0x1800077e2  js      loc_1800078EF
0x1800077e8  lea     r8, [rdi+10h]; unsigned int *
0x1800077ec  mov     [rdi+0Ch], ebp
0x1800077ef  lea     rdx, aLogextfileflag; "logExtFileFlags"
0x1800077f6  mov     rcx, rsi; struct IAppHostElement *
0x1800077f9  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x1800077fe  mov     ebx, eax
0x180007800  test    eax, eax
0x180007802  js      loc_1800078EF
0x180007808  lea     r8, [rdi+14h]; unsigned int *
0x18000780c  mov     rcx, rsi; struct IAppHostElement *
0x18000780f  lea     rdx, aLogformat; "logFormat"
0x180007816  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x18000781b  mov     ebx, eax
0x18000781d  test    eax, eax
0x18000781f  js      loc_1800078EF
0x180007825  lea     r8, [rdi+18h]; unsigned int *
0x180007829  mov     rcx, rsi; struct IAppHostElement *
0x18000782c  lea     rdx, aPeriod; "period"
0x180007833  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x180007838  mov     ebx, eax
0x18000783a  test    eax, eax
0x18000783c  js      loc_1800078EF
0x180007842  lea     r8, [rdi+1Ch]; unsigned int *
0x180007846  mov     rcx, rsi; struct IAppHostElement *
0x180007849  lea     rdx, aTruncatesize; "truncateSize"
0x180007850  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x180007855  mov     ebx, eax
0x180007857  test    eax, eax
0x180007859  js      loc_1800078EF
0x18000785f  lea     r8, [rdi+24h]; unsigned int *
0x180007863  mov     rcx, rsi; struct IAppHostElement *
0x180007866  lea     rdx, aFlushbyentryco; "flushByEntryCountW3cLog"
0x18000786d  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x180007872  mov     ebx, eax
0x180007874  test    eax, eax
0x180007876  js      short loc_1800078EF
0x180007878  lea     r8, [rdi+28h]; unsigned int *
0x18000787c  mov     rcx, rsi; struct IAppHostElement *
0x18000787f  lea     rdx, aLogtargetw3c; "logTargetW3C"
0x180007886  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x18000788b  mov     ebx, eax
0x18000788d  test    eax, eax
0x18000788f  js      short loc_1800078EF
0x180007891  lea     r8, [rdi+68h]; struct STRU *
0x180007895  mov     rcx, rsi; struct IAppHostElement *
0x180007898  lea     rdx, aDirectory; "directory"
0x18000789f  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAVSTRU@@@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,STRU *)
0x1800078a4  mov     ebx, eax
0x1800078a6  test    eax, eax
0x1800078a8  js      short loc_1800078EF
0x1800078aa  lea     r8, [rdi+0DCh]; unsigned int *
0x1800078b1  mov     rcx, rsi; struct IAppHostElement *
0x1800078b4  lea     rdx, aMaxloglineleng; "maxLogLineLength"
0x1800078bb  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x1800078c0  mov     ebx, eax
0x1800078c2  test    eax, eax
0x1800078c4  js      short loc_1800078EF
0x1800078c6  lea     r8, [rsp+88h+var_58]; struct IAppHostElement **
0x1800078cb  mov     rcx, rsi; struct IAppHostElement *
0x1800078ce  lea     rdx, aCustomfields; "customFields"
0x1800078d5  call    ?Config_GetSubElement@@YAJPEAUIAppHostElement@@PEBGPEAPEAU1@@Z; Config_GetSubElement(IAppHostElement *,ushort const *,IAppHostElement * *)
0x1800078da  mov     ebx, eax
0x1800078dc  test    eax, eax
0x1800078de  js      short loc_1800078EF
0x1800078e0  mov     rdx, [rsp+88h+var_58]; struct IAppHostElement *
0x1800078e5  mov     rcx, rdi; this
0x1800078e8  call    ?PopulateCustomFieldsCollection@HTTP_LOG_FILE_CONFIG@@AEAAJPEAUIAppHostElement@@@Z; HTTP_LOG_FILE_CONFIG::PopulateCustomFieldsCollection(IAppHostElement *)
0x1800078ed  mov     ebx, eax
0x1800078ef  mov     rcx, [rsp+88h+var_58]
0x1800078f4  test    rcx, rcx
0x1800078f7  jz      short loc_18000790E
0x1800078f9  mov     rax, [rcx]
0x1800078fc  mov     rax, [rax+10h]
0x180007900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007905  mov     [rsp+88h+var_58], 0
0x18000790e  test    ebx, ebx
0x180007910  jns     short loc_180007961
0x180007912  mov     r8d, 0Ah; Radix
0x180007918  mov     [rsp+88h+var_50], 0
0x180007921  lea     rdx, [rsp+88h+Buffer]; Buffer
0x180007926  mov     ecx, r14d; Value
0x180007929  call    cs:__imp__ultow
0x18000792f  mov     rcx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x180007936  lea     rax, [rsp+88h+Buffer]
0x18000793b  add     rcx, 768h
0x180007942  mov     [rsp+88h+var_50], rax
0x180007947  mov     r8d, 1
0x18000794d  mov     [rsp+88h+var_68], ebx
0x180007951  lea     r9, [rsp+88h+var_50]
0x180007956  mov     edx, 0C000177Ah
0x18000795b  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180007961  mov     eax, ebx
0x180007963  mov     rcx, [rsp+88h+var_30]
0x180007968  xor     rcx, rsp; StackCookie
0x18000796b  call    __security_check_cookie
0x180007970  add     rsp, 60h
0x180007974  pop     r14
0x180007976  pop     rdi
0x180007977  pop     rsi
0x180007978  pop     rbp
0x180007979  pop     rbx
0x18000797a  retn
```

# TpmResumeFromHibernation

- ea: `0x140006838`
- end: `0x140006b6a`
- name: `TpmResumeFromHibernation`
- size: `818`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x14000660c`
- `0x1400110f0`

## callees

- `0x140006838`
- `0x140009fc8`
- `0x14000b6c8`
- `0x14000b9a4`
- `0x140010eb8`
- `0x14001d63c`
- `0x140039740`
- `0x140039b40`
- `0x140045430`
- `0x1400454a0`

## import_xrefs

- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400069a8`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140006a10`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400069a8`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140006a10`

## string_xrefs

- `0x14000699a`: `TpmDriverLogPath`
- `0x1400069fe`: `TpmDriverLogPath`
- `0x140006967`: `WBCLPath`

## pseudocode

```c
__int64 TpmResumeFromHibernation()
{
  wchar_t *v0; // rdi
  int v1; // eax
  NTSTATUS Value; // ebx
  int v3; // eax
  __int64 v5; // [rsp+20h] [rbp-E0h]
  __int64 v6; // [rsp+20h] [rbp-E0h]
  __int64 v7; // [rsp+28h] [rbp-D8h]
  __int64 v8; // [rsp+28h] [rbp-D8h]
  int v9; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v10; // [rsp+44h] [rbp-BCh] BYREF
  size_t pcchLength; // [rsp+50h] [rbp-B0h] BYREF
  int v12; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszDest[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Dst[280]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t Src[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  unsigned __int64 retaddr; // [rsp+6E8h] [rbp+5E8h]

  memset(Src, 0, 0x208u);
  memset(pszDest, 0, 520);
  v9 = 0;
  v0 = 0;
  pcchLength = 0;
  v10 = 0;
  memset(Dst, 0, sizeof(Dst));
  if ( (int)TpmRegistry::QueryValue(1, L"OsResumeCount", 4, &v9, 4, 0) >= 0 )
    v1 = v9;
  else
    v1 = 0;
  v9 = v1 + 1;
  v12 = v1 + 1;
  Value = TpmRegistry::AssignValue(1, L"OsResumeCount", 4, &v12, 4);
  if ( Value < 0 )
    goto LABEL_21;
  Value = TpmRegistry::QueryValue(0, L"OsBootCount", 4, (char *)&v10 + 4, 4, 0);
  if ( Value < 0 )
    goto LABEL_21;
  v3 = TpmRegistry::QueryValue(0, L"WBCLPath", 1, Src, 520, 0);
  Value = v3;
  if ( v3 != -1073741772 )
  {
    if ( v3 >= 0 )
    {
      TpmConvertFilePathToObjectPath(Dst, Src);
      v0 = Dst;
LABEL_14:
      LODWORD(v7) = v9;
      LODWORD(v5) = HIDWORD(v10);
      Value = RtlStringCchPrintfW(pszDest, 0x104u, L"%s\\%010u-%010u.log", v0, v5, v7);
      if ( Value >= 0 )
      {
        Value = RtlStringCchLengthW(pszDest, 0x104u, &pcchLength);
        if ( Value >= 0 )
        {
          Value = TpmRegistry::AssignValue(1, L"PlatformLogFile", 1, pszDest, 2 * (int)pcchLength + 2);
          if ( Value >= 0 )
          {
            LODWORD(v8) = v9;
            LODWORD(v6) = HIDWORD(v10);
            Value = RtlStringCchPrintfW(pszDest, 0x104u, L"%s\\%010u-%010u-DRTM.log", v0, v6, v8);
            if ( Value >= 0 )
            {
              Value = RtlStringCchLengthW(pszDest, 0x104u, &pcchLength);
              if ( Value >= 0 )
                Value = TpmRegistry::AssignValue(1, L"PlatformLogFileDrtm", 1, pszDest, 2 * (int)pcchLength + 2);
            }
          }
        }
      }
      goto LABEL_20;
    }
LABEL_21:
    TpmFree(v0);
    return (unsigned int)Value;
  }
  Value = RtlGetPersistedStateLocation(L"TpmDriverLogPath", 0, L"\\SystemRoot\\Logs\\MeasuredBoot", 1, 0, 0, &v10);
  if ( Value != -2147483643 )
    goto LABEL_21;
  v0 = (wchar_t *)TpmAlloc(1, (unsigned int)v10, retaddr);
  if ( !v0 )
  {
    Value = -1073741670;
    goto LABEL_20;
  }
  Value = RtlGetPersistedStateLocation(L"TpmDriverLogPath", 0, L"\\SystemRoot\\Logs\\MeasuredBoot", 1, v0, v10, &v10);
  if ( Value >= 0 )
    goto LABEL_14;
LABEL_20:
  if ( v0 != Dst )
    goto LABEL_21;
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x140006838  push    rbp
0x14000683a  push    rbx
0x14000683b  push    rdi
0x14000683c  push    r14
0x14000683e  push    r15
0x140006840  lea     rbp, [rsp-5C0h]
0x140006848  sub     rsp, 6C0h
0x14000684f  mov     rax, cs:__security_cookie
0x140006856  xor     rax, rsp
0x140006859  mov     [rbp+5E0h+var_30], rax
0x140006860  xor     edx, edx; Val
0x140006862  lea     rcx, [rbp+5E0h+Src]; void *
0x140006869  mov     r8d, 208h; Size
0x14000686f  call    memset
0x140006874  xor     eax, eax
0x140006876  mov     dword ptr [rsp+6E0h+var_69C+4], 0
0x14000687e  xor     edx, edx; Val
0x140006880  mov     [rsp+6E0h+pszDest], ax
0x140006885  mov     r8d, 206h; Size
0x14000688b  mov     [rsp+6E0h+var_6A0], 0
0x140006893  lea     rcx, [rsp+6E0h+var_67E]; void *
0x140006898  call    memset
0x14000689d  xor     edi, edi
0x14000689f  mov     [rsp+6E0h+pcchLength], 0
0x1400068a8  xor     edx, edx; Val
0x1400068aa  mov     dword ptr [rsp+6E0h+var_69C], edi
0x1400068ae  mov     r8d, 230h; Size
0x1400068b4  lea     rcx, [rbp+5E0h+Dst]; void *
0x1400068bb  call    memset
0x1400068c0  lea     r15d, [rdi+4]
0x1400068c4  mov     [rsp+6E0h+var_6B8], rdi
0x1400068c9  lea     r14d, [rdi+1]
0x1400068cd  mov     dword ptr [rsp+6E0h+var_6C0], r15d
0x1400068d2  mov     r8d, r15d
0x1400068d5  lea     r9, [rsp+6E0h+var_6A0]
0x1400068da  mov     ecx, r14d
0x1400068dd  lea     rdx, aOsresumecount; "OsResumeCount"
0x1400068e4  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x1400068e9  test    eax, eax
0x1400068eb  jns     short loc_1400068F1
0x1400068ed  xor     eax, eax
0x1400068ef  jmp     short loc_1400068F5
0x1400068f1  mov     eax, [rsp+6E0h+var_6A0]
0x1400068f5  add     eax, r14d
0x1400068f8  mov     dword ptr [rsp+6E0h+var_6C0], r15d
0x1400068fd  lea     r9, [rsp+6E0h+var_688]
0x140006902  mov     [rsp+6E0h+var_6A0], eax
0x140006906  mov     r8d, r15d
0x140006909  mov     [rsp+6E0h+var_688], eax
0x14000690d  lea     rdx, aOsresumecount; "OsResumeCount"
0x140006914  mov     ecx, r14d
0x140006917  call    ?AssignValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXK@Z; TpmRegistry::AssignValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong)
0x14000691c  mov     ebx, eax
0x14000691e  test    eax, eax
0x140006920  js      loc_140006B41
0x140006926  mov     [rsp+6E0h+var_6B8], rdi
0x14000692b  lea     r9, [rsp+6E0h+var_69C+4]
0x140006930  mov     r8d, r15d
0x140006933  mov     dword ptr [rsp+6E0h+var_6C0], r15d
0x140006938  lea     rdx, aOsbootcount; "OsBootCount"
0x14000693f  xor     ecx, ecx
0x140006941  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x140006946  mov     ebx, eax
0x140006948  test    eax, eax
0x14000694a  js      loc_140006B41
0x140006950  mov     [rsp+6E0h+var_6B8], rdi
0x140006955  lea     r9, [rbp+5E0h+Src]
0x14000695c  mov     r8d, r14d
0x14000695f  mov     dword ptr [rsp+6E0h+var_6C0], 208h
0x140006967  lea     rdx, aWbclpath; "WBCLPath"
0x14000696e  xor     ecx, ecx
0x140006970  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x140006975  mov     ebx, eax
0x140006977  cmp     eax, 0C0000034h
0x14000697c  jnz     loc_140006A27
0x140006982  lea     rax, [rsp+6E0h+var_69C]
0x140006987  mov     r9d, r14d
0x14000698a  mov     [rsp+6E0h+var_6B0], rax
0x14000698f  lea     r8, aSystemrootLogs; "\\SystemRoot\\Logs\\MeasuredBoot"
0x140006996  mov     dword ptr [rsp+6E0h+var_6B8], edi
0x14000699a  lea     rcx, aTpmdriverlogpa; "TpmDriverLogPath"
0x1400069a1  xor     edx, edx
0x1400069a3  mov     [rsp+6E0h+var_6C0], rdi
0x1400069a8  call    cs:__imp_RtlGetPersistedStateLocation
0x1400069af  nop     dword ptr [rax+rax+00h]
0x1400069b4  mov     ebx, eax
0x1400069b6  cmp     eax, 80000005h
0x1400069bb  jnz     loc_140006B41
0x1400069c1  mov     r8, [rbp+5E8h]; unsigned __int64
0x1400069c8  mov     cl, r14b; bool
0x1400069cb  mov     edx, dword ptr [rsp+6E0h+var_69C]; unsigned __int64
0x1400069cf  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x1400069d4  mov     rdi, rax
0x1400069d7  test    rax, rax
0x1400069da  jnz     short loc_1400069E6
0x1400069dc  mov     ebx, 0C000009Ah
0x1400069e1  jmp     loc_140006B35
0x1400069e6  lea     rax, [rsp+6E0h+var_69C]
0x1400069eb  mov     r9d, r14d
0x1400069ee  mov     [rsp+6E0h+var_6B0], rax
0x1400069f3  lea     r8, aSystemrootLogs; "\\SystemRoot\\Logs\\MeasuredBoot"
0x1400069fa  mov     eax, dword ptr [rsp+6E0h+var_69C]
0x1400069fe  lea     rcx, aTpmdriverlogpa; "TpmDriverLogPath"
0x140006a05  mov     dword ptr [rsp+6E0h+var_6B8], eax
0x140006a09  xor     edx, edx
0x140006a0b  mov     [rsp+6E0h+var_6C0], rdi
0x140006a10  call    cs:__imp_RtlGetPersistedStateLocation
0x140006a17  nop     dword ptr [rax+rax+00h]
0x140006a1c  mov     ebx, eax
0x140006a1e  test    eax, eax
0x140006a20  jns     short loc_140006A49
0x140006a22  jmp     loc_140006B35
0x140006a27  test    eax, eax
0x140006a29  js      loc_140006B41
0x140006a2f  lea     rdx, [rbp+5E0h+Src]; Src
0x140006a36  lea     rcx, [rbp+5E0h+Dst]; Dst
0x140006a3d  call    TpmConvertFilePathToObjectPath
0x140006a42  lea     rdi, [rbp+5E0h+Dst]
0x140006a49  mov     eax, [rsp+6E0h+var_6A0]
0x140006a4d  lea     r8, aS010u010uLog; "%s\\%010u-%010u.log"
0x140006a54  mov     dword ptr [rsp+6E0h+var_6B8], eax
0x140006a58  lea     rcx, [rsp+6E0h+pszDest]; pszDest
0x140006a5d  mov     eax, dword ptr [rsp+6E0h+var_69C+4]
0x140006a61  mov     r15d, 104h
0x140006a67  mov     edx, r15d; cchDest
0x140006a6a  mov     dword ptr [rsp+6E0h+var_6C0], eax
0x140006a6e  mov     r9, rdi
0x140006a71  call    RtlStringCchPrintfW
0x140006a76  mov     ebx, eax
0x140006a78  test    eax, eax
0x140006a7a  js      loc_140006B35
0x140006a80  lea     r8, [rsp+6E0h+pcchLength]; pcchLength
0x140006a85  mov     edx, r15d; cchMax
0x140006a88  lea     rcx, [rsp+6E0h+pszDest]; psz
0x140006a8d  call    RtlStringCchLengthW
0x140006a92  mov     ebx, eax
0x140006a94  test    eax, eax
0x140006a96  js      loc_140006B35
0x140006a9c  mov     eax, dword ptr [rsp+6E0h+pcchLength]
0x140006aa0  lea     r9, [rsp+6E0h+pszDest]
0x140006aa5  mov     r8d, r14d
0x140006aa8  lea     rdx, aPlatformlogfil; "PlatformLogFile"
0x140006aaf  mov     ecx, r14d
0x140006ab2  lea     eax, ds:2[rax*2]
0x140006ab9  mov     dword ptr [rsp+6E0h+var_6C0], eax
0x140006abd  call    ?AssignValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXK@Z; TpmRegistry::AssignValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong)
0x140006ac2  mov     ebx, eax
0x140006ac4  test    eax, eax
0x140006ac6  js      short loc_140006B35
0x140006ac8  mov     eax, [rsp+6E0h+var_6A0]
0x140006acc  lea     r8, aS010u010uDrtmL; "%s\\%010u-%010u-DRTM.log"
0x140006ad3  mov     dword ptr [rsp+6E0h+var_6B8], eax
0x140006ad7  lea     rcx, [rsp+6E0h+pszDest]; pszDest
0x140006adc  mov     eax, dword ptr [rsp+6E0h+var_69C+4]
0x140006ae0  mov     r9, rdi
0x140006ae3  mov     edx, r15d; cchDest
0x140006ae6  mov     dword ptr [rsp+6E0h+var_6C0], eax
0x140006aea  call    RtlStringCchPrintfW
0x140006aef  mov     ebx, eax
0x140006af1  test    eax, eax
0x140006af3  js      short loc_140006B35
0x140006af5  lea     r8, [rsp+6E0h+pcchLength]; pcchLength
0x140006afa  mov     edx, r15d; cchMax
0x140006afd  lea     rcx, [rsp+6E0h+pszDest]; psz
0x140006b02  call    RtlStringCchLengthW
0x140006b07  mov     ebx, eax
0x140006b09  test    eax, eax
0x140006b0b  js      short loc_140006B35
0x140006b0d  mov     eax, dword ptr [rsp+6E0h+pcchLength]
0x140006b11  lea     r9, [rsp+6E0h+pszDest]
0x140006b16  mov     r8d, r14d
0x140006b19  lea     rdx, aPlatformlogfil_0; "PlatformLogFileDrtm"
0x140006b20  mov     ecx, r14d
0x140006b23  lea     eax, ds:2[rax*2]
0x140006b2a  mov     dword ptr [rsp+6E0h+var_6C0], eax
0x140006b2e  call    ?AssignValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXK@Z; TpmRegistry::AssignValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong)
0x140006b33  mov     ebx, eax
0x140006b35  lea     rax, [rbp+5E0h+Dst]
0x140006b3c  cmp     rdi, rax
0x140006b3f  jz      short loc_140006B49
0x140006b41  mov     rcx, rdi; void *
0x140006b44  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x140006b49  mov     eax, ebx
0x140006b4b  mov     rcx, [rbp+5E0h+var_30]
0x140006b52  xor     rcx, rsp; StackCookie
0x140006b55  call    __security_check_cookie
0x140006b5a  add     rsp, 6C0h
0x140006b61  pop     r15
0x140006b63  pop     r14
0x140006b65  pop     rdi
0x140006b66  pop     rbx
0x140006b67  pop     rbp
0x140006b68  retn
```

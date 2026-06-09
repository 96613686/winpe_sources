# NotificationParser::ParseSoundUri(ushort const *,WPN_APP_TYPE,ushort const *,ushort * *,ushort * *)

- ea: `0x18000e4c0`
- end: `0x18000e7e3`
- name: `?ParseSoundUri@NotificationParser@@AEAAXPEBGW4WPN_APP_TYPE@@0PEAPEAG2@Z`
- size: `803`
- prototype: `void __high(const unsigned __int16 *, enum WPN_APP_TYPE, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800089a0`

## callees

- `0x18000e4c0`
- `0x18000e7f0`
- `0x18000e93c`
- `0x18000eab0`
- `0x18001b848`
- `0x18001ff00`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e5d6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e648`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e6e4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e5d6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e648`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e6e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall NotificationParser::ParseSoundUri(
        __int64 a1,
        const WCHAR *a2,
        int a3,
        __int64 a4,
        unsigned __int16 **a5,
        _QWORD *a6)
{
  unsigned __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rsi
  unsigned int v11; // esi
  __int64 v12; // rax
  const unsigned __int16 *v13; // rbx
  const unsigned __int16 *v14; // rsi
  int v15; // eax
  __int64 v16; // r14
  unsigned __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-79h]
  unsigned __int16 *v23; // [rsp+40h] [rbp-59h] BYREF
  __int64 v24; // [rsp+48h] [rbp-51h] BYREF
  __int64 v25; // [rsp+50h] [rbp-49h]
  _DWORD v26[8]; // [rsp+58h] [rbp-41h] BYREF
  WCHAR String2[20]; // [rsp+78h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+4Fh]

  v25 = a4;
  LODWORD(v24) = a3;
  *a5 = 0;
  *a6 = 0;
  wcscpy(String2, L"ms-winsoundevent:");
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  v10 = v9;
  if ( (int)((2 * v9) >> 1) >= 17 )
  {
    if ( CompareStringOrdinal(a2, 17, String2, 17, 1) == 2 )
    {
      v13 = &a2[v10];
      v14 = a2 + 17;
      wcscpy((wchar_t *)v26, L"notification.");
      v12 = v13 - (a2 + 17);
      if ( (int)v12 >= 13 && (LODWORD(v12) = CompareStringOrdinal(a2 + 17, 13, (LPCWCH)v26, 13, 1), (_DWORD)v12 == 2) )
      {
        v14 = a2 + 30;
      }
      else if ( (_DWORD)v24 != 0x40000000 )
      {
        v14 = v13;
      }
      if ( (char *)v13 - (char *)v14 >= 0 && (((char *)v13 - (char *)v14) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      {
        v23 = 0;
        v15 = ResolveWinSound(v14, &v23);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7D4,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v15,
            bIgnoreCase);
        wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v24,
          a2,
          (int)(v14 - a2 - 1));
        *a6 = v24;
        LODWORD(v12) = (_DWORD)v23;
        *a5 = v23;
      }
      goto LABEL_7;
    }
    a3 = v24;
  }
  do
    ++v8;
  while ( a2[v8] );
  v11 = 0;
  v12 = (__int64)&off_180044000;
  while ( v11 < 3 )
  {
    v16 = 4LL * v11;
    if ( (a3 & *(_DWORD *)(&off_180044000 + v16 + 3)) != 0 )
    {
      v17 = (unsigned __int64)*(&off_180044000 + v16 + 1);
      if ( v8 >= v17 )
      {
        if ( CompareStringOrdinal(a2, v17, (&off_180044000)[v16], v17, 1) == 2 )
        {
          v23 = 0;
          bIgnoreCase = 0;
          v18 = ((__int64 (__fastcall *)(_QWORD, const WCHAR *, __int64, _QWORD))(&off_180044000)[v16 + 1])(
                  *(_QWORD *)(a1 + 32),
                  a2,
                  v25,
                  0);
          if ( v18 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x7F8,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notif"
                            "icationparser.cpp",
              (const char *)(unsigned int)v18,
              0);
          v20 = _AllocString<CTCoAllocPolicy>(retaddr, v19, (&off_180044000)[v16], a6);
          if ( v20 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x7F9,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notif"
                            "icationparser.cpp",
              (const char *)(unsigned int)v20,
              0);
          LODWORD(v12) = (_DWORD)v23;
          *a5 = v23;
          break;
        }
        a3 = v24;
        v12 = (__int64)&off_180044000;
      }
    }
    ++v11;
  }
LABEL_7:
  if ( !*a5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x802,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
  return v12;
}

```

## disassembly

```asm
0x18000e4c0  mov     [rsp-8+arg_10], rbx
0x18000e4c5  push    rbp
0x18000e4c6  push    rsi
0x18000e4c7  push    rdi
0x18000e4c8  push    r12
0x18000e4ca  push    r13
0x18000e4cc  push    r14
0x18000e4ce  push    r15
0x18000e4d0  lea     rbp, [rsp-17h]
0x18000e4d5  sub     rsp, 0B0h
0x18000e4dc  mov     rax, cs:__security_cookie
0x18000e4e3  xor     rax, rsp
0x18000e4e6  mov     [rbp+47h+var_40], rax
0x18000e4ea  mov     [rbp+47h+var_90], r9
0x18000e4ee  mov     dword ptr [rbp+47h+var_98], r8d
0x18000e4f2  mov     rdi, rdx
0x18000e4f5  mov     r13, rcx
0x18000e4f8  mov     r15, [rbp+47h+arg_20]
0x18000e4fc  mov     r12, [rbp+47h+arg_28]
0x18000e500  xor     r14d, r14d
0x18000e503  mov     [r15], r14
0x18000e506  mov     [r12], r14
0x18000e50a  mov     dword ptr [rbp+47h+String2], 73006Dh
0x18000e511  mov     [rbp+47h+var_64], 77002Dh
0x18000e518  mov     [rbp+47h+var_60], 6E0069h
0x18000e51f  mov     [rbp+47h+var_5C], 6F0073h
0x18000e526  mov     [rbp+47h+var_58], 6E0075h
0x18000e52d  mov     [rbp+47h+var_54], 650064h
0x18000e534  mov     [rbp+47h+var_50], 650076h
0x18000e53b  mov     [rbp+47h+var_4C], 74006Eh
0x18000e542  mov     [rbp+47h+var_48], 3Ah ; ':'
0x18000e549  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000e550  mov     rax, rbx
0x18000e553  lea     rax, [rax+1]
0x18000e557  cmp     [rdx+rax*2], r14w
0x18000e55c  jnz     short loc_18000E553
0x18000e55e  lea     rsi, [rax+rax]
0x18000e562  mov     rax, rsi
0x18000e565  sar     rax, 1
0x18000e568  cmp     eax, 11h
0x18000e56b  jge     short loc_18000E5BE
0x18000e56d  nop     dword ptr [rax]
0x18000e570  inc     rbx
0x18000e573  cmp     [rdi+rbx*2], r14w
0x18000e578  jnz     short loc_18000E570
0x18000e57a  mov     esi, r14d
0x18000e57d  lea     rax, off_180044000; "ms-appx:///"
0x18000e584  cmp     esi, 3
0x18000e587  jb      loc_18000E6B2
0x18000e58d  cmp     qword ptr [r15], 0
0x18000e591  jz      loc_18000E7C7
0x18000e597  mov     rcx, [rbp+47h+var_40]
0x18000e59b  xor     rcx, rsp; StackCookie
0x18000e59e  call    __security_check_cookie
0x18000e5a3  mov     rbx, [rsp+0E0h+arg_10]
0x18000e5ab  add     rsp, 0B0h
0x18000e5b2  pop     r15
0x18000e5b4  pop     r14
0x18000e5b6  pop     r13
0x18000e5b8  pop     r12
0x18000e5ba  pop     rdi
0x18000e5bb  pop     rsi
0x18000e5bc  pop     rbp
0x18000e5bd  retn
0x18000e5be  mov     [rsp+0E0h+bIgnoreCase], 1; bIgnoreCase
0x18000e5c6  mov     r9d, 11h; cchCount2
0x18000e5cc  lea     r8, [rbp+47h+String2]; lpString2
0x18000e5d0  mov     edx, r9d; cchCount1
0x18000e5d3  mov     rcx, rdi; lpString1
0x18000e5d6  call    cs:__imp_CompareStringOrdinal
0x18000e5dc  cmp     eax, 2
0x18000e5df  jnz     loc_18000E782
0x18000e5e5  lea     rbx, [rsi+rdi]
0x18000e5e9  lea     rsi, [rdi+22h]
0x18000e5ed  mov     dword ptr [rbp+47h+var_88], 6F006Eh
0x18000e5f4  mov     dword ptr [rbp+47h+var_88+4], 690074h
0x18000e5fb  mov     dword ptr [rbp+47h+var_88+8], 690066h
0x18000e602  mov     dword ptr [rbp+47h+var_88+0Ch], 610063h
0x18000e609  mov     [rbp+47h+var_78], 690074h
0x18000e610  mov     [rbp+47h+var_74], 6E006Fh
0x18000e617  mov     [rbp+47h+var_70], 2Eh ; '.'
0x18000e61e  mov     rax, rbx
0x18000e621  sub     rax, rsi
0x18000e624  sar     rax, 1
0x18000e627  cmp     eax, 0Dh
0x18000e62a  jl      loc_18000E75D
0x18000e630  mov     [rsp+0E0h+bIgnoreCase], 1; int
0x18000e638  mov     r9d, 0Dh; cchCount2
0x18000e63e  lea     r8, [rbp+47h+var_88]; lpString2
0x18000e642  mov     edx, r9d; cchCount1
0x18000e645  mov     rcx, rsi; lpString1
0x18000e648  call    cs:__imp_CompareStringOrdinal
0x18000e64e  cmp     eax, 2
0x18000e651  jnz     loc_18000E75D
0x18000e657  add     rsi, 1Ah
0x18000e65b  sub     rbx, rsi
0x18000e65e  test    rbx, 0FFFFFFFFFFFFFFFEh
0x18000e665  jle     loc_18000E58D
0x18000e66b  mov     [rbp+47h+var_A0], r14
0x18000e66f  lea     rdx, [rbp+47h+var_A0]; unsigned __int16 **
0x18000e673  mov     rcx, rsi; unsigned __int16 *
0x18000e676  call    ?ResolveWinSound@@YAJPEBGPEAPEAG@Z; ResolveWinSound(ushort const *,ushort * *)
0x18000e67b  mov     rcx, [rbp+4Fh]; this
0x18000e67f  test    eax, eax
0x18000e681  js      loc_18000E76D
0x18000e687  sub     rsi, rdi
0x18000e68a  sar     rsi, 1
0x18000e68d  dec     esi
0x18000e68f  movsxd  r8, esi
0x18000e692  mov     rdx, rdi
0x18000e695  lea     rcx, [rbp+47h+var_98]
0x18000e699  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000e69e  mov     rax, [rbp+47h+var_98]
0x18000e6a2  mov     [r12], rax
0x18000e6a6  mov     rax, [rbp+47h+var_A0]
0x18000e6aa  mov     [r15], rax
0x18000e6ad  jmp     loc_18000E58D
0x18000e6b2  mov     r14d, esi
0x18000e6b5  shl     r14, 5
0x18000e6b9  test    [r14+rax+18h], r8d
0x18000e6be  jz      loc_18000E796
0x18000e6c4  mov     rdx, [r14+rax+8]; cchCount1
0x18000e6c9  cmp     rbx, rdx
0x18000e6cc  jb      loc_18000E796
0x18000e6d2  mov     [rsp+0E0h+bIgnoreCase], 1; bIgnoreCase
0x18000e6da  mov     r9d, edx; cchCount2
0x18000e6dd  mov     r8, [r14+rax]; lpString2
0x18000e6e1  mov     rcx, rdi; lpString1
0x18000e6e4  call    cs:__imp_CompareStringOrdinal
0x18000e6ea  cmp     eax, 2
0x18000e6ed  jnz     loc_18000E78B
0x18000e6f3  mov     [rbp+47h+var_A0], 0
0x18000e6fb  lea     rax, [rbp+47h+var_A0]
0x18000e6ff  mov     [rsp+0E0h+var_B0], rax
0x18000e704  mov     [rsp+0E0h+var_B8], 0
0x18000e70d  mov     qword ptr [rsp+0E0h+bIgnoreCase], 0; int
0x18000e716  xor     r9d, r9d
0x18000e719  mov     r8, [rbp+47h+var_90]
0x18000e71d  mov     rdx, rdi
0x18000e720  mov     rcx, [r13+20h]
0x18000e724  lea     rbx, off_180044000; "ms-appx:///"
0x18000e72b  mov     rax, [r14+rbx+10h]
0x18000e730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e735  mov     rcx, [rbp+4Fh]; this
0x18000e739  test    eax, eax
0x18000e73b  js      short loc_18000E79D
0x18000e73d  mov     r9, r12
0x18000e740  mov     r8, [r14+rbx]
0x18000e744  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000e749  mov     rcx, [rbp+4Fh]; this
0x18000e74d  test    eax, eax
0x18000e74f  js      short loc_18000E7B2
0x18000e751  mov     rax, [rbp+47h+var_A0]
0x18000e755  mov     [r15], rax
0x18000e758  jmp     loc_18000E58D
0x18000e75d  cmp     dword ptr [rbp+47h+var_98], 40000000h
0x18000e764  cmovnz  rsi, rbx
0x18000e768  jmp     loc_18000E65B
0x18000e76d  mov     r9d, eax; char *
0x18000e770  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000e777  mov     edx, 7D4h; void *
0x18000e77c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e782  mov     r8d, dword ptr [rbp+47h+var_98]
0x18000e786  jmp     loc_18000E570
0x18000e78b  mov     r8d, dword ptr [rbp+47h+var_98]
0x18000e78f  lea     rax, off_180044000; "ms-appx:///"
0x18000e796  inc     esi
0x18000e798  jmp     loc_18000E584
0x18000e79d  mov     r9d, eax; char *
0x18000e7a0  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000e7a7  mov     edx, 7F8h; void *
0x18000e7ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e7b2  mov     r9d, eax; char *
0x18000e7b5  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000e7bc  mov     edx, 7F9h; void *
0x18000e7c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e7c7  mov     rcx, [rbp+4Fh]; this
0x18000e7cb  mov     r9d, 80070057h; char *
0x18000e7d1  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000e7d8  mov     edx, 802h; void *
0x18000e7dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

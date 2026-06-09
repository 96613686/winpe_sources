# SetUserEnvironmentVariable(void * *,ushort const *,ushort const *,int)

- ea: `0x140008370`
- end: `0x140008540`
- name: `?SetUserEnvironmentVariable@@YAHPEAPEAXPEBG1H@Z`
- size: `464`
- prototype: `_BOOL8 __fastcall(PWSTR *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007970`
- `0x140007e30`
- `0x140008700`
- `0x14003ec9c`

## callees

- `0x140008370`
- `0x14001a520`
- `0x140053720`
- `0x14009cbd0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000843b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008471`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000843b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140008471`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x140008525`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x140008525`
- `ntdll!RtlSetEnvironmentVariable` at `0x1400084e2`
- `ntdll!RtlSetEnvironmentVariable` at `0x1400084e2`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x1400083fb`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x1400083fb`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400083ce`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400084cb`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400083ce`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400084cb`

## pseudocode

```c
_BOOL8 __fastcall SetUserEnvironmentVariable(PWSTR *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  bool v3; // zf
  WCHAR *v7; // rcx
  __int64 v8; // rax
  WCHAR *v9; // rdx
  __int64 v10; // rdi
  WCHAR *v11; // rcx
  struct _UNICODE_STRING *p_Value; // r8
  struct _UNICODE_STRING Value; // [rsp+30h] [rbp-2048h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-2038h] BYREF
  WCHAR SourceString[4096]; // [rsp+50h] [rbp-2028h] BYREF

  v3 = *a1 == 0;
  DestinationString = 0;
  Value = 0;
  if ( v3 || !a2 || !*a2 || RtlInitUnicodeStringEx(&DestinationString, a2) < 0 )
    return 0;
  v7 = *a1;
  Value.Buffer = SourceString;
  *(_DWORD *)&Value.Length = 0x20000000;
  RtlQueryEnvironmentVariable_U(v7, &DestinationString, &Value);
  if ( a3 && *a3 )
  {
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"TEMP", -1) == 2 || CompareStringW(0x7Fu, 1u, a2, -1, L"TMP", -1) == 2 )
    {
      if ( !GetShortPathNameW(a3, SourceString, 0x1000u) )
        StringCchCopyW(SourceString, 0x1000u, a3);
    }
    else
    {
      v8 = 2147483646;
      v9 = SourceString;
      v10 = 4096;
      do
      {
        if ( !v8 )
          break;
        if ( !*a3 )
          break;
        *v9++ = *a3++;
        --v8;
        --v10;
      }
      while ( v10 );
      v11 = v9 - 1;
      if ( v10 )
        v11 = v9;
      *v11 = 0;
    }
    if ( RtlInitUnicodeStringEx(&Value, SourceString) < 0 )
      return 0;
    p_Value = &Value;
  }
  else
  {
    p_Value = 0;
  }
  return RtlSetEnvironmentVariable(a1, &DestinationString, p_Value) >= 0;
}

```

## disassembly

```asm
0x140008370  push    rbx
0x140008372  push    rsi
0x140008373  push    rdi
0x140008374  mov     eax, 2060h
0x140008379  call    _alloca_probe
0x14000837e  sub     rsp, rax
0x140008381  mov     rax, cs:__security_cookie
0x140008388  xor     rax, rsp
0x14000838b  mov     [rsp+2078h+var_28], rax
0x140008393  cmp     qword ptr [rcx], 0
0x140008397  xorps   xmm0, xmm0
0x14000839a  xorps   xmm1, xmm1
0x14000839d  mov     rbx, r8
0x1400083a0  movups  xmmword ptr [rsp+2078h+DestinationString.Length], xmm0
0x1400083a5  mov     rdi, rdx
0x1400083a8  mov     rsi, rcx
0x1400083ab  movups  xmmword ptr [rsp+2078h+Value.Length], xmm1
0x1400083b0  jz      loc_1400084EC
0x1400083b6  test    rdx, rdx
0x1400083b9  jz      loc_1400084EC
0x1400083bf  cmp     word ptr [rdx], 0
0x1400083c3  jz      loc_1400084EC
0x1400083c9  lea     rcx, [rsp+2078h+DestinationString]; DestinationString
0x1400083ce  call    cs:__imp_RtlInitUnicodeStringEx
0x1400083d4  test    eax, eax
0x1400083d6  js      loc_1400084EC
0x1400083dc  mov     rcx, [rsi]; Environment
0x1400083df  lea     rax, [rsp+2078h+SourceString]
0x1400083e4  lea     r8, [rsp+2078h+Value]; Value
0x1400083e9  mov     [rsp+2078h+Value.Buffer], rax
0x1400083ee  lea     rdx, [rsp+2078h+DestinationString]; Name
0x1400083f3  mov     dword ptr [rsp+2078h+Value.Length], 20000000h
0x1400083fb  call    cs:__imp_RtlQueryEnvironmentVariable_U
0x140008401  test    rbx, rbx
0x140008404  jz      loc_140008510
0x14000840a  cmp     word ptr [rbx], 0
0x14000840e  jz      loc_140008510
0x140008414  lea     rax, aTemp; "TEMP"
0x14000841b  mov     [rsp+2078h+cchCount2], 0FFFFFFFFh; cchCount2
0x140008423  mov     r9d, 0FFFFFFFFh; cchCount1
0x140008429  mov     [rsp+2078h+lpString2], rax; lpString2
0x14000842e  mov     r8, rdi; lpString1
0x140008431  mov     edx, 1; dwCmpFlags
0x140008436  mov     ecx, 7Fh; Locale
0x14000843b  call    cs:__imp_CompareStringW
0x140008441  cmp     eax, 2
0x140008444  jz      loc_140008515
0x14000844a  lea     rax, aTmp; "TMP"
0x140008451  mov     [rsp+2078h+cchCount2], 0FFFFFFFFh; cchCount2
0x140008459  mov     r9d, 0FFFFFFFFh; cchCount1
0x14000845f  mov     [rsp+2078h+lpString2], rax; lpString2
0x140008464  mov     r8, rdi; lpString1
0x140008467  mov     edx, 1; dwCmpFlags
0x14000846c  mov     ecx, 7Fh; Locale
0x140008471  call    cs:__imp_CompareStringW
0x140008477  cmp     eax, 2
0x14000847a  jz      loc_140008515
0x140008480  mov     eax, 7FFFFFFEh
0x140008485  lea     rdx, [rsp+2078h+SourceString]
0x14000848a  mov     edi, 1000h
0x14000848f  nop
0x140008490  test    rax, rax
0x140008493  jz      short loc_1400084B1
0x140008495  movzx   ecx, word ptr [rbx]
0x140008498  test    cx, cx
0x14000849b  jz      short loc_1400084B1
0x14000849d  mov     [rdx], cx
0x1400084a0  add     rbx, 2
0x1400084a4  add     rdx, 2
0x1400084a8  dec     rax
0x1400084ab  sub     rdi, 1
0x1400084af  jnz     short loc_140008490
0x1400084b1  test    rdi, rdi
0x1400084b4  lea     rcx, [rdx-2]
0x1400084b8  cmovnz  rcx, rdx
0x1400084bc  xor     eax, eax
0x1400084be  mov     [rcx], ax
0x1400084c1  lea     rdx, [rsp+2078h+SourceString]; SourceString
0x1400084c6  lea     rcx, [rsp+2078h+Value]; DestinationString
0x1400084cb  call    cs:__imp_RtlInitUnicodeStringEx
0x1400084d1  test    eax, eax
0x1400084d3  js      short loc_1400084EC
0x1400084d5  lea     r8, [rsp+2078h+Value]; Value
0x1400084da  lea     rdx, [rsp+2078h+DestinationString]; Name
0x1400084df  mov     rcx, rsi; Environment
0x1400084e2  call    cs:__imp_RtlSetEnvironmentVariable
0x1400084e8  test    eax, eax
0x1400084ea  jns     short loc_140008509
0x1400084ec  xor     eax, eax
0x1400084ee  mov     rcx, [rsp+2078h+var_28]
0x1400084f6  xor     rcx, rsp; StackCookie
0x1400084f9  call    __security_check_cookie
0x1400084fe  add     rsp, 2060h
0x140008505  pop     rdi
0x140008506  pop     rsi
0x140008507  pop     rbx
0x140008508  retn
0x140008509  mov     eax, 1
0x14000850e  jmp     short loc_1400084EE
0x140008510  xor     r8d, r8d
0x140008513  jmp     short loc_1400084DA
0x140008515  mov     edi, 1000h
0x14000851a  lea     rdx, [rsp+2078h+SourceString]; lpszShortPath
0x14000851f  mov     r8d, edi; cchBuffer
0x140008522  mov     rcx, rbx; lpszLongPath
0x140008525  call    cs:__imp_GetShortPathNameW
0x14000852b  test    eax, eax
0x14000852d  jnz     short loc_1400084C1
0x14000852f  mov     r8, rbx; unsigned __int16 *
0x140008532  lea     rcx, [rsp+2078h+SourceString]; unsigned __int16 *
0x140008537  mov     edx, edi; unsigned __int64
0x140008539  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000853e  jmp     short loc_1400084C1
```

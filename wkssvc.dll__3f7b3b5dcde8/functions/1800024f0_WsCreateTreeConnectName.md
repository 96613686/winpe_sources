# WsCreateTreeConnectName

- ea: `0x1800024f0`
- end: `0x1800026f9`
- name: `WsCreateTreeConnectName`
- size: `521`
- prototype: `__int64 __fastcall(__int64, unsigned int, const WCHAR *, char, PUNICODE_STRING Destination)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001710`
- `0x180003b70`
- `0x180009b80`
- `0x1800299a4`

## callees

- `0x180001594`
- `0x1800024f0`
- `0x180002a60`
- `0x18001e420`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800026cb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800026e9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800026cb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800026e9`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000261f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180002655`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000261f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180002655`
- `ntdll!RtlAppendUnicodeToString` at `0x18000262f`
- `ntdll!RtlAppendUnicodeToString` at `0x180002647`
- `ntdll!RtlAppendUnicodeToString` at `0x180002662`
- `ntdll!RtlAppendUnicodeToString` at `0x18000262f`
- `ntdll!RtlAppendUnicodeToString` at `0x180002647`
- `ntdll!RtlAppendUnicodeToString` at `0x180002662`
- `ntdll!RtlInitUnicodeString` at `0x18000258b`
- `ntdll!RtlInitUnicodeString` at `0x18000258b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002602`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002602`

## pseudocode

```c
__int64 __fastcall WsCreateTreeConnectName(
        __int64 a1,
        unsigned int a2,
        const WCHAR *a3,
        char a4,
        PUNICODE_STRING Destination)
{
  __int64 result; // rax
  unsigned int v9; // edi
  int Length; // ecx
  int v11; // edi
  unsigned int v12; // ecx
  WCHAR *v13; // rax
  const WCHAR *v14; // rdx
  __int64 v15; // rdi
  struct _LUID DestinationLuid; // [rsp+30h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-A0h] BYREF
  wchar_t pszDest[40]; // [rsp+50h] [rbp-88h] BYREF

  *(_QWORD *)&DestinationString.Length = 786444;
  DestinationLuid = 0;
  DestinationString.Buffer = L"GLOBAL";
  if ( !a4 )
  {
    result = WsImpersonateAndGetLogonId(&DestinationLuid);
    if ( (_DWORD)result )
      return result;
    StringCchPrintfW(pszDest, 0x21u, L"%08x%08x", (unsigned int)DestinationLuid.HighPart, DestinationLuid.LowPart);
    pszDest[32] = 0;
    RtlInitUnicodeString(&DestinationString, pszDest);
  }
  v9 = 0;
  if ( a3 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a3[v15] );
    v9 = 2 * v15;
    if ( (unsigned int)_o__wcsnicmp(a3, L"LPT", 3) )
      _o__wcsnicmp(a3, L"COM", 3);
  }
  if ( a2 >= 0xFFFF || v9 >= 0xFFFF )
  {
    *(_DWORD *)&Destination->Length = 0;
    goto LABEL_16;
  }
  Length = DestinationString.Length;
  if ( !a3 )
    v9 = 2;
  v11 = RedirectorDeviceName.Length + (unsigned __int16)(2 * a2) + v9;
  Destination->Length = 0;
  v12 = v11 + Length + 4;
  if ( v12 >= 0xFFFF )
  {
    Destination->MaximumLength = 0;
LABEL_16:
    result = 2140;
    Destination->Buffer = 0;
    return result;
  }
  Destination->MaximumLength = v12;
  v13 = (WCHAR *)LocalAlloc(0x40u, v12 + 2LL);
  Destination->Buffer = v13;
  if ( !v13 )
    return 8;
  RtlAppendUnicodeStringToString(Destination, &RedirectorDeviceName);
  RtlAppendUnicodeToString(Destination, L"\\;");
  v14 = a3;
  if ( !a3 )
    v14 = L":";
  RtlAppendUnicodeToString(Destination, v14);
  RtlAppendUnicodeStringToString(Destination, &DestinationString);
  RtlAppendUnicodeToString(Destination, (PCWSTR)(a1 + 2));
  return 0;
}

```

## disassembly

```asm
0x1800024f0  push    rbx
0x1800024f2  push    rbp
0x1800024f3  push    rsi
0x1800024f4  push    r14
0x1800024f6  push    r15
0x1800024f8  sub     rsp, 0B0h
0x1800024ff  mov     rax, cs:__security_cookie
0x180002506  xor     rax, rsp
0x180002509  mov     [rsp+0D8h+var_38], rax
0x180002511  mov     rbx, [rsp+0D8h+Destination]
0x180002519  lea     rax, aGlobal; "GLOBAL"
0x180002520  xor     r15d, r15d
0x180002523  mov     qword ptr [rsp+0D8h+DestinationString.Length], 0C000Ch
0x18000252c  mov     qword ptr [rsp+0D8h+DestinationLuid.LowPart], r15
0x180002531  mov     rsi, r8
0x180002534  mov     [rsp+0D8h+DestinationString.Buffer], rax
0x180002539  mov     ebp, edx
0x18000253b  mov     r14, rcx
0x18000253e  test    r9b, r9b
0x180002541  jnz     short loc_180002591
0x180002543  lea     rcx, [rsp+0D8h+DestinationLuid]; DestinationLuid
0x180002548  call    WsImpersonateAndGetLogonId
0x18000254d  test    eax, eax
0x18000254f  jnz     loc_180002672
0x180002555  mov     eax, [rsp+0D8h+DestinationLuid.LowPart]
0x180002559  lea     r8, a08x08x; "%08x%08x"
0x180002560  mov     r9d, [rsp+0D8h+DestinationLuid.HighPart]
0x180002565  lea     rcx, [rsp+0D8h+pszDest]; pszDest
0x18000256a  mov     edx, 21h ; '!'; cchDest
0x18000256f  mov     [rsp+0D8h+var_B8], eax
0x180002573  call    StringCchPrintfW
0x180002578  lea     rdx, [rsp+0D8h+pszDest]; SourceString
0x18000257d  mov     [rsp+0D8h+var_48], r15w
0x180002586  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x18000258b  call    cs:__imp_RtlInitUnicodeString
0x180002591  mov     [rsp+0D8h+arg_18], rdi
0x180002599  mov     edi, r15d
0x18000259c  test    rsi, rsi
0x18000259f  jnz     loc_1800026A8
0x1800025a5  cmp     ebp, 0FFFFh
0x1800025ab  jnb     loc_1800026F4
0x1800025b1  cmp     edi, 0FFFFh
0x1800025b7  jnb     loc_1800026F4
0x1800025bd  movzx   ecx, [rsp+0D8h+DestinationString.Length]
0x1800025c2  test    rsi, rsi
0x1800025c5  mov     eax, 2
0x1800025ca  cmovz   edi, eax
0x1800025cd  add     bp, bp
0x1800025d0  movzx   eax, bp
0x1800025d3  add     ecx, 4
0x1800025d6  add     edi, eax
0x1800025d8  movzx   eax, cs:RedirectorDeviceName.Length
0x1800025df  add     edi, eax
0x1800025e1  mov     [rbx], r15w
0x1800025e5  add     ecx, edi
0x1800025e7  cmp     ecx, 0FFFFh
0x1800025ed  jnb     loc_180002691
0x1800025f3  mov     edx, ecx
0x1800025f5  mov     [rbx+2], cx
0x1800025f9  add     rdx, 2; uBytes
0x1800025fd  mov     ecx, 40h ; '@'; uFlags
0x180002602  call    cs:__imp_LocalAlloc
0x180002608  mov     [rbx+8], rax
0x18000260c  test    rax, rax
0x18000260f  jz      loc_1800026A1
0x180002615  lea     rdx, RedirectorDeviceName; Source
0x18000261c  mov     rcx, rbx; Destination
0x18000261f  call    cs:__imp_RtlAppendUnicodeStringToString
0x180002625  lea     rdx, Source; "\\;"
0x18000262c  mov     rcx, rbx; Destination
0x18000262f  call    cs:__imp_RtlAppendUnicodeToString
0x180002635  mov     rcx, rbx; Destination
0x180002638  mov     rdx, rsi
0x18000263b  test    rsi, rsi
0x18000263e  jnz     short loc_180002647
0x180002640  lea     rdx, SubStr; ":"
0x180002647  call    cs:__imp_RtlAppendUnicodeToString
0x18000264d  lea     rdx, [rsp+0D8h+DestinationString]; Source
0x180002652  mov     rcx, rbx; Destination
0x180002655  call    cs:__imp_RtlAppendUnicodeStringToString
0x18000265b  lea     rdx, [r14+2]; Source
0x18000265f  mov     rcx, rbx; Destination
0x180002662  call    cs:__imp_RtlAppendUnicodeToString
0x180002668  xor     eax, eax
0x18000266a  mov     rdi, [rsp+0D8h+arg_18]
0x180002672  mov     rcx, [rsp+0D8h+var_38]
0x18000267a  xor     rcx, rsp; StackCookie
0x18000267d  call    __security_check_cookie
0x180002682  add     rsp, 0B0h
0x180002689  pop     r15
0x18000268b  pop     r14
0x18000268d  pop     rsi
0x18000268e  pop     rbp
0x18000268f  pop     rbx
0x180002690  retn
0x180002691  mov     [rbx+2], r15w
0x180002696  mov     eax, 85Ch
0x18000269b  mov     [rbx+8], r15
0x18000269f  jmp     short loc_18000266A
0x1800026a1  mov     eax, 8
0x1800026a6  jmp     short loc_18000266A
0x1800026a8  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800026af  inc     rdi
0x1800026b2  cmp     [rsi+rdi*2], r15w
0x1800026b7  jnz     short loc_1800026AF
0x1800026b9  mov     r8d, 3
0x1800026bf  lea     rdx, aLpt; "LPT"
0x1800026c6  mov     rcx, rsi
0x1800026c9  add     edi, edi
0x1800026cb  call    cs:__imp__o__wcsnicmp
0x1800026d1  test    eax, eax
0x1800026d3  jz      loc_1800025A5
0x1800026d9  mov     r8d, 3
0x1800026df  lea     rdx, aCom; "COM"
0x1800026e6  mov     rcx, rsi
0x1800026e9  call    cs:__imp__o__wcsnicmp
0x1800026ef  jmp     loc_1800025A5
0x1800026f4  mov     [rbx], r15d
0x1800026f7  jmp     short loc_180002696
```

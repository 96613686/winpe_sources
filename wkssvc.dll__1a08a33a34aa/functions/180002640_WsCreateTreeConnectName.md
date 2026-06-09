# WsCreateTreeConnectName

- ea: `0x180002640`
- end: `0x180002880`
- name: `WsCreateTreeConnectName`
- size: `576`
- prototype: `__int64 __fastcall(int, int, int, int, PUNICODE_STRING Destination)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001750`
- `0x180003db0`
- `0x18000a3a0`
- `0x18002be90`

## callees

- `0x1800015c0`
- `0x180002640`
- `0x180002c20`
- `0x18001fbd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180002846`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000286a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180002846`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000286a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000277b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800027c3`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000277b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800027c3`
- `ntdll!RtlAppendUnicodeToString` at `0x180002791`
- `ntdll!RtlAppendUnicodeToString` at `0x1800027af`
- `ntdll!RtlAppendUnicodeToString` at `0x1800027d6`
- `ntdll!RtlAppendUnicodeToString` at `0x180002791`
- `ntdll!RtlAppendUnicodeToString` at `0x1800027af`
- `ntdll!RtlAppendUnicodeToString` at `0x1800027d6`
- `ntdll!RtlInitUnicodeString` at `0x1800026db`
- `ntdll!RtlInitUnicodeString` at `0x1800026db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002758`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002758`

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
0x180002640  push    rbx
0x180002642  push    rbp
0x180002643  push    rsi
0x180002644  push    r14
0x180002646  push    r15
0x180002648  sub     rsp, 0B0h
0x18000264f  mov     rax, cs:__security_cookie
0x180002656  xor     rax, rsp
0x180002659  mov     [rsp+0D8h+var_38], rax
0x180002661  mov     rbx, [rsp+0D8h+Destination]
0x180002669  lea     rax, aGlobal; "GLOBAL"
0x180002670  xor     r15d, r15d
0x180002673  mov     qword ptr [rsp+0D8h+DestinationString.Length], 0C000Ch
0x18000267c  mov     qword ptr [rsp+0D8h+DestinationLuid.LowPart], r15
0x180002681  mov     rsi, r8
0x180002684  mov     [rsp+0D8h+DestinationString.Buffer], rax
0x180002689  mov     ebp, edx
0x18000268b  mov     r14, rcx
0x18000268e  test    r9b, r9b
0x180002691  jnz     short loc_1800026E7
0x180002693  lea     rcx, [rsp+0D8h+DestinationLuid]; DestinationLuid
0x180002698  call    WsImpersonateAndGetLogonId
0x18000269d  test    eax, eax
0x18000269f  jnz     loc_1800027EC
0x1800026a5  mov     eax, [rsp+0D8h+DestinationLuid.LowPart]
0x1800026a9  lea     r8, a08x08x; "%08x%08x"
0x1800026b0  mov     r9d, [rsp+0D8h+DestinationLuid.HighPart]
0x1800026b5  lea     rcx, [rsp+0D8h+pszDest]; pszDest
0x1800026ba  mov     edx, 21h ; '!'; cchDest
0x1800026bf  mov     [rsp+0D8h+var_B8], eax
0x1800026c3  call    StringCchPrintfW
0x1800026c8  lea     rdx, [rsp+0D8h+pszDest]; SourceString
0x1800026cd  mov     [rsp+0D8h+var_48], r15w
0x1800026d6  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x1800026db  call    cs:__imp_RtlInitUnicodeString
0x1800026e2  nop     dword ptr [rax+rax+00h]
0x1800026e7  mov     [rsp+0D8h+arg_18], rdi
0x1800026ef  mov     edi, r15d
0x1800026f2  test    rsi, rsi
0x1800026f5  jnz     loc_180002823
0x1800026fb  cmp     ebp, 0FFFFh
0x180002701  jnb     loc_18000287B
0x180002707  cmp     edi, 0FFFFh
0x18000270d  jnb     loc_18000287B
0x180002713  movzx   ecx, [rsp+0D8h+DestinationString.Length]
0x180002718  test    rsi, rsi
0x18000271b  mov     eax, 2
0x180002720  cmovz   edi, eax
0x180002723  add     bp, bp
0x180002726  movzx   eax, bp
0x180002729  add     ecx, 4
0x18000272c  add     edi, eax
0x18000272e  movzx   eax, cs:RedirectorDeviceName.Length
0x180002735  add     edi, eax
0x180002737  mov     [rbx], r15w
0x18000273b  add     ecx, edi
0x18000273d  cmp     ecx, 0FFFFh
0x180002743  jnb     loc_18000280C
0x180002749  mov     edx, ecx
0x18000274b  mov     [rbx+2], cx
0x18000274f  add     rdx, 2; uBytes
0x180002753  mov     ecx, 40h ; '@'; uFlags
0x180002758  call    cs:__imp_LocalAlloc
0x18000275f  nop     dword ptr [rax+rax+00h]
0x180002764  mov     [rbx+8], rax
0x180002768  test    rax, rax
0x18000276b  jz      loc_18000281C
0x180002771  lea     rdx, RedirectorDeviceName; Source
0x180002778  mov     rcx, rbx; Destination
0x18000277b  call    cs:__imp_RtlAppendUnicodeStringToString
0x180002782  nop     dword ptr [rax+rax+00h]
0x180002787  lea     rdx, Source; "\\;"
0x18000278e  mov     rcx, rbx; Destination
0x180002791  call    cs:__imp_RtlAppendUnicodeToString
0x180002798  nop     dword ptr [rax+rax+00h]
0x18000279d  mov     rcx, rbx; Destination
0x1800027a0  mov     rdx, rsi
0x1800027a3  test    rsi, rsi
0x1800027a6  jnz     short loc_1800027AF
0x1800027a8  lea     rdx, SubStr; ":"
0x1800027af  call    cs:__imp_RtlAppendUnicodeToString
0x1800027b6  nop     dword ptr [rax+rax+00h]
0x1800027bb  lea     rdx, [rsp+0D8h+DestinationString]; Source
0x1800027c0  mov     rcx, rbx; Destination
0x1800027c3  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800027ca  nop     dword ptr [rax+rax+00h]
0x1800027cf  lea     rdx, [r14+2]; Source
0x1800027d3  mov     rcx, rbx; Destination
0x1800027d6  call    cs:__imp_RtlAppendUnicodeToString
0x1800027dd  nop     dword ptr [rax+rax+00h]
0x1800027e2  xor     eax, eax
0x1800027e4  mov     rdi, [rsp+0D8h+arg_18]
0x1800027ec  mov     rcx, [rsp+0D8h+var_38]
0x1800027f4  xor     rcx, rsp; StackCookie
0x1800027f7  call    __security_check_cookie
0x1800027fc  add     rsp, 0B0h
0x180002803  pop     r15
0x180002805  pop     r14
0x180002807  pop     rsi
0x180002808  pop     rbp
0x180002809  pop     rbx
0x18000280a  retn
0x18000280c  mov     [rbx+2], r15w
0x180002811  mov     eax, 85Ch
0x180002816  mov     [rbx+8], r15
0x18000281a  jmp     short loc_1800027E4
0x18000281c  mov     eax, 8
0x180002821  jmp     short loc_1800027E4
0x180002823  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000282a  inc     rdi
0x18000282d  cmp     [rsi+rdi*2], r15w
0x180002832  jnz     short loc_18000282A
0x180002834  mov     r8d, 3
0x18000283a  lea     rdx, aLpt; "LPT"
0x180002841  mov     rcx, rsi
0x180002844  add     edi, edi
0x180002846  call    cs:__imp__o__wcsnicmp
0x18000284d  nop     dword ptr [rax+rax+00h]
0x180002852  test    eax, eax
0x180002854  jz      loc_1800026FB
0x18000285a  mov     r8d, 3
0x180002860  lea     rdx, aCom; "COM"
0x180002867  mov     rcx, rsi
0x18000286a  call    cs:__imp__o__wcsnicmp
0x180002871  nop     dword ptr [rax+rax+00h]
0x180002876  jmp     loc_1800026FB
0x18000287b  mov     [rbx], r15d
0x18000287e  jmp     short loc_180002811
```

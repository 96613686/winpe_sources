# LogEventCommon(ulong,ushort const * * const,ushort,ushort const * const,ushort,ushort)

- ea: `0x180023ff4`
- end: `0x1800240d0`
- name: `?LogEventCommon@@YAXKQEAPEBGGQEBGGG@Z`
- size: `220`
- prototype: `void __usercall(DWORD dwEventID@<ecx>, LPCWSTR *lpStrings@<rdx>, unsigned __int16@<r8w>, const unsigned __int16 *const@<r9>, unsigned __int16, unsigned __int16)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020b64`
- `0x180022770`

## callees

- `0x180023ff4`
- `0x180024640`

## import_xrefs

- `ntdll!RtlIntegerToUnicodeString` at `0x18002405b`
- `ntdll!RtlIntegerToUnicodeString` at `0x18002405b`
- `KERNEL32!GetCurrentProcessId` at `0x18002404c`
- `KERNEL32!GetCurrentProcessId` at `0x18002404c`
- `ADVAPI32!DeregisterEventSource` at `0x1800240aa`
- `ADVAPI32!DeregisterEventSource` at `0x1800240aa`
- `ADVAPI32!RegisterEventSourceW` at `0x18002402c`
- `ADVAPI32!RegisterEventSourceW` at `0x18002402c`
- `ADVAPI32!ReportEventW` at `0x1800240a1`
- `ADVAPI32!ReportEventW` at `0x1800240a1`

## pseudocode

```c
void __fastcall LogEventCommon(DWORD dwEventID, LPCWSTR *lpStrings, WORD a3, const unsigned __int16 *const a4, WORD a5)
{
  HANDLE v8; // rbx
  ULONG CurrentProcessId; // eax
  struct _UNICODE_STRING String; // [rsp+50h] [rbp-48h] BYREF
  _BYTE v11[24]; // [rsp+60h] [rbp-38h] BYREF

  String = 0;
  v8 = RegisterEventSourceW(0, L"RPC Proxy");
  if ( v8 )
  {
    *(_DWORD *)&String.Length = 1441792;
    String.Buffer = (PWSTR)v11;
    CurrentProcessId = GetCurrentProcessId();
    RtlIntegerToUnicodeString(CurrentProcessId, 0, &String);
    *lpStrings = (LPCWSTR)v11;
    ReportEventW(v8, a5, 1u, dwEventID, 0, a3, 0, lpStrings, 0);
    DeregisterEventSource(v8);
  }
}

```

## disassembly

```asm
0x180023ff4  mov     [rsp+arg_18], rbx
0x180023ff9  push    rbp
0x180023ffa  push    rsi
0x180023ffb  push    rdi
0x180023ffc  sub     rsp, 80h
0x180024003  mov     rax, cs:__security_cookie
0x18002400a  xor     rax, rsp
0x18002400d  mov     [rsp+98h+var_20], rax
0x180024012  mov     rdi, rdx
0x180024015  mov     esi, ecx
0x180024017  xorps   xmm0, xmm0
0x18002401a  lea     rdx, SourceName; "RPC Proxy"
0x180024021  xor     ecx, ecx; lpUNCServerName
0x180024023  movzx   ebp, r8w
0x180024027  movups  xmmword ptr [rsp+98h+String.Length], xmm0
0x18002402c  call    cs:__imp_RegisterEventSourceW
0x180024032  mov     rbx, rax
0x180024035  test    rax, rax
0x180024038  jz      short loc_1800240B0
0x18002403a  lea     rax, [rsp+98h+var_38]
0x18002403f  mov     dword ptr [rsp+98h+String.Length], 160000h
0x180024047  mov     [rsp+98h+String.Buffer], rax
0x18002404c  call    cs:__imp_GetCurrentProcessId
0x180024052  lea     r8, [rsp+98h+String]; String
0x180024057  xor     edx, edx; Base
0x180024059  mov     ecx, eax; Value
0x18002405b  call    cs:__imp_RtlIntegerToUnicodeString
0x180024061  movzx   edx, [rsp+98h+arg_20]; wType
0x180024069  lea     rax, [rsp+98h+var_38]
0x18002406e  mov     [rsp+98h+lpRawData], 0; lpRawData
0x180024077  mov     r8d, 1; wCategory
0x18002407d  mov     [rsp+98h+lpStrings], rdi; lpStrings
0x180024082  mov     r9d, esi; dwEventID
0x180024085  mov     [rsp+98h+dwDataSize], 0; dwDataSize
0x18002408d  mov     rcx, rbx; hEventLog
0x180024090  mov     [rsp+98h+wNumStrings], bp; wNumStrings
0x180024095  mov     [rsp+98h+lpUserSid], 0; lpUserSid
0x18002409e  mov     [rdi], rax
0x1800240a1  call    cs:__imp_ReportEventW
0x1800240a7  mov     rcx, rbx; hEventLog
0x1800240aa  call    cs:__imp_DeregisterEventSource
0x1800240b0  mov     rcx, [rsp+98h+var_20]
0x1800240b5  xor     rcx, rsp; StackCookie
0x1800240b8  call    __security_check_cookie
0x1800240bd  mov     rbx, [rsp+98h+arg_18]
0x1800240c5  add     rsp, 80h
0x1800240cc  pop     rdi
0x1800240cd  pop     rsi
0x1800240ce  pop     rbp
0x1800240cf  retn
```

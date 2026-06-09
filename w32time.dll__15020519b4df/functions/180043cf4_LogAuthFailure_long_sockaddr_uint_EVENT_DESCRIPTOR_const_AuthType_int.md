# LogAuthFailure(long,sockaddr *,uint,_EVENT_DESCRIPTOR const *,AuthType,int)

- ea: `0x180043cf4`
- end: `0x180043e0b`
- name: `?LogAuthFailure@@YAXJPEAUsockaddr@@IPEBU_EVENT_DESCRIPTOR@@W4AuthType@@H@Z`
- size: `279`
- prototype: `HLOCAL __fastcall(signed int, struct sockaddr *, DWORD, __int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003163c`

## callees

- `0x18000a7e0`
- `0x180018138`
- `0x18001a780`
- `0x18001d9a0`
- `0x18002bbf8`
- `0x180041fc8`
- `0x180043cf4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043ddf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043dee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043ddf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043dee`
- `ntdll!RtlInitUnicodeString` at `0x180043d65`
- `ntdll!RtlInitUnicodeString` at `0x180043d78`
- `ntdll!RtlInitUnicodeString` at `0x180043d65`
- `ntdll!RtlInitUnicodeString` at `0x180043d78`

## string_xrefs

- `0x180043d9d`: `Logging warning: NtpServer encountered an error while validating the computer account for symmetric peer %s. NtpServer cannot provide secure (%s) time to the peer and will not send a packet. The error was: %s\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HLOCAL __fastcall LogAuthFailure(signed int a1, struct sockaddr *a2, DWORD a3, __int64 a4, unsigned int a5, int a6)
{
  HLOCAL result; // rax
  int v9; // eax
  WCHAR *v10; // rbx
  WCHAR *v11; // rdi
  __int64 v12; // rax
  PCWSTR SourceString; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING v14; // [rsp+38h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  PCWSTR v16; // [rsp+88h] [rbp+28h] BYREF

  v16 = 0;
  SourceString = 0;
  result = (HLOCAL)GetSystemErrorString(a1, (unsigned __int16 **)&v16);
  if ( (int)result >= 0 )
  {
    v9 = MyAddressToString(a2, a3, (unsigned __int16 **)&SourceString);
    v10 = (WCHAR *)v16;
    if ( v9 >= 0 )
    {
      v11 = (WCHAR *)SourceString;
      DestinationString = 0;
      v14 = 0;
      RtlInitUnicodeString(&DestinationString, SourceString);
      RtlInitUnicodeString(&v14, v10);
      if ( (unsigned __int8)FileLogAllowEntry(2) )
      {
        v12 = AuthTypeToSz(a5);
        FileLogAdd(
          L"Logging warning: NtpServer encountered an error while validating the computer account for symmetric peer %s. N"
           "tpServer cannot provide secure (%s) time to the peer and will not send a packet. The error was: %s\n",
          v11,
          v12,
          v10);
      }
      if ( a6 )
        LogEvent(
          &_W32TimeRegistrationHandle,
          W32TIME_EVENT_SYMMETRIC_COMPUTE_SERVER_DIGEST_FAILED,
          L"uu",
          &DestinationString);
      LocalFree(v11);
    }
    return LocalFree(v10);
  }
  return result;
}

```

## disassembly

```asm
0x180043cf4  mov     [rsp-8+arg_0], rbx
0x180043cf9  mov     [rsp-8+arg_8], rdi
0x180043cfe  mov     [rsp-8+arg_18], r9
0x180043d03  push    rbp
0x180043d04  mov     rbp, rsp
0x180043d07  sub     rsp, 60h
0x180043d0b  mov     rdi, rdx
0x180043d0e  mov     [rbp+arg_18], 0
0x180043d16  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x180043d1a  mov     [rbp+SourceString], 0
0x180043d22  mov     ebx, r8d
0x180043d25  call    ?GetSystemErrorString@@YAJJPEAPEAG@Z; GetSystemErrorString(long,ushort * *)
0x180043d2a  test    eax, eax
0x180043d2c  js      loc_180043DFA
0x180043d32  lea     r8, [rbp+SourceString]; unsigned __int16 **
0x180043d36  mov     edx, ebx; dwAddressLength
0x180043d38  mov     rcx, rdi; lpsaAddress
0x180043d3b  call    ?MyAddressToString@@YAJPEAUsockaddr@@IPEAPEAG@Z; MyAddressToString(sockaddr *,uint,ushort * *)
0x180043d40  mov     rbx, [rbp+arg_18]
0x180043d44  test    eax, eax
0x180043d46  js      loc_180043DEB
0x180043d4c  mov     rdi, [rbp+SourceString]
0x180043d50  lea     rcx, [rbp+DestinationString]; DestinationString
0x180043d54  xorps   xmm0, xmm0
0x180043d57  xorps   xmm1, xmm1
0x180043d5a  mov     rdx, rdi; SourceString
0x180043d5d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180043d61  movups  xmmword ptr [rbp+var_28.Length], xmm1
0x180043d65  call    cs:__imp_RtlInitUnicodeString
0x180043d6c  nop     dword ptr [rax+rax+00h]
0x180043d71  mov     rdx, rbx; SourceString
0x180043d74  lea     rcx, [rbp+var_28]; DestinationString
0x180043d78  call    cs:__imp_RtlInitUnicodeString
0x180043d7f  nop     dword ptr [rax+rax+00h]
0x180043d84  mov     ecx, 2
0x180043d89  call    FileLogAllowEntry
0x180043d8e  test    al, al
0x180043d90  jz      short loc_180043DAF
0x180043d92  mov     ecx, [rbp+arg_20]
0x180043d95  call    ?AuthTypeToSz@@YAPEAGW4AuthType@@@Z; AuthTypeToSz(AuthType)
0x180043d9a  mov     r8, rax
0x180043d9d  lea     rcx, aLoggingWarning_14; "Logging warning: NtpServer encountered "...
0x180043da4  mov     r9, rbx
0x180043da7  mov     rdx, rdi
0x180043daa  call    FileLogAdd
0x180043daf  cmp     [rbp+arg_28], 0
0x180043db3  jz      short loc_180043DDC
0x180043db5  lea     rax, [rbp+var_28]
0x180043db9  lea     r9, [rbp+DestinationString]
0x180043dbd  mov     [rsp+60h+var_40], rax
0x180043dc2  lea     r8, aUu; "uu"
0x180043dc9  lea     rdx, W32TIME_EVENT_SYMMETRIC_COMPUTE_SERVER_DIGEST_FAILED
0x180043dd0  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x180043dd7  call    LogEvent
0x180043ddc  mov     rcx, rdi; hMem
0x180043ddf  call    cs:__imp_LocalFree
0x180043de6  nop     dword ptr [rax+rax+00h]
0x180043deb  mov     rcx, rbx; hMem
0x180043dee  call    cs:__imp_LocalFree
0x180043df5  nop     dword ptr [rax+rax+00h]
0x180043dfa  mov     rbx, [rsp+60h+arg_0]
0x180043dff  mov     rdi, [rsp+60h+arg_8]
0x180043e04  add     rsp, 60h
0x180043e08  pop     rbp
0x180043e09  retn
```

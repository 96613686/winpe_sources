# ReadDwordKey

- ea: `0x18000725c`
- end: `0x18000730a`
- name: `ReadDwordKey`
- size: `174`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000acac`

## callees

- `0x18000725c`
- `0x1800138f0`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x1800072cd`
- `ntdll!NtQueryValueKey` at `0x1800072cd`
- `ntdll!RtlInitUnicodeString` at `0x18000729c`
- `ntdll!RtlInitUnicodeString` at `0x18000729c`

## pseudocode

```c
NTSTATUS __fastcall ReadDwordKey(HANDLE KeyHandle, __int64 a2, _DWORD *a3)
{
  NTSTATUS result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-30h] BYREF
  __int128 KeyValueInformation; // [rsp+48h] [rbp-20h] BYREF

  ResultLength = 0;
  KeyValueInformation = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RestartApps");
  result = NtQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             &KeyValueInformation,
             0x10u,
             &ResultLength);
  if ( result >= 0 )
  {
    if ( DWORD1(KeyValueInformation) == 4 )
      *a3 = HIDWORD(KeyValueInformation);
    else
      return -1073741823;
  }
  return result;
}

```

## disassembly

```asm
0x18000725c  mov     [rsp+arg_8], rbx
0x180007261  push    rdi
0x180007262  sub     rsp, 60h
0x180007266  mov     rax, cs:__security_cookie
0x18000726d  xor     rax, rsp
0x180007270  mov     [rsp+68h+var_10], rax
0x180007275  xorps   xmm0, xmm0
0x180007278  mov     [rsp+68h+var_38], 0
0x180007280  mov     rbx, rcx
0x180007283  lea     rdx, aRestartapps; "RestartApps"
0x18000728a  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18000728f  mov     rdi, r8
0x180007292  movups  [rsp+68h+KeyValueInformation], xmm0
0x180007297  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18000729c  call    cs:__imp_RtlInitUnicodeString
0x1800072a3  nop     dword ptr [rax+rax+00h]
0x1800072a8  lea     rax, [rsp+68h+var_38]
0x1800072ad  mov     r8d, 2; KeyValueInformationClass
0x1800072b3  mov     [rsp+68h+ResultLength], rax; ResultLength
0x1800072b8  lea     r9, [rsp+68h+KeyValueInformation]; KeyValueInformation
0x1800072bd  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x1800072c2  mov     [rsp+68h+Length], 10h; Length
0x1800072ca  mov     rcx, rbx; KeyHandle
0x1800072cd  call    cs:__imp_NtQueryValueKey
0x1800072d4  nop     dword ptr [rax+rax+00h]
0x1800072d9  test    eax, eax
0x1800072db  js      short loc_1800072F1
0x1800072dd  cmp     dword ptr [rsp+68h+KeyValueInformation+4], 4
0x1800072e2  jnz     short loc_1800072EC
0x1800072e4  mov     ecx, dword ptr [rsp+68h+KeyValueInformation+0Ch]
0x1800072e8  mov     [rdi], ecx
0x1800072ea  jmp     short loc_1800072F1
0x1800072ec  mov     eax, 0C0000001h
0x1800072f1  mov     rcx, [rsp+68h+var_10]
0x1800072f6  xor     rcx, rsp; StackCookie
0x1800072f9  call    __security_check_cookie
0x1800072fe  mov     rbx, [rsp+68h+arg_8]
0x180007303  add     rsp, 60h
0x180007307  pop     rdi
0x180007308  retn
```

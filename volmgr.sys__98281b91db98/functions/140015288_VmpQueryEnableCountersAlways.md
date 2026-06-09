# VmpQueryEnableCountersAlways

- ea: `0x140015288`
- end: `0x140015415`
- name: `VmpQueryEnableCountersAlways`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000e270`

## callees

- `0x140005050`
- `0x140005090`
- `0x140015288`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400152e4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140015346`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400152e4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140015346`
- `ntoskrnl!ZwClose` at `0x140015391`
- `ntoskrnl!ZwClose` at `0x140015391`
- `ntoskrnl!ZwQueryValueKey` at `0x140015373`
- `ntoskrnl!ZwQueryValueKey` at `0x140015373`
- `ntoskrnl!ZwOpenKey` at `0x140015323`
- `ntoskrnl!ZwOpenKey` at `0x140015323`

## string_xrefs

- `0x1400152b4`: `\Registry\Machine\System\CurrentControlSet\Services\Partmgr`

## pseudocode

```c
__int64 __fastcall VmpQueryEnableCountersAlways(__int64 a1)
{
  __int64 v1; // rdi
  NTSTATUS v2; // ebx
  int v3; // esi
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-9h] BYREF
  _BYTE KeyValueInformation[8]; // [rsp+80h] [rbp+27h] BYREF
  int v10; // [rsp+88h] [rbp+2Fh]
  int v11; // [rsp+8Ch] [rbp+33h]

  v1 = *(_QWORD *)(a1 + 64);
  KeyHandle = 0;
  ResultLength = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Partmgr");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v2 >= 0 )
  {
    v3 = 0;
    RtlInitUnicodeString(&DestinationString, L"EnableCounterForIoctl");
    v2 = ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x10u,
           &ResultLength);
    if ( v2 >= 0 && v10 == 4 )
      v3 = v11;
    ZwClose(KeyHandle);
    if ( v2 >= 0 )
    {
      if ( v3 == 1 )
      {
        if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v1 + 216), 1, 0) )
        {
          v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v1 + 8) + 304LL))(v1 + 224);
          if ( v2 < 0 )
            _InterlockedExchange((volatile __int32 *)(v1 + 216), 0);
          else
            *(_BYTE *)(v1 + 161) = 1;
        }
      }
      else
      {
        return (unsigned int)-1073741808;
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140015288  mov     [rsp-8+arg_8], rbx
0x14001528d  mov     [rsp-8+arg_10], rsi
0x140015292  push    rbp
0x140015293  push    rdi
0x140015294  push    r15
0x140015296  lea     rbp, [rsp-47h]
0x14001529b  sub     rsp, 0A0h
0x1400152a2  mov     rax, cs:__security_cookie
0x1400152a9  xor     rax, rsp
0x1400152ac  mov     [rbp+57h+var_20], rax
0x1400152b0  mov     rdi, [rcx+40h]
0x1400152b4  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400152bb  xorps   xmm1, xmm1
0x1400152be  mov     [rbp+57h+KeyHandle], 0
0x1400152c6  xorps   xmm0, xmm0
0x1400152c9  mov     [rbp+57h+var_80], 0
0x1400152d0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400152d4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400152d8  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1400152dc  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1400152e0  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400152e4  call    cs:__imp_RtlInitUnicodeString
0x1400152eb  nop     dword ptr [rax+rax+00h]
0x1400152f0  lea     rax, [rbp+57h+DestinationString]
0x1400152f4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400152fb  xorps   xmm0, xmm0
0x1400152fe  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140015302  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140015306  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14001530e  mov     edx, 20019h; DesiredAccess
0x140015313  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14001531a  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14001531e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140015323  call    cs:__imp_ZwOpenKey
0x14001532a  nop     dword ptr [rax+rax+00h]
0x14001532f  mov     ebx, eax
0x140015331  test    eax, eax
0x140015333  js      loc_1400153EE
0x140015339  lea     rdx, aEnablecounterf; "EnableCounterForIoctl"
0x140015340  xor     esi, esi
0x140015342  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140015346  call    cs:__imp_RtlInitUnicodeString
0x14001534d  nop     dword ptr [rax+rax+00h]
0x140015352  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140015356  lea     rax, [rbp+57h+var_80]
0x14001535a  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x14001535f  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140015363  lea     r8d, [rsi+2]; KeyValueInformationClass
0x140015367  mov     [rsp+0B0h+Length], 10h; Length
0x14001536f  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140015373  call    cs:__imp_ZwQueryValueKey
0x14001537a  nop     dword ptr [rax+rax+00h]
0x14001537f  mov     ebx, eax
0x140015381  test    eax, eax
0x140015383  js      short loc_14001538D
0x140015385  cmp     [rbp+57h+var_28], 4
0x140015389  cmovz   esi, [rbp+57h+var_24]
0x14001538d  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140015391  call    cs:__imp_ZwClose
0x140015398  nop     dword ptr [rax+rax+00h]
0x14001539d  test    ebx, ebx
0x14001539f  js      short loc_1400153EE
0x1400153a1  mov     r15d, 1
0x1400153a7  cmp     esi, r15d
0x1400153aa  jnz     short loc_1400153E9
0x1400153ac  xor     eax, eax
0x1400153ae  lock cmpxchg [rdi+0D8h], r15d
0x1400153b7  jnz     short loc_1400153EE
0x1400153b9  mov     rax, [rdi+8]
0x1400153bd  lea     rcx, [rdi+0E0h]
0x1400153c4  mov     rax, [rax+130h]
0x1400153cb  call    _guard_dispatch_icall
0x1400153d0  mov     ebx, eax
0x1400153d2  test    eax, eax
0x1400153d4  js      short loc_1400153DF
0x1400153d6  mov     [rdi+0A1h], r15b
0x1400153dd  jmp     short loc_1400153EE
0x1400153df  xor     eax, eax
0x1400153e1  xchg    eax, [rdi+0D8h]
0x1400153e7  jmp     short loc_1400153EE
0x1400153e9  mov     ebx, 0C0000010h
0x1400153ee  mov     eax, ebx
0x1400153f0  mov     rcx, [rbp+57h+var_20]
0x1400153f4  xor     rcx, rsp; StackCookie
0x1400153f7  call    __security_check_cookie
0x1400153fc  lea     r11, [rsp+0B0h+var_10]
0x140015404  mov     rbx, [r11+28h]
0x140015408  mov     rsi, [r11+30h]
0x14001540c  mov     rsp, r11
0x14001540f  pop     r15
0x140015411  pop     rdi
0x140015412  pop     rbp
0x140015413  retn
```

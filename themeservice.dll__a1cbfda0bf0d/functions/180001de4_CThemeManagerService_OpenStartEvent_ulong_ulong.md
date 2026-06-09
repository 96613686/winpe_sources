# CThemeManagerService::OpenStartEvent(ulong,ulong)

- ea: `0x180001de4`
- end: `0x180001eda`
- name: `?OpenStartEvent@CThemeManagerService@@SAPEAXKK@Z`
- size: `246`
- prototype: `void *__fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ce50`

## callees

- `0x180001de4`
- `0x180002ae0`
- `0x18000fa00`

## import_xrefs

- `ntdll!NtOpenEvent` at `0x180001eb2`
- `ntdll!NtOpenEvent` at `0x180001eb2`
- `ntdll!RtlInitUnicodeString` at `0x180001e71`
- `ntdll!RtlInitUnicodeString` at `0x180001e71`

## pseudocode

```c
void *__fastcall CThemeManagerService::OpenStartEvent(unsigned int a1)
{
  int v1; // eax
  void *EventHandle; // [rsp+30h] [rbp-D0h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SourceString[64]; // [rsp+80h] [rbp-80h] BYREF

  EventHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( a1 )
    v1 = StringCchPrintfW(SourceString, 0x40u, L"\\Sessions\\%d\\BaseNamedObjects\\%s", a1, L"ThemesStartEvent");
  else
    v1 = StringCchPrintfW(SourceString, 0x40u, L"\\BaseNamedObjects\\%s", L"ThemesStartEvent");
  if ( v1 < 0 )
    return 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenEvent(&EventHandle, 2u, &ObjectAttributes) < 0 )
    return 0;
  else
    return EventHandle;
}

```

## disassembly

```asm
0x180001de4  push    rbp
0x180001de6  lea     rbp, [rsp-10h]
0x180001deb  sub     rsp, 110h
0x180001df2  mov     rax, cs:__security_cookie
0x180001df9  xor     rax, rsp
0x180001dfc  mov     [rbp+10h+var_10], rax
0x180001e00  mov     [rsp+110h+EventHandle], 0
0x180001e09  xorps   xmm1, xmm1
0x180001e0c  xorps   xmm0, xmm0
0x180001e0f  mov     edx, 40h ; '@'; unsigned __int64
0x180001e14  movups  xmmword ptr [rsp+110h+DestinationString.Length], xmm0
0x180001e19  movups  xmmword ptr [rsp+110h+ObjectAttributes.Length], xmm1
0x180001e1e  movups  xmmword ptr [rsp+110h+ObjectAttributes.ObjectName], xmm1
0x180001e23  movups  xmmword ptr [rsp+110h+ObjectAttributes.SecurityDescriptor], xmm1
0x180001e28  test    ecx, ecx
0x180001e2a  jnz     short loc_180001E45
0x180001e2c  lea     r9, aThemesstarteve; "ThemesStartEvent"
0x180001e33  lea     r8, aBasenamedobjec; "\\BaseNamedObjects\\%s"
0x180001e3a  lea     rcx, [rbp+10h+SourceString]; unsigned __int16 *
0x180001e3e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180001e43  jmp     short loc_180001E64
0x180001e45  lea     rax, aThemesstarteve; "ThemesStartEvent"
0x180001e4c  mov     r9d, ecx
0x180001e4f  lea     rcx, [rbp+10h+SourceString]; unsigned __int16 *
0x180001e53  mov     [rsp+110h+var_F0], rax
0x180001e58  lea     r8, aSessionsDBasen; "\\Sessions\\%d\\BaseNamedObjects\\%s"
0x180001e5f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180001e64  test    eax, eax
0x180001e66  js      short loc_180001EC3
0x180001e68  lea     rdx, [rbp+10h+SourceString]; SourceString
0x180001e6c  lea     rcx, [rsp+110h+DestinationString]; DestinationString
0x180001e71  call    cs:__imp_RtlInitUnicodeString
0x180001e77  lea     rax, [rsp+110h+DestinationString]
0x180001e7c  mov     [rsp+110h+ObjectAttributes.Length], 30h ; '0'
0x180001e84  xorps   xmm0, xmm0
0x180001e87  mov     [rsp+110h+ObjectAttributes.ObjectName], rax
0x180001e8c  lea     r8, [rsp+110h+ObjectAttributes]; ObjectAttributes
0x180001e91  mov     [rsp+110h+ObjectAttributes.RootDirectory], 0
0x180001e9a  mov     edx, 2; DesiredAccess
0x180001e9f  mov     [rsp+110h+ObjectAttributes.Attributes], 0
0x180001ea7  lea     rcx, [rsp+110h+EventHandle]; EventHandle
0x180001eac  movdqu  xmmword ptr [rsp+110h+ObjectAttributes.SecurityDescriptor], xmm0
0x180001eb2  call    cs:__imp_NtOpenEvent
0x180001eb8  test    eax, eax
0x180001eba  js      short loc_180001EC3
0x180001ebc  mov     rax, [rsp+110h+EventHandle]
0x180001ec1  jmp     short loc_180001EC5
0x180001ec3  xor     eax, eax
0x180001ec5  mov     rcx, [rbp+10h+var_10]
0x180001ec9  xor     rcx, rsp; StackCookie
0x180001ecc  call    __security_check_cookie
0x180001ed1  add     rsp, 110h
0x180001ed8  pop     rbp
0x180001ed9  retn
```

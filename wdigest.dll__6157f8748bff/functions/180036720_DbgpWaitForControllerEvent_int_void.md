# _DbgpWaitForControllerEvent(int *,void * *)

- ea: `0x180036720`
- end: `0x18003686e`
- name: `?_DbgpWaitForControllerEvent@@YAJPEAHPEAPEAX@Z`
- size: `334`
- prototype: `int(int *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x180036360`

## callees

- `0x180012880`
- `0x180013364`
- `0x180036310`
- `0x180036720`

## import_xrefs

- `ntdll!NtOpenEvent` at `0x180036814`
- `ntdll!NtOpenEvent` at `0x180036814`
- `ntdll!NtCreateEvent` at `0x1800367f3`
- `ntdll!NtCreateEvent` at `0x1800367f3`
- `ntdll!NtWaitForSingleObject` at `0x180036831`
- `ntdll!NtWaitForSingleObject` at `0x180036831`
- `ntdll!RtlInitUnicodeString` at `0x1800367ac`
- `ntdll!RtlInitUnicodeString` at `0x1800367ac`

## pseudocode

```c
NTSTATUS __fastcall _DbgpWaitForControllerEvent(int *a1, void **a2)
{
  const unsigned __int16 *TraceMappingName; // rax
  NTSTATUS result; // eax
  void *v6; // rcx
  union _LARGE_INTEGER Timeout; // [rsp+30h] [rbp-D0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  wchar_t Buffer[264]; // [rsp+80h] [rbp-80h] BYREF

  Timeout.QuadPart = 0;
  *a1 = 0;
  memset(&ObjectAttributes.Length + 1, 0, 44);
  Buffer[259] = 0;
  DestinationString = 0;
  TraceMappingName = _DbgpGetTraceMappingName();
  snwprintf_s(Buffer, 0x104u, 0x103u, L"\\DSYSDBG.%s", TraceMappingName);
  RtlInitUnicodeString(&DestinationString, Buffer);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 0;
  result = NtCreateEvent(a2, 0x100002u, &ObjectAttributes, NotificationEvent, 0);
  if ( result == -1073741771 || result == 0x40000000 )
  {
    result = NtOpenEvent(a2, 0x100000u, &ObjectAttributes);
    if ( result >= 0 )
    {
      v6 = *a2;
      Timeout.QuadPart = -600000000;
      result = NtWaitForSingleObject(v6, 0, &Timeout);
      if ( result )
      {
        if ( result >= 0 )
          return -1073741823;
      }
      else
      {
        *a1 = 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180036720  mov     [rsp-8+arg_10], rbx
0x180036725  mov     [rsp-8+arg_18], rdi
0x18003672a  push    rbp
0x18003672b  lea     rbp, [rsp-1A0h]
0x180036733  sub     rsp, 2A0h
0x18003673a  mov     rax, cs:__security_cookie
0x180036741  xor     rax, rsp
0x180036744  mov     [rbp+1A0h+var_10], rax
0x18003674b  xorps   xmm0, xmm0
0x18003674e  mov     qword ptr [rsp+2A0h+Timeout], 0
0x180036757  xor     eax, eax
0x180036759  mov     dword ptr [rcx], 0
0x18003675f  movups  xmmword ptr [rsp+2A0h+ObjectAttributes.Length], xmm0
0x180036764  mov     [rbp+1A0h+var_1A], ax
0x18003676b  mov     rbx, rdx
0x18003676e  movups  xmmword ptr [rsp+2A0h+ObjectAttributes.ObjectName], xmm0
0x180036773  mov     rdi, rcx
0x180036776  movups  xmmword ptr [rsp+2A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003677b  movups  xmmword ptr [rsp+2A0h+DestinationString.Length], xmm0
0x180036780  call    ?_DbgpGetTraceMappingName@@YAPEBGXZ; _DbgpGetTraceMappingName(void)
0x180036785  mov     edx, 104h; BufferCount
0x18003678a  mov     qword ptr [rsp+2A0h+InitialState], rax
0x18003678f  lea     r9, aDsysdbgS; "\\DSYSDBG.%s"
0x180036796  lea     rcx, [rbp+1A0h+Buffer]; Buffer
0x18003679a  lea     r8d, [rdx-1]; MaxCount
0x18003679e  call    _snwprintf_s
0x1800367a3  lea     rdx, [rbp+1A0h+Buffer]; SourceString
0x1800367a7  lea     rcx, [rsp+2A0h+DestinationString]; DestinationString
0x1800367ac  call    cs:__imp_RtlInitUnicodeString
0x1800367b2  lea     rax, [rsp+2A0h+DestinationString]
0x1800367b7  mov     [rsp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x1800367bf  xorps   xmm0, xmm0
0x1800367c2  mov     [rsp+2A0h+ObjectAttributes.ObjectName], rax
0x1800367c7  xor     r9d, r9d; EventType
0x1800367ca  mov     [rsp+2A0h+ObjectAttributes.RootDirectory], 0
0x1800367d3  lea     r8, [rsp+2A0h+ObjectAttributes]; ObjectAttributes
0x1800367d8  mov     [rsp+2A0h+ObjectAttributes.Attributes], 0
0x1800367e0  mov     edx, 100002h; DesiredAccess
0x1800367e5  mov     [rsp+2A0h+InitialState], 0; InitialState
0x1800367ea  mov     rcx, rbx; EventHandle
0x1800367ed  movdqu  xmmword ptr [rsp+2A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800367f3  call    cs:__imp_NtCreateEvent
0x1800367f9  cmp     eax, 0C0000035h
0x1800367fe  jz      short loc_180036807
0x180036800  cmp     eax, 40000000h
0x180036805  jnz     short loc_18003684A
0x180036807  lea     r8, [rsp+2A0h+ObjectAttributes]; ObjectAttributes
0x18003680c  mov     edx, 100000h; DesiredAccess
0x180036811  mov     rcx, rbx; EventHandle
0x180036814  call    cs:__imp_NtOpenEvent
0x18003681a  test    eax, eax
0x18003681c  js      short loc_18003684A
0x18003681e  mov     rcx, [rbx]; Handle
0x180036821  lea     r8, [rsp+2A0h+Timeout]; Timeout
0x180036826  xor     edx, edx; Alertable
0x180036828  mov     qword ptr [rsp+2A0h+Timeout], 0FFFFFFFFDC3CBA00h
0x180036831  call    cs:__imp_NtWaitForSingleObject
0x180036837  test    eax, eax
0x180036839  jz      short loc_180036844
0x18003683b  js      short loc_18003684A
0x18003683d  mov     eax, 0C0000001h
0x180036842  jmp     short loc_18003684A
0x180036844  mov     dword ptr [rdi], 1
0x18003684a  mov     rcx, [rbp+1A0h+var_10]
0x180036851  xor     rcx, rsp; StackCookie
0x180036854  call    __security_check_cookie
0x180036859  lea     r11, [rsp+2A0h+var_s0]
0x180036861  mov     rbx, [r11+20h]
0x180036865  mov     rdi, [r11+28h]
0x180036869  mov     rsp, r11
0x18003686c  pop     rbp
0x18003686d  retn
```

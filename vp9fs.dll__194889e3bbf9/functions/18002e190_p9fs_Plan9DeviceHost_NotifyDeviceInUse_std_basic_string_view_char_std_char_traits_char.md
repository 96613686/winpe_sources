# p9fs::Plan9DeviceHost::NotifyDeviceInUse(std::basic_string_view<char,std::char_traits<char>>)

- ea: `0x18002e190`
- end: `0x18002e26b`
- name: `?NotifyDeviceInUse@Plan9DeviceHost@p9fs@@QEAAXV?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18002e28c`

## callees

- `0x180004120`
- `0x180004c98`
- `0x18001d8b4`
- `0x180028718`
- `0x18002e190`
- `0x180034010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18002e215`
- `ntdll!RtlFreeUnicodeString` at `0x18002e215`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18002e1e2`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18002e1e2`

## string_xrefs

- `0x18002e235`: `onecore\vm\dv\storage\plan9\dll\windows\p9virtio.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall p9fs::Plan9DeviceHost::NotifyDeviceInUse(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  NTSTATUS v4; // eax
  __int128 pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  __int64 v6; // [rsp+30h] [rbp-30h]
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-28h] BYREF
  _STRING SourceString; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v3 = *(unsigned __int16 *)(a2 + 8);
  if ( v3 != *(_QWORD *)(a2 + 8) )
  {
    pExceptionObject = 0;
    v6 = 0;
    gsl::narrowing_error::narrowing_error((gsl::narrowing_error *)&pExceptionObject);
    throw (gsl::narrowing_error *)&pExceptionObject;
  }
  SourceString.Length = *(_WORD *)(a2 + 8);
  SourceString.MaximumLength = v3;
  *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
  SourceString.Buffer = *(PCHAR *)a2;
  DestinationString = 0;
  v4 = RtlAnsiStringToUnicodeString(&DestinationString, &SourceString, 1u);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x266,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
      (const char *)(unsigned int)v4,
      pExceptionObject);
  *(_QWORD *)&pExceptionObject = &DestinationString;
  BYTE8(pExceptionObject) = 1;
  (*(void (__fastcall **)(_QWORD, PWSTR))(**(_QWORD **)(a1 + 8) + 24LL))(*(_QWORD *)(a1 + 8), DestinationString.Buffer);
  RtlFreeUnicodeString(&DestinationString);
}

```

## disassembly

```asm
0x18002e190  mov     [rsp-8+arg_8], rbx
0x18002e195  push    rbp
0x18002e196  mov     rbp, rsp
0x18002e199  sub     rsp, 60h
0x18002e19d  mov     rax, cs:__security_cookie
0x18002e1a4  xor     rax, rsp
0x18002e1a7  mov     [rbp+var_8], rax
0x18002e1ab  mov     rbx, rcx
0x18002e1ae  movzx   eax, word ptr [rdx+8]
0x18002e1b2  xorps   xmm0, xmm0
0x18002e1b5  cmp     rax, [rdx+8]
0x18002e1b9  jnz     loc_18002E247
0x18002e1bf  xor     ecx, ecx
0x18002e1c1  mov     [rbp+SourceString.Length], ax
0x18002e1c5  mov     [rbp+SourceString.MaximumLength], ax
0x18002e1c9  mov     dword ptr [rbp+SourceString+4], ecx
0x18002e1cc  mov     rax, [rdx]
0x18002e1cf  mov     [rbp+SourceString.Buffer], rax
0x18002e1d3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002e1d7  mov     r8b, 1; AllocateDestinationString
0x18002e1da  lea     rdx, [rbp+SourceString]; SourceString
0x18002e1de  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002e1e2  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18002e1e8  mov     rcx, [rbp+8]; this
0x18002e1ec  test    eax, eax
0x18002e1ee  js      short loc_18002E232
0x18002e1f0  lea     rax, [rbp+DestinationString]
0x18002e1f4  mov     qword ptr [rbp+pExceptionObject], rax
0x18002e1f8  mov     byte ptr [rbp+pExceptionObject+8], 1
0x18002e1fc  mov     rcx, [rbx+8]
0x18002e200  mov     rax, [rcx]
0x18002e203  mov     rdx, [rbp+DestinationString.Buffer]
0x18002e207  mov     rax, [rax+18h]
0x18002e20b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e210  nop
0x18002e211  lea     rcx, [rbp+DestinationString]; UnicodeString
0x18002e215  call    cs:__imp_RtlFreeUnicodeString
0x18002e21b  mov     rcx, [rbp+var_8]
0x18002e21f  xor     rcx, rsp; StackCookie
0x18002e222  call    __security_check_cookie
0x18002e227  mov     rbx, [rsp+60h+arg_8]
0x18002e22c  add     rsp, 60h
0x18002e230  pop     rbp
0x18002e231  retn
0x18002e232  mov     r9d, eax; char *
0x18002e235  lea     r8, aOnecoreVmDvSto_0; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002e23c  mov     edx, 266h; void *
0x18002e241  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002e247  xor     eax, eax
0x18002e249  movups  [rbp+pExceptionObject], xmm0
0x18002e24d  mov     [rbp+var_30], rax
0x18002e251  lea     rcx, [rbp+pExceptionObject]; this
0x18002e255  call    ??0narrowing_error@gsl@@QEAA@XZ; gsl::narrowing_error::narrowing_error(void)
0x18002e25a  lea     rdx, _TI2?AUnarrowing_error@gsl@@; pThrowInfo
0x18002e261  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002e265  call    _CxxThrowException_0
```

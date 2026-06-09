# CheckValidLayoutName(ushort *)

- ea: `0x1800192f4`
- end: `0x18001937e`
- name: `?CheckValidLayoutName@@YAXPEAG@Z`
- size: `138`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019650`

## callees

- `0x1800192f4`
- `0x18004c348`
- `0x18004ed44`
- `0x180096e00`

## import_xrefs

- `ntdll!wcstoul` at `0x180019343`
- `ntdll!wcstoul` at `0x180019343`
- `ntdll!NtClose` at `0x18009990a`
- `ntdll!NtClose` at `0x18009990a`
- `ntdll!NtOpenKey` at `0x180099863`
- `ntdll!NtOpenKey` at `0x1800998e9`
- `ntdll!NtOpenKey` at `0x180099863`
- `ntdll!NtOpenKey` at `0x1800998e9`
- `ntdll!RtlInitUnicodeString` at `0x180099822`
- `ntdll!RtlInitUnicodeString` at `0x1800998ac`
- `ntdll!RtlInitUnicodeString` at `0x180099822`
- `ntdll!RtlInitUnicodeString` at `0x1800998ac`

## string_xrefs

- `0x1800997f4`: `\Registry\Machine\System\CurrentControlSet\Control\Keyboard Layouts\`
- `0x180099871`: `\Registry\Machine\System\CurrentControlSet\Control\Keyboard Layouts\`

## pseudocode

```c
void __fastcall CheckValidLayoutName(unsigned __int16 *a1)
{
  void *KeyHandle; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-D8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SourceString[160]; // [rsp+70h] [rbp-90h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( ((wcstoul(a1, 0, 16) >> 16) & 0xF000) == 0xE000 )
  {
    StringCchCopyW(SourceString, 0x9Au, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Keyboard Layouts\\");
    StringCchCatW(SourceString, 0x9Au, a1);
    RtlInitUnicodeString(&DestinationString, SourceString);
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.Length = 48;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
      goto LABEL_5;
    *(_DWORD *)a1 = 3145829;
    *((_DWORD *)a1 + 1) = 3211312;
    StringCchCopyW(SourceString, 0x9Au, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Keyboard Layouts\\");
    StringCchCatW(SourceString, 0x9Au, a1);
    RtlInitUnicodeString(&DestinationString, SourceString);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
    {
LABEL_5:
      NtClose(KeyHandle);
    }
    else
    {
      *((_DWORD *)a1 + 1) = 3145776;
      *(_DWORD *)a1 = 3145776;
    }
  }
}

```

## disassembly

```asm
0x1800192f4  push    rbp
0x1800192f6  push    rbx
0x1800192f7  push    rdi
0x1800192f8  push    r14
0x1800192fa  lea     rbp, [rsp-0C8h]
0x180019302  sub     rsp, 1C8h
0x180019309  mov     rax, cs:__security_cookie
0x180019310  xor     rax, rsp
0x180019313  mov     [rbp+0E0h+var_30], rax
0x18001931a  xorps   xmm0, xmm0
0x18001931d  mov     [rsp+1E0h+KeyHandle], 0
0x180019326  xor     edx, edx; EndPtr
0x180019328  mov     rbx, rcx
0x18001932b  movups  xmmword ptr [rsp+1E0h+ObjectAttributes.Length], xmm0
0x180019330  movups  xmmword ptr [rsp+1E0h+ObjectAttributes.ObjectName], xmm0
0x180019335  lea     r8d, [rdx+10h]; Radix
0x180019339  movups  xmmword ptr [rsp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001933e  movups  xmmword ptr [rsp+1E0h+DestinationString.Length], xmm0
0x180019343  call    cs:__imp_wcstoul
0x180019349  shr     eax, 10h
0x18001934c  mov     ecx, 0F000h
0x180019351  and     ax, cx
0x180019354  mov     ecx, 0E000h
0x180019359  cmp     ax, cx
0x18001935c  jz      loc_1800997EE
0x180019362  mov     rcx, [rbp+0E0h+var_30]
0x180019369  xor     rcx, rsp; StackCookie
0x18001936c  call    __security_check_cookie
0x180019371  add     rsp, 1C8h
0x180019378  pop     r14
0x18001937a  pop     rdi
0x18001937b  pop     rbx
0x18001937c  pop     rbp
0x18001937d  retn
0x1800997ee  mov     r14d, 9Ah
0x1800997f4  lea     r8, aRegistryMachin_4; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800997fb  mov     edx, r14d; unsigned __int64
0x1800997fe  lea     rcx, [rsp+1E0h+SourceString]; unsigned __int16 *
0x180099803  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180099808  mov     r8, rbx; unsigned __int16 *
0x18009980b  lea     rcx, [rsp+1E0h+SourceString]; unsigned __int16 *
0x180099810  mov     edx, r14d; unsigned __int64
0x180099813  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180099818  lea     rdx, [rsp+1E0h+SourceString]; SourceString
0x18009981d  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x180099822  call    cs:__imp_RtlInitUnicodeString
0x180099828  lea     rax, [rsp+1E0h+DestinationString]
0x18009982d  mov     [rsp+1E0h+ObjectAttributes.RootDirectory], 0
0x180099836  xorps   xmm0, xmm0
0x180099839  mov     [rsp+1E0h+ObjectAttributes.ObjectName], rax
0x18009983e  lea     edi, [r14-6Ah]
0x180099842  mov     [rsp+1E0h+ObjectAttributes.Attributes], 40h ; '@'
0x18009984a  lea     r8, [rsp+1E0h+ObjectAttributes]; ObjectAttributes
0x18009984f  mov     [rsp+1E0h+ObjectAttributes.Length], edi
0x180099853  mov     edx, 20019h; DesiredAccess
0x180099858  lea     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x18009985d  movdqu  xmmword ptr [rsp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180099863  call    cs:__imp_NtOpenKey
0x180099869  test    eax, eax
0x18009986b  jns     loc_180099905
0x180099871  lea     r8, aRegistryMachin_4; "\\Registry\\Machine\\System\\CurrentCon"...
0x180099878  mov     dword ptr [rbx], 300065h
0x18009987e  mov     edx, r14d; unsigned __int64
0x180099881  mov     dword ptr [rbx+4], 310030h
0x180099888  lea     rcx, [rsp+1E0h+SourceString]; unsigned __int16 *
0x18009988d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180099892  mov     r8, rbx; unsigned __int16 *
0x180099895  lea     rcx, [rsp+1E0h+SourceString]; unsigned __int16 *
0x18009989a  mov     edx, r14d; unsigned __int64
0x18009989d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800998a2  lea     rdx, [rsp+1E0h+SourceString]; SourceString
0x1800998a7  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x1800998ac  call    cs:__imp_RtlInitUnicodeString
0x1800998b2  lea     rax, [rsp+1E0h+DestinationString]
0x1800998b7  mov     [rsp+1E0h+ObjectAttributes.Length], edi
0x1800998bb  xorps   xmm0, xmm0
0x1800998be  mov     [rsp+1E0h+ObjectAttributes.ObjectName], rax
0x1800998c3  lea     r8, [rsp+1E0h+ObjectAttributes]; ObjectAttributes
0x1800998c8  mov     [rsp+1E0h+ObjectAttributes.RootDirectory], 0
0x1800998d1  mov     edx, 20019h; DesiredAccess
0x1800998d6  mov     [rsp+1E0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800998de  lea     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x1800998e3  movdqu  xmmword ptr [rsp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800998e9  call    cs:__imp_NtOpenKey
0x1800998ef  test    eax, eax
0x1800998f1  jns     short loc_180099905
0x1800998f3  mov     dword ptr [rbx+4], 300030h
0x1800998fa  mov     dword ptr [rbx], 300030h
0x180099900  jmp     loc_180019362
0x180099905  mov     rcx, [rsp+1E0h+KeyHandle]; Handle
0x18009990a  call    cs:__imp_NtClose
0x180099910  nop
0x180099911  jmp     loc_180019362
```

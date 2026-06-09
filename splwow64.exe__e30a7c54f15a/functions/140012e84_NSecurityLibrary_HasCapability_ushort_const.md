# NSecurityLibrary::HasCapability(ushort const *)

- ea: `0x140012e84`
- end: `0x140012f21`
- name: `?HasCapability@NSecurityLibrary@@YA_NPEBG@Z`
- size: `157`
- prototype: `bool __fastcall(NSecurityLibrary *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400077fc`
- `0x14000f5c4`

## callees

- `0x140001ee0`
- `0x140012e84`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140012eb8`
- `ntdll!RtlInitUnicodeString` at `0x140012eb8`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x140012ed0`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x140012ed0`
- `ntdll!RtlCheckTokenCapability` at `0x140012eec`
- `ntdll!RtlCheckTokenCapability` at `0x140012eec`

## pseudocode

```c
char __fastcall NSecurityLibrary::HasCapability(NSecurityLibrary *this, const unsigned __int16 *a2)
{
  char v3; // bl
  _BYTE v4[8]; // [rsp+20h] [rbp-D8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-D0h] BYREF
  _BYTE v6[80]; // [rsp+40h] [rbp-B8h] BYREF
  _BYTE v7[80]; // [rsp+90h] [rbp-68h] BYREF

  v4[0] = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"isolatedWin32-print");
  if ( (int)RtlDeriveCapabilitySidsFromName(&DestinationString, v7, v6) < 0 )
    return 0;
  v3 = 0;
  if ( (int)RtlCheckTokenCapability(0, v6, v4) >= 0 )
    return v4[0] != 0;
  return v3;
}

```

## disassembly

```asm
0x140012e84  push    rbx
0x140012e86  sub     rsp, 0F0h
0x140012e8d  mov     rax, cs:__security_cookie
0x140012e94  xor     rax, rsp
0x140012e97  mov     [rsp+0F8h+var_18], rax
0x140012e9f  xorps   xmm0, xmm0
0x140012ea2  mov     [rsp+0F8h+var_D8], 0
0x140012ea7  lea     rdx, SourceString; "isolatedWin32-print"
0x140012eae  lea     rcx, [rsp+0F8h+DestinationString]; DestinationString
0x140012eb3  movups  xmmword ptr [rsp+0F8h+DestinationString.Length], xmm0
0x140012eb8  call    cs:__imp_RtlInitUnicodeString
0x140012ebe  lea     r8, [rsp+0F8h+var_B8]
0x140012ec3  lea     rdx, [rsp+0F8h+var_68]
0x140012ecb  lea     rcx, [rsp+0F8h+DestinationString]
0x140012ed0  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x140012ed6  test    eax, eax
0x140012ed8  jns     short loc_140012EDE
0x140012eda  xor     al, al
0x140012edc  jmp     short loc_140012F08
0x140012ede  lea     r8, [rsp+0F8h+var_D8]
0x140012ee3  xor     ecx, ecx
0x140012ee5  lea     rdx, [rsp+0F8h+var_B8]
0x140012eea  xor     bl, bl
0x140012eec  call    cs:__imp_RtlCheckTokenCapability
0x140012ef2  test    eax, eax
0x140012ef4  js      short loc_140012F06
0x140012ef6  cmp     [rsp+0F8h+var_D8], 0
0x140012efb  mov     eax, 1
0x140012f00  movzx   ebx, bl
0x140012f03  cmovnz  ebx, eax
0x140012f06  mov     al, bl
0x140012f08  mov     rcx, [rsp+0F8h+var_18]
0x140012f10  xor     rcx, rsp; StackCookie
0x140012f13  call    __security_check_cookie
0x140012f18  add     rsp, 0F0h
0x140012f1f  pop     rbx
0x140012f20  retn
```

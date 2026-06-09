# ConvertSidToStringSidW

- ea: `0x18000e110`
- end: `0x18000e214`
- name: `ConvertSidToStringSidW`
- size: `260`
- prototype: `BOOL __stdcall(PSID Sid, LPWSTR *StringSid)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001a590`
- `0x18001b030`
- `0x1800237d8`
- `0x180039910`

## callees

- `0x18000e110`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000e1c7`
- `ntdll!RtlNtStatusToDosError` at `0x18000e1c7`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18000e13e`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18000e13e`
- `ntdll!RtlFreeUnicodeString` at `0x18000e1e2`
- `ntdll!RtlFreeUnicodeString` at `0x18000e200`
- `ntdll!RtlFreeUnicodeString` at `0x18000e1e2`
- `ntdll!RtlFreeUnicodeString` at `0x18000e200`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e1cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e1ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e1cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e1ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e158`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e158`

## pseudocode

```c
BOOL __stdcall ConvertSidToStringSidW(PSID Sid, LPWSTR *StringSid)
{
  int v3; // ecx
  WCHAR *v4; // rax
  WCHAR *v5; // r8
  unsigned __int64 v6; // rdx
  PWSTR Buffer; // r9
  unsigned __int64 v8; // rax
  WCHAR *v9; // rcx
  DWORD v10; // eax
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-18h] BYREF

  UnicodeString = 0;
  if ( !Sid || !StringSid )
    goto LABEL_16;
  v3 = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u);
  if ( v3 < 0 )
    goto LABEL_14;
  v4 = (WCHAR *)LocalAlloc(0x40u, UnicodeString.Length + 2LL);
  *StringSid = v4;
  v5 = v4;
  if ( !v4 )
  {
    RtlFreeUnicodeString(&UnicodeString);
    v3 = -1073741801;
    goto LABEL_14;
  }
  v6 = ((unsigned __int64)UnicodeString.Length + 2) >> 1;
  if ( !v6 )
  {
LABEL_16:
    v3 = -1073741811;
    goto LABEL_14;
  }
  Buffer = UnicodeString.Buffer;
  v8 = (unsigned __int64)UnicodeString.Length >> 1;
  do
  {
    if ( !v8 )
      break;
    if ( !*Buffer )
      break;
    *v5++ = *Buffer++;
    --v8;
    --v6;
  }
  while ( v6 );
  v9 = v5 - 1;
  if ( v6 )
    v9 = v5;
  *v9 = 0;
  v3 = -2147483643;
  if ( v6 )
  {
    RtlFreeUnicodeString(&UnicodeString);
    SetLastError(0);
    return 1;
  }
LABEL_14:
  v10 = RtlNtStatusToDosError(v3);
  SetLastError(v10);
  return 0;
}

```

## disassembly

```asm
0x18000e110  push    rbx
0x18000e112  sub     rsp, 30h
0x18000e116  xorps   xmm0, xmm0
0x18000e119  mov     rbx, rdx
0x18000e11c  movups  xmmword ptr [rsp+38h+UnicodeString.Length], xmm0
0x18000e121  test    rcx, rcx
0x18000e124  jz      loc_18000E20D
0x18000e12a  test    rdx, rdx
0x18000e12d  jz      loc_18000E20D
0x18000e133  mov     rdx, rcx; Sid
0x18000e136  mov     r8b, 1; AllocateDestinationString
0x18000e139  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x18000e13e  call    cs:__imp_RtlConvertSidToUnicodeString
0x18000e144  mov     ecx, eax
0x18000e146  test    eax, eax
0x18000e148  js      short loc_18000E1C7
0x18000e14a  movzx   edx, [rsp+38h+UnicodeString.Length]
0x18000e14f  mov     ecx, 40h ; '@'; uFlags
0x18000e154  add     rdx, 2; uBytes
0x18000e158  call    cs:__imp_LocalAlloc
0x18000e15e  mov     [rbx], rax
0x18000e161  mov     r8, rax
0x18000e164  test    rax, rax
0x18000e167  jz      loc_18000E1FB
0x18000e16d  movzx   eax, [rsp+38h+UnicodeString.Length]
0x18000e172  lea     rdx, [rax+2]
0x18000e176  shr     rdx, 1
0x18000e179  jz      loc_18000E20D
0x18000e17f  mov     r9, [rsp+38h+UnicodeString.Buffer]
0x18000e184  shr     rax, 1
0x18000e187  test    rax, rax
0x18000e18a  jz      short loc_18000E1AA
0x18000e18c  movzx   ecx, word ptr [r9]
0x18000e190  test    cx, cx
0x18000e193  jz      short loc_18000E1AA
0x18000e195  mov     [r8], cx
0x18000e199  add     r9, 2
0x18000e19d  add     r8, 2
0x18000e1a1  dec     rax
0x18000e1a4  sub     rdx, 1
0x18000e1a8  jnz     short loc_18000E187
0x18000e1aa  test    rdx, rdx
0x18000e1ad  lea     rcx, [r8-2]
0x18000e1b1  cmovnz  rcx, r8
0x18000e1b5  xor     eax, eax
0x18000e1b7  test    rdx, rdx
0x18000e1ba  mov     [rcx], ax
0x18000e1bd  mov     ecx, 80000005h
0x18000e1c2  cmovnz  ecx, eax; Status
0x18000e1c5  jnz     short loc_18000E1DD
0x18000e1c7  call    cs:__imp_RtlNtStatusToDosError
0x18000e1cd  mov     ecx, eax; dwErrCode
0x18000e1cf  call    cs:__imp_SetLastError
0x18000e1d5  xor     eax, eax
0x18000e1d7  add     rsp, 30h
0x18000e1db  pop     rbx
0x18000e1dc  retn
0x18000e1dd  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x18000e1e2  call    cs:__imp_RtlFreeUnicodeString
0x18000e1e8  xor     ecx, ecx; dwErrCode
0x18000e1ea  call    cs:__imp_SetLastError
0x18000e1f0  mov     eax, 1
0x18000e1f5  add     rsp, 30h
0x18000e1f9  pop     rbx
0x18000e1fa  retn
0x18000e1fb  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x18000e200  call    cs:__imp_RtlFreeUnicodeString
0x18000e206  mov     ecx, 0C0000017h
0x18000e20b  jmp     short loc_18000E1C7
0x18000e20d  mov     ecx, 0C000000Dh
0x18000e212  jmp     short loc_18000E1C7
```

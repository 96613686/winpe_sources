# IsValidEndpointSecPath

- ea: `0x180035f90`
- end: `0x180036113`
- name: `IsValidEndpointSecPath`
- size: `387`
- prototype: `char __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800369a0`

## callees

- `0x1800159a0`
- `0x180021ec0`
- `0x180035c64`
- `0x180035f90`
- `0x180036654`
- `0x180036800`
- `0x180036904`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180036022`
- `ntdll!RtlInitUnicodeString` at `0x180036022`
- `ntdll!RtlGUIDFromString` at `0x1800360ae`
- `ntdll!RtlGUIDFromString` at `0x1800360ae`

## pseudocode

```c
char __fastcall IsValidEndpointSecPath(const wchar_t *a1)
{
  __int64 v1; // rax
  const WCHAR *v2; // rdx
  __int64 v3; // rax
  const wchar_t *v4; // rcx
  char v5; // di
  const wchar_t *v7; // [rsp+30h] [rbp-89h] BYREF
  __int64 v8; // [rsp+38h] [rbp-81h]
  _BYTE *v9; // [rsp+40h] [rbp-79h]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-71h] BYREF
  _QWORD v11[4]; // [rsp+58h] [rbp-61h] BYREF
  PCWSTR SourceString[4]; // [rsp+78h] [rbp-41h] BYREF
  _BYTE v13[32]; // [rsp+98h] [rbp-21h] BYREF
  GUID Guid; // [rsp+B8h] [rbp-1h] BYREF
  _BYTE v15[32]; // [rsp+C8h] [rbp+Fh] BYREF

  DestinationString = 0;
  Guid = 0;
  v9 = v13;
  v1 = -1;
  do
    ++v1;
  while ( a1[v1] );
  v7 = a1;
  v8 = v1;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v13, &v7);
  std::filesystem::path::stem(v13, SourceString);
  v2 = (const WCHAR *)SourceString;
  if ( SourceString[3] > (PCWSTR)7 )
    v2 = SourceString[0];
  RtlInitUnicodeString(&DestinationString, v2);
  v9 = v11;
  v7 = L".cip";
  v8 = 4;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v11, &v7);
  v3 = std::filesystem::path::extension(v13, v15);
  v4 = (const wchar_t *)v11;
  if ( v11[3] > 7u )
    v4 = (const wchar_t *)v11[0];
  v7 = v4;
  v8 = v11[2];
  if ( (unsigned int)std::filesystem::path::compare(v3, &v7)
    || (v5 = 1, RtlGUIDFromString(&DestinationString, &Guid) < 0) )
  {
    v5 = 0;
  }
  std::wstring::~wstring(v15);
  std::wstring::~wstring(v11);
  std::wstring::~wstring(SourceString);
  std::wstring::~wstring(v13);
  return v5;
}

```

## disassembly

```asm
0x180035f90  push    rbp
0x180035f92  push    rbx
0x180035f93  push    rsi
0x180035f94  push    rdi
0x180035f95  lea     rbp, [rsp-3Fh]
0x180035f9a  sub     rsp, 0F8h
0x180035fa1  mov     rax, cs:__security_cookie
0x180035fa8  xor     rax, rsp
0x180035fab  mov     [rbp+57h+var_28], rax
0x180035faf  xor     esi, esi
0x180035fb1  mov     [rsp+110h+var_F0], esi
0x180035fb5  xorps   xmm0, xmm0
0x180035fb8  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180035fbc  xorps   xmm1, xmm1
0x180035fbf  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm1
0x180035fc3  lea     rax, [rbp+57h+var_78]
0x180035fc7  mov     [rbp+57h+var_D0], rax
0x180035fcb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035fcf  inc     rax
0x180035fd2  cmp     [rcx+rax*2], si
0x180035fd6  jnz     short loc_180035FCF
0x180035fd8  mov     [rsp+110h+var_E0], rcx
0x180035fdd  mov     [rsp+110h+var_D8], rax
0x180035fe2  lea     rdx, [rsp+110h+var_E0]
0x180035fe7  lea     rcx, [rbp+57h+var_78]
0x180035feb  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x180035ff0  mov     edi, 4
0x180035ff5  mov     [rsp+110h+var_F0], edi
0x180035ff9  mov     ebx, edi
0x180035ffb  and     ebx, 0FFFFFFFBh
0x180035ffe  mov     [rsp+110h+var_F0], ebx
0x180036002  lea     rdx, [rbp+57h+SourceString]
0x180036006  lea     rcx, [rbp+57h+var_78]
0x18003600a  call    ?stem@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::stem(void)
0x18003600f  nop
0x180036010  lea     rdx, [rbp+57h+SourceString]
0x180036014  cmp     [rbp+57h+var_80], 7
0x180036019  cmova   rdx, [rbp+57h+SourceString]; SourceString
0x18003601e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180036022  call    cs:__imp_RtlInitUnicodeString
0x180036028  lea     rax, [rbp+57h+var_B8]
0x18003602c  mov     [rbp+57h+var_D0], rax
0x180036030  lea     rax, aCip; ".cip"
0x180036037  mov     [rsp+110h+var_E0], rax
0x18003603c  mov     [rsp+110h+var_D8], rdi
0x180036041  lea     rdx, [rsp+110h+var_E0]
0x180036046  lea     rcx, [rbp+57h+var_B8]
0x18003604a  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x18003604f  or      ebx, 10h
0x180036052  mov     [rsp+110h+var_F0], ebx
0x180036056  and     ebx, 0FFFFFFEFh
0x180036059  mov     [rsp+110h+var_F0], ebx
0x18003605d  or      ebx, 1
0x180036060  mov     [rsp+110h+var_F0], ebx
0x180036064  lea     rdx, [rbp+57h+var_48]
0x180036068  lea     rcx, [rbp+57h+var_78]
0x18003606c  call    ?extension@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::extension(void)
0x180036071  nop
0x180036072  or      ebx, 2
0x180036075  mov     [rsp+110h+var_F0], ebx
0x180036079  lea     rcx, [rbp+57h+var_B8]
0x18003607d  cmp     [rbp+57h+var_A0], 7
0x180036082  cmova   rcx, [rbp+57h+var_B8]
0x180036087  mov     [rsp+110h+var_E0], rcx
0x18003608c  mov     rcx, [rbp+57h+var_A8]
0x180036090  mov     [rsp+110h+var_D8], rcx
0x180036095  lea     rdx, [rsp+110h+var_E0]
0x18003609a  mov     rcx, rax
0x18003609d  call    ?compare@path@filesystem@std@@QEBAHV?$basic_string_view@GU?$char_traits@G@std@@@3@@Z; std::filesystem::path::compare(std::basic_string_view<ushort>)
0x1800360a2  test    eax, eax
0x1800360a4  jnz     short loc_1800360BB
0x1800360a6  lea     rdx, [rbp+57h+Guid]; Guid
0x1800360aa  lea     rcx, [rbp+57h+DestinationString]; GuidString
0x1800360ae  call    cs:__imp_RtlGUIDFromString
0x1800360b4  test    eax, eax
0x1800360b6  mov     dil, 1
0x1800360b9  jns     short loc_1800360BE
0x1800360bb  mov     dil, sil
0x1800360be  and     ebx, 0FFFFFFFDh
0x1800360c1  mov     [rsp+110h+var_F0], ebx
0x1800360c5  lea     rcx, [rbp+57h+var_48]
0x1800360c9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800360ce  nop
0x1800360cf  test    bl, 1
0x1800360d2  jz      short loc_1800360E5
0x1800360d4  and     ebx, 0FFFFFFFEh
0x1800360d7  mov     [rsp+110h+var_F0], ebx
0x1800360db  lea     rcx, [rbp+57h+var_B8]
0x1800360df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800360e4  nop
0x1800360e5  lea     rcx, [rbp+57h+SourceString]
0x1800360e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800360ee  nop
0x1800360ef  lea     rcx, [rbp+57h+var_78]
0x1800360f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800360f8  mov     al, dil
0x1800360fb  mov     rcx, [rbp+57h+var_28]
0x1800360ff  xor     rcx, rsp; StackCookie
0x180036102  call    __security_check_cookie
0x180036107  add     rsp, 0F8h
0x18003610e  pop     rdi
0x18003610f  pop     rsi
0x180036110  pop     rbx
0x180036111  pop     rbp
0x180036112  retn
```

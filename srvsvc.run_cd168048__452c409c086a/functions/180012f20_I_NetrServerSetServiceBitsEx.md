# I_NetrServerSetServiceBitsEx

- ea: `0x180012f20`
- end: `0x1800131d3`
- name: `I_NetrServerSetServiceBitsEx`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180022e90`

## callees

- `0x18000a460`
- `0x18000b1c0`
- `0x18000b5a0`
- `0x18000b940`
- `0x18000b9a0`
- `0x180012f20`
- `0x18001deb0`
- `0x1800435ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800130d4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800130d4`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001302b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001302b`
- `ntdll!RtlReleaseResource` at `0x18001311a`
- `ntdll!RtlReleaseResource` at `0x180013168`
- `ntdll!RtlReleaseResource` at `0x1800131a1`
- `ntdll!RtlReleaseResource` at `0x18001311a`
- `ntdll!RtlReleaseResource` at `0x180013168`
- `ntdll!RtlReleaseResource` at `0x1800131a1`
- `ntdll!RtlInitUnicodeString` at `0x180012fd9`
- `ntdll!RtlInitUnicodeString` at `0x180012fd9`

## string_xrefs

- `0x180012fa3`: `SRV Config Info`

## pseudocode

```c
__int64 __fastcall I_NetrServerSetServiceBitsEx(
        __int64 a1,
        const wchar_t *a2,
        const wchar_t *a3,
        int a4,
        int a5,
        unsigned int a6)
{
  size_t v7; // r9
  __int64 result; // rax
  unsigned int v11; // esi
  int *v12; // r15
  unsigned int v13; // ebx
  int v14; // ebp
  _DWORD *v15; // rdi
  unsigned int v16; // ebx
  int v17; // esi
  __int64 *i; // rdi
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-160h] BYREF
  _BYTE Buf1[272]; // [rsp+50h] [rbp-148h] BYREF

  v7 = 1024;
  if ( a2 && StringCchLengthW(a2, 0x400u, 0) || a3 && StringCchLengthW(a3, v7, 0) )
    return 87;
  if ( dword_18005CE2C && (unsigned int)SsCheckAccess((__int64)&SsConfigInfoSecurityObject, L"SRV Config Info", 0x10u) )
    return 5;
  if ( a2 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, a2);
    result = ConvertStringToTransportAddress(&DestinationString, Buf1);
    if ( (_DWORD)result )
      return result;
    v11 = 0;
    v12 = (int *)Buf1;
  }
  else
  {
    v11 = Size;
    v12 = &dword_18005CF14;
  }
  v13 = a4 & 0xFF7FEDFD;
  v14 = a5 & v13;
  RtlAcquireResourceExclusive(&Resource, 1u);
  v15 = hMem;
  if ( hMem )
  {
    do
    {
LABEL_17:
      if ( v15[67] == v11 && !memcmp_0(v12, v15 + 2, v11) )
        break;
      v15 = *(_DWORD **)v15;
    }
    while ( v15 );
    if ( v15 )
    {
      v17 = 0;
      if ( dword_18005D028 && (v15[71] & 1) != 0 )
      {
        v15[70] = dword_18005D028;
        dword_18005D028 = 0;
        v17 = 1;
      }
      if ( a3 )
      {
        for ( i = (__int64 *)*((_QWORD *)v15 + 37); ; i = (__int64 *)*i )
        {
          if ( !i )
          {
            v16 = 3;
            goto LABEL_39;
          }
          if ( !(unsigned int)_o__wcsicmp(a3, i[1]) )
            break;
        }
        if ( (v13 & (_DWORD)i[2]) != v14 )
        {
          v17 = 1;
          *((_DWORD *)i + 4) = v14 | i[2] & ~v13;
        }
      }
      else if ( (v13 & v15[70]) != v14 )
      {
        v17 = 1;
        v15[70] = v14 | v15[70] & ~v13;
LABEL_32:
        SsSetExportedServerType(0, 1, a6);
LABEL_33:
        RtlReleaseResource(&Resource);
        if ( !SsBrowserServiceIsRunning && v17 && (v14 & 0x10000) != 0 )
          SsBrowserServiceIsRunning = (unsigned int)SsServerFsControl(0x144070u, 0, 0, 0, 0) == 0;
        return 0;
      }
      if ( !v17 )
        goto LABEL_33;
      goto LABEL_32;
    }
LABEL_42:
    RtlReleaseResource(&Resource);
    return 2310;
  }
  if ( a3 )
  {
    if ( !hMem )
      goto LABEL_42;
    goto LABEL_17;
  }
  dword_18005D028 = v14 | dword_18005D028 & ~v13;
  v16 = 0;
LABEL_39:
  RtlReleaseResource(&Resource);
  return v16;
}

```

## disassembly

```asm
0x180012f20  mov     [rsp+arg_0], rbx
0x180012f25  push    rbp
0x180012f26  push    rsi
0x180012f27  push    rdi
0x180012f28  push    r14
0x180012f2a  push    r15
0x180012f2c  sub     rsp, 170h
0x180012f33  mov     rax, cs:__security_cookie
0x180012f3a  xor     rax, rsp
0x180012f3d  mov     [rsp+198h+var_38], rax
0x180012f45  mov     dword ptr [rsp+198h+Size], 0
0x180012f4d  mov     ebx, r9d
0x180012f50  mov     r9d, 400h
0x180012f56  mov     r14, r8
0x180012f59  mov     rdi, rdx
0x180012f5c  test    rdx, rdx
0x180012f5f  jz      short loc_180012F73
0x180012f61  xor     r8d, r8d; pcchLength
0x180012f64  mov     edx, r9d; cchMax
0x180012f67  mov     rcx, rdi; psz
0x180012f6a  call    StringCchLengthW
0x180012f6f  test    eax, eax
0x180012f71  jnz     short loc_180012F8A
0x180012f73  test    r14, r14
0x180012f76  jz      short loc_180012F94
0x180012f78  xor     r8d, r8d; pcchLength
0x180012f7b  mov     rdx, r9; cchMax
0x180012f7e  mov     rcx, r14; psz
0x180012f81  call    StringCchLengthW
0x180012f86  test    eax, eax
0x180012f88  jz      short loc_180012F94
0x180012f8a  mov     eax, 57h ; 'W'
0x180012f8f  jmp     loc_1800131AC
0x180012f94  cmp     cs:dword_18005CE2C, 0
0x180012f9b  jz      short loc_180012FC4
0x180012f9d  mov     r8d, 10h
0x180012fa3  lea     rdx, aSrvConfigInfo; "SRV Config Info"
0x180012faa  lea     rcx, SsConfigInfoSecurityObject
0x180012fb1  call    SsCheckAccess
0x180012fb6  test    eax, eax
0x180012fb8  jz      short loc_180012FC4
0x180012fba  mov     eax, 5
0x180012fbf  jmp     loc_1800131AC
0x180012fc4  test    rdi, rdi
0x180012fc7  jz      short loc_180013006
0x180012fc9  xorps   xmm0, xmm0
0x180012fcc  lea     rcx, [rsp+198h+DestinationString]; DestinationString
0x180012fd1  mov     rdx, rdi; SourceString
0x180012fd4  movups  xmmword ptr [rsp+198h+DestinationString.Length], xmm0
0x180012fd9  call    cs:__imp_RtlInitUnicodeString
0x180012fdf  lea     r8, [rsp+198h+Size]
0x180012fe4  lea     rdx, [rsp+198h+Buf1]; void *
0x180012fe9  lea     rcx, [rsp+198h+DestinationString]; SourceString
0x180012fee  call    ConvertStringToTransportAddress
0x180012ff3  test    eax, eax
0x180012ff5  jnz     loc_1800131AC
0x180012ffb  mov     esi, dword ptr [rsp+198h+Size]
0x180012fff  lea     r15, [rsp+198h+Buf1]
0x180013004  jmp     short loc_180013013
0x180013006  mov     esi, cs:Size
0x18001300c  lea     r15, dword_18005CF14
0x180013013  and     ebx, 0FF7FEDFDh
0x180013019  lea     rcx, Resource; Resource
0x180013020  mov     ebp, ebx
0x180013022  mov     dl, 1; Wait
0x180013024  and     ebp, [rsp+198h+arg_20]
0x18001302b  call    cs:__imp_RtlAcquireResourceExclusive
0x180013031  mov     rdi, cs:hMem
0x180013038  test    rdi, rdi
0x18001303b  jnz     short loc_180013062
0x18001303d  test    r14, r14
0x180013040  jnz     short loc_180013059
0x180013042  not     ebx
0x180013044  and     ebx, cs:dword_18005D028
0x18001304a  or      ebx, ebp
0x18001304c  mov     cs:dword_18005D028, ebx
0x180013052  xor     ebx, ebx
0x180013054  jmp     loc_180013161
0x180013059  test    rdi, rdi
0x18001305c  jz      loc_18001319A
0x180013062  cmp     [rdi+10Ch], esi
0x180013068  jnz     short loc_18001307D
0x18001306a  mov     r8d, esi; Size
0x18001306d  lea     rdx, [rdi+8]; Buf2
0x180013071  mov     rcx, r15; Buf1
0x180013074  call    memcmp_0
0x180013079  test    eax, eax
0x18001307b  jz      short loc_180013085
0x18001307d  mov     rdi, [rdi]
0x180013080  test    rdi, rdi
0x180013083  jnz     short loc_180013062
0x180013085  test    rdi, rdi
0x180013088  jz      loc_18001319A
0x18001308e  mov     eax, cs:dword_18005D028
0x180013094  xor     esi, esi
0x180013096  test    eax, eax
0x180013098  jz      short loc_1800130B4
0x18001309a  test    byte ptr [rdi+11Ch], 1
0x1800130a1  jz      short loc_1800130B4
0x1800130a3  mov     [rdi+118h], eax
0x1800130a9  mov     cs:dword_18005D028, esi
0x1800130af  mov     esi, 1
0x1800130b4  test    r14, r14
0x1800130b7  jz      loc_180013172
0x1800130bd  mov     rdi, [rdi+128h]
0x1800130c4  test    rdi, rdi
0x1800130c7  jz      loc_18001315C
0x1800130cd  mov     rdx, [rdi+8]
0x1800130d1  mov     rcx, r14
0x1800130d4  call    cs:__imp__o__wcsicmp
0x1800130da  test    eax, eax
0x1800130dc  jz      short loc_1800130E3
0x1800130de  mov     rdi, [rdi]
0x1800130e1  jmp     short loc_1800130C4
0x1800130e3  mov     eax, [rdi+10h]
0x1800130e6  and     eax, ebx
0x1800130e8  cmp     eax, ebp
0x1800130ea  jz      short loc_1800130FB
0x1800130ec  not     ebx
0x1800130ee  mov     esi, 1
0x1800130f3  and     ebx, [rdi+10h]
0x1800130f6  or      ebx, ebp
0x1800130f8  mov     [rdi+10h], ebx
0x1800130fb  test    esi, esi
0x1800130fd  jz      short loc_180013113
0x1800130ff  mov     r8d, [rsp+198h+arg_28]
0x180013107  mov     edx, 1
0x18001310c  xor     ecx, ecx
0x18001310e  call    SsSetExportedServerType
0x180013113  lea     rcx, Resource; Resource
0x18001311a  call    cs:__imp_RtlReleaseResource
0x180013120  cmp     cs:SsBrowserServiceIsRunning, 0
0x180013127  jnz     short loc_180013158
0x180013129  test    esi, esi
0x18001312b  jz      short loc_180013158
0x18001312d  bt      ebp, 10h
0x180013131  jnb     short loc_180013158
0x180013133  xor     r9d, r9d
0x180013136  mov     [rsp+198h+var_178], 0; int
0x18001313e  xor     r8d, r8d
0x180013141  xor     edx, edx
0x180013143  mov     ecx, 144070h; FsControlCode
0x180013148  call    SsServerFsControl
0x18001314d  test    eax, eax
0x18001314f  jnz     short loc_180013158
0x180013151  mov     cs:SsBrowserServiceIsRunning, 1
0x180013158  xor     eax, eax
0x18001315a  jmp     short loc_1800131AC
0x18001315c  mov     ebx, 3
0x180013161  lea     rcx, Resource; Resource
0x180013168  call    cs:__imp_RtlReleaseResource
0x18001316e  mov     eax, ebx
0x180013170  jmp     short loc_1800131AC
0x180013172  mov     ecx, [rdi+118h]
0x180013178  mov     eax, ecx
0x18001317a  and     eax, ebx
0x18001317c  cmp     eax, ebp
0x18001317e  jz      loc_1800130FB
0x180013184  not     ebx
0x180013186  mov     esi, 1
0x18001318b  and     ebx, ecx
0x18001318d  or      ebx, ebp
0x18001318f  mov     [rdi+118h], ebx
0x180013195  jmp     loc_1800130FF
0x18001319a  lea     rcx, Resource; Resource
0x1800131a1  call    cs:__imp_RtlReleaseResource
0x1800131a7  mov     eax, 906h
0x1800131ac  mov     rcx, [rsp+198h+var_38]
0x1800131b4  xor     rcx, rsp; StackCookie
0x1800131b7  call    __security_check_cookie
0x1800131bc  mov     rbx, [rsp+198h+arg_0]
0x1800131c4  add     rsp, 170h
0x1800131cb  pop     r15
0x1800131cd  pop     r14
0x1800131cf  pop     rdi
0x1800131d0  pop     rsi
0x1800131d1  pop     rbp
0x1800131d2  retn
```

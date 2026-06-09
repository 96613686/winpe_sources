# PluginsNtOpenKey(ulong,wchar_t const *,wchar_t *,void *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>> *)

- ea: `0x180005d24`
- end: `0x180005fb7`
- name: `?PluginsNtOpenKey@@YAJKPEB_WPEA_WPEAXPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@Z$0A@@tlx@@@tlx@@@Z`
- size: `659`
- prototype: `__int64 __fastcall(ACCESS_MASK DesiredAccess, PCWSTR SourceString, _WORD *, void *, PHANDLE KeyHandle)`
- caller_count: `9`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002234`
- `0x180002790`
- `0x1800028d0`
- `0x180002cc8`
- `0x1800034cc`
- `0x180003838`
- `0x180003e10`
- `0x18000401c`
- `0x180005158`

## callees

- `0x180001cd4`
- `0x180003b58`
- `0x180005d24`
- `0x180006128`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180005ef3`
- `ntdll!RtlInitUnicodeString` at `0x180005ef3`
- `ntdll!NtClose` at `0x180005d7a`
- `ntdll!NtClose` at `0x180005f45`
- `ntdll!NtClose` at `0x180005d7a`
- `ntdll!NtClose` at `0x180005f45`
- `ntdll!DbgPrintEx` at `0x180005ddf`
- `ntdll!DbgPrintEx` at `0x180005e94`
- `ntdll!DbgPrintEx` at `0x180005eb2`
- `ntdll!DbgPrintEx` at `0x180005f0e`
- `ntdll!DbgPrintEx` at `0x180005f72`
- `ntdll!DbgPrintEx` at `0x180005f9b`
- `ntdll!DbgPrintEx` at `0x180005ddf`
- `ntdll!DbgPrintEx` at `0x180005e94`
- `ntdll!DbgPrintEx` at `0x180005eb2`
- `ntdll!DbgPrintEx` at `0x180005f0e`
- `ntdll!DbgPrintEx` at `0x180005f72`
- `ntdll!DbgPrintEx` at `0x180005f9b`
- `ntdll!NtOpenKey` at `0x180005f55`
- `ntdll!NtOpenKey` at `0x180005f55`

## string_xrefs

- `0x180005f64`: `WERDIAG: Failed opening registry key. NTSTATUS: %08X\n`

## pseudocode

```c
__int64 __fastcall PluginsNtOpenKey(
        ACCESS_MASK DesiredAccess,
        PCWSTR SourceString,
        _WORD *a3,
        void *a4,
        PHANDLE KeyHandle)
{
  wchar_t *v5; // rbx
  PHANDLE v10; // rsi
  void *v11; // rcx
  _WORD *v12; // rax
  __int64 v13; // rdx
  unsigned int v14; // edi
  unsigned __int64 v15; // r10
  __int64 v16; // rcx
  PCWSTR v17; // rax
  __int64 v18; // rdx
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rdi
  wchar_t **unique_for; // rax
  int v22; // eax
  const WCHAR *v23; // rdx
  void *v24; // rcx
  NTSTATUS v25; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *v29; // [rsp+C8h] [rbp+50h] BYREF

  v5 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( SourceString )
  {
    v10 = KeyHandle;
    if ( KeyHandle )
    {
      v11 = *KeyHandle;
      *KeyHandle = 0;
      if ( v11 )
        NtClose(v11);
      if ( a3 )
      {
        v12 = a3;
        v13 = 0x7FFFFFFF;
        do
        {
          if ( !*v12 )
            break;
          ++v12;
          --v13;
        }
        while ( v13 );
        v14 = v13 == 0 ? 0xC000000D : 0;
        v15 = (0x7FFFFFFF - v13) & -(__int64)(v13 != 0);
        if ( !v13 )
          goto LABEL_10;
        v16 = 0x7FFFFFFF;
        v17 = SourceString;
        do
        {
          if ( !*v17 )
            break;
          ++v17;
          --v16;
        }
        while ( v16 );
        v14 = v16 == 0 ? 0xC000000D : 0;
        v18 = (0x7FFFFFFF - v16) & ((unsigned __int128)-(__int128)(unsigned __int64)v16 >> 64);
        if ( !v16 )
        {
LABEL_10:
          DbgPrintEx(0x96u, 0, "WERDIAG: Failed obtaining string length. NTSTATUS: %08X\n", v14);
          return v14;
        }
        v19 = v15 + v18;
        if ( v15 + v18 < v15 )
        {
          v14 = -1073741675;
          DbgPrintEx(0x96u, 0, "WERDIAG: RtlSizeTAdd failed. NTSTATUS: %08X\n", 3221225621LL);
        }
        else
        {
          v20 = v19 + 2;
          if ( v19 + 2 < v19 )
          {
            v14 = -1073741675;
            DbgPrintEx(0x96u, 0, "WERDIAG: RtlSizeTAdd operation failed. NTSTATUS: %08X\n", 3221225621LL);
          }
          else
          {
            unique_for = (wchar_t **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v29, v19 + 2);
            v5 = *unique_for;
            *unique_for = 0;
            if ( v29 )
              operator delete[](v29);
            if ( v5 )
            {
              v22 = RtlStringCchPrintfW(v5, v20, L"%s\\%s", a3, SourceString);
              v14 = v22;
              if ( v22 < 0 )
              {
                DbgPrintEx(0x96u, 0, "WERDIAG: Failed concatenating strings. NTSTATUS: %08X\n", v22);
LABEL_34:
                operator delete[](v5);
                return v14;
              }
              v23 = v5;
LABEL_28:
              RtlInitUnicodeString(&DestinationString, v23);
              DbgPrintEx(0x96u, 3u, "WERDIAG: Key: %S\n", DestinationString.Buffer);
              v24 = *v10;
              ObjectAttributes.Length = 48;
              ObjectAttributes.RootDirectory = a4;
              ObjectAttributes.Attributes = 64;
              ObjectAttributes.ObjectName = &DestinationString;
              *v10 = 0;
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
              if ( v24 )
                NtClose(v24);
              v25 = NtOpenKey(v10, DesiredAccess, &ObjectAttributes);
              v14 = v25;
              if ( v25 >= 0 )
                v14 = 0;
              else
                DbgPrintEx(0x96u, 0, "WERDIAG: Failed opening registry key. NTSTATUS: %08X\n", v25);
              if ( !v5 )
                return v14;
              goto LABEL_34;
            }
            DbgPrintEx(0x96u, 0, "WERDIAG: Insufficient resources\n");
            return (unsigned int)-1073741670;
          }
        }
        return v14;
      }
      v23 = SourceString;
      goto LABEL_28;
    }
  }
  DbgPrintEx(0x96u, 0, "WERDIAG: Invalid parameters\n");
  return 3221225485LL;
}

```

## disassembly

```asm
0x180005d24  push    rbp
0x180005d26  push    rbx
0x180005d27  push    rsi
0x180005d28  push    rdi
0x180005d29  push    r12
0x180005d2b  push    r13
0x180005d2d  push    r14
0x180005d2f  push    r15
0x180005d31  mov     rbp, rsp
0x180005d34  sub     rsp, 78h
0x180005d38  xorps   xmm0, xmm0
0x180005d3b  xor     ebx, ebx
0x180005d3d  mov     r13, r9
0x180005d40  mov     r15, r8
0x180005d43  mov     r14, rdx
0x180005d46  mov     r12d, ecx
0x180005d49  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180005d4d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180005d51  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180005d55  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180005d59  test    rdx, rdx
0x180005d5c  jz      loc_180005F8D
0x180005d62  mov     rsi, [rbp+KeyHandle]
0x180005d66  test    rsi, rsi
0x180005d69  jz      loc_180005F8D
0x180005d6f  mov     rcx, [rsi]; Handle
0x180005d72  mov     [rsi], rbx
0x180005d75  test    rcx, rcx
0x180005d78  jz      short loc_180005D80
0x180005d7a  call    cs:__imp_NtClose
0x180005d80  test    r15, r15
0x180005d83  jz      loc_180005EEC
0x180005d89  mov     r9d, 7FFFFFFFh
0x180005d8f  mov     rax, r15
0x180005d92  mov     edx, r9d
0x180005d95  cmp     [rax], bx
0x180005d98  jz      short loc_180005DA4
0x180005d9a  add     rax, 2
0x180005d9e  sub     rdx, 1
0x180005da2  jnz     short loc_180005D95
0x180005da4  mov     rax, rdx
0x180005da7  mov     r8d, 0C000000Dh
0x180005dad  neg     rax
0x180005db0  mov     rcx, r9
0x180005db3  mov     rax, rdx
0x180005db6  sbb     edi, edi
0x180005db8  sub     rcx, rdx
0x180005dbb  not     edi
0x180005dbd  and     edi, r8d
0x180005dc0  neg     rax
0x180005dc3  sbb     r10, r10
0x180005dc6  and     r10, rcx
0x180005dc9  test    rdx, rdx
0x180005dcc  jnz     short loc_180005DEA
0x180005dce  mov     r9d, edi
0x180005dd1  lea     r8, aWerdiagFailedO_0; "WERDIAG: Failed obtaining string length"...
0x180005dd8  xor     edx, edx; Level
0x180005dda  mov     ecx, 96h; ComponentId
0x180005ddf  call    cs:__imp_DbgPrintEx
0x180005de5  jmp     loc_180005F89
0x180005dea  mov     rcx, r9
0x180005ded  mov     rax, r14
0x180005df0  cmp     [rax], bx
0x180005df3  jz      short loc_180005DFF
0x180005df5  add     rax, 2
0x180005df9  sub     rcx, 1
0x180005dfd  jnz     short loc_180005DF0
0x180005dff  mov     rax, rcx
0x180005e02  neg     rax
0x180005e05  mov     rax, rcx
0x180005e08  sbb     edi, edi
0x180005e0a  sub     r9, rcx
0x180005e0d  not     edi
0x180005e0f  and     edi, r8d
0x180005e12  neg     rax
0x180005e15  sbb     rdx, rdx
0x180005e18  and     rdx, r9
0x180005e1b  test    rcx, rcx
0x180005e1e  jz      short loc_180005DCE
0x180005e20  lea     rax, [r10+rdx]
0x180005e24  cmp     rax, r10
0x180005e27  jb      loc_180005ED7
0x180005e2d  lea     rdi, [rax+2]
0x180005e31  cmp     rdi, rax
0x180005e34  jb      loc_180005EC2
0x180005e3a  mov     rdx, rdi
0x180005e3d  lea     rcx, [rbp+arg_8]
0x180005e41  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180005e46  mov     rbx, [rax]
0x180005e49  mov     qword ptr [rax], 0
0x180005e50  mov     rcx, [rbp+arg_8]; void *
0x180005e54  test    rcx, rcx
0x180005e57  jz      short loc_180005E5E
0x180005e59  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180005e5e  test    rbx, rbx
0x180005e61  jz      short loc_180005EA4
0x180005e63  mov     r9, r15
0x180005e66  mov     [rsp+78h+var_58], r14
0x180005e6b  lea     r8, aSS; "%s\\%s"
0x180005e72  mov     rdx, rdi; unsigned __int64
0x180005e75  mov     rcx, rbx; wchar_t *
0x180005e78  call    ?RtlStringCchPrintfW@@YAJPEA_W_KPEB_WZZ; RtlStringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180005e7d  mov     edi, eax
0x180005e7f  test    eax, eax
0x180005e81  jns     short loc_180005E9F
0x180005e83  mov     r9d, eax
0x180005e86  lea     r8, aWerdiagFailedC_5; "WERDIAG: Failed concatenating strings. "...
0x180005e8d  xor     edx, edx; Level
0x180005e8f  mov     ecx, 96h; ComponentId
0x180005e94  call    cs:__imp_DbgPrintEx
0x180005e9a  jmp     loc_180005F81
0x180005e9f  mov     rdx, rbx
0x180005ea2  jmp     short loc_180005EEF
0x180005ea4  lea     r8, aWerdiagInsuffi; "WERDIAG: Insufficient resources\n"
0x180005eab  xor     edx, edx; Level
0x180005ead  mov     ecx, 96h; ComponentId
0x180005eb2  call    cs:__imp_DbgPrintEx
0x180005eb8  mov     edi, 0C000009Ah
0x180005ebd  jmp     loc_180005F89
0x180005ec2  mov     r9d, 0C0000095h
0x180005ec8  lea     r8, aWerdiagRtlsize_0; "WERDIAG: RtlSizeTAdd operation failed. "...
0x180005ecf  mov     edi, r9d
0x180005ed2  jmp     loc_180005DD8
0x180005ed7  mov     r9d, 0C0000095h
0x180005edd  lea     r8, aWerdiagRtlsize; "WERDIAG: RtlSizeTAdd failed. NTSTATUS: "...
0x180005ee4  mov     edi, r9d
0x180005ee7  jmp     loc_180005DD8
0x180005eec  mov     rdx, r14; SourceString
0x180005eef  lea     rcx, [rbp+DestinationString]; DestinationString
0x180005ef3  call    cs:__imp_RtlInitUnicodeString
0x180005ef9  mov     r9, [rbp+DestinationString.Buffer]
0x180005efd  lea     r8, aWerdiagKeyS; "WERDIAG: Key: %S\n"
0x180005f04  mov     edx, 3; Level
0x180005f09  mov     ecx, 96h; ComponentId
0x180005f0e  call    cs:__imp_DbgPrintEx
0x180005f14  mov     rcx, [rsi]; Handle
0x180005f17  lea     rax, [rbp+DestinationString]
0x180005f1b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180005f22  xorps   xmm0, xmm0
0x180005f25  mov     [rbp+ObjectAttributes.RootDirectory], r13
0x180005f29  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180005f30  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180005f34  mov     qword ptr [rsi], 0
0x180005f3b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180005f40  test    rcx, rcx
0x180005f43  jz      short loc_180005F4B
0x180005f45  call    cs:__imp_NtClose
0x180005f4b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180005f4f  mov     edx, r12d; DesiredAccess
0x180005f52  mov     rcx, rsi; KeyHandle
0x180005f55  call    cs:__imp_NtOpenKey
0x180005f5b  mov     edi, eax
0x180005f5d  test    eax, eax
0x180005f5f  jns     short loc_180005F7A
0x180005f61  mov     r9d, eax
0x180005f64  lea     r8, aWerdiagFailedO_5; "WERDIAG: Failed opening registry key. N"...
0x180005f6b  xor     edx, edx; Level
0x180005f6d  mov     ecx, 96h; ComponentId
0x180005f72  call    cs:__imp_DbgPrintEx
0x180005f78  jmp     short loc_180005F7C
0x180005f7a  xor     edi, edi
0x180005f7c  test    rbx, rbx
0x180005f7f  jz      short loc_180005F89
0x180005f81  mov     rcx, rbx; void *
0x180005f84  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180005f89  mov     eax, edi
0x180005f8b  jmp     short loc_180005FA6
0x180005f8d  lea     r8, aWerdiagInvalid_3; "WERDIAG: Invalid parameters\n"
0x180005f94  xor     edx, edx; Level
0x180005f96  mov     ecx, 96h; ComponentId
0x180005f9b  call    cs:__imp_DbgPrintEx
0x180005fa1  mov     eax, 0C000000Dh
0x180005fa6  add     rsp, 78h
0x180005faa  pop     r15
0x180005fac  pop     r14
0x180005fae  pop     r13
0x180005fb0  pop     r12
0x180005fb2  pop     rdi
0x180005fb3  pop     rsi
0x180005fb4  pop     rbx
0x180005fb5  pop     rbp
0x180005fb6  retn
```

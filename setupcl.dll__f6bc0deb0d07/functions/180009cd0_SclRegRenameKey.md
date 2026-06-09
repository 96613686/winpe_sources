# SclRegRenameKey

- ea: `0x180009cd0`
- end: `0x18000a184`
- name: `SclRegRenameKey`
- size: `1204`
- prototype: `__int64 __fastcall(void *, wchar_t *, wchar_t *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x1800025ec`
- `0x1800088bc`
- `0x180008e40`
- `0x180009864`
- `0x180009cd0`
- `0x18000a75c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180009f88`
- `ntdll!RtlInitUnicodeString` at `0x18000a000`
- `ntdll!RtlInitUnicodeString` at `0x18000a063`
- `ntdll!RtlInitUnicodeString` at `0x18000a0e1`
- `ntdll!RtlInitUnicodeString` at `0x18000a11d`
- `ntdll!RtlInitUnicodeString` at `0x180009f88`
- `ntdll!RtlInitUnicodeString` at `0x18000a000`
- `ntdll!RtlInitUnicodeString` at `0x18000a063`
- `ntdll!RtlInitUnicodeString` at `0x18000a0e1`
- `ntdll!RtlInitUnicodeString` at `0x18000a11d`
- `ntdll!NtClose` at `0x180009ef7`
- `ntdll!NtClose` at `0x180009f13`
- `ntdll!NtClose` at `0x180009fe2`
- `ntdll!NtClose` at `0x18000a0a3`
- `ntdll!NtClose` at `0x18000a164`
- `ntdll!NtClose` at `0x180009ef7`
- `ntdll!NtClose` at `0x180009f13`
- `ntdll!NtClose` at `0x180009fe2`
- `ntdll!NtClose` at `0x18000a0a3`
- `ntdll!NtClose` at `0x18000a164`
- `ntdll!RtlFreeHeap` at `0x180009f34`
- `ntdll!RtlFreeHeap` at `0x180009f55`
- `ntdll!RtlFreeHeap` at `0x180009f34`
- `ntdll!RtlFreeHeap` at `0x180009f55`
- `ntdll!_wcsicmp` at `0x180009e83`
- `ntdll!_wcsicmp` at `0x180009f94`
- `ntdll!_wcsicmp` at `0x18000a0c1`
- `ntdll!_wcsicmp` at `0x180009e83`
- `ntdll!_wcsicmp` at `0x180009f94`
- `ntdll!_wcsicmp` at `0x18000a0c1`
- `ntdll!wcschr` at `0x180009d01`
- `ntdll!wcschr` at `0x180009d79`
- `ntdll!wcschr` at `0x180009d91`
- `ntdll!wcschr` at `0x180009da1`
- `ntdll!wcschr` at `0x180009dc9`
- `ntdll!wcschr` at `0x180009ddb`
- `ntdll!wcschr` at `0x180009ebb`
- `ntdll!wcschr` at `0x180009ed5`
- `ntdll!wcschr` at `0x180009d01`
- `ntdll!wcschr` at `0x180009d79`
- `ntdll!wcschr` at `0x180009d91`
- `ntdll!wcschr` at `0x180009da1`
- `ntdll!wcschr` at `0x180009dc9`
- `ntdll!wcschr` at `0x180009ddb`
- `ntdll!wcschr` at `0x180009ebb`
- `ntdll!wcschr` at `0x180009ed5`
- `ntdll!NtRenameKey` at `0x18000a00e`
- `ntdll!NtRenameKey` at `0x18000a12b`
- `ntdll!NtRenameKey` at `0x18000a00e`
- `ntdll!NtRenameKey` at `0x18000a12b`

## pseudocode

```c
__int64 __fastcall SclRegRenameKey(void *a1, wchar_t *a2, wchar_t *a3)
{
  wchar_t *v6; // r15
  __int64 v7; // rsi
  __int64 v8; // rdx
  int v9; // eax
  wchar_t *v10; // r12
  int v11; // ebx
  wchar_t *v12; // rax
  const wchar_t *i; // rcx
  wchar_t *v14; // rsi
  wchar_t *v15; // rax
  wchar_t *v16; // rdi
  wchar_t *v17; // r13
  wchar_t *v18; // r14
  HANDLE v19; // rdi
  wchar_t *v20; // rsi
  const WCHAR *v21; // rsi
  bool v22; // r15
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25; // eax
  void *v26; // rcx
  NTSTATUS v27; // eax
  int v28; // eax
  void *v29; // rcx
  NTSTATUS v30; // eax
  int v31; // eax
  bool v33; // [rsp+30h] [rbp-40h] BYREF
  char v34; // [rsp+31h] [rbp-3Fh]
  HANDLE Handle; // [rsp+38h] [rbp-38h] BYREF
  PVOID P; // [rsp+40h] [rbp-30h] BYREF
  wchar_t *Str; // [rsp+48h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-20h] BYREF
  struct _UNICODE_STRING NewName; // [rsp+60h] [rbp-10h] BYREF
  HANDLE KeyHandle; // [rsp+C8h] [rbp+58h] BYREF

  v6 = 0;
  if ( !wcschr(a2, 0x5Cu) )
  {
    v11 = 0;
    if ( !_wcsicmp(a2, a3) )
      return (unsigned int)v11;
    KeyHandle = 0;
    NewName = 0;
    RtlInitUnicodeString(&NewName, a2);
    KeyHandle = 0;
    v30 = SclOpenKey(a1, &NewName, 0x20006u, 0, &KeyHandle);
    v11 = v30;
    if ( v30 < 0 )
    {
      if ( v30 != -1073741790 || (v11 = SclRegCopyKeyRecursiveByName(a1, a3, a2), v11 < 0) )
      {
LABEL_82:
        if ( KeyHandle )
          NtClose(KeyHandle);
        return (unsigned int)v11;
      }
      v31 = SclRegDeleteKeyRecursive((__int64)a1, a2);
    }
    else
    {
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, a3);
      v31 = NtRenameKey(KeyHandle, &DestinationString);
    }
    v11 = v31;
    goto LABEL_82;
  }
  v7 = -1;
  Str = 0;
  v8 = -1;
  P = 0;
  do
    ++v8;
  while ( a2[v8] );
  v9 = SclCloneString(a2, v8, &Str, 0);
  v10 = Str;
  v11 = v9;
  if ( v9 < 0 )
    goto LABEL_50;
  do
    ++v7;
  while ( a3[v7] );
  v11 = SclCloneString(a3, v7, &P, 0);
  if ( v11 < 0 )
    goto LABEL_48;
  v12 = wcschr(v10, 0x5Cu);
  for ( i = (const wchar_t *)P; ; i = v16 + 1 )
  {
    v14 = v12;
    v15 = wcschr(i, 0x5Cu);
    v16 = v15;
    if ( !v14 )
      break;
    if ( !v15 )
      goto LABEL_12;
    v12 = wcschr(v14 + 1, 0x5Cu);
  }
  if ( v15 )
  {
LABEL_12:
    v11 = -1073741811;
    goto LABEL_48;
  }
  v34 = 0;
  v17 = wcschr(v10, 0x5Cu);
  v18 = wcschr((const wchar_t *)P, 0x5Cu);
  v19 = 0;
  v20 = 0;
  while ( !v34 )
  {
    if ( v20 )
      v10 = v20 + 1;
    v21 = v6 + 1;
    if ( !v6 )
      v21 = (const WCHAR *)P;
    if ( v17 )
      *v17 = 0;
    if ( v18 )
      *v18 = 0;
    Handle = 0;
    v22 = 0;
    LOBYTE(KeyHandle) = 0;
    v33 = 0;
    v23 = (__int64)a1;
    if ( v19 )
      v23 = (__int64)v19;
    v11 = SclRegKeyExists(v23, v10, (bool *)&KeyHandle);
    if ( v11 >= 0 )
    {
      v24 = (__int64)a1;
      if ( v19 )
        v24 = (__int64)v19;
      v25 = SclRegKeyExists(v24, v21, &v33);
      v22 = v33;
      v11 = v25;
    }
    if ( (_BYTE)KeyHandle )
    {
      if ( v22 && _wcsicmp(v10, v21) )
      {
LABEL_33:
        v11 = -1073739508;
        goto LABEL_34;
      }
    }
    else if ( !v22 )
    {
      goto LABEL_33;
    }
    if ( v11 >= 0 )
    {
      if ( (_BYTE)KeyHandle )
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, v10);
        LODWORD(KeyHandle) = _wcsicmp(v10, v21);
        v26 = a1;
        if ( v19 )
          v26 = v19;
        v27 = SclOpenKey(v26, &DestinationString, (_DWORD)KeyHandle != 0 ? 131078 : 131097, 0, &Handle);
        v11 = v27;
        if ( v27 < 0 )
        {
          if ( v27 == -1073741790 )
          {
            if ( !(_DWORD)KeyHandle )
              goto LABEL_34;
            v11 = SclRegCopyKeyRecursiveByName(a1, v21, v10);
            if ( v11 < 0 )
              goto LABEL_34;
            v28 = SclRegDeleteKeyRecursive((__int64)a1, v10);
LABEL_66:
            v11 = v28;
          }
        }
        else
        {
          if ( v19 )
            NtClose(v19);
          v19 = 0;
          if ( (_DWORD)KeyHandle )
          {
            NewName = 0;
            RtlInitUnicodeString(&NewName, v21);
            v28 = NtRenameKey(Handle, &NewName);
            goto LABEL_66;
          }
        }
        if ( v11 < 0 )
          goto LABEL_34;
      }
      else
      {
        NewName = 0;
        RtlInitUnicodeString(&NewName, v21);
        v29 = a1;
        if ( v19 )
          v29 = v19;
        v11 = SclOpenKey(v29, &NewName, 0x1020019u, 0, &Handle);
        if ( v11 < 0 )
          goto LABEL_34;
        if ( v19 )
          NtClose(v19);
      }
      v19 = Handle;
      Handle = 0;
    }
LABEL_34:
    if ( v18 )
      *v18 = 92;
    v20 = v17;
    if ( v17 )
    {
      *v17 = 92;
      v17 = wcschr(v17 + 1, 0x5Cu);
    }
    v6 = v18;
    if ( v18 )
      v18 = wcschr(v18 + 1, 0x5Cu);
    if ( !v20 || !v6 )
      v34 = 1;
    if ( Handle )
      NtClose(Handle);
    v10 = Str;
    if ( v11 < 0 )
      break;
  }
  if ( v19 )
    NtClose(v19);
LABEL_48:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
LABEL_50:
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180009cd0  mov     [rsp-38h+arg_8], rbx
0x180009cd5  mov     [rsp-38h+arg_0], rcx
0x180009cda  push    rbp
0x180009cdb  push    rsi
0x180009cdc  push    rdi
0x180009cdd  push    r12
0x180009cdf  push    r13
0x180009ce1  push    r14
0x180009ce3  push    r15
0x180009ce5  mov     rbp, rsp
0x180009ce8  sub     rsp, 70h
0x180009cec  mov     rdi, rdx
0x180009cef  mov     rsi, rcx
0x180009cf2  mov     r13d, 5Ch ; '\'
0x180009cf8  mov     rcx, rdi; Str
0x180009cfb  mov     edx, r13d; Ch
0x180009cfe  mov     r14, r8
0x180009d01  call    cs:__imp_wcschr
0x180009d07  xor     r15d, r15d
0x180009d0a  test    rax, rax
0x180009d0d  jz      loc_18000A0B8
0x180009d13  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009d17  mov     [rbp+Str], r15
0x180009d1b  mov     rdx, rsi
0x180009d1e  mov     [rbp+P], r15
0x180009d22  inc     rdx
0x180009d25  cmp     [rdi+rdx*2], r15w
0x180009d2a  jnz     short loc_180009D22
0x180009d2c  xor     r9d, r9d
0x180009d2f  lea     r8, [rbp+Str]
0x180009d33  mov     rcx, rdi
0x180009d36  call    SclCloneString
0x180009d3b  mov     r12, [rbp+Str]
0x180009d3f  xor     edx, edx
0x180009d41  mov     ebx, eax
0x180009d43  test    eax, eax
0x180009d45  js      loc_180009F3A
0x180009d4b  inc     rsi
0x180009d4e  cmp     [r14+rsi*2], dx
0x180009d53  jnz     short loc_180009D4B
0x180009d55  xor     r9d, r9d
0x180009d58  lea     r8, [rbp+P]
0x180009d5c  mov     rdx, rsi
0x180009d5f  mov     rcx, r14
0x180009d62  call    SclCloneString
0x180009d67  xor     edx, edx
0x180009d69  mov     ebx, eax
0x180009d6b  test    eax, eax
0x180009d6d  js      loc_180009F1B
0x180009d73  mov     edx, r13d; Ch
0x180009d76  mov     rcx, r12; Str
0x180009d79  call    cs:__imp_wcschr
0x180009d7f  mov     rcx, [rbp+P]
0x180009d83  jmp     short loc_180009D9B
0x180009d85  test    rdi, rdi
0x180009d88  jz      short loc_180009DB6
0x180009d8a  mov     edx, r13d; Ch
0x180009d8d  lea     rcx, [rsi+2]; Str
0x180009d91  call    cs:__imp_wcschr
0x180009d97  lea     rcx, [rdi+2]; Str
0x180009d9b  mov     edx, r13d; Ch
0x180009d9e  mov     rsi, rax
0x180009da1  call    cs:__imp_wcschr
0x180009da7  xor     edx, edx
0x180009da9  mov     rdi, rax
0x180009dac  test    rsi, rsi
0x180009daf  jnz     short loc_180009D85
0x180009db1  test    rax, rax
0x180009db4  jz      short loc_180009DC0
0x180009db6  mov     ebx, 0C000000Dh
0x180009dbb  jmp     loc_180009F1B
0x180009dc0  mov     [rbp+var_3F], dl
0x180009dc3  mov     rcx, r12; Str
0x180009dc6  mov     edx, r13d; Ch
0x180009dc9  call    cs:__imp_wcschr
0x180009dcf  mov     rcx, [rbp+P]; Str
0x180009dd3  mov     edx, 5Ch ; '\'; Ch
0x180009dd8  mov     r13, rax
0x180009ddb  call    cs:__imp_wcschr
0x180009de1  xor     edx, edx
0x180009de3  mov     r14, rax
0x180009de6  mov     edi, edx
0x180009de8  mov     esi, edx
0x180009dea  cmp     [rbp+var_3F], dl
0x180009ded  jnz     loc_180009F0B
0x180009df3  test    rsi, rsi
0x180009df6  jz      short loc_180009DFC
0x180009df8  lea     r12, [rsi+2]
0x180009dfc  lea     rsi, [r15+2]
0x180009e00  test    r15, r15
0x180009e03  jnz     short loc_180009E09
0x180009e05  mov     rsi, [rbp+P]
0x180009e09  test    r13, r13
0x180009e0c  jz      short loc_180009E13
0x180009e0e  mov     [r13+0], dx
0x180009e13  test    r14, r14
0x180009e16  jz      short loc_180009E1C
0x180009e18  mov     [r14], dx
0x180009e1c  mov     [rbp+Handle], rdx
0x180009e20  mov     r15b, dl
0x180009e23  mov     byte ptr [rbp+KeyHandle], dl
0x180009e26  mov     [rbp+var_40], dl
0x180009e29  test    ebx, ebx
0x180009e2b  js      short loc_180009E93
0x180009e2d  mov     rcx, [rbp+arg_0]
0x180009e31  lea     r8, [rbp+KeyHandle]
0x180009e35  test    rdi, rdi
0x180009e38  mov     rdx, r12
0x180009e3b  cmovnz  rcx, rdi
0x180009e3f  call    SclRegKeyExists
0x180009e44  xor     edx, edx
0x180009e46  mov     ebx, eax
0x180009e48  test    eax, eax
0x180009e4a  js      short loc_180009E6B
0x180009e4c  mov     rcx, [rbp+arg_0]
0x180009e50  lea     r8, [rbp+var_40]
0x180009e54  test    rdi, rdi
0x180009e57  mov     rdx, rsi
0x180009e5a  cmovnz  rcx, rdi
0x180009e5e  call    SclRegKeyExists
0x180009e63  mov     r15b, [rbp+var_40]
0x180009e67  mov     ebx, eax
0x180009e69  xor     edx, edx
0x180009e6b  cmp     byte ptr [rbp+KeyHandle], dl
0x180009e6e  jz      loc_180009F60
0x180009e74  test    r15b, r15b
0x180009e77  jz      loc_180009F69
0x180009e7d  mov     rdx, rsi; String2
0x180009e80  mov     rcx, r12; String1
0x180009e83  call    cs:__imp__wcsicmp
0x180009e89  xor     edx, edx
0x180009e8b  test    eax, eax
0x180009e8d  jz      loc_180009F69
0x180009e93  mov     ebx, 0C000090Ch
0x180009e98  mov     r12d, 5Ch ; '\'
0x180009e9e  test    r14, r14
0x180009ea1  jz      short loc_180009EA7
0x180009ea3  mov     [r14], r12w
0x180009ea7  mov     rsi, r13
0x180009eaa  test    r13, r13
0x180009ead  jz      short loc_180009EC6
0x180009eaf  mov     edx, r12d; Ch
0x180009eb2  mov     [r13+0], r12w
0x180009eb7  lea     rcx, [r13+2]; Str
0x180009ebb  call    cs:__imp_wcschr
0x180009ec1  mov     r13, rax
0x180009ec4  xor     edx, edx
0x180009ec6  mov     r15, r14
0x180009ec9  test    r14, r14
0x180009ecc  jz      short loc_180009EE0
0x180009ece  mov     edx, r12d; Ch
0x180009ed1  lea     rcx, [r14+2]; Str
0x180009ed5  call    cs:__imp_wcschr
0x180009edb  mov     r14, rax
0x180009ede  xor     edx, edx
0x180009ee0  test    rsi, rsi
0x180009ee3  jz      short loc_180009EEA
0x180009ee5  test    r15, r15
0x180009ee8  jnz     short loc_180009EEE
0x180009eea  mov     [rbp+var_3F], 1
0x180009eee  mov     rcx, [rbp+Handle]; Handle
0x180009ef2  test    rcx, rcx
0x180009ef5  jz      short loc_180009EFF
0x180009ef7  call    cs:__imp_NtClose
0x180009efd  xor     edx, edx
0x180009eff  mov     r12, [rbp+Str]
0x180009f03  test    ebx, ebx
0x180009f05  jns     loc_180009DEA
0x180009f0b  test    rdi, rdi
0x180009f0e  jz      short loc_180009F1B
0x180009f10  mov     rcx, rdi; Handle
0x180009f13  call    cs:__imp_NtClose
0x180009f19  xor     edx, edx
0x180009f1b  cmp     [rbp+P], rdx
0x180009f1f  jz      short loc_180009F3A
0x180009f21  mov     rcx, gs:60h
0x180009f2a  xor     edx, edx; Flags
0x180009f2c  mov     r8, [rbp+P]; P
0x180009f30  mov     rcx, [rcx+30h]; HeapHandle
0x180009f34  call    cs:__imp_RtlFreeHeap
0x180009f3a  test    r12, r12
0x180009f3d  jz      loc_18000A16A
0x180009f43  mov     rcx, gs:60h
0x180009f4c  mov     r8, r12; P
0x180009f4f  xor     edx, edx; Flags
0x180009f51  mov     rcx, [rcx+30h]; HeapHandle
0x180009f55  call    cs:__imp_RtlFreeHeap
0x180009f5b  jmp     loc_18000A16A
0x180009f60  test    r15b, r15b
0x180009f63  jz      loc_180009E93
0x180009f69  test    ebx, ebx
0x180009f6b  js      loc_180009E98
0x180009f71  xorps   xmm0, xmm0
0x180009f74  cmp     byte ptr [rbp+KeyHandle], dl
0x180009f77  jz      loc_18000A058
0x180009f7d  mov     rdx, r12; SourceString
0x180009f80  lea     rcx, [rbp+DestinationString]; DestinationString
0x180009f84  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180009f88  call    cs:__imp_RtlInitUnicodeString
0x180009f8e  mov     rdx, rsi; String2
0x180009f91  mov     rcx, r12; String1
0x180009f94  call    cs:__imp__wcsicmp
0x180009f9a  mov     r15, [rbp+arg_0]
0x180009f9e  lea     rdx, [rbp+DestinationString]
0x180009fa2  mov     ecx, eax
0x180009fa4  mov     dword ptr [rbp+KeyHandle], eax
0x180009fa7  neg     ecx
0x180009fa9  lea     rax, [rbp+Handle]
0x180009fad  mov     rcx, r15
0x180009fb0  mov     [rsp+70h+var_50], rax
0x180009fb5  sbb     r8d, r8d
0x180009fb8  and     r8d, 0FFFFFFEDh
0x180009fbc  add     r8d, 20019h
0x180009fc3  test    rdi, rdi
0x180009fc6  cmovnz  rcx, rdi
0x180009fca  xor     r9d, r9d
0x180009fcd  call    SclOpenKey
0x180009fd2  xor     edx, edx
0x180009fd4  mov     ebx, eax
0x180009fd6  test    eax, eax
0x180009fd8  js      short loc_18000A016
0x180009fda  test    rdi, rdi
0x180009fdd  jz      short loc_180009FEA
0x180009fdf  mov     rcx, rdi; Handle
0x180009fe2  call    cs:__imp_NtClose
0x180009fe8  xor     edx, edx
0x180009fea  mov     rdi, rdx
0x180009fed  cmp     dword ptr [rbp+KeyHandle], edx
0x180009ff0  jz      short loc_18000A04F
0x180009ff2  xorps   xmm0, xmm0
0x180009ff5  lea     rcx, [rbp+NewName]; DestinationString
0x180009ff9  mov     rdx, rsi; SourceString
0x180009ffc  movups  xmmword ptr [rbp+NewName.Length], xmm0
0x18000a000  call    cs:__imp_RtlInitUnicodeString
0x18000a006  mov     rcx, [rbp+Handle]; KeyHandle
0x18000a00a  lea     rdx, [rbp+NewName]; NewName
0x18000a00e  call    cs:__imp_NtRenameKey
0x18000a014  jmp     short loc_18000A04B
0x18000a016  cmp     eax, 0C0000022h
0x18000a01b  jnz     short loc_18000A04F
0x18000a01d  cmp     dword ptr [rbp+KeyHandle], edx
0x18000a020  jz      loc_180009E98
0x18000a026  mov     r8, r12
0x18000a029  mov     rdx, rsi
0x18000a02c  mov     rcx, r15
0x18000a02f  call    SclRegCopyKeyRecursiveByName
0x18000a034  xor     edx, edx
0x18000a036  mov     ebx, eax
0x18000a038  test    eax, eax
0x18000a03a  js      loc_180009E98
0x18000a040  mov     rdx, r12
0x18000a043  mov     rcx, r15
0x18000a046  call    SclRegDeleteKeyRecursive
0x18000a04b  xor     edx, edx
0x18000a04d  mov     ebx, eax
0x18000a04f  test    ebx, ebx
0x18000a051  jns     short loc_18000A0AB
0x18000a053  jmp     loc_180009E98
0x18000a058  mov     rdx, rsi; SourceString
0x18000a05b  lea     rcx, [rbp+NewName]; DestinationString
0x18000a05f  movups  xmmword ptr [rbp+NewName.Length], xmm0
0x18000a063  call    cs:__imp_RtlInitUnicodeString
0x18000a069  mov     rcx, [rbp+arg_0]
0x18000a06d  lea     rax, [rbp+Handle]
0x18000a071  test    rdi, rdi
0x18000a074  mov     [rsp+70h+var_50], rax
0x18000a079  mov     r8d, 1020019h
0x18000a07f  lea     rdx, [rbp+NewName]
0x18000a083  cmovnz  rcx, rdi
0x18000a087  xor     r9d, r9d
0x18000a08a  call    SclOpenKey
0x18000a08f  xor     edx, edx
0x18000a091  mov     ebx, eax
0x18000a093  test    eax, eax
0x18000a095  js      loc_180009E98
0x18000a09b  test    rdi, rdi
0x18000a09e  jz      short loc_18000A0AB
0x18000a0a0  mov     rcx, rdi; Handle
0x18000a0a3  call    cs:__imp_NtClose
0x18000a0a9  xor     edx, edx
0x18000a0ab  mov     rdi, [rbp+Handle]
0x18000a0af  mov     [rbp+Handle], rdx
0x18000a0b3  jmp     loc_180009E98
0x18000a0b8  mov     rdx, r14; String2
0x18000a0bb  mov     rcx, rdi; String1
0x18000a0be  mov     ebx, r15d
0x18000a0c1  call    cs:__imp__wcsicmp
0x18000a0c7  test    eax, eax
0x18000a0c9  jz      loc_18000A16A
0x18000a0cf  xorps   xmm0, xmm0
0x18000a0d2  mov     [rbp+KeyHandle], r15
0x18000a0d6  mov     rdx, rdi; SourceString
0x18000a0d9  lea     rcx, [rbp+NewName]; DestinationString
0x18000a0dd  movups  xmmword ptr [rbp+NewName.Length], xmm0
0x18000a0e1  call    cs:__imp_RtlInitUnicodeString
0x18000a0e7  lea     rax, [rbp+KeyHandle]
0x18000a0eb  mov     [rbp+KeyHandle], r15
0x18000a0ef  xor     r9d, r9d
0x18000a0f2  mov     [rsp+70h+var_50], rax
0x18000a0f7  mov     r8d, 20006h
  ... truncated ...
```

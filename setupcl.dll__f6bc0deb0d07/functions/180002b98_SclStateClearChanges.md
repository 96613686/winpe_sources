# SclStateClearChanges

- ea: `0x180002b98`
- end: `0x180002cc2`
- name: `SclStateClearChanges`
- size: `298`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update`

## callers

- `0x180005a90`
- `0x180005da0`

## callees

- `0x180002b98`
- `0x180007ac4`
- `0x180007b30`
- `0x18000de94`
- `0x18000e4e4`
- `0x18000e66c`
- `0x1800153c8`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180002c81`
- `ntdll!RtlFreeHeap` at `0x180002c99`
- `ntdll!RtlFreeHeap` at `0x180002c81`
- `ntdll!RtlFreeHeap` at `0x180002c99`

## string_xrefs

- `0x180002c1d`: `System32\config`

## pseudocode

```c
__int64 __fastcall SclStateClearChanges(__int64 a1, __int64 a2)
{
  __int64 v2; // r10
  int v3; // ebx
  const wchar_t *v4; // rdx
  wchar_t *v5; // rax
  wchar_t *v6; // rsi
  PVOID P[2]; // [rsp+20h] [rbp-238h] BYREF
  _BYTE v9[528]; // [rsp+30h] [rbp-228h] BYREF

  P[0] = 0;
  if ( !SclOSIsValid(a2) )
    return (unsigned int)-1073741811;
  if ( !v2 || *(_DWORD *)v2 == 1 )
  {
    v3 = SclExpandString(L"%SYSTEMROOT%", v9);
    if ( v3 < 0 )
      return (unsigned int)v3;
    v4 = (const wchar_t *)v9;
  }
  else
  {
    if ( *(_DWORD *)v2 != 2 )
      return (unsigned int)-1073741811;
    v4 = *(const wchar_t **)(v2 + 8);
  }
  v5 = BuildPathMulti(3u, v4, L"System32\\config", L"SETUPCL", P[0]);
  v6 = v5;
  if ( v5 )
  {
    v3 = SclDosPathToNtPath((__int64)v5, P);
    if ( v3 >= 0 && SclFileObjectExists((const WCHAR *)P[0]) )
      v3 = SclDeleteFileObject((const WCHAR *)P[0]);
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180002b98  mov     [rsp+arg_0], rbx
0x180002b9d  push    rsi
0x180002b9e  sub     rsp, 250h
0x180002ba5  mov     rax, cs:__security_cookie
0x180002bac  xor     rax, rsp
0x180002baf  mov     [rsp+258h+var_18], rax
0x180002bb7  mov     rcx, rdx
0x180002bba  mov     [rsp+258h+P], 0
0x180002bc3  mov     r10, rdx
0x180002bc6  call    SclOSIsValid
0x180002bcb  test    al, al
0x180002bcd  jnz     short loc_180002BD9
0x180002bcf  mov     ebx, 0C000000Dh
0x180002bd4  jmp     loc_180002C9F
0x180002bd9  test    r10, r10
0x180002bdc  jz      short loc_180002BF1
0x180002bde  mov     ecx, [r10]
0x180002be1  sub     ecx, 1
0x180002be4  jz      short loc_180002BF1
0x180002be6  cmp     ecx, 1
0x180002be9  jnz     short loc_180002BCF
0x180002beb  mov     rdx, [r10+8]
0x180002bef  jmp     short loc_180002C11
0x180002bf1  lea     rdx, [rsp+258h+var_228]; void *
0x180002bf6  lea     rcx, aSystemroot_0; "%SYSTEMROOT%"
0x180002bfd  call    SclExpandString
0x180002c02  mov     ebx, eax
0x180002c04  test    eax, eax
0x180002c06  js      loc_180002C9F
0x180002c0c  lea     rdx, [rsp+258h+var_228]
0x180002c11  lea     r9, aSetupcl; "SETUPCL"
0x180002c18  mov     ecx, 3
0x180002c1d  lea     r8, aSystem32Config; "System32\\config"
0x180002c24  call    BuildPathMulti
0x180002c29  mov     rsi, rax
0x180002c2c  test    rax, rax
0x180002c2f  jnz     short loc_180002C38
0x180002c31  mov     ebx, 0C0000017h
0x180002c36  jmp     short loc_180002C9F
0x180002c38  lea     rdx, [rsp+258h+P]
0x180002c3d  mov     rcx, rsi
0x180002c40  call    SclDosPathToNtPath
0x180002c45  mov     ebx, eax
0x180002c47  test    eax, eax
0x180002c49  js      short loc_180002C65
0x180002c4b  mov     rcx, [rsp+258h+P]
0x180002c50  call    SclFileObjectExists
0x180002c55  test    al, al
0x180002c57  jz      short loc_180002C65
0x180002c59  mov     rcx, [rsp+258h+P]
0x180002c5e  call    SclDeleteFileObject
0x180002c63  mov     ebx, eax
0x180002c65  cmp     [rsp+258h+P], 0
0x180002c6b  jz      short loc_180002C87
0x180002c6d  mov     rcx, gs:60h
0x180002c76  xor     edx, edx; Flags
0x180002c78  mov     r8, [rsp+258h+P]; P
0x180002c7d  mov     rcx, [rcx+30h]; HeapHandle
0x180002c81  call    cs:__imp_RtlFreeHeap
0x180002c87  mov     rcx, gs:60h
0x180002c90  mov     r8, rsi; P
0x180002c93  xor     edx, edx; Flags
0x180002c95  mov     rcx, [rcx+30h]; HeapHandle
0x180002c99  call    cs:__imp_RtlFreeHeap
0x180002c9f  mov     eax, ebx
0x180002ca1  mov     rcx, [rsp+258h+var_18]
0x180002ca9  xor     rcx, rsp; StackCookie
0x180002cac  call    __security_check_cookie
0x180002cb1  mov     rbx, [rsp+258h+arg_0]
0x180002cb9  add     rsp, 250h
0x180002cc0  pop     rsi
0x180002cc1  retn
```

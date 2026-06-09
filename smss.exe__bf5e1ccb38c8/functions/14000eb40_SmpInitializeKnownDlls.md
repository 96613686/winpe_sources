# SmpInitializeKnownDlls

- ea: `0x14000eb40`
- end: `0x14000ed1a`
- name: `SmpInitializeKnownDlls`
- size: `474`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x14000c638`
- `0x140014f30`

## callees

- `0x140003114`
- `0x140008470`
- `0x140008d10`
- `0x14000d494`
- `0x14000eb40`
- `0x140015660`

## import_xrefs

- `ntdll!NtClose` at `0x14000ec74`
- `ntdll!NtClose` at `0x14000ec82`
- `ntdll!NtClose` at `0x14000ec9e`
- `ntdll!NtClose` at `0x14000ecb0`
- `ntdll!NtClose` at `0x14000ec74`
- `ntdll!NtClose` at `0x14000ec82`
- `ntdll!NtClose` at `0x14000ec9e`
- `ntdll!NtClose` at `0x14000ecb0`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x14000eb95`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x14000eb95`

## string_xrefs

- `0x14000eb53`: `\KnownDlls32`
- `0x14000ebd2`: `SmpInitializeKnownDlls`
- `0x14000ec32`: `SmpInitializeKnownDlls`

## pseudocode

```c
__int64 __fastcall SmpInitializeKnownDlls(int a1)
{
  HANDLE v2; // rsi
  HANDLE v3; // r14
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // r15d
  int v7; // eax
  int v8; // edx
  __int64 *v9; // rdi
  __int64 *v10; // rcx
  __int64 *v11; // rdi
  __int64 *v12; // rcx
  UNICODE_STRING v14; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING v15; // [rsp+40h] [rbp-10h] BYREF
  char v16; // [rsp+80h] [rbp+30h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+38h] BYREF
  HANDLE v18; // [rsp+90h] [rbp+40h] BYREF

  v15.Buffer = L"\\KnownDlls32";
  *(_QWORD *)&v15.Length = 1703960;
  v2 = 0;
  v14.Buffer = L"\\SysWOW64";
  v3 = 0;
  v18 = 0;
  Handle = 0;
  *(_QWORD *)&v14.Length = 1310738;
  v16 = 0;
  if ( (int)RtlWow64IsWowGuestMachineSupported(332, &v16) < 0 || !v16 )
    goto LABEL_7;
  v4 = SmpOpenKnownDllsHandles(&v15, &v14, 0, &v18, &Handle);
  v5 = v4;
  if ( v4 < 0 )
  {
    SmLogFailureInt((unsigned int)"SmpInitializeKnownDlls", 4538, a1, 0, v4);
    goto LABEL_19;
  }
  v2 = v18;
  v3 = Handle;
  if ( v18 )
    v6 = 1;
  else
LABEL_7:
    v6 = 0;
  v7 = SmpInitializeKnownDllsInternal((__int64)SmpKnownDllsObjectDirectory, SmpKnownDllsFileDirectory, 0, v6, a1);
  v5 = v7;
  if ( v7 >= 0 )
  {
    if ( !v2 || (v7 = SmpInitializeKnownDllsInternal((__int64)v2, v3, 1, v6, a1), v5 = v7, v7 >= 0) )
    {
      v5 = 0;
      goto LABEL_15;
    }
    v8 = 4627;
  }
  else
  {
    v8 = 4581;
  }
  SmLogFailureInt((unsigned int)"SmpInitializeKnownDlls", v8, a1, 0, v7);
LABEL_15:
  if ( v3 )
    NtClose(v3);
  if ( v2 )
    NtClose(v2);
LABEL_19:
  if ( (a1 & 3) != 1 )
  {
    if ( SmpKnownDllsFileDirectory )
      NtClose(SmpKnownDllsFileDirectory);
    if ( SmpKnownDllsObjectDirectory )
      NtClose(SmpKnownDllsObjectDirectory);
    v9 = (__int64 *)SmpKnownDllsList;
    while ( v9 != &SmpKnownDllsList )
    {
      v10 = v9;
      v9 = (__int64 *)*v9;
      SmpFreeSavedRegistryEntry(v10);
    }
    v11 = (__int64 *)SmpExcludeKnownDllsList;
    while ( v11 != &SmpExcludeKnownDllsList )
    {
      v12 = v11;
      v11 = (__int64 *)*v11;
      SmpFreeSavedRegistryEntry(v12);
    }
    SmpEventWriteULONG(&SmssEvt_InitializeKnownDlls_Stop, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x14000eb40  mov     [rsp-28h+arg_18], rbx
0x14000eb45  push    rbp
0x14000eb46  push    rsi
0x14000eb47  push    rdi
0x14000eb48  push    r14
0x14000eb4a  push    r15
0x14000eb4c  mov     rbp, rsp
0x14000eb4f  sub     rsp, 50h
0x14000eb53  lea     rax, aKnowndlls32; "\\KnownDlls32"
0x14000eb5a  mov     edi, ecx
0x14000eb5c  mov     [rbp+var_8], rax
0x14000eb60  lea     rdx, [rbp+arg_0]
0x14000eb64  lea     rax, aSyswow64; "\\SysWOW64"
0x14000eb6b  mov     [rbp+var_10], 1A0018h
0x14000eb73  xor     esi, esi
0x14000eb75  mov     [rbp+var_18], rax
0x14000eb79  xor     r14d, r14d
0x14000eb7c  mov     [rbp+arg_10], rsi
0x14000eb80  mov     ecx, 14Ch
0x14000eb85  mov     [rbp+Handle], r14
0x14000eb89  mov     [rbp+var_20], 140012h
0x14000eb91  mov     [rbp+arg_0], sil
0x14000eb95  call    cs:__imp_RtlWow64IsWowGuestMachineSupported
0x14000eb9b  test    eax, eax
0x14000eb9d  js      short loc_14000EBFD
0x14000eb9f  cmp     [rbp+arg_0], sil
0x14000eba3  jz      short loc_14000EBFD
0x14000eba5  lea     rax, [rbp+Handle]
0x14000eba9  xor     r8d, r8d
0x14000ebac  lea     r9, [rbp+arg_10]
0x14000ebb0  mov     [rsp+50h+var_30], rax
0x14000ebb5  lea     rdx, [rbp+var_20]
0x14000ebb9  lea     rcx, [rbp+var_10]
0x14000ebbd  call    SmpOpenKnownDllsHandles
0x14000ebc2  mov     ebx, eax
0x14000ebc4  test    eax, eax
0x14000ebc6  jns     short loc_14000EBE8
0x14000ebc8  mov     r8d, edi
0x14000ebcb  mov     dword ptr [rsp+50h+var_30], eax
0x14000ebcf  xor     r9d, r9d
0x14000ebd2  lea     rcx, aSmpinitializek_0; "SmpInitializeKnownDlls"
0x14000ebd9  mov     edx, 11BAh
0x14000ebde  call    SmLogFailureInt
0x14000ebe3  jmp     loc_14000EC88
0x14000ebe8  mov     rsi, [rbp+arg_10]
0x14000ebec  mov     r14, [rbp+Handle]
0x14000ebf0  test    rsi, rsi
0x14000ebf3  jz      short loc_14000EBFD
0x14000ebf5  mov     r15d, 1
0x14000ebfb  jmp     short loc_14000EC00
0x14000ebfd  xor     r15d, r15d
0x14000ec00  mov     rdx, cs:SmpKnownDllsFileDirectory
0x14000ec07  mov     r9d, r15d
0x14000ec0a  mov     rcx, cs:SmpKnownDllsObjectDirectory
0x14000ec11  xor     r8d, r8d
0x14000ec14  mov     dword ptr [rsp+50h+var_30], edi
0x14000ec18  call    SmpInitializeKnownDllsInternal
0x14000ec1d  mov     ebx, eax
0x14000ec1f  test    eax, eax
0x14000ec21  jns     short loc_14000EC40
0x14000ec23  mov     edx, 11E5h
0x14000ec28  xor     r9d, r9d
0x14000ec2b  mov     dword ptr [rsp+50h+var_30], eax
0x14000ec2f  mov     r8, rdi
0x14000ec32  lea     rcx, aSmpinitializek_0; "SmpInitializeKnownDlls"
0x14000ec39  call    SmLogFailureInt
0x14000ec3e  jmp     short loc_14000EC6C
0x14000ec40  test    rsi, rsi
0x14000ec43  jz      short loc_14000EC6A
0x14000ec45  mov     r9d, r15d
0x14000ec48  mov     dword ptr [rsp+50h+var_30], edi
0x14000ec4c  mov     r8d, 1
0x14000ec52  mov     rdx, r14
0x14000ec55  mov     rcx, rsi
0x14000ec58  call    SmpInitializeKnownDllsInternal
0x14000ec5d  mov     ebx, eax
0x14000ec5f  test    eax, eax
0x14000ec61  jns     short loc_14000EC6A
0x14000ec63  mov     edx, 1213h
0x14000ec68  jmp     short loc_14000EC28
0x14000ec6a  xor     ebx, ebx
0x14000ec6c  test    r14, r14
0x14000ec6f  jz      short loc_14000EC7A
0x14000ec71  mov     rcx, r14; Handle
0x14000ec74  call    cs:__imp_NtClose
0x14000ec7a  test    rsi, rsi
0x14000ec7d  jz      short loc_14000EC88
0x14000ec7f  mov     rcx, rsi; Handle
0x14000ec82  call    cs:__imp_NtClose
0x14000ec88  and     dil, 3
0x14000ec8c  cmp     dil, 1
0x14000ec90  jz      short loc_14000ED04
0x14000ec92  mov     rcx, cs:SmpKnownDllsFileDirectory; Handle
0x14000ec99  test    rcx, rcx
0x14000ec9c  jz      short loc_14000ECA4
0x14000ec9e  call    cs:__imp_NtClose
0x14000eca4  mov     rcx, cs:SmpKnownDllsObjectDirectory; Handle
0x14000ecab  test    rcx, rcx
0x14000ecae  jz      short loc_14000ECB6
0x14000ecb0  call    cs:__imp_NtClose
0x14000ecb6  mov     rdi, cs:SmpKnownDllsList
0x14000ecbd  lea     rsi, SmpKnownDllsList
0x14000ecc4  jmp     short loc_14000ECD1
0x14000ecc6  mov     rcx, rdi
0x14000ecc9  mov     rdi, [rdi]
0x14000eccc  call    SmpFreeSavedRegistryEntry
0x14000ecd1  cmp     rdi, rsi
0x14000ecd4  jnz     short loc_14000ECC6
0x14000ecd6  mov     rdi, cs:SmpExcludeKnownDllsList
0x14000ecdd  lea     rsi, SmpExcludeKnownDllsList
0x14000ece4  jmp     short loc_14000ECF1
0x14000ece6  mov     rcx, rdi
0x14000ece9  mov     rdi, [rdi]
0x14000ecec  call    SmpFreeSavedRegistryEntry
0x14000ecf1  cmp     rdi, rsi
0x14000ecf4  jnz     short loc_14000ECE6
0x14000ecf6  mov     edx, ebx
0x14000ecf8  lea     rcx, SmssEvt_InitializeKnownDlls_Stop; EventDescriptor
0x14000ecff  call    SmpEventWriteULONG
0x14000ed04  mov     eax, ebx
0x14000ed06  mov     rbx, [rsp+50h+arg_18]
0x14000ed0e  add     rsp, 50h
0x14000ed12  pop     r15
0x14000ed14  pop     r14
0x14000ed16  pop     rdi
0x14000ed17  pop     rsi
0x14000ed18  pop     rbp
0x14000ed19  retn
```

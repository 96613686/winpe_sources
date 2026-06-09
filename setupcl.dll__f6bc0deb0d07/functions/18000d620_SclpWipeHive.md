# SclpWipeHive

- ea: `0x18000d620`
- end: `0x18000dad9`
- name: `SclpWipeHive`
- size: `1209`
- prototype: `__int64 __fastcall(__int64, __int64, wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18000b90c`

## callees

- `0x180001c74`
- `0x180001d48`
- `0x180008e40`
- `0x1800091c0`
- `0x18000923c`
- `0x18000a524`
- `0x18000d620`
- `0x1800179c5`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000d6aa`
- `ntdll!RtlAllocateHeap` at `0x18000d6d7`
- `ntdll!RtlAllocateHeap` at `0x18000d6aa`
- `ntdll!RtlAllocateHeap` at `0x18000d6d7`
- `ntdll!NtClose` at `0x18000da6d`
- `ntdll!NtClose` at `0x18000da6d`
- `ntdll!RtlFreeHeap` at `0x18000da8a`
- `ntdll!RtlFreeHeap` at `0x18000daa7`
- `ntdll!RtlFreeHeap` at `0x18000da8a`
- `ntdll!RtlFreeHeap` at `0x18000daa7`
- `ntdll!NtOpenKey` at `0x18000d771`
- `ntdll!NtOpenKey` at `0x18000d771`
- `ntdll!NtFlushKey` at `0x18000da05`
- `ntdll!NtFlushKey` at `0x18000da05`
- `ntdll!NtDeleteValueKey` at `0x18000d953`
- `ntdll!NtDeleteValueKey` at `0x18000d953`
- `ntdll!_wcsicmp` at `0x18000d856`
- `ntdll!_wcsicmp` at `0x18000d856`

## string_xrefs

- `0x18000d6f4`: `\REGISTRY\MACHINE`
- `0x18000d79c`: `(%lx): Error opening hive key [%ws]`
- `0x18000d995`: `(%lx): Failed to delete value [%wZ]`

## pseudocode

```c
__int64 __fastcall SclpWipeHive(__int64 a1, __int64 a2, wchar_t *a3)
{
  unsigned int v4; // r12d
  USHORT *v6; // rsi
  wchar_t *v7; // rdi
  unsigned int v8; // r13d
  NTSTATUS v9; // ebx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // r15d
  int v14; // r8d
  int v15; // eax
  int v16; // edx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  NTSTATUS v21; // eax
  __int64 v22; // rcx
  __int64 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *Heap; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v28; // [rsp+58h] [rbp-A8h] BYREF
  int v29; // [rsp+5Ch] [rbp-A4h] BYREF
  USHORT *v30; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *String1; // [rsp+78h] [rbp-88h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING v34; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  wchar_t v36[264]; // [rsp+D0h] [rbp-30h] BYREF

  KeyHandle = 0;
  v34 = 0;
  v4 = 2064;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  String1 = a3;
  v33 = a2;
  LODWORD(v25) = 0;
  v28 = 2064;
  ValueName = 0;
  v6 = 0;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x810u);
  v7 = Heap;
  if ( !Heap
    || (v29 = 2064, v8 = 2064, v30 = (USHORT *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x810u), (v6 = v30) == 0) )
  {
    v9 = -1073741801;
    goto LABEL_41;
  }
  v10 = RtlStringCchPrintfW(v36, 0x104u, L"%ws\\%ws", L"\\REGISTRY\\MACHINE", a2);
  v9 = v10;
  if ( v10 < 0 )
  {
    v11 = a1 + 1152;
    if ( !a1 )
      v11 = 0;
    SclLogGenericMessage(
      v11,
      3,
      (int)SclEvent_Generic_Error,
      2260,
      (__int64)"SclpWipeHive",
      "(%lx): Failed to calculate full key for the new hive [%ws]",
      v10,
      a2,
      v25);
    goto LABEL_41;
  }
  INIT_OBJA_EX((__int64)&ObjectAttributes, &v34, v36, 64, 0);
  v9 = NtOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
  if ( v9 < 0 )
  {
    v12 = a1 + 1152;
    if ( !a1 )
      v12 = 0;
    SclLogGenericMessage(
      v12,
      3,
      (int)SclEvent_Generic_Error,
      2274,
      (__int64)"SclpWipeHive",
      "(%lx): Error opening hive key [%ws]",
      v9,
      v36,
      v25);
    goto LABEL_41;
  }
  v13 = 0;
  while ( 1 )
  {
    memset_0(v7, 0, v4);
    v15 = SclRegEnumerateKey((_DWORD)KeyHandle, v13, v14, (unsigned int)&Heap, (__int64)&v28, 2, (__int64)&v25);
    v9 = v15;
    if ( v15 == -2147483622 )
      break;
    if ( v15 < 0 )
    {
      v17 = a1 + 1152;
      if ( !a1 )
        v17 = 0;
      SclLogGenericMessage(
        v17,
        3,
        (int)SclEvent_Generic_Error,
        2306,
        (__int64)"SclpWipeHive",
        "SclRegEnumerateKey failed [0x%08X]",
        v15);
      goto LABEL_40;
    }
    v7 = Heap;
    v4 = v28;
    v16 = *((_DWORD *)Heap + 3);
    if ( (unsigned __int64)(unsigned int)(v16 + 16) + 2 > v28 )
    {
      v9 = -2147483643;
      goto LABEL_41;
    }
    *(wchar_t *)((char *)Heap + (v16 & 0xFFFFFFFE) + 16) = 0;
    if ( !String1 || _wcsicmp(String1, v7 + 8) )
    {
      v13 = 0;
      v9 = SclRegDeleteKeyRecursive(KeyHandle, v7 + 8);
      if ( v9 < 0 )
        goto LABEL_41;
    }
    else
    {
      ++v13;
    }
  }
  while ( 1 )
  {
    LODWORD(v25) = 0;
    memset_0(v6, 0, v8);
    v18 = SclRegEnumerateValueKey((_DWORD)KeyHandle, 0, 0, (unsigned int)&v30, (__int64)&v29, (__int64)&v25);
    v9 = v18;
    if ( v18 == -2147483622 )
    {
      v21 = NtFlushKey(KeyHandle);
      v22 = a1 + 1152;
      v9 = v21;
      if ( !a1 )
        v22 = 0;
      SclLogGenericMessage(
        v22,
        1,
        (int)SclEvent_Generic_Info,
        2394,
        (__int64)"SclpWipeHive",
        "Flushed changes after wiping hive content for [%ws] Status:0x%x",
        v33,
        v21);
      goto LABEL_39;
    }
    if ( v18 < 0 )
    {
      v20 = a1 + 1152;
      if ( !a1 )
        v20 = 0;
      SclLogGenericMessage(
        v20,
        3,
        (int)SclEvent_Generic_Error,
        2367,
        (__int64)"SclpWipeHive",
        "SclRegEnumerateValueKey failed [0x%08X]",
        v18);
LABEL_39:
      v6 = v30;
      goto LABEL_40;
    }
    v6 = v30;
    ValueName.Buffer = v30 + 6;
    ValueName.Length = v30[4];
    ValueName.MaximumLength = v30[4];
    v9 = NtDeleteValueKey(KeyHandle, &ValueName);
    if ( v9 < 0 )
      break;
    v8 = v29;
  }
  v19 = a1 + 1152;
  if ( !a1 )
    v19 = 0;
  LODWORD(v24) = v9;
  SclLogGenericMessage(
    v19,
    3,
    (int)SclEvent_Generic_Error,
    2382,
    (__int64)"SclpWipeHive",
    "(%lx): Failed to delete value [%wZ]",
    v24,
    &ValueName);
LABEL_40:
  v7 = Heap;
LABEL_41:
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( v7 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000d620  mov     [rsp-8+arg_18], rbx
0x18000d625  push    rbp
0x18000d626  push    rsi
0x18000d627  push    rdi
0x18000d628  push    r12
0x18000d62a  push    r13
0x18000d62c  push    r14
0x18000d62e  push    r15
0x18000d630  lea     rbp, [rsp-1F0h]
0x18000d638  sub     rsp, 2F0h
0x18000d63f  mov     rax, cs:__security_cookie
0x18000d646  xor     rax, rsp
0x18000d649  mov     [rbp+220h+var_40], rax
0x18000d650  xorps   xmm0, xmm0
0x18000d653  mov     [rsp+320h+KeyHandle], 0
0x18000d65c  movups  [rbp+220h+var_298], xmm0
0x18000d660  mov     r14, rcx
0x18000d663  mov     r12d, 810h
0x18000d669  movups  xmmword ptr [rbp+220h+ObjectAttributes.Length], xmm0
0x18000d66d  mov     [rsp+320h+String1], r8
0x18000d672  mov     r15, rdx
0x18000d675  movups  xmmword ptr [rbp+220h+ObjectAttributes.ObjectName], xmm0
0x18000d679  mov     [rbp+220h+var_2A0], rdx
0x18000d67d  mov     r8d, r12d; Size
0x18000d680  movups  xmmword ptr [rbp+220h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d684  mov     dword ptr [rsp+320h+var_2E0], 0
0x18000d68c  xor     edx, edx; Flags
0x18000d68e  xorps   xmm1, xmm1
0x18000d691  mov     [rsp+320h+var_2C8], r12d
0x18000d696  movups  xmmword ptr [rsp+320h+ValueName.Length], xmm1
0x18000d69b  mov     rcx, gs:60h
0x18000d6a4  xor     esi, esi
0x18000d6a6  mov     rcx, [rcx+30h]; HeapHandle
0x18000d6aa  call    cs:__imp_RtlAllocateHeap
0x18000d6b0  mov     [rsp+320h+var_2D0], rax
0x18000d6b5  mov     rdi, rax
0x18000d6b8  test    rax, rax
0x18000d6bb  jz      short loc_18000D6EA
0x18000d6bd  mov     rcx, gs:60h
0x18000d6c6  mov     r8d, r12d; Size
0x18000d6c9  xor     edx, edx; Flags
0x18000d6cb  mov     [rsp+320h+var_2C4], r12d
0x18000d6d0  mov     r13d, r12d
0x18000d6d3  mov     rcx, [rcx+30h]; HeapHandle
0x18000d6d7  call    cs:__imp_RtlAllocateHeap
0x18000d6dd  mov     [rsp+320h+var_2C0], rax
0x18000d6e2  mov     rsi, rax
0x18000d6e5  test    rax, rax
0x18000d6e8  jnz     short loc_18000D6F4
0x18000d6ea  mov     ebx, 0C0000017h
0x18000d6ef  jmp     loc_18000DA63
0x18000d6f4  lea     r9, aRegistryMachin_1; "\\REGISTRY\\MACHINE"
0x18000d6fb  mov     [rsp+320h+var_300], r15
0x18000d700  lea     r8, aWsWs_0; "%ws\\%ws"
0x18000d707  mov     edx, 104h
0x18000d70c  lea     rcx, [rbp+220h+var_250]
0x18000d710  call    RtlStringCchPrintfW
0x18000d715  mov     ebx, eax
0x18000d717  test    eax, eax
0x18000d719  jns     short loc_18000D743
0x18000d71b  xor     edx, edx
0x18000d71d  mov     [rsp+320h+var_2E8], r15
0x18000d722  test    r14, r14
0x18000d725  mov     dword ptr [rsp+320h+var_2F0], eax
0x18000d729  lea     rcx, [r14+480h]
0x18000d730  mov     r9d, 8D4h
0x18000d736  cmovz   rcx, rdx
0x18000d73a  lea     rax, aLxFailedToCalc_0; "(%lx): Failed to calculate full key for"...
0x18000d741  jmp     short loc_18000D7A7
0x18000d743  mov     r9d, 40h ; '@'
0x18000d749  mov     [rsp+320h+var_300], 0
0x18000d752  lea     r8, [rbp+220h+var_250]
0x18000d756  lea     rdx, [rbp+220h+var_298]
0x18000d75a  lea     rcx, [rbp+220h+ObjectAttributes]
0x18000d75e  call    INIT_OBJA_EX
0x18000d763  lea     r8, [rbp+220h+ObjectAttributes]; ObjectAttributes
0x18000d767  mov     edx, 0F003Fh; DesiredAccess
0x18000d76c  lea     rcx, [rsp+320h+KeyHandle]; KeyHandle
0x18000d771  call    cs:__imp_NtOpenKey
0x18000d777  mov     ebx, eax
0x18000d779  test    eax, eax
0x18000d77b  jns     short loc_18000D7CE
0x18000d77d  xor     eax, eax
0x18000d77f  lea     rcx, [r14+480h]
0x18000d786  test    r14, r14
0x18000d789  mov     r9d, 8E2h
0x18000d78f  cmovz   rcx, rax
0x18000d793  lea     rax, [rbp+220h+var_250]
0x18000d797  mov     [rsp+320h+var_2E8], rax
0x18000d79c  lea     rax, aLxErrorOpening_2; "(%lx): Error opening hive key [%ws]"
0x18000d7a3  mov     dword ptr [rsp+320h+var_2F0], ebx
0x18000d7a7  mov     [rsp+320h+var_2F8], rax
0x18000d7ac  lea     r8, SclEvent_Generic_Error
0x18000d7b3  lea     rax, aSclpwipehive; "SclpWipeHive"
0x18000d7ba  mov     edx, 3
0x18000d7bf  mov     [rsp+320h+var_300], rax
0x18000d7c4  call    SclLogGenericMessage
0x18000d7c9  jmp     loc_18000DA63
0x18000d7ce  xor     r15d, r15d
0x18000d7d1  mov     r8d, r12d; Size
0x18000d7d4  xor     edx, edx; Val
0x18000d7d6  mov     rcx, rdi; void *
0x18000d7d9  call    memset_0
0x18000d7de  mov     rcx, [rsp+320h+KeyHandle]
0x18000d7e3  lea     rax, [rsp+320h+var_2E0]
0x18000d7e8  mov     [rsp+320h+var_2F0], rax
0x18000d7ed  lea     r9, [rsp+320h+var_2D0]
0x18000d7f2  lea     rax, [rsp+320h+var_2C8]
0x18000d7f7  mov     dword ptr [rsp+320h+var_2F8], 2
0x18000d7ff  mov     edx, r15d
0x18000d802  mov     [rsp+320h+var_300], rax
0x18000d807  call    SclRegEnumerateKey
0x18000d80c  mov     edi, 8000001Ah
0x18000d811  mov     ebx, eax
0x18000d813  cmp     eax, edi
0x18000d815  jz      loc_18000D8DA
0x18000d81b  test    eax, eax
0x18000d81d  js      short loc_18000D892
0x18000d81f  mov     rdi, [rsp+320h+var_2D0]
0x18000d824  mov     r12d, [rsp+320h+var_2C8]
0x18000d829  mov     edx, [rdi+0Ch]
0x18000d82c  lea     ecx, [rdx+10h]
0x18000d82f  add     rcx, 2
0x18000d833  cmp     rcx, r12
0x18000d836  ja      short loc_18000D888
0x18000d838  xor     eax, eax
0x18000d83a  mov     ecx, edx
0x18000d83c  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000d840  mov     [rcx+rdi+10h], ax
0x18000d845  mov     rax, [rsp+320h+String1]
0x18000d84a  test    rax, rax
0x18000d84d  jz      short loc_18000D868
0x18000d84f  lea     rdx, [rdi+10h]; String2
0x18000d853  mov     rcx, rax; String1
0x18000d856  call    cs:__imp__wcsicmp
0x18000d85c  test    eax, eax
0x18000d85e  jnz     short loc_18000D868
0x18000d860  inc     r15d
0x18000d863  jmp     loc_18000D7D1
0x18000d868  mov     rcx, [rsp+320h+KeyHandle]
0x18000d86d  lea     rdx, [rdi+10h]
0x18000d871  call    SclRegDeleteKeyRecursive
0x18000d876  xor     r15d, r15d
0x18000d879  mov     ebx, eax
0x18000d87b  test    eax, eax
0x18000d87d  jns     loc_18000D7D1
0x18000d883  jmp     loc_18000DA63
0x18000d888  mov     ebx, 80000005h
0x18000d88d  jmp     loc_18000DA63
0x18000d892  xor     eax, eax
0x18000d894  mov     dword ptr [rsp+320h+var_2F0], ebx
0x18000d898  test    r14, r14
0x18000d89b  lea     rcx, [r14+480h]
0x18000d8a2  mov     r9d, 902h
0x18000d8a8  lea     r8, SclEvent_Generic_Error
0x18000d8af  cmovz   rcx, rax
0x18000d8b3  mov     edx, 3
0x18000d8b8  lea     rax, aSclregenumerat_0; "SclRegEnumerateKey failed [0x%08X]"
0x18000d8bf  mov     [rsp+320h+var_2F8], rax
0x18000d8c4  lea     rax, aSclpwipehive; "SclpWipeHive"
0x18000d8cb  mov     [rsp+320h+var_300], rax
0x18000d8d0  call    SclLogGenericMessage
0x18000d8d5  jmp     loc_18000DA5E
0x18000d8da  mov     r8d, r13d; Size
0x18000d8dd  xor     edx, edx; Val
0x18000d8df  mov     rcx, rsi; void *
0x18000d8e2  mov     dword ptr [rsp+320h+var_2E0], 0
0x18000d8ea  call    memset_0
0x18000d8ef  mov     rcx, [rsp+320h+KeyHandle]
0x18000d8f4  lea     rax, [rsp+320h+var_2E0]
0x18000d8f9  mov     [rsp+320h+var_2F8], rax
0x18000d8fe  lea     r9, [rsp+320h+var_2C0]
0x18000d903  lea     rax, [rsp+320h+var_2C4]
0x18000d908  xor     r8d, r8d
0x18000d90b  xor     edx, edx
0x18000d90d  mov     [rsp+320h+var_300], rax
0x18000d912  call    SclRegEnumerateValueKey
0x18000d917  mov     ebx, eax
0x18000d919  cmp     eax, edi
0x18000d91b  jz      loc_18000DA00
0x18000d921  test    eax, eax
0x18000d923  js      loc_18000D9BB
0x18000d929  mov     rsi, [rsp+320h+var_2C0]
0x18000d92e  lea     rdx, [rsp+320h+ValueName]; ValueName
0x18000d933  mov     rcx, [rsp+320h+KeyHandle]; KeyHandle
0x18000d938  lea     rax, [rsi+0Ch]
0x18000d93c  mov     [rsp+320h+ValueName.Buffer], rax
0x18000d941  movzx   eax, word ptr [rsi+8]
0x18000d945  mov     [rsp+320h+ValueName.Length], ax
0x18000d94a  movzx   eax, word ptr [rsi+8]
0x18000d94e  mov     [rsp+320h+ValueName.MaximumLength], ax
0x18000d953  call    cs:__imp_NtDeleteValueKey
0x18000d959  mov     ebx, eax
0x18000d95b  test    eax, eax
0x18000d95d  js      short loc_18000D969
0x18000d95f  mov     r13d, [rsp+320h+var_2C4]
0x18000d964  jmp     loc_18000D8DA
0x18000d969  xor     eax, eax
0x18000d96b  lea     rcx, [r14+480h]
0x18000d972  test    r14, r14
0x18000d975  lea     r8, SclEvent_Generic_Error
0x18000d97c  mov     r9d, 94Eh
0x18000d982  mov     edx, 3
0x18000d987  cmovz   rcx, rax
0x18000d98b  lea     rax, [rsp+320h+ValueName]
0x18000d990  mov     [rsp+320h+var_2E8], rax
0x18000d995  lea     rax, aLxFailedToDele; "(%lx): Failed to delete value [%wZ]"
0x18000d99c  mov     dword ptr [rsp+320h+var_2F0], ebx
0x18000d9a0  mov     [rsp+320h+var_2F8], rax
0x18000d9a5  lea     rax, aSclpwipehive; "SclpWipeHive"
0x18000d9ac  mov     [rsp+320h+var_300], rax
0x18000d9b1  call    SclLogGenericMessage
0x18000d9b6  jmp     loc_18000DA5E
0x18000d9bb  xor     eax, eax
0x18000d9bd  mov     dword ptr [rsp+320h+var_2F0], ebx
0x18000d9c1  test    r14, r14
0x18000d9c4  lea     rcx, [r14+480h]
0x18000d9cb  mov     r9d, 93Fh
0x18000d9d1  lea     r8, SclEvent_Generic_Error
0x18000d9d8  cmovz   rcx, rax
0x18000d9dc  mov     edx, 3
0x18000d9e1  lea     rax, aSclregenumerat; "SclRegEnumerateValueKey failed [0x%08X]"
0x18000d9e8  mov     [rsp+320h+var_2F8], rax
0x18000d9ed  lea     rax, aSclpwipehive; "SclpWipeHive"
0x18000d9f4  mov     [rsp+320h+var_300], rax
0x18000d9f9  call    SclLogGenericMessage
0x18000d9fe  jmp     short loc_18000DA59
0x18000da00  mov     rcx, [rsp+320h+KeyHandle]; KeyHandle
0x18000da05  call    cs:__imp_NtFlushKey
0x18000da0b  lea     rcx, [r14+480h]
0x18000da12  mov     r9d, 95Ah
0x18000da18  mov     ebx, eax
0x18000da1a  lea     r8, SclEvent_Generic_Info
0x18000da21  xor     eax, eax
0x18000da23  mov     dword ptr [rsp+320h+var_2E8], ebx
0x18000da27  test    r14, r14
0x18000da2a  mov     edx, 1
0x18000da2f  cmovz   rcx, rax
0x18000da33  mov     rax, [rbp+220h+var_2A0]
0x18000da37  mov     [rsp+320h+var_2F0], rax
0x18000da3c  lea     rax, aFlushedChanges; "Flushed changes after wiping hive conte"...
0x18000da43  mov     [rsp+320h+var_2F8], rax
0x18000da48  lea     rax, aSclpwipehive; "SclpWipeHive"
0x18000da4f  mov     [rsp+320h+var_300], rax
0x18000da54  call    SclLogGenericMessage
0x18000da59  mov     rsi, [rsp+320h+var_2C0]
0x18000da5e  mov     rdi, [rsp+320h+var_2D0]
0x18000da63  mov     rcx, [rsp+320h+KeyHandle]; Handle
0x18000da68  test    rcx, rcx
0x18000da6b  jz      short loc_18000DA73
0x18000da6d  call    cs:__imp_NtClose
0x18000da73  test    rsi, rsi
0x18000da76  jz      short loc_18000DA90
0x18000da78  mov     rcx, gs:60h
0x18000da81  mov     r8, rsi; P
0x18000da84  xor     edx, edx; Flags
0x18000da86  mov     rcx, [rcx+30h]; HeapHandle
0x18000da8a  call    cs:__imp_RtlFreeHeap
0x18000da90  test    rdi, rdi
0x18000da93  jz      short loc_18000DAAD
0x18000da95  mov     rcx, gs:60h
0x18000da9e  mov     r8, rdi; P
0x18000daa1  xor     edx, edx; Flags
0x18000daa3  mov     rcx, [rcx+30h]; HeapHandle
0x18000daa7  call    cs:__imp_RtlFreeHeap
0x18000daad  mov     eax, ebx
0x18000daaf  mov     rcx, [rbp+220h+var_40]
0x18000dab6  xor     rcx, rsp; StackCookie
0x18000dab9  call    __security_check_cookie
0x18000dabe  mov     rbx, [rsp+320h+arg_18]
0x18000dac6  add     rsp, 2F0h
0x18000dacd  pop     r15
0x18000dacf  pop     r14
0x18000dad1  pop     r13
0x18000dad3  pop     r12
0x18000dad5  pop     rdi
0x18000dad6  pop     rsi
0x18000dad7  pop     rbp
0x18000dad8  retn
```

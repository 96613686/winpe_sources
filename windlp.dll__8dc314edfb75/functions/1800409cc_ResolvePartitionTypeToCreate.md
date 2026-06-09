# ResolvePartitionTypeToCreate

- ea: `0x1800409cc`
- end: `0x180040c15`
- name: `ResolvePartitionTypeToCreate`
- size: `585`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003e3c0`

## callees

- `0x180039394`
- `0x180039c40`
- `0x1800409cc`
- `0x18007ed40`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180040a2b`
- `ntdll!NtQuerySystemInformation` at `0x180040a2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040a77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040aed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040a77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040aed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040a85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040afb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040a85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040afb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040a9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040b12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040a9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040b12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040b06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040b06`

## string_xrefs

- `0x180040b77`: `ResolvePartitionTypeToCreate: %s: Couldn't figure out the number of partitions on disk %d, assume there're at least one partition.`
- `0x180040b36`: `ResolvePartitionTypeToCreate: %s: disk %d already has %d allocated partitions`
- `0x180040b18`: `DiskConfiguration`
- `0x180040bd0`: `DiskConfiguration`
- `0x180040ba1`: `ResolvePartitionTypeToCreate: %s: disk %d is a RAW disk on an EFI computer; assuming %s setting wants to create GPT basic data partition`
- `0x180040b6c`: `ResolvePartitionTypeToCreate: %s: disk %d has zero existing partitions on an EFI computer; assuming %s setting wants to create GPT basic data partition`
- `0x180040b91`: `ResolvePartitionTypeToCreate: %s: disk %d is a GPT disk and has more than zero existing partitions; assuming %s setting wants to create GPT basic data partition`
- `0x180040bc4`: `CreatePartition`
- `0x180040bb0`: `ResolvePartitionTypeToCreate: %s: disk %d is of an unknown type and is on an EFI computer; assuming %s setting wants to create GPT basic data partition`

## pseudocode

```c
__int64 __fastcall ResolvePartitionTypeToCreate(int a1, _DWORD *a2)
{
  int v4; // r14d
  int *DriveLayout; // rsi
  int v6; // ebx
  DWORD LastError; // r15d
  int v8; // ebp
  HANDLE ProcessHeap; // rax
  int v10; // ebp
  _DWORD *v11; // rsi
  DWORD v12; // r13d
  __int64 i; // rax
  int v14; // r15d
  HANDLE v15; // rax
  const wchar_t *v16; // r8
  __int64 v18; // [rsp+20h] [rbp-78h]
  __int128 SystemInformation; // [rsp+30h] [rbp-68h] BYREF
  __int128 v20; // [rsp+40h] [rbp-58h]

  if ( a2 && a1 >= 0 )
  {
    *a2 = 1;
    SystemInformation = 0;
    v20 = 0;
    if ( NtQuerySystemInformation(SystemBootEnvironmentInformation, &SystemInformation, 0x20u, 0) < 0 )
    {
      v4 = 1;
    }
    else
    {
      v4 = 0;
      if ( (int)v20 < 3 )
        v4 = v20;
    }
    DriveLayout = (int *)GetDriveLayout((unsigned int)a1, 0);
    if ( DriveLayout )
    {
      v6 = *DriveLayout;
      LastError = 0;
      if ( !*(_QWORD *)DriveLayout && !DriveLayout[2] )
        v6 = 2;
      v8 = 1;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, DriveLayout);
    }
    else
    {
      v6 = 0;
      v8 = 0;
      LastError = GetLastError();
    }
    SetLastError(LastError);
    if ( v8 == 1 )
    {
      v10 = 0;
      v11 = (_DWORD *)GetDriveLayout((unsigned int)a1, 0);
      if ( v11 )
      {
        v12 = 0;
        for ( i = 0; (unsigned int)i < v11[1]; i = (unsigned int)(i + 1) )
        {
          if ( v11[36 * i + 12] == 2 || v11[36 * i + 18] )
            ++v10;
        }
        v14 = 1;
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v11);
      }
      else
      {
        v14 = 0;
        v12 = GetLastError();
      }
      SetLastError(v12);
      if ( v14 )
      {
        LibLog(
          &g_VdsLibLog,
          0x4000000,
          L"ResolvePartitionTypeToCreate: %s: disk %d already has %d allocated partitions",
          L"DiskConfiguration",
          a1,
          v10);
        if ( !v10 )
        {
LABEL_25:
          if ( !v6 && v10 || v4 != 2 )
            return 0;
          *a2 = 4;
          if ( !v10 )
          {
            v16 = L"ResolvePartitionTypeToCreate: %s: disk %d has zero existing partitions on an EFI computer; assuming %s"
                   " setting wants to create GPT basic data partition";
LABEL_38:
            LODWORD(v18) = a1;
            LibLog(&g_VdsLibLog, 0x4000000, v16, L"DiskConfiguration", v18, L"CreatePartition");
            return 0;
          }
          if ( v6 != 1 )
          {
            v16 = L"ResolvePartitionTypeToCreate: %s: disk %d is a RAW disk on an EFI computer; assuming %s setting wants "
                   "to create GPT basic data partition";
            goto LABEL_38;
          }
          return 0;
        }
      }
      else
      {
        v10 = 1;
        LibLog(
          &g_VdsLibLog,
          0x4000000,
          L"ResolvePartitionTypeToCreate: %s: Couldn't figure out the number of partitions on disk %d, assume there're at "
           "least one partition.",
          L"DiskConfiguration",
          a1);
      }
      if ( v6 != 1 )
        goto LABEL_25;
      v16 = L"ResolvePartitionTypeToCreate: %s: disk %d is a GPT disk and has more than zero existing partitions; assuming"
             " %s setting wants to create GPT basic data partition";
    }
    else
    {
      if ( v4 != 2 )
        return 0;
      v16 = L"ResolvePartitionTypeToCreate: %s: disk %d is of an unknown type and is on an EFI computer; assuming %s setti"
             "ng wants to create GPT basic data partition";
    }
    *a2 = 4;
    goto LABEL_38;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800409cc  mov     [rsp+arg_10], rbx
0x1800409d1  push    rbp
0x1800409d2  push    rsi
0x1800409d3  push    rdi
0x1800409d4  push    r12
0x1800409d6  push    r13
0x1800409d8  push    r14
0x1800409da  push    r15
0x1800409dc  sub     rsp, 60h
0x1800409e0  mov     rax, cs:__security_cookie
0x1800409e7  xor     rax, rsp
0x1800409ea  mov     [rsp+98h+var_48], rax
0x1800409ef  mov     r12, rdx
0x1800409f2  mov     edi, ecx
0x1800409f4  test    rdx, rdx
0x1800409f7  jz      loc_180040BEB
0x1800409fd  test    ecx, ecx
0x1800409ff  js      loc_180040BEB
0x180040a05  mov     r13d, 1
0x180040a0b  xorps   xmm0, xmm0
0x180040a0e  mov     [rdx], r13d
0x180040a11  xor     r9d, r9d; ReturnLength
0x180040a14  lea     rdx, [rsp+98h+SystemInformation]; SystemInformation
0x180040a19  movups  [rsp+98h+SystemInformation], xmm0
0x180040a1e  lea     r8d, [r13+1Fh]; SystemInformationLength
0x180040a22  lea     ecx, [r13+59h]; SystemInformationClass
0x180040a26  movups  [rsp+98h+var_58], xmm0
0x180040a2b  call    cs:__imp_NtQuerySystemInformation
0x180040a31  test    eax, eax
0x180040a33  js      short loc_180040A45
0x180040a35  xor     r14d, r14d
0x180040a38  cmp     dword ptr [rsp+98h+var_58], 3
0x180040a3d  cmovl   r14d, dword ptr [rsp+98h+var_58]
0x180040a43  jmp     short loc_180040A48
0x180040a45  mov     r14d, r13d
0x180040a48  xor     edx, edx
0x180040a4a  mov     ecx, edi
0x180040a4c  call    GetDriveLayout
0x180040a51  mov     rsi, rax
0x180040a54  mov     eax, 2
0x180040a59  test    rsi, rsi
0x180040a5c  jz      short loc_180040A8D
0x180040a5e  mov     ebx, [rsi]
0x180040a60  xor     r15d, r15d
0x180040a63  test    ebx, ebx
0x180040a65  jnz     short loc_180040A74
0x180040a67  cmp     [rsi+4], r15d
0x180040a6b  jnz     short loc_180040A74
0x180040a6d  cmp     [rsi+8], r15d
0x180040a71  cmovz   ebx, eax
0x180040a74  mov     ebp, r13d
0x180040a77  call    cs:__imp_GetProcessHeap
0x180040a7d  mov     r8, rsi; lpMem
0x180040a80  xor     edx, edx; dwFlags
0x180040a82  mov     rcx, rax; hHeap
0x180040a85  call    cs:__imp_HeapFree
0x180040a8b  jmp     short loc_180040A9A
0x180040a8d  xor     ebx, ebx
0x180040a8f  xor     ebp, ebp
0x180040a91  call    cs:__imp_GetLastError
0x180040a97  mov     r15d, eax
0x180040a9a  mov     ecx, r15d; dwErrCode
0x180040a9d  call    cs:__imp_SetLastError
0x180040aa3  cmp     ebp, r13d
0x180040aa6  jnz     loc_180040BAA
0x180040aac  xor     edx, edx
0x180040aae  mov     ecx, edi
0x180040ab0  call    GetDriveLayout
0x180040ab5  xor     ebp, ebp
0x180040ab7  mov     rsi, rax
0x180040aba  test    rax, rax
0x180040abd  jz      short loc_180040B03
0x180040abf  xor     r13d, r13d
0x180040ac2  xor     eax, eax
0x180040ac4  cmp     [rsi+4], eax
0x180040ac7  jbe     short loc_180040AE7
0x180040ac9  lea     rdx, [rax+rax*8]
0x180040acd  add     rdx, rdx
0x180040ad0  cmp     dword ptr [rsi+rdx*8+30h], 2
0x180040ad5  jz      short loc_180040ADE
0x180040ad7  cmp     [rsi+rdx*8+48h], r13d
0x180040adc  jz      short loc_180040AE0
0x180040ade  inc     ebp
0x180040ae0  inc     eax
0x180040ae2  cmp     eax, [rsi+4]
0x180040ae5  jb      short loc_180040AC9
0x180040ae7  mov     r15d, 1
0x180040aed  call    cs:__imp_GetProcessHeap
0x180040af3  mov     r8, rsi; lpMem
0x180040af6  xor     edx, edx; dwFlags
0x180040af8  mov     rcx, rax; hHeap
0x180040afb  call    cs:__imp_HeapFree
0x180040b01  jmp     short loc_180040B0F
0x180040b03  xor     r15d, r15d
0x180040b06  call    cs:__imp_GetLastError
0x180040b0c  mov     r13d, eax
0x180040b0f  mov     ecx, r13d; dwErrCode
0x180040b12  call    cs:__imp_SetLastError
0x180040b18  lea     r9, aDiskconfigurat; "DiskConfiguration"
0x180040b1f  mov     esi, 4000000h
0x180040b24  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x180040b2b  mov     edx, esi
0x180040b2d  test    r15d, r15d
0x180040b30  jz      short loc_180040B77
0x180040b32  mov     dword ptr [rsp+98h+var_70], ebp
0x180040b36  lea     r8, aResolvepartiti_1; "ResolvePartitionTypeToCreate: %s: disk "...
0x180040b3d  mov     dword ptr [rsp+98h+var_78], edi
0x180040b41  call    LibLog
0x180040b46  test    ebp, ebp
0x180040b48  jnz     short loc_180040B8C
0x180040b4a  test    ebx, ebx
0x180040b4c  jnz     short loc_180040B56
0x180040b4e  test    ebp, ebp
0x180040b50  jnz     loc_180040BE7
0x180040b56  cmp     r14d, 2
0x180040b5a  jnz     loc_180040BE7
0x180040b60  mov     dword ptr [r12], 4
0x180040b68  test    ebp, ebp
0x180040b6a  jnz     short loc_180040B9C
0x180040b6c  lea     r8, aResolvepartiti_3; "ResolvePartitionTypeToCreate: %s: disk "...
0x180040b73  mov     edx, esi
0x180040b75  jmp     short loc_180040BC4
0x180040b77  lea     r8, aResolvepartiti; "ResolvePartitionTypeToCreate: %s: Could"...
0x180040b7e  mov     dword ptr [rsp+98h+var_78], edi
0x180040b82  mov     ebp, 1
0x180040b87  call    LibLog
0x180040b8c  cmp     ebx, 1
0x180040b8f  jnz     short loc_180040B4A
0x180040b91  lea     r8, aResolvepartiti_2; "ResolvePartitionTypeToCreate: %s: disk "...
0x180040b98  mov     edx, esi
0x180040b9a  jmp     short loc_180040BBC
0x180040b9c  cmp     ebx, 1
0x180040b9f  jz      short loc_180040BE7
0x180040ba1  lea     r8, aResolvepartiti_4; "ResolvePartitionTypeToCreate: %s: disk "...
0x180040ba8  jmp     short loc_180040B73
0x180040baa  cmp     r14d, 2
0x180040bae  jnz     short loc_180040BE7
0x180040bb0  lea     r8, aResolvepartiti_0; "ResolvePartitionTypeToCreate: %s: disk "...
0x180040bb7  mov     edx, 4000000h
0x180040bbc  mov     dword ptr [r12], 4
0x180040bc4  lea     rax, aCreatepartitio_2; "CreatePartition"
0x180040bcb  mov     [rsp+98h+var_70], rax
0x180040bd0  lea     r9, aDiskconfigurat; "DiskConfiguration"
0x180040bd7  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x180040bde  mov     dword ptr [rsp+98h+var_78], edi
0x180040be2  call    LibLog
0x180040be7  xor     eax, eax
0x180040be9  jmp     short loc_180040BF0
0x180040beb  mov     eax, 80070057h
0x180040bf0  mov     rcx, [rsp+98h+var_48]
0x180040bf5  xor     rcx, rsp; StackCookie
0x180040bf8  call    __security_check_cookie
0x180040bfd  mov     rbx, [rsp+98h+arg_10]
0x180040c05  add     rsp, 60h
0x180040c09  pop     r15
0x180040c0b  pop     r14
0x180040c0d  pop     r13
0x180040c0f  pop     r12
0x180040c11  pop     rdi
0x180040c12  pop     rsi
0x180040c13  pop     rbp
0x180040c14  retn
```

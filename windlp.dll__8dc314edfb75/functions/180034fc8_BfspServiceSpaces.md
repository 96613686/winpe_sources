# BfspServiceSpaces

- ea: `0x180034fc8`
- end: `0x180035276`
- name: `BfspServiceSpaces`
- size: `686`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x180032518`

## callees

- `0x180031598`
- `0x180034fc8`
- `0x18003545c`
- `0x1800358e0`
- `0x1800366b8`
- `0x180037220`
- `0x180037440`
- `0x180038c34`
- `0x18007ecb2`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180035047`
- `ntdll!RtlNtStatusToDosError` at `0x180035047`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035226`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003523f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035226`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003523f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035234`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003524d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035234`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003524d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035066`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800350be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035259`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035066`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800350be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800350a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003513d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800350a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003513d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035202`
- `bcd!SyspartIsSpace` at `0x18003503b`
- `bcd!SyspartIsSpace` at `0x18003503b`

## string_xrefs

- `0x180035126`: `|DEST|\bootspaces.dll`
- `0x18003512d`: `|SOURCE|\Misc\|FWTYPE|\bootspaces.dll`
- `0x180035143`: `Failed to service spaces DLL. Last Error = %#x`
- `0x18003517a`: `Failed to service spaces default bootmgr`
- `0x1800351b1`: `Failed to service spaces bootmgr. Last Error = %#x`
- `0x1800351c7`: `|SYSPART|\|DEST|\bootspaces.dll`
- `0x18003520b`: `Error deleting stale spaces dll (%s)! Last Error = %#x`

## pseudocode

```c
__int64 __fastcall BfspServiceSpaces(__int64 a1, int a2)
{
  void *v2; // rdi
  unsigned int v4; // r14d
  _WORD *v5; // rsi
  __int64 v6; // rbx
  unsigned __int64 v7; // rax
  NTSTATUS IsSpace; // eax
  ULONG v9; // eax
  DWORD LastError; // eax
  const wchar_t *Value; // rax
  DWORD v12; // eax
  const wchar_t *v13; // rdx
  const wchar_t *v14; // r8
  const wchar_t *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rbp
  HANDLE ProcessHeap; // rax
  HANDLE v19; // rax
  int v21; // [rsp+68h] [rbp+10h] BYREF
  _DWORD *v22; // [rsp+70h] [rbp+18h] BYREF

  v21 = a2;
  LOBYTE(v21) = 0;
  v2 = 0;
  v22 = 0;
  v4 = 1;
  v5 = (_WORD *)BfspEnvExpandString(a1, L"|SYSPART|");
  if ( !v5 )
  {
    LODWORD(v6) = GetLastError();
    goto LABEL_27;
  }
  v7 = -1;
  do
    ++v7;
  while ( v5[v7] );
  if ( v7 > 1 && v5[1] == 92 )
    v5[1] = 63;
  IsSpace = SyspartIsSpace(v5, &v21);
  if ( IsSpace < 0 )
  {
    v9 = RtlNtStatusToDosError(IsSpace);
    BfspLogMessage(3, L"Failed to determine whether the system partition is in a space. Last Error = %#x", v9);
    LODWORD(v6) = 0;
    SetLastError(0);
    goto LABEL_27;
  }
  LODWORD(v6) = 0;
  if ( (_BYTE)v21 )
  {
    if ( !(unsigned int)BfspSpacesGetPhysicalPartitions(v5, &v22) )
    {
      LastError = GetLastError();
      BfspLogMessage(3, L"Failed to retrieve physical partitions. Last Error = %#x", LastError);
      SetLastError(0);
      v2 = v22;
      goto LABEL_27;
    }
    v2 = v22;
    if ( !v22[2] )
    {
      BfspLogMessage(2, L"No physical partitions found");
      goto LABEL_27;
    }
    BfspLogMessage(2, L"Servicing spaces files");
    Value = (const wchar_t *)BfspEnvGetValue(a1, L"FWTYPE");
    if ( !wcsncmp_0(Value, L"EFI", 4u) )
    {
      if ( !(unsigned int)BfspSpacesCopyToPhysicalPartitions(
                            a1,
                            (__int64)L"|SYSPART|\\|DEST|\\|BOOTMGBIN|",
                            (__int64)L"|EFIDEFAULTDIR|\\|DEFAULTAPP|",
                            (__int64)L"bootmgr.exe",
                            (__int64)v2) )
        BfspLogMessage(3, L"Failed to service spaces default bootmgr");
      v14 = L"|DEST|\\|BOOTMGBIN|";
      v15 = L"|SYSPART|\\|DEST|\\|BOOTMGBIN|";
    }
    else
    {
      if ( !(unsigned int)BfspSpacesCopyToPhysicalPartitions(
                            a1,
                            (__int64)L"|SOURCE|\\Misc\\|FWTYPE|\\bootspaces.dll",
                            (__int64)L"|DEST|\\bootspaces.dll",
                            0,
                            (__int64)v2) )
      {
        v12 = GetLastError();
        v13 = L"Failed to service spaces DLL. Last Error = %#x";
LABEL_26:
        LODWORD(v6) = v12;
        BfspLogMessage(4, v13, v12);
        goto LABEL_27;
      }
      v14 = L"|BOOTMGBIN|";
      v15 = L"|SYSPART|\\|BOOTMGBIN|";
    }
    if ( (unsigned int)BfspSpacesCopyToPhysicalPartitions(a1, (__int64)v15, (__int64)v14, 0, (__int64)v2) )
      goto LABEL_27;
    v12 = GetLastError();
    v13 = L"Failed to service spaces bootmgr. Last Error = %#x";
    goto LABEL_26;
  }
  BfspLogMessage(2, L"System partition is not in a space");
LABEL_27:
  v16 = BfspEnvExpandString(a1, L"|SYSPART|\\|DEST|\\bootspaces.dll");
  v17 = v16;
  if ( v16 )
  {
    if ( (unsigned int)BfspFileExists(v16) && !DeleteFileEx2(v17, 0) )
    {
      v6 = GetLastError();
      BfspLogMessage(4, L"Error deleting stale spaces dll (%s)! Last Error = %#x", v17, v6);
    }
  }
  else
  {
    LODWORD(v6) = GetLastError();
  }
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  if ( v5 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v5);
  }
  if ( (_DWORD)v6 )
  {
    SetLastError(v6);
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180034fc8  mov     rax, rsp
0x180034fcb  mov     [rax+8], rbx
0x180034fcf  mov     [rax+10h], edx
0x180034fd2  push    rbp
0x180034fd3  push    rsi
0x180034fd4  push    rdi
0x180034fd5  push    r14
0x180034fd7  push    r15
0x180034fd9  sub     rsp, 30h
0x180034fdd  xor     r15d, r15d
0x180034fe0  lea     rdx, aSyspart; "|SYSPART|"
0x180034fe7  mov     [rax+10h], r15b
0x180034feb  mov     edi, r15d
0x180034fee  mov     [rax+18h], r15
0x180034ff2  mov     rbp, rcx
0x180034ff5  call    BfspEnvExpandString
0x180034ffa  lea     r14d, [r15+1]
0x180034ffe  mov     rsi, rax
0x180035001  test    rax, rax
0x180035004  jnz     short loc_180035013
0x180035006  call    cs:__imp_GetLastError
0x18003500c  mov     ebx, eax
0x18003500e  jmp     loc_1800351C7
0x180035013  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035017  inc     rax
0x18003501a  cmp     [rsi+rax*2], r15w
0x18003501f  jnz     short loc_180035017
0x180035021  cmp     rax, r14
0x180035024  jbe     short loc_180035033
0x180035026  cmp     word ptr [rsi+2], 5Ch ; '\'
0x18003502b  jnz     short loc_180035033
0x18003502d  mov     word ptr [rsi+2], 3Fh ; '?'
0x180035033  lea     rdx, [rsp+58h+arg_8]
0x180035038  mov     rcx, rsi
0x18003503b  call    cs:__imp_SyspartIsSpace
0x180035041  test    eax, eax
0x180035043  jns     short loc_180035071
0x180035045  mov     ecx, eax; Status
0x180035047  call    cs:__imp_RtlNtStatusToDosError
0x18003504d  lea     rdx, aFailedToDeterm_0; "Failed to determine whether the system "...
0x180035054  mov     ecx, 3
0x180035059  mov     r8d, eax
0x18003505c  call    BfspLogMessage
0x180035061  xor     ecx, ecx; dwErrCode
0x180035063  mov     ebx, r15d
0x180035066  call    cs:__imp_SetLastError
0x18003506c  jmp     loc_1800351C7
0x180035071  mov     ebx, r15d
0x180035074  cmp     byte ptr [rsp+58h+arg_8], r15b
0x180035079  jnz     short loc_180035091
0x18003507b  lea     rdx, aSystemPartitio; "System partition is not in a space"
0x180035082  mov     ecx, 2
0x180035087  call    BfspLogMessage
0x18003508c  jmp     loc_1800351C7
0x180035091  lea     rdx, [rsp+58h+arg_10]
0x180035096  mov     rcx, rsi
0x180035099  call    BfspSpacesGetPhysicalPartitions
0x18003509e  test    eax, eax
0x1800350a0  jnz     short loc_1800350CE
0x1800350a2  call    cs:__imp_GetLastError
0x1800350a8  lea     rdx, aFailedToRetrie; "Failed to retrieve physical partitions."...
0x1800350af  mov     ecx, 3
0x1800350b4  mov     r8d, eax
0x1800350b7  call    BfspLogMessage
0x1800350bc  xor     ecx, ecx; dwErrCode
0x1800350be  call    cs:__imp_SetLastError
0x1800350c4  mov     rdi, [rsp+58h+arg_10]
0x1800350c9  jmp     loc_1800351C7
0x1800350ce  mov     rdi, [rsp+58h+arg_10]
0x1800350d3  mov     ecx, 2
0x1800350d8  cmp     [rdi+8], r15d
0x1800350dc  jnz     short loc_1800350E7
0x1800350de  lea     rdx, aNoPhysicalPart; "No physical partitions found"
0x1800350e5  jmp     short loc_180035087
0x1800350e7  lea     rdx, aServicingSpace; "Servicing spaces files"
0x1800350ee  call    BfspLogMessage
0x1800350f3  lea     rdx, aFwtype; "FWTYPE"
0x1800350fa  mov     rcx, rbp
0x1800350fd  call    BfspEnvGetValue
0x180035102  mov     rcx, rax; String1
0x180035105  lea     rdx, aEfi; "EFI"
0x18003510c  mov     r8d, 4; MaxCount
0x180035112  call    wcsncmp_0
0x180035117  mov     [rsp+58h+var_38], rdi
0x18003511c  mov     rcx, rbp
0x18003511f  test    eax, eax
0x180035121  jz      short loc_18003515C
0x180035123  xor     r9d, r9d
0x180035126  lea     r8, aDestBootspaces; "|DEST|\\bootspaces.dll"
0x18003512d  lea     rdx, aSourceMiscFwty; "|SOURCE|\\Misc\\|FWTYPE|\\bootspaces.dl"...
0x180035134  call    BfspSpacesCopyToPhysicalPartitions
0x180035139  test    eax, eax
0x18003513b  jnz     short loc_18003514C
0x18003513d  call    cs:__imp_GetLastError
0x180035143  lea     rdx, aFailedToServic_0; "Failed to service spaces DLL. Last Erro"...
0x18003514a  jmp     short loc_1800351B8
0x18003514c  lea     r8, aBootmgbin_0; "|BOOTMGBIN|"
0x180035153  lea     rdx, aSyspartBootmgb; "|SYSPART|\\|BOOTMGBIN|"
0x18003515a  jmp     short loc_180035197
0x18003515c  lea     r9, aBootmgrExe; "bootmgr.exe"
0x180035163  lea     r8, aEfidefaultdirD; "|EFIDEFAULTDIR|\\|DEFAULTAPP|"
0x18003516a  lea     rdx, aSyspartDestBoo_2; "|SYSPART|\\|DEST|\\|BOOTMGBIN|"
0x180035171  call    BfspSpacesCopyToPhysicalPartitions
0x180035176  test    eax, eax
0x180035178  jnz     short loc_180035189
0x18003517a  lea     rdx, aFailedToServic_1; "Failed to service spaces default bootmg"...
0x180035181  lea     ecx, [rax+3]
0x180035184  call    BfspLogMessage
0x180035189  lea     r8, aDestBootmgbin; "|DEST|\\|BOOTMGBIN|"
0x180035190  lea     rdx, aSyspartDestBoo_2; "|SYSPART|\\|DEST|\\|BOOTMGBIN|"
0x180035197  xor     r9d, r9d
0x18003519a  mov     [rsp+58h+var_38], rdi
0x18003519f  mov     rcx, rbp
0x1800351a2  call    BfspSpacesCopyToPhysicalPartitions
0x1800351a7  test    eax, eax
0x1800351a9  jnz     short loc_1800351C7
0x1800351ab  call    cs:__imp_GetLastError
0x1800351b1  lea     rdx, aFailedToServic; "Failed to service spaces bootmgr. Last "...
0x1800351b8  mov     r8d, eax
0x1800351bb  mov     ecx, 4
0x1800351c0  mov     ebx, eax
0x1800351c2  call    BfspLogMessage
0x1800351c7  lea     rdx, aSyspartDestBoo_0; "|SYSPART|\\|DEST|\\bootspaces.dll"
0x1800351ce  mov     rcx, rbp
0x1800351d1  call    BfspEnvExpandString
0x1800351d6  mov     rbp, rax
0x1800351d9  test    rax, rax
0x1800351dc  jnz     short loc_1800351E8
0x1800351de  call    cs:__imp_GetLastError
0x1800351e4  mov     ebx, eax
0x1800351e6  jmp     short loc_180035221
0x1800351e8  mov     rcx, rbp
0x1800351eb  call    BfspFileExists
0x1800351f0  test    eax, eax
0x1800351f2  jz      short loc_180035221
0x1800351f4  xor     edx, edx
0x1800351f6  mov     rcx, rbp
0x1800351f9  call    DeleteFileEx2
0x1800351fe  test    eax, eax
0x180035200  jnz     short loc_180035221
0x180035202  call    cs:__imp_GetLastError
0x180035208  mov     r8, rbp
0x18003520b  lea     rdx, aErrorDeletingS; "Error deleting stale spaces dll (%s)! L"...
0x180035212  mov     r9d, eax
0x180035215  mov     ecx, 4
0x18003521a  mov     ebx, eax
0x18003521c  call    BfspLogMessage
0x180035221  test    rdi, rdi
0x180035224  jz      short loc_18003523A
0x180035226  call    cs:__imp_GetProcessHeap
0x18003522c  mov     r8, rdi; lpMem
0x18003522f  xor     edx, edx; dwFlags
0x180035231  mov     rcx, rax; hHeap
0x180035234  call    cs:__imp_HeapFree
0x18003523a  test    rsi, rsi
0x18003523d  jz      short loc_180035253
0x18003523f  call    cs:__imp_GetProcessHeap
0x180035245  mov     r8, rsi; lpMem
0x180035248  xor     edx, edx; dwFlags
0x18003524a  mov     rcx, rax; hHeap
0x18003524d  call    cs:__imp_HeapFree
0x180035253  test    ebx, ebx
0x180035255  jz      short loc_180035262
0x180035257  mov     ecx, ebx; dwErrCode
0x180035259  call    cs:__imp_SetLastError
0x18003525f  mov     r14d, r15d
0x180035262  mov     rbx, [rsp+58h+arg_0]
0x180035267  mov     eax, r14d
0x18003526a  add     rsp, 30h
0x18003526e  pop     r15
0x180035270  pop     r14
0x180035272  pop     rdi
0x180035273  pop     rsi
0x180035274  pop     rbp
0x180035275  retn
```

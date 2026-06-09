# AsrGetSystemVolumeDevPath(ushort *,ulong)

- ea: `0x1400242a0`
- end: `0x1400244fa`
- name: `?AsrGetSystemVolumeDevPath@@YAHPEAGK@Z`
- size: `602`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `5`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400235e0`
- `0x140025210`
- `0x140058f70`
- `0x1400d616c`
- `0x1400d763c`

## callees

- `0x140021ca0`
- `0x1400235a8`
- `0x1400242a0`
- `0x14003b160`
- `0x14005b208`
- `0x1400d257c`
- `0x1400d7ebc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400244df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400244df`
- `ntdll!NtQuerySystemInformation` at `0x1400242e7`
- `ntdll!NtQuerySystemInformation` at `0x1400243b0`
- `ntdll!NtQuerySystemInformation` at `0x1400243f6`
- `ntdll!NtQuerySystemInformation` at `0x1400242e7`
- `ntdll!NtQuerySystemInformation` at `0x1400243b0`
- `ntdll!NtQuerySystemInformation` at `0x1400243f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002435d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14002435d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400244cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400244cb`

## string_xrefs

- `0x1400242b9`: `AsrGetSystemVolumeDevPath`
- `0x1400244d1`: `AsrGetSystemVolumeDevPath`
- `0x140024401`: `NtQuerySystemInformation( SystemSystemPartitionInformation, pSysInfo, cbRequiredSize, &cbRequiredSize)`
- `0x140024476`: `::StringCchCopyN( pwszVolume, cchVolume, pSysInfo->SystemPartition.Buffer, (pSysInfo->SystemPartition.Length)/sizeof(WCHAR) )`

## pseudocode

```c
__int64 __fastcall AsrGetSystemVolumeDevPath(unsigned __int16 *a1, ULONG a2)
{
  unsigned int v3; // ebp
  const unsigned __int16 **v4; // rsi
  NTSTATUS v5; // eax
  NTSTATUS v6; // edi
  DWORD v7; // ebx
  const unsigned __int16 **v8; // rax
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  int v11; // edx
  const char *v12; // rcx
  int v13; // eax
  ULONG ReturnLength; // [rsp+58h] [rbp+10h] BYREF

  ReturnLength = a2;
  TraceFunctionEnter(L"AsrGetSystemVolumeDevPath");
  v3 = 0;
  ReturnLength = 0;
  v4 = 0;
  if ( a1 )
  {
    *a1 = 0;
    v5 = NtQuerySystemInformation(MaxSystemInfoClass, 0, 0, &ReturnLength);
    v6 = v5;
    if ( v5 < 0 && v5 != -1073741789 && v5 != -2147483643 && v5 != -1073741820 )
    {
      v7 = WIN32_FROM_NTSTATUS((unsigned int)v5);
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          24,
          (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
          v6,
          "ntStatus");
      }
      goto LABEL_27;
    }
    v8 = (const unsigned __int16 **)CoTaskMemAlloc(ReturnLength);
    v4 = v8;
    if ( !v8 )
    {
      v7 = 14;
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          25,
          (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
          14,
          "pSysInfo");
      }
      goto LABEL_27;
    }
    v9 = NtQuerySystemInformation(MaxSystemInfoClass, v8, ReturnLength, &ReturnLength);
    if ( v9 < 0 )
    {
      v7 = WIN32_FROM_NTSTATUS((unsigned int)v9);
      if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
      {
        goto LABEL_27;
      }
      v10 = NtQuerySystemInformation(MaxSystemInfoClass, v4, ReturnLength, &ReturnLength);
      v11 = 26;
      v12 = "NtQuerySystemInformation( SystemSystemPartitionInformation, pSysInfo, cbRequiredSize, &cbRequiredSize)";
LABEL_18:
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        v11,
        (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
        v10,
        v12);
      goto LABEL_27;
    }
    v13 = StringCchCopyNW(a1, 0x104u, v4[1], (unsigned __int64)*(unsigned __int16 *)v4 >> 1);
    if ( v13 >= 0 )
    {
      v7 = 0;
      v3 = 1;
      goto LABEL_27;
    }
    v7 = WIN32_FROM_HRESULT((unsigned int)v13);
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v10 = StringCchCopyNW(a1, 0x104u, v4[1], (unsigned __int64)*(unsigned __int16 *)v4 >> 1);
      v11 = 27;
      v12 = "::StringCchCopyN( pwszVolume, cchVolume, pSysInfo->SystemPartition.Buffer, (pSysInfo->SystemPartition.Length"
            ")/sizeof(WCHAR) )";
      goto LABEL_18;
    }
  }
  else
  {
    v7 = 87;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        22,
        (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
        87,
        "pwszVolume");
    }
  }
LABEL_27:
  CoTaskMemFree(v4);
  TraceFunctionExit(L"AsrGetSystemVolumeDevPath");
  SetLastError(v7);
  return v3;
}

```

## disassembly

```asm
0x1400242a0  mov     [rsp+arg_0], rbx
0x1400242a5  mov     [rsp+arg_10], rbp
0x1400242aa  mov     [rsp+ReturnLength], edx
0x1400242ae  push    rsi
0x1400242af  push    rdi
0x1400242b0  push    r14
0x1400242b2  sub     rsp, 30h
0x1400242b6  mov     r14, rcx
0x1400242b9  lea     rcx, aAsrgetsystemvo_4; "AsrGetSystemVolumeDevPath"
0x1400242c0  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x1400242c5  xor     ebp, ebp
0x1400242c7  mov     [rsp+48h+ReturnLength], ebp
0x1400242cb  mov     esi, ebp
0x1400242cd  test    r14, r14
0x1400242d0  jz      loc_140024488
0x1400242d6  lea     r9, [rsp+48h+ReturnLength]; ReturnLength
0x1400242db  mov     [r14], bp
0x1400242df  xor     r8d, r8d; SystemInformationLength
0x1400242e2  lea     ecx, [rbp+62h]; SystemInformationClass
0x1400242e5  xor     edx, edx; SystemInformation
0x1400242e7  call    cs:__imp_NtQuerySystemInformation
0x1400242ed  mov     edi, eax
0x1400242ef  test    eax, eax
0x1400242f1  jns     short loc_140024359
0x1400242f3  cmp     eax, 0C0000023h
0x1400242f8  jz      short loc_140024359
0x1400242fa  cmp     eax, 80000005h
0x1400242ff  jz      short loc_140024359
0x140024301  cmp     eax, 0C0000004h
0x140024306  jz      short loc_140024359
0x140024308  mov     ecx, eax
0x14002430a  call    WIN32_FROM_NTSTATUS
0x14002430f  mov     ebx, eax
0x140024311  mov     rcx, cs:WPP_GLOBAL_Control
0x140024318  lea     rdx, WPP_GLOBAL_Control
0x14002431f  cmp     rcx, rdx
0x140024322  jz      loc_1400244C8
0x140024328  test    byte ptr [rcx+1Ch], 8
0x14002432c  jz      loc_1400244C8
0x140024332  lea     rax, aNtstatus; "ntStatus"
0x140024339  mov     r9d, edi
0x14002433c  mov     [rsp+48h+var_28], rax
0x140024341  lea     edx, [rbp+18h]
0x140024344  mov     rcx, [rcx+10h]
0x140024348  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x14002434f  call    WPP_SF_Ds
0x140024354  jmp     loc_1400244C8
0x140024359  mov     ecx, [rsp+48h+ReturnLength]; cb
0x14002435d  call    cs:__imp_CoTaskMemAlloc
0x140024363  mov     rsi, rax
0x140024366  test    rax, rax
0x140024369  jnz     short loc_14002439E
0x14002436b  lea     ebx, [rax+0Eh]
0x14002436e  mov     rcx, cs:WPP_GLOBAL_Control
0x140024375  lea     rdx, WPP_GLOBAL_Control
0x14002437c  cmp     rcx, rdx
0x14002437f  jz      loc_1400244C8
0x140024385  test    byte ptr [rcx+1Ch], 8
0x140024389  jz      loc_1400244C8
0x14002438f  lea     edx, [rax+19h]
0x140024392  lea     rax, aPsysinfo; "pSysInfo"
0x140024399  jmp     loc_1400244B0
0x14002439e  mov     r8d, [rsp+48h+ReturnLength]; SystemInformationLength
0x1400243a3  lea     r9, [rsp+48h+ReturnLength]; ReturnLength
0x1400243a8  mov     rdx, rsi; SystemInformation
0x1400243ab  mov     ecx, 62h ; 'b'; SystemInformationClass
0x1400243b0  call    cs:__imp_NtQuerySystemInformation
0x1400243b6  test    eax, eax
0x1400243b8  jns     short loc_14002441C
0x1400243ba  mov     ecx, eax
0x1400243bc  call    WIN32_FROM_NTSTATUS
0x1400243c1  mov     ebx, eax
0x1400243c3  mov     rax, cs:WPP_GLOBAL_Control
0x1400243ca  lea     rdx, WPP_GLOBAL_Control
0x1400243d1  cmp     rax, rdx
0x1400243d4  jz      loc_1400244C8
0x1400243da  test    byte ptr [rax+1Ch], 8
0x1400243de  jz      loc_1400244C8
0x1400243e4  mov     r8d, [rsp+48h+ReturnLength]; SystemInformationLength
0x1400243e9  lea     r9, [rsp+48h+ReturnLength]; ReturnLength
0x1400243ee  mov     rdx, rsi; SystemInformation
0x1400243f1  mov     ecx, 62h ; 'b'; SystemInformationClass
0x1400243f6  call    cs:__imp_NtQuerySystemInformation
0x1400243fc  mov     edx, 1Ah
0x140024401  lea     rcx, aNtquerysystemi_0; "NtQuerySystemInformation( SystemSystemP"...
0x140024408  mov     [rsp+48h+var_28], rcx
0x14002440d  mov     r9d, eax
0x140024410  mov     rcx, cs:WPP_GLOBAL_Control
0x140024417  jmp     loc_140024344
0x14002441c  movzx   r9d, word ptr [rsi]
0x140024420  mov     edi, 104h
0x140024425  mov     r8, [rsi+8]; unsigned __int16 *
0x140024429  mov     edx, edi; unsigned __int64
0x14002442b  shr     r9, 1; unsigned __int64
0x14002442e  mov     rcx, r14; unsigned __int16 *
0x140024431  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x140024436  test    eax, eax
0x140024438  jns     short loc_14002447F
0x14002443a  mov     ecx, eax
0x14002443c  call    WIN32_FROM_HRESULT
0x140024441  mov     ebx, eax
0x140024443  mov     rax, cs:WPP_GLOBAL_Control
0x14002444a  lea     rdx, WPP_GLOBAL_Control
0x140024451  cmp     rax, rdx
0x140024454  jz      short loc_1400244C8
0x140024456  test    byte ptr [rax+1Ch], 8
0x14002445a  jz      short loc_1400244C8
0x14002445c  movzx   r9d, word ptr [rsi]
0x140024460  mov     edx, edi; unsigned __int64
0x140024462  mov     r8, [rsi+8]; unsigned __int16 *
0x140024466  mov     rcx, r14; unsigned __int16 *
0x140024469  shr     r9, 1; unsigned __int64
0x14002446c  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x140024471  mov     edx, 1Bh
0x140024476  lea     rcx, aStringcchcopyn_4; "::StringCchCopyN( pwszVolume, cchVolume"...
0x14002447d  jmp     short loc_140024408
0x14002447f  mov     ebx, ebp
0x140024481  mov     ebp, 1
0x140024486  jmp     short loc_1400244C8
0x140024488  mov     ebx, 57h ; 'W'
0x14002448d  mov     rcx, cs:WPP_GLOBAL_Control
0x140024494  lea     rdx, WPP_GLOBAL_Control
0x14002449b  cmp     rcx, rdx
0x14002449e  jz      short loc_1400244C8
0x1400244a0  test    byte ptr [rcx+1Ch], 8
0x1400244a4  jz      short loc_1400244C8
0x1400244a6  lea     edx, [rbx-41h]
0x1400244a9  lea     rax, aPwszvolume; "pwszVolume"
0x1400244b0  mov     rcx, [rcx+10h]
0x1400244b4  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x1400244bb  mov     r9d, ebx
0x1400244be  mov     [rsp+48h+var_28], rax
0x1400244c3  call    WPP_SF_Ds
0x1400244c8  mov     rcx, rsi; pv
0x1400244cb  call    cs:__imp_CoTaskMemFree
0x1400244d1  lea     rcx, aAsrgetsystemvo_4; "AsrGetSystemVolumeDevPath"
0x1400244d8  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x1400244dd  mov     ecx, ebx; dwErrCode
0x1400244df  call    cs:__imp_SetLastError
0x1400244e5  mov     rbx, [rsp+48h+arg_0]
0x1400244ea  mov     eax, ebp
0x1400244ec  mov     rbp, [rsp+48h+arg_10]
0x1400244f1  add     rsp, 30h
0x1400244f5  pop     r14
0x1400244f7  pop     rdi
0x1400244f8  pop     rsi
0x1400244f9  retn
```

# GatherSMBIOS(_SYSTEM_CONFIGURATION *)

- ea: `0x180015834`
- end: `0x180015ae2`
- name: `?GatherSMBIOS@@YAJPEAU_SYSTEM_CONFIGURATION@@@Z`
- size: `686`
- prototype: `__int64 __fastcall(struct _SYSTEM_CONFIGURATION *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015ae8`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x18000cad8`
- `0x180015834`
- `0x1800161e8`
- `0x18001650c`
- `0x1800180be`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800158f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800158f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015a75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015a75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800158e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015a67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800158e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015a67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800158b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800158b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015971`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemFirmwareTable` at `0x1800158ad`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemFirmwareTable` at `0x180015967`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemFirmwareTable` at `0x1800158ad`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemFirmwareTable` at `0x180015967`

## string_xrefs

- `0x180015873`: `SystemConfiguration`

## pseudocode

```c
__int64 __fastcall GatherSMBIOS(struct _SYSTEM_CONFIGURATION *a1, int a2)
{
  signed int v3; // ebx
  UINT SystemFirmwareTable; // eax
  SIZE_T v5; // rsi
  signed int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  HANDLE ProcessHeap; // rax
  _BYTE *v10; // rax
  _BYTE *v11; // r14
  __int64 *v12; // rdx
  signed int LastError; // eax
  bool v15; // zf
  const CHAR *v16; // r10
  __int64 v17; // rdx
  _BYTE *v18; // r10
  const CHAR *v19; // rsi
  int (*v20)(unsigned int, const unsigned __int16 *, void *const, struct _SYSTEM_CONFIGURATION *); // rax
  __int64 v21; // rdx
  HANDLE v22; // rax
  __int64 v23; // r9
  SIZE_T BufferSize; // [rsp+50h] [rbp+20h] BYREF
  unsigned __int64 v25; // [rsp+58h] [rbp+28h] BYREF

  LODWORD(BufferSize) = 0;
  v25 = 0;
  if ( a1 )
  {
    *((_DWORD *)a1 + 32) = -1;
    SystemFirmwareTable = GetSystemFirmwareTable(0x52534D42u, 0, 0, 0);
    v5 = SystemFirmwareTable;
    if ( SystemFirmwareTable )
    {
      ProcessHeap = GetProcessHeap();
      v10 = HeapAlloc(ProcessHeap, 8u, v5);
      v11 = v10;
      if ( !v10 )
      {
        v3 = -2147024882;
        goto LABEL_11;
      }
      memset_0(v10, 0, v5);
      v3 = ULongLongToULong(v5, (unsigned int *)&BufferSize);
      if ( v3 >= 0 )
      {
        if ( GetSystemFirmwareTable(0x52534D42u, 0, v11, BufferSize) )
        {
          v15 = v11[1] == 2;
          BufferSize = v5;
          if ( v15 && v11[2] >= 4u )
          {
            v3 = SizeTSub(v5, 8u, &BufferSize);
            if ( v3 >= 0 )
            {
              while ( BufferSize )
              {
                if ( (int)SizeTSub(BufferSize, *((unsigned __int8 *)v16 + 1), &BufferSize) < 0 )
                {
                  v3 = 0;
                  break;
                }
                v19 = &v18[v17];
                if ( *v18 )
                {
                  if ( *v18 == 1 )
                  {
                    v20 = SystemTableParser;
                  }
                  else if ( *v18 == 2 )
                  {
                    v20 = (int (*)(unsigned int, const unsigned __int16 *, void *const, struct _SYSTEM_CONFIGURATION *))BaseBoardTableParser;
                  }
                  else
                  {
                    v20 = 0;
                  }
                }
                else
                {
                  v20 = (int (*)(unsigned int, const unsigned __int16 *, void *const, struct _SYSTEM_CONFIGURATION *))BIOSTableParser;
                }
                v3 = ScanTable(v19, BufferSize, v18, a1, v20, &v25);
                if ( v3 < 0 )
                  break;
                v3 = SizeTSub(BufferSize, v25, &BufferSize);
                if ( v3 < 0 )
                  break;
                v16 = &v19[v21];
              }
            }
          }
        }
        else
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          if ( LastError >= 0 )
            LastError = -2147467259;
          v3 = LastError;
        }
      }
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v11);
    }
    else
    {
      v6 = GetLastError();
      v3 = v6;
      if ( v6 > 0 )
        v3 = (unsigned __int16)v6 | 0x80070000;
      if ( v3 >= 0 )
      {
        v3 = -2147467259;
        goto LABEL_42;
      }
    }
    if ( v3 != -2147024882 )
    {
      if ( v3 == -2147024809 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          return (unsigned int)v3;
        v23 = 2147942487LL;
        goto LABEL_44;
      }
      if ( v3 )
      {
LABEL_42:
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          return (unsigned int)v3;
        v23 = (unsigned int)v3;
LABEL_44:
        McTemplateU0sq_EventWriteTransfer(v8, v7, "GatherSMBIOS", v23);
        return (unsigned int)v3;
      }
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
        return (unsigned int)v3;
      v12 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_13:
      McTemplateU0s_EventWriteTransfer(v8, v12, "GatherSMBIOS");
      return (unsigned int)v3;
    }
LABEL_11:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      return (unsigned int)v3;
    v12 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
    goto LABEL_13;
  }
  v3 = -2147024809;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sqs_EventWriteTransfer(0, a2, (unsigned int)"GatherSMBIOS", -2147024809, (__int64)"SystemConfiguration");
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180015834  mov     [rsp-18h+arg_10], rbx
0x180015839  mov     [rsp-18h+arg_18], rsi
0x18001583e  push    rbp
0x18001583f  push    r14
0x180015841  push    r15
0x180015843  mov     rbp, rsp
0x180015846  sub     rsp, 30h
0x18001584a  mov     dword ptr [rbp+BufferSize], 0
0x180015851  mov     r15, rcx
0x180015854  mov     [rbp+arg_8], 0
0x18001585c  test    rcx, rcx
0x18001585f  jnz     short loc_180015896
0x180015861  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180015868  mov     ebx, 80070057h
0x18001586d  jz      loc_180015920
0x180015873  lea     rax, aSystemconfigur; "SystemConfiguration"
0x18001587a  mov     r9d, 80070057h
0x180015880  lea     r8, aGathersmbios; "GatherSMBIOS"
0x180015887  mov     [rsp+30h+var_10], rax
0x18001588c  call    McTemplateU0sqs_EventWriteTransfer
0x180015891  jmp     loc_180015920
0x180015896  mov     dword ptr [rcx+80h], 0FFFFFFFFh
0x1800158a0  xor     r9d, r9d; BufferSize
0x1800158a3  mov     ecx, 52534D42h; FirmwareTableProviderSignature
0x1800158a8  xor     r8d, r8d; pFirmwareTableBuffer
0x1800158ab  xor     edx, edx; FirmwareTableID
0x1800158ad  call    cs:__imp_GetSystemFirmwareTable
0x1800158b3  mov     esi, eax
0x1800158b5  test    eax, eax
0x1800158b7  jnz     short loc_1800158E0
0x1800158b9  call    cs:__imp_GetLastError
0x1800158bf  mov     ebx, eax
0x1800158c1  test    eax, eax
0x1800158c3  jle     short loc_1800158CE
0x1800158c5  movzx   ebx, ax
0x1800158c8  or      ebx, 80070000h
0x1800158ce  test    ebx, ebx
0x1800158d0  js      loc_180015A7B
0x1800158d6  mov     ebx, 80004005h
0x1800158db  jmp     loc_180015A93
0x1800158e0  call    cs:__imp_GetProcessHeap
0x1800158e6  mov     r8, rsi; dwBytes
0x1800158e9  mov     edx, 8; dwFlags
0x1800158ee  mov     rcx, rax; hHeap
0x1800158f1  call    cs:__imp_HeapAlloc
0x1800158f7  mov     r14, rax
0x1800158fa  test    rax, rax
0x1800158fd  jnz     short loc_180015936
0x1800158ff  mov     ebx, 8007000Eh
0x180015904  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001590b  jz      short loc_180015920
0x18001590d  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180015914  lea     r8, aGathersmbios; "GatherSMBIOS"
0x18001591b  call    McTemplateU0s_EventWriteTransfer
0x180015920  mov     rsi, [rsp+30h+arg_18]
0x180015925  mov     eax, ebx
0x180015927  mov     rbx, [rsp+30h+arg_10]
0x18001592c  add     rsp, 30h
0x180015930  pop     r15
0x180015932  pop     r14
0x180015934  pop     rbp
0x180015935  retn
0x180015936  mov     r8, rsi; Size
0x180015939  xor     edx, edx; Val
0x18001593b  mov     rcx, r14; void *
0x18001593e  call    memset_0
0x180015943  lea     rdx, [rbp+BufferSize]; unsigned int *
0x180015947  mov     rcx, rsi; unsigned __int64
0x18001594a  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18001594f  mov     ebx, eax
0x180015951  test    eax, eax
0x180015953  js      loc_180015A67
0x180015959  mov     r9d, dword ptr [rbp+BufferSize]; BufferSize
0x18001595d  mov     r8, r14; pFirmwareTableBuffer
0x180015960  xor     edx, edx; FirmwareTableID
0x180015962  mov     ecx, 52534D42h; FirmwareTableProviderSignature
0x180015967  call    cs:__imp_GetSystemFirmwareTable
0x18001596d  test    eax, eax
0x18001596f  jnz     short loc_180015994
0x180015971  call    cs:__imp_GetLastError
0x180015977  test    eax, eax
0x180015979  jle     short loc_180015983
0x18001597b  movzx   eax, ax
0x18001597e  or      eax, 80070000h
0x180015983  mov     ebx, 80004005h
0x180015988  test    eax, eax
0x18001598a  cmovns  eax, ebx
0x18001598d  mov     ebx, eax
0x18001598f  jmp     loc_180015A67
0x180015994  cmp     byte ptr [r14+1], 2
0x180015999  mov     [rbp+BufferSize], rsi
0x18001599d  jnz     loc_180015A67
0x1800159a3  cmp     byte ptr [r14+2], 4
0x1800159a8  jb      loc_180015A67
0x1800159ae  lea     r8, [rbp+BufferSize]; unsigned __int64 *
0x1800159b2  mov     edx, 8; unsigned __int64
0x1800159b7  mov     rcx, rsi; unsigned __int64
0x1800159ba  lea     r10, [r14+8]
0x1800159be  call    ?SizeTSub@@YAJ_K0PEA_K@Z; SizeTSub(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800159c3  mov     ebx, eax
0x1800159c5  test    eax, eax
0x1800159c7  js      loc_180015A67
0x1800159cd  mov     rcx, [rbp+BufferSize]; unsigned __int64
0x1800159d1  test    rcx, rcx
0x1800159d4  jz      loc_180015A67
0x1800159da  movzx   edx, byte ptr [r10+1]; unsigned __int64
0x1800159df  lea     r8, [rbp+BufferSize]; unsigned __int64 *
0x1800159e3  call    ?SizeTSub@@YAJ_K0PEA_K@Z; SizeTSub(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800159e8  test    eax, eax
0x1800159ea  js      short loc_180015A65
0x1800159ec  movzx   ecx, byte ptr [r10]
0x1800159f0  lea     rsi, [rdx+r10]
0x1800159f4  test    ecx, ecx
0x1800159f6  jz      short loc_180015A18
0x1800159f8  sub     ecx, 1
0x1800159fb  jz      short loc_180015A0F
0x1800159fd  cmp     ecx, 1
0x180015a00  jz      short loc_180015A06
0x180015a02  xor     eax, eax
0x180015a04  jmp     short loc_180015A1F
0x180015a06  lea     rax, ?BaseBoardTableParser@@YAJIPEBGQEAXPEAU_SYSTEM_CONFIGURATION@@@Z; BaseBoardTableParser(uint,ushort const *,void * const,_SYSTEM_CONFIGURATION *)
0x180015a0d  jmp     short loc_180015A1F
0x180015a0f  lea     rax, ?SystemTableParser@@YAJIPEBGQEAXPEAU_SYSTEM_CONFIGURATION@@@Z; SystemTableParser(uint,ushort const *,void * const,_SYSTEM_CONFIGURATION *)
0x180015a16  jmp     short loc_180015A1F
0x180015a18  lea     rax, ?BIOSTableParser@@YAJIPEBGQEAXPEAU_SYSTEM_CONFIGURATION@@@Z; BIOSTableParser(uint,ushort const *,void * const,_SYSTEM_CONFIGURATION *)
0x180015a1f  mov     rdx, [rbp+BufferSize]; unsigned __int64
0x180015a23  lea     rcx, [rbp+arg_8]
0x180015a27  mov     [rsp+30h+var_8], rcx; unsigned __int64 *
0x180015a2c  mov     r9, r15; struct _SYSTEM_CONFIGURATION *
0x180015a2f  mov     rcx, rsi; lpMultiByteStr
0x180015a32  mov     [rsp+30h+var_10], rax; int (*)(unsigned int, const unsigned __int16 *, void *const, struct _SYSTEM_CONFIGURATION *)
0x180015a37  mov     r8, r10; void *
0x180015a3a  call    ?ScanTable@@YAJPEBD_KQEAXPEAU_SYSTEM_CONFIGURATION@@P6AJIPEBG23@ZPEA_K@Z; ScanTable(char const *,unsigned __int64,void * const,_SYSTEM_CONFIGURATION *,long (*)(uint,ushort const *,void * const,_SYSTEM_CONFIGURATION *),unsigned __int64 *)
0x180015a3f  mov     ebx, eax
0x180015a41  test    eax, eax
0x180015a43  js      short loc_180015A67
0x180015a45  mov     rdx, [rbp+arg_8]; unsigned __int64
0x180015a49  lea     r8, [rbp+BufferSize]; unsigned __int64 *
0x180015a4d  mov     rcx, [rbp+BufferSize]; unsigned __int64
0x180015a51  call    ?SizeTSub@@YAJ_K0PEA_K@Z; SizeTSub(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180015a56  mov     ebx, eax
0x180015a58  test    eax, eax
0x180015a5a  js      short loc_180015A67
0x180015a5c  lea     r10, [rsi+rdx]
0x180015a60  jmp     loc_1800159CD
0x180015a65  xor     ebx, ebx
0x180015a67  call    cs:__imp_GetProcessHeap
0x180015a6d  mov     r8, r14; lpMem
0x180015a70  xor     edx, edx; dwFlags
0x180015a72  mov     rcx, rax; hHeap
0x180015a75  call    cs:__imp_HeapFree
0x180015a7b  cmp     ebx, 8007000Eh
0x180015a81  jz      loc_180015904
0x180015a87  cmp     ebx, 80070057h
0x180015a8d  jz      short loc_180015ACD
0x180015a8f  test    ebx, ebx
0x180015a91  jz      short loc_180015AB4
0x180015a93  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180015a9a  jz      loc_180015920
0x180015aa0  mov     r9d, ebx
0x180015aa3  lea     r8, aGathersmbios; "GatherSMBIOS"
0x180015aaa  call    McTemplateU0sq_EventWriteTransfer
0x180015aaf  jmp     loc_180015920
0x180015ab4  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180015abb  jz      loc_180015920
0x180015ac1  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180015ac8  jmp     loc_180015914
0x180015acd  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180015ad4  jz      loc_180015920
0x180015ada  mov     r9d, 80070057h
0x180015ae0  jmp     short loc_180015AA3
```

# UHReportBootGood

- ea: `0x14003aca4`
- end: `0x14003ae52`
- name: `UHReportBootGood`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14006cf20`

## callees

- `0x1400057f4`
- `0x14003aca4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003ad64`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003ad64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003adce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003adce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003ad53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003adc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003ad53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003adc0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14003ae1e`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14003ae1e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14003adff`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14003adff`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003ae15`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003ae15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ae27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ae27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003acfa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003acfa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003ada1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003ada1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003ae45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009e6a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003ae45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009e6a8`
- `api-ms-win-base-bootconfig-l1-1-0!NotifyBootConfigStatus` at `0x14003ae34`
- `api-ms-win-base-bootconfig-l1-1-0!NotifyBootConfigStatus` at `0x14003ae34`

## pseudocode

```c
int UHReportBootGood()
{
  BYTE *v0; // rax
  SIZE_T v1; // rbx
  HANDLE ProcessHeap; // rax
  BYTE *v3; // rbx
  HANDLE v4; // rax
  HANDLE v5; // rax
  void *v6; // rbx
  DWORD cbData; // [rsp+50h] [rbp+8h] BYREF
  DWORD Type; // [rsp+58h] [rbp+10h] BYREF
  DWORD ThreadId; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  ThreadId = 0;
  hKey = 0;
  Type = 0;
  cbData = 128;
  LODWORD(v0) = dword_1400D1A58;
  if ( dword_1400D1A58 == -1 )
  {
    LODWORD(v0) = RegOpenKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
                    0,
                    1u,
                    &hKey);
    if ( (_DWORD)v0 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LODWORD(v0) = WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        14,
                        WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids,
                        (unsigned int)v0);
      }
      goto LABEL_13;
    }
    v1 = 2LL * cbData;
    ProcessHeap = GetProcessHeap();
    v0 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v1);
    v3 = v0;
    if ( !v0 )
      goto LABEL_13;
    *(_WORD *)v0 = 48;
    RegQueryValueExW(hKey, L"ReportBootOk", 0, &Type, v0, &cbData);
    dword_1400D1A58 = *(_WORD *)v3 != 48;
    v4 = GetProcessHeap();
    HeapFree(v4, 0, v3);
    LODWORD(v0) = dword_1400D1A58;
  }
  if ( (_DWORD)v0 == 1 )
  {
    v5 = CreateThread(0, 0, ReportBootGoodThread, 0, 4u, &ThreadId);
    v6 = v5;
    if ( v5 )
    {
      SetThreadPriority(v5, -2);
      ResumeThread(v6);
      LODWORD(v0) = CloseHandle(v6);
    }
    else
    {
      LODWORD(v0) = NotifyBootConfigStatus(1);
    }
  }
LABEL_13:
  if ( hKey )
    LODWORD(v0) = RegCloseKey(hKey);
  return (int)v0;
}

```

## disassembly

```asm
0x14003aca4  mov     rax, rsp
0x14003aca7  push    rbx
0x14003aca8  push    rsi
0x14003aca9  sub     rsp, 38h
0x14003acad  mov     dword ptr [rax+18h], 0
0x14003acb4  mov     qword ptr [rax+20h], 0
0x14003acbc  mov     dword ptr [rax+10h], 0
0x14003acc3  mov     dword ptr [rax+8], 80h
0x14003acca  mov     eax, cs:dword_1400D1A58
0x14003acd0  cmp     eax, 0FFFFFFFFh
0x14003acd3  jnz     loc_14003ADDA
0x14003acd9  lea     rax, [rsp+48h+hKey]
0x14003acde  mov     [rsp+48h+phkResult], rax; phkResult
0x14003ace3  mov     r9d, 1; samDesired
0x14003ace9  xor     r8d, r8d; ulOptions
0x14003acec  lea     rdx, aSoftwareMicros_20; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14003acf3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003acfa  call    cs:__imp_RegOpenKeyExW
0x14003ad00  test    eax, eax
0x14003ad02  jz      short loc_14003AD4C
0x14003ad04  lea     rdx, WPP_GLOBAL_Control
0x14003ad0b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ad12  cmp     rcx, rdx
0x14003ad15  jz      loc_14003AE3B
0x14003ad1b  test    byte ptr [rcx+1Ch], 1
0x14003ad1f  jz      loc_14003AE3B
0x14003ad25  cmp     byte ptr [rcx+19h], 2
0x14003ad29  jb      loc_14003AE3B
0x14003ad2f  mov     edx, 0Eh
0x14003ad34  mov     r9d, eax
0x14003ad37  lea     r8, WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids
0x14003ad3e  mov     rcx, [rcx+10h]
0x14003ad42  call    WPP_SF_d
0x14003ad47  jmp     loc_14003AE3B
0x14003ad4c  mov     ebx, [rsp+48h+cbData]
0x14003ad50  add     rbx, rbx
0x14003ad53  call    cs:__imp_GetProcessHeap
0x14003ad59  mov     rcx, rax; hHeap
0x14003ad5c  mov     r8, rbx; dwBytes
0x14003ad5f  mov     edx, 8; dwFlags
0x14003ad64  call    cs:__imp_HeapAlloc
0x14003ad6a  mov     rbx, rax
0x14003ad6d  test    rax, rax
0x14003ad70  jz      loc_14003AE3B
0x14003ad76  mov     esi, 30h ; '0'
0x14003ad7b  mov     [rax], si
0x14003ad7e  lea     rax, [rsp+48h+cbData]
0x14003ad83  mov     [rsp+48h+lpcbData], rax; lpcbData
0x14003ad88  mov     [rsp+48h+phkResult], rbx; lpData
0x14003ad8d  lea     r9, [rsp+48h+Type]; lpType
0x14003ad92  xor     r8d, r8d; lpReserved
0x14003ad95  lea     rdx, aReportbootok; "ReportBootOk"
0x14003ad9c  mov     rcx, [rsp+48h+hKey]; hKey
0x14003ada1  call    cs:__imp_RegQueryValueExW
0x14003ada7  mov     cs:dword_1400D1A58, 0
0x14003adb1  cmp     [rbx], si
0x14003adb4  jz      short loc_14003ADC0
0x14003adb6  mov     cs:dword_1400D1A58, 1
0x14003adc0  call    cs:__imp_GetProcessHeap
0x14003adc6  mov     r8, rbx; lpMem
0x14003adc9  xor     edx, edx; dwFlags
0x14003adcb  mov     rcx, rax; hHeap
0x14003adce  call    cs:__imp_HeapFree
0x14003add4  mov     eax, cs:dword_1400D1A58
0x14003adda  cmp     eax, 1
0x14003addd  jnz     short loc_14003AE3B
0x14003addf  lea     rax, [rsp+48h+ThreadId]
0x14003ade4  mov     [rsp+48h+lpcbData], rax; lpThreadId
0x14003ade9  mov     dword ptr [rsp+48h+phkResult], 4; dwCreationFlags
0x14003adf1  xor     r9d, r9d; lpParameter
0x14003adf4  lea     r8, ?ReportBootGoodThread@@YAXPEAX@Z; lpStartAddress
0x14003adfb  xor     edx, edx; dwStackSize
0x14003adfd  xor     ecx, ecx; lpThreadAttributes
0x14003adff  call    cs:__imp_CreateThread
0x14003ae05  mov     rbx, rax
0x14003ae08  test    rax, rax
0x14003ae0b  jz      short loc_14003AE2F
0x14003ae0d  mov     edx, 0FFFFFFFEh; nPriority
0x14003ae12  mov     rcx, rax; hThread
0x14003ae15  call    cs:__imp_SetThreadPriority
0x14003ae1b  mov     rcx, rbx; hThread
0x14003ae1e  call    cs:__imp_ResumeThread
0x14003ae24  mov     rcx, rbx; hObject
0x14003ae27  call    cs:__imp_CloseHandle
0x14003ae2d  jmp     short loc_14003AE3B
0x14003ae2f  mov     ecx, 1; BootAcceptable
0x14003ae34  call    cs:__imp_NotifyBootConfigStatus
0x14003ae3a  nop
0x14003ae3b  mov     rcx, [rsp+48h+hKey]; hKey
0x14003ae40  test    rcx, rcx
0x14003ae43  jz      short loc_14003AE4B
0x14003ae45  call    cs:__imp_RegCloseKey
0x14003ae4b  add     rsp, 38h
0x14003ae4f  pop     rsi
0x14003ae50  pop     rbx
0x14003ae51  retn
0x14009e696  push    rbp
0x14009e698  sub     rsp, 30h
0x14009e69c  mov     rbp, rdx
0x14009e69f  mov     rcx, [rbp+68h]; hKey
0x14009e6a3  test    rcx, rcx
0x14009e6a6  jz      short loc_14009E6AF
0x14009e6a8  call    cs:__imp_RegCloseKey
0x14009e6ae  nop
0x14009e6af  add     rsp, 30h
0x14009e6b3  pop     rbp
0x14009e6b4  retn
```

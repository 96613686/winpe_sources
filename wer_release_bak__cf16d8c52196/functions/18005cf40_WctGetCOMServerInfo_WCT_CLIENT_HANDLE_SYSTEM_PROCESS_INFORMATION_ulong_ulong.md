# WctGetCOMServerInfo(_WCT_CLIENT_HANDLE *,_SYSTEM_PROCESS_INFORMATION *,ulong *,ulong *)

- ea: `0x18005cf40`
- end: `0x18005d1b1`
- name: `?WctGetCOMServerInfo@@YAXPEAU_WCT_CLIENT_HANDLE@@PEAU_SYSTEM_PROCESS_INFORMATION@@PEAK2@Z`
- size: `625`
- prototype: `void __fastcall(struct _WCT_CLIENT_HANDLE *, struct _SYSTEM_PROCESS_INFORMATION *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004e684`

## callees

- `0x180004bb4`
- `0x180007e10`
- `0x180007e34`
- `0x18001fe24`
- `0x18005cf40`
- `0x18005efd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18005d078`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18005d078`
- `ntdll!NtQueryInformationThread` at `0x18005d0a8`
- `ntdll!NtQueryInformationThread` at `0x18005d0a8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005d007`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005d007`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18005d0ee`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18005d127`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18005d0ee`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18005d127`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WctGetCOMServerInfo(
        struct _WCT_CLIENT_HANDLE *a1,
        struct _SYSTEM_PROCESS_INFORMATION *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  ULONG v4; // r14d
  wchar_t *v8; // rcx
  HANDLE v9; // rax
  HANDLE v10; // rbx
  struct _SYSTEM_PROCESS_INFORMATION *v11; // r15
  DWORD LowPart; // r12d
  HANDLE v13; // rax
  NTSTATUS v14; // edi
  ULONG ReturnLength; // [rsp+30h] [rbp-49h] BYREF
  int v16; // [rsp+34h] [rbp-45h] BYREF
  HANDLE v17; // [rsp+38h] [rbp-41h] BYREF
  HANDLE hProcess; // [rsp+40h] [rbp-39h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+48h] [rbp-31h] BYREF
  __int64 Buffer; // [rsp+50h] [rbp-29h] BYREF
  _OWORD ThreadInformation[7]; // [rsp+58h] [rbp-21h] BYREF

  v4 = 0;
  hProcess = 0;
  memset(ThreadInformation, 0, 48);
  v16 = 0;
  NumberOfBytesRead = 0;
  ReturnLength = 0;
  Buffer = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_4c32fa7a72a13340317baef891270170_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( dword_1800D9C84 )
  {
    v9 = OpenProcess(0x450u, 0, *a4);
    tlx::unique_any<tlx::file_handle_traits>::reset(&hProcess, v9);
    v10 = hProcess;
    if ( (unsigned __int64)hProcess + 1 > 1 && !(unsigned int)WctIsWow64(hProcess) )
    {
      while ( a2 )
      {
        if ( *a4 == LODWORD(a2->UniqueProcessId) )
        {
          v11 = a2 + 1;
          while ( v4 < a2->NumberOfThreads )
          {
            LowPart = v11->KernelTime.LowPart;
            v13 = OpenThread(0x40u, 0, LowPart);
            v17 = v13;
            if ( (unsigned __int64)v13 + 1 <= 1 )
              goto LABEL_26;
            v14 = NtQueryInformationThread(v13, ThreadBasicInformation, ThreadInformation, 0x30u, &ReturnLength);
            tlx::unique_any<tlx::file_handle_traits>::reset(&v17, 0);
            if ( v14 < 0
              || ReturnLength != 48
              || !ReadProcessMemory(
                    v10,
                    (LPCVOID)(*((_QWORD *)&ThreadInformation[0] + 1) + 5976LL),
                    &Buffer,
                    8u,
                    &NumberOfBytesRead)
              || NumberOfBytesRead != 8 )
            {
              goto LABEL_26;
            }
            if ( Buffer
              && ReadProcessMemory(v10, (LPCVOID)(Buffer + (unsigned int)dword_1800D9C84), &v16, 4u, 0)
              && v16 == *((_DWORD *)a1 + 4) )
            {
              *a3 = LowPart;
LABEL_26:
              tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v17);
              goto LABEL_27;
            }
            v11 = (struct _SYSTEM_PROCESS_INFORMATION *)((char *)v11 + 136);
            tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v17);
            ++v4;
          }
          break;
        }
        if ( !a2->NextEntryOffset )
          break;
        a2 = (struct _SYSTEM_PROCESS_INFORMATION *)((char *)a2 + a2->NextEntryOffset);
      }
    }
LABEL_27:
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_4c32fa7a72a13340317baef891270170_Traceguids, *a3);
  }
  else if ( v8 != (wchar_t *)&WPP_GLOBAL_Control && (v8[14] & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)v8 + 2), 41, WPP_4c32fa7a72a13340317baef891270170_Traceguids);
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hProcess);
}

```

## disassembly

```asm
0x18005cf40  mov     [rsp-8+arg_0], rcx
0x18005cf45  push    rbp
0x18005cf46  push    rbx
0x18005cf47  push    rsi
0x18005cf48  push    rdi
0x18005cf49  push    r12
0x18005cf4b  push    r13
0x18005cf4d  push    r14
0x18005cf4f  push    r15
0x18005cf51  lea     rbp, [rsp-1Fh]
0x18005cf56  sub     rsp, 98h
0x18005cf5d  xor     r14d, r14d
0x18005cf60  xorps   xmm0, xmm0
0x18005cf63  mov     [rbp+57h+hProcess], r14
0x18005cf67  mov     rdi, r9
0x18005cf6a  movups  [rbp+57h+ThreadInformation], xmm0
0x18005cf6e  mov     [rbp+57h+var_9C], r14d
0x18005cf72  mov     r13, r8
0x18005cf75  movups  [rbp+57h+var_68], xmm0
0x18005cf79  mov     [rbp+57h+NumberOfBytesRead], r14
0x18005cf7d  mov     rsi, rdx
0x18005cf80  movups  [rbp+57h+var_58], xmm0
0x18005cf84  mov     [rbp+57h+var_A0], r14d
0x18005cf88  mov     [rbp+57h+Buffer], r14
0x18005cf8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cf93  lea     rax, WPP_GLOBAL_Control
0x18005cf9a  cmp     rcx, rax
0x18005cf9d  jz      short loc_18005CFC7
0x18005cf9f  test    byte ptr [rcx+1Ch], 4
0x18005cfa3  jz      short loc_18005CFC7
0x18005cfa5  mov     rcx, [rcx+10h]
0x18005cfa9  lea     edx, [r14+28h]
0x18005cfad  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005cfb4  call    WPP_SF_
0x18005cfb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cfc0  lea     rax, WPP_GLOBAL_Control
0x18005cfc7  cmp     cs:dword_1800D9C84, r14d
0x18005cfce  jnz     short loc_18005CFFD
0x18005cfd0  cmp     rcx, rax
0x18005cfd3  jz      loc_18005D194
0x18005cfd9  test    byte ptr [rcx+1Ch], 4
0x18005cfdd  jz      loc_18005D194
0x18005cfe3  mov     rcx, [rcx+10h]
0x18005cfe7  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005cfee  mov     edx, 29h ; ')'
0x18005cff3  call    WPP_SF_
0x18005cff8  jmp     loc_18005D194
0x18005cffd  mov     r8d, [rdi]; dwProcessId
0x18005d000  xor     edx, edx; bInheritHandle
0x18005d002  mov     ecx, 450h; dwDesiredAccess
0x18005d007  call    cs:__imp_OpenProcess
0x18005d00d  mov     rdx, rax
0x18005d010  lea     rcx, [rbp+57h+hProcess]
0x18005d014  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005d019  mov     rbx, [rbp+57h+hProcess]
0x18005d01d  lea     rax, [rbx+1]
0x18005d021  cmp     rax, 1
0x18005d025  jbe     loc_18005D162
0x18005d02b  mov     rcx, rbx; void *
0x18005d02e  call    ?WctIsWow64@@YAHPEAX@Z; WctIsWow64(void *)
0x18005d033  test    eax, eax
0x18005d035  jnz     loc_18005D162
0x18005d03b  test    rsi, rsi
0x18005d03e  jz      loc_18005D162
0x18005d044  mov     eax, [rsi+50h]
0x18005d047  cmp     [rdi], eax
0x18005d049  jz      short loc_18005D05B
0x18005d04b  cmp     [rsi], r14d
0x18005d04e  jz      loc_18005D162
0x18005d054  mov     eax, [rsi]
0x18005d056  add     rsi, rax
0x18005d059  jmp     short loc_18005D03B
0x18005d05b  lea     r15, [rsi+100h]
0x18005d062  cmp     r14d, [rsi+4]
0x18005d066  jnb     loc_18005D162
0x18005d06c  mov     r12d, [r15+30h]
0x18005d070  xor     edx, edx; bInheritHandle
0x18005d072  mov     r8d, r12d; dwThreadId
0x18005d075  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18005d078  call    cs:__imp_OpenThread
0x18005d07e  mov     [rbp+57h+var_98], rax
0x18005d082  lea     rcx, [rax+1]
0x18005d086  cmp     rcx, 1
0x18005d08a  jbe     loc_18005D159
0x18005d090  lea     rcx, [rbp+57h+var_A0]
0x18005d094  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18005d09a  mov     [rsp+0D0h+ReturnLength], rcx; ReturnLength
0x18005d09f  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x18005d0a3  mov     rcx, rax; ThreadHandle
0x18005d0a6  xor     edx, edx; ThreadInformationClass
0x18005d0a8  call    cs:__imp_NtQueryInformationThread
0x18005d0ae  xor     edx, edx
0x18005d0b0  lea     rcx, [rbp+57h+var_98]
0x18005d0b4  mov     edi, eax
0x18005d0b6  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005d0bb  test    edi, edi
0x18005d0bd  js      loc_18005D159
0x18005d0c3  cmp     [rbp+57h+var_A0], 30h ; '0'
0x18005d0c7  jnz     loc_18005D159
0x18005d0cd  mov     rdx, qword ptr [rbp+57h+ThreadInformation+8]
0x18005d0d1  lea     rax, [rbp+57h+NumberOfBytesRead]
0x18005d0d5  add     rdx, 1758h; lpBaseAddress
0x18005d0dc  mov     [rsp+0D0h+ReturnLength], rax; lpNumberOfBytesRead
0x18005d0e1  mov     r9d, 8; nSize
0x18005d0e7  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18005d0eb  mov     rcx, rbx; hProcess
0x18005d0ee  call    cs:__imp_ReadProcessMemory
0x18005d0f4  test    eax, eax
0x18005d0f6  jz      short loc_18005D159
0x18005d0f8  cmp     [rbp+57h+NumberOfBytesRead], 8
0x18005d0fd  jnz     short loc_18005D159
0x18005d0ff  mov     rax, [rbp+57h+Buffer]
0x18005d103  test    rax, rax
0x18005d106  jz      short loc_18005D13D
0x18005d108  mov     edx, cs:dword_1800D9C84
0x18005d10e  lea     r8, [rbp+57h+var_9C]; lpBuffer
0x18005d112  add     rdx, rax; lpBaseAddress
0x18005d115  mov     [rsp+0D0h+ReturnLength], 0; lpNumberOfBytesRead
0x18005d11e  mov     r9d, 4; nSize
0x18005d124  mov     rcx, rbx; hProcess
0x18005d127  call    cs:__imp_ReadProcessMemory
0x18005d12d  test    eax, eax
0x18005d12f  jz      short loc_18005D13D
0x18005d131  mov     rax, [rbp+57h+arg_0]
0x18005d135  mov     eax, [rax+10h]
0x18005d138  cmp     [rbp+57h+var_9C], eax
0x18005d13b  jz      short loc_18005D155
0x18005d13d  lea     rcx, [rbp+57h+var_98]
0x18005d141  add     r15, 88h
0x18005d148  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18005d14d  inc     r14d
0x18005d150  jmp     loc_18005D062
0x18005d155  mov     [r13+0], r12d
0x18005d159  lea     rcx, [rbp+57h+var_98]
0x18005d15d  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18005d162  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d169  lea     rax, WPP_GLOBAL_Control
0x18005d170  cmp     rcx, rax
0x18005d173  jz      short loc_18005D194
0x18005d175  test    byte ptr [rcx+1Ch], 4
0x18005d179  jz      short loc_18005D194
0x18005d17b  mov     r9d, [r13+0]
0x18005d17f  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005d186  mov     rcx, [rcx+10h]
0x18005d18a  mov     edx, 2Ah ; '*'
0x18005d18f  call    WPP_SF_d
0x18005d194  lea     rcx, [rbp+57h+hProcess]
0x18005d198  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18005d19d  add     rsp, 98h
0x18005d1a4  pop     r15
0x18005d1a6  pop     r14
0x18005d1a8  pop     r13
0x18005d1aa  pop     r12
0x18005d1ac  pop     rdi
0x18005d1ad  pop     rsi
0x18005d1ae  pop     rbx
0x18005d1af  pop     rbp
0x18005d1b0  retn
```

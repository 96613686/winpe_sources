# WctGetCOMServerInfo(_WCT_CLIENT_HANDLE *,_SYSTEM_PROCESS_INFORMATION *,ulong *,ulong *)

- ea: `0x18005f4b0`
- end: `0x18005f740`
- name: `?WctGetCOMServerInfo@@YAXPEAU_WCT_CLIENT_HANDLE@@PEAU_SYSTEM_PROCESS_INFORMATION@@PEAK2@Z`
- size: `656`
- prototype: `void __fastcall(struct _WCT_CLIENT_HANDLE *, struct _SYSTEM_PROCESS_INFORMATION *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180050a48`

## callees

- `0x180004c64`
- `0x180007fd8`
- `0x180008004`
- `0x180020680`
- `0x18005f4b0`
- `0x1800616b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18005f5ee`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18005f5ee`
- `ntdll!NtQueryInformationThread` at `0x18005f624`
- `ntdll!NtQueryInformationThread` at `0x18005f624`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005f577`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005f577`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18005f670`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18005f6af`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18005f670`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18005f6af`

## pseudocode

```c
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( dword_1800DEC84 )
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
              && ReadProcessMemory(v10, (LPCVOID)(Buffer + (unsigned int)dword_1800DEC84), &v16, 4u, 0)
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, *a3);
  }
  else if ( v8 != (wchar_t *)&WPP_GLOBAL_Control && (v8[14] & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)v8 + 2), 41, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hProcess);
}

```

## disassembly

```asm
0x18005f4b0  mov     [rsp-8+arg_0], rcx
0x18005f4b5  push    rbp
0x18005f4b6  push    rbx
0x18005f4b7  push    rsi
0x18005f4b8  push    rdi
0x18005f4b9  push    r12
0x18005f4bb  push    r13
0x18005f4bd  push    r14
0x18005f4bf  push    r15
0x18005f4c1  lea     rbp, [rsp-1Fh]
0x18005f4c6  sub     rsp, 98h
0x18005f4cd  xor     r14d, r14d
0x18005f4d0  xorps   xmm0, xmm0
0x18005f4d3  mov     [rbp+57h+hProcess], r14
0x18005f4d7  mov     rdi, r9
0x18005f4da  movups  [rbp+57h+ThreadInformation], xmm0
0x18005f4de  mov     [rbp+57h+var_9C], r14d
0x18005f4e2  mov     r13, r8
0x18005f4e5  movups  [rbp+57h+var_68], xmm0
0x18005f4e9  mov     [rbp+57h+NumberOfBytesRead], r14
0x18005f4ed  mov     rsi, rdx
0x18005f4f0  movups  [rbp+57h+var_58], xmm0
0x18005f4f4  mov     [rbp+57h+var_A0], r14d
0x18005f4f8  mov     [rbp+57h+Buffer], r14
0x18005f4fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f503  lea     rax, WPP_GLOBAL_Control
0x18005f50a  cmp     rcx, rax
0x18005f50d  jz      short loc_18005F537
0x18005f50f  test    byte ptr [rcx+1Ch], 4
0x18005f513  jz      short loc_18005F537
0x18005f515  mov     rcx, [rcx+10h]
0x18005f519  lea     edx, [r14+28h]
0x18005f51d  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005f524  call    WPP_SF_
0x18005f529  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f530  lea     rax, WPP_GLOBAL_Control
0x18005f537  cmp     cs:dword_1800DEC84, r14d
0x18005f53e  jnz     short loc_18005F56D
0x18005f540  cmp     rcx, rax
0x18005f543  jz      loc_18005F722
0x18005f549  test    byte ptr [rcx+1Ch], 4
0x18005f54d  jz      loc_18005F722
0x18005f553  mov     rcx, [rcx+10h]
0x18005f557  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005f55e  mov     edx, 29h ; ')'
0x18005f563  call    WPP_SF_
0x18005f568  jmp     loc_18005F722
0x18005f56d  mov     r8d, [rdi]; dwProcessId
0x18005f570  xor     edx, edx; bInheritHandle
0x18005f572  mov     ecx, 450h; dwDesiredAccess
0x18005f577  call    cs:__imp_OpenProcess
0x18005f57e  nop     dword ptr [rax+rax+00h]
0x18005f583  mov     rdx, rax
0x18005f586  lea     rcx, [rbp+57h+hProcess]
0x18005f58a  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005f58f  mov     rbx, [rbp+57h+hProcess]
0x18005f593  lea     rax, [rbx+1]
0x18005f597  cmp     rax, 1
0x18005f59b  jbe     loc_18005F6F0
0x18005f5a1  mov     rcx, rbx; void *
0x18005f5a4  call    ?WctIsWow64@@YAHPEAX@Z; WctIsWow64(void *)
0x18005f5a9  test    eax, eax
0x18005f5ab  jnz     loc_18005F6F0
0x18005f5b1  test    rsi, rsi
0x18005f5b4  jz      loc_18005F6F0
0x18005f5ba  mov     eax, [rsi+50h]
0x18005f5bd  cmp     [rdi], eax
0x18005f5bf  jz      short loc_18005F5D1
0x18005f5c1  cmp     [rsi], r14d
0x18005f5c4  jz      loc_18005F6F0
0x18005f5ca  mov     eax, [rsi]
0x18005f5cc  add     rsi, rax
0x18005f5cf  jmp     short loc_18005F5B1
0x18005f5d1  lea     r15, [rsi+100h]
0x18005f5d8  cmp     r14d, [rsi+4]
0x18005f5dc  jnb     loc_18005F6F0
0x18005f5e2  mov     r12d, [r15+30h]
0x18005f5e6  xor     edx, edx; bInheritHandle
0x18005f5e8  mov     r8d, r12d; dwThreadId
0x18005f5eb  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18005f5ee  call    cs:__imp_OpenThread
0x18005f5f5  nop     dword ptr [rax+rax+00h]
0x18005f5fa  mov     [rbp+57h+var_98], rax
0x18005f5fe  lea     rcx, [rax+1]
0x18005f602  cmp     rcx, 1
0x18005f606  jbe     loc_18005F6E7
0x18005f60c  lea     rcx, [rbp+57h+var_A0]
0x18005f610  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18005f616  mov     [rsp+0D0h+ReturnLength], rcx; ReturnLength
0x18005f61b  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x18005f61f  mov     rcx, rax; ThreadHandle
0x18005f622  xor     edx, edx; ThreadInformationClass
0x18005f624  call    cs:__imp_NtQueryInformationThread
0x18005f62b  nop     dword ptr [rax+rax+00h]
0x18005f630  xor     edx, edx
0x18005f632  lea     rcx, [rbp+57h+var_98]
0x18005f636  mov     edi, eax
0x18005f638  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005f63d  test    edi, edi
0x18005f63f  js      loc_18005F6E7
0x18005f645  cmp     [rbp+57h+var_A0], 30h ; '0'
0x18005f649  jnz     loc_18005F6E7
0x18005f64f  mov     rdx, qword ptr [rbp+57h+ThreadInformation+8]
0x18005f653  lea     rax, [rbp+57h+NumberOfBytesRead]
0x18005f657  add     rdx, 1758h; lpBaseAddress
0x18005f65e  mov     [rsp+0D0h+ReturnLength], rax; lpNumberOfBytesRead
0x18005f663  mov     r9d, 8; nSize
0x18005f669  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18005f66d  mov     rcx, rbx; hProcess
0x18005f670  call    cs:__imp_ReadProcessMemory
0x18005f677  nop     dword ptr [rax+rax+00h]
0x18005f67c  test    eax, eax
0x18005f67e  jz      short loc_18005F6E7
0x18005f680  cmp     [rbp+57h+NumberOfBytesRead], 8
0x18005f685  jnz     short loc_18005F6E7
0x18005f687  mov     rax, [rbp+57h+Buffer]
0x18005f68b  test    rax, rax
0x18005f68e  jz      short loc_18005F6CB
0x18005f690  mov     edx, cs:dword_1800DEC84
0x18005f696  lea     r8, [rbp+57h+var_9C]; lpBuffer
0x18005f69a  add     rdx, rax; lpBaseAddress
0x18005f69d  mov     [rsp+0D0h+ReturnLength], 0; lpNumberOfBytesRead
0x18005f6a6  mov     r9d, 4; nSize
0x18005f6ac  mov     rcx, rbx; hProcess
0x18005f6af  call    cs:__imp_ReadProcessMemory
0x18005f6b6  nop     dword ptr [rax+rax+00h]
0x18005f6bb  test    eax, eax
0x18005f6bd  jz      short loc_18005F6CB
0x18005f6bf  mov     rax, [rbp+57h+arg_0]
0x18005f6c3  mov     eax, [rax+10h]
0x18005f6c6  cmp     [rbp+57h+var_9C], eax
0x18005f6c9  jz      short loc_18005F6E3
0x18005f6cb  lea     rcx, [rbp+57h+var_98]
0x18005f6cf  add     r15, 88h
0x18005f6d6  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18005f6db  inc     r14d
0x18005f6de  jmp     loc_18005F5D8
0x18005f6e3  mov     [r13+0], r12d
0x18005f6e7  lea     rcx, [rbp+57h+var_98]
0x18005f6eb  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18005f6f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f6f7  lea     rax, WPP_GLOBAL_Control
0x18005f6fe  cmp     rcx, rax
0x18005f701  jz      short loc_18005F722
0x18005f703  test    byte ptr [rcx+1Ch], 4
0x18005f707  jz      short loc_18005F722
0x18005f709  mov     r9d, [r13+0]
0x18005f70d  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005f714  mov     rcx, [rcx+10h]
0x18005f718  mov     edx, 2Ah ; '*'
0x18005f71d  call    WPP_SF_d
0x18005f722  lea     rcx, [rbp+57h+hProcess]
0x18005f726  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18005f72b  add     rsp, 98h
0x18005f732  pop     r15
0x18005f734  pop     r14
0x18005f736  pop     r13
0x18005f738  pop     r12
0x18005f73a  pop     rdi
0x18005f73b  pop     rsi
0x18005f73c  pop     rbx
0x18005f73d  pop     rbp
0x18005f73e  retn
```

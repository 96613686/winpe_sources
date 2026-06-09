# CEventUI::UploadUIInitiate(void)

- ea: `0x180008b90`
- end: `0x180008cc8`
- name: `?UploadUIInitiate@CEventUI@@AEAAJXZ`
- size: `312`
- prototype: `__int64 __fastcall(CEventUI *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006e8c`

## callees

- `0x180003604`
- `0x180003fe4`
- `0x180008b90`
- `0x1800090f8`
- `0x18000983c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008bfa`
- `KERNEL32!GetLastError` at `0x180008c1f`
- `KERNEL32!GetLastError` at `0x180008c8f`
- `KERNEL32!GetLastError` at `0x180008bfa`
- `KERNEL32!GetLastError` at `0x180008c1f`
- `KERNEL32!GetLastError` at `0x180008c8f`
- `KERNEL32!CreateThread` at `0x180008c58`
- `KERNEL32!CreateThread` at `0x180008c58`
- `KERNEL32!CreateEventW` at `0x180008bc4`
- `KERNEL32!CreateEventW` at `0x180008bc4`

## pseudocode

```c
__int64 __fastcall CEventUI::UploadUIInitiate(const unsigned __int16 **this)
{
  _QWORD *v2; // rdi
  HANDLE EventW; // rax
  DWORD LastError; // eax
  __int64 v5; // rdx
  DWORD v6; // eax
  HANDLE v8; // rax
  unsigned int v9; // edx
  bool v10; // r9
  const unsigned __int16 *v11; // rcx
  DWORD dwCreationFlags; // [rsp+20h] [rbp-28h]
  __int128 v13; // [rsp+30h] [rbp-18h] BYREF
  DWORD ThreadId; // [rsp+50h] [rbp+8h] BYREF

  ThreadId = 0;
  v2 = this + 20;
  v13 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(v2, EventW);
  if ( *v2 == -1 || *v2 == 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    LastError = GetLastError();
    v5 = 46;
LABEL_5:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids, LastError);
LABEL_6:
    v6 = GetLastError();
    return ERROR_HR_FROM_WIN32(v6);
  }
  v8 = CreateThread(0, 0, CEventUI::Static_UploadUIThread, this, 0, &ThreadId);
  tlx::unique_any<tlx::file_handle_traits>::reset(this + 19, v8);
  v11 = this[19];
  if ( (unsigned __int64)v11 + 1 <= 1 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_6;
    LastError = GetLastError();
    v5 = 47;
    goto LABEL_5;
  }
  *(_QWORD *)&v13 = *v2;
  *((_QWORD *)&v13 + 1) = v11;
  UtilWaitForMultipleObjects(v11, v9, (void **const)&v13, v10, dwCreationFlags);
  return 0;
}

```

## disassembly

```asm
0x180008b90  mov     rax, rsp
0x180008b93  mov     [rax+10h], rbx
0x180008b97  mov     [rax+18h], rsi
0x180008b9b  push    rdi
0x180008b9c  sub     rsp, 40h
0x180008ba0  xor     r9d, r9d; lpName
0x180008ba3  mov     dword ptr [rax+8], 0
0x180008baa  mov     rsi, rcx
0x180008bad  lea     rdi, [rcx+0A0h]
0x180008bb4  xorps   xmm0, xmm0
0x180008bb7  xor     r8d, r8d; bInitialState
0x180008bba  xor     ecx, ecx; lpEventAttributes
0x180008bbc  lea     edx, [r9+1]; bManualReset
0x180008bc0  movups  xmmword ptr [rax-18h], xmm0
0x180008bc4  call    cs:__imp_CreateEventW
0x180008bca  mov     rdx, rax
0x180008bcd  mov     rcx, rdi
0x180008bd0  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180008bd5  mov     rax, [rdi]
0x180008bd8  inc     rax
0x180008bdb  cmp     rax, 1
0x180008bdf  ja      short loc_180008C31
0x180008be1  mov     rcx, cs:WPP_GLOBAL_Control
0x180008be8  lea     rax, WPP_GLOBAL_Control
0x180008bef  cmp     rcx, rax
0x180008bf2  jz      short loc_180008C1F
0x180008bf4  test    byte ptr [rcx+1Ch], 1
0x180008bf8  jz      short loc_180008C1F
0x180008bfa  call    cs:__imp_GetLastError
0x180008c00  mov     edx, 2Eh ; '.'
0x180008c05  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c0c  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x180008c13  mov     r9d, eax
0x180008c16  mov     rcx, [rcx+10h]
0x180008c1a  call    WPP_SF_d
0x180008c1f  call    cs:__imp_GetLastError
0x180008c25  mov     ecx, eax; unsigned int
0x180008c27  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180008c2c  jmp     loc_180008CB8
0x180008c31  lea     rax, [rsp+48h+ThreadId]
0x180008c36  mov     r9, rsi; lpParameter
0x180008c39  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x180008c3e  lea     r8, ?Static_UploadUIThread@CEventUI@@CAKPEAX@Z; lpStartAddress
0x180008c45  xor     edx, edx; dwStackSize
0x180008c47  mov     [rsp+48h+dwCreationFlags], 0; unsigned int
0x180008c4f  xor     ecx, ecx; lpThreadAttributes
0x180008c51  lea     rbx, [rsi+98h]
0x180008c58  call    cs:__imp_CreateThread
0x180008c5e  mov     rdx, rax
0x180008c61  mov     rcx, rbx
0x180008c64  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180008c69  mov     rcx, [rbx]; unsigned __int16 *
0x180008c6c  lea     rax, [rcx+1]
0x180008c70  cmp     rax, 1
0x180008c74  ja      short loc_180008C9F
0x180008c76  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c7d  lea     rax, WPP_GLOBAL_Control
0x180008c84  cmp     rcx, rax
0x180008c87  jz      short loc_180008C1F
0x180008c89  test    byte ptr [rcx+1Ch], 1
0x180008c8d  jz      short loc_180008C1F
0x180008c8f  call    cs:__imp_GetLastError
0x180008c95  mov     edx, 2Fh ; '/'
0x180008c9a  jmp     loc_180008C05
0x180008c9f  mov     rax, [rdi]
0x180008ca2  lea     r8, [rsp+48h+var_18]; void **
0x180008ca7  mov     [rsp+48h+var_18], rax
0x180008cac  mov     [rsp+48h+var_10], rcx
0x180008cb1  call    ?UtilWaitForMultipleObjects@@YAKPEBGKQEAPEAX_NK@Z; UtilWaitForMultipleObjects(ushort const *,ulong,void * * const,bool,ulong)
0x180008cb6  xor     eax, eax
0x180008cb8  mov     rbx, [rsp+48h+arg_8]
0x180008cbd  mov     rsi, [rsp+48h+arg_10]
0x180008cc2  add     rsp, 40h
0x180008cc6  pop     rdi
0x180008cc7  retn
```

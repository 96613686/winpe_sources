# _InitializeSyncHandle

- ea: `0x18002eb40`
- end: `0x18002ec66`
- name: `_InitializeSyncHandle`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800271fc`
- `0x18002e8ac`
- `0x18002eb40`
- `0x1800301bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002eb77`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002eb77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec23`

## pseudocode

```c
__int64 __fastcall InitializeSyncHandle(_QWORD *a1)
{
  HANDLE Semaphore; // rax
  HANDLE v4; // rdi
  DWORD LastError; // eax
  __int64 v6; // rdx

  if ( !a1 )
    return 87;
  Semaphore = CreateSemaphoreExW(0, 0, 0x7FFFFFFF, 0, 0, 0x1F0003u);
  v4 = Semaphore;
  if ( !Semaphore )
  {
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_16;
    LastError = GetLastError();
    v6 = 19;
    goto LABEL_15;
  }
  if ( (unsigned int)CSsdpNotifyRequestManager::HrAddNotifySemaphoreToList(
                       &CSsdpNotifyRequestManager::s_instance,
                       Semaphore) )
  {
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_16;
    LastError = GetLastError();
    v6 = 17;
LABEL_15:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids, LastError);
LABEL_16:
    *a1 = 0;
    return 8;
  }
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids);
  *a1 = v4;
  return 0;
}

```

## disassembly

```asm
0x18002eb40  mov     [rsp+arg_0], rbx
0x18002eb45  push    rdi
0x18002eb46  sub     rsp, 30h
0x18002eb4a  mov     rbx, rcx
0x18002eb4d  test    rcx, rcx
0x18002eb50  jnz     short loc_18002EB5A
0x18002eb52  lea     eax, [rcx+57h]
0x18002eb55  jmp     loc_18002EC5A
0x18002eb5a  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18002eb62  xor     r9d, r9d; lpName
0x18002eb65  xor     edx, edx; lInitialCount
0x18002eb67  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18002eb6f  xor     ecx, ecx; lpSemaphoreAttributes
0x18002eb71  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18002eb77  call    cs:__imp_CreateSemaphoreExW
0x18002eb7e  nop     dword ptr [rax+rax+00h]
0x18002eb83  mov     rdi, rax
0x18002eb86  test    rax, rax
0x18002eb89  jz      short loc_18002EC0A
0x18002eb8b  mov     rdx, rax; void *
0x18002eb8e  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; lpCriticalSection
0x18002eb95  call    ?HrAddNotifySemaphoreToList@CSsdpNotifyRequestManager@@QEAAJPEAX@Z; CSsdpNotifyRequestManager::HrAddNotifySemaphoreToList(void *)
0x18002eb9a  test    eax, eax
0x18002eb9c  jz      short loc_18002EBD2
0x18002eb9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eba5  lea     rax, WPP_GLOBAL_Control
0x18002ebac  cmp     rcx, rax
0x18002ebaf  jz      loc_18002EC4E
0x18002ebb5  test    byte ptr [rcx+1Ch], 1
0x18002ebb9  jz      loc_18002EC4E
0x18002ebbf  call    cs:__imp_GetLastError
0x18002ebc6  nop     dword ptr [rax+rax+00h]
0x18002ebcb  mov     edx, 11h
0x18002ebd0  jmp     short loc_18002EC34
0x18002ebd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ebd9  lea     rax, WPP_GLOBAL_Control
0x18002ebe0  cmp     rcx, rax
0x18002ebe3  jz      short loc_18002EC03
0x18002ebe5  test    byte ptr [rcx+1Ch], 8
0x18002ebe9  jz      short loc_18002EC03
0x18002ebeb  mov     rcx, [rcx+10h]
0x18002ebef  lea     r8, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids
0x18002ebf6  mov     edx, 12h
0x18002ebfb  mov     r9, rdi
0x18002ebfe  call    WPP_SF_q
0x18002ec03  mov     [rbx], rdi
0x18002ec06  xor     eax, eax
0x18002ec08  jmp     short loc_18002EC5A
0x18002ec0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec11  lea     rax, WPP_GLOBAL_Control
0x18002ec18  cmp     rcx, rax
0x18002ec1b  jz      short loc_18002EC4E
0x18002ec1d  test    byte ptr [rcx+1Ch], 1
0x18002ec21  jz      short loc_18002EC4E
0x18002ec23  call    cs:__imp_GetLastError
0x18002ec2a  nop     dword ptr [rax+rax+00h]
0x18002ec2f  mov     edx, 13h
0x18002ec34  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec3b  lea     r8, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids
0x18002ec42  mov     r9d, eax
0x18002ec45  mov     rcx, [rcx+10h]
0x18002ec49  call    WPP_SF_d
0x18002ec4e  mov     qword ptr [rbx], 0
0x18002ec55  mov     eax, 8
0x18002ec5a  mov     rbx, [rsp+38h+arg_0]
0x18002ec5f  add     rsp, 30h
0x18002ec63  pop     rdi
0x18002ec64  retn
```

# _InitializeSyncHandle

- ea: `0x18002cb40`
- end: `0x18002cc53`
- name: `_InitializeSyncHandle`
- size: `275`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800255a8`
- `0x18002c8cc`
- `0x18002cb40`
- `0x18002e088`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002cb77`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002cb77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cbb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cbb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc17`

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
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids, v4);
  *a1 = v4;
  return 0;
}

```

## disassembly

```asm
0x18002cb40  mov     [rsp+arg_0], rbx
0x18002cb45  push    rdi
0x18002cb46  sub     rsp, 30h
0x18002cb4a  mov     rbx, rcx
0x18002cb4d  test    rcx, rcx
0x18002cb50  jnz     short loc_18002CB5A
0x18002cb52  lea     eax, [rcx+57h]
0x18002cb55  jmp     loc_18002CC48
0x18002cb5a  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18002cb62  xor     r9d, r9d; lpName
0x18002cb65  xor     edx, edx; lInitialCount
0x18002cb67  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18002cb6f  xor     ecx, ecx; lpSemaphoreAttributes
0x18002cb71  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18002cb77  call    cs:__imp_CreateSemaphoreExW
0x18002cb7d  mov     rdi, rax
0x18002cb80  test    rax, rax
0x18002cb83  jz      short loc_18002CBFE
0x18002cb85  mov     rdx, rax; void *
0x18002cb88  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; lpCriticalSection
0x18002cb8f  call    ?HrAddNotifySemaphoreToList@CSsdpNotifyRequestManager@@QEAAJPEAX@Z; CSsdpNotifyRequestManager::HrAddNotifySemaphoreToList(void *)
0x18002cb94  test    eax, eax
0x18002cb96  jz      short loc_18002CBC6
0x18002cb98  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb9f  lea     rax, WPP_GLOBAL_Control
0x18002cba6  cmp     rcx, rax
0x18002cba9  jz      loc_18002CC3C
0x18002cbaf  test    byte ptr [rcx+1Ch], 1
0x18002cbb3  jz      loc_18002CC3C
0x18002cbb9  call    cs:__imp_GetLastError
0x18002cbbf  mov     edx, 11h
0x18002cbc4  jmp     short loc_18002CC22
0x18002cbc6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbcd  lea     rax, WPP_GLOBAL_Control
0x18002cbd4  cmp     rcx, rax
0x18002cbd7  jz      short loc_18002CBF7
0x18002cbd9  test    byte ptr [rcx+1Ch], 8
0x18002cbdd  jz      short loc_18002CBF7
0x18002cbdf  mov     rcx, [rcx+10h]
0x18002cbe3  lea     r8, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids
0x18002cbea  mov     edx, 12h
0x18002cbef  mov     r9, rdi
0x18002cbf2  call    WPP_SF_q
0x18002cbf7  mov     [rbx], rdi
0x18002cbfa  xor     eax, eax
0x18002cbfc  jmp     short loc_18002CC48
0x18002cbfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc05  lea     rax, WPP_GLOBAL_Control
0x18002cc0c  cmp     rcx, rax
0x18002cc0f  jz      short loc_18002CC3C
0x18002cc11  test    byte ptr [rcx+1Ch], 1
0x18002cc15  jz      short loc_18002CC3C
0x18002cc17  call    cs:__imp_GetLastError
0x18002cc1d  mov     edx, 13h
0x18002cc22  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc29  lea     r8, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids
0x18002cc30  mov     r9d, eax
0x18002cc33  mov     rcx, [rcx+10h]
0x18002cc37  call    WPP_SF_d
0x18002cc3c  mov     qword ptr [rbx], 0
0x18002cc43  mov     eax, 8
0x18002cc48  mov     rbx, [rsp+38h+arg_0]
0x18002cc4d  add     rsp, 30h
0x18002cc51  pop     rdi
0x18002cc52  retn
```

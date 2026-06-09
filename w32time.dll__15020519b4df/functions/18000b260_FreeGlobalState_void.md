# FreeGlobalState(void)

- ea: `0x18000b260`
- end: `0x18000b48c`
- name: `?FreeGlobalState@@YAXXZ`
- size: `556`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009a80`
- `0x180039100`

## callees

- `0x180009204`
- `0x18000b260`
- `0x18003dd2c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b3fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b414`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b42c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b444`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b45c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b3fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b414`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b42c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b444`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b45c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b282`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b2a8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b2cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b2ee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b282`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b2a8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b2cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b2ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3d3`

## pseudocode

```c
void FreeGlobalState(void)
{
  __int64 v0; // rbx
  HANDLE v1; // rcx
  HANDLE hObject[16]; // [rsp+20h] [rbp-29h]

  if ( g_state )
  {
    DeleteCriticalSection(&CriticalSection);
    g_state = 0;
  }
  if ( byte_1800A4608 )
  {
    DeleteCriticalSection(&stru_1800A45E0);
    byte_1800A4608 = 0;
  }
  if ( byte_1800A4638 )
  {
    DeleteCriticalSection(&stru_1800A4610);
    byte_1800A4638 = 0;
  }
  if ( byte_1800A4688 )
  {
    DeleteCriticalSection(&stru_1800A4660);
    byte_1800A4688 = 0;
  }
  v0 = 0;
  hObject[0] = hEvent;
  hObject[1] = qword_1800A36D0;
  hObject[2] = qword_1800A36D8;
  hObject[3] = qword_1800A36E8;
  hObject[4] = qword_1800A36F0;
  hObject[5] = qword_1800A36F8;
  hObject[6] = qword_1800A3710;
  hObject[7] = qword_1800A3718;
  hObject[8] = qword_1800A3700;
  hObject[9] = qword_1800A3708;
  hObject[10] = NotificationEventHandle;
  hObject[11] = qword_1800A3730;
  hObject[12] = qword_1800A3738;
  hObject[13] = qword_1800A3740;
  hObject[14] = qword_1800A3748;
  do
  {
    v1 = hObject[v0];
    if ( v1 )
      CloseHandle(v1);
    ++v0;
  }
  while ( v0 != 15 );
  if ( hThread )
    CloseHandle(hThread);
  if ( qword_1800A42F0 )
    FreeConfigInfo((HLOCAL *)qword_1800A42F0);
  if ( Src )
    LocalFree(Src);
  if ( *(&Src + 1) )
    LocalFree(*(&Src + 1));
  if ( Base )
    LocalFree(Base);
  if ( *(&Base + 1) )
    LocalFree(*(&Base + 1));
  if ( qword_1800A4718 )
    LocalFree(qword_1800A4718);
  memset_0(&g_state, 0, 0x10E0u);
}

```

## disassembly

```asm
0x18000b260  mov     [rsp-8+arg_0], rbx
0x18000b265  push    rbp
0x18000b266  lea     rbp, [rsp-57h]
0x18000b26b  sub     rsp, 0A0h
0x18000b272  cmp     cs:?g_state@@3UStateInfo@@A, 0; StateInfo g_state
0x18000b279  jz      short loc_18000B298
0x18000b27b  lea     rcx, CriticalSection; lpCriticalSection
0x18000b282  call    cs:__imp_DeleteCriticalSection
0x18000b289  nop     dword ptr [rax+rax+00h]
0x18000b28e  mov     cs:?g_state@@3UStateInfo@@A, 0; StateInfo g_state
0x18000b298  cmp     cs:byte_1800A4608, 0
0x18000b29f  jz      short loc_18000B2BB
0x18000b2a1  lea     rcx, stru_1800A45E0; lpCriticalSection
0x18000b2a8  call    cs:__imp_DeleteCriticalSection
0x18000b2af  nop     dword ptr [rax+rax+00h]
0x18000b2b4  mov     cs:byte_1800A4608, 0
0x18000b2bb  cmp     cs:byte_1800A4638, 0
0x18000b2c2  jz      short loc_18000B2DE
0x18000b2c4  lea     rcx, stru_1800A4610; lpCriticalSection
0x18000b2cb  call    cs:__imp_DeleteCriticalSection
0x18000b2d2  nop     dword ptr [rax+rax+00h]
0x18000b2d7  mov     cs:byte_1800A4638, 0
0x18000b2de  cmp     cs:byte_1800A4688, 0
0x18000b2e5  jz      short loc_18000B301
0x18000b2e7  lea     rcx, stru_1800A4660; lpCriticalSection
0x18000b2ee  call    cs:__imp_DeleteCriticalSection
0x18000b2f5  nop     dword ptr [rax+rax+00h]
0x18000b2fa  mov     cs:byte_1800A4688, 0
0x18000b301  mov     rax, cs:hEvent
0x18000b308  xor     ebx, ebx
0x18000b30a  mov     [rbp+57h+hObject], rax
0x18000b30e  mov     rax, cs:qword_1800A36D0
0x18000b315  mov     [rbp+57h+var_78], rax
0x18000b319  mov     rax, cs:qword_1800A36D8
0x18000b320  mov     [rbp+57h+var_70], rax
0x18000b324  mov     rax, cs:qword_1800A36E8
0x18000b32b  mov     [rbp+57h+var_68], rax
0x18000b32f  mov     rax, cs:qword_1800A36F0
0x18000b336  mov     [rbp+57h+var_60], rax
0x18000b33a  mov     rax, cs:qword_1800A36F8
0x18000b341  mov     [rbp+57h+var_58], rax
0x18000b345  mov     rax, cs:qword_1800A3710
0x18000b34c  mov     [rbp+57h+var_50], rax
0x18000b350  mov     rax, cs:qword_1800A3718
0x18000b357  mov     [rbp+57h+var_48], rax
0x18000b35b  mov     rax, cs:qword_1800A3700
0x18000b362  mov     [rbp+57h+var_40], rax
0x18000b366  mov     rax, cs:qword_1800A3708
0x18000b36d  mov     [rbp+57h+var_38], rax
0x18000b371  mov     rax, cs:NotificationEventHandle
0x18000b378  mov     [rbp+57h+var_30], rax
0x18000b37c  mov     rax, cs:qword_1800A3730
0x18000b383  mov     [rbp+57h+var_28], rax
0x18000b387  mov     rax, cs:qword_1800A3738
0x18000b38e  mov     [rbp+57h+var_20], rax
0x18000b392  mov     rax, cs:qword_1800A3740
0x18000b399  mov     [rbp+57h+var_18], rax
0x18000b39d  mov     rax, cs:qword_1800A3748
0x18000b3a4  mov     [rbp+57h+var_10], rax
0x18000b3a8  mov     rcx, [rbp+rbx*8+57h+hObject]; hObject
0x18000b3ad  test    rcx, rcx
0x18000b3b0  jz      short loc_18000B3BE
0x18000b3b2  call    cs:__imp_CloseHandle
0x18000b3b9  nop     dword ptr [rax+rax+00h]
0x18000b3be  inc     rbx
0x18000b3c1  cmp     rbx, 0Fh
0x18000b3c5  jnz     short loc_18000B3A8
0x18000b3c7  mov     rcx, cs:hThread; hObject
0x18000b3ce  test    rcx, rcx
0x18000b3d1  jz      short loc_18000B3DF
0x18000b3d3  call    cs:__imp_CloseHandle
0x18000b3da  nop     dword ptr [rax+rax+00h]
0x18000b3df  mov     rcx, cs:qword_1800A42F0; struct ConfigInfo *
0x18000b3e6  test    rcx, rcx
0x18000b3e9  jz      short loc_18000B3F0
0x18000b3eb  call    ?FreeConfigInfo@@YAXPEAUConfigInfo@@@Z; FreeConfigInfo(ConfigInfo *)
0x18000b3f0  mov     rcx, qword ptr cs:Src; hMem
0x18000b3f7  test    rcx, rcx
0x18000b3fa  jz      short loc_18000B408
0x18000b3fc  call    cs:__imp_LocalFree
0x18000b403  nop     dword ptr [rax+rax+00h]
0x18000b408  mov     rcx, qword ptr cs:Src+8; hMem
0x18000b40f  test    rcx, rcx
0x18000b412  jz      short loc_18000B420
0x18000b414  call    cs:__imp_LocalFree
0x18000b41b  nop     dword ptr [rax+rax+00h]
0x18000b420  mov     rcx, qword ptr cs:Base; hMem
0x18000b427  test    rcx, rcx
0x18000b42a  jz      short loc_18000B438
0x18000b42c  call    cs:__imp_LocalFree
0x18000b433  nop     dword ptr [rax+rax+00h]
0x18000b438  mov     rcx, qword ptr cs:Base+8; hMem
0x18000b43f  test    rcx, rcx
0x18000b442  jz      short loc_18000B450
0x18000b444  call    cs:__imp_LocalFree
0x18000b44b  nop     dword ptr [rax+rax+00h]
0x18000b450  mov     rcx, cs:qword_1800A4718; hMem
0x18000b457  test    rcx, rcx
0x18000b45a  jz      short loc_18000B468
0x18000b45c  call    cs:__imp_LocalFree
0x18000b463  nop     dword ptr [rax+rax+00h]
0x18000b468  xor     edx, edx; Val
0x18000b46a  lea     rcx, ?g_state@@3UStateInfo@@A; void *
0x18000b471  mov     r8d, 10E0h; Size
0x18000b477  mov     rbx, [rsp+0A0h+arg_0]
0x18000b47f  add     rsp, 0A0h
0x18000b486  pop     rbp
0x18000b487  jmp     memset_0
```

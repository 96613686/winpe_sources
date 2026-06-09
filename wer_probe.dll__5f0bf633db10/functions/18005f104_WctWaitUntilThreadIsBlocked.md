# WctWaitUntilThreadIsBlocked

- ea: `0x18005f104`
- end: `0x18005f257`
- name: `WctWaitUntilThreadIsBlocked`
- size: `339`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18002e908`
- `0x18005c8fc`

## callees

- `0x180004bb4`
- `0x18001c650`
- `0x18001fe24`
- `0x180027748`
- `0x1800517cc`
- `0x18005f104`
- `0x18005f4f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f1cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f1cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005f190`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005f190`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005f16c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005f201`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005f16c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005f201`

## pseudocode

```c
__int64 __fastcall WctWaitUntilThreadIsBlocked(unsigned int a1, int a2)
{
  int v4; // edi
  unsigned int v5; // ebx
  DWORD CurrentProcessId; // eax
  unsigned int ThreadWaitStatus; // eax
  void *v8; // r11
  unsigned int v9; // esi
  _BYTE v11[68]; // [rsp+20h] [rbp-C8h] BYREF
  int v12; // [rsp+64h] [rbp-84h]
  int v13; // [rsp+68h] [rbp-80h]
  struct _SYSTEM_PROCESS_INFORMATION *v14; // [rsp+100h] [rbp+18h] BYREF

  memset_0(v11, 0, 0x88u);
  v4 = 10;
  v14 = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_4c32fa7a72a13340317baef891270170_Traceguids);
  Sleep(0x64u);
  v5 = 1;
  while ( v4 && !(unsigned int)WctCreateSystemSnapshot(&v14) )
  {
    CurrentProcessId = GetCurrentProcessId();
    ThreadWaitStatus = WctGetThreadWaitStatus(
                         CurrentProcessId,
                         a1,
                         v14,
                         (struct _SYSTEM_EXTENDED_THREAD_INFORMATION *)v11);
    v14 = 0;
    v9 = ThreadWaitStatus;
    if ( v8 )
      HeapFree(g_hWerheap, 0, v8);
    if ( v9 )
      break;
    if ( v12 == 5 && a2 == v13 )
      goto LABEL_17;
    if ( (unsigned int)(v12 - 1) > 1 && (v12 != 5 || v13) )
      break;
    --v4;
    Sleep(0x1F4u);
  }
  v5 = 0;
LABEL_17:
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_4c32fa7a72a13340317baef891270170_Traceguids, v5);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v14);
  return v5;
}

```

## disassembly

```asm
0x18005f104  push    rbx
0x18005f106  push    rbp
0x18005f107  push    rsi
0x18005f108  push    rdi
0x18005f109  push    r14
0x18005f10b  push    r15
0x18005f10d  sub     rsp, 0B8h
0x18005f114  mov     ebp, edx
0x18005f116  mov     r14d, ecx
0x18005f119  xor     edx, edx; Val
0x18005f11b  lea     rcx, [rsp+0E8h+var_C8]; void *
0x18005f120  mov     r8d, 88h; Size
0x18005f126  call    memset_0
0x18005f12b  mov     edi, 0Ah
0x18005f130  mov     [rsp+0E8h+arg_10], 0
0x18005f13c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f143  lea     r15, WPP_GLOBAL_Control
0x18005f14a  cmp     rcx, r15
0x18005f14d  jz      short loc_18005F167
0x18005f14f  test    byte ptr [rcx+1Ch], 4
0x18005f153  jz      short loc_18005F167
0x18005f155  mov     rcx, [rcx+10h]
0x18005f159  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005f160  mov     edx, edi
0x18005f162  call    WPP_SF_
0x18005f167  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18005f16c  call    cs:__imp_Sleep
0x18005f172  mov     ebx, 1
0x18005f177  test    edi, edi
0x18005f179  jz      loc_18005F20C
0x18005f17f  lea     rcx, [rsp+0E8h+arg_10]
0x18005f187  call    ?WctCreateSystemSnapshot@@YAKPEAV?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@Z; WctCreateSystemSnapshot(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> *)
0x18005f18c  test    eax, eax
0x18005f18e  jnz     short loc_18005F20C
0x18005f190  call    cs:__imp_GetCurrentProcessId
0x18005f196  mov     r11, [rsp+0E8h+arg_10]
0x18005f19e  lea     r9, [rsp+0E8h+var_C8]; struct _SYSTEM_EXTENDED_THREAD_INFORMATION *
0x18005f1a3  mov     r8, r11; struct _SYSTEM_PROCESS_INFORMATION *
0x18005f1a6  mov     edx, r14d; unsigned int
0x18005f1a9  mov     ecx, eax; unsigned int
0x18005f1ab  call    ?WctGetThreadWaitStatus@@YAKKKPEAU_SYSTEM_PROCESS_INFORMATION@@PEAU_SYSTEM_EXTENDED_THREAD_INFORMATION@@@Z; WctGetThreadWaitStatus(ulong,ulong,_SYSTEM_PROCESS_INFORMATION *,_SYSTEM_EXTENDED_THREAD_INFORMATION *)
0x18005f1b0  mov     [rsp+0E8h+arg_10], 0
0x18005f1bc  mov     esi, eax
0x18005f1be  test    r11, r11
0x18005f1c1  jz      short loc_18005F1D5
0x18005f1c3  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18005f1ca  mov     r8, r11; lpMem
0x18005f1cd  xor     edx, edx; dwFlags
0x18005f1cf  call    cs:__imp_HeapFree
0x18005f1d5  test    esi, esi
0x18005f1d7  jnz     short loc_18005F20C
0x18005f1d9  mov     ecx, [rsp+0E8h+var_84]
0x18005f1dd  mov     edx, [rsp+0E8h+var_80]
0x18005f1e1  cmp     ecx, 5
0x18005f1e4  jnz     short loc_18005F1EA
0x18005f1e6  cmp     ebp, edx
0x18005f1e8  jz      short loc_18005F20E
0x18005f1ea  lea     eax, [rcx-1]
0x18005f1ed  cmp     eax, ebx
0x18005f1ef  jbe     short loc_18005F1FA
0x18005f1f1  cmp     ecx, 5
0x18005f1f4  jnz     short loc_18005F20C
0x18005f1f6  test    edx, edx
0x18005f1f8  jnz     short loc_18005F20C
0x18005f1fa  dec     edi
0x18005f1fc  mov     ecx, 1F4h; dwMilliseconds
0x18005f201  call    cs:__imp_Sleep
0x18005f207  jmp     loc_18005F177
0x18005f20c  xor     ebx, ebx
0x18005f20e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f215  cmp     rcx, r15
0x18005f218  jz      short loc_18005F238
0x18005f21a  test    byte ptr [rcx+1Ch], 4
0x18005f21e  jz      short loc_18005F238
0x18005f220  mov     rcx, [rcx+10h]
0x18005f224  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005f22b  mov     edx, 0Bh
0x18005f230  mov     r9d, ebx
0x18005f233  call    WPP_SF_d
0x18005f238  lea     rcx, [rsp+0E8h+arg_10]; void *
0x18005f240  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18005f245  mov     eax, ebx
0x18005f247  add     rsp, 0B8h
0x18005f24e  pop     r15
0x18005f250  pop     r14
0x18005f252  pop     rdi
0x18005f253  pop     rsi
0x18005f254  pop     rbp
0x18005f255  pop     rbx
0x18005f256  retn
```

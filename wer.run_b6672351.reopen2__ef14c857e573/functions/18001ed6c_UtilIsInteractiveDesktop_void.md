# UtilIsInteractiveDesktop(void)

- ea: `0x18001ed6c`
- end: `0x18001f106`
- name: `?UtilIsInteractiveDesktop@@YAHXZ`
- size: `922`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18002dca0`
- `0x180030de4`

## callees

- `0x180004c64`
- `0x18001e0d0`
- `0x18001ed6c`
- `0x18001f3a0`
- `0x180020680`
- `0x18003b180`
- `0x180055fa8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f08d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f0a7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f08d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f0a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f0ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f0e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f0ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f0e7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001eee4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001eee4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001edc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001edc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001efb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f06d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001efb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f06d`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18001ee09`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18001ef14`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18001ef74`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18001f044`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18001ee09`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18001ef14`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18001ef74`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18001f044`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x18001edb3`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x18001edb3`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18001edd0`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18001edd0`

## pseudocode

```c
__int64 UtilIsInteractiveDesktop(void)
{
  void *v0; // rbx
  PVOID v1; // rsi
  unsigned int v2; // r14d
  HWINSTA ProcessWindowStation; // r15
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  HDESK v6; // r12
  DWORD LastError; // eax
  __int64 v8; // rdx
  DWORD v9; // eax
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  SIZE_T v12; // rax
  unsigned __int64 v13; // kr00_8
  __int64 unique_for; // rax
  DWORD nLengthNeeded; // [rsp+70h] [rbp+40h] BYREF
  PVOID pvInfo; // [rsp+78h] [rbp+48h] BYREF
  char v18; // [rsp+80h] [rbp+50h] BYREF

  v0 = 0;
  v1 = 0;
  pvInfo = 0;
  v2 = 0;
  nLengthNeeded = 0;
  if ( !(unsigned __int8)IsGetThreadDesktopPresent() )
    goto LABEL_41;
  if ( !(unsigned __int8)IsGetThreadDesktopPresent() )
    goto LABEL_41;
  if ( !(unsigned __int8)IsGetThreadDesktopPresent() )
    goto LABEL_41;
  ProcessWindowStation = GetProcessWindowStation();
  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  v6 = ThreadDesktop;
  if ( !ProcessWindowStation || !ThreadDesktop )
    goto LABEL_41;
  nLengthNeeded = 0;
  if ( !GetUserObjectInformationW(ProcessWindowStation, 2, 0, 0, &nLengthNeeded) && GetLastError() != 122 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      LastError = GetLastError();
      v8 = 10;
LABEL_11:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids, LastError);
      goto LABEL_41;
    }
    goto LABEL_41;
  }
  v9 = nLengthNeeded + 1;
  if ( nLengthNeeded == -1 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_41;
    v11 = 11;
    goto LABEL_16;
  }
  v13 = v9;
  v12 = 2LL * v9;
  if ( !is_mul_ok(v13, 2u) )
    v12 = -1;
  v0 = HeapAlloc(g_hWerheap, 0, v12);
  if ( !v0 )
    goto LABEL_41;
  if ( GetUserObjectInformationW(ProcessWindowStation, 2, v0, nLengthNeeded, &nLengthNeeded) )
  {
    nLengthNeeded = 0;
    if ( !GetUserObjectInformationW(v6, 2, 0, 0, &nLengthNeeded) && GetLastError() != 122 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        LastError = GetLastError();
        v8 = 13;
        goto LABEL_11;
      }
      goto LABEL_41;
    }
    if ( nLengthNeeded )
    {
      unique_for = utl::make_unique_for_overwrite<wchar_t [0],0>(&v18, nLengthNeeded + 1);
      utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(&pvInfo, unique_for);
      utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v18);
      v1 = pvInfo;
      if ( !pvInfo )
        goto LABEL_43;
      if ( GetUserObjectInformationW(v6, 2, pvInfo, nLengthNeeded, &nLengthNeeded) )
      {
        if ( !(unsigned int)_o__wcsicmp(v0, L"WinSta0") && !(unsigned int)_o__wcsicmp(v1, L"default") )
          v2 = 1;
        goto LABEL_41;
      }
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        LastError = GetLastError();
        v8 = 15;
        goto LABEL_11;
      }
      goto LABEL_41;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_41;
    v11 = 14;
LABEL_16:
    WPP_SF_(*((_QWORD *)v10 + 2), v11, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids);
    goto LABEL_41;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    LastError = GetLastError();
    v8 = 12;
    goto LABEL_11;
  }
LABEL_41:
  if ( v1 )
    HeapFree(g_hWerheap, 0, v1);
LABEL_43:
  if ( v0 )
    HeapFree(g_hWerheap, 0, v0);
  return v2;
}

```

## disassembly

```asm
0x18001ed6c  push    rbp
0x18001ed6e  push    rbx
0x18001ed6f  push    rsi
0x18001ed70  push    rdi
0x18001ed71  push    r12
0x18001ed73  push    r14
0x18001ed75  push    r15
0x18001ed77  mov     rbp, rsp
0x18001ed7a  sub     rsp, 30h
0x18001ed7e  xor     ebx, ebx
0x18001ed80  xor     esi, esi
0x18001ed82  mov     [rbp+pvInfo], rsi
0x18001ed86  xor     r14d, r14d
0x18001ed89  mov     [rbp+nLengthNeeded], ebx
0x18001ed8c  call    IsGetThreadDesktopPresent
0x18001ed91  test    al, al
0x18001ed93  jz      loc_18001F0B9
0x18001ed99  call    IsGetThreadDesktopPresent
0x18001ed9e  test    al, al
0x18001eda0  jz      loc_18001F0B9
0x18001eda6  call    IsGetThreadDesktopPresent
0x18001edab  test    al, al
0x18001edad  jz      loc_18001F0B9
0x18001edb3  call    cs:__imp_GetProcessWindowStation
0x18001edba  nop     dword ptr [rax+rax+00h]
0x18001edbf  mov     r15, rax
0x18001edc2  call    cs:__imp_GetCurrentThreadId
0x18001edc9  nop     dword ptr [rax+rax+00h]
0x18001edce  mov     ecx, eax; dwThreadId
0x18001edd0  call    cs:__imp_GetThreadDesktop
0x18001edd7  nop     dword ptr [rax+rax+00h]
0x18001eddc  mov     r12, rax
0x18001eddf  test    r15, r15
0x18001ede2  jz      loc_18001F0B9
0x18001ede8  test    rax, rax
0x18001edeb  jz      loc_18001F0B9
0x18001edf1  lea     rax, [rbp+nLengthNeeded]
0x18001edf5  mov     [rbp+nLengthNeeded], ebx
0x18001edf8  xor     r9d, r9d; nLength
0x18001edfb  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001ee00  xor     r8d, r8d; pvInfo
0x18001ee03  lea     edx, [rbx+2]; nIndex
0x18001ee06  mov     rcx, r15; hObj
0x18001ee09  call    cs:__imp_GetUserObjectInformationW
0x18001ee10  nop     dword ptr [rax+rax+00h]
0x18001ee15  test    eax, eax
0x18001ee17  jnz     short loc_18001EE7C
0x18001ee19  call    cs:__imp_GetLastError
0x18001ee20  nop     dword ptr [rax+rax+00h]
0x18001ee25  cmp     eax, 7Ah ; 'z'
0x18001ee28  jz      short loc_18001EE7C
0x18001ee2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee31  lea     rax, WPP_GLOBAL_Control
0x18001ee38  cmp     rcx, rax
0x18001ee3b  jz      loc_18001F0B9
0x18001ee41  lea     edi, [rbx+1]
0x18001ee44  test    [rcx+1Ch], dil
0x18001ee48  jz      loc_18001F0B9
0x18001ee4e  call    cs:__imp_GetLastError
0x18001ee55  nop     dword ptr [rax+rax+00h]
0x18001ee5a  lea     edx, [rbx+0Ah]
0x18001ee5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee64  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x18001ee6b  mov     r9d, eax
0x18001ee6e  mov     rcx, [rcx+10h]
0x18001ee72  call    WPP_SF_d
0x18001ee77  jmp     loc_18001F0B9
0x18001ee7c  mov     eax, [rbp+nLengthNeeded]
0x18001ee7f  mov     edi, 1
0x18001ee84  inc     eax
0x18001ee86  cmp     eax, edi
0x18001ee88  jnb     short loc_18001EEC3
0x18001ee8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee91  lea     rax, WPP_GLOBAL_Control
0x18001ee98  cmp     rcx, rax
0x18001ee9b  jz      loc_18001F0B9
0x18001eea1  test    [rcx+1Ch], dil
0x18001eea5  jz      loc_18001F0B9
0x18001eeab  lea     edx, [rdi+0Ah]
0x18001eeae  mov     rcx, [rcx+10h]
0x18001eeb2  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x18001eeb9  call    WPP_SF_
0x18001eebe  jmp     loc_18001F0B9
0x18001eec3  mov     ecx, eax
0x18001eec5  mov     eax, 2
0x18001eeca  mul     rcx
0x18001eecd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001eed4  cmovb   rax, rcx
0x18001eed8  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18001eedf  mov     r8, rax; dwBytes
0x18001eee2  xor     edx, edx; dwFlags
0x18001eee4  call    cs:__imp_HeapAlloc
0x18001eeeb  nop     dword ptr [rax+rax+00h]
0x18001eef0  mov     rbx, rax
0x18001eef3  test    rax, rax
0x18001eef6  jz      loc_18001F0B9
0x18001eefc  mov     r9d, [rbp+nLengthNeeded]; nLength
0x18001ef00  lea     rax, [rbp+nLengthNeeded]
0x18001ef04  mov     r8, rbx; pvInfo
0x18001ef07  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001ef0c  mov     edx, 2; nIndex
0x18001ef11  mov     rcx, r15; hObj
0x18001ef14  call    cs:__imp_GetUserObjectInformationW
0x18001ef1b  nop     dword ptr [rax+rax+00h]
0x18001ef20  test    eax, eax
0x18001ef22  jnz     short loc_18001EF5B
0x18001ef24  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef2b  lea     rax, WPP_GLOBAL_Control
0x18001ef32  cmp     rcx, rax
0x18001ef35  jz      loc_18001F0B9
0x18001ef3b  test    [rcx+1Ch], dil
0x18001ef3f  jz      loc_18001F0B9
0x18001ef45  call    cs:__imp_GetLastError
0x18001ef4c  nop     dword ptr [rax+rax+00h]
0x18001ef51  mov     edx, 0Ch
0x18001ef56  jmp     loc_18001EE5D
0x18001ef5b  xor     r9d, r9d; nLength
0x18001ef5e  mov     [rbp+nLengthNeeded], esi
0x18001ef61  lea     rax, [rbp+nLengthNeeded]
0x18001ef65  xor     r8d, r8d; pvInfo
0x18001ef68  mov     rcx, r12; hObj
0x18001ef6b  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001ef70  lea     edx, [r9+2]; nIndex
0x18001ef74  call    cs:__imp_GetUserObjectInformationW
0x18001ef7b  nop     dword ptr [rax+rax+00h]
0x18001ef80  test    eax, eax
0x18001ef82  jnz     short loc_18001EFCC
0x18001ef84  call    cs:__imp_GetLastError
0x18001ef8b  nop     dword ptr [rax+rax+00h]
0x18001ef90  cmp     eax, 7Ah ; 'z'
0x18001ef93  jz      short loc_18001EFCC
0x18001ef95  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef9c  lea     rax, WPP_GLOBAL_Control
0x18001efa3  cmp     rcx, rax
0x18001efa6  jz      loc_18001F0B9
0x18001efac  test    [rcx+1Ch], dil
0x18001efb0  jz      loc_18001F0B9
0x18001efb6  call    cs:__imp_GetLastError
0x18001efbd  nop     dword ptr [rax+rax+00h]
0x18001efc2  mov     edx, 0Dh
0x18001efc7  jmp     loc_18001EE5D
0x18001efcc  mov     eax, [rbp+nLengthNeeded]
0x18001efcf  cmp     eax, edi
0x18001efd1  jnb     short loc_18001EFFE
0x18001efd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efda  lea     rax, WPP_GLOBAL_Control
0x18001efe1  cmp     rcx, rax
0x18001efe4  jz      loc_18001F0B9
0x18001efea  test    [rcx+1Ch], dil
0x18001efee  jz      loc_18001F0B9
0x18001eff4  mov     edx, 0Eh
0x18001eff9  jmp     loc_18001EEAE
0x18001effe  lea     edx, [rax+1]
0x18001f001  lea     rcx, [rbp+arg_10]
0x18001f005  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x18001f00a  mov     rdx, rax
0x18001f00d  lea     rcx, [rbp+pvInfo]
0x18001f011  call    ??4?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&)
0x18001f016  lea     rcx, [rbp+arg_10]; void *
0x18001f01a  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18001f01f  mov     rsi, [rbp+pvInfo]
0x18001f023  test    rsi, rsi
0x18001f026  jz      loc_18001F0D6
0x18001f02c  mov     r9d, [rbp+nLengthNeeded]; nLength
0x18001f030  lea     rax, [rbp+nLengthNeeded]
0x18001f034  mov     r8, rsi; pvInfo
0x18001f037  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001f03c  mov     edx, 2; nIndex
0x18001f041  mov     rcx, r12; hObj
0x18001f044  call    cs:__imp_GetUserObjectInformationW
0x18001f04b  nop     dword ptr [rax+rax+00h]
0x18001f050  test    eax, eax
0x18001f052  jnz     short loc_18001F083
0x18001f054  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f05b  lea     rax, WPP_GLOBAL_Control
0x18001f062  cmp     rcx, rax
0x18001f065  jz      short loc_18001F0B9
0x18001f067  test    [rcx+1Ch], dil
0x18001f06b  jz      short loc_18001F0B9
0x18001f06d  call    cs:__imp_GetLastError
0x18001f074  nop     dword ptr [rax+rax+00h]
0x18001f079  mov     edx, 0Fh
0x18001f07e  jmp     loc_18001EE5D
0x18001f083  lea     rdx, aWinsta0; "WinSta0"
0x18001f08a  mov     rcx, rbx
0x18001f08d  call    cs:__imp__o__wcsicmp
0x18001f094  nop     dword ptr [rax+rax+00h]
0x18001f099  test    eax, eax
0x18001f09b  jnz     short loc_18001F0B9
0x18001f09d  lea     rdx, aDefault; "default"
0x18001f0a4  mov     rcx, rsi
0x18001f0a7  call    cs:__imp__o__wcsicmp
0x18001f0ae  nop     dword ptr [rax+rax+00h]
0x18001f0b3  test    eax, eax
0x18001f0b5  cmovz   r14d, edi
0x18001f0b9  test    rsi, rsi
0x18001f0bc  jz      short loc_18001F0D6
0x18001f0be  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18001f0c5  mov     r8, rsi; lpMem
0x18001f0c8  xor     edx, edx; dwFlags
0x18001f0ca  call    cs:__imp_HeapFree
0x18001f0d1  nop     dword ptr [rax+rax+00h]
0x18001f0d6  test    rbx, rbx
0x18001f0d9  jz      short loc_18001F0F3
0x18001f0db  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18001f0e2  mov     r8, rbx; lpMem
0x18001f0e5  xor     edx, edx; dwFlags
0x18001f0e7  call    cs:__imp_HeapFree
0x18001f0ee  nop     dword ptr [rax+rax+00h]
0x18001f0f3  mov     eax, r14d
0x18001f0f6  add     rsp, 30h
0x18001f0fa  pop     r15
0x18001f0fc  pop     r14
0x18001f0fe  pop     r12
0x18001f100  pop     rdi
0x18001f101  pop     rsi
0x18001f102  pop     rbx
0x18001f103  pop     rbp
0x18001f104  retn
```

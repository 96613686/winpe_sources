# WIMReadFileEx

- ea: `0x18000e674`
- end: `0x18000ea57`
- name: `WIMReadFileEx`
- size: `995`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000cf38`

## callees

- `0x18000e494`
- `0x18000e5f0`
- `0x18000e674`
- `0x180011a38`
- `0x180011a84`
- `0x180011bb8`
- `0x180012304`
- `0x180012368`
- `0x180012ff0`
- `0x1800607b0`
- `0x180060e42`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000ea0b`
- `KERNEL32!HeapFree` at `0x18000ea0b`
- `KERNEL32!HeapAlloc` at `0x18000e824`
- `KERNEL32!HeapAlloc` at `0x18000e824`
- `KERNEL32!GetLastError` at `0x18000e98e`
- `KERNEL32!GetLastError` at `0x18000e98e`
- `KERNEL32!ReadFile` at `0x18000e97a`
- `KERNEL32!ReadFile` at `0x18000e97a`
- `KERNEL32!SetLastError` at `0x18000e7c0`
- `KERNEL32!SetLastError` at `0x18000e9ab`
- `KERNEL32!SetLastError` at `0x18000e9d9`
- `KERNEL32!SetLastError` at `0x18000ea27`
- `KERNEL32!SetLastError` at `0x18000e7c0`
- `KERNEL32!SetLastError` at `0x18000e9ab`
- `KERNEL32!SetLastError` at `0x18000e9d9`
- `KERNEL32!SetLastError` at `0x18000ea27`
- `KERNEL32!GetProcessHeap` at `0x18000e80c`
- `KERNEL32!GetProcessHeap` at `0x18000e9f7`
- `KERNEL32!GetProcessHeap` at `0x18000e80c`
- `KERNEL32!GetProcessHeap` at `0x18000e9f7`
- `ntdll!RtlNtStatusToDosError` at `0x18000e876`
- `ntdll!RtlNtStatusToDosError` at `0x18000e88b`
- `ntdll!RtlNtStatusToDosError` at `0x18000e876`
- `ntdll!RtlNtStatusToDosError` at `0x18000e88b`
- `ntdll!RtlSetIoCompletionCallback` at `0x18000e79b`
- `ntdll!RtlSetIoCompletionCallback` at `0x18000e79b`

## pseudocode

```c
__int64 __fastcall WIMReadFileEx(__int64 a1, void *a2, unsigned int a3, ULONG_PTR a4)
{
  __int64 v5; // r14
  DWORD v7; // r13d
  struct _OVERLAPPED *lpOverlapped; // r15
  unsigned int v9; // edi
  __int64 v10; // r12
  void *WimFileHandle; // rax
  int v12; // eax
  NTSTATUS v13; // ebx
  __int64 WimLastEOF; // rax
  HANDLE ProcessHeap; // rax
  struct _OVERLAPPED *v16; // rax
  struct _IO_STATUS_BLOCK *v17; // rdx
  DWORD v18; // ecx
  DWORD v19; // ebx
  int v20; // r14d
  DWORD v21; // eax
  __int64 WimHeader; // rax
  __int64 v23; // r9
  void *v24; // rax
  LPVOID v25; // rdx
  HANDLE v26; // rax
  unsigned int v28; // [rsp+38h] [rbp-3A0h]
  DWORD v29; // [rsp+4Ch] [rbp-38Ch]
  __int64 v30; // [rsp+50h] [rbp-388h]
  __int64 v33; // [rsp+68h] [rbp-370h]
  _BYTE v34[208]; // [rsp+90h] [rbp-348h] BYREF
  _BYTE v35[560]; // [rsp+160h] [rbp-278h] BYREF

  v5 = a3;
  memset_0(v35, 0, sizeof(v35));
  v7 = 0;
  memset_0(v34, 0, sizeof(v34));
  lpOverlapped = 0;
  v9 = 0;
  if ( !a1 || !a2 || !a4 )
  {
    v18 = 87;
    goto LABEL_47;
  }
  if ( *(_DWORD *)a1 == -17960958 )
  {
    v10 = *(_QWORD *)(a1 + 8);
  }
  else
  {
    v10 = 0;
    if ( *(_DWORD *)a1 == -17960959 )
      v10 = a1;
  }
  if ( !v10 || GetWimFileHandle(v10) == -1 )
  {
    v18 = 6;
LABEL_47:
    SetLastError(v18);
    return 0;
  }
  if ( !(unsigned int)WIMGetAttributes(v10, v35) )
    return 0;
  if ( (GetHandleFlags(v10) & 0x200) == 0 )
  {
    WimFileHandle = (void *)GetWimFileHandle(v10);
    v12 = RtlSetIoCompletionCallback(WimFileHandle, WIMReadIoDone, 0);
    v13 = v12;
    if ( v12 >= 0 )
    {
      SetHandleFlag(v10, 512);
      goto LABEL_14;
    }
    if ( RtlNtStatusToDosError(v12) != 317 )
      v13 = RtlNtStatusToDosError(v13);
    v18 = v13;
    goto LABEL_47;
  }
LABEL_14:
  SetLastError(0);
  v28 = *(_DWORD *)(a4 + 16);
  LODWORD(v30) = v28;
  v29 = *(_DWORD *)(a4 + 20);
  HIDWORD(v30) = v29;
  WimLastEOF = GetWimLastEOF(v10);
  v33 = WimLastEOF;
  if ( v30 < 0 || v30 >= WimLastEOF )
  {
    SetLastError(0x26u);
    goto LABEL_41;
  }
  ProcessHeap = GetProcessHeap();
  v16 = (struct _OVERLAPPED *)HeapAlloc(ProcessHeap, 8u, 0x38u);
  lpOverlapped = v16;
  if ( v16 )
  {
    v16[1].Internal = a4;
    v16[1].InternalHigh = (ULONG_PTR)CTptReadFile::_IOCompletionCallback;
    if ( !(_DWORD)v5 )
    {
      v17 = 0;
LABEL_19:
      WIMReadIoDone(0, v17, (ULONG)lpOverlapped);
LABEL_20:
      v9 = 1;
      goto LABEL_41;
    }
    v19 = v28;
    if ( v30 + v5 >= v30 )
    {
      if ( v30 + v5 <= v33 )
      {
LABEL_29:
        v21 = v29;
        if ( !v29 && v28 < 0xD0 )
        {
          if ( 208 - (unsigned __int64)v28 <= (unsigned int)v5 )
            v7 = 208 - v28;
          else
            v7 = v5;
          WimHeader = GetWimHeader(v10);
          PackWimHeader(WimHeader, v34);
          memcpy_0(a2, &v34[v23], v7);
          v19 = v7 + v28;
          LODWORD(v5) = v5 - v7;
          if ( !(_DWORD)v5 )
          {
            v17 = (struct _IO_STATUS_BLOCK *)v7;
            goto LABEL_19;
          }
          v21 = 0;
        }
        lpOverlapped->Offset = v19;
        lpOverlapped->OffsetHigh = v21;
        lpOverlapped[1].Offset = v7;
        v24 = (void *)GetWimFileHandle(v10);
        if ( !ReadFile(v24, v25, v5, 0, lpOverlapped) && GetLastError() != 997 )
          goto LABEL_41;
        goto LABEL_20;
      }
      v20 = v28 + v5;
    }
    else
    {
      v20 = -1;
    }
    LODWORD(v5) = v20 - v28;
    goto LABEL_29;
  }
LABEL_41:
  if ( !v9 )
  {
    if ( lpOverlapped )
    {
      v26 = GetProcessHeap();
      HeapFree(v26, 0, lpOverlapped);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18000e674  push    rbx
0x18000e676  push    rdi
0x18000e677  push    r12
0x18000e679  push    r13
0x18000e67b  push    r14
0x18000e67d  push    r15
0x18000e67f  sub     rsp, 3A8h
0x18000e686  mov     rax, cs:__security_cookie
0x18000e68d  xor     rax, rsp
0x18000e690  mov     [rsp+3D8h+var_48], rax
0x18000e698  mov     r12, r9
0x18000e69b  mov     [rsp+3D8h+var_378], r9
0x18000e6a0  mov     r14d, r8d
0x18000e6a3  mov     [rsp+3D8h+var_380], rdx
0x18000e6a8  mov     rbx, rcx
0x18000e6ab  mov     [rsp+3D8h+var_398], r14d
0x18000e6b0  xor     edx, edx; Val
0x18000e6b2  mov     r8d, 230h; Size
0x18000e6b8  lea     rcx, [rsp+3D8h+var_278]; void *
0x18000e6c0  call    memset_0
0x18000e6c5  and     [rsp+3D8h+var_388], 0
0x18000e6cb  and     [rsp+3D8h+var_358], 0
0x18000e6d4  xor     r13d, r13d
0x18000e6d7  mov     [rsp+3D8h+var_390], r13d
0x18000e6dc  and     [rsp+3D8h+var_3A8], r13d
0x18000e6e1  xor     edx, edx; Val
0x18000e6e3  mov     r8d, 0D0h; Size
0x18000e6e9  lea     rcx, [rsp+3D8h+var_348]; void *
0x18000e6f1  call    memset_0
0x18000e6f6  xor     r15d, r15d
0x18000e6f9  mov     [rsp+3D8h+var_368], r15
0x18000e6fe  and     [rsp+3D8h+var_370], r13
0x18000e703  xor     edi, edi
0x18000e705  mov     [rsp+3D8h+var_3A4], edi
0x18000e709  and     [rsp+3D8h+var_360], edi
0x18000e70d  test    rbx, rbx
0x18000e710  jz      loc_18000EA22
0x18000e716  cmp     [rsp+3D8h+var_380], rdi
0x18000e71b  jz      loc_18000EA22
0x18000e721  test    r12, r12
0x18000e724  jz      loc_18000EA22
0x18000e72a  cmp     dword ptr [rbx], 0FEEDF002h
0x18000e730  jnz     short loc_18000E738
0x18000e732  mov     r12, [rbx+8]
0x18000e736  jmp     short loc_18000E745
0x18000e738  xor     r12d, r12d
0x18000e73b  cmp     dword ptr [rbx], 0FEEDF001h
0x18000e741  cmovz   r12, rbx
0x18000e745  test    r12, r12
0x18000e748  jz      loc_18000EA1B
0x18000e74e  mov     rcx, r12
0x18000e751  call    GetWimFileHandle
0x18000e756  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e75a  jz      loc_18000EA1B
0x18000e760  lea     rdx, [rsp+3D8h+var_278]
0x18000e768  mov     rcx, r12
0x18000e76b  call    WIMGetAttributes
0x18000e770  test    eax, eax
0x18000e772  jz      loc_18000EA33
0x18000e778  mov     rcx, r12
0x18000e77b  call    GetHandleFlags
0x18000e780  bt      eax, 9
0x18000e784  jb      short loc_18000E7BE
0x18000e786  mov     rcx, r12
0x18000e789  call    GetWimFileHandle
0x18000e78e  mov     rcx, rax; FileHandle
0x18000e791  xor     r8d, r8d; Flags
0x18000e794  lea     rdx, WIMReadIoDone; Callback
0x18000e79b  call    cs:__imp_RtlSetIoCompletionCallback
0x18000e7a2  nop     dword ptr [rax+rax+00h]
0x18000e7a7  mov     ebx, eax
0x18000e7a9  test    eax, eax
0x18000e7ab  js      loc_18000E874
0x18000e7b1  mov     edx, 200h
0x18000e7b6  mov     rcx, r12
0x18000e7b9  call    SetHandleFlag
0x18000e7be  xor     ecx, ecx; dwErrCode
0x18000e7c0  call    cs:__imp_SetLastError
0x18000e7c7  nop     dword ptr [rax+rax+00h]
0x18000e7cc  nop
0x18000e7cd  mov     rcx, [rsp+3D8h+var_378]
0x18000e7d2  mov     eax, [rcx+10h]
0x18000e7d5  mov     [rsp+3D8h+var_3A0], eax
0x18000e7d9  mov     dword ptr [rsp+3D8h+var_388], eax
0x18000e7dd  mov     eax, [rcx+14h]
0x18000e7e0  mov     [rsp+3D8h+var_38C], eax
0x18000e7e4  mov     dword ptr [rsp+3D8h+var_388+4], eax
0x18000e7e8  mov     rcx, r12
0x18000e7eb  call    GetWimLastEOF
0x18000e7f0  mov     [rsp+3D8h+var_370], rax
0x18000e7f5  mov     rbx, [rsp+3D8h+var_388]
0x18000e7fa  test    rbx, rbx
0x18000e7fd  js      loc_18000E9A6
0x18000e803  cmp     rbx, rax
0x18000e806  jge     loc_18000E9A6
0x18000e80c  call    cs:__imp_GetProcessHeap
0x18000e813  nop     dword ptr [rax+rax+00h]
0x18000e818  mov     rcx, rax; hHeap
0x18000e81b  mov     edx, 8; dwFlags
0x18000e820  lea     r8d, [rdx+30h]; dwBytes
0x18000e824  call    cs:__imp_HeapAlloc
0x18000e82b  nop     dword ptr [rax+rax+00h]
0x18000e830  mov     r15, rax
0x18000e833  mov     [rsp+3D8h+var_368], rax
0x18000e838  test    rax, rax
0x18000e83b  jz      loc_18000E9B7
0x18000e841  mov     rax, [rsp+3D8h+var_378]
0x18000e846  mov     [r15+20h], rax
0x18000e84a  lea     rax, ?_IOCompletionCallback@CTptReadFile@@SAXKKPEAU_OVERLAPPED@@@Z; CTptReadFile::_IOCompletionCallback(ulong,ulong,_OVERLAPPED *)
0x18000e851  mov     [r15+28h], rax
0x18000e855  test    r14d, r14d
0x18000e858  jnz     short loc_18000E8A0
0x18000e85a  xor     edx, edx; IoStatusBlock
0x18000e85c  mov     r8, r15; Reserved
0x18000e85f  xor     ecx, ecx; ApcContext
0x18000e861  call    WIMReadIoDone
0x18000e866  mov     edi, 1
0x18000e86b  mov     [rsp+3D8h+var_3A4], edi
0x18000e86f  jmp     loc_18000E9B7
0x18000e874  mov     ecx, ebx; Status
0x18000e876  call    cs:__imp_RtlNtStatusToDosError
0x18000e87d  nop     dword ptr [rax+rax+00h]
0x18000e882  cmp     eax, 13Dh
0x18000e887  jz      short loc_18000E899
0x18000e889  mov     ecx, ebx; Status
0x18000e88b  call    cs:__imp_RtlNtStatusToDosError
0x18000e892  nop     dword ptr [rax+rax+00h]
0x18000e897  mov     ebx, eax
0x18000e899  mov     ecx, ebx
0x18000e89b  jmp     loc_18000EA27
0x18000e8a0  lea     rcx, [rbx+r14]
0x18000e8a4  mov     [rsp+3D8h+var_358], rcx
0x18000e8ac  cmp     rcx, rbx
0x18000e8af  mov     ebx, [rsp+3D8h+var_3A0]
0x18000e8b3  jge     short loc_18000E8BB
0x18000e8b5  or      r14d, 0FFFFFFFFh
0x18000e8b9  jmp     short loc_18000E8C5
0x18000e8bb  cmp     rcx, [rsp+3D8h+var_370]
0x18000e8c0  jle     short loc_18000E8CD
0x18000e8c2  mov     r14d, ecx
0x18000e8c5  sub     r14d, ebx
0x18000e8c8  mov     [rsp+3D8h+var_398], r14d
0x18000e8cd  mov     eax, [rsp+3D8h+var_38C]
0x18000e8d1  test    eax, eax
0x18000e8d3  jnz     short loc_18000E950
0x18000e8d5  mov     edx, 0D0h
0x18000e8da  cmp     ebx, edx
0x18000e8dc  jnb     short loc_18000E950
0x18000e8de  mov     r9d, ebx
0x18000e8e1  mov     ecx, edx
0x18000e8e3  sub     rcx, r9
0x18000e8e6  mov     eax, r14d
0x18000e8e9  cmp     rcx, rax
0x18000e8ec  jbe     short loc_18000E8F8
0x18000e8ee  mov     r13d, r14d
0x18000e8f1  mov     [rsp+3D8h+var_390], r14d
0x18000e8f6  jmp     short loc_18000E903
0x18000e8f8  mov     r13d, edx
0x18000e8fb  sub     r13d, ebx
0x18000e8fe  mov     [rsp+3D8h+var_390], r13d
0x18000e903  mov     rcx, r12
0x18000e906  call    GetWimHeader
0x18000e90b  mov     rcx, rax
0x18000e90e  lea     rdx, [rsp+3D8h+var_348]
0x18000e916  call    PackWimHeader
0x18000e91b  mov     r8d, r13d; Size
0x18000e91e  lea     rdx, [rsp+3D8h+var_348]
0x18000e926  add     rdx, r9; Src
0x18000e929  mov     rcx, [rsp+3D8h+var_380]; void *
0x18000e92e  call    memcpy_0
0x18000e933  add     ebx, r13d
0x18000e936  mov     dword ptr [rsp+3D8h+var_388], ebx
0x18000e93a  sub     r14d, r13d
0x18000e93d  mov     [rsp+3D8h+var_398], r14d
0x18000e942  jnz     short loc_18000E94C
0x18000e944  mov     edx, r13d
0x18000e947  jmp     loc_18000E85C
0x18000e94c  mov     eax, [rsp+3D8h+var_38C]
0x18000e950  mov     [r15+10h], ebx
0x18000e954  mov     [r15+14h], eax
0x18000e958  mov     [r15+30h], r13d
0x18000e95c  mov     edx, r13d
0x18000e95f  add     rdx, [rsp+3D8h+var_380]
0x18000e964  mov     rcx, r12
0x18000e967  call    GetWimFileHandle
0x18000e96c  mov     rcx, rax; hFile
0x18000e96f  mov     [rsp+3D8h+lpOverlapped], r15; lpOverlapped
0x18000e974  xor     r9d, r9d; lpNumberOfBytesRead
0x18000e977  mov     r8d, r14d; nNumberOfBytesToRead
0x18000e97a  call    cs:__imp_ReadFile
0x18000e981  nop     dword ptr [rax+rax+00h]
0x18000e986  test    eax, eax
0x18000e988  jnz     loc_18000E866
0x18000e98e  call    cs:__imp_GetLastError
0x18000e995  nop     dword ptr [rax+rax+00h]
0x18000e99a  cmp     eax, 3E5h
0x18000e99f  jnz     short loc_18000E9B7
0x18000e9a1  jmp     loc_18000E866
0x18000e9a6  mov     ecx, 26h ; '&'; dwErrCode
0x18000e9ab  call    cs:__imp_SetLastError
0x18000e9b2  nop     dword ptr [rax+rax+00h]
0x18000e9b7  jmp     short loc_18000E9EE
0x18000e9b9  cmp     [rsp+3D8h+var_3A8], 0C0000005h
0x18000e9c1  jz      short loc_18000E9D4
0x18000e9c3  cmp     [rsp+3D8h+var_3A8], 0C0000006h
0x18000e9cb  jnz     short loc_18000E9E5
0x18000e9cd  mov     ecx, 45Dh
0x18000e9d2  jmp     short loc_18000E9D9
0x18000e9d4  mov     ecx, 1E7h; dwErrCode
0x18000e9d9  call    cs:__imp_SetLastError
0x18000e9e0  nop     dword ptr [rax+rax+00h]
0x18000e9e5  mov     r15, [rsp+3D8h+var_368]
0x18000e9ea  mov     edi, [rsp+3D8h+var_3A4]
0x18000e9ee  test    edi, edi
0x18000e9f0  jnz     short loc_18000EA17
0x18000e9f2  test    r15, r15
0x18000e9f5  jz      short loc_18000EA17
0x18000e9f7  call    cs:__imp_GetProcessHeap
0x18000e9fe  nop     dword ptr [rax+rax+00h]
0x18000ea03  mov     rcx, rax; hHeap
0x18000ea06  mov     r8, r15; lpMem
0x18000ea09  xor     edx, edx; dwFlags
0x18000ea0b  call    cs:__imp_HeapFree
0x18000ea12  nop     dword ptr [rax+rax+00h]
0x18000ea17  mov     eax, edi
0x18000ea19  jmp     short loc_18000EA35
0x18000ea1b  mov     ecx, 6
0x18000ea20  jmp     short loc_18000EA27
0x18000ea22  mov     ecx, 57h ; 'W'; dwErrCode
0x18000ea27  call    cs:__imp_SetLastError
0x18000ea2e  nop     dword ptr [rax+rax+00h]
0x18000ea33  xor     eax, eax
0x18000ea35  mov     rcx, [rsp+3D8h+var_48]
0x18000ea3d  xor     rcx, rsp; StackCookie
0x18000ea40  call    __security_check_cookie
0x18000ea45  add     rsp, 3A8h
0x18000ea4c  pop     r15
0x18000ea4e  pop     r14
0x18000ea50  pop     r13
0x18000ea52  pop     r12
0x18000ea54  pop     rdi
0x18000ea55  pop     rbx
0x18000ea56  retn
0x180061a63  push    rbp
0x180061a65  sub     rsp, 30h
0x180061a69  mov     rbp, rdx
0x180061a6c  mov     [rbp+88h], rcx
0x180061a73  mov     rax, [rcx]
0x180061a76  mov     ecx, [rax]
0x180061a78  mov     [rbp+7Ch], ecx
0x180061a7b  mov     [rbp+30h], ecx
0x180061a7e  mov     eax, [rbp+30h]
0x180061a81  cmp     eax, 0C0000006h
0x180061a86  jz      short loc_180061A96
0x180061a88  mov     eax, [rbp+30h]
0x180061a8b  cmp     eax, 0C0000005h
0x180061a90  jz      short loc_180061A96
0x180061a92  xor     eax, eax
0x180061a94  jmp     short loc_180061A9B
0x180061a96  mov     eax, 1
0x180061a9b  add     rsp, 30h
0x180061a9f  pop     rbp
0x180061aa0  retn
```

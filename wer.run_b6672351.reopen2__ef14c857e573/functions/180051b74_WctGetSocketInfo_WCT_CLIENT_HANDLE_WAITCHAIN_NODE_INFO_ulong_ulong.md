# WctGetSocketInfo(_WCT_CLIENT_HANDLE *,_WAITCHAIN_NODE_INFO *,ulong *,ulong *)

- ea: `0x180051b74`
- end: `0x180051dbc`
- name: `?WctGetSocketInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAU_WAITCHAIN_NODE_INFO@@PEAK2@Z`
- size: `584`
- prototype: `unsigned int __fastcall(struct _WCT_CLIENT_HANDLE *, struct _WAITCHAIN_NODE_INFO *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, loader_planting`

## callers

- `0x18005fa0c`

## callees

- `0x180004c64`
- `0x18001e0d0`
- `0x180020680`
- `0x18002e94c`
- `0x180051b74`
- `0x180051dc4`
- `0x1800616b8`
- `0x180061f40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051cdd`
- `ntdll!RtlNtStatusToDosError` at `0x180051c25`
- `ntdll!RtlNtStatusToDosError` at `0x180051c25`
- `ntdll!NtQueryInformationThread` at `0x180051c13`
- `ntdll!NtQueryInformationThread` at `0x180051c13`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180051ccd`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180051ccd`

## pseudocode

```c
__int64 __fastcall WctGetSocketInfo(HANDLE *a1, struct _WAITCHAIN_NODE_INFO *a2, unsigned int *a3, unsigned int *a4)
{
  unsigned int *v4; // rsi
  unsigned int *v5; // r15
  unsigned __int64 v8; // rdi
  NTSTATUS v9; // eax
  ULONG LastError; // ebx
  int IsWow64; // eax
  const void *v12; // r12
  int v13; // esi
  unsigned __int64 v14; // r15
  __int64 v15; // rax
  _QWORD *v16; // rbx
  unsigned __int64 v17; // rcx
  int v18; // r9d
  unsigned int ReturnLength; // [rsp+20h] [rbp-60h]
  union _SOCKADDR_INET *v21; // [rsp+30h] [rbp-50h]
  union _SOCKADDR_INET *v22; // [rsp+38h] [rbp-48h]
  LPVOID lpBuffer; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v24[8]; // [rsp+48h] [rbp-38h] BYREF
  _OWORD ThreadInformation[3]; // [rsp+50h] [rbp-30h] BYREF
  ULONG v26; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int *v27; // [rsp+D0h] [rbp+50h]
  unsigned int *v28; // [rsp+D8h] [rbp+58h]

  v28 = a4;
  v27 = a3;
  v4 = a4;
  v5 = a3;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  v26 = 0;
  v8 = -1;
  lpBuffer = 0;
  memset(ThreadInformation, 0, sizeof(ThreadInformation));
  if ( !a1 )
  {
    LastError = 87;
    goto LABEL_23;
  }
  v9 = NtQueryInformationThread(*a1, ThreadBasicInformation, ThreadInformation, 0x30u, &v26);
  if ( v9 )
  {
    LastError = RtlNtStatusToDosError(v9);
    goto LABEL_23;
  }
  if ( !*((_QWORD *)&ThreadInformation[0] + 1) )
  {
    LastError = 13;
    goto LABEL_23;
  }
  IsWow64 = WctIsWow64(a1[1]);
  v12 = (const void *)*((_QWORD *)&ThreadInformation[0] + 1);
  v13 = IsWow64;
  if ( IsWow64 )
    v12 = (const void *)(*((_QWORD *)&ThreadInformation[0] + 1) + 0x2000LL);
  v14 = -(__int64)(IsWow64 != 0) & 0xFFFFFFFFFFFFF7C0uLL;
  v15 = utl::make_unique<unsigned char [0],0>(v24, v14 + 6256);
  utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
    &lpBuffer,
    v15);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(v24);
  v16 = lpBuffer;
  if ( !lpBuffer )
  {
    LastError = 8;
LABEL_13:
    v4 = v28;
    v5 = v27;
    goto LABEL_23;
  }
  if ( !ReadProcessMemory(a1[1], v12, lpBuffer, v14 + 6256, 0) )
  {
    LastError = GetLastError();
    goto LABEL_13;
  }
  if ( v13 )
    v17 = *((unsigned int *)v16 + 987);
  else
    v17 = v16[743];
  v4 = v28;
  v5 = v27;
  if ( ((v17 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    LastError = 0;
    v8 = v17;
  }
  else
  {
    LastError = 1168;
  }
LABEL_23:
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&lpBuffer);
  if ( !LastError )
  {
    *v4 = 0;
    *v5 = 0;
    a2->ObjectType = WctSocketIoType;
    a2->ObjectStatus = WctStatusNotOwned;
    if ( WctIsSocketRestorable(
           (struct _WCT_CLIENT_HANDLE *)a1,
           v8,
           &a2->LockObject.Alertable,
           v18,
           ReturnLength,
           a2->LockObject.ObjectName,
           v21,
           v22) )
    {
      a2->LockObject.Alertable = 0;
    }
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180051b74  mov     [rsp-38h+arg_8], rbx
0x180051b79  mov     [rsp-38h+arg_18], r9
0x180051b7e  mov     [rsp-38h+arg_10], r8
0x180051b83  push    rbp
0x180051b84  push    rsi
0x180051b85  push    rdi
0x180051b86  push    r12
0x180051b88  push    r13
0x180051b8a  push    r14
0x180051b8c  push    r15
0x180051b8e  mov     rbp, rsp
0x180051b91  sub     rsp, 80h
0x180051b98  mov     rsi, r9
0x180051b9b  mov     r15, r8
0x180051b9e  mov     r13, rdx
0x180051ba1  mov     r14, rcx
0x180051ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x180051bab  lea     r12, WPP_GLOBAL_Control
0x180051bb2  cmp     rcx, r12
0x180051bb5  jz      short loc_180051BD2
0x180051bb7  test    byte ptr [rcx+1Ch], 4
0x180051bbb  jz      short loc_180051BD2
0x180051bbd  mov     rcx, [rcx+10h]
0x180051bc1  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x180051bc8  mov     edx, 39h ; '9'
0x180051bcd  call    WPP_SF_
0x180051bd2  xorps   xmm0, xmm0
0x180051bd5  mov     [rbp+arg_0], 0
0x180051bdc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180051be0  mov     [rbp+lpBuffer], 0
0x180051be8  movups  [rbp+ThreadInformation], xmm0
0x180051bec  movups  [rbp+var_20], xmm0
0x180051bf0  movups  [rbp+var_10], xmm0
0x180051bf4  test    r14, r14
0x180051bf7  jz      loc_180051D29
0x180051bfd  mov     rcx, [r14]; ThreadHandle
0x180051c00  lea     rax, [rbp+arg_0]
0x180051c04  lea     r9d, [rdi+31h]; ThreadInformationLength
0x180051c08  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180051c0d  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x180051c11  xor     edx, edx; ThreadInformationClass
0x180051c13  call    cs:__imp_NtQueryInformationThread
0x180051c1a  nop     dword ptr [rax+rax+00h]
0x180051c1f  test    eax, eax
0x180051c21  jz      short loc_180051C38
0x180051c23  mov     ecx, eax; Status
0x180051c25  call    cs:__imp_RtlNtStatusToDosError
0x180051c2c  nop     dword ptr [rax+rax+00h]
0x180051c31  mov     ebx, eax
0x180051c33  jmp     loc_180051D2E
0x180051c38  cmp     qword ptr [rbp+ThreadInformation+8], 0
0x180051c3d  jnz     short loc_180051C49
0x180051c3f  mov     ebx, 0Dh
0x180051c44  jmp     loc_180051D2E
0x180051c49  mov     rcx, [r14+8]; void *
0x180051c4d  call    ?WctIsWow64@@YAHPEAX@Z; WctIsWow64(void *)
0x180051c52  mov     r12, qword ptr [rbp+ThreadInformation+8]
0x180051c56  mov     esi, eax
0x180051c58  test    eax, eax
0x180051c5a  jz      short loc_180051C63
0x180051c5c  add     r12, 2000h
0x180051c63  neg     eax
0x180051c65  lea     rcx, [rbp+var_38]
0x180051c69  sbb     r15, r15
0x180051c6c  and     r15, 0FFFFFFFFFFFFF7C0h
0x180051c73  lea     rdx, [r15+1870h]
0x180051c7a  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x180051c7f  mov     rdx, rax
0x180051c82  lea     rcx, [rbp+lpBuffer]
0x180051c86  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x180051c8b  lea     rcx, [rbp+var_38]; void *
0x180051c8f  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180051c94  mov     rbx, [rbp+lpBuffer]
0x180051c98  test    rbx, rbx
0x180051c9b  jnz     short loc_180051CB3
0x180051c9d  mov     ebx, 8
0x180051ca2  mov     rsi, [rbp+arg_18]
0x180051ca6  lea     r12, WPP_GLOBAL_Control
0x180051cad  mov     r15, [rbp+arg_10]
0x180051cb1  jmp     short loc_180051D2E
0x180051cb3  mov     rcx, [r14+8]; hProcess
0x180051cb7  lea     r9, [r15+1870h]; nSize
0x180051cbe  mov     r8, rbx; lpBuffer
0x180051cc1  mov     [rsp+80h+ReturnLength], 0; lpNumberOfBytesRead
0x180051cca  mov     rdx, r12; lpBaseAddress
0x180051ccd  call    cs:__imp_ReadProcessMemory
0x180051cd4  nop     dword ptr [rax+rax+00h]
0x180051cd9  test    eax, eax
0x180051cdb  jnz     short loc_180051CED
0x180051cdd  call    cs:__imp_GetLastError
0x180051ce4  nop     dword ptr [rax+rax+00h]
0x180051ce9  mov     ebx, eax
0x180051ceb  jmp     short loc_180051CA2
0x180051ced  test    esi, esi
0x180051cef  jz      short loc_180051CF9
0x180051cf1  mov     ecx, [rbx+0F6Ch]
0x180051cf7  jmp     short loc_180051D00
0x180051cf9  mov     rcx, [rbx+1738h]
0x180051d00  mov     rsi, [rbp+arg_18]
0x180051d04  lea     rax, [rcx+1]
0x180051d08  mov     r15, [rbp+arg_10]
0x180051d0c  lea     r12, WPP_GLOBAL_Control
0x180051d13  test    rax, 0FFFFFFFFFFFFFFFEh
0x180051d19  jnz     short loc_180051D22
0x180051d1b  mov     ebx, 490h
0x180051d20  jmp     short loc_180051D2E
0x180051d22  xor     ebx, ebx
0x180051d24  mov     rdi, rcx
0x180051d27  jmp     short loc_180051D2E
0x180051d29  mov     ebx, 57h ; 'W'
0x180051d2e  lea     rcx, [rbp+lpBuffer]; void *
0x180051d32  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180051d37  test    ebx, ebx
0x180051d39  jnz     short loc_180051D74
0x180051d3b  mov     [rsi], ebx
0x180051d3d  lea     rax, [r13+8]
0x180051d41  mov     [r15], ebx
0x180051d44  lea     rsi, [r13+110h]
0x180051d4b  mov     r8, rsi; int *
0x180051d4e  mov     dword ptr [r13+0], 0Bh
0x180051d56  mov     rdx, rdi; unsigned __int64
0x180051d59  mov     dword ptr [r13+4], 7
0x180051d61  mov     rcx, r14; struct _WCT_CLIENT_HANDLE *
0x180051d64  mov     [rsp+80h+var_58], rax; wchar_t *
0x180051d69  call    ?WctIsSocketRestorable@@YAKPEAU_WCT_CLIENT_HANDLE@@_KPEAHHKPEA_WPEAT_SOCKADDR_INET@@4@Z; WctIsSocketRestorable(_WCT_CLIENT_HANDLE *,unsigned __int64,int *,int,ulong,wchar_t *,_SOCKADDR_INET *,_SOCKADDR_INET *)
0x180051d6e  test    eax, eax
0x180051d70  jz      short loc_180051D74
0x180051d72  mov     [rsi], ebx
0x180051d74  mov     rcx, cs:WPP_GLOBAL_Control
0x180051d7b  cmp     rcx, r12
0x180051d7e  jz      short loc_180051D9E
0x180051d80  test    byte ptr [rcx+1Ch], 4
0x180051d84  jz      short loc_180051D9E
0x180051d86  mov     rcx, [rcx+10h]
0x180051d8a  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x180051d91  mov     edx, 3Ah ; ':'
0x180051d96  mov     r9d, ebx
0x180051d99  call    WPP_SF_d
0x180051d9e  mov     eax, ebx
0x180051da0  mov     rbx, [rsp+80h+arg_8]
0x180051da8  add     rsp, 80h
0x180051daf  pop     r15
0x180051db1  pop     r14
0x180051db3  pop     r13
0x180051db5  pop     r12
0x180051db7  pop     rdi
0x180051db8  pop     rsi
0x180051db9  pop     rbp
0x180051dba  retn
```

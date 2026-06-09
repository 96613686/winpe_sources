# WTSEnumerateProcessesA

- ea: `0x180001b90`
- end: `0x180001ea1`
- name: `WTSEnumerateProcessesA`
- size: `785`
- prototype: `BOOL __stdcall(HANDLE hServer, DWORD Reserved, DWORD Version, PWTS_PROCESS_INFOA *ppProcessInfo, DWORD *pCount)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001b90`
- `0x180001eb0`
- `0x180015582`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001dd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001e2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001e66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001e8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001dd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001e2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001e66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001e8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001da2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001da2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001e83`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001ca0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001ca0`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180001d43`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180001d43`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x180001c4a`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x180001c4a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001c71`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001d72`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001c71`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001d72`

## pseudocode

```c
BOOL __stdcall WTSEnumerateProcessesA(
        HANDLE hServer,
        DWORD Reserved,
        DWORD Version,
        PWTS_PROCESS_INFOA *ppProcessInfo,
        DWORD *pCount)
{
  __int64 v5; // r13
  unsigned int v6; // edi
  PWTS_PROCESS_INFOW v7; // r14
  __int64 v8; // r12
  WCHAR *pProcessName; // rdx
  __int64 v10; // rcx
  LPWSTR v11; // rax
  unsigned __int16 v12; // bx
  ULONG v13; // r8d
  NTSTATUS v14; // ebx
  PSID pUserSid; // rcx
  __int64 v16; // rbx
  struct _WTS_PROCESS_INFOA *v17; // rax
  struct _WTS_PROCESS_INFOA *v18; // r15
  CHAR *v19; // rbp
  __int64 i; // rdi
  DWORD SessionId; // eax
  struct _WTS_PROCESS_INFOW *v22; // rsi
  struct _WTS_PROCESS_INFOA *v23; // r14
  LPWSTR v24; // rax
  __int64 v25; // rcx
  NTSTATUS v26; // ebx
  __int64 v27; // rcx
  PSID v28; // rcx
  DWORD LengthSid; // eax
  __int64 v30; // rbx
  DWORD v32; // ecx
  ULONG BytesInMultiByteString; // [rsp+30h] [rbp-58h] BYREF
  DWORD v34; // [rsp+34h] [rbp-54h] BYREF
  PWTS_PROCESS_INFOW ppProcessInfoa; // [rsp+38h] [rbp-50h] BYREF

  ppProcessInfoa = 0;
  BytesInMultiByteString = 0;
  v34 = 0;
  if ( !WTSEnumerateProcessesW(hServer, Reserved, Version, &ppProcessInfoa, &v34) )
    goto LABEL_33;
  v5 = v34;
  v6 = 0;
  v7 = ppProcessInfoa;
  v8 = 0;
  while ( v6 < (unsigned int)v5 )
  {
    pProcessName = v7[v6].pProcessName;
    if ( !pProcessName )
    {
      v12 = 87;
LABEL_41:
      LocalFree(v7);
      v32 = v12;
LABEL_39:
      SetLastError(v32);
      goto LABEL_33;
    }
    v10 = 261;
    v11 = v7[v6].pProcessName;
    do
    {
      if ( !*v11 )
        break;
      ++v11;
      --v10;
    }
    while ( v10 );
    v12 = 87;
    if ( v10 )
    {
      v12 = 0;
      v13 = 2 * (261 - v10);
    }
    else
    {
      v13 = 0;
    }
    if ( !v10 )
      goto LABEL_41;
    v14 = RtlUnicodeToMultiByteSize(&BytesInMultiByteString, pProcessName, v13);
    if ( v14 )
    {
      LocalFree(v7);
      v32 = v14;
      goto LABEL_39;
    }
    pUserSid = v7[v6].pUserSid;
    if ( pUserSid )
    {
      v16 = v8 + BytesInMultiByteString + 1LL;
      v8 = v16 + GetLengthSid(pUserSid);
    }
    else
    {
      v8 += BytesInMultiByteString + 1LL;
    }
    ++v6;
  }
  v17 = (struct _WTS_PROCESS_INFOA *)LocalAlloc(0x40u, 24 * v5 + v8);
  v18 = v17;
  if ( !v17 )
  {
    LocalFree(v7);
LABEL_33:
    if ( ppProcessInfo )
      *ppProcessInfo = 0;
    if ( pCount )
      *pCount = 0;
    return 0;
  }
  v19 = (CHAR *)&v17[v5];
  for ( i = 0; (unsigned int)i < (unsigned int)v5; i = (unsigned int)(i + 1) )
  {
    SessionId = v7[i].SessionId;
    v22 = &v7[i];
    v23 = &v18[i];
    v23->SessionId = SessionId;
    v23->ProcessId = v22->ProcessId;
    v24 = v22->pProcessName;
    if ( !v24 )
      goto LABEL_44;
    v25 = 261;
    do
    {
      if ( !*v24 )
        break;
      ++v24;
      --v25;
    }
    while ( v25 );
    if ( !v25 )
    {
LABEL_44:
      LocalFree(ppProcessInfoa);
      LocalFree(v18);
      SetLastError(0x57u);
      goto LABEL_33;
    }
    v23->pProcessName = v19;
    v26 = RtlUnicodeToMultiByteN(v19, v8, &BytesInMultiByteString, v22->pProcessName, 2 * (261 - v25));
    if ( v26 )
    {
      LocalFree(ppProcessInfoa);
      LocalFree(v18);
      SetLastError(v26);
      goto LABEL_33;
    }
    v27 = BytesInMultiByteString + 1;
    v19[BytesInMultiByteString] = 0;
    v8 -= v27;
    v19 += BytesInMultiByteString + 1;
    v28 = v22->pUserSid;
    if ( v28 )
    {
      LengthSid = GetLengthSid(v28);
      v23->pUserSid = v19;
      v30 = LengthSid;
      memcpy_0(v19, v22->pUserSid, LengthSid);
      v8 -= v30;
      v19 += v30;
    }
    v7 = ppProcessInfoa;
  }
  LocalFree(v7);
  if ( ppProcessInfo )
  {
    *ppProcessInfo = v18;
    if ( pCount )
    {
      *pCount = v5;
      return 1;
    }
  }
  SetLastError(0x6F8u);
  return 0;
}

```

## disassembly

```asm
0x180001b90  mov     [rsp+arg_18], r9
0x180001b95  push    rbx
0x180001b96  push    rbp
0x180001b97  push    rsi
0x180001b98  push    rdi
0x180001b99  push    r12
0x180001b9b  push    r13
0x180001b9d  push    r14
0x180001b9f  push    r15
0x180001ba1  sub     rsp, 48h
0x180001ba5  xor     ebp, ebp
0x180001ba7  lea     rax, [rsp+88h+var_54]
0x180001bac  lea     r9, [rsp+88h+ppProcessInfo]; ppProcessInfo
0x180001bb1  mov     [rsp+88h+ppProcessInfo], rbp
0x180001bb6  mov     [rsp+88h+BytesInMultiByteString], ebp
0x180001bba  mov     [rsp+88h+var_54], ebp
0x180001bbe  mov     qword ptr [rsp+88h+UnicodeSize], rax; pCount
0x180001bc3  call    WTSEnumerateProcessesW
0x180001bc8  test    eax, eax
0x180001bca  jz      loc_180001DF5
0x180001bd0  mov     r13d, [rsp+88h+var_54]
0x180001bd5  mov     edi, ebp
0x180001bd7  mov     r14, [rsp+88h+ppProcessInfo]
0x180001bdc  mov     r12d, ebp
0x180001bdf  nop
0x180001be0  cmp     edi, r13d
0x180001be3  jnb     loc_180001C84
0x180001be9  mov     eax, edi
0x180001beb  lea     rcx, [rax+rax*2]
0x180001bef  mov     rdx, [r14+rcx*8+8]; UnicodeString
0x180001bf4  lea     rsi, [r14+rcx*8]
0x180001bf8  test    rdx, rdx
0x180001bfb  jz      loc_180001E32
0x180001c01  mov     ecx, 105h
0x180001c06  mov     rax, rdx
0x180001c09  nop     dword ptr [rax+00000000h]
0x180001c10  cmp     [rax], bp
0x180001c13  jz      short loc_180001C1F
0x180001c15  add     rax, 2
0x180001c19  sub     rcx, 1
0x180001c1d  jnz     short loc_180001C10
0x180001c1f  test    rcx, rcx
0x180001c22  mov     ebx, 80070057h
0x180001c27  cmovnz  ebx, ebp
0x180001c2a  jz      loc_180001E17
0x180001c30  mov     r8d, 105h
0x180001c36  sub     r8, rcx
0x180001c39  add     r8, r8; BytesInUnicodeString
0x180001c3c  test    rcx, rcx
0x180001c3f  jz      loc_180001E37
0x180001c45  lea     rcx, [rsp+88h+BytesInMultiByteString]; BytesInMultiByteString
0x180001c4a  call    cs:__imp_RtlUnicodeToMultiByteSize
0x180001c50  mov     ebx, eax
0x180001c52  test    eax, eax
0x180001c54  jnz     loc_180001E1F
0x180001c5a  mov     ebx, [rsp+88h+BytesInMultiByteString]
0x180001c5e  mov     rcx, [rsi+10h]; pSid
0x180001c62  inc     rbx
0x180001c65  add     rbx, r12
0x180001c68  test    rcx, rcx
0x180001c6b  jz      loc_180001DED
0x180001c71  call    cs:__imp_GetLengthSid
0x180001c77  mov     r12d, eax
0x180001c7a  add     r12, rbx
0x180001c7d  inc     edi
0x180001c7f  jmp     loc_180001BE0
0x180001c84  lea     rcx, ds:0[r13*2]
0x180001c8c  add     rcx, r13
0x180001c8f  lea     rbx, ds:0[rcx*8]
0x180001c97  mov     ecx, 40h ; '@'; uFlags
0x180001c9c  lea     rdx, [rbx+r12]; uBytes
0x180001ca0  call    cs:__imp_LocalAlloc
0x180001ca6  mov     r15, rax
0x180001ca9  test    rax, rax
0x180001cac  jz      loc_180001E45
0x180001cb2  lea     rbp, [rbx+rax]
0x180001cb6  xor     edi, edi
0x180001cb8  nop     dword ptr [rax+rax+00000000h]
0x180001cc0  cmp     edi, r13d
0x180001cc3  jnb     loc_180001D9F
0x180001cc9  lea     rcx, [rdi+rdi*2]
0x180001ccd  mov     eax, [r14+rcx*8]
0x180001cd1  lea     rsi, [r14+rcx*8]
0x180001cd5  lea     r14, [r15+rcx*8]
0x180001cd9  mov     [r14], eax
0x180001cdc  mov     eax, [rsi+4]
0x180001cdf  mov     [r14+4], eax
0x180001ce3  mov     rax, [rsi+8]
0x180001ce7  test    rax, rax
0x180001cea  jz      loc_180001E70
0x180001cf0  mov     ecx, 105h
0x180001cf5  cmp     word ptr [rax], 0
0x180001cf9  jz      short loc_180001D05
0x180001cfb  add     rax, 2
0x180001cff  sub     rcx, 1
0x180001d03  jnz     short loc_180001CF5
0x180001d05  xor     eax, eax
0x180001d07  mov     ebx, 80070057h
0x180001d0c  test    rcx, rcx
0x180001d0f  cmovnz  ebx, eax
0x180001d12  jz      loc_180001E75
0x180001d18  mov     eax, 105h
0x180001d1d  sub     rax, rcx
0x180001d20  add     rax, rax
0x180001d23  test    rcx, rcx
0x180001d26  jz      loc_180001E75
0x180001d2c  mov     [r14+8], rbp
0x180001d30  lea     r8, [rsp+88h+BytesInMultiByteString]; ResultSize
0x180001d35  mov     r9, [rsi+8]; UnicodeString
0x180001d39  mov     edx, r12d; MbSize
0x180001d3c  mov     rcx, rbp; MbString
0x180001d3f  mov     [rsp+88h+UnicodeSize], eax; UnicodeSize
0x180001d43  call    cs:__imp_RtlUnicodeToMultiByteN
0x180001d49  mov     ebx, eax
0x180001d4b  test    eax, eax
0x180001d4d  jnz     loc_180001E50
0x180001d53  mov     edx, [rsp+88h+BytesInMultiByteString]
0x180001d57  lea     ecx, [rdx+1]
0x180001d5a  mov     [rdx+rbp], al
0x180001d5d  sub     r12, rcx
0x180001d60  mov     ecx, [rsp+88h+BytesInMultiByteString]
0x180001d64  inc     ecx
0x180001d66  add     rbp, rcx
0x180001d69  mov     rcx, [rsi+10h]; pSid
0x180001d6d  test    rcx, rcx
0x180001d70  jz      short loc_180001D93
0x180001d72  call    cs:__imp_GetLengthSid
0x180001d78  mov     [r14+10h], rbp
0x180001d7c  mov     rcx, rbp; void *
0x180001d7f  mov     rdx, [rsi+10h]; Src
0x180001d83  mov     r8d, eax; Size
0x180001d86  mov     ebx, eax
0x180001d88  call    memcpy_0
0x180001d8d  sub     r12, rbx
0x180001d90  add     rbp, rbx
0x180001d93  mov     r14, [rsp+88h+ppProcessInfo]
0x180001d98  inc     edi
0x180001d9a  jmp     loc_180001CC0
0x180001d9f  mov     rcx, r14; hMem
0x180001da2  call    cs:__imp_LocalFree
0x180001da8  mov     rax, [rsp+88h+arg_18]
0x180001db0  test    rax, rax
0x180001db3  jz      short loc_180001DCF
0x180001db5  mov     [rax], r15
0x180001db8  mov     rax, [rsp+88h+pCount]
0x180001dc0  test    rax, rax
0x180001dc3  jz      short loc_180001DCF
0x180001dc5  mov     [rax], r13d
0x180001dc8  mov     eax, 1
0x180001dcd  jmp     short loc_180001DDC
0x180001dcf  mov     ecx, 6F8h; dwErrCode
0x180001dd4  call    cs:__imp_SetLastError
0x180001dda  xor     eax, eax
0x180001ddc  add     rsp, 48h
0x180001de0  pop     r15
0x180001de2  pop     r14
0x180001de4  pop     r13
0x180001de6  pop     r12
0x180001de8  pop     rdi
0x180001de9  pop     rsi
0x180001dea  pop     rbp
0x180001deb  pop     rbx
0x180001dec  retn
0x180001ded  mov     r12, rbx
0x180001df0  jmp     loc_180001C7D
0x180001df5  mov     rax, [rsp+88h+arg_18]
0x180001dfd  test    rax, rax
0x180001e00  jnz     loc_180001E99
0x180001e06  mov     rax, [rsp+88h+pCount]
0x180001e0e  test    rax, rax
0x180001e11  jz      short loc_180001DDA
0x180001e13  mov     [rax], ebp
0x180001e15  jmp     short loc_180001DDA
0x180001e17  mov     r8, rbp
0x180001e1a  jmp     loc_180001C3C
0x180001e1f  mov     rcx, r14; hMem
0x180001e22  call    cs:__imp_LocalFree
0x180001e28  mov     ecx, ebx; dwErrCode
0x180001e2a  call    cs:__imp_SetLastError
0x180001e30  jmp     short loc_180001DF5
0x180001e32  mov     ebx, 80070057h
0x180001e37  mov     rcx, r14; hMem
0x180001e3a  call    cs:__imp_LocalFree
0x180001e40  movzx   ecx, bx
0x180001e43  jmp     short loc_180001E2A
0x180001e45  mov     rcx, r14; hMem
0x180001e48  call    cs:__imp_LocalFree
0x180001e4e  jmp     short loc_180001DF5
0x180001e50  mov     rcx, [rsp+88h+ppProcessInfo]; hMem
0x180001e55  call    cs:__imp_LocalFree
0x180001e5b  mov     rcx, r15; hMem
0x180001e5e  call    cs:__imp_LocalFree
0x180001e64  mov     ecx, ebx; dwErrCode
0x180001e66  call    cs:__imp_SetLastError
0x180001e6c  xor     ebp, ebp
0x180001e6e  jmp     short loc_180001DF5
0x180001e70  mov     ebx, 80070057h
0x180001e75  mov     rcx, [rsp+88h+ppProcessInfo]; hMem
0x180001e7a  call    cs:__imp_LocalFree
0x180001e80  mov     rcx, r15; hMem
0x180001e83  call    cs:__imp_LocalFree
0x180001e89  movzx   ecx, bx; dwErrCode
0x180001e8c  call    cs:__imp_SetLastError
0x180001e92  xor     ebp, ebp
0x180001e94  jmp     loc_180001DF5
0x180001e99  mov     [rax], rbp
0x180001e9c  jmp     loc_180001E06
```

# WTSQueryUserConfigA

- ea: `0x180009df0`
- end: `0x180009fc5`
- name: `WTSQueryUserConfigA`
- size: `469`
- prototype: `BOOL __stdcall(LPSTR pServerName, LPSTR pUserName, WTS_CONFIG_CLASS WTSConfigClass, LPSTR *ppBuffer, DWORD *pBytesReturned)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180005c60`
- `0x180008acc`
- `0x180009c08`
- `0x180009df0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009fa5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009fa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f9c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009ee4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009f37`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009ee4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009f37`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180009f57`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180009f57`

## pseudocode

```c
BOOL __stdcall WTSQueryUserConfigA(
        LPSTR pServerName,
        LPSTR pUserName,
        WTS_CONFIG_CLASS WTSConfigClass,
        LPSTR *ppBuffer,
        DWORD *pBytesReturned)
{
  int v5; // edi
  LPWSTR v8; // rsi
  LPWSTR v9; // r15
  DWORD *v10; // r12
  DWORD LastError; // r14d
  int v12; // eax
  __int32 v13; // ebx
  __int32 v14; // ebx
  __int32 v15; // ebx
  __int32 v16; // ebx
  int v17; // ebx
  CHAR *v18; // rax
  LPWSTR v19; // rcx
  const WCHAR *v20; // rbx
  __int64 v21; // rax
  ULONG UnicodeSize; // edi
  CHAR *v23; // rax
  LPWSTR pUserNamea; // [rsp+30h] [rbp-10h] BYREF
  LPWSTR pServerNamea; // [rsp+38h] [rbp-8h] BYREF
  LPWSTR ppBuffera; // [rsp+98h] [rbp+58h] BYREF

  v5 = 0;
  ppBuffera = 0;
  pUserNamea = 0;
  pServerNamea = 0;
  v8 = 0;
  v9 = 0;
  if ( ppBuffer && (v10 = pBytesReturned) != 0 )
  {
    LastError = 0;
    v5 = CopyStringA((__int64)pUserName, &pUserNamea, 0);
    if ( v5 )
    {
      v12 = CopyStringA((__int64)pServerName, &pServerNamea, 0);
      v8 = pUserNamea;
      v5 = v12;
      v9 = pServerNamea;
      if ( !v12 )
        goto LABEL_28;
      v5 = WTSQueryUserConfigW(pServerNamea, pUserNamea, WTSConfigClass, &ppBuffera, v10);
      if ( !v5 )
      {
        LastError = GetLastError();
        goto LABEL_28;
      }
      if ( WTSConfigClass
        && (v13 = WTSConfigClass - 1) != 0
        && (v14 = v13 - 12) != 0
        && (v15 = v14 - 2) != 0
        && (v16 = v15 - 1) != 0
        && (v17 = v16 - 1) != 0 )
      {
        if ( v17 != 2 )
        {
          *ppBuffer = (LPSTR)ppBuffera;
          goto LABEL_28;
        }
        v18 = (CHAR *)LocalAlloc(0x40u, 0x44Cu);
        v5 = 0;
        *ppBuffer = v18;
        if ( v18 )
        {
          v5 = ConvertUserInfoFromUnicodeToAnsi(ppBuffera, v18);
          *v10 = 1100;
        }
        else
        {
          LastError = GetLastError();
        }
        v19 = ppBuffera;
      }
      else
      {
        v20 = ppBuffera;
        v21 = -1;
        do
          ++v21;
        while ( ppBuffera[v21] );
        UnicodeSize = 2 * v21 + 2;
        v23 = (CHAR *)LocalAlloc(0x40u, UnicodeSize);
        *ppBuffer = v23;
        if ( v23 )
        {
          RtlUnicodeToMultiByteN(v23, UnicodeSize, v10, v20, UnicodeSize);
          v5 = 1;
        }
        else
        {
          v5 = 0;
          LastError = GetLastError();
        }
        v19 = (LPWSTR)v20;
      }
      LocalFree(v19);
    }
    else
    {
      v8 = pUserNamea;
    }
  }
  else
  {
    LastError = 87;
  }
LABEL_28:
  if ( v8 )
    LocalFree(v8);
  if ( v9 )
    LocalFree(v9);
  SetLastError(LastError);
  return v5;
}

```

## disassembly

```asm
0x180009df0  mov     [rsp-38h+arg_8], rbx
0x180009df5  mov     [rsp-38h+arg_0], rcx
0x180009dfa  push    rbp
0x180009dfb  push    rsi
0x180009dfc  push    rdi
0x180009dfd  push    r12
0x180009dff  push    r13
0x180009e01  push    r14
0x180009e03  push    r15
0x180009e05  mov     rbp, rsp
0x180009e08  sub     rsp, 40h
0x180009e0c  xor     edi, edi
0x180009e0e  mov     r13, r9
0x180009e11  mov     [rbp+ppBuffer], rdi
0x180009e15  mov     ebx, r8d
0x180009e18  mov     [rbp+pUserName], rdi
0x180009e1c  mov     rax, rdx
0x180009e1f  mov     [rbp+pServerName], rdi
0x180009e23  mov     esi, edi
0x180009e25  mov     r15d, edi
0x180009e28  test    r9, r9
0x180009e2b  jz      loc_180009F80
0x180009e31  mov     r12, [rbp+pBytesReturned]
0x180009e35  test    r12, r12
0x180009e38  jz      loc_180009F80
0x180009e3e  xor     r8d, r8d
0x180009e41  lea     rdx, [rbp+pUserName]
0x180009e45  mov     rcx, rax
0x180009e48  mov     r14d, edi
0x180009e4b  call    _CopyStringA
0x180009e50  mov     edi, eax
0x180009e52  test    eax, eax
0x180009e54  jz      loc_180009F7A
0x180009e5a  mov     rcx, [rbp+arg_0]
0x180009e5e  lea     rdx, [rbp+pServerName]
0x180009e62  xor     r8d, r8d
0x180009e65  call    _CopyStringA
0x180009e6a  mov     rsi, [rbp+pUserName]
0x180009e6e  mov     edi, eax
0x180009e70  mov     r15, [rbp+pServerName]
0x180009e74  test    eax, eax
0x180009e76  jz      loc_180009F86
0x180009e7c  lea     r9, [rbp+ppBuffer]; ppBuffer
0x180009e80  mov     qword ptr [rsp+40h+UnicodeSize], r12; pBytesReturned
0x180009e85  mov     r8d, ebx; WTSConfigClass
0x180009e88  mov     rdx, rsi; pUserName
0x180009e8b  mov     rcx, r15; pServerName
0x180009e8e  call    WTSQueryUserConfigW
0x180009e93  xor     ecx, ecx
0x180009e95  mov     edi, eax
0x180009e97  test    eax, eax
0x180009e99  jnz     short loc_180009EA9
0x180009e9b  call    cs:__imp_GetLastError
0x180009ea1  mov     r14d, eax
0x180009ea4  jmp     loc_180009F86
0x180009ea9  test    ebx, ebx
0x180009eab  jz      short loc_180009F18
0x180009ead  sub     ebx, 1
0x180009eb0  jz      short loc_180009F18
0x180009eb2  sub     ebx, 0Ch
0x180009eb5  jz      short loc_180009F18
0x180009eb7  sub     ebx, 2
0x180009eba  jz      short loc_180009F18
0x180009ebc  sub     ebx, 1
0x180009ebf  jz      short loc_180009F18
0x180009ec1  sub     ebx, 1
0x180009ec4  jz      short loc_180009F18
0x180009ec6  cmp     ebx, 2
0x180009ec9  jz      short loc_180009ED8
0x180009ecb  mov     rax, [rbp+ppBuffer]
0x180009ecf  mov     [r13+0], rax
0x180009ed3  jmp     loc_180009F86
0x180009ed8  mov     ebx, 44Ch
0x180009edd  mov     ecx, 40h ; '@'; uFlags
0x180009ee2  mov     edx, ebx; uBytes
0x180009ee4  call    cs:__imp_LocalAlloc
0x180009eea  xor     edi, edi
0x180009eec  mov     [r13+0], rax
0x180009ef0  test    rax, rax
0x180009ef3  jz      short loc_180009F09
0x180009ef5  mov     rcx, [rbp+ppBuffer]
0x180009ef9  mov     rdx, rax
0x180009efc  call    ConvertUserInfoFromUnicodeToAnsi
0x180009f01  mov     edi, eax
0x180009f03  mov     [r12], ebx
0x180009f07  jmp     short loc_180009F12
0x180009f09  call    cs:__imp_GetLastError
0x180009f0f  mov     r14d, eax
0x180009f12  mov     rcx, [rbp+ppBuffer]
0x180009f16  jmp     short loc_180009F72
0x180009f18  mov     rbx, [rbp+ppBuffer]
0x180009f1c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009f20  inc     rax
0x180009f23  cmp     [rbx+rax*2], cx
0x180009f27  jnz     short loc_180009F20
0x180009f29  lea     edi, ds:2[rax*2]
0x180009f30  mov     ecx, 40h ; '@'; uFlags
0x180009f35  mov     edx, edi; uBytes
0x180009f37  call    cs:__imp_LocalAlloc
0x180009f3d  xor     ecx, ecx
0x180009f3f  mov     [r13+0], rax
0x180009f43  test    rax, rax
0x180009f46  jz      short loc_180009F64
0x180009f48  mov     r9, rbx; UnicodeString
0x180009f4b  mov     [rsp+40h+UnicodeSize], edi; UnicodeSize
0x180009f4f  mov     r8, r12; ResultSize
0x180009f52  mov     edx, edi; MbSize
0x180009f54  mov     rcx, rax; MbString
0x180009f57  call    cs:__imp_RtlUnicodeToMultiByteN
0x180009f5d  mov     edi, 1
0x180009f62  jmp     short loc_180009F6F
0x180009f64  mov     edi, ecx
0x180009f66  call    cs:__imp_GetLastError
0x180009f6c  mov     r14d, eax
0x180009f6f  mov     rcx, rbx; hMem
0x180009f72  call    cs:__imp_LocalFree
0x180009f78  jmp     short loc_180009F86
0x180009f7a  mov     rsi, [rbp+pUserName]
0x180009f7e  jmp     short loc_180009F86
0x180009f80  mov     r14d, 57h ; 'W'
0x180009f86  test    rsi, rsi
0x180009f89  jz      short loc_180009F94
0x180009f8b  mov     rcx, rsi; hMem
0x180009f8e  call    cs:__imp_LocalFree
0x180009f94  test    r15, r15
0x180009f97  jz      short loc_180009FA2
0x180009f99  mov     rcx, r15; hMem
0x180009f9c  call    cs:__imp_LocalFree
0x180009fa2  mov     ecx, r14d; dwErrCode
0x180009fa5  call    cs:__imp_SetLastError
0x180009fab  mov     rbx, [rsp+40h+arg_8]
0x180009fb3  mov     eax, edi
0x180009fb5  add     rsp, 40h
0x180009fb9  pop     r15
0x180009fbb  pop     r14
0x180009fbd  pop     r13
0x180009fbf  pop     r12
0x180009fc1  pop     rdi
0x180009fc2  pop     rsi
0x180009fc3  pop     rbp
0x180009fc4  retn
```

# CCabDecompress::static_FDIWrite(__int64,void *,uint)

- ea: `0x1800a0c60`
- end: `0x1800a0d70`
- name: `?static_FDIWrite@CCabDecompress@@KAI_JPEAXI@Z`
- size: `272`
- prototype: `UINT __cdecl(INT_PTR hf, void *pv, UINT cb)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004c64`
- `0x18001c368`
- `0x180020680`
- `0x1800a0c60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0cf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0cf4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a0c9f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a0c9f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a0ccb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a0ccb`

## pseudocode

```c
__int64 __fastcall CCabDecompress::static_FDIWrite(INT_PTR hf, void *pv, UINT cb)
{
  HANDLE *v6; // rcx
  DWORD LastError; // eax
  unsigned int v8; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  if ( hf && pv )
  {
    v6 = *(HANDLE **)hf;
    if ( !v6 || WaitForSingleObject(*v6, 0) )
    {
      if ( WriteFile(*(HANDLE *)(hf + 8), pv, cb, &NumberOfBytesWritten, 0) )
        return NumberOfBytesWritten;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        LastError = GetLastError();
        v8 = ERROR_HR_FROM_WIN32(LastError);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids, v8);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1800a0c60  mov     [rsp+arg_8], rbx
0x1800a0c65  mov     [rsp+arg_10], rsi
0x1800a0c6a  push    rdi
0x1800a0c6b  sub     rsp, 30h
0x1800a0c6f  mov     [rsp+38h+NumberOfBytesWritten], 0
0x1800a0c77  mov     esi, r8d
0x1800a0c7a  mov     rdi, rdx
0x1800a0c7d  mov     rbx, rcx
0x1800a0c80  test    rcx, rcx
0x1800a0c83  jz      loc_1800A0D2E
0x1800a0c89  test    rdx, rdx
0x1800a0c8c  jz      loc_1800A0D2E
0x1800a0c92  mov     rcx, [rcx]
0x1800a0c95  test    rcx, rcx
0x1800a0c98  jz      short loc_1800A0CB3
0x1800a0c9a  mov     rcx, [rcx]; hHandle
0x1800a0c9d  xor     edx, edx; dwMilliseconds
0x1800a0c9f  call    cs:__imp_WaitForSingleObject
0x1800a0ca6  nop     dword ptr [rax+rax+00h]
0x1800a0cab  test    eax, eax
0x1800a0cad  jz      loc_1800A0D5C
0x1800a0cb3  mov     rcx, [rbx+8]; hFile
0x1800a0cb7  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a0cbc  mov     r8d, esi; nNumberOfBytesToWrite
0x1800a0cbf  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1800a0cc8  mov     rdx, rdi; lpBuffer
0x1800a0ccb  call    cs:__imp_WriteFile
0x1800a0cd2  nop     dword ptr [rax+rax+00h]
0x1800a0cd7  test    eax, eax
0x1800a0cd9  jnz     short loc_1800A0D28
0x1800a0cdb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0ce2  lea     rax, WPP_GLOBAL_Control
0x1800a0ce9  cmp     rcx, rax
0x1800a0cec  jz      short loc_1800A0D5C
0x1800a0cee  test    byte ptr [rcx+1Ch], 1
0x1800a0cf2  jz      short loc_1800A0D5C
0x1800a0cf4  call    cs:__imp_GetLastError
0x1800a0cfb  nop     dword ptr [rax+rax+00h]
0x1800a0d00  mov     ecx, eax; unsigned int
0x1800a0d02  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800a0d07  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0d0e  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x1800a0d15  mov     edx, 3Ch ; '<'
0x1800a0d1a  mov     r9d, eax
0x1800a0d1d  mov     rcx, [rcx+10h]
0x1800a0d21  call    WPP_SF_d
0x1800a0d26  jmp     short loc_1800A0D5C
0x1800a0d28  mov     eax, [rsp+38h+NumberOfBytesWritten]
0x1800a0d2c  jmp     short loc_1800A0D5F
0x1800a0d2e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0d35  lea     rax, WPP_GLOBAL_Control
0x1800a0d3c  cmp     rcx, rax
0x1800a0d3f  jz      short loc_1800A0D5C
0x1800a0d41  test    byte ptr [rcx+1Ch], 1
0x1800a0d45  jz      short loc_1800A0D5C
0x1800a0d47  mov     rcx, [rcx+10h]
0x1800a0d4b  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x1800a0d52  mov     edx, 3Bh ; ';'
0x1800a0d57  call    WPP_SF_
0x1800a0d5c  or      eax, 0FFFFFFFFh
0x1800a0d5f  mov     rbx, [rsp+38h+arg_8]
0x1800a0d64  mov     rsi, [rsp+38h+arg_10]
0x1800a0d69  add     rsp, 30h
0x1800a0d6d  pop     rdi
0x1800a0d6e  retn
```

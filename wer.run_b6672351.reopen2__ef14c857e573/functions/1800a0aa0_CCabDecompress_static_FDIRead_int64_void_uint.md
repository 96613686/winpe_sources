# CCabDecompress::static_FDIRead(__int64,void *,uint)

- ea: `0x1800a0aa0`
- end: `0x1800a0bb0`
- name: `?static_FDIRead@CCabDecompress@@KAI_JPEAXI@Z`
- size: `272`
- prototype: `UINT __cdecl(INT_PTR hf, void *pv, UINT cb)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004c64`
- `0x18001c368`
- `0x180020680`
- `0x1800a0aa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0b34`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a0adf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a0adf`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a0b0b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a0b0b`

## pseudocode

```c
__int64 __fastcall CCabDecompress::static_FDIRead(INT_PTR hf, void *pv, UINT cb)
{
  HANDLE *v6; // rcx
  DWORD LastError; // eax
  unsigned int v8; // eax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp+8h] BYREF

  NumberOfBytesRead = 0;
  if ( hf && pv )
  {
    v6 = *(HANDLE **)hf;
    if ( !v6 || WaitForSingleObject(*v6, 0) )
    {
      if ( ReadFile(*(HANDLE *)(hf + 8), pv, cb, &NumberOfBytesRead, 0) )
        return NumberOfBytesRead;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        LastError = GetLastError();
        v8 = ERROR_HR_FROM_WIN32(LastError);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids, v8);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1800a0aa0  mov     [rsp+arg_8], rbx
0x1800a0aa5  mov     [rsp+arg_10], rsi
0x1800a0aaa  push    rdi
0x1800a0aab  sub     rsp, 30h
0x1800a0aaf  mov     [rsp+38h+NumberOfBytesRead], 0
0x1800a0ab7  mov     esi, r8d
0x1800a0aba  mov     rdi, rdx
0x1800a0abd  mov     rbx, rcx
0x1800a0ac0  test    rcx, rcx
0x1800a0ac3  jz      loc_1800A0B6E
0x1800a0ac9  test    rdx, rdx
0x1800a0acc  jz      loc_1800A0B6E
0x1800a0ad2  mov     rcx, [rcx]
0x1800a0ad5  test    rcx, rcx
0x1800a0ad8  jz      short loc_1800A0AF3
0x1800a0ada  mov     rcx, [rcx]; hHandle
0x1800a0add  xor     edx, edx; dwMilliseconds
0x1800a0adf  call    cs:__imp_WaitForSingleObject
0x1800a0ae6  nop     dword ptr [rax+rax+00h]
0x1800a0aeb  test    eax, eax
0x1800a0aed  jz      loc_1800A0B9C
0x1800a0af3  mov     rcx, [rbx+8]; hFile
0x1800a0af7  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800a0afc  mov     r8d, esi; nNumberOfBytesToRead
0x1800a0aff  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1800a0b08  mov     rdx, rdi; lpBuffer
0x1800a0b0b  call    cs:__imp_ReadFile
0x1800a0b12  nop     dword ptr [rax+rax+00h]
0x1800a0b17  test    eax, eax
0x1800a0b19  jnz     short loc_1800A0B68
0x1800a0b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0b22  lea     rax, WPP_GLOBAL_Control
0x1800a0b29  cmp     rcx, rax
0x1800a0b2c  jz      short loc_1800A0B9C
0x1800a0b2e  test    byte ptr [rcx+1Ch], 1
0x1800a0b32  jz      short loc_1800A0B9C
0x1800a0b34  call    cs:__imp_GetLastError
0x1800a0b3b  nop     dword ptr [rax+rax+00h]
0x1800a0b40  mov     ecx, eax; unsigned int
0x1800a0b42  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800a0b47  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0b4e  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x1800a0b55  mov     edx, 3Ah ; ':'
0x1800a0b5a  mov     r9d, eax
0x1800a0b5d  mov     rcx, [rcx+10h]
0x1800a0b61  call    WPP_SF_d
0x1800a0b66  jmp     short loc_1800A0B9C
0x1800a0b68  mov     eax, [rsp+38h+NumberOfBytesRead]
0x1800a0b6c  jmp     short loc_1800A0B9F
0x1800a0b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0b75  lea     rax, WPP_GLOBAL_Control
0x1800a0b7c  cmp     rcx, rax
0x1800a0b7f  jz      short loc_1800A0B9C
0x1800a0b81  test    byte ptr [rcx+1Ch], 1
0x1800a0b85  jz      short loc_1800A0B9C
0x1800a0b87  mov     rcx, [rcx+10h]
0x1800a0b8b  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x1800a0b92  mov     edx, 39h ; '9'
0x1800a0b97  call    WPP_SF_
0x1800a0b9c  or      eax, 0FFFFFFFFh
0x1800a0b9f  mov     rbx, [rsp+38h+arg_8]
0x1800a0ba4  mov     rsi, [rsp+38h+arg_10]
0x1800a0ba9  add     rsp, 30h
0x1800a0bad  pop     rdi
0x1800a0bae  retn
```

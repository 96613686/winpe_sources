# CCabDecompress::static_FDIWrite(__int64,void *,uint)

- ea: `0x18009c360`
- end: `0x18009c45d`
- name: `?static_FDIWrite@CCabDecompress@@KAI_JPEAXI@Z`
- size: `253`
- prototype: `UINT __cdecl(INT_PTR hf, void *pv, UINT cb)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18001fe24`
- `0x18009c360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c3e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c3e8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009c39f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009c39f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18009c3c5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18009c3c5`

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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_79ef5c27a1f136def879418ea58f312b_Traceguids, v8);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_79ef5c27a1f136def879418ea58f312b_Traceguids);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18009c360  mov     [rsp+arg_8], rbx
0x18009c365  mov     [rsp+arg_10], rsi
0x18009c36a  push    rdi
0x18009c36b  sub     rsp, 30h
0x18009c36f  mov     [rsp+38h+NumberOfBytesWritten], 0
0x18009c377  mov     esi, r8d
0x18009c37a  mov     rdi, rdx
0x18009c37d  mov     rbx, rcx
0x18009c380  test    rcx, rcx
0x18009c383  jz      loc_18009C41C
0x18009c389  test    rdx, rdx
0x18009c38c  jz      loc_18009C41C
0x18009c392  mov     rcx, [rcx]
0x18009c395  test    rcx, rcx
0x18009c398  jz      short loc_18009C3AD
0x18009c39a  mov     rcx, [rcx]; hHandle
0x18009c39d  xor     edx, edx; dwMilliseconds
0x18009c39f  call    cs:__imp_WaitForSingleObject
0x18009c3a5  test    eax, eax
0x18009c3a7  jz      loc_18009C44A
0x18009c3ad  mov     rcx, [rbx+8]; hFile
0x18009c3b1  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18009c3b6  mov     r8d, esi; nNumberOfBytesToWrite
0x18009c3b9  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18009c3c2  mov     rdx, rdi; lpBuffer
0x18009c3c5  call    cs:__imp_WriteFile
0x18009c3cb  test    eax, eax
0x18009c3cd  jnz     short loc_18009C416
0x18009c3cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c3d6  lea     rax, WPP_GLOBAL_Control
0x18009c3dd  cmp     rcx, rax
0x18009c3e0  jz      short loc_18009C44A
0x18009c3e2  test    byte ptr [rcx+1Ch], 1
0x18009c3e6  jz      short loc_18009C44A
0x18009c3e8  call    cs:__imp_GetLastError
0x18009c3ee  mov     ecx, eax; unsigned int
0x18009c3f0  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009c3f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c3fc  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009c403  mov     edx, 3Ch ; '<'
0x18009c408  mov     r9d, eax
0x18009c40b  mov     rcx, [rcx+10h]
0x18009c40f  call    WPP_SF_d
0x18009c414  jmp     short loc_18009C44A
0x18009c416  mov     eax, [rsp+38h+NumberOfBytesWritten]
0x18009c41a  jmp     short loc_18009C44D
0x18009c41c  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c423  lea     rax, WPP_GLOBAL_Control
0x18009c42a  cmp     rcx, rax
0x18009c42d  jz      short loc_18009C44A
0x18009c42f  test    byte ptr [rcx+1Ch], 1
0x18009c433  jz      short loc_18009C44A
0x18009c435  mov     rcx, [rcx+10h]
0x18009c439  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009c440  mov     edx, 3Bh ; ';'
0x18009c445  call    WPP_SF_
0x18009c44a  or      eax, 0FFFFFFFFh
0x18009c44d  mov     rbx, [rsp+38h+arg_8]
0x18009c452  mov     rsi, [rsp+38h+arg_10]
0x18009c457  add     rsp, 30h
0x18009c45b  pop     rdi
0x18009c45c  retn
```

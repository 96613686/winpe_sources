# CCabDecompress::static_FDIRead(__int64,void *,uint)

- ea: `0x18009c1c0`
- end: `0x18009c2bd`
- name: `?static_FDIRead@CCabDecompress@@KAI_JPEAXI@Z`
- size: `253`
- prototype: `__int64 __fastcall(INT_PTR hf, void *pv, UINT cb)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18001fe24`
- `0x18009c1c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c248`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c248`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009c1ff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009c1ff`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009c225`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009c225`

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
0x18009c1c0  mov     [rsp+arg_8], rbx
0x18009c1c5  mov     [rsp+arg_10], rsi
0x18009c1ca  push    rdi
0x18009c1cb  sub     rsp, 30h
0x18009c1cf  mov     [rsp+38h+NumberOfBytesRead], 0
0x18009c1d7  mov     esi, r8d
0x18009c1da  mov     rdi, rdx
0x18009c1dd  mov     rbx, rcx
0x18009c1e0  test    rcx, rcx
0x18009c1e3  jz      loc_18009C27C
0x18009c1e9  test    rdx, rdx
0x18009c1ec  jz      loc_18009C27C
0x18009c1f2  mov     rcx, [rcx]
0x18009c1f5  test    rcx, rcx
0x18009c1f8  jz      short loc_18009C20D
0x18009c1fa  mov     rcx, [rcx]; hHandle
0x18009c1fd  xor     edx, edx; dwMilliseconds
0x18009c1ff  call    cs:__imp_WaitForSingleObject
0x18009c205  test    eax, eax
0x18009c207  jz      loc_18009C2AA
0x18009c20d  mov     rcx, [rbx+8]; hFile
0x18009c211  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18009c216  mov     r8d, esi; nNumberOfBytesToRead
0x18009c219  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18009c222  mov     rdx, rdi; lpBuffer
0x18009c225  call    cs:__imp_ReadFile
0x18009c22b  test    eax, eax
0x18009c22d  jnz     short loc_18009C276
0x18009c22f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c236  lea     rax, WPP_GLOBAL_Control
0x18009c23d  cmp     rcx, rax
0x18009c240  jz      short loc_18009C2AA
0x18009c242  test    byte ptr [rcx+1Ch], 1
0x18009c246  jz      short loc_18009C2AA
0x18009c248  call    cs:__imp_GetLastError
0x18009c24e  mov     ecx, eax; unsigned int
0x18009c250  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009c255  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c25c  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009c263  mov     edx, 3Ah ; ':'
0x18009c268  mov     r9d, eax
0x18009c26b  mov     rcx, [rcx+10h]
0x18009c26f  call    WPP_SF_d
0x18009c274  jmp     short loc_18009C2AA
0x18009c276  mov     eax, [rsp+38h+NumberOfBytesRead]
0x18009c27a  jmp     short loc_18009C2AD
0x18009c27c  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c283  lea     rax, WPP_GLOBAL_Control
0x18009c28a  cmp     rcx, rax
0x18009c28d  jz      short loc_18009C2AA
0x18009c28f  test    byte ptr [rcx+1Ch], 1
0x18009c293  jz      short loc_18009C2AA
0x18009c295  mov     rcx, [rcx+10h]
0x18009c299  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009c2a0  mov     edx, 39h ; '9'
0x18009c2a5  call    WPP_SF_
0x18009c2aa  or      eax, 0FFFFFFFFh
0x18009c2ad  mov     rbx, [rsp+38h+arg_8]
0x18009c2b2  mov     rsi, [rsp+38h+arg_10]
0x18009c2b7  add     rsp, 30h
0x18009c2bb  pop     rdi
0x18009c2bc  retn
```

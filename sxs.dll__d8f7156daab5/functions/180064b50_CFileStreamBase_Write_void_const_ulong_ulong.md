# CFileStreamBase::Write(void const *,ulong,ulong *)

- ea: `0x180064b50`
- end: `0x180064c88`
- name: `?Write@CFileStreamBase@@UEAAJPEBXKPEAK@Z`
- size: `312`
- prototype: `int(CFileStreamBase *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x18000a804`
- `0x18000df40`
- `0x18002ff90`
- `0x18005cc58`
- `0x18005d2b0`
- `0x180064b50`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064c04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064c04`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180064c27`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180064c27`

## pseudocode

```c
__int64 __fastcall CFileStreamBase::Write(HANDLE *this, const void *a2, DWORD a3, unsigned int *a4)
{
  const char *v8; // rcx
  DWORD v9; // ecx
  unsigned int v10; // ebx
  BOOL v12; // [rsp+30h] [rbp-40h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+34h] [rbp-3Ch] BYREF
  int v14; // [rsp+38h] [rbp-38h] BYREF
  __int64 v15; // [rsp+40h] [rbp-30h]
  __int64 *v16; // [rsp+48h] [rbp-28h]
  __int64 v17; // [rsp+50h] [rbp-20h]
  int v18; // [rsp+58h] [rbp-18h]
  BOOL *v19; // [rsp+60h] [rbp-10h]

  v12 = 0;
  v16 = &qword_180078280;
  v14 = 1;
  v19 = &v12;
  v15 = 0;
  v17 = 544438355;
  v18 = 290;
  CFrame::BaseEnter((CFrame *)&v14);
  NumberOfBytesWritten = 0;
  if ( a4 )
    *a4 = 0;
  if ( this[2] == (HANDLE)-1LL )
  {
    *v19 = -2147023537;
  }
  else if ( !a3 || a2 )
  {
    SetLastError(0);
    if ( WriteFile(this[2], a2, a3, &NumberOfBytesWritten, 0) )
    {
      v9 = NumberOfBytesWritten;
      if ( a4 )
        *a4 = NumberOfBytesWritten;
      v12 = v9 == 0;
    }
    else
    {
      CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v14);
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180078260);
    }
  }
  else
  {
    v18 = 298;
    FusionpTraceParameterCheck(v8);
    *v19 = -2147024809;
  }
  v10 = v12;
  CFnTracerHR::~CFnTracerHR((CFnTracerHR *)&v14);
  return v10;
}

```

## disassembly

```asm
0x180064b50  push    rbp
0x180064b52  push    rbx
0x180064b53  push    rsi
0x180064b54  push    rdi
0x180064b55  push    r14
0x180064b57  mov     rbp, rsp
0x180064b5a  sub     rsp, 70h
0x180064b5e  mov     rax, cs:__security_cookie
0x180064b65  xor     rax, rsp
0x180064b68  mov     [rbp+var_8], rax
0x180064b6c  lea     rax, qword_180078280
0x180064b73  mov     [rbp+var_40], 0
0x180064b7a  mov     [rbp+var_28], rax
0x180064b7e  mov     r14, rcx
0x180064b81  lea     rax, [rbp+var_40]
0x180064b85  mov     [rbp+var_38], 1
0x180064b8c  lea     rcx, [rbp+var_38]; this
0x180064b90  mov     [rbp+var_10], rax
0x180064b94  mov     rbx, r9
0x180064b97  mov     [rbp+var_30], 0
0x180064b9f  mov     esi, r8d
0x180064ba2  mov     [rbp+var_20], 20737853h
0x180064baa  mov     rdi, rdx
0x180064bad  mov     [rbp+var_18], 122h
0x180064bb4  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180064bb9  mov     [rbp+NumberOfBytesWritten], 0
0x180064bc0  test    rbx, rbx
0x180064bc3  jz      short loc_180064BCB
0x180064bc5  mov     dword ptr [rbx], 0
0x180064bcb  cmp     qword ptr [r14+10h], 0FFFFFFFFFFFFFFFFh
0x180064bd0  jnz     short loc_180064BE1
0x180064bd2  mov     rax, [rbp+var_10]
0x180064bd6  mov     dword ptr [rax], 8007054Fh
0x180064bdc  jmp     loc_180064C62
0x180064be1  test    esi, esi
0x180064be3  jz      short loc_180064C02
0x180064be5  test    rdi, rdi
0x180064be8  jnz     short loc_180064C02
0x180064bea  mov     [rbp+var_18], 12Ah
0x180064bf1  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180064bf6  mov     rax, [rbp+var_10]
0x180064bfa  mov     dword ptr [rax], 80070057h
0x180064c00  jmp     short loc_180064C62
0x180064c02  xor     ecx, ecx; dwErrCode
0x180064c04  call    cs:__imp_SetLastError
0x180064c0b  nop     dword ptr [rax+rax+00h]
0x180064c10  mov     rcx, [r14+10h]; hFile
0x180064c14  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180064c18  mov     r8d, esi; nNumberOfBytesToWrite
0x180064c1b  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x180064c24  mov     rdx, rdi; lpBuffer
0x180064c27  call    cs:__imp_WriteFile
0x180064c2e  nop     dword ptr [rax+rax+00h]
0x180064c33  test    eax, eax
0x180064c35  jnz     short loc_180064C4E
0x180064c37  lea     rcx, [rbp+var_38]; this
0x180064c3b  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x180064c40  lea     rcx, off_180078260; struct _CALL_SITE_INFO *
0x180064c47  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180064c4c  jmp     short loc_180064C62
0x180064c4e  mov     ecx, [rbp+NumberOfBytesWritten]
0x180064c51  test    rbx, rbx
0x180064c54  jz      short loc_180064C58
0x180064c56  mov     [rbx], ecx
0x180064c58  xor     eax, eax
0x180064c5a  test    ecx, ecx
0x180064c5c  setz    al
0x180064c5f  mov     [rbp+var_40], eax
0x180064c62  mov     ebx, [rbp+var_40]
0x180064c65  lea     rcx, [rbp+var_38]; this
0x180064c69  call    ??1CFnTracerHR@@QEAA@XZ; CFnTracerHR::~CFnTracerHR(void)
0x180064c6e  mov     eax, ebx
0x180064c70  mov     rcx, [rbp+var_8]
0x180064c74  xor     rcx, rsp; StackCookie
0x180064c77  call    __security_check_cookie
0x180064c7c  add     rsp, 70h
0x180064c80  pop     r14
0x180064c82  pop     rdi
0x180064c83  pop     rsi
0x180064c84  pop     rbx
0x180064c85  pop     rbp
0x180064c86  retn
```

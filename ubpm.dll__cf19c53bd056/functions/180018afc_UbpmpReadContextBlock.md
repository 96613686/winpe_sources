# UbpmpReadContextBlock

- ea: `0x180018afc`
- end: `0x180018e35`
- name: `UbpmpReadContextBlock`
- size: `825`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017e88`

## callees

- `0x18000f9a0`
- `0x180016d80`
- `0x180018afc`
- `0x180019d90`
- `0x18003cc78`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018bff`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018c96`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018bff`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018c96`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180018d1e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180018d1e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180018c26`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180018cbd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180018c26`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180018cbd`
- `ntdll!RtlReleaseSRWLockShared` at `0x180018b90`
- `ntdll!RtlReleaseSRWLockShared` at `0x180018b90`
- `ntdll!RtlAcquireSRWLockShared` at `0x180018b32`
- `ntdll!RtlAcquireSRWLockShared` at `0x180018b32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018dc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018df7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018dc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018df7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018e2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018e2a`

## pseudocode

```c
__int64 __fastcall UbpmpReadContextBlock(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        _DWORD *a6,
        unsigned __int16 **a7)
{
  void *v11; // rbp
  void *v12; // r14
  __int64 v13; // rax
  unsigned int v14; // edi
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rsi
  DWORD LastError; // edi
  __int64 v18; // r8
  _QWORD *v19; // rcx
  void *v21; // rcx
  void *v22; // rcx
  DWORD v23; // edi
  void *v24; // rax
  void *v25; // rcx
  int v26; // edx
  _DWORD *v27; // rax
  HANDLE v28; // rdx
  DWORD LengthSid; // edi
  void *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // [rsp+30h] [rbp-58h]
  HANDLE hObject; // [rsp+90h] [rbp+8h] BYREF

  hObject = 0;
  v32 = a1 + 64;
  v11 = 0;
  v12 = 0;
  RtlAcquireSRWLockShared(a1 + 64);
  if ( (*(_BYTE *)(a1 + 104) & 4) != 0 )
  {
    v16 = 0;
    LastError = 1067;
    goto LABEL_6;
  }
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(*(_QWORD *)(a1 + 152) + 2 * v13) );
  v14 = 2 * v13 + 2;
  v15 = (unsigned __int16 *)UbpmAlloc(v14);
  v16 = v15;
  if ( v15 )
  {
    StringCbCopyW(v15, v14, *(const unsigned __int16 **)(a1 + 152));
    v21 = *(void **)(a1 + 184);
    if ( !v21 )
      goto LABEL_10;
    LengthSid = GetLengthSid(v21);
    v30 = UbpmAlloc(LengthSid);
    v11 = v30;
    if ( !v30 )
    {
      LastError = GetLastError();
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v31 = 202;
        goto LABEL_24;
      }
      goto LABEL_6;
    }
    if ( CopySid(LengthSid, v30, *(PSID *)(a1 + 184)) )
    {
LABEL_10:
      v22 = *(void **)(a1 + 176);
      if ( v22 )
      {
        v23 = GetLengthSid(v22);
        v24 = UbpmAlloc(v23);
        v12 = v24;
        if ( !v24 )
        {
          LastError = GetLastError();
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v31 = 204;
            goto LABEL_24;
          }
          goto LABEL_6;
        }
        if ( !CopySid(v23, v24, *(PSID *)(a1 + 176)) )
        {
          LastError = GetLastError();
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v31 = 205;
            goto LABEL_24;
          }
          goto LABEL_6;
        }
      }
      v25 = *(void **)(a1 + 248);
      if ( !v25 || DuplicateTokenEx(v25, 0x2000000u, 0, SecurityImpersonation, TokenPrimary, &hObject) )
      {
        LastError = 0;
        v26 = *(_DWORD *)(a1 + 32);
        *a2 = *(_DWORD *)(a1 + 192);
        v27 = a6;
        *a3 = v11;
        v11 = 0;
        *a4 = v12;
        v12 = 0;
        *v27 = v26;
        v28 = hObject;
        hObject = 0;
        *a5 = v28;
        *a7 = v16;
        v16 = 0;
        goto LABEL_6;
      }
      LastError = GetLastError();
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_6;
      v31 = 206;
    }
    else
    {
      LastError = GetLastError();
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_6;
      v31 = 203;
    }
LABEL_24:
    WPP_SF_qdd(v19[2], v31, v18, a1, *(_DWORD *)(a1 + 32), LastError);
    goto LABEL_6;
  }
  LastError = GetLastError();
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v31 = 201;
    goto LABEL_24;
  }
LABEL_6:
  RtlReleaseSRWLockShared(v32);
  if ( hObject )
    CloseHandle(hObject);
  UBPM_MIDL_user_free(v11);
  UBPM_MIDL_user_free(v12);
  UBPM_MIDL_user_free(v16);
  return LastError;
}

```

## disassembly

```asm
0x180018afc  mov     rax, rsp
0x180018aff  push    rbx
0x180018b00  push    rbp
0x180018b01  push    rsi
0x180018b02  push    rdi
0x180018b03  push    r12
0x180018b05  push    r13
0x180018b07  push    r14
0x180018b09  push    r15
0x180018b0b  sub     rsp, 48h
0x180018b0f  xor     edi, edi
0x180018b11  mov     rbx, rcx
0x180018b14  mov     [rax+8], rdi
0x180018b18  mov     r15, r9
0x180018b1b  lea     rax, [rcx+40h]
0x180018b1f  mov     r12, r8
0x180018b22  mov     rcx, rax
0x180018b25  mov     [rsp+88h+var_58], rax
0x180018b2a  mov     r13, rdx
0x180018b2d  mov     ebp, edi
0x180018b2f  mov     r14d, edi
0x180018b32  call    cs:__imp_RtlAcquireSRWLockShared
0x180018b38  test    byte ptr [rbx+68h], 4
0x180018b3c  jnz     loc_180018D76
0x180018b42  mov     rcx, [rbx+98h]
0x180018b49  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018b4d  inc     rax
0x180018b50  cmp     [rcx+rax*2], di
0x180018b54  jnz     short loc_180018B4D
0x180018b56  lea     edi, ds:2[rax*2]
0x180018b5d  mov     ecx, edi; Size
0x180018b5f  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180018b64  mov     rsi, rax
0x180018b67  test    rax, rax
0x180018b6a  jnz     short loc_180018BD2
0x180018b6c  call    cs:__imp_GetLastError
0x180018b72  mov     edi, eax
0x180018b74  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b7b  lea     rax, WPP_GLOBAL_Control
0x180018b82  cmp     rcx, rax
0x180018b85  jnz     loc_180018D83
0x180018b8b  mov     rcx, [rsp+88h+var_58]
0x180018b90  call    cs:__imp_RtlReleaseSRWLockShared
0x180018b96  mov     rcx, [rsp+88h+hObject]; hObject
0x180018b9e  test    rcx, rcx
0x180018ba1  jnz     loc_180018E2A
0x180018ba7  mov     rcx, rbp
0x180018baa  call    UBPM_MIDL_user_free
0x180018baf  mov     rcx, r14
0x180018bb2  call    UBPM_MIDL_user_free
0x180018bb7  mov     rcx, rsi
0x180018bba  call    UBPM_MIDL_user_free
0x180018bbf  mov     eax, edi
0x180018bc1  add     rsp, 48h
0x180018bc5  pop     r15
0x180018bc7  pop     r14
0x180018bc9  pop     r13
0x180018bcb  pop     r12
0x180018bcd  pop     rdi
0x180018bce  pop     rsi
0x180018bcf  pop     rbp
0x180018bd0  pop     rbx
0x180018bd1  retn
0x180018bd2  mov     r8, [rbx+98h]; unsigned __int16 *
0x180018bd9  mov     rcx, rsi; unsigned __int16 *
0x180018bdc  mov     edx, edi; unsigned __int64
0x180018bde  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180018be3  mov     rcx, [rbx+0B8h]; pSid
0x180018bea  test    rcx, rcx
0x180018bed  jnz     loc_180018C96
0x180018bf3  mov     rcx, [rbx+0B0h]; pSid
0x180018bfa  test    rcx, rcx
0x180018bfd  jz      short loc_180018C34
0x180018bff  call    cs:__imp_GetLengthSid
0x180018c05  mov     ecx, eax; Size
0x180018c07  mov     edi, eax
0x180018c09  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180018c0e  mov     r14, rax
0x180018c11  test    rax, rax
0x180018c14  jz      loc_180018DC4
0x180018c1a  mov     r8, [rbx+0B0h]; pSourceSid
0x180018c21  mov     rdx, rax; pDestinationSid
0x180018c24  mov     ecx, edi; nDestinationSidLength
0x180018c26  call    cs:__imp_CopySid
0x180018c2c  test    eax, eax
0x180018c2e  jz      loc_180018DF7
0x180018c34  mov     rcx, [rbx+0F8h]; hExistingToken
0x180018c3b  test    rcx, rcx
0x180018c3e  jnz     loc_180018CFB
0x180018c44  mov     eax, [rbx+0C0h]
0x180018c4a  xor     edi, edi
0x180018c4c  mov     edx, [rbx+20h]
0x180018c4f  mov     [r13+0], eax
0x180018c53  mov     rax, [rsp+88h+arg_28]
0x180018c5b  mov     [r12], rbp
0x180018c5f  xor     ebp, ebp
0x180018c61  mov     [r15], r14
0x180018c64  xor     r14d, r14d
0x180018c67  mov     [rax], edx
0x180018c69  mov     rax, [rsp+88h+arg_20]
0x180018c71  mov     rdx, [rsp+88h+hObject]
0x180018c79  mov     [rsp+88h+hObject], rdi
0x180018c81  mov     [rax], rdx
0x180018c84  mov     rax, [rsp+88h+arg_30]
0x180018c8c  mov     [rax], rsi
0x180018c8f  xor     esi, esi
0x180018c91  jmp     loc_180018B8B
0x180018c96  call    cs:__imp_GetLengthSid
0x180018c9c  mov     ecx, eax; Size
0x180018c9e  mov     edi, eax
0x180018ca0  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180018ca5  mov     rbp, rax
0x180018ca8  test    rax, rax
0x180018cab  jz      loc_180018D94
0x180018cb1  mov     r8, [rbx+0B8h]; pSourceSid
0x180018cb8  mov     rdx, rax; pDestinationSid
0x180018cbb  mov     ecx, edi; nDestinationSidLength
0x180018cbd  call    cs:__imp_CopySid
0x180018cc3  test    eax, eax
0x180018cc5  jnz     loc_180018BF3
0x180018ccb  call    cs:__imp_GetLastError
0x180018cd1  mov     edi, eax
0x180018cd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180018cda  lea     rax, WPP_GLOBAL_Control
0x180018ce1  cmp     rcx, rax
0x180018ce4  jz      loc_180018B8B
0x180018cea  test    byte ptr [rcx+1Ch], 1
0x180018cee  jz      loc_180018B8B
0x180018cf4  mov     edx, 0CBh
0x180018cf9  jmp     short loc_180018D5A
0x180018cfb  lea     rax, [rsp+88h+hObject]
0x180018d03  mov     r9d, 2; ImpersonationLevel
0x180018d09  mov     [rsp+88h+phNewToken], rax; phNewToken
0x180018d0e  xor     r8d, r8d; lpTokenAttributes
0x180018d11  mov     edx, 2000000h; dwDesiredAccess
0x180018d16  mov     [rsp+88h+TokenType], 1; TokenType
0x180018d1e  call    cs:__imp_DuplicateTokenEx
0x180018d24  test    eax, eax
0x180018d26  jnz     loc_180018C44
0x180018d2c  call    cs:__imp_GetLastError
0x180018d32  mov     edi, eax
0x180018d34  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d3b  lea     rax, WPP_GLOBAL_Control
0x180018d42  cmp     rcx, rax
0x180018d45  jz      loc_180018B8B
0x180018d4b  test    byte ptr [rcx+1Ch], 1
0x180018d4f  jz      loc_180018B8B
0x180018d55  mov     edx, 0CEh
0x180018d5a  mov     eax, [rbx+20h]
0x180018d5d  mov     r9, rbx
0x180018d60  mov     rcx, [rcx+10h]
0x180018d64  mov     dword ptr [rsp+88h+phNewToken], edi
0x180018d68  mov     [rsp+88h+TokenType], eax
0x180018d6c  call    WPP_SF_qdd
0x180018d71  jmp     loc_180018B8B
0x180018d76  mov     rsi, rdi
0x180018d79  mov     edi, 42Bh
0x180018d7e  jmp     loc_180018B8B
0x180018d83  test    byte ptr [rcx+1Ch], 1
0x180018d87  jz      loc_180018B8B
0x180018d8d  mov     edx, 0C9h
0x180018d92  jmp     short loc_180018D5A
0x180018d94  call    cs:__imp_GetLastError
0x180018d9a  mov     edi, eax
0x180018d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018da3  lea     rax, WPP_GLOBAL_Control
0x180018daa  cmp     rcx, rax
0x180018dad  jz      loc_180018B8B
0x180018db3  test    byte ptr [rcx+1Ch], 1
0x180018db7  jz      loc_180018B8B
0x180018dbd  mov     edx, 0CAh
0x180018dc2  jmp     short loc_180018D5A
0x180018dc4  call    cs:__imp_GetLastError
0x180018dca  mov     edi, eax
0x180018dcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180018dd3  lea     rax, WPP_GLOBAL_Control
0x180018dda  cmp     rcx, rax
0x180018ddd  jz      loc_180018B8B
0x180018de3  test    byte ptr [rcx+1Ch], 1
0x180018de7  jz      loc_180018B8B
0x180018ded  mov     edx, 0CCh
0x180018df2  jmp     loc_180018D5A
0x180018df7  call    cs:__imp_GetLastError
0x180018dfd  mov     edi, eax
0x180018dff  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e06  lea     rax, WPP_GLOBAL_Control
0x180018e0d  cmp     rcx, rax
0x180018e10  jz      loc_180018B8B
0x180018e16  test    byte ptr [rcx+1Ch], 1
0x180018e1a  jz      loc_180018B8B
0x180018e20  mov     edx, 0CDh
0x180018e25  jmp     loc_180018D5A
0x180018e2a  call    cs:__imp_CloseHandle
0x180018e30  jmp     loc_180018BA7
```

# UbpmpReadContextBlock

- ea: `0x18000e6bc`
- end: `0x18000ea4a`
- name: `UbpmpReadContextBlock`
- size: `910`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000d9bc`

## callees

- `0x18000e6bc`
- `0x18000fbf0`
- `0x1800150c0`
- `0x1800191a0`
- `0x18003f678`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e7d2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e875`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e7d2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e875`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000e90f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000e90f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000e7ff`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000e8a2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000e7ff`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000e8a2`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000e75c`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000e75c`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000e6f2`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000e6f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ea39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ea39`

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
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  void *v30; // rcx
  void *v31; // rcx
  DWORD v32; // edi
  void *v33; // rax
  void *v34; // rcx
  int v35; // edx
  _DWORD *v36; // rax
  HANDLE v37; // rdx
  DWORD LengthSid; // edi
  void *v39; // rax
  __int64 v40; // rdx
  __int64 v41; // [rsp+30h] [rbp-58h]
  HANDLE hObject; // [rsp+90h] [rbp+8h] BYREF

  hObject = 0;
  v41 = a1 + 64;
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
    v30 = *(void **)(a1 + 184);
    if ( !v30 )
      goto LABEL_10;
    LengthSid = GetLengthSid(v30);
    v39 = UbpmAlloc(LengthSid);
    v11 = v39;
    if ( !v39 )
    {
      LastError = GetLastError();
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v40 = 202;
        goto LABEL_24;
      }
      goto LABEL_6;
    }
    if ( CopySid(LengthSid, v39, *(PSID *)(a1 + 184)) )
    {
LABEL_10:
      v31 = *(void **)(a1 + 176);
      if ( v31 )
      {
        v32 = GetLengthSid(v31);
        v33 = UbpmAlloc(v32);
        v12 = v33;
        if ( !v33 )
        {
          LastError = GetLastError();
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v40 = 204;
            goto LABEL_24;
          }
          goto LABEL_6;
        }
        if ( !CopySid(v32, v33, *(PSID *)(a1 + 176)) )
        {
          LastError = GetLastError();
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v40 = 205;
            goto LABEL_24;
          }
          goto LABEL_6;
        }
      }
      v34 = *(void **)(a1 + 248);
      if ( !v34 || DuplicateTokenEx(v34, 0x2000000u, 0, SecurityImpersonation, TokenPrimary, &hObject) )
      {
        LastError = 0;
        v35 = *(_DWORD *)(a1 + 32);
        *a2 = *(_DWORD *)(a1 + 192);
        v36 = a6;
        *a3 = v11;
        v11 = 0;
        *a4 = v12;
        v12 = 0;
        *v36 = v35;
        v37 = hObject;
        hObject = 0;
        *a5 = v37;
        *a7 = v16;
        v16 = 0;
        goto LABEL_6;
      }
      LastError = GetLastError();
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_6;
      v40 = 206;
    }
    else
    {
      LastError = GetLastError();
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_6;
      v40 = 203;
    }
LABEL_24:
    WPP_SF_qdd(v19[2], v40, v18, a1, *(_DWORD *)(a1 + 32), LastError, v41);
    goto LABEL_6;
  }
  LastError = GetLastError();
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v40 = 201;
    goto LABEL_24;
  }
LABEL_6:
  RtlReleaseSRWLockShared(v41);
  if ( hObject )
    CloseHandle(hObject);
  UBPM_MIDL_user_free(v11, v20, v21, v22);
  UBPM_MIDL_user_free(v12, v23, v24, v25);
  UBPM_MIDL_user_free(v16, v26, v27, v28);
  return LastError;
}

```

## disassembly

```asm
0x18000e6bc  mov     rax, rsp
0x18000e6bf  push    rbx
0x18000e6c0  push    rbp
0x18000e6c1  push    rsi
0x18000e6c2  push    rdi
0x18000e6c3  push    r12
0x18000e6c5  push    r13
0x18000e6c7  push    r14
0x18000e6c9  push    r15
0x18000e6cb  sub     rsp, 48h
0x18000e6cf  xor     edi, edi
0x18000e6d1  mov     rbx, rcx
0x18000e6d4  mov     [rax+8], rdi
0x18000e6d8  mov     r15, r9
0x18000e6db  lea     rax, [rcx+40h]
0x18000e6df  mov     r12, r8
0x18000e6e2  mov     rcx, rax
0x18000e6e5  mov     [rsp+88h+var_58], rax
0x18000e6ea  mov     r13, rdx
0x18000e6ed  mov     ebp, edi
0x18000e6ef  mov     r14d, edi
0x18000e6f2  call    cs:__imp_RtlAcquireSRWLockShared
0x18000e6f9  nop     dword ptr [rax+rax+00h]
0x18000e6fe  test    byte ptr [rbx+68h], 4
0x18000e702  jnz     loc_18000E973
0x18000e708  mov     rcx, [rbx+98h]
0x18000e70f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e713  inc     rax
0x18000e716  cmp     [rcx+rax*2], di
0x18000e71a  jnz     short loc_18000E713
0x18000e71c  lea     edi, ds:2[rax*2]
0x18000e723  mov     ecx, edi; Size
0x18000e725  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18000e72a  mov     rsi, rax
0x18000e72d  test    rax, rax
0x18000e730  jnz     short loc_18000E7A5
0x18000e732  call    cs:__imp_GetLastError
0x18000e739  nop     dword ptr [rax+rax+00h]
0x18000e73e  mov     edi, eax
0x18000e740  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e747  lea     rax, WPP_GLOBAL_Control
0x18000e74e  cmp     rcx, rax
0x18000e751  jnz     loc_18000E980
0x18000e757  mov     rcx, [rsp+88h+var_58]
0x18000e75c  call    cs:__imp_RtlReleaseSRWLockShared
0x18000e763  nop     dword ptr [rax+rax+00h]
0x18000e768  mov     rcx, [rsp+88h+hObject]; hObject
0x18000e770  test    rcx, rcx
0x18000e773  jnz     loc_18000EA39
0x18000e779  mov     rcx, rbp
0x18000e77c  call    UBPM_MIDL_user_free
0x18000e781  mov     rcx, r14
0x18000e784  call    UBPM_MIDL_user_free
0x18000e789  mov     rcx, rsi
0x18000e78c  call    UBPM_MIDL_user_free
0x18000e791  mov     eax, edi
0x18000e793  add     rsp, 48h
0x18000e797  pop     r15
0x18000e799  pop     r14
0x18000e79b  pop     r13
0x18000e79d  pop     r12
0x18000e79f  pop     rdi
0x18000e7a0  pop     rsi
0x18000e7a1  pop     rbp
0x18000e7a2  pop     rbx
0x18000e7a3  retn
0x18000e7a5  mov     r8, [rbx+98h]; unsigned __int16 *
0x18000e7ac  mov     rcx, rsi; unsigned __int16 *
0x18000e7af  mov     edx, edi; unsigned __int64
0x18000e7b1  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e7b6  mov     rcx, [rbx+0B8h]; pSid
0x18000e7bd  test    rcx, rcx
0x18000e7c0  jnz     loc_18000E875
0x18000e7c6  mov     rcx, [rbx+0B0h]; pSid
0x18000e7cd  test    rcx, rcx
0x18000e7d0  jz      short loc_18000E813
0x18000e7d2  call    cs:__imp_GetLengthSid
0x18000e7d9  nop     dword ptr [rax+rax+00h]
0x18000e7de  mov     ecx, eax; Size
0x18000e7e0  mov     edi, eax
0x18000e7e2  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18000e7e7  mov     r14, rax
0x18000e7ea  test    rax, rax
0x18000e7ed  jz      loc_18000E9C7
0x18000e7f3  mov     r8, [rbx+0B0h]; pSourceSid
0x18000e7fa  mov     rdx, rax; pDestinationSid
0x18000e7fd  mov     ecx, edi; nDestinationSidLength
0x18000e7ff  call    cs:__imp_CopySid
0x18000e806  nop     dword ptr [rax+rax+00h]
0x18000e80b  test    eax, eax
0x18000e80d  jz      loc_18000EA00
0x18000e813  mov     rcx, [rbx+0F8h]; hExistingToken
0x18000e81a  test    rcx, rcx
0x18000e81d  jnz     loc_18000E8EC
0x18000e823  mov     eax, [rbx+0C0h]
0x18000e829  xor     edi, edi
0x18000e82b  mov     edx, [rbx+20h]
0x18000e82e  mov     [r13+0], eax
0x18000e832  mov     rax, [rsp+88h+arg_28]
0x18000e83a  mov     [r12], rbp
0x18000e83e  xor     ebp, ebp
0x18000e840  mov     [r15], r14
0x18000e843  xor     r14d, r14d
0x18000e846  mov     [rax], edx
0x18000e848  mov     rax, [rsp+88h+arg_20]
0x18000e850  mov     rdx, [rsp+88h+hObject]
0x18000e858  mov     [rsp+88h+hObject], rdi
0x18000e860  mov     [rax], rdx
0x18000e863  mov     rax, [rsp+88h+arg_30]
0x18000e86b  mov     [rax], rsi
0x18000e86e  xor     esi, esi
0x18000e870  jmp     loc_18000E757
0x18000e875  call    cs:__imp_GetLengthSid
0x18000e87c  nop     dword ptr [rax+rax+00h]
0x18000e881  mov     ecx, eax; Size
0x18000e883  mov     edi, eax
0x18000e885  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18000e88a  mov     rbp, rax
0x18000e88d  test    rax, rax
0x18000e890  jz      loc_18000E991
0x18000e896  mov     r8, [rbx+0B8h]; pSourceSid
0x18000e89d  mov     rdx, rax; pDestinationSid
0x18000e8a0  mov     ecx, edi; nDestinationSidLength
0x18000e8a2  call    cs:__imp_CopySid
0x18000e8a9  nop     dword ptr [rax+rax+00h]
0x18000e8ae  test    eax, eax
0x18000e8b0  jnz     loc_18000E7C6
0x18000e8b6  call    cs:__imp_GetLastError
0x18000e8bd  nop     dword ptr [rax+rax+00h]
0x18000e8c2  mov     edi, eax
0x18000e8c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8cb  lea     rax, WPP_GLOBAL_Control
0x18000e8d2  cmp     rcx, rax
0x18000e8d5  jz      loc_18000E757
0x18000e8db  test    byte ptr [rcx+1Ch], 1
0x18000e8df  jz      loc_18000E757
0x18000e8e5  mov     edx, 0CBh
0x18000e8ea  jmp     short loc_18000E957
0x18000e8ec  lea     rax, [rsp+88h+hObject]
0x18000e8f4  mov     r9d, 2; ImpersonationLevel
0x18000e8fa  mov     [rsp+88h+phNewToken], rax; phNewToken
0x18000e8ff  xor     r8d, r8d; lpTokenAttributes
0x18000e902  mov     edx, 2000000h; dwDesiredAccess
0x18000e907  mov     [rsp+88h+TokenType], 1; TokenType
0x18000e90f  call    cs:__imp_DuplicateTokenEx
0x18000e916  nop     dword ptr [rax+rax+00h]
0x18000e91b  test    eax, eax
0x18000e91d  jnz     loc_18000E823
0x18000e923  call    cs:__imp_GetLastError
0x18000e92a  nop     dword ptr [rax+rax+00h]
0x18000e92f  mov     edi, eax
0x18000e931  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e938  lea     rax, WPP_GLOBAL_Control
0x18000e93f  cmp     rcx, rax
0x18000e942  jz      loc_18000E757
0x18000e948  test    byte ptr [rcx+1Ch], 1
0x18000e94c  jz      loc_18000E757
0x18000e952  mov     edx, 0CEh
0x18000e957  mov     eax, [rbx+20h]
0x18000e95a  mov     r9, rbx
0x18000e95d  mov     rcx, [rcx+10h]
0x18000e961  mov     dword ptr [rsp+88h+phNewToken], edi
0x18000e965  mov     [rsp+88h+TokenType], eax
0x18000e969  call    WPP_SF_qdd
0x18000e96e  jmp     loc_18000E757
0x18000e973  mov     rsi, rdi
0x18000e976  mov     edi, 42Bh
0x18000e97b  jmp     loc_18000E757
0x18000e980  test    byte ptr [rcx+1Ch], 1
0x18000e984  jz      loc_18000E757
0x18000e98a  mov     edx, 0C9h
0x18000e98f  jmp     short loc_18000E957
0x18000e991  call    cs:__imp_GetLastError
0x18000e998  nop     dword ptr [rax+rax+00h]
0x18000e99d  mov     edi, eax
0x18000e99f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9a6  lea     rax, WPP_GLOBAL_Control
0x18000e9ad  cmp     rcx, rax
0x18000e9b0  jz      loc_18000E757
0x18000e9b6  test    byte ptr [rcx+1Ch], 1
0x18000e9ba  jz      loc_18000E757
0x18000e9c0  mov     edx, 0CAh
0x18000e9c5  jmp     short loc_18000E957
0x18000e9c7  call    cs:__imp_GetLastError
0x18000e9ce  nop     dword ptr [rax+rax+00h]
0x18000e9d3  mov     edi, eax
0x18000e9d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9dc  lea     rax, WPP_GLOBAL_Control
0x18000e9e3  cmp     rcx, rax
0x18000e9e6  jz      loc_18000E757
0x18000e9ec  test    byte ptr [rcx+1Ch], 1
0x18000e9f0  jz      loc_18000E757
0x18000e9f6  mov     edx, 0CCh
0x18000e9fb  jmp     loc_18000E957
0x18000ea00  call    cs:__imp_GetLastError
0x18000ea07  nop     dword ptr [rax+rax+00h]
0x18000ea0c  mov     edi, eax
0x18000ea0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea15  lea     rax, WPP_GLOBAL_Control
0x18000ea1c  cmp     rcx, rax
0x18000ea1f  jz      loc_18000E757
0x18000ea25  test    byte ptr [rcx+1Ch], 1
0x18000ea29  jz      loc_18000E757
0x18000ea2f  mov     edx, 0CDh
0x18000ea34  jmp     loc_18000E957
0x18000ea39  call    cs:__imp_CloseHandle
0x18000ea40  nop     dword ptr [rax+rax+00h]
0x18000ea45  jmp     loc_18000E779
```

# CreateWorkerProcessSid(_GUID const *,_GUID const *,ushort const *,uchar *)

- ea: `0x180091a24`
- end: `0x180091c01`
- name: `?CreateWorkerProcessSid@@YAJPEBU_GUID@@0PEBGPEAE@Z`
- size: `477`
- prototype: `int(const struct _GUID *, const struct _GUID *, const unsigned __int16 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c44ac`

## callees

- `0x18008f5e4`
- `0x180091a24`
- `0x180091c08`
- `0x1800a1d10`
- `0x1800da308`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180091b81`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180091b81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091b8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091b8b`
- `KERNELBASE!AppContainerRegisterSid` at `0x180091b5e`
- `KERNELBASE!AppContainerRegisterSid` at `0x180091b5e`
- `ntdll!RtlValidSid` at `0x180091afb`
- `ntdll!RtlValidSid` at `0x180091afb`
- `ntdll!RtlLengthSid` at `0x180091b1c`
- `ntdll!RtlLengthSid` at `0x180091b1c`

## pseudocode

```c
__int64 __fastcall CreateWorkerProcessSid(
        const struct _GUID *a1,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4)
{
  unsigned int v7; // edi
  signed int v8; // ebx
  __int128 v9; // xmm0
  int active; // eax
  int v11; // eax
  signed int LastError; // eax
  __int64 v14; // [rsp+20h] [rbp-50h]
  _BYTE Sid[40]; // [rsp+38h] [rbp-38h] BYREF

  *(_QWORD *)&Sid[32] = 0;
  *(_OWORD *)a4 = 0;
  *((_OWORD *)a4 + 1) = 0;
  *((_QWORD *)a4 + 4) = 0;
  memset(Sid, 0, 32);
  if ( !a1 )
  {
    v7 = -2147024809;
    v8 = -2147024809;
    goto LABEL_23;
  }
  if ( !a4 )
  {
    v7 = -2147024809;
    v8 = -2147024809;
    goto LABEL_23;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_S_guid__guid_((_DWORD)a1, (_DWORD)a2, (_DWORD)a3, (_DWORD)a3, (__int64)a1);
  v9 = (__int128)*a1;
  *(_DWORD *)&Sid[2] = 0;
  *(_WORD *)&Sid[6] = 3840;
  *(_DWORD *)&Sid[36] = *(_DWORD *)PacWorkerClient::s_WorkerCallbackGuid.Data4;
  *(_WORD *)Sid = 2049;
  *(_DWORD *)&Sid[8] = 2;
  *(_OWORD *)&Sid[12] = v9;
  *(_QWORD *)&Sid[28] = *(_QWORD *)&PacWorkerClient::s_WorkerCallbackGuid.Data1;
  if ( !RtlValidSid(Sid) )
  {
    v7 = -2147023559;
    v8 = -2147023559;
    goto LABEL_23;
  }
  if ( RtlLengthSid(Sid) != 40 )
  {
    v7 = -2147023559;
    v8 = -2147023559;
    goto LABEL_23;
  }
  active = AddActiveAppContainerSids(Sid);
  v8 = active;
  if ( active < 0 )
  {
    v7 = active;
    goto LABEL_23;
  }
  v11 = AppContainerRegisterSid(Sid, a3, a3);
  v8 = v11;
  if ( v11 < 0 )
  {
    v7 = v11;
LABEL_21:
    RemoveActiveAppContainerSids(Sid);
    goto LABEL_23;
  }
  if ( !CopySid(0x28u, a4, Sid) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147418113;
    v7 = v8;
    goto LABEL_21;
  }
  v8 = 0;
  v7 = 0;
LABEL_23:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 21, WPP_7810932928333f0bccbe94d071e2aef3_Traceguids, (unsigned int)v8, v14);
  return v7;
}

```

## disassembly

```asm
0x180091a24  mov     [rsp-18h+arg_8], rbx
0x180091a29  push    rbp
0x180091a2a  push    rsi
0x180091a2b  push    rdi
0x180091a2c  mov     rbp, rsp
0x180091a2f  sub     rsp, 70h
0x180091a33  mov     rax, cs:__security_cookie
0x180091a3a  xor     rax, rsp
0x180091a3d  mov     [rbp+var_10], rax
0x180091a41  xor     eax, eax
0x180091a43  mov     [rbp+var_3C], 0
0x180091a4a  mov     [rbp+var_18], rax
0x180091a4e  xorps   xmm1, xmm1
0x180091a51  xorps   xmm0, xmm0
0x180091a54  mov     rdi, r9
0x180091a57  mov     rsi, r8
0x180091a5a  mov     rbx, rcx
0x180091a5d  movups  xmmword ptr [r9], xmm1
0x180091a61  movups  xmmword ptr [r9+10h], xmm1
0x180091a66  mov     [r9+20h], rax
0x180091a6a  movups  [rbp+Sid], xmm0
0x180091a6e  movups  [rbp+var_28], xmm0
0x180091a72  test    rcx, rcx
0x180091a75  jnz     short loc_180091A8A
0x180091a77  mov     edi, 80070057h
0x180091a7c  mov     [rbp+var_3C], 0F1h
0x180091a83  mov     ebx, edi
0x180091a85  jmp     loc_180091BC1
0x180091a8a  test    rdi, rdi
0x180091a8d  jnz     short loc_180091AA2
0x180091a8f  mov     edi, 80070057h
0x180091a94  mov     [rbp+var_3C], 0F3h
0x180091a9b  mov     ebx, edi
0x180091a9d  jmp     loc_180091BC1
0x180091aa2  test    byte ptr cs:xmmword_180107A60, 20h
0x180091aa9  jz      short loc_180091AB8
0x180091aab  mov     r9, rsi
0x180091aae  mov     [rsp+70h+var_50], rbx
0x180091ab3  call    WPP_SF_S_guid__guid_
0x180091ab8  mov     eax, cs:dword_1800EB398
0x180091abe  lea     rcx, [rbp+Sid]; Sid
0x180091ac2  movups  xmm0, xmmword ptr [rbx]
0x180091ac5  mov     dword ptr [rbp+Sid+2], eax
0x180091ac8  movzx   eax, cs:word_1800EB39C
0x180091acf  movsd   xmm1, qword ptr cs:?s_WorkerCallbackGuid@PacWorkerClient@@0U_GUID@@A.Data1; _GUID PacWorkerClient::s_WorkerCallbackGuid ...
0x180091ad7  mov     word ptr [rbp+Sid+6], ax
0x180091adb  mov     eax, dword ptr cs:?s_WorkerCallbackGuid@PacWorkerClient@@0U_GUID@@A.Data4; _GUID PacWorkerClient::s_WorkerCallbackGuid ...
0x180091ae1  mov     dword ptr [rbp+var_18+4], eax
0x180091ae4  mov     word ptr [rbp+Sid], 801h
0x180091aea  mov     dword ptr [rbp+Sid+8], 2
0x180091af1  movdqu  [rbp+Sid+0Ch], xmm0
0x180091af6  movsd   qword ptr [rbp+var_28+0Ch], xmm1
0x180091afb  call    cs:__imp_RtlValidSid
0x180091b01  test    al, al
0x180091b03  jnz     short loc_180091B18
0x180091b05  mov     edi, 80070539h
0x180091b0a  mov     [rbp+var_3C], 136h
0x180091b11  mov     ebx, edi
0x180091b13  jmp     loc_180091BC1
0x180091b18  lea     rcx, [rbp+Sid]; Sid
0x180091b1c  call    cs:__imp_RtlLengthSid
0x180091b22  cmp     eax, 28h ; '('
0x180091b25  jz      short loc_180091B3A
0x180091b27  mov     edi, 80070539h
0x180091b2c  mov     [rbp+var_3C], 139h
0x180091b33  mov     ebx, edi
0x180091b35  jmp     loc_180091BC1
0x180091b3a  lea     rcx, [rbp+Sid]; pSourceSid
0x180091b3e  call    ?AddActiveAppContainerSids@@YAJQEAE@Z; AddActiveAppContainerSids(uchar * const)
0x180091b43  mov     ebx, eax
0x180091b45  test    eax, eax
0x180091b47  jns     short loc_180091B54
0x180091b49  mov     [rbp+var_3C], 13Fh
0x180091b50  mov     edi, eax
0x180091b52  jmp     short loc_180091BC1
0x180091b54  mov     r8, rsi
0x180091b57  lea     rcx, [rbp+Sid]
0x180091b5b  mov     rdx, rsi
0x180091b5e  call    cs:__imp_AppContainerRegisterSid
0x180091b64  mov     ebx, eax
0x180091b66  test    eax, eax
0x180091b68  jns     short loc_180091B75
0x180091b6a  mov     [rbp+var_3C], 149h
0x180091b71  mov     edi, eax
0x180091b73  jmp     short loc_180091BB2
0x180091b75  lea     r8, [rbp+Sid]; pSourceSid
0x180091b79  mov     rdx, rdi; pDestinationSid
0x180091b7c  mov     ecx, 28h ; '('; nDestinationSidLength
0x180091b81  call    cs:__imp_CopySid
0x180091b87  test    eax, eax
0x180091b89  jnz     short loc_180091BBD
0x180091b8b  call    cs:__imp_GetLastError
0x180091b91  mov     ebx, eax
0x180091b93  test    eax, eax
0x180091b95  jle     short loc_180091BA0
0x180091b97  movzx   ebx, ax
0x180091b9a  or      ebx, 80070000h
0x180091ba0  test    ebx, ebx
0x180091ba2  js      short loc_180091BA9
0x180091ba4  mov     ebx, 8000FFFFh
0x180091ba9  mov     edi, ebx
0x180091bab  mov     [rbp+var_3C], 14Dh
0x180091bb2  lea     rcx, [rbp+Sid]; pSid2
0x180091bb6  call    ?RemoveActiveAppContainerSids@@YAJQEAE@Z; RemoveActiveAppContainerSids(uchar * const)
0x180091bbb  jmp     short loc_180091BC1
0x180091bbd  xor     ebx, ebx
0x180091bbf  xor     edi, edi
0x180091bc1  test    byte ptr cs:xmmword_180107A60, 20h
0x180091bc8  jz      short loc_180091BE3
0x180091bca  mov     edx, 15h
0x180091bcf  lea     r8, WPP_7810932928333f0bccbe94d071e2aef3_Traceguids
0x180091bd6  mov     ecx, 405h
0x180091bdb  mov     r9d, ebx
0x180091bde  call    WPP_SF_d
0x180091be3  mov     eax, edi
0x180091be5  mov     rcx, [rbp+var_10]
0x180091be9  xor     rcx, rsp; StackCookie
0x180091bec  call    __security_check_cookie
0x180091bf1  mov     rbx, [rsp+70h+arg_8]
0x180091bf9  add     rsp, 70h
0x180091bfd  pop     rdi
0x180091bfe  pop     rsi
0x180091bff  pop     rbp
0x180091c00  retn
```

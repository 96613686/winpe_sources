# BaseSrvSxsCreateActivationContextFromMessage

- ea: `0x180004a60`
- end: `0x180004e53`
- name: `BaseSrvSxsCreateActivationContextFromMessage`
- size: `1011`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004a50`

## callees

- `0x180003310`
- `0x180004a60`
- `0x180006cf0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180004dd7`
- `ntdll!RtlFreeHeap` at `0x180004dd7`
- `ntdll!NtClose` at `0x180004dad`
- `ntdll!NtClose` at `0x180004dad`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180004c66`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180004c66`
- `ntdll!DbgPrintEx` at `0x180004d89`
- `ntdll!DbgPrintEx` at `0x180004d89`
- `ntdll!NtOpenFile` at `0x180004cc4`
- `ntdll!NtOpenFile` at `0x180004cc4`
- `ntdll!NtQueryInformationFile` at `0x180004cf3`
- `ntdll!NtQueryInformationFile` at `0x180004d22`
- `ntdll!NtQueryInformationFile` at `0x180004cf3`
- `ntdll!NtQueryInformationFile` at `0x180004d22`
- `CSRSRV!CsrRevertToSelf` at `0x180004de7`
- `CSRSRV!CsrRevertToSelf` at `0x180004de7`
- `CSRSRV!CsrImpersonateClient` at `0x180004c41`
- `CSRSRV!CsrImpersonateClient` at `0x180004c41`
- `CSRSRV!CsrValidateMessageBuffer` at `0x180004b2d`
- `CSRSRV!CsrValidateMessageBuffer` at `0x180004b95`
- `CSRSRV!CsrValidateMessageBuffer` at `0x180004b2d`
- `CSRSRV!CsrValidateMessageBuffer` at `0x180004b95`

## pseudocode

```c
__int64 __fastcall BaseSrvSxsCreateActivationContextFromMessage(__int64 a1)
{
  __int64 v1; // r14
  unsigned __int16 *v2; // r13
  _WORD *v3; // r12
  __int64 v5; // rsi
  unsigned __int16 *v6; // rdi
  int v7; // eax
  unsigned __int64 v8; // rax
  _WORD *v9; // rcx
  bool v10; // zf
  unsigned __int64 v11; // rax
  __int16 v12; // di
  void *v13; // rsi
  char v14; // bl
  unsigned __int64 v15; // rax
  void *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // xmm1_8
  __int64 result; // rax
  int ActivationContextFromStruct; // eax
  unsigned int v21; // ecx
  void *FileHandle; // [rsp+58h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES FileHandle_8; // [rsp+60h] [rbp-A8h] BYREF
  PVOID P[2]; // [rsp+90h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v26; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v27; // [rsp+C0h] [rbp-48h]
  __int128 v28; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v29; // [rsp+E0h] [rbp-28h]
  __int128 FileInformation; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v31; // [rsp+F8h] [rbp-10h]
  __int64 v32; // [rsp+108h] [rbp+0h]

  v1 = a1 + 64;
  FileHandle_8.RootDirectory = (HANDLE)(a1 + 152);
  v2 = (unsigned __int16 *)(a1 + 96);
  *(_QWORD *)&FileHandle_8.Length = a1 + 96;
  FileHandle_8.ObjectName = (PUNICODE_STRING)(a1 + 200);
  v3 = (_WORD *)(a1 + 280);
  FileHandle_8.SecurityQualityOfService = (PVOID)(a1 + 280);
  *(_QWORD *)&FileHandle_8.Attributes = a1 + 216;
  v5 = 0;
  FileHandle_8.SecurityDescriptor = (PVOID)(a1 + 72);
  v26 = 0;
  v27 = 0;
  do
  {
    v6 = (unsigned __int16 *)*((_QWORD *)&FileHandle_8.Length + v5);
    if ( v6 )
    {
      v7 = *v6;
      if ( (_WORD)v7 && !*((_QWORD *)v6 + 1) || (unsigned __int16)v7 > v6[1] || (v7 & 1) != 0 )
        return 3221225485LL;
      if ( *((_QWORD *)v6 + 1) )
      {
        if ( !(unsigned __int8)CsrValidateMessageBuffer(a1, v6 + 4, (unsigned int)(v7 + 2), 1) )
        {
          DbgPrintEx(
            0x33u,
            0,
            "SXS: Validation of message buffer 0x%lx failed.\n"
            " Message:%p\n"
            " String %p{Length:0x%x, MaximumLength:0x%x, Buffer:%p}\n",
            v5,
            (const void *)a1,
            v6,
            *v6,
            v6[1],
            *((const void **)v6 + 1));
          return 3221225485LL;
        }
        v8 = *v6;
        v9 = (_WORD *)*((_QWORD *)v6 + 1);
        if ( (_WORD)v8 )
        {
          v11 = v8 >> 1;
          if ( !v9[v11] )
            goto LABEL_14;
          v10 = v9[v11 - 1] == 0;
        }
        else
        {
          v10 = *v9 == 0;
        }
        if ( !v10 )
          return 3221225485LL;
      }
    }
LABEL_14:
    v5 = (unsigned int)(v5 + 1);
  }
  while ( (_DWORD)v5 != 6 );
  v12 = 0;
  if ( *(_WORD *)(v1 + 218)
    && !(unsigned __int8)CsrValidateMessageBuffer(a1, v1 + 224, *(unsigned __int16 *)(v1 + 218), 1) )
  {
    v12 = *(_WORD *)(v1 + 218);
    *(_WORD *)(v1 + 218) = *v3 + 2;
  }
  v13 = *(void **)(*((_QWORD *)NtCurrentTeb()->CsrClientThread + 7) + 80LL);
  if ( (*(_BYTE *)v1 & 0x40) != 0 )
  {
    v32 = 0;
    v29 = 0;
    v14 = 0;
    v15 = *v2;
    v16 = 0;
    FileHandle = 0;
    *(_OWORD *)P = 0;
    memset(&FileHandle_8, 0, 44);
    IoStatusBlock = 0;
    FileInformation = 0;
    v31 = 0;
    v28 = 0;
    if ( (_WORD)v15 )
    {
      v17 = *(_QWORD *)(v1 + 40);
      if ( v17 )
      {
        if ( !*(_WORD *)(v17 + 2 * (v15 >> 1)) )
        {
          v14 = CsrImpersonateClient(0);
          if ( v14 )
          {
            if ( (int)RtlDosPathNameToNtPathName_U_WithStatus(*(_QWORD *)(v1 + 40), P, 0, 0) >= 0 )
            {
              FileHandle_8.ObjectName = (PUNICODE_STRING)P;
              FileHandle_8.Length = 48;
              FileHandle_8.RootDirectory = 0;
              FileHandle_8.Attributes = 64;
              *(_OWORD *)&FileHandle_8.SecurityDescriptor = 0;
              if ( NtOpenFile(&FileHandle, 0x120089u, &FileHandle_8, &IoStatusBlock, 5u, 0x60u) >= 0
                && NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation) >= 0
                && NtQueryInformationFile(
                     FileHandle,
                     &IoStatusBlock,
                     &v28,
                     0x18u,
                     FileMaximumInformation|FileBothDirectoryInformation) >= 0 )
              {
                v18 = v29;
                v16 = FileHandle;
                v26 = v28;
                *(_QWORD *)(v1 + 168) = v31;
                *(_QWORD *)&v27 = v18;
                goto LABEL_32;
              }
            }
          }
          v16 = FileHandle;
        }
      }
    }
    DWORD2(v27) |= 1u;
LABEL_32:
    if ( v16 )
    {
      NtClose(v16);
      FileHandle = 0;
    }
    if ( P[1] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
    if ( v14 )
      CsrRevertToSelf();
  }
  ActivationContextFromStruct = BaseSrvSxsCreateActivationContextFromStructEx(
                                  v13,
                                  v13,
                                  (unsigned int *)v1,
                                  (union _LARGE_INTEGER)&v26,
                                  0);
  v21 = 0;
  if ( ActivationContextFromStruct < 0 )
    v21 = ActivationContextFromStruct;
  result = v21;
  if ( v12 )
    *(_WORD *)(v1 + 218) = v12;
  return result;
}

```

## disassembly

```asm
0x180004a60  mov     r11, rsp
0x180004a63  mov     [r11+18h], rsi
0x180004a67  mov     [r11+20h], rdi
0x180004a6b  push    rbp
0x180004a6c  push    r12
0x180004a6e  push    r13
0x180004a70  push    r14
0x180004a72  push    r15
0x180004a74  lea     rbp, [r11-38h]
0x180004a78  sub     rsp, 110h
0x180004a7f  mov     rax, cs:__security_cookie
0x180004a86  xor     rax, rsp
0x180004a89  mov     [rbp+30h+var_28], rax
0x180004a8d  lea     r14, [rcx+40h]
0x180004a91  mov     [r11+10h], rbx
0x180004a95  lea     rax, [r14+58h]
0x180004a99  xorps   xmm0, xmm0
0x180004a9c  mov     qword ptr [rsp+130h+var_D0], rax
0x180004aa1  lea     r13, [r14+20h]
0x180004aa5  lea     rax, [r14+88h]
0x180004aac  mov     [rsp+130h+FileHandle+8], r13
0x180004ab1  mov     qword ptr [rsp+130h+var_D0+8], rax
0x180004ab6  lea     r12, [r14+0D8h]
0x180004abd  lea     rax, [r14+98h]
0x180004ac4  mov     [rbp+30h+var_B0], r12
0x180004ac8  mov     qword ptr [rsp+130h+var_C0], rax
0x180004acd  mov     r15, rcx
0x180004ad0  lea     rax, [r14+8]
0x180004ad4  xor     esi, esi
0x180004ad6  mov     qword ptr [rsp+130h+var_C0+8], rax
0x180004adb  movups  [rbp+30h+var_88], xmm0
0x180004adf  movups  [rbp+30h+var_78], xmm0
0x180004ae3  mov     rdi, [rsp+rsi*8+130h+FileHandle+8]
0x180004ae8  test    rdi, rdi
0x180004aeb  jz      short loc_180004B68
0x180004aed  movzx   eax, word ptr [rdi]
0x180004af0  test    ax, ax
0x180004af3  jz      short loc_180004B00
0x180004af5  cmp     qword ptr [rdi+8], 0
0x180004afa  jz      loc_180004D95
0x180004b00  cmp     ax, [rdi+2]
0x180004b04  ja      loc_180004D95
0x180004b0a  mov     r8d, eax
0x180004b0d  test    al, 1
0x180004b0f  jnz     loc_180004D95
0x180004b15  cmp     qword ptr [rdi+8], 0
0x180004b1a  jz      short loc_180004B68
0x180004b1c  add     r8d, 2
0x180004b20  lea     rdx, [rdi+8]
0x180004b24  mov     r9d, 1
0x180004b2a  mov     rcx, r15
0x180004b2d  call    cs:__imp_CsrValidateMessageBuffer
0x180004b34  nop     dword ptr [rax+rax+00h]
0x180004b39  test    al, al
0x180004b3b  jz      loc_180004D56
0x180004b41  movzx   eax, word ptr [rdi]
0x180004b44  mov     rcx, [rdi+8]
0x180004b48  test    ax, ax
0x180004b4b  jnz     short loc_180004B52
0x180004b4d  cmp     [rcx], ax
0x180004b50  jmp     short loc_180004B62
0x180004b52  shr     rax, 1
0x180004b55  cmp     word ptr [rcx+rax*2], 0
0x180004b5a  jz      short loc_180004B68
0x180004b5c  cmp     word ptr [rcx+rax*2-2], 0
0x180004b62  jnz     loc_180004D95
0x180004b68  inc     esi
0x180004b6a  cmp     esi, 6
0x180004b6d  jnz     loc_180004AE3
0x180004b73  xor     edi, edi
0x180004b75  movzx   eax, word ptr [r14+0DAh]
0x180004b7d  test    ax, ax
0x180004b80  jz      short loc_180004BBE
0x180004b82  mov     r8d, eax
0x180004b85  lea     rdx, [r14+0E0h]
0x180004b8c  mov     r9d, 1
0x180004b92  mov     rcx, r15
0x180004b95  call    cs:__imp_CsrValidateMessageBuffer
0x180004b9c  nop     dword ptr [rax+rax+00h]
0x180004ba1  test    al, al
0x180004ba3  jnz     short loc_180004BBE
0x180004ba5  movzx   eax, word ptr [r12]
0x180004baa  movzx   edi, word ptr [r14+0DAh]
0x180004bb2  add     ax, 2
0x180004bb6  mov     [r14+0DAh], ax
0x180004bbe  mov     rax, gs:70h
0x180004bc7  xor     r15d, r15d
0x180004bca  test    byte ptr [r14], 40h
0x180004bce  mov     rcx, [rax+38h]
0x180004bd2  mov     rsi, [rcx+50h]
0x180004bd6  jz      loc_180004DF3
0x180004bdc  xorps   xmm0, xmm0
0x180004bdf  xor     eax, eax
0x180004be1  xorps   xmm1, xmm1
0x180004be4  mov     [rbp+30h+var_30], rax
0x180004be8  mov     [rbp+30h+var_58], rax
0x180004bec  xor     bl, bl
0x180004bee  movzx   eax, word ptr [r13+0]
0x180004bf3  mov     ecx, r15d
0x180004bf6  mov     [rsp+130h+FileHandle], rcx
0x180004bfb  movups  [rsp+130h+var_D0+8], xmm0
0x180004c00  movups  xmmword ptr [rbp+30h+P], xmm0
0x180004c04  movups  xmmword ptr [rsp+130h+FileHandle+8], xmm0
0x180004c09  movups  [rsp+130h+var_C0+4], xmm0
0x180004c0e  movups  xmmword ptr [rbp+30h+IoStatusBlock], xmm0
0x180004c12  movups  [rbp+30h+FileInformation], xmm1
0x180004c16  movups  [rbp+30h+var_40], xmm1
0x180004c1a  movups  [rbp+30h+var_68], xmm0
0x180004c1e  test    ax, ax
0x180004c21  jz      loc_180004DA4
0x180004c27  mov     rdx, [r14+28h]
0x180004c2b  test    rdx, rdx
0x180004c2e  jz      loc_180004DA4
0x180004c34  shr     rax, 1
0x180004c37  cmp     [rdx+rax*2], cx
0x180004c3b  jnz     loc_180004DA4
0x180004c41  call    cs:__imp_CsrImpersonateClient
0x180004c48  nop     dword ptr [rax+rax+00h]
0x180004c4d  movzx   ebx, al
0x180004c50  test    al, al
0x180004c52  jz      loc_180004D9F
0x180004c58  mov     rcx, [r14+28h]
0x180004c5c  lea     rdx, [rbp+30h+P]
0x180004c60  xor     r9d, r9d
0x180004c63  xor     r8d, r8d
0x180004c66  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180004c6d  nop     dword ptr [rax+rax+00h]
0x180004c72  test    eax, eax
0x180004c74  js      loc_180004D9F
0x180004c7a  lea     rax, [rbp+30h+P]
0x180004c7e  mov     [rsp+130h+OpenOptions], 60h ; '`'; OpenOptions
0x180004c86  xorps   xmm0, xmm0
0x180004c89  mov     qword ptr [rsp+130h+var_D0+8], rax
0x180004c8e  lea     r9, [rbp+30h+IoStatusBlock]; IoStatusBlock
0x180004c92  mov     dword ptr [rsp+130h+FileHandle+8], 30h ; '0'
0x180004c9a  lea     r8, [rsp+130h+FileHandle+8]; ObjectAttributes
0x180004c9f  mov     qword ptr [rsp+130h+var_D0], r15
0x180004ca4  mov     edx, 120089h; DesiredAccess
0x180004ca9  mov     dword ptr [rsp+130h+var_C0], 40h ; '@'
0x180004cb1  lea     rcx, [rsp+130h+FileHandle]; FileHandle
0x180004cb6  mov     [rsp+130h+ShareAccess], 5; ShareAccess
0x180004cbe  movdqu  [rsp+130h+var_C0+8], xmm0
0x180004cc4  call    cs:__imp_NtOpenFile
0x180004ccb  nop     dword ptr [rax+rax+00h]
0x180004cd0  test    eax, eax
0x180004cd2  js      loc_180004D9F
0x180004cd8  mov     rcx, [rsp+130h+FileHandle]; FileHandle
0x180004cdd  lea     r8, [rbp+30h+FileInformation]; FileInformation
0x180004ce1  mov     r9d, 28h ; '('; Length
0x180004ce7  mov     [rsp+130h+ShareAccess], 4; FileInformationClass
0x180004cef  lea     rdx, [rbp+30h+IoStatusBlock]; IoStatusBlock
0x180004cf3  call    cs:__imp_NtQueryInformationFile
0x180004cfa  nop     dword ptr [rax+rax+00h]
0x180004cff  test    eax, eax
0x180004d01  js      loc_180004D9F
0x180004d07  mov     rcx, [rsp+130h+FileHandle]; FileHandle
0x180004d0c  lea     r8, [rbp+30h+var_68]; FileInformation
0x180004d10  mov     r9d, 18h; Length
0x180004d16  mov     [rsp+130h+ShareAccess], 3Bh ; ';'; FileInformationClass
0x180004d1e  lea     rdx, [rbp+30h+IoStatusBlock]; IoStatusBlock
0x180004d22  call    cs:__imp_NtQueryInformationFile
0x180004d29  nop     dword ptr [rax+rax+00h]
0x180004d2e  test    eax, eax
0x180004d30  js      short loc_180004D9F
0x180004d32  movups  xmm0, [rbp+30h+var_68]
0x180004d36  mov     rax, qword ptr [rbp+30h+var_40]
0x180004d3a  movsd   xmm1, [rbp+30h+var_58]
0x180004d3f  mov     rcx, [rsp+130h+FileHandle]
0x180004d44  movups  [rbp+30h+var_88], xmm0
0x180004d48  mov     [r14+0A8h], rax
0x180004d4f  movsd   qword ptr [rbp+30h+var_78], xmm1
0x180004d54  jmp     short loc_180004DA8
0x180004d56  movzx   ecx, word ptr [rdi+2]
0x180004d5a  lea     r8, Format; "SXS: Validation of message buffer 0x%lx"...
0x180004d61  movzx   edx, word ptr [rdi]
0x180004d64  mov     r9d, esi
0x180004d67  mov     rax, [rdi+8]
0x180004d6b  mov     [rsp+130h+var_F0], rax
0x180004d70  mov     dword ptr [rsp+130h+var_F8], ecx
0x180004d74  mov     ecx, 33h ; '3'; ComponentId
0x180004d79  mov     [rsp+130h+var_100], edx
0x180004d7d  xor     edx, edx; Level
0x180004d7f  mov     qword ptr [rsp+130h+OpenOptions], rdi
0x180004d84  mov     qword ptr [rsp+130h+ShareAccess], r15
0x180004d89  call    cs:__imp_DbgPrintEx
0x180004d90  nop     dword ptr [rax+rax+00h]
0x180004d95  mov     eax, 0C000000Dh
0x180004d9a  jmp     loc_180004E21
0x180004d9f  mov     rcx, [rsp+130h+FileHandle]; Handle
0x180004da4  or      dword ptr [rbp+30h+var_78+8], 1
0x180004da8  test    rcx, rcx
0x180004dab  jz      short loc_180004DBE
0x180004dad  call    cs:__imp_NtClose
0x180004db4  nop     dword ptr [rax+rax+00h]
0x180004db9  mov     [rsp+130h+FileHandle], r15
0x180004dbe  cmp     [rbp+30h+P+8], r15
0x180004dc2  jz      short loc_180004DE3
0x180004dc4  mov     rcx, gs:60h
0x180004dcd  xor     edx, edx; Flags
0x180004dcf  mov     r8, [rbp+30h+P+8]; P
0x180004dd3  mov     rcx, [rcx+30h]; HeapHandle
0x180004dd7  call    cs:__imp_RtlFreeHeap
0x180004dde  nop     dword ptr [rax+rax+00h]
0x180004de3  test    bl, bl
0x180004de5  jz      short loc_180004DF3
0x180004de7  call    cs:__imp_CsrRevertToSelf
0x180004dee  nop     dword ptr [rax+rax+00h]
0x180004df3  lea     r9, [rbp+30h+var_88]
0x180004df7  mov     qword ptr [rsp+130h+ShareAccess], r15; __int64
0x180004dfc  mov     r8, r14
0x180004dff  mov     rdx, rsi
0x180004e02  mov     rcx, rsi; SourceProcessHandle
0x180004e05  call    BaseSrvSxsCreateActivationContextFromStructEx
0x180004e0a  test    eax, eax
0x180004e0c  mov     ecx, r15d
0x180004e0f  cmovs   ecx, eax
0x180004e12  mov     eax, ecx
0x180004e14  test    di, di
0x180004e17  jz      short loc_180004E21
0x180004e19  mov     [r14+0DAh], di
0x180004e21  mov     rbx, [rsp+130h+arg_8]
0x180004e29  mov     rcx, [rbp+30h+var_28]
0x180004e2d  xor     rcx, rsp; StackCookie
0x180004e30  call    __security_check_cookie
0x180004e35  lea     r11, [rsp+130h+var_20]
0x180004e3d  mov     rsi, [r11+40h]
0x180004e41  mov     rdi, [r11+48h]
0x180004e45  mov     rsp, r11
0x180004e48  pop     r15
0x180004e4a  pop     r14
0x180004e4c  pop     r13
0x180004e4e  pop     r12
0x180004e50  pop     rbp
0x180004e51  retn
```

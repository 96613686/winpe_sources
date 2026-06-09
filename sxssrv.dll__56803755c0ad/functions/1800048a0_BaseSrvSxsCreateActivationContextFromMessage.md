# BaseSrvSxsCreateActivationContextFromMessage

- ea: `0x1800048a0`
- end: `0x180004ca2`
- name: `BaseSrvSxsCreateActivationContextFromMessage`
- size: `1026`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005ac0`

## callees

- `0x180003170`
- `0x1800048a0`
- `0x180006c30`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180004c24`
- `ntdll!RtlFreeHeap` at `0x180004c24`
- `ntdll!NtClose` at `0x180004bf8`
- `ntdll!NtClose` at `0x180004bf8`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180004ab4`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180004ab4`
- `ntdll!DbgPrintEx` at `0x180004bd4`
- `ntdll!DbgPrintEx` at `0x180004bd4`
- `ntdll!NtOpenFile` at `0x180004b0e`
- `ntdll!NtOpenFile` at `0x180004b0e`
- `ntdll!NtQueryInformationFile` at `0x180004b3e`
- `ntdll!NtQueryInformationFile` at `0x180004b6e`
- `ntdll!NtQueryInformationFile` at `0x180004b3e`
- `ntdll!NtQueryInformationFile` at `0x180004b6e`
- `CSRSRV!CsrRevertToSelf` at `0x180004c34`
- `CSRSRV!CsrRevertToSelf` at `0x180004c34`
- `CSRSRV!CsrImpersonateClient` at `0x180004a8e`
- `CSRSRV!CsrImpersonateClient` at `0x180004a8e`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000497a`
- `CSRSRV!CsrValidateMessageBuffer` at `0x1800049df`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000497a`
- `CSRSRV!CsrValidateMessageBuffer` at `0x1800049df`

## pseudocode

```c
__int64 __fastcall BaseSrvSxsCreateActivationContextFromMessage(__int64 a1)
{
  unsigned int v1; // r15d
  __int16 v3; // r12
  unsigned int v4; // esi
  unsigned __int16 *v5; // rdi
  int v6; // eax
  unsigned __int64 v7; // rax
  _WORD *v8; // rcx
  bool v9; // zf
  unsigned __int64 v10; // rax
  void *v11; // rdi
  char v12; // bl
  void *v13; // rcx
  unsigned __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // xmm1_8
  __int64 result; // rax
  int ActivationContextFromStruct; // eax
  void *FileHandle; // [rsp+58h] [rbp-B0h] BYREF
  void *FileHandle_8[2]; // [rsp+60h] [rbp-A8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock_8; // [rsp+70h] [rbp-98h] BYREF
  __int128 v22; // [rsp+80h] [rbp-88h] BYREF
  __int128 v23; // [rsp+90h] [rbp-78h]
  __int128 v24; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v25; // [rsp+B0h] [rbp-58h]
  __int128 FileInformation; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v27; // [rsp+C8h] [rbp-40h]
  __int64 v28; // [rsp+D8h] [rbp-30h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E0h] [rbp-28h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = a1 + 96;
  v1 = 0;
  ObjectAttributes.RootDirectory = (HANDLE)(a1 + 152);
  v3 = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)(a1 + 200);
  v4 = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = a1 + 216;
  ObjectAttributes.SecurityDescriptor = (PVOID)(a1 + 72);
  ObjectAttributes.SecurityQualityOfService = (PVOID)(a1 + 280);
  v22 = 0;
  v23 = 0;
  do
  {
    v5 = (unsigned __int16 *)*((_QWORD *)&ObjectAttributes.Length + v4);
    if ( v5 )
    {
      v6 = *v5;
      if ( (_WORD)v6 && !*((_QWORD *)v5 + 1) || (unsigned __int16)v6 > v5[1] || (v6 & 1) != 0 )
        return 3221225485LL;
      if ( *((_QWORD *)v5 + 1) )
      {
        if ( !(unsigned __int8)CsrValidateMessageBuffer(a1, v5 + 4, (unsigned int)(v6 + 2), 1) )
        {
          DbgPrintEx(
            0x33u,
            0,
            "SXS: Validation of message buffer 0x%lx failed.\n"
            " Message:%p\n"
            " String %p{Length:0x%x, MaximumLength:0x%x, Buffer:%p}\n",
            v4,
            (const void *)a1,
            v5,
            *v5,
            v5[1],
            *((const void **)v5 + 1));
          return 3221225485LL;
        }
        v7 = *v5;
        v8 = (_WORD *)*((_QWORD *)v5 + 1);
        if ( (_WORD)v7 )
        {
          v10 = v7 >> 1;
          if ( !v8[v10] )
            goto LABEL_14;
          v9 = v8[v10 - 1] == 0;
        }
        else
        {
          v9 = *v8 == 0;
        }
        if ( !v9 )
          return 3221225485LL;
      }
    }
LABEL_14:
    ++v4;
  }
  while ( v4 != 6 );
  if ( *(_WORD *)(a1 + 282)
    && !(unsigned __int8)CsrValidateMessageBuffer(a1, a1 + 288, *(unsigned __int16 *)(a1 + 282), 1) )
  {
    v3 = *(_WORD *)(a1 + 282);
    *(_WORD *)(a1 + 282) = *(_WORD *)(a1 + 280) + 2;
  }
  v11 = *(void **)(*((_QWORD *)NtCurrentTeb()->CsrClientThread + 7) + 80LL);
  if ( (*(_BYTE *)(a1 + 64) & 0x40) != 0 )
  {
    v12 = 0;
    v28 = 0;
    v13 = 0;
    v25 = 0;
    v14 = *(unsigned __int16 *)(a1 + 96);
    FileHandle = 0;
    *(_OWORD *)FileHandle_8 = 0;
    memset(&ObjectAttributes, 0, 44);
    IoStatusBlock_8 = 0;
    FileInformation = 0;
    v27 = 0;
    v24 = 0;
    if ( (_WORD)v14 )
    {
      v15 = *(_QWORD *)(a1 + 104);
      if ( v15 )
      {
        if ( !*(_WORD *)(v15 + 2 * (v14 >> 1)) )
        {
          v12 = CsrImpersonateClient(0);
          if ( v12 )
          {
            if ( (int)RtlDosPathNameToNtPathName_U_WithStatus(*(_QWORD *)(a1 + 104), FileHandle_8, 0, 0) >= 0 )
            {
              ObjectAttributes.ObjectName = (PUNICODE_STRING)FileHandle_8;
              ObjectAttributes.Length = 48;
              ObjectAttributes.RootDirectory = 0;
              ObjectAttributes.Attributes = 64;
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
              if ( NtOpenFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock_8, 5u, 0x60u) >= 0
                && NtQueryInformationFile(FileHandle, &IoStatusBlock_8, &FileInformation, 0x28u, FileBasicInformation) >= 0
                && NtQueryInformationFile(
                     FileHandle,
                     &IoStatusBlock_8,
                     &v24,
                     0x18u,
                     FileMaximumInformation|FileBothDirectoryInformation) >= 0 )
              {
                v16 = v25;
                v13 = FileHandle;
                v22 = v24;
                *(_QWORD *)(a1 + 232) = v27;
                *(_QWORD *)&v23 = v16;
                goto LABEL_32;
              }
            }
          }
          v13 = FileHandle;
        }
      }
    }
    DWORD2(v23) |= 1u;
LABEL_32:
    if ( v13 )
    {
      NtClose(v13);
      FileHandle = 0;
    }
    if ( FileHandle_8[1] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, FileHandle_8[1]);
    if ( v12 )
      CsrRevertToSelf();
  }
  ActivationContextFromStruct = BaseSrvSxsCreateActivationContextFromStructEx(
                                  v11,
                                  v11,
                                  (unsigned int *)(a1 + 64),
                                  (union _LARGE_INTEGER)&v22,
                                  0);
  if ( ActivationContextFromStruct < 0 )
    v1 = ActivationContextFromStruct;
  result = v1;
  if ( v3 )
    *(_WORD *)(a1 + 282) = v3;
  return result;
}

```

## disassembly

```asm
0x1800048a0  mov     r11, rsp
0x1800048a3  mov     [r11+18h], rsi
0x1800048a7  mov     [r11+20h], rdi
0x1800048ab  push    rbp
0x1800048ac  push    r12
0x1800048ae  push    r13
0x1800048b0  push    r14
0x1800048b2  push    r15
0x1800048b4  lea     rbp, [r11-38h]
0x1800048b8  sub     rsp, 110h
0x1800048bf  mov     rax, cs:__security_cookie
0x1800048c6  xor     rax, rsp
0x1800048c9  mov     [rbp+30h+var_28], rax
0x1800048cd  lea     rax, [rcx+60h]
0x1800048d1  mov     [r11+10h], rbx
0x1800048d5  mov     qword ptr [rbp+30h+ObjectAttributes.Length], rax
0x1800048d9  xorps   xmm0, xmm0
0x1800048dc  lea     rax, [rcx+98h]
0x1800048e3  xor     r15d, r15d
0x1800048e6  mov     [rbp+30h+ObjectAttributes.RootDirectory], rax
0x1800048ea  mov     r13, rcx
0x1800048ed  lea     rax, [rcx+0C8h]
0x1800048f4  movzx   r12d, r15w
0x1800048f8  mov     [rbp+30h+ObjectAttributes.ObjectName], rax
0x1800048fc  mov     esi, r15d
0x1800048ff  lea     rax, [rcx+0D8h]
0x180004906  mov     qword ptr [rbp+30h+ObjectAttributes.Attributes], rax
0x18000490a  lea     rax, [rcx+48h]
0x18000490e  mov     [rbp+30h+ObjectAttributes.SecurityDescriptor], rax
0x180004912  lea     rax, [rcx+118h]
0x180004919  mov     [rbp+30h+ObjectAttributes.SecurityQualityOfService], rax
0x18000491d  movups  xmmword ptr [rsp+130h+var_C0+8], xmm0
0x180004922  movups  [rbp+30h+var_A8], xmm0
0x180004926  nop     word ptr [rax+rax+00000000h]
0x180004930  mov     eax, esi
0x180004932  mov     rdi, qword ptr [rbp+rax*8+30h+ObjectAttributes.Length]
0x180004937  test    rdi, rdi
0x18000493a  jz      short loc_1800049B6
0x18000493c  movzx   eax, word ptr [rdi]
0x18000493f  test    ax, ax
0x180004942  jz      short loc_18000494E
0x180004944  cmp     [rdi+8], r15
0x180004948  jz      loc_180004BE0
0x18000494e  cmp     ax, [rdi+2]
0x180004952  ja      loc_180004BE0
0x180004958  mov     r8d, eax
0x18000495b  test    al, 1
0x18000495d  jnz     loc_180004BE0
0x180004963  cmp     [rdi+8], r15
0x180004967  jz      short loc_1800049B6
0x180004969  add     r8d, 2
0x18000496d  lea     rdx, [rdi+8]
0x180004971  mov     r9d, 1
0x180004977  mov     rcx, r13
0x18000497a  call    cs:__imp_CsrValidateMessageBuffer
0x180004981  nop     dword ptr [rax+rax+00h]
0x180004986  test    al, al
0x180004988  jz      loc_180004BA3
0x18000498e  movzx   eax, word ptr [rdi]
0x180004991  mov     rcx, [rdi+8]
0x180004995  test    ax, ax
0x180004998  jnz     short loc_1800049A0
0x18000499a  cmp     [rcx], r15w
0x18000499e  jmp     short loc_1800049B0
0x1800049a0  shr     rax, 1
0x1800049a3  cmp     [rcx+rax*2], r15w
0x1800049a8  jz      short loc_1800049B6
0x1800049aa  cmp     [rcx+rax*2-2], r15w
0x1800049b0  jnz     loc_180004BE0
0x1800049b6  inc     esi
0x1800049b8  cmp     esi, 6
0x1800049bb  jnz     loc_180004930
0x1800049c1  movzx   eax, word ptr [r13+11Ah]
0x1800049c9  test    ax, ax
0x1800049cc  jz      short loc_180004A0B
0x1800049ce  mov     r8d, eax
0x1800049d1  lea     rdx, [r13+120h]
0x1800049d8  lea     r9d, [rsi-5]
0x1800049dc  mov     rcx, r13
0x1800049df  call    cs:__imp_CsrValidateMessageBuffer
0x1800049e6  nop     dword ptr [rax+rax+00h]
0x1800049eb  test    al, al
0x1800049ed  jnz     short loc_180004A0B
0x1800049ef  movzx   eax, word ptr [r13+118h]
0x1800049f7  movzx   r12d, word ptr [r13+11Ah]
0x1800049ff  add     ax, 2
0x180004a03  mov     [r13+11Ah], ax
0x180004a0b  mov     rax, gs:70h
0x180004a14  test    byte ptr [r13+40h], 40h
0x180004a19  mov     rcx, [rax+38h]
0x180004a1d  mov     rdi, [rcx+50h]
0x180004a21  jz      loc_180004C40
0x180004a27  xor     eax, eax
0x180004a29  xorps   xmm0, xmm0
0x180004a2c  xorps   xmm1, xmm1
0x180004a2f  mov     [rbp+30h+ObjectAttributes.SecurityDescriptor], rax
0x180004a33  mov     dword ptr [rbp+30h+ObjectAttributes.SecurityQualityOfService], eax
0x180004a36  xor     bl, bl
0x180004a38  mov     [rbp+30h+var_60], rax
0x180004a3c  mov     rcx, r15
0x180004a3f  mov     [rbp+30h+var_88], rax
0x180004a43  movzx   eax, word ptr [r13+60h]
0x180004a48  mov     [rsp+130h+FileHandle], rcx
0x180004a4d  movups  xmmword ptr [rsp+130h+FileHandle+8], xmm0
0x180004a52  movups  xmmword ptr [rbp+30h+ObjectAttributes.Length], xmm0
0x180004a56  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm0
0x180004a5a  movups  xmmword ptr [rsp+130h+IoStatusBlock.Information], xmm0
0x180004a5f  movups  [rbp+30h+FileInformation], xmm1
0x180004a63  movups  [rbp+30h+var_70], xmm1
0x180004a67  movups  [rbp+30h+var_98], xmm0
0x180004a6b  test    ax, ax
0x180004a6e  jz      loc_180004BEF
0x180004a74  mov     rdx, [r13+68h]
0x180004a78  test    rdx, rdx
0x180004a7b  jz      loc_180004BEF
0x180004a81  shr     rax, 1
0x180004a84  cmp     [rdx+rax*2], cx
0x180004a88  jnz     loc_180004BEF
0x180004a8e  call    cs:__imp_CsrImpersonateClient
0x180004a95  nop     dword ptr [rax+rax+00h]
0x180004a9a  movzx   ebx, al
0x180004a9d  test    al, al
0x180004a9f  jz      loc_180004BEA
0x180004aa5  mov     rcx, [r13+68h]
0x180004aa9  lea     rdx, [rsp+130h+FileHandle+8]
0x180004aae  xor     r9d, r9d
0x180004ab1  xor     r8d, r8d
0x180004ab4  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180004abb  nop     dword ptr [rax+rax+00h]
0x180004ac0  test    eax, eax
0x180004ac2  js      loc_180004BEA
0x180004ac8  lea     rax, [rsp+130h+FileHandle+8]
0x180004acd  mov     [rsp+130h+OpenOptions], 60h ; '`'; OpenOptions
0x180004ad5  xorps   xmm0, xmm0
0x180004ad8  mov     [rbp+30h+ObjectAttributes.ObjectName], rax
0x180004adc  lea     r9, [rsp+130h+IoStatusBlock.Information]; IoStatusBlock
0x180004ae1  mov     [rbp+30h+ObjectAttributes.Length], 30h ; '0'
0x180004ae8  lea     r8, [rbp+30h+ObjectAttributes]; ObjectAttributes
0x180004aec  mov     [rbp+30h+ObjectAttributes.RootDirectory], r15
0x180004af0  mov     edx, 120089h; DesiredAccess
0x180004af5  mov     [rbp+30h+ObjectAttributes.Attributes], 40h ; '@'
0x180004afc  lea     rcx, [rsp+130h+FileHandle]; FileHandle
0x180004b01  mov     [rsp+130h+ShareAccess], 5; ShareAccess
0x180004b09  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x180004b0e  call    cs:__imp_NtOpenFile
0x180004b15  nop     dword ptr [rax+rax+00h]
0x180004b1a  test    eax, eax
0x180004b1c  js      loc_180004BEA
0x180004b22  mov     rcx, [rsp+130h+FileHandle]; FileHandle
0x180004b27  lea     r8, [rbp+30h+FileInformation]; FileInformation
0x180004b2b  mov     r9d, 28h ; '('; Length
0x180004b31  mov     [rsp+130h+ShareAccess], 4; FileInformationClass
0x180004b39  lea     rdx, [rsp+130h+IoStatusBlock.Information]; IoStatusBlock
0x180004b3e  call    cs:__imp_NtQueryInformationFile
0x180004b45  nop     dword ptr [rax+rax+00h]
0x180004b4a  test    eax, eax
0x180004b4c  js      loc_180004BEA
0x180004b52  mov     rcx, [rsp+130h+FileHandle]; FileHandle
0x180004b57  lea     r8, [rbp+30h+var_98]; FileInformation
0x180004b5b  mov     r9d, 18h; Length
0x180004b61  mov     [rsp+130h+ShareAccess], 3Bh ; ';'; FileInformationClass
0x180004b69  lea     rdx, [rsp+130h+IoStatusBlock.Information]; IoStatusBlock
0x180004b6e  call    cs:__imp_NtQueryInformationFile
0x180004b75  nop     dword ptr [rax+rax+00h]
0x180004b7a  test    eax, eax
0x180004b7c  js      short loc_180004BEA
0x180004b7e  movups  xmm0, [rbp+30h+var_98]
0x180004b82  mov     rax, qword ptr [rbp+30h+var_70]
0x180004b86  movsd   xmm1, [rbp+30h+var_88]
0x180004b8b  mov     rcx, [rsp+130h+FileHandle]
0x180004b90  movups  xmmword ptr [rsp+130h+var_C0+8], xmm0
0x180004b95  mov     [r13+0E8h], rax
0x180004b9c  movsd   qword ptr [rbp+30h+var_A8], xmm1
0x180004ba1  jmp     short loc_180004BF3
0x180004ba3  movzx   ecx, word ptr [rdi+2]
0x180004ba7  lea     r8, Format; "SXS: Validation of message buffer 0x%lx"...
0x180004bae  movzx   edx, word ptr [rdi]
0x180004bb1  mov     r9d, esi
0x180004bb4  mov     rax, [rdi+8]
0x180004bb8  mov     [rsp+130h+var_F0], rax
0x180004bbd  mov     dword ptr [rsp+130h+var_F8], ecx
0x180004bc1  mov     [rsp+130h+var_100], edx
0x180004bc5  xor     edx, edx; Level
0x180004bc7  mov     qword ptr [rsp+130h+OpenOptions], rdi
0x180004bcc  mov     qword ptr [rsp+130h+ShareAccess], r13
0x180004bd1  lea     ecx, [rdx+33h]; ComponentId
0x180004bd4  call    cs:__imp_DbgPrintEx
0x180004bdb  nop     dword ptr [rax+rax+00h]
0x180004be0  mov     eax, 0C000000Dh
0x180004be5  jmp     loc_180004C70
0x180004bea  mov     rcx, [rsp+130h+FileHandle]; Handle
0x180004bef  or      dword ptr [rbp+30h+var_A8+8], 1
0x180004bf3  test    rcx, rcx
0x180004bf6  jz      short loc_180004C09
0x180004bf8  call    cs:__imp_NtClose
0x180004bff  nop     dword ptr [rax+rax+00h]
0x180004c04  mov     [rsp+130h+FileHandle], r15
0x180004c09  cmp     qword ptr [rsp+130h+IoStatusBlock], r15
0x180004c0e  jz      short loc_180004C30
0x180004c10  mov     rcx, gs:60h
0x180004c19  xor     edx, edx; Flags
0x180004c1b  mov     r8, qword ptr [rsp+130h+IoStatusBlock]; P
0x180004c20  mov     rcx, [rcx+30h]; HeapHandle
0x180004c24  call    cs:__imp_RtlFreeHeap
0x180004c2b  nop     dword ptr [rax+rax+00h]
0x180004c30  test    bl, bl
0x180004c32  jz      short loc_180004C40
0x180004c34  call    cs:__imp_CsrRevertToSelf
0x180004c3b  nop     dword ptr [rax+rax+00h]
0x180004c40  lea     r9, [rsp+130h+var_C0+8]
0x180004c45  mov     qword ptr [rsp+130h+ShareAccess], r15; __int64
0x180004c4a  lea     r8, [r13+40h]
0x180004c4e  mov     rdx, rdi
0x180004c51  mov     rcx, rdi; SourceProcessHandle
0x180004c54  call    BaseSrvSxsCreateActivationContextFromStructEx
0x180004c59  test    eax, eax
0x180004c5b  cmovs   r15d, eax
0x180004c5f  mov     eax, r15d
0x180004c62  test    r12w, r12w
0x180004c66  jz      short loc_180004C70
0x180004c68  mov     [r13+11Ah], r12w
0x180004c70  mov     rbx, [rsp+130h+arg_8]
0x180004c78  mov     rcx, [rbp+30h+var_28]
0x180004c7c  xor     rcx, rsp; StackCookie
0x180004c7f  call    __security_check_cookie
0x180004c84  lea     r11, [rsp+130h+var_20]
0x180004c8c  mov     rsi, [r11+40h]
0x180004c90  mov     rdi, [r11+48h]
0x180004c94  mov     rsp, r11
0x180004c97  pop     r15
0x180004c99  pop     r14
0x180004c9b  pop     r13
0x180004c9d  pop     r12
0x180004c9f  pop     rbp
0x180004ca0  retn
```

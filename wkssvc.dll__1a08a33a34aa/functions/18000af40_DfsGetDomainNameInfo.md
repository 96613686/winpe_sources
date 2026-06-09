# DfsGetDomainNameInfo

- ea: `0x18000af40`
- end: `0x18000b181`
- name: `DfsGetDomainNameInfo`
- size: `577`
- prototype: `__int64 __fastcall(PBYTE *Buffer)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ace0`

## callees

- `0x18000af40`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18000afa8`
- `ntdll!NtOpenFile` at `0x18000afa8`
- `ntdll!RtlNtStatusToDosError` at `0x18000afba`
- `ntdll!RtlNtStatusToDosError` at `0x18000b171`
- `ntdll!RtlNtStatusToDosError` at `0x18000afba`
- `ntdll!RtlNtStatusToDosError` at `0x18000b171`
- `ntdll!NtFsControlFile` at `0x18000b066`
- `ntdll!NtFsControlFile` at `0x18000b0e0`
- `ntdll!NtFsControlFile` at `0x18000b066`
- `ntdll!NtFsControlFile` at `0x18000b0e0`
- `ntdll!NtClose` at `0x18000b000`
- `ntdll!NtClose` at `0x18000b000`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18000afe2`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18000afe2`

## pseudocode

```c
ULONG __fastcall DfsGetDomainNameInfo(PBYTE *Buffer)
{
  int Status; // eax
  DWORD PrimaryDomainInformation; // edi
  NTSTATUS v5; // ebp
  _WORD *v6; // rcx
  bool v7; // zf
  __int64 v8; // rbx
  NTSTATUS v9; // eax
  __int64 v10; // rax
  _WORD *InputBuffer; // rcx
  NTSTATUS v12; // ecx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES v14; // [rsp+60h] [rbp-48h] BYREF
  HANDLE Handle; // [rsp+B0h] [rbp+8h] BYREF

  *Buffer = 0;
  Handle = 0;
  *(_QWORD *)&v14.Length = 48;
  *(_QWORD *)&v14.Attributes = 64;
  v14.RootDirectory = 0;
  v14.ObjectName = (PUNICODE_STRING)LocalDfsName;
  IoStatusBlock = 0;
  *(_OWORD *)&v14.SecurityDescriptor = 0;
  Status = NtOpenFile(&Handle, 0x100002u, &v14, &IoStatusBlock, 7u, 0x20u);
  if ( Status < 0 )
    return RtlNtStatusToDosError(Status);
  Status = IoStatusBlock.Status;
  if ( IoStatusBlock.Status < 0 )
    return RtlNtStatusToDosError(Status);
  PrimaryDomainInformation = DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, Buffer);
  if ( !PrimaryDomainInformation )
  {
    if ( *Buffer )
    {
      InputBuffer = (_WORD *)*((_QWORD *)*Buffer + 1);
      v8 = -1;
      if ( InputBuffer )
      {
        v10 = -1;
        do
          v7 = InputBuffer[++v10] == 0;
        while ( !v7 );
        IoStatusBlock = 0;
        v5 = NtFsControlFile(Handle, 0, 0, 0, &IoStatusBlock, 0x6811Cu, InputBuffer, 2 * v10 + 2, 0, 0);
        if ( v5 >= 0 )
          v5 = IoStatusBlock.Status;
      }
      else
      {
        v5 = 0;
      }
      v6 = (_WORD *)*((_QWORD *)*Buffer + 2);
      if ( v6 )
      {
        do
          v7 = v6[++v8] == 0;
        while ( !v7 );
        IoStatusBlock = 0;
        v9 = NtFsControlFile(Handle, 0, 0, 0, &IoStatusBlock, 0x68120u, v6, 2 * v8 + 2, 0, 0);
        if ( v9 >= 0 )
          v9 = IoStatusBlock.Status;
      }
      else
      {
        v9 = v5;
      }
      if ( v9 < 0 )
      {
        v12 = v9;
      }
      else
      {
        if ( v5 >= 0 )
          goto LABEL_5;
        v12 = v5;
      }
      PrimaryDomainInformation = RtlNtStatusToDosError(v12);
    }
    else
    {
      PrimaryDomainInformation = 59;
    }
  }
LABEL_5:
  NtClose(Handle);
  return PrimaryDomainInformation;
}

```

## disassembly

```asm
0x18000af40  mov     r11, rsp
0x18000af43  push    rsi
0x18000af44  push    r14
0x18000af46  sub     rsp, 98h
0x18000af4d  xor     r14d, r14d
0x18000af50  mov     [rsp+0A8h+OpenOptions], 20h ; ' '; OpenOptions
0x18000af58  xorps   xmm0, xmm0
0x18000af5b  mov     [rcx], r14
0x18000af5e  mov     rsi, rcx
0x18000af61  mov     [r11+8], r14
0x18000af65  lea     rax, LocalDfsName; "\"\""
0x18000af6c  mov     qword ptr [r11-48h], 30h ; '0'
0x18000af74  lea     rcx, [r11+8]; FileHandle
0x18000af78  mov     qword ptr [r11-30h], 40h ; '@'
0x18000af80  lea     r9, [r11-58h]; IoStatusBlock
0x18000af84  mov     [r11-40h], r14
0x18000af88  lea     r8, [r11-48h]; ObjectAttributes
0x18000af8c  mov     [r11-38h], rax
0x18000af90  mov     edx, 100002h; DesiredAccess
0x18000af95  mov     [rsp+0A8h+ShareAccess], 7; ShareAccess
0x18000af9d  movups  xmmword ptr [rsp+0A8h+IoStatusBlock], xmm0
0x18000afa2  movdqu  xmmword ptr [r11-28h], xmm0
0x18000afa8  call    cs:__imp_NtOpenFile
0x18000afaf  nop     dword ptr [rax+rax+00h]
0x18000afb4  test    eax, eax
0x18000afb6  jns     short loc_18000AFC8
0x18000afb8  mov     ecx, eax; Status
0x18000afba  call    cs:__imp_RtlNtStatusToDosError
0x18000afc1  nop     dword ptr [rax+rax+00h]
0x18000afc6  jmp     short loc_18000B016
0x18000afc8  mov     eax, dword ptr [rsp+0A8h+IoStatusBlock]
0x18000afcc  test    eax, eax
0x18000afce  js      short loc_18000AFB8
0x18000afd0  mov     r8, rsi; Buffer
0x18000afd3  mov     [rsp+0A8h+var_18], rdi
0x18000afdb  mov     edx, 1; InfoLevel
0x18000afe0  xor     ecx, ecx; lpServer
0x18000afe2  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x18000afe9  nop     dword ptr [rax+rax+00h]
0x18000afee  mov     edi, eax
0x18000aff0  test    eax, eax
0x18000aff2  jz      loc_18000B159
0x18000aff8  mov     rcx, [rsp+0A8h+Handle]; Handle
0x18000b000  call    cs:__imp_NtClose
0x18000b007  nop     dword ptr [rax+rax+00h]
0x18000b00c  mov     eax, edi
0x18000b00e  mov     rdi, [rsp+0A8h+var_18]
0x18000b016  add     rsp, 98h
0x18000b01d  pop     r14
0x18000b01f  pop     rsi
0x18000b020  retn
0x18000b022  mov     [rsp+0A8h+OutputBufferLength], r14d; OutputBufferLength
0x18000b027  lea     eax, ds:2[rax*2]
0x18000b02e  mov     [rsp+0A8h+OutputBuffer], r14; OutputBuffer
0x18000b033  xorps   xmm0, xmm0
0x18000b036  mov     [rsp+0A8h+InputBufferLength], eax; InputBufferLength
0x18000b03a  xor     r9d, r9d; ApcContext
0x18000b03d  mov     [rsp+0A8h+InputBuffer], rcx; InputBuffer
0x18000b042  lea     rax, [rsp+0A8h+IoStatusBlock]
0x18000b047  mov     rcx, [rsp+0A8h+Handle]; FileHandle
0x18000b04f  xor     r8d, r8d; ApcRoutine
0x18000b052  mov     [rsp+0A8h+OpenOptions], 6811Ch; FsControlCode
0x18000b05a  xor     edx, edx; Event
0x18000b05c  mov     qword ptr [rsp+0A8h+ShareAccess], rax; IoStatusBlock
0x18000b061  movups  xmmword ptr [rsp+0A8h+IoStatusBlock], xmm0
0x18000b066  call    cs:__imp_NtFsControlFile
0x18000b06d  nop     dword ptr [rax+rax+00h]
0x18000b072  test    eax, eax
0x18000b074  mov     ebp, eax
0x18000b076  cmovns  ebp, dword ptr [rsp+0A8h+IoStatusBlock]
0x18000b07b  mov     rax, [rsi]
0x18000b07e  mov     rcx, [rax+10h]
0x18000b082  test    rcx, rcx
0x18000b085  jz      loc_18000B110
0x18000b08b  nop     dword ptr [rax+rax+00h]
0x18000b090  cmp     [rcx+rbx*2+2], r14w
0x18000b096  lea     rbx, [rbx+1]
0x18000b09a  jnz     short loc_18000B090
0x18000b09c  mov     [rsp+0A8h+OutputBufferLength], r14d; OutputBufferLength
0x18000b0a1  lea     rax, [rsp+0A8h+IoStatusBlock]
0x18000b0a6  mov     [rsp+0A8h+OutputBuffer], r14; OutputBuffer
0x18000b0ab  lea     ebx, ds:2[rbx*2]
0x18000b0b2  mov     [rsp+0A8h+InputBufferLength], ebx; InputBufferLength
0x18000b0b6  xorps   xmm0, xmm0
0x18000b0b9  mov     [rsp+0A8h+InputBuffer], rcx; InputBuffer
0x18000b0be  xor     r9d, r9d; ApcContext
0x18000b0c1  mov     rcx, [rsp+0A8h+Handle]; FileHandle
0x18000b0c9  xor     r8d, r8d; ApcRoutine
0x18000b0cc  mov     [rsp+0A8h+OpenOptions], 68120h; FsControlCode
0x18000b0d4  xor     edx, edx; Event
0x18000b0d6  mov     qword ptr [rsp+0A8h+ShareAccess], rax; IoStatusBlock
0x18000b0db  movups  xmmword ptr [rsp+0A8h+IoStatusBlock], xmm0
0x18000b0e0  call    cs:__imp_NtFsControlFile
0x18000b0e7  nop     dword ptr [rax+rax+00h]
0x18000b0ec  test    eax, eax
0x18000b0ee  cmovns  eax, dword ptr [rsp+0A8h+IoStatusBlock]
0x18000b0f3  mov     rbx, [rsp+0A8h+arg_8]
0x18000b0fb  test    eax, eax
0x18000b0fd  js      short loc_18000B16B
0x18000b0ff  test    ebp, ebp
0x18000b101  js      short loc_18000B16F
0x18000b103  mov     rbp, [rsp+0A8h+arg_10]
0x18000b10b  jmp     loc_18000AFF8
0x18000b110  mov     eax, ebp
0x18000b112  jmp     short loc_18000B0F3
0x18000b114  mov     rax, rbx
0x18000b117  nop     word ptr [rax+rax+00000000h]
0x18000b120  cmp     [rcx+rax*2+2], r14w
0x18000b126  lea     rax, [rax+1]
0x18000b12a  jnz     short loc_18000B120
0x18000b12c  jmp     loc_18000B022
0x18000b131  mov     rcx, [rcx+8]
0x18000b135  mov     [rsp+0A8h+arg_8], rbx
0x18000b13d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b144  mov     [rsp+0A8h+arg_10], rbp
0x18000b14c  test    rcx, rcx
0x18000b14f  jnz     short loc_18000B114
0x18000b151  mov     ebp, r14d
0x18000b154  jmp     loc_18000B07B
0x18000b159  mov     rcx, [rsi]
0x18000b15c  test    rcx, rcx
0x18000b15f  jnz     short loc_18000B131
0x18000b161  mov     edi, 3Bh ; ';'
0x18000b166  jmp     loc_18000AFF8
0x18000b16b  mov     ecx, eax
0x18000b16d  jmp     short loc_18000B171
0x18000b16f  mov     ecx, ebp; Status
0x18000b171  call    cs:__imp_RtlNtStatusToDosError
0x18000b178  nop     dword ptr [rax+rax+00h]
0x18000b17d  mov     edi, eax
0x18000b17f  jmp     short loc_18000B103
```

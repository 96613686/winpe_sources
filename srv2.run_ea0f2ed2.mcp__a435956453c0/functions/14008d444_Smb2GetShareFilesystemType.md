# Smb2GetShareFilesystemType

- ea: `0x14008d444`
- end: `0x14008d688`
- name: `Smb2GetShareFilesystemType`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140081de0`

## callees

- `0x140022958`
- `0x140028ab8`
- `0x140038490`
- `0x14008d444`

## import_xrefs

- `ntoskrnl!ZwCreateEvent` at `0x14008d4de`
- `ntoskrnl!ZwCreateEvent` at `0x14008d4de`
- `ntoskrnl!NtFsControlFile` at `0x14008d535`
- `ntoskrnl!NtFsControlFile` at `0x14008d535`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14008d603`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14008d603`
- `ntoskrnl!NtClose` at `0x14008d552`
- `ntoskrnl!NtClose` at `0x14008d552`

## pseudocode

```c
__int64 __fastcall Smb2GetShareFilesystemType(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 result; // rax
  unsigned int Status; // ebx
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  void *EventHandle; // [rsp+50h] [rbp-69h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-61h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-51h] BYREF
  _WORD OutputBuffer[32]; // [rsp+A0h] [rbp-19h] BYREF

  result = 0;
  EventHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  IoStatusBlock = 0;
  if ( !a1 || !a2 || !a3 )
    return 3221225485LL;
  *a3 = 0;
  if ( !*(_DWORD *)(a1 + 284) )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    Status = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
    if ( (Status & 0x80000000) == 0 )
    {
      Status = NtFsControlFile(
                 *(HANDLE *)(a2 + 88),
                 EventHandle,
                 0,
                 0,
                 &IoStatusBlock,
                 0x90060u,
                 0,
                 0,
                 OutputBuffer,
                 0x40u);
      if ( Status == 259 )
      {
        ZwWaitForSingleObject(EventHandle, 0, 0);
        Status = IoStatusBlock.Status;
      }
      NtClose(EventHandle);
      EventHandle = 0;
      if ( (int)(Status + 0x80000000) < 0 || Status == -2147483643 )
      {
        v10 = OutputBuffer[0];
        Status = 0;
      }
      else
      {
        if ( Status != -1073741808 && Status != -1073741811 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || !BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            return Status;
          }
          v12 = 17;
LABEL_29:
          WPP_SF_qD(v11->AttachedDevice, v12, &WPP_4e8015138ece3414973dc97451d118ee_Traceguids, a1, Status);
          return Status;
        }
        Status = 0;
        v10 = 0;
      }
      *a3 = v10;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_DqZd(WPP_GLOBAL_Control->AttachedDevice, v8, v9, v10, a1, a1 + 120);
      }
      return Status;
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return Status;
    }
    v12 = 16;
    goto LABEL_29;
  }
  return result;
}

```

## disassembly

```asm
0x14008d444  push    rbp
0x14008d446  push    rbx
0x14008d447  push    rsi
0x14008d448  push    rdi
0x14008d449  push    r14
0x14008d44b  lea     rbp, [rsp-37h]
0x14008d450  sub     rsp, 0F0h
0x14008d457  mov     rax, cs:__security_cookie
0x14008d45e  xor     rax, rsp
0x14008d461  mov     [rbp+57h+var_30], rax
0x14008d465  xor     eax, eax
0x14008d467  mov     [rbp+57h+EventHandle], 0
0x14008d46f  mov     dword ptr [rbp+57h+ObjectAttributes+4], eax
0x14008d472  xorps   xmm0, xmm0
0x14008d475  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], eax
0x14008d478  mov     rsi, r8
0x14008d47b  mov     r14, rdx
0x14008d47e  mov     rdi, rcx
0x14008d481  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14008d485  test    rcx, rcx
0x14008d488  jz      loc_14008D67E
0x14008d48e  test    rdx, rdx
0x14008d491  jz      loc_14008D67E
0x14008d497  test    r8, r8
0x14008d49a  jz      loc_14008D67E
0x14008d4a0  mov     [r8], eax
0x14008d4a3  cmp     [rcx+11Ch], eax
0x14008d4a9  jnz     loc_14008D595
0x14008d4af  xor     r9d, r9d; EventType
0x14008d4b2  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14008d4b9  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14008d4bd  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14008d4c1  mov     edx, 1F0003h; DesiredAccess
0x14008d4c6  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14008d4cd  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x14008d4d1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14008d4d5  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14008d4da  mov     [rsp+110h+InitialState], al; InitialState
0x14008d4de  call    cs:__imp_ZwCreateEvent
0x14008d4e5  nop     dword ptr [rax+rax+00h]
0x14008d4ea  mov     ebx, eax
0x14008d4ec  test    eax, eax
0x14008d4ee  js      loc_14008D648
0x14008d4f4  mov     rdx, [rbp+57h+EventHandle]; Event
0x14008d4f8  lea     rax, [rbp+57h+var_70]
0x14008d4fc  mov     rcx, [r14+58h]; FileHandle
0x14008d500  xor     r9d, r9d; ApcContext
0x14008d503  mov     [rsp+110h+OutputBufferLength], 40h ; '@'; OutputBufferLength
0x14008d50b  xor     r8d, r8d; ApcRoutine
0x14008d50e  mov     [rsp+110h+OutputBuffer], rax; OutputBuffer
0x14008d513  lea     rax, [rbp+57h+IoStatusBlock]
0x14008d517  mov     [rsp+110h+InputBufferLength], 0; InputBufferLength
0x14008d51f  mov     [rsp+110h+InputBuffer], 0; InputBuffer
0x14008d528  mov     [rsp+110h+FsControlCode], 90060h; FsControlCode
0x14008d530  mov     qword ptr [rsp+110h+InitialState], rax; IoStatusBlock
0x14008d535  call    cs:__imp_NtFsControlFile
0x14008d53c  nop     dword ptr [rax+rax+00h]
0x14008d541  mov     ebx, eax
0x14008d543  cmp     eax, 103h
0x14008d548  jz      loc_14008D5FA
0x14008d54e  mov     rcx, [rbp+57h+EventHandle]; Handle
0x14008d552  call    cs:__imp_NtClose
0x14008d559  nop     dword ptr [rax+rax+00h]
0x14008d55e  mov     ecx, 80000000h
0x14008d563  mov     [rbp+57h+EventHandle], 0
0x14008d56b  lea     eax, [rbx+rcx]
0x14008d56e  test    ecx, eax
0x14008d570  jz      short loc_14008D5B0
0x14008d572  movzx   r9d, [rbp+57h+var_70]
0x14008d577  xor     ebx, ebx
0x14008d579  mov     [rsi], r9d
0x14008d57c  lea     rax, WPP_GLOBAL_Control
0x14008d583  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d58a  cmp     rcx, rax
0x14008d58d  jnz     loc_14008D617
0x14008d593  mov     eax, ebx
0x14008d595  mov     rcx, [rbp+57h+var_30]
0x14008d599  xor     rcx, rsp; StackCookie
0x14008d59c  call    __security_check_cookie
0x14008d5a1  add     rsp, 0F0h
0x14008d5a8  pop     r14
0x14008d5aa  pop     rdi
0x14008d5ab  pop     rsi
0x14008d5ac  pop     rbx
0x14008d5ad  pop     rbp
0x14008d5ae  retn
0x14008d5b0  cmp     ebx, 80000005h
0x14008d5b6  jz      short loc_14008D572
0x14008d5b8  cmp     ebx, 0C0000010h
0x14008d5be  jz      loc_14009B976
0x14008d5c4  cmp     ebx, 0C000000Dh
0x14008d5ca  jz      loc_14009B976
0x14008d5d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d5d7  lea     rax, WPP_GLOBAL_Control
0x14008d5de  cmp     rcx, rax
0x14008d5e1  jz      short loc_14008D593
0x14008d5e3  mov     eax, [rcx+2Ch]
0x14008d5e6  test    al, 1
0x14008d5e8  jz      short loc_14008D593
0x14008d5ea  cmp     byte ptr [rcx+29h], 1
0x14008d5ee  jb      short loc_14008D593
0x14008d5f0  mov     edx, 11h
0x14008d5f5  jmp     loc_14009B980
0x14008d5fa  mov     rcx, [rbp+57h+EventHandle]; Handle
0x14008d5fe  xor     r8d, r8d; Timeout
0x14008d601  xor     edx, edx; Alertable
0x14008d603  call    cs:__imp_ZwWaitForSingleObject
0x14008d60a  nop     dword ptr [rax+rax+00h]
0x14008d60f  mov     ebx, dword ptr [rbp+57h+IoStatusBlock]
0x14008d612  jmp     loc_14008D54E
0x14008d617  mov     eax, [rcx+2Ch]
0x14008d61a  test    al, 1
0x14008d61c  jz      loc_14008D593
0x14008d622  cmp     byte ptr [rcx+29h], 2
0x14008d626  jb      loc_14008D593
0x14008d62c  mov     rcx, [rcx+18h]
0x14008d630  lea     rax, [rdi+78h]
0x14008d634  mov     qword ptr [rsp+110h+FsControlCode], rax
0x14008d639  mov     qword ptr [rsp+110h+InitialState], rdi
0x14008d63e  call    WPP_SF_DqZd
0x14008d643  jmp     loc_14008D593
0x14008d648  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d64f  lea     rax, WPP_GLOBAL_Control
0x14008d656  cmp     rcx, rax
0x14008d659  jz      loc_14008D593
0x14008d65f  mov     eax, [rcx+2Ch]
0x14008d662  test    al, 1
0x14008d664  jz      loc_14008D593
0x14008d66a  cmp     byte ptr [rcx+29h], 1
0x14008d66e  jb      loc_14008D593
0x14008d674  mov     edx, 10h
0x14008d679  jmp     loc_14009B980
0x14008d67e  mov     eax, 0C000000Dh
0x14008d683  jmp     loc_14008D595
0x14009b976  xor     ebx, ebx
0x14009b978  xor     r9d, r9d
0x14009b97b  jmp     loc_14008D579
0x14009b980  mov     rcx, [rcx+18h]
0x14009b984  lea     r8, WPP_4e8015138ece3414973dc97451d118ee_Traceguids
0x14009b98b  mov     r9, rdi
0x14009b98e  mov     dword ptr [rsp+110h+InitialState], ebx
0x14009b992  call    WPP_SF_qD
0x14009b997  nop
0x14009b998  jmp     loc_14008D593
```

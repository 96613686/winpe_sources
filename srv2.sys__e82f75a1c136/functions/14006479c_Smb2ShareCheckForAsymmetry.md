# Smb2ShareCheckForAsymmetry

- ea: `0x14006479c`
- end: `0x140064985`
- name: `Smb2ShareCheckForAsymmetry`
- size: `489`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14008d858`

## callees

- `0x140013810`
- `0x140038490`
- `0x14006479c`
- `0x140081d90`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14006494e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006494e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400647fd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400647fd`
- `ntoskrnl!ZwCreateEvent` at `0x14006487f`
- `ntoskrnl!ZwCreateEvent` at `0x14006487f`
- `ntoskrnl!NtFsControlFile` at `0x1400648d8`
- `ntoskrnl!NtFsControlFile` at `0x1400648d8`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400648f6`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400648f6`
- `ntoskrnl!NtClose` at `0x140064909`
- `ntoskrnl!NtClose` at `0x140064909`

## pseudocode

```c
bool __fastcall Smb2ShareCheckForAsymmetry(__int64 a1)
{
  HANDLE *ShareHandle; // rsi
  NTSTATUS Status; // edi
  void *EventHandle; // [rsp+50h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-21h] BYREF
  __int128 InputBuffer; // [rsp+98h] [rbp+Fh] BYREF
  __int128 OutputBuffer; // [rsp+A8h] [rbp+1Fh] BYREF

  if ( Smb2SofsAsymmetryMode == 2 )
    return 1;
  if ( !Smb2SofsAsymmetryMode )
    return 0;
  if ( !*(_BYTE *)(a1 + 372) && (*(_DWORD *)(a1 + 368) & 0x4000000) != 0 )
  {
    ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)a1 + 200LL), 1u);
    if ( !*(_BYTE *)(a1 + 372) )
    {
      ShareHandle = (HANDLE *)Smb2GetShareHandleEx(a1, 0, 0, 0);
      if ( ShareHandle )
      {
        EventHandle = 0;
        *(_QWORD *)&ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.ObjectName = 0;
        *(_QWORD *)&ObjectAttributes.Attributes = 512;
        IoStatusBlock = 0;
        InputBuffer = 0;
        OutputBuffer = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0) >= 0 )
        {
          LODWORD(InputBuffer) = 10;
          Status = NtFsControlFile(
                     ShareHandle[11],
                     EventHandle,
                     0,
                     0,
                     &IoStatusBlock,
                     0x9026Cu,
                     &InputBuffer,
                     0x10u,
                     &OutputBuffer,
                     0x10u);
          if ( Status == 259 )
          {
            ZwWaitForSingleObject(EventHandle, 0, 0);
            Status = IoStatusBlock.Status;
          }
          NtClose(EventHandle);
          EventHandle = 0;
          if ( Status >= 0 )
          {
            if ( HIDWORD(OutputBuffer) == 1 )
            {
              *(_BYTE *)(a1 + 372) = 1;
            }
            else if ( HIDWORD(OutputBuffer) )
            {
              *(_BYTE *)(a1 + 372) = 2;
            }
          }
        }
        Smb2DereferenceHandle(ShareHandle);
      }
    }
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)a1 + 200LL));
  }
  return *(_BYTE *)(a1 + 372) == 1;
}

```

## disassembly

```asm
0x14006479c  push    rbp
0x14006479e  push    rbx
0x14006479f  push    rsi
0x1400647a0  push    rdi
0x1400647a1  lea     rbp, [rsp-3Fh]
0x1400647a6  sub     rsp, 0C8h
0x1400647ad  mov     rax, cs:__security_cookie
0x1400647b4  xor     rax, rsp
0x1400647b7  mov     [rbp+57h+var_28], rax
0x1400647bb  mov     al, cs:Smb2SofsAsymmetryMode
0x1400647c1  mov     rbx, rcx
0x1400647c4  cmp     al, 2
0x1400647c6  jz      loc_14006496A
0x1400647cc  test    al, al
0x1400647ce  jz      loc_140064966
0x1400647d4  cmp     byte ptr [rcx+174h], 0
0x1400647db  jnz     loc_14006495A
0x1400647e1  test    dword ptr [rcx+170h], 4000000h
0x1400647eb  jz      loc_14006495A
0x1400647f1  mov     rcx, [rcx]
0x1400647f4  mov     dl, 1; Wait
0x1400647f6  add     rcx, 0C8h; Resource
0x1400647fd  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140064804  nop     dword ptr [rax+rax+00h]
0x140064809  cmp     byte ptr [rbx+174h], 0
0x140064810  jnz     loc_140064944
0x140064816  xor     r9d, r9d
0x140064819  xor     r8d, r8d
0x14006481c  xor     edx, edx
0x14006481e  mov     rcx, rbx
0x140064821  call    Smb2GetShareHandleEx
0x140064826  mov     rsi, rax
0x140064829  test    rax, rax
0x14006482c  jz      loc_140064944
0x140064832  xorps   xmm0, xmm0
0x140064835  mov     [rbp+57h+EventHandle], 0
0x14006483d  xor     eax, eax
0x14006483f  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140064847  xorps   xmm1, xmm1
0x14006484a  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14006484e  xor     r9d, r9d; EventType
0x140064851  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140064855  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140064859  mov     [rsp+0E0h+InitialState], al; InitialState
0x14006485d  mov     edx, 1F0003h; DesiredAccess
0x140064862  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x14006486a  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x14006486e  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140064872  movups  [rbp+57h+var_48], xmm0
0x140064876  movups  [rbp+57h+var_38], xmm1
0x14006487a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14006487f  call    cs:__imp_ZwCreateEvent
0x140064886  nop     dword ptr [rax+rax+00h]
0x14006488b  test    eax, eax
0x14006488d  js      loc_14006493C
0x140064893  mov     rdx, [rbp+57h+EventHandle]; Event
0x140064897  lea     rax, [rbp+57h+var_38]
0x14006489b  mov     ecx, 10h
0x1400648a0  mov     dword ptr [rbp+57h+var_48], 0Ah
0x1400648a7  mov     [rsp+0E0h+OutputBufferLength], ecx; OutputBufferLength
0x1400648ab  xor     r9d, r9d; ApcContext
0x1400648ae  mov     [rsp+0E0h+OutputBuffer], rax; OutputBuffer
0x1400648b3  xor     r8d, r8d; ApcRoutine
0x1400648b6  mov     [rsp+0E0h+InputBufferLength], ecx; InputBufferLength
0x1400648ba  lea     rax, [rbp+57h+var_48]
0x1400648be  mov     rcx, [rsi+58h]; FileHandle
0x1400648c2  mov     [rsp+0E0h+InputBuffer], rax; InputBuffer
0x1400648c7  lea     rax, [rbp+57h+IoStatusBlock]
0x1400648cb  mov     [rsp+0E0h+FsControlCode], 9026Ch; FsControlCode
0x1400648d3  mov     qword ptr [rsp+0E0h+InitialState], rax; IoStatusBlock
0x1400648d8  call    cs:__imp_NtFsControlFile
0x1400648df  nop     dword ptr [rax+rax+00h]
0x1400648e4  mov     edi, eax
0x1400648e6  cmp     eax, 103h
0x1400648eb  jnz     short loc_140064905
0x1400648ed  mov     rcx, [rbp+57h+EventHandle]; Handle
0x1400648f1  xor     r8d, r8d; Timeout
0x1400648f4  xor     edx, edx; Alertable
0x1400648f6  call    cs:__imp_ZwWaitForSingleObject
0x1400648fd  nop     dword ptr [rax+rax+00h]
0x140064902  mov     edi, dword ptr [rbp+57h+IoStatusBlock]
0x140064905  mov     rcx, [rbp+57h+EventHandle]; Handle
0x140064909  call    cs:__imp_NtClose
0x140064910  nop     dword ptr [rax+rax+00h]
0x140064915  mov     [rbp+57h+EventHandle], 0
0x14006491d  test    edi, edi
0x14006491f  js      short loc_14006493C
0x140064921  mov     eax, dword ptr [rbp+57h+var_38+0Ch]
0x140064924  cmp     eax, 1
0x140064927  jnz     short loc_140064931
0x140064929  mov     [rbx+174h], al
0x14006492f  jmp     short loc_14006493C
0x140064931  test    eax, eax
0x140064933  jz      short loc_14006493C
0x140064935  mov     byte ptr [rbx+174h], 2
0x14006493c  mov     rcx, rsi; P
0x14006493f  call    Smb2DereferenceHandle
0x140064944  mov     rcx, [rbx]
0x140064947  add     rcx, 0C8h; Resource
0x14006494e  call    cs:__imp_ExReleaseResourceLite
0x140064955  nop     dword ptr [rax+rax+00h]
0x14006495a  cmp     byte ptr [rbx+174h], 1
0x140064961  setz    al
0x140064964  jmp     short loc_14006496C
0x140064966  xor     al, al
0x140064968  jmp     short loc_14006496C
0x14006496a  mov     al, 1
0x14006496c  mov     rcx, [rbp+57h+var_28]
0x140064970  xor     rcx, rsp; StackCookie
0x140064973  call    __security_check_cookie
0x140064978  add     rsp, 0C8h
0x14006497f  pop     rdi
0x140064980  pop     rsi
0x140064981  pop     rbx
0x140064982  pop     rbp
0x140064983  retn
```

# Smb2ShareCheckForAsymmetry

- ea: `0x14006474c`
- end: `0x140064935`
- name: `Smb2ShareCheckForAsymmetry`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14008d858`

## callees

- `0x140013810`
- `0x140038490`
- `0x14006474c`
- `0x140081d90`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1400648fe`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400648fe`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400647ad`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400647ad`
- `ntoskrnl!ZwCreateEvent` at `0x14006482f`
- `ntoskrnl!ZwCreateEvent` at `0x14006482f`
- `ntoskrnl!NtFsControlFile` at `0x140064888`
- `ntoskrnl!NtFsControlFile` at `0x140064888`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400648a6`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400648a6`
- `ntoskrnl!NtClose` at `0x1400648b9`
- `ntoskrnl!NtClose` at `0x1400648b9`

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
0x14006474c  push    rbp
0x14006474e  push    rbx
0x14006474f  push    rsi
0x140064750  push    rdi
0x140064751  lea     rbp, [rsp-3Fh]
0x140064756  sub     rsp, 0C8h
0x14006475d  mov     rax, cs:__security_cookie
0x140064764  xor     rax, rsp
0x140064767  mov     [rbp+57h+var_28], rax
0x14006476b  mov     al, cs:Smb2SofsAsymmetryMode
0x140064771  mov     rbx, rcx
0x140064774  cmp     al, 2
0x140064776  jz      loc_14006491A
0x14006477c  test    al, al
0x14006477e  jz      loc_140064916
0x140064784  cmp     byte ptr [rcx+174h], 0
0x14006478b  jnz     loc_14006490A
0x140064791  test    dword ptr [rcx+170h], 4000000h
0x14006479b  jz      loc_14006490A
0x1400647a1  mov     rcx, [rcx]
0x1400647a4  mov     dl, 1; Wait
0x1400647a6  add     rcx, 0C8h; Resource
0x1400647ad  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400647b4  nop     dword ptr [rax+rax+00h]
0x1400647b9  cmp     byte ptr [rbx+174h], 0
0x1400647c0  jnz     loc_1400648F4
0x1400647c6  xor     r9d, r9d
0x1400647c9  xor     r8d, r8d
0x1400647cc  xor     edx, edx
0x1400647ce  mov     rcx, rbx
0x1400647d1  call    Smb2GetShareHandleEx
0x1400647d6  mov     rsi, rax
0x1400647d9  test    rax, rax
0x1400647dc  jz      loc_1400648F4
0x1400647e2  xorps   xmm0, xmm0
0x1400647e5  mov     [rbp+57h+EventHandle], 0
0x1400647ed  xor     eax, eax
0x1400647ef  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400647f7  xorps   xmm1, xmm1
0x1400647fa  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1400647fe  xor     r9d, r9d; EventType
0x140064801  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140064805  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140064809  mov     [rsp+0E0h+InitialState], al; InitialState
0x14006480d  mov     edx, 1F0003h; DesiredAccess
0x140064812  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x14006481a  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x14006481e  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140064822  movups  [rbp+57h+var_48], xmm0
0x140064826  movups  [rbp+57h+var_38], xmm1
0x14006482a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14006482f  call    cs:__imp_ZwCreateEvent
0x140064836  nop     dword ptr [rax+rax+00h]
0x14006483b  test    eax, eax
0x14006483d  js      loc_1400648EC
0x140064843  mov     rdx, [rbp+57h+EventHandle]; Event
0x140064847  lea     rax, [rbp+57h+var_38]
0x14006484b  mov     ecx, 10h
0x140064850  mov     dword ptr [rbp+57h+var_48], 0Ah
0x140064857  mov     [rsp+0E0h+OutputBufferLength], ecx; OutputBufferLength
0x14006485b  xor     r9d, r9d; ApcContext
0x14006485e  mov     [rsp+0E0h+OutputBuffer], rax; OutputBuffer
0x140064863  xor     r8d, r8d; ApcRoutine
0x140064866  mov     [rsp+0E0h+InputBufferLength], ecx; InputBufferLength
0x14006486a  lea     rax, [rbp+57h+var_48]
0x14006486e  mov     rcx, [rsi+58h]; FileHandle
0x140064872  mov     [rsp+0E0h+InputBuffer], rax; InputBuffer
0x140064877  lea     rax, [rbp+57h+IoStatusBlock]
0x14006487b  mov     [rsp+0E0h+FsControlCode], 9026Ch; FsControlCode
0x140064883  mov     qword ptr [rsp+0E0h+InitialState], rax; IoStatusBlock
0x140064888  call    cs:__imp_NtFsControlFile
0x14006488f  nop     dword ptr [rax+rax+00h]
0x140064894  mov     edi, eax
0x140064896  cmp     eax, 103h
0x14006489b  jnz     short loc_1400648B5
0x14006489d  mov     rcx, [rbp+57h+EventHandle]; Handle
0x1400648a1  xor     r8d, r8d; Timeout
0x1400648a4  xor     edx, edx; Alertable
0x1400648a6  call    cs:__imp_ZwWaitForSingleObject
0x1400648ad  nop     dword ptr [rax+rax+00h]
0x1400648b2  mov     edi, dword ptr [rbp+57h+IoStatusBlock]
0x1400648b5  mov     rcx, [rbp+57h+EventHandle]; Handle
0x1400648b9  call    cs:__imp_NtClose
0x1400648c0  nop     dword ptr [rax+rax+00h]
0x1400648c5  mov     [rbp+57h+EventHandle], 0
0x1400648cd  test    edi, edi
0x1400648cf  js      short loc_1400648EC
0x1400648d1  mov     eax, dword ptr [rbp+57h+var_38+0Ch]
0x1400648d4  cmp     eax, 1
0x1400648d7  jnz     short loc_1400648E1
0x1400648d9  mov     [rbx+174h], al
0x1400648df  jmp     short loc_1400648EC
0x1400648e1  test    eax, eax
0x1400648e3  jz      short loc_1400648EC
0x1400648e5  mov     byte ptr [rbx+174h], 2
0x1400648ec  mov     rcx, rsi; P
0x1400648ef  call    Smb2DereferenceHandle
0x1400648f4  mov     rcx, [rbx]
0x1400648f7  add     rcx, 0C8h; Resource
0x1400648fe  call    cs:__imp_ExReleaseResourceLite
0x140064905  nop     dword ptr [rax+rax+00h]
0x14006490a  cmp     byte ptr [rbx+174h], 1
0x140064911  setz    al
0x140064914  jmp     short loc_14006491C
0x140064916  xor     al, al
0x140064918  jmp     short loc_14006491C
0x14006491a  mov     al, 1
0x14006491c  mov     rcx, [rbp+57h+var_28]
0x140064920  xor     rcx, rsp; StackCookie
0x140064923  call    __security_check_cookie
0x140064928  add     rsp, 0C8h
0x14006492f  pop     rdi
0x140064930  pop     rsi
0x140064931  pop     rbx
0x140064932  pop     rbp
0x140064933  retn
```

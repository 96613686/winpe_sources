# WimpFSFBitLockerCheckWorker

- ea: `0x1400292e0`
- end: `0x14002958e`
- name: `WimpFSFBitLockerCheckWorker`
- size: `686`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x1400292e0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14002954c`
- `ntoskrnl!ZwClose` at `0x14002954c`
- `ntoskrnl!RtlCompareMemory` at `0x1400294be`
- `ntoskrnl!RtlCompareMemory` at `0x1400294e9`
- `ntoskrnl!RtlCompareMemory` at `0x1400294be`
- `ntoskrnl!RtlCompareMemory` at `0x1400294e9`
- `ntoskrnl!KeSetEvent` at `0x140029565`
- `ntoskrnl!KeSetEvent` at `0x140029565`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400293b1`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x140029449`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400293b1`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x140029449`
- `ntoskrnl!ZwOpenFile` at `0x14002935b`
- `ntoskrnl!ZwOpenFile` at `0x14002935b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029537`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029537`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400293f5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400293f5`

## pseudocode

```c
LONG __fastcall WimpFSFBitLockerCheckWorker(__int64 a1)
{
  NTSTATUS v2; // ebx
  unsigned int *OutputBuffer; // rax
  unsigned int *v4; // rsi
  unsigned int v5; // r15d
  unsigned int *v6; // rdi
  unsigned int i; // r12d
  unsigned int v8; // eax
  unsigned int v9; // edx
  __int64 v10; // rax
  struct _KEVENT *v11; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  SIZE_T NumberOfBytes; // [rsp+C0h] [rbp+67h] BYREF
  void *FileHandle; // [rsp+C8h] [rbp+6Fh] BYREF

  ObjectAttributes.RootDirectory = 0;
  LODWORD(NumberOfBytes) = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)(a1 + 48);
  FileHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenFile(&FileHandle, 0x80u, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( v2 >= 0 )
  {
    v2 = ZwDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x4C4210CCu, 0, 0, &NumberOfBytes, 4u);
    if ( (int)(v2 + 0x80000000) < 0 || v2 == -2147483643 )
    {
      if ( IoStatusBlock.Information >= 4 )
      {
        OutputBuffer = (unsigned int *)ExAllocatePoolWithTag(PagedPool, (unsigned int)NumberOfBytes, 0x69637077u);
        v4 = OutputBuffer;
        if ( OutputBuffer )
        {
          v2 = ZwDeviceIoControlFile(
                 FileHandle,
                 0,
                 0,
                 0,
                 &IoStatusBlock,
                 0x4C4210CCu,
                 0,
                 0,
                 OutputBuffer,
                 NumberOfBytes);
          if ( v2 >= 0 )
          {
            v5 = 8;
            v6 = v4 + 2;
            for ( i = 0; i < v4[1] && *v4 > v5; ++i )
            {
              v8 = v6[4];
              if ( v8 )
              {
                v9 = v6[5];
                if ( v9 )
                {
                  if ( v8 >= *v6 || v9 + v8 > *v6 )
                  {
                    v2 = -1073741675;
                    break;
                  }
                  if ( v6[3] == 6
                    && (RtlCompareMemory(L"SEI", (char *)v6 + v6[2], 6u) == 6
                     || v6[3] == 6 && RtlCompareMemory(L"HEI", (char *)v6 + v6[2], 6u) == 6) )
                  {
                    if ( v6[5] != 4 )
                    {
                      v2 = -1073741811;
                      break;
                    }
                    if ( (*(unsigned int *)((char *)v6 + v6[4]) & 4) != 0 )
                    {
                      *(_BYTE *)(a1 + 44) = 1;
                      break;
                    }
                  }
                }
              }
              v10 = *v6;
              v5 += v10;
              v6 = (unsigned int *)((char *)v6 + v10);
            }
          }
          ExFreePoolWithTag(v4, 0x69637077u);
        }
        else
        {
          v2 = -1073741801;
        }
      }
      else
      {
        v2 = -1073741811;
      }
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  v11 = *(struct _KEVENT **)(a1 + 32);
  *(_DWORD *)(a1 + 40) = v2;
  return KeSetEvent(v11, 0, 0);
}

```

## disassembly

```asm
0x1400292e0  mov     [rsp-8+arg_10], rbx
0x1400292e5  mov     [rsp-8+arg_18], rsi
0x1400292ea  push    rbp
0x1400292eb  push    rdi
0x1400292ec  push    r12
0x1400292ee  push    r14
0x1400292f0  push    r15
0x1400292f2  lea     rbp, [rsp-37h]
0x1400292f7  sub     rsp, 90h
0x1400292fe  xor     eax, eax
0x140029300  mov     [rsp+0B0h+OpenOptions], 20h ; ' '; OpenOptions
0x140029308  xorps   xmm0, xmm0
0x14002930b  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14002930f  lea     rax, [rcx+30h]
0x140029313  mov     dword ptr [rbp+57h+NumberOfBytes], 0
0x14002931a  mov     r14, rcx
0x14002931d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140029321  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140029325  mov     [rbp+57h+FileHandle], 0
0x14002932d  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140029331  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140029339  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002933d  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140029345  mov     edx, 80h; DesiredAccess
0x14002934a  mov     [rsp+0B0h+ShareAccess], 3; ShareAccess
0x140029352  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140029356  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002935b  call    cs:__imp_ZwOpenFile
0x140029362  nop     dword ptr [rax+rax+00h]
0x140029367  mov     ebx, eax
0x140029369  test    eax, eax
0x14002936b  js      loc_140029543
0x140029371  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140029375  lea     rax, [rbp+57h+NumberOfBytes]
0x140029379  mov     [rsp+0B0h+OutputBufferLength], 4; OutputBufferLength
0x140029381  mov     edi, 4C4210CCh
0x140029386  mov     [rsp+0B0h+OutputBuffer], rax; OutputBuffer
0x14002938b  xor     r9d, r9d; ApcContext
0x14002938e  mov     [rsp+0B0h+InputBufferLength], 0; InputBufferLength
0x140029396  lea     rax, [rbp+57h+IoStatusBlock]
0x14002939a  mov     [rsp+0B0h+InputBuffer], 0; InputBuffer
0x1400293a3  xor     r8d, r8d; ApcRoutine
0x1400293a6  mov     [rsp+0B0h+OpenOptions], edi; IoControlCode
0x1400293aa  xor     edx, edx; Event
0x1400293ac  mov     qword ptr [rsp+0B0h+ShareAccess], rax; IoStatusBlock
0x1400293b1  call    cs:__imp_ZwDeviceIoControlFile
0x1400293b8  nop     dword ptr [rax+rax+00h]
0x1400293bd  mov     ecx, 80000000h
0x1400293c2  mov     ebx, eax
0x1400293c4  add     eax, ecx
0x1400293c6  test    ecx, eax
0x1400293c8  jnz     short loc_1400293D6
0x1400293ca  cmp     ebx, 80000005h
0x1400293d0  jnz     loc_140029543
0x1400293d6  cmp     [rbp+57h+IoStatusBlock.Information], 4
0x1400293db  jnb     short loc_1400293E7
0x1400293dd  mov     ebx, 0C000000Dh
0x1400293e2  jmp     loc_140029543
0x1400293e7  mov     edx, dword ptr [rbp+57h+NumberOfBytes]; NumberOfBytes
0x1400293ea  mov     ecx, 1; PoolType
0x1400293ef  mov     r8d, 69637077h; Tag
0x1400293f5  call    cs:__imp_ExAllocatePoolWithTag
0x1400293fc  nop     dword ptr [rax+rax+00h]
0x140029401  mov     rsi, rax
0x140029404  test    rax, rax
0x140029407  jnz     short loc_140029413
0x140029409  mov     ebx, 0C0000017h
0x14002940e  jmp     loc_140029543
0x140029413  mov     eax, dword ptr [rbp+57h+NumberOfBytes]
0x140029416  xor     r9d, r9d; ApcContext
0x140029419  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14002941d  xor     r8d, r8d; ApcRoutine
0x140029420  mov     [rsp+0B0h+OutputBufferLength], eax; OutputBufferLength
0x140029424  xor     edx, edx; Event
0x140029426  mov     [rsp+0B0h+OutputBuffer], rsi; OutputBuffer
0x14002942b  lea     rax, [rbp+57h+IoStatusBlock]
0x14002942f  mov     [rsp+0B0h+InputBufferLength], 0; InputBufferLength
0x140029437  mov     [rsp+0B0h+InputBuffer], 0; InputBuffer
0x140029440  mov     [rsp+0B0h+OpenOptions], edi; IoControlCode
0x140029444  mov     qword ptr [rsp+0B0h+ShareAccess], rax; IoStatusBlock
0x140029449  call    cs:__imp_ZwDeviceIoControlFile
0x140029450  nop     dword ptr [rax+rax+00h]
0x140029455  mov     ebx, eax
0x140029457  test    eax, eax
0x140029459  js      loc_14002952F
0x14002945f  mov     r15d, 8
0x140029465  lea     rdi, [rsi+8]
0x140029469  xor     r12d, r12d
0x14002946c  cmp     r12d, [rsi+4]
0x140029470  jnb     loc_14002952F
0x140029476  cmp     [rsi], r15d
0x140029479  jbe     loc_14002952F
0x14002947f  mov     eax, [rdi+10h]
0x140029482  test    eax, eax
0x140029484  jz      loc_14002950C
0x14002948a  mov     edx, [rdi+14h]
0x14002948d  test    edx, edx
0x14002948f  jz      short loc_14002950C
0x140029491  mov     ecx, [rdi]
0x140029493  cmp     eax, ecx
0x140029495  jnb     loc_14002952A
0x14002949b  add     eax, edx
0x14002949d  cmp     eax, ecx
0x14002949f  ja      loc_14002952A
0x1400294a5  cmp     dword ptr [rdi+0Ch], 6
0x1400294a9  jnz     short loc_14002950C
0x1400294ab  mov     edx, [rdi+8]
0x1400294ae  lea     rcx, aSei; "SEI"
0x1400294b5  add     rdx, rdi; Source2
0x1400294b8  mov     r8d, 6; Length
0x1400294be  call    cs:__imp_RtlCompareMemory
0x1400294c5  nop     dword ptr [rax+rax+00h]
0x1400294ca  cmp     rax, 6
0x1400294ce  jz      short loc_1400294FB
0x1400294d0  cmp     dword ptr [rdi+0Ch], 6
0x1400294d4  jnz     short loc_14002950C
0x1400294d6  mov     edx, [rdi+8]
0x1400294d9  lea     rcx, aHei; "HEI"
0x1400294e0  add     rdx, rdi; Source2
0x1400294e3  mov     r8d, 6; Length
0x1400294e9  call    cs:__imp_RtlCompareMemory
0x1400294f0  nop     dword ptr [rax+rax+00h]
0x1400294f5  cmp     rax, 6
0x1400294f9  jnz     short loc_14002950C
0x1400294fb  cmp     dword ptr [rdi+14h], 4
0x1400294ff  jnz     short loc_140029523
0x140029501  mov     eax, [rdi+10h]
0x140029504  mov     ecx, [rax+rdi]
0x140029507  test    cl, 4
0x14002950a  jnz     short loc_14002951C
0x14002950c  mov     eax, [rdi]
0x14002950e  inc     r12d
0x140029511  add     r15d, eax
0x140029514  add     rdi, rax
0x140029517  jmp     loc_14002946C
0x14002951c  mov     byte ptr [r14+2Ch], 1
0x140029521  jmp     short loc_14002952F
0x140029523  mov     ebx, 0C000000Dh
0x140029528  jmp     short loc_14002952F
0x14002952a  mov     ebx, 0C0000095h
0x14002952f  mov     edx, 69637077h; Tag
0x140029534  mov     rcx, rsi; P
0x140029537  call    cs:__imp_ExFreePoolWithTag
0x14002953e  nop     dword ptr [rax+rax+00h]
0x140029543  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140029547  test    rcx, rcx
0x14002954a  jz      short loc_140029558
0x14002954c  call    cs:__imp_ZwClose
0x140029553  nop     dword ptr [rax+rax+00h]
0x140029558  mov     rcx, [r14+20h]; Event
0x14002955c  xor     r8d, r8d; Wait
0x14002955f  xor     edx, edx; Increment
0x140029561  mov     [r14+28h], ebx
0x140029565  call    cs:__imp_KeSetEvent
0x14002956c  nop     dword ptr [rax+rax+00h]
0x140029571  lea     r11, [rsp+0B0h+var_20]
0x140029579  mov     rbx, [r11+40h]
0x14002957d  mov     rsi, [r11+48h]
0x140029581  mov     rsp, r11
0x140029584  pop     r15
0x140029586  pop     r14
0x140029588  pop     r12
0x14002958a  pop     rdi
0x14002958b  pop     rbp
0x14002958c  retn
```

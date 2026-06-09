# RootFileRdmaIoctlPreprocess

- ea: `0x140006b50`
- end: `0x140006c14`
- name: `RootFileRdmaIoctlPreprocess`
- size: `196`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002f04`
- `0x1400030fc`
- `0x140006b50`
- `0x140017190`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140006bc8`
- `ntoskrnl!IofCompleteRequest` at `0x140006bc8`

## pseudocode

```c
__int64 __fastcall RootFileRdmaIoctlPreprocess(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r8
  PVOID FsContext; // rdx
  DWORD LowPart; // eax
  KSPIN_LOCK *v7; // rcx
  NTSTATUS v8; // eax
  unsigned int v9; // edi

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FsContext = CurrentStackLocation->FileObject->FsContext;
  if ( *((_DWORD *)FsContext + 2) != 7 || (*((_BYTE *)FsContext + 232) & 0x10) == 0 )
    goto LABEL_11;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  v7 = (KSPIN_LOCK *)*((_QWORD *)FsContext + 47);
  if ( LowPart == 4112536 )
  {
    v8 = PipeSetupGpaRange(v7);
  }
  else
  {
    if ( LowPart != 4112540 )
    {
LABEL_11:
      ++a2->CurrentLocation;
      ++a2->Tail.Overlay.CurrentStackLocation;
      return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, IRP *))(WdfFunctions_01033 + 272))(
               WdfDriverGlobals,
               a1,
               a2);
    }
    v8 = PipeTeardownGpaRange(v7);
  }
  v9 = v8;
  if ( v8 == -1073741802 )
    goto LABEL_11;
  if ( v8 != 259 )
  {
    a2->IoStatus.Status = v8;
    IofCompleteRequest(a2, 0);
  }
  return v9;
}

```

## disassembly

```asm
0x140006b50  mov     [rsp+arg_0], rbx
0x140006b55  mov     [rsp+arg_8], rsi
0x140006b5a  push    rdi
0x140006b5b  sub     rsp, 20h
0x140006b5f  mov     r8, [rdx+0B8h]
0x140006b66  mov     rbx, rdx
0x140006b69  mov     rsi, rcx
0x140006b6c  mov     rax, [r8+30h]
0x140006b70  mov     rdx, [rax+18h]
0x140006b74  mov     eax, [rdx+8]
0x140006b77  cmp     eax, 7
0x140006b7a  jnz     short loc_140006BD8
0x140006b7c  test    byte ptr [rdx+0E8h], 10h
0x140006b83  jz      short loc_140006BD8
0x140006b85  mov     eax, [r8+18h]
0x140006b89  mov     rcx, [rdx+178h]; SpinLock
0x140006b90  cmp     eax, 3EC098h
0x140006b95  jnz     short loc_140006BA1
0x140006b97  mov     rdx, rbx
0x140006b9a  call    PipeSetupGpaRange
0x140006b9f  jmp     short loc_140006BB0
0x140006ba1  cmp     eax, 3EC09Ch
0x140006ba6  jnz     short loc_140006BD8
0x140006ba8  mov     rdx, rbx
0x140006bab  call    PipeTeardownGpaRange
0x140006bb0  mov     edi, eax
0x140006bb2  cmp     eax, 0C0000016h
0x140006bb7  jz      short loc_140006BD8
0x140006bb9  cmp     eax, 103h
0x140006bbe  jz      short loc_140006BD4
0x140006bc0  xor     edx, edx; PriorityBoost
0x140006bc2  mov     [rbx+30h], eax
0x140006bc5  mov     rcx, rbx; Irp
0x140006bc8  call    cs:__imp_IofCompleteRequest
0x140006bcf  nop     dword ptr [rax+rax+00h]
0x140006bd4  mov     eax, edi
0x140006bd6  jmp     short loc_140006C03
0x140006bd8  inc     byte ptr [rbx+43h]
0x140006bdb  mov     r8, rbx
0x140006bde  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x140006be6  mov     rdx, rsi
0x140006be9  mov     rax, cs:WdfFunctions_01033
0x140006bf0  mov     rcx, cs:WdfDriverGlobals
0x140006bf7  mov     rax, [rax+110h]
0x140006bfe  call    _guard_dispatch_icall
0x140006c03  mov     rbx, [rsp+28h+arg_0]
0x140006c08  mov     rsi, [rsp+28h+arg_8]
0x140006c0d  add     rsp, 20h
0x140006c11  pop     rdi
0x140006c12  retn
```

# TdiRegisterProvider

- ea: `0x140004080`
- end: `0x14000419c`
- name: `TdiRegisterProvider`
- size: `284`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING ProviderName, HANDLE *ProviderHandle)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002f50`
- `0x140004080`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400040a5`
- `ntoskrnl!ExAllocatePool2` at `0x1400040e3`
- `ntoskrnl!ExAllocatePool2` at `0x1400040a5`
- `ntoskrnl!ExAllocatePool2` at `0x1400040e3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140004129`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140004129`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400040fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004160`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004171`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400040fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004160`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004171`

## pseudocode

```c
NTSTATUS __stdcall TdiRegisterProvider(PUNICODE_STRING ProviderName, HANDLE *ProviderHandle)
{
  __int64 Pool2; // rbx
  void *v6; // rbp
  NTSTATUS v7; // edi

  Pool2 = ExAllocatePool2(64, 136, 1665746004);
  if ( !Pool2 )
    return -1073741670;
  v6 = (void *)ExAllocatePool2(64, ProviderName->MaximumLength, 1682523220);
  if ( v6 )
  {
    *(_BYTE *)(Pool2 + 16) = 3;
    *(_WORD *)(Pool2 + 122) = ProviderName->MaximumLength;
    *(_QWORD *)(Pool2 + 128) = v6;
    RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 120), ProviderName);
    *ProviderHandle = (HANDLE)Pool2;
    *(_QWORD *)(Pool2 + 80) = 0;
    *(_QWORD *)(Pool2 + 88) = 0;
    v7 = TdiHandleSerializedRequest(Pool2, 17);
    if ( v7 )
    {
      ExFreePoolWithTag(v6, 0);
      ExFreePoolWithTag((PVOID)Pool2, 0);
      *ProviderHandle = 0;
    }
    return v7;
  }
  else
  {
    ExFreePoolWithTag((PVOID)Pool2, 0);
    return -1073741670;
  }
}

```

## disassembly

```asm
0x140004080  mov     [rsp+arg_8], rbx
0x140004085  mov     [rsp+arg_10], rsi
0x14000408a  push    rdi
0x14000408b  sub     rsp, 20h
0x14000408f  mov     rsi, rdx
0x140004092  mov     rdi, rcx
0x140004095  mov     edx, 88h
0x14000409a  mov     ecx, 40h ; '@'
0x14000409f  mov     r8d, 63494454h
0x1400040a5  call    cs:__imp_ExAllocatePool2
0x1400040ac  nop     dword ptr [rax+rax+00h]
0x1400040b1  mov     rbx, rax
0x1400040b4  test    rax, rax
0x1400040b7  jnz     short loc_1400040CF
0x1400040b9  mov     eax, 0C000009Ah
0x1400040be  mov     rbx, [rsp+28h+arg_8]
0x1400040c3  mov     rsi, [rsp+28h+arg_10]
0x1400040c8  add     rsp, 20h
0x1400040cc  pop     rdi
0x1400040cd  retn
0x1400040cf  movzx   edx, word ptr [rdi+2]
0x1400040d3  mov     ecx, 40h ; '@'
0x1400040d8  mov     r8d, 64494454h
0x1400040de  mov     [rsp+28h+arg_0], rbp
0x1400040e3  call    cs:__imp_ExAllocatePool2
0x1400040ea  nop     dword ptr [rax+rax+00h]
0x1400040ef  mov     rbp, rax
0x1400040f2  test    rax, rax
0x1400040f5  jnz     short loc_14000410F
0x1400040f7  xor     edx, edx; Tag
0x1400040f9  mov     rcx, rbx; P
0x1400040fc  call    cs:__imp_ExFreePoolWithTag
0x140004103  nop     dword ptr [rax+rax+00h]
0x140004108  mov     eax, 0C000009Ah
0x14000410d  jmp     short loc_140004186
0x14000410f  mov     byte ptr [rbx+10h], 3
0x140004113  lea     rcx, [rbx+78h]; DestinationString
0x140004117  movzx   eax, word ptr [rdi+2]
0x14000411b  mov     rdx, rdi; SourceString
0x14000411e  mov     [rbx+7Ah], ax
0x140004122  mov     [rbx+80h], rbp
0x140004129  call    cs:__imp_RtlCopyUnicodeString
0x140004130  nop     dword ptr [rax+rax+00h]
0x140004135  mov     [rsi], rbx
0x140004138  mov     edx, 11h
0x14000413d  mov     rcx, rbx
0x140004140  mov     qword ptr [rbx+50h], 0
0x140004148  mov     qword ptr [rbx+58h], 0
0x140004150  call    TdiHandleSerializedRequest
0x140004155  mov     edi, eax
0x140004157  test    eax, eax
0x140004159  jz      short loc_140004184
0x14000415b  xor     edx, edx; Tag
0x14000415d  mov     rcx, rbp; P
0x140004160  call    cs:__imp_ExFreePoolWithTag
0x140004167  nop     dword ptr [rax+rax+00h]
0x14000416c  xor     edx, edx; Tag
0x14000416e  mov     rcx, rbx; P
0x140004171  call    cs:__imp_ExFreePoolWithTag
0x140004178  nop     dword ptr [rax+rax+00h]
0x14000417d  mov     qword ptr [rsi], 0
0x140004184  mov     eax, edi
0x140004186  mov     rbp, [rsp+28h+arg_0]
0x14000418b  mov     rbx, [rsp+28h+arg_8]
0x140004190  mov     rsi, [rsp+28h+arg_10]
0x140004195  add     rsp, 20h
0x140004199  pop     rdi
0x14000419a  retn
```

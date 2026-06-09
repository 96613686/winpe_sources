# Smb2IsKnownPassthroughEcp

- ea: `0x140032a78`
- end: `0x140032bb5`
- name: `Smb2IsKnownPassthroughEcp`
- size: `317`
- prototype: `__int64 __fastcall(void *Source1)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000f4d0`
- `0x14007d3e4`

## callees

- `0x140032a78`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140032a9c`
- `ntoskrnl!RtlCompareMemory` at `0x140032abe`
- `ntoskrnl!RtlCompareMemory` at `0x140032ae0`
- `ntoskrnl!RtlCompareMemory` at `0x140032b02`
- `ntoskrnl!RtlCompareMemory` at `0x140032b24`
- `ntoskrnl!RtlCompareMemory` at `0x140032b42`
- `ntoskrnl!RtlCompareMemory` at `0x140032b57`
- `ntoskrnl!RtlCompareMemory` at `0x140032b75`
- `ntoskrnl!RtlCompareMemory` at `0x140032b93`
- `ntoskrnl!RtlCompareMemory` at `0x140032a9c`
- `ntoskrnl!RtlCompareMemory` at `0x140032abe`
- `ntoskrnl!RtlCompareMemory` at `0x140032ae0`
- `ntoskrnl!RtlCompareMemory` at `0x140032b02`
- `ntoskrnl!RtlCompareMemory` at `0x140032b24`
- `ntoskrnl!RtlCompareMemory` at `0x140032b42`
- `ntoskrnl!RtlCompareMemory` at `0x140032b57`
- `ntoskrnl!RtlCompareMemory` at `0x140032b75`
- `ntoskrnl!RtlCompareMemory` at `0x140032b93`

## pseudocode

```c
bool __fastcall Smb2IsKnownPassthroughEcp(void *Source1, char a2)
{
  if ( a2 )
  {
    if ( RtlCompareMemory(Source1, &Smb2RkfGuidEcpIn, 0x10u) != 16
      && RtlCompareMemory(Source1, &GUID_ECP_NETWORK_APP_INSTANCE, 0x10u) != 16
      && RtlCompareMemory(Source1, &GUID_ECP_NETWORK_APP_INSTANCE_VERSION, 0x10u) != 16
      && RtlCompareMemory(Source1, &GUID_ECP_CSV_INITIAL_INFO, 0x10u) != 16
      && RtlCompareMemory(Source1, &GUID_ECP_OPEN_AS_BLOCK_DEVICE, 0x10u) != 16
      && RtlCompareMemory(Source1, &GUID_ECP_ENABLE_REDIRECTIONGUARD, 0x10u) != 16 )
    {
      return 0;
    }
  }
  else if ( RtlCompareMemory(Source1, &Smb2RkfGuidEcpIn, 0x10u) != 16
         && RtlCompareMemory(Source1, &GUID_ECP_CSV_INITIAL_INFO, 0x10u) != 16 )
  {
    return RtlCompareMemory(Source1, &GUID_ECP_OPEN_AS_BLOCK_DEVICE, 0x10u) == 16;
  }
  return 1;
}

```

## disassembly

```asm
0x140032a78  mov     [rsp+arg_0], rbx
0x140032a7d  push    rdi
0x140032a7e  sub     rsp, 20h
0x140032a82  mov     ebx, 10h
0x140032a87  test    dl, dl
0x140032a89  mov     r8d, ebx; Length
0x140032a8c  lea     rdx, Smb2RkfGuidEcpIn; Source2
0x140032a93  mov     rdi, rcx
0x140032a96  jz      loc_140032B57
0x140032a9c  call    cs:__imp_RtlCompareMemory
0x140032aa3  nop     dword ptr [rax+rax+00h]
0x140032aa8  cmp     rax, rbx
0x140032aab  jz      loc_140032BA7
0x140032ab1  mov     r8d, ebx; Length
0x140032ab4  lea     rdx, GUID_ECP_NETWORK_APP_INSTANCE; Source2
0x140032abb  mov     rcx, rdi; Source1
0x140032abe  call    cs:__imp_RtlCompareMemory
0x140032ac5  nop     dword ptr [rax+rax+00h]
0x140032aca  cmp     rax, rbx
0x140032acd  jz      loc_140032BA7
0x140032ad3  mov     r8d, ebx; Length
0x140032ad6  lea     rdx, GUID_ECP_NETWORK_APP_INSTANCE_VERSION; Source2
0x140032add  mov     rcx, rdi; Source1
0x140032ae0  call    cs:__imp_RtlCompareMemory
0x140032ae7  nop     dword ptr [rax+rax+00h]
0x140032aec  cmp     rax, rbx
0x140032aef  jz      loc_140032BA7
0x140032af5  mov     r8d, ebx; Length
0x140032af8  lea     rdx, GUID_ECP_CSV_INITIAL_INFO; Source2
0x140032aff  mov     rcx, rdi; Source1
0x140032b02  call    cs:__imp_RtlCompareMemory
0x140032b09  nop     dword ptr [rax+rax+00h]
0x140032b0e  cmp     rax, rbx
0x140032b11  jz      loc_140032BA7
0x140032b17  mov     r8d, ebx; Length
0x140032b1a  lea     rdx, GUID_ECP_OPEN_AS_BLOCK_DEVICE; Source2
0x140032b21  mov     rcx, rdi; Source1
0x140032b24  call    cs:__imp_RtlCompareMemory
0x140032b2b  nop     dword ptr [rax+rax+00h]
0x140032b30  cmp     rax, rbx
0x140032b33  jz      short loc_140032BA7
0x140032b35  mov     r8d, ebx; Length
0x140032b38  lea     rdx, GUID_ECP_ENABLE_REDIRECTIONGUARD; Source2
0x140032b3f  mov     rcx, rdi; Source1
0x140032b42  call    cs:__imp_RtlCompareMemory
0x140032b49  nop     dword ptr [rax+rax+00h]
0x140032b4e  cmp     rax, rbx
0x140032b51  jz      short loc_140032BA7
0x140032b53  xor     al, al
0x140032b55  jmp     short loc_140032BA9
0x140032b57  call    cs:__imp_RtlCompareMemory
0x140032b5e  nop     dword ptr [rax+rax+00h]
0x140032b63  cmp     rax, rbx
0x140032b66  jz      short loc_140032BA7
0x140032b68  mov     r8, rbx; Length
0x140032b6b  lea     rdx, GUID_ECP_CSV_INITIAL_INFO; Source2
0x140032b72  mov     rcx, rdi; Source1
0x140032b75  call    cs:__imp_RtlCompareMemory
0x140032b7c  nop     dword ptr [rax+rax+00h]
0x140032b81  cmp     rax, rbx
0x140032b84  jz      short loc_140032BA7
0x140032b86  mov     r8, rbx; Length
0x140032b89  lea     rdx, GUID_ECP_OPEN_AS_BLOCK_DEVICE; Source2
0x140032b90  mov     rcx, rdi; Source1
0x140032b93  call    cs:__imp_RtlCompareMemory
0x140032b9a  nop     dword ptr [rax+rax+00h]
0x140032b9f  cmp     rax, rbx
0x140032ba2  setz    al
0x140032ba5  jmp     short loc_140032BA9
0x140032ba7  mov     al, 1
0x140032ba9  mov     rbx, [rsp+28h+arg_0]
0x140032bae  add     rsp, 20h
0x140032bb2  pop     rdi
0x140032bb3  retn
```

# SmbCompressionInitialize

- ea: `0x140020a94`
- end: `0x140020b9d`
- name: `SmbCompressionInitialize`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005b3c8`

## callees

- `0x140013a84`
- `0x14001b808`
- `0x140020a94`

## import_xrefs

- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x140020ac1`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x140020aee`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x140020b18`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x140020b3e`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x140020ac1`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x140020aee`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x140020b18`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x140020b3e`

## pseudocode

```c
__int64 SmbCompressionInitialize()
{
  NTSTATUS CompressionWorkSpaceSize; // ebx
  ULONG v1; // edi
  int v3; // [rsp+20h] [rbp-30h]
  int v4; // [rsp+38h] [rbp-18h]
  ULONG CompressBufferWorkSpaceSize; // [rsp+60h] [rbp+10h] BYREF
  ULONG CompressFragmentWorkSpaceSize; // [rsp+68h] [rbp+18h] BYREF

  CompressBufferWorkSpaceSize = 0;
  CompressFragmentWorkSpaceSize = 0;
  CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(
                               2u,
                               &CompressBufferWorkSpaceSize,
                               &CompressFragmentWorkSpaceSize);
  if ( CompressionWorkSpaceSize < 0 )
    goto LABEL_15;
  v1 = 0;
  if ( CompressBufferWorkSpaceSize )
    v1 = CompressBufferWorkSpaceSize;
  CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(
                               3u,
                               &CompressBufferWorkSpaceSize,
                               &CompressFragmentWorkSpaceSize);
  if ( CompressionWorkSpaceSize < 0 )
    goto LABEL_15;
  if ( CompressBufferWorkSpaceSize > v1 )
    v1 = CompressBufferWorkSpaceSize;
  CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(
                               4u,
                               &CompressBufferWorkSpaceSize,
                               &CompressFragmentWorkSpaceSize);
  if ( CompressionWorkSpaceSize < 0 )
    goto LABEL_15;
  if ( CompressBufferWorkSpaceSize > v1 )
    v1 = CompressBufferWorkSpaceSize;
  CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(
                               6u,
                               &CompressBufferWorkSpaceSize,
                               &CompressFragmentWorkSpaceSize);
  if ( CompressionWorkSpaceSize < 0 )
    goto LABEL_15;
  if ( CompressBufferWorkSpaceSize > v1 )
    v1 = CompressBufferWorkSpaceSize;
  P = (PVOID)PplCreateLookasideList(0, 0, v3, v1, 0x2532534Cu, v4, 0x2532534Cu);
  if ( !P )
  {
    CompressionWorkSpaceSize = -1073741670;
LABEL_15:
    SmbCompressionCleanup();
  }
  return (unsigned int)CompressionWorkSpaceSize;
}

```

## disassembly

```asm
0x140020a94  mov     [rsp-8+arg_10], rbx
0x140020a99  mov     [rsp-8+arg_18], rdi
0x140020a9e  push    rbp
0x140020a9f  mov     rbp, rsp
0x140020aa2  sub     rsp, 50h
0x140020aa6  mov     ecx, 2; CompressionFormatAndEngine
0x140020aab  mov     [rbp+CompressBufferWorkSpaceSize], 0
0x140020ab2  lea     r8, [rbp+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x140020ab6  mov     [rbp+CompressFragmentWorkSpaceSize], 0
0x140020abd  lea     rdx, [rbp+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x140020ac1  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x140020ac8  nop     dword ptr [rax+rax+00h]
0x140020acd  mov     ebx, eax
0x140020acf  test    eax, eax
0x140020ad1  js      loc_140020B85
0x140020ad7  mov     eax, [rbp+CompressBufferWorkSpaceSize]
0x140020ada  lea     r8, [rbp+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x140020ade  xor     edi, edi
0x140020ae0  lea     rdx, [rbp+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x140020ae4  test    eax, eax
0x140020ae6  mov     ecx, 3; CompressionFormatAndEngine
0x140020aeb  cmovnz  edi, eax
0x140020aee  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x140020af5  nop     dword ptr [rax+rax+00h]
0x140020afa  mov     ebx, eax
0x140020afc  test    eax, eax
0x140020afe  js      loc_140020B85
0x140020b04  cmp     [rbp+CompressBufferWorkSpaceSize], edi
0x140020b07  lea     r8, [rbp+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x140020b0b  mov     ecx, 4; CompressionFormatAndEngine
0x140020b10  lea     rdx, [rbp+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x140020b14  cmova   edi, [rbp+CompressBufferWorkSpaceSize]
0x140020b18  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x140020b1f  nop     dword ptr [rax+rax+00h]
0x140020b24  mov     ebx, eax
0x140020b26  test    eax, eax
0x140020b28  js      short loc_140020B85
0x140020b2a  cmp     [rbp+CompressBufferWorkSpaceSize], edi
0x140020b2d  lea     r8, [rbp+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x140020b31  mov     ecx, 6; CompressionFormatAndEngine
0x140020b36  lea     rdx, [rbp+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x140020b3a  cmova   edi, [rbp+CompressBufferWorkSpaceSize]
0x140020b3e  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x140020b45  nop     dword ptr [rax+rax+00h]
0x140020b4a  mov     ebx, eax
0x140020b4c  test    eax, eax
0x140020b4e  js      short loc_140020B85
0x140020b50  cmp     [rbp+CompressBufferWorkSpaceSize], edi
0x140020b53  mov     ecx, 2532534Ch
0x140020b58  mov     [rsp+50h+var_10], ecx; ULONG
0x140020b5c  cmova   edi, [rbp+CompressBufferWorkSpaceSize]
0x140020b60  xor     edx, edx; int
0x140020b62  mov     [rsp+50h+var_20], ecx; ULONG
0x140020b66  xor     ecx, ecx; int
0x140020b68  mov     eax, edi
0x140020b6a  mov     [rsp+50h+var_28], rax; SIZE_T
0x140020b6f  call    PplCreateLookasideList
0x140020b74  mov     cs:P, rax
0x140020b7b  test    rax, rax
0x140020b7e  jnz     short loc_140020B8A
0x140020b80  mov     ebx, 0C000009Ah
0x140020b85  call    SmbCompressionCleanup
0x140020b8a  mov     rdi, [rsp+50h+arg_18]
0x140020b8f  mov     eax, ebx
0x140020b91  mov     rbx, [rsp+50h+arg_10]
0x140020b96  add     rsp, 50h
0x140020b9a  pop     rbp
0x140020b9b  retn
```

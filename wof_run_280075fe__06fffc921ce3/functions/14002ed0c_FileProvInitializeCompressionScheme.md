# FileProvInitializeCompressionScheme

- ea: `0x14002ed0c`
- end: `0x14002ef02`
- name: `FileProvInitializeCompressionScheme`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002ef08`

## callees

- `0x14000cee8`
- `0x1400119c0`
- `0x14002ed0c`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002edf7`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002eea5`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002eed5`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002edf7`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002eea5`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002eed5`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14002eda3`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14002eda3`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002ee30`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002ee70`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002ee30`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002ee70`

## pseudocode

```c
__int64 __fastcall FileProvInitializeCompressionScheme(_DWORD *a1, int a2)
{
  int v4; // esi
  int v5; // r14d
  NTSTATUS CompressionWorkSpaceSize; // edi
  ULONG DecodeBufferSize; // ecx
  ULONG v8; // eax
  USHORT v9; // cx
  unsigned int v10; // eax
  ULONG CompressFragmentWorkSpaceSize; // [rsp+68h] [rbp+28h] BYREF
  ULONG CompressBufferWorkSpaceSize; // [rsp+70h] [rbp+30h] BYREF

  CompressFragmentWorkSpaceSize = 0;
  CompressBufferWorkSpaceSize = 0;
  memset(a1, 0, 0x340u);
  v4 = 0x8000;
  v5 = 4096;
  if ( a2 )
  {
    switch ( a2 )
    {
      case 1:
        CompressionWorkSpaceSize = 0;
        *a1 = 0x8000;
        DecodeBufferSize = LZX_GetDecodeBufferSize(0x8000);
        CompressFragmentWorkSpaceSize = DecodeBufferSize;
        v8 = 17352;
        CompressBufferWorkSpaceSize = 17352;
        goto LABEL_11;
      case 2:
        *a1 = 0x2000;
        break;
      case 3:
        *a1 = 0x4000;
        break;
      default:
        return (unsigned int)-1073741217;
    }
  }
  else
  {
    *a1 = 4096;
  }
  v9 = FileProvXPressAlgorithm;
  *((_BYTE *)a1 + 17) = 1;
  CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(
                               v9,
                               &CompressBufferWorkSpaceSize,
                               &CompressFragmentWorkSpaceSize);
  if ( CompressionWorkSpaceSize < 0 )
    return (unsigned int)CompressionWorkSpaceSize;
  DecodeBufferSize = CompressFragmentWorkSpaceSize;
  v8 = CompressBufferWorkSpaceSize;
LABEL_11:
  a1[2] = v8;
  v10 = *a1;
  a1[3] = DecodeBufferSize;
  if ( v10 > 0x1000 )
    v5 = v10;
  a1[1] = v5;
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 48), 0, 0, 0, DecodeBufferSize + v10, 0x77647066u, 0);
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)a1 + 4, 0, 0, 0x200u, 0x60u, 0x69777066u, 0);
  if ( *a1 > 0x8000u )
    v4 = *a1;
  a1[80] = v4;
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)a1 + 5, 0, 0, 0x200u, 0xE0u, 0x78637066u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)a1 + 3, 0, 0, 0, (unsigned int)a1[80], 0x64727066u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 16), 0, 0, 0, (unsigned int)(*a1 + a1[2]), 0x77637066u, 0);
  *((_BYTE *)a1 + 16) = 1;
  return (unsigned int)CompressionWorkSpaceSize;
}

```

## disassembly

```asm
0x14002ed0c  mov     [rsp-18h+arg_0], rbx
0x14002ed11  mov     [rsp-18h+arg_18], rsi
0x14002ed16  push    rbp
0x14002ed17  push    rdi
0x14002ed18  push    r14
0x14002ed1a  mov     rbp, rsp
0x14002ed1d  sub     rsp, 40h
0x14002ed21  mov     edi, edx
0x14002ed23  mov     [rbp+CompressFragmentWorkSpaceSize], 0
0x14002ed2a  xor     edx, edx; Val
0x14002ed2c  mov     [rbp+CompressBufferWorkSpaceSize], 0
0x14002ed33  mov     r8d, 340h; Size
0x14002ed39  mov     rbx, rcx
0x14002ed3c  call    memset
0x14002ed41  mov     esi, 8000h
0x14002ed46  mov     r14d, 1000h
0x14002ed4c  test    edi, edi
0x14002ed4e  jnz     short loc_14002ED55
0x14002ed50  mov     [rbx], r14d
0x14002ed53  jmp     short loc_14002ED90
0x14002ed55  cmp     edi, 1
0x14002ed58  jnz     short loc_14002ED74
0x14002ed5a  xor     edi, edi
0x14002ed5c  mov     [rbx], esi
0x14002ed5e  mov     ecx, esi
0x14002ed60  call    LZX_GetDecodeBufferSize
0x14002ed65  mov     ecx, eax
0x14002ed67  mov     [rbp+CompressFragmentWorkSpaceSize], eax
0x14002ed6a  mov     eax, 43C8h
0x14002ed6f  mov     [rbp+CompressBufferWorkSpaceSize], eax
0x14002ed72  jmp     short loc_14002EDBF
0x14002ed74  cmp     edi, 2
0x14002ed77  jnz     short loc_14002ED81
0x14002ed79  mov     dword ptr [rbx], 2000h
0x14002ed7f  jmp     short loc_14002ED90
0x14002ed81  cmp     edi, 3
0x14002ed84  jnz     loc_14002EEE7
0x14002ed8a  mov     dword ptr [rbx], 4000h
0x14002ed90  movzx   ecx, cs:FileProvXPressAlgorithm; CompressionFormatAndEngine
0x14002ed97  lea     r8, [rbp+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x14002ed9b  lea     rdx, [rbp+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x14002ed9f  mov     byte ptr [rbx+11h], 1
0x14002eda3  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x14002edaa  nop     dword ptr [rax+rax+00h]
0x14002edaf  mov     edi, eax
0x14002edb1  test    eax, eax
0x14002edb3  js      loc_14002EEEC
0x14002edb9  mov     ecx, [rbp+CompressFragmentWorkSpaceSize]
0x14002edbc  mov     eax, [rbp+CompressBufferWorkSpaceSize]
0x14002edbf  mov     [rbx+8], eax
0x14002edc2  mov     eax, [rbx]
0x14002edc4  cmp     eax, r14d
0x14002edc7  mov     [rbx+0Ch], ecx
0x14002edca  cmova   r14d, eax
0x14002edce  xor     edx, edx; Allocate
0x14002edd0  mov     [rsp+40h+Depth], dx; Depth
0x14002edd5  xor     r9d, r9d; Flags
0x14002edd8  lea     r8d, [rcx+rax]
0x14002eddc  mov     [rsp+40h+Tag], 77647066h; Tag
0x14002ede4  mov     [rsp+40h+Size], r8; Size
0x14002ede9  lea     rcx, [rbx+0C0h]; Lookaside
0x14002edf0  xor     r8d, r8d; Free
0x14002edf3  mov     [rbx+4], r14d
0x14002edf7  call    cs:__imp_ExInitializePagedLookasideList
0x14002edfe  nop     dword ptr [rax+rax+00h]
0x14002ee03  xor     eax, eax
0x14002ee05  lea     rcx, [rbx+200h]; Lookaside
0x14002ee0c  mov     [rsp+40h+Depth], ax; Depth
0x14002ee11  mov     r14d, 200h
0x14002ee17  mov     [rsp+40h+Tag], 69777066h; Tag
0x14002ee1f  mov     r9d, r14d; Flags
0x14002ee22  xor     r8d, r8d; Free
0x14002ee25  mov     [rsp+40h+Size], 60h ; '`'; Size
0x14002ee2e  xor     edx, edx; Allocate
0x14002ee30  call    cs:__imp_ExInitializeNPagedLookasideList
0x14002ee37  nop     dword ptr [rax+rax+00h]
0x14002ee3c  mov     eax, [rbx]
0x14002ee3e  lea     rcx, [rbx+280h]; Lookaside
0x14002ee45  cmp     eax, esi
0x14002ee47  mov     r9d, r14d; Flags
0x14002ee4a  cmova   esi, eax
0x14002ee4d  xor     eax, eax
0x14002ee4f  mov     [rsp+40h+Depth], ax; Depth
0x14002ee54  xor     r8d, r8d; Free
0x14002ee57  mov     [rsp+40h+Tag], 78637066h; Tag
0x14002ee5f  xor     edx, edx; Allocate
0x14002ee61  mov     [rsp+40h+Size], 0E0h; Size
0x14002ee6a  mov     [rbx+140h], esi
0x14002ee70  call    cs:__imp_ExInitializeNPagedLookasideList
0x14002ee77  nop     dword ptr [rax+rax+00h]
0x14002ee7c  mov     edx, [rbx+140h]
0x14002ee82  lea     rcx, [rbx+180h]; Lookaside
0x14002ee89  xor     eax, eax
0x14002ee8b  xor     r9d, r9d; Flags
0x14002ee8e  mov     [rsp+40h+Depth], ax; Depth
0x14002ee93  xor     r8d, r8d; Free
0x14002ee96  mov     [rsp+40h+Tag], 64727066h; Tag
0x14002ee9e  mov     [rsp+40h+Size], rdx; Size
0x14002eea3  xor     edx, edx; Allocate
0x14002eea5  call    cs:__imp_ExInitializePagedLookasideList
0x14002eeac  nop     dword ptr [rax+rax+00h]
0x14002eeb1  mov     edx, [rbx+8]
0x14002eeb4  lea     rcx, [rbx+40h]; Lookaside
0x14002eeb8  add     edx, [rbx]
0x14002eeba  xor     r8d, r8d; Free
0x14002eebd  mov     [rsp+40h+Depth], r8w; Depth
0x14002eec3  xor     r9d, r9d; Flags
0x14002eec6  mov     [rsp+40h+Tag], 77637066h; Tag
0x14002eece  mov     [rsp+40h+Size], rdx; Size
0x14002eed3  xor     edx, edx; Allocate
0x14002eed5  call    cs:__imp_ExInitializePagedLookasideList
0x14002eedc  nop     dword ptr [rax+rax+00h]
0x14002eee1  mov     byte ptr [rbx+10h], 1
0x14002eee5  jmp     short loc_14002EEEC
0x14002eee7  mov     edi, 0C000025Fh
0x14002eeec  mov     rbx, [rsp+40h+arg_0]
0x14002eef1  mov     eax, edi
0x14002eef3  mov     rsi, [rsp+40h+arg_18]
0x14002eef8  add     rsp, 40h
0x14002eefc  pop     r14
0x14002eefe  pop     rdi
0x14002eeff  pop     rbp
0x14002ef00  retn
```

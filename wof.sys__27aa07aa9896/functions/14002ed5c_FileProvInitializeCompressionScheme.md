# FileProvInitializeCompressionScheme

- ea: `0x14002ed5c`
- end: `0x14002ef52`
- name: `FileProvInitializeCompressionScheme`
- size: `502`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002ef58`

## callees

- `0x14000cee8`
- `0x1400119c0`
- `0x14002ed5c`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002ee47`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002eef5`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002ef25`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002ee47`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002eef5`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002ef25`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14002edf3`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14002edf3`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002ee80`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002eec0`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002ee80`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002eec0`

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
0x14002ed5c  mov     [rsp-18h+arg_0], rbx
0x14002ed61  mov     [rsp-18h+arg_18], rsi
0x14002ed66  push    rbp
0x14002ed67  push    rdi
0x14002ed68  push    r14
0x14002ed6a  mov     rbp, rsp
0x14002ed6d  sub     rsp, 40h
0x14002ed71  mov     edi, edx
0x14002ed73  mov     [rbp+CompressFragmentWorkSpaceSize], 0
0x14002ed7a  xor     edx, edx; Val
0x14002ed7c  mov     [rbp+CompressBufferWorkSpaceSize], 0
0x14002ed83  mov     r8d, 340h; Size
0x14002ed89  mov     rbx, rcx
0x14002ed8c  call    memset
0x14002ed91  mov     esi, 8000h
0x14002ed96  mov     r14d, 1000h
0x14002ed9c  test    edi, edi
0x14002ed9e  jnz     short loc_14002EDA5
0x14002eda0  mov     [rbx], r14d
0x14002eda3  jmp     short loc_14002EDE0
0x14002eda5  cmp     edi, 1
0x14002eda8  jnz     short loc_14002EDC4
0x14002edaa  xor     edi, edi
0x14002edac  mov     [rbx], esi
0x14002edae  mov     ecx, esi
0x14002edb0  call    LZX_GetDecodeBufferSize
0x14002edb5  mov     ecx, eax
0x14002edb7  mov     [rbp+CompressFragmentWorkSpaceSize], eax
0x14002edba  mov     eax, 43C8h
0x14002edbf  mov     [rbp+CompressBufferWorkSpaceSize], eax
0x14002edc2  jmp     short loc_14002EE0F
0x14002edc4  cmp     edi, 2
0x14002edc7  jnz     short loc_14002EDD1
0x14002edc9  mov     dword ptr [rbx], 2000h
0x14002edcf  jmp     short loc_14002EDE0
0x14002edd1  cmp     edi, 3
0x14002edd4  jnz     loc_14002EF37
0x14002edda  mov     dword ptr [rbx], 4000h
0x14002ede0  movzx   ecx, cs:FileProvXPressAlgorithm; CompressionFormatAndEngine
0x14002ede7  lea     r8, [rbp+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x14002edeb  lea     rdx, [rbp+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x14002edef  mov     byte ptr [rbx+11h], 1
0x14002edf3  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x14002edfa  nop     dword ptr [rax+rax+00h]
0x14002edff  mov     edi, eax
0x14002ee01  test    eax, eax
0x14002ee03  js      loc_14002EF3C
0x14002ee09  mov     ecx, [rbp+CompressFragmentWorkSpaceSize]
0x14002ee0c  mov     eax, [rbp+CompressBufferWorkSpaceSize]
0x14002ee0f  mov     [rbx+8], eax
0x14002ee12  mov     eax, [rbx]
0x14002ee14  cmp     eax, r14d
0x14002ee17  mov     [rbx+0Ch], ecx
0x14002ee1a  cmova   r14d, eax
0x14002ee1e  xor     edx, edx; Allocate
0x14002ee20  mov     [rsp+40h+Depth], dx; Depth
0x14002ee25  xor     r9d, r9d; Flags
0x14002ee28  lea     r8d, [rcx+rax]
0x14002ee2c  mov     [rsp+40h+Tag], 77647066h; Tag
0x14002ee34  mov     [rsp+40h+Size], r8; Size
0x14002ee39  lea     rcx, [rbx+0C0h]; Lookaside
0x14002ee40  xor     r8d, r8d; Free
0x14002ee43  mov     [rbx+4], r14d
0x14002ee47  call    cs:__imp_ExInitializePagedLookasideList
0x14002ee4e  nop     dword ptr [rax+rax+00h]
0x14002ee53  xor     eax, eax
0x14002ee55  lea     rcx, [rbx+200h]; Lookaside
0x14002ee5c  mov     [rsp+40h+Depth], ax; Depth
0x14002ee61  mov     r14d, 200h
0x14002ee67  mov     [rsp+40h+Tag], 69777066h; Tag
0x14002ee6f  mov     r9d, r14d; Flags
0x14002ee72  xor     r8d, r8d; Free
0x14002ee75  mov     [rsp+40h+Size], 60h ; '`'; Size
0x14002ee7e  xor     edx, edx; Allocate
0x14002ee80  call    cs:__imp_ExInitializeNPagedLookasideList
0x14002ee87  nop     dword ptr [rax+rax+00h]
0x14002ee8c  mov     eax, [rbx]
0x14002ee8e  lea     rcx, [rbx+280h]; Lookaside
0x14002ee95  cmp     eax, esi
0x14002ee97  mov     r9d, r14d; Flags
0x14002ee9a  cmova   esi, eax
0x14002ee9d  xor     eax, eax
0x14002ee9f  mov     [rsp+40h+Depth], ax; Depth
0x14002eea4  xor     r8d, r8d; Free
0x14002eea7  mov     [rsp+40h+Tag], 78637066h; Tag
0x14002eeaf  xor     edx, edx; Allocate
0x14002eeb1  mov     [rsp+40h+Size], 0E0h; Size
0x14002eeba  mov     [rbx+140h], esi
0x14002eec0  call    cs:__imp_ExInitializeNPagedLookasideList
0x14002eec7  nop     dword ptr [rax+rax+00h]
0x14002eecc  mov     edx, [rbx+140h]
0x14002eed2  lea     rcx, [rbx+180h]; Lookaside
0x14002eed9  xor     eax, eax
0x14002eedb  xor     r9d, r9d; Flags
0x14002eede  mov     [rsp+40h+Depth], ax; Depth
0x14002eee3  xor     r8d, r8d; Free
0x14002eee6  mov     [rsp+40h+Tag], 64727066h; Tag
0x14002eeee  mov     [rsp+40h+Size], rdx; Size
0x14002eef3  xor     edx, edx; Allocate
0x14002eef5  call    cs:__imp_ExInitializePagedLookasideList
0x14002eefc  nop     dword ptr [rax+rax+00h]
0x14002ef01  mov     edx, [rbx+8]
0x14002ef04  lea     rcx, [rbx+40h]; Lookaside
0x14002ef08  add     edx, [rbx]
0x14002ef0a  xor     r8d, r8d; Free
0x14002ef0d  mov     [rsp+40h+Depth], r8w; Depth
0x14002ef13  xor     r9d, r9d; Flags
0x14002ef16  mov     [rsp+40h+Tag], 77637066h; Tag
0x14002ef1e  mov     [rsp+40h+Size], rdx; Size
0x14002ef23  xor     edx, edx; Allocate
0x14002ef25  call    cs:__imp_ExInitializePagedLookasideList
0x14002ef2c  nop     dword ptr [rax+rax+00h]
0x14002ef31  mov     byte ptr [rbx+10h], 1
0x14002ef35  jmp     short loc_14002EF3C
0x14002ef37  mov     edi, 0C000025Fh
0x14002ef3c  mov     rbx, [rsp+40h+arg_0]
0x14002ef41  mov     eax, edi
0x14002ef43  mov     rsi, [rsp+40h+arg_18]
0x14002ef48  add     rsp, 40h
0x14002ef4c  pop     r14
0x14002ef4e  pop     rdi
0x14002ef4f  pop     rbp
0x14002ef50  retn
```

# UdfMapViewOfDirectory

- ea: `0x140055f00`
- end: `0x140056038`
- name: `UdfMapViewOfDirectory`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140004514`
- `0x140012308`
- `0x1400425b0`

## callees

- `0x14000b938`
- `0x140055f00`

## import_xrefs

- `ntoskrnl!CcMapData` at `0x140055fa9`
- `ntoskrnl!CcMapData` at `0x140055fa9`
- `ntoskrnl!CcUnpinData` at `0x140055f6e`
- `ntoskrnl!CcUnpinData` at `0x140055f6e`
- `ntoskrnl!ExRaiseStatus` at `0x140056017`
- `ntoskrnl!ExRaiseStatus` at `0x140056017`
- `ntoskrnl!CcPinRead` at `0x140056024`
- `ntoskrnl!CcPinRead` at `0x140056024`

## pseudocode

```c
__int64 __fastcall UdfMapViewOfDirectory(__int64 a1, __int64 a2, __int64 a3)
{
  ULONG *v3; // rsi
  bool v4; // zf
  union _LARGE_INTEGER v8; // r8
  LONGLONG v9; // rdx
  void *v10; // rcx
  ULONG v11; // r8d
  struct _FILE_OBJECT *v12; // rcx
  unsigned int v13; // eax
  __int64 result; // rax
  PVOID *Bcb; // [rsp+20h] [rbp-28h]
  union _LARGE_INTEGER FileOffset; // [rsp+58h] [rbp+10h] BYREF

  v3 = (ULONG *)(a3 + 24);
  v4 = (*(_DWORD *)(a2 + 212) & 0x8000000) == 0;
  FileOffset.QuadPart = 0;
  if ( v4 )
  {
    v8 = *(union _LARGE_INTEGER *)(a3 + 16);
    *v3 = 4096;
    v9 = *(_QWORD *)(a2 + 32);
    if ( v8.QuadPart + 4096 > v9 )
      *v3 = v9 - v8.LowPart;
    FileOffset = v8;
  }
  else
  {
    UdfFindDataInMetadataStream(a1, a2, a3 + 16, &FileOffset, a3 + 24);
    if ( FileOffset.QuadPart + *v3 > *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 320LL) + 24LL) )
    {
      *(_DWORD *)(a1 + 24) = -1073741566;
      ExRaiseStatus(-1073741566);
    }
  }
  v10 = *(void **)(a3 + 8);
  if ( v10 )
  {
    CcUnpinData(v10);
    *(_QWORD *)(a3 + 8) = 0;
  }
  v11 = *v3;
  v12 = *(struct _FILE_OBJECT **)(a2 + 504);
  Bcb = (PVOID *)(a3 + 8);
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL) & 0x4000) != 0 )
  {
    CcMapData(v12, &FileOffset, v11, 1u, Bcb, (PVOID *)a3);
    v13 = *(_DWORD *)(a3 + 56) & 0xFFFFFFEF;
  }
  else
  {
    CcPinRead(v12, &FileOffset, v11, 1u, Bcb, (PVOID *)a3);
    v13 = *(_DWORD *)(a3 + 56) | 0x10;
  }
  result = v13 & 0xFFFFFFDF;
  *(_DWORD *)(a3 + 56) = result;
  return result;
}

```

## disassembly

```asm
0x140055f00  mov     [rsp+arg_10], rbx
0x140055f05  mov     [rsp+arg_18], rbp
0x140055f0a  push    rsi
0x140055f0b  push    r14
0x140055f0d  push    r15
0x140055f0f  sub     rsp, 30h
0x140055f13  xor     r15d, r15d
0x140055f16  lea     rsi, [r8+18h]
0x140055f1a  test    dword ptr [rdx+0D4h], 8000000h
0x140055f24  mov     rbx, r8
0x140055f27  mov     rbp, rdx
0x140055f2a  mov     qword ptr [rsp+48h+FileOffset], r15
0x140055f2f  mov     r14, rcx
0x140055f32  jnz     loc_140055FDB
0x140055f38  mov     r8, [r8+10h]
0x140055f3c  mov     dword ptr [rsi], 1000h
0x140055f42  mov     rdx, [rdx+20h]
0x140055f46  lea     rax, [r8+1000h]
0x140055f4d  cmp     rax, rdx
0x140055f50  jle     short loc_140055F57
0x140055f52  sub     edx, r8d
0x140055f55  mov     [rsi], edx
0x140055f57  mov     qword ptr [rsp+48h+FileOffset], r8
0x140055f5c  mov     rcx, [rbx+8]; Bcb
0x140055f60  mov     [rsp+48h+arg_0], rdi
0x140055f65  lea     rdi, [rbx+8]
0x140055f69  test    rcx, rcx
0x140055f6c  jz      short loc_140055F7D
0x140055f6e  call    cs:__imp_CcUnpinData
0x140055f75  nop     dword ptr [rax+rax+00h]
0x140055f7a  mov     [rdi], r15
0x140055f7d  mov     rax, [r14+10h]
0x140055f81  lea     rdx, [rsp+48h+FileOffset]; FileOffset
0x140055f86  mov     r8d, [rsi]; Length
0x140055f89  mov     r9d, 1; Flags
0x140055f8f  mov     rcx, [rbp+1F8h]; FileObject
0x140055f96  mov     [rsp+48h+Buffer], rbx; Buffer
0x140055f9b  test    dword ptr [rax+30h], 4000h
0x140055fa2  mov     [rsp+48h+Bcb], rdi; Bcb
0x140055fa7  jz      short loc_140056024
0x140055fa9  call    cs:__imp_CcMapData
0x140055fb0  nop     dword ptr [rax+rax+00h]
0x140055fb5  mov     eax, [rbx+38h]
0x140055fb8  and     eax, 0FFFFFFEFh
0x140055fbb  mov     rdi, [rsp+48h+arg_0]
0x140055fc0  and     eax, 0FFFFFFDFh
0x140055fc3  mov     rbp, [rsp+48h+arg_18]
0x140055fc8  mov     [rbx+38h], eax
0x140055fcb  mov     rbx, [rsp+48h+arg_10]
0x140055fd0  add     rsp, 30h
0x140055fd4  pop     r15
0x140055fd6  pop     r14
0x140055fd8  pop     rsi
0x140055fd9  retn
0x140055fdb  lea     r9, [rsp+48h+FileOffset]
0x140055fe0  mov     [rsp+48h+Bcb], rsi
0x140055fe5  add     r8, 10h
0x140055fe9  call    UdfFindDataInMetadataStream
0x140055fee  mov     rax, [r14+10h]
0x140055ff2  mov     edx, [rsi]
0x140055ff4  add     rdx, qword ptr [rsp+48h+FileOffset]
0x140055ff9  mov     rcx, [rax+140h]
0x140056000  cmp     rdx, [rcx+18h]
0x140056004  jle     loc_140055F5C
0x14005600a  mov     ecx, 0C0000102h; Status
0x14005600f  mov     dword ptr [r14+18h], 0C0000102h
0x140056017  call    cs:__imp_ExRaiseStatus
0x140056024  call    cs:__imp_CcPinRead
0x14005602b  nop     dword ptr [rax+rax+00h]
0x140056030  mov     eax, [rbx+38h]
0x140056033  or      eax, 10h
0x140056036  jmp     short loc_140055FBB
```

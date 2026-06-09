# VidExoVppDelete

- ea: `0x140084b44`
- end: `0x140084c72`
- name: `VidExoVppDelete`
- size: `302`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140084460`
- `0x14008476c`
- `0x140084884`

## callees

- `0x140013084`
- `0x140084b44`
- `0x1400ed1f0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140084c41`
- `ntoskrnl!ObfDereferenceObject` at `0x140084c41`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084c55`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084c55`
- `winhvr!WinHvDeleteVp` at `0x140084c2c`
- `winhvr!WinHvDeleteVp` at `0x140084c2c`
- `winhvr!WinHvUnmapStatsPage` at `0x140084bd3`
- `winhvr!WinHvUnmapStatsPage` at `0x140084bf0`
- `winhvr!WinHvUnmapStatsPage` at `0x140084bd3`
- `winhvr!WinHvUnmapStatsPage` at `0x140084bf0`

## pseudocode

```c
void __fastcall VidExoVppDelete(__int64 a1, unsigned int *a2, char a3)
{
  int v6; // edx
  __int64 v7; // rcx
  void *v8; // rcx

  VidClientBufferUninitialize(a2 + 26);
  VidClientBufferUninitialize(a2 + 44);
  VidExoVppUnmapStatePage(a1, *a2, (_DWORD)a2 + 248, 0);
  v6 = *a2;
  *((_QWORD *)a2 + 40) = 0;
  VidExoVppUnmapStatePage(a1, v6, (_DWORD)a2 + 328, 1);
  v7 = *((_QWORD *)a2 + 10);
  *((_QWORD *)a2 + 50) = 0;
  if ( v7 )
  {
    WinHvUnmapStatsPage();
    *((_QWORD *)a2 + 10) = 0;
  }
  if ( *((_QWORD *)a2 + 11) )
  {
    WinHvUnmapStatsPage();
    *((_QWORD *)a2 + 11) = 0;
  }
  if ( *((_BYTE *)a2 + 408) && (!a3 || (*((_DWORD *)VidDeviceExtension + 162) & 0x20) != 0) )
    WinHvDeleteVp(*(_QWORD *)(a1 + 648), *a2);
  v8 = (void *)*((_QWORD *)a2 + 9);
  if ( v8 )
    ObfDereferenceObject(v8);
  ExFreePoolWithTag(a2, 0x72446456u);
}

```

## disassembly

```asm
0x140084b44  mov     [rsp+arg_0], rbx
0x140084b49  mov     [rsp+arg_8], rsi
0x140084b4e  push    rdi
0x140084b4f  sub     rsp, 30h
0x140084b53  mov     rdi, rcx
0x140084b56  mov     sil, r8b
0x140084b59  lea     rcx, [rdx+68h]
0x140084b5d  mov     rbx, rdx
0x140084b60  call    VidClientBufferUninitialize
0x140084b65  lea     rcx, [rbx+0B0h]
0x140084b6c  call    VidClientBufferUninitialize
0x140084b71  mov     rax, [rbx+140h]
0x140084b78  lea     r8, [rbx+0F8h]
0x140084b7f  mov     edx, [rbx]
0x140084b81  xor     r9d, r9d
0x140084b84  mov     rcx, rdi
0x140084b87  mov     [rsp+38h+var_10], rax
0x140084b8c  call    VidExoVppUnmapStatePage
0x140084b91  mov     rax, [rbx+190h]
0x140084b98  lea     r8, [rbx+148h]
0x140084b9f  mov     edx, [rbx]
0x140084ba1  mov     r9d, 1
0x140084ba7  mov     rcx, rdi
0x140084baa  mov     [rsp+38h+var_10], rax
0x140084baf  mov     qword ptr [rbx+140h], 0
0x140084bba  call    VidExoVppUnmapStatePage
0x140084bbf  mov     rcx, [rbx+50h]
0x140084bc3  mov     qword ptr [rbx+190h], 0
0x140084bce  test    rcx, rcx
0x140084bd1  jz      short loc_140084BE7
0x140084bd3  call    cs:__imp_WinHvUnmapStatsPage
0x140084bda  nop     dword ptr [rax+rax+00h]
0x140084bdf  mov     qword ptr [rbx+50h], 0
0x140084be7  mov     rcx, [rbx+58h]
0x140084beb  test    rcx, rcx
0x140084bee  jz      short loc_140084C04
0x140084bf0  call    cs:__imp_WinHvUnmapStatsPage
0x140084bf7  nop     dword ptr [rax+rax+00h]
0x140084bfc  mov     qword ptr [rbx+58h], 0
0x140084c04  cmp     byte ptr [rbx+198h], 0
0x140084c0b  jz      short loc_140084C38
0x140084c0d  test    sil, sil
0x140084c10  jz      short loc_140084C23
0x140084c12  mov     rax, cs:VidDeviceExtension
0x140084c19  mov     eax, [rax+288h]
0x140084c1f  test    al, 20h
0x140084c21  jz      short loc_140084C38
0x140084c23  mov     edx, [rbx]
0x140084c25  mov     rcx, [rdi+288h]
0x140084c2c  call    cs:__imp_WinHvDeleteVp
0x140084c33  nop     dword ptr [rax+rax+00h]
0x140084c38  mov     rcx, [rbx+48h]; Object
0x140084c3c  test    rcx, rcx
0x140084c3f  jz      short loc_140084C4D
0x140084c41  call    cs:__imp_ObfDereferenceObject
0x140084c48  nop     dword ptr [rax+rax+00h]
0x140084c4d  mov     edx, 72446456h; Tag
0x140084c52  mov     rcx, rbx; P
0x140084c55  call    cs:__imp_ExFreePoolWithTag
0x140084c5c  nop     dword ptr [rax+rax+00h]
0x140084c61  mov     rbx, [rsp+38h+arg_0]
0x140084c66  mov     rsi, [rsp+38h+arg_8]
0x140084c6b  add     rsp, 30h
0x140084c6f  pop     rdi
0x140084c70  retn
```

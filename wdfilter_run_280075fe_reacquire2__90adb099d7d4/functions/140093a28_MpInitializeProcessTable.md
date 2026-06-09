# MpInitializeProcessTable

- ea: `0x140093a28`
- end: `0x140093bf5`
- name: `MpInitializeProcessTable`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14008f314`

## callees

- `0x1400026c0`
- `0x1400051bc`
- `0x140093a28`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x140093aaf`
- `ntoskrnl!ExInitializeResourceLite` at `0x140093aaf`
- `ntoskrnl!KeInitializeEvent` at `0x140093bdb`
- `ntoskrnl!KeInitializeEvent` at `0x140093bdb`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140093ae4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140093b1c`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140093ae4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140093b1c`

## pseudocode

```c
__int64 MpInitializeProcessTable()
{
  _DWORD *PoolWithTag; // rax
  unsigned int v1; // ebx
  __int64 v3; // rax
  _QWORD *v4; // r9
  __int64 v5; // rdx
  __int64 v6; // r8
  _QWORD *v7; // rcx
  char *v8; // rcx

  PoolWithTag = (_DWORD *)MpAllocatePoolWithTag((unsigned int)ExDefaultNonPagedPoolType, 448, 1416646733);
  v1 = 0;
  MpProcessTable = PoolWithTag;
  if ( PoolWithTag )
  {
    *PoolWithTag = 29415955;
    ExInitializeResourceLite((PERESOURCE)(PoolWithTag + 2));
    ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpProcessTable + 1, 0, 0, 0, 0x130u, 0x5870504Du, 0);
    ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpProcessTable + 2, 0, 0, 0, 0x18u, 0x6570504Du, 0);
    v3 = MpAllocatePoolWithTag(1, 2048, 1416646733);
    v4 = MpProcessTable;
    *((_QWORD *)MpProcessTable + 48) = v3;
    if ( v3 )
    {
      v5 = 0;
      v6 = 128;
      do
      {
        v7 = (_QWORD *)(v5 + v4[48]);
        v5 += 16;
        v7[1] = v7;
        *v7 = v7;
        --v6;
      }
      while ( v6 );
      v8 = (char *)MpProcessTable;
      *((_DWORD *)MpProcessTable + 104) = 0;
      KeInitializeEvent((PRKEVENT)(v8 + 392), NotificationEvent, 1u);
    }
    else
    {
      v1 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids,
          KeGetCurrentThread(),
          -1073741670);
    }
    return v1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids,
        KeGetCurrentThread(),
        -1073741670);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140093a28  mov     [rsp+arg_0], rbx
0x140093a2d  push    rsi
0x140093a2e  sub     rsp, 40h
0x140093a32  mov     ecx, cs:ExDefaultNonPagedPoolType
0x140093a38  mov     edx, 1C0h
0x140093a3d  mov     r8d, 5470504Dh
0x140093a43  call    MpAllocatePoolWithTag
0x140093a48  xor     ebx, ebx
0x140093a4a  mov     cs:MpProcessTable, rax
0x140093a51  test    rax, rax
0x140093a54  jnz     short loc_140093AA5
0x140093a56  mov     rcx, cs:WPP_GLOBAL_Control
0x140093a5d  lea     rax, WPP_GLOBAL_Control
0x140093a64  cmp     rcx, rax
0x140093a67  jz      short loc_140093A9B
0x140093a69  mov     eax, [rcx+2Ch]
0x140093a6c  test    al, 1
0x140093a6e  jz      short loc_140093A9B
0x140093a70  mov     r9, gs:188h
0x140093a79  lea     edx, [rbx+0Ah]
0x140093a7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140093a83  lea     r8, WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids
0x140093a8a  mov     dword ptr [rsp+48h+Size], 0C000009Ah
0x140093a92  mov     rcx, [rcx+18h]
0x140093a96  call    WPP_SF_qD
0x140093a9b  mov     eax, 0C000009Ah
0x140093aa0  jmp     loc_140093BE9
0x140093aa5  lea     rcx, [rax+8]; Resource
0x140093aa9  mov     dword ptr [rax], 1C0DA13h
0x140093aaf  call    cs:__imp_ExInitializeResourceLite
0x140093ab6  nop     dword ptr [rax+rax+00h]
0x140093abb  mov     rcx, cs:MpProcessTable
0x140093ac2  xor     r9d, r9d; Flags
0x140093ac5  mov     [rsp+48h+Depth], bx; Depth
0x140093aca  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x140093ace  mov     [rsp+48h+Tag], 5870504Dh; Tag
0x140093ad6  xor     r8d, r8d; Free
0x140093ad9  xor     edx, edx; Allocate
0x140093adb  mov     [rsp+48h+Size], 130h; Size
0x140093ae4  call    cs:__imp_ExInitializePagedLookasideList
0x140093aeb  nop     dword ptr [rax+rax+00h]
0x140093af0  mov     rcx, cs:MpProcessTable
0x140093af7  xor     r9d, r9d; Flags
0x140093afa  mov     [rsp+48h+Depth], bx; Depth
0x140093aff  add     rcx, 100h; Lookaside
0x140093b06  mov     [rsp+48h+Tag], 6570504Dh; Tag
0x140093b0e  xor     r8d, r8d; Free
0x140093b11  xor     edx, edx; Allocate
0x140093b13  mov     [rsp+48h+Size], 18h; Size
0x140093b1c  call    cs:__imp_ExInitializePagedLookasideList
0x140093b23  nop     dword ptr [rax+rax+00h]
0x140093b28  mov     edx, 800h
0x140093b2d  mov     ecx, 1
0x140093b32  mov     r8d, 5470504Dh
0x140093b38  call    MpAllocatePoolWithTag
0x140093b3d  mov     r9, cs:MpProcessTable
0x140093b44  mov     [r9+180h], rax
0x140093b4b  test    rax, rax
0x140093b4e  jnz     short loc_140093B9E
0x140093b50  mov     ebx, 0C000009Ah
0x140093b55  mov     rcx, cs:WPP_GLOBAL_Control
0x140093b5c  lea     rax, WPP_GLOBAL_Control
0x140093b63  cmp     rcx, rax
0x140093b66  jz      short loc_140093BE7
0x140093b68  mov     eax, [rcx+2Ch]
0x140093b6b  test    al, 1
0x140093b6d  jz      short loc_140093BE7
0x140093b6f  mov     r9, gs:188h
0x140093b78  lea     r8, WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids
0x140093b7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140093b86  mov     edx, 0Bh
0x140093b8b  mov     dword ptr [rsp+48h+Size], 0C000009Ah
0x140093b93  mov     rcx, [rcx+18h]
0x140093b97  call    WPP_SF_qD
0x140093b9c  jmp     short loc_140093BE7
0x140093b9e  mov     rdx, rbx
0x140093ba1  mov     r8d, 80h
0x140093ba7  mov     rcx, [r9+180h]
0x140093bae  add     rcx, rdx
0x140093bb1  add     rdx, 10h
0x140093bb5  mov     [rcx+8], rcx
0x140093bb9  mov     [rcx], rcx
0x140093bbc  sub     r8, 1
0x140093bc0  jnz     short loc_140093BA7
0x140093bc2  mov     rcx, cs:MpProcessTable
0x140093bc9  mov     r8b, 1; State
0x140093bcc  xor     edx, edx; Type
0x140093bce  mov     [rcx+1A0h], ebx
0x140093bd4  add     rcx, 188h; Event
0x140093bdb  call    cs:__imp_KeInitializeEvent
0x140093be2  nop     dword ptr [rax+rax+00h]
0x140093be7  mov     eax, ebx
0x140093be9  mov     rbx, [rsp+48h+arg_0]
0x140093bee  add     rsp, 40h
0x140093bf2  pop     rsi
0x140093bf3  retn
```

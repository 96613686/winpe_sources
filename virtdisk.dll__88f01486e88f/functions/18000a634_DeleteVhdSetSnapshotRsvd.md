# DeleteVhdSetSnapshotRsvd

- ea: `0x18000a634`
- end: `0x18000a763`
- name: `DeleteVhdSetSnapshotRsvd`
- size: `303`
- prototype: `__int64 __fastcall(HANDLE hFile, __int128 *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000648c`

## callees

- `0x180004110`
- `0x18000a634`
- `0x18000b00c`
- `0x18000b5a4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000a701`
- `ntdll!RtlNtStatusToDosError` at `0x18000a701`
- `ntdll!RtlFreeHeap` at `0x18000a721`
- `ntdll!RtlFreeHeap` at `0x18000a721`
- `ntdll!RtlAllocateHeap` at `0x18000a68f`
- `ntdll!RtlAllocateHeap` at `0x18000a68f`

## pseudocode

```c
__int64 __fastcall DeleteVhdSetSnapshotRsvd(HANDLE hFile, __int128 *a2, __int64 a3)
{
  _DWORD *Heap; // rax
  int v6; // edx
  int v7; // r8d
  _DWORD *v8; // rdi
  DWORD v9; // ebx
  __int128 v10; // xmm0
  NTSTATUS v11; // ecx
  DWORD NumberOfBytesTransferred; // [rsp+80h] [rbp+18h] BYREF

  NumberOfBytesTransferred = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF__guid_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a2);
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x28u);
  v8 = Heap;
  if ( Heap )
  {
    *Heap = 33562630;
    *((_BYTE *)Heap + 32) = 0;
    v10 = *a2;
    Heap[9] = 1;
    *((_OWORD *)Heap + 1) = v10;
    v9 = IssueSynchronousDeviceIoControl(hFile, 0x90304u, Heap, 0x28u, Heap, 0x28u, &NumberOfBytesTransferred);
    if ( !v9 )
    {
      v11 = v8[1];
      if ( v11 < 0 )
        v9 = RtlNtStatusToDosError(v11);
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  }
  else
  {
    v9 = 14;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_D_guid_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, v9, (__int64)a2);
  }
  return v9;
}

```

## disassembly

```asm
0x18000a634  mov     rax, rsp
0x18000a637  mov     [rax+18h], r8b
0x18000a63b  push    rbx
0x18000a63c  push    rsi
0x18000a63d  push    rdi
0x18000a63e  push    r14
0x18000a640  sub     rsp, 48h
0x18000a644  mov     rsi, rdx
0x18000a647  mov     dword ptr [rax+18h], 0
0x18000a64e  mov     rbx, rcx
0x18000a651  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a658  lea     r14, WPP_GLOBAL_Control
0x18000a65f  cmp     rcx, r14
0x18000a662  jz      short loc_18000A67C
0x18000a664  test    byte ptr [rcx+1Ch], 20h
0x18000a668  jz      short loc_18000A67C
0x18000a66a  cmp     byte ptr [rcx+19h], 4
0x18000a66e  jb      short loc_18000A67C
0x18000a670  mov     rcx, [rcx+10h]
0x18000a674  mov     r9, rdx
0x18000a677  call    WPP_SF__guid_dd
0x18000a67c  mov     rcx, gs:60h
0x18000a685  xor     edx, edx; Flags
0x18000a687  mov     rcx, [rcx+30h]; HeapHandle
0x18000a68b  lea     r8d, [rdx+28h]; Size
0x18000a68f  call    cs:__imp_RtlAllocateHeap
0x18000a696  nop     dword ptr [rax+rax+00h]
0x18000a69b  mov     rdi, rax
0x18000a69e  test    rax, rax
0x18000a6a1  jnz     short loc_18000A6AB
0x18000a6a3  lea     ebx, [rax+0Eh]
0x18000a6a6  jmp     loc_18000A72D
0x18000a6ab  mov     dword ptr [rax], 2002006h
0x18000a6b1  mov     r9d, 28h ; '('; nInBufferSize
0x18000a6b7  mov     byte ptr [rax+20h], 0
0x18000a6bb  mov     r8, rdi; lpInBuffer
0x18000a6be  movups  xmm0, xmmword ptr [rsi]
0x18000a6c1  mov     dword ptr [rax+24h], 1
0x18000a6c8  mov     edx, 90304h; dwIoControlCode
0x18000a6cd  mov     rcx, rbx; hFile
0x18000a6d0  movdqu  xmmword ptr [rax+10h], xmm0
0x18000a6d5  lea     rax, [rsp+68h+NumberOfBytesTransferred]
0x18000a6dd  mov     [rsp+68h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x18000a6e2  mov     [rsp+68h+var_40], 28h ; '('; DWORD
0x18000a6ea  mov     [rsp+68h+var_48], rdi; LPVOID
0x18000a6ef  call    IssueSynchronousDeviceIoControl
0x18000a6f4  mov     ebx, eax
0x18000a6f6  test    eax, eax
0x18000a6f8  jnz     short loc_18000A70F
0x18000a6fa  mov     ecx, [rdi+4]; Status
0x18000a6fd  test    ecx, ecx
0x18000a6ff  jns     short loc_18000A70F
0x18000a701  call    cs:__imp_RtlNtStatusToDosError
0x18000a708  nop     dword ptr [rax+rax+00h]
0x18000a70d  mov     ebx, eax
0x18000a70f  mov     rcx, gs:60h
0x18000a718  mov     r8, rdi; P
0x18000a71b  xor     edx, edx; Flags
0x18000a71d  mov     rcx, [rcx+30h]; HeapHandle
0x18000a721  call    cs:__imp_RtlFreeHeap
0x18000a728  nop     dword ptr [rax+rax+00h]
0x18000a72d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a734  cmp     rcx, r14
0x18000a737  jz      short loc_18000A756
0x18000a739  test    byte ptr [rcx+1Ch], 20h
0x18000a73d  jz      short loc_18000A756
0x18000a73f  cmp     byte ptr [rcx+19h], 4
0x18000a743  jb      short loc_18000A756
0x18000a745  mov     rcx, [rcx+10h]
0x18000a749  mov     r9d, ebx
0x18000a74c  mov     [rsp+68h+var_48], rsi
0x18000a751  call    WPP_SF_D_guid_dd
0x18000a756  mov     eax, ebx
0x18000a758  add     rsp, 48h
0x18000a75c  pop     r14
0x18000a75e  pop     rdi
0x18000a75f  pop     rsi
0x18000a760  pop     rbx
0x18000a761  retn
```

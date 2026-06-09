# CheckRsvdSupport

- ea: `0x18000a018`
- end: `0x18000a17e`
- name: `CheckRsvdSupport`
- size: `358`
- prototype: `__int64 __fastcall(const void **, char *, char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180002740`

## callees

- `0x18000a018`
- `0x18000a184`
- `0x18000b3d0`
- `0x18000b4e4`
- `0x18000ba11`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a0cc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a0cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a128`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a128`
- `ntdll!RtlFreeHeap` at `0x18000a113`
- `ntdll!RtlFreeHeap` at `0x18000a113`
- `ntdll!RtlAllocateHeap` at `0x18000a07c`
- `ntdll!RtlAllocateHeap` at `0x18000a07c`

## pseudocode

```c
__int64 __fastcall CheckRsvdSupport(const void **a1, char *a2, char *a3)
{
  DWORD LastError; // ebx
  WCHAR *Heap; // rax
  int v8; // r8d
  WCHAR *v9; // rbp
  HANDLE FileW; // rax
  void *v11; // rsi

  LastError = 14;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, a3, a1);
  }
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, *(unsigned __int16 *)a1 + 2LL);
  v9 = Heap;
  if ( Heap )
  {
    memcpy_0(Heap, a1[1], *(unsigned __int16 *)a1);
    FileW = CreateFileW(v9, 0x80000000, 7u, 0, 4u, 0x2100080u, 0);
    v11 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
    }
    else
    {
      LastError = 0;
      CheckRsvdSupportHandle(FileW);
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
    if ( v11 != (void *)-1LL )
      CloseHandle(v11);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_ZDdd(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned __int8)*a2, v8, (_DWORD)a1, LastError, *a2, *a3);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000a018  push    rbx
0x18000a01a  push    rbp
0x18000a01b  push    rsi
0x18000a01c  push    rdi
0x18000a01d  push    r12
0x18000a01f  push    r14
0x18000a021  push    r15
0x18000a023  sub     rsp, 40h
0x18000a027  mov     r14, r8
0x18000a02a  mov     r15, rdx
0x18000a02d  mov     rdi, rcx
0x18000a030  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a037  lea     r12, WPP_GLOBAL_Control
0x18000a03e  mov     ebx, 0Eh
0x18000a043  cmp     rcx, r12
0x18000a046  jz      short loc_18000A062
0x18000a048  test    byte ptr [rcx+1Ch], 20h
0x18000a04c  jz      short loc_18000A062
0x18000a04e  cmp     byte ptr [rcx+19h], 4
0x18000a052  jb      short loc_18000A062
0x18000a054  mov     rcx, [rcx+10h]
0x18000a058  mov     edx, ebx
0x18000a05a  mov     r9, rdi
0x18000a05d  call    WPP_SF_Z
0x18000a062  mov     rcx, gs:60h
0x18000a06b  mov     edx, 8; Flags
0x18000a070  movzx   r8d, word ptr [rdi]
0x18000a074  add     r8, 2; Size
0x18000a078  mov     rcx, [rcx+30h]; HeapHandle
0x18000a07c  call    cs:__imp_RtlAllocateHeap
0x18000a083  nop     dword ptr [rax+rax+00h]
0x18000a088  mov     rbp, rax
0x18000a08b  test    rax, rax
0x18000a08e  jz      loc_18000A134
0x18000a094  movzx   r8d, word ptr [rdi]; Size
0x18000a098  mov     rcx, rax; void *
0x18000a09b  mov     rdx, [rdi+8]; Src
0x18000a09f  call    memcpy_0
0x18000a0a4  xor     r9d, r9d; lpSecurityAttributes
0x18000a0a7  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18000a0b0  mov     [rsp+78h+dwFlagsAndAttributes], 2100080h; dwFlagsAndAttributes
0x18000a0b8  mov     edx, 80000000h; dwDesiredAccess
0x18000a0bd  mov     rcx, rbp; lpFileName
0x18000a0c0  mov     [rsp+78h+dwCreationDisposition], 4; dwCreationDisposition
0x18000a0c8  lea     r8d, [r9+7]; dwShareMode
0x18000a0cc  call    cs:__imp_CreateFileW
0x18000a0d3  nop     dword ptr [rax+rax+00h]
0x18000a0d8  mov     rsi, rax
0x18000a0db  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a0df  jnz     short loc_18000A0F1
0x18000a0e1  call    cs:__imp_GetLastError
0x18000a0e8  nop     dword ptr [rax+rax+00h]
0x18000a0ed  mov     ebx, eax
0x18000a0ef  jmp     short loc_18000A101
0x18000a0f1  xor     ebx, ebx
0x18000a0f3  mov     r8, r14
0x18000a0f6  mov     rdx, r15
0x18000a0f9  mov     rcx, rsi; hFile
0x18000a0fc  call    CheckRsvdSupportHandle
0x18000a101  mov     rcx, gs:60h
0x18000a10a  mov     r8, rbp; P
0x18000a10d  xor     edx, edx; Flags
0x18000a10f  mov     rcx, [rcx+30h]; HeapHandle
0x18000a113  call    cs:__imp_RtlFreeHeap
0x18000a11a  nop     dword ptr [rax+rax+00h]
0x18000a11f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000a123  jz      short loc_18000A134
0x18000a125  mov     rcx, rsi; hObject
0x18000a128  call    cs:__imp_CloseHandle
0x18000a12f  nop     dword ptr [rax+rax+00h]
0x18000a134  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a13b  cmp     rcx, r12
0x18000a13e  jz      short loc_18000A16C
0x18000a140  test    byte ptr [rcx+1Ch], 20h
0x18000a144  jz      short loc_18000A16C
0x18000a146  cmp     byte ptr [rcx+19h], 4
0x18000a14a  jb      short loc_18000A16C
0x18000a14c  movzx   eax, byte ptr [r14]
0x18000a150  mov     r9, rdi
0x18000a153  movzx   edx, byte ptr [r15]
0x18000a157  mov     rcx, [rcx+10h]
0x18000a15b  mov     dword ptr [rsp+78h+hTemplateFile], eax
0x18000a15f  mov     [rsp+78h+dwFlagsAndAttributes], edx
0x18000a163  mov     [rsp+78h+dwCreationDisposition], ebx
0x18000a167  call    WPP_SF_ZDdd
0x18000a16c  mov     eax, ebx
0x18000a16e  add     rsp, 40h
0x18000a172  pop     r15
0x18000a174  pop     r14
0x18000a176  pop     r12
0x18000a178  pop     rdi
0x18000a179  pop     rsi
0x18000a17a  pop     rbp
0x18000a17b  pop     rbx
0x18000a17c  retn
```

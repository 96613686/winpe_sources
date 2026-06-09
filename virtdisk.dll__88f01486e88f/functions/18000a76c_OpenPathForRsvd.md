# OpenPathForRsvd

- ea: `0x18000a76c`
- end: `0x18000a8b9`
- name: `OpenPathForRsvd`
- size: `333`
- prototype: `__int64 __fastcall(const void **, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18000648c`
- `0x18000a3f8`

## callees

- `0x18000a76c`
- `0x18000b3d0`
- `0x18000b44c`
- `0x18000ba11`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a822`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a837`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a875`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a875`
- `ntdll!RtlFreeHeap` at `0x18000a857`
- `ntdll!RtlFreeHeap` at `0x18000a857`
- `ntdll!RtlAllocateHeap` at `0x18000a7d0`
- `ntdll!RtlAllocateHeap` at `0x18000a7d0`

## pseudocode

```c
__int64 __fastcall OpenPathForRsvd(const void **a1, __int64 a2, _QWORD *a3)
{
  struct _PEB *v5; // rcx
  SIZE_T v6; // r8
  WCHAR *Heap; // rax
  int v8; // edx
  int v9; // r8d
  WCHAR *v10; // rbp
  DWORD LastError; // ebx
  HANDLE FileW; // rdi

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, a3, a1);
  }
  v5 = NtCurrentPeb();
  v6 = *(unsigned __int16 *)a1 + 2LL;
  *a3 = -1;
  Heap = (WCHAR *)RtlAllocateHeap(v5->ProcessHeap, 8u, v6);
  v10 = Heap;
  if ( Heap )
  {
    LastError = 0;
    memcpy_0(Heap, a1[1], *(unsigned __int16 *)a1);
    FileW = CreateFileW(v10, 0xC0000000, 7u, 0, 3u, 0xA0000080, 0);
    if ( FileW == (HANDLE)-1LL )
      LastError = GetLastError();
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
    if ( LastError )
    {
      if ( FileW != (HANDLE)-1LL )
        CloseHandle(FileW);
    }
    else
    {
      *a3 = FileW;
    }
  }
  else
  {
    LastError = 14;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, (_DWORD)a1, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000a76c  push    rbx
0x18000a76e  push    rbp
0x18000a76f  push    rsi
0x18000a770  push    rdi
0x18000a771  push    r14
0x18000a773  push    r15
0x18000a775  sub     rsp, 48h
0x18000a779  mov     r14, r8
0x18000a77c  mov     rsi, rcx
0x18000a77f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a786  lea     r15, WPP_GLOBAL_Control
0x18000a78d  cmp     rcx, r15
0x18000a790  jz      short loc_18000A7AF
0x18000a792  test    byte ptr [rcx+1Ch], 20h
0x18000a796  jz      short loc_18000A7AF
0x18000a798  cmp     byte ptr [rcx+19h], 4
0x18000a79c  jb      short loc_18000A7AF
0x18000a79e  mov     rcx, [rcx+10h]
0x18000a7a2  mov     edx, 0Ch
0x18000a7a7  mov     r9, rsi
0x18000a7aa  call    WPP_SF_Z
0x18000a7af  mov     rcx, gs:60h
0x18000a7b8  mov     edx, 8; Flags
0x18000a7bd  movzx   r8d, word ptr [rsi]
0x18000a7c1  add     r8, 2; Size
0x18000a7c5  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18000a7cc  mov     rcx, [rcx+30h]; HeapHandle
0x18000a7d0  call    cs:__imp_RtlAllocateHeap
0x18000a7d7  nop     dword ptr [rax+rax+00h]
0x18000a7dc  mov     rbp, rax
0x18000a7df  test    rax, rax
0x18000a7e2  jnz     short loc_18000A7EC
0x18000a7e4  lea     ebx, [rax+0Eh]
0x18000a7e7  jmp     loc_18000A881
0x18000a7ec  movzx   r8d, word ptr [rsi]; Size
0x18000a7f0  mov     rcx, rbp; void *
0x18000a7f3  mov     rdx, [rsi+8]; Src
0x18000a7f7  xor     ebx, ebx
0x18000a7f9  call    memcpy_0
0x18000a7fe  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x18000a803  lea     r8d, [rbx+7]; dwShareMode
0x18000a807  mov     [rsp+78h+dwFlagsAndAttributes], 0A0000080h; dwFlagsAndAttributes
0x18000a80f  xor     r9d, r9d; lpSecurityAttributes
0x18000a812  mov     edx, 0C0000000h; dwDesiredAccess
0x18000a817  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18000a81f  mov     rcx, rbp; lpFileName
0x18000a822  call    cs:__imp_CreateFileW
0x18000a829  nop     dword ptr [rax+rax+00h]
0x18000a82e  mov     rdi, rax
0x18000a831  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a835  jnz     short loc_18000A845
0x18000a837  call    cs:__imp_GetLastError
0x18000a83e  nop     dword ptr [rax+rax+00h]
0x18000a843  mov     ebx, eax
0x18000a845  mov     rcx, gs:60h
0x18000a84e  mov     r8, rbp; P
0x18000a851  xor     edx, edx; Flags
0x18000a853  mov     rcx, [rcx+30h]; HeapHandle
0x18000a857  call    cs:__imp_RtlFreeHeap
0x18000a85e  nop     dword ptr [rax+rax+00h]
0x18000a863  test    ebx, ebx
0x18000a865  jnz     short loc_18000A86C
0x18000a867  mov     [r14], rdi
0x18000a86a  jmp     short loc_18000A881
0x18000a86c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000a870  jz      short loc_18000A881
0x18000a872  mov     rcx, rdi; hObject
0x18000a875  call    cs:__imp_CloseHandle
0x18000a87c  nop     dword ptr [rax+rax+00h]
0x18000a881  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a888  cmp     rcx, r15
0x18000a88b  jz      short loc_18000A8A9
0x18000a88d  test    byte ptr [rcx+1Ch], 20h
0x18000a891  jz      short loc_18000A8A9
0x18000a893  cmp     byte ptr [rcx+19h], 4
0x18000a897  jb      short loc_18000A8A9
0x18000a899  mov     rcx, [rcx+10h]
0x18000a89d  mov     r9, rsi
0x18000a8a0  mov     [rsp+78h+dwCreationDisposition], ebx
0x18000a8a4  call    WPP_SF_ZD
0x18000a8a9  mov     eax, ebx
0x18000a8ab  add     rsp, 48h
0x18000a8af  pop     r15
0x18000a8b1  pop     r14
0x18000a8b3  pop     rdi
0x18000a8b4  pop     rsi
0x18000a8b5  pop     rbp
0x18000a8b6  pop     rbx
0x18000a8b7  retn
```

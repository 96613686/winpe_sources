# ConstructRsvdPathToFile

- ea: `0x18000a27c`
- end: `0x18000a3f1`
- name: `ConstructRsvdPathToFile`
- size: `373`
- prototype: `__int64 __fastcall(const UNICODE_STRING *, struct _UNICODE_STRING *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000648c`
- `0x18000a3f8`

## callees

- `0x18000a27c`
- `0x18000b1a0`
- `0x18000b3d0`

## import_xrefs

- `ntdll!RtlAppendUnicodeStringToString` at `0x18000a33a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000a33a`
- `ntdll!RtlAppendUnicodeToString` at `0x18000a35b`
- `ntdll!RtlAppendUnicodeToString` at `0x18000a35b`
- `ntdll!RtlFreeHeap` at `0x18000a391`
- `ntdll!RtlFreeHeap` at `0x18000a391`
- `ntdll!RtlAllocateHeap` at `0x18000a311`
- `ntdll!RtlAllocateHeap` at `0x18000a311`

## pseudocode

```c
__int64 __fastcall ConstructRsvdPathToFile(const UNICODE_STRING *a1, struct _UNICODE_STRING *a2, __int64 a3)
{
  unsigned __int64 v5; // rbx
  char v6; // si
  WCHAR *Heap; // rax
  unsigned int v8; // ebx
  PWSTR Buffer; // r8

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, a1);
  }
  *a2 = 0;
  if ( !is_mul_ok(0x12u, 2u) || (v5 = a1->Length + 36LL, v5 < 0x24) )
  {
    v6 = 22;
    goto LABEL_15;
  }
  v6 = 0;
  if ( v5 > 0xFFFC )
  {
LABEL_15:
    v8 = 534;
    goto LABEL_16;
  }
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, a1->Length + 36LL);
  a2->Buffer = Heap;
  if ( Heap )
  {
    a2->MaximumLength = v5;
    a2->Length = 0;
    if ( RtlAppendUnicodeStringToString(a2, a1) >= 0 && RtlAppendUnicodeToString(a2, L":SharedVirtualDisk") >= 0 )
    {
      v8 = 0;
      goto LABEL_18;
    }
    v8 = 1359;
  }
  else
  {
    v8 = 14;
  }
LABEL_16:
  Buffer = a2->Buffer;
  if ( Buffer )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    a2->Buffer = 0;
    *(_DWORD *)&a2->Length = 0;
  }
LABEL_18:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DdZZ(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, (__int64)a1, (__int64)a2);
  }
  return v8;
}

```

## disassembly

```asm
0x18000a27c  mov     [rsp+arg_0], rbx
0x18000a281  mov     [rsp+arg_8], rbp
0x18000a286  push    rsi
0x18000a287  push    rdi
0x18000a288  push    r14
0x18000a28a  sub     rsp, 40h
0x18000a28e  mov     rdi, rdx
0x18000a291  mov     rbp, rcx
0x18000a294  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a29b  lea     r14, WPP_GLOBAL_Control
0x18000a2a2  cmp     rcx, r14
0x18000a2a5  jz      short loc_18000A2C4
0x18000a2a7  test    byte ptr [rcx+1Ch], 20h
0x18000a2ab  jz      short loc_18000A2C4
0x18000a2ad  cmp     byte ptr [rcx+19h], 4
0x18000a2b1  jb      short loc_18000A2C4
0x18000a2b3  mov     rcx, [rcx+10h]
0x18000a2b7  mov     edx, 0Ah
0x18000a2bc  mov     r9, rbp
0x18000a2bf  call    WPP_SF_Z
0x18000a2c4  mov     ecx, 12h
0x18000a2c9  mov     [rsp+58h+arg_10], 0
0x18000a2d2  xorps   xmm0, xmm0
0x18000a2d5  movups  xmmword ptr [rdi], xmm0
0x18000a2d8  lea     eax, [rcx-10h]
0x18000a2db  mul     rcx
0x18000a2de  test    rdx, rdx
0x18000a2e1  jnz     loc_18000A36F
0x18000a2e7  movzx   ebx, word ptr [rbp+0]
0x18000a2eb  add     rbx, rax
0x18000a2ee  cmp     rbx, rax
0x18000a2f1  jb      short loc_18000A36F
0x18000a2f3  xor     esi, esi
0x18000a2f5  cmp     rbx, 0FFFCh
0x18000a2fc  ja      short loc_18000A374
0x18000a2fe  mov     rcx, gs:60h
0x18000a307  lea     edx, [rsi+8]; Flags
0x18000a30a  mov     r8, rbx; Size
0x18000a30d  mov     rcx, [rcx+30h]; HeapHandle
0x18000a311  call    cs:__imp_RtlAllocateHeap
0x18000a318  nop     dword ptr [rax+rax+00h]
0x18000a31d  mov     [rdi+8], rax
0x18000a321  test    rax, rax
0x18000a324  jnz     short loc_18000A32B
0x18000a326  lea     ebx, [rsi+0Eh]
0x18000a329  jmp     short loc_18000A379
0x18000a32b  xor     eax, eax
0x18000a32d  mov     [rdi+2], bx
0x18000a331  mov     rdx, rbp; Source
0x18000a334  mov     [rdi], ax
0x18000a337  mov     rcx, rdi; Destination
0x18000a33a  call    cs:__imp_RtlAppendUnicodeStringToString
0x18000a341  nop     dword ptr [rax+rax+00h]
0x18000a346  test    eax, eax
0x18000a348  jns     short loc_18000A351
0x18000a34a  mov     ebx, 54Fh
0x18000a34f  jmp     short loc_18000A379
0x18000a351  lea     rdx, aSharedvirtuald; ":SharedVirtualDisk"
0x18000a358  mov     rcx, rdi; Destination
0x18000a35b  call    cs:__imp_RtlAppendUnicodeToString
0x18000a362  nop     dword ptr [rax+rax+00h]
0x18000a367  test    eax, eax
0x18000a369  js      short loc_18000A34A
0x18000a36b  xor     ebx, ebx
0x18000a36d  jmp     short loc_18000A3A9
0x18000a36f  mov     esi, 80070216h
0x18000a374  mov     ebx, 216h
0x18000a379  mov     r8, [rdi+8]; P
0x18000a37d  test    r8, r8
0x18000a380  jz      short loc_18000A3A9
0x18000a382  mov     rcx, gs:60h
0x18000a38b  xor     edx, edx; Flags
0x18000a38d  mov     rcx, [rcx+30h]; HeapHandle
0x18000a391  call    cs:__imp_RtlFreeHeap
0x18000a398  nop     dword ptr [rax+rax+00h]
0x18000a39d  xor     eax, eax
0x18000a39f  mov     qword ptr [rdi+8], 0
0x18000a3a7  mov     [rdi], eax
0x18000a3a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3b0  cmp     rcx, r14
0x18000a3b3  jz      short loc_18000A3DB
0x18000a3b5  test    byte ptr [rcx+1Ch], 20h
0x18000a3b9  jz      short loc_18000A3DB
0x18000a3bb  cmp     byte ptr [rcx+19h], 4
0x18000a3bf  jb      short loc_18000A3DB
0x18000a3c1  mov     rcx, [rcx+10h]; LoggerHandle
0x18000a3c5  mov     r9d, ebx
0x18000a3c8  mov     [rsp+58h+var_28], rdi; __int64
0x18000a3cd  mov     [rsp+58h+var_30], rbp; __int64
0x18000a3d2  mov     dword ptr [rsp+58h+var_38], esi; char
0x18000a3d6  call    WPP_SF_DdZZ
0x18000a3db  mov     rbp, [rsp+58h+arg_8]
0x18000a3e0  mov     eax, ebx
0x18000a3e2  mov     rbx, [rsp+58h+arg_0]
0x18000a3e7  add     rsp, 40h
0x18000a3eb  pop     r14
0x18000a3ed  pop     rdi
0x18000a3ee  pop     rsi
0x18000a3ef  retn
```

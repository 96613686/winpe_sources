# TmpNamespaceLookup

- ea: `0x140020a6c`
- end: `0x140020b41`
- name: `TmpNamespaceLookup`
- size: `213`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table, PVOID Buffer)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000eee4`
- `0x140015a50`
- `0x140016c00`
- `0x1400175d0`
- `0x140019a30`
- `0x140019a5c`
- `0x14001c4a0`

## callees

- `0x140020a6c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140020a9e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140020a9e`
- `ntoskrnl!KeReleaseMutex` at `0x140020b29`
- `ntoskrnl!KeReleaseMutex` at `0x140020b29`
- `ntoskrnl!ObfReferenceObject` at `0x140020b08`
- `ntoskrnl!ObfReferenceObject` at `0x140020b08`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140020ad6`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140020ad6`

## pseudocode

```c
__int64 __fastcall TmpNamespaceLookup(PRTL_AVL_TABLE Table, PVOID Buffer, _QWORD *a3)
{
  struct _KMUTANT *v3; // rbp
  unsigned int v7; // ebx
  _BYTE *v8; // rax
  _BYTE *v9; // rcx
  __int128 v11; // [rsp+30h] [rbp-38h] BYREF

  v3 = (struct _KMUTANT *)&Table[1];
  v11 = 0;
  KeWaitForSingleObject(&Table[1], Executive, 0, 0, 0);
  if ( BYTE4(Table[1].RestartKey) )
  {
    v7 = -1073741816;
  }
  else
  {
    DWORD2(v11) = 1;
    Table->TableContext = &v11;
    *(_QWORD *)&v11 = Buffer;
    v8 = RtlLookupElementGenericTableAvl(Table, Buffer);
    Table->TableContext = 0;
    if ( !v8 || *v8 )
    {
      *a3 = 0;
      v7 = -1073741772;
    }
    else
    {
      v9 = &v8[-LOWORD(Table[1].RestartKey) - 32];
      *a3 = v9;
      ObfReferenceObject(v9);
      v7 = 0;
    }
  }
  KeReleaseMutex(v3, 0);
  return v7;
}

```

## disassembly

```asm
0x140020a6c  push    rbx
0x140020a6e  push    rbp
0x140020a6f  push    rsi
0x140020a70  push    rdi
0x140020a71  sub     rsp, 48h
0x140020a75  lea     rbp, [rcx+68h]
0x140020a79  mov     [rsp+68h+Timeout], 0; Timeout
0x140020a82  mov     rdi, r8
0x140020a85  mov     rsi, rdx
0x140020a88  mov     rbx, rcx
0x140020a8b  xorps   xmm0, xmm0
0x140020a8e  mov     rcx, rbp; Object
0x140020a91  xor     r9d, r9d; Alertable
0x140020a94  xor     r8d, r8d; WaitMode
0x140020a97  xor     edx, edx; WaitReason
0x140020a99  movups  [rsp+68h+var_38], xmm0
0x140020a9e  call    cs:__imp_KeWaitForSingleObject
0x140020aa5  nop     dword ptr [rax+rax+00h]
0x140020aaa  cmp     byte ptr [rbx+0A4h], 0
0x140020ab1  jz      short loc_140020ABA
0x140020ab3  mov     ebx, 0C0000008h
0x140020ab8  jmp     short loc_140020B24
0x140020aba  lea     rax, [rsp+68h+var_38]
0x140020abf  mov     dword ptr [rsp+68h+var_38+8], 1
0x140020ac7  mov     rdx, rsi; Buffer
0x140020aca  mov     [rbx+60h], rax
0x140020ace  mov     rcx, rbx; Table
0x140020ad1  mov     qword ptr [rsp+68h+var_38], rsi
0x140020ad6  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140020add  nop     dword ptr [rax+rax+00h]
0x140020ae2  mov     qword ptr [rbx+60h], 0
0x140020aea  mov     rcx, rax
0x140020aed  test    rax, rax
0x140020af0  jz      short loc_140020B18
0x140020af2  cmp     byte ptr [rax], 0
0x140020af5  jnz     short loc_140020B18
0x140020af7  movzx   eax, word ptr [rbx+0A0h]
0x140020afe  sub     rcx, rax
0x140020b01  add     rcx, 0FFFFFFFFFFFFFFE0h; Object
0x140020b05  mov     [rdi], rcx
0x140020b08  call    cs:__imp_ObfReferenceObject
0x140020b0f  nop     dword ptr [rax+rax+00h]
0x140020b14  xor     ebx, ebx
0x140020b16  jmp     short loc_140020B24
0x140020b18  mov     qword ptr [rdi], 0
0x140020b1f  mov     ebx, 0C0000034h
0x140020b24  xor     edx, edx; Wait
0x140020b26  mov     rcx, rbp; Mutex
0x140020b29  call    cs:__imp_KeReleaseMutex
0x140020b30  nop     dword ptr [rax+rax+00h]
0x140020b35  mov     eax, ebx
0x140020b37  add     rsp, 48h
0x140020b3b  pop     rdi
0x140020b3c  pop     rsi
0x140020b3d  pop     rbp
0x140020b3e  pop     rbx
0x140020b3f  retn
```

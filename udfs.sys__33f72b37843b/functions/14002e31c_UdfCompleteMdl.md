# UdfCompleteMdl

- ea: `0x14002e31c`
- end: `0x14002e4f3`
- name: `UdfCompleteMdl`
- size: `471`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400094c0`

## callees

- `0x1400030e0`
- `0x140010c5c`
- `0x140014c08`
- `0x14002e31c`

## import_xrefs

- `ntoskrnl!CcSetFileSizes` at `0x14002e448`
- `ntoskrnl!CcSetFileSizes` at `0x14002e448`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002e3d8`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002e3d8`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002e488`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002e488`
- `ntoskrnl!CcMdlReadComplete` at `0x14002e4be`
- `ntoskrnl!CcMdlReadComplete` at `0x14002e4be`
- `ntoskrnl!CcMdlWriteComplete` at `0x14002e4a6`
- `ntoskrnl!CcMdlWriteComplete` at `0x14002e4a6`
- `ntoskrnl!KeBugCheckEx` at `0x14002e38c`
- `ntoskrnl!KeBugCheckEx` at `0x14002e38c`

## pseudocode

```c
__int64 __fastcall UdfCompleteMdl(__int64 a1, __int64 a2)
{
  __int64 v3; // r14
  PMDL *v4; // r12
  struct _MDL *v5; // rdx
  __int64 v6; // r13
  struct _FILE_OBJECT *v7; // rdi
  char *FsContext; // rbx
  union _LARGE_INTEGER *v9; // r13
  union _LARGE_INTEGER v10; // r14
  union _LARGE_INTEGER v11; // r9
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rax

  v3 = a1;
  v4 = (PMDL *)(a2 + 8);
  v5 = *(struct _MDL **)(a2 + 8);
  v6 = *(_QWORD *)(a2 + 184);
  v7 = *(struct _FILE_OBJECT **)(v6 + 48);
  if ( *(_BYTE *)(a1 + 56) == 3 )
  {
    CcMdlReadComplete(v7, v5);
  }
  else
  {
    if ( *(_BYTE *)(a1 + 56) != 4 )
      KeBugCheckEx(0x9Bu, 0x201C1u, *(unsigned __int8 *)(a1 + 56), 0, 0);
    FsContext = (char *)v7->FsContext;
    v9 = (union _LARGE_INTEGER *)(v6 + 24);
    if ( FsContext[4] < 0 )
    {
      v10 = *v9;
      while ( v5 )
      {
        v10.QuadPart += v5->ByteCount;
        v5 = v5->Next;
      }
      ExAcquireFastMutex(*((PFAST_MUTEX *)FsContext + 6));
      v11 = *(union _LARGE_INTEGER *)(FsContext + 40);
      if ( v10.QuadPart > v11.QuadPart )
      {
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 2) != 0 )
        {
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qq)(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            12,
            WPP_caac521dd36031f4ea1a4be88351727a_Traceguids,
            (union _LARGE_INTEGER)v11.QuadPart,
            *((_QWORD *)FsContext + 4));
        }
        *((_QWORD *)FsContext + 5) = *((_QWORD *)FsContext + 4);
        SectionObjectPointer = v7->SectionObjectPointer;
        if ( SectionObjectPointer && SectionObjectPointer->SharedCacheMap )
          CcSetFileSizes(v7, (PCC_FILE_SIZES)FsContext + 1);
        UdfFinishIoAtEof(FsContext);
      }
      ExReleaseFastMutex(*((PFAST_MUTEX *)FsContext + 6));
      v3 = a1;
    }
    CcMdlWriteComplete(v7, v9, *v4);
    *(_DWORD *)(a2 + 48) = 0;
  }
  *v4 = 0;
  UdfCompleteRequest(v3, a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14002e31c  mov     [rsp+arg_8], rdx
0x14002e321  mov     [rsp+arg_0], rcx
0x14002e326  push    rbx
0x14002e327  push    rsi
0x14002e328  push    rdi
0x14002e329  push    r12
0x14002e32b  push    r13
0x14002e32d  push    r14
0x14002e32f  push    r15
0x14002e331  sub     rsp, 50h
0x14002e335  mov     rsi, rdx
0x14002e338  mov     r14, rcx
0x14002e33b  lea     r12, [rdx+8]
0x14002e33f  mov     [rsp+88h+var_58], r12
0x14002e344  mov     rdx, [r12]; MdlChain
0x14002e348  mov     r13, [rsi+0B8h]
0x14002e34f  mov     rdi, [r13+30h]
0x14002e353  mov     [rsp+88h+arg_10], rdi
0x14002e35b  movzx   r9d, byte ptr [rcx+38h]
0x14002e360  mov     r8d, r9d
0x14002e363  sub     r8d, 3
0x14002e367  jz      loc_14002E4BB
0x14002e36d  cmp     r8d, 1
0x14002e371  jz      short loc_14002E399
0x14002e373  mov     r8d, r9d; BugCheckParameter2
0x14002e376  mov     [rsp+88h+BugCheckParameter4], 0; BugCheckParameter4
0x14002e37f  xor     r9d, r9d; BugCheckParameter3
0x14002e382  mov     edx, 201C1h; BugCheckParameter1
0x14002e387  mov     ecx, 9Bh; BugCheckCode
0x14002e38c  call    cs:__imp_KeBugCheckEx
0x14002e399  mov     rbx, [rdi+18h]
0x14002e39d  add     r13, 18h
0x14002e3a1  mov     [rsp+88h+var_50], r13
0x14002e3a6  cmp     byte ptr [rbx+4], 0
0x14002e3aa  jge     loc_14002E49C
0x14002e3b0  mov     [rsp+88h+arg_18], rbx
0x14002e3b8  mov     r14, [r13+0]
0x14002e3bc  jmp     short loc_14002E3C7
0x14002e3be  mov     eax, [rdx+28h]
0x14002e3c1  add     r14, rax
0x14002e3c4  mov     rdx, [rdx]
0x14002e3c7  test    rdx, rdx
0x14002e3ca  jnz     short loc_14002E3BE
0x14002e3cc  lea     r15, [rbx+30h]
0x14002e3d0  mov     [rsp+88h+var_48], r15
0x14002e3d5  mov     rcx, [r15]; FastMutex
0x14002e3d8  call    cs:__imp_ExAcquireFastMutex
0x14002e3df  nop     dword ptr [rax+rax+00h]
0x14002e3e4  mov     r9, [rbx+28h]
0x14002e3e8  cmp     r14, r9
0x14002e3eb  jle     loc_14002E485
0x14002e3f1  lea     rax, WPP_GLOBAL_Control
0x14002e3f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e3ff  cmp     rcx, rax
0x14002e402  jz      short loc_14002E429
0x14002e404  mov     eax, [rcx+2Ch]
0x14002e407  test    al, 2
0x14002e409  jz      short loc_14002E429
0x14002e40b  mov     edx, 0Ch
0x14002e410  mov     rax, [rbx+20h]
0x14002e414  mov     [rsp+88h+BugCheckParameter4], rax
0x14002e419  lea     r8, WPP_caac521dd36031f4ea1a4be88351727a_Traceguids
0x14002e420  mov     rcx, [rcx+18h]
0x14002e424  call    WPP_SF_qq
0x14002e429  mov     rax, [rbx+20h]
0x14002e42d  mov     [rbx+28h], rax
0x14002e431  mov     rax, [rdi+28h]
0x14002e435  test    rax, rax
0x14002e438  jz      short loc_14002E47D
0x14002e43a  cmp     qword ptr [rax+8], 0
0x14002e43f  jz      short loc_14002E47D
0x14002e441  lea     rdx, [rbx+18h]; FileSizes
0x14002e445  mov     rcx, rdi; FileObject
0x14002e448  call    cs:__imp_CcSetFileSizes
0x14002e44f  nop     dword ptr [rax+rax+00h]
0x14002e454  jmp     short loc_14002E47D
0x14002e456  mov     rsi, [rsp+88h+arg_8]
0x14002e45e  mov     rdi, [rsp+88h+arg_10]
0x14002e466  mov     rbx, [rsp+88h+arg_18]
0x14002e46e  mov     r12, [rsp+88h+var_58]
0x14002e473  mov     r13, [rsp+88h+var_50]
0x14002e478  mov     r15, [rsp+88h+var_48]
0x14002e47d  mov     rcx, rbx
0x14002e480  call    UdfFinishIoAtEof
0x14002e485  mov     rcx, [r15]; FastMutex
0x14002e488  call    cs:__imp_ExReleaseFastMutex
0x14002e48f  nop     dword ptr [rax+rax+00h]
0x14002e494  mov     r14, [rsp+88h+arg_0]
0x14002e49c  mov     r8, [r12]; MdlChain
0x14002e4a0  mov     rdx, r13; FileOffset
0x14002e4a3  mov     rcx, rdi; FileObject
0x14002e4a6  call    cs:__imp_CcMdlWriteComplete
0x14002e4ad  nop     dword ptr [rax+rax+00h]
0x14002e4b2  mov     dword ptr [rsi+30h], 0
0x14002e4b9  jmp     short loc_14002E4CA
0x14002e4bb  mov     rcx, rdi; FileObject
0x14002e4be  call    cs:__imp_CcMdlReadComplete
0x14002e4c5  nop     dword ptr [rax+rax+00h]
0x14002e4ca  mov     qword ptr [r12], 0
0x14002e4d2  xor     r8d, r8d
0x14002e4d5  mov     rdx, rsi
0x14002e4d8  mov     rcx, r14
0x14002e4db  call    UdfCompleteRequest
0x14002e4e0  xor     eax, eax
0x14002e4e2  add     rsp, 50h
0x14002e4e6  pop     r15
0x14002e4e8  pop     r14
0x14002e4ea  pop     r13
0x14002e4ec  pop     r12
0x14002e4ee  pop     rdi
0x14002e4ef  pop     rsi
0x14002e4f0  pop     rbx
0x14002e4f1  retn
```

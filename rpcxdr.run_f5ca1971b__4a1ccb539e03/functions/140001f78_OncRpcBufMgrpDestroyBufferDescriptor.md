# OncRpcBufMgrpDestroyBufferDescriptor

- ea: `0x140001f78`
- end: `0x14000205a`
- name: `OncRpcBufMgrpDestroyBufferDescriptor`
- size: `226`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400010dc`
- `0x1400015ec`
- `0x140006d70`

## callees

- `0x140001f78`
- `0x140015680`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000201a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000203c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000201a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000203c`
- `ntoskrnl!IoFreeMdl` at `0x140001fca`
- `ntoskrnl!IoFreeMdl` at `0x140001fca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001f98`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001f98`

## pseudocode

```c
void __fastcall OncRpcBufMgrpDestroyBufferDescriptor(PVOID Entry)
{
  int v1; // eax
  struct _MDL *v3; // rcx
  _QWORD *v4; // rax
  int v5; // eax

  v1 = *((_DWORD *)Entry + 20);
  if ( (v1 & 8) != 0 )
  {
    ExFreePoolWithTag(*((PVOID *)Entry + 7), 0x50426458u);
    --dword_14001A6F4;
  }
  else if ( (v1 & 0x10) != 0 )
  {
    (*((void (__fastcall **)(_QWORD, _QWORD))Entry + 5))(*((_QWORD *)Entry + 6), *((_QWORD *)Entry + 7));
    v3 = (struct _MDL *)*((_QWORD *)Entry + 11);
    if ( v3 )
      IoFreeMdl(v3);
    --dword_14001A6F8;
  }
  else if ( (v1 & 0x20) != 0 )
  {
    v4 = (_QWORD *)*((_QWORD *)Entry + 12);
    if ( v4 )
    {
      *v4 = 0;
      (*((void (__fastcall **)(_QWORD, _QWORD))Entry + 5))(*((_QWORD *)Entry + 6), *((_QWORD *)Entry + 11));
    }
    --dword_14001A6FC;
  }
  v5 = *((_DWORD *)Entry + 20);
  if ( (v5 & 2) != 0 )
  {
    ExFreeToNPagedLookasideList(&stru_14001A600, Entry);
    --dword_14001A6F0;
  }
  else if ( (v5 & 1) != 0 )
  {
    ExFreeToNPagedLookasideList(&stru_14001A580, Entry);
    --dword_14001A6EC;
  }
}

```

## disassembly

```asm
0x140001f78  mov     [rsp+arg_0], rbx
0x140001f7d  push    rdi
0x140001f7e  sub     rsp, 20h
0x140001f82  mov     eax, [rcx+50h]
0x140001f85  or      edi, 0FFFFFFFFh
0x140001f88  mov     rbx, rcx
0x140001f8b  test    al, 8
0x140001f8d  jz      short loc_140001FAC
0x140001f8f  mov     rcx, [rcx+38h]; P
0x140001f93  mov     edx, 50426458h; Tag
0x140001f98  call    cs:__imp_ExFreePoolWithTag
0x140001f9f  nop     dword ptr [rax+rax+00h]
0x140001fa4  add     cs:dword_14001A6F4, edi
0x140001faa  jmp     short loc_140002009
0x140001fac  test    al, 10h
0x140001fae  jz      short loc_140001FDE
0x140001fb0  mov     rax, [rcx+28h]
0x140001fb4  mov     rdx, [rcx+38h]
0x140001fb8  mov     rcx, [rcx+30h]
0x140001fbc  call    _guard_dispatch_icall
0x140001fc1  mov     rcx, [rbx+58h]; Mdl
0x140001fc5  test    rcx, rcx
0x140001fc8  jz      short loc_140001FD6
0x140001fca  call    cs:__imp_IoFreeMdl
0x140001fd1  nop     dword ptr [rax+rax+00h]
0x140001fd6  add     cs:dword_14001A6F8, edi
0x140001fdc  jmp     short loc_140002009
0x140001fde  test    al, 20h
0x140001fe0  jz      short loc_140002009
0x140001fe2  mov     rax, [rcx+60h]
0x140001fe6  test    rax, rax
0x140001fe9  jz      short loc_140002003
0x140001feb  mov     qword ptr [rax], 0
0x140001ff2  mov     rax, [rcx+28h]
0x140001ff6  mov     rdx, [rcx+58h]
0x140001ffa  mov     rcx, [rcx+30h]
0x140001ffe  call    _guard_dispatch_icall
0x140002003  add     cs:dword_14001A6FC, edi
0x140002009  mov     eax, [rbx+50h]
0x14000200c  test    al, 2
0x14000200e  jz      short loc_14000202E
0x140002010  mov     rdx, rbx; Entry
0x140002013  lea     rcx, stru_14001A600; Lookaside
0x14000201a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140002021  nop     dword ptr [rax+rax+00h]
0x140002026  add     cs:dword_14001A6F0, edi
0x14000202c  jmp     short loc_14000204E
0x14000202e  test    al, 1
0x140002030  jz      short loc_14000204E
0x140002032  mov     rdx, rbx; Entry
0x140002035  lea     rcx, stru_14001A580; Lookaside
0x14000203c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140002043  nop     dword ptr [rax+rax+00h]
0x140002048  add     cs:dword_14001A6EC, edi
0x14000204e  mov     rbx, [rsp+28h+arg_0]
0x140002053  add     rsp, 20h
0x140002057  pop     rdi
0x140002058  retn
```

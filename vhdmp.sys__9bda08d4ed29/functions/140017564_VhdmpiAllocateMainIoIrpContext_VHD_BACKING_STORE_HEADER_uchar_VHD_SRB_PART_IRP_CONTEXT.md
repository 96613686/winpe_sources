# VhdmpiAllocateMainIoIrpContext(_VHD_BACKING_STORE_HEADER *,uchar,VHD_SRB_PART_IRP_CONTEXT * *)

- ea: `0x140017564`
- end: `0x140017638`
- name: `?VhdmpiAllocateMainIoIrpContext@@YAJPEAU_VHD_BACKING_STORE_HEADER@@EPEAPEAUVHD_SRB_PART_IRP_CONTEXT@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(struct _VHD_BACKING_STORE_HEADER *, unsigned __int8, struct VHD_SRB_PART_IRP_CONTEXT **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140017450`

## callees

- `0x140017564`
- `0x14005e100`

## import_xrefs

- `ntoskrnl!IoInitializeIrpEx` at `0x1400175dc`
- `ntoskrnl!IoInitializeIrpEx` at `0x1400175dc`
- `ntoskrnl!IoReuseIrp` at `0x140017623`
- `ntoskrnl!IoReuseIrp` at `0x140017623`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140017586`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140017586`

## pseudocode

```c
__int64 __fastcall VhdmpiAllocateMainIoIrpContext(struct _NPAGED_LOOKASIDE_LIST *a1, char a2, ULONGLONG *a3)
{
  char *v5; // rax
  char *v6; // r14
  unsigned __int16 v7; // di
  char *v8; // rsi
  __int64 v9; // r9
  unsigned int v10; // ebx

  if ( a2 )
  {
    v10 = 0;
    *a3 = a1[14].L.ListHead.Alignment;
    *((_BYTE *)&a1[14].L.SingleListHead + 9) = 1;
    IoReuseIrp(*(PIRP *)(*a3 + 16), 259);
  }
  else
  {
    v5 = (char *)ExAllocateFromNPagedLookasideList(a1 + 13);
    v6 = v5;
    if ( v5 )
    {
      v7 = *((_WORD *)&a1[14].L.SingleListHead + 5);
      v8 = v5 + 160;
      memset(v5 + 24, 0, 0x58u);
      *(_QWORD *)v6 = &a1->L.ListEntry.Blink;
      *((_QWORD *)v6 + 1) = a1;
      *((_QWORD *)v6 + 2) = v8;
      LOBYTE(v9) = a1[4].L.Future[4];
      IoInitializeIrpEx(v8, -1, v7, v9);
      *((_QWORD *)v8 + 18) = v6;
      v10 = 0;
      *a3 = (ULONGLONG)v6;
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x140017564  push    rbx
0x140017566  push    rbp
0x140017567  push    rsi
0x140017568  push    rdi
0x140017569  push    r14
0x14001756b  push    r15
0x14001756d  sub     rsp, 28h
0x140017571  mov     r15, r8
0x140017574  mov     rbp, rcx
0x140017577  test    dl, dl
0x140017579  jnz     loc_140017604
0x14001757f  add     rcx, 680h; Lookaside
0x140017586  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001758d  nop     dword ptr [rax+rax+00h]
0x140017592  mov     r14, rax
0x140017595  test    rax, rax
0x140017598  jz      loc_140017631
0x14001759e  movzx   edi, word ptr [rbp+70Ah]
0x1400175a5  lea     rcx, [rax+18h]; void *
0x1400175a9  xor     edx, edx; Val
0x1400175ab  lea     rbx, [rbp+48h]
0x1400175af  lea     rsi, [rax+0A0h]
0x1400175b6  lea     r8d, [rdx+58h]; Size
0x1400175ba  call    memset
0x1400175bf  mov     [r14], rbx
0x1400175c2  movzx   r8d, di
0x1400175c6  mov     [r14+8], rbp
0x1400175ca  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400175ce  mov     [r14+10h], rsi
0x1400175d2  mov     rcx, rsi
0x1400175d5  mov     r9b, [rbx+220h]
0x1400175dc  call    cs:__imp_IoInitializeIrpEx
0x1400175e3  nop     dword ptr [rax+rax+00h]
0x1400175e8  mov     [rsi+90h], r14
0x1400175ef  xor     ebx, ebx
0x1400175f1  mov     [r15], r14
0x1400175f4  mov     eax, ebx
0x1400175f6  add     rsp, 28h
0x1400175fa  pop     r15
0x1400175fc  pop     r14
0x1400175fe  pop     rdi
0x1400175ff  pop     rsi
0x140017600  pop     rbp
0x140017601  pop     rbx
0x140017602  retn
0x140017604  mov     rcx, [rcx+700h]
0x14001760b  xor     ebx, ebx
0x14001760d  mov     [r8], rcx
0x140017610  mov     edx, 103h; Iostatus
0x140017615  mov     byte ptr [rbp+709h], 1
0x14001761c  mov     rcx, [r8]
0x14001761f  mov     rcx, [rcx+10h]; Irp
0x140017623  call    cs:__imp_IoReuseIrp
0x14001762a  nop     dword ptr [rax+rax+00h]
0x14001762f  jmp     short loc_1400175F4
0x140017631  mov     ebx, 0C000009Ah
0x140017636  jmp     short loc_1400175F4
```

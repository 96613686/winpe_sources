# VhdmpiAllocateMainIoIrpContext(_VHD_BACKING_STORE_HEADER *,uchar,VHD_SRB_PART_IRP_CONTEXT * *)

- ea: `0x1400170c4`
- end: `0x140017198`
- name: `?VhdmpiAllocateMainIoIrpContext@@YAJPEAU_VHD_BACKING_STORE_HEADER@@EPEAPEAUVHD_SRB_PART_IRP_CONTEXT@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(struct _NPAGED_LOOKASIDE_LIST *, char, ULONGLONG *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140016fb0`

## callees

- `0x1400170c4`
- `0x14005dd00`

## import_xrefs

- `ntoskrnl!IoInitializeIrpEx` at `0x14001713c`
- `ntoskrnl!IoInitializeIrpEx` at `0x14001713c`
- `ntoskrnl!IoReuseIrp` at `0x140017183`
- `ntoskrnl!IoReuseIrp` at `0x140017183`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400170e6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400170e6`

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
0x1400170c4  push    rbx
0x1400170c6  push    rbp
0x1400170c7  push    rsi
0x1400170c8  push    rdi
0x1400170c9  push    r14
0x1400170cb  push    r15
0x1400170cd  sub     rsp, 28h
0x1400170d1  mov     r15, r8
0x1400170d4  mov     rbp, rcx
0x1400170d7  test    dl, dl
0x1400170d9  jnz     loc_140017164
0x1400170df  add     rcx, 680h; Lookaside
0x1400170e6  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400170ed  nop     dword ptr [rax+rax+00h]
0x1400170f2  mov     r14, rax
0x1400170f5  test    rax, rax
0x1400170f8  jz      loc_140017191
0x1400170fe  movzx   edi, word ptr [rbp+70Ah]
0x140017105  lea     rcx, [rax+18h]; void *
0x140017109  xor     edx, edx; Val
0x14001710b  lea     rbx, [rbp+48h]
0x14001710f  lea     rsi, [rax+0A0h]
0x140017116  lea     r8d, [rdx+58h]; Size
0x14001711a  call    memset
0x14001711f  mov     [r14], rbx
0x140017122  movzx   r8d, di
0x140017126  mov     [r14+8], rbp
0x14001712a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14001712e  mov     [r14+10h], rsi
0x140017132  mov     rcx, rsi
0x140017135  mov     r9b, [rbx+220h]
0x14001713c  call    cs:__imp_IoInitializeIrpEx
0x140017143  nop     dword ptr [rax+rax+00h]
0x140017148  mov     [rsi+90h], r14
0x14001714f  xor     ebx, ebx
0x140017151  mov     [r15], r14
0x140017154  mov     eax, ebx
0x140017156  add     rsp, 28h
0x14001715a  pop     r15
0x14001715c  pop     r14
0x14001715e  pop     rdi
0x14001715f  pop     rsi
0x140017160  pop     rbp
0x140017161  pop     rbx
0x140017162  retn
0x140017164  mov     rcx, [rcx+700h]
0x14001716b  xor     ebx, ebx
0x14001716d  mov     [r8], rcx
0x140017170  mov     edx, 103h; Iostatus
0x140017175  mov     byte ptr [rbp+709h], 1
0x14001717c  mov     rcx, [r8]
0x14001717f  mov     rcx, [rcx+10h]; Irp
0x140017183  call    cs:__imp_IoReuseIrp
0x14001718a  nop     dword ptr [rax+rax+00h]
0x14001718f  jmp     short loc_140017154
0x140017191  mov     ebx, 0C000009Ah
0x140017196  jmp     short loc_140017154
```

# UdfCleanupIrpContext

- ea: `0x140044860`
- end: `0x140044943`
- name: `UdfCleanupIrpContext`
- size: `227`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `12`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400010f0`
- `0x1400030e0`
- `0x140006680`
- `0x1400077f0`
- `0x140008790`
- `0x1400094c0`
- `0x14000cce0`
- `0x140016170`
- `0x14002c330`
- `0x14002dc50`
- `0x140044f90`
- `0x1400541a8`

## callees

- `0x140044860`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140044909`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044909`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400448b9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400448b9`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14004488f`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14004492a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14004488f`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14004492a`

## pseudocode

```c
void __fastcall UdfCleanupIrpContext(PVOID Entry, char a2)
{
  int v2; // eax
  _DWORD *v4; // rax
  _DWORD *v5; // rax

  v2 = *((_DWORD *)Entry + 7);
  if ( (v2 & 0x8000) != 0 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)Entry + 2) + 2016LL));
    *(_DWORD *)(*((_QWORD *)Entry + 2) + 2132LL) = 0;
    *((_DWORD *)Entry + 7) &= ~0x8000u;
    v2 = *((_DWORD *)Entry + 7);
  }
  if ( (v2 & 2) != 0 )
  {
    if ( a2 )
    {
      v5 = (_DWORD *)*((_QWORD *)Entry + 8);
      if ( v5 )
      {
        *v5 = 0;
        IoSetTopLevelIrp(*(PIRP *)(*((_QWORD *)Entry + 8) + 8LL));
        *((_QWORD *)Entry + 8) = 0;
      }
      *((_DWORD *)Entry + 7) &= 0xFFFFFD01;
    }
    else
    {
      *((_DWORD *)Entry + 7) = v2 & 0xFFFFFD7D;
    }
  }
  else
  {
    v4 = (_DWORD *)*((_QWORD *)Entry + 8);
    if ( v4 )
    {
      *v4 = 0;
      IoSetTopLevelIrp(*(PIRP *)(*((_QWORD *)Entry + 8) + 8LL));
      *((_QWORD *)Entry + 8) = 0;
    }
    if ( (*((_DWORD *)Entry + 7) & 0x100) != 0 )
      ExFreePoolWithTag(*((PVOID *)Entry + 5), 0);
    if ( (*((_DWORD *)Entry + 7) & 1) == 0 )
      ExFreeToNPagedLookasideList(&UdfIrpContextLookasideList, Entry);
  }
}

```

## disassembly

```asm
0x140044860  mov     [rsp+arg_0], rbx
0x140044865  push    rdi
0x140044866  sub     rsp, 20h
0x14004486a  mov     eax, [rcx+1Ch]
0x14004486d  xor     edi, edi
0x14004486f  mov     rbx, rcx
0x140044872  bt      eax, 0Fh
0x140044876  jb      short loc_1400448DF
0x140044878  test    al, 2
0x14004487a  jnz     short loc_1400448D1
0x14004487c  mov     rax, [rcx+40h]
0x140044880  test    rax, rax
0x140044883  jz      short loc_14004489F
0x140044885  mov     [rax], edi
0x140044887  mov     rcx, [rcx+40h]
0x14004488b  mov     rcx, [rcx+8]; Irp
0x14004488f  call    cs:__imp_IoSetTopLevelIrp
0x140044896  nop     dword ptr [rax+rax+00h]
0x14004489b  mov     [rbx+40h], rdi
0x14004489f  test    dword ptr [rbx+1Ch], 100h
0x1400448a6  jnz     short loc_140044903
0x1400448a8  mov     eax, [rbx+1Ch]
0x1400448ab  test    al, 1
0x1400448ad  jnz     short loc_1400448C5
0x1400448af  mov     rdx, rbx; Entry
0x1400448b2  lea     rcx, UdfIrpContextLookasideList; Lookaside
0x1400448b9  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400448c0  nop     dword ptr [rax+rax+00h]
0x1400448c5  mov     rbx, [rsp+28h+arg_0]
0x1400448ca  add     rsp, 20h
0x1400448ce  pop     rdi
0x1400448cf  retn
0x1400448d1  test    dl, dl
0x1400448d3  jnz     short loc_140044917
0x1400448d5  and     eax, 0FFFFFD7Dh
0x1400448da  mov     [rcx+1Ch], eax
0x1400448dd  jmp     short loc_1400448C5
0x1400448df  mov     rax, [rcx+10h]
0x1400448e3  lock dec dword ptr [rax+7E0h]
0x1400448ea  mov     rax, [rcx+10h]
0x1400448ee  mov     [rax+854h], edi
0x1400448f4  and     dword ptr [rcx+1Ch], 0FFFF7FFFh
0x1400448fb  mov     eax, [rcx+1Ch]
0x1400448fe  jmp     loc_140044878
0x140044903  mov     rcx, [rbx+28h]; P
0x140044907  xor     edx, edx; Tag
0x140044909  call    cs:__imp_ExFreePoolWithTag
0x140044910  nop     dword ptr [rax+rax+00h]
0x140044915  jmp     short loc_1400448A8
0x140044917  mov     rax, [rcx+40h]
0x14004491b  test    rax, rax
0x14004491e  jz      short loc_14004493A
0x140044920  mov     [rax], edi
0x140044922  mov     rcx, [rcx+40h]
0x140044926  mov     rcx, [rcx+8]; Irp
0x14004492a  call    cs:__imp_IoSetTopLevelIrp
0x140044931  nop     dword ptr [rax+rax+00h]
0x140044936  mov     [rbx+40h], rdi
0x14004493a  and     dword ptr [rbx+1Ch], 0FFFFFD01h
0x140044941  jmp     short loc_1400448C5
```

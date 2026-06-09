# VMX_PHYSICAL_DISK::CreatePrivateRegion(VMX_PACK *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX * *)

- ea: `0x140045798`
- end: `0x1400458e1`
- name: `?CreatePrivateRegion@VMX_PHYSICAL_DISK@@QEAAJPEAVVMX_PACK@@PEAU_DISK_GEOMETRY@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `329`
- prototype: `__int64 __fastcall(VMX_PHYSICAL_DISK *__hidden this, struct VMX_PACK *, struct _DISK_GEOMETRY *, struct _DRIVE_LAYOUT_INFORMATION_EX **)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14002e230`
- `0x1400358f4`

## callees

- `0x1400099d8`
- `0x140029294`
- `0x14002eab4`
- `0x140045798`
- `0x140047c7c`
- `0x1400483bc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140045830`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045884`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045830`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045884`

## pseudocode

```c
__int64 __fastcall VMX_PHYSICAL_DISK::CreatePrivateRegion(
        VMX_PHYSICAL_DISK *this,
        struct VMX_PACK *a2,
        struct _DISK_GEOMETRY *a3,
        PVOID *a4)
{
  int v6; // edi
  VMX_NOTIFICATION_QUEUE *v7; // rcx
  __int64 v8; // rdx
  PVOID P; // [rsp+48h] [rbp+20h] BYREF

  *a4 = 0;
  P = 0;
  v6 = VMX_PHYSICAL_DISK::NewMetadata(this, a2, a3, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)v6;
    }
    v8 = 18;
LABEL_6:
    WPP_SF_d(*((_QWORD *)v7 + 3), v8, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, (unsigned int)v6);
    return (unsigned int)v6;
  }
  v6 = VMX_PHYSICAL_DISK::ZeroPrivateRegion(this, 1u);
  if ( v6 < 0 )
  {
    VMX_PHYSICAL_DISK::DeletePrivateRegion(this, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
    ExFreePoolWithTag(P, 0);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)v6;
    }
    v8 = 19;
    goto LABEL_6;
  }
  v6 = VMX_PHYSICAL_DISK::WriteMetadata(this, 0);
  if ( v6 < 0 )
  {
    VMX_PHYSICAL_DISK::DeletePrivateRegion(this, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
    ExFreePoolWithTag(P, 0);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return (unsigned int)v6;
    }
    v8 = 20;
    goto LABEL_6;
  }
  *a4 = P;
  return 0;
}

```

## disassembly

```asm
0x140045798  mov     rax, rsp
0x14004579b  mov     [rax+8], rbx
0x14004579f  mov     [rax+10h], rsi
0x1400457a3  push    rdi
0x1400457a4  sub     rsp, 20h
0x1400457a8  mov     rsi, r9
0x1400457ab  mov     qword ptr [r9], 0
0x1400457b2  lea     r9, [rax+20h]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x1400457b6  mov     qword ptr [rax+20h], 0
0x1400457be  mov     rbx, rcx
0x1400457c1  call    ?NewMetadata@VMX_PHYSICAL_DISK@@AEAAJPEAVVMX_PACK@@PEAU_DISK_GEOMETRY@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::NewMetadata(VMX_PACK *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x1400457c6  mov     edi, eax
0x1400457c8  test    eax, eax
0x1400457ca  jns     short loc_14004580C
0x1400457cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400457d3  lea     rdx, WPP_GLOBAL_Control
0x1400457da  cmp     rcx, rdx
0x1400457dd  jz      short loc_140045805
0x1400457df  mov     edx, [rcx+2Ch]
0x1400457e2  test    dl, 10h
0x1400457e5  jz      short loc_140045805
0x1400457e7  cmp     byte ptr [rcx+29h], 2
0x1400457eb  jb      short loc_140045805
0x1400457ed  mov     edx, 12h
0x1400457f2  mov     rcx, [rcx+18h]
0x1400457f6  lea     r8, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids
0x1400457fd  mov     r9d, edi
0x140045800  call    WPP_SF_d
0x140045805  mov     eax, edi
0x140045807  jmp     loc_1400458D0
0x14004580c  mov     dl, 1; unsigned __int8
0x14004580e  mov     rcx, rbx; this
0x140045811  call    ?ZeroPrivateRegion@VMX_PHYSICAL_DISK@@QEAAJE@Z; VMX_PHYSICAL_DISK::ZeroPrivateRegion(uchar)
0x140045816  mov     edi, eax
0x140045818  mov     rcx, rbx; this
0x14004581b  test    eax, eax
0x14004581d  jns     short loc_140045863
0x14004581f  mov     rdx, [rsp+28h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140045824  call    ?DeletePrivateRegion@VMX_PHYSICAL_DISK@@QEAAXPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::DeletePrivateRegion(_DRIVE_LAYOUT_INFORMATION_EX *)
0x140045829  mov     rcx, [rsp+28h+P]; P
0x14004582e  xor     edx, edx; Tag
0x140045830  call    cs:__imp_ExFreePoolWithTag
0x140045837  nop     dword ptr [rax+rax+00h]
0x14004583c  mov     rcx, cs:WPP_GLOBAL_Control
0x140045843  lea     rdx, WPP_GLOBAL_Control
0x14004584a  cmp     rcx, rdx
0x14004584d  jz      short loc_140045805
0x14004584f  mov     eax, [rcx+2Ch]
0x140045852  test    al, 10h
0x140045854  jz      short loc_140045805
0x140045856  cmp     byte ptr [rcx+29h], 2
0x14004585a  jb      short loc_140045805
0x14004585c  mov     edx, 13h
0x140045861  jmp     short loc_1400457F2
0x140045863  xor     edx, edx; unsigned __int8
0x140045865  call    ?WriteMetadata@VMX_PHYSICAL_DISK@@QEAAJE@Z; VMX_PHYSICAL_DISK::WriteMetadata(uchar)
0x14004586a  mov     edi, eax
0x14004586c  test    eax, eax
0x14004586e  jns     short loc_1400458C6
0x140045870  mov     rdx, [rsp+28h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140045875  mov     rcx, rbx; this
0x140045878  call    ?DeletePrivateRegion@VMX_PHYSICAL_DISK@@QEAAXPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::DeletePrivateRegion(_DRIVE_LAYOUT_INFORMATION_EX *)
0x14004587d  mov     rcx, [rsp+28h+P]; P
0x140045882  xor     edx, edx; Tag
0x140045884  call    cs:__imp_ExFreePoolWithTag
0x14004588b  nop     dword ptr [rax+rax+00h]
0x140045890  mov     rcx, cs:WPP_GLOBAL_Control
0x140045897  lea     rdx, WPP_GLOBAL_Control
0x14004589e  cmp     rcx, rdx
0x1400458a1  jz      loc_140045805
0x1400458a7  mov     eax, [rcx+2Ch]
0x1400458aa  test    al, 10h
0x1400458ac  jz      loc_140045805
0x1400458b2  cmp     byte ptr [rcx+29h], 2
0x1400458b6  jb      loc_140045805
0x1400458bc  mov     edx, 14h
0x1400458c1  jmp     loc_1400457F2
0x1400458c6  mov     rax, [rsp+28h+P]
0x1400458cb  mov     [rsi], rax
0x1400458ce  xor     eax, eax
0x1400458d0  mov     rbx, [rsp+28h+arg_0]
0x1400458d5  mov     rsi, [rsp+28h+arg_8]
0x1400458da  add     rsp, 20h
0x1400458de  pop     rdi
0x1400458df  retn
```

# VmpQueryInterfaceName(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140016320`
- end: `0x1400163d9`
- name: `?VmpQueryInterfaceName@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140005240`
- `0x140016320`

## pseudocode

```c
__int64 __fastcall VmpQueryInterfaceName(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  char v5; // cl
  __int64 v6; // rax
  struct _IRP *MasterIrp; // rsi
  unsigned int v8; // edi
  __int64 v9; // rdx
  __int64 result; // rax

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->Parameters.Read.Length < 2 )
    return 3221225485LL;
  v5 = *((_BYTE *)a1 + 152);
  v6 = 168;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  if ( v5 )
    v6 = 184;
  MasterIrp->Type = *(_WORD *)((char *)a1 + v6);
  a2->IoStatus.Information = 2;
  v8 = (unsigned __int16)MasterIrp->Type + 2;
  if ( CurrentStackLocation->Parameters.Read.Length < v8 )
    return 2147483653LL;
  v9 = 176;
  if ( v5 )
    v9 = 192;
  memmove(&MasterIrp->Size, *(const void **)((char *)a1 + v9), (unsigned __int16)MasterIrp->Type);
  if ( a2->RequestorMode )
    *(&MasterIrp->Size + 1) = 92;
  result = 0;
  a2->IoStatus.Information = v8;
  return result;
}

```

## disassembly

```asm
0x140016320  push    rbx
0x140016322  sub     rsp, 20h
0x140016326  mov     rbx, rdx
0x140016329  mov     r9, rcx
0x14001632c  mov     rdx, [rdx+0B8h]
0x140016333  cmp     dword ptr [rdx+8], 2
0x140016337  jb      loc_1400163BE
0x14001633d  movzx   ecx, byte ptr [rcx+98h]
0x140016344  mov     eax, 0A8h
0x140016349  test    cl, cl
0x14001634b  mov     [rsp+28h+arg_0], rsi
0x140016350  mov     rsi, [rbx+18h]
0x140016354  mov     r8d, 0B8h
0x14001635a  cmovnz  eax, r8d
0x14001635e  mov     [rsp+28h+arg_8], rdi
0x140016363  movzx   eax, word ptr [rax+r9]
0x140016368  mov     [rsi], ax
0x14001636b  mov     qword ptr [rbx+38h], 2
0x140016373  movzx   eax, word ptr [rsi]
0x140016376  lea     edi, [rax+2]
0x140016379  cmp     [rdx+8], edi
0x14001637c  jb      short loc_1400163CA
0x14001637e  test    cl, cl
0x140016380  mov     r10d, 0C0h
0x140016386  mov     edx, 0B0h
0x14001638b  lea     rcx, [rsi+2]; void *
0x14001638f  cmovnz  edx, r10d
0x140016393  mov     r8d, eax; Size
0x140016396  mov     rdx, [rdx+r9]; Src
0x14001639a  call    memmove
0x14001639f  cmp     byte ptr [rbx+40h], 0
0x1400163a3  jnz     short loc_1400163D1
0x1400163a5  mov     ecx, edi
0x1400163a7  xor     eax, eax
0x1400163a9  mov     [rbx+38h], rcx
0x1400163ad  mov     rsi, [rsp+28h+arg_0]
0x1400163b2  mov     rdi, [rsp+28h+arg_8]
0x1400163b7  add     rsp, 20h
0x1400163bb  pop     rbx
0x1400163bc  retn
0x1400163be  mov     eax, 0C000000Dh
0x1400163c3  add     rsp, 20h
0x1400163c7  pop     rbx
0x1400163c8  retn
0x1400163ca  mov     eax, 80000005h
0x1400163cf  jmp     short loc_1400163AD
0x1400163d1  mov     word ptr [rsi+4], 5Ch ; '\'
0x1400163d7  jmp     short loc_1400163A5
```

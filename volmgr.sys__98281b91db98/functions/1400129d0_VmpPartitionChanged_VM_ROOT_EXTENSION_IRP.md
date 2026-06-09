# VmpPartitionChanged(VM_ROOT_EXTENSION *,_IRP *)

- ea: `0x1400129d0`
- end: `0x140012b33`
- name: `?VmpPartitionChanged@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z`
- size: `355`
- prototype: `__int64 __fastcall(struct VM_ROOT_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140002ea0`

## callees

- `0x140002db0`
- `0x140003170`
- `0x140003990`
- `0x1400129d0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140012af1`
- `ntoskrnl!ObfDereferenceObject` at `0x140012af1`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140012a95`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140012a95`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012b08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012b08`
- `ntoskrnl!ExAllocatePool2` at `0x140012a42`
- `ntoskrnl!ExAllocatePool2` at `0x140012a42`

## pseudocode

```c
__int64 __fastcall VmpPartitionChanged(struct VM_ROOT_EXTENSION *a1, struct _IRP *a2)
{
  unsigned int v3; // ebx
  struct _IRP *MasterIrp; // r14
  __int64 *v5; // rsi
  __int64 *i; // rcx
  __int64 Pool2; // rax
  _DWORD *v8; // rbx
  __int64 *v9; // rcx
  unsigned int v10; // ebp
  __int64 v11; // rdi
  __int64 j; // rdi

  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options >= 0x18 )
  {
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    VmpAcquireDevices(a1);
    v5 = (__int64 *)((char *)a1 + 208);
    for ( i = (__int64 *)*((_QWORD *)a1 + 26); ; i = (__int64 *)*i )
    {
      if ( i == v5 )
      {
        v3 = -1073741811;
        goto LABEL_25;
      }
      if ( *((_BYTE *)i + 124) && !*((_BYTE *)i + 394) && i[39] == *(_QWORD *)&MasterIrp->Type )
        break;
    }
    Pool2 = ExAllocatePool2(258, 16, 538987862);
    v8 = (_DWORD *)Pool2;
    if ( !Pool2 )
    {
      v3 = -1073741670;
LABEL_25:
      VmpReleaseDevices((struct _KMUTANT *)a1);
      return v3;
    }
    v9 = (__int64 *)*v5;
    v10 = 0;
    *(_DWORD *)Pool2 = 0;
    while ( v9 != v5 )
    {
      if ( *((_BYTE *)v9 + 124) && !*((_BYTE *)v9 + 394) && v9[39] == *(_QWORD *)&MasterIrp->Type )
      {
        *(_QWORD *)(Pool2 + 8) = IoGetAttachedDeviceReference((PDEVICE_OBJECT)*(v9 - 4));
        v10 = 1;
        break;
      }
      v9 = (__int64 *)*v9;
    }
    *v8 = v10;
    VmpReleaseDevices((struct _KMUTANT *)a1);
    if ( v10 )
    {
      v11 = 0;
      do
      {
        VmpSendDeviceControl(*(PDEVICE_OBJECT *)&v8[2 * v11 + 2], 0x560054u, 0, 0, 0, 0);
        v11 = (unsigned int)(v11 + 1);
      }
      while ( (unsigned int)v11 < v10 );
    }
    for ( j = 0; (unsigned int)j < v10; j = (unsigned int)(j + 1) )
      ObfDereferenceObject(*(PVOID *)&v8[2 * j + 2]);
    ExFreePoolWithTag(v8, 0);
    return 0;
  }
  else
  {
    return (unsigned int)-1073741811;
  }
}

```

## disassembly

```asm
0x1400129d0  push    rbx
0x1400129d2  push    rbp
0x1400129d3  push    rsi
0x1400129d4  push    rdi
0x1400129d5  push    r14
0x1400129d7  sub     rsp, 30h
0x1400129db  mov     rax, [rdx+0B8h]
0x1400129e2  mov     rdi, rcx
0x1400129e5  cmp     dword ptr [rax+10h], 18h
0x1400129e9  jnb     short loc_1400129F5
0x1400129eb  mov     ebx, 0C000000Dh
0x1400129f0  jmp     loc_140012B25
0x1400129f5  mov     r14, [rdx+18h]
0x1400129f9  call    ?VmpAcquireDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireDevices(VM_ROOT_EXTENSION *)
0x1400129fe  lea     rsi, [rdi+0D0h]
0x140012a05  mov     rcx, [rsi]
0x140012a08  cmp     rcx, rsi
0x140012a0b  jz      loc_140012B18
0x140012a11  mov     al, [rcx+7Ch]
0x140012a14  test    al, al
0x140012a16  jz      short loc_140012A2D
0x140012a18  cmp     byte ptr [rcx+18Ah], 0
0x140012a1f  jnz     short loc_140012A2D
0x140012a21  mov     rax, [r14]
0x140012a24  cmp     [rcx+138h], rax
0x140012a2b  jz      short loc_140012A32
0x140012a2d  mov     rcx, [rcx]
0x140012a30  jmp     short loc_140012A08
0x140012a32  mov     edx, 10h
0x140012a37  mov     ecx, 102h
0x140012a3c  mov     r8d, 20204D56h
0x140012a42  call    cs:__imp_ExAllocatePool2
0x140012a49  nop     dword ptr [rax+rax+00h]
0x140012a4e  mov     rbx, rax
0x140012a51  test    rax, rax
0x140012a54  jnz     short loc_140012A60
0x140012a56  mov     ebx, 0C000009Ah
0x140012a5b  jmp     loc_140012B1D
0x140012a60  mov     rcx, [rsi]
0x140012a63  xor     ebp, ebp
0x140012a65  mov     dword ptr [rax], 0
0x140012a6b  cmp     rcx, rsi
0x140012a6e  jz      short loc_140012AAA
0x140012a70  mov     al, [rcx+7Ch]
0x140012a73  test    al, al
0x140012a75  jz      short loc_140012A8C
0x140012a77  cmp     [rcx+18Ah], bpl
0x140012a7e  jnz     short loc_140012A8C
0x140012a80  mov     rax, [r14]
0x140012a83  cmp     [rcx+138h], rax
0x140012a8a  jz      short loc_140012A91
0x140012a8c  mov     rcx, [rcx]
0x140012a8f  jmp     short loc_140012A6B
0x140012a91  mov     rcx, [rcx-20h]; DeviceObject
0x140012a95  call    cs:__imp_IoGetAttachedDeviceReference
0x140012a9c  nop     dword ptr [rax+rax+00h]
0x140012aa1  mov     [rbx+8], rax
0x140012aa5  mov     ebp, 1
0x140012aaa  mov     rcx, rdi; struct VM_ROOT_EXTENSION *
0x140012aad  mov     [rbx], ebp
0x140012aaf  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x140012ab4  test    ebp, ebp
0x140012ab6  jz      short loc_140012AE6
0x140012ab8  xor     edi, edi
0x140012aba  mov     rcx, [rbx+rdi*8+8]; DeviceObject
0x140012abf  xor     r9d, r9d; InputBufferLength
0x140012ac2  mov     [rsp+58h+var_30], 0; ULONG
0x140012aca  xor     r8d, r8d; InputBuffer
0x140012acd  mov     edx, 560054h; IoControlCode
0x140012ad2  mov     [rsp+58h+var_38], 0; PVOID
0x140012adb  call    VmpSendDeviceControl
0x140012ae0  inc     edi
0x140012ae2  cmp     edi, ebp
0x140012ae4  jb      short loc_140012ABA
0x140012ae6  xor     edi, edi
0x140012ae8  test    ebp, ebp
0x140012aea  jz      short loc_140012B03
0x140012aec  mov     rcx, [rbx+rdi*8+8]; Object
0x140012af1  call    cs:__imp_ObfDereferenceObject
0x140012af8  nop     dword ptr [rax+rax+00h]
0x140012afd  inc     edi
0x140012aff  cmp     edi, ebp
0x140012b01  jb      short loc_140012AEC
0x140012b03  xor     edx, edx; Tag
0x140012b05  mov     rcx, rbx; P
0x140012b08  call    cs:__imp_ExFreePoolWithTag
0x140012b0f  nop     dword ptr [rax+rax+00h]
0x140012b14  xor     ebx, ebx
0x140012b16  jmp     short loc_140012B25
0x140012b18  mov     ebx, 0C000000Dh
0x140012b1d  mov     rcx, rdi; struct VM_ROOT_EXTENSION *
0x140012b20  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x140012b25  mov     eax, ebx
0x140012b27  add     rsp, 30h
0x140012b2b  pop     r14
0x140012b2d  pop     rdi
0x140012b2e  pop     rsi
0x140012b2f  pop     rbp
0x140012b30  pop     rbx
0x140012b31  retn
```

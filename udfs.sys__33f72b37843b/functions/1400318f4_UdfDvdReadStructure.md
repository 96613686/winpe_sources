# UdfDvdReadStructure

- ea: `0x1400318f4`
- end: `0x1400319f0`
- name: `UdfDvdReadStructure`
- size: `252`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140054830`

## callees

- `0x1400030e0`
- `0x1400318f4`

## import_xrefs

- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14003196c`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14003196c`
- `ntoskrnl!IofCallDriver` at `0x1400319b1`
- `ntoskrnl!IofCallDriver` at `0x1400319b1`

## pseudocode

```c
__int64 __fastcall UdfDvdReadStructure(_QWORD *a1, IRP *a2, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IRP *MasterIrp; // r14
  unsigned int v8; // ebx
  __int64 v10; // [rsp+78h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v10 = 0;
  if ( CurrentStackLocation->Parameters.Create.Options == 17
    && (MasterIrp = a2->AssociatedIrp.MasterIrp, *(_QWORD *)&MasterIrp->Type < *(_QWORD *)(a3 + 32))
    && FsRtlLookupLargeMcbEntry(
         (PLARGE_MCB)(a3 + 232),
         (unsigned int)(*(_QWORD *)&MasterIrp->Type >> *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 136) + 8LL) + 72LL)),
         &v10,
         0,
         0,
         0,
         0)
    && v10 != -1 )
  {
    *(_QWORD *)&MasterIrp->Type = v10 << *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 136) + 8LL) + 72LL);
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    v8 = IofCallDriver(*(PDEVICE_OBJECT *)(a1[2] + 24LL), a2);
    UdfCompleteRequest(a1, 0, 0);
    return v8;
  }
  else
  {
    UdfCompleteRequest(a1, a2, -1073741811);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x1400318f4  mov     r11, rsp
0x1400318f7  push    rbx
0x1400318f8  push    rsi
0x1400318f9  push    rdi
0x1400318fa  push    r14
0x1400318fc  sub     rsp, 48h
0x140031900  mov     rax, [rdx+0B8h]
0x140031907  mov     rdi, r8
0x14003190a  mov     qword ptr [r11+10h], 0
0x140031912  mov     rbx, rdx
0x140031915  mov     rsi, rcx
0x140031918  cmp     dword ptr [rax+10h], 11h
0x14003191c  jnz     loc_1400319D0
0x140031922  mov     r14, [rdx+18h]
0x140031926  mov     rdx, [r14]
0x140031929  cmp     rdx, [r8+20h]
0x14003192d  jge     loc_1400319D0
0x140031933  mov     rax, [r8+88h]
0x14003193a  xor     r9d, r9d; SectorCountFromLbn
0x14003193d  mov     qword ptr [r11-38h], 0
0x140031945  mov     qword ptr [r11-40h], 0
0x14003194d  mov     qword ptr [r11-48h], 0
0x140031955  mov     rcx, [rax+8]
0x140031959  mov     ecx, [rcx+48h]
0x14003195c  shr     rdx, cl
0x14003195f  lea     rcx, [r8+0E8h]; Mcb
0x140031966  mov     edx, edx; Vbn
0x140031968  lea     r8, [r11+10h]; Lbn
0x14003196c  call    cs:__imp_FsRtlLookupLargeMcbEntry
0x140031973  nop     dword ptr [rax+rax+00h]
0x140031978  test    al, al
0x14003197a  jz      short loc_1400319D0
0x14003197c  mov     rax, [rsp+68h+arg_8]
0x140031981  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140031985  jz      short loc_1400319D0
0x140031987  mov     rcx, [rdi+88h]
0x14003198e  mov     rdx, rbx; Irp
0x140031991  mov     rcx, [rcx+8]
0x140031995  mov     ecx, [rcx+48h]
0x140031998  shl     rax, cl
0x14003199b  mov     [r14], rax
0x14003199e  inc     byte ptr [rbx+43h]
0x1400319a1  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x1400319a9  mov     rcx, [rsi+10h]
0x1400319ad  mov     rcx, [rcx+18h]; DeviceObject
0x1400319b1  call    cs:__imp_IofCallDriver
0x1400319b8  nop     dword ptr [rax+rax+00h]
0x1400319bd  xor     r8d, r8d
0x1400319c0  xor     edx, edx
0x1400319c2  mov     rcx, rsi
0x1400319c5  mov     ebx, eax
0x1400319c7  call    UdfCompleteRequest
0x1400319cc  mov     eax, ebx
0x1400319ce  jmp     short loc_1400319E5
0x1400319d0  mov     edi, 0C000000Dh
0x1400319d5  mov     rdx, rbx
0x1400319d8  mov     r8d, edi
0x1400319db  mov     rcx, rsi
0x1400319de  call    UdfCompleteRequest
0x1400319e3  mov     eax, edi
0x1400319e5  add     rsp, 48h
0x1400319e9  pop     r14
0x1400319eb  pop     rdi
0x1400319ec  pop     rsi
0x1400319ed  pop     rbx
0x1400319ee  retn
```

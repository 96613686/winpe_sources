# SubmitUrb

- ea: `0x14000b40c`
- end: `0x14000b4b5`
- name: `SubmitUrb`
- size: `169`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140001314`
- `0x14000aed0`
- `0x1400114d8`
- `0x1400133e0`
- `0x140023214`
- `0x14002b99c`
- `0x14002c430`
- `0x14002ca84`

## callees

- `0x14000b40c`
- `0x140029b30`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000b48f`
- `ntoskrnl!IoFreeIrp` at `0x14000b48f`
- `ntoskrnl!IoAllocateIrp` at `0x14000b42a`
- `ntoskrnl!IoAllocateIrp` at `0x14000b42a`

## pseudocode

```c
__int64 __fastcall SubmitUrb(__int64 a1, _FILE_OBJECT *a2, __int64 a3, __int64 a4, __int64 a5, char a6)
{
  PIRP Irp; // rax
  IRP *v9; // rdi
  _IO_STACK_LOCATION *CurrentStackLocation; // r8
  unsigned int v11; // ebx

  Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(a1 + 40) + 76LL), 0);
  v9 = Irp;
  if ( Irp )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].MajorFunction = 15;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 2228227;
    if ( a6 && (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 1344) + 216LL) - 1538) <= 0xFFFFF9FC )
      CurrentStackLocation[-1].FileObject = a2;
    CurrentStackLocation[-1].Parameters.WMI.ProviderId = (unsigned __int64)a2;
    v11 = CallNextDriverSync(a1, Irp);
    IoFreeIrp(v9);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v11;
}

```

## disassembly

```asm
0x14000b40c  mov     [rsp+arg_0], rbx
0x14000b411  mov     [rsp+arg_8], rsi
0x14000b416  push    rdi
0x14000b417  sub     rsp, 20h
0x14000b41b  mov     rbx, rcx
0x14000b41e  mov     rsi, rdx
0x14000b421  mov     rcx, [rcx+28h]
0x14000b425  xor     edx, edx; ChargeQuota
0x14000b427  mov     cl, [rcx+4Ch]; StackSize
0x14000b42a  call    cs:__imp_IoAllocateIrp
0x14000b431  nop     dword ptr [rax+rax+00h]
0x14000b436  mov     rdi, rax
0x14000b439  test    rax, rax
0x14000b43c  jz      short loc_14000B4AE
0x14000b43e  cmp     [rsp+28h+arg_28], 0
0x14000b443  mov     r8, [rax+0B8h]
0x14000b44a  mov     byte ptr [r8-48h], 0Fh
0x14000b44f  mov     dword ptr [r8-30h], 220003h
0x14000b457  jz      short loc_14000B478
0x14000b459  mov     rcx, [rbx+540h]
0x14000b460  mov     edx, [rcx+0D8h]
0x14000b466  sub     edx, 602h
0x14000b46c  cmp     edx, 0FFFFF9FCh
0x14000b472  ja      short loc_14000B478
0x14000b474  mov     [r8-18h], rsi
0x14000b478  mov     [r8-40h], rsi
0x14000b47c  mov     rdx, rdi
0x14000b47f  mov     r8b, 1
0x14000b482  mov     rcx, rbx
0x14000b485  call    CallNextDriverSync
0x14000b48a  mov     rcx, rdi; Irp
0x14000b48d  mov     ebx, eax
0x14000b48f  call    cs:__imp_IoFreeIrp
0x14000b496  nop     dword ptr [rax+rax+00h]
0x14000b49b  mov     rsi, [rsp+28h+arg_8]
0x14000b4a0  mov     eax, ebx
0x14000b4a2  mov     rbx, [rsp+28h+arg_0]
0x14000b4a7  add     rsp, 20h
0x14000b4ab  pop     rdi
0x14000b4ac  retn
0x14000b4ae  mov     ebx, 0C000009Ah
0x14000b4b3  jmp     short loc_14000B49B
```

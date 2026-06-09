# UdfCommonPnp

- ea: `0x1400590b0`
- end: `0x1400591da`
- name: `UdfCommonPnp`
- size: `298`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400077f0`
- `0x1400094c0`

## callees

- `0x1400030e0`
- `0x140037544`
- `0x1400375d8`
- `0x140037770`
- `0x14003787c`
- `0x1400590b0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140059175`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400591af`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059175`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400591af`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400590d3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400590d3`
- `ntoskrnl!IofCallDriver` at `0x140059193`
- `ntoskrnl!IofCallDriver` at `0x140059193`

## pseudocode

```c
__int64 __fastcall UdfCommonPnp(_DWORD *a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  PDEVICE_OBJECT DeviceObject; // rbx
  struct _IRP **p_CurrentIrp; // rbx
  unsigned int v8; // ebx
  NTSTATUS v9; // eax
  NTSTATUS v10; // r8d
  IRP *v11; // rdx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  DeviceObject = CurrentStackLocation->DeviceObject;
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  if ( DeviceObject->Size != 2928 || (p_CurrentIrp = &DeviceObject[1].CurrentIrp) == 0 || *(_WORD *)p_CurrentIrp != 2354 )
  {
    ExReleaseResourceLite(&Resource);
    v8 = -1073741811;
    v11 = a2;
    v10 = -1073741811;
    goto LABEL_16;
  }
  a1[7] |= 4u;
  if ( !p_CurrentIrp[1] )
    goto LABEL_14;
  switch ( CurrentStackLocation->MinorFunction )
  {
    case 1u:
      return (unsigned int)UdfPnpQueryRemove(a1, a2, p_CurrentIrp);
    case 2u:
      return (unsigned int)UdfPnpRemove(a1, a2, p_CurrentIrp);
    case 3u:
      return (unsigned int)UdfPnpCancelRemove(a1, a2, p_CurrentIrp);
  }
  if ( CurrentStackLocation->MinorFunction != 23 )
  {
LABEL_14:
    ExReleaseResourceLite(&Resource);
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    v9 = IofCallDriver((PDEVICE_OBJECT)p_CurrentIrp[3], a2);
    v10 = 0;
    v8 = v9;
    v11 = 0;
LABEL_16:
    UdfCompleteRequest(a1, v11, v10);
    return v8;
  }
  return (unsigned int)UdfPnpSurpriseRemove((_DWORD)a1);
}

```

## disassembly

```asm
0x1400590b0  push    rbx
0x1400590b2  push    rbp
0x1400590b3  push    rsi
0x1400590b4  push    rdi
0x1400590b5  sub     rsp, 28h
0x1400590b9  mov     rbp, [rdx+0B8h]
0x1400590c0  mov     rdi, rdx
0x1400590c3  mov     rsi, rcx
0x1400590c6  mov     dl, 1; Wait
0x1400590c8  lea     rcx, Resource; Resource
0x1400590cf  mov     rbx, [rbp+28h]
0x1400590d3  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400590da  nop     dword ptr [rax+rax+00h]
0x1400590df  mov     eax, 0B70h
0x1400590e4  cmp     [rbx+2], ax
0x1400590e8  jnz     loc_1400591A8
0x1400590ee  add     rbx, 170h
0x1400590f5  jz      loc_1400591A8
0x1400590fb  mov     eax, 932h
0x140059100  cmp     [rbx], ax
0x140059103  jnz     loc_1400591A8
0x140059109  or      dword ptr [rsi+1Ch], 4
0x14005910d  cmp     qword ptr [rbx+8], 0
0x140059112  jz      short loc_14005916E
0x140059114  movzx   ecx, byte ptr [rbp+1]
0x140059118  sub     ecx, 1
0x14005911b  jz      short loc_14005915C
0x14005911d  sub     ecx, 1
0x140059120  jz      short loc_14005914C
0x140059122  sub     ecx, 1
0x140059125  jz      short loc_14005913C
0x140059127  cmp     ecx, 14h
0x14005912a  jnz     short loc_14005916E
0x14005912c  mov     r8, rbx
0x14005912f  mov     rdx, rdi
0x140059132  mov     rcx, rsi
0x140059135  call    UdfPnpSurpriseRemove
0x14005913a  jmp     short loc_14005916A
0x14005913c  mov     r8, rbx
0x14005913f  mov     rdx, rdi
0x140059142  mov     rcx, rsi
0x140059145  call    UdfPnpCancelRemove
0x14005914a  jmp     short loc_14005916A
0x14005914c  mov     r8, rbx
0x14005914f  mov     rdx, rdi
0x140059152  mov     rcx, rsi
0x140059155  call    UdfPnpRemove
0x14005915a  jmp     short loc_14005916A
0x14005915c  mov     r8, rbx
0x14005915f  mov     rdx, rdi
0x140059162  mov     rcx, rsi
0x140059165  call    UdfPnpQueryRemove
0x14005916a  mov     ebx, eax
0x14005916c  jmp     short loc_1400591CE
0x14005916e  lea     rcx, Resource; Resource
0x140059175  call    cs:__imp_ExReleaseResourceLite
0x14005917c  nop     dword ptr [rax+rax+00h]
0x140059181  inc     byte ptr [rdi+43h]
0x140059184  mov     rdx, rdi; Irp
0x140059187  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x14005918f  mov     rcx, [rbx+18h]; DeviceObject
0x140059193  call    cs:__imp_IofCallDriver
0x14005919a  nop     dword ptr [rax+rax+00h]
0x14005919f  xor     r8d, r8d
0x1400591a2  mov     ebx, eax
0x1400591a4  xor     edx, edx
0x1400591a6  jmp     short loc_1400591C6
0x1400591a8  lea     rcx, Resource; Resource
0x1400591af  call    cs:__imp_ExReleaseResourceLite
0x1400591b6  nop     dword ptr [rax+rax+00h]
0x1400591bb  mov     ebx, 0C000000Dh
0x1400591c0  mov     rdx, rdi
0x1400591c3  mov     r8d, ebx
0x1400591c6  mov     rcx, rsi
0x1400591c9  call    UdfCompleteRequest
0x1400591ce  mov     eax, ebx
0x1400591d0  add     rsp, 28h
0x1400591d4  pop     rdi
0x1400591d5  pop     rsi
0x1400591d6  pop     rbp
0x1400591d7  pop     rbx
0x1400591d8  retn
```

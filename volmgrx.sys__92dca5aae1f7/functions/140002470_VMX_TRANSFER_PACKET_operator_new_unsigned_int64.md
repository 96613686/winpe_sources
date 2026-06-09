# VMX_TRANSFER_PACKET::operator new(unsigned __int64)

- ea: `0x140002470`
- end: `0x14000263b`
- name: `??2VMX_TRANSFER_PACKET@@SAPEAX_K@Z`
- size: `459`
- prototype: `_BYTE *__fastcall(unsigned __int64)`
- caller_count: `34`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140001580`
- `0x140001948`
- `0x140001ab0`
- `0x140003774`
- `0x140003f3c`
- `0x1400040f0`
- `0x140007bb0`
- `0x140008300`
- `0x1400087d0`
- `0x14000de34`
- `0x14000e088`
- `0x14000e2d8`
- `0x14000e464`
- `0x14000e5b4`
- `0x14000ea38`
- `0x14000fad8`
- `0x140010c44`
- `0x140010e0c`
- `0x140010f4c`
- `0x140011410`
- `0x140011510`
- `0x140012244`
- `0x140012b90`
- `0x140014fc0`
- `0x1400153e0`
- `0x140017cd0`
- `0x14003aa3c`
- `0x14003c2e0`
- `0x14004be00`
- `0x14004c694`
- `0x14004ca00`
- `0x14004cd24`
- `0x14004d1dc`
- `0x14004d44c`

## callees

- `0x140002470`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400024e8`
- `ntoskrnl!ExAllocatePool2` at `0x140002518`
- `ntoskrnl!ExAllocatePool2` at `0x1400025c8`
- `ntoskrnl!ExAllocatePool2` at `0x1400024e8`
- `ntoskrnl!ExAllocatePool2` at `0x140002518`
- `ntoskrnl!ExAllocatePool2` at `0x1400025c8`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140002556`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140002594`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000260a`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140002556`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140002594`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000260a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002489`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400024bd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000261d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002489`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400024bd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000261d`

## pseudocode

```c
_BYTE *__fastcall VMX_TRANSFER_PACKET::operator new(unsigned __int64 a1)
{
  struct _NPAGED_LOOKASIDE_LIST *DeviceExtension; // rcx
  _BYTE *result; // rax
  struct _LIST_ENTRY *Flink; // rcx
  struct _NPAGED_LOOKASIDE_LIST *Pool2; // rax
  struct _LIST_ENTRY *v5; // rax
  struct _NPAGED_LOOKASIDE_LIST *v6; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v7; // rax

  if ( a1 <= 0xC0 )
  {
    DeviceExtension = (struct _NPAGED_LOOKASIDE_LIST *)WPP_MAIN_CB.DeviceExtension;
    if ( WPP_MAIN_CB.DeviceExtension )
      goto LABEL_3;
    Pool2 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocatePool2(66, 128, 538996054);
    WPP_MAIN_CB.DeviceExtension = Pool2;
    if ( Pool2 )
    {
      ExInitializeNPagedLookasideList(Pool2, 0, 0, 0x200u, 0xC0u, 0x31506D56u, 0x20u);
      DeviceExtension = (struct _NPAGED_LOOKASIDE_LIST *)WPP_MAIN_CB.DeviceExtension;
LABEL_3:
      result = ExAllocateFromNPagedLookasideList(DeviceExtension);
      if ( result )
        result[80] = 1;
      return result;
    }
    return 0;
  }
  if ( a1 > 0x128 )
  {
    v6 = *(struct _NPAGED_LOOKASIDE_LIST **)&WPP_MAIN_CB.DeviceType;
    if ( !*(_QWORD *)&WPP_MAIN_CB.DeviceType )
    {
      v7 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocatePool2(66, 128, 538996054);
      *(_QWORD *)&WPP_MAIN_CB.DeviceType = v7;
      if ( !v7 )
        return 0;
      ExInitializeNPagedLookasideList(v7, 0, 0, 0x200u, 0x308u, 0x33506D56u, 0x20u);
      v6 = *(struct _NPAGED_LOOKASIDE_LIST **)&WPP_MAIN_CB.DeviceType;
    }
    result = ExAllocateFromNPagedLookasideList(v6);
    if ( result )
      result[80] = 3;
  }
  else
  {
    Flink = WPP_MAIN_CB.Queue.ListEntry.Flink;
    if ( !WPP_MAIN_CB.Queue.ListEntry.Flink )
    {
      v5 = (struct _LIST_ENTRY *)ExAllocatePool2(66, 128, 538996054);
      WPP_MAIN_CB.Queue.ListEntry.Flink = v5;
      if ( !v5 )
        return 0;
      ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v5, 0, 0, 0x200u, 0x128u, 0x32506D56u, 0x20u);
      Flink = WPP_MAIN_CB.Queue.ListEntry.Flink;
    }
    result = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)Flink);
    if ( result )
      result[80] = 2;
  }
  return result;
}

```

## disassembly

```asm
0x140002470  sub     rsp, 48h
0x140002474  cmp     rcx, 0C0h
0x14000247b  ja      short loc_1400024A4
0x14000247d  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension; Lookaside
0x140002484  test    rcx, rcx
0x140002487  jz      short loc_1400024D8
0x140002489  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140002490  nop     dword ptr [rax+rax+00h]
0x140002495  test    rax, rax
0x140002498  jz      short loc_14000249E
0x14000249a  mov     byte ptr [rax+50h], 1
0x14000249e  add     rsp, 48h
0x1400024a2  retn
0x1400024a4  cmp     rcx, 128h
0x1400024ab  ja      loc_1400025AC
0x1400024b1  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue; Lookaside
0x1400024b8  test    rcx, rcx
0x1400024bb  jz      short loc_140002508
0x1400024bd  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400024c4  nop     dword ptr [rax+rax+00h]
0x1400024c9  test    rax, rax
0x1400024cc  jz      short loc_14000249E
0x1400024ce  mov     byte ptr [rax+50h], 2
0x1400024d2  add     rsp, 48h
0x1400024d6  retn
0x1400024d8  mov     edx, 80h
0x1400024dd  mov     r8d, 20206D56h
0x1400024e3  mov     ecx, 42h ; 'B'
0x1400024e8  call    cs:__imp_ExAllocatePool2
0x1400024ef  nop     dword ptr [rax+rax+00h]
0x1400024f4  mov     cs:WPP_MAIN_CB.DeviceExtension, rax
0x1400024fb  test    rax, rax
0x1400024fe  jnz     short loc_14000256E
0x140002500  xor     eax, eax
0x140002502  add     rsp, 48h
0x140002506  retn
0x140002508  mov     edx, 80h
0x14000250d  mov     r8d, 20206D56h
0x140002513  mov     ecx, 42h ; 'B'
0x140002518  call    cs:__imp_ExAllocatePool2
0x14000251f  nop     dword ptr [rax+rax+00h]
0x140002524  mov     qword ptr cs:WPP_MAIN_CB.Queue, rax
0x14000252b  test    rax, rax
0x14000252e  jz      short loc_140002500
0x140002530  mov     [rsp+48h+Depth], 20h ; ' '; Depth
0x140002537  mov     r9d, 200h; Flags
0x14000253d  mov     [rsp+48h+Tag], 32506D56h; Tag
0x140002545  xor     r8d, r8d; Free
0x140002548  xor     edx, edx; Allocate
0x14000254a  mov     [rsp+48h+Size], 128h; Size
0x140002553  mov     rcx, rax; Lookaside
0x140002556  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000255d  nop     dword ptr [rax+rax+00h]
0x140002562  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140002569  jmp     loc_1400024BD
0x14000256e  mov     [rsp+48h+Depth], 20h ; ' '; Depth
0x140002575  mov     r9d, 200h; Flags
0x14000257b  mov     [rsp+48h+Tag], 31506D56h; Tag
0x140002583  xor     r8d, r8d; Free
0x140002586  xor     edx, edx; Allocate
0x140002588  mov     [rsp+48h+Size], 0C0h; Size
0x140002591  mov     rcx, rax; Lookaside
0x140002594  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000259b  nop     dword ptr [rax+rax+00h]
0x1400025a0  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400025a7  jmp     loc_140002489
0x1400025ac  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceType
0x1400025b3  test    rcx, rcx
0x1400025b6  jnz     short loc_14000261D
0x1400025b8  mov     edx, 80h
0x1400025bd  mov     r8d, 20206D56h
0x1400025c3  mov     ecx, 42h ; 'B'
0x1400025c8  call    cs:__imp_ExAllocatePool2
0x1400025cf  nop     dword ptr [rax+rax+00h]
0x1400025d4  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rax
0x1400025db  test    rax, rax
0x1400025de  jz      loc_140002500
0x1400025e4  mov     [rsp+48h+Depth], 20h ; ' '; Depth
0x1400025eb  mov     r9d, 200h; Flags
0x1400025f1  mov     [rsp+48h+Tag], 33506D56h; Tag
0x1400025f9  xor     r8d, r8d; Free
0x1400025fc  xor     edx, edx; Allocate
0x1400025fe  mov     [rsp+48h+Size], 308h; Size
0x140002607  mov     rcx, rax; Lookaside
0x14000260a  call    cs:__imp_ExInitializeNPagedLookasideList
0x140002611  nop     dword ptr [rax+rax+00h]
0x140002616  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceType; Lookaside
0x14000261d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140002624  nop     dword ptr [rax+rax+00h]
0x140002629  test    rax, rax
0x14000262c  jz      loc_14000249E
0x140002632  mov     byte ptr [rax+50h], 3
0x140002636  jmp     loc_14000249E
```

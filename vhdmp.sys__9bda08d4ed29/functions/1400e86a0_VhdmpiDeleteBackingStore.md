# VhdmpiDeleteBackingStore

- ea: `0x1400e86a0`
- end: `0x1400e883c`
- name: `VhdmpiDeleteBackingStore`
- size: `412`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400cff1c`

## callees

- `0x140023980`
- `0x140026b08`
- `0x140036284`
- `0x14005dc30`
- `0x14009e12c`
- `0x1400b977c`
- `0x1400e86a0`
- `0x1400ebb10`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1400e8795`
- `ntoskrnl!IoFreeIrp` at `0x1400e8795`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400e8776`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400e8776`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400e8744`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400e8744`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e87e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e87e0`

## string_xrefs

- `0x1400e86ec`: `VhdmpiDeleteBackingStore`
- `0x1400e8824`: `VhdmpiDeleteBackingStore`
- `0x1400e880a`: `VhdmpiDeleteVhdBackingStore: leaving...`
- `0x1400e86cf`: `VhdmpiDeleteVhdBackingStore: enter... BackingStore: 0x%p`

## pseudocode

```c
void __fastcall VhdmpiDeleteBackingStore(__int64 *a1, __int64 a2)
{
  __int64 v3; // rax
  IRP *v4; // rcx
  void *v5; // rcx

  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
    TraceEvents(
      "VhdmpiDeleteBackingStore",
      0x641u,
      5u,
      0x10u,
      "VhdmpiDeleteVhdBackingStore: enter... BackingStore: 0x%p",
      a1);
  LOBYTE(a2) = 1;
  (*(void (__fastcall **)(__int64 *, __int64))(*a1 + 80))(a1, a2);
  v3 = *a1;
  *((_BYTE *)a1 + 8) = 0;
  (*(void (__fastcall **)(__int64 *))(v3 + 104))(a1);
  DvRundownWorkQueue(a1 + 149);
  DvRundownWorkQueue(a1 + 158);
  if ( *((_BYTE *)a1 + 856) )
  {
    ExDeleteResourceLite((PERESOURCE)(a1 + 108));
    *((_BYTE *)a1 + 856) = 0;
  }
  VhdmpiCleanupFileWrapper((struct _VHD_FILE_WRAPPER *)(a1 + 9));
  if ( *((_BYTE *)a1 + 1472) )
  {
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 168));
    *((_BYTE *)a1 + 1472) = 0;
  }
  v4 = (IRP *)a1[129];
  if ( v4 )
  {
    IoFreeIrp(v4);
    a1[129] = 0;
  }
  VhdmpiCleanupSrbPartHandling((struct _VHD_BACKING_STORE_HEADER *)a1);
  v5 = (void *)a1[185];
  if ( v5 )
    RmwDeletePackage(v5);
  if ( (__int64 *)a1[229] != a1 + 229 )
    __fastfail(0xEu);
  ExFreePoolWithTag(a1, 0x6C444856u);
  if ( (unsigned int)dword_1400876D0 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
      TraceEvents("VhdmpiDeleteBackingStore", 0x69Eu, 5u, 0x10u, "VhdmpiDeleteVhdBackingStore: leaving...");
  }
}

```

## disassembly

```asm
0x1400e86a0  mov     [rsp+arg_0], rbx
0x1400e86a5  push    rbp
0x1400e86a6  sub     rsp, 30h
0x1400e86aa  mov     eax, cs:dword_1400876D0
0x1400e86b0  mov     rbx, rcx
0x1400e86b3  mov     ebp, 10h
0x1400e86b8  cmp     eax, 5
0x1400e86bb  jbe     short loc_1400E86F8
0x1400e86bd  mov     edx, ebp
0x1400e86bf  lea     rcx, dword_1400876D0
0x1400e86c6  call    _tlgKeywordOn
0x1400e86cb  test    al, al
0x1400e86cd  jz      short loc_1400E86F8
0x1400e86cf  lea     rax, aVhdmpideletevh_0; "VhdmpiDeleteVhdBackingStore: enter... B"...
0x1400e86d6  mov     qword ptr [rsp+38h+var_10], rbx; char
0x1400e86db  mov     edx, 641h; int
0x1400e86e0  mov     [rsp+38h+var_18], rax; char *
0x1400e86e5  mov     r9d, ebp; int
0x1400e86e8  lea     r8d, [rbp-0Bh]; int
0x1400e86ec  lea     rcx, aVhdmpideleteba; "VhdmpiDeleteBackingStore"
0x1400e86f3  call    TraceEvents
0x1400e86f8  mov     rax, [rbx]
0x1400e86fb  mov     dl, 1
0x1400e86fd  mov     rcx, rbx
0x1400e8700  mov     rax, [rax+50h]
0x1400e8704  call    _guard_dispatch_icall
0x1400e8709  mov     rax, [rbx]
0x1400e870c  mov     rcx, rbx
0x1400e870f  mov     byte ptr [rbx+8], 0
0x1400e8713  mov     rax, [rax+68h]
0x1400e8717  call    _guard_dispatch_icall
0x1400e871c  lea     rcx, [rbx+4A8h]
0x1400e8723  call    DvRundownWorkQueue
0x1400e8728  lea     rcx, [rbx+4F0h]
0x1400e872f  call    DvRundownWorkQueue
0x1400e8734  cmp     byte ptr [rbx+358h], 0
0x1400e873b  jz      short loc_1400E8757
0x1400e873d  lea     rcx, [rbx+360h]; Resource
0x1400e8744  call    cs:__imp_ExDeleteResourceLite
0x1400e874b  nop     dword ptr [rax+rax+00h]
0x1400e8750  mov     byte ptr [rbx+358h], 0
0x1400e8757  mov     dl, [rbx+3CDh]
0x1400e875d  lea     rcx, [rbx+48h]; struct _VHD_FILE_WRAPPER *
0x1400e8761  call    VhdmpiCleanupFileWrapper
0x1400e8766  cmp     byte ptr [rbx+5C0h], 0
0x1400e876d  jz      short loc_1400E8789
0x1400e876f  lea     rcx, [rbx+540h]; Lookaside
0x1400e8776  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400e877d  nop     dword ptr [rax+rax+00h]
0x1400e8782  mov     byte ptr [rbx+5C0h], 0
0x1400e8789  mov     rcx, [rbx+408h]; Irp
0x1400e8790  test    rcx, rcx
0x1400e8793  jz      short loc_1400E87AC
0x1400e8795  call    cs:__imp_IoFreeIrp
0x1400e879c  nop     dword ptr [rax+rax+00h]
0x1400e87a1  mov     qword ptr [rbx+408h], 0
0x1400e87ac  mov     rcx, rbx; struct _VHD_BACKING_STORE_HEADER *
0x1400e87af  call    VhdmpiCleanupSrbPartHandling
0x1400e87b4  mov     rcx, [rbx+5C8h]; P
0x1400e87bb  test    rcx, rcx
0x1400e87be  jz      short loc_1400E87C5
0x1400e87c0  call    ?RmwDeletePackage@@YAXPEAU_RMW_STORE@@@Z; RmwDeletePackage(_RMW_STORE *)
0x1400e87c5  lea     rax, [rbx+728h]
0x1400e87cc  cmp     [rax], rax
0x1400e87cf  jz      short loc_1400E87D8
0x1400e87d1  mov     ecx, 0Eh
0x1400e87d6  int     29h; Win8: RtlFailFast(ecx)
0x1400e87d8  mov     edx, 6C444856h; Tag
0x1400e87dd  mov     rcx, rbx; P
0x1400e87e0  call    cs:__imp_ExFreePoolWithTag
0x1400e87e7  nop     dword ptr [rax+rax+00h]
0x1400e87ec  mov     eax, cs:dword_1400876D0
0x1400e87f2  cmp     eax, 5
0x1400e87f5  jbe     short loc_1400E8830
0x1400e87f7  mov     rdx, rbp
0x1400e87fa  lea     rcx, dword_1400876D0
0x1400e8801  call    _tlgKeywordOn
0x1400e8806  test    al, al
0x1400e8808  jz      short loc_1400E8830
0x1400e880a  lea     rax, aVhdmpideletevh_1; "VhdmpiDeleteVhdBackingStore: leaving..."
0x1400e8811  mov     edx, 69Eh; int
0x1400e8816  mov     r9d, ebp; int
0x1400e8819  mov     [rsp+38h+var_18], rax; char *
0x1400e881e  mov     r8d, 5; int
0x1400e8824  lea     rcx, aVhdmpideleteba; "VhdmpiDeleteBackingStore"
0x1400e882b  call    TraceEvents
0x1400e8830  mov     rbx, [rsp+38h+arg_0]
0x1400e8835  add     rsp, 30h
0x1400e8839  pop     rbp
0x1400e883a  retn
```

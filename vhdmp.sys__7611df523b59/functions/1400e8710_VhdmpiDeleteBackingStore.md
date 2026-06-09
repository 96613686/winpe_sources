# VhdmpiDeleteBackingStore

- ea: `0x1400e8710`
- end: `0x1400e88ac`
- name: `VhdmpiDeleteBackingStore`
- size: `412`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400cff8c`

## callees

- `0x140023560`
- `0x1400266e8`
- `0x140035e94`
- `0x14005d840`
- `0x14009e12c`
- `0x1400b978c`
- `0x1400e8710`
- `0x1400ebb80`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1400e8805`
- `ntoskrnl!IoFreeIrp` at `0x1400e8805`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400e87e6`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400e87e6`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400e87b4`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400e87b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e8850`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e8850`

## string_xrefs

- `0x1400e887a`: `VhdmpiDeleteVhdBackingStore: leaving...`
- `0x1400e873f`: `VhdmpiDeleteVhdBackingStore: enter... BackingStore: 0x%p`
- `0x1400e875c`: `VhdmpiDeleteBackingStore`
- `0x1400e8894`: `VhdmpiDeleteBackingStore`

## pseudocode

```c
void __fastcall VhdmpiDeleteBackingStore(__int64 *a1, __int64 a2)
{
  __int64 v3; // rax
  IRP *v4; // rcx
  _QWORD *v5; // rcx

  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
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
  v5 = (_QWORD *)a1[185];
  if ( v5 )
    RmwDeletePackage(v5);
  if ( (__int64 *)a1[229] != a1 + 229 )
    __fastfail(0xEu);
  ExFreePoolWithTag(a1, 0x6C444856u);
  if ( (unsigned int)dword_140087708 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
      TraceEvents("VhdmpiDeleteBackingStore", 0x69Eu, 5u, 0x10u, "VhdmpiDeleteVhdBackingStore: leaving...");
  }
}

```

## disassembly

```asm
0x1400e8710  mov     [rsp+arg_0], rbx
0x1400e8715  push    rbp
0x1400e8716  sub     rsp, 30h
0x1400e871a  mov     eax, cs:dword_140087708
0x1400e8720  mov     rbx, rcx
0x1400e8723  mov     ebp, 10h
0x1400e8728  cmp     eax, 5
0x1400e872b  jbe     short loc_1400E8768
0x1400e872d  mov     edx, ebp
0x1400e872f  lea     rcx, dword_140087708
0x1400e8736  call    _tlgKeywordOn
0x1400e873b  test    al, al
0x1400e873d  jz      short loc_1400E8768
0x1400e873f  lea     rax, aVhdmpideletevh_0; "VhdmpiDeleteVhdBackingStore: enter... B"...
0x1400e8746  mov     qword ptr [rsp+38h+var_10], rbx; char
0x1400e874b  mov     edx, 641h; int
0x1400e8750  mov     [rsp+38h+var_18], rax; char *
0x1400e8755  mov     r9d, ebp; int
0x1400e8758  lea     r8d, [rbp-0Bh]; int
0x1400e875c  lea     rcx, aVhdmpideleteba; "VhdmpiDeleteBackingStore"
0x1400e8763  call    TraceEvents
0x1400e8768  mov     rax, [rbx]
0x1400e876b  mov     dl, 1
0x1400e876d  mov     rcx, rbx
0x1400e8770  mov     rax, [rax+50h]
0x1400e8774  call    _guard_dispatch_icall
0x1400e8779  mov     rax, [rbx]
0x1400e877c  mov     rcx, rbx
0x1400e877f  mov     byte ptr [rbx+8], 0
0x1400e8783  mov     rax, [rax+68h]
0x1400e8787  call    _guard_dispatch_icall
0x1400e878c  lea     rcx, [rbx+4A8h]
0x1400e8793  call    DvRundownWorkQueue
0x1400e8798  lea     rcx, [rbx+4F0h]
0x1400e879f  call    DvRundownWorkQueue
0x1400e87a4  cmp     byte ptr [rbx+358h], 0
0x1400e87ab  jz      short loc_1400E87C7
0x1400e87ad  lea     rcx, [rbx+360h]; Resource
0x1400e87b4  call    cs:__imp_ExDeleteResourceLite
0x1400e87bb  nop     dword ptr [rax+rax+00h]
0x1400e87c0  mov     byte ptr [rbx+358h], 0
0x1400e87c7  mov     dl, [rbx+3CDh]
0x1400e87cd  lea     rcx, [rbx+48h]; struct _VHD_FILE_WRAPPER *
0x1400e87d1  call    VhdmpiCleanupFileWrapper
0x1400e87d6  cmp     byte ptr [rbx+5C0h], 0
0x1400e87dd  jz      short loc_1400E87F9
0x1400e87df  lea     rcx, [rbx+540h]; Lookaside
0x1400e87e6  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400e87ed  nop     dword ptr [rax+rax+00h]
0x1400e87f2  mov     byte ptr [rbx+5C0h], 0
0x1400e87f9  mov     rcx, [rbx+408h]; Irp
0x1400e8800  test    rcx, rcx
0x1400e8803  jz      short loc_1400E881C
0x1400e8805  call    cs:__imp_IoFreeIrp
0x1400e880c  nop     dword ptr [rax+rax+00h]
0x1400e8811  mov     qword ptr [rbx+408h], 0
0x1400e881c  mov     rcx, rbx; struct _VHD_BACKING_STORE_HEADER *
0x1400e881f  call    VhdmpiCleanupSrbPartHandling
0x1400e8824  mov     rcx, [rbx+5C8h]; P
0x1400e882b  test    rcx, rcx
0x1400e882e  jz      short loc_1400E8835
0x1400e8830  call    ?RmwDeletePackage@@YAXPEAU_RMW_STORE@@@Z; RmwDeletePackage(_RMW_STORE *)
0x1400e8835  lea     rax, [rbx+728h]
0x1400e883c  cmp     [rax], rax
0x1400e883f  jz      short loc_1400E8848
0x1400e8841  mov     ecx, 0Eh
0x1400e8846  int     29h; Win8: RtlFailFast(ecx)
0x1400e8848  mov     edx, 6C444856h; Tag
0x1400e884d  mov     rcx, rbx; P
0x1400e8850  call    cs:__imp_ExFreePoolWithTag
0x1400e8857  nop     dword ptr [rax+rax+00h]
0x1400e885c  mov     eax, cs:dword_140087708
0x1400e8862  cmp     eax, 5
0x1400e8865  jbe     short loc_1400E88A0
0x1400e8867  mov     rdx, rbp
0x1400e886a  lea     rcx, dword_140087708
0x1400e8871  call    _tlgKeywordOn
0x1400e8876  test    al, al
0x1400e8878  jz      short loc_1400E88A0
0x1400e887a  lea     rax, aVhdmpideletevh_1; "VhdmpiDeleteVhdBackingStore: leaving..."
0x1400e8881  mov     edx, 69Eh; int
0x1400e8886  mov     r9d, ebp; int
0x1400e8889  mov     [rsp+38h+var_18], rax; char *
0x1400e888e  mov     r8d, 5; int
0x1400e8894  lea     rcx, aVhdmpideleteba; "VhdmpiDeleteBackingStore"
0x1400e889b  call    TraceEvents
0x1400e88a0  mov     rbx, [rsp+38h+arg_0]
0x1400e88a5  add     rsp, 30h
0x1400e88a9  pop     rbp
0x1400e88aa  retn
```

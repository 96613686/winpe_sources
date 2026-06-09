# CGenericTableMap<HWND__ *,CMagnifierControl::MagnifierTableElement>::RemoveElement(CMagnifierControl::MagnifierTableElement *)

- ea: `0x1800bcfc4`
- end: `0x1800bd016`
- name: `?RemoveElement@?$CGenericTableMap@PEAUHWND__@@VMagnifierTableElement@CMagnifierControl@@@@QEAAXPEAVMagnifierTableElement@CMagnifierControl@@@Z`
- size: `82`
- prototype: `__int64 __fastcall(PRTL_GENERIC_TABLE Table, CMagnifierControl::MagnifierTableElement *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800bc968`
- `0x1800bcc9c`

## callees

- `0x180071388`
- `0x1800bcfc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800bd000`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800bd000`
- `ntdll!RtlDeleteElementGenericTable` at `0x1800bcfee`
- `ntdll!RtlDeleteElementGenericTable` at `0x1800bcfee`

## pseudocode

```c
void __fastcall CGenericTableMap<HWND__ *,CMagnifierControl::MagnifierTableElement>::RemoveElement(
        PRTL_GENERIC_TABLE Table,
        CMagnifierControl::MagnifierTableElement *this)
{
  _QWORD Buffer[3]; // [rsp+20h] [rbp-18h] BYREF

  Buffer[0] = *(_QWORD *)this;
  Buffer[1] = 0;
  CMagnifierControl::MagnifierTableElement::~MagnifierTableElement(this);
  if ( !RtlDeleteElementGenericTable(Table, Buffer) )
    RaiseFailFastException(0, 0, 1u);
  CMagnifierControl::MagnifierTableElement::~MagnifierTableElement((CMagnifierControl::MagnifierTableElement *)Buffer);
}

```

## disassembly

```asm
0x1800bcfc4  push    rbx
0x1800bcfc6  sub     rsp, 30h
0x1800bcfca  mov     rax, [rdx]
0x1800bcfcd  mov     rbx, rcx
0x1800bcfd0  mov     rcx, rdx; this
0x1800bcfd3  mov     [rsp+38h+Buffer], rax
0x1800bcfd8  mov     [rsp+38h+var_10], 0
0x1800bcfe1  call    ??1MagnifierTableElement@CMagnifierControl@@QEAA@XZ; CMagnifierControl::MagnifierTableElement::~MagnifierTableElement(void)
0x1800bcfe6  lea     rdx, [rsp+38h+Buffer]; Buffer
0x1800bcfeb  mov     rcx, rbx; Table
0x1800bcfee  call    cs:__imp_RtlDeleteElementGenericTable
0x1800bcff4  test    al, al
0x1800bcff6  jnz     short loc_1800BD006
0x1800bcff8  xor     edx, edx; pContextRecord
0x1800bcffa  xor     ecx, ecx; pExceptionRecord
0x1800bcffc  lea     r8d, [rdx+1]; dwFlags
0x1800bd000  call    cs:__imp_RaiseFailFastException
0x1800bd006  lea     rcx, [rsp+38h+Buffer]; this
0x1800bd00b  call    ??1MagnifierTableElement@CMagnifierControl@@QEAA@XZ; CMagnifierControl::MagnifierTableElement::~MagnifierTableElement(void)
0x1800bd010  add     rsp, 30h
0x1800bd014  pop     rbx
0x1800bd015  retn
```

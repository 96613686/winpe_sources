# SclRegGetValue

- ea: `0x180009668`
- end: `0x18000985c`
- name: `SclRegGetValue`
- size: `500`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, const WCHAR *, int, _QWORD *, ULONG ResultLength)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001a18`
- `0x180002010`
- `0x180002cc8`
- `0x18000548c`
- `0x1800065f8`
- `0x180009438`
- `0x18000952c`
- `0x18000a190`

## callees

- `0x180009668`
- `0x18000a524`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180009788`
- `ntdll!RtlAllocateHeap` at `0x180009788`
- `ntdll!RtlInitUnicodeString` at `0x180009695`
- `ntdll!RtlInitUnicodeString` at `0x180009695`
- `ntdll!RtlFreeHeap` at `0x180009842`
- `ntdll!RtlFreeHeap` at `0x180009842`
- `ntdll!NtQueryValueKey` at `0x1800096bf`
- `ntdll!NtQueryValueKey` at `0x1800097f1`
- `ntdll!NtQueryValueKey` at `0x1800096bf`
- `ntdll!NtQueryValueKey` at `0x1800097f1`

## pseudocode

```c
__int64 __fastcall SclRegGetValue(HANDLE KeyHandle, const WCHAR *a2, int a3, _QWORD *a4, ULONG ResultLength)
{
  NTSTATUS v9; // eax
  int v10; // ebx
  PVOID Heap; // rax
  void *v12; // rdi
  NTSTATUS v13; // eax
  __int64 v15; // [rsp+30h] [rbp-58h]
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-48h] BYREF

  ResultLength = 0;
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, a2);
  v9 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
  v10 = v9;
  if ( v9 == -2147483643 || v9 == -1073741789 )
  {
LABEL_8:
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, a3 + ResultLength);
    v12 = Heap;
    if ( Heap )
    {
      v13 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, Heap, ResultLength, &ResultLength);
      v10 = v13;
      if ( v13 >= 0 )
      {
        *a4 = v12;
      }
      else
      {
        LODWORD(v15) = v13;
        SclLogGenericMessage(
          0,
          3,
          (int)SclEvent_Generic_Error,
          1736,
          (__int64)"SclRegGetValue",
          "(%lx): Failed to query key [%ws]",
          v15,
          a2);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
      }
    }
    else
    {
      v10 = -1073741801;
      SclLogGenericMessage(
        0,
        3,
        (int)SclEvent_Generic_Error,
        1721,
        (__int64)"SclRegGetValue",
        "Unable to allocate buffer");
    }
    return (unsigned int)v10;
  }
  if ( v9 == -1073741772 || v9 == -1073741766 )
  {
    SclLogGenericMessage(
      0,
      1,
      (int)SclEvent_Generic_Info,
      1697,
      (__int64)"SclRegGetValue",
      "Reg value [%ws] does not exist",
      a2);
    if ( v10 < 0 )
      return (unsigned int)v10;
    goto LABEL_8;
  }
  SclLogGenericMessage(
    0,
    3,
    (int)SclEvent_Generic_Error,
    1704,
    (__int64)"SclRegGetValue",
    "(%lx): Failed to query reg value [%ws].",
    v9,
    a2);
  if ( v10 >= 0 )
    return (unsigned int)-1073741823;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180009668  mov     rax, rsp
0x18000966b  push    rbx
0x18000966c  push    rbp
0x18000966d  push    rsi
0x18000966e  push    rdi
0x18000966f  push    r14
0x180009671  push    r15
0x180009673  sub     rsp, 58h
0x180009677  mov     rbp, rcx
0x18000967a  mov     dword ptr [rax+28h], 0
0x180009681  xorps   xmm0, xmm0
0x180009684  lea     rcx, [rax-48h]; DestinationString
0x180009688  movups  xmmword ptr [rax-48h], xmm0
0x18000968c  mov     r14, r9
0x18000968f  mov     edi, r8d
0x180009692  mov     rsi, rdx
0x180009695  call    cs:__imp_RtlInitUnicodeString
0x18000969b  xor     r9d, r9d; KeyValueInformation
0x18000969e  lea     rax, [rsp+88h+arg_20]
0x1800096a6  mov     [rsp+88h+ResultLength], rax; ResultLength
0x1800096ab  lea     rdx, [rsp+88h+ValueName]; ValueName
0x1800096b0  mov     rcx, rbp; KeyHandle
0x1800096b3  mov     [rsp+88h+Length], 0; Length
0x1800096bb  lea     r8d, [r9+2]; KeyValueInformationClass
0x1800096bf  call    cs:__imp_NtQueryValueKey
0x1800096c5  lea     r15, aSclreggetvalue; "SclRegGetValue"
0x1800096cc  mov     ebx, eax
0x1800096ce  cmp     eax, 80000005h
0x1800096d3  jz      loc_18000976E
0x1800096d9  cmp     eax, 0C0000023h
0x1800096de  jz      loc_18000976E
0x1800096e4  cmp     eax, 0C0000034h
0x1800096e9  jz      short loc_180009737
0x1800096eb  cmp     eax, 0C000003Ah
0x1800096f0  jz      short loc_180009737
0x1800096f2  mov     [rsp+88h+var_50], rsi
0x1800096f7  lea     r8, SclEvent_Generic_Error
0x1800096fe  mov     dword ptr [rsp+88h+var_58], eax
0x180009702  mov     r9d, 6A8h
0x180009708  lea     rax, aLxFailedToQuer_1; "(%lx): Failed to query reg value [%ws]."
0x18000970f  mov     edx, 3
0x180009714  mov     [rsp+88h+ResultLength], rax
0x180009719  xor     ecx, ecx
0x18000971b  mov     qword ptr [rsp+88h+Length], r15
0x180009720  call    SclLogGenericMessage
0x180009725  test    ebx, ebx
0x180009727  js      loc_18000984D
0x18000972d  mov     ebx, 0C0000001h
0x180009732  jmp     loc_18000984D
0x180009737  lea     rax, aRegValueWsDoes; "Reg value [%ws] does not exist"
0x18000973e  mov     [rsp+88h+var_58], rsi
0x180009743  mov     [rsp+88h+ResultLength], rax
0x180009748  lea     r8, SclEvent_Generic_Info
0x18000974f  mov     r9d, 6A1h
0x180009755  mov     qword ptr [rsp+88h+Length], r15
0x18000975a  mov     edx, 1
0x18000975f  xor     ecx, ecx
0x180009761  call    SclLogGenericMessage
0x180009766  test    ebx, ebx
0x180009768  js      loc_18000984D
0x18000976e  mov     rcx, gs:60h
0x180009777  xor     edx, edx; Flags
0x180009779  mov     r8d, [rsp+88h+arg_20]
0x180009781  add     r8d, edi; Size
0x180009784  mov     rcx, [rcx+30h]; HeapHandle
0x180009788  call    cs:__imp_RtlAllocateHeap
0x18000978e  mov     rdi, rax
0x180009791  test    rax, rax
0x180009794  jnz     short loc_1800097C8
0x180009796  lea     rax, aUnableToAlloca; "Unable to allocate buffer"
0x18000979d  mov     r9d, 6B9h
0x1800097a3  mov     [rsp+88h+ResultLength], rax
0x1800097a8  lea     r8, SclEvent_Generic_Error
0x1800097af  lea     edx, [rdi+3]
0x1800097b2  mov     qword ptr [rsp+88h+Length], r15
0x1800097b7  xor     ecx, ecx
0x1800097b9  mov     ebx, 0C0000017h
0x1800097be  call    SclLogGenericMessage
0x1800097c3  jmp     loc_18000984D
0x1800097c8  lea     rax, [rsp+88h+arg_20]
0x1800097d0  mov     r9, rdi; KeyValueInformation
0x1800097d3  mov     [rsp+88h+ResultLength], rax; ResultLength
0x1800097d8  lea     rdx, [rsp+88h+ValueName]; ValueName
0x1800097dd  mov     eax, [rsp+88h+arg_20]
0x1800097e4  mov     r8d, 2; KeyValueInformationClass
0x1800097ea  mov     rcx, rbp; KeyHandle
0x1800097ed  mov     [rsp+88h+Length], eax; Length
0x1800097f1  call    cs:__imp_NtQueryValueKey
0x1800097f7  mov     ebx, eax
0x1800097f9  test    eax, eax
0x1800097fb  jns     short loc_18000984A
0x1800097fd  mov     [rsp+88h+var_50], rsi
0x180009802  lea     r8, SclEvent_Generic_Error
0x180009809  mov     dword ptr [rsp+88h+var_58], eax
0x18000980d  mov     r9d, 6C8h
0x180009813  lea     rax, aLxFailedToQuer_2; "(%lx): Failed to query key [%ws]"
0x18000981a  mov     edx, 3
0x18000981f  mov     [rsp+88h+ResultLength], rax
0x180009824  xor     ecx, ecx
0x180009826  mov     qword ptr [rsp+88h+Length], r15
0x18000982b  call    SclLogGenericMessage
0x180009830  mov     rcx, gs:60h
0x180009839  mov     r8, rdi; P
0x18000983c  xor     edx, edx; Flags
0x18000983e  mov     rcx, [rcx+30h]; HeapHandle
0x180009842  call    cs:__imp_RtlFreeHeap
0x180009848  jmp     short loc_18000984D
0x18000984a  mov     [r14], rdi
0x18000984d  mov     eax, ebx
0x18000984f  add     rsp, 58h
0x180009853  pop     r15
0x180009855  pop     r14
0x180009857  pop     rdi
0x180009858  pop     rsi
0x180009859  pop     rbp
0x18000985a  pop     rbx
0x18000985b  retn
```

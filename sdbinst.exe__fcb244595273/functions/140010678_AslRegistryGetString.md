# AslRegistryGetString

- ea: `0x140010678`
- end: `0x14001083b`
- name: `AslRegistryGetString`
- size: `451`
- prototype: `__int64 __fastcall(_QWORD *, void *, const WCHAR *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000a9ec`
- `0x14000d8e8`
- `0x140010844`
- `0x140016c98`

## callees

- `0x14001008c`
- `0x140010678`
- `0x140010d44`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1400106a7`
- `ntdll!RtlInitUnicodeString` at `0x1400106a7`
- `ntdll!RtlAllocateHeap` at `0x140010736`
- `ntdll!RtlAllocateHeap` at `0x140010736`
- `ntdll!RtlFreeHeap` at `0x140010829`
- `ntdll!RtlFreeHeap` at `0x140010829`
- `ntdll!ZwQueryValueKey` at `0x1400106ce`
- `ntdll!ZwQueryValueKey` at `0x14001078d`
- `ntdll!ZwQueryValueKey` at `0x1400106ce`
- `ntdll!ZwQueryValueKey` at `0x14001078d`

## string_xrefs

- `0x140010700`: `AslRegistryGetString`
- `0x140010751`: `AslRegistryGetString`
- `0x1400107bf`: `AslRegistryGetString`
- `0x140010802`: `AslRegistryGetString`

## pseudocode

```c
__int64 __fastcall AslRegistryGetString(_QWORD *a1, void *a2, const WCHAR *a3)
{
  NTSTATUS v5; // eax
  unsigned int v6; // ebx
  _DWORD *Heap; // rax
  _DWORD *v8; // rdi
  NTSTATUS v9; // eax
  const char *v10; // r9
  __int64 v11; // r8
  __int64 Length; // [rsp+20h] [rbp-48h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+70h] [rbp+8h] BYREF

  *a1 = 0;
  ResultLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a3);
  v5 = ZwQueryValueKey(a2, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
  v6 = v5;
  if ( v5 == -2147483643 || v5 == -1073741789 )
  {
    ResultLength += 2;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, ResultLength);
    v8 = Heap;
    if ( !Heap )
    {
      v6 = -1073741801;
      AslLogCallPrintf(1, "AslRegistryGetString", 1348, "Out of memory");
      return v6;
    }
    v9 = ZwQueryValueKey(a2, &DestinationString, KeyValuePartialInformation, Heap, ResultLength, &ResultLength);
    v6 = v9;
    if ( v9 < 0 )
    {
      v10 = "Failed to query key value [%x]";
      v11 = 1360;
LABEL_13:
      LODWORD(Length) = v9;
      AslLogCallPrintf(1, "AslRegistryGetString", v11, v10, Length);
      goto LABEL_14;
    }
    if ( (unsigned int)(v8[1] - 1) <= 1 )
    {
      *((_WORD *)v8 + ((unsigned __int64)(unsigned int)v8[2] >> 1) + 6) = 0;
      v9 = AslStringDuplicate(a1, v8 + 3);
      v6 = v9;
      if ( v9 < 0 )
      {
        v10 = "Out of memory [%x]";
        v11 = 1378;
        goto LABEL_13;
      }
    }
    else
    {
      AslLogCallPrintf(1, "AslRegistryGetString", 1368, "Invalid value type");
      v6 = -1073741788;
    }
LABEL_14:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
    return v6;
  }
  if ( v5 != -1073741772 )
    AslLogCallPrintf(1, "AslRegistryGetString", 1334, "Failed to query key value [%x]", v5);
  return v6;
}

```

## disassembly

```asm
0x140010678  push    rbx
0x14001067a  push    rsi
0x14001067b  push    rdi
0x14001067c  push    r14
0x14001067e  sub     rsp, 48h
0x140010682  mov     rsi, rdx
0x140010685  mov     qword ptr [rcx], 0
0x14001068c  mov     r14, rcx
0x14001068f  mov     [rsp+68h+arg_0], 0
0x140010697  xorps   xmm0, xmm0
0x14001069a  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14001069f  mov     rdx, r8; SourceString
0x1400106a2  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1400106a7  call    cs:__imp_RtlInitUnicodeString
0x1400106ad  xor     r9d, r9d; KeyValueInformation
0x1400106b0  lea     rax, [rsp+68h+arg_0]
0x1400106b5  mov     [rsp+68h+ResultLength], rax; ResultLength
0x1400106ba  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x1400106bf  mov     rcx, rsi; KeyHandle
0x1400106c2  mov     dword ptr [rsp+68h+Length], 0; Length
0x1400106ca  lea     r8d, [r9+2]; KeyValueInformationClass
0x1400106ce  call    cs:__imp_ZwQueryValueKey
0x1400106d4  mov     ebx, eax
0x1400106d6  cmp     eax, 80000005h
0x1400106db  jz      short loc_140010716
0x1400106dd  cmp     eax, 0C0000023h
0x1400106e2  jz      short loc_140010716
0x1400106e4  cmp     eax, 0C0000034h
0x1400106e9  jz      loc_14001082F
0x1400106ef  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x1400106f6  mov     dword ptr [rsp+68h+Length], eax
0x1400106fa  mov     r8d, 536h
0x140010700  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x140010707  mov     ecx, 1
0x14001070c  call    AslLogCallPrintf
0x140010711  jmp     loc_14001082F
0x140010716  mov     eax, [rsp+68h+arg_0]
0x14001071a  mov     edx, 8; Flags
0x14001071f  add     eax, 2
0x140010722  mov     [rsp+68h+arg_0], eax
0x140010726  mov     rcx, gs:60h
0x14001072f  mov     r8d, eax; Size
0x140010732  mov     rcx, [rcx+30h]; HeapHandle
0x140010736  call    cs:__imp_RtlAllocateHeap
0x14001073c  mov     rdi, rax
0x14001073f  test    rax, rax
0x140010742  jnz     short loc_14001076A
0x140010744  lea     r9, aOutOfMemory; "Out of memory"
0x14001074b  mov     r8d, 544h
0x140010751  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x140010758  mov     ebx, 0C0000017h
0x14001075d  lea     ecx, [rax+1]
0x140010760  call    AslLogCallPrintf
0x140010765  jmp     loc_14001082F
0x14001076a  lea     rax, [rsp+68h+arg_0]
0x14001076f  mov     r9, rdi; KeyValueInformation
0x140010772  mov     [rsp+68h+ResultLength], rax; ResultLength
0x140010777  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x14001077c  mov     eax, [rsp+68h+arg_0]
0x140010780  mov     r8d, 2; KeyValueInformationClass
0x140010786  mov     rcx, rsi; KeyHandle
0x140010789  mov     dword ptr [rsp+68h+Length], eax; Length
0x14001078d  call    cs:__imp_ZwQueryValueKey
0x140010793  mov     ebx, eax
0x140010795  test    eax, eax
0x140010797  jns     short loc_1400107A8
0x140010799  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x1400107a0  mov     r8d, 550h
0x1400107a6  jmp     short loc_140010802
0x1400107a8  mov     eax, [rdi+4]
0x1400107ab  dec     eax
0x1400107ad  cmp     eax, 1
0x1400107b0  jbe     short loc_1400107D7
0x1400107b2  lea     r9, aInvalidValueTy; "Invalid value type"
0x1400107b9  mov     r8d, 558h
0x1400107bf  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x1400107c6  mov     ecx, 1
0x1400107cb  call    AslLogCallPrintf
0x1400107d0  mov     ebx, 0C0000024h
0x1400107d5  jmp     short loc_140010817
0x1400107d7  mov     ecx, [rdi+8]
0x1400107da  lea     rdx, [rdi+0Ch]
0x1400107de  shr     rcx, 1
0x1400107e1  xor     eax, eax
0x1400107e3  mov     [rdx+rcx*2], ax
0x1400107e7  mov     rcx, r14
0x1400107ea  call    AslStringDuplicate
0x1400107ef  mov     ebx, eax
0x1400107f1  test    eax, eax
0x1400107f3  jns     short loc_140010817
0x1400107f5  lea     r9, aOutOfMemoryX; "Out of memory [%x]"
0x1400107fc  mov     r8d, 562h
0x140010802  lea     rdx, aAslregistryget_1; "AslRegistryGetString"
0x140010809  mov     dword ptr [rsp+68h+Length], eax
0x14001080d  mov     ecx, 1
0x140010812  call    AslLogCallPrintf
0x140010817  mov     rcx, gs:60h
0x140010820  mov     r8, rdi; P
0x140010823  xor     edx, edx; Flags
0x140010825  mov     rcx, [rcx+30h]; HeapHandle
0x140010829  call    cs:__imp_RtlFreeHeap
0x14001082f  mov     eax, ebx
0x140010831  add     rsp, 48h
0x140010835  pop     r14
0x140010837  pop     rdi
0x140010838  pop     rsi
0x140010839  pop     rbx
0x14001083a  retn
```

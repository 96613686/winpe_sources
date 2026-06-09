# OpenPerfCounters(ushort *)

- ea: `0x180009400`
- end: `0x180009498`
- name: `?OpenPerfCounters@@YAKPEAG@Z`
- size: `152`
- prototype: `unsigned int __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180009400`
- `0x18001a8d0`
- `0x180022a34`
- `0x180025850`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180009450`
- `KERNEL32!RaiseException` at `0x180009450`

## pseudocode

```c
__int64 __fastcall OpenPerfCounters(CHpAllocator *a1)
{
  unsigned int v1; // ebx
  const char *v2; // rdx
  const char *v3; // rdx
  const struct _GUID *v4; // rdx
  const struct _GUID *v5; // r8
  const unsigned __int16 *v6; // r9
  const char *v7; // rdx

  v1 = 0;
  if ( !qword_1800336A0 || !qword_1800336A8 )
  {
    g_HpAllocator = 1;
    v1 = CHpAllocator::ServerInitialize(a1);
    ElValidateWin32(v1, v2, "base\\eco\\wds\\wdslib\\hpalloc\\hpallocator.cpp", 0xB2u);
    if ( v1 )
      RaiseException(0xC0000017, 0, 0, 0);
    if ( !ElValidateWin32(v1, v3, "base\\eco\\wds\\transport\\server\\mc\\mcperfcounter.cpp", 0x96u) )
    {
      v1 = CPerfCounters::InitializeClient((CPerfCounters *)&qword_1800336A0, v4, v5, v6);
      ElValidateWin32(v1, v7, "base\\eco\\wds\\transport\\server\\mc\\mcperfcounter.cpp", 0x99u);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180009400  push    rbx
0x180009402  sub     rsp, 40h
0x180009406  xor     ebx, ebx
0x180009408  cmp     cs:qword_1800336A0, rbx
0x18000940f  jz      short loc_18000941A
0x180009411  cmp     cs:qword_1800336A8, rbx
0x180009418  jnz     short loc_180009490
0x18000941a  mov     cs:?g_HpAllocator@@3VCHpAllocator@@A, 1; CHpAllocator g_HpAllocator
0x180009424  call    ?ServerInitialize@CHpAllocator@@AEAAKXZ; CHpAllocator::ServerInitialize(void)
0x180009429  mov     r9d, 0B2h; unsigned int
0x18000942f  lea     r8, aBaseEcoWdsWdsl_4; "base\\eco\\wds\\wdslib\\hpalloc\\hpallo"...
0x180009436  mov     ecx, eax; unsigned int
0x180009438  mov     ebx, eax
0x18000943a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000943f  test    ebx, ebx
0x180009441  jz      short loc_180009456
0x180009443  xor     r9d, r9d; lpArguments
0x180009446  xor     r8d, r8d; nNumberOfArguments
0x180009449  xor     edx, edx; dwExceptionFlags
0x18000944b  mov     ecx, 0C0000017h; dwExceptionCode
0x180009450  call    cs:__imp_RaiseException
0x180009456  mov     r9d, 96h; unsigned int
0x18000945c  lea     r8, aBaseEcoWdsTran_14; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180009463  mov     ecx, ebx; unsigned int
0x180009465  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000946a  test    eax, eax
0x18000946c  jnz     short loc_180009490
0x18000946e  lea     rcx, qword_1800336A0; this
0x180009475  call    ?InitializeClient@CPerfCounters@@QEAAKAEBU_GUID@@0PEBGKKPEAK@Z; CPerfCounters::InitializeClient(_GUID const &,_GUID const &,ushort const *,ulong,ulong,ulong *)
0x18000947a  mov     r9d, 99h; unsigned int
0x180009480  lea     r8, aBaseEcoWdsTran_14; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180009487  mov     ecx, eax; unsigned int
0x180009489  mov     ebx, eax
0x18000948b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009490  mov     eax, ebx
0x180009492  add     rsp, 40h
0x180009496  pop     rbx
0x180009497  retn
```

# wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Telemetry4UpdateCli,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Telemetry4UpdateCli,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x18000d14c`
- end: `0x18000d1c4`
- name: `??1?$ActivityData@VTelemetry4UpdateCli@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VTelemetry4UpdateCli@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000cfc0`
- `0x18000d1cc`

## callees

- `0x180004158`
- `0x180005730`
- `0x18000d0d8`
- `0x18000d14c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d171`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d171`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d17f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d17f`

## pseudocode

```c
void __fastcall wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Telemetry4UpdateCli,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Telemetry4UpdateCli,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  struct Telemetry4UpdateCli *v4; // rax

  wil::StoredFailureInfo::~StoredFailureInfo((wil::StoredFailureInfo *)(a1 + 80));
  if ( *(_BYTE *)(a1 + 64) )
  {
    v2 = *(void **)(a1 + 56);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
    *(_BYTE *)(a1 + 64) = 0;
  }
  *(_QWORD *)(a1 + 56) = 0;
  if ( *(_DWORD *)a1 == 1 )
  {
    *(_DWORD *)a1 = 2;
    v4 = Telemetry4UpdateCli::Instance();
    _tlgWriteActivityAutoStop<70368744177664,5>(*((_QWORD *)v4 + 1), a1 + 8);
  }
  *(_DWORD *)a1 = 3;
}

```

## disassembly

```asm
0x18000d14c  mov     [rsp+arg_0], rbx
0x18000d151  mov     [rsp+arg_8], rsi
0x18000d156  push    rdi
0x18000d157  sub     rsp, 20h
0x18000d15b  mov     rdi, rcx
0x18000d15e  add     rcx, 50h ; 'P'; this
0x18000d162  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x18000d167  cmp     byte ptr [rdi+40h], 0
0x18000d16b  jz      short loc_18000D189
0x18000d16d  mov     rbx, [rdi+38h]
0x18000d171  call    cs:__imp_GetProcessHeap
0x18000d177  mov     r8, rbx; lpMem
0x18000d17a  xor     edx, edx; dwFlags
0x18000d17c  mov     rcx, rax; hHeap
0x18000d17f  call    cs:__imp_HeapFree
0x18000d185  mov     byte ptr [rdi+40h], 0
0x18000d189  mov     qword ptr [rdi+38h], 0
0x18000d191  cmp     dword ptr [rdi], 1
0x18000d194  jnz     short loc_18000D1AE
0x18000d196  mov     dword ptr [rdi], 2
0x18000d19c  call    ?Instance@Telemetry4UpdateCli@@KAPEAV1@XZ; Telemetry4UpdateCli::Instance(void)
0x18000d1a1  lea     rdx, [rdi+8]
0x18000d1a5  mov     rcx, [rax+8]
0x18000d1a9  call    ??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)
0x18000d1ae  mov     rbx, [rsp+28h+arg_0]
0x18000d1b3  mov     rsi, [rsp+28h+arg_8]
0x18000d1b8  mov     dword ptr [rdi], 3
0x18000d1be  add     rsp, 20h
0x18000d1c2  pop     rdi
0x18000d1c3  retn
```

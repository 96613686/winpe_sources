# TetheringServiceTelemetry::GetSession(_GUID *,TetheringSessionTelemetry * *)

- ea: `0x1800272c0`
- end: `0x18002738b`
- name: `?GetSession@TetheringServiceTelemetry@@QEAAJPEAU_GUID@@PEAPEAVTetheringSessionTelemetry@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(TetheringServiceTelemetry *this, struct _GUID *, struct TetheringSessionTelemetry **)`
- caller_count: `14`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d9dc`
- `0x18000dfd8`
- `0x18000ee3c`
- `0x180010c6c`
- `0x180010e84`
- `0x1800110d4`
- `0x18001379c`
- `0x180014c8c`
- `0x180015430`
- `0x18001dc08`
- `0x18001e4a4`
- `0x18001f740`
- `0x180027424`
- `0x180027550`

## callees

- `0x1800271b0`
- `0x180027288`
- `0x1800272c0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800272eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800272eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180027373`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180027373`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180027321`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180027339`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180027321`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180027339`

## pseudocode

```c
__int64 __fastcall TetheringServiceTelemetry::GetSession(
        TetheringServiceTelemetry *this,
        struct _GUID *a2,
        struct TetheringSessionTelemetry **a3)
{
  unsigned int v6; // ebx
  struct _GUID *Id; // rax
  struct _GUID *v8; // rbx
  TetheringSessionTelemetry *v9; // rcx

  if ( !a2 )
    return 2147942487LL;
  AcquireSRWLockShared(&g_pTetheringServiceTelemetry);
  if ( qword_180041E50 )
  {
    Id = TetheringSessionTelemetry::GetId(qword_180041E50);
    v8 = Id;
    if ( Id && RtlCompareMemory(Id, &GUID_NULL, 0x10u) != 16 && RtlCompareMemory(a2, v8, 0x10u) == 16 )
    {
      v9 = qword_180041E50;
      v6 = 0;
      *a3 = qword_180041E50;
      TetheringSessionTelemetry::AddThread(v9);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
    }
    else
    {
      v6 = -2147023728;
    }
  }
  else
  {
    v6 = -2147418113;
  }
  ReleaseSRWLockShared(&g_pTetheringServiceTelemetry);
  return v6;
}

```

## disassembly

```asm
0x1800272c0  mov     [rsp+arg_0], rbx
0x1800272c5  mov     [rsp+arg_8], rsi
0x1800272ca  push    rdi
0x1800272cb  sub     rsp, 20h
0x1800272cf  mov     rsi, r8
0x1800272d2  mov     rdi, rdx
0x1800272d5  test    rdx, rdx
0x1800272d8  jnz     short loc_1800272E4
0x1800272da  mov     eax, 80070057h
0x1800272df  jmp     loc_18002737B
0x1800272e4  lea     rcx, ?g_pTetheringServiceTelemetry@@3VTetheringServiceTelemetry@@A; SRWLock
0x1800272eb  call    cs:__imp_AcquireSRWLockShared
0x1800272f1  mov     rcx, cs:qword_180041E50; this
0x1800272f8  test    rcx, rcx
0x1800272fb  jnz     short loc_180027304
0x1800272fd  mov     ebx, 8000FFFFh
0x180027302  jmp     short loc_18002736C
0x180027304  call    ?GetId@TetheringSessionTelemetry@@QEAAPEAU_GUID@@XZ; TetheringSessionTelemetry::GetId(void)
0x180027309  mov     rbx, rax
0x18002730c  test    rax, rax
0x18002730f  jz      short loc_180027367
0x180027311  mov     r8d, 10h; Length
0x180027317  lea     rdx, GUID_NULL; Source2
0x18002731e  mov     rcx, rax; Source1
0x180027321  call    cs:__imp_RtlCompareMemory
0x180027327  cmp     rax, 10h
0x18002732b  jz      short loc_180027367
0x18002732d  mov     r8d, 10h; Length
0x180027333  mov     rdx, rbx; Source2
0x180027336  mov     rcx, rdi; Source1
0x180027339  call    cs:__imp_RtlCompareMemory
0x18002733f  cmp     rax, 10h
0x180027343  jnz     short loc_180027367
0x180027345  mov     rcx, cs:qword_180041E50; this
0x18002734c  xor     ebx, ebx
0x18002734e  mov     [rsi], rcx
0x180027351  call    ?AddThread@TetheringSessionTelemetry@@AEAAJXZ; TetheringSessionTelemetry::AddThread(void)
0x180027356  mov     rcx, [rsi]
0x180027359  mov     rax, [rcx]
0x18002735c  mov     rax, [rax+8]
0x180027360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027365  jmp     short loc_18002736C
0x180027367  mov     ebx, 80070490h
0x18002736c  lea     rcx, ?g_pTetheringServiceTelemetry@@3VTetheringServiceTelemetry@@A; SRWLock
0x180027373  call    cs:__imp_ReleaseSRWLockShared
0x180027379  mov     eax, ebx
0x18002737b  mov     rbx, [rsp+28h+arg_0]
0x180027380  mov     rsi, [rsp+28h+arg_8]
0x180027385  add     rsp, 20h
0x180027389  pop     rdi
0x18002738a  retn
```

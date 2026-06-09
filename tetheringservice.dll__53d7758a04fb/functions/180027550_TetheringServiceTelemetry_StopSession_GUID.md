# TetheringServiceTelemetry::StopSession(_GUID *)

- ea: `0x180027550`
- end: `0x180027600`
- name: `?StopSession@TetheringServiceTelemetry@@QEAAJPEAU_GUID@@@Z`
- size: `176`
- prototype: `__int64 __fastcall(TetheringServiceTelemetry *__hidden this, struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001dc08`
- `0x18001f740`

## callees

- `0x1800272c0`
- `0x180027550`
- `0x180027608`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800275d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800275d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800275a5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800275a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TetheringServiceTelemetry::StopSession(TetheringServiceTelemetry *this, struct _GUID *a2)
{
  int Session; // edi
  void (*v3)(void); // rax
  TetheringSessionTelemetry *v4; // rbx
  TetheringSessionTelemetry *v5; // rcx
  TetheringSessionTelemetry *v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  Session = TetheringServiceTelemetry::GetSession(this, *(struct _GUID **)&g_pTetheringSessionId.Data1, &v7);
  if ( Session >= 0 )
  {
    v4 = v7;
    TetheringSessionTelemetry::StopSession(v7);
    AcquireSRWLockExclusive(&g_pTetheringServiceTelemetry);
    v5 = qword_180041E50;
    if ( qword_180041E50 )
    {
      qword_180041E50 = 0;
      (*(void (__fastcall **)(TetheringSessionTelemetry *))(*(_QWORD *)v5 + 16LL))(v5);
    }
    ReleaseSRWLockExclusive(&g_pTetheringServiceTelemetry);
    if ( v4 )
    {
      v3 = *(void (**)(void))(*(_QWORD *)v4 + 16LL);
      goto LABEL_8;
    }
  }
  else if ( v7 )
  {
    v3 = *(void (**)(void))(*(_QWORD *)v7 + 16LL);
LABEL_8:
    v3();
  }
  return (unsigned int)Session;
}

```

## disassembly

```asm
0x180027550  mov     rax, rsp
0x180027553  mov     [rax+8], rbx
0x180027557  mov     [rax+10h], rdx
0x18002755b  push    rdi
0x18002755c  sub     rsp, 20h
0x180027560  mov     qword ptr [rax+10h], 0
0x180027568  lea     r8, [rax+10h]; struct TetheringSessionTelemetry **
0x18002756c  mov     rdx, qword ptr cs:?g_pTetheringSessionId@@3PEAU_GUID@@EA.Data1; struct _GUID *
0x180027573  call    ?GetSession@TetheringServiceTelemetry@@QEAAJPEAU_GUID@@PEAPEAVTetheringSessionTelemetry@@@Z; TetheringServiceTelemetry::GetSession(_GUID *,TetheringSessionTelemetry * *)
0x180027578  mov     edi, eax
0x18002757a  test    eax, eax
0x18002757c  jns     short loc_180027591
0x18002757e  mov     rcx, [rsp+28h+arg_8]
0x180027583  test    rcx, rcx
0x180027586  jz      short loc_1800275F3
0x180027588  mov     rdx, [rcx]
0x18002758b  mov     rax, [rdx+10h]
0x18002758f  jmp     short loc_1800275ED
0x180027591  mov     rbx, [rsp+28h+arg_8]
0x180027596  mov     rcx, rbx; this
0x180027599  call    ?StopSession@TetheringSessionTelemetry@@QEAAXXZ; TetheringSessionTelemetry::StopSession(void)
0x18002759e  lea     rcx, ?g_pTetheringServiceTelemetry@@3VTetheringServiceTelemetry@@A; SRWLock
0x1800275a5  call    cs:__imp_AcquireSRWLockExclusive
0x1800275ab  nop
0x1800275ac  mov     rcx, cs:qword_180041E50
0x1800275b3  test    rcx, rcx
0x1800275b6  jz      short loc_1800275D0
0x1800275b8  mov     cs:qword_180041E50, 0
0x1800275c3  mov     rax, [rcx]
0x1800275c6  mov     rax, [rax+10h]
0x1800275ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275cf  nop
0x1800275d0  lea     rcx, ?g_pTetheringServiceTelemetry@@3VTetheringServiceTelemetry@@A; SRWLock
0x1800275d7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800275dd  nop
0x1800275de  test    rbx, rbx
0x1800275e1  jz      short loc_1800275F3
0x1800275e3  mov     rax, [rbx]
0x1800275e6  mov     rcx, rbx
0x1800275e9  mov     rax, [rax+10h]
0x1800275ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275f2  nop
0x1800275f3  mov     eax, edi
0x1800275f5  mov     rbx, [rsp+28h+arg_0]
0x1800275fa  add     rsp, 20h
0x1800275fe  pop     rdi
0x1800275ff  retn
```

# UwfServicingWinupdateCleanup

- ea: `0x1800031c0`
- end: `0x180003259`
- name: `UwfServicingWinupdateCleanup`
- size: `153`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, installer_update`

## callees

- `0x180001536`
- `0x180002a20`
- `0x1800031c0`
- `0x180006010`

## string_xrefs

- `0x180003226`: `Exiting UPDATE AGENT`

## pseudocode

```c
__int64 UwfServicingWinupdateCleanup()
{
  UWFUpdateAgent *v0; // rbx
  __int64 v1; // rax
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx
  __int64 result; // rax

  v0 = qword_18000C840;
  v1 = *((_QWORD *)qword_18000C840 + 2);
  if ( v1 )
  {
    v2 = *(void **)(v1 + 24);
    if ( v2 )
      operator delete(v2);
    v3 = *(void **)(*((_QWORD *)v0 + 2) + 32LL);
    if ( v3 )
      operator delete(v3);
    operator delete(*((void **)v0 + 2));
  }
  v4 = *((_QWORD *)v0 + 1);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *((_QWORD *)v0 + 1) = 0;
  *((_QWORD *)v0 + 2) = 0;
  result = UwfServicingLog(1, 0, 0, L"Exiting UPDATE AGENT");
  if ( qword_18000C840 )
    return (**(__int64 (__fastcall ***)(UWFUpdateAgent *, __int64))qword_18000C840)(qword_18000C840, 1);
  return result;
}

```

## disassembly

```asm
0x1800031c0  push    rbx
0x1800031c2  sub     rsp, 20h
0x1800031c6  mov     rbx, cs:qword_18000C840
0x1800031cd  mov     rax, [rbx+10h]
0x1800031d1  test    rax, rax
0x1800031d4  jz      short loc_1800031FF
0x1800031d6  mov     rcx, [rax+18h]; void *
0x1800031da  test    rcx, rcx
0x1800031dd  jz      short loc_1800031E4
0x1800031df  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x1800031e4  mov     rax, [rbx+10h]
0x1800031e8  mov     rcx, [rax+20h]; void *
0x1800031ec  test    rcx, rcx
0x1800031ef  jz      short loc_1800031F6
0x1800031f1  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x1800031f6  mov     rcx, [rbx+10h]; void *
0x1800031fa  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x1800031ff  mov     rcx, [rbx+8]
0x180003203  test    rcx, rcx
0x180003206  jz      short loc_180003214
0x180003208  mov     rax, [rcx]
0x18000320b  mov     rax, [rax+10h]
0x18000320f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003214  xor     edx, edx
0x180003216  mov     qword ptr [rbx+8], 0
0x18000321e  mov     qword ptr [rbx+10h], 0
0x180003226  lea     r9, aExitingUpdateA; "Exiting UPDATE AGENT"
0x18000322d  xor     r8d, r8d
0x180003230  lea     ebx, [rdx+1]
0x180003233  mov     ecx, ebx
0x180003235  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x18000323a  mov     rcx, cs:qword_18000C840
0x180003241  test    rcx, rcx
0x180003244  jz      short loc_180003253
0x180003246  mov     rax, [rcx]
0x180003249  mov     edx, ebx
0x18000324b  mov     rax, [rax]
0x18000324e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003253  add     rsp, 20h
0x180003257  pop     rbx
0x180003258  retn
```

# CSWbemObject::get_Path_(ISWbemObjectPath * *)

- ea: `0x180001370`
- end: `0x180001440`
- name: `?get_Path_@CSWbemObject@@UEAAJPEAPEAUISWbemObjectPath@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(CSWbemObject *__hidden this, struct ISWbemObjectPath **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180001370`
- `0x180001448`
- `0x180006300`
- `0x18000c228`
- `0x180024774`
- `0x180036010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800013b2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800013b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSWbemObject::get_Path_(CSWbemObject *this, struct ISWbemObjectPath **a2)
{
  CSWbemObject *v3; // rdi
  int v4; // ebx
  CSWbemObjectObjectPath *v5; // rax
  CSWbemObjectObjectPath *v6; // rsi
  unsigned int v8; // edx
  CWbemDispatchMgr *v9; // rcx

  v3 = this;
  ResetLastErrors();
  if ( !a2 )
  {
    v4 = -2147217400;
LABEL_14:
    v9 = (CWbemDispatchMgr *)*((_QWORD *)v3 + 9);
    if ( v9 )
      CWbemDispatchMgr::RaiseException(v9, v4);
    return (unsigned int)v4;
  }
  v4 = -2147217407;
  *a2 = 0;
  if ( !*((_QWORD *)v3 + 8) )
    goto LABEL_14;
  try
  {
    v5 = (CSWbemObjectObjectPath *)CWin32DefaultArena::WbemMemAlloc(0x90u);
    if ( v5 )
      v6 = CSWbemObjectObjectPath::CSWbemObjectObjectPath(v5, *((struct CSWbemServices **)v3 + 7), v3);
    else
      v6 = 0;
    if ( v6 )
    {
      v4 = (**(__int64 (__fastcall ***)(CSWbemObjectObjectPath *, GUID *, struct ISWbemObjectPath **))v6)(
             v6,
             &IID_ISWbemObjectPath,
             a2);
      if ( v4 < 0 )
        CSWbemObjectObjectPath::`scalar deleting destructor'(v6, v8);
    }
    else
    {
      v4 = -2147217402;
    }
  }
  catch ( CX_MemoryException )
  {
    v3 = this;
    v4 = -2147217402;
    goto LABEL_14;
  }
  if ( v4 < 0 )
    goto LABEL_14;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001370  mov     [rsp+arg_10], rbx
0x180001375  mov     [rsp+arg_0], rcx
0x18000137a  push    rsi
0x18000137b  push    rdi
0x18000137c  push    r14
0x18000137e  sub     rsp, 20h
0x180001382  mov     r14, rdx
0x180001385  mov     rdi, rcx
0x180001388  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18000138d  test    r14, r14
0x180001390  jz      loc_18000141E
0x180001396  mov     ebx, 80041001h
0x18000139b  mov     qword ptr [r14], 0
0x1800013a2  cmp     qword ptr [rdi+40h], 0
0x1800013a7  jz      loc_18000142E
0x1800013ad  mov     ecx, 90h
0x1800013b2  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800013b8  mov     [rsp+38h+arg_8], rax
0x1800013bd  test    rax, rax
0x1800013c0  jz      short loc_18000141A
0x1800013c2  mov     r8, rdi; struct CSWbemObject *
0x1800013c5  mov     rdx, [rdi+38h]; struct CSWbemServices *
0x1800013c9  mov     rcx, rax; this
0x1800013cc  call    ??0CSWbemObjectObjectPath@@QEAA@PEAVCSWbemServices@@PEAVCSWbemObject@@@Z; CSWbemObjectObjectPath::CSWbemObjectObjectPath(CSWbemServices *,CSWbemObject *)
0x1800013d1  mov     rsi, rax
0x1800013d4  test    rsi, rsi
0x1800013d7  jnz     short loc_1800013F2
0x1800013d9  mov     ebx, 80041006h
0x1800013de  test    ebx, ebx
0x1800013e0  js      short loc_18000142E
0x1800013e2  mov     eax, ebx
0x1800013e4  mov     rbx, [rsp+38h+arg_10]
0x1800013e9  add     rsp, 20h
0x1800013ed  pop     r14
0x1800013ef  pop     rdi
0x1800013f0  pop     rsi
0x1800013f1  retn
0x1800013f2  mov     rax, [rsi]
0x1800013f5  mov     r8, r14
0x1800013f8  lea     rdx, IID_ISWbemObjectPath
0x1800013ff  mov     rcx, rsi
0x180001402  mov     rax, [rax]
0x180001405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000140a  mov     ebx, eax
0x18000140c  test    eax, eax
0x18000140e  jns     short loc_1800013DE
0x180001410  mov     rcx, rsi; this
0x180001413  call    ??_GCSWbemObjectObjectPath@@QEAAPEAXI@Z; CSWbemObjectObjectPath::`scalar deleting destructor'(uint)
0x180001418  jmp     short loc_1800013DE
0x18000141a  xor     esi, esi
0x18000141c  jmp     short loc_1800013D4
0x18000141e  mov     ebx, 80041008h
0x180001423  jmp     short loc_18000142E
0x180001425  mov     rdi, [rsp+38h+arg_0]
0x18000142a  mov     ebx, dword ptr [rsp+38h+arg_8]
0x18000142e  mov     rcx, [rdi+48h]; this
0x180001432  test    rcx, rcx
0x180001435  jz      short loc_1800013E2
0x180001437  mov     edx, ebx; int
0x180001439  call    ?RaiseException@CWbemDispatchMgr@@QEAAXJ@Z; CWbemDispatchMgr::RaiseException(long)
0x18000143e  jmp     short loc_1800013E2
```

# ATL::CRegObject::~CRegObject(void)

- ea: `0x140002228`
- end: `0x1400022c4`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002560`
- `0x140004d0c`
- `0x140005034`

## callees

- `0x140002228`
- `0x14000302c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140002289`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000229f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140002289`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000229f`
- `KERNEL32!DeleteCriticalSection` at `0x140002273`
- `KERNEL32!DeleteCriticalSection` at `0x140002273`
- `KERNEL32!EnterCriticalSection` at `0x14000224b`
- `KERNEL32!EnterCriticalSection` at `0x14000224b`
- `KERNEL32!LeaveCriticalSection` at `0x140002260`
- `KERNEL32!LeaveCriticalSection` at `0x140002260`

## pseudocode

```c
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  void **v3; // rdi
  void *v4; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  *(_QWORD *)this = &ATL::CRegObject::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v3 = (void **)((char *)this + 8);
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8));
  LeaveCriticalSection(v2);
  if ( LOBYTE(v2[1].DebugInfo) )
  {
    LOBYTE(v2[1].DebugInfo) = 0;
    DeleteCriticalSection(v2);
  }
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8));
  if ( *v3 )
  {
    free(*v3);
    *v3 = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 2) = 0;
  }
  *((_DWORD *)this + 6) = 0;
}

```

## disassembly

```asm
0x140002228  mov     [rsp+arg_0], rbx
0x14000222d  mov     [rsp+arg_8], rsi
0x140002232  push    rdi
0x140002233  sub     rsp, 20h
0x140002237  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x14000223e  mov     rbx, rcx
0x140002241  lea     rsi, [rcx+20h]
0x140002245  mov     [rcx], rax
0x140002248  mov     rcx, rsi; lpCriticalSection
0x14000224b  call    cs:__imp_EnterCriticalSection
0x140002251  lea     rdi, [rbx+8]
0x140002255  mov     rcx, rdi; this
0x140002258  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x14000225d  mov     rcx, rsi; lpCriticalSection
0x140002260  call    cs:__imp_LeaveCriticalSection
0x140002266  cmp     byte ptr [rsi+28h], 0
0x14000226a  jz      short loc_140002279
0x14000226c  mov     rcx, rsi; lpCriticalSection
0x14000226f  mov     byte ptr [rsi+28h], 0
0x140002273  call    cs:__imp_DeleteCriticalSection
0x140002279  mov     rcx, rdi; this
0x14000227c  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x140002281  mov     rcx, [rdi]; Block
0x140002284  test    rcx, rcx
0x140002287  jz      short loc_140002296
0x140002289  call    cs:__imp_free
0x14000228f  mov     qword ptr [rdi], 0
0x140002296  mov     rcx, [rbx+10h]; Block
0x14000229a  test    rcx, rcx
0x14000229d  jz      short loc_1400022AD
0x14000229f  call    cs:__imp_free
0x1400022a5  mov     qword ptr [rbx+10h], 0
0x1400022ad  mov     rsi, [rsp+28h+arg_8]
0x1400022b2  mov     dword ptr [rbx+18h], 0
0x1400022b9  mov     rbx, [rsp+28h+arg_0]
0x1400022be  add     rsp, 20h
0x1400022c2  pop     rdi
0x1400022c3  retn
```

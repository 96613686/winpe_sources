# CClientLibrary::AllocatePacket(void *,ulong)

- ea: `0x180004680`
- end: `0x180004743`
- name: `?AllocatePacket@CClientLibrary@@QEAAPEAXPEAXK@Z`
- size: `195`
- prototype: `void *(CClientLibrary *__hidden this, void *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000be30`
- `0x18000c190`
- `0x18000c5dc`

## callees

- `0x180004680`
- `0x18000d6d2`
- `0x18000e010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180004723`
- `KERNEL32!SetLastError` at `0x180004723`
- `KERNEL32!GetLastError` at `0x1800046e3`
- `KERNEL32!GetLastError` at `0x1800046e3`
- `WdsCommonLib!?Allocate@CMemoryBuffer@@SAPEAV1@K@Z` at `0x1800046f5`
- `WdsCommonLib!?Allocate@CMemoryBuffer@@SAPEAV1@K@Z` at `0x1800046f5`

## pseudocode

```c
void *__fastcall CClientLibrary::AllocatePacket(CClientLibrary *this, void *a2, unsigned int a3)
{
  DWORD LastError; // ebx
  size_t v4; // rsi
  void *v5; // rdi
  struct CMemoryBuffer *v6; // rax

  LastError = 0;
  v4 = a3;
  v5 = 0;
  if ( !_InterlockedExchangeAdd((volatile signed __int32 *)this + 10, 0) )
  {
    LastError = 5023;
LABEL_14:
    SetLastError(LastError);
    return v5;
  }
  if ( !a3 )
  {
    LastError = 87;
    goto LABEL_14;
  }
  if ( a2 )
  {
    if ( !*((_DWORD *)this + 12) )
    {
      LastError = 6;
      goto LABEL_14;
    }
    v5 = (void *)(*((__int64 (__fastcall **)(void *, _QWORD, _QWORD))this + 8))(a2, 0, a3);
    if ( !v5 )
    {
      LastError = GetLastError();
      goto LABEL_14;
    }
  }
  else
  {
    v6 = CMemoryBuffer::Allocate(a3);
    if ( !v6 )
    {
      LastError = 8;
      goto LABEL_14;
    }
    v5 = (void *)*((_QWORD *)v6 + 5);
  }
  memset_0(v5, 0, v4);
  if ( !v5 )
    goto LABEL_14;
  return v5;
}

```

## disassembly

```asm
0x180004680  mov     [rsp+arg_0], rbx
0x180004685  mov     [rsp+arg_8], rsi
0x18000468a  push    rdi
0x18000468b  sub     rsp, 20h
0x18000468f  xor     ebx, ebx
0x180004691  mov     esi, r8d
0x180004694  mov     edi, ebx
0x180004696  mov     eax, ebx
0x180004698  mov     r10, rdx
0x18000469b  mov     r9, rcx
0x18000469e  lock xadd [rcx+28h], eax
0x1800046a3  test    eax, eax
0x1800046a5  jnz     short loc_1800046AE
0x1800046a7  mov     ebx, 139Fh
0x1800046ac  jmp     short loc_180004721
0x1800046ae  test    r8d, r8d
0x1800046b1  jnz     short loc_1800046B9
0x1800046b3  lea     ebx, [r8+57h]
0x1800046b7  jmp     short loc_180004721
0x1800046b9  test    r10, r10
0x1800046bc  jz      short loc_1800046F3
0x1800046be  cmp     [rcx+30h], ebx
0x1800046c1  jnz     short loc_1800046CA
0x1800046c3  mov     ebx, 6
0x1800046c8  jmp     short loc_180004721
0x1800046ca  mov     rax, [r9+40h]
0x1800046ce  mov     r8d, esi
0x1800046d1  xor     edx, edx
0x1800046d3  mov     rcx, r10
0x1800046d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046db  mov     rdi, rax
0x1800046de  test    rax, rax
0x1800046e1  jnz     short loc_18000470F
0x1800046e3  call    cs:__imp_GetLastError
0x1800046ea  nop     dword ptr [rax+rax+00h]
0x1800046ef  mov     ebx, eax
0x1800046f1  jmp     short loc_180004721
0x1800046f3  mov     ecx, esi
0x1800046f5  call    cs:__imp_?Allocate@CMemoryBuffer@@SAPEAV1@K@Z; CMemoryBuffer::Allocate(ulong)
0x1800046fc  nop     dword ptr [rax+rax+00h]
0x180004701  test    rax, rax
0x180004704  jnz     short loc_18000470B
0x180004706  lea     ebx, [rax+8]
0x180004709  jmp     short loc_180004721
0x18000470b  mov     rdi, [rax+28h]
0x18000470f  mov     r8, rsi; Size
0x180004712  xor     edx, edx; Val
0x180004714  mov     rcx, rdi; void *
0x180004717  call    memset_0
0x18000471c  test    rdi, rdi
0x18000471f  jnz     short loc_18000472F
0x180004721  mov     ecx, ebx; dwErrCode
0x180004723  call    cs:__imp_SetLastError
0x18000472a  nop     dword ptr [rax+rax+00h]
0x18000472f  mov     rbx, [rsp+28h+arg_0]
0x180004734  mov     rax, rdi
0x180004737  mov     rsi, [rsp+28h+arg_8]
0x18000473c  add     rsp, 20h
0x180004740  pop     rdi
0x180004741  retn
```

# CIndexedDBServerTransaction::CTransactionThreadScope::Attach(void)

- ea: `0x180024870`
- end: `0x180024915`
- name: `?Attach@CTransactionThreadScope@CIndexedDBServerTransaction@@QEAAJXZ`
- size: `165`
- prototype: `__int64 __fastcall(CIndexedDBServerTransaction::CTransactionThreadScope *__hidden this)`
- caller_count: `26`
- callee_count: `2`
- tags: ``

## callers

- `0x18002ce80`
- `0x18002dbd0`
- `0x18002ff40`
- `0x180032498`
- `0x180045034`
- `0x18004dbe8`
- `0x18004dfc0`
- `0x180059cb4`
- `0x1800b16fc`
- `0x1800b182c`
- `0x1800b18f4`
- `0x1800b1a68`
- `0x1800b1b4c`
- `0x1800b1c34`
- `0x1800b1d0c`
- `0x1800b1e40`
- `0x1800b1f00`
- `0x1800b1fc8`
- `0x1800b20ac`
- `0x1800b216c`
- `0x1800b222c`
- `0x1800b2300`
- `0x1800b2404`
- `0x1800b24e8`
- `0x1800b3234`
- `0x1800b355c`

## callees

- `0x180024870`
- `0x18002491c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800248ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800248ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024897`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024897`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800248fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800248fb`

## pseudocode

```c
__int64 __fastcall CIndexedDBServerTransaction::CTransactionThreadScope::Attach(
        CIndexedDBServerTransaction::CTransactionThreadScope *this)
{
  __int64 v2; // rdi
  int v3; // esi
  unsigned __int64 v4; // rdi
  __int64 result; // rax

  if ( *(_BYTE *)this )
    return 2147500037LL;
  EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 1) + 192LL));
  v2 = *((_QWORD *)this + 1);
  v3 = -2147024891;
  if ( *(_BYTE *)(v2 + 56) )
  {
    v4 = *(_QWORD *)(v2 + 168);
    if ( *(_BYTE *)(v4 + 8) )
    {
      v3 = HrJetSetSessionContext(*(_QWORD *)(v4 + 24), v4);
      if ( v3 >= 0 )
        *(_DWORD *)(v4 + 12) = GetCurrentThreadId();
    }
  }
  if ( v3 < 0 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 1) + 192LL));
    return (unsigned int)v3;
  }
  else
  {
    result = (unsigned int)v3;
    *(_BYTE *)this = 1;
  }
  return result;
}

```

## disassembly

```asm
0x180024870  push    rbx
0x180024872  sub     rsp, 20h
0x180024876  cmp     byte ptr [rcx], 0
0x180024879  mov     rbx, rcx
0x18002487c  jnz     loc_18002490E
0x180024882  mov     rcx, [rcx+8]
0x180024886  add     rcx, 0C0h; lpCriticalSection
0x18002488d  mov     [rsp+28h+arg_0], rsi
0x180024892  mov     [rsp+28h+arg_8], rdi
0x180024897  call    cs:__imp_EnterCriticalSection
0x18002489d  mov     rdi, [rbx+8]
0x1800248a1  mov     esi, 80070005h
0x1800248a6  movzx   eax, byte ptr [rdi+38h]
0x1800248aa  nop
0x1800248ab  test    al, al
0x1800248ad  jz      short loc_1800248D7
0x1800248af  mov     rdi, [rdi+0A8h]
0x1800248b6  cmp     byte ptr [rdi+8], 0
0x1800248ba  jz      short loc_1800248D7
0x1800248bc  mov     rcx, [rdi+18h]; unsigned __int64
0x1800248c0  mov     rdx, rdi; unsigned __int64
0x1800248c3  call    ?HrJetSetSessionContext@@YAJ_K0@Z; HrJetSetSessionContext(unsigned __int64,unsigned __int64)
0x1800248c8  mov     esi, eax
0x1800248ca  test    eax, eax
0x1800248cc  js      short loc_1800248D7
0x1800248ce  call    cs:__imp_GetCurrentThreadId
0x1800248d4  mov     [rdi+0Ch], eax
0x1800248d7  mov     rdi, [rsp+28h+arg_8]
0x1800248dc  test    esi, esi
0x1800248de  js      short loc_1800248F0
0x1800248e0  mov     eax, esi
0x1800248e2  mov     byte ptr [rbx], 1
0x1800248e5  mov     rsi, [rsp+28h+arg_0]
0x1800248ea  add     rsp, 20h
0x1800248ee  pop     rbx
0x1800248ef  retn
0x1800248f0  mov     rcx, [rbx+8]
0x1800248f4  add     rcx, 0C0h; lpCriticalSection
0x1800248fb  call    cs:__imp_LeaveCriticalSection
0x180024901  mov     eax, esi
0x180024903  mov     rsi, [rsp+28h+arg_0]
0x180024908  add     rsp, 20h
0x18002490c  pop     rbx
0x18002490d  retn
0x18002490e  mov     eax, 80004005h
0x180024913  jmp     short loc_1800248EA
```

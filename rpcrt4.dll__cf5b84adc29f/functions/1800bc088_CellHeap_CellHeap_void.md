# CellHeap::~CellHeap(void)

- ea: `0x1800bc088`
- end: `0x1800bc13c`
- name: `??1CellHeap@@QEAA@XZ`
- size: `180`
- prototype: `void __fastcall(CellHeap *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a306c`

## callees

- `0x1800160dc`
- `0x180016600`
- `0x180023a40`
- `0x1800bc088`
- `0x1800cc2f8`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x1800bc11c`
- `ntdll!RtlDeleteCriticalSection` at `0x1800bc11c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800bc0ba`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800bc0ba`

## pseudocode

```c
void __fastcall CellHeap::~CellHeap(CellHeap *this)
{
  void *v2; // rcx
  __int16 *v3; // r9
  QUEUE *v4; // rbp
  __int64 v5; // r9
  CellHeap *v6; // rbx
  WINBOOL v7; // [rsp+40h] [rbp+8h] BYREF
  WINBOOL v8; // [rsp+48h] [rbp+10h] BYREF
  void *lpMem; // [rsp+50h] [rbp+18h] BYREF

  v2 = (void *)*((_QWORD *)this + 10);
  lpMem = 0;
  v8 = 0;
  v7 = 0;
  if ( v2 )
  {
    if ( GetSecurityDescriptorDacl(v2, &v8, (PACL *)&lpMem, &v7) )
      FreeWrapper(lpMem);
    FreeWrapper(*((void **)this + 10));
  }
  v3 = (__int16 *)*((_QWORD *)this + 2);
  if ( v3 == (__int16 *)((char *)this + 16) )
  {
    v4 = (CellHeap *)((char *)this + 32);
  }
  else
  {
    do
    {
      v4 = (CellHeap *)((char *)this + 32);
      SIMPLE_DICT::Delete((CellHeap *)((char *)this + 32), v3[2]);
      v6 = *(CellHeap **)(v5 + 32);
      CloseDbgSection(*(void **)(v5 + 24), (void *)v5);
      v3 = (__int16 *)v6;
    }
    while ( v6 != (CellHeap *)((char *)this + 16) );
  }
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 96));
  QUEUE::~QUEUE(v4);
}

```

## disassembly

```asm
0x1800bc088  mov     rax, rsp
0x1800bc08b  mov     [rax+20h], rbx
0x1800bc08f  push    rbp
0x1800bc090  push    rsi
0x1800bc091  push    rdi
0x1800bc092  sub     rsp, 20h
0x1800bc096  xor     ebx, ebx
0x1800bc098  mov     rdi, rcx
0x1800bc09b  mov     rcx, [rcx+50h]; pSecurityDescriptor
0x1800bc09f  mov     [rax+18h], rbx
0x1800bc0a3  mov     [rax+10h], ebx
0x1800bc0a6  mov     [rax+8], ebx
0x1800bc0a9  test    rcx, rcx
0x1800bc0ac  jz      short loc_1800BC0DD
0x1800bc0ae  lea     r9, [rax+8]; lpbDaclDefaulted
0x1800bc0b2  lea     r8, [rax+18h]; pDacl
0x1800bc0b6  lea     rdx, [rax+10h]; lpbDaclPresent
0x1800bc0ba  call    cs:__imp_GetSecurityDescriptorDacl
0x1800bc0c1  nop     dword ptr [rax+rax+00h]
0x1800bc0c6  test    eax, eax
0x1800bc0c8  jz      short loc_1800BC0D4
0x1800bc0ca  mov     rcx, [rsp+38h+lpMem]; lpMem
0x1800bc0cf  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800bc0d4  mov     rcx, [rdi+50h]; lpMem
0x1800bc0d8  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800bc0dd  lea     rsi, [rdi+10h]
0x1800bc0e1  mov     r9, [rsi]
0x1800bc0e4  cmp     r9, rsi
0x1800bc0e7  jz      short loc_1800BC114
0x1800bc0e9  movsx   edx, word ptr [r9+4]; unsigned int
0x1800bc0ee  lea     rbp, [rdi+20h]
0x1800bc0f2  mov     rcx, rbp; this
0x1800bc0f5  call    ?Delete@SIMPLE_DICT@@QEAAPEAXI@Z; SIMPLE_DICT::Delete(uint)
0x1800bc0fa  mov     rcx, [r9+18h]; void *
0x1800bc0fe  mov     rdx, r9; void *
0x1800bc101  mov     rbx, [r9+20h]
0x1800bc105  call    ?CloseDbgSection@@YAXPEAX0@Z; CloseDbgSection(void *,void *)
0x1800bc10a  mov     r9, rbx
0x1800bc10d  cmp     rbx, rsi
0x1800bc110  jnz     short loc_1800BC0E9
0x1800bc112  jmp     short loc_1800BC118
0x1800bc114  lea     rbp, [rdi+20h]
0x1800bc118  lea     rcx, [rdi+60h]; CriticalSection
0x1800bc11c  call    cs:__imp_RtlDeleteCriticalSection
0x1800bc123  nop     dword ptr [rax+rax+00h]
0x1800bc128  mov     rcx, rbp; this
0x1800bc12b  mov     rbx, [rsp+38h+arg_18]
0x1800bc130  add     rsp, 20h
0x1800bc134  pop     rdi
0x1800bc135  pop     rsi
0x1800bc136  pop     rbp
0x1800bc137  jmp     ??1QUEUE@@QEAA@XZ; QUEUE::~QUEUE(void)
```

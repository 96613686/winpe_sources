# CellHeap::~CellHeap(void)

- ea: `0x1800b7ca4`
- end: `0x1800b7d4c`
- name: `??1CellHeap@@QEAA@XZ`
- size: `168`
- prototype: `void __fastcall(CellHeap *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18009fa24`

## callees

- `0x180022870`
- `0x18004a8c8`
- `0x18004cc10`
- `0x1800b7ca4`
- `0x1800c77ac`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x1800b7d32`
- `ntdll!RtlDeleteCriticalSection` at `0x1800b7d32`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800b7cd6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800b7cd6`

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
0x1800b7ca4  mov     rax, rsp
0x1800b7ca7  mov     [rax+20h], rbx
0x1800b7cab  push    rbp
0x1800b7cac  push    rsi
0x1800b7cad  push    rdi
0x1800b7cae  sub     rsp, 20h
0x1800b7cb2  xor     ebx, ebx
0x1800b7cb4  mov     rdi, rcx
0x1800b7cb7  mov     rcx, [rcx+50h]; pSecurityDescriptor
0x1800b7cbb  mov     [rax+18h], rbx
0x1800b7cbf  mov     [rax+10h], ebx
0x1800b7cc2  mov     [rax+8], ebx
0x1800b7cc5  test    rcx, rcx
0x1800b7cc8  jz      short loc_1800B7CF3
0x1800b7cca  lea     r9, [rax+8]; lpbDaclDefaulted
0x1800b7cce  lea     r8, [rax+18h]; pDacl
0x1800b7cd2  lea     rdx, [rax+10h]; lpbDaclPresent
0x1800b7cd6  call    cs:__imp_GetSecurityDescriptorDacl
0x1800b7cdc  test    eax, eax
0x1800b7cde  jz      short loc_1800B7CEA
0x1800b7ce0  mov     rcx, [rsp+38h+lpMem]; lpMem
0x1800b7ce5  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800b7cea  mov     rcx, [rdi+50h]; lpMem
0x1800b7cee  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800b7cf3  lea     rsi, [rdi+10h]
0x1800b7cf7  mov     r9, [rsi]
0x1800b7cfa  cmp     r9, rsi
0x1800b7cfd  jz      short loc_1800B7D2A
0x1800b7cff  movsx   edx, word ptr [r9+4]; unsigned int
0x1800b7d04  lea     rbp, [rdi+20h]
0x1800b7d08  mov     rcx, rbp; this
0x1800b7d0b  call    ?Delete@SIMPLE_DICT@@QEAAPEAXI@Z; SIMPLE_DICT::Delete(uint)
0x1800b7d10  mov     rcx, [r9+18h]; void *
0x1800b7d14  mov     rdx, r9; void *
0x1800b7d17  mov     rbx, [r9+20h]
0x1800b7d1b  call    ?CloseDbgSection@@YAXPEAX0@Z; CloseDbgSection(void *,void *)
0x1800b7d20  mov     r9, rbx
0x1800b7d23  cmp     rbx, rsi
0x1800b7d26  jnz     short loc_1800B7CFF
0x1800b7d28  jmp     short loc_1800B7D2E
0x1800b7d2a  lea     rbp, [rdi+20h]
0x1800b7d2e  lea     rcx, [rdi+60h]; CriticalSection
0x1800b7d32  call    cs:__imp_RtlDeleteCriticalSection
0x1800b7d38  mov     rcx, rbp; this
0x1800b7d3b  mov     rbx, [rsp+38h+arg_18]
0x1800b7d40  add     rsp, 20h
0x1800b7d44  pop     rdi
0x1800b7d45  pop     rsi
0x1800b7d46  pop     rbp
0x1800b7d47  jmp     ??1QUEUE@@QEAA@XZ; QUEUE::~QUEUE(void)
```

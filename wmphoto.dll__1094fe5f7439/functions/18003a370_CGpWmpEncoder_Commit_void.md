# CGpWmpEncoder::Commit(void)

- ea: `0x18003a370`
- end: `0x18003a3ce`
- name: `?Commit@CGpWmpEncoder@@UEAAJXZ`
- size: `94`
- prototype: `__int64 __fastcall(CGpWmpEncoder *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18002db34`
- `0x18003a370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a391`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a391`

## pseudocode

```c
__int64 __fastcall CGpWmpEncoder::Commit(CGpWmpEncoder *this)
{
  char *v1; // rax
  struct _RTL_CRITICAL_SECTION *v3; // rcx
  unsigned int v4; // ebx
  char *v6; // [rsp+30h] [rbp+8h] BYREF

  v1 = (char *)this - 56;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 48);
  v6 = v1;
  v4 = 0;
  if ( LOBYTE(v3[1].DebugInfo) )
    EnterCriticalSection(v3);
  if ( *((_DWORD *)this - 16) == 2 )
  {
    if ( *((_DWORD *)this + 13) )
      *((_DWORD *)this - 16) = 4;
    else
      v4 = -2003292318;
  }
  else
  {
    v4 = -2003292412;
  }
  CGuard<CMTALock>::~CGuard<CMTALock>(&v6);
  return v4;
}

```

## disassembly

```asm
0x18003a370  mov     [rsp+arg_8], rbx
0x18003a375  push    rdi
0x18003a376  sub     rsp, 20h
0x18003a37a  lea     rax, [rcx-38h]
0x18003a37e  mov     rdi, rcx
0x18003a381  lea     rcx, [rax+8]; lpCriticalSection
0x18003a385  mov     [rsp+28h+arg_0], rax
0x18003a38a  xor     ebx, ebx
0x18003a38c  cmp     [rcx+28h], bl
0x18003a38f  jz      short loc_18003A397
0x18003a391  call    cs:__imp_EnterCriticalSection
0x18003a397  cmp     dword ptr [rdi-40h], 2
0x18003a39b  jnz     short loc_18003A3B2
0x18003a39d  cmp     [rdi+34h], ebx
0x18003a3a0  jz      short loc_18003A3AB
0x18003a3a2  mov     dword ptr [rdi-40h], 4
0x18003a3a9  jmp     short loc_18003A3B7
0x18003a3ab  mov     ebx, 88982F62h
0x18003a3b0  jmp     short loc_18003A3B7
0x18003a3b2  mov     ebx, 88982F04h
0x18003a3b7  lea     rcx, [rsp+28h+arg_0]
0x18003a3bc  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003a3c1  mov     eax, ebx
0x18003a3c3  mov     rbx, [rsp+28h+arg_8]
0x18003a3c8  add     rsp, 20h
0x18003a3cc  pop     rdi
0x18003a3cd  retn
```

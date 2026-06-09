# CGpWmpEncoder::Commit(void)

- ea: `0x18003aac0`
- end: `0x18003ab25`
- name: `?Commit@CGpWmpEncoder@@UEAAJXZ`
- size: `101`
- prototype: `__int64 __fastcall(CGpWmpEncoder *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18002de30`
- `0x18003aac0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003aae1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003aae1`

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
0x18003aac0  mov     [rsp+arg_8], rbx
0x18003aac5  push    rdi
0x18003aac6  sub     rsp, 20h
0x18003aaca  lea     rax, [rcx-38h]
0x18003aace  mov     rdi, rcx
0x18003aad1  lea     rcx, [rax+8]; lpCriticalSection
0x18003aad5  mov     [rsp+28h+arg_0], rax
0x18003aada  xor     ebx, ebx
0x18003aadc  cmp     [rcx+28h], bl
0x18003aadf  jz      short loc_18003AAED
0x18003aae1  call    cs:__imp_EnterCriticalSection
0x18003aae8  nop     dword ptr [rax+rax+00h]
0x18003aaed  cmp     dword ptr [rdi-40h], 2
0x18003aaf1  jnz     short loc_18003AB08
0x18003aaf3  cmp     [rdi+34h], ebx
0x18003aaf6  jz      short loc_18003AB01
0x18003aaf8  mov     dword ptr [rdi-40h], 4
0x18003aaff  jmp     short loc_18003AB0D
0x18003ab01  mov     ebx, 88982F62h
0x18003ab06  jmp     short loc_18003AB0D
0x18003ab08  mov     ebx, 88982F04h
0x18003ab0d  lea     rcx, [rsp+28h+arg_0]
0x18003ab12  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003ab17  mov     eax, ebx
0x18003ab19  mov     rbx, [rsp+28h+arg_8]
0x18003ab1e  add     rsp, 20h
0x18003ab22  pop     rdi
0x18003ab23  retn
```

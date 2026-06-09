# DelayedLoadCryptoRandom::~DelayedLoadCryptoRandom(void)

- ea: `0x180033fe0`
- end: `0x180034057`
- name: `??1DelayedLoadCryptoRandom@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(DelayedLoadCryptoRandom *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002f900`

## callees

- `0x180033fe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003402a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003402a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033ffa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033ffa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003403f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003403f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180034011`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180034011`

## pseudocode

```c
void __fastcall DelayedLoadCryptoRandom::~DelayedLoadCryptoRandom(DelayedLoadCryptoRandom *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  if ( *((_DWORD *)this + 14) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( *(_DWORD *)this && CryptReleaseContext(*((_QWORD *)this + 6), 0) )
      *(_DWORD *)this = 0;
    LeaveCriticalSection(v1);
  }
  if ( *((_DWORD *)this + 14) )
    DeleteCriticalSection(v1);
}

```

## disassembly

```asm
0x180033fe0  mov     [rsp+arg_0], rbx
0x180033fe5  push    rdi
0x180033fe6  sub     rsp, 20h
0x180033fea  cmp     dword ptr [rcx+38h], 0
0x180033fee  lea     rdi, [rcx+8]
0x180033ff2  mov     rbx, rcx
0x180033ff5  jz      short loc_180034036
0x180033ff7  mov     rcx, rdi; lpCriticalSection
0x180033ffa  call    cs:__imp_EnterCriticalSection
0x180034001  nop     dword ptr [rax+rax+00h]
0x180034006  cmp     dword ptr [rbx], 0
0x180034009  jz      short loc_180034027
0x18003400b  mov     rcx, [rbx+30h]; hProv
0x18003400f  xor     edx, edx; dwFlags
0x180034011  call    cs:__imp_CryptReleaseContext
0x180034018  nop     dword ptr [rax+rax+00h]
0x18003401d  test    eax, eax
0x18003401f  jz      short loc_180034027
0x180034021  mov     dword ptr [rbx], 0
0x180034027  mov     rcx, rdi; lpCriticalSection
0x18003402a  call    cs:__imp_LeaveCriticalSection
0x180034031  nop     dword ptr [rax+rax+00h]
0x180034036  cmp     dword ptr [rbx+38h], 0
0x18003403a  jz      short loc_18003404B
0x18003403c  mov     rcx, rdi; lpCriticalSection
0x18003403f  call    cs:__imp_DeleteCriticalSection
0x180034046  nop     dword ptr [rax+rax+00h]
0x18003404b  mov     rbx, [rsp+28h+arg_0]
0x180034050  add     rsp, 20h
0x180034054  pop     rdi
0x180034055  retn
```

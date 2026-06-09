# DelayedLoadCryptoRandom::~DelayedLoadCryptoRandom(void)

- ea: `0x180031738`
- end: `0x180031796`
- name: `??1DelayedLoadCryptoRandom@@QEAA@XZ`
- size: `94`
- prototype: `void __fastcall(DelayedLoadCryptoRandom *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002d870`

## callees

- `0x180031738`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031776`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031776`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031752`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031752`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031785`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031785`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180031763`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180031763`

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
0x180031738  mov     [rsp+arg_0], rbx
0x18003173d  push    rdi
0x18003173e  sub     rsp, 20h
0x180031742  cmp     dword ptr [rcx+38h], 0
0x180031746  lea     rdi, [rcx+8]
0x18003174a  mov     rbx, rcx
0x18003174d  jz      short loc_18003177C
0x18003174f  mov     rcx, rdi; lpCriticalSection
0x180031752  call    cs:__imp_EnterCriticalSection
0x180031758  cmp     dword ptr [rbx], 0
0x18003175b  jz      short loc_180031773
0x18003175d  mov     rcx, [rbx+30h]; hProv
0x180031761  xor     edx, edx; dwFlags
0x180031763  call    cs:__imp_CryptReleaseContext
0x180031769  test    eax, eax
0x18003176b  jz      short loc_180031773
0x18003176d  mov     dword ptr [rbx], 0
0x180031773  mov     rcx, rdi; lpCriticalSection
0x180031776  call    cs:__imp_LeaveCriticalSection
0x18003177c  cmp     dword ptr [rbx+38h], 0
0x180031780  jz      short loc_18003178B
0x180031782  mov     rcx, rdi; lpCriticalSection
0x180031785  call    cs:__imp_DeleteCriticalSection
0x18003178b  mov     rbx, [rsp+28h+arg_0]
0x180031790  add     rsp, 20h
0x180031794  pop     rdi
0x180031795  retn
```

# C1in1outDMO::GetOutputCurrentType(ulong,_AMMediaType *)

- ea: `0x180004880`
- end: `0x180004926`
- name: `?GetOutputCurrentType@C1in1outDMO@@UEAAJKPEAU_AMMediaType@@@Z`
- size: `166`
- prototype: `int(C1in1outDMO *__hidden this, unsigned int, struct _AMMediaType *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800048aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800048ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800048eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004915`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800048aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800048ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800048eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004915`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004898`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004898`
- `msdmo!MoCopyMediaType` at `0x180004906`
- `msdmo!MoCopyMediaType` at `0x180004906`

## pseudocode

```c
__int64 __fastcall C1in1outDMO::GetOutputCurrentType(C1in1outDMO *this, int a2, struct _AMMediaType *a3)
{
  unsigned int v7; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  if ( a2 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
    return 2147746305LL;
  }
  else if ( a3 )
  {
    if ( *((_DWORD *)this + 3) )
    {
      v7 = MoCopyMediaType(a3, (const DMO_MEDIA_TYPE *)((char *)this + 104));
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
      return v7;
    }
    else
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
      return 2147746307LL;
    }
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180004880  push    rbx
0x180004882  push    rbp
0x180004883  push    rsi
0x180004884  push    rdi
0x180004885  sub     rsp, 28h
0x180004889  mov     rsi, rcx
0x18000488c  mov     rbp, r8
0x18000488f  add     rcx, 0D8h; lpCriticalSection
0x180004896  mov     ebx, edx
0x180004898  call    cs:__imp_EnterCriticalSection
0x18000489e  cmp     ebx, 1
0x1800048a1  jb      short loc_1800048BE
0x1800048a3  lea     rcx, [rsi+0D8h]; lpCriticalSection
0x1800048aa  call    cs:__imp_LeaveCriticalSection
0x1800048b0  mov     eax, 80040201h
0x1800048b5  add     rsp, 28h
0x1800048b9  pop     rdi
0x1800048ba  pop     rsi
0x1800048bb  pop     rbp
0x1800048bc  pop     rbx
0x1800048bd  retn
0x1800048be  test    rbp, rbp
0x1800048c1  jnz     short loc_1800048DE
0x1800048c3  lea     rcx, [rsi+0D8h]; lpCriticalSection
0x1800048ca  call    cs:__imp_LeaveCriticalSection
0x1800048d0  mov     eax, 80004003h
0x1800048d5  add     rsp, 28h
0x1800048d9  pop     rdi
0x1800048da  pop     rsi
0x1800048db  pop     rbp
0x1800048dc  pop     rbx
0x1800048dd  retn
0x1800048de  cmp     dword ptr [rsi+0Ch], 0
0x1800048e2  jnz     short loc_1800048FF
0x1800048e4  lea     rcx, [rsi+0D8h]; lpCriticalSection
0x1800048eb  call    cs:__imp_LeaveCriticalSection
0x1800048f1  mov     eax, 80040203h
0x1800048f6  add     rsp, 28h
0x1800048fa  pop     rdi
0x1800048fb  pop     rsi
0x1800048fc  pop     rbp
0x1800048fd  pop     rbx
0x1800048fe  retn
0x1800048ff  lea     rdx, [rsi+68h]; pmtSrc
0x180004903  mov     rcx, rbp; pmtDest
0x180004906  call    cs:__imp_MoCopyMediaType
0x18000490c  lea     rcx, [rsi+0D8h]; lpCriticalSection
0x180004913  mov     ebx, eax
0x180004915  call    cs:__imp_LeaveCriticalSection
0x18000491b  mov     eax, ebx
0x18000491d  add     rsp, 28h
0x180004921  pop     rdi
0x180004922  pop     rsi
0x180004923  pop     rbp
0x180004924  pop     rbx
0x180004925  retn
```

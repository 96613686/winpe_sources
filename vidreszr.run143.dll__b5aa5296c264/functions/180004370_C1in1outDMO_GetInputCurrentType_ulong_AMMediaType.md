# C1in1outDMO::GetInputCurrentType(ulong,_AMMediaType *)

- ea: `0x180004370`
- end: `0x180004416`
- name: `?GetInputCurrentType@C1in1outDMO@@UEAAJKPEAU_AMMediaType@@@Z`
- size: `166`
- prototype: `int(C1in1outDMO *__hidden this, unsigned int, struct _AMMediaType *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000439a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004405`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000439a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004405`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004388`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004388`
- `msdmo!MoCopyMediaType` at `0x1800043f6`
- `msdmo!MoCopyMediaType` at `0x1800043f6`

## pseudocode

```c
__int64 __fastcall C1in1outDMO::GetInputCurrentType(C1in1outDMO *this, int a2, struct _AMMediaType *a3)
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
    if ( *((_DWORD *)this + 2) )
    {
      v7 = MoCopyMediaType(a3, (const DMO_MEDIA_TYPE *)((char *)this + 16));
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
0x180004370  push    rbx
0x180004372  push    rbp
0x180004373  push    rsi
0x180004374  push    rdi
0x180004375  sub     rsp, 28h
0x180004379  mov     rsi, rcx
0x18000437c  mov     rbp, r8
0x18000437f  add     rcx, 0D8h; lpCriticalSection
0x180004386  mov     ebx, edx
0x180004388  call    cs:__imp_EnterCriticalSection
0x18000438e  cmp     ebx, 1
0x180004391  jb      short loc_1800043AE
0x180004393  lea     rcx, [rsi+0D8h]; lpCriticalSection
0x18000439a  call    cs:__imp_LeaveCriticalSection
0x1800043a0  mov     eax, 80040201h
0x1800043a5  add     rsp, 28h
0x1800043a9  pop     rdi
0x1800043aa  pop     rsi
0x1800043ab  pop     rbp
0x1800043ac  pop     rbx
0x1800043ad  retn
0x1800043ae  test    rbp, rbp
0x1800043b1  jnz     short loc_1800043CE
0x1800043b3  lea     rcx, [rsi+0D8h]; lpCriticalSection
0x1800043ba  call    cs:__imp_LeaveCriticalSection
0x1800043c0  mov     eax, 80004003h
0x1800043c5  add     rsp, 28h
0x1800043c9  pop     rdi
0x1800043ca  pop     rsi
0x1800043cb  pop     rbp
0x1800043cc  pop     rbx
0x1800043cd  retn
0x1800043ce  cmp     dword ptr [rsi+8], 0
0x1800043d2  jnz     short loc_1800043EF
0x1800043d4  lea     rcx, [rsi+0D8h]; lpCriticalSection
0x1800043db  call    cs:__imp_LeaveCriticalSection
0x1800043e1  mov     eax, 80040203h
0x1800043e6  add     rsp, 28h
0x1800043ea  pop     rdi
0x1800043eb  pop     rsi
0x1800043ec  pop     rbp
0x1800043ed  pop     rbx
0x1800043ee  retn
0x1800043ef  lea     rdx, [rsi+10h]; pmtSrc
0x1800043f3  mov     rcx, rbp; pmtDest
0x1800043f6  call    cs:__imp_MoCopyMediaType
0x1800043fc  lea     rcx, [rsi+0D8h]; lpCriticalSection
0x180004403  mov     ebx, eax
0x180004405  call    cs:__imp_LeaveCriticalSection
0x18000440b  mov     eax, ebx
0x18000440d  add     rsp, 28h
0x180004411  pop     rdi
0x180004412  pop     rsi
0x180004413  pop     rbp
0x180004414  pop     rbx
0x180004415  retn
```

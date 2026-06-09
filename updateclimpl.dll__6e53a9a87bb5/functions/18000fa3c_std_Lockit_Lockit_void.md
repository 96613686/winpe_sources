# std::_Lockit::~_Lockit(void)

- ea: `0x18000fa3c`
- end: `0x18000fa71`
- name: `??1_Lockit@std@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(std::_Lockit *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180009888`
- `0x18000aa3c`
- `0x18000f4bc`
- `0x18000fabc`
- `0x18000fbc0`
- `0x18000fc90`
- `0x180015cf1`
- `0x180015d4b`
- `0x180015e6f`

## callees

- `0x18000fa3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fa66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fa66`
- `api-ms-win-crt-locale-l1-1-0!_unlock_locales` at `0x18000fa4b`

## pseudocode

```c
void __fastcall std::_Lockit::~_Lockit(std::_Lockit *this)
{
  __int64 v1; // rax

  v1 = *(int *)this;
  if ( (_DWORD)v1 )
  {
    if ( (int)v1 < 8 )
      LeaveCriticalSection(&CriticalSection + v1);
  }
  else
  {
    _unlock_locales();
  }
}

```

## disassembly

```asm
0x18000fa3c  sub     rsp, 28h
0x18000fa40  movsxd  rax, dword ptr [rcx]
0x18000fa43  test    eax, eax
0x18000fa45  jnz     short loc_18000FA52
0x18000fa47  add     rsp, 28h
0x18000fa4b  jmp     cs:__imp__unlock_locales
0x18000fa52  cmp     eax, 8
0x18000fa55  jge     short loc_18000FA6C
0x18000fa57  lea     rcx, [rax+rax*4]
0x18000fa5b  lea     rax, CriticalSection
0x18000fa62  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18000fa66  call    cs:__imp_LeaveCriticalSection
0x18000fa6c  add     rsp, 28h
0x18000fa70  retn
```

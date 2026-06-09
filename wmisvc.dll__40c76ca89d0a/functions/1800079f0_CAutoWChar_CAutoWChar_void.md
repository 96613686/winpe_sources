# CAutoWChar::~CAutoWChar(void)

- ea: `0x1800079f0`
- end: `0x180007a14`
- name: `??1CAutoWChar@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(void **this)`
- caller_count: `28`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002478`
- `0x180005048`
- `0x18000d744`
- `0x18000e230`
- `0x1800174ec`
- `0x180017e3c`
- `0x18001855c`
- `0x180018850`
- `0x1800193b4`
- `0x18001947c`
- `0x180019520`
- `0x180019bbc`
- `0x18001a310`
- `0x18001b9bc`
- `0x18001d55e`
- `0x18001d62f`
- `0x18001d641`
- `0x18001d677`
- `0x18001d6e3`
- `0x18001d768`
- `0x18001d780`
- `0x18001d8f7`
- `0x18001d909`
- `0x18001d91b`
- `0x18001e2e8`
- `0x18001ec4e`
- `0x18001ec9e`
- `0x18001eda1`

## callees

- `0x1800079f0`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180007a01`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180007a01`

## pseudocode

```c
void __fastcall CAutoWChar::~CAutoWChar(void **this)
{
  void *v2; // rcx

  v2 = *this;
  if ( v2 )
    CWin32DefaultArena::WbemMemFree(v2);
  *this = 0;
}

```

## disassembly

```asm
0x1800079f0  push    rbx
0x1800079f2  sub     rsp, 20h
0x1800079f6  mov     rbx, rcx
0x1800079f9  mov     rcx, [rcx]
0x1800079fc  test    rcx, rcx
0x1800079ff  jz      short loc_180007A07
0x180007a01  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180007a07  mov     qword ptr [rbx], 0
0x180007a0e  add     rsp, 20h
0x180007a12  pop     rbx
0x180007a13  retn
```

# CWcnWfdGoApiWrapper::~CWcnWfdGoApiWrapper(void)

- ea: `0x180052b20`
- end: `0x180052b49`
- name: `??1CWcnWfdGoApiWrapper@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(CWcnWfdGoApiWrapper *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18004d780`
- `0x18005956f`

## callees

- `0x180052b20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052b42`
- `wlanapi!WFDCloseHandleInt` at `0x180052b33`
- `wlanapi!WFDCloseHandleInt` at `0x180052b33`

## pseudocode

```c
void __fastcall CWcnWfdGoApiWrapper::~CWcnWfdGoApiWrapper(CWcnWfdGoApiWrapper *this)
{
  if ( *((_DWORD *)this + 14) )
    WFDCloseHandleInt(*((_QWORD *)this + 8));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180052b20  push    rbx
0x180052b22  sub     rsp, 20h
0x180052b26  cmp     dword ptr [rcx+38h], 0
0x180052b2a  mov     rbx, rcx
0x180052b2d  jz      short loc_180052B39
0x180052b2f  mov     rcx, [rcx+40h]
0x180052b33  call    cs:__imp_WFDCloseHandleInt
0x180052b39  lea     rcx, [rbx+10h]
0x180052b3d  add     rsp, 20h
0x180052b41  pop     rbx
0x180052b42  jmp     cs:__imp_DeleteCriticalSection
```

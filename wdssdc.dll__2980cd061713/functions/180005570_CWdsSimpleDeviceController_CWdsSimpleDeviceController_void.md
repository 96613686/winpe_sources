# CWdsSimpleDeviceController::~CWdsSimpleDeviceController(void)

- ea: `0x180005570`
- end: `0x1800055aa`
- name: `??1CWdsSimpleDeviceController@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(CWdsSimpleDeviceController *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800027e0`
- `0x180002860`

## callees

- `0x180005570`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000557d`
- `KERNEL32!DeleteCriticalSection` at `0x180005597`
- `KERNEL32!DeleteCriticalSection` at `0x18000557d`
- `KERNEL32!DeleteCriticalSection` at `0x180005597`

## pseudocode

```c
void __fastcall CWdsSimpleDeviceController::~CWdsSimpleDeviceController(CWdsSimpleDeviceController *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( *((_BYTE *)this + 64) )
  {
    *((_BYTE *)this + 64) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  }
}

```

## disassembly

```asm
0x180005570  push    rbx
0x180005572  sub     rsp, 20h
0x180005576  mov     rbx, rcx
0x180005579  add     rcx, 48h ; 'H'; lpCriticalSection
0x18000557d  call    cs:__imp_DeleteCriticalSection
0x180005584  nop     dword ptr [rax+rax+00h]
0x180005589  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000558d  cmp     byte ptr [rcx+28h], 0
0x180005591  jz      short loc_1800055A3
0x180005593  mov     byte ptr [rcx+28h], 0
0x180005597  call    cs:__imp_DeleteCriticalSection
0x18000559e  nop     dword ptr [rax+rax+00h]
0x1800055a3  add     rsp, 20h
0x1800055a7  pop     rbx
0x1800055a8  retn
```

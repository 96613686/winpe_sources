# CThemeServer::~CThemeServer(void)

- ea: `0x180006144`
- end: `0x18000618d`
- name: `??1CThemeServer@@QEAA@XZ`
- size: `73`
- prototype: `void __fastcall(void **this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006114`

## callees

- `0x180006144`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006171`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006171`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006155`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006155`

## pseudocode

```c
void __fastcall CThemeServer::~CThemeServer(void **this)
{
  void *v2; // rcx
  struct _RTL_CRITICAL_SECTION *v3; // rbx

  v2 = *this;
  if ( v2 )
  {
    CloseHandle(v2);
    *this = 0;
  }
  v3 = (struct _RTL_CRITICAL_SECTION *)(this + 5);
  if ( v3 )
  {
    if ( v3->DebugInfo )
    {
      DeleteCriticalSection(v3);
      *(_OWORD *)&v3->DebugInfo = 0;
      *(_OWORD *)&v3->OwningThread = 0;
      v3->SpinCount = 0;
    }
  }
}

```

## disassembly

```asm
0x180006144  push    rbx
0x180006146  sub     rsp, 20h
0x18000614a  mov     rbx, rcx
0x18000614d  mov     rcx, [rcx]; hObject
0x180006150  test    rcx, rcx
0x180006153  jz      short loc_180006162
0x180006155  call    cs:__imp_CloseHandle
0x18000615b  mov     qword ptr [rbx], 0
0x180006162  add     rbx, 28h ; '('
0x180006166  jz      short loc_180006187
0x180006168  cmp     qword ptr [rbx], 0
0x18000616c  jz      short loc_180006187
0x18000616e  mov     rcx, rbx; lpCriticalSection
0x180006171  call    cs:__imp_DeleteCriticalSection
0x180006177  xorps   xmm0, xmm0
0x18000617a  xor     eax, eax
0x18000617c  movups  xmmword ptr [rbx], xmm0
0x18000617f  movups  xmmword ptr [rbx+10h], xmm0
0x180006183  mov     [rbx+20h], rax
0x180006187  add     rsp, 20h
0x18000618b  pop     rbx
0x18000618c  retn
```

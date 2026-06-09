# CDropImpersonation::~CDropImpersonation(void)

- ea: `0x180032644`
- end: `0x180032679`
- name: `??1CDropImpersonation@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CDropImpersonation *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800083e0`

## callees

- `0x180032644`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180032658`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180032658`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032666`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032666`

## pseudocode

```c
void __fastcall CDropImpersonation::~CDropImpersonation(CDropImpersonation *this)
{
  HANDLE *v1; // rbx

  v1 = (HANDLE *)((char *)this + 8);
  if ( *(_BYTE *)this )
    SetThreadToken(0, *v1);
  if ( *v1 )
  {
    CloseHandle(*v1);
    *v1 = 0;
  }
}

```

## disassembly

```asm
0x180032644  push    rbx
0x180032646  sub     rsp, 20h
0x18003264a  cmp     byte ptr [rcx], 0
0x18003264d  lea     rbx, [rcx+8]
0x180032651  jz      short loc_18003265E
0x180032653  mov     rdx, [rbx]; Token
0x180032656  xor     ecx, ecx; Thread
0x180032658  call    cs:__imp_SetThreadToken
0x18003265e  mov     rcx, [rbx]; hObject
0x180032661  test    rcx, rcx
0x180032664  jz      short loc_180032673
0x180032666  call    cs:__imp_CloseHandle
0x18003266c  mov     qword ptr [rbx], 0
0x180032673  add     rsp, 20h
0x180032677  pop     rbx
0x180032678  retn
```

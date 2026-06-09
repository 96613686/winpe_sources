# CParseTreeNode::~CParseTreeNode(void)

- ea: `0x18000ee14`
- end: `0x18000ee50`
- name: `??1CParseTreeNode@@UEAA@XZ`
- size: `60`
- prototype: `void __fastcall(CParseTreeNode *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009178`

## callees

- `0x18000ee14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ee21`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ee21`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000ee30`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000ee30`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ee44`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ee44`

## pseudocode

```c
void __fastcall CParseTreeNode::~CParseTreeNode(CParseTreeNode *this)
{
  SAFEARRAY *v2; // rcx

  free(*((void **)this + 10));
  v2 = (SAFEARRAY *)*((_QWORD *)this + 12);
  if ( v2 )
    SafeArrayDestroy(v2);
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x18000ee14  push    rbx
0x18000ee16  sub     rsp, 20h
0x18000ee1a  mov     rbx, rcx
0x18000ee1d  mov     rcx, [rcx+50h]; Block
0x18000ee21  call    cs:__imp_free
0x18000ee27  mov     rcx, [rbx+60h]; psa
0x18000ee2b  test    rcx, rcx
0x18000ee2e  jz      short loc_18000EE36
0x18000ee30  call    cs:__imp_SafeArrayDestroy
0x18000ee36  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000ee3a  cmp     byte ptr [rcx+28h], 0
0x18000ee3e  jz      short loc_18000EE4A
0x18000ee40  mov     byte ptr [rcx+28h], 0
0x18000ee44  call    cs:__imp_DeleteCriticalSection
0x18000ee4a  add     rsp, 20h
0x18000ee4e  pop     rbx
0x18000ee4f  retn
```

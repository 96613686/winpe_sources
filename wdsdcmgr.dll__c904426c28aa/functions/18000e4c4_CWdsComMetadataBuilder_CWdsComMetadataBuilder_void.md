# CWdsComMetadataBuilder::~CWdsComMetadataBuilder(void)

- ea: `0x18000e4c4`
- end: `0x18000e4fd`
- name: `??1CWdsComMetadataBuilder@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(CWdsComMetadataBuilder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e390`
- `0x180011450`

## callees

- `0x18000a5e8`
- `0x18000e4c4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000e4d4`
- `KERNEL32!DeleteCriticalSection` at `0x18000e4f1`
- `KERNEL32!DeleteCriticalSection` at `0x18000e4d4`
- `KERNEL32!DeleteCriticalSection` at `0x18000e4f1`

## pseudocode

```c
void __fastcall CWdsComMetadataBuilder::~CWdsComMetadataBuilder(CWdsComMetadataBuilder *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  CWdsMetadata::~CWdsMetadata((CWdsComMetadataBuilder *)((char *)this + 64));
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x18000e4c4  push    rbx
0x18000e4c6  sub     rsp, 20h
0x18000e4ca  mov     rbx, rcx
0x18000e4cd  add     rcx, 88h; lpCriticalSection
0x18000e4d4  call    cs:__imp_DeleteCriticalSection
0x18000e4da  lea     rcx, [rbx+40h]; this
0x18000e4de  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x18000e4e3  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000e4e7  cmp     byte ptr [rcx+28h], 0
0x18000e4eb  jz      short loc_18000E4F7
0x18000e4ed  mov     byte ptr [rcx+28h], 0
0x18000e4f1  call    cs:__imp_DeleteCriticalSection
0x18000e4f7  add     rsp, 20h
0x18000e4fb  pop     rbx
0x18000e4fc  retn
```

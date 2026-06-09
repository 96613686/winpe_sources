# NtpPeer::~NtpPeer(void)

- ea: `0x1800147d8`
- end: `0x180014841`
- name: `??1NtpPeer@@QEAA@XZ`
- size: `105`
- prototype: `void __fastcall(NtpPeer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800147ac`

## callees

- `0x1800147d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800147ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014825`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014833`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800147ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014825`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014833`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014811`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014811`

## pseudocode

```c
void __fastcall NtpPeer::~NtpPeer(NtpPeer *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  v2 = (void *)*((_QWORD *)this + 9);
  if ( v2 )
    LocalFree(v2);
  v3 = (void *)*((_QWORD *)this + 11);
  if ( v3 )
    LocalFree(v3);
  v4 = (void *)*((_QWORD *)this + 12);
  if ( v4 )
    LocalFree(v4);
  if ( *(_BYTE *)this )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800147d8  push    rbx
0x1800147da  sub     rsp, 20h
0x1800147de  mov     rbx, rcx
0x1800147e1  mov     rcx, [rcx+48h]; hMem
0x1800147e5  test    rcx, rcx
0x1800147e8  jz      short loc_1800147F6
0x1800147ea  call    cs:__imp_LocalFree
0x1800147f1  nop     dword ptr [rax+rax+00h]
0x1800147f6  mov     rcx, [rbx+58h]; hMem
0x1800147fa  test    rcx, rcx
0x1800147fd  jnz     short loc_180014833
0x1800147ff  mov     rcx, [rbx+60h]; hMem
0x180014803  test    rcx, rcx
0x180014806  jnz     short loc_180014825
0x180014808  cmp     byte ptr [rbx], 0
0x18001480b  jz      short loc_18001481E
0x18001480d  lea     rcx, [rbx+8]; lpCriticalSection
0x180014811  call    cs:__imp_DeleteCriticalSection
0x180014818  nop     dword ptr [rax+rax+00h]
0x18001481d  nop
0x18001481e  add     rsp, 20h
0x180014822  pop     rbx
0x180014823  retn
0x180014825  call    cs:__imp_LocalFree
0x18001482c  nop     dword ptr [rax+rax+00h]
0x180014831  jmp     short loc_180014808
0x180014833  call    cs:__imp_LocalFree
0x18001483a  nop     dword ptr [rax+rax+00h]
0x18001483f  jmp     short loc_1800147FF
```

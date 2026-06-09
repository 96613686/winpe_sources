# CWdsTransportTftpClient::~CWdsTransportTftpClient(void)

- ea: `0x180005f90`
- end: `0x180005fb7`
- name: `??1CWdsTransportTftpClient@@QEAA@XZ`
- size: `39`
- prototype: `void __fastcall(CWdsTransportTftpClient *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005f38`
- `0x180010c0c`
- `0x180010c60`
- `0x180010cc4`
- `0x180014830`
- `0x1800154a4`
- `0x180016248`
- `0x180018380`
- `0x180018d28`

## callees

- `0x180002bc4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180005f9d`
- `KERNEL32!DeleteCriticalSection` at `0x180005f9d`

## pseudocode

```c
void __fastcall CWdsTransportTftpClient::~CWdsTransportTftpClient(CWdsTransportTftpClient *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CWdsTransportTftpClient *)((char *)this + 16));
}

```

## disassembly

```asm
0x180005f90  push    rbx
0x180005f92  sub     rsp, 20h
0x180005f96  mov     rbx, rcx
0x180005f99  add     rcx, 40h ; '@'; lpCriticalSection
0x180005f9d  call    cs:__imp_DeleteCriticalSection
0x180005fa4  nop     dword ptr [rax+rax+00h]
0x180005fa9  lea     rcx, [rbx+10h]; this
0x180005fad  add     rsp, 20h
0x180005fb1  pop     rbx
0x180005fb2  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```

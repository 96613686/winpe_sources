# CWcnUProxySession::~CWcnUProxySession(void)

- ea: `0x180043534`
- end: `0x18004358e`
- name: `??1CWcnUProxySession@@UEAA@XZ`
- size: `90`
- prototype: `void __fastcall(CWcnUProxySession *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800435b0`

## callees

- `0x18000a5ac`
- `0x180043534`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004356a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004356a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043557`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043557`

## pseudocode

```c
void __fastcall CWcnUProxySession::~CWcnUProxySession(CWcnUProxySession *this)
{
  __int64 i; // rdi
  void *v3; // rcx

  *(_QWORD *)this = &CWcnUProxySession::`vftable';
  for ( i = 0; i != 2; ++i )
  {
    v3 = (void *)*((_QWORD *)this + i + 3);
    if ( v3 )
      CloseHandle(v3);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  CSbSafeBuffer::~CSbSafeBuffer((CWcnUProxySession *)((char *)this + 40));
  *(_QWORD *)this = &IWcnLowLevelTransport::`vftable';
}

```

## disassembly

```asm
0x180043534  mov     [rsp+arg_0], rbx
0x180043539  push    rdi
0x18004353a  sub     rsp, 20h
0x18004353e  lea     rax, ??_7CWcnUProxySession@@6B@; const CWcnUProxySession::`vftable'
0x180043545  mov     rbx, rcx
0x180043548  mov     [rcx], rax
0x18004354b  xor     edi, edi
0x18004354d  mov     rcx, [rbx+rdi*8+18h]; hObject
0x180043552  test    rcx, rcx
0x180043555  jz      short loc_18004355D
0x180043557  call    cs:__imp_CloseHandle
0x18004355d  inc     rdi
0x180043560  cmp     rdi, 2
0x180043564  jnz     short loc_18004354D
0x180043566  lea     rcx, [rbx+58h]; lpCriticalSection
0x18004356a  call    cs:__imp_DeleteCriticalSection
0x180043570  lea     rcx, [rbx+28h]; this
0x180043574  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180043579  lea     rax, ??_7IWcnLowLevelTransport@@6B@; const IWcnLowLevelTransport::`vftable'
0x180043580  mov     [rbx], rax
0x180043583  mov     rbx, [rsp+28h+arg_0]
0x180043588  add     rsp, 20h
0x18004358c  pop     rdi
0x18004358d  retn
```

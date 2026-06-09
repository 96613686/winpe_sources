# CNetDiagHelperEx::~CNetDiagHelperEx(void)

- ea: `0x180002e38`
- end: `0x180002eb0`
- name: `??1CNetDiagHelperEx@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(CNetDiagHelperEx *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002f7c`

## callees

- `0x180002e38`
- `0x180004ac4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002e98`
- `KERNEL32!DeleteCriticalSection` at `0x180002e98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002e6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002e6f`

## pseudocode

```c
void __fastcall CNetDiagHelperEx::~CNetDiagHelperEx(CNetDiagHelperEx *this)
{
  __int64 i; // rdi

  if ( *((_QWORD *)this + 4) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 6); i = (unsigned int)(i + 1) )
      _attribute_t::FreeAll((LPVOID *)(*((_QWORD *)this + 4) + 144 * i));
  }
  CoTaskMemFree(*((LPVOID *)this + 4));
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 6) = 0;
  if ( *((_BYTE *)this + 112) )
  {
    *((_BYTE *)this + 112) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  }
}

```

## disassembly

```asm
0x180002e38  mov     [rsp+arg_0], rbx
0x180002e3d  push    rdi
0x180002e3e  sub     rsp, 20h
0x180002e42  cmp     qword ptr [rcx+20h], 0
0x180002e47  mov     rbx, rcx
0x180002e4a  jz      short loc_180002E6B
0x180002e4c  xor     edi, edi
0x180002e4e  cmp     [rcx+18h], edi
0x180002e51  jbe     short loc_180002E6B
0x180002e53  lea     rcx, [rdi+rdi*8]
0x180002e57  shl     rcx, 4
0x180002e5b  add     rcx, [rbx+20h]; this
0x180002e5f  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180002e64  inc     edi
0x180002e66  cmp     edi, [rbx+18h]
0x180002e69  jb      short loc_180002E53
0x180002e6b  mov     rcx, [rbx+20h]; pv
0x180002e6f  call    cs:__imp_CoTaskMemFree
0x180002e76  nop     dword ptr [rax+rax+00h]
0x180002e7b  lea     rcx, [rbx+48h]; lpCriticalSection
0x180002e7f  mov     qword ptr [rbx+20h], 0
0x180002e87  mov     dword ptr [rbx+18h], 0
0x180002e8e  cmp     byte ptr [rcx+28h], 0
0x180002e92  jz      short loc_180002EA4
0x180002e94  mov     byte ptr [rcx+28h], 0
0x180002e98  call    cs:__imp_DeleteCriticalSection
0x180002e9f  nop     dword ptr [rax+rax+00h]
0x180002ea4  mov     rbx, [rsp+28h+arg_0]
0x180002ea9  add     rsp, 20h
0x180002ead  pop     rdi
0x180002eae  retn
```

# _DbgpTraceTimerCallback(void *,uchar)

- ea: `0x18000fdf0`
- end: `0x18000fe79`
- name: `?_DbgpTraceTimerCallback@@YAXPEAXE@Z`
- size: `137`
- prototype: `void __fastcall(struct _DBG_TRACE_CONTROL_BLOCK *, unsigned __int8)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000fdf0`
- `0x1800355cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fe44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fe44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe5a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fe2c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fe2c`
- `ntdll!NtQuerySystemTime` at `0x18000fe63`
- `ntdll!NtQuerySystemTime` at `0x18000fe63`

## pseudocode

```c
void __fastcall _DbgpTraceTimerCallback(struct _DBG_TRACE_CONTROL_BLOCK *a1)
{
  union _LARGE_INTEGER *v1; // rsi
  struct _RTL_CRITICAL_SECTION *v3; // rbx

  v1 = (union _LARGE_INTEGER *)((char *)a1 + 24);
  if ( *((_DWORD *)a1 + 7) )
  {
    if ( *((_DWORD *)a1 + 7) != -1 )
      return;
    v3 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 192);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 192));
    _DbgpControlTracing(a1, v1->LowPart, 0);
    LeaveCriticalSection(v3);
  }
  else
  {
    RegSetValueExW(*((HKEY *)a1 + 21), *((LPCWSTR *)a1 + 23), 0, 4u, (const BYTE *)v1, 4u);
  }
  NtQuerySystemTime(v1);
}

```

## disassembly

```asm
0x18000fdf0  mov     rax, rsp
0x18000fdf3  mov     [rax+8], rbx
0x18000fdf7  mov     [rax+10h], rsi
0x18000fdfb  push    rdi
0x18000fdfc  sub     rsp, 30h
0x18000fe00  lea     rsi, [rcx+18h]
0x18000fe04  mov     rdi, rcx
0x18000fe07  cmp     dword ptr [rsi+4], 0
0x18000fe0b  jnz     short loc_18000FE34
0x18000fe0d  mov     rdx, [rcx+0B8h]; lpValueName
0x18000fe14  mov     r9d, 4; dwType
0x18000fe1a  mov     rcx, [rcx+0A8h]; hKey
0x18000fe21  xor     r8d, r8d; Reserved
0x18000fe24  mov     [rax-10h], r9d
0x18000fe28  mov     [rax-18h], rsi
0x18000fe2c  call    cs:__imp_RegSetValueExW
0x18000fe32  jmp     short loc_18000FE60
0x18000fe34  cmp     dword ptr [rsi+4], 0FFFFFFFFh
0x18000fe38  jnz     short loc_18000FE69
0x18000fe3a  lea     rbx, [rcx+0C0h]
0x18000fe41  mov     rcx, rbx; lpCriticalSection
0x18000fe44  call    cs:__imp_EnterCriticalSection
0x18000fe4a  mov     edx, [rsi]; unsigned int
0x18000fe4c  xor     r8d, r8d; int
0x18000fe4f  mov     rcx, rdi; struct _DBG_TRACE_CONTROL_BLOCK *
0x18000fe52  call    ?_DbgpControlTracing@@YAKPEAU_DBG_TRACE_CONTROL_BLOCK@@KH@Z; _DbgpControlTracing(_DBG_TRACE_CONTROL_BLOCK *,ulong,int)
0x18000fe57  mov     rcx, rbx; lpCriticalSection
0x18000fe5a  call    cs:__imp_LeaveCriticalSection
0x18000fe60  mov     rcx, rsi; SystemTime
0x18000fe63  call    cs:__imp_NtQuerySystemTime
0x18000fe69  mov     rbx, [rsp+38h+arg_0]
0x18000fe6e  mov     rsi, [rsp+38h+arg_8]
0x18000fe73  add     rsp, 30h
0x18000fe77  pop     rdi
0x18000fe78  retn
```

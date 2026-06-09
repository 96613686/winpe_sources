# _DbgpControlTracingThroughRegistry(_DBG_TRACE_CONTROL_BLOCK *,int)

- ea: `0x180035c7c`
- end: `0x180035d2f`
- name: `?_DbgpControlTracingThroughRegistry@@YAKPEAU_DBG_TRACE_CONTROL_BLOCK@@H@Z`
- size: `179`
- prototype: `unsigned int __fastcall(struct _DBG_TRACE_CONTROL_BLOCK *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180036570`

## callees

- `0x1800355cc`
- `0x180035c7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035cf9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035cf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035d13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035d13`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035ccc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035ccc`

## pseudocode

```c
__int64 __fastcall _DbgpControlTracingThroughRegistry(struct _DBG_TRACE_CONTROL_BLOCK *a1, int a2)
{
  const WCHAR *v3; // rdx
  HKEY v5; // rcx
  LSTATUS v6; // eax
  unsigned int v7; // edi
  DWORD v9; // [rsp+50h] [rbp+8h] BYREF
  DWORD v10; // [rsp+60h] [rbp+18h] BYREF
  unsigned int v11; // [rsp+68h] [rbp+20h] BYREF

  v10 = 0;
  v11 = 0;
  v3 = (const WCHAR *)*((_QWORD *)a1 + 23);
  v5 = (HKEY)*((_QWORD *)a1 + 21);
  v9 = 4;
  v6 = RegQueryValueExW(v5, v3, 0, &v10, (LPBYTE)&v11, &v9);
  v7 = v6;
  if ( v6 == 2 )
  {
    return 0;
  }
  else if ( !v6 )
  {
    if ( v9 >= 4 && v10 == 4 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 192));
      v7 = _DbgpControlTracing(a1, v11, a2);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 192));
    }
    else
    {
      return 1169;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180035c7c  mov     r11, rsp
0x180035c7f  mov     [r11+10h], rbx
0x180035c83  push    rbp
0x180035c84  push    rsi
0x180035c85  push    rdi
0x180035c86  sub     rsp, 30h
0x180035c8a  lea     rax, [r11+8]
0x180035c8e  mov     [rsp+48h+arg_10], 0
0x180035c96  mov     [r11-20h], rax
0x180035c9a  lea     r9, [r11+18h]; lpType
0x180035c9e  mov     ebp, edx
0x180035ca0  mov     [rsp+48h+arg_18], 0
0x180035ca8  mov     rdx, [rcx+0B8h]; lpValueName
0x180035caf  lea     rax, [r11+20h]
0x180035cb3  mov     rsi, rcx
0x180035cb6  mov     [r11-28h], rax
0x180035cba  mov     rcx, [rcx+0A8h]; hKey
0x180035cc1  xor     r8d, r8d; lpReserved
0x180035cc4  mov     [rsp+48h+arg_0], 4
0x180035ccc  call    cs:__imp_RegQueryValueExW
0x180035cd2  mov     edi, eax
0x180035cd4  cmp     eax, 2
0x180035cd7  jnz     short loc_180035CDD
0x180035cd9  xor     edi, edi
0x180035cdb  jmp     short loc_180035D20
0x180035cdd  test    eax, eax
0x180035cdf  jnz     short loc_180035D20
0x180035ce1  cmp     [rsp+48h+arg_0], 4
0x180035ce6  jb      short loc_180035D1B
0x180035ce8  cmp     [rsp+48h+arg_10], 4
0x180035ced  jnz     short loc_180035D1B
0x180035cef  lea     rbx, [rsi+0C0h]
0x180035cf6  mov     rcx, rbx; lpCriticalSection
0x180035cf9  call    cs:__imp_EnterCriticalSection
0x180035cff  mov     edx, [rsp+48h+arg_18]; unsigned int
0x180035d03  mov     r8d, ebp; int
0x180035d06  mov     rcx, rsi; struct _DBG_TRACE_CONTROL_BLOCK *
0x180035d09  call    ?_DbgpControlTracing@@YAKPEAU_DBG_TRACE_CONTROL_BLOCK@@KH@Z; _DbgpControlTracing(_DBG_TRACE_CONTROL_BLOCK *,ulong,int)
0x180035d0e  mov     rcx, rbx; lpCriticalSection
0x180035d11  mov     edi, eax
0x180035d13  call    cs:__imp_LeaveCriticalSection
0x180035d19  jmp     short loc_180035D20
0x180035d1b  mov     edi, 491h
0x180035d20  mov     rbx, [rsp+48h+arg_8]
0x180035d25  mov     eax, edi
0x180035d27  add     rsp, 30h
0x180035d2b  pop     rdi
0x180035d2c  pop     rsi
0x180035d2d  pop     rbp
0x180035d2e  retn
```

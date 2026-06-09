# CRegKeyDPA::Add(HKEY__ *,ushort const *)

- ea: `0x180002570`
- end: `0x18000260e`
- name: `?Add@CRegKeyDPA@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `158`
- prototype: `int(CRegKeyDPA *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002b10`

## callees

- `0x180002570`

## import_xrefs

- `iertutil!__imp_DPA_CreateEx` at `0x180002593`
- `iertutil!__imp_DPA_CreateEx` at `0x180002593`
- `iertutil!__imp_DPA_InsertPtr` at `0x1800025e1`
- `iertutil!__imp_DPA_InsertPtr` at `0x1800025e1`
- `ADVAPI32!RegCloseKey` at `0x1800025f1`
- `ADVAPI32!RegCloseKey` at `0x1800025f1`
- `ADVAPI32!RegOpenKeyExW` at `0x1800025c3`
- `ADVAPI32!RegOpenKeyExW` at `0x1800025c3`

## pseudocode

```c
__int64 __fastcall CRegKeyDPA::Add(HDPA *this, HKEY a2, const unsigned __int16 *a3)
{
  HDPA v6; // rax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  if ( !*this )
  {
    v6 = DPA_CreateEx(5, 0);
    *this = v6;
    if ( !v6 )
      return 2147500037LL;
  }
  hKey = 0;
  if ( RegOpenKeyExW(a2, a3, 0, 9u, &hKey) )
    return 2147500037LL;
  if ( DPA_InsertPtr(*this, 0x7FFFFFFF, hKey) == -1 )
  {
    RegCloseKey(hKey);
    return 2147500037LL;
  }
  ++*((_DWORD *)this + 2);
  return 0;
}

```

## disassembly

```asm
0x180002570  mov     [rsp+arg_8], rbx
0x180002575  mov     [rsp+arg_10], rsi
0x18000257a  push    rdi
0x18000257b  sub     rsp, 30h
0x18000257f  cmp     qword ptr [rcx], 0
0x180002583  mov     rdi, r8
0x180002586  mov     rsi, rdx
0x180002589  mov     rbx, rcx
0x18000258c  jnz     short loc_1800025A1
0x18000258e  xor     edx, edx; hheap
0x180002590  lea     ecx, [rdx+5]; cpGrow
0x180002593  call    cs:__imp_DPA_CreateEx
0x180002599  mov     [rbx], rax
0x18000259c  test    rax, rax
0x18000259f  jz      short loc_1800025CD
0x1800025a1  lea     rax, [rsp+38h+hKey]
0x1800025a6  mov     [rsp+38h+hKey], 0
0x1800025af  mov     r9d, 9; samDesired
0x1800025b5  mov     [rsp+38h+phkResult], rax; phkResult
0x1800025ba  xor     r8d, r8d; ulOptions
0x1800025bd  mov     rdx, rdi; lpSubKey
0x1800025c0  mov     rcx, rsi; hKey
0x1800025c3  call    cs:__imp_RegOpenKeyExW
0x1800025c9  test    eax, eax
0x1800025cb  jz      short loc_1800025D4
0x1800025cd  mov     eax, 80004005h
0x1800025d2  jmp     short loc_1800025FE
0x1800025d4  mov     r8, [rsp+38h+hKey]; p
0x1800025d9  mov     edx, 7FFFFFFFh; i
0x1800025de  mov     rcx, [rbx]; hdpa
0x1800025e1  call    cs:__imp_DPA_InsertPtr
0x1800025e7  cmp     eax, 0FFFFFFFFh
0x1800025ea  jnz     short loc_1800025F9
0x1800025ec  mov     rcx, [rsp+38h+hKey]; hKey
0x1800025f1  call    cs:__imp_RegCloseKey
0x1800025f7  jmp     short loc_1800025CD
0x1800025f9  inc     dword ptr [rbx+8]
0x1800025fc  xor     eax, eax
0x1800025fe  mov     rbx, [rsp+38h+arg_8]
0x180002603  mov     rsi, [rsp+38h+arg_10]
0x180002608  add     rsp, 30h
0x18000260c  pop     rdi
0x18000260d  retn
```

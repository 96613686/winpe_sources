# AppendSessionIDToKey(ushort const *,uint,ushort *)

- ea: `0x14000d604`
- end: `0x14000d66f`
- name: `?AppendSessionIDToKey@@YAJPEBGIPEAG@Z`
- size: `107`
- prototype: `int(const unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000dd50`
- `0x14000dea0`

## callees

- `0x1400088cc`
- `0x14000d604`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14000d622`
- `KERNEL32!GetCurrentProcessId` at `0x14000d622`
- `KERNEL32!ProcessIdToSessionId` at `0x14000d635`
- `KERNEL32!ProcessIdToSessionId` at `0x14000d635`

## pseudocode

```c
__int64 __fastcall AppendSessionIDToKey(const unsigned __int16 *a1, unsigned int a2, unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  DWORD CurrentProcessId; // eax
  DWORD v9; // [rsp+20h] [rbp-38h]
  DWORD pSessionId; // [rsp+78h] [rbp+20h] BYREF

  pSessionId = 0;
  v6 = -2147467259;
  CurrentProcessId = GetCurrentProcessId();
  if ( ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
  {
    v9 = pSessionId;
    return (unsigned int)StringCchPrintfW(a3, a2, L"%s%d", a1, v9);
  }
  return v6;
}

```

## disassembly

```asm
0x14000d604  push    rbx
0x14000d606  push    rbp
0x14000d607  push    rsi
0x14000d608  push    rdi
0x14000d609  sub     rsp, 38h
0x14000d60d  mov     rdi, r8
0x14000d610  mov     esi, edx
0x14000d612  mov     rbp, rcx
0x14000d615  mov     [rsp+58h+pSessionId], 0
0x14000d61d  mov     ebx, 80004005h
0x14000d622  call    cs:__imp_GetCurrentProcessId
0x14000d629  nop     dword ptr [rax+rax+00h]
0x14000d62e  mov     ecx, eax; dwProcessId
0x14000d630  lea     rdx, [rsp+58h+pSessionId]; pSessionId
0x14000d635  call    cs:__imp_ProcessIdToSessionId
0x14000d63c  nop     dword ptr [rax+rax+00h]
0x14000d641  test    eax, eax
0x14000d643  jz      short loc_14000D663
0x14000d645  mov     eax, [rsp+58h+pSessionId]
0x14000d649  lea     r8, aSD; "%s%d"
0x14000d650  mov     edx, esi; unsigned __int64
0x14000d652  mov     [rsp+58h+var_38], eax
0x14000d656  mov     r9, rbp
0x14000d659  mov     rcx, rdi; unsigned __int16 *
0x14000d65c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000d661  mov     ebx, eax
0x14000d663  mov     eax, ebx
0x14000d665  add     rsp, 38h
0x14000d669  pop     rdi
0x14000d66a  pop     rsi
0x14000d66b  pop     rbp
0x14000d66c  pop     rbx
0x14000d66d  retn
```

# NetpEventlogClose

- ea: `0x18001c0ac`
- end: `0x18001c119`
- name: `NetpEventlogClose`
- size: `109`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180017b70`
- `0x18001b810`

## callees

- `0x18001c0ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c0ff`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c0ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c0b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c0b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c0f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c0f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c0e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c0e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c112`

## pseudocode

```c
HLOCAL __fastcall NetpEventlogClose(LPCRITICAL_SECTION lpCriticalSection)
{
  LPCRITICAL_SECTION v2; // rdi
  _QWORD *p_Type; // rcx
  __int64 v4; // rax
  _QWORD *v5; // rdx

  EnterCriticalSection(lpCriticalSection);
  v2 = lpCriticalSection + 1;
  while ( 1 )
  {
    p_Type = &v2->DebugInfo->Type;
    if ( (LPCRITICAL_SECTION)v2->DebugInfo == v2 )
      break;
    v4 = *p_Type;
    if ( *(_QWORD **)(*p_Type + 8LL) != p_Type || (v5 = (_QWORD *)p_Type[1], (_QWORD *)*v5 != p_Type) )
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    LocalFree(p_Type);
  }
  LeaveCriticalSection(lpCriticalSection);
  DeleteCriticalSection(lpCriticalSection);
  return LocalFree(lpCriticalSection);
}

```

## disassembly

```asm
0x18001c0ac  mov     [rsp+arg_0], rbx
0x18001c0b1  push    rdi
0x18001c0b2  sub     rsp, 20h
0x18001c0b6  mov     rbx, rcx
0x18001c0b9  call    cs:__imp_EnterCriticalSection
0x18001c0bf  lea     rdi, [rbx+28h]
0x18001c0c3  mov     rcx, [rdi]; hMem
0x18001c0c6  cmp     rcx, rdi
0x18001c0c9  jz      short loc_18001C0F3
0x18001c0cb  mov     rax, [rcx]
0x18001c0ce  cmp     [rax+8], rcx
0x18001c0d2  jnz     short loc_18001C0EC
0x18001c0d4  mov     rdx, [rcx+8]
0x18001c0d8  cmp     [rdx], rcx
0x18001c0db  jnz     short loc_18001C0EC
0x18001c0dd  mov     [rdx], rax
0x18001c0e0  mov     [rax+8], rdx
0x18001c0e4  call    cs:__imp_LocalFree
0x18001c0ea  jmp     short loc_18001C0C3
0x18001c0ec  mov     ecx, 3
0x18001c0f1  int     29h; Win8: RtlFailFast(ecx)
0x18001c0f3  mov     rcx, rbx; lpCriticalSection
0x18001c0f6  call    cs:__imp_LeaveCriticalSection
0x18001c0fc  mov     rcx, rbx; lpCriticalSection
0x18001c0ff  call    cs:__imp_DeleteCriticalSection
0x18001c105  mov     rcx, rbx
0x18001c108  mov     rbx, [rsp+28h+arg_0]
0x18001c10d  add     rsp, 20h
0x18001c111  pop     rdi
0x18001c112  jmp     cs:__imp_LocalFree
```

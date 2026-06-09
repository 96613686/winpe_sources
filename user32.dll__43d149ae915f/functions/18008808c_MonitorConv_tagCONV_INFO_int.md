# MonitorConv(tagCONV_INFO *,int)

- ea: `0x18008808c`
- end: `0x1800881a9`
- name: `?MonitorConv@@YAXPEAUtagCONV_INFO@@H@Z`
- size: `285`
- prototype: `void __fastcall(struct tagCONV_INFO *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180045fc0`
- `0x18005e2b4`
- `0x180076dd0`

## callees

- `0x1800481f4`
- `0x180048320`
- `0x18008808c`

## import_xrefs

- `win32u!NtUserEvent` at `0x180088169`
- `win32u!NtUserEvent` at `0x180088169`
- `ntdll!RtlEnterCriticalSection` at `0x180088193`
- `ntdll!RtlEnterCriticalSection` at `0x180088193`
- `ntdll!RtlLeaveCriticalSection` at `0x180088160`
- `ntdll!RtlLeaveCriticalSection` at `0x180088160`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800880a7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800880a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180088186`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180088186`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180088173`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008817d`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180088173`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008817d`

## pseudocode

```c
void __fastcall MonitorConv(struct tagCONV_INFO *a1, int a2)
{
  _WORD *v4; // rax
  HLOCAL v5; // rbx
  bool v6; // cf

  v4 = LocalAlloc(0x40u, 0x40u);
  v5 = v4;
  if ( v4 )
  {
    *(_DWORD *)v4 = 0x40000000;
    v4[2] = 1;
    v4[3] = 56;
    *((_DWORD *)v4 + 2) = 56;
    *((_DWORD *)v4 + 3) = a2;
    *((_DWORD *)v4 + 4) = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
    *((_QWORD *)v4 + 3) = *(int *)(*((_QWORD *)a1 + 1) + 76LL);
    *((_QWORD *)v4 + 4) = LocalToGlobalAtom(*((_WORD *)a1 + 16));
    *((_QWORD *)v5 + 5) = LocalToGlobalAtom(*((_WORD *)a1 + 17));
    v6 = (*((_WORD *)a1 + 28) & 0x10) != 0;
    *((_QWORD *)v5 + 6) = *(_QWORD *)((char *)a1 + (v6 ? 8 : 0) + 40);
    *((_QWORD *)v5 + 7) = *(_QWORD *)((char *)a1 + (-(__int64)v6 & 0xFFFFFFFFFFFFFFF8uLL) + 48);
    RtlLeaveCriticalSection(&gcsDDEML);
    NtUserEvent(v5);
    GlobalDeleteAtom(*((_WORD *)v5 + 16));
    GlobalDeleteAtom(*((_WORD *)v5 + 20));
    LocalFree(v5);
    RtlEnterCriticalSection(&gcsDDEML);
  }
  else
  {
    SetLastDDEMLError(*((struct tagCL_INSTANCE_INFO **)a1 + 1), 0x4008u);
  }
}

```

## disassembly

```asm
0x18008808c  mov     [rsp+arg_0], rbx
0x180088091  mov     [rsp+arg_8], rsi
0x180088096  push    rdi
0x180088097  sub     rsp, 20h
0x18008809b  mov     rdi, rcx
0x18008809e  mov     esi, edx
0x1800880a0  mov     ecx, 40h ; '@'; uFlags
0x1800880a5  mov     edx, ecx; uBytes
0x1800880a7  call    cs:__imp_LocalAlloc
0x1800880ad  mov     rbx, rax
0x1800880b0  test    rax, rax
0x1800880b3  jnz     short loc_1800880C8
0x1800880b5  mov     rcx, [rdi+8]; struct tagCL_INSTANCE_INFO *
0x1800880b9  mov     edx, 4008h; unsigned int
0x1800880be  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x1800880c3  jmp     loc_180088199
0x1800880c8  mov     dword ptr [rax], 40000000h
0x1800880ce  mov     word ptr [rax+4], 1
0x1800880d4  mov     eax, 38h ; '8'
0x1800880d9  mov     [rbx+6], ax
0x1800880dd  mov     [rbx+8], eax
0x1800880e0  mov     eax, 7FFE0320h
0x1800880e5  mov     [rbx+0Ch], esi
0x1800880e8  mov     rax, [rax]
0x1800880eb  mov     ecx, ds:7FFE0004h
0x1800880f2  imul    rcx, rax
0x1800880f6  shr     rcx, 18h
0x1800880fa  mov     [rbx+10h], ecx
0x1800880fd  mov     rax, [rdi+8]
0x180088101  movsxd  rcx, dword ptr [rax+4Ch]
0x180088105  mov     [rbx+18h], rcx
0x180088109  movzx   ecx, word ptr [rdi+20h]; unsigned __int16
0x18008810d  call    ?LocalToGlobalAtom@@YAGG@Z; LocalToGlobalAtom(ushort)
0x180088112  movzx   eax, ax
0x180088115  mov     [rbx+20h], rax
0x180088119  movzx   ecx, word ptr [rdi+22h]; unsigned __int16
0x18008811d  call    ?LocalToGlobalAtom@@YAGG@Z; LocalToGlobalAtom(ushort)
0x180088122  movzx   eax, ax
0x180088125  mov     [rbx+28h], rax
0x180088129  movzx   ecx, word ptr [rdi+38h]
0x18008812d  and     cx, 10h
0x180088131  movzx   eax, cx
0x180088134  neg     ax
0x180088137  sbb     rax, rax
0x18008813a  and     eax, 8
0x18008813d  neg     cx
0x180088140  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180088147  mov     rax, [rax+rdi+28h]
0x18008814c  mov     [rbx+30h], rax
0x180088150  sbb     rax, rax
0x180088153  and     rax, 0FFFFFFFFFFFFFFF8h
0x180088157  mov     rax, [rax+rdi+30h]
0x18008815c  mov     [rbx+38h], rax
0x180088160  call    cs:__imp_RtlLeaveCriticalSection
0x180088166  mov     rcx, rbx
0x180088169  call    cs:__imp_NtUserEvent
0x18008816f  movzx   ecx, word ptr [rbx+20h]; nAtom
0x180088173  call    cs:__imp_GlobalDeleteAtom
0x180088179  movzx   ecx, word ptr [rbx+28h]; nAtom
0x18008817d  call    cs:__imp_GlobalDeleteAtom
0x180088183  mov     rcx, rbx; hMem
0x180088186  call    cs:__imp_LocalFree
0x18008818c  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180088193  call    cs:__imp_RtlEnterCriticalSection
0x180088199  mov     rbx, [rsp+28h+arg_0]
0x18008819e  mov     rsi, [rsp+28h+arg_8]
0x1800881a3  add     rsp, 20h
0x1800881a7  pop     rdi
0x1800881a8  retn
```

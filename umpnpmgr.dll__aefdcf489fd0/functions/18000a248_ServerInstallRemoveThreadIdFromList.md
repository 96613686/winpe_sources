# ServerInstallRemoveThreadIdFromList

- ea: `0x18000a248`
- end: `0x18000a2f0`
- name: `ServerInstallRemoveThreadIdFromList`
- size: `168`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180009d70`

## callees

- `0x18000a210`
- `0x18000a248`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000a2a3`
- `ntdll!RtlFreeHeap` at `0x18000a2a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a2c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a2dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a2c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a2dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018cc8`

## pseudocode

```c
__int64 __fastcall ServerInstallRemoveThreadIdFromList(int a1)
{
  unsigned int v2; // ebx
  PVOID *i; // r8
  PVOID **v4; // rax
  PVOID **v5; // rdx

  v2 = 0;
  pSetupBeginSynchronizedAccess(&qword_1800239B0);
  for ( i = (PVOID *)ServerInstallThreadIdList; i != &ServerInstallThreadIdList; i = (PVOID *)*i )
  {
    v4 = (PVOID **)*i;
    if ( *((_DWORD *)i + 4) == a1 )
    {
      if ( v4[1] != i || (v5 = (PVOID **)i[1], *v5 != i) )
        __fastfail(3u);
      *v5 = (PVOID *)v4;
      v4[1] = (PVOID *)v5;
      v2 = 1;
      RtlFreeHeap(PnpHeapHandle, 0, i);
      pSetupBeginSynchronizedAccess(&qword_1800239B0);
      --ServerInstallThreadTotal;
      ReleaseMutex(qword_1800239B8);
      break;
    }
  }
  ReleaseMutex(qword_1800239B8);
  return v2;
}

```

## disassembly

```asm
0x18000a248  mov     [rsp+arg_0], rbx
0x18000a24d  push    rdi
0x18000a24e  sub     rsp, 20h
0x18000a252  mov     edi, ecx
0x18000a254  xor     ebx, ebx
0x18000a256  lea     rcx, qword_1800239B0; lpHandles
0x18000a25d  call    pSetupBeginSynchronizedAccess
0x18000a262  nop
0x18000a263  mov     r8, cs:ServerInstallThreadIdList; P
0x18000a26a  lea     rax, ServerInstallThreadIdList
0x18000a271  cmp     r8, rax
0x18000a274  jz      short loc_18000A2D6
0x18000a276  mov     rax, [r8]
0x18000a279  cmp     [r8+10h], edi
0x18000a27d  jnz     short loc_18000A2D1
0x18000a27f  cmp     [rax+8], r8
0x18000a283  jnz     short loc_18000A2CA
0x18000a285  mov     rdx, [r8+8]
0x18000a289  cmp     [rdx], r8
0x18000a28c  jnz     short loc_18000A2CA
0x18000a28e  mov     [rdx], rax
0x18000a291  mov     [rax+8], rdx
0x18000a295  mov     ebx, 1
0x18000a29a  xor     edx, edx; Flags
0x18000a29c  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x18000a2a3  call    cs:__imp_RtlFreeHeap
0x18000a2a9  lea     rcx, qword_1800239B0; lpHandles
0x18000a2b0  call    pSetupBeginSynchronizedAccess
0x18000a2b5  dec     cs:ServerInstallThreadTotal
0x18000a2bb  mov     rcx, cs:qword_1800239B8; hMutex
0x18000a2c2  call    cs:__imp_ReleaseMutex
0x18000a2c8  jmp     short loc_18000A2D6
0x18000a2ca  mov     ecx, 3
0x18000a2cf  int     29h; Win8: RtlFailFast(ecx)
0x18000a2d1  mov     r8, rax
0x18000a2d4  jmp     short loc_18000A26A
0x18000a2d6  mov     rcx, cs:qword_1800239B8; hMutex
0x18000a2dd  call    cs:__imp_ReleaseMutex
0x18000a2e3  mov     eax, ebx
0x18000a2e5  mov     rbx, [rsp+28h+arg_0]
0x18000a2ea  add     rsp, 20h
0x18000a2ee  pop     rdi
0x18000a2ef  retn
0x180018cb3  push    rbp
0x180018cb5  sub     rsp, 20h
0x180018cb9  mov     rbp, rdx
0x180018cbc  mov     rcx, cs:qword_1800239B8
0x180018cc3  add     rsp, 20h
0x180018cc7  pop     rbp
0x180018cc8  jmp     cs:__imp_ReleaseMutex
```

# MonitorLink(tagCL_INSTANCE_INFO *,int,int,ushort,ushort,ushort,ushort,int,HCONV__ *,HCONV__ *)

- ea: `0x1800881b0`
- end: `0x1800882e3`
- name: `?MonitorLink@@YAXPEAUtagCL_INSTANCE_INFO@@HHGGGGHPEAUHCONV__@@1@Z`
- size: `307`
- prototype: `void __usercall(struct tagCL_INSTANCE_INFO *@<rcx>, int@<edx>, int@<r8d>, unsigned __int16@<r9w>, unsigned __int16, unsigned __int16, unsigned __int16, int, HCONV, HCONV)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18005e380`
- `0x18008f390`
- `0x18008febc`
- `0x1800900d0`
- `0x180090768`

## callees

- `0x18003ac24`
- `0x1800481f4`
- `0x180048320`
- `0x1800881b0`

## import_xrefs

- `win32u!NtUserEvent` at `0x18008829f`
- `win32u!NtUserEvent` at `0x18008829f`
- `ntdll!RtlEnterCriticalSection` at `0x1800882d2`
- `ntdll!RtlEnterCriticalSection` at `0x1800882d2`
- `ntdll!RtlLeaveCriticalSection` at `0x180088296`
- `ntdll!RtlLeaveCriticalSection` at `0x180088296`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800881d0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800881d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800882c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800882c5`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800882a9`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800882b3`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800882bc`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800882a9`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800882b3`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800882bc`

## pseudocode

```c
void __fastcall MonitorLink(
        struct tagCL_INSTANCE_INFO *a1,
        int a2,
        int a3,
        unsigned __int16 a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        unsigned __int16 a7,
        int a8,
        HCONV a9,
        HCONV a10)
{
  _WORD *v14; // rax
  HLOCAL v15; // rdi

  v14 = LocalAlloc(0x40u, 0x50u);
  v15 = v14;
  if ( v14 )
  {
    *(_DWORD *)v14 = 0x20000000;
    v14[2] = 1;
    v14[3] = 72;
    *((_DWORD *)v14 + 2) = 72;
    *((_DWORD *)v14 + 3) = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
    *((_QWORD *)v14 + 2) = *((int *)a1 + 19);
    *((_DWORD *)v14 + 6) = a2;
    *((_DWORD *)v14 + 7) = a3;
    *((_QWORD *)v14 + 4) = LocalToGlobalAtom(a4);
    *((_QWORD *)v15 + 5) = LocalToGlobalAtom(a5);
    IncGlobalAtomCount(a6);
    *((_DWORD *)v15 + 14) = a7;
    *((_DWORD *)v15 + 15) = a8;
    *((_QWORD *)v15 + 8) = a9;
    *((_QWORD *)v15 + 9) = a10;
    *((_QWORD *)v15 + 6) = a6;
    RtlLeaveCriticalSection(&gcsDDEML);
    NtUserEvent(v15);
    GlobalDeleteAtom(*((_WORD *)v15 + 16));
    GlobalDeleteAtom(*((_WORD *)v15 + 20));
    GlobalDeleteAtom(a6);
    LocalFree(v15);
    RtlEnterCriticalSection(&gcsDDEML);
  }
  else
  {
    SetLastDDEMLError(a1, 0x4008u);
  }
}

```

## disassembly

```asm
0x1800881b0  push    rbx
0x1800881b2  push    rbp
0x1800881b3  push    rsi
0x1800881b4  push    rdi
0x1800881b5  push    r14
0x1800881b7  sub     rsp, 20h
0x1800881bb  mov     r14d, edx
0x1800881be  mov     rbx, rcx
0x1800881c1  mov     edx, 50h ; 'P'; uBytes
0x1800881c6  movzx   esi, r9w
0x1800881ca  mov     ebp, r8d
0x1800881cd  lea     ecx, [rdx-10h]; uFlags
0x1800881d0  call    cs:__imp_LocalAlloc
0x1800881d6  mov     rdi, rax
0x1800881d9  test    rax, rax
0x1800881dc  jnz     short loc_1800881F0
0x1800881de  mov     edx, 4008h; unsigned int
0x1800881e3  mov     rcx, rbx; struct tagCL_INSTANCE_INFO *
0x1800881e6  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x1800881eb  jmp     loc_1800882D8
0x1800881f0  mov     dword ptr [rax], 20000000h
0x1800881f6  mov     word ptr [rax+4], 1
0x1800881fc  mov     eax, 48h ; 'H'
0x180088201  mov     [rdi+6], ax
0x180088205  mov     [rdi+8], eax
0x180088208  mov     eax, 7FFE0320h
0x18008820d  mov     rax, [rax]
0x180088210  mov     ecx, ds:7FFE0004h
0x180088217  imul    rcx, rax
0x18008821b  shr     rcx, 18h
0x18008821f  mov     [rdi+0Ch], ecx
0x180088222  movzx   ecx, si; unsigned __int16
0x180088225  movsxd  rax, dword ptr [rbx+4Ch]
0x180088229  mov     [rdi+10h], rax
0x18008822d  mov     [rdi+18h], r14d
0x180088231  mov     [rdi+1Ch], ebp
0x180088234  call    ?LocalToGlobalAtom@@YAGG@Z; LocalToGlobalAtom(ushort)
0x180088239  movzx   ecx, [rsp+48h+arg_20]; unsigned __int16
0x18008823e  movzx   eax, ax
0x180088241  mov     [rdi+20h], rax
0x180088245  call    ?LocalToGlobalAtom@@YAGG@Z; LocalToGlobalAtom(ushort)
0x18008824a  movzx   ebx, [rsp+48h+arg_28]
0x18008824f  movzx   eax, ax
0x180088252  movzx   ecx, bx; unsigned __int16
0x180088255  mov     [rdi+28h], rax
0x180088259  call    ?IncGlobalAtomCount@@YAGG@Z; IncGlobalAtomCount(ushort)
0x18008825e  movzx   eax, [rsp+48h+arg_30]
0x180088266  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18008826d  mov     [rdi+38h], eax
0x180088270  mov     eax, [rsp+48h+arg_38]
0x180088277  mov     [rdi+3Ch], eax
0x18008827a  mov     rax, [rsp+48h+arg_40]
0x180088282  mov     [rdi+40h], rax
0x180088286  mov     rax, [rsp+48h+arg_48]
0x18008828e  mov     [rdi+48h], rax
0x180088292  mov     [rdi+30h], rbx
0x180088296  call    cs:__imp_RtlLeaveCriticalSection
0x18008829c  mov     rcx, rdi
0x18008829f  call    cs:__imp_NtUserEvent
0x1800882a5  movzx   ecx, word ptr [rdi+20h]; nAtom
0x1800882a9  call    cs:__imp_GlobalDeleteAtom
0x1800882af  movzx   ecx, word ptr [rdi+28h]; nAtom
0x1800882b3  call    cs:__imp_GlobalDeleteAtom
0x1800882b9  movzx   ecx, bx; nAtom
0x1800882bc  call    cs:__imp_GlobalDeleteAtom
0x1800882c2  mov     rcx, rdi; hMem
0x1800882c5  call    cs:__imp_LocalFree
0x1800882cb  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800882d2  call    cs:__imp_RtlEnterCriticalSection
0x1800882d8  add     rsp, 20h
0x1800882dc  pop     r14
0x1800882de  pop     rdi
0x1800882df  pop     rsi
0x1800882e0  pop     rbp
0x1800882e1  pop     rbx
0x1800882e2  retn
```

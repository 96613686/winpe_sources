# wdmDevInterfaceInstall(ushort const *,unsigned __int64,ulong)

- ea: `0x180002460`
- end: `0x180002550`
- name: `?wdmDevInterfaceInstall@@YAPEBGPEBG_KK@Z`
- size: `240`
- prototype: `const unsigned __int16 *__fastcall(const unsigned __int16 *, unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001660`
- `0x1800023f0`

## callees

- `0x180001eb0`
- `0x180002460`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000250e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000250e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800024ae`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800024ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000247d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000247d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024c7`

## pseudocode

```c
const unsigned __int16 *__fastcall wdmDevInterfaceInstall(const unsigned __int16 *a1, __int64 a2, int a3)
{
  unsigned __int16 *v6; // rbx
  __int64 v7; // rdi
  unsigned __int64 v9; // rdi
  unsigned __int16 *v10; // rax

  EnterCriticalSection(&NumDevsCritSec);
  v6 = (unsigned __int16 *)wdmDevZ;
  v7 = -1;
  while ( v6 )
  {
    if ( CompareStringW(0x7Fu, 1u, v6 + 16, -1, a1, -1) == 2 )
    {
      ++*((_DWORD *)v6 + 5);
      *((_QWORD *)v6 + 3) = a2;
      goto LABEL_5;
    }
    v6 = *(unsigned __int16 **)v6;
  }
  do
    ++v7;
  while ( a1[v7] );
  v9 = 2 * v7 + 2;
  v10 = (unsigned __int16 *)HeapAlloc(hHeap, 8u, v9 + 40);
  v6 = v10;
  if ( v10 )
  {
    *((_DWORD *)v10 + 2) = a3;
    *((_DWORD *)v10 + 5) = 1;
    *((_QWORD *)v10 + 3) = a2;
    StringCbCopyW(v10 + 16, v9, a1);
    *(_QWORD *)v6 = wdmDevZ;
    wdmDevZ = v6;
  }
LABEL_5:
  LeaveCriticalSection(&NumDevsCritSec);
  return (const unsigned __int16 *)((unsigned __int64)(v6 + 16) & -(__int64)(v6 != 0));
}

```

## disassembly

```asm
0x180002460  push    rbx
0x180002462  push    rbp
0x180002463  push    rsi
0x180002464  push    rdi
0x180002465  push    r12
0x180002467  push    r14
0x180002469  sub     rsp, 38h
0x18000246d  mov     rsi, rcx
0x180002470  mov     r14d, r8d
0x180002473  lea     rcx, NumDevsCritSec; lpCriticalSection
0x18000247a  mov     rbp, rdx
0x18000247d  call    cs:__imp_EnterCriticalSection
0x180002483  mov     rbx, qword ptr cs:?wdmDevZ@@3Utag_wdmdeviceinterface@@A; tag_wdmdeviceinterface wdmDevZ
0x18000248a  xor     r12d, r12d
0x18000248d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180002491  test    rbx, rbx
0x180002494  jz      short loc_1800024EC
0x180002496  mov     edx, 1; dwCmpFlags
0x18000249b  mov     [rsp+68h+cchCount2], edi; cchCount2
0x18000249f  lea     r8, [rbx+20h]; lpString1
0x1800024a3  mov     [rsp+68h+lpString2], rsi; lpString2
0x1800024a8  mov     r9d, edi; cchCount1
0x1800024ab  lea     ecx, [rdx+7Eh]; Locale
0x1800024ae  call    cs:__imp_CompareStringW
0x1800024b4  cmp     eax, 2
0x1800024b7  jnz     short loc_1800024E7
0x1800024b9  inc     dword ptr [rbx+14h]
0x1800024bc  mov     [rbx+18h], rbp
0x1800024c0  lea     rcx, NumDevsCritSec; lpCriticalSection
0x1800024c7  call    cs:__imp_LeaveCriticalSection
0x1800024cd  lea     rcx, [rbx+20h]
0x1800024d1  neg     rbx
0x1800024d4  sbb     rax, rax
0x1800024d7  and     rax, rcx
0x1800024da  add     rsp, 38h
0x1800024de  pop     r14
0x1800024e0  pop     r12
0x1800024e2  pop     rdi
0x1800024e3  pop     rsi
0x1800024e4  pop     rbp
0x1800024e5  pop     rbx
0x1800024e6  retn
0x1800024e7  mov     rbx, [rbx]
0x1800024ea  jmp     short loc_180002491
0x1800024ec  inc     rdi
0x1800024ef  cmp     [rsi+rdi*2], r12w
0x1800024f4  jnz     short loc_1800024EC
0x1800024f6  mov     rcx, cs:hHeap; hHeap
0x1800024fd  lea     rdi, ds:2[rdi*2]
0x180002505  lea     r8, [rdi+28h]; dwBytes
0x180002509  mov     edx, 8; dwFlags
0x18000250e  call    cs:__imp_HeapAlloc
0x180002514  mov     rbx, rax
0x180002517  test    rax, rax
0x18000251a  jz      short loc_1800024C0
0x18000251c  lea     rcx, [rax+20h]; unsigned __int16 *
0x180002520  mov     [rax+8], r14d
0x180002524  mov     r8, rsi; unsigned __int16 *
0x180002527  mov     dword ptr [rax+14h], 1
0x18000252e  mov     rdx, rdi; unsigned __int64
0x180002531  mov     [rax+18h], rbp
0x180002535  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000253a  mov     r10, qword ptr cs:?wdmDevZ@@3Utag_wdmdeviceinterface@@A; tag_wdmdeviceinterface wdmDevZ
0x180002541  mov     [rbx], r10
0x180002544  mov     qword ptr cs:?wdmDevZ@@3Utag_wdmdeviceinterface@@A, rbx; tag_wdmdeviceinterface wdmDevZ
0x18000254b  jmp     loc_1800024C0
```

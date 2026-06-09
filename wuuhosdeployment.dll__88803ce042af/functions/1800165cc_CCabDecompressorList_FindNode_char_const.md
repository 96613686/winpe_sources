# CCabDecompressorList::FindNode(char const *)

- ea: `0x1800165cc`
- end: `0x18001667b`
- name: `?FindNode@CCabDecompressorList@@SAPEAVCCabDecompressor@@PEBD@Z`
- size: `175`
- prototype: `struct CCabDecompressor *__fastcall(PCNZCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015670`

## callees

- `0x1800165cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016655`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016655`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800165f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800165f6`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180016632`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180016632`

## pseudocode

```c
struct CCabDecompressor *__fastcall CCabDecompressorList::FindNode(PCNZCH lpString1)
{
  __int64 v1; // rbx
  int v3; // esi
  unsigned int v4; // edi

  v1 = 0;
  v3 = 0;
  if ( CCabDecompressorList::m_fInited )
  {
    EnterCriticalSection(&CriticalSection);
    v4 = 0;
    if ( dword_180075684 )
    {
      while ( 1 )
      {
        v1 = *(_QWORD *)(qword_180075678 + 8LL * v4);
        if ( CompareStringA(0x7Fu, 1u, lpString1, -1, *(PCNZCH *)(v1 + 48), -1) == 2 )
          break;
        if ( ++v4 >= dword_180075684 )
          goto LABEL_7;
      }
      v3 = 1;
    }
LABEL_7:
    LeaveCriticalSection(&CriticalSection);
    return (struct CCabDecompressor *)(-(__int64)(v3 != 0) & v1);
  }
  return (struct CCabDecompressor *)v1;
}

```

## disassembly

```asm
0x1800165cc  mov     [rsp+arg_0], rbx
0x1800165d1  mov     [rsp+arg_8], rbp
0x1800165d6  mov     [rsp+arg_10], rsi
0x1800165db  push    rdi
0x1800165dc  sub     rsp, 30h
0x1800165e0  xor     ebx, ebx
0x1800165e2  mov     rbp, rcx
0x1800165e5  cmp     cs:?m_fInited@CCabDecompressorList@@0HA, ebx; int CCabDecompressorList::m_fInited
0x1800165eb  mov     esi, ebx
0x1800165ed  jz      short loc_180016663
0x1800165ef  lea     rcx, CriticalSection; lpCriticalSection
0x1800165f6  call    cs:__imp_EnterCriticalSection
0x1800165fc  cmp     cs:dword_180075684, ebx
0x180016602  mov     edi, ebx
0x180016604  jbe     short loc_18001664E
0x180016606  mov     rax, cs:qword_180075678
0x18001660d  mov     ecx, edi
0x18001660f  mov     rbx, [rax+rcx*8]
0x180016613  mov     rax, [rbx+30h]
0x180016617  or      r9d, 0FFFFFFFFh; cchCount1
0x18001661b  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x180016623  mov     r8, rbp; lpString1
0x180016626  mov     [rsp+38h+lpString2], rax; lpString2
0x18001662b  lea     edx, [r9+2]; dwCmpFlags
0x18001662f  lea     ecx, [rdx+7Eh]; Locale
0x180016632  call    cs:__imp_CompareStringA
0x180016638  cmp     eax, 2
0x18001663b  jz      short loc_180016649
0x18001663d  inc     edi
0x18001663f  cmp     edi, cs:dword_180075684
0x180016645  jb      short loc_180016606
0x180016647  jmp     short loc_18001664E
0x180016649  mov     esi, 1
0x18001664e  lea     rcx, CriticalSection; lpCriticalSection
0x180016655  call    cs:__imp_LeaveCriticalSection
0x18001665b  neg     esi
0x18001665d  sbb     rax, rax
0x180016660  and     rbx, rax
0x180016663  mov     rbp, [rsp+38h+arg_8]
0x180016668  mov     rax, rbx
0x18001666b  mov     rbx, [rsp+38h+arg_0]
0x180016670  mov     rsi, [rsp+38h+arg_10]
0x180016675  add     rsp, 30h
0x180016679  pop     rdi
0x18001667a  retn
```

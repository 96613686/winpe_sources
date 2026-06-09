# FindOrAddService(ulong,ulong)

- ea: `0x14001d51c`
- end: `0x14001d5e0`
- name: `?FindOrAddService@@YAPEAU_SERVICE_RECORD@@KK@Z`
- size: `196`
- prototype: `struct _SERVICE_RECORD *__fastcall(int, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140003a30`
- `0x140006588`
- `0x1400069c8`
- `0x14000a0d4`
- `0x14000a3a4`

## callees

- `0x14001b8d8`
- `0x14001d51c`

## pseudocode

```c
struct _SERVICE_RECORD *__fastcall FindOrAddService(int a1, int a2)
{
  struct _PROCESS_RECORD *v3; // rdx
  struct _PROCESS_RECORD *v5; // rax
  struct _SERVICE_RECORD *result; // rax
  struct _PROCESS_RECORD **v7; // rcx
  struct _PROCESS_RECORD *v8; // rax
  char *v9; // rcx
  __int64 v10; // r8
  struct _SERVICE_RECORD **v11; // rdx
  __int64 v12; // rdx

  v3 = qword_140082130;
  if ( qword_140082130 == (struct _PROCESS_RECORD *)&qword_140082130 )
    return 0;
  while ( 1 )
  {
    v5 = *(struct _PROCESS_RECORD **)v3;
    if ( a2 == *((_DWORD *)v3 + 30) )
      break;
    v3 = *(struct _PROCESS_RECORD **)v3;
    if ( v5 == (struct _PROCESS_RECORD *)&qword_140082130 )
      return 0;
  }
  if ( *((struct _PROCESS_RECORD **)v5 + 1) != v3 )
    goto LABEL_16;
  v7 = (struct _PROCESS_RECORD **)*((_QWORD *)v3 + 1);
  if ( *v7 != v3 )
    goto LABEL_16;
  *v7 = v5;
  *((_QWORD *)v5 + 1) = v7;
  v8 = qword_140082130;
  if ( *((struct _PROCESS_RECORD ***)qword_140082130 + 1) != &qword_140082130 )
    goto LABEL_16;
  *(_QWORD *)v3 = qword_140082130;
  v9 = (char *)v3 + 32;
  *((_QWORD *)v3 + 1) = &qword_140082130;
  *((_QWORD *)v8 + 1) = v3;
  qword_140082130 = v3;
  result = (struct _SERVICE_RECORD *)*((_QWORD *)v3 + 4);
  if ( result == (struct _PROCESS_RECORD *)((char *)v3 + 32) )
    return AddService(a1, v3);
  while ( 1 )
  {
    v10 = *(_QWORD *)result;
    if ( a1 == *((_DWORD *)result + 8) )
      break;
    result = *(struct _SERVICE_RECORD **)result;
    if ( (char *)v10 == v9 )
      return AddService(a1, v3);
  }
  if ( *(struct _SERVICE_RECORD **)(v10 + 8) != result
    || (v11 = (struct _SERVICE_RECORD **)*((_QWORD *)result + 1), *v11 != result)
    || (*v11 = (struct _SERVICE_RECORD *)v10,
        *(_QWORD *)(v10 + 8) = v11,
        v12 = *(_QWORD *)v9,
        *(char **)(*(_QWORD *)v9 + 8LL) != v9) )
  {
LABEL_16:
    __fastfail(3u);
  }
  *(_QWORD *)result = v12;
  *((_QWORD *)result + 1) = v9;
  *(_QWORD *)(v12 + 8) = result;
  *(_QWORD *)v9 = result;
  return result;
}

```

## disassembly

```asm
0x14001d51c  mov     r8d, edx
0x14001d51f  lea     r10, qword_140082130
0x14001d526  mov     rdx, cs:qword_140082130; struct _PROCESS_RECORD *
0x14001d52d  mov     r9d, ecx
0x14001d530  cmp     rdx, r10
0x14001d533  jz      short loc_14001D546
0x14001d535  mov     rax, [rdx]
0x14001d538  cmp     r8d, [rdx+78h]
0x14001d53c  jz      short loc_14001D549
0x14001d53e  mov     rdx, rax
0x14001d541  cmp     rax, r10
0x14001d544  jnz     short loc_14001D535
0x14001d546  xor     eax, eax
0x14001d548  retn
0x14001d549  cmp     [rax+8], rdx
0x14001d54d  jnz     loc_14001D5D9
0x14001d553  mov     rcx, [rdx+8]
0x14001d557  cmp     [rcx], rdx
0x14001d55a  jnz     short loc_14001D5D9
0x14001d55c  mov     [rcx], rax
0x14001d55f  mov     [rax+8], rcx
0x14001d563  mov     rax, cs:qword_140082130
0x14001d56a  cmp     [rax+8], r10
0x14001d56e  jnz     short loc_14001D5D9
0x14001d570  mov     [rdx], rax
0x14001d573  lea     rcx, [rdx+20h]
0x14001d577  mov     [rdx+8], r10
0x14001d57b  mov     [rax+8], rdx
0x14001d57f  mov     cs:qword_140082130, rdx
0x14001d586  mov     rax, [rcx]
0x14001d589  cmp     rax, rcx
0x14001d58c  jz      short loc_14001D59F
0x14001d58e  mov     r8, [rax]
0x14001d591  cmp     r9d, [rax+20h]
0x14001d595  jz      short loc_14001D5A7
0x14001d597  mov     rax, r8
0x14001d59a  cmp     r8, rcx
0x14001d59d  jnz     short loc_14001D58E
0x14001d59f  mov     ecx, r9d; unsigned int
0x14001d5a2  jmp     ?AddService@@YAPEAU_SERVICE_RECORD@@KPEAU_PROCESS_RECORD@@@Z; AddService(ulong,_PROCESS_RECORD *)
0x14001d5a7  cmp     [r8+8], rax
0x14001d5ab  jnz     short loc_14001D5D9
0x14001d5ad  mov     rdx, [rax+8]
0x14001d5b1  cmp     [rdx], rax
0x14001d5b4  jnz     short loc_14001D5D9
0x14001d5b6  mov     [rdx], r8
0x14001d5b9  mov     [r8+8], rdx
0x14001d5bd  mov     rdx, [rcx]
0x14001d5c0  cmp     [rdx+8], rcx
0x14001d5c4  jnz     short loc_14001D5D9
0x14001d5c6  mov     [rax], rdx
0x14001d5c9  mov     [rax+8], rcx
0x14001d5cd  mov     [rdx+8], rax
0x14001d5d1  mov     [rcx], rax
0x14001d5d4  jmp     locret_14001D548
0x14001d5d9  mov     ecx, 3
0x14001d5de  int     29h; Win8: RtlFailFast(ecx)
```

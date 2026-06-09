# DeletePrintJobRecord(_PRINT_JOB_RECORD *,ulong)

- ea: `0x14001c5d4`
- end: `0x14001c855`
- name: `?DeletePrintJobRecord@@YAKPEAU_PRINT_JOB_RECORD@@K@Z`
- size: `641`
- prototype: `__int64 __fastcall(struct _PRINT_JOB_RECORD *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140007ec4`

## callees

- `0x14001c5d4`

## import_xrefs

- `msvcrt!fprintf` at `0x14001c624`
- `msvcrt!fprintf` at `0x14001c638`
- `msvcrt!fprintf` at `0x14001c64c`
- `msvcrt!fprintf` at `0x14001c660`
- `msvcrt!fprintf` at `0x14001c67b`
- `msvcrt!fprintf` at `0x14001c68f`
- `msvcrt!fprintf` at `0x14001c6a7`
- `msvcrt!fprintf` at `0x14001c6bb`
- `msvcrt!fprintf` at `0x14001c6cf`
- `msvcrt!fprintf` at `0x14001c6e3`
- `msvcrt!fprintf` at `0x14001c6f7`
- `msvcrt!fprintf` at `0x14001c70b`
- `msvcrt!fprintf` at `0x14001c71f`
- `msvcrt!fprintf` at `0x14001c73b`
- `msvcrt!fprintf` at `0x14001c74f`
- `msvcrt!fprintf` at `0x14001c764`
- `msvcrt!fprintf` at `0x14001c779`
- `msvcrt!fprintf` at `0x14001c78e`
- `msvcrt!fprintf` at `0x14001c7a3`
- `msvcrt!fprintf` at `0x14001c7b8`
- `msvcrt!fprintf` at `0x14001c7cd`
- `msvcrt!fprintf` at `0x14001c7e8`
- `msvcrt!fprintf` at `0x14001c624`
- `msvcrt!fprintf` at `0x14001c638`
- `msvcrt!fprintf` at `0x14001c64c`
- `msvcrt!fprintf` at `0x14001c660`
- `msvcrt!fprintf` at `0x14001c67b`
- `msvcrt!fprintf` at `0x14001c68f`
- `msvcrt!fprintf` at `0x14001c6a7`
- `msvcrt!fprintf` at `0x14001c6bb`
- `msvcrt!fprintf` at `0x14001c6cf`
- `msvcrt!fprintf` at `0x14001c6e3`
- `msvcrt!fprintf` at `0x14001c6f7`
- `msvcrt!fprintf` at `0x14001c70b`
- `msvcrt!fprintf` at `0x14001c71f`
- `msvcrt!fprintf` at `0x14001c73b`
- `msvcrt!fprintf` at `0x14001c74f`
- `msvcrt!fprintf` at `0x14001c764`
- `msvcrt!fprintf` at `0x14001c779`
- `msvcrt!fprintf` at `0x14001c78e`
- `msvcrt!fprintf` at `0x14001c7a3`
- `msvcrt!fprintf` at `0x14001c7b8`
- `msvcrt!fprintf` at `0x14001c7cd`
- `msvcrt!fprintf` at `0x14001c7e8`
- `ntdll!RtlEnterCriticalSection` at `0x14001c7f5`
- `ntdll!RtlEnterCriticalSection` at `0x14001c7f5`
- `ntdll!RtlLeaveCriticalSection` at `0x14001c841`
- `ntdll!RtlLeaveCriticalSection` at `0x14001c841`

## pseudocode

```c
__int64 __fastcall DeletePrintJobRecord(struct _PRINT_JOB_RECORD *a1, int a2)
{
  __int64 v4; // rax
  struct _PRINT_JOB_RECORD **v5; // rdx
  _QWORD *v6; // rax

  if ( !a1 )
    return 87;
  if ( Stream && a2 )
  {
    fprintf(Stream, "%d, ", *((_DWORD *)a1 + 4));
    fprintf(Stream, "%d, ", *((_DWORD *)a1 + 5));
    fprintf(Stream, "%d, ", *((_DWORD *)a1 + 6));
    fprintf(Stream, "%d, ", *((_DWORD *)a1 + 7));
    fprintf(Stream, "%I64u, ", *((_QWORD *)a1 + 8));
    fprintf(Stream, "%I64u, ", *((_QWORD *)a1 + 9));
    fprintf(Stream, "%I64u, ", *((_QWORD *)a1 + 10) - *((_QWORD *)a1 + 11));
    fprintf(Stream, "%I64u, ", *((_QWORD *)a1 + 13));
    fprintf(Stream, "%d, ", *((_DWORD *)a1 + 8));
    fprintf(Stream, "%d, ", *((_DWORD *)a1 + 9));
    fprintf(Stream, "%d, ", *((_DWORD *)a1 + 10));
    fprintf(Stream, "%d, ", *((_DWORD *)a1 + 11));
    fprintf(Stream, "%d, ", *((_DWORD *)a1 + 12));
    fprintf(Stream, "%hd, ", *((__int16 *)a1 + 56));
    fprintf(Stream, "%d, ", *((_DWORD *)a1 + 14));
    fprintf(Stream, "%hd, ", *((__int16 *)a1 + 57));
    fprintf(Stream, "%hd, ", *((__int16 *)a1 + 58));
    fprintf(Stream, "%hd, ", *((__int16 *)a1 + 59));
    fprintf(Stream, "%hd, ", *((__int16 *)a1 + 60));
    fprintf(Stream, "%hd, ", *((__int16 *)a1 + 61));
    fprintf(Stream, "%hd, ", *((__int16 *)a1 + 62));
    fprintf(Stream, "%d\n", *((_DWORD *)a1 + 32));
  }
  RtlEnterCriticalSection(&TLCritSect);
  v4 = *(_QWORD *)a1;
  if ( *(struct _PRINT_JOB_RECORD **)(*(_QWORD *)a1 + 8LL) != a1
    || (v5 = (struct _PRINT_JOB_RECORD **)*((_QWORD *)a1 + 1), *v5 != a1)
    || (*v5 = (struct _PRINT_JOB_RECORD *)v4,
        *(_QWORD *)(v4 + 8) = v5,
        v6 = qword_140082228,
        *((LPVOID **)qword_140082228 + 1) != &qword_140082228) )
  {
    __fastfail(3u);
  }
  *((_QWORD *)a1 + 1) = &qword_140082228;
  *(_QWORD *)a1 = v6;
  v6[1] = a1;
  qword_140082228 = a1;
  RtlLeaveCriticalSection(&TLCritSect);
  return 0;
}

```

## disassembly

```asm
0x14001c5d4  mov     [rsp+arg_0], rbx
0x14001c5d9  mov     [rsp+arg_8], rsi
0x14001c5de  push    rdi
0x14001c5df  sub     rsp, 20h
0x14001c5e3  mov     rbx, rcx
0x14001c5e6  test    rcx, rcx
0x14001c5e9  jnz     short loc_14001C5FE
0x14001c5eb  lea     eax, [rcx+57h]
0x14001c5ee  mov     rbx, [rsp+28h+arg_0]
0x14001c5f3  mov     rsi, [rsp+28h+arg_8]
0x14001c5f8  add     rsp, 20h
0x14001c5fc  pop     rdi
0x14001c5fd  retn
0x14001c5fe  mov     rcx, cs:Stream; Stream
0x14001c605  test    rcx, rcx
0x14001c608  jz      loc_14001C7EE
0x14001c60e  test    edx, edx
0x14001c610  jz      loc_14001C7EE
0x14001c616  mov     r8d, [rbx+10h]
0x14001c61a  lea     rsi, aD_4; "%d, "
0x14001c621  mov     rdx, rsi; Format
0x14001c624  call    cs:__imp_fprintf
0x14001c62a  mov     r8d, [rbx+14h]
0x14001c62e  mov     rdx, rsi; Format
0x14001c631  mov     rcx, cs:Stream; Stream
0x14001c638  call    cs:__imp_fprintf
0x14001c63e  mov     r8d, [rbx+18h]
0x14001c642  mov     rdx, rsi; Format
0x14001c645  mov     rcx, cs:Stream; Stream
0x14001c64c  call    cs:__imp_fprintf
0x14001c652  mov     r8d, [rbx+1Ch]
0x14001c656  mov     rdx, rsi; Format
0x14001c659  mov     rcx, cs:Stream; Stream
0x14001c660  call    cs:__imp_fprintf
0x14001c666  mov     r8, [rbx+40h]
0x14001c66a  lea     rdi, aI64u; "%I64u, "
0x14001c671  mov     rcx, cs:Stream; Stream
0x14001c678  mov     rdx, rdi; Format
0x14001c67b  call    cs:__imp_fprintf
0x14001c681  mov     r8, [rbx+48h]
0x14001c685  mov     rdx, rdi; Format
0x14001c688  mov     rcx, cs:Stream; Stream
0x14001c68f  call    cs:__imp_fprintf
0x14001c695  mov     r8, [rbx+50h]
0x14001c699  mov     rdx, rdi; Format
0x14001c69c  sub     r8, [rbx+58h]
0x14001c6a0  mov     rcx, cs:Stream; Stream
0x14001c6a7  call    cs:__imp_fprintf
0x14001c6ad  mov     r8, [rbx+68h]
0x14001c6b1  mov     rdx, rdi; Format
0x14001c6b4  mov     rcx, cs:Stream; Stream
0x14001c6bb  call    cs:__imp_fprintf
0x14001c6c1  mov     r8d, [rbx+20h]
0x14001c6c5  mov     rdx, rsi; Format
0x14001c6c8  mov     rcx, cs:Stream; Stream
0x14001c6cf  call    cs:__imp_fprintf
0x14001c6d5  mov     r8d, [rbx+24h]
0x14001c6d9  mov     rdx, rsi; Format
0x14001c6dc  mov     rcx, cs:Stream; Stream
0x14001c6e3  call    cs:__imp_fprintf
0x14001c6e9  mov     r8d, [rbx+28h]
0x14001c6ed  mov     rdx, rsi; Format
0x14001c6f0  mov     rcx, cs:Stream; Stream
0x14001c6f7  call    cs:__imp_fprintf
0x14001c6fd  mov     r8d, [rbx+2Ch]
0x14001c701  mov     rdx, rsi; Format
0x14001c704  mov     rcx, cs:Stream; Stream
0x14001c70b  call    cs:__imp_fprintf
0x14001c711  mov     r8d, [rbx+30h]
0x14001c715  mov     rdx, rsi; Format
0x14001c718  mov     rcx, cs:Stream; Stream
0x14001c71f  call    cs:__imp_fprintf
0x14001c725  movsx   r8d, word ptr [rbx+70h]
0x14001c72a  lea     rdi, aHd; "%hd, "
0x14001c731  mov     rcx, cs:Stream; Stream
0x14001c738  mov     rdx, rdi; Format
0x14001c73b  call    cs:__imp_fprintf
0x14001c741  mov     r8d, [rbx+38h]
0x14001c745  mov     rdx, rsi; Format
0x14001c748  mov     rcx, cs:Stream; Stream
0x14001c74f  call    cs:__imp_fprintf
0x14001c755  movsx   r8d, word ptr [rbx+72h]
0x14001c75a  mov     rdx, rdi; Format
0x14001c75d  mov     rcx, cs:Stream; Stream
0x14001c764  call    cs:__imp_fprintf
0x14001c76a  movsx   r8d, word ptr [rbx+74h]
0x14001c76f  mov     rdx, rdi; Format
0x14001c772  mov     rcx, cs:Stream; Stream
0x14001c779  call    cs:__imp_fprintf
0x14001c77f  movsx   r8d, word ptr [rbx+76h]
0x14001c784  mov     rdx, rdi; Format
0x14001c787  mov     rcx, cs:Stream; Stream
0x14001c78e  call    cs:__imp_fprintf
0x14001c794  movsx   r8d, word ptr [rbx+78h]
0x14001c799  mov     rdx, rdi; Format
0x14001c79c  mov     rcx, cs:Stream; Stream
0x14001c7a3  call    cs:__imp_fprintf
0x14001c7a9  movsx   r8d, word ptr [rbx+7Ah]
0x14001c7ae  mov     rdx, rdi; Format
0x14001c7b1  mov     rcx, cs:Stream; Stream
0x14001c7b8  call    cs:__imp_fprintf
0x14001c7be  movsx   r8d, word ptr [rbx+7Ch]
0x14001c7c3  mov     rdx, rdi; Format
0x14001c7c6  mov     rcx, cs:Stream; Stream
0x14001c7cd  call    cs:__imp_fprintf
0x14001c7d3  mov     r8d, [rbx+80h]
0x14001c7da  lea     rdx, aD_2; "%d\n"
0x14001c7e1  mov     rcx, cs:Stream; Stream
0x14001c7e8  call    cs:__imp_fprintf
0x14001c7ee  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x14001c7f5  call    cs:__imp_RtlEnterCriticalSection
0x14001c7fb  mov     rax, [rbx]
0x14001c7fe  cmp     [rax+8], rbx
0x14001c802  jnz     short loc_14001C84E
0x14001c804  mov     rdx, [rbx+8]
0x14001c808  cmp     [rdx], rbx
0x14001c80b  jnz     short loc_14001C84E
0x14001c80d  mov     [rdx], rax
0x14001c810  lea     rcx, qword_140082228
0x14001c817  mov     [rax+8], rdx
0x14001c81b  mov     rax, cs:qword_140082228
0x14001c822  cmp     [rax+8], rcx
0x14001c826  jnz     short loc_14001C84E
0x14001c828  mov     [rbx+8], rcx
0x14001c82c  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x14001c833  mov     [rbx], rax
0x14001c836  mov     [rax+8], rbx
0x14001c83a  mov     cs:qword_140082228, rbx
0x14001c841  call    cs:__imp_RtlLeaveCriticalSection
0x14001c847  xor     eax, eax
0x14001c849  jmp     loc_14001C5EE
0x14001c84e  mov     ecx, 3
0x14001c853  int     29h; Win8: RtlFailFast(ecx)
```
